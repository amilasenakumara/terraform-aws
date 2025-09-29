# 📘 Terraform Basics – Configuration Files, Blocks & Usage

## 🌱 Introduction
- Terraform is an **Infrastructure as Code (IaC)** tool.
- Infrastructure is defined using **configuration files**.
- Files use the `.tf` extension (e.g., `main.tf`).
- Code is divided into **blocks**:
  - **Terraform Block**
  - **Provider Block**
  - **Resource Block**

---

## 📝 Configuration Files
- Set of files used to **describe infrastructure** in Terraform.
- Written in **HashiCorp Configuration Language (HCL)**.
- Main file usually named **`main.tf`**.

---

## 🔑 Key Blocks in Terraform

### 1. **Terraform Block**
- Provides required provider information.
- Example: selecting **AWS** as the cloud platform.
- Tells Terraform which provider plugin to use.

---

### 2. **Provider Block**
- Defines **configuration for the provider**.
- Example: specify **AWS region** where resources will be created.
- Involves:
  - **Downloading the provider** (via Terraform commands).
  - **Configuring provider settings** (region, authentication, etc.).

---

### 3. **Resource Block**
- Main block that **defines infrastructure components**.
- A resource can be:
  - EC2 Instance
  - S3 Bucket
  - VPC, etc.
- Example:  
  - Deploying an **EC2 instance** of type **t2.micro**.

#### Resource Block Structure:
1. **Resource Keyword** – Reserved word in Terraform.  
   Example: `resource`
2. **Resource Type** – From Terraform documentation.  
   Example: `aws_instance`, `aws_s3_bucket`
3. **Resource Name** – A **friendly internal name** managed by Terraform (not visible in AWS console).  
4. **Arguments** – Settings for the resource.  
   - Example: AMI ID, instance type, disk size, etc.

---

## 📌 Summary
- Terraform uses **configuration files (.tf)** to define infrastructure.
- Three major blocks:
  - **Terraform Block** – Provider information.  
  - **Provider Block** – Region/configuration of provider.  
  - **Resource Block** – Defines resources with type, name, and arguments.
- Resources are declared with:
  - Reserved keyword → Resource type → Friendly name → Arguments.

---

## ❓ Exam Questions & Answers

### Basic Exam Q&A
1. **Q:** What is the extension of Terraform configuration files?  
   **A:** `.tf`

2. **Q:** Name the three main blocks in a Terraform configuration.  
   **A:** Terraform block, Provider block, Resource block.

3. **Q:** What does the provider block define?  
   **A:** Region and configuration for the provider (e.g., AWS).

4. **Q:** Is the resource "friendly name" visible in AWS console?  
   **A:** No, it is only managed internally by Terraform.

5. **Q:** Which language is used in Terraform configuration files?  
   **A:** HashiCorp Configuration Language (HCL).

---

## 💼 Interview Questions & Answers

### Entry-Level
1. **Q:** What is Infrastructure as Code (IaC)?  
   **A:** It is the practice of managing and provisioning infrastructure using code instead of manual processes.

2. **Q:** Why do we need a provider block in Terraform?  
   **A:** To specify the cloud provider (e.g., AWS) and its configuration like region.

3. **Q:** How does Terraform know which resource to create?  
   **A:** From the **resource block**, which defines resource type and arguments.

4. **Q:** What is the difference between Terraform and AWS Console?  
   **A:** Terraform automates resource creation using code, AWS Console requires manual setup.

5. **Q:** What happens when you run `terraform init`?  
   **A:** It initializes the project and downloads required provider plugins.

---

## 🧠 Advanced Exam Questions & Answers

1. **Q:** Can Terraform manage resources across multiple providers?  
   **A:** Yes, by configuring multiple provider blocks (e.g., AWS, Azure, GCP).

2. **Q:** What is the difference between `terraform plan` and `terraform apply`?  
   **A:** `plan` shows execution steps without making changes, `apply` executes them.

3. **Q:** How does Terraform handle state management?  
   **A:** By storing resource information in a **state file** (`terraform.tfstate`).

4. **Q:** What is the purpose of `terraform destroy`?  
   **A:** To remove all resources defined in the configuration.

5. **Q:** Can Terraform reuse code?  
   **A:** Yes, using **modules**.

---

## 🎯 Advanced Interview Questions & Answers

1. **Q:** How does Terraform achieve idempotency?  
   **A:** By comparing the desired state (config) with the actual state and making only necessary changes.

2. **Q:** What is a Terraform state file, and why is it important?  
   **A:** It tracks infrastructure deployed, ensuring Terraform knows existing resources to prevent duplication.

3. **Q:** How do you secure Terraform state files?  
   **A:** By using remote backends with encryption (e.g., S3 with DynamoDB for locking).

4. **Q:** Explain the difference between mutable and immutable infrastructure in Terraform.  
   **A:** Mutable modifies existing resources, immutable replaces them with new ones.

5. **Q:** What strategies are used to organize Terraform code for large projects?  
   **A:** Using modules, workspaces, and separating environments (dev, staging, prod).

---

## 📂 Suggested File Name
`terraform_configuration_blocks_summary.md`
