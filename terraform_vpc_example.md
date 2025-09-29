# 🌐  creating two vpc resource using count meta argument - Terraform AWS VPC Example

This repository demonstrates creating multiple AWS VPCs using Terraform.  
The configuration includes provider setup, variables, and a VPC resource.

---

## 📌 Terraform Provider Configuration (`main.tf`)

The `main.tf` file configures the AWS provider and creates VPC resources.

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

# Configure the AWS Provider
provider "aws" {
  region = var.region
}

# Create VPCs
resource "aws_vpc" "VPC-T" {
  count      = 2
  cidr_block = element(var.vpc_cidrs, count.index)
  tags = {
    Name = "VPC-T-0${count.index+1}"
  }
}
```

**Description:**

- `terraform { required_providers { ... } }` → Specifies the AWS provider and version.
- `provider "aws"` → Configures the AWS provider using the `region` variable.
- `resource "aws_vpc"` → Creates two VPCs based on the list of CIDRs provided in `variables.tf`.
- `count` → Used to create multiple instances of the resource.
- `element(var.vpc_cidrs, count.index)` → Selects the corresponding CIDR for each VPC.
- `tags` → Adds a name to each VPC dynamically.

---

## 📌 Variables (`variables.tf`)

The `variables.tf` file defines input variables for the Terraform configuration.

```hcl
variable "region" {
  type        = string
  description = "Please enter AWS region name"
  default     = "ap-southeast-1"
}

variable "vpc_cidrs" {
  type        = list(string)
  description = "This is a list of VPC CIDR ranges"
  default     = ["172.16.0.0/16", "192.168.0.0/16"]
}
```

**Description:**

- `variable "region"` → AWS region where the resources will be created. Default is `ap-southeast-1`.
- `variable "vpc_cidrs"` → List of CIDR blocks for the VPCs to be created. Default contains two CIDRs.

---

## 📌 How to Use

1. **Initialize Terraform**  
```bash
terraform init
```

2. **Format the Configuration**  
```bash
terraform fmt
```

3. **Validate Configuration**  
```bash
terraform validate
```

4. **Plan the Deployment**  
```bash
terraform plan
```

5. **Apply the Configuration**  
```bash
terraform apply
```

---

## 📌 Notes

- This configuration creates **two VPCs** using the CIDR blocks defined in `variables.tf`.
- The `count` parameter allows dynamic creation of multiple resources.
- Modify `variables.tf` to add additional CIDRs or change the AWS region.

---

## 📌 Optional Commands

- Destroy created resources:  
```bash
terraform destroy
```

- Apply changes with confirmation:  
```bash
terraform apply
```

---