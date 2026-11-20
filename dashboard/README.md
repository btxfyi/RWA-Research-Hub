# RWA data dashboard
**Snapshot date:** 20 November 2026

This folder defines a source-first dashboard for tracking tokenized assets. Every metric needs a definition, source URL, observation timestamp and coverage note.

## Dashboard panels
| Panel | Metrics | Suggested source |
|---|---|---|
| Market overview | Distributed value, asset count, change over time | RWA.xyz |
| Asset-class mix | Treasuries, private credit, commodities, real estate | RWA.xyz taxonomy |
| Network distribution | Value and asset count by chain | RWA.xyz + explorers |
| Protocol watchlist | Issuer, product, category, chain, contract | Issuer docs + explorers |
| Holder activity | Holders, transfers, active addresses | Explorers / Dune |
| Product risk | Redemption, restrictions, custody, legal wrapper | Offering documents |
| Data quality | Last updated, missing fields, confidence | Research Hub methodology |

## Measurement rules
1. Keep distributed value, TVL, market capitalization, NAV and trading volume separate.
2. Never aggregate providers unless their definitions and coverage align.
3. Record chain and contract for onchain metrics.
4. Distinguish issuer-reported, provider-indexed and independently computed values.
5. Preserve historical snapshots; do not silently overwrite.
6. Use N/A for missing data, never zero.
7. Treat dashboards as discovery tools, not proof of legal ownership or asset quality.

## CSV schema
Use one row per entity, metric and snapshot. Required fields: snapshot_date, entity_name, entity_type, asset_class, chain, contract_address, metric_name, metric_value, currency, metric_definition, source_name, source_url, retrieved_at, confidence and coverage_notes.

## Starter watchlist
| Protocol/product | Model | Initial research focus | Primary source |
|---|---|---|---|
| Ondo OUSG | Tokenized fund interest | Legal rights, holdings, fees, eligibility, redemption | https://ondo.finance/ousg |
| Centrifuge pools | Fund infrastructure/products | Pool-specific terms, NAV, share classes, vaults | https://developer.centrifuge.io/ |
| Maple syrupUSDC | Institutional credit pool | Borrower risk, collateral, concentration, withdrawals | https://maple.finance/transparency/products/syrupusdc |
| BlackRock BUIDL | Tokenized liquidity fund | Fund documents, transfer agent, eligibility, distribution | https://www.blackrock.com/ |

## Data sources
- RWA.xyz catalog: https://app.rwa-xyz.com/catalog
- RWA.xyz docs: https://docs.rwa.xyz/
- Dune: https://dune.com/
- Etherscan: https://etherscan.io/
- Solscan: https://solscan.io/
- DeFiLlama: https://defillama.com/

## Implementation roadmap
Start with manually reviewed CSV snapshots. Later connect ingestion scripts or APIs to a notebook, static site or BI tool. Keep ingestion separate from presentation so every chart can be audited.