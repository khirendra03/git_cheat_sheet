# cheat sheet
Some commonly used git commands

## Basic Git Concepts
- **main:** default development branch
- **origin:** default upstream repo
- **HEAD:** current branch
- **HEAD^:** parent of HEAD
- **HEAD~4:** great-great grandparent of HEAD

## Start a Project
      git init <directory>

- Download a remote repo

      git clone <repo url>

## adding/pushing Changes
- Add a file to staging
      
      git add <file>

- Add all files to staging
      
      git add .

- Commit all staged files to git
      
      git commit -m "commit message"

- Add all changes made to tracked files & commit

      git commit -am "commit message"

## Branches
- List all local branches

      git branch
  `-r` flag to show all remote branches. 
   `-a` flag for all branches

- Create a new branch


      git branch <new-branch>


- Switch to a branch and update the working directory

       git checkout <branch>

- Create a new branch and switch to it

        git checkout -b <newbranch>

- Delete a merged branch

        git branch -d <branch>

- Delete a branch, whether merged or not

        git branch -D <branch>

- Add a tag to current commit

        git tag <tag-name>

## Merging
- Merge branch `a` into branch `b`. 
  Add `--no-ff` option for no-fast-forward merge

        git checkout b
        git merge a

- Merge & squash all commits into one new commit
     
        git merge --squash a

## Rebasing
- rewrite commits from one branch onto another branch. 
  Rebase branch-1 branch onto main branch

       git checkout branch-1
       git rebase main

- Interactively clean up a branches commits before rebasing onto main branch

       git rebase -i main

- Interactively rebase the last 3 commits on current branch

       git rebase -i Head~3

## Undoing Things
- Move/ename a file and stage move

      git mv <existing_path> <new_path>

- Remove a file from working directory and staging area then stage the removal

      git rm <file>

- Remove from staging area only

      git rm --cached <file>

- View a previous commit

      git checkout <commit_ID>

- Reverting the changes from a specified commit

      git revert <commit_ID>

- Reset your index and working directory to the state of your last commit.
  - `--soft`: Tells Git to reset HEAD to another commit, 
              so index and the working directory will not be altered in any way. 
              All of the files changed between the original HEAD and the commit will be staged.
  - `--mixed`: Just like the soft, this will reset HEAD to another commit. 
               It will also reset the index to match it while working directory will not be touched. 
               All the changes will stay in the working directory and appear as modified, but not staged. 
              >The main difference between `--mixed` and `--soft` is whether or not your index is also modified.
  - `--hard`: This resets everything - it resets HEAD back to another commit, 
              resets the index to match it, and resets the working directory to match it as well.

        git reset <commit_ID>
