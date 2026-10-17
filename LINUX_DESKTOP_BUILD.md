> Historical project note — current qualification is documented in README.md. Completion percentages, platform promises and feature counts below have not been revalidated.

# Linux Desktop Application Build Guide

## ChatGPT 2.0 UNRESTRICTED - Linux Desktop Version

This guide explains how to build and run **Copilot Pro** (ChatGPT 2.0 UNRESTRICTED) as a native Linux desktop application using Electron.

---

## 🎯 Overview

The project is fully configured for Linux desktop deployment with:
- ✅ Electron framework (v39.2.5)
- ✅ electron-builder (v26.0.12)  
- ✅ Custom application icon
- ✅ Desktop entry files
- ✅ Multiple Linux package formats (AppImage, .deb)

---

## 📦 What You Get

### Desktop Application Features:
- **Native Linux App** - Runs as standalone desktop application
- **Auto-Start Backend** - Embedded Node.js server starts automatically
- **System Integration** - Appears in application menus
- **Offline Operation** - 100% works without internet
- **Custom Menus** - File, Edit, View, AI, and Help menus
- **Keyboard Shortcuts** - Professional IDE-like shortcuts

---

## 🏗️ Build Instructions

### Prerequisites

```bash
# Install Node.js (v18+ required)
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs

# Install build dependencies
sudo apt-get install -y build-essential
```

### Quick Build

```bash
# 1. Install dependencies
npm install

# 2. Build the frontend (React/Vite)
npm run build

# 3. Build Linux desktop app
npm run electron:build:linux
```

### Alternative: AppImage Only (Faster)

```bash
# Build AppImage only (universal Linux binary)
npx electron-builder --linux appimage --config.npmRebuild=false
```

---

## 🚀 Running the Desktop App

### Development Mode

```bash
# Start in development mode (with DevTools)
npm run electron:dev
```

This will:
1. Start the backend server (`http://localhost:3001`)
2. Launch Electron window with DevTools

### Production Mode

After building, find your package in `dist-electron/`:

```bash
# Run AppImage
chmod +x dist-electron/Copilot-Pro-*.AppImage
./dist-electron/Copilot-Pro-*.AppImage

# Install .deb (Ubuntu/Debian)
sudo dpkg -i dist-electron/copilot-pro_*.deb
```

---

## 🎨 Application Icon

The app uses a custom gradient AI icon:
- `public/icon.png` (512x512px)
- `public/icon.svg` (SVG source)

---

## ⚙️ Configuration Files

### Electron Main Process: `electron.js`
- Window management
- Backend server integration
- Custom menus
- IPC communication

### Preload Script: `preload.js`
- Secure context bridge
- Node.js API exposure

### Build Config: `package.json` → `build` section
- Linux-specific settings
- Package formats
- File inclusion/exclusion rules

---

## 🔧 Troubleshooting

### Native Module Build Errors

If you encounter errors with `tree-sitter`, `canvas`, or `@tensorflow`:

```bash
# Skip native module rebuild
npx electron-builder --linux --config.npmRebuild=false

# Use external config with exclusions
npx electron-builder --config electron-builder.yml
```

### AppImage Won't Run

```bash
# Make executable
chmod +x Copilot-Pro-*.AppImage

# Run with --no-sandbox flag
./Copilot-Pro-*.AppImage --no-sandbox
```

---

## 🌟 Desktop Features

### Custom Application Menus

**File Menu:**
- Open Project (Ctrl+O)
- Save (Ctrl+S)
- Export/Import Skills
- Quit

**AI Menu:**
- Analyze Code (Ctrl+Shift+A)
- Get Suggestions (Ctrl+Shift+S)
- Refactor (Ctrl+Shift+R)
- Toggle Learning
- View Skills

**View Menu:**
- Toggle DevTools
- Reload/Force Reload
- Zoom Controls
- Fullscreen

---

## 📦 Distribution

### AppImage (Recommended)

Universal Linux binary that runs on all distributions:

```bash
# Make executable
chmod +x Copilot-Pro-1.0.0.AppImage

# Run
./Copilot-Pro-1.0.0.AppImage
```

**Pros:**
- ✅ No installation needed
- ✅ Runs on all distros
- ✅ Self-contained
- ✅ Easy distribution

### .deb Package

For Debian/Ubuntu-based systems:

```bash
# Install
sudo dpkg -i copilot-pro_1.0.0_amd64.deb

# Fix dependencies if needed
sudo apt-get install -f

# Run
copilot-pro
```

---

## 🎯 System Requirements

- **OS:** Any modern Linux distro (Ubuntu 20.04+, Fedora 35+, etc.)
- **RAM:** 4GB minimum, 8GB recommended
- **Disk:** ~500MB for app + dependencies
- **CPU:** x64 architecture

---

## 🚀 Quick Start for End Users

```bash
# 1. Download latest AppImage from releases
wget https://github.com/SpidermanTotro/AgentFoundry-instantly/releases/latest/download/Copilot-Pro-Linux.AppImage

# 2. Make executable
chmod +x Copilot-Pro-Linux.AppImage

# 3. Run
./Copilot-Pro-Linux.AppImage
```

---

## ✅ What's Included

The Linux desktop app includes ALL features:

### Core Features:
- ✅ ChatGPT 2.0 UNRESTRICTED
- ✅ Local AI engines (offline mode)
- ✅ Code Intelligence
- ✅ WebSocket streaming
- ✅ Authentication system
- ✅ Vector Database (RAG)

### Multi-Modal AI:
- ✅ Image generation
- ✅ Video generation
- ✅ Audio/Music generation
- ✅ Web search & crawling
- ✅ Document processing

### Development Tools:
- ✅ Monaco code editor
- ✅ Syntax highlighting
- ✅ File system access
- ✅ Code execution
- ✅ GitHub integration

---

## 📚 Resources

- **GitHub:** https://github.com/SpidermanTotro/AgentFoundry-instantly
- **Electron Docs:** https://www.electronjs.org/docs
- **electron-builder:** https://www.electron.build/

---

## 📝 License

MIT License

---

**Built with ❤️ using Electron + React + Node.js**
