# Terraform Apply Command 🚀

Hello everyone! 👋  

In this lecture, we will discuss the **Terraform apply** command, which is used to **apply infrastructure changes**.

---

## Terraform Apply Overview 🛠️
- **Command:** `terraform apply`  
- **Purpose:** Apply the Terraform configuration to the cloud platform (AWS, Azure, GCP, etc.).  
- **Requirement:** Must be run **after `terraform plan`** to review the execution plan.  
- **Confirmation:** The command will prompt for **confirmation** before applying changes.  

---

## How Terraform Apply Works 🔍
1. Applies the configuration defined in Terraform files.  
2. Prompts the user:

3. User must type **`yes`** to proceed.  
4. Executes the changes and creates/modifies resources in the cloud.  
5. Example scenario:
- Creating a **VPC resource**.  
- Shows details such as the **CIDR range**.  
- Some details will be known only after applying.  

---

## Key Points ✅
- **Command Name:** `terraform apply`  
- **Purpose:** Apply infrastructure changes to the cloud.  
- **Confirmation Required:** User must approve changes by typing `yes`.  
- **Benefit:** Ensures that the planned infrastructure is actually deployed.

---

## 5 Basic Exam Questions & Answers 🎓

1. **Q:** What is the purpose of `terraform apply`?  
**A:** To deploy the infrastructure defined in Terraform configuration files.

2. **Q:** Does `terraform apply` require confirmation?  
**A:** Yes, the user must type `yes` to proceed.

3. **Q:** Can `terraform apply` be used without running `terraform plan`?  
**A:** Yes, but it is best practice to run `terraform plan` first.

4. **Q:** Which platforms can `terraform apply` deploy to?  
**A:** AWS, Azure, GCP, or any supported cloud provider.

5. **Q:** Does `terraform apply` modify local Terraform files?  
**A:** No, it only applies changes to the cloud infrastructure.

---

## 5 Basic Interview Questions & Answers 💼

1. **Q:** Why is `terraform apply` important?  
**A:** It is the command that actually deploys the infrastructure to the cloud.

2. **Q:** What happens if you type `no` at the confirmation prompt?  
**A:** The command aborts and no changes are applied.

3. **Q:** Can you run `terraform apply` multiple times?  
**A:** Yes, Terraform will detect changes and only apply new or modified resources.

4. **Q:** How does `terraform apply` relate to `terraform plan`?  
**A:** `terraform plan` previews changes, while `terraform apply` executes them.

5. **Q:** Can `terraform apply` create multiple resources at once?  
**A:** Yes, it applies all resources defined in the configuration.

---

## 5 Advanced Exam Questions & Answers 🎓⚡

1. **Q:** How can `terraform apply` be automated in CI/CD pipelines?  
**A:** By using `terraform apply -auto-approve` in scripts to bypass manual confirmation.

2. **Q:** What happens if `terraform apply` fails midway?  
**A:** Terraform will stop and maintain the state of resources that were successfully applied.

3. **Q:** How does Terraform track changes applied by `terraform apply`?  
**A:** Changes are tracked in the **Terraform state file** (`terraform.tfstate`).

4. **Q:** Can `terraform apply` handle dependencies between resources?  
**A:** Yes, Terraform automatically orders resource creation based on dependencies.

5. **Q:** What is the difference between `terraform apply` and `terraform destroy`?  
**A:** `terraform apply` creates or updates resources; `terraform destroy` deletes resources.

---

## 5 Advanced Interview Questions & Answers 💼⚡

1. **Q:** How can you ensure `terraform apply` is idempotent?  
**A:** Terraform ensures idempotency by comparing desired state in configuration with the current state.

2. **Q:** What flags are commonly used with `terraform apply` for advanced usage?  
**A:** Flags like `-auto-approve`, `-refresh-only`, and `-var-file` for automation and customization.

3. **Q:** How does Terraform handle errors during `terraform apply`?  
**A:** Terraform halts on errors and allows you to fix the issue before retrying.

4. **Q:** Can `terraform apply` create resources in multiple regions simultaneously?  
**A:** Yes, if resources are defined for different providers or regions in the configuration.

5. **Q:** How can `terraform apply` be used safely in production environments?  
**A:** Run `terraform plan` first, review the execution plan, and then apply changes with approval.

---

