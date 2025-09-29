# 📝 Why the Name **HashiCorp Configuration Language (HCL)?**

The name **HashiCorp Configuration Language (HCL)** comes directly from its creator: **HashiCorp** (the company behind Terraform, Vault, Consul, Nomad, etc.).

---

## 🏗 Breakdown of the Name
- **HashiCorp** → The company that designed the language.  
- **Configuration** → Its purpose is to **describe infrastructure and system configuration** in a simple, declarative way.  
- **Language** → Because it has its own syntax and rules, like any programming language (but simpler).  

👉 So the name literally means:  
**A configuration language created by HashiCorp for defining infrastructure.**

---

## 🔑 Why Not Just Use JSON or YAML?
- Terraform actually supports **JSON** as an alternative.  
- But JSON/YAML are not as human-friendly for infrastructure code.  
- **HCL is designed to be both human-readable and machine-friendly.**
  - Easy for developers/ops to read/write.  
  - Easy for machines to parse.  

---

## 📌 Example  

### HCL:
```hcl
resource "aws_instance" "web" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}




{
  "resource": {
    "aws_instance": {
      "web": {
        "ami": "ami-123456",
        "instance_type": "t2.micro"
      }
    }
  }
}
