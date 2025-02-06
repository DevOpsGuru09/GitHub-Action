# 🚀 Using Actions in Workflows

This GitHub Actions workflow demonstrates how to use **actions** within our GitHub Actions workflow to test a React application.

---

## 📋 Workflow Details

- **Trigger**: This workflow is triggered **manually** from the UI.  
  _Icon_: 👆
- **Runner**: It runs on an **Ubuntu environment** provided by GitHub-hosted runners.  
  _Icon_: 🌐

---

## 🛠️ Workflow Steps

1. **Checkout Code**  
   The workflow checks out the code from the repository using the [`actions/checkout`](https://github.com/actions/checkout) action.  
   _Icon_: 📥

2. **Set up Node.js**  
   The [`actions/setup-node`](https://github.com/actions/setup-node) action sets up a **Node.js environment** with version `20.x`. By specifying the `.x` option, we ensure that the **latest release** of version 20 will be used.  
   _Icon_: ⚙️

3. **Install Dependencies**  
   It installs project dependencies using `npm ci`.  
   _Icon_: 📦

4. **Run Tests**  
   It runs tests for the application using `npm run test`.  
   _Icon_: ✅

---

## 📍 Default Configuration

We use the `defaults` option in our `job` definition to define the common `working-directory` for the `run` commands executed from within steps. This default only applies to the `run` commands.

---

## 📚 Additional Resources

```markdown
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [actions/checkout Repository](https://github.com/actions/checkout)
- [actions/setup-node Repository](https://github.com/actions/setup-node)
- [npm ci vs npm install](https://docs.npmjs.com/cli/ci.html)
```
