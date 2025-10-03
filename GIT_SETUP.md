# Git Repository Setup Documentation

## Current Configuration

**Current Remote:**
- Origin: `https://github.com/bradtraversy/50projects50days.git`
- This is the original upstream repository from Traversy Media's course

## Connecting to New Repository

### New Repository Details
- **URL**: `https://github.com/VirtualNative/50-web-projects.git`
- **Owner**: VirtualNative
- **Repository Name**: 50-web-projects

### Steps to Change Remote

#### Option 1: Replace Existing Remote (Recommended)

```bash
# Remove the current origin remote
git remote remove origin

# Add your new repository as origin
git remote add origin https://github.com/VirtualNative/50-web-projects.git

# Verify the new remote
git remote -v

# Push to your new repository (first time)
git push -u origin master
```

#### Option 2: Keep Original as Upstream, Add New as Origin

```bash
# Rename current origin to upstream
git remote rename origin upstream

# Add your new repository as origin
git remote add origin https://github.com/VirtualNative/50-web-projects.git

# Verify remotes
git remote -v

# Push to your new repository
git push -u origin master
```

This option allows you to:
- Pull updates from the original course repository: `git pull upstream master`
- Push your changes to your own repository: `git push origin master`

### Verify Configuration

After changing remotes, verify with:
```bash
git remote -v
```

Expected output (Option 1):
```
origin  https://github.com/VirtualNative/50-web-projects.git (fetch)
origin  https://github.com/VirtualNative/50-web-projects.git (push)
```

Expected output (Option 2):
```
origin    https://github.com/VirtualNative/50-web-projects.git (fetch)
origin    https://github.com/VirtualNative/50-web-projects.git (push)
upstream  https://github.com/bradtraversy/50projects50days.git (fetch)
upstream  https://github.com/bradtraversy/50projects50days.git (push)
```

## Current Branch Status

- **Current Branch**: master
- **Recent Commits**:
  - c92b0bc - fix disable other draggings
  - 8109aaf - updated the disclaimer more readable
  - a90f6d3 - Fixed CSS selector issue
  - 9409685 - Simple timer

## Untracked Files

The following directories are currently untracked:
- `.claude/` - Claude Code configuration
- `.specify/` - Project specification and templates

### Recommended .gitignore Additions

Consider adding these to `.gitignore`:
```
# Claude Code
.claude/

# Specify templates (if internal use only)
.specify/
```

Or if you want to version control the documentation setup:
```
# Just ignore local state
.specify/memory/
```

## Initial Push to New Repository

After configuring the remote, push your code:

```bash
# Push all branches and set upstream
git push -u origin master

# Or push all branches
git push -u origin --all

# Push tags if any
git push -u origin --tags
```

## Authentication

If using HTTPS, you may need:
- **Personal Access Token** (PAT) for authentication
- Configure Git credential helper: `git config --global credential.helper store`

If using SSH:
- Ensure SSH keys are set up in your GitHub account
- Use SSH URL: `git@github.com:VirtualNative/50-web-projects.git`

## Next Steps

1. Choose your preferred remote configuration option
2. Execute the commands to change the remote
3. Push your code to the new repository
4. Verify the push was successful by visiting: https://github.com/VirtualNative/50-web-projects

---

*This documentation guides the process of connecting the local repository to the new GitHub remote at VirtualNative/50-web-projects*
