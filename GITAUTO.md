## Code Style
- Keep `noUnusedLocals` and `noUnusedParameters` enabled in `tsconfig.json` to prevent dead code.

## GitHub Actions
- Pin GitHub Actions to full-length immutable commit SHAs instead of mutable tags to ensure workflow stability and security.
- Use `persist-credentials: false` in `actions/checkout` to reduce credential exposure risk.
- Validate required credentials in shell scripts to ensure workflows fail with clear error messages if configuration is missing.

## JAIPilot Workflow
- **Purpose**: Automates test generation for pull requests.
- **Triggers**: Triggered when a pull request is `opened`, `synchronize`, or `reopened`.
- **Configuration**:
    - `JAIPILOT_TOKEN_ENDPOINT`: Credential containing the URL for exchanging GitHub OIDC tokens for JAIPilot runtime tokens.
    - `JAIPILOT_BACKEND_URL`: Credential containing the JAIPilot backend API URL.
- **Troubleshooting**:
    - Check the "JAIPilot Generate" action logs in the GitHub Actions tab.
    - Ensure the required credentials are configured in the repository settings.
    - Verify that the PR is coming from the same repository (forks are excluded by default).
