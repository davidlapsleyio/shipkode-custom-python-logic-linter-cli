# Requirements: Security & API Integrity Rules

## Introduction

Feature F4: Security & API Integrity Rules provides the Sentinel engine with the specialized logic required to detect and prevent the leakage of sensitive data and the misuse of unauthorized private APIs. By leveraging Abstract Syntax Tree (AST) analysis, this feature allows developers to define rigorous security guardrails that run locally, ensuring that intellectual property and sensitive patterns are identified without the data ever leaving the workstation.

## Requirements

### F4-R1: Private API Call Detection

- **Priority:** must
- **Type:** event_driven

> As a High-Stakes Consultant I want to identify unauthorized private API calls so that I can ensure compliance with client architectural constraints and prevent illegal dependency usage.

**Acceptance Criteria:**
- WHEN a scan is initiated, THE Sentinel engine SHALL identify function calls or imports labeled as 'private' within the user-defined YAML rule schema.
- IF a private API call is detected in the source code, THEN THE Sentinel engine SHALL report the exact file line and column of the violation.

### F4-R2: Sensitive Data Masking Check

- **Priority:** must
- **Type:** ubiquitous

> As an Independent Maintainer I want to detect unmasked sensitive data in logging statements so that I can prevent accidental exposure of credentials in public log files.

**Acceptance Criteria:**
- THE Sentinel engine SHALL allow the definition of regex patterns and AST nodes associated with sensitive variable names (e.g., 'password', 'secret', 'apiKey').
- WHEN sensitive variables are detected within logging or output function calls, THE Sentinel engine SHALL flag the occurrence as a high-risk data leak.

### F4-R3: High-Precision Security Reporting

- **Priority:** should
- **Type:** state_driven

> As a High-Stakes Consultant I want high-precision security alerts so that I can avoid wasting time on false positives during critical safety audits.

**Acceptance Criteria:**
- IF the Sentinel engine identifies a security violation, THEN THE output SHALL include a zero-noise justification based on the AST structure rather than cosmetic heuristics.

### F4-R4: Air-Gapped Security Integrity

- **Priority:** must
- **Type:** ubiquitous

> As a High-Stakes Consultant I want to run security checks on air-gapped servers so that I can handle sensitive client source code without violating non-disclosure agreements or security protocols.

**Acceptance Criteria:**
- WHEN the security scanner evaluates code, THE Sentinel engine SHALL execute all checks entirely offline without generating external network traffic.

