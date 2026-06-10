# GitHubActionsLab-LakshChhabra
ICE-5
   test
back to main


This is my lab for learning GitHub Actions. It has two workflows.

Workflow 1 - Dependent Jobs (dependent-jobs.yml)
This workflow has three jobs: build, test, and deploy. They run one after
another in order using the `needs` key. It runs when I push to the main branch.

Workflow 2 - Multi-Platform Testing (multi-platform.yml)
This workflow has three jobs that run at the same time on Ubuntu, Windows,
and macOS. Each job checks out the code, prints the OS info, runs a command,
and makes a file and shows what's inside it. It runs when I open a pull request.

Key Concepts
needs: Used to make jobs run in order. If you don't use it, the jobs run at the same time.
runs-on: Tells the job which operating system to use (like ubuntu-latest or windows-latest).
env: Used to set environment variables in the workflow.

Challenges I Faced
At first my multi-platform workflow didn't run. I learned it only runs on a pull request, not when you push to main. So I made a branch and opened a pull request and then it worked.
Windows uses different commands than Mac and Linux, so I had to use systeminfo and type for Windows instead of uname and cat.
