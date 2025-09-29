# Terraform FMT (Format) 📐

Hello everyone 👋  

Today we'll be discussing a Terraform command called **Terraform FMT**, also known as **Terraform Format**.

---

## What is Terraform FMT? 🔹
- **Terraform FMT** is used to format Terraform configuration files consistently.
- HashiCorp recommends using **consistent formatting** in all your Terraform configuration files.
- Helps maintain proper **spacing**, **indentation**, and **argument order**.

---

## Why Use Terraform FMT? 🤔
- Ensures all configuration files follow a **uniform structure**.
- Makes Terraform files **more readable and organized**.
- Helps avoid confusion caused by **misaligned arguments or improper indentation**.

---

## Example of Formatting Issue ❌
- Imagine a Terraform file with the following issues:
  - `region` argument has fewer spaces.
  - `Cidr block` argument has too many spaces.
  - Overall indentation is inconsistent.
- This makes the file **hard to read** and maintain.

---

## How to Use Terraform FMT 🛠️
1. Open terminal.
2. Run the command:

   terraform fmt

# Terraform FMT (Format) 📐

## Terraform FMT Overview 🛠️
- Terraform will identify the files and **apply consistent formatting**.  
- **Example output:** `Formatting main.tf`

### After Running the Command
- Proper **spacing** and **indentation** are applied.  
- **Argument order** and **file layout** look clean and consistent.

---

## Key Points ✅
- Terraform FMT is an **optional command**.  
- Primarily used for **cleaning up configuration files**.  
- Ensures proper **spacing, indentation, and formatting** across files.

---

## Summary 📝
- **Command Name:** `terraform fmt`  
- **Purpose:** Format Terraform files consistently.  
- **Benefit:** Makes files more readable and maintainable.  
- **Optional:** Not required for Terraform to run but highly recommended.

---

## 5 Basic Exam Questions & Answers 🎓

1. **Q:** What is Terraform FMT?  
   **A:** Terraform FMT is a command used to format Terraform configuration files consistently.

2. **Q:** Is Terraform FMT mandatory?  
   **A:** No, it is optional, but recommended for consistent formatting.

3. **Q:** Which issues does Terraform FMT fix?  
   **A:** Fixes spacing, indentation, and argument ordering issues.

4. **Q:** How do you run Terraform FMT?  
   **A:** Use the command `terraform fmt` in the terminal.

5. **Q:** Does Terraform FMT change the functionality of the code?  
   **A:** No, it only changes formatting, not the functionality.

---

## 5 Basic Interview Questions & Answers 💼

1. **Q:** Why should you use Terraform FMT?  
   **A:** To maintain consistent formatting and readability of Terraform files.

2. **Q:** Can Terraform FMT fix syntax errors?  
   **A:** No, it only formats the file; syntax errors must be corrected manually.

3. **Q:** Which company recommends using Terraform FMT?  
   **A:** HashiCorp recommends using Terraform FMT.

4. **Q:** Will Terraform FMT reorder arguments automatically?  
   **A:** Yes, it reorders arguments in a standardized way for consistency.

5. **Q:** Does Terraform FMT apply to all `.tf` files?  
   **A:** Yes, it formats all Terraform configuration files in the directory.

---

## 5 Advanced Exam Questions & Answers 🎓⚡

1. **Q:** Can Terraform FMT be integrated into CI/CD pipelines?  
   **A:** Yes, to ensure consistent formatting across multiple developers' code.

2. **Q:** How does Terraform FMT affect version control?  
   **A:** It reduces merge conflicts caused by inconsistent formatting.

3. **Q:** Can Terraform FMT be configured to skip certain files?  
   **A:** Yes, using the `-check` or `-diff` flags to control behavior.

4. **Q:** What is the difference between `terraform fmt` and `terraform validate`?  
   **A:** `terraform fmt` formats files; `terraform validate` checks for syntax and errors.

5. **Q:** How can Terraform FMT improve team collaboration?  
   **A:** By ensuring all team members follow the same formatting standards.

---

## 5 Advanced Interview Questions & Answers 💼⚡

1. **Q:** How would you automate Terraform FMT in a Git pre-commit hook?  
   **A:** By adding `terraform fmt -recursive` to the pre-commit script to automatically format files before commits.

2. **Q:** What flags can be used with `terraform fmt` for advanced usage?  
   **A:** Flags like `-check`, `-diff`, and `-recursive` for selective or recursive formatting.

3. **Q:** How does Terraform FMT affect large-scale infrastructure projects?  
   **A:** It ensures readability and maintainability, reducing human errors in large configurations.

4. **Q:** Can Terraform FMT handle custom indentation rules?  
   **A:** No, it follows Terraform's default formatting rules; custom rules are not supported.

5. **Q:** How do you check which files will be formatted without changing them?  
   **A:** Use the `terraform fmt -check -diff` command to see differences before applying formatting.

