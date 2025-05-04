## **Kubernetes**

**Definition:**
Kubernetes is an open-source container orchestration tool used to deploy, scale, and manage containerized applications. It follows a master-slave architecture, where the **master node** manages cluster operations and **worker nodes** run the containers.

---

## **Key Components of Kubernetes**

1. **Master Node:**
   Runs the control plane and manages the cluster. It includes components like the API server, controller manager, scheduler, and etcd.

2. **Nodes (Worker Nodes):**
   Physical or virtual machines that run application workloads as containers.

3. **Pods:**
   The smallest deployable unit in Kubernetes. A pod can run one or more containers that share storage, network, and a specification for how to run them.

4. **Replication Controller / ReplicaSet:**
   Ensures that a specified number of pod replicas are running at any given time.

5. **Services:**
   An abstraction that defines a logical set of pods and a policy by which to access them. Services also act as load balancers.

6. **Namespaces:**
   Virtual clusters within a Kubernetes cluster. They help organize resources and divide cluster usage among multiple users or teams.

7. **RBAC (Role-Based Access Control):**
   Controls access to resources in the cluster based on the user's role, helping enforce security policies.

---

## **Kubernetes Clusters and Nodes**

* **Cluster:**
  A collection of nodes that form the compute infrastructure for your applications.

* **Node:**
  An individual machine (VM or physical) that runs containers. Nodes are categorized as **master** or **worker**.

---

## **Kubernetes Deployment Strategies**

1. **Rolling Updates:**
   Gradually replaces old pods with new ones, ensuring zero downtime. Common in CI/CD pipelines.

2. **Blue/Green Deployment:**
   Deploys a new version alongside the old one. After testing, traffic is shifted to the new version.

3. **Canary Deployment:**
   Releases the new version to a small subset of users before rolling it out to everyone.

4. **Recreate Strategy:**
   Deletes all existing pods before creating new ones. It can cause downtime but is useful for stateful apps.

---

## **Basic Workflow**

1. Define your application’s desired state in a YAML file (e.g., number of pods, container image, ports).
2. Use `kubectl apply -f <file>.yaml` to apply the configuration.
3. Kubernetes continuously maintains the desired state.

---

## **kubectl (Kubernetes Control)**

The command-line tool for interacting with Kubernetes clusters.

### Common `kubectl` Commands:

* `kubectl version` – Check client and server versions.
* `kubectl cluster-info` – Show cluster information.
* `kubectl get nodes` – List all cluster nodes.
* `kubectl get pods` – List all pods in the current namespace.
* `kubectl get deployments` – Show deployments in the cluster.
* `kubectl apply -f <filename>.yaml` – Create or update resources.
* `kubectl delete -f <filename>.yaml` – Delete specified resources.
* `kubectl logs <pod-name>` – Show logs from a specific pod.
* `kubectl exec -it <pod-name> -- bash` – Open shell inside a pod.
* `kubectl describe pod <pod-name>` – Detailed information about a pod.

---

## **Kubernetes YAML Example**

### `deployment.yaml`

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
        - name: app-container
          image: nginx
          ports:
            - containerPort: 80
```

---

## **SonarQube in Kubernetes**

**SonarQube** is a code quality and security analysis tool. Running it in Kubernetes offers:

* **Scalability:** Easily handle multiple users and CI pipelines.
* **CI/CD Integration:** Works with Jenkins, GitLab, etc.
* **Cloud-Native Setup:** Use Ingress or LoadBalancer for secure access.
* **Resilience:** Auto-restarts, centralized configs using Secrets/ConfigMaps.
* **Resource Control:** Manage CPU/memory limits for SonarQube and PostgreSQL.

---

## **Helm – Kubernetes Package Manager**

**Helm** simplifies the deployment and management of applications in Kubernetes using packaged configurations called **charts**.

### **Why Use Helm?**

* Avoid writing multiple YAML files manually.
* Simplify deployment, upgrade, and rollback of applications.
* Manage configuration easily across environments.

### **Main Components of Helm:**

1. **Helm Client:** CLI tool for managing charts.
2. **Helm Charts:** Preconfigured Kubernetes resources bundled as packages.
3. **Helm Repositories:** Storage for Helm charts (public or private).
4. **Releases:** A running instance of a Helm chart in a cluster.
5. **Chart Templates:** YAML files with dynamic variables for flexibility.
6. **Values Files:** Configuration files to override chart defaults.
7. **Tiller (Helm 2 only):** Server-side component (removed in Helm 3 for better security and simplicity).

