# Git Aliases Cheatsheet


#### Following aliases can be added to `.gitconfig` in your home directory: 

```
[alias]

# Oneline Log format
  ll = log --oneline

# Oneline Pretty Log Format
  l = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short

# Log (filtered by author) in the above format
  la = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short --author

# Status
  s = status
  st = status -s

# Add Files to staging
  a = add
  ap = add -p

# Diff changes
  d = diff
  ds = diff --stat
  dc = diff --cached

# Commit staged files
  c = commit --verbose
  ca = commit -a --verbose
  cm = commit -m
  cam = commit -a -m
  m = commit --amend --verbose


# List branches (sorted by last modified)
  b = "!git for-each-ref --sort='-authordate' --format='%(authordate)%09%(objectname:short)%09%(refname)' refs/heads | sed -e 's-refs/heads/--'"
  # BE CAUTIOUS - Delete a local branch
  bd = branch -D

# Checkout to branch / Create branch
  co = checkout
  cob = checkout -b

# git please =  --force-with-lease (checks your local copy of the ref is up-to-date before overwriting it)
  please = push --force-with-lease

# BE CAUTIOUS - Reset Hard
  rh = reset --hard HEAD


# List Aliases
  # For Windows
  # a = !git config --list | findstr "alias"
  # For Linux / Mac
  a = "!git config -l | grep alias | cut -c 7-"



# SETTINGS 

# Specify a global .gitignore
[core]
  excludesfile = ~/.gitignore


# Add colors
[color]
  ui = true
  diff = auto

# Avoid confusing merge commits with autorebase
[branch]
  autosetuprebase = always

# Push to the current branch by default
[push]
  default = current

# Remove usage hints
[advice]
  statusHints = false

# Show exact diff details instead of using a and b notation
[diff]
  mnemonicprefix = true


```
