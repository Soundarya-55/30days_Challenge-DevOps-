## **Infrastructure as Code (IaC)**

IaC is the practice of managing and provisioning infrastructure through code instead of manual processes. It allows automation, consistency, and scalability, especially in DevOps environments.

---

### 🔧 **How IaC Works**

IaC describes system architecture—servers, networks, OS, and storage—using code. It automates the entire setup process, similar to how source code defines application behavior.

---

### 🔄 **Role of IaC in DevOps**

* Automates infrastructure provisioning
* Integrates into CI/CD pipelines
* Reduces manual errors and improves deployment speed

---

### 🌟 **Key Features**

* **Automation** – Reduces manual work
* **Repeatability** – Easily replicate environments
* **Version Control** – Track and manage code (e.g., using Git)
* **Scalability** – Scale resources easily
* **Transparency** – Infrastructure is clear and documented in code
* **Security** – Enforces consistent configurations

---

### 📌 **Use Cases**

* Cloud provisioning (e.g., VMs, DBs)
* CI/CD pipeline deployments
* Web apps and DB setup
* Networking (subnets, firewalls)
* Big data platforms (e.g., Spark, Hadoop)

---

### 🧭 **Declarative vs Imperative IaC**

| Approach        | Description                                                                    | Tools                                      |
| --------------- | ------------------------------------------------------------------------------ | ------------------------------------------ |
| **Declarative** | Define *what* the final state should be; tool figures out *how* to achieve it. | Terraform, CloudFormation, Ansible, Puppet |
| **Imperative**  | Define *how* to reach the desired state with specific steps.                   | Chef                                       |

---

### 🛠️ **Popular IaC Tools**

#### **1. Terraform (HashiCorp)**

* Open-source and cloud-agnostic
* Plan and validate infrastructure changes
* Manages full lifecycle of infrastructure

#### **2. AWS CloudFormation**

* Native to AWS
* Manages AWS & third-party resources
* Uses templates to define infrastructure

#### **3. Ansible (Red Hat)**

* YAML-based
* Agentless automation
* Manages compliance and provisioning

#### **4. Puppet**

* Declarative, Ruby-based
* Ideal for large-scale configuration
* Reduces downtime via consistent setup

#### **5. Chef**

* Imperative, Ruby DSL
* Uses cookbooks and recipes
* Enables detailed procedural control

#### **6. SaltStack**

* High-speed agent-based architecture
* Scales infrastructure efficiently

#### **7. Vagrant**

* Manages dev environments as code
* Simplifies team collaboration

#### **8. Packer**

* Creates consistent machine images
* Works across cloud providers and platforms
