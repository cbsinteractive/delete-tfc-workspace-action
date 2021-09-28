# Delete TFC Workspace Action

This action is used to delete Terraform Cloud workspaces.

## Inputs

The action expects the following inputs:

| Variable             | Required | Description                                                                 |
| -------------------- | -------- | --------------------------------------------------------------------------- |
| `tfcToken`           | Yes      | A Terraform Cloud API token with access to manage the workspace             |
| `orgName`            | Yes      | The name of the Terraform Cloud organization in which the workspace resides |
| `workspaceName`      | Yes      | The name of the Terraform Cloud workspace to manage                         |

## Outputs

The action generates no outputs. However, the return code will be non-zero if the Terraform Cloud workspace does not exist.

## Example Usage

```yaml
- name: Delete TFC workspace
  uses: cbsinteractive/delete-tfc-workspace-action@v1
  with:
    tfcToken: ${{ secrets.tfc_token }}
    orgName: ${{ secrets.tfc_organization }}
    workspaceName: some-workspace-name
```

This example assumes variables stored as GitHub [encrypted secrets][].

[encrypted secrets]: https://docs.github.com/en/actions/reference/encrypted-secrets
