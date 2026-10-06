# Github-Workflow-Microsoft-Azure-for-DICOM
This repo contains a markdown file that displays procedure of the GitHub Setup required to work with the DICOM project

GitHub Workflow: Microsoft Azure Docs Contribution Setup
This document records the Git and GitHub setup used to contribute to the Microsoft Azure documentation repository.

Repository: MicrosoftDocs/azure-docs-pr

1. Fork the Microsoft repository
The first step was to fork the Microsoft repository to my personal GitHub account.

Original repository:

MicrosoftDocs/azure-docs-pr

My fork:

klokhande007/azure-docs-pr

Why fork?
A fork creates my own copy of the Microsoft repository under my GitHub account.

I can make changes in my fork and later create a pull request to the original Microsoft repository.

2. Clone the fork to the local environment
I cloned my fork to my local computer.

git clone https://github.com/klokhande007/azure-docs-pr.git

The repository was cloned to:

C:\Users\klokhande\OneDrive - Microsoft\From Nuance\DICOM\azure-docs-pr

Why clone?
Cloning downloads the repository to the local computer so that I can work with the files using Git and my development tools.

3. Navigate to the cloned repository
Because the Windows path contains spaces, the path must be enclosed in quotation marks when using Git Bash.

cd "C:\Users\klokhande\OneDrive - Microsoft\From Nuance\DICOM\azure-docs-pr"

Verify the current location
pwd

This confirms that Git Bash is working inside the cloned repository.

4. Check the existing remote repository
After cloning, I checked the configured Git remotes:

git remote -v

Initially, the output showed:

origin  https://github.com/klokhande007/azure-docs-pr.git (fetch)
origin  https://github.com/klokhande007/azure-docs-pr.git (push)

What is origin?
origin is the name Git uses for the remote repository from which the repository was cloned.

In this case:

origin → my GitHub fork

So I do not need to add origin manually because git clone already configured it.

5. Add the Microsoft repository as upstream
I added the original Microsoft repository as another remote:

git remote add upstream https://github.com/MicrosoftDocs/azure-docs-pr.git

Why add upstream?
There are two repositories involved:

origin   → My GitHub fork
upstream → Microsoft's original repository

upstream allows me to retrieve updates from the original Microsoft repository.

For example:

git fetch upstream

can be used to retrieve information about changes in Microsoft's repository.

6. Verify both remotes
I ran:

git remote -v

The final configuration is:

origin    https://github.com/klokhande007/azure-docs-pr.git (fetch)
origin    https://github.com/klokhande007/azure-docs-pr.git (push)

upstream  https://github.com/MicrosoftDocs/azure-docs-pr.git (fetch)
upstream  https://github.com/MicrosoftDocs/azure-docs-pr.git (push)

Current Git setup
                    Microsoft
                        │
                        │
                        ▼
            MicrosoftDocs/azure-docs-pr
                     ↑
                  upstream
                     │
                    fork
                     │
                     ▼
            klokhande007/azure-docs-pr
                     ↑
                  origin
                     │
                    clone
                     │
                     ▼
                 Local PC

Simple way to remember
Git remote	Points to	Purpose
origin	My GitHub fork	Push my work
upstream	Microsoft's repository	Get updates from Microsoft
Local repository	My computer	Edit and commit files
7. Current status
At this point, the repository setup is complete.

I have not started editing any documentation files yet.

Current status:

[x] Forked the Microsoft repository
[x] Cloned the fork locally
[x] Navigated to the local repository
[x] Verified origin
[x] Added upstream
[x] Verified both remotes
[ ] Create a working branch
[ ] Make documentation changes
[ ] Review changes
[ ] Commit changes
[ ] Push the branch to my fork
[ ] Create a pull request
8. Next step: Create a branch
A branch should be created when I am ready to start a specific documentation task.

For example:

git checkout -b update-azure-documentation

The branch provides a separate workspace for the changes.

I should avoid making task-specific changes directly on the main branch.

9. Expected contribution workflow
Once I start working, the general workflow will be:

Create branch
     ↓
Edit documentation
     ↓
Review changes
     ↓
Commit changes
     ↓
Push branch to my fork
     ↓
Create Pull Request
     ↓
Microsoft reviews the changes

Example commands:

Create a branch
git checkout -b <branch-name>

Check the current status
git status

Review changes
git diff

Stage changes
git add <file-name>

Commit changes
git commit -m "Update Azure documentation"

Push the branch to my fork
git push origin <branch-name>

Key Git concepts learned
Fork
A personal copy of another GitHub repository.

Microsoft repository
        ↓
      Fork
        ↓
My GitHub repository

Clone
Downloads a repository to the local computer.

GitHub repository
        ↓
      clone
        ↓
Local computer

Remote
A named reference to another Git repository.

origin   → my fork
upstream → original Microsoft repository

Branch
A separate workspace for a specific piece of work.

main
 ├── documentation-update
 ├── bug-fix
 └── new-content

Commit
A saved set of changes in the local Git history.

Push
Sends local commits to a remote repository.

git push origin <branch-name>

Pull Request
A request to merge changes from my branch into the target repository.

Useful commands learned so far
# Clone a repository
git clone <repository-url>

# Navigate to repository
cd "<path-to-repository>"

# Show configured remotes
git remote -v

# Add a remote
git remote add <name> <repository-url>

# Fetch updates from a remote
git fetch <remote>

# Check repository status
git status

# Create a new branch
git checkout -b <branch-name>

# Review changes
git diff

# Push a branch
git push origin <branch-name>

Important takeaway
The most important part of this setup is understanding the relationship between the three locations:

Microsoft's repository
        ↑
     upstream

My GitHub fork
        ↑
      origin

My local repository
        ↑
      working copy

origin = my fork

upstream = Microsoft's original repository

local repository = where I work on the files
