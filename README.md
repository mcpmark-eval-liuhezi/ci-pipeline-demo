# ci-pipeline-demo

Welcome! This repository is a **CI onboarding sandbox** — a small, safe place to
learn how GitHub Actions and continuous integration (CI) work by clicking
through a real example.

## What to do here

1. Find the open pull request in this repository (see the **Pull requests** tab).
2. Open the **Actions** tab and locate the workflow run that the pull request
   triggered.
3. Open the job's log and search for the marker line:

   ```
   PIPELINE-DEMO-OK
   ```

If you can find the `PIPELINE-DEMO-OK` marker in the CI logs, you have completed
this onboarding exercise.

## Where the workflow lives

The CI configuration is in [`.github/workflows/ci.yml`](.github/workflows/ci.yml).
It triggers on pull requests and prints the marker line.
