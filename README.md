# Vite Basic Deployment Tutorial

This repository demonstrates a standard, basic Vite deployment. It is designed as a step-by-step tutorial for beginners to quickly set up, build, and preview a Vite project.

## Table of Contents
- [Vite Basic Deployment Tutorial](#vite-basic-deployment-tutorial)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Getting Started](#getting-started)
  - [Project Structure](#project-structure)
  - [Available Scripts](#available-scripts)
  - [Building and Previewing](#building-and-previewing)
  - [How It Works](#how-it-works)
  - [Resources](#resources)
  - [Step-by-Step: Create Your Own Vite Project](#step-by-step-create-your-own-vite-project)
    - [1. Install Node.js](#1-install-nodejs)
    - [2. Create a New Vite Project](#2-create-a-new-vite-project)
    - [3. Install Dependencies](#3-install-dependencies)
    - [4. Project Structure](#4-project-structure)
    - [5. Development Server](#5-development-server)
    - [6. Build for Production](#6-build-for-production)
    - [7. Preview Production Build](#7-preview-production-build)
    - [8. Customize Your App](#8-customize-your-app)
    - [9. Deploy](#9-deploy)

---

## Project Overview
This is a minimal Vite project with a simple counter app. It demonstrates:
- Vite configuration
- Basic file structure
- How to build and preview a Vite app

## Getting Started
Follow these steps to set up and run the project:

1. **Clone the repository**
	```sh
	git clone <your-repo-url>
	cd VITE-DEPLOY
	```
2. **Install dependencies**
	```sh
	npm install
	```
3. **Start the development server**
	```sh
	npm run dev
	```
	The app will be available at [http://localhost:5173](http://localhost:5173) (default Vite port).

## Project Structure
```
VITE-DEPLOY/
├── index.html           # Main HTML file
├── package.json         # Project metadata and scripts
├── vite.config.js       # Vite configuration
├── public/              # Static assets (e.g., vite.svg)
├── src/                 # Source code
│   ├── main.js          # Entry point
│   ├── counter.js       # Counter logic
│   ├── style.css        # Styles
│   └── javascript.svg   # JS logo
├── README.md            # This tutorial
└── SETUP.md             # Setup notes and commands
```

## Available Scripts
Defined in `package.json`:

- `npm run dev` — Start development server
- `npm run build` — Build for production
- `npm run preview` — Preview production build (default port: 8080)

## Building and Previewing
To build and preview your app:

1. **Build the project**
	```sh
	npm run build
	```
	This creates a `dist/` folder with production files.

2. **Preview the build**
	```sh
	npm run preview
	```
	The preview server runs at [http://localhost:8080](http://localhost:8080).

## How It Works
- The main entry point is `src/main.js`, which loads styles, logos, and sets up the counter.
- The counter logic is in `src/counter.js`.
- Static assets (SVGs) are in `public/` and `src/`.
- The Vite config (`vite.config.js`) sets the base path for deployment.
- Styles are in `src/style.css`.

## Resources
- [Vite Documentation](https://vitejs.dev/)
- [Vite GitHub](https://github.com/vitejs/vite)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

---

Feel free to use this repository as a template for your own Vite projects!

---

## Step-by-Step: Create Your Own Vite Project

Follow these instructions to set up a new Vite project from scratch. This guide is designed to save you time and help you avoid hours of searching through documentation.

### 1. Install Node.js
Make sure you have Node.js installed. Download it from [nodejs.org](https://nodejs.org/).

### 2. Create a New Vite Project
Open your terminal and run:
```sh
npm create vite@latest my-vite-app
cd my-vite-app
```
You will be prompted to choose a framework (select Vanilla for this template, or pick React/Vue/etc. as needed).

### 3. Install Dependencies
```sh
npm install
```

### 4. Project Structure
Your project will look like this:
```
my-vite-app/
├── index.html
├── package.json
├── vite.config.js
├── public/
├── src/
│   ├── main.js
│   ├── counter.js
│   └── style.css
└── README.md
```

### 5. Development Server
Start the local server:
```sh
npm run dev
```
Visit [http://localhost:5173](http://localhost:5173) in your browser.

### 6. Build for Production
To build your app for deployment:
```sh
npm run build
```
This creates a `dist/` folder with optimized files.

### 7. Preview Production Build
Test your build locally:
```sh
npm run preview
```
Default preview port is 8080. Visit [http://localhost:8080](http://localhost:8080).

### 8. Customize Your App
Edit files in the `src/` folder to change your app. Use this template as a starting point for your own projects.

### 9. Deploy
You can deploy the contents of the `dist/` folder to any static hosting service (GitHub Pages, Netlify, Vercel, etc.).

---

**Tip:** Copy this README and adjust it for your own project. This template is designed to help you get started fast and avoid confusion.


---

## Deploying to GitHub Pages

For a complete, step-by-step guide to deploying your Vite site to GitHub Pages, see:

- [GITHUB_PAGES_DEPLOY.md](./GITHUB_PAGES_DEPLOY.md)
