## Chain ID Clarification for Wormhole Relayer Contracts

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

### Conclusion

Understanding and correctly applying these Chain IDs ensures smooth and accurate cross-chain communication within your decentralized application. If you have any questions or encounter issues, please refer to the Wormhole documentation or reach out to our support team.

---

This section should be included in your documentation to help other developers understand the important distinction between these IDs.