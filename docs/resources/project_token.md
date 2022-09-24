---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "sanity_project_token Resource - terraform-provider-sanity"
subcategory: ""
description: |-
  Provides a Sanity project token. The token key is a sensitive value that can be used to make authenticated requests against the Sanity HTTP API.
---

# sanity_project_token (Resource)

Provides a Sanity project token. The token key is a sensitive value that can be used to make authenticated requests against the Sanity HTTP API.

## Example Usage

```terraform
resource "sanity_project_token" "deployer" {
  project   = var.project_id
  label     = "Deployer token"
  role_name = "deploy-studio"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `label` (String) A descriptive label for the token.
- `project` (String) The project ID, which you can find at the top of the project page in Sanity.
- `role_name` (String) The role name that indicates which permissions are assigned to the token. For a free account, valid values are `viewer`, `editor`, and `deploy-studio`.

### Read-Only

- `id` (String) The unique token ID generated by Sanity.
- `key` (String, Sensitive) The token value. This value can be used for making authenticated requests against the API with the permissions indicated by the role name.

