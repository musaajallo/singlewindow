# Windows PowerShell Quick Reference

Essential PowerShell commands for Next.js development on Windows.

## 🚀 Quick Setup Commands

```powershell
# Complete setup in one go (copy and paste this block)
winget install OpenJS.NodeJS
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
$env:PATH = "C:\Program Files\nodejs;" + $env:PATH
[Environment]::SetEnvironmentVariable("PATH", $env:PATH + ";C:\Program Files\nodejs", [EnvironmentVariableTarget]::User)

# Verify installation
node --version
npm --version
```

## 📁 Navigation Commands

```powershell
# Navigate to common directories
cd $HOME\Documents\Development          # Development folder
cd $HOME\Desktop                        # Desktop
cd C:\                                  # Root drive

# Create and navigate to project
mkdir nextjs-app
cd nextjs-app

# List directory contents
ls                                      # List files and folders
Get-ChildItem -Force                    # Include hidden files
```

## 🔧 Node.js Management

```powershell
# Check versions
node --version
npm --version
npx --version

# Update npm
npm install -g npm@latest

# Clear npm cache
npm cache clean --force

# Global packages location
npm list -g --depth=0
```

## 🌐 Development Server Commands

```powershell
# Start development server
npm run dev                             # Standard start
npm run dev -- -p 3001                 # Different port
npm run dev -- --host 0.0.0.0          # External access

# Stop server
# Press Ctrl+C in the terminal

# Kill all Node processes (if stuck)
taskkill /f /im node.exe
```

## 🔍 Troubleshooting Commands

```powershell
# Check what's using a port
netstat -ano | findstr :3000
netstat -ano | findstr :8080

# Kill process by PID
taskkill /PID [ProcessID] /F

# Check execution policy
Get-ExecutionPolicy
Get-ExecutionPolicy -List

# Fix execution policy
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
```

## 📦 Package Management

```powershell
# Install dependencies
npm install                             # Install from package.json
npm install [package-name]              # Add new package
npm install -D [package-name]           # Add dev dependency
npm install -g [package-name]           # Install globally

# Remove packages
npm uninstall [package-name]            # Remove package
npm uninstall -g [package-name]         # Remove global package

# Update packages
npm update                              # Update all packages
npm outdated                            # Check for outdated packages
```

## 🛠️ Project Commands

```powershell
# Create new Next.js project
npx create-next-app@latest . --typescript --tailwind --eslint --app --src-dir --use-npm

# Build and deployment
npm run build                           # Production build
npm run start                           # Start production server
npm run lint                            # Run ESLint
npm run lint -- --fix                  # Fix ESLint issues
```

## 🔐 Environment & PATH

```powershell
# View environment variables
$env:PATH                               # Current PATH
$env:NODE_ENV                           # Node environment
Get-ChildItem Env:                      # All environment variables

# Set environment variable
$env:NODE_ENV = "development"           # Temporary
[Environment]::SetEnvironmentVariable("NODE_ENV", "development", [EnvironmentVariableTarget]::User)  # Permanent

# Add to PATH
$env:PATH = "C:\Program Files\nodejs;" + $env:PATH                                                    # Temporary
[Environment]::SetEnvironmentVariable("PATH", $env:PATH + ";C:\Program Files\nodejs", [EnvironmentVariableTarget]::User)  # Permanent
```

## 📊 System Information

```powershell
# System details
systeminfo | findstr /B /C:"OS Name" /C:"OS Version"
$PSVersionTable.PSVersion              # PowerShell version
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion

# Disk space
Get-PSDrive C                           # C: drive space
Get-WmiObject -Class Win32_LogicalDisk | Select-Object Size,FreeSpace,DeviceID

# Process information
Get-Process node                        # Node.js processes
Get-Process | Where-Object {$_.ProcessName -like "*node*"}
```

## 🧹 Cleanup Commands

```powershell
# Clean npm cache
npm cache clean --force

# Remove node_modules (if needed)
Remove-Item -Recurse -Force node_modules
npm install

# Clear VS Code workspace cache
Remove-Item -Recurse -Force .vscode\settings.json

# Windows temp files cleanup
Remove-Item -Recurse -Force $env:TEMP\*
```

## 🔄 Git Commands (if using Git)

```powershell
# Initialize repository
git init
git add .
git commit -m "Initial commit"

# Check status
git status
git log --oneline

# Branch management
git branch                              # List branches
git checkout -b feature-branch          # Create and switch to branch
git merge feature-branch                # Merge branch
```

## 🔒 Security Commands

```powershell
# Check Windows Defender status
Get-MpComputerStatus

# Add folder to Windows Defender exclusions (Run as Admin)
Add-MpPreference -ExclusionPath "C:\Users\$env:USERNAME\Documents\Development"

# Check firewall rules
Get-NetFirewallRule | Where-Object {$_.DisplayName -like "*Node*"}
```

## 📝 Useful Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + C` | Stop running process |
| `Ctrl + L` | Clear terminal |
| `Tab` | Auto-complete command/path |
| `Ctrl + R` | Search command history |
| `Ctrl + Shift + C` | Copy from terminal |
| `Ctrl + Shift + V` | Paste to terminal |
| `Alt + F4` | Close terminal window |

## 📋 Copy-Paste Scripts

### Complete Project Setup
```powershell
# Run this entire block to set up a new project
cd $HOME\Documents\Development
mkdir my-nextjs-app
cd my-nextjs-app
npx create-next-app@latest . --typescript --tailwind --eslint --app --src-dir --use-npm
npm run dev
```

### Troubleshooting Reset
```powershell
# Run this if you're having issues
taskkill /f /im node.exe
npm cache clean --force
Remove-Item -Recurse -Force node_modules
npm install
npm run dev
```

### Environment Check
```powershell
# Check your environment setup
Write-Host "Node.js Version:" (node --version)
Write-Host "NPM Version:" (npm --version)
Write-Host "PowerShell Version:" $PSVersionTable.PSVersion
Write-Host "Execution Policy:" (Get-ExecutionPolicy)
Write-Host "Node.js in PATH:" ($env:PATH -split ';' | Where-Object {$_ -like "*nodejs*"})
```

---

**Tip:** Bookmark this page for quick reference during development!
