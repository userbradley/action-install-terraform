# GitHub Action: Install Terraform

![Pets at Home](https://img.shields.io/badge/Pets%20At%20Home-%23000000.svg?style=for-the-badge&logo=userbradley&logoColor=#4BA840)

This action is designed to install Terraform by using the `provider.tf` version of terraform requested

## Quick Start

```yaml
name: Install terraform with specified version

on: [push]
jobs:
  terraform:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
      - name: Install Terraform
        uses: userbradley/action-install-terraform@v1.2.0
        with:
          providerFileLocation: "terraform"
```

## Terraform Wrapper

```yaml
name: Install terraform with specified version

on: [push]
jobs:
  terraform:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
      - name: Install Terraform
        uses: userbradley/action-install-terraform@v1.2.0
        with:
          providerFileLocation: "terraform"
          wrapper: true
```

Assumes your directory structure is as below:

```text
.
└── repo
    ├── .github
    │   └── workflows
    │       └── install-terraform.yml
    └── terraform
        ├── backend.tf
        ├── main.tf
        └── provider.tf
```

The workflow will inspect the `provider.tf` file and install the required terraform version as specified in

```hcl
terraform {
  required_version = "1.5.3"
}
```

## Inputs

| Input Name             | Required | Default Value         | Example                          |
|------------------------|----------|-----------------------|----------------------------------|
| `providerFileLocation` | `no`     | `terraform/templates` | `terraform/deployments/puppy-ui` |
| `wrapper`              | `no`     | `false`               | `true`                           |

---

Created by Bradley