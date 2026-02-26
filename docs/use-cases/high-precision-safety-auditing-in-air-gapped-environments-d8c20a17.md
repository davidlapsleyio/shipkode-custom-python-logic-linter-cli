# High-Precision Safety Auditing in Air-Gapped Environments

As a High-Stakes Consultant, I want to run high-precision logic checks on-premise without internet access so that I can eliminate 100% of high-risk flaws before delivery.

## Actors

- The High-Stakes Consultant

## Preconditions

- The client environment is disconnected from the internet.
- Custom safety rules involving sensitive data handling are pre-defined.

## Main Flow

1. The consultant copies the portable linter binary to the air-gapped client workstation.
2. The consultant defines a regex-guarded AST rule for sensitive data masking.
3. The consultant initiates a scan of the local financial processing script.
4. The tool flags a logic flaw where a raw account number is passed to an unencrypted logging function.
5. The consultant rectifies the code before the final delivery to the client.

## Postconditions

- The codebase is verified against high-stakes safety rules in a restricted environment.
- Professional liability risk is mitigated by preventing logic flaws from reaching production.

## Acceptance Criteria

- The linter operates with 0 network requests confirmed by system logs.
- The tool detects 100% of hardcoded financial identifier patterns defined in the rule set.
- Analysis completion time is less than 5 minutes for a 2,000-line script.

