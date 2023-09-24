# GitHub Action: Install Terraform


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
        uses: actions/checkout@v3
      - name: Install Terraform
        uses: userbradley/action-install-terraform@v1.0.0
        with:
          providerFileLocation: "terraform"
```

Below assumes your directory structure is as below:


The workflow will inspect the `provider.tf` file and install the required terraform version as specified in 

```hcl
terraform {
  required_version = "1.5.3"
}
```

## Inputs

| Input Name             | Required | Default Value | Example                          |
|------------------------|----------|---------------|----------------------------------|
| `providerFileLocation` | `no`     | `null`        | `terraform/deployments/puppy-ui` |

---

Created by Bradley
