# CI Pipeline Demo — Handover Note

A self-contained GitHub Actions onboarding example. Students can click through
this after the session and find every artifact referenced below.

- **Repository:** https://github.com/mcpmark-eval-liuhezi/ci-pipeline-demo
- **Workflow file:** `.github/workflows/ci.yml` (triggers on `pull_request`)
- **What to look for in the logs:** the marker line `PIPELINE-DEMO-OK`

---

## 1. The pull request

**Pull request #1 — "Add changelog section to README"**
https://github.com/mcpmark-eval-liuhezi/ci-pipeline-demo/pull/1

Raw diff of the pull request:

```diff
diff --git a/README.md b/README.md
index e66d6f9..a0d438a 100644
--- a/README.md
+++ b/README.md
@@ -22,3 +22,8 @@ this onboarding exercise.
 
 The CI configuration is in [`.github/workflows/ci.yml`](.github/workflows/ci.yml).
 It triggers on pull requests and prints the marker line.
+
+## Changelog
+
+This section records the notable changes made to this repository. Check back
+here after each exercise to see what has been added or updated.
```

## 2. The workflow run

Opening the pull request automatically triggered the `CI` workflow.

- **Run id:** `39336234084`
- **Run URL:** https://github.com/mcpmark-eval-liuhezi/ci-pipeline-demo/actions/runs/39336234084
- **Final conclusion (as reported by the run details):** `success`
- Status reported by the run: `completed`

## 3. Run usage (billed)

Quoting the workflow-run usage API response verbatim:

```json
{"billable":{"UBUNTU":{"total_ms":0,"jobs":1,"job_runs":[{"job_id":118346307656,"duration_ms":0}]}},"run_duration_ms":7000}
```

- **Billable platform:** `UBUNTU`
- **Billable milliseconds:** `0` (`total_ms: 0` for 1 job, job id `118346307656`, `duration_ms: 0`)
- **Overall run duration:** `7000` ms (`run_duration_ms: 7000`)

Note: the billable total is reported as `0` ms, while the overall run duration
is `7000` ms — the billed figure rounds down for this very short public-repo
run on Ubuntu runners (free for public repositories).

## 4. The marker in the CI logs

Log lines from job `118346307656` showing the `PIPELINE-DEMO-OK` marker:

```text
2026-10-19T22:37:21.9579533Z ##[group]Run echo "PIPELINE-DEMO-OK"
2026-10-19T22:37:21.9580317Z echo "PIPELINE-DEMO-OK"
2026-10-19T22:37:21.9747457Z shell: /usr/bin/bash -e {0}
2026-10-19T22:37:21.9748113Z ##[endgroup]
2026-10-19T22:37:21.9844676Z PIPELINE-DEMO-OK
```

The final line, `2026-10-19T22:37:21.9844676Z PIPELINE-DEMO-OK`, is the marker
students should search for in the **Actions** log.

## 5. How to click through it yourself

1. Open the repository: https://github.com/mcpmark-eval-liuhezi/ci-pipeline-demo
2. Go to the **Pull requests** tab and open **#1 — Add changelog section to README**.
3. On the pull request page, look at the checks section, or open the **Actions** tab.
4. Open the `CI` run for the `add-changelog` branch (run id `39336234084`).
5. Click the `build` job, then scroll to the **Print CI marker** step and search
   the log for `PIPELINE-DEMO-OK`.

Finding the marker means you have successfully navigated a pull request, its
triggered workflow run, and its logs — the core loop of GitHub CI.
