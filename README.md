# Create Pull Request Github Action

Creates a pull request in the specified directory's repo.

## Usage

```yml
- name: Create Pull Request
  uses: brownuniversity/create-pull-request@v1
```

Sets `env.pr_url` to the URL of the new pull request.

### Inputs

#### Required

- `directory`: Directory in which to create the branch
- `branch-name`
- `commit-message`
- `title`: PR title

#### Optional

- `description`: PR description
- `draft`: Create draft PR
- `token`: Personal Access Token (defaults to `github.token`)

## Example

```yml
jobs:
  main:
    name: main
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Source
        uses: actions/checkout@v2
        with:
          path: main
      - name: Checkout Destination Repo
        uses: actions/checkout@v2
        with:
          repository: "BrownUniversity/destination-repo"
          path: destination
          token: ${{ secrets.PAT }}
      - name: Make change to destination repo
        run: cp main/file.txt destination/file.txt
      - name: Create Pull Request in Destination Repo
        uses: brownuniversity/create-pull-request@v1.0.15
        with:
          token: ${{ secrets.PAT }}
          branch-name: task/update-file
          commit-message: "Update file"
          title: "Update file"
          description: "Fixed comma splice"
          draft: true
          directory: "destination"
```
