# Create Pull Request Github Action

Creates a pull request in the current directory's repo.

## Usage

```yml
- name: Create Pull Request
  uses: brownuniversity/create-pull-request@v1
```

### Inputs

#### Required

- `branch-name`
- `commit-message`

#### Optional

- `title`: PR title
- `description`: PR description
- `draft`: Create draft PR
- `token`: Personal Access Token

### Outputs

- `pr-url`: URL of created PR
