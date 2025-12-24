# Git Rules Chatmodes

A collection of chatmode rules for maintaining consistent commit messages, pull request descriptions, and production release notes. These chatmodes work together to create a workflow where good commits lead to good pull requests, which serve as context for generating release notes with historical links and summaries.

## Overview

This project contains three chatmode files designed to be used in whatever your agent coding workflow of choice is:

1. **Interactive Commit Generator** - Creates conventional commit messages
2. **Pull Request Description Generator** - Generates structured PR descriptions from git diffs
3. **Production Release Notes Generator** - Creates release notes from commit history and PR information

## Workflow

These chatmodes are designed to work together:

```text
Good Commits → Good Pull Requests → Good Release Notes
```

- **Commits**: Follow conventional commit format for consistency
- **Pull Requests**: Reference commits and link to tickets for context
- **Release Notes**: Aggregate commits and PRs with historical links for easy review

## Chatmodes

### 1. Interactive Commit Message Generator

**File**: `interactive-commit.chatmode.md`

Helps create properly formatted conventional commit messages using commitlint prompts. Guides you through:

- Selecting commit type (feat, fix, docs, etc.)
- Defining scope (optional)
- Writing imperative tense subject
- Adding body description (optional)
- Handling breaking changes
- Referencing issues

**Usage**: Activate this chatmode when you have staged changes and need help creating a conventional commit message.

### 2. Pull Request Description Generator

**File**: `pull-request.chatmode.md`

Generates structured PR descriptions by analyzing git diffs and ticket information. Creates PR descriptions with:

- Ticket/project management links
- Goals section
- Changes based on diff analysis
- Concerns/Issues
- TODOs found in code

**Usage**: Activate this chatmode when creating a pull request. It will analyze your branch's diff against the base branch and generate a formatted description ready to paste into GitHub.

### 3. Production Release Notes Generator

**File**: `production-release-notes.chatmode.md`

Generates production release notes by analyzing commit history and PR information. Organizes changes by:

- Platform sections (e.g. Frontend, Backend, AWS Lambdas, Infrastructure)
- Feature areas within each section
- Links to related PRs
- Concise bullet points for each change

**Usage**: Activate this chatmode when preparing a release. Provide a starting commit hash, and it will generate structured release notes with PR links for easy review.

## Usage Tips

- **Start with commits**: Use the interactive commit generator to ensure all commits follow conventional format
- **Link tickets in PRs**: The PR generator helps maintain consistency and links to project management tickets
- **Review before release**: Use the release notes generator to create summaries that reference all related PRs and commits
- **Maintain history**: The workflow ensures every change in release notes has traceable links back to PRs and commits

## Suggested Tools

- Git repository with conventional commits (commitlint recommended)
- Access to git diff and log commands
- GitHub repository for PR links (for release notes)
- Project management tool integration (e.g., Monday.com) for ticket links (for PR descriptions)
