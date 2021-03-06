# Test Inject

## Input

```yaml
- name: Should generate README.md for tf12_inject and push up all changes
  uses: ./
  with:
    working-dir: examples/tf12_inject
    output-file: README.md
    args: --sort-by-required
    indention: 3
    git-push: true
    git-commit-message: "terraform-docs: automated action"
```

## Verify

- Should inject below Usage
- Should push up changes on build with commit message 'terraform-docs: automated action'

## Usage

<!--- BEGIN_TF_DOCS --->
### Requirements

| Name | Version |
|------|---------|
| aws | ~> 2.20.0 |
| consul | >= 2.4.0 |

### Providers

| Name | Version |
|------|---------|
| aws | ~> 2.20.0 |
| consul | >= 2.4.0 |

### Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| subnet\_ids | A list of subnet ids to use | `list(string)` | n/a | yes |
| vpc\_id | The id of the vpc | `string` | n/a | yes |
| extra\_environment | List of additional environment variables | <pre>list(object({<br>    name  = string<br>    value = string<br>  }))</pre> | `[]` | no |
| extra\_tags | Additional tags | `map(string)` | `{}` | no |
| instance\_count | Number of instances to create | `number` | `1` | no |
| instance\_name | Instance name prefix | `string` | `"test-"` | no |

### Outputs

| Name | Description |
|------|-------------|
| vpc\_id | The Id of the VPC |

<!--- END_TF_DOCS --->
