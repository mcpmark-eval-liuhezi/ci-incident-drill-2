# ci-incident-drill-2

**This repository is a throwaway sandbox.** It exists only to rehearse a "CI is red, now what?" incident-response drill before the runbook is handed to the team. Nothing here is a real project.

## What this sandbox does

- Contains a workflow at `.github/workflows/drill-fail.yml` that runs on every push (and can be started manually via `workflow_dispatch`).
- The workflow's only step is a shell command that exits non-zero, so the run **reliably fails** on purpose.
- The failure is used to rehearse: reading the run state, re-running only the failed jobs, and logging the incident in an issue.

## Drill steps

1. Push to `main` (or dispatch manually) to trigger a run.
2. Confirm the run fails and record the run id and failing job name.
3. Re-run only the failed jobs of that run.
4. Check the run's status after the re-run.
5. Log everything in the "Incident drill log" issue.

## Cleanup

Delete this repository once the drill is over.
