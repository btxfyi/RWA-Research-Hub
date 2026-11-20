# Case study: Centrifuge tokenized-fund infrastructure
**Snapshot:** 20 November 2026 | **Category:** Tokenized-fund infrastructure | **Status:** Protocol-level desk research

## What Centrifuge provides
Centrifuge provides infrastructure for creating, operating and distributing tokenized financial products. It is not one single fund or one uniform asset. Each pool represents a product and can contain multiple share classes with distinct terms and tokens.

Docs: https://developer.centrifuge.io/

## Core product components
- **Pool:** onchain product record, balance sheet and share-class structure.
- **Share class:** class of interests with its own terms, pricing and eligibility.
- **Share token:** ERC-20-compatible token representing a share class.
- **Vault:** contract path used to subscribe and redeem.
- **NAV/pricing:** product share price published onchain by the manager.
- **Access controls:** allowlists and transfer hooks can restrict holding or transfers.

A token's existence does not by itself establish the legal nature of the investor's claim. Review the specific pool's legal documents.

## Hub-and-spoke architecture
Current protocol documentation describes a hub-and-spoke model. A hub network handles product operations, accounting, pricing and investment request processing. Spoke networks provide token issuance, transfers and vault interactions. The pool coordinates consolidated accounting and product information across deployments.

This can improve distribution flexibility, but creates cross-chain messaging, synchronization and operational dependencies.

## Standards and composability
Documentation references ERC-20 share tokens, ERC-1404-style transfer restrictions, ERC-4626 synchronous vaults and ERC-7540 asynchronous vaults. Additional standards are used in the evolving vault architecture. Do not assume every pool implements every standard or supports identical deposit and redemption flows. Inspect the exact deployment.

## Pool-level diligence checklist
- Identify legal issuer, fund vehicle and jurisdiction.
- Read offering memorandum and subscription/redemption terms.
- Identify assets, borrowers and concentration.
- Verify custodian, servicer, administrator, auditor and valuation agent.
- Understand share-class priority, loss allocation and fee waterfall.
- Check investor eligibility and transfer restrictions.
- Determine whether deposits/redemptions are synchronous or asynchronous.
- Review NAV source, cadence, stale-price controls and dispute process.
- Map hub/spoke deployments and cross-chain dependencies.
- Review pool-specific audits and deployed contract addresses.

## Balanced assessment
**Potential strengths:** modular fund representation, share classes, configurable access controls, NAV publication, multi-chain distribution and compatibility with established token/vault standards.

**Risks and dependencies:** manager discretion, legal enforceability, asset servicing, NAV accuracy, redemption queues, smart-contract risk, cross-chain coordination and pool-specific counterparty exposure.

Analyze Centrifuge at two levels: shared protocol infrastructure and each individual pool's legal/economic design. A sound architecture does not automatically make every pool low risk.

## Sources
- Protocol overview: https://docs.centrifuge.io/developer/protocol/overview/
- Pools and tokens: https://docs.centrifuge.io/user/concepts/pools/
- Product onchain: https://developer.centrifuge.io/getting-started/how-it-works/product-onchain/
- Standards: https://developer.centrifuge.io/developer/protocol/features/composability/
- Vault architecture: https://developer.centrifuge.io/developer/vault-development-kit/architecture/

Last checked 20 November 2026. Individual pool terms and deployments may change.