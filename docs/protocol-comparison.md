# RWA protocol comparison matrix
**Snapshot:** 20 November 2026 | **Purpose:** Illustrative research comparison, not a ranking or investment recommendation.

## At-a-glance
| Dimension | Ondo OUSG | Centrifuge | Maple syrupUSDC |
|---|---|---|---|
| Compared entity | Specific tokenized fund product | Infrastructure for multiple tokenized products | Specific institutional lending-pool product |
| Underlying exposure | Short-term US government securities-related exposure through fund holdings | Varies by pool | Institutional loans |
| Wrapper | Limited partnership interests in a US 3(c)(7) fund, per issuer page | Depends on each pool's legal documents and share class | Depositor share in lending pool; consult current product docs for exact rights |
| Access | Eligibility/onboarding restrictions | Pool-specific allowlists and transfer rules | Product and jurisdiction-specific access |
| Yield source | Underlying portfolio income, net of fees/expenses | Depends on pool assets | Interest paid by institutional borrowers |
| Redemption | Issuer advertises instant mint/redemption subject to terms | Synchronous or request-based/asynchronous depending on vault | Depends on pool liquidity and withdrawal terms |
| Main counterparties | Fund, underlying funds/assets, custodian, administrator | Pool manager, issuer, custodian, servicer, valuation and network providers | Borrowers, collateral/custody/liquidation and pool service providers |
| Contract focus | Token proxy, transfer restrictions, admin/upgrade controls | Share token, vaults, transfer hooks, hub/spoke messaging | Pool contracts, share token, router and withdrawal logic |
| Primary diligence | Fund rights, underlying holdings, eligibility, fees, redemption | Pool terms, NAV, share-class waterfall, servicing | Borrower credit, collateral, concentration, liquidation and liquidity |

## Product notes

### Ondo OUSG
Issuer page identifies OUSG as limited partnership interests in a US-domiciled 3(c)(7) fund offered under Rule 506(c). It lists a $5,000 minimum mint/redemption and exposure including BUIDL, USDC and bank deposits. Recheck current terms and offering documents.
Source: https://ondo.finance/ousg

### Centrifuge
Centrifuge is infrastructure, not one uniform asset. Documentation describes pools, share classes, share tokens, vaults, onchain NAV and configurable investor access. Pool assets and legal structures vary.
Sources:
- https://docs.centrifuge.io/user/concepts/pools/
- https://developer.centrifuge.io/getting-started/how-it-works/product-onchain/

### Maple syrupUSDC
Maple describes syrupUSDC as a yield-bearing token representing a depositor's share in a pool of institutional loans. Maple says its value derives from underlying loan assets rather than being backed by USDC itself. Credit and principal-loss risk remain.
Sources:
- https://maple.finance/transparency/products/syrupusdc
- https://maple.finance/transparency

## How to maintain this matrix
- Compare product with product and infrastructure with infrastructure.
- Add legal entity, jurisdiction, contract, auditor, custodian, NAV cadence, fee schedule and redemption terms only when supported by evidence.
- Mark unknown fields Not verified; do not infer missing facts.
- Revisit monthly and after material product or contract changes.

## Limitations
First-pass desk research from public product and developer pages. This is not independent verification of reserves, legal enforceability, collateral ownership, audits or service-provider arrangements.