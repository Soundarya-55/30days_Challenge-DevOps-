# GitHub Actions Overview

## 1. What is GitHub Actions?

**GitHub Actions** is a CI/CD (Continuous Integration and Continuous Deployment) tool integrated directly within GitHub. It allows you to automate, customize, and execute software development workflows right in your repository. Whether you're running tests, deploying applications, or managing infrastructure, GitHub Actions enables streamlined automation from code to production.

---

## 2. Why Use GitHub Actions in DevOps?

GitHub Actions has become a vital part of modern DevOps pipelines due to its:

- Seamless integration with GitHub repositories.
- Automation of CI/CD workflows, minimizing manual effort.
- Support for multi-cloud deployment and popular DevOps tools.
- Access to a wide range of reusable actions via the GitHub Marketplace.
- Flexibility through both self-hosted and cloud-hosted runners.

---

## 3. Core Concepts of GitHub Actions

To effectively use GitHub Actions, it's important to understand its key components:

### ✅ Workflows

- Defined using `.yml` files in the `.github/workflows/` directory.
- Triggered by GitHub events like `push`, `pull_request`, or `schedule` (cron jobs).
  
### ✅ Jobs

- A workflow can contain one or more **jobs**.
- Jobs run in separate runner environments and can execute in parallel or sequentially, depending on dependencies.

### ✅ Steps

- Each **job** consists of multiple **steps**.
- Steps run in order within the same runner environment, allowing shared access to the workspace.
- Each step can be a shell command or a pre-defined action.

### ✅ Actions

- **Actions** are reusable code packages used in steps.
- Can be custom-made or imported from the [GitHub Marketplace](https://github.com/marketplace/actions).
- You can create your own actions using JavaScript or Docker.

### ✅ Runners

- **Runners** are servers that execute your workflows.
- GitHub provides hosted runners (e.g., Ubuntu, Windows, macOS), or you can set up your own **self-hosted runners** for more control.
