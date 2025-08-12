# Installation
# My portfolio webstie: [www.mahdiharooni.ir](https://mahdiharooni.ir)


![Static Badge](https://img.shields.io/badge/course_title-git_and20_github-red?logo=github)
![Static Badge](https://img.shields.io/badge/course_title-git_and_github-pink?style=flat&labelColor=green&color=red)

![Static Badge](https://img.shields.io/badge/course_title-git_and_github-pink?style=flat&labelColor=green&color=red)



```

///////////////////////////////////////////
// The Complete and Practical Summary of the Pro Git Book



///////////////////////////////////////////
//Table of Contents

// License
// Preface by Scott Chacon
// Preface by Ben Straub
// Dedications
// Contributors
// Introduction

// Getting Started
//   About Version Control
//   A Short History of Git
//   What is Git?
//   The Command Line
//   Installing Git
//   First-Time Git Setup
//   Getting Help
//   Summary

// Git Basics
//   Getting a Git Repository
//   Recording Changes to the Repository
//   Viewing the Commit History
//   Undoing Things
//   Working with Remotes
//   Tagging
//   Git Aliases
//   Summary

// Git Branching
//   Branches in a Nutshell
//   Basic Branching and Merging
//   Branch Management
//   Branching Workflows
//   Remote Branches
//   Rebasing
//   Summary

// Git on the Server
//   The Protocols
//   Getting Git on a Server
//   Generating Your SSH Public Key
//   Setting Up the Server
//   Git Daemon
//   Smart HTTP
//   GitWeb
//   GitLab
//   Third Party Hosted Options
//   Summary

// Distributed Git
//   Distributed Workflows
//   Contributing to a Project
//   Maintaining a Project
//   Summary

// GitHub
//   Account Setup and Configuration
//   Contributing to a Project
//   Maintaining a Project
//   Managing an organization
//   Scripting GitHub
//   Summary

// Git Tools
//   Revision Selection
//   Interactive Staging
//   Stashing and Cleaning
//   Signing Your Work
//   Searching
//   Rewriting History
//   Reset Demystified
//   Advanced Merging
//   Rerere
//   Debugging with Git
//   Submodules
//   Bundling
//   Replace
//   Credential Storage
//   Summary

// Customizing Git
//   Git Configuration
//   Git Attributes
//   Git Hooks
//   An Example Git-Enforced Policy
//   Summary

// Git and Other Systems
//   Git as a Client
//   Migrating to Git
//   Summary

// Git Internals
//   Plumbing and Porcelain
//   Git Objects
//   Git References
//   Packfiles
//   The Refspec
//   Transfer Protocols
//   Maintenance and Data Recovery
//   Environment Variables
//   Summary

// Appendix A: Git in Other Environments
//   Graphical Interfaces
//   Git in Visual Studio
//   Git in Visual Studio Code
//   Git in IntelliJ / PyCharm / WebStorm / PhpStorm / RubyMine
//   Git in Sublime Text
//   Git in Bash
//   Git in Zsh
//   Git in PowerShell
//   Summary

// Appendix B: Embedding Git in your Applications
//   Command-line Git
//   Libgit2
//   JGit
//   go-git
//   Dulwich

// Appendix C: Git Commands
//   Setup and Config
//   Getting and Creating Projects
//   Basic Snapshotting
//   Branching and Merging
//   Sharing and Updating Projects
//   Inspection and Comparison
//   Debugging
//   Patching
//   Email
//   External Systems
//   Administration
//   Plumbing Commands



///////////////////////////////////////////
// Chapter 01 – Getting Started
// Install Git, configure identity, set defaults, and create/clone repositories

# Check installed Git version
git --version

# Set global identity (name and email) for all repositories
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Set local identity (overrides global for current repository)
git config user.name "Local Name"
git config user.email "local@example.com"

# View Git configuration settings
git config --list
git config --global --list
git config --system --list
git config user.name
git config user.email

# Set default text editor for Git (used in commit messages, rebase, etc.)
git config --global core.editor "vim"
git config --global core.editor "nano"
git config --global core.editor "code --wait"
git config --global core.editor "notepad"

# Enable colored Git output
git config --global color.ui true

# Git built-in help system
git help
git help <command>
git <command> --help
man git
git help -a      # List all available commands
git help -g      # List common guides

# Install Git (OS-specific methods)
# macOS
brew install git

# Debian/Ubuntu
sudo apt install git

# Fedora
sudo dnf install git

# Windows
# Download from https://git-scm.com/downloads
# Use Git Bash or Git CMD after installation

# Initialize a new repository in the current folder
git init

# Clone a remote repository into current directory
git clone <repository-url>

# Clone and rename target directory
git clone <repository-url> <target-directory>

# Notes:
# - Git configurations exist at 3 levels: system (/etc/gitconfig), global (~/.gitconfig), and local (.git/config)
# - Local overrides global, global overrides system
# - `git init` creates an empty repository starting from scratch
# - `git clone` copies an existing project and sets up remote tracking
# - Use `git config` to customize behavior and identity
# - Editor settings affect commands requiring input (e.g., commit, rebase) 



///////////////////////////////////////////
// Chapter 02 – Git Basics
// Working directory, staging, commits, file tracking, and basic history

# Check the current repository status
git status

# Add files to the staging area
git add <file>                    # Add specific file
git add .                         # Add all files in current directory
git add -A                        # Add all changes (new, modified, deleted)
git add -u                        # Add updated/deleted files, not new ones
git add -p                        # Interactively choose chunks to stage

# Commit staged changes to the repository
git commit -m "Your commit message"             # Commit with message
git commit                                      # Opens editor to write message
git commit -a -m "Commit message"               # Automatically stage tracked files, then commit
git commit --amend                              # Amend the last commit (message or staged content)

# View commit history
git log
git log --oneline                               # Compact, one-line-per-commit view
git log --stat                                  # Include diffstat summary
git log -p                                      # Include full patch (diffs)
git log --graph                                 # ASCII graph of branches and merges
git log --pretty=oneline                        # One line with SHA
git log --pretty=format:"%h - %an, %ar : %s"     # Custom format

# Check differences between working directory, staging area, and latest commit
git diff                                        # Changes in working directory (unstaged)
git diff --staged                               # Differences between staged and last commit
git diff HEAD                                   # Difference between working directory and HEAD

# Remove files
git rm <file>                                   # Delete file from working dir and staging area
git rm --cached <file>                          # Unstage (keep file in working dir)
git rm -f <file>                                # Force delete (if modified)

# Move or rename files
git mv <oldname> <newname>                      # Stage rename/move

# Git aliases for faster commands
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --all --decorate"

# Notes:
# - Working directory: your current project files
# - Staging area (index): preps what will go into the next commit
# - Committed: snapshot saved in Git database
# - `git add` stages changes; `git commit` saves them
# - Use `git diff` and `git status` to inspect what's changed
# - Aliases are set via `git config --global alias.<shortcut> <command>`
# - `git rm --cached` is useful for stopping tracking without deleting file



///////////////////////////////////////////
// Chapter 03 – Git Branching
// Branch creation, switching, merging, resolving conflicts, and history control

# List branches
git branch                           # List local branches
git branch -v                        # Show last commit on each branch
git branch --merged                  # Branches already merged into current
git branch --no-merged               # Branches not yet merged

# Create new branch
git branch <branch-name>

# Switch to another branch
git checkout <branch-name>           # Legacy switch
git switch <branch-name>             # Preferred way (Git 2.23+)

# Create and switch to a new branch
git checkout -b <branch-name>        # Legacy
git switch -c <branch-name>          # Preferred

# Rename a branch
git branch -m <new-name>             # Rename current branch
git branch -m <old-name> <new-name>  # Rename another branch

# Delete a branch
git branch -d <branch-name>          # Delete safely (only if merged)
git branch -D <branch-name>          # Force delete

# Merge another branch into current branch
git merge <branch-name>              # Merge target into current branch

# Abort a merge in progress (e.g., after conflict)
git merge --abort

# Resolve merge conflicts manually and mark resolved
git add <conflicted-files>
git commit                           # Finalize merge after resolving

# View commits from all branches
git log --oneline --decorate --graph --all

# Rebase current branch onto another
git rebase <base-branch>             # Replay current commits on top of base
git rebase -i HEAD~<n>               # Interactive rebase last n commits

# Abort an in-progress rebase
git rebase --abort

# Continue after resolving rebase conflicts
git rebase --continue

# Skip a commit during rebase
git rebase --skip

# Cherry-pick specific commit onto current branch
git cherry-pick <commit-hash>

# Stash changes temporarily (e.g., before switching branches)
git stash
git stash list
git stash apply                      # Apply most recent stash
git stash apply stash@{n}            # Apply specific stash
git stash pop                        # Apply and remove from stash
git stash drop stash@{n}             # Delete a specific stash
git stash clear                      # Delete all stashes

# Notes:
# - Branches are lightweight pointers to commits
# - `git merge` combines histories, may create merge commits
# - `git rebase` rewrites history by replaying commits
# - Use `rebase -i` for clean history (e.g., squash/fixup)
# - Conflicts must be resolved manually during merge or rebase
# - Use `git stash` to save uncommitted changes without committing
# - Always test before force-deleting branches or rebasing shared branches



///////////////////////////////////////////
// Chapter 04 – Git on the Server
// Setting up remote repositories, SSH access, sharing, and server setup

# Show configured remote repositories
git remote                           # List short names
git remote -v                        # Show URLs for fetch/push

# Add a new remote
git remote add <name> <url>         # Example: git remote add origin git@github.com:user/repo.git

# Rename a remote
git remote rename <old> <new>

# Remove a remote
git remote remove <name>
git remote rm <name>                # Equivalent

# Show detailed info about a remote
git remote show <name>

# Change remote URL
git remote set-url <name> <new-url>

# Fetch from remote (without merging)
git fetch <remote>                  # Fetch all branches from remote
git fetch <remote> <branch>

# Push changes to remote
git push <remote>                   # Push default branch
git push <remote> <branch>          # Push specific branch
git push -u <remote> <branch>       # Push and set upstream for tracking

# Pull changes (fetch + merge/rebase)
git pull                            # From default remote/branch
git pull --rebase                   # Rebase instead of merge

# Clone a repository from a remote server
git clone <url>
git clone <url> <folder>            # Clone into specific folder

# Set up Git server over SSH (bare repository)
ssh user@server
mkdir -p ~/repos/project.git
cd ~/repos/project.git
git init --bare                     # Initialize a bare repository (no working directory)

# Push local project to the new server
git remote add origin ssh://user@server:/home/user/repos/project.git
git push -u origin master

# Access remote with SSH key (client-side)
ssh-keygen                          # Generate SSH key (default: ~/.ssh/id_rsa)
# Copy public key to server
ssh-copy-id user@server

# Manual SSH key upload (if no ssh-copy-id)
cat ~/.ssh/id_rsa.pub | ssh user@server "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"

# Use Git Daemon (anonymous read access, TCP)
# On server:
git daemon --reuseaddr --base-path=/home/git/ --export-all --enable=receive-pack --informative-errors --verbose

# Clone from Git Daemon:
git clone git://server/path/to/repo.git

# Use HTTPS for Git server (e.g., via GitHub, GitLab, or Apache/nginx + smart HTTP)
# Clone over HTTPS:
git clone https://example.com/user/repo.git

# Notes:
# - Bare repos are used for sharing; no working directory
# - `git push -u` sets upstream so later you can just `git push`
# - SSH keys allow secure, password-less authentication
# - Use `git remote` to manage and inspect connections
# - Git Daemon and HTTPS are alternatives to SSH
# - GitHub/GitLab provide hosted solutions that integrate all these protocols



///////////////////////////////////////////
// Chapter 05 – Distributed Git
// Collaborating via forks, tracking branches, pushing/pulling, and contribution workflows

# View remotes and their branches
git remote -v                           # Show remotes and their URLs
git remote show <remote>               # Show tracking branches and more

# Fetch from a remote without merging
git fetch <remote>

# Merge fetched changes from a remote branch
git merge <remote>/<branch>

# Rebase on top of a remote branch (cleaner history)
git rebase <remote>/<branch>

# Add a new remote (e.g., contributor fork)
git remote add <name> <url>

# Push a branch to a remote
git push <remote> <branch>

# Set upstream for a branch (track remote)
git push -u <remote> <branch>

# Track a remote branch locally
git checkout --track <remote>/<branch>     # Create local branch tracking remote one
git branch --set-upstream-to=<remote>/<branch>  # Set tracking for existing branch

# View configured upstream branch
git status
git branch -vv                             # Show upstream info for all local branches

# Delete a remote-tracking branch (e.g., if deleted upstream)
git fetch --prune
git remote prune <remote>

# Push to multiple remotes
git remote set-url --add <remote> <url2>
git remote set-url --delete <remote> <url>

# Pull with rebase (preferred in collaborative workflows)
git pull --rebase

# Push a tag to a remote
git push <remote> <tag>

# Push all tags to remote
git push <remote> --tags

# Fetch all branches and tags
git fetch --all

# Remove a remote
git remote remove <name>

# Collaboration flow (example):
# 1. Fork upstream project on GitHub
# 2. Clone your fork
# 3. Add original repo as upstream remote:
git remote add upstream https://github.com/original/project.git

# 4. Sync changes from upstream:
git fetch upstream
git rebase upstream/main                # or git merge upstream/main

# Notes:
# - Tracking branches auto-follow a remote branch
# - `git fetch` + `merge` or `rebase` gives more control than `git pull`
# - Use `--rebase` to keep a linear history when collaborating
# - `git remote prune` removes stale tracking references
# - Tags are not pushed by default, must push explicitly
# - Remote workflows often use multiple remotes (origin, upstream)



///////////////////////////////////////////
// Chapter 06 – GitHub
// Working with hosted repositories, forks, pull requests, issues, and collaboration

# Clone a GitHub repository
git clone https://github.com/user/repo.git
git clone git@github.com:user/repo.git           # SSH

# Add remotes for fork and upstream
git remote add origin https://github.com/yourname/repo.git
git remote add upstream https://github.com/original/repo.git

# Create and push a feature branch
git checkout -b feature-branch
git push -u origin feature-branch

# Keep fork up to date with upstream
git fetch upstream
git checkout main
git merge upstream/main

# Alternatively, use rebase
git rebase upstream/main

# Push local changes to your fork
git push origin main
git push origin feature-branch

# Create a pull request (PR) from GitHub web interface

# Sync fork using GitHub CLI
gh repo clone yourname/repo
gh repo fork --clone
gh repo sync
gh pr create --base main --head yourname:feature-branch --title "PR Title" --body "Description"
gh pr list
gh pr view
gh pr checkout <number>
gh pr merge

# Fork a project (GitHub UI) then:
git clone https://github.com/yourname/project.git
git remote add upstream https://github.com/original/project.git

# Manage issues with GitHub CLI
gh issue list
gh issue view <number>
gh issue create --title "Issue Title" --body "Issue description"
gh issue status

# View repo info with GitHub CLI
gh repo view
gh repo list user
gh repo fork

# Notes:
# - `origin` typically points to your fork
# - `upstream` points to the original project
# - Use branches to isolate work; PRs help propose changes
# - GitHub CLI (`gh`) helps automate PR and issue management
# - Always sync your fork before contributing
# - Tags and releases are managed via GitHub UI or CLI
# - GitHub Actions (CI/CD) can automate workflows (covered in later chapters)



///////////////////////////////////////////
// Chapter 07 – Git Tools
// Stashing, cleaning, searching, signing, attributes, submodules, debugging

# Stash current changes
git stash
git stash push -m "message"               # Save with custom message
git stash -u                           # Include untracked files
git stash -a                           # Include ignored and untracked files

# List, apply, and drop stashes
git stash list
git stash show                         # Show latest stash
git stash show -p                      # Show full patch
git stash apply                        # Apply latest stash
git stash apply stash@{n}              # Apply specific stash
git stash pop                          # Apply and remove
git stash drop stash@{n}               # Delete specific
git stash clear                        # Delete all

# Clean untracked or ignored files
git clean -n                           # Dry-run (show what would be deleted)
git clean -f                           # Delete untracked files
git clean -fd                          # Delete untracked files and directories
git clean -fx                          # Remove ignored files as well

# Search project history
git log -S <string>                    # Search commit diffs for string
git log -G <regex>                     # Regex search in diffs
git grep <pattern>                     # Search working directory
git grep -n <pattern>                  # Include line numbers

# Sign commits with GPG
git commit -S -m "Signed commit"
git tag -s v1.0 -m "Signed tag"
git tag -v v1.0                        # Verify tag signature

# Configure signing
git config --global user.signingkey <key-id>
git config --global commit.gpgsign true

# Git attributes (per-file settings)
# Example: mark *.jpg files as binary
echo "*.jpg binary" >> .gitattributes

# Useful attributes
*.txt diff=custom                      # Use custom diff driver
*.ps merge=ignore-space-change        # Use custom merge driver

# External diff/merge tools
git config --global diff.tool meld
git config --global merge.tool kdiff3
git difftool
git mergetool

# Git Submodules
git submodule add <repo-url> <path>   # Add submodule
git submodule init
git submodule update
git submodule update --remote         # Fetch latest commits from submodule origin

# Show submodule status
git submodule status

# Clone project with submodules
git clone --recurse-submodules <repo-url>

# Troubleshooting and debugging
git fsck                              # Verify integrity of object database
git gc                                # Run garbage collection
git prune                             # Remove unreachable objects
git reflog                            # Show history of HEAD changes

# Recover lost commits
git reflog
git checkout <commit-id>

# Notes:
# - Use `stash` to save dirty work temporarily
# - `clean` is destructive: always dry-run first
# - `log -S` and `-G` are powerful search tools
# - GPG signing ensures authenticity
# - Git attributes help control how Git handles certain files
# - Submodules allow embedding external repos inside another
# - `reflog` is invaluable for recovering lost work



///////////////////////////////////////////
// Chapter 08 – Customizing Git
// Git configuration, hooks, aliases, templates, and external tools

# View Git configuration
git config --list
git config --global --list
git config --system --list

# Set configuration values
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global core.editor "vim"
git config --global color.ui auto

# Configure aliases for shortcuts
git config --global alias.st status
git config --global alias.ci commit
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.lg "log --oneline --graph --all"

# Configure global Git ignore file
echo "*.log" >> ~/.gitignore_global
git config --global core.excludesfile ~/.gitignore_global

# Define a custom Git template for new repositories
mkdir -p ~/.git-templates/hooks
cp prepare-commit-msg ~/.git-templates/hooks/
chmod +x ~/.git-templates/hooks/prepare-commit-msg
git config --global init.templateDir ~/.git-templates

# Initialize repo with template
git init                                # Uses template hooks/settings

# Use Git hooks (scripts triggered by Git events)
# Located in .git/hooks/

# Common hooks:
# - pre-commit: run checks before commit (e.g., lint)
# - prepare-commit-msg: modify commit message automatically
# - commit-msg: validate commit message
# - post-commit: run actions after a successful commit

# Enable a hook
cp .git/hooks/pre-commit.sample .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

# Sample: pre-commit hook to block TODOs
echo 'grep -n "TODO" *.py && exit 1' > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

# Use external diff and merge tools
git config --global diff.tool meld
git config --global merge.tool meld
git difftool
git mergetool

# Notes:
# - Git config levels: system (/etc/gitconfig), global (~/.gitconfig), local (.git/config)
# - Hooks are shell scripts triggered by Git events
# - Templates can standardize repo setup (hooks, files)
# - Aliases improve workflow speed
# - Tools like `meld`, `kdiff3`, `vimdiff`, etc. can be integrated for visual comparisons



///////////////////////////////////////////
// Chapter 09 – Git and Other Systems
// Interfacing with Subversion, CVS, Perforce; using Git as a client

# Git as a Subversion client
git svn clone <svn-repo-url>               # Clone SVN repo into Git
git svn clone <svn-url> -T trunk -b branches -t tags    # Specify layout
git svn fetch                              # Fetch latest SVN commits
git svn rebase                             # Rebase against latest SVN changes
git svn dcommit                            # Commit Git changes back to SVN
git svn info                               # Show SVN info for Git repo
git svn log                                # Show SVN commit history
git svn set-tree                           # Set a Git tree to reflect SVN
git svn create-ignore                      # Add ignore patterns from SVN
git svn show-ignore                        # Display ignore patterns

# Track remote SVN branches
git branch -r                              # List remote-tracking branches
git checkout -b <local-branch> <remote>    # Track a remote SVN branch locally

# Importing from other version control systems
# From CVS (requires cvsps tool)
git cvsimport -v -d <CVSROOT> -C <git-dir> <module>

# From Perforce (via p4)
git p4 clone //depot/project@all           # Clone from Perforce
git p4 sync                                # Sync Perforce changes
git p4 submit                              # Submit Git commits back to Perforce
git p4 rebase                              # Rebase on top of latest Perforce state

# Export Git repo to other VCS
# Export to a tarball for archival or conversion
git archive --format=tar --prefix=project/ HEAD > project.tar

# Export to Subversion or others (via intermediary tools like git-fast-export)
git fast-export HEAD > repo.export
git fast-import < repo.export

# Notes:
# - `git svn` lets you work with SVN while retaining Git features
# - Only one branch can be pushed to SVN with `dcommit`
# - `git p4` and `git cvsimport` are bridges for legacy systems
# - Converting between systems often requires careful mapping of metadata
# - Exported Git histories (via `fast-export`) can be re-imported elsewhere



///////////////////////////////////////////
// Chapter 10 – Git Internals
// Low-level Git concepts: plumbing commands, objects, references, packfiles, and maintenance

# Git as a content-addressable filesystem
# - Git stores objects in .git/objects directory
# - Objects are identified by SHA-1 hash
# - Types: blob (file), tree (directory), commit (snapshot), tag (annotation)

# Inspect raw Git objects
git init                                      # Creates .git directory
ls .git                                       # Shows config, HEAD, objects/, refs/, etc.
git hash-object <file>                        # Compute SHA-1 for file contents
git hash-object -w <file>                     # Store blob object in database
git cat-file -p <sha1>                        # Pretty-print object content
git cat-file -t <sha1>                        # Show object type (blob/tree/commit/tag)

# Creating tree and commit objects manually (plumbing)
git update-index --add <file>                 # Stage file into index
git write-tree                                # Write current index as a tree object
git commit-tree <tree-sha1> -m "message"      # Create commit from tree
git update-ref refs/heads/<branch> <commit>   # Move branch to commit

# Exploring references
cat .git/HEAD                                 # Shows current branch ref
git show-ref                                  # List all references (branches/tags)
git rev-parse HEAD                            # Resolve ref to SHA-1
git symbolic-ref HEAD                         # Show symbolic reference

# Packfiles
git gc                                        # Compress loose objects into packfiles
ls .git/objects/pack                          # View pack and index files
git verify-pack -v <pack-file>                # Inspect packfile contents

# Refspecs & transfer
# - Defines how refs are pushed/fetched between repos
git fetch origin refs/heads/main:refs/remotes/origin/main
git push origin main:main

# Maintenance and data recovery
git fsck                                      # Verify repository integrity
git reflog                                    # Show branch movement history
git show HEAD@{1}                             # Inspect older branch tip
git cat-file -p <dangling-sha1>               # Recover dangling object

# Notes:
# - Git internals revolve around 4 object types: blob, tree, commit, tag
# - Plumbing commands are low-level building blocks; porcelain commands are user-friendly
# - Packfiles improve storage and transfer efficiency
# - Understanding internals aids in data recovery and custom tooling



///////////////////////////////////////////
// Appendix A – Git in Other Environments
// Using Git with GUIs, IDEs, and different shell environments

# Graphical Git tools
gitk                                     # GUI for browsing history (graph view)
git gui                                  # GUI for staging/committing changes
# Notes:
# - gitk ~ visualizes `git log --graph`
# - git gui ~ focus on staging, committing, and basic history
# - Use `gitk --all` to show all branch histories

# GitHub Desktop (Windows/macOS)
# - Workflow-oriented GUI for basic Git operations
# - Supports cloning, committing, syncing, and PRs
# - Hides low-level operations, focuses on common tasks

# Git in IDEs
# Visual Studio:
#   - Integrated Team Explorer for Git
#   - Supports clone, branch, commit, sync
# Visual Studio Code:
#   - Built-in Source Control panel
#   - Quick actions: stage, commit, pull/push
# IntelliJ / PyCharm / WebStorm / PhpStorm / RubyMine:
#   - VCS menu for commit, branch, log, stash
# Sublime Text:
#   - Requires Git plugins (GitSavvy, Sublime Merge integration)

# Git in shells
# Bash:
#   - Default environment for Git
#   - Enhance prompt with branch info via `__git_ps1`
# Zsh:
#   - Supports rich Git prompt & plugins (oh-my-zsh `git` plugin)
# PowerShell:
#   - Use `posh-git` module for tab-completion and branch info

# Tips:
# - GUI/IDE tools are convenient but expose limited features
# - Command-line always gives full Git control
# - Combine CLI + GUI for productivity (e.g., staging in GUI, rebasing in CLI)

# Notes:
# - GUIs like gitk help visualize branches and history
# - IDE integration is great for local workflows
# - Shell enhancements improve awareness of repo state in prompt
# - Always know CLI equivalents for GUI actions



///////////////////////////////////////////
// Appendix B: Embedding Git in your Applications
// Using Git programmatically via command-line or libraries like libgit2, JGit, go-git, and Dulwich

# Command-line Git
# - Easiest way to integrate Git: invoke CLI from your app
# - Pros: full feature coverage, same behavior as terminal
# - Cons: platform-dependent, slower for heavy operations

# Basic pattern (pseudo-code)
system("git init")
system("git add file.txt")
system("git commit -m 'Message'")

# Capture output
result = `git status`
puts result

# Libgit2 (C library)
# - High-performance library for Git operations
# - Used in apps like GitHub Desktop
# - Bindings in many languages: Python (pygit2), Ruby (rugged)
# Examples:
# - Open repo: git_repository_open()
# - Lookup commit: git_commit_lookup()
# - Create branch: git_branch_create()

# JGit (Java library)
# - Pure Java Git implementation
# - Used in Eclipse EGit plugin
# Example usage:
Repository repo = new FileRepository("/path/to/repo/.git");
Git git = new Git(repo);
git.add().addFilepattern("file.txt").call();
git.commit().setMessage("My commit").call();

# go-git (Go library)
# - Pure Go Git library
# - Supports reading/writing repos and performing most Git ops
repo, _ := git.PlainOpen("/path/to/repo")
w, _ := repo.Worktree()
w.Add("file.txt")
w.Commit("Commit message", &git.CommitOptions{})

# Dulwich (Python library)
# - Pure Python Git library
# - Provides both low-level and porcelain API
from dulwich import porcelain
porcelain.clone("git://server/repo.git", "local_path")
porcelain.commit(".", message=b"My commit")

# Notes:
# - Choose CLI for simplicity; choose libraries for performance or embedded apps
# - Libgit2 and its bindings offer most complete low-level control
# - Pure-language libraries (JGit, go-git, Dulwich) are best for cross-platform and server apps
# - Always consider security and performance when executing Git from your app



///////////////////////////////////////////
// Appendix C: Git Commands
// Cheat sheet of common Git commands grouped by usage

# Setup and Config
git config --global user.name "Your Name"            # Set global username
git config --global user.email "you@example.com"     # Set global email
git config --global core.editor "code --wait"        # Set default editor
git help <command>                                  # Get help for command

# Getting and Creating Projects
git init                                            # Initialize new repo
git clone <url>                                     # Clone repo
git clone <url> <dir>                               # Clone to specific dir

# Basic Snapshotting
git status                                          # Show working tree status
git add <file>                                      # Stage file
git add .                                           # Stage all changes
git commit -m "Message"                             # Commit staged changes
git commit --amend                                  # Amend last commit
git rm <file>                                       # Remove file and stage
git rm --cached <file>                              # Untrack file without deleting
git mv <old> <new>                                  # Rename/move file
git clean -fd                                       # Remove untracked files

# Branching and Merging
git branch                                          # List branches
git branch <name>                                   # Create branch
git checkout <name>                                 # Switch branch
git switch <name>                                   # Alternative to checkout
git merge <branch>                                  # Merge branch
git mergetool                                       # Launch merge tool
git log --oneline --graph --decorate --all          # Visual history

# Sharing and Updating Projects
git remote -v                                       # List remotes
git remote add origin <url>                         # Add remote
git fetch origin                                    # Fetch changes
git pull                                            # Fetch + merge
git push                                            # Push to remote
git push origin <branch>                            # Push specific branch
git push origin --tags                              # Push tags
git push origin --delete <branch>                   # Delete remote branch

# Inspection and Comparison
git diff                                            # Show unstaged changes
git diff --staged                                   # Show staged changes
git show <commit>                                   # Show commit info
git shortlog                                        # Summarize commits by author
git describe                                        # Human-readable commit description
git blame <file>                                    # Show last change per line
git grep <pattern>                                  # Search repo content

# Debugging
git bisect                                          # Binary search for bug
git log --stat                                      # Show stats of changes
git log -p                                          # Show patches

# Patching & Email
git format-patch <rev>                              # Create patch files
git am <patch>                                      # Apply patch from email
git apply <patch>                                   # Apply patch directly

# External Systems
git svn                                             # Work with Subversion
git p4                                              # Work with Perforce

# Administration
git gc                                              # Garbage collection
git fsck                                            # Integrity check
git reflog                                          # Show branch tip history
git filter-branch                                   # Rewrite history

# Plumbing Commands (low-level)
git cat-file -p <sha>                               # Show object content
git hash-object <file>                              # Hash file
git ls-files                                        # List staged files
git rev-parse <ref>                                 # Get SHA from ref
git show-ref                                        # List all refs

```