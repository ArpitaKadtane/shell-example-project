# GitHub Repository Collaborator Lister

A lightweight bash shell script designed to query the GitHub API and fetch a complete list of all users and collaborators who have access to a specific organization's repository. 

## Features
- Integrates seamlessly with the official GitHub REST API.
- Securely authentication using GitHub Personal Access Tokens (PAT).
- Easy execution via terminal command-line arguments.

---

## Step-by-Step Deployment Guide

Follow these exact steps to set up, deploy, and run the script on a remote Linux environment or AWS EC2 Virtual Machine.

### 1. Script Creation & GitHub Upload
Write your Bash script locally to fetch users from the GitHub API endpoint, save it, and commit/push it to your personal GitHub repository.

### 2. Launch Terminal
Open your local terminal (e.g., WSL, Git Bash, or Linux Terminal).

### 3. Connect to your Virtual Machine
SSH into your remote cloud instance or virtual machine using your private key (`.pem` file):
```bash
ssh -i /path/to/your-key.pem ubuntu@your-vm-ip-address
```

### 4. Clone the Project
Download your repository containing the script onto the virtual machine:
```bash
git clone https://github.com
```

### 5. Navigate to the Project Directory
Move into the newly cloned project workspace:
```bash
cd shell-example-projects
```

### 6. Configure Authentication Environment Variables
The GitHub API requires authentication to read repository data. Export your GitHub credentials as environment variables securely in your terminal session:
```bash
export username="YOUR_GITHUB_USERNAME"
export token="YOUR_GITHUB_PERSONAL_ACCESS_TOKEN"
```
*(Note: Never hardcode your token directly inside the script script file for safety.)*

### 7. Run the Script
Execute the script by passing the **Organization Name** and **Repository Name** as two trailing command-line arguments:
```bash
./collaborators.sh <organization_name> <repository_name>
```

### 8. Troubleshooting Permissions (If Denied)
If you encounter a `Permission denied` error when trying to run the file, elevate the file permissions to allow execution:
```bash
chmod +x collaborators.sh
```
*(Alternatively, you can grant global permissions using `chmod 777 collaborators.sh`)*

### 9. View Output
Upon successful execution, the terminal screen will instantly print out the formatted list of all collaborators actively assigned to that specific organizational repository.

---

## Requirements
- A GitHub Account with a generated **Personal Access Token (Classic)** or Fine-Grained Token containing `repo` read permissions.
- `curl` and `jq` command-line tools installed on your Linux instance to fetch and parse JSON API outputs.
