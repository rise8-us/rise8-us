---
hide:
- toc
---

# GitHub Workflows with Webhook Actions

## Discover how Webhook Actions can streamline automation and unlock hidden flexibility in event-driven CI/CD pipelines

As developers and operations professionals, we're always on the lookout for tools that can make our lives easier and streamline our workflows. GitHub Actions has become an absolute game changer in the world of CI/CD and automation, and today, I want to introduce you to an incredibly flexible and powerful addition to the GitHub Actions ecosystem: Webhook Actions

This simple GitHub application is designed to make your life easier by transforming webhook events into streamlined repository dispatches. In this blog post, I'll guide you through the benefits of using Webhook Actions, and show you some practical examples of how it can be used to ultimately help you unleash the full potential of GitHub Actions in your organization.

## The Power of Webhook Actions

Webhook Actions is a GitHub App that enables you to harness the full power of GitHub webhooks to create more efficient and flexible workflows. It aims to reduce the complexity of your GitHub Actions workflows while ensuring that your workflows only trigger when the conditions you specify are met.

One of the things that sets Webhook Actions apart is its ability to filter and map webhook events, allowing you to create more concise and readable workflows, reduce unnecessary job executions, and simplify the overall process of automating tasks on GitHub.

## A Glimpse into Streamlined Repository Dispatches

Let's take a look at some practical examples of how Webhook Actions can be leveraged to optimize your GitHub workflows.

### Example 1: Running Workflows Only on Merged Pull Requests

Traditionally, you might have created a workflow that triggers on a pull request being closed and then used a conditional to check if it was actually merged. This approach often leads to many skipped jobs and unnecessary resource consumption. For example, a typical workflow might look like this:

```yaml
name: Merged Pull Request

on:
  pull_request:
    types:
      - closed

jobs:
  notify:
    if: github.event.pull_request.merged
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v3
    # ...
```

With Webhook Actions, you can create a configuration file that instead listens for a `pull_request_closed` event, making your workflow look like this:

```yaml
name: Merged Pull Request

on:
  repository_dispatch:
    types:
      - pull_request_closed

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v3
    # ...
```

Et voilà- no more conditional! This approach is much more efficient and it also ensures that your workflow only runs when a pull request is *actually* merged. No more skipped jobs!

### Example 2: Auto-Assigning Team Members Based on File Paths

Now, let's imagine a more complicated scenario! Perhaps we want to automatically assign a team member to a new pull request based on the directory of the modified files. Without Webhook Actions, this would require complex logic within your workflows.

However, Webhook Actions simplifies this process by enabling you to listen for the `pull_request_opened` event within a configuration file inside your repository, like so:

```json
{
  "events": {
    "pull_request_opened": {
      "filter": {
        "repository.name": "your-repo-name"
      }
    }
  }
}
```

... and now you can filter it based on the repository and map the pull request number and repository name in the payload. You can then use this information in your GitHub Actions workflow to easily assign the appropriate team member based on the modified files' directory:

```yaml
name: Auto-Assign Team Members

on:
  repository_dispatch:
    types:
      - pull_request_opened

jobs:
  assign:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Assign team members based on file paths
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        run: |
          PR_NUMBER=${{ github.event.client_payload.number }}
          PR_USER=${{ github.event.client_payload.user.login }}
          PR_URL="https://api.github.com/repos/${{ github.repository }}/pulls/${PR_NUMBER}"
          PR_FILES_URL="${PR_URL}/files"

          TEAM_MEMBERS_BACKEND=( "backend-team-member-1" "backend-team-member-2" )
          TEAM_MEMBERS_FRONTEND=( "frontend-team-member-1" "frontend-team-member-2" )

          # Fetch the files in the PR
          PR_FILES=$(gh api $PR_FILES_URL)
          FRONTEND_FILES=$(echo $PR_FILES | jq '.[] | select(.filename | test("frontend"))')
          BACKEND_FILES=$(echo $PR_FILES | jq '.[] | select(.filename | test("backend"))')

          # Assign team members based on file paths
          if [ ! -z "$FRONTEND_FILES" ]; then
            for member in "${TEAM_MEMBERS_FRONTEND[@]}"; do
              gh api "${PR_URL}/assignees" -X POST -F "assignees[]=$member"
            done
          fi

          if [ ! -z "$BACKEND_FILES" ]; then
            for member in "${TEAM_MEMBERS_BACKEND[@]}"; do
              gh api "${PR_URL}/assignees" -X POST -F "assignees[]=$member"
            done
          fi
```

## Unlock New Possibilities with Webhook Actions

The examples above are just the tip of the iceberg when it comes to the possibilities that Webhook Actions unlocks. With its flexibility and simplicity, you can create more efficient and powerful workflows, streamline your automation processes, and ultimately, spend more time focusing on what really matters: delivering value to your users.

If you're already a fan of GitHub Actions, I encourage you to explore Webhook Actions and see how it can revolutionize your automation processes. And if you're new to GitHub Actions, there's never been a better time to dive in and experience the power of this incredible ecosystem.

Happy automating!