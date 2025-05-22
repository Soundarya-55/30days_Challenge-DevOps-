## **Ansible in DevOps**

**Ansible** is an open-source **automation** and **configuration management** tool used for:

* Provisioning infrastructure
* Configuring systems
* Deploying applications
* Orchestrating complex workflows

It is agentless and uses **SSH** for communication, making it simple and efficient.

---

### **Ansible Architecture**

| Component         | Description                                                                                                                        |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| **Control Node**  | The machine from which Ansible commands and playbooks are run. It must run a Unix-like OS (not Windows) and have Python installed. |
| **Managed Nodes** | The target machines (servers/devices) being managed by Ansible, often called *hosts*.                                              |
| **Inventory**     | A file (INI or YAML format) listing managed nodes. Supports grouping and hierarchy.                                                |
| **Modules**       | Reusable code blocks Ansible uses to perform tasks (e.g., install packages, create users).                                         |
| **Tasks**         | Individual units of work. Can be executed via playbooks or ad-hoc commands.                                                        |

---

### **Ansible Playbook Basics**

Playbooks are YAML files that define a sequence of tasks to run on target hosts.

**Example:**

```yaml
---
- hosts: all
  tasks:
    - name: Install the Apache web server
      apt:
        name: apache2
        state: present
```

**Key Sections:**

* `hosts`: Defines which machines the tasks should run on
* `vars`: Variables that can be reused throughout the playbook
* `tasks`: List of actions to be executed on the remote hosts

---

### **Common Use Cases**

* Application deployment
* OS configuration and patching
* Multi-tier service orchestration
* Cloud resource management

---

### **Running Playbooks**

| Command                                      | Description                       |
| -------------------------------------------- | --------------------------------- |
| `ansible-playbook site.yml -i inventory.ini` | Run a playbook on inventory hosts |
| `--syntax-check`                             | Validate playbook syntax          |
| `--check`                                    | Perform a dry run                 |
| `-K`                                         | Prompt for sudo password          |
| `--private-key ~/.ssh/id_rsa`                | Use custom SSH key                |

---

### **Types of Ansible Modules**

| Module Category         | Example Purpose                     |
| ----------------------- | ----------------------------------- |
| **System Modules**      | User, group, service management     |
| **Application Modules** | Install/configure software          |
| **Cloud Modules**       | Provision AWS, Azure, GCP resources |
| **Networking Modules**  | Manage routers, switches, firewalls |
| **Command Modules**     | Run arbitrary shell commands        |

---

### **Essential Ansible Commands**

#### **Inventory & Setup**

* `ansible --version` – Check installed Ansible version
* `ansible all -m ping -i inventory.ini` – Ping all hosts to check connection

#### **Ad-Hoc Commands**

* `ansible all -m shell -a "uptime"` – Run `uptime` on all hosts
* `ansible all -m copy -a "src=./file.txt dest=/tmp/"` – Copy files to hosts
* `ansible all -m apt -a "name=nginx state=present"` – Install Nginx on Debian hosts
