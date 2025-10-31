# How to Deploy a Static Vite Site to GitHub Pages

This guide walks you through deploying a static Vite site to GitHub Pages, step by step. It covers all config changes, GitHub repository setup, and workflow options so anyone can follow and succeed.

---

## 1. Prepare Your GitHub Repository
- Create a free account at [github.com](https://github.com/) if you don't have one.
- Create a new repository for your site (e.g., `my-vite-site`).
- Clone your repository locally:
  ```sh
  git clone https://github.com/<your-username>/<your-repo-name>.git
  cd <your-repo-name>
  ```

## 2. Set the Vite Base Path
- Open `vite.config.js`.
- If deploying to `https://<username>.github.io/<repo>/`, set:
  ```js
  export default {
    base: '/<repo>/',
  }
  ```
- If deploying to `https://<username>.github.io/` (user/organization site), set:
  ```js
  export default {
    base: '/',
  }
  ```
- Save the file.

## 3. Build Your Project
- Run:
  ```sh
  npm run build
  ```
- This creates a `dist/` folder with your production files.

## 4. Choose a Deployment Method
You can deploy using either GitHub Actions (recommended) or the `gh-pages` npm package.

### Option A: GitHub Actions (Recommended)
1. In your repo, create `.github/workflows/deploy.yml` with the following content:
   ```yaml
   name: Deploy static content to Pages
   on:
     push:
       branches: ['main']
     workflow_dispatch:
   permissions:
     contents: read
     pages: write
     id-token: write
   concurrency:
     group: 'pages'
     cancel-in-progress: true
   jobs:
     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v5
         - name: Set up Node
           uses: actions/setup-node@v5
           with:
             node-version: lts/*
             cache: 'npm'
         - name: Install dependencies
           run: npm ci
         - name: Build
           run: npm run build
         - name: Setup Pages
           uses: actions/configure-pages@v5
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v4
           with:
             path: './dist'
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v4
   ```
2. Commit and push the workflow file:
   ```sh
   git add .github/workflows/deploy.yml
   git commit -m "Add GitHub Pages deploy workflow"
   git push
   ```
3. Go to your repo's **Settings > Pages** and set the source to **GitHub Actions**.
4. After a push to `main`, your site will be deployed. The URL will be shown in the workflow output and in the Pages settings.

### Option B: gh-pages npm Package
1. Install the package:
   ```sh
   npm install --save-dev gh-pages
   ```
2. Add a deploy script to your `package.json`:
   ```json
   "scripts": {
     ...existing scripts...
     "deploy": "gh-pages -d dist"
   }
   ```
3. Commit and push all changes:
   ```sh
   git add .
   git commit -m "Prepare for GitHub Pages deployment"
   git push
   ```
4. Run the deploy command:
   ```sh
   npm run deploy
   ```
5. Go to your repo's **Settings > Pages** and set the source to the `gh-pages` branch.
6. Your site will be live at `https://<username>.github.io/<repo>/`.

## 5. Additional GitHub Pages Settings
- For custom domains, see: [GitHub Docs: Custom Domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- For HTTPS, see: [GitHub Docs: Securing with HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- For troubleshooting, see: [GitHub Docs: Troubleshooting](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

## 6. Useful Links
- [Vite Static Deploy Guide](https://vitejs.dev/guide/static-deploy.html)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [GitHub Pages Quickstart](https://pages.github.com/)

---

**Your Vite site is now live!**

If you need more help, check the official docs or ask the GitHub community.
