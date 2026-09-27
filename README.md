# 🚉 The Operator's Booth

### Meera's Railway Delay API

> A tiny x402-powered API that turns messy railway delay notices into clean JSON — and charges only when the parser successfully does its job.

[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript)](https://www.typescriptlang.org/)
[![Node.js](https://img.shields.io/badge/Node.js-20%2B-green?logo=node.js)](https://nodejs.org/)
[![x402](https://img.shields.io/badge/Payments-x402-purple)](https://x402.org/)
[![Base Sepolia](https://img.shields.io/badge/Network-Base%20Sepolia-blue)](https://docs.base.org/)
[![USDC](https://img.shields.io/badge/Currency-Test%20USDC-2775CA)](https://www.circle.com/usdc)

---

## What is The Operator's Booth?

Meera is a retired Indian Railways clerk in Pune.

Every morning she reads railway delay notices posted by stations. These notices are often messy, inconsistent, and sometimes contain reasons written in Hindi or Marathi.

She built a small parser that converts those notices into structured JSON.

The problem?

Three commuter applications started using her parser — but nobody was paying for the infrastructure.

So she turned the API into a tiny **pay-per-request service using x402**.

No:

- Signups
- API keys
- Subscriptions
- Monthly invoices

Instead:

```text
Request
   ↓
x402 Payment
   ↓
Parse Notice
   ↓
Success?
 ┌─┴─────────┐
YES          NO
 │            │
 ↓            ↓
Settle      No Settlement
 │            │
 ↓            ↓
JSON       Error
