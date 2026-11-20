# Smart-contract research playbook for RWAs
A practical guide to inspecting an RWA token or vault without confusing onchain visibility with proof of offchain backing.

## 1. Establish contract identity
1. Find the address in the issuer's official documentation.
2. Confirm network and product name.
3. Cross-check in the relevant block explorer.
4. Record source URL and date checked.
5. Identify whether the address is a proxy, implementation, vault, router or share token.

Never treat an address from an aggregator or social post as authoritative.

## 2. Inspection checklist
| Area | Inspect | Why it matters |
|---|---|---|
| Source verification | Verified source, compiler, constructor args | Enables reproducible review |
| Proxy | Proxy type, implementation, beacon | Logic may change while address stays fixed |
| Admin roles | Owner, proxy admin, role holders, multisig | Identifies privileged control |
| Upgradeability | Upgrade functions, timelocks, emergency powers | Determines who can change behavior |
| Mint/burn | Authorized minters, caps, pause conditions | Controls token supply |
| Transfers | Allowlist, blacklist, freeze controls | Transfers may be restricted |
| Fees | Fee setters and recipients | Economics may change |
| Pausing | Pause authority and scope | Can interrupt operations |
| Oracles | Source, update cadence, stale-data checks | Bad data can affect NAV or settlement |
| External calls | Routers, bridges, callbacks | Expands attack surface |
| Events | Mint, burn, role changes, upgrades, pause | Supports monitoring |

## 3. Worked starting point: OUSG on Ethereum
Public explorer page identifies the Ethereum OUSG token at:
0x1b19c19393e2d034d8ff31ff34c81252fcbbee92

Explorer: https://etherscan.io/token/0x1b19c19393e2d034d8ff31ff34c81252fcbbee92
Issuer product page: https://ondo.finance/ousg

The explorer labels this token contract as a proxy and exposes an implementation reference. This is only a starting point. Reconfirm the address with current issuer documentation, then inspect proxy standard, implementation, upgrade administrator, verified source, privileged roles, transfer restrictions and recent upgrade/role/mint/burn/pause events.

## 4. What onchain analysis cannot prove
A token contract alone cannot establish that an underlying asset exists or is unencumbered, that legal title is valid, that a custodian is solvent, that a borrower will repay, that NAV is accurate, or that a redemption will settle on time. Those questions require legal documents, attestations, audits, custody evidence and operational testing.

## 5. Research output template
For every contract, publish product/issuer, network/address, source/date, contract type, proxy status, implementation, admin and roles, mint/burn/pause/transfer controls, upgrade/timelock, oracle dependencies, audit scope, notable events, unanswered questions and confidence level.

## 6. Safe research practice
Prefer read-only explorer and RPC queries. Do not connect a wallet, sign transactions, approve tokens or interact with an unfamiliar contract merely to inspect it. This repository is educational, not a smart-contract audit.