## **Terraform in DevOps**

**Terraform** is an open-source **Infrastructure as Code (IaC)** tool developed by **HashiCorp**. It allows you to define, provision, and manage cloud infrastructure using declarative configuration files. It supports **multi-cloud** environments like **AWS, Azure, and GCP**, making it cloud-agnostic.

---

### **Terraform in a DevOps Workflow**

1. **Write** – Define the infrastructure using `.tf` configuration files.
2. **Plan** – Preview infrastructure changes before applying.
3. **Apply** – Provision or update infrastructure automatically.
4. **Destroy** – Tear down infrastructure when no longer needed.

---

### **Benefits of Using Terraform in DevOps**

* **Automation** of infrastructure provisioning
* **Version control** of infrastructure like application code
* **Reproducible environments** (dev, test, prod)
* **CI/CD integration** for infrastructure deployment
* **Prevents drift** by maintaining consistency

---

### **Typical Terraform Project Structure**

```
terraform/
├── dev/
│   └── main.tf
├── prod/
│   └── main.tf
├── modules/
│   └── ec2/
│       └── main.tf
├── variables.tf
├── outputs.tf
└── backend.tf
```

---

### **Common Terraform Commands**

| Command               | Description                                               |
| --------------------- | --------------------------------------------------------- |
| `terraform init`      | Initializes the working directory and downloads providers |
| `terraform validate`  | Validates `.tf` files for syntax and schema               |
| `terraform fmt`       | Formats `.tf` files to standard style                     |
| `terraform plan`      | Shows changes before applying them                        |
| `terraform apply`     | Applies the desired state                                 |
| `terraform destroy`   | Destroys all managed infrastructure                       |
| `terraform output`    | Displays configured output values                         |
| `terraform show`      | Shows current state in human-readable form                |
| `terraform state`     | Manages state file (e.g., list, show resources)           |
| `terraform taint`     | Forces a resource to be recreated                         |
| `terraform untaint`   | Removes the taint flag                                    |
| `terraform workspace` | Manages different environments (dev, staging, prod)       |
| `terraform login`     | Authenticates with Terraform Cloud                        |
| `terraform test`      | Runs HCL-based tests (Terraform 1.6+)                     |

---

### **Core Components of Terraform**

| Component                                  | Description                                                    |
| ------------------------------------------ | -------------------------------------------------------------- |
| **Terraform CLI**                          | Interface to run Terraform commands                            |
| **HCL (HashiCorp Configuration Language)** | Declarative syntax used in `.tf` files                         |
| **Providers**                              | Plugins to manage specific cloud/service resources             |
| **Modules**                                | Reusable groups of configuration files                         |
| **Provisioners**                           | Used to execute scripts post resource creation                 |
| **State File (`terraform.tfstate`)**       | Tracks infrastructure state, can be local or remote (e.g., S3) |

