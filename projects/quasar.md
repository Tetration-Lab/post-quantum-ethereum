Quasar, an initiative for the Post-Quantum Ethereum Era

Prepare for the Q-day with our Account Abstraction, wallet extension, and three quantum secure signature libraries.

Quasar aims to advance quantum-secure cryptography for production. 

The project comprises three main components: Account Abstraction (AA), a web wallet extension, and three quantum-secure signature libraries.

At its core lies our quantum-secure signature library, which incorporates three selected signature schemes.Our team has adapted the signing algorithm to optimize compatibility on-chain and have implemented verifiers in Solidity.

I) Dilithium Solidity: a lattice-based cryptosystem utilizing Learning With Error (LWE) and Short Integer Solution (SIS) modules. We have tailored the SHA256 component to our keccak256-based XOF function. Our library comprises a Rust signer, a WebAssembly (WASM) signer, and a Solidity verifier.

II) Falcon Solidity: A lattice-based cryptosystem employing a Short Integer Solution (SIS) module over NTRU lattices. Similarly, we have adjusted the SHA256 component to our keccak256-based XOF function. Our library includes a Python signer and a Solidity verifier.

III)Lamport Solidity: A hash-based signature efficiently verifiable on-chain. Our library encompasses a JavaScript signer and a Solidity verifier.

Note: Dilithium and Falcon are both top candidates recognized by the US National Institute of Standards and Technology (NIST).

Next is our Account Abstraction:
Our Account Abstraction feature implements a smart contract wallet supporting authentication with quantum-secure digital signatures.
         
The Browser Extension Wallet enables the utilization of the Account Abstraction feature and quantum-secure signatures in a user experience similar to MetaMask.

Key Finding:

From this initiative, our team has discovered significant findings that would help shape the ecosystem toward the post-quantum era.
Lamport algorithms can efficiently verify on-chain at less than 700K gas. The one-time nature of Lamport can be efficiently mitigated by rotating the key after every transaction. BIP39 can help with UX by deriving each key from a seed phrase. However, the key and signature size, totaling 24 KB, will hurt state growth.
The Dilithium algorithm can also be implemented, but the gas cost is not practical at close to 30M gas per verification. Optimization tricks reduced it from our previous 47M gas, but when combined with other parts of the contract, it exceeds the gas limit of most chains and reverts. Most of the gas is in the NTT and SHAKE256 operations. The signature is 4.5KB, which is significantly better than that of Lamport.
Falcon can also be implemented, but faces a similar challenge. We can reduce the verification gas to around 24M gas and potentially optimize even more. However, the deployment cost exceeds the block gas limit, making it unusable on most chains. The main gas expenditure is also from NTT, while the deployment costs are incurred from storing modulo inverse data. The signature is less than 1 KB, which is the smallest signature so far.
We found that a few tools do not reflect this revert by block gas limit behavior, even when using a chain fork.
Given that the Q day is still far off and algorithms are still making progress, we recommend waiting/monitoring for the time being.
We found that the emergency fork proposed by Vitalik could recover some user funds by changing to STAKE proof of seed phase. This might not be possible for wallets that are generated by other methods. Smart contracts that rely on ECRecover precompile would also break. We recommend more research into the potential impact of Q day and mitigation my plans. We’ll publish our list soon.
NTT and SHAKE256 are part of many algorithms and can be efficiently computed. It might be helpful to add a precompile for them.