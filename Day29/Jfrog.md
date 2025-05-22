## 🐸 **JFrog**

**JFrog** is a **DevOps and DevSecOps platform** best known for **JFrog Artifactory**, a universal artifact repository manager. It enables teams to manage binaries and dependencies across the software development lifecycle.

---

### 🔹 **Core Products:**

1. **JFrog Artifactory**

   * A universal binary repository for storing, versioning, and managing build artifacts.
   * Supports multiple package types: Docker, Maven, NPM, PyPI, Go, NuGet, Helm, etc.
   * Acts as a caching proxy for remote repositories like Docker Hub, Maven Central.

2. **JFrog Xray**

   * Security scanning and license compliance tool.
   * Scans artifacts and dependencies for vulnerabilities.
   * Integrates with Artifactory for **continuous security**.

3. **JFrog Pipelines**

   * CI/CD automation for building, testing, and deploying applications.
   * Native integration with Artifactory and Xray.

4. **JFrog Distribution**

   * Facilitates the **secure and traceable release** of artifacts to production environments.

5. **JFrog Mission Control & Insight**

   * Centralized management and analytics across JFrog services.

---

### 🧰 **Key Features:**

| Feature                    | Description                                                       |
| -------------------------- | ----------------------------------------------------------------- |
| **Universal Repo Manager** | Supports all major build tools and package formats                |
| **Immutable Artifacts**    | Ensures traceability and version control of binaries              |
| **Metadata Storage**       | Stores build info, checksums, and promotion status                |
| **Security & Compliance**  | Integration with JFrog Xray for CVE and license scanning          |
| **CI/CD Integration**      | Works with Jenkins, GitHub Actions, GitLab CI, Azure DevOps, etc. |
| **Replication**            | Artifact replication across multiple sites or cloud regions       |

---

### 🔐 **DevSecOps with JFrog:**

* **Secure your SDLC**: Scan dependencies at build time.
* **Fail builds** when vulnerabilities are found.
* **Automated policy enforcement** (e.g., block deployment of critical CVEs).

---

### 🧪 **Example Use Cases:**

* Store Docker images in a private Docker registry.
* Manage Maven/NPM dependencies across multiple teams.
* Scan artifacts in CI pipelines before deployment.
* Promote builds from `dev` to `qa` to `prod`.

---

### ☁️ **Deployment Options:**

* **JFrog Cloud** (SaaS on AWS, Azure, GCP)
* **Self-Hosted** (On-prem or cloud VM/Kubernetes)

---

### 🧭 **Why JFrog?**

* Enterprise-ready binary management
* End-to-end DevSecOps platform
* Scalable and secure for large teams

