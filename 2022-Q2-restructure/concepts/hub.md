- What is the Hub

> THIS IS STILL A DRAFT : The Polywrap Hub is a web application that leverages the polywrap core toolchain. The hub is designed to allow anyone to publish, browse and interact with any wrappers directly from a web browser. 
> 
> The vision of the hub is to be an open tool for anyone to create, use, and share wrappers. Furthermore, the goal of this hub and interface is to have all imaginable wrappers readily available for people to use. 
>
> In order to use a wrapper from the hub or see its functions, one can use the specific IPFS hash and paste it into the hub (see below). IPFS is a distributed system for storing and accessing files, websites, applications, and data. Following, the related wrapper appears, and followingly it shows the data that can be read from the blockchain with it and what can be changed on the blockchain through the wrapper. 
>
> Our hub can be found here, whilst it is still under development there are already a few fully-developed wrappers integrated with the hub, for example, the ENS (Ethereum Name Service) wrapper was the first one created. Some wrappers can already be tested today, for example, the Avalanche wrapper or ENS wrapper. 
>
> The ENS wrapper 
> The protocol for the “.eth” domains is essentially a contract that has multiple functions. What the ENS wrapper allows is the interaction with the functions of the contract. Hence instead of having to employ one’s own instance for the wrapper, or creating an application simply to run the wrapper, polywrap instead leverages the client on the site. 


- How is the Hub built today (compilation of the technical architecture and architecture diagrams)
> see: https://user-images.githubusercontent.com/1008882/161544640-6a7f535d-69a8-4512-b7dd-9dd0258f7b45.png

- Publishing on the hub (process overview, some screenshots and links)
> TBD

- Browsing wrappers (simple process and screenshots of the functionality)
> TBD

- What is the Playground? (explain how we- are leveraging the polywrap js client, and all of the features within the playground)
> The easiest way to try a wrapper will be through the Playground. In order to use a wrapper from the hub or see its functions, one can use the specific IPFS hash or ENS domain and paste it into the "URI" field of the Playground. IPFS is a distributed system for storing and accessing files, websites, applications, and data. Following, the related wrapper appears, and followingly it shows the data that can be read from the blockchain with it and what can be changed on the blockchain through the wrapper. 


- How to query any wrapper from the hub using the playground (link back to specific sections in the doc which go in depth into how to formulate a proper query to a wrapper)
> TBD

- Sample use-cases 
>   - swapping a token on uniswap v3
>   - configuring an ENS domain on a testnet
>   - checking the price of a token through the coingecko wrapper
>   - using defiwrapper to know the balance of any eth address )

- List of cases for when using the hub is more convenient than launching a local environment
> If you just need to query a static value, or there are recipes available to execute from the playground
> - Checking the price of a token on a uniswap pool
> - Approving a token
> - Getting an estimate of your account balance with defiwrapper

- Tips to using the hub for developing on web3
> Begin with getting familiar with [GraphQL Syntax]() which is used to interact with all of the endpoints built into the wrappers. It's a simple interface language that bases itself on Query and Mutation modules. 
> Understand the different types of URIs you can create for wrappers
> Bridging Web2 and Web3: Since we're able to query web3 protocols and also leverage web2 tools like the HTTP plugin, you can essentially integrate decentralised protocols with web2 virtually any architecture. If you have a service working with a REST API, like [Twitter](https://developer.twitter.com/en/docs/twitter-api) for example, you can integrate this with any other wrapper directly, so the possibilities are endless.

- Avoid getting rekt : Using the hub securely *(dont query wrappers that you dont trust, they can control your wallet and steal all of your funds)
> Just like on any other product, there is risk associated with the human factor. Since these wrappers are able to bundle any logic, you have to be careful when using code that has not been audited, reviewed, or closed source. Avoid querying wrappers you dont know about or approving tokens through them, as this may end to loss of funds. Feel free to [ask around the community](https://discord.gg/BDqantrZ5w) to verify if a wrapper is you're about to use is legit or not.
