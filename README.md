<h1 align="center">
    Terraform Git Hooks 
</h1>
<p align="center" style="font-size: 1.2rem;"> pre-commit hooks to keep Terraform configurations in a good share ;) </p>

<hr />

* `fmt` - Rewrites all Terraform configuration files to a canonical format.
* `validate_without_variables` - Validates all Terraform configuration files without checking whether all required 
variables were set.
* `validate_with_variables` - Validates all Terraform configuration files and checks whether all required variables were specified.
* `docs` - Inserts input and output documentation into `README.md`.

## Notes about hooks

1. `validate_without_variables` and `validate_with_variables` will not work if variables are being set 
dynamically (eg, when using [Terragrunt](https://github.com/gruntwork-io/terragrunt)). Use `terragrunt validate` command instead.

1. `docs` will insert/update documentation generated by [terraform-docs](https://github.com/segmentio/terraform-docs) between markers - `<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->` and `<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->` if they are present in `README.md`. Make sure that `terraform-docs` is installed.

## Example

`.pre-commit-config.yaml`:

```yaml
- repo: git://github.com/devops-talks/terraform-git-hook
  hooks:
    - id: fmt
    - id: docs
```

Enjoy the clean and documented code!

---
## 👬 Contribution

- Open pull request with improvements
- Discuss ideas in issues
- Reach out with any feedback [![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/anmol_nagpal.svg?style=social&label=Follow%20%40anmol_nagpal)](https://twitter.com/anmol_nagpal)
