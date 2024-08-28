Certainly! Below is the revised README section with the added code snippet:

---

## Chain ID Clarification for Wormhole Relayer Contracts

[Wormhole Hello Wormhole Tutorial](https://docs.wormhole.com/wormhole/quick-start/tutorials/hello-wormhole/hello-wormhole-explained)

### Overview

When working with cross-chain applications using the Wormhole Relayer, it’s crucial to understand the difference between Wormhole's internal Chain IDs and the standard blockchain Chain IDs. This distinction is important for correctly configuring and interacting with the Wormhole Relayer across various test networks.

### Wormhole Chain IDs vs. Standard Chain IDs

In the context of the Wormhole network:

- **Wormhole Chain ID**: This ID is specific to the Wormhole protocol and is used internally by Wormhole to identify different blockchain networks.
- **Standard Chain ID**: This is the widely recognized Chain ID used by the broader blockchain community to distinguish between different networks (e.g., BSC, Polygon, Avalanche).

### Testnet Deployment Information

Below are the relevant Chain IDs and contract addresses for the Wormhole Relayer deployed on various test networks. **Ensure you use the correct Wormhole Chain ID for Wormhole-specific interactions and the Standard Chain ID for blockchain-specific configurations.**

| Network           | Wormhole Chain ID | Standard Chain ID | Wormhole Relayer Contract Address                         |
|-------------------|-------------------|-------------------|-----------------------------------------------------------|
| **BSC Testnet**    | 4                 | 97                | `0x80aC94316391752A193C1c47E27D382b507c93F3`              |
| **Polygon Testnet**| 5                 | 80001             | `0x0591C25ebd0580E0d4F27A82Fc2e24E7489CB5e0`              |
| **Avalanche Testnet (Fuji)**| 6       | 43113             | `0xA3cF45939bD6260bcFe3D66bc73d60f19e49a8BB`              |
| **Celo Testnet**   | 14                | 44787             | `0x306B68267Deb7c5DfCDa3619E22E9Ca39C374f84`              |
| **Moonbeam Testnet**| 16               | 1287              | `0x0591C25ebd0580E0d4F27A82Fc2e24E7489CB5e0`              |

### Key Points

- **Use Wormhole Chain IDs** when configuring cross-chain interactions within the Wormhole protocol.
- **Use Standard Chain IDs** for general blockchain operations, such as deploying contracts or setting up connections to the blockchain.

### Example Usage

When sending a message from BSC Testnet to Polygon Testnet via the Wormhole Relayer:

- Specify `4` as the target chain ID (Wormhole Chain ID for BSC Testnet) in the Wormhole-specific function calls.
- For general blockchain operations on BSC Testnet, use `97` (Standard Chain ID).

### Wormhole Relayer Contract Functions

Here are the key functions from the Wormhole Relayer contract that are used to send messages across chains:

```solidity
function sendPayloadToEvm(
    uint16 targetChain,
    address targetAddress,
    bytes memory payload,
    uint256 receiverValue,
    uint256 gasLimit
) external payable returns (uint64 sequence);

function quoteEVMDeliveryPrice(
    uint16 targetChain,
    uint256 receiverValue,
    uint256 gasLimit
) external view returns (uint256 nativePriceQuote, uint256);
```

- **sendPayloadToEvm**: Sends a payload (message/data) to a specified contract on a target chain.
  - `targetChain`: The Wormhole Chain ID of the destination chain.
  - `targetAddress`: The contract address on the destination chain.
  - `payload`: The data/message to send.
  - `receiverValue`: The amount of native currency (if any) to send with the message.
  - `gasLimit`: The gas limit for executing the message on the target chain.
  - **Returns**: `sequence` - A unique identifier for the message.

- **quoteEVMDeliveryPrice**: Provides a quote for the delivery price in native currency.
  - `targetChain`: The Wormhole Chain ID of the destination chain.
  - `receiverValue`: The amount of native currency (if any) to send with the message.
  - `gasLimit`: The gas limit for executing the message on the target chain.
  - **Returns**: 
    - `nativePriceQuote`: The cost in the native currency of the source chain to deliver the message.
    - An additional value related to the quote.

---

This section should be included in your documentation to help other developers understand the important distinction between these IDs and to provide them with the necessary code references.