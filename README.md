# Create Pull Request Github Action

Creates a pull request in the current directory's repo.

## Usage

```yml
- name: Create Pull Request
  uses: brownuniversity/create-pull-request@v1
```

### Inputs

#### Required

- `directory`: Directory in which to create the branch
- `branch-name`
- `commit-message`
- `title`: PR title

#### Optional

- `description`: PR description
- `draft`: Create draft PR
- `token`: Personal Access Token
