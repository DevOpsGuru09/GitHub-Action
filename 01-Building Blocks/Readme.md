# 🚀 WORKFLOWs, JOBs & STEPs in CI/CD

Understanding **WORKFLOWs**, **JOBs**, and **STEPS** is essential for setting up efficient CI/CD pipelines. These components help automate tasks like building, testing, and deploying your code.

---

## 🌟 What Are WORKFLOWs, JOBs & STEPs?

### 1. **WORKFLOW**

A **workflow** is an automated process that defines how your project should be built, tested, and deployed. It's triggered by events like pushing code or creating a pull request.

### 2. **JOB**

A **job** is a set of steps that run on the same machine. Jobs can run independently or depend on other jobs.

### 3. **STEP**

A **step** is an individual task within a job. Steps execute commands or scripts to perform specific actions.

---

## 📊 Visualizing the Relationship

![Workflow Diagram](https://i.imgur.com/4QJvWjB.png)

_In this diagram:_

- A **workflow** contains two **jobs** (`Build` and `Test`).
- Each job has multiple **steps** that execute sequentially.

---

## 🛠️ Example Code: GitHub Actions Workflow

Here’s an example of a GitHub Actions workflow:

```yaml
name: CI Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Install Dependencies
        run: npm install

      - name: Run Build Script
        run: npm run build

  test:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Run Tests
        run: npm test
```

🔍 **Breaking Down the Example**

- **WORKFLOW**: Triggers on `push` or `pull_request` to the `main` branch.
- **JOBS**:
  - `build`: Installs dependencies and builds the project.
  - `test`: Runs tests after the `build` job completes.
- **STEPS**: Each job contains steps like checking out the repository, installing dependencies, and running scripts.

💡 **Why Use WORKFLOWs, JOBs & STEPs?**

- Automate repetitive tasks.
- Run jobs in parallel to save time.
- Easily scale your pipeline as your project grows.

🎯 **Best Practices**

- Keep jobs focused on a single task.
- Use caching to speed up builds.
- Monitor logs to catch errors early.
