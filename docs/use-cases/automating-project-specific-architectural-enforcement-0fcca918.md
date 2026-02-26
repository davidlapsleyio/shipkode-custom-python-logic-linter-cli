# Automating Project-Specific Architectural Enforcement

As an Independent Maintainer, I want to execute custom AST-based pattern checks locally so that I can eliminate architectural drift without waiting for 10-minute CI loops.

## Actors

- The Independent Maintainer

## Preconditions

- A configuration file defining 10+ custom architectural rules exists.
- The Python source code is accessible on the local file system.

## Main Flow

1. The maintainer opens the terminal in the root directory of the open-source library.
2. The maintainer runs the command 'custom-linter check --rules ./arch-rules.yaml'.
3. The engine traverses the Python AST for all files in the project.
4. The tool identifies three instances where a private internal API is accessed by an external module.
5. The tool outputs a summary of violations with zero noise from standard PEP8 rules.

## Postconditions

- The developer has a list of specific architectural drifts to fix.
- The code remains compliant with the project's long-term design goals.

## Acceptance Criteria

- The tool validates the entire 50-file repository in under 2 seconds.
- All 12 architectural violations are flagged with specific line numbers.
- Zero false positives are reported for correctly implemented patterns.

