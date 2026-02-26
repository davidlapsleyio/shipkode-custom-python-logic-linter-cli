# Tasks: Zero-Noise Reporting Engine

- [ ] **F3-T1: Domain Data Models**
  Define the core data structures for AST source locations, violations, and scan summaries.
  *Refs: 1, 5*
  - [ ] **F3-T1.1: Core SourceLocation Schema**
    Implement a SourceLocation schema that supports start/end line and column coordinates.
  - [ ] **F3-T1.2: Violation Data Model**
    Define a Violation model that links AST node findings to SourceLocation and suppression metadata.
- [ ] **F3-T2: Reporting Engine Services**
  Develop the core logic for filtering architectural noise and mapping AST findings to source code.
  *Refs: 1, 2*
  - [ ] **F3-T2.1: Noise Suppression Logic Implementation**
    Implement logic to discard standard linting patterns and focus only on critical architectural violations.
  - [ ] **F3-T2.2: AST Coordinate Resolver Service**
    Develop a service to map AST node offsets to precise human-readable line/column markers.
- [ ] **F3-T3: Reporting Adapters**
  Build the adapters for air-gapped reporting and terminal display.
  *Refs: 3, 4, 5*
  - [ ] **F3-T3.1: Terminal Snippet Formatter**
    Implement local file reading and contextual snippet extraction with syntax highlighting for the terminal.
  - [ ] **F3-T3.2: Air-Gapped Report Generator Adapter**
    Create a report generator that uses embedded templates to ensure zero network requests during output.
- [ ] **F3-T4: User Interface & CLI**
  Construct the command-line interface and summary views for the engine output.
  *Refs: 3, 5*
  - [ ] **F3-T4.1: Scan Summary View**
    Create a concise summary view showing total violations, files scanned, and suppression statistics.
  - [ ] **F3-T4.2: Interactive Violation CLI Output**
    Ensure violation paths include IDE-friendly protocol links (e.g., vscode://) based on AST coordinates.
