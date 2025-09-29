# 💻 Introduction to Infrastructure as Code (IaC)

## 1. What is Infrastructure as Code (IaC)? 🏗️

- IaC allows **codifying the entire provisioning process** for infrastructure.
- Infrastructure can be **defined, provisioned, configured, updated, and destroyed using code**.
- Can manage almost any infrastructure component:
  - Servers / virtual machines
  - Databases
  - Networks
  - Storage
  - Application configuration

---

## 2. Traditional Scripts vs IaC Tools 📝

- **Shell scripts**:
  - Require programming skills.
  - Hard to maintain and reuse.
  - Complex logic and long scripts.
- **IaC Tools (Terraform, Ansible)**:
  - Simple, human-readable code.
  - Easy to maintain and version control.
  - Can replace large shell scripts with concise configuration files.

---

## 3. Examples of IaC Tools ⚙️

- **Configuration Management**:
  - Ansible, Puppet, Chef, SaltStack
- **Server Templating**:
  - Docker, Packer, Vagrant
- **Infrastructure Provisioning**:
  - Terraform, CloudFormation

---

## 4. Types of IaC Tools 🔧

### 4.1 Configuration Management Tools 🖥️

- Purpose: Install and manage software on existing infrastructure.
- Key features:
  - Maintain **consistent & standard code structure**.
  - Run on **multiple remote resources** at once.
  - **Version controlled** (playbooks/roles can be reused and distributed).
  - **Idempotent**:
    - Running the code multiple times only applies necessary changes.
    - Leaves already-configured components untouched.

### 4.2 Server Templating Tools 🏭

- Tools: Docker, Vagrant, Packer
- Purpose: Create **custom VM or container images** with all required software installed.
- Promote **immutable infrastructure**:
  - Deployed instance is not changed.
  - Updates are done by creating a new image and redeploying.
- Examples:
  - Custom AMIs on AWS
  - Docker images on DockerHub
  - VM images from osboxes.org

### 4.3 Provisioning Tools ☁️

- Tools: Terraform, CloudFormation
- Purpose: **Provision infrastructure resources** using declarative code.
- Manage resources like:
  - Servers / VMs
  - Databases
  - VPCs / subnets / security groups
  - Storage
  - Other cloud services
- Key differences:
  - CloudFormation → AWS specific
  - Terraform → Vendor-agnostic, supports multiple cloud providers

---

## 5. Advantages of Using IaC ✅

- Faster, repeatable infrastructure deployment.
- **Version control** and reuse of code.
- Reduced human errors.
- Easier management of **large-scale environments**.
- Enables automation via **API integration**.
- Supports **immutable infrastructure** principles.

---

## 6. Summary Table 📊

| IaC Type | Tools | Purpose | Key Feature |
|----------|-------|---------|-------------|
| Configuration Management | Ansible, Puppet, Chef, SaltStack | Install/manage software on existing infra | Idempotent, version-controlled |
| Server Templating | Docker, Packer, Vagrant | Create pre-configured VM/container images | Immutable infrastructure |
| Provisioning | Terraform, CloudFormation | Provision infrastructure resources | Declarative code, scalable |

---

## 7. Exam Questions & Answers ✅

1. **Q:** What is Infrastructure as Code?  
   **A:** IaC is the practice of managing and provisioning infrastructure through code instead of manual processes.

2. **Q:** Name three types of IaC tools.  
   **A:** Configuration management, server templating, provisioning tools.

3. **Q:** Give two examples of configuration management tools.  
   **A:** Ansible, Puppet.

4. **Q:** What does idempotent mean in IaC?  
   **A:** Running the same code multiple times only applies necessary changes, leaving existing configuration intact.

5. **Q:** What is immutable infrastructure?  
   **A:** Infrastructure that, once deployed, is not modified; changes are made by redeploying a new instance/image.

---

## 8. Interview Questions & Answers 💼

1. **Q:** How does Terraform differ from CloudFormation?  
   **A:** Terraform is vendor-agnostic and supports multiple cloud providers, whereas CloudFormation is AWS-specific.

2. **Q:** Why use IaC over shell scripts?  
   **A:** IaC is easier to maintain, human-readable, version-controlled, reusable, and reduces errors.

3. **Q:** Give an example of a server templating tool and its purpose.  
   **A:** Docker → create containers with pre-installed software and dependencies.

4. **Q:** What is the key advantage of idempotency in configuration management tools?  
   **A:** Ensures consistent environments and prevents unnecessary changes when code is run multiple times.

5. **Q:** How does IaC help in large-scale cloud environments?  
   **A:** Provides automated, repeatable, and scalable infrastructure deployment, reducing human errors and overhead.

---

## 9. Advanced Exam Questions & Answers ⚡

1. **Q:** Explain the difference between immutable and mutable infrastructure.  
   **A:** Immutable infrastructure is never modified after deployment; updates are applied by redeploying. Mutable infrastructure is modified in place.

2. **Q:** Name two server templating tools and describe their function.  
   **A:** Docker and Packer → create images/containers with pre-installed software for consistent deployments.

3. **Q:** How can IaC be integrated with CI/CD pipelines?  
   **A:** IaC scripts can automatically provision or update infrastructure during deployment stages.

4. **Q:** What is the main advantage of declarative code in Terraform?  
   **A:** You define the desired state, and Terraform ensures the infrastructure matches it automatically.

5. **Q:** How does IaC reduce human error in cloud deployments?  
   **A:** By codifying the entire process, automation ensures consistency and repeatability, eliminating manual mistakes.

---

## 10. Advanced Interview Questions & Answers 💡

1. **Q:** What is the difference between Ansible and Terraform?  
   **A:** Ansible focuses on configuration management (software setup), while Terraform focuses on infrastructure provisioning.

2. **Q:** How do server templating tools support immutable infrastructure?  
   **A:** Images are pre-configured, so deployed instances are not modified; updates require new images.

3. **Q:** Why is version control important for IaC scripts?  
   **A:** Allows tracking changes, collaboration, rollback, and reuse of infrastructure code.

4. **Q:** What are some common challenges when using IaC?  
   **A:** Managing state files, handling secrets securely, and ensuring idempotency across distributed systems.

5. **Q:** Name a situation where immutable infrastructure is preferred over configuration management.  
   **A:** Deploying a critical production service where consistency and rollback safety are essential.

---

