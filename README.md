# Git Command Cheatsheet

## Repository Setup
```bash
# Initialize a new Git repository
git init

# Clone an existing repository
git clone <repository-url>

# Configure user information
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Basic Workflow
```bash
# Check repository status
git status

# Add files to staging area
git add <filename>
git add .  # Add all changes

# Commit changes
git commit -m "Descriptive message"

# Push changes to remote
git push -u origin <branch-name>

# Pull changes from remote
git pull origin <branch-name>
```

## Branch Management
```bash
# List all branches
git branch
git branch -a  # Show remote branches too

# Create new branch
git checkout -b <new-branch-name>

# Switch to existing branch
git checkout <branch-name>

# Create branch from remote branch
git checkout -b <new-branch> origin/<branch-name>

# Delete branch locally
git branch -d <branch-name>
git branch -D <branch-name>  # Force delete

# Delete remote branch
git push origin --delete <branch-name>
```

## Remote Operations
```bash
# Add remote repository
git remote add origin <repository-url>

# List remote repositories
git remote -v

# Fetch changes from remote
git fetch origin
git fetch --all  # All remotes

# Push to a different branch
git push origin <local-branch>:<remote-branch>

# Track remote branch
git branch --set-upstream-to=origin/<branch-name>
```

## History and Diff
```bash
# View commit history
git log
git log --oneline  # Compact view
git log --graph --oneline --all  # Visual branch history
git log --date=short --pretty=format:"%h %ad %s (%an)"  # Custom format

# Compare branches
git log <branch1>..<branch2> --oneline

# Show changes between commits
git diff <commit1>..<commit2>

# Show changes in working directory
git diff
```

## Undoing Changes
```bash
# Reset to specific commit
git reset --hard <commit-hash>

# Reset to remote branch
git reset --hard origin/<branch-name>

# Revert a commit (creates a new commit)
git revert <commit-hash>

# Revert a merge commit
git revert -m 1 <merge-commit-hash>

# Amend the last commit
git commit --amend
```

## Advanced Operations
```bash
# Cherry-pick a commit
git cherry-pick <commit-hash>

# Interactive rebase
git rebase -i <base-branch>
git rebase -i HEAD~3  # Rebase last 3 commits

# Stash changes
git stash
git stash pop  # Apply and remove stashed changes
git stash list  # View stashed changes

# Clean untracked files
git clean -fd  # Remove untracked files and directories
git clean -fdx  # Also remove ignored files
git clean -fdxn  # Dry run (preview what would be deleted)
```

## Pull Requests (GitHub CLI)
```bash
# Create pull request
gh pr create --base <target-branch> --head <your-branch>

# View pull requests
gh pr list

# Check out a pull request
gh pr checkout <pr-number>
```

## Tagging
```bash
# Create a tag
git tag <tag-name>
git tag -a <tag-name> -m "Tag message"  # Annotated tag

# Push tags to remote
git push origin <tag-name>
git push --tags  # Push all tags
```

## Git Troubleshooting
```bash
# Check reflog history
git reflog

# Garbage collection
git gc --prune=now

# Repair repositories
git fsck

# Recover lost commits
git fsck --lost-found
```
