# The Polywrap Client

The Polywrap Client allows developers to integrate wrappers into their applications. Wrappers can be written as WebAssembly modules, or as plugins in any client supported language. Developers can call into any wrapper by simply knowing its URI. The developer experience is similar to interacting with a web service, but the magic is that it's all executing right within your application.

## Supported Languages

| Language | Support | Release | Source |
| ------- | ------- | ------- | ------- | 
| JavaScript | Live | [npm](https://www.npmjs.com/package/@web3api/client-js) | [GitHub](https://github.com/polywrap/monorepo/tree/prealpha/packages/js/client) |
| Rust | TBD | N/A | N/A |
| Python | TBD | N/A | N/A |
| Go | TBD | N/A | N/A |
| C# | TBD | N/A | N/A |
| Java | TBD | N/A | N/A |
| Swift | TBD | N/A | N/A |

## Installation and Instantiation

The Polywrap Client is available on popular package managers.
```
npm install @web3api/client-js
```

To use it, import and construct an instance of the Web3ApiClient class.

```typescript
import { Web3ApiClient } from '@web3api/client-js';

const client = new Web3ApiClient();
```

## Configuration

The Client accepts a `ClientConfig` argument at construction. The default configuration can be modified to use different plugins, Ethereum providers, IPFS providers, and more.

```typescript
ClientConfig<TUri extends Uri | string = string> {
  redirects: UriRedirect<TUri>[];
  plugins: PluginRegistration<TUri>[];
  interfaces: InterfaceImplementations<TUri>[];
  envs: Env<TUri>[];
  uriResolvers: UriResolver[];
}
```
The Client's configuration can also be modified when querying a wrapper or plugin, so that each call can be made with a specific Client context.

### Redirects

The `redirects` property can be used to change the URI resolution process by redirecting queries from one URI to another. This redirection occurs in all queries to the URI, even in cases where one wrapper calls another during its execution.

```typescript
export interface UriRedirect<TUri = string> {
  from: TUri;
  to: TUri;
}

```

### Plugins

Polywrap plugins are written in a Client’s native language. They offer a user experience similar to that of wrappers, but with different benefits.

Plugins are declared and constructed in the Client config by providing an array of `PluginRegistration`. Each `PluginRegistration` contains the URI at which the plugin will be queried and a `PluginPackage`.

```typescript
export interface PluginRegistration<TUri = string> {
  uri: TUri;
  plugin: PluginPackage;
}
```

### Interfaces

Users can declare custom a implementation for a core interface by providing the interface URI and the URIs at which the implementations can be queried.

```typescript
export interface InterfaceImplementations<TUri = string> {
  interface: TUri;
  implementations: TUri[];
}
```

### Envs

Because wrapper calls are sandboxed and stateless, they cannot access the global state that persists outside the call. Users can instead provide wrapper-specific environmental variables in the Client configuration. Wrapper developers are expected to inform users which environmental variables should be set for their API.

```typescript
export interface Env<TUri = string> {
  /** Uri of Web3Api */
  uri: TUri;

  /** Env variables shared by both mutation and query */
  common?: Record<string, unknown>;

  /** Env variables specific to mutation module */
  mutation?: Record<string, unknown>;

  /** Env variables specific to query module */
  query?: Record<string, unknown>;
}
```

### Uri Resolvers

Users can extend the Client's URI resolution capabilities by provider new implemenations of `UriResolver`. A `UriResolver` takes a URI as input and resolves it to a wrapper or plugin.

By default, the Client includes an ExtendableUriResolver that can accept ENS, IPFS, and filesystem URIs as input and fetch wrappers from those sources. It is "extendable" in the sense that it works with any plugin or wrapper that implements the `UriResolverInterface`. The Client's default resolvers can also resolve URI's that point to redirects, plugins, and cached wrappers.

```typescript
export abstract class UriResolver {
  public abstract get name(): string;

  public abstract resolveUri(
    uri: Uri,
    client: Client,
    cache: ApiCache,
    resolutionPath: UriResolutionStack
  ): Promise<UriResolutionResult>;
}
```

### Default Configuration

The current default `ClientConfig` for the JavaScript implementation of the PolywrapClient can be viewed on [Github](https://github.com/polywrap/monorepo/blob/prealpha/packages/js/client/src/default-client-config.ts). When a user provides a `ClientConfig` to the Client, the default configuration is still applied but is modified by the user's configuration.

## Sanitization

The Client's configuration is *sanitized* when the Client is constructed. During the sanitization process, URI strings are validated and transformed into instances of the `Uri` class.