# Architectural Decision Records (ADRs)

## ADR 1: EventBridge + AWS Lambda for Real-Time Auto-Remediation
- **Status:** Approved
- **Decision:** Use Amazon EventBridge rules triggered by CloudTrail events to invoke AWS Lambda functions for instant remediation of S3 public blocks.

## ADR 2: S3 Object Lock for Audit Log Preservation
- **Status:** Approved
- **Decision:** Enable S3 Object Lock in Compliance Mode on the centralized Log Archive bucket to ensure WORM compliance.
