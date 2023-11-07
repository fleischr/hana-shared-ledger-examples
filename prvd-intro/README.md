# Introduction to Provide Platform integration with the Shared Ledger on SAP BTP

The Provide Platform comprises of five open source API microservices and the Shuttle low-code designer. You can also interact with the APIs via the PRVD cli

<b>API Microservices</b>
- Ident
- Vault
- Nchain
- Axiom
- Privacy

<b>Shuttle low-code designer</b>
https://shuttle.provide.services

## Getting Started with API credentials

### Shuttle
See additional docs here

### Postman

Download the PRVD - SAP BTP Shared Ledger Quickstart
See additional docs here

### CLI
Using the Provide CLI, you can easily setup a secure vault instance to secure your Baseledger keys. Baseledger currently supports Ed25519 keys for peer-to-peer authorization and validator keys.

If you have not previously created a Provide user, first create one:

'''prvd users create'''
Next, authenticate using those credentials and create a vault and Ed25519 key:

prvd authenticate
prvd vaults init --name 'SAP BTP Shared Ledger Vault'
prvd vaults keys init

# follow the prompts; control-c to bypass selecting an application and organization

✔ asymmetric
✔ sign/verify
Name:  SAP BTP Shared Ledger key
Description: My first SAP BTP Shared Ledger key
✔ Ed25519
You will see the UUID of the created vault key.

You can choose to adopt usage of a long-dated refresh token for secure convenient access

prvd api_tokens init --organization <org uuid> --offline-access

You can also choose basic auth credentials instead

## Integrating to BTP applications

-[ ] Add destinations to your BTP subaccount/SaaS application for your deployed instance to the Provide APIs
- Replace usage of .env vars and code for public/private keys with PRVD user and Vault
-[ ] Use Provide Vault to create, manage, sign, verify the private/public keys you will use to integrate to the SAP BTP Shared Ledger
-[ ] Experiment with the use of Nchain, Axiom, Privacy and other Provide apps like ProvideSync, the Carbonmark API, and Provide Payments with the SAP Business Blockchain Connector, Shared Ledger and other SAP BTP Blockchain apps. Have fun!

## Benefits

Vault enables a business user within an organization to encrypt/decrypt/sign/verify with a public/private key without revealing the contents of the private key. Workgroups also enable business organizations to create a secure, but also easy to use secure enclave for distributing cryptographic keys between multiple business units.

With the same set of PRVD credentials - the same user, organization and vault can be used across multiple technical contexts (e.g. Typescript, Java, Golang) without the pain of replicating the same sensitive private key data across different applications. 

This simplifies and accelerates an enterprise's ability to adopt the SAP BTP Shared Ledger - among several other enterprise blockchain solutions.

## Examples

Provided with each language example accordingly