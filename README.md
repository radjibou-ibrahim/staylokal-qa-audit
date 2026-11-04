# StayLokal — Mini QA Audit

**Application:** https://staylokal.app/  
**Audit type:** Functional testing and browser network inspection  
**Environment:** Windows / Google Chrome  
**Audit date:** 2026-11-04  
**Status:** In progress

## Objective
Assess selected file-processing workflows and collect observable evidence relevant to StayLokal's claim that files are processed locally rather than uploaded to a server.

## Current scope

| ID | Scenario | Current observation |
|---|---|---|
| QA-001 | Import a test PDF and inspect Network | PDF appeared in the workspace. No identifiable file-upload request was visible in the captured Fetch/XHR requests. |
| QA-002 | Create a ZIP archive and inspect Network | The app displayed **COMPLETED LOCALLY**. No additional Fetch/XHR request was observed during ZIP creation. |
| QA-003 | Download the generated ZIP and inspect Network | No additional request was observed after the download action, according to the tester. |

## Important limitation
These observations are limited to the tested workflows and the visible Chrome DevTools Network panel. They do **not** prove that every feature, every session, or every network mechanism in the application is free of file transmission. A broader assessment would require additional scenarios and inspection of all relevant network activity.

## Repository structure
- `01-test-strategy/` — scope and approach
- `02-test-cases/` — reproducible test scenarios
- `03-test-execution/` — execution log and observations
- `04-evidence/` — screenshots and evidence index
- `05-report/` — audit report
- `06-linkedin/` — public communication draft

## Evidence handling
Screenshots should be added to `04-evidence/screenshots/` and referenced from the evidence index. Do not include personal documents, private data, authentication tokens, cookies, or sensitive request payloads.

## Conclusion so far
The two observed workflows behave consistently with local processing, within the limited scope described above. The audit remains in progress; no privacy defect has been confirmed.
