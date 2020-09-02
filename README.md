# AWS VPC Flow Log module for Terraform [![CircleCI](https://circleci.com/gh/GSA/terraform-vpc-flow-log.svg?style=svg)](https://circleci.com/gh/GSA/terraform-vpc-flow-log)

This is a reusable Terraform module for setting up [VPC flow logs](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/flow-logs.html) in Amazon Web Services.

## Usage

```hcl
module "flow_logs" {
  source = "github.com/GSA/terraform-vpc-flow-log"
  vpc_id = "${aws_vpc.main.id}"
}
```

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| aws | n/a |
| template | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| log\_group\_name | Defaults to `$${default_log_group_name}` | `string` | `""` | no |
| prefix | The prefix for the resource names. You will probably want to set this to the name of your VPC, if you have multiple. | `string` | `"vpc"` | no |
| tags | A map containing tags to apply to the cloudwatch\_log\_group | `map` | `{}` | no |
| traffic\_type | https://www.terraform.io/docs/providers/aws/r/flow_log.html#traffic_type | `string` | `"ALL"` | no |
| vpc\_id | n/a | `any` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| log\_group\_name | The name of the created cloudwatch log group |

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
