# 🌐 Terraform Variables – Lists & Indexing Guide

Terraform variables allow you to **manage infrastructure dynamically**. This guide focuses on using **lists** and accessing elements via **indexing**, along with dynamic resource creation using the `count` meta-argument.

---

## 📌 Key Concepts

- **List Variable**: A collection of values enclosed in square brackets `[]`.
- **Indexing**: Access elements of a list using `var.<variable_name>[index]`.
- **Count Meta-Argument**: Dynamically creates resources based on the number of elements in a list.

---

## 📌 Example: List of CIDR Blocks

```hcl
variable "subnet_cidr_block" {
  type    = list(string)
  default = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
}
```

### 🔹 Accessing List Elements

| Index | Expression                         | Value             |
|-------|------------------------------------|-----------------|
| 0     | `var.subnet_cidr_block[0]`         | `"10.0.1.0/24"` |
| 1     | `var.subnet_cidr_block[1]`         | `"10.0.2.0/24"` |
| 2     | `var.subnet_cidr_block[2]`         | `"10.0.3.0/24"` |

> ✅ Note: Indexing starts at **0**. The first element is always `[0]`.

---

## 📌 Using Lists for Dynamic Resource Creation

When creating multiple resources (like subnets), use **`count`** with the **length of the list**:

```hcl
resource "aws_subnet" "example" {
  count = length(var.subnet_cidr_block)

  cidr_block = var.subnet_cidr_block[count.index]
}
```

### 🔹 How it works

1. `length(var.subnet_cidr_block)` returns the number of elements in the list.
2. Terraform creates that many resources dynamically.
3. `count.index` ranges from `0` to `length - 1`.
4. Each resource gets its corresponding CIDR block from the list.

---

## 📌 Example Execution Flow

1. List has 3 elements → `length = 3`.
2. Resource runs 3 times:
   - **Iteration 0**: `cidr_block = var.subnet_cidr_block[0]` → First subnet created.
   - **Iteration 1**: `cidr_block = var.subnet_cidr_block[1]` → Second subnet created.
   - **Iteration 2**: `cidr_block = var.subnet_cidr_block[2]` → Third subnet created.

> Using `length()` prevents hardcoding the number of resources. If list size changes, Terraform automatically adjusts `count`.

---

## 📌 Important Notes

- Always use **square brackets** to access list elements.
- Indexing always starts at **0**.
- The `count` meta-argument ensures resources are created dynamically based on the list size.
- Avoid hardcoding values for scalability and maintainability.

---

# 🌐 Terraform VPC and Subnet Example

This Terraform configuration demonstrates how to create an AWS VPC and multiple subnets dynamically using variables and the `count` meta-argument.

---

## 📄 Terraform Configuration Overview


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
  #region = "us-east-1"
  region = var.region
}

# Create a VPC
resource "aws_vpc" "VPC-T" {
  cidr_block = "10.0.0.0/16"
  tags = {
    Name = "VPC-T-03"
  }
}

resource "aws_subnet" "subnet-t" {
    count = length(var.subnet_Ciderblock)
    cidr_block = var.subnet_Ciderblock[count.index]
    vpc_id = aws_vpc.VPC-T.id
    tags = {
      Name = "VPC-T-03-SN0${count.index+1}"
    }
}
```




---

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}
```

- **terraform { }**: Specifies Terraform settings for the configuration.
- **required_providers**: Defines which provider(s) Terraform should use.
  - **aws**: Specifies AWS provider.
  - **source**: Indicates the source for the provider (HashiCorp registry).
  - **version**: Version constraint for the provider.

---

```hcl
provider "aws" {
  #region = "us-east-1"
  region = var.region
}
```

- **provider "aws" { }**: Configures the AWS provider.
- **region = var.region**: Sets the AWS region dynamically using a Terraform variable `region`.
- The commented line shows an example of hardcoding the region, but using variables is more flexible.

---

```hcl
resource "aws_vpc" "VPC-T" {
  cidr_block = "10.0.0.0/16"
  tags = {
    Name = "VPC-T-03"
  }
}
```

- **resource "aws_vpc" "VPC-T" { }**: Creates an AWS VPC resource with the Terraform name `VPC-T`.
- **cidr_block**: The network range for the VPC (`10.0.0.0/16` in this case).
- **tags**: Key-value pairs to assign metadata to the VPC.
  - **Name = "VPC-T-03"**: Tags the VPC in AWS as `VPC-T-03`.

---

```hcl
resource "aws_subnet" "subnet-t" {
    count = length(var.subnet_Ciderblock)
    cidr_block = var.subnet_Ciderblock[count.index]
    vpc_id = aws_vpc.VPC-T.id
    tags = {
      Name = "VPC-T-03-SN0${count.index+1}"
    }
}
```

- **resource "aws_subnet" "subnet-t" { }**: Creates AWS subnets dynamically.
- **count = length(var.subnet_Ciderblock)**: Creates as many subnets as elements in the variable list `subnet_Ciderblock`.
- **cidr_block = var.subnet_Ciderblock[count.index]**: Assigns each subnet a CIDR block from the list.
  - **count.index**: Current index of the loop (starts at `0`).
- **vpc_id = aws_vpc.VPC-T.id**: Associates the subnet with the VPC created earlier.
  - `.id` is required because `vpc_id` expects a string, not the whole VPC object.
- **tags**: Metadata for the subnet.
  - **Name = "VPC-T-03-SN0${count.index+1}"**: Dynamically names subnets (`VPC-T-03-SN01`, `VPC-T-03-SN02`, ...).

---

## ✅ Key Concepts

- **count**: Used for creating multiple instances of a resource dynamically.
- **count.index**: Provides the index for each instance when using `count`.
- **Variables**: `var.region` and `var.subnet_Ciderblock` make the code flexible.
- **Dynamic naming**: Using `${count.index+1}` to create sequential subnet names.

---

## 📌 Variables Example

```hcl
variable "region" {
  type        = string
  description = "AWS region to deploy resources"
  default     = "ap-southeast-1"
}

variable "subnet_Ciderblock" {
  type        = list(string)
  description = "List of subnet CIDR blocks"
  default     = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
}
```

- `region` specifies the AWS region.
- `subnet_Ciderblock` is a list of subnet CIDR blocks, used in the subnet resource with `count`.

---

## 📝 Summary

- Creates **one VPC** and **multiple subnets** dynamically.
- Uses `count` and `count.index` to iterate over subnet CIDR blocks.
- Uses variables for **region** and **subnet CIDRs**.
- Subnet names are dynamically generated using **count.index**.

---

## 📚 Recommended Commands

```bash
terraform init      # Initialize Terraform
terraform plan      # Preview changes
terraform apply     # Apply changes
terraform destroy   # Destroy resources
```

---

# 🗑️ Terraform Destroy Commands – Targeted Resource Deletion

This section provides a quick reference for **destroying specific Terraform-managed resources** using the `-target` flag. It also explains how to use `-auto-approve` to skip manual confirmation.

---

## 📌 Destroying Specific Subnets

### 1️⃣ Destroy the third subnet
```bash
terraform destroy -target="aws_subnet.subnet-t[2]"
```
**Description:**  
Destroys the third subnet (index `2`) defined in `aws_subnet.subnet-t`. Terraform will prompt for approval before executing.

---

### 2️⃣ Destroy the second subnet
```bash
terraform destroy -target="aws_subnet.subnet-t[1]"
```
**Description:**  
Destroys the second subnet (index `1`) in `aws_subnet.subnet-t`. Approval is required unless `-auto-approve` is added.

---

### 3️⃣ Destroy the first subnet without approval
```bash
terraform destroy -target="aws_subnet.subnet-t[0]" -auto-approve
```
**Description:**  
Destroys the first subnet (index `0`) immediately without prompting for confirmation. Useful for automation scripts.

---

## 📌 Destroying the VPC

### 4️⃣ Destroy the VPC without approval
```bash
terraform destroy -target="aws_vpc.VPC-T" -auto-approve
```
**Description:**  
Destroys the VPC resource `VPC-T` immediately, skipping manual approval. All dependent resources not explicitly targeted may cause errors if they still exist.

---

## ⚠️ Important Notes

- Terraform targets resources using **resource type + name + index**.  
- The `-auto-approve` flag should be used cautiously; it executes destruction immediately.  
- Always ensure no critical resources depend on the target resource before destroying.


---

## 🎓 Exam Questions & Answers

1. **Q:** What is a list variable in Terraform?  
   **A:** A collection of values enclosed in square brackets `[]`.

2. **Q:** How do you access the first element of a list?  
   **A:** Using `var.<variable_name>[0]`.

3. **Q:** What does `count = length(var.list_var)` do?  
   **A:** Dynamically creates resources equal to the number of elements in the list.

4. **Q:** Why start index from zero in lists?  
   **A:** Terraform uses zero-based indexing for list elements.

5. **Q:** How can you avoid hardcoding resource count?  
   **A:** Use `count = length(var.list_variable)` to match list size.

---

## 💼 Interview Questions & Answers

1. **Q:** Why use list variables in Terraform?  
   **A:** To manage multiple values dynamically and avoid repetitive code.

2. **Q:** What is `count.index`?  
   **A:** Index of the current iteration when using the `count` meta-argument.

3. **Q:** How do you dynamically assign resources based on a list?  
   **A:** By setting `count = length(var.list)` and using `var.list[count.index]`.

4. **Q:** Can list elements be accessed without using an index?  
   **A:** No, Terraform requires the index to access specific elements.

5. **Q:** What is the advantage of using `length()` over hardcoding?  
   **A:** It ensures resources scale automatically when the list changes.

---

## 🎓 Advanced Exam Questions & Answers

1. **Q:** How do you use nested lists in Terraform variables?  
   **A:** Use `list(list(string))` and access with `var.list[index1][index2]`.

2. **Q:** Can you combine `for_each` with list variables?  
   **A:** Yes, using `for_each = toset(var.list_variable)`.

3. **Q:** How does Terraform handle an empty list?  
   **A:** `length()` returns `0`, and no resources are created.

4. **Q:** How can you map multiple values to multiple resources?  
   **A:** Use `count.index` with corresponding lists for each attribute.

5. **Q:** Can list variables accept dynamic values from other resources?  
   **A:** Yes, using outputs from other modules or data sources.

---

## 💼 Advanced Interview Questions & Answers

1. **Q:** How do you scale resources dynamically with changing list sizes?  
   **A:** Use `count = length(var.list_variable)` to automatically adjust resource count.

2. **Q:** What is the difference between `count` and `for_each` for list variables?  
   **A:** `count` uses index numbers, `for_each` uses keys for iteration.

3. **Q:** How do you access elements of a list of objects?  
   **A:** Use `var.list_var[index].attribute_name`.

4. **Q:** How do you prevent Terraform from recreating resources if the list changes?  
   **A:** Use lifecycle rules like `ignore_changes` on relevant attributes.

5. **Q:** Can you pass lists as module input variables?  
   **A:** Yes, Terraform modules accept lists and handle dynamic resource creation.

---





