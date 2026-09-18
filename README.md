# 🤖 Doxynix Repository Documenter Action

Automate your codebase intelligence and architecture documentation directly inside your GitHub Actions workflow! 

This action triggers the **Doxynix AI engine** to run a deterministic AST analysis of your repository, automatically updating your documentation briefs, charts, and explanations.

---

## 🚀 Usage

Add this job to your workflow file (e.g., `.github/workflows/doxynix-docs.yml`):

```yaml
name: Rebuild AI Documentation

on:
  push:
    branches:
      - main # Run whenever code is merged into main

jobs:
  document:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Trigger Doxynix Documenter
        uses: doxynix/action@v1.0.0
        with:
          doxynix-token: ${{ secrets.DOXYNIX_TOKEN }}
          branch: 'main'
```

---

## 🎛️ Configuration Inputs

| Input | Description | Required | Default |
| :--- | :--- | :---: | :--- |
| `doxynix-token` | Your secure Doxynix API key. Create one at [Doxynix Settings](https://doxynix.space). | **Yes** | — |
| `branch` | The specific branch you want the AI engine to map and analyze. | No | `main` |
| `api-url` | Custom base API endpoint (mostly used for internal testing). | No | `https://doxynix.space` |

---

## 🔒 Security Notice

Never expose your `doxynix-token` in plain text. Always save it as an **Encrypted Secret** in your GitHub repository settings (`Settings -> Secrets and variables -> Actions`) under the name `DOXYNIX_TOKEN` and reference it via context tokens.

---

<p align="center">
  Crafted with ❤ by the <a href="https://doxynix.space">Doxynix Engineering Team</a>.
</p>
