# Terraform Plan Command 📊

Hello everyone! 👋  

So far, we discussed the following Terraform commands:
- `terraform init` – Initializes the working directory to become a Terraform directory.  
- `terraform fmt` – Formats the configuration files for consistency.  
- `terraform validate` – Validates the configuration for syntax and internal consistency.  

---

## Terraform Plan Overview 🛠️
- **Command:** `terraform plan`  
- **Purpose:** Creates an **execution plan** for your Terraform configuration.  
- **Best Practice:** Always run this command **before `terraform apply`**.  

---

## What Terraform Plan Does 🔍
- Shows a **blueprint** of what Terraform will create or change on the AWS platform.  
- Lets you **preview the changes** before actually applying them.  
- Does **not apply** any changes; it only displays the plan.  

---

## Example Scenario 🌐
- Suppose we are creating a **VPC resource** in our Terraform configuration.  
- Running `terraform plan` will show:
  - Which resources will be **added**, **changed**, or **destroyed**.  
- Example output:
- **1 to add** → creating a new VPC resource.  
- **0 to change** → no existing resources will be modified.  
- **0 to destroy** → nothing will be deleted.  

---

## Key Points ✅
- **Command Name:** `terraform plan`  
- **Purpose:** Preview infrastructure changes without applying them.  
- **Benefit:** Helps avoid mistakes by showing the **execution plan** in advance.  
- **Best Practice:** Always run before `terraform apply`.

---

## 5 Basic Exam Questions & Answers 🎓

1. **Q:** What is the purpose of `terraform plan`?  
 **A:** To preview the execution plan and see what changes Terraform will make.

2. **Q:** Does `terraform plan` apply changes to the infrastructure?  
 **A:** No, it only shows a blueprint of the changes.

3. **Q:** Why is it a best practice to run `terraform plan`?  
 **A:** To review and validate planned changes before applying them.

4. **Q:** What does "1 to add, 0 to change, 0 to destroy" mean?  
 **A:** It means one resource will be created, none changed, and none destroyed.

5. **Q:** Can `terraform plan` help avoid configuration mistakes?  
 **A:** Yes, it previews changes and highlights potential issues.

---

## 5 Basic Interview Questions & Answers 💼

1. **Q:** Why should `terraform plan` be used before `terraform apply`?  
 **A:** It provides a safe way to review planned changes before applying them.

2. **Q:** What is an execution plan in Terraform?  
 **A:** A blueprint showing which resources will be added, changed, or destroyed.

3. **Q:** Does `terraform plan` require initialization of the directory?  
 **A:** Yes, the directory must be initialized using `terraform init`.

4. **Q:** Can `terraform plan` preview changes for multiple resources?  
 **A:** Yes, it shows planned actions for all resources in the configuration.

5. **Q:** Will `terraform plan` modify your AWS infrastructure?  
 **A:** No, it only previews the changes.

---

## 5 Advanced Exam Questions & Answers 🎓⚡

1. **Q:** How does `terraform plan` help in team collaboration?  
 **A:** By showing a clear blueprint, team members can review and approve changes before applying.

2. **Q:** Can `terraform plan` detect conflicts with existing resources?  
 **A:** Yes, it highlights potential conflicts or misconfigurations.

3. **Q:** How can `terraform plan` be integrated into CI/CD pipelines?  
 **A:** By running it in automated pipelines to preview infrastructure changes before deployment.

4. **Q:** What is the difference between `terraform plan` and `terraform apply`?  
 **A:** `terraform plan` previews changes; `terraform apply` actually creates, updates, or destroys resources.

5. **Q:** Can `terraform plan` be used with variables and workspaces?  
 **A:** Yes, it evaluates changes based on the provided variables and selected workspace.

---

## 5 Advanced Interview Questions & Answers 💼⚡

1. **Q:** How can `terraform plan` improve infrastructure reliability?  
 **A:** By allowing review and approval of planned changes, reducing the risk of errors.

2. **Q:** What flags can be used with `terraform plan` for advanced usage?  
 **A:** Flags like `-out`, `-var`, and `-refresh` for customized plans and saving execution plans.

3. **Q:** How does `terraform plan` interact with remote state?  
 **A:** It reads the current state from the backend to determine what changes are needed.

4. **Q:** Can `terraform plan` detect changes outside Terraform?  
 **A:** It can show drift if the state is refreshed but cannot modify external changes.

5. **Q:** How can `terraform plan` output be used in automated approvals?  
 **A:** Save the plan with `-out` and use it in automated pipelines for review before `apply`.

---
