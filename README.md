# Pathly--Task-allocation

## Code Review Process

This repository implements a structured code review process to ensure code quality and collaboration between AI and human reviewers.

### Requirements

- **Minimum 1 code reviewer approval** required for all pull requests
- **Team leader review** automatically requested via CODEOWNERS
- **AI code review** integrated through GitHub Actions workflow
- **Structured PR template** for consistent review format

### How It Works

1. **Create Pull Request**: Use the provided PR template for consistent formatting
2. **Automatic Review Assignment**: Team leader is automatically assigned via CODEOWNERS
3. **AI Code Review**: Automated workflow runs to facilitate AI-powered code review
4. **Human Approval**: At least 1 human reviewer must approve before merge
5. **Branch Protection**: Main branch is protected and enforces these requirements

### Configuration Files

- `.github/CODEOWNERS` - Defines required reviewers
- `.github/pull_request_template.md` - Standard PR format
- `.github/workflows/code-review.yml` - AI code review automation
- `.github/BRANCH_PROTECTION.md` - Branch protection setup guide

For detailed setup instructions, see [Branch Protection Configuration](.github/BRANCH_PROTECTION.md).