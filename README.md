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
