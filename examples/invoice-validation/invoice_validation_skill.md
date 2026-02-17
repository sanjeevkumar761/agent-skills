# Invoice Validation Skill  

---
name: invoice-validation  
description:  
  Validate vendor invoices and classify processing outcomes.  
  Use when an invoice is received and needs to be assessed for  
  match status, compliance, and routing.  
metadata:  
  domain: finance  
  process: accounts-payable  
  owner: finance-operations  
  version: 1.0  
---  

## Purpose
This skill teaches the agent how to **evaluate a vendor invoice** and determine whether it can proceed automatically or requires human intervention.

Use this skill when:
- A vendor invoice is received
- Matching, compliance, or approval decisions are required
- The agent must explain *why* an invoice is accepted or flagged

This skill focuses on **judgment and classification**, not execution.

## Scope
The agent uses this skill to:
- Assess invoice completeness and correctness
- Evaluate match status against available purchase and receipt data
- Classify invoices into standard outcomes
- Explain decisions in business terms suitable for audit and review

## Non-Goals
This skill does NOT:
- Post invoices to ERP systems
- Trigger payments
- Modify financial records
- Route workflow approvals
- Call APIs or external systems

## Decision Logic
### Step 1: Invoice Completeness
Confirm presence of vendor identity, invoice number/date, line items, totals, and tax info.

### Step 2: Matching Assessment
Evaluate 3-way, 2-way, or no-match scenarios and tolerance breaches.

### Step 3: Compliance Considerations
Assess tax plausibility, contractual alignment, and approval implications.

## Outcomes
- Auto-processable
- Price or Quantity Mismatch
- Missing Information
- Approval Required
- Compliance Review Required

Each outcome must include a clear explanation.

## Guardrails
- Never assume correctness if data is missing
- Prefer conservative classification
- Do not invent values

## Inputs
- Invoice document or extracted fields
- Purchase order data (if available)
- Goods receipt data (if available)

## Outputs
- Classification
- Rationale
- Recommended next step

## Related Capabilities
Execution is delegated to MCP tools or workflow systems.

## Versioning
Behavioral changes require version updates and finance review.
