# Windows Troubleshooting Guide

This document contains solutions to common issues encountered when setting up and running the Next.js boilerplate on Windows systems.

## 🛠️ Node.js Installation Issues

### Problem: "node is not recognized as an internal or external command"

**Causes:**
- Node.js not installed
- Node.js not in system PATH
- Terminal needs to be restarted

**Solutions:**

1. **Check if Node.js is installed:**
   ```powershell
   # Check in Program Files
   Test-Path "C:\Program Files\nodejs\node.exe"
   ```

2. **Install Node.js if missing:**
   ```powershell
   winget install OpenJS.NodeJS
   ```

3. **Add to PATH manually:**
   ```powershell
   # Temporary (current session only)
   $env:PATH = "C:\Program Files\nodejs;" + $env:PATH
   
   # Permanent (user level)
   [Environment]::SetEnvironmentVariable("PATH", $env:PATH + ";C:\Program Files\nodejs", [EnvironmentVariableTarget]::User)
   ```

4. **Restart terminal or VS Code completely**

### Problem: "npm is not recognized as an internal or external command"

**Solution:**
```powershell
# Check if npm exists
Get-ChildItem "C:\Program Files\nodejs\" | Where-Object {$_.Name -like "*npm*"}

# Use full path temporarily
& "C:\Program Files\nodejs\npm.cmd" --version

# Add Node.js to PATH (see above)
```

## 🔐 PowerShell Execution Policy Issues

### Problem: "cannot be loaded because running scripts is disabled on this system"

**Error Example:**
```
npx : File C:\Program Files\nodejs\npx.ps1 cannot be loaded because running scripts is disabled on this system.
```

**Solution:**
```powershell
# Check current execution policy
Get-ExecutionPolicy

# Set execution policy for current user (recommended)
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force

# Alternative: Set for current process only
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process -Force
```

## 📦 NPX and Package Installation Issues

### Problem: "Need to install create-next-app" hangs or fails

**Solutions:**

1. **Clear npm cache:**
   ```powershell
   npm cache clean --force
   ```

2. **Use specific npm registry:**
   ```powershell
   npm config set registry https://registry.npmjs.org/
   ```

3. **Install globally first:**
   ```powershell
   npm install -g create-next-app
   create-next-app . --typescript --tailwind --eslint --app --src-dir
   ```

### Problem: Project naming restrictions

**Error:** "Could not create a project called 'Development' because of npm naming restrictions"

**Solution:**
```powershell
# Create project in lowercase directory
mkdir nextjs-app
cd nextjs-app
npx create-next-app@latest . [options]
```

## 🌐 Development Server Issues

### Problem: Port 3000 already in use

**Error:** "Port 3000 is already in use"

**Solutions:**

1. **Find what's using the port:**
   ```powershell
   netstat -ano | findstr :3000
   ```

2. **Kill the process:**
   ```powershell
   # Replace [PID] with the Process ID from above
   taskkill /PID [PID] /F
   ```

3. **Use a different port:**
   ```powershell
   npm run dev -- -p 3001
   ```

### Problem: "EADDRINUSE" error

**Full error:** "Error: listen EADDRINUSE: address already in use :::3000"

**Solution:**
```powershell
# Kill all Node.js processes
taskkill /f /im node.exe

# Or restart the computer if persistent
shutdown /r /t 0
```

## 🔄 Hot Reload Not Working

### Problem: Changes not reflecting in browser

**Solutions:**

1. **Check if running in development mode:**
   ```powershell
   npm run dev
   ```

2. **Clear browser cache:** `Ctrl + Shift + R` or `Ctrl + F5`

3. **Restart development server:**
   ```powershell
   # Stop with Ctrl+C, then restart
   npm run dev
   ```

4. **Check Windows Defender or antivirus:** Exclude project folder

## 📁 File System Issues

### Problem: "EPERM: operation not permitted" or "ENOENT: no such file"

**Causes:**
- Antivirus software blocking operations
- Files in use by another process
- Insufficient permissions

**Solutions:**

1. **Run PowerShell as Administrator:**
   ```powershell
   # Right-click PowerShell → "Run as Administrator"
   ```

2. **Close VS Code and other editors**

3. **Add exclusion to Windows Defender:**
   - Windows Security → Virus & threat protection
   - Add exclusion for your development folder

4. **Check file permissions:**
   ```powershell
   # Check folder permissions
   Get-Acl "C:\Users\[Username]\Documents\Development"
   ```

## 🎨 VS Code Integration Issues

### Problem: TypeScript errors not showing

**Solutions:**

1. **Restart TypeScript server:** `Ctrl + Shift + P` → "TypeScript: Restart TS Server"

2. **Check TypeScript version:**
   ```powershell
   npx tsc --version
   ```

3. **Reload VS Code window:** `Ctrl + Shift + P` → "Developer: Reload Window"

### Problem: Tailwind CSS classes not working

**Solutions:**

1. **Install Tailwind CSS IntelliSense extension**

2. **Check tailwind.config.ts:**
   ```typescript
   // Ensure content paths are correct
   content: [
     "./src/pages/**/*.{js,ts,jsx,tsx,mdx}",
     "./src/components/**/*.{js,ts,jsx,tsx,mdx}",
     "./src/app/**/*.{js,ts,jsx,tsx,mdx}",
   ]
   ```

3. **Restart development server**

## 🔍 Environment Debugging

### Gather System Information

Run these commands to gather debugging information:

```powershell
# Node.js and npm versions
node --version
npm --version

# PowerShell version
$PSVersionTable.PSVersion

# Windows version
systeminfo | findstr /B /C:"OS Name" /C:"OS Version"

# Current PATH
$env:PATH -split ';' | Where-Object {$_ -like "*node*"}

# Check execution policy
Get-ExecutionPolicy -List
```

### Environment Variables Check

```powershell
# Check Node.js related environment variables
Get-ChildItem Env: | Where-Object {$_.Name -like "*NODE*"}

# Check PATH contains Node.js
$env:PATH -split ';' | Where-Object {$_ -like "*nodejs*"}
```

## 📞 When to Seek Help

If you're still experiencing issues after trying these solutions:

1. **Provide system information** (from debugging section above)
2. **Include exact error messages**
3. **Mention what you were trying to do**
4. **List what solutions you've already tried**

## 🔗 Useful Resources

- **Node.js Windows Troubleshooting:** [nodejs.org/en/docs/guides/debugging-getting-started/](https://nodejs.org/en/docs/guides/debugging-getting-started/)
- **PowerShell Execution Policies:** [docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies)
- **Windows PATH Environment Variable:** [docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/ee537574(v=office.14)](https://docs.microsoft.com/en-us/previous-versions/office/developer/sharepoint-2010/ee537574(v=office.14))

---

**Last Updated:** June 29, 2025  
**Windows Versions Tested:** Windows 10 (1909+), Windows 11
