# Oracles, Attestations, and Proof in RWA

A blockchain can record transactions and execute rules, but it cannot independently know whether an off-chain event occurred. RWA systems therefore need ways to bring external information into the on-chain environment.

## What is an oracle?

An oracle is infrastructure that delivers external data to a smart contract. Depending on the design, it may provide prices, interest rates, reserve information, payment status, or other real-world facts.

Examples:
- A price feed used to calculate the value of collateral
- An interest-rate feed used by a lending product
- A report of a loan payment or default
- A data feed supporting a fund's NAV process

## A simplified data flow

1. An event occurs off-chain—for example, a borrower makes a loan payment.
2. A source system records the event, such as a bank, servicer, custodian, or administrator.
3. A data provider or attestor obtains and checks the information.
4. An oracle transmits a signed or otherwise authenticated update.
5. A smart contract consumes the update and performs an allowed action.
6. Reports and reconciliation processes help users compare on-chain records with off-chain evidence.

The smart contract can verify that data arrived in an expected format or from an authorized signer. It cannot automatically prove that the original off-chain source was truthful.

## Oracle design questions

- Who operates the data source?
- Is there one source or multiple independent sources?
- How are data errors detected and corrected?
- How often are updates published?
- What happens when data is stale or unavailable?
- Are timestamps and source identifiers recorded?
- Can an administrator override the feed?
- Who is accountable for incorrect information?

## Proof of reserves and attestations

A proof-of-reserves report may provide evidence about assets held by a custodian or issuer at a point in time. Its scope matters.

Check:
- What assets and liabilities are included?
- What date and time does the report cover?
- Who performed the verification?
- Does it cover ownership, control, and encumbrances?
- Are liabilities and off-balance-sheet obligations considered?
- Is the report continuous or only a snapshot?

A reserve attestation is not necessarily a full financial-statement audit, legal-title opinion, or guarantee of redemption.

## Different evidence answers different questions

| Evidence | What it may help establish | What it does not automatically establish |
|---|---|---|
| On-chain transaction | A transaction was recorded on a chain | Truth of the off-chain event |
| Smart-contract audit | Review of specified code and scope | Absence of all vulnerabilities |
| Proof of reserves | Evidence about specified reserves at a stated time | Full solvency or legal ownership |
| Financial audit | Opinion on financial statements under a defined scope | Real-time asset status |
| Valuation report | Estimated value under a methodology | Immediate sale price |
| Custodian statement | Records held by a custodian | Independent proof of every legal right |
| Oracle update | Data was delivered by a configured source | Truthfulness of the original source |

## Example: loan repayment

A loan repayment can involve a borrower, payment processor, bank account, servicer, issuer, data provider, oracle, and smart contract. A robust design documents each handoff and explains how failed, reversed, late, or disputed payments are handled.

## Core principle

On-chain transparency is valuable, but it is only one part of verification. Strong RWA diligence connects blockchain records to credible off-chain evidence, clear legal rights, and accountable service providers.
