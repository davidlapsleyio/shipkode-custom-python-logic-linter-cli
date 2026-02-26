# Requirements: Custom Logic Rule Schema

## Introduction

The Custom Logic Rule Schema feature enables developers to define sophisticated architectural constraints and security policies using a structured YAML format. By leveraging Abstract Syntax Tree (AST) matching, this feature allows the Sentinel engine to identify deep structural patterns in source code—such as specific function calls or class hierarchies—balancing high-precision enforcement with local-first performance. This schema serves as the foundational language for the zero-noise promise of the Sentinel engine.

## Requirements

### F1-R1: YAML Rule Schema Definition

- **Priority:** must
- **Type:** ubiquitous

> As a High-Stakes Consultant I want a standardized YAML schema for rules so that I can define complex logic checks in a human-readable format.

**Acceptance Criteria:**
- The schema SHALL support a 'id' field for unique rule identification.
- The schema SHALL support a 'severity' field accepting 'error' or 'warning' values.
- IF a YAML file does not conform to the predefined Sentinel schema, THEN the system SHALL report a validation error.

### F1-R2: AST Pattern Matching Logic

- **Priority:** must
- **Type:** event_driven

> As an Independent Maintainer I want to match specific AST nodes like function calls and class definitions so that I can catch structural flaws without regex-based false positives.

**Acceptance Criteria:**
- The schema SHALL provide a 'match' property containing 'pattern' and 'target' keys.
- WHEN the 'target' is 'function_call', THE system SHALL match the pattern against AST call expressions.
- WHEN the 'target' is 'class_definition', THE system SHALL match the pattern against AST class declarations.

### F1-R3: Custom Violation Messaging

- **Priority:** should
- **Type:** ubiquitous

> As a High-Stakes Consultant I want to define custom violation messages so that I can provide specific remediation guidance to my clients.

**Acceptance Criteria:**
- The schema SHALL support a 'message' field for custom error reporting.
- THE system SHALL include the user-defined 'message' in the output when a rule violation is detected.

### F1-R4: Severity Level Enforcement

- **Priority:** must
- **Type:** state_driven

> As an Independent Maintainer I want to set severity levels for my rules so that critical architectural breaks fail my local build while minor issues only warn me.

**Acceptance Criteria:**
- IF the engine encounters a rule with an 'error' severity, THEN the system SHALL return a non-zero exit code upon completion.
- IF the engine encounters a rule with a 'warning' severity, THEN the system SHALL return a zero exit code but log the violation.

