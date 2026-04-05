# Complete DevOps Tools Installation Guide for Beginners

Welcome! This guide will help you install essential DevOps tools step-by-step. Don't worry if you're new to this—we'll explain everything in simple terms.

---

##  What You'll Learn

This guide covers installing and configuring these tools:
- **Python** - A popular programming language
- **Git** - Version control system (tracks code changes)
- **GitHub** - Cloud platform for managing code repositories
- **AWS CLI** - Command-line tool to manage Amazon Web Services
- **Terraform** - Infrastructure as Code tool
- **MongoDB Compass** - Database visualization tool
- **Docker** - Containerization platform
- **WSL & Ubuntu** - Linux environment on Windows

---

##  Before You Start

1. **Administrator Access**: You'll need admin rights on your computer
2. **Internet Connection**: Required to download tools
3. **Patience**: Take your time with each step
4. **Notes**: Keep a notepad handy for installation paths (we'll explain why)

---

# 🪟 WINDOWS INSTALLATION GUIDE

## Understanding Windows Installation

On Windows, you'll download installers and run them. Some tools need to be added to your **PATH** so you can use them anywhere in your terminal.

### ❓ What is PATH?

**PATH** is a list of folders Windows checks to find programs. When you type a command like `python`, Windows looks in PATH folders to find it. Adding a tool to PATH means you can use it from any folder in your terminal.

---

## 1️⃣ Install Python

### Step-by-Step:

1. **Download Python**
   - Go to: https://www.python.org/downloads/
   - Click the large blue **"Download Python x.x.x"** button (latest version)

2. **Run the Installer**
   - Find the downloaded file (usually in Downloads folder)
   - Double-click it to open

3. **⚠️ IMPORTANT: Setup Options**
   - ✅ **CHECK THIS BOX**: "Add Python to PATH" (at bottom of first screen)
   - Then click: **"Install Now"** or customize if you prefer
   - This automatically adds Python to your PATH!

4. **Verify Installation**
   - Open Command Prompt (Press: `Windows Key + R`, type `cmd`, press Enter)
   - Type:
   ```bash
   python --version
   ```
   - You should see something like: `Python 3.12.0`

#### 🔧 Manual PATH Setup (if you skipped the checkbox)

If Python isn't recognized:

1. **Find Python Installation Folder**
   - Open Command Prompt and type:
   ```bash
   where python
   ```
   - Copy the full path (e.g., `C:\Users\YourName\AppData\Local\Programs\Python\Python312`)

2. **Add to PATH**
   - Press: `Windows Key + X`, search for "Environment Variables"
   - Click: **"Edit the system environment variables"**
   - Click: **"Environment Variables"** button
   - Under **"System variables"**, find **"Path"** and click **"Edit"**
   - Click: **"New"** and paste your Python folder path
   - Click: **"OK"** three times
   - Restart Command Prompt and test again

---

## 2️⃣ Install Git

### Step-by-Step:

1. **Download Git**
   - Go to: https://git-scm.com/download/win
   - Windows will auto-detect your OS version
   - Click to download

2. **Run Installer**
   - Double-click the downloaded file
   - Click **"Next"** through most screens (default settings are fine)
   - Important screen: Keep **"Use Git from the Windows Command Prompt"** selected
   - Click **"Finish"**

3. **Verify Installation**
   - Open Command Prompt (new window)
   - Type:
   ```bash
   git --version
   ```
   - You should see: `git version 2.x.x`

#### ℹ️ Git Note
Git automatically adds itself to PATH during installation, so no manual setup needed!

---

## 3️⃣ Install GitHub Desktop (Optional but Recommended)

### What is GitHub Desktop?
A user-friendly app to manage GitHub repositories without using command-line.

### Step-by-Step:

1. **Option A: Microsoft Store** (Easiest)
   - Open Microsoft Store
   - Search: **"GitHub Desktop"**
   - Click **"Install"**

2. **Option B: Direct Download**
   - Go to: https://desktop.github.com/
   - Click **"Download for Windows"**
   - Run the installer

3. **Setup**
   - Launch GitHub Desktop
   - Sign in with your GitHub account (create one if needed at github.com)

---

## 4️⃣ Install AWS CLI (Amazon Web Services)

### What is AWS CLI?
Command-line tool to interact with Amazon Web Services without using the website.

### Step-by-Step:

1. **Download AWS CLI Installer**
   - Go to: https://aws.amazon.com/cli/
   - Click the **Windows installer** link (looks like `msiexec.exe` or `.msi`)

2. **Run Installer**
   - Double-click the downloaded file
   - Click **"Next"** through screens
   - Select **"Install for all users"** (recommended)
   - Click **"Finish"**

3. **Verify Installation**
   - Open a **new** Command Prompt
   - Type:
   ```bash
   aws --version
   ```
   - You should see: `aws-cli/2.x.x`

#### 🔧 Configure AWS Credentials (Important!)

Before using AWS CLI, you need to add your AWS credentials:

1. Open Command Prompt and type:
   ```bash
   aws configure
   ```

2. You'll be prompted for:
   ```
   AWS Access Key ID: [paste your access key]
   AWS Secret Access Key: [paste your secret key]
   Default region name: us-east-1
   Default output format: json
   ```

3. Get keys from: https://console.aws.amazon.com/iam/
   - Go to: Security Credentials → Access Keys
   - Create new access key and save safely

---

## 5️⃣ Install Terraform

### What is Terraform?
Infrastructure as Code tool—write code to create cloud resources automatically.

### Step-by-Step:

1. **Download Terraform**
   - Go to: https://developer.hashicorp.com/terraform/downloads
   - Click **Windows** → **AMD64** (for most computers)

2. **Extract the File**
   - Locate the downloaded `.zip` file
   - Right-click → **"Extract All"**
   - Create a folder like `C:\Terraform`
   - Extract the `terraform.exe` file there

3. **Add to PATH**
   - Press: `Windows Key + X` → Search **"Environment Variables"**
   - Click: **"Edit the system environment variables"**
   - Click: **"Environment Variables"** button
   - Under **"System variables"**, find and click **"Path"** → **"Edit"**
   - Click: **"New"**
   - Paste: `C:\Terraform` (or your extraction folder)
   - Click: **"OK"** three times
   - Restart Command Prompt

4. **Verify Installation**
   - Open a **new** Command Prompt
   - Type:
   ```bash
   terraform -version
   ```
   - You should see: `Terraform v1.x.x`

---

## 6️⃣ Install WSL 2 (Windows Subsystem for Linux)

### What is WSL?
Runs a Linux environment inside Windows—great for DevOps work.

### Step-by-Step:

1. **Enable WSL**
   - Open Command Prompt **as Administrator** (right-click → Run as administrator)
   - Type:
   ```bash
   wsl --install
   ```
   - This downloads and installs WSL 2 + Ubuntu automatically

2. **Restart Your Computer**
   - The installation requires a restart
   - Save all work and restart

3. **First Ubuntu Launch**
   - After restart, Ubuntu terminal opens automatically
   - Create a **username** and **password** (different from Windows!)
   - You're now in Linux!

#### ℹ️ Difference: Windows vs Linux
- **Windows CMD/PowerShell**: Your regular Windows terminal
- **Ubuntu Terminal**: Linux environment (better for DevOps)

---

## 7️⃣ Install Docker Desktop

### What is Docker?
Containerization platform—package applications with all dependencies.

### Step-by-Step:

1. **Ensure WSL 2 is Installed** (from previous step)

2. **Download Docker Desktop**
   - Go to: https://www.docker.com/products/docker-desktop/
   - Click **"Download for Windows"**
   - Installer should auto-detect your Windows version

3. **Run Installer**
   - Double-click the downloaded file
   - ✅ Check: **"Install required Windows components for WSL 2"**
   - Click **"OK"** and **"Finish"**
   - Restart when prompted

4. **Verify Installation**
   - Open Command Prompt or PowerShell
   - Type:
   ```bash
   docker --version
   ```
   - You should see: `Docker version 24.x.x`

5. **Test Docker**
   - Type:
   ```bash
   docker run hello-world
   ```
   - Should print a welcome message

---

## 8️⃣ Install MongoDB Compass

### What is MongoDB Compass?
Visual tool to manage MongoDB databases (no command-line needed).

### Step-by-Step:

1. **Download MongoDB Compass**
   - Go to: https://www.mongodb.com/try/download/compass
   - Choose **Windows** version
   - Select **MSI** installer

2. **Run Installer**
   - Double-click the downloaded file
   - Click through setup screens (default settings are fine)
   - Click **"Finish"**

3. **Launch**
   - Search for **"MongoDB Compass"** in Windows
   - Click to open


---

# 🐧 UBUNTU (LINUX) INSTALLATION GUIDE

### ℹ️ About Ubuntu Terminal

On Ubuntu, you'll use the **terminal** (command-line). Commands are similar but a bit different from Windows.

---

## 1️⃣ Update Your System

Before installing anything, update Ubuntu's package list:

```bash
sudo apt update && sudo apt upgrade -y
```

**Explanation:**
- `sudo` = Run as administrator
- `apt update` = Check for latest packages
- `apt upgrade` = Install updates
- `-y` = Answer "yes" to prompts automatically

---

## 2️⃣ Install Python

```bash
sudo apt install python3 python3-pip -y
```

**What's being installed:**
- `python3` = Python programming language
- `python3-pip` = Package manager for Python libraries

**Verify:**
```bash
python3 --version
```

---

## 3️⃣ Install Git

```bash
sudo apt install git -y
```

**Verify:**
```bash
git --version
```

---

## 4️⃣ Install GitHub CLI

```bash
sudo apt install gh -y
```

**What it does:** Manage GitHub from command-line

**Verify:**
```bash
gh --version
```

---

## 5️⃣ Install AWS CLI

```bash
sudo apt install awscli -y
```

**Verify:**
```bash
aws --version
```

**Configure AWS Credentials:**
```bash
aws configure
```

You'll be prompted for:
- AWS Access Key ID
- AWS Secret Access Key
- Default region (e.g., `us-east-1`)
- Output format (usually `json`)

---

## 6️⃣ Install Terraform

```bash
# Add HashiCorp repository
sudo apt install -y gnupg software-properties-common
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add Terraform to package list
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

# Install Terraform
sudo apt update && sudo apt install terraform -y
```

**Verify:**
```bash
terraform -version
```

---

## 7️⃣ Install Docker

```bash
# Install Docker
sudo apt install docker.io -y

# Start Docker service
sudo systemctl start docker

# Enable Docker to start on boot
sudo systemctl enable docker
```

**Verify:**
```bash
docker --version
```

**Optional: Run Docker without `sudo`**

```bash
# Create docker group
sudo groupadd docker

# Add your user to docker group
sudo usermod -aG docker $USER

# Apply new group
newgrp docker

# Test (should work without sudo now)
docker run hello-world
```

---


# 🍎 macOS INSTALLATION GUIDE

### ℹ️ Using Homebrew on macOS

On macOS, we use **Homebrew** (a package manager) to easily install tools.

---

## 1️⃣ Install Homebrew (Required First!)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Verify:**
```bash
brew --version
```

---

## 2️⃣ Install Python

```bash
brew install python
```

**Verify:**
```bash
python3 --version
```

---

## 3️⃣ Install Git

```bash
brew install git
```

**Verify:**
```bash
git --version
```

---

## 4️⃣ Install GitHub CLI

```bash
brew install gh
```

**Verify:**
```bash
gh --version
```

---

## 5️⃣ Install AWS CLI

```bash
brew install awscli
```

**Verify:**
```bash
aws --version
```

**Configure AWS:**
```bash
aws configure
```

---

## 6️⃣ Install Terraform

```bash
# Add HashiCorp tap
brew tap hashicorp/tap

# Install Terraform
brew install hashicorp/tap/terraform
```

**Verify:**
```bash
terraform -version
```

---

## 7️⃣ Install Docker Desktop

```bash
brew install --cask docker
```

Or download from: https://www.docker.com/products/docker-desktop/

**Verify:**
```bash
docker --version
```

---

## 8️⃣ Install MongoDB Compass

Option A: Using Homebrew
```bash
brew install --cask mongodb-compass
```

Option B: Direct download from https://www.mongodb.com/try/download/compass

---

# 🏪 Microsoft Store Availability

| Tool | Windows Store | How to Install |
|------|---------------|---|
| **Python** | ✅ Yes | Search "Python" in Microsoft Store |
| **GitHub Desktop** | ✅ Yes | Search "GitHub Desktop" |
| **Ubuntu** | ✅ Yes | Search "Ubuntu" (needed for WSL) |
| **Git** | ❌ No | Download from git-scm.com |
| **AWS CLI** | ❌ No | Download from aws.amazon.com |
| **Terraform** | ❌ No | Download from hashicorp.com |
| **Docker Desktop** | ❌ No | Download from docker.com |
| **MongoDB Compass** | ❌ No | Download from mongodb.com |

---

---

# 🎯 Understanding Environment Variables & PATH

### ❓ What is an Environment Variable?

An **environment variable** is a setting your operating system remembers and uses:

**Example:**
```
PATH = C:\Python312;C:\Git\bin;C:\Terraform
```

This tells Windows: "Look in these folders for programs"

### Common Environment Variables:

| Variable | Purpose |
|----------|---------|
| **PATH** | Folders where OS looks for programs |
| **PYTHON_HOME** | Python installation folder |
| **JAVA_HOME** | Java installation folder |
| **AWS_ACCESS_KEY_ID** | AWS authentication |

### How to Find Your Installation Paths

**Windows Command Prompt:**
```bash
# Find Python
where python

# Find Git
where git

# Find AWS
where aws
```

**Ubuntu/macOS Terminal:**
```bash
# Find Python
which python3

# Find Git
which git

# Find AWS
which aws
```

---

---

# 🚦 Recommended Installation Order (All Platforms)

### Why This Order Matters:

1. **First**: Update system and install basics
   - System packages
   - Python
   - Git

2. **Second**: Cloud tools
   - AWS CLI (requires Python)
   - Terraform

3. **Third**: Containerization
   - Docker (last because it's complex)

4. **Fourth**: UI Tools
   - MongoDB Compass
   - GitHub Desktop

---

# 🆘 Troubleshooting Guide

### Problem: "Python command not found"

**Windows:**
```bash
# Check if Python is installed
where python

# If not found, add to PATH:
# Settings → Environment Variables → Path → New → C:\Users\YourName\AppData\Local\Programs\Python\Python312
```

**Ubuntu/macOS:**
```bash
python3 --version  # Use python3 instead of python
```

---

### Problem: "Git command not found"

**Windows:**
- Reinstall Git from git-scm.com
- Restart Command Prompt after installation

**Ubuntu/macOS:**
```bash
# Ubuntu
sudo apt install git -y

# macOS
brew install git
```

---

### Problem: "Permission denied" on Ubuntu

Add `sudo` before the command:
```bash
# Instead of:
apt install python3

# Use:
sudo apt install python3
```

---

### Problem: "AWS configure not working"

1. Create AWS account at https://aws.amazon.com/
2. Go to IAM Console → Security Credentials
3. Create Access Key
4. Run: `aws configure` and paste keys

---

### Problem: "Terraform not recognized"

**Windows:** Add to PATH (see Terraform installation section)

**Ubuntu/macOS:** Should work automatically with package managers

---

### Problem: "Docker won't start on Windows"

1. Ensure WSL 2 is installed: `wsl --install`
2. Restart computer
3. Open Docker Desktop
4. Wait 2-3 minutes for startup

---

---

# 📌 Verification Commands Cheat Sheet

Test all installations with these commands:

```bash
# Python
python --version           # Windows
python3 --version         # Ubuntu/macOS

# Git
git --version

# AWS CLI
aws --version
aws configure list        # See your configuration

# Terraform
terraform -version
terraform -help          # See available commands

# Docker
docker --version
docker run hello-world   # Full test

# GitHub CLI
gh --version
gh auth status          # Check login status
```

---
