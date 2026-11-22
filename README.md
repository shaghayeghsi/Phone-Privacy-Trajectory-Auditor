# Phone Privacy Trajectory Auditor

A compact Jupyter Notebook project that audits synthetic AI coding-agent sessions for phone-number leaks in generated artifacts.

## Problem

A coding agent may pass its unit tests while leaving phone numbers in fixtures, logs, snapshots, exports, or other files about to be committed. This project demonstrates why auditing the **workflow and final artifacts** is more reliable than checking test status alone.

## What it does

- Creates a reproducible synthetic coding-agent session.
- Detects selected common phone-number formats in repository artifacts.
- Checks whether the agent scanned final artifacts before committing.
- Produces an evidence-backed scorecard with step numbers and file paths.
- Generates a remediation checklist.
- Runs regression tests for the "green tests, leaked data" failure mode.
- Exports a JSON audit report and CSV scorecard.

## Run

Open `phone_privacy_trajectory_auditor.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab and run all cells.

**Requirements:** Python 3.10+; standard library only. No API key or external dataset required.

## Example scenario

The synthetic agent reports 11 passing unit tests, but a legacy fixture still contains phone-number candidates. The auditor flags the artifact leak and the commit that occurred without a final artifact scan.

All phone numbers and session data in the demo are synthetic.

## Project structure

```text
phone-privacy-trajectory-auditor/
├── phone_privacy_trajectory_auditor.ipynb
└── README.md
```

## Limitations

This is an educational prototype, not a production DLP system. The detector supports selected common formats and may produce false positives or miss country-specific formats. Production use should add country-aware validation, real coding-agent log parsers, CI integration, and human review for ambiguous matches.

## Skills demonstrated

Python, regex-based PII detection, audit logging, evidence-backed evaluation, privacy engineering, automated testing, JSON/CSV reporting, and notebook-based reproducibility.

