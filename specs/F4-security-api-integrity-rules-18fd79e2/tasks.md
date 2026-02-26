# Tasks: Security & API Integrity Rules

- [ ] **F4-T1: Security Domain Models and Types**
  Define the core data structures for security audits, including Severity levels, Vulnerability types (PrivateAPI, SensitiveData), and High-Precision Result containers.
  *Refs: 3*
  - [ ] **F4-T1.1: Define Security Domain Types**
    Create Enums for vulnerability types and Audit severity.
  - [ ] **F4-T1.2: Define Scan Result Schema**
    Implement the ScanResult schema that includes file path, line number, matched token, and confidence score for high-precision reporting.
- [ ] **F4-T2: Security Audit Service Logic**
  Develop the core logic for identifying security violations within source code.
  *Refs: 1, 2, 3*
  - [ ] **F4-T2.1: Implement Pattern Matching Logic**
    Implement a regex-based scanner that identifies private API patterns and unmasked sensitive data (PII/Credentials) in logs.
  - [ ] **F4-T2.2: Implement Precision Filtering Logic**
    Develop a filtering service to reduce false positives by analyzing call context, ensuring high-precision reporting.
  - [ ] **F4-T2.3: Sensitive Data Masking Property Test**
    Property Test: Verify that the scanner triggers alerts for tokens matching PII/Credential regex database.
- [ ] **F4-T3: Local Adapter and Air-Gapped Integration**
  Implement the local adapter that interfaces with filesystem for air-gapped execution.
  *Refs: 4*
  - [ ] **F4-T3.1: Implement Local File Adapter**
    Create a local file reader that loads source code into the SecurityAuditEngine without outbound network calls.
  - [ ] **F4-T3.2: Air-Gapped Isolation Property Test**
    Property Test: Assert that the entire scanning process performs zero network requests during execution.
- [ ] **F4-T4: Reporting Interface**
  Develop the interface for triggering audits and retrieving security reports.
  *Refs: 1, 2, 3*
  - [ ] **F4-T4.1: Security Report Generator**
    Implement an internal CLI or API route to initiate the static analysis and return a JSON report.
