# Outline

## Introduction

## Quick Start:
High-level guides that help developers hit the ground running. These should be able to be used by all types of developers to get started right away, and link to external documentation if devs want to dive deeper.

### Try Existing Wrappers
  * Hub
  * CLI
  * Client

### Integrating Wrappers
  1. Setup Client
      * Client
      * Configurations
      * Sanitization
  2. Configure Plugins
  3. Import Dependencies
      * Known
        * Import Wrappers
        * Generate Types
      * Unknown
        * Runtime Validation
  4. Invoke Wrappers
  5. Using Interfaces
      * Get Implementations
      * Invoking Implementations

### Building Wrappers
  1. Schema
      * Dependency Imports
      * Custom Types & Functions
  2. Implementation
      * Languages
      * Bindings
      * Custom Types
      * Function Signatures
      * Imported Types
      * Imported Functions
  3. Build
      * Build Pipeline Overview
      * Presets
      * Configuration
      * Roll Your Own
  4. Test
      * Recipes
      * Custom E2E Tests
      * Infrastructure
  5. Metadata
      * Meta Manifest
      * Content Restrictions
  6. Deploy
      * Deploy to IPFS
      * Deploy to Filecoin
      * IPFS
      * Fleek
      * Pinata
  7. Publish
      * Publish IPFS hash to ENS
      * Publish IPFS hash to Tezos domains
      * Publish ENS domain to another DNS
      * Publish Filecoin URI to Tezos
      * Publish IPFS hash to Polywrap Registry
      * ENS
      * Hub

### Defining Wrapper Interfaces
  0. Description
      * Brief Intro -> Concepts_Interface
  1. Interface Schema
      * Dependency Imports
        * Rules
      * Custom Types & Functions
  2. Build
  3. Deploy
  4. Publish
      * Implementation Registries
  5. Implement
      * Interface Template Projects
      * Importing Interface Schemas
      * Implement Types
      * Register Implementation
  6. Integrate Interface Wrappers
      * Get Implementations
      * Invoke Implementation


### Building Plugins
  1. Schema
      * Dependency Imports
      * Custom Types & Functions
  2. Generate Types
  3. Implementation

## Concepts
Underlying concepts that are necessary to understand the why/what/how of Polywrap. These should hopefully give enough context so that readers can go from here straight into any of the other sections (quick start, reference, standards).

### WRAP Protocol
  ...

### Polywrap
  ...

### Wrapper
  ...

### URI
  ...

### Client
  ...

### Plugin
  ...

### Interface
  ...

### Hub
[concepts/hub.md](./concepts/hub.md)  

## Demos
Glossary of existing demos (apps & wrappers) for readers to look through.

## Reference
This will be the most "low level" documentation, most of which can hopefully be automated to some degree. We will detail the ins-and-outs of our various tools (cli, client, etc), file formats (manifests, etc), and various technical specifications Polywrap makes use of (WebAssembly, WRAP, etc) 

### CLI
...

### Clients
...

### Manifests
...

### Specifications
...

