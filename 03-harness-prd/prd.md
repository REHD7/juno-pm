# AI PRD · Juno

> Module 3 · Write an AI PRD Engineers Can Build from. The AI product requirements doc specifying all six harness surfaces, built with the **M3 · AI PRD Builder** (archetype and starting settings from the **M3 · Harness Architecture Decider**). Paste the tool's markdown over this file.

## Problem & user

Independent artists and small record labels often struggle to track royalty earnings, verify payments, and identify discrepancies in contracts and royalty statements.
Juno helps them monitor their music revenue, reconcile payments, and detect potential financial discrepancies.

_____

## The harness

| Surface | Specification |
|---|---|
| 01 Context | Juno can access user-uploaded royalty statements, recording agreements, contractual amendments, and supporting financial documents in PDF format.|
| 02 Tools | Documentation parsing to extract Financial and contractual information. Calculation|
| 03 Loop | Analysis → Verification → Validation. Maximum 3 attempts; stop and explain failures. 
| 04 Memory | Securely retain contractual clauses, statements, and previous results with user authorization|
| 05 Permissions | Read: Auto · Draft: Auto · Write: Confirm · Send: Confirm|
| 06 Verification | Validate calculations, check contractual evidence, and link findings to source IDs. Never invent data.|

## 01 Context · Data Requirements

- **Required sources:** Required sources: User-uploaded royalty statements, recording agreements, amendments, and supporting financial PDFs.
- **Deliberate exclusions:**  External accounts and unverified online data to protect privacy and reliability.
- **SLA of truth:** New or updated documents are reflected in the next analysis.
- **When a source is unreachable:** Flag missing information, explain the limitation, and never invent data.

## 02 Tools · System Capabilities

- **The verb list:** Read documents (read), extract clauses (read), calculate royalties (read), validate evidence (read), generate reports (draft), save results (write)._
- **Deliberate omissions:** No automatic external account access, payment claims, or third-party communication to protect privacy and maintain human control

## 03 Loop · AI Costs & Latency

- **Turn ceiling:** _max 3 attempts
- **Escalation trigger:** Stop when validation repeatedly fails or required evidence is missing.
- **Latency and cost target:**Minimize processing time and unnecessary token consumption; numerical targets TBD.

## 04 Memory · Data Requirements

- **What persists, at what scope:**User-level storage of contracts, clauses, royalty statements, and verified results.
- **Expiry:**Retain until user deletion, subject to the agreed retention policy.
- **Write rules:** User-confirmed corrections take priority over AI-generated information. Preserve the original source records.

## 05 Permissions · AI Risks & Mitigations

| Side-effect class | Tier |
|---|---|
| read | _auto  |
| draft | _auto  |
| write | confirm|
| send |  confirm |

**Justification:** Juno can autonomously analyze information and prepare reports. Modifying stored records or initiating external actions requires explicit human approval.

## 06 Verification · AI Testing & Measurement

- **The check before output ships:**Validate all calculations through mathematical tests, verify applicable contractual clauses, and link findings to source IDs. Only classify fully supported results as VERIFIED.
- **Failure behaviour:** _Retry up to 3 times for correctable errors. If verification fails, explain why and classify the result as POTENTIAL or UNVERIFIABLE. Never invent missing data.._

## Eval plan

_To be defined in Module 5 using 05-evals/human-rubric.md, including accuracy, evidence traceability, and reliability criteria._

## Out of scope

_Automatic financial claims or payments.

Unauthorized external account access.

Legal advice.

Actions outside the defined tool capabilities.

External communications without human approval._
