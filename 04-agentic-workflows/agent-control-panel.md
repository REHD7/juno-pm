# Agent Control Panel · Juno

> Module 4 · Decide When an Agent Acts on Its Own. Spec'd with the **M4 - Agent Control Panel** tool. Paste the tool's markdown over this file.

## What Juno Is Doing

Juno is a semi-autonomous AI agent (Level 2) that reads contracts and royalty statements, verifies calculations, identifies financial discrepancies, and generates evidence-based reports using a ReAct workflow.

## Four Levers

**Stop Conditions** (Loop):

Maximum 3 attempts. Stop when verification succeeds, essential evidence is missing, or repeated validation fails.

**Structured Tool Outputs** (Tools):

Each tool returns structured data: status (success/failure), extracted values, calculations, source IDs, validation results, and errors

**Confidence Thresholds** (Verification):

Classify results as VERIFIED only when calculations and supporting contractual evidence pass validation. Otherwise, flag them as POTENTIAL or UNVERIFIABLE.

**North Star** (Context):

Provide accurate, transparent, and traceable royalty reconciliation without inventing financial information

## Rules of Engagement

**Agency Permission:**

READ: Automatic

DRAFT: Automatic

WRITE: Human confirmation required

SEND: Human confirmation required

**Access Control:**

Only authorized users can access their uploaded contracts, statements, and financial records. No unauthorized external account access.

**Fallback Protocols:**

Retry correctable errors up to 3 times. If verification fails or evidence is missing, stop, explain the issue, and request human intervention.

**Checkpoints:**

Validate calculations and source references before presenting verified results. Require human approval before modifying stored records, contacting labels, or initiating financial claims.
