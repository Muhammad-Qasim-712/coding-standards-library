# 🚀 Personal Dev Command Vault

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-September%202025-blue.svg)](https://github.com)

> *A comprehensive, personal reference library of essential development commands, code snippets, and quick-start guides for all my projects.*

## 📖 Introduction

Welcome to my Personal Dev Command Vault! This repository serves as my central hub for all the commands, code snippets, and tutorials I frequently reference during development. Instead of constantly googling the same commands or digging through old projects, everything I need is organized and accessible in one place.

**Who is this for?**
- Primarily for my own reference and productivity
- Fellow developers who might find these resources helpful
- Anyone looking for a template to create their own knowledge base

**What you'll find here:**
- Essential Git and GitHub commands with real-world examples
- Terminal commands for efficient file system navigation
- Project setup guides for different tech stacks
- Reusable code snippets in multiple programming languages
- Quick reference cards for common development tasks

## 📚 Table of Contents

- [Git & GitHub Essentials](#-git--github-essentials)
- [Terminal & Shell Commands](#-terminal--shell-commands)
- [Project Setup & Environment](#-project-setup--environment)
- [Common Code Snippets](#-common-code-snippets)
- [Development Tools & Utilities](#-development-tools--utilities)
- [Quick Reference Cards](#-quick-reference-cards)
- [How to Contribute](#-how-to-contribute)
- [Repository Structure](#-repository-structure)
- [License](#-license)

---
### Prompt Coach
Here’s a reusable “Prompt Coach” prompt you can keep handy. You’ll paste this into ChatGPT (or any LLM), then just drop in your messy idea, and it will rewrite it into a polished, effective prompt for you:

Copy Paste this in your LLM:
```bash
You are my Prompt Coach. I will give you a rough or unclear prompt. 
Your task is to:
1. Clarify it
2. Add missing context
3. Structure it for best results
4. Suggest 2–3 alternative versions (different styles: simple, detailed, structured)

Here’s my rough prompt: [INSERT YOUR PROMPT HERE]
```
## 🔧 Git & GitHub Essentials

### Daily Git Workflow
```bash
# Check repository status
git status

# Add all files to staging
git add .

# Add specific file
git add filename.txt

# Commit with message
git commit -m "Add feature: user authentication"

# Push to remote repository
git push origin main

# Pull latest changes
git pull origin main
```

### Repository Management
```bash
# Clone a repository
git clone https://github.com/username/repository.git

# Initialize new repository
git init

# Add remote origin
git remote add origin https://github.com/username/repository.git

# Check remote URLs
git remote -v

# Change remote URL
git remote set-url origin https://github.com/username/new-repository.git
```

### Branch Operations
```bash
# List all branches
git branch -a

# Create and switch to new branch
git checkout -b feature/new-feature

# Switch branches
git checkout main

# Merge branch into current branch
git merge feature/new-feature

# Delete local branch
git branch -d feature/new-feature

# Delete remote branch
git push origin --delete feature/new-feature
```

### Undoing Changes
```bash
# Discard changes in working directory
git checkout -- filename.txt

# Unstage files
git reset HEAD filename.txt

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes) - DANGEROUS
git reset --hard HEAD~1

# View commit history
git log --oneline
```

---

## 💻 Terminal & Shell Commands

### File System Navigation
```bash
# Print current directory
pwd

# List files and folders
ls
ls -la          # Detailed list with hidden files
ls -lh          # Human-readable file sizes

# Change directory
cd /path/to/directory
cd ..           # Go up one level
cd ~            # Go to home directory
cd -            # Go to previous directory

# Create directory
mkdir new-folder
mkdir -p path/to/nested/folder    # Create nested directories
```

### File Operations
```bash
# Copy files
cp file.txt backup.txt
cp -r folder/ backup-folder/      # Copy directory recursively

# Move/rename files
mv old-name.txt new-name.txt
mv file.txt /path/to/destination/

# Remove files
rm file.txt
rm -rf folder/                    # Remove directory and contents (DANGEROUS)

# Create empty file
touch new-file.txt

# View file contents
cat file.txt                      # Display entire file
head file.txt                     # First 10 lines
tail file.txt                     # Last 10 lines
less file.txt                     # Paginated view
```

### Search and Find
```bash
# Find files by name
find . -name "*.txt"
find /path -name "filename.txt"

# Search within files
grep "search-term" file.txt
grep -r "search-term" .           # Recursive search in directory
grep -i "search-term" file.txt    # Case-insensitive search

# Search command history
history | grep "git"

# Find and replace in files (using sed)
sed 's/old-text/new-text/g' file.txt
```

### System Information
```bash
# Disk usage
df -h                             # Disk space usage
du -sh folder/                    # Directory size

# Process management
ps aux                            # List all processes
ps aux | grep python              # Find specific processes
kill PID                          # Kill process by ID
killall process-name              # Kill all processes by name

# System information
uname -a                          # System information
whoami                            # Current user
which python                      # Find command location
```

---

## ⚙️ Project Setup & Environment

### Python Projects
```bash
# Create virtual environment
python -m venv project-env

# Activate virtual environment (macOS/Linux)
source project-env/bin/activate

# Activate virtual environment (Windows)
project-env\Scripts\activate

# Install packages
pip install package-name
pip install -r requirements.txt

# Generate requirements file
pip freeze > requirements.txt

# Deactivate virtual environment
deactivate

# Python project structure
mkdir -p my-python-project/{src,tests,docs}
cd my-python-project
touch README.md setup.py requirements.txt .gitignore
```

### Node.js Projects
```bash
# Initialize new Node.js project
npm init
npm init -y                       # Skip questions, use defaults

# Install packages
npm install package-name
npm install package-name --save-dev
npm install -g package-name       # Install globally

# Install from package.json
npm install

# Start development server
npm start
npm run dev

# Node.js project structure
mkdir -p my-node-project/{src,public,tests}
cd my-node-project
npm init -y
touch README.md .gitignore
```

### Docker Projects
```bash
# Build Docker image
docker build -t my-app .

# Run Docker container
docker run -p 3000:3000 my-app
docker run -d --name my-container my-app    # Run in background

# List containers
docker ps                         # Running containers
docker ps -a                      # All containers

# Stop and remove containers
docker stop container-id
docker rm container-id

# List and remove images
docker images
docker rmi image-id

# Docker Compose
docker-compose up
docker-compose up -d              # Run in background
docker-compose down               # Stop and remove containers
```

---

## 📝 Common Code Snippets

### Python Snippets

#### File Handling
```python
# Read file contents
def read_file(filename):
    try:
        with open(filename, 'r', encoding='utf-8') as file:
            return file.read()
    except FileNotFoundError:
        print(f"File '{filename}' not found.")
        return None

# Write to file
def write_file(filename, content):
    try:
        with open(filename, 'w', encoding='utf-8') as file:
            file.write(content)
        print(f"Content written to '{filename}' successfully.")
    except Exception as e:
        print(f"Error writing to file: {e}")
```

#### API Requests
```python
import requests
import json

def make_api_request(url, headers=None):
    """Make a GET request to an API endpoint."""
    try:
        response = requests.get(url, headers=headers, timeout=10)
        response.raise_for_status()  # Raise exception for bad status codes
        return response.json()
    except requests.exceptions.RequestException as e:
        print(f"API request failed: {e}")
        return None

# Example usage
api_url = "https://jsonplaceholder.typicode.com/posts/1"
data = make_api_request(api_url)
if data:
    print(json.dumps(data, indent=2))
```

### JavaScript Snippets

#### Async/Await API Call
```javascript
// Fetch data from API
async function fetchData(url) {
    try {
        const response = await fetch(url);
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error fetching data:', error);
        return null;
    }
}

// Example usage
fetchData('https://jsonplaceholder.typicode.com/posts/1')
    .then(data => console.log(data))
    .catch(error => console.error(error));
```

#### DOM Manipulation
```javascript
// Wait for DOM to load
document.addEventListener('DOMContentLoaded', function() {
    console.log('DOM fully loaded');
});

// Select elements
const element = document.getElementById('myElement');
const elements = document.querySelectorAll('.myClass');

// Add event listener
element.addEventListener('click', function(event) {
    event.preventDefault();
    console.log('Element clicked!');
});

// Create and append element
const newDiv = document.createElement('div');
newDiv.textContent = 'Hello, World!';
newDiv.className = 'my-new-element';
document.body.appendChild(newDiv);
```

### Bash Scripts

#### Basic Script Template
```bash
#!/bin/bash

# Script: example-script.sh
# Description: Template for bash scripts
# Author: Your Name
# Date: $(date)

set -e  # Exit on any error

# Variables
SCRIPT_NAME=$(basename "$0")
LOG_FILE="/tmp/${SCRIPT_NAME}.log"

# Functions
log() {
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] $1" | tee -a "$LOG_FILE"
}

error_exit() {
    log "ERROR: $1"
    exit 1
}

# Main script logic
main() {
    log "Starting $SCRIPT_NAME"
    
    # Your code here
    
    log "Script completed successfully"
}

# Check if running as root (if needed)
if [[ $EUID -eq 0 ]]; then
   error_exit "This script should not be run as root"
fi

# Run main function
main "$@"
```

---

## 🛠️ Development Tools & Utilities

### VS Code Extensions (Essential)
```json
{
    "recommendations": [
        "ms-python.python",
        "ms-vscode.vscode-typescript-next",
        "bradlc.vscode-tailwindcss",
        "esbenp.prettier-vscode",
        "ms-vscode.vscode-json",
        "redhat.vscode-yaml",
        "ms-azuretools.vscode-docker",
        "gitpod.gitpod-desktop"
    ]
}
```

### Useful Aliases (.bashrc or .zshrc)
```bash
# Git aliases
alias gs='git status'
alias ga='git add'
alias gc='git commit'
alias gp='git push'
alias gl='git pull'
alias glog='git log --oneline --graph --all'

# Directory navigation
alias ..='cd ..'
alias ...='cd ../..'
alias ll='ls -la'
alias la='ls -A'

# Python
alias python='python3'
alias pip='pip3'

# Quick edit common files
alias bashrc='code ~/.bashrc'
alias zshrc='code ~/.zshrc'
alias hosts='sudo code /etc/hosts'
```

### .gitignore Templates

#### Python .gitignore
```gitignore
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# Virtual environments
venv/
env/
ENV/

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Environment variables
.env
.env.local
```

#### Node.js .gitignore
```gitignore
# Dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Production build
build/
dist/

# Environment variables
.env
.env.local
.env.production

# IDE
.vscode/
.idea/

# OS
.DS_Store
Thumbs.db
```

---

## 🎯 Quick Reference Cards

### Git Commands Quick Card
| Command | Description |
|---------|-------------|
| `git status` | Check working directory status |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Commit with message |
| `git push` | Push to remote |
| `git pull` | Pull from remote |
| `git log --oneline` | View commit history |
| `git branch` | List branches |
| `git checkout -b name` | Create and switch branch |

### Terminal Navigation Quick Card
| Command | Description |
|---------|-------------|
| `pwd` | Print working directory |
| `ls -la` | List all files with details |
| `cd path` | Change directory |
| `mkdir name` | Create directory |
| `cp src dest` | Copy file/directory |
| `mv old new` | Move/rename |
| `rm file` | Remove file |
| `grep pattern file` | Search in file |

---

## 🤝 How to Contribute

This repository is primarily for personal use, but contributions are welcome! Here's how you can help improve this knowledge base:

### Adding New Content
1. **Fork this repository** to your GitHub account
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/your-username/personal-dev-command-vault.git
   ```
3. **Create a new branch** for your additions:
   ```bash
   git checkout -b add-new-content
   ```
4. **Make your changes** by adding new commands, snippets, or sections
5. **Test your changes** to ensure all links and code work correctly
6. **Commit your changes**:
   ```bash
   git add .
   git commit -m "Add: New Python debugging techniques"
   ```
7. **Push to your fork**:
   ```bash
   git push origin add-new-content
   ```
8. **Create a Pull Request** from your fork to this repository

### Content Guidelines
- **Keep it practical**: Focus on commands and snippets you actually use
- **Add clear examples**: Include working code examples with comments
- **Maintain consistency**: Follow the existing format and style
- **Test everything**: Ensure all commands and code snippets work
- **Update the Table of Contents** if adding new sections

### Suggesting Improvements
- Open an **Issue** to suggest new sections or improvements
- Use **Discussions** for questions or general feedback
- Tag issues appropriately (enhancement, bug, documentation)

---

## 📁 Repository Structure

```
personal-dev-command-vault/
├── README.md                 # This file - main reference
├── snippets/                 # Code snippets organized by language
│   ├── python/
│   ├── javascript/
│   ├── bash/
│   └── sql/
├── configs/                  # Configuration files and dotfiles
│   ├── .gitignore-templates/
│   ├── vscode-settings/
│   └── aliases/
├── scripts/                  # Utility scripts
│   ├── setup-new-project.sh
│   └── backup-configs.py
├── docs/                     # Additional documentation
│   ├── git-workflows.md
│   ├── docker-guide.md
│   └── deployment-checklist.md
└── LICENSE                   # MIT License
```

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🔗 Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [MDN Web Docs](https://developer.mozilla.org/)
- [Python Documentation](https://docs.python.org/3/)
- [Node.js Documentation](https://nodejs.org/en/docs/)

---

**📌 Remember**: This is a living document. Keep it updated as you learn new commands and discover better ways of doing things!

*Last updated: September 2025*
