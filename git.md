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



## git reset
 will move HEAD and the current branch back to wherever you specify, abandoning any commits that may be left behind. This is useful to undo a commit that you no longer need.

This command is normally used with one of three flags: "--soft", "--mixed", and "--hard". The soft and mixed flags deal with what to do with the work that was inside the commit after you reset, and you can read about it here. Since this visualization cannot graphically display that work, only the "--hard" flag will work on this site.

The ref "HEAD^" is usually used together with this command. "HEAD^" means "the commit right before HEAD. "HEAD^^" means "two commits before HEAD", and so on.

Note that you must never use git reset to abandon commits that have already been pushed and merged into the origin. This can cause your local repository to become out of sync with the origin. Don't do it unless you really know what you're doing.
[visual representation](https://onlywei.github.io/explain-git-with-d3/#reset)

---
--- 

## git revert
will create a new commit that undoes all of the changes made in a bad commit. This is also useful for undoing a commit that has already been pushed to the origin, but it is not a good idea to use it to undo a commit that has already been pulled into another repository.  
bash
``git revert HEAD``
This will create a new commit that undoes everything that was in the last commit. You can also specify a commit to revert, instead of using HEAD. For example, if you wanted to revert the commit "abc123", you would run:
bash
``git revert abc123``
[visual representation](https://onlywei.github.io/explain-git-with-d3/#revert)

---
---
## git rebase
will move a branch to begin on a commit with a different parent. This can be used to change the parent of a branch, which changes the base of the branch.  
bash
``git rebase master``
This moves the current branch to begin on the tip of the master branch. This should be done in a feature branch, not in master.  

Rebasing will rewrite history - please see the interactive rebase section below for more information about this.
[visual representation](https://onlywei.github.io/explain-git-with-d3/#rebase)

---
---

## git merge   

will combine multiple sequences of commits into one unified history. In the most frequent use cases, git merge is used to combine two branches. The following examples below are demonstrated using git merge master but the examples apply to other branches as well (e.g. git merge <feature_branch>).  

bash
``git merge master``
This command merges the master branch into the current branch, and can be used by both beginners and experts. When you merge, Git will try to auto-merge changes. Unfortunately, this is not always possible and results in conflicts. You are responsible for merging those conflicts manually by editing the files shown by git. After you have edited the files, you need to tell Git that the conflicts have been resolved with:  
bash
``git add <resolved-file>``
You can also use git mergetool, which is a GUI tool to resolve conflicts.  
bash
``git mergetool``
After you are done, you can continue the merge by running:  
bash
``git merge --continue``
If you decide to abort the merge, you can do:
bash
``git merge --abort``
[visual representation](https://onlywei.github.io/explain-git-with-d3/#merge)
---
---
## git fetch  

will download all branches and tags from the repository. It won't, however, merge any of this new data into your working files. Fetch is great for getting a fresh view on all the things that happened in a remote repository.  
bash  

``git fetch origin``

This command will fetch all branches from the repository origin. After fetching, you can see all branches with:  
bash
``git log remotes/origin/master..HEAD``
[visual representation](https://onlywei.github.io/explain-git-with-d3/#fetch)
---
---
## git pull

will download all branches and tags from the repository and then merge one of those branches into your current working branch.  
bash
``git pull origin master``
This command will fetch all branches from the repository origin. After fetching, you can see all branches with:  
bash

``git log remotes/origin/master..HEAD``

[visual representation](https://onlywei.github.io/explain-git-with-d3/#pull)
---

---
## git stash  
will temporarily save your local modifications away and revert the working directory to match the HEAD commit.  

The modifications stashed away by this command can be listed with git stash list, inspected with git stash show, and restored (potentially on top of a different commit) with git stash apply. Calling git stash without any arguments is equivalent to git stash push. A stash is by default listed as "WIP on branchname …​", but you can give a more descriptive message on the command line when you create one.  
bash
``git stash``
This command will stash away your local modifications. You can list your stashes with:  
bash


``git stash list``
To apply one of these changes back on top of your working directory (without losing them), run this command:    
bash
``git stash apply``
[visual representation](https://onlywei.github.io/explain-git-with-d3/#stash)

---
---
## git cherry-pick  

will apply the changes introduced by some existing commits. It is often used to get changes introduced by some existing commits and apply them to another branch. Since it allows to partially cherry-pick a commit by taking only specific files, it can also be used to split a commit into multiple commits.  

bash
``git cherry-pick <commit-hash>``
This command will apply the changes introduced by the commit <commit-hash> to the current branch. You can also specify a range of commits using the notation <start-commit-hash>..<end-commit-hash>. For example, if you wanted to cherry-pick the commits "abc123" and "def456", you would run:  
bash

``git cherry-pick abc123..def456``
[visual representation](https://onlywei.github.io/explain-git-with-d3/#cherry_pick)

---
---

