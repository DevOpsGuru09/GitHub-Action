# 🎯 WORKFLOW EVENTS

## Triggering Workflow in Multiple Ways

There are many ways we can trigger a GitHub Workflow. Below are some common methods:

# REPOSITORY EVENT

- **Push Events**: Trigger workflows when code is pushed to specific branches or tags.

  ```yaml
  on:
    push:
      branches:
        - main
        - develop
  ```

- **Pull Request Events**: Trigger workflows when a pull request is opened, synchronized, or reopened.

  ```yaml
  on:
    pull_request:
      branches:
        - main
        - develop
  ```

- **Issues**: Trigger workflows when issues are created, edited, labeled, or closed.
  ```yaml
  on:
  issues:
    types:
      - opened
      - edited
      - labeled
      - closed
  ```
- **Pull Request Review**: Trigger workflows when pull request reviews are submitted, edited, or dismissed.
  ```yaml
  on:
  pull_request_review:
    types:
      - submitted
      - edited
      - dismissed
  ```
- **Fork**: Trigger workflows when someone forks the repository.
  ```yaml
  on:
  fork:
  ```

# MANUAL EVENT

- **Manual Trigger (Workflow Dispatch)**: Allow workflows to be triggered manually from the GitHub UI.
  ```yaml
  on:
  workflow_dispatch:
  ```
- **External Events (Repository Dispatch)**: Trigger workflows from external systems via the GitHub API.
  ```yaml
  on:
  repository_dispatch:
    types:
      - custom_event
  ```
- **Trigger from another workflow**: Trigger workflows programmatically using reusable workflows or composite actions.
  ```yaml
  on:
  workflow_run:
    workflows:
      - "Another Workflow Name"
    types:
      - completed
  ```

# SCHEDULE EVENT

- **Scheduled Events (Cron Jobs)**: Trigger workflows at specific times using cron syntax.

  ```yaml
  on:
  schedule:
    - cron: "0 12 * * *" # Runs every day at 12 PM UTC
  ```

- **Tag Events**: Trigger workflows when a new tag is created.
  ```yaml
  on:
  push:
    tags:
      - v*.*.*
  ```
- **Release Events**: Trigger workflows when a release is published, edited, or deleted.
  ```yaml
  on:
  release:
    types:
      - published
  ```
- **Webhook Events**: Trigger workflows based on webhook events like issues, comments, or labels.
  ```yaml
  on:
  issues:
    types:
      - opened
      - labeled
  ```
- **Custom Paths**: Trigger workflows only when changes occur in specific files or directories.
  ```yaml
  on:
  push:
    paths:
      - "src/**"
      - "tests/**"
  ```

# REFERENCE LINK:

For more details on events that trigger workflows, refer to the official GitHub documentation:  
[GitHub Actions - Events That Trigger Workflows](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows)
