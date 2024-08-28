## Valid Tokens and TokenBridge

### Overview

To facilitate token transfers between chains using Wormhole, you need to utilize the Wormhole TokenBridge. Before you can send tokens using the methods provided, it is essential to ensure that the token is attested onto the TokenBridge contract on the target blockchain.

### Attesting Tokens

To send a token between chains, the token must be attested to the TokenBridge contract on the destination blockchain. In the example provided, when you run `npm run deploy`, a mock token contract is deployed and attested on the target chain's TokenBridge contract.

#### Attesting Tokens

If you need to attest a token yourself, you can use the `attestWorkflow` function. This function allows you to add your token to the TokenBridge.

### Checking Token Status

To verify whether a token is already attested on the TokenBridge, use the `wrappedAsset(uint16 tokenChainId, bytes32 tokenAddress)` function on the TokenBridge contract. This function will return:

- The address of the wrapped token on the current blockchain if the token is attested.
- The zero address (`0x0000000000000000000000000000000000000000`) if the token has not been attested yet.

### Missing 

### 

How to attest token on more then 1 chain ?
How to deploy token on more than 1 chain ?

### TokenBridge Contract Address

As of now, the TokenBridge contract addresses are not specified.

### Using TokenBridge with Remix

Looking for simple remix version


This improved README section should guide users on attesting tokens, checking their status, and using Remix for interacting with TokenBridge contracts. It also acknowledges the lack of specific contract addresses and directs users to official resources for further information.