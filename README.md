# Elroi
📌 Overview

This smart contract is a SIP-010 token escrow system built in Clarity v2 for the Stacks blockchain.
It is designed to handle trustless agreements between a payer and a payee, with optional involvement of an arbiter.

By deploying this contract, you can securely:

Create new escrow agreements.

Lock funds once pre-funded.

Release payments in full or partially to the payee.

Refund the payer if conditions aren’t met.

Finalize and clean up once the escrow is completed.

This contract is audit-friendly, gas-efficient, and optimized for Google Clarity Web3 contract procurement.

🚀 Features

SIP-010 Compatibility: Works with any SIP-010 compliant fungible token.

Partial Releases: Payments can be disbursed gradually instead of all at once.

Refunds with Deadlines: If milestones are not reached, funds can be refunded after a deadline.

Arbiter Support: An optional arbiter can resolve disputes or expedite refunds.

Event Logging: On-chain events (escrow_created, escrow_locked, escrow_released, etc.) provide full transparency for off-chain monitoring.

Finalization: Escrows can be cleared from storage once completed to save space.

🔑 Lifecycle of an Escrow

Create → The payer initializes an escrow with payee, token, amount, deadline, and arbiter (optional).

Pre-fund → The payer transfers the token amount to the escrow contract address.

Lock → The payer confirms the escrow once funds are in place.

Release → Funds can be released fully or partially to the payee by the payer or arbiter.

Refund → If deadlines expire, or arbiter intervenes, payer can reclaim unspent funds.

Finalize → Once complete, the escrow entry is deleted from storage.

🛠️ Public Functions

create (payee token amount deadline arbiter) → Initializes a new escrow.

lock (id) → Locks escrow after verifying pre-funding.

release (id amt) → Releases tokens to payee.

refund (id amt) → Refunds tokens back to payer.

finalize (id) → Deletes completed escrow.

📊 Events Emitted

escrow_created → A new escrow is set up.

escrow_locked → Escrow is confirmed and secured.

escrow_released → Payment released to payee.

escrow_refunded → Refund issued to payer.

escrow_finalized → Escrow closed and cleaned up.
