<div align="center">

# Atheron · ATON

**A GhostDAG Layer 1 with two mining lanes, two virtual machines, and a GPU network that mines and computes at the same time.**

[aton-network.org](https://aton-network.org) · Building in the open, closed to outside pull requests until the spec settles

</div>

---

## Read this before opening a pull request

**We are not accepting outside pull requests right now.**

Any pull request from outside the core team will be closed without review, and the branch removed from our forks. That sounds blunt written down, so here is the actual reason.

Atheron is pre-testnet. Consensus parameters are unfixed, the cross-VM router interface changes most weeks, and five of these repositories contain contracts that will move real value and are scheduled for independent third-party audit. Taking outside changes into that codebase right now means either we merge code that nobody can properly review yet, or we leave a contributor's work sitting open for months. Neither is a good outcome for anyone.

This is temporary and it has a defined end. When the protocol specification is stable and the first audits come back, the repositories marked for public release open up with real contribution guidelines, a review rota, and maintainers who can actually give your work the time it deserves.

**Security reports are the exception and are always welcome.** Email security@aton-network.org rather than filing an issue. See the security policy in any repository for what to include.

---

## What is being built

**Atheron Chain.** GhostDAG ordering, targeting a high block rate from genesis rather than starting slow and upgrading later. Two independent proof-of-work lanes, one for ASICs and one built to be memory-hard on GPUs, with independent difficulty retargeting and a dampener so neither lane can dominate the other. Account-based state rather than UTXO, because a real smart contract platform needs it.

**Two execution engines.** EVM bytecode runs unmodified, so existing Solidity, MetaMask and Hardhat and Foundry workflows work on day one. Alongside it, a native WASM engine with direct access to protocol precompiles for staking, mining statistics and compute job submission. A router sits between them.

**Compute Mesh.** Consumer and prosumer GPUs earn ATON for two things at once: mining the GPU lane, and running inference jobs. Jobs execute redundantly across staked nodes and a majority has to agree on the result hash before anyone gets paid. It is open to third-party workloads from mainnet, not reserved for our own.

**Atheron AI.** A non-custodial trading agent. Exchange API keys are encrypted and stay on the user's machine, always. It never holds funds and never places a trade of its own. Every decision it produces is committed on-chain as a receipt, so the track record is verifiable by anyone rather than self-reported by us.

**Native DEX.** An order book for major pairs plus AMM pools for the long tail. Spot only at launch. Derivatives are deliberately deferred, not quietly planned.

---

## The repositories

Most of this org is private while we build. Each repository has a stated point at which it becomes public. Two never do.

| | Opens |
|---|---|
| **Chain** consensus · node · vm · mesh | at public testnet or mainnet |
| **Contracts** governance · signal-ledger · compute-mesh-contracts · registries · dex | when their audits complete |
| **Developer** sdk-rs · sdk-ts · spec · docs | at public testnet |
| **Product** desktop · explorer | at mainnet |
| **Product** site · portal · discord · telegram | stays private, these hold billing and moderation internals |
| **atheron-ai** | stays private, permanently |

The trading engine is the one piece we are not open-sourcing. It is the product the subscription pays for and the primary paying customer of the compute network. Everything the chain needs in order to run without us is going public.

---

## What is centralized and what is not

Worth stating plainly, because most projects are vague about it.

**Not ours to switch off:** mining on both lanes, full nodes, consensus, the Compute Mesh including the oracle service, the DEX contracts, the Strategy Marketplace, the Governance Module, the Signal Ledger, and both on-chain registries. None of it depends on a machine we own.

**Ours, and we say so:** this website, subscription billing, and the Discord and Telegram systems. Normal product infrastructure.

**One real exception.** We hold a time-locked multisig safety valve over exactly two components, the tensor-memory-hard mining lane and the cross-VM router, because they are the newest and highest-risk code in the system. It cannot touch anything else. It sunsets at defined thresholds into full community governance. We would rather write that down here than have someone find it in a contract later.

---

## Live build tracker

Progress against the build plan updates on every merge, at **[aton-network.org/build](https://aton-network.org/build)**, alongside a plain-English changelog of what changed, why, and what it means. It is generated from the repositories themselves, not maintained by hand.

---

<div align="center">
<sub>Atheron is a British Columbia corporation. Nothing in this organization is investment advice, and no part of it should be read as a legal opinion on ATON's regulatory status.</sub>
</div>
