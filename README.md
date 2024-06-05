# DCO-CHECK-ACTION

This is a GitHub Action to check if the DCO sign-off are present in the commits in a Pull Request


To use create a workflow and can use the example below:

```yaml
name: DCO

on:
  pull_request:

jobs:
  DCO:
    runs-on: ubuntu-latest

    permissions:
      contents: read

    steps:
      - name: Check DCO
        uses: cpanato/dco-check-action@main
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          repository: ${{ github.repository }}
          pull_request_number: ${{ github.event.number }}
```

### Inputs


| Input | Description |
| --- | --- |
| `github_token` | The GitHub token to access the API. Default `${{ github.token }}`. |
| `repository` | The `owner/repo`. Default `${{ github.repository }}`. |
| `pull_request_number` | The Pull Request number. Default `${{ github.event.number }}`. |
