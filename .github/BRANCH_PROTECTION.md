# Branch Protection Configuration Guide

This document outlines the branch protection settings required to enforce code review requirements.

## Required Settings

To implement the code review requirements, configure the following branch protection rules in GitHub repository settings:

### Main/Master Branch Protection

1. **Go to Repository Settings** → **Branches** → **Add rule** for `main` branch

2. **Required Status Checks**
   - ☑️ Require status checks to pass before merging
   - ☑️ Require branches to be up to date before merging
   - Add required checks: `check-review-requirements`, `ai-code-review-ready`

3. **Required Reviews**
   - ☑️ Require pull request reviews before merging
   - **Required number of reviewers**: `1` (minimum)
   - ☑️ Dismiss stale PR approvals when new commits are pushed
   - ☑️ Require review from code owners (uses `.github/CODEOWNERS`)

4. **Additional Restrictions**
   - ☑️ Restrict pushes that create files larger than 100 MB
   - ☑️ Include administrators (recommended)

## Code Owners Configuration

The `.github/CODEOWNERS` file specifies that:
- All files (`*`) require review from `@team-leader`
- This ensures team leader involvement in all code reviews
- AI code review is facilitated through the workflow and PR template

## AI Code Review Integration

AI code review is integrated through:
1. **GitHub Actions Workflow**: `.github/workflows/code-review.yml`
   - Runs automated checks on every PR
   - Provides AI-ready review checklist
   - Validates PR template usage

2. **PR Template**: `.github/pull_request_template.md`
   - Structured format for consistent reviews
   - Code review checklist for both human and AI reviewers
   - Clear indication that 1+ reviewer approval is required

## Enforcement Summary

- ✅ At least 1 code reviewer approval required for merge
- ✅ Team leader automatically requested as reviewer (via CODEOWNERS)
- ✅ AI code review workflow provides structured review process
- ✅ PR template ensures consistent review format
- ✅ Branch protection prevents bypassing review requirements