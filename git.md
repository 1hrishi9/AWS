### What is git ?
>Git is a version control system that allows you to track changes to files and folders over time. It is distributed, meaning that the entire codebase and history is available on every developer's computer, which allows for easy branching and merging.
---
---
### what is branching in git?
>Branching means you diverge from the main line of development and continue to do work without messing with that main line. In many VCS tools, this is a somewhat expensive process, often requiring you to create a new copy of your source code directory, which can take a long time for large projects.
---
---
### What is the difference between git and github?
>Git is a version control system that lets you manage and keep track of your source code history. GitHub is a cloud-based hosting service that lets you manage Git repositories. If you have open-source projects that use Git, then GitHub is designed to help you better manage them.
---
---
### What is the difference between git and svn?
>Git is a distributed version control system, whereas SVN is a centralized version control system. This means that Git does not just have a single central server that contains all the versioned files, but the full copy of the repository is present in every developer's computer.  
---
---
### What is the difference between git and bitbucket?
>Bitbucket is a web-based version control repository hosting service owned by Atlassian, for source code and development projects that use either Mercurial or Git revision control systems. Bitbucket offers both commercial plans and free accounts.
---
---
### What is the difference between git and tfs?
>Git is a distributed version control system, whereas TFS is a centralized version control system. This means that Git does not just have a single central server that contains all the versioned files, but the full copy of the repository is present in every developer's computer.
---
---
### list of git command and their defination
-**git init**: Create a new local repository
-**git clone**: Clone a repository into a new directory
-**git add**: Add file contents to the index
-**git commit**: Record changes to the repository
-**git diff**: Show changes between commits, commit and working tree, etc
-**git reset**: Reset current HEAD to the specified state
-**git status**: Show the working tree status
-**git rm**: Remove files from the working tree and from the index
-**git log**: Show commit logs
-**git show**: Show various types of objects
-**git tag**: Create, list, delete or verify a tag object signed with GPG
-**git branch**: List, create, or delete branches
-**git checkout**: Switch branches or restore working tree files
-**git merge**: Join two or more development histories together
-**git remote**: Manage set of tracked repositories
-**git push**: Update remote refs along with associated objects
-**git pull**: Fetch from and integrate with another repository or a local branch
-**git stash**: Stash the changes in a dirty working directory away
-**git fetch**: Download objects and refs from another repository
-**git grep**: Print lines matching a pattern

---
---

```

## git reset
 will move HEAD and the current branch back to wherever you specify, abandoning any commits that may be left behind. This is useful to undo a commit that you no longer need.

This command is normally used with one of three flags: "--soft", "--mixed", and "--hard". The soft and mixed flags deal with what to do with the work that was inside the commit after you reset, and you can read about it here. Since this visualization cannot graphically display that work, only the "--hard" flag will work on this site.

The ref "HEAD^" is usually used together with this command. "HEAD^" means "the commit right before HEAD. "HEAD^^" means "two commits before HEAD", and so on.

Note that you must never use git reset to abandon commits that have already been pushed and merged into the origin. This can cause your local repository to become out of sync with the origin. Don't do it unless you really know what you're doing.
[visual representation](https://onlywei.github.io/explain-git-with-d3/#reset)
```