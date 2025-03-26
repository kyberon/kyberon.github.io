
+++
date = 2025-03-26T12:16:39+05:00
draft = false  
title = "GitHub CLI: Power at Your Fingertips"
+++



## What is GitHub CLI?
GitHub CLI is a command-line tool that lets you interact with GitHub directly from your terminal, streamlining your workflow. It allows you to manage repositories, pull requests, issues, and more without switching to a browser. With GitHub CLI, developers can automate tasks, collaborate efficiently, and boost productivity.

## Advantages of GitHub CLI
- **Efficient Workflow** – Perform GitHub actions directly from the terminal without switching to a browser.
- **Faster Collaboration** – Manage issues, pull requests, and repositories quickly with simple commands.
- **Automation & Scripting** – Integrate GitHub CLI into scripts to automate tasks and streamline development.
- **Improved Productivity** – Reduces context switching, keeping developers focused in their coding environment.
- **Seamless Git Integration** – Works alongside Git commands for a smoother version control experience.
- **Cross-Platform Support** – Available on Windows, macOS, and Linux for flexibility.
- **Customization & Aliases** – Users can create custom aliases to simplify repetitive tasks.
- **Secure Authentication** – Uses OAuth or SSH for secure login and repository management.

---

## Installing and Setting Up GitHub CLI

### Step 1: Update Package List
```sh
sudo apt update
```

### Step 2: Install GitHub CLI
```sh
sudo apt install gh -y
```

### Step 3: Verify Installation
```sh
gh --version
```

### Alternative Method: Installing via GitHub’s Official Repository
#### 1. Download & Install Dependencies
```sh
sudo apt update
sudo apt install curl -y
```

#### 2. Enable GitHub CLI Repository
```sh
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
```

#### 3. Install GitHub CLI
```sh
sudo apt update
sudo apt install gh -y
```

#### 4. Check Installation
```sh
gh --version
```

If you just need GitHub CLI and don’t require the latest version, the first method (simple apt install gh) is fine. But if you want the most up-to-date and secure version, the second method is the better choice.

---

## Checking GitHub CLI Version
To verify the installed version of GitHub CLI, use:
```sh
gh --version
```

![command screenshot](/ghCLI/a.png)

### Default Path for GitHub CLI
The default installation path for GitHub CLI is:
```sh
/usr/bin
```
To permanently set the path, run:
```sh
export PATH=/usr/bin:$PATH
echo 'export PATH=/usr/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
gh --version
```

---

## Logging into GitHub CLI
To authenticate your GitHub account using CLI, run:
```sh
gh auth login
```

### Select GitHub Platform
- If using GitHub.com, select GitHub.com (default).
- If using GitHub Enterprise, enter your Enterprise server URL.

### Choose Authentication Method
- **Preferred protocol for Git operations:** Choose HTTPS or SSH.

### Login via Browser
- The CLI will generate a one-time code and a login link.
- Copy the one-time code displayed.
- Press Enter to open GitHub in your web browser.
- Paste the one-time code and click Continue.
- Click **Authorize GitHub CLI** to complete authentication.

### Verify Authentication
To confirm successful authentication, run:
```sh
gh auth status
```

---

![command screenshot](/ghCLI/d.png)

![display screenshot](/ghCLI/f.png)

![command screenshot](/ghCLI/i.png)

## Managing Repositories with GitHub CLI

### Check Existing Repositories
To list all repositories associated with your account:
```sh
gh repo list
```

### Create a New Repository
To create a new public repository:
```sh
gh repo create multithreading --public
```

---

## Pushing Files to GitHub Using GitHub CLI

### Step 1: Open Terminal & Navigate to Your Folder
To navigate to your working directory:
```sh
cd /home/your-username
ls
```

### Step 2: Initialize Git in Your Folder
To initialize Git in your project folder:
```sh
git init
```

### Step 3: Link Local Folder to GitHub Repository
To connect your local directory with a remote repository:
```sh
git remote add origin https://github.com/your-username/multithreading.git
git remote -v
```
Expected output:
```
origin  https://github.com/your-username/multithreading.git (fetch)
origin  https://github.com/your-username/multithreading.git (push)
```

### Step 4: Add Files to Git Tracking
To stage specific files for commit:
```sh
git add thread.py
git status
```

### Step 5: Commit the Changes
To commit the staged files:
```sh
git commit -m "Added thread.py file"
```

### Step 6: Push Files to GitHub
To push the local files to the GitHub repository:
```sh
git push -u origin master
```

### Step 7: Verify the Upload
To confirm the file upload:
Run:
```sh
gh repo view --web
```
This will open the repository in your default browser.
Alternatively, manually visit:
```
https://github.com/your-username/multithreading
```
Check if `thread.py` is present in the repository.

---

![command screenshot](/ghCLI/k.png)
![command screenshot](/ghCLI/i.png)
![command screenshot](/ghCLI/m.png)

## Conclusion
GitHub CLI simplifies repository management, authentication, and collaboration directly from the terminal. By mastering `gh`, developers can speed up their workflow and enhance productivity without relying on the GitHub web interface.
