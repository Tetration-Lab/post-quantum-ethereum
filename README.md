# Post Quantum Ethereum

> This is a work originated from [Scaling Ethereum 2024](https://ethglobal.com/events/scaling2024) hackathon project called [Quasar](https://github.com/Tetration-Lab/quasar)

Welcome to the Post Quantum Ethereum GitHub repository!

In an era where cryptographic security is of paramount importance, the traditional cryptographic algorithms used in Ethereum and other blockchain platforms are being scrutinized for their resilience against quantum computing threats. As quantum computers continue to evolve, their potential to break widely-used cryptographic schemes poses a significant risk to the security of blockchain networks.

Post Quantum Ethereum aims to explore, research, and implement post-quantum cryptographic algorithms and solutions to safeguard Ethereum and its ecosystem against future quantum threats. This repository serves as a collaborative platform for developers, researchers, and enthusiasts interested in advancing the state of quantum-resistant technologies within the Ethereum network.

## Why Post Quantum?

The rise of quantum computing brings both opportunities and challenges. While quantum computers promise to revolutionize various industries with their computational power, they also threaten the cryptographic foundations that underpin the security of blockchain technologies like Ethereum.

By transitioning to post-quantum cryptographic algorithms, Ethereum can maintain its security and integrity in a quantum-computing landscape, ensuring that transactions, smart contracts, and user data remain secure and uncompromised.

## Quantum Emergency Response: Hard-Fork to Protect User Funds

[Link to the research](https://ethresear.ch/t/how-to-hard-fork-to-save-most-users-funds-in-a-quantum-emergency/18901/1)

One of the ongoing research efforts in this repository focuses on "How to hard-fork to save most users’ funds in a quantum emergency." This research proposes a structured Ethereum Improvement Proposal (EIP) to hard-fork the chain in response to a quantum emergency, aiming to revert blocks, disable traditional EOA transactions, enable smart contract wallet transactions, and introduce a quantum-resistant transaction type using STARK proofs for enhanced security and user fund protection.

## How Can You Contribute?

We welcome contributions from all interested parties! Whether you're a developer, researcher, or simply passionate about blockchain security. Please open the pull-request for additional link in this `README.md` or add a directory in `/project/` about your project!

## Projects

### Signature Scheme

- [Dilithium Solidity](https://github.com/Tetration-Lab/dilithium-solidity)
- [Lamport Solidity](https://github.com/Tetration-Lab/lamport-solidity)
- [Falcon Solidity](https://github.com/Tetration-Lab/falcon-solidity)

### Account Abstraction
- [Quasar](https://github.com/Tetration-Lab/quasar) and [Quasar Learning And Writeup](https://github.com/Tetration-Lab/post-quantum-ethereum/blob/main/projects/quasar.md)
