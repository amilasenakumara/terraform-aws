# 🌍 Terraform Commands Cheatsheet

A comprehensive Terraform commands reference with **description** and **PowerShell example code**.

---

## 1️⃣ Initialize Terraform Directory

**Description:**
Sets up a working directory for Terraform. Downloads required providers and modules.

**PowerShell Code:**
```powershell
terraform init
```

---

## 2️⃣ Format Terraform Configuration

**Description:**
Automatically formats Terraform files to ensure proper indentation and readability.

**PowerShell Code:**
```powershell
terraform fmt
```

---

## 3️⃣ Validate Terraform Configuration

**Description:**
Checks the syntax and internal consistency of Terraform files without applying changes.

**PowerShell Code:**
```powershell
terraform validate
```

---

## 4️⃣ Create an Execution Plan

**Description:**
Shows a blueprint of changes Terraform will make to the infrastructure. Does not apply changes.

**PowerShell Code:**
```powershell
terraform plan
```

---

## 5️⃣ Apply Terraform Configuration

**Description:**
Applies the Terraform plan and provisions infrastructure on the cloud platform.

**PowerShell Code:**
```powershell
terraform apply
```

Optional: use `-auto-approve` to skip confirmation:
```powershell
terraform apply -auto-approve
```

---

## 6️⃣ Destroy Terraform Managed Infrastructure

**Description:**
Destroys resources managed by Terraform. Use `-target` to destroy specific resources.

**PowerShell Code:**
```powershell
terraform destroy
```

Destroy specific resource example:
```powershell
terraform destroy -target="aws_vpc.VPC-T"
```

---

## 7️⃣ Show Terraform State

**Description:**
Displays detailed Terraform state, including resource IDs and attributes.

**PowerShell Code:**
```powershell
terraform show
```

---

## 8️⃣ List Terraform Resources

**Description:**
Lists resources in the current state file.

**PowerShell Code:**
```powershell
terraform state list
```

---

## 9️⃣ Inspect Terraform Resource

**Description:**
Shows detailed information about a specific resource in the state.

**PowerShell Code:**
```powershell
terraform state show <resource_name>
```

---

## 🔟 Remove Resource from State

**Description:**
Removes a resource from Terraform state without destroying it on cloud provider.

**PowerShell Code:**
```powershell
terraform state rm <resource_name>
```

---

## 1️⃣1️⃣ Import Existing Resource

**Description:**
Imports an existing cloud resource into Terraform state.

**PowerShell Code:**
```powershell
terraform import <resource_type.name> <resource_id>
```

Example:
```powershell
terraform import aws_vpc.VPC-T vpc-0abc12345
```

---

## 1️⃣2️⃣ Output Terraform Values

**Description:**
Shows output variables defined in Terraform configuration.

**PowerShell Code:**
```powershell
terraform output
```

Show a specific output:
```powershell
terraform output vpc_id
```

---

## 1️⃣3️⃣ Refresh Terraform State

**Description:**
Updates Terraform state to match the real infrastructure without applying changes.

**PowerShell Code:**
```powershell
terraform refresh
```

---

## 1️⃣4️⃣ Graph Terraform Resources

**Description:**
Generates a visual representation of Terraform resources and dependencies.

**PowerShell Code:**
```powershell
terraform graph
```

Optional: output to a PNG graph:
```powershell
terraform graph | dot -Tpng > graph.png
```

---

## 1️⃣5️⃣ Workspace Management

**Description:**
Manage multiple environments (e.g., dev, staging, prod).

**PowerShell Code:**
```powershell
terraform workspace list
terraform workspace new dev
terraform workspace select dev
terraform workspace show
```

---

## 1️⃣6️⃣ Versioning Terraform

**Description:**
Check Terraform version installed on your machine.

**PowerShell Code:**
```powershell
terraform version
```

---

## ✅ Best Practices

- Always run `terraform init` first in a new directory.  
- Run `terraform fmt` before committing files.  
- Validate configuration with `terraform validate`.  
- Use `terraform plan` before `terraform apply`.  
- Keep `.tfvars` files for environment-specific variables.  
- Never commit sensitive secrets in Terraform files.  
- Use workspaces for multi-environment setups.  

---

## 🎓 Quick Questions & Answers

**Q:** How to skip confirmation during apply?  
**A:** Use `terraform apply -auto-approve`.

**Q:** How to destroy a single resource?  
**A:** Use `terraform destroy -target="<resource_name>"`.

**Q:** How to list all Terraform-managed resources?  
**A:** Use `terraform state list`.

**Q:** How to import an existing resource?  
**A:** Use `terraform import <resource_type.name> <resource_id>`.

**Q:** How to visualize Terraform resources?  
**A:** Use `terraform graph | dot -Tpng > graph.png`.

