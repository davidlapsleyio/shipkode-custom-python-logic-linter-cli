# Tasks: Air-Gapped Privacy Mode

- [ ] **F2-T1: Domain Data Models and Types**
  Define the PrivacyProfile data structures and configuration schemas for air-gapped operations.
  *Refs: 3*
  - [ ] **F2-T1.1: Define PrivacyProfile Schema**
    Implement PrivacyProfile model including OfflineMode, TelemetryEnabled, and UpdateCheckAllowed flags.
  - [ ] **F2-T1.2: Validation Logic**
    Implement configuration validation logic to ensure mutual exclusivity of high-security flags.
- [ ] **F2-T2: Service and Use Case Logic**
  Develop the core orchestration logic for managing the execution environment state and enforced restrictions.
  *Refs: 1, 3, 4*
  - [ ] **F2-T2.1: Privacy Mode Orchestrator**
    Implement the coordinator to intercept execution requests and verify privacy constraints.
  - [ ] **F2-T2.2: Socket Connection Guardian (Property Test 1)**
    Develop a pre-execution guard that scans for active network sockets and blocks processing if external connections are detected.
- [ ] **F2-T3: API Routes and Adapters**
  Implement adapters that interface with local resources and provide external service mocks for restricted environments.
  *Refs: 1, 4*
  - [ ] **F2-T3.1: Local LLM Adapter Implementation**
    Implement LocalLLMAdapter to interact with local inference servers (e.g., llama.cpp) via Unix domain sockets or localhost only.
  - [ ] **F2-T3.2: Network-Locked Update Mock**
    Implement a dummy update service that returns 'No Updates' immediately when PrivacyMode is enabled to prevent network calls.
- [ ] **F2-T4: Distribution and UI Components**
  Package the application into a single executable and provide UI feedback for privacy status.
  *Refs: 2, 3*
  - [ ] **F2-T4.1: Standalone Binary Build Pipeline**
    Configure PyInstaller or similar tool to bundle all dependencies and the local LLM runtime into a single portable binary.
  - [ ] **F2-T4.2: Air-Gap Status UI Indicator**
    Add a 'Privacy Shield' indicator to the CLI/UI that visually confirms the tool is in Verified Zero-Telemetry mode.
