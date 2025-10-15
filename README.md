# GitHubActionsLab-YourName (Lab 4)

This repository contains three GitHub Actions workflows implementing **job dependencies**, **environment variables & secrets**, and **multi-platform testing**.

## Workflows

### 1) `dependent-jobs.yml`
- **Trigger:** on push to `main`
- **Jobs:** `build` → `test` → `deploy` (ordered with `needs`)
- **Proof to capture:** Actions run showing dependency graph and sequential execution

### 2) `env-and-secrets.yml`
- **Trigger:** `workflow_dispatch` (manual)
- **Env Levels:** workflow-level (`AWS_REGION`, `ENVIRONMENT`), job-level (`DEPLOYMENT_NAME`), step-level (`STEP_TAG`)
- **Secrets:** `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY` (dummy values), echoed as **masked** in logs
- **Proof:** Screenshot Settings → Secrets (names only) + run logs showing env resolution

### 3) `multi-platform.yml`
- **Trigger:** on `pull_request` to `main`
- **Jobs:** `ubuntu-job`, `macos-job`, `windows-job` running **in parallel**
- **Proof:** PR checks page showing all three jobs running simultaneously and their logs

## Submission Checklist

- [ ] Push all three YAML files to `.github/workflows/`
- [ ] **Screenshots:**
  - [ ] Each workflow file content in GitHub UI
  - [ ] Actions tab showing all workflows
  - [ ] Workflow 1: dependency visualization & order
  - [ ] Workflow 2: Secrets page (names only) + output with env usage
  - [ ] Workflow 3: Three OS jobs running in parallel (PR checks)
  - [ ] Successful run logs
- [ ] `README.md` updated with your name + any brief notes on challenges and fixes

> Note: Secret names must use underscores (e.g., `AWS_ACCESS_KEY_ID`) due to GitHub naming rules.
