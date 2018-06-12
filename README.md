# okta-vault-signer
Client-side JS code for crypto-signing a transaction with a private key stored in Hashicorp Vault, authenticated via Okta MFA.

## Motivation
We want to make it painless for people to keep their crypto private keys inside of Hashicorp Vault, and that means creating client-side Vault integrations.  This will eventually end up living inside of a website version of the Mist Browser, so we need JS.

## Implementation Overview
At the end of the day, we just need some API glue and a form which gathers a few key variables:

- `VAULT_KEYNAME`: Which key would you like to sign with in Vault?
- `VAULT_ADDR`: What address can we reach your Vault deployment at?
- `OKTA_USERNAME`: Username for your Okta account to authenticate with Vault.
- `OKTA_PASSWORD`: Password for your Okta account to authenticate with Vault.

The Okta password is required to begin authenticating via Vault's connection.  Additional auth requirements (e.g. SSO, Social Logins) will be setup on the account within Okta.


## Next Steps
- [ ] Explore how Okta multi-factor authentication is triggered by a Vault API call.
- [ ] Fork the `ethereumjs-tx` lib so we can add our own `verifySignature()` method.
- [ ] Design rough form GUI for key variables.
- [ ] Nail down user flow for how exactly a user will create the transaction that gets sent to this code.

## Useful Links
- [ethevents](https://github.com/brainbot-com/ethevents/tree/master/ethevents)
- [ethjs](https://github.com/ethjs/ethjs)
- [eth-json-rpc](https://github.com/kumavis/eth-json-rpc-infura/blob/master/src/index.js#L119)
- [MetaMask Provider Engine](https://github.com/MetaMask/provider-engine)
- [web3 Provider Engine](https://www.npmjs.com/package/web3-provider-engine)
