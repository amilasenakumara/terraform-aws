# 🌐 Application Delivery & Infrastructure Evolution

## 1. Traditional Infrastructure Model 🏢

- Organizations roll out applications through multiple teams.
- Process flow:
  1. **Business requirements** → defined by business analyst.
  2. **High-level technical requirements** → converted by business analyst.
  3. **Solution architect** → designs infrastructure architecture.
- Infrastructure considerations include:
  - Front-end web servers
  - Back-end servers
  - Databases
  - Load balancers
- Deployment in **on-premise environment**:
  - Hardware ordered via procurement → can take days to months.
  - Field engineers perform **rack and stack**.
  - System administrators configure servers.
  - Network admins connect systems to network.
  - Storage admins assign storage.
  - Backup admins configure backups.
- Application teams finally deploy the software.

### ⚠ Disadvantages of Traditional Model
- Long turnover: **weeks to months** just to provision systems.
- **Scaling** up or down on demand is slow/impossible.
- High cost to deploy & maintain.
- Many manual steps → prone to **human error**.
- **Underutilization** of compute resources: servers sized for peak usage.
- Inconsistent environments due to manual processes.

---

## 2. Evolution to Virtualization & Cloud ☁️

- Organizations move to cloud providers: **AWS, Azure, GCP**.
- Advantages:
  - **Infrastructure deployment in minutes** instead of months.
  - No need to manage hardware assets.
  - **Reduced costs**: no extra data center & human resource expenses.
  - **APIs** enable automation.
  - Built-in **auto-scaling & elastic functionality** reduces resource wastage.
- **Virtualization** allows provisioning with a few clicks.
- Limitations of manual cloud console provisioning:
  - Works for a small number of resources.
  - In large organizations → not feasible due to process overhead & human errors.

---

## 3. Infrastructure as Code (IaC) 💻

- Organizations started creating **scripts & tools** for automation.
- Languages/tools used: Shell scripts, Python, Ruby, Perl, PowerShell.
- Goal: automate infrastructure provisioning **faster & consistently**.
- IaC leverages **API functionalities** of cloud providers.
- Provides:
  - Speed
  - Consistency
  - Scalable & automated deployments

> Next lecture will dive deeper into **Infrastructure as Code**.

---

## 4. Summary Table 📝

| Aspect | Traditional | Cloud + IaC |
|--------|-------------|-------------|
| Provisioning time | Weeks to months | Minutes to hours |
| Manual effort | High | Low |
| Scaling | Difficult | Easy (auto-scaling) |
| Cost | High | Reduced |
| Human error | High | Low (automation) |
| Resource utilization | Poor | Efficient |
| Automation | Limited | High (via APIs & IaC) |

---

## 5. Exam Questions & Answers ✅

1. **Q:** What is the main disadvantage of traditional infrastructure provisioning?  
   **A:** It is slow, manual, costly, and prone to human error.  

2. **Q:** Name three cloud providers commonly used by organizations.  
   **A:** AWS, Microsoft Azure, Google Cloud Platform (GCP).  

3. **Q:** How does cloud infrastructure reduce resource wastage?  
   **A:** Auto-scaling and elastic functionality allow resources to match demand.  

4. **Q:** What is the role of a solution architect?  
   **A:** To design infrastructure and deployment architecture based on requirements.  

5. **Q:** Why was Infrastructure as Code developed?  
   **A:** To automate provisioning, reduce errors, and create consistent environments using APIs.

---

## 6. Interview Questions & Answers 💼

1. **Q:** Explain the steps to deploy a new application in a traditional model.  
   **A:** Business requirements → technical requirements → solution architect → hardware procurement → setup → deployment.  

2. **Q:** What are the challenges of manual infrastructure provisioning?  
   **A:** Slow, error-prone, inconsistent, expensive, and hard to scale.  

3. **Q:** How does virtualization improve deployment speed?  
   **A:** Virtual machines can be spun up in minutes without managing physical hardware.  

4. **Q:** What is the benefit of APIs in cloud environments?  
   **A:** They allow automation and integration, enabling faster and consistent provisioning.  

5. **Q:** How does IaC ensure consistent environments?  
   **A:** Infrastructure is defined in code, eliminating manual configuration errors.

---

## 7. Advanced Exam Questions & Answers ⚡

1. **Q:** What is immutable infrastructure and how does IaC support it?  
   **A:** Servers are never modified after deployment; IaC allows redeploying consistent environments automatically.  

2. **Q:** Explain the difference between horizontal and vertical scaling.  
   **A:** Horizontal = add more servers; Vertical = increase resources of a single server.  

3. **Q:** How can IaC reduce deployment downtime?  
   **A:** By automating provisioning and using blue-green or rolling deployments.  

4. **Q:** Name two IaC tools other than Terraform.  
   **A:** Ansible, CloudFormation, Pulumi, Chef, Puppet.  

5. **Q:** How does IaC integrate with CI/CD pipelines?  
   **A:** IaC scripts can be triggered automatically to provision or update infrastructure during deployment.

---

## 8. Advanced Interview Questions & Answers 💡

1. **Q:** How does Terraform maintain state and why is it important?  
   **A:** Terraform keeps a state file to track resources; it ensures accurate updates and prevents drift.  

2. **Q:** Explain the concept of idempotency in IaC.  
   **A:** Running the same IaC script multiple times produces the same environment without errors.  

3. **Q:** How can cloud cost optimization be achieved with IaC?  
   **A:** By automating resource provisioning, scaling, and destruction of unused resources.  

4. **Q:** Describe how IaC helps in disaster recovery.  
   **A:** Infrastructure can be quickly recreated in another region from code, minimizing downtime.  

5. **Q:** What are the security considerations when using IaC?  
   **A:** Secure credentials, restrict access to IaC code, and validate templates to prevent misconfigurations.

---

## Suggested File Name
