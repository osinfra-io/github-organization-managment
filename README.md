# <img align="left" width="45" height="45" src="https://user-images.githubusercontent.com/1610100/201473670-e0e6bdeb-742f-4be1-a47a-3506309620a3.png"> GitHub Organization: osinfra.io

**[GitHub Actions](https://github.com/osinfra-io/github-organization-managment/actions):**

[![Dependabot](https://github.com/osinfra-io/github-organization-managment/actions/workflows/dependabot.yml/badge.svg)](https://github.com/osinfra-io/github-organization-managment/actions/workflows/dependabot.yml)

**[Bridgecrew](https://www.bridgecrew.cloud/projects?types=Passed&repository=osinfra-io%2Fgithub-organization-management&branch=main):**

[![Infrastructure Tests](https://www.bridgecrew.cloud/badges/github/osinfra-io/github-organization-management/general)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=osinfra-io%2Fgithub-organization-management&benchmark=INFRASTRUCTURE+SECURITY)

This repository manages the osinfra.io GitHub organization.

## Development

See the documentation for setting up a local development environment [here](https://docs.osinfra.io).

Tools in use:

- [checkov](https://github.com/bridgecrewio/checkov)
- [pre-commit](https://github.com/pre-commit/pre-commit)
- [pre-commit-terraform](https://github.com/antonbabenko/pre-commit-terraform)
- [terraform-docs](https://github.com/terraform-docs/terraform-docs)

## Terraform Documentation
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
### Providers

| Name | Version |
|------|---------|
| <a name="provider_github"></a> [github](#provider_github) | 5.9.1 |
| <a name="provider_random"></a> [random](#provider_random) | 3.4.3 |

### Modules

No modules.

### Resources

| Name | Type |
|------|------|
| [github_actions_organization_secret.this](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/actions_organization_secret) | resource |
| [github_branch_protection.this](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/branch_protection) | resource |
| [github_membership.this](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/membership) | resource |
| [github_repository.this](https://registry.terraform.io/providers/integrations/github/latest/docs/resources/repository) | resource |
| [random_password.this](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/password) | resource |

### Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_admins"></a> [admins](#input_admins) | A set of admins to add to the organization | `set(string)` | n/a | yes |
| <a name="input_github_token"></a> [github_token](#input_github_token) | The GitHub token used for managing the organization | `string` | n/a | yes |
| <a name="input_organization_secrets"></a> [organization_secrets](#input_organization_secrets) | Map of secrets to add to the organization | <pre>map(object({<br>    description = string<br>    visibility  = string<br>  }))</pre> | n/a | yes |
| <a name="input_repositories"></a> [repositories](#input_repositories) | Map of repositories to create | <pre>map(object({<br>    description = string<br>    template    = optional(string)<br>    topics      = optional(list(string))<br><br>    # In most cases, the visibility of your organizations repository should be private.<br>    # However, we are keeping our code public to encourage others to learn from our work.<br><br>    visibility = optional(string, "public")<br>  }))</pre> | n/a | yes |
| <a name="input_members"></a> [members](#input_members) | A set of members to add to the organization | `set(string)` | `[]` | no |

### Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
