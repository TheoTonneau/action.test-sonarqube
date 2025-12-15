# Terraform Linter GitHub Action

This GitHub Action checks Terraform code.

## INPUTS

| Variable                  | Description                                                                                                            | Required | Default |
|:--------------------------|:-----------------------------------------------------------------------------------------------------------------------|:---------|:--------|
| `WORKING_DIRECTORY`       | Working Directory where terraform code is stored.                                                                      | No       | `./iac` |
| `GH_TOKEN`                | The GitHub token to interact with the repository.                                                                      | Yes      | N/A     |
| `USE_GENERIC_TFLINT_FILE` | Use the generic .tflint file or that of your project, if there is one (note that it must be in the WORKING_DIRECTORY). | No       | `true`  |
| `FAIL_ON_WARNINGS`        | Fail the action if there are warnings.                                                                                 | No       | `false` |

## USAGE

```yaml     
  # Test linter terraform
  tf-lint:
  runs-on: ubuntu-latest
  steps:
    - uses: actions/checkout@v5

    - name: "Run terraform linter"
      uses: energies-vienne/actions.lint-terraform@v1
      with:
        WORKING_DIRECTORY: './iac'
        GH_TOKEN: ${{ secrets.SERVICE_USER_ACCESS_TOKEN }}
        FAIL_ON_WARNINGS: 'true'

  #DO NOT CHANGE the GH_TOKEN
```

## Example
[App-Security](https://github.com/energies-vienne/aws.app-security.terraform)

## Contribute
We welcome contributions to this project. To contribute, please follow these steps:

1. Fork the Repository: Create a fork of this repository to your own GitHub account.
2. Create a New Branch: Create a new branch in your fork for your feature or bugfix.

```bash
git checkout -b feature/your-feature-name
```

3. Make Your Changes: Implement your feature or bugfix.
4. Update the Version: Update the version.txt file with a new version number following Semantic Versioning. The version should be in the format vX.Y.Z (e.g., v1.0.1).
5. Commit Your Changes: Commit your changes with a meaningful commit message.

```bash
git add .
git commit -m "Add feature: description of your feature"
```

6. Push Your Changes: Push your new branch to your fork.

```bash
git push origin feature/your-feature-name
```

7. Create a Pull Request (PR): Go to the original repository on GitHub and create a pull request from your branch. Make sure to provide a detailed description of your changes and the reasoning behind them.
8. Code Review: Your PR will be reviewed by the repository maintainers. Please be responsive to any feedback and make necessary adjustments.
9. Merge: Once your PR is approved, it will be merged into the main branch.

### Expected Tag Format
When updating the version in version.txt, please ensure the version follows this format:

- vX.Y.Z where X is the major version, Y is the minor version, and Z is the patch version.
- Example: v1.0.0

Thank you for your contributions!