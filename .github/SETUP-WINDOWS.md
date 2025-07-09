# Next.js Boilerplate Setup Guide for Windows

This guide provides step-by-step instructions to set up this Next.js boilerplate application on Windows systems.

## 🖥️ Windows Prerequisites

### 1. Check Windows Version
Ensure you have Windows 10 version 1709 or later (required for winget).

```powershell
winver
```

### 2. Open PowerShell as Administrator
- Press `Win + X`
- Select "Windows PowerShell (Admin)" or "Terminal (Admin)"

## 📦 Step 1: Install Node.js

### Option A: Using Windows Package Manager (Recommended)

```powershell
# Install Node.js using winget
winget install OpenJS.NodeJS
```

### Option B: Manual Installation
1. Visit [nodejs.org](https://nodejs.org/)
2. Download the Windows Installer (.msi)
3. Run the installer and follow the setup wizard

## 🔧 Step 2: Configure PowerShell Execution Policy

Node.js tools require script execution to be enabled:

```powershell
# Set execution policy to allow scripts
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
```

## 🔄 Step 3: Update Environment Variables

After installing Node.js, you may need to update your PATH:

```powershell
# Check if Node.js is in PATH
node --version
npm --version

# If commands are not recognized, add Node.js to PATH
$env:PATH = "C:\Program Files\nodejs;" + $env:PATH

# Make the PATH change permanent
[Environment]::SetEnvironmentVariable("PATH", $env:PATH + ";C:\Program Files\nodejs", [EnvironmentVariableTarget]::User)
```

## 🚀 Step 4: Create Next.js Project

### Navigate to Your Development Directory

```powershell
# Navigate to your preferred development folder
cd "C:\Users\[YourUsername]\Documents\Development"

# Create a new project directory
mkdir nextjs-app
cd nextjs-app
```

### Create Next.js Application

```powershell
# Create Next.js app with all modern features
npx create-next-app@latest . --typescript --tailwind --eslint --app --src-dir --use-npm

# When prompted:
# - Turbopack: Select "Yes" (y)
# - Import alias: Select "No" (n) to keep default @/*
```

## 📁 Step 5: Project Structure Overview

After setup, your project structure will look like this:

```
nextjs-app/
├── .github/
│   ├── copilot-instructions.md
│   └── SETUP-WINDOWS.md
├── .vscode/
│   └── tasks.json
├── src/
│   └── app/
│       ├── globals.css
│       ├── layout.tsx
│       ├── page.tsx
│       └── favicon.ico
├── public/
│   ├── next.svg
│   ├── vercel.svg
│   └── (other assets)
├── .gitignore
├── eslint.config.mjs
├── next.config.ts
├── package.json
├── postcss.config.mjs
├── README.md
├── tailwind.config.ts
└── tsconfig.json
```

## 🏃‍♂️ Step 6: Start Development

### Install Dependencies (if needed)

```powershell
# Install project dependencies
npm install
```

### Start Development Server

```powershell
# Start the development server with Turbopack
npm run dev
```

### Access Your Application

Open your browser and navigate to: `http://localhost:3000`

## 🛠️ Available Commands

```powershell
# Development server with Turbopack (faster builds)
npm run dev

# Build for production
npm run build

# Start production server
npm run start

# Run ESLint for code quality
npm run lint
```

## 🎨 Project Features

This boilerplate includes:

- ⚡ **Next.js 15.3.4** with App Router
- 🎯 **TypeScript** for type safety
- 🎨 **Tailwind CSS 4** for utility-first styling
- ⚡ **Turbopack** for faster development builds
- 📏 **ESLint** for code quality and consistency
- 📁 **src/ directory** structure for better organization
- 🤖 **GitHub Copilot** integration with custom instructions

## 🔧 VS Code Integration

### Recommended Extensions

Install these VS Code extensions for the best development experience:

```powershell
# Install via VS Code Extensions marketplace:
# - ES7+ React/Redux/React-Native snippets
# - Tailwind CSS IntelliSense
# - TypeScript Importer
# - ESLint
# - Prettier - Code formatter
# - Auto Rename Tag
```

### Run Tasks in VS Code

Use `Ctrl + Shift + P` → "Tasks: Run Task" → "Next.js: Start Development Server"

## 🚨 Common Windows Issues & Solutions

### Issue: `npx` not recognized

**Solution:**
```powershell
# Refresh PATH environment variable
$env:PATH = "C:\Program Files\nodejs;" + $env:PATH

# Or restart your terminal/VS Code
```

### Issue: Script execution disabled

**Solution:**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
```

### Issue: npm naming restrictions

**Error:** "Could not create a project called 'Development'"

**Solution:** Create project in a directory without capital letters:
```powershell
mkdir nextjs-app
cd nextjs-app
npx create-next-app@latest . --typescript --tailwind --eslint --app --src-dir
```

### Issue: Port 3000 already in use

**Solution:**
```powershell
# Find and kill process using port 3000
netstat -ano | findstr :3000
taskkill /PID [ProcessID] /F

# Or use a different port
npm run dev -- -p 3001
```

## 📝 Next Steps

1. **Customize the home page:** Edit `src/app/page.tsx`
2. **Add components:** Create reusable components in `src/components/`
3. **Add new pages:** Create new routes in `src/app/`
4. **Style with Tailwind:** Use utility classes for responsive design
5. **Configure ESLint:** Customize rules in `eslint.config.mjs`

## 🆘 Getting Help

- **Next.js Documentation:** [nextjs.org/docs](https://nextjs.org/docs)
- **Tailwind CSS:** [tailwindcss.com/docs](https://tailwindcss.com/docs)
- **TypeScript:** [typescriptlang.org/docs](https://www.typescriptlang.org/docs/)
- **Node.js Issues:** [nodejs.org/en/docs](https://nodejs.org/en/docs/)

## ✅ Verification Checklist

- [ ] Node.js and npm installed and accessible
- [ ] PowerShell execution policy configured
- [ ] Next.js project created successfully
- [ ] Development server starts without errors
- [ ] Application loads in browser at `localhost:3000`
- [ ] Hot reloading works when editing files
- [ ] No ESLint errors in the terminal

---

**Note:** This setup guide is specifically designed for Windows environments. For other operating systems, refer to the standard Next.js documentation.
