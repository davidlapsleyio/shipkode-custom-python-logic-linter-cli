# Requirements: Zero-Noise Reporting Engine

## Introduction

The Zero-Noise Reporting Engine is the core output component of Sentinel, designed to provide developers with hyper-accurate, actionable feedback on architectural violations. By bypassing cosmetic linting issues and focusing exclusively on Abstract Syntax Tree (AST) pattern matches, this engine ensures that every report represents a genuine logic or structural flaw. The engine operates entirely locally, providing precise line and column data alongside contextual code snippets to facilitate immediate remediation in high-stakes or air-gapped environments.

## Requirements

### F3-R1: Precise AST Location Mapping

- **Priority:** must
- **Type:** ubiquitous

> As an Independent Maintainer I want precise line and column reporting for AST matches so that I can navigate directly to the structural flaw in my IDE.

**Acceptance Criteria:**
- THE Sentinel engine SHALL calculate the exact line and column start/end points for every AST node match.
- WHEN a violation is detected, THE system SHALL output the precise coordinates to the terminal.

### F3-R2: Noise Suppression Logic

- **Priority:** must
- **Type:** unwanted

> As a High-Stakes Consultant I want the engine to suppress standard 'lint' noise so that I can focus on critical logic errors without being distracted by 40% false positives.

**Acceptance Criteria:**
- IF a code pattern does not match the structural logic defined in the YAML rule, THEN THE system SHALL NOT generate a report.
- THE system SHALL exclude all stylistic, whitespace, and formatting-only variations from its analysis.

### F3-R3: Contextual Code Snippet Display

- **Priority:** should
- **Type:** event_driven

> As an Independent Maintainer I want to see a contextual code snippet in the terminal so that I can verify the violation without opening the source file.

**Acceptance Criteria:**
- WHEN a violation is reported, THE system SHALL display the relevant code snippet from the source file.
- THE code snippet display SHALL highlight the specific tokens that triggered the AST match.

### F3-R4: Air-Gapped Report Generation

- **Priority:** must
- **Type:** ubiquitous

> As a High-Stakes Consultant I want to generate high-precision reports on-premise without internet access so that I can maintain security in air-gapped environments.

**Acceptance Criteria:**
- THE reporting engine SHALL operate without requiring an active internet connection.
- THE system SHALL generate reports using only local assets and the portable binary.

### F3-R5: Scan Summary Output

- **Priority:** should
- **Type:** event_driven

> As an Independent Maintainer I want a concise summary of scan results so that I can quickly assess the overall health of my project architecture.

**Acceptance Criteria:**
- WHEN the engine completes a scan, THE system SHALL provide a summary including the total number of files scanned and the count of unique logic violations found.

