# GitHubActionsLab-LakshChhabra
ICE-5
   test
back to main



GitHub Actions Lab - Laksh Chhabra

This repository contains two GitHub Actions workflows.

Workflow 1: Dependent Jobs (dependent-jobs.yml)
Runs three jobs — 'build, test, deploy' in order using the `needs` key.
Each job waits for the previous one to finish. Triggered on push to main.

Workflow 2: Multi-Platform Testing (multi-platform.yml)
Runs three independent jobs in parallel on Ubuntu, Windows, and macOS.
Each job checks out code, prints OS info, runs an OS-specific command,
and creates and displays a file. Triggered on pull requests to main.

Key Concepts
- needs: Makes jobs run in a set order (used in Workflow 1). Without it, jobs run in parallel (Workflow 2).
- runs-on: Sets the OS a job runs on (ubuntu-latest, windows-latest, macos-latest).
- env: Defines environment variables for use in a workflow, job, or step.

Challenges Faced
- The multi-platform workflow only runs on pull requests, not on commits to main. I fixed this by opening a pull request to trigger it.
- Windows uses different commands than Linux/macOS (`systeminfo`/`type` vs `uname`/`cat`), so each job needed the right commands.
