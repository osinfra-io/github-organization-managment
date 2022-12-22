# <img align="left" width="45" height="45" src="https://user-images.githubusercontent.com/1610100/201473670-e0e6bdeb-742f-4be1-a47a-3506309620a3.png"> GitHub Organization: osinfra.io

**[GitHub Actions](https://github.com/osinfra-io/github-organization-management/actions):**

[![Dependabot](https://github.com/osinfra-io/github-organization-management/actions/workflows/dependabot.yml/badge.svg)](https://github.com/osinfra-io/github-organization-management/actions/workflows/dependabot.yml)

**[Bridgecrew](https://www.bridgecrew.cloud/projects?types=Passed&repository=osinfra-io%2Fgithub-organization-management&branch=main):**

[![Infrastructure Tests](https://www.bridgecrew.cloud/badges/github/osinfra-io/github-organization-management/general)](https://www.bridgecrew.cloud/link/badge?vcs=github&fullRepo=osinfra-io%2Fgithub-organization-management&benchmark=INFRASTRUCTURE+SECURITY)

This repository is an example of a collection of sensible defaults for managing your GitHub organization using [Terraform](https://www.terraform.io), concepts from [Team Topologies](https://teamtopologies.com/), and practices learned from software development.

## <img align="left" width="35" height="35" src="https://user-images.githubusercontent.com/1610100/209028188-b880baa5-cf8f-44c7-bdb5-f2c788ccd013.png"> Team Topologies

Simple but comprehensive information for the platform provides a single point of entry for anyone wanting to know more about the services, report an issue or find out the current status, roadmap, and so on. - [Team Topologies: Thin Platform Template](https://github.com/TeamTopologies/Thin-Platform-template)

### Services documentation

- [docs.osinfra.io](https://docs.osinfra.io/github/organization-management)

### Service interfaces

- `github_membership` service interface: [GitHub Issue](https://github.com/osinfra-io/github-organization-management/issues/new?assignees=&labels=enhancement&template=github-membership.yml&title=Membership+Request)

### Response times

- Responsible team: [GitHub Platform Team](https://github.com/orgs/osinfra-io/teams/github-platform-team)
- Response time for incidents: `60 minutes`
- Response time for other incidents: `120 minutes`
- Response time for support:  `60 minutes`
- Response time for feedback: `30 minutes`

### Roadmap

- Link to roadmap: [GitHub Project](https://github.com/orgs/osinfra-io/projects/5/views/1)

### Communication channels

#### To report a possible incident

Contact exclusively via:

- Google Chat: [GitHub](https://chat.google.com/room/AAAAPvNvpeM?cls=7)
- Phone number:

#### To ask for support or provide feedback

Contact via any of these:

- Google Chat: [GitHub](https://chat.google.com/room/AAAAPvNvpeM?cls=7)
- Email address: [github-platform-team@osinfra.io](mailto:github-platform-team@osinfra.io)
- Phone number:
- Office hours (EST): `Weekdays 5:00 PM - 10:00 PM` `Weekends 8:00 AM - 5:00 PM`

## <img align="left" width="35" height="35" src="https://user-images.githubusercontent.com/1610100/209029142-410349b7-4b22-40a9-9d4d-729f07e2b4a2.png"> Development

See the documentation for setting up a local development environment [here](https://docs.osinfra.io).

Tools in use:

- [checkov](https://github.com/bridgecrewio/checkov)
- [pre-commit](https://github.com/pre-commit/pre-commit)
- [pre-commit-terraform](https://github.com/antonbabenko/pre-commit-terraform)
- [terraform-docs](https://github.com/terraform-docs/terraform-docs)

## Skills and Knowledge

Links to documentation and other resources required to develop and iterate in this repository successfully.

- [Encrypted secrets for an organization](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-an-organization)
- [Branch protection rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branchess)
- [Organization membership](https://docs.github.com/en/organizations/managing-membership-in-your-organization)
- [Repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories)

## Terraform documentation
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
### Providers

| Name | Version |
|------|---------|
| <a name="provider_github"></a> [github](#provider_github) | 5.12.0 |
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
| <a name="input_repositories"></a> [repositories](#input_repositories) | Map of repositories to create | <pre>map(object({<br>    description              = string<br>    enable_branch_protection = optional(bool, true)<br>    template                 = optional(string)<br>    topics                   = optional(list(string))<br><br>    # In most cases, the visibility of your organizations repository should be private.<br>    # However, we are keeping our code public to encourage others to learn from our work.<br><br>    visibility = optional(string, "public")<br>  }))</pre> | n/a | yes |
| <a name="input_members"></a> [members](#input_members) | A set of members to add to the organization | `set(string)` | `[]` | no |

### Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
