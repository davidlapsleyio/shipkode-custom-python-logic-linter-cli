# Requirements: Sentinel CLI Core

## Introduction

The Sentinel CLI Core provides the foundational command-line interface for the Sentinel logic engine. Built using high-performance Python CLI frameworks (Click/Typer), this feature enables developers to execute AST-based code analysis locally. It handles the discovery of source files and rule definitions, manages the execution lifecycle of the analysis engine, and provides standardized exit codes for integration into local development workflows and air-gapped automation pipelines. The core focuses on speed, local-first execution, and zero-noise reporting to ensure architectural integrity is maintained without external dependencies.

## Requirements

### F0a-R1: Local Directory Scanning and Discovery

- **Priority:** must
- **Type:** event_driven

> As an Independent Maintainer I want to point the CLI at my project directory so that I can automatically discover all source files for analysis.

**Acceptance Criteria:**
- THE Sentinel CLI SHALL provide a 'scan' command to initiate code analysis.
- WHEN the 'scan' command is executed without arguments, THE system SHALL search the current working directory for a default configuration file.
- IF a directory path is provided as an argument, THEN THE system SHALL recursively discover all supported source files within that path.

### F0a-R2: Rule File Loading

- **Priority:** must
- **Type:** state_driven

> As a High-Stakes Consultant I want to load custom logic rules from local YAML files so that I can perform specialized audits in air-gapped environments.

**Acceptance Criteria:**
- THE Sentinel CLI SHALL load rules from a local YAML file specified via a '--rules' flag.
- IF the rules file is malformed or missing, THEN THE system SHALL exit with a non-zero status code and a descriptive error message.

### F0a-R3: Standardized Exit Codes for CI/CD Integration

- **Priority:** must
- **Type:** event_driven

> As an Independent Maintainer I want the CLI to return standard exit codes so that I can integrate Sentinel into my local pre-commit hooks or scripts.

**Acceptance Criteria:**
- WHEN zero rule violations are found, THE system SHALL exit with code 0.
- WHEN one or more rule violations are found, THE system SHALL exit with code 1.
- WHEN a system or configuration error occurs, THE system SHALL exit with code 2 or higher.

### F0a-R4: Offline Execution Mode

- **Priority:** must
- **Type:** ubiquitous

> As a High-Stakes Consultant I want the tool to run entirely offline so that my client's sensitive intellectual property never leaves the workstation.

**Acceptance Criteria:**
- THE Sentinel CLI SHALL process all analysis steps without making any network requests.
- THE system SHALL function correctly when the 'INTERNET_CONNECTION' is unavailable.

### F0a-R5: Console Result Reporting

- **Priority:** should
- **Type:** event_driven

> As an Independent Maintainer I want to see clear, high-precision violation reports in my terminal so that I can fix architectural flaws immediately.

**Acceptance Criteria:**
- WHEN the 'scan' is complete, THE system SHALL display a summary including the number of files scanned and the count of violations found.
- IF violations are detected, THEN THE system SHALL output the file path, line number, and rule description for each violation.

