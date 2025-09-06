# Git Installation Guide

This guide will help you install Git on your system for the GitHub workshop.

## Table of Contents
- [Windows Installation](#windows-installation)
- [macOS Installation](#macos-installation)
- [Linux Installation](#linux-installation)
- [Verification](#verification)
- [Initial Configuration](#initial-configuration)

## Windows Installation

### Option 1: Git for Windows (Recommended)
1. Visit [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Download the latest version of Git for Windows
3. Run the installer and follow these recommendations:
   - **Editor**: Choose VS Code (if installed) or Nano
   - **PATH environment**: Use Git from the command line and 3rd-party software
   - **Line ending conversions**: Checkout Windows-style, commit Unix-style
   - **Terminal emulator**: Use Windows' default console window
   - **Credential manager**: Git Credential Manager

### Option 2: Using Package Manager
If you have Chocolatey installed:
```powershell
choco install git
```

If you have Winget installed:
```powershell
winget install --id Git.Git -e --source winget
```

## macOS Installation

### Option 1: Using Homebrew (Recommended)
1. Install Homebrew if not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install Git:
   ```bash
   brew install git
   ```

### Option 2: Using Git Installer
1. Visit [https://git-scm.com/download/mac](https://git-scm.com/download/mac)
2. Download and run the installer

### Option 3: Using Xcode Command Line Tools
```bash
xcode-select --install
```

## Linux Installation

### Ubuntu/Debian
```bash
sudo apt update
sudo apt install git
```

### CentOS/RHEL/Fedora
For older versions (CentOS 7, RHEL 7):
```bash
sudo yum install git
```

For newer versions (CentOS 8+, RHEL 8+, Fedora):
```bash
sudo dnf install git
```

### Arch Linux
```bash
sudo pacman -S git
```

### openSUSE
```bash
sudo zypper install git
```

## Verification

After installation, verify Git is working:

```bash
git --version
```

You should see output similar to:
```
git version 2.40.0
```

## Initial Configuration

Configure your Git identity (use your real name and email):

```bash
# Set your name
git config --global user.name "Your Full Name"

# Set your email (use the same email as your GitHub account)
git config --global user.email "your.email@example.com"

# Set default branch name to main
git config --global init.defaultBranch main

# Set default editor (optional)
git config --global core.editor "code --wait"  # For VS Code
# or
git config --global core.editor "nano"  # For Nano

# Enable colored output
git config --global color.ui auto
```

### Verify Configuration
```bash
git config --list --global
```

## SSH Key Setup (Optional but Recommended)

Setting up SSH keys allows you to authenticate with GitHub without entering your password every time.

### Generate SSH Key
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```

When prompted:
- Press Enter to save the key in the default location
- Enter a secure passphrase (optional but recommended)

### Add SSH Key to SSH Agent
```bash
# Start the ssh-agent
eval "$(ssh-agent -s)"

# Add your SSH private key to the ssh-agent
ssh-add ~/.ssh/id_ed25519
```

### Add SSH Key to GitHub
1. Copy the SSH public key:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. Go to GitHub.com → Settings → SSH and GPG keys → New SSH key
3. Paste your key and give it a descriptive title
4. Click "Add SSH key"

### Test SSH Connection
```bash
ssh -T git@github.com
```

You should see a message like:
```
Hi yourusername! You've successfully authenticated, but GitHub does not provide shell access.
```

## Common Issues and Solutions

### Issue: Git command not found
**Solution**: Restart your terminal/command prompt after installation, or add Git to your PATH manually.

### Issue: Permission denied (Windows)
**Solution**: Run your terminal as Administrator or check antivirus software.

### Issue: SSL certificate problem
**Solution**: 
```bash
git config --global http.sslverify false
```
*Note: Only use this as a temporary solution*

### Issue: Line ending issues (Windows)
**Solution**:
```bash
git config --global core.autocrlf true
```

## Next Steps

1. Create a GitHub account at [github.com](https://github.com) if you haven't already
2. Download and install a code editor (VS Code recommended)
3. Join our workshop Discord/Slack channel
4. Complete the pre-workshop survey

## Need Help?

If you encounter any issues during installation:
- Check our troubleshooting guide
- Ask in the workshop Discord/Slack channel
- Email technical support: tech-support@githubugkaduna.org
- Arrive 15 minutes early to the workshop for help with setup

---

**Workshop**: GitHub User Group Kaduna  
**Date**: September 20-21, 2025  
**Contact**: info@githubugkaduna.org
