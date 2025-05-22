# **DevOps Automation with Shell Scripting**

## **1. Introduction**

In the world of **DevOps**, automation is essential for managing complex systems, streamlining workflows, and accelerating development cycles. **Shell scripting** is a versatile and powerful tool that helps DevOps engineers automate routine tasks, reduce manual effort, and ensure consistent, reliable processes.

This guide covers the essentials of DevOps automation using shell scripting, including common use cases, core techniques, and best practices.

---

## **2. Why Automate with Shell Scripting?**

Shell scripting is widely used in DevOps automation because:

* ✅ It’s **lightweight** and quick to execute on almost any system with a shell (e.g., Bash on Linux).
* 🔧 Easily integrates with tools like **Jenkins**, **Ansible**, **Kubernetes**, etc.
* 🚀 Faster to implement for simple automation tasks compared to more complex programming languages.

---

## **3. Basic Concepts of Shell Scripting**

### **3.1 Essential Shell Commands**

Familiar commands include:

* `echo` – Print text to the terminal
* `cat`, `tail`, `head` – View or manipulate file contents
* `grep` – Search patterns in files
* `awk`, `sed` – Text processing
* `curl`, `wget` – Fetch data from the web

**Example:**

```bash
echo "Hello, DevOps!"
cat /etc/passwd | grep "user_name"
```

---

### **3.2 Variables and Data Types**

```bash
NAME="DevOpsEngineer"
echo "Hello, $NAME"
```

* Variables are typeless by default.
* Use `declare -i` for integers.
* Use `export` to pass variables to subprocesses.

---

### **3.3 Conditionals**

```bash
if [ "$USER" == "devops" ]; then
  echo "Welcome, DevOps Engineer!"
else
  echo "Access denied."
fi
```

* Use `==` and `!=` for strings.
* Use `-eq`, `-ne`, `-gt`, `-lt` for integers.

---

### **3.4 Loops**

**For Loop:**

```bash
for i in {1..5}; do
  echo "Number $i"
done
```

**While Loop:**

```bash
count=1
while [ $count -le 5 ]; do
  echo "Count $count"
  ((count++))
done
```

---

## **4. Setting Up Your Environment**

* **Shell**: Bash (`/bin/bash`)
* **Text Editor**: Use `vim`, `nano`, or your preferred editor
* **Permissions**: Use `chmod +x script.sh` to make scripts executable

---

## **5. Shell Scripting for DevOps Use Cases**

### **5.1 System Monitoring**

Monitor CPU usage and alert when a threshold is exceeded:

```bash
#!/bin/bash
THRESHOLD=80
cpu_usage=$(top -bn1 | grep "Cpu(s)" | sed "s/.*, *\([0-9.]*\)%* id.*/\1/" | awk '{print 100 - $1}')
if (( $(echo "$cpu_usage > $THRESHOLD" | bc -l) )); then
  echo "CPU usage is above $THRESHOLD%. Current usage: $cpu_usage%" | mail -s "CPU Alert" you@example.com
fi
```

---

### **5.2 Automating Deployments**

```bash
#!/bin/bash
echo "Starting deployment..."
git pull origin main
docker build -t myapp:latest .
docker stop myapp || true
docker rm myapp || true
docker run -d --name myapp -p 80:80 myapp:latest
echo "Deployment completed."
```

---

### **5.3 Backup and Restore**

```bash
#!/bin/bash
DATE=$(date +%F)
DB_BACKUP_PATH='/backup/dbbackup'
DB_USER='root'
DB_PASS='password'
DB_NAME='mydb'
mkdir -p ${DB_BACKUP_PATH}/${DATE}
mysqldump -u${DB_USER} -p${DB_PASS} ${DB_NAME} > ${DB_BACKUP_PATH}/${DATE}/${DB_NAME}.sql
echo "Backup completed for database ${DB_NAME}."
```

---

### **5.4 Log Management**

```bash
#!/bin/bash
LOG_DIR="/var/log/myapp/"
ARCHIVE_DIR="/var/log/myapp/archive/"
find $LOG_DIR -name "*.log" -mtime +30 -exec mv {} $ARCHIVE_DIR \;
gzip $ARCHIVE_DIR/*.log
echo "Log files older than 30 days archived and compressed."
```

---

## **6. Advanced Shell Scripting Techniques**

* **Functions** – Break logic into reusable blocks:

```bash
function backup() {
  echo "Performing backup..."
  # logic here
}
backup
```

* **Error Handling** – Exit on error:

```bash
set -e
```

* **Parsing Arguments**:

```bash
while getopts u:p: flag; do
  case "${flag}" in
    u) user=${OPTARG};;
    p) pass=${OPTARG};;
  esac
done
echo "User: $user"
echo "Password: $pass"
```

---

## **7. Best Practices**

✅ Use comments for clarity
✅ Choose meaningful variable names
✅ Organize with functions
✅ Handle errors gracefully
✅ Limit root permissions

---

## **8. Hands-On Projects for Practice**

1. **Automated Server Provisioning**
   Script to install and configure Apache/Nginx on a Linux server.

2. **CI/CD Pipeline Automation**
   Automate cloning, building, and deploying code with a single script.

3. **User Access Management**
   Script for adding users, setting permissions, and logging access.

4. **Automated Health Checks**
   Periodic checks on service status (e.g., `nginx`, `mysql`) with notifications.

---

🛠️ **DevOps All in One Shot — Do It Now, Don’t Regret Later**

Let me know if you want these scripts bundled into a GitHub repo or turned into an e-learning module with animations and interactive practice!
