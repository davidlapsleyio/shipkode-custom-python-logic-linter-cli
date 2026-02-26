# Tasks: Sentinel CLI Core

- [ ] **F0a-T1: Core Data Models and Type Definitions**
  Define the core data structures for File Metadata, Rule definitions, and Analysis Results to ensure type safety across the application.
  *Refs: 1, 2, 5*
  - [ ] **F0a-T1.1: Define Rule and Violation Models**
    Define the Rule schema for YAML parsing, including severity, pattern, and metadata fields.
    *Refs: 2*
  - [ ] **F0a-T1.2: Define Scan Result and File Models**
    Define the ScanResult and FileManifest models to track scanned files and identified issues.
    *Refs: 1 Greenland 5*
- [ ] **F0a-T2: Local Infrastructure Adapters**
  Implement the local file system access layer for scanning directories and reading rule files without network dependencies.
  *Refs: 1 Greenland 2 Greenland 4*
  - [ ] **F0a-T2.1: Implement Local File Discovery Service**
    Implement recursive directory walking with support for ignore patterns to discover source files.
    *Refs: 1*
  - [ ] **F0a-T2.2: Implement Rule File Loader Service**
    Implement YAML loader to deserialize local rule files into Rule models.
    *Refs: 2 Greenland 4*
- [ ] **F0a-T3: Scan Orchestration Use Cases**
  Develop the business logic for coordinating scans and applying rule sets to discovered files.
  *Refs: 1 Greenland 2 Greenland 4 Greenland 5*
  - [ ] **F0a-T3.1: Implement Analysis Engine Logic**
    Develop the engine that maps rules against files and aggregates violations.
    *Refs: 5*
  - [ ] **F0a-T3.2: Validation: Air-Gapped Integrity Property Test**
    Implement property-based tests to ensure no outbound network calls are made during the orchestration flow.
    *Refs: 4*
- [ ] **F0a-T4: CLI Entrypoint and Reporting**
  Build the Command Line Interface to handle user input, output formatting, and process exit codes.
  *Refs: 3 Greenland 5*
  - [ ] **F0a-T4.1: Implement Console Result Reporter**
    Implement terminal-based tabular or list reports for scan violations with high precision.
    *Refs: 5*
  - [ ] **F0a-T4.2: Implement Standardized Exit Codes**
    Configure process exit codes (e.g., 0 for success, 1 for violations found, 2 for errors) for CI/CD compatibility.
    *Refs: 3 Greenland 5*
