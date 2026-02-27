# Contributing to Fastronome Copilot Code Review for Azure DevOps

Thank you for your interest in contributing to this project!

## Development Setup

### Prerequisites

- Node.js 20 or later
- npm
- TypeScript (`npm install -g typescript`)
- TFX CLI (`npm install -g tfx-cli`)

### Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/fastronome/azure-devops-copilot-code-review.git
   cd azure-devops-copilot-code-review
   ```

2. Install dependencies:
   ```bash
   cd CopilotCodeReviewV1
   npm install
   ```

3. Compile TypeScript:
   ```bash
   npm run build
   ```

### Building the Extension

1. Ensure you have a valid PNG icon at `images/logo-fastronome-128.png` (minimum 128x128 pixels)

2. From the root directory, package the extension:
   ```bash
   tfx extension create --manifest-globs vss-extension.json
   ```

3. This creates a `.vsix` file that can be uploaded to the Azure DevOps Marketplace

### Testing Locally

1. Set environment variables for testing:
   ```powershell
   $env:INPUT_GITHUBPAT = "your-github-pat"
   $env:INPUT_AZUREDEVOPSPAT = "your-ado-pat"
   $env:INPUT_ORGANIZATION = "your-org"
   $env:INPUT_PROJECT = "your-project"
   $env:INPUT_REPOSITORY = "your-repo"
   $env:INPUT_PULLREQUESTID = "123"
   ```

2. Run the task:
   ```bash
   cd CopilotCodeReviewV1
   node index.js
   ```

### Project Structure

```
azure-devops-copilot-code-review/
├── vss-extension.json          # Extension manifest
├── README.md                   # Documentation
├── LICENSE                     # LGPLv3 License
├── CONTRIBUTING.md             # This file
├── .gitignore
├── images/
│   └── logo-fastronome-128.png # Extension icon used by manifests
└── CopilotCodeReviewV1/
    ├── task.json               # Task definition
    ├── index.ts                # Main task logic
    ├── package.json            # Node.js dependencies
    ├── tsconfig.json           # TypeScript config
    └── scripts/
        ├── Get-AzureDevOpsPR.ps1           # Fetch PR details
        ├── Get-AzureDevOpsPRChanges.ps1    # Fetch PR changes
        ├── Add-AzureDevOpsPRComment.ps1    # Post comments
        ├── Add-CopilotComment.ps1          # Simplified comment wrapper
        └── prompt.txt                       # Default Copilot prompt
```

### Code Style

- Use TypeScript for the main task logic
- Use PowerShell for Azure DevOps API interactions
- Follow existing code patterns and formatting
- Include JSDoc/comment headers for functions

### Submitting Changes

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Make your changes
4. Test locally
5. Commit with clear messages
6. Push to your fork
7. Open a Pull Request

### Reporting Issues

Please use GitHub Issues to report bugs or request features. Include:
- Clear description of the issue
- Steps to reproduce
- Expected vs actual behavior
- Environment details (agent OS, Node version, etc.)

## License

By contributing, you agree that your contributions will be licensed under the GNU Lesser General Public License v3.0 (LGPLv3).
