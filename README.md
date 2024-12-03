# gitNotes

##  git push origin head will auto set up origin branch while git push will trigger an error if origin branch does not exist
`git push`: Pushes to the current branch’s upstream if it's already set up (default origin branch).
- If not upstream branch is set up, there is will be error in the terminal.

`git push origin HEAD`: Pushes the current branch (HEAD) explicitly to the origin remote, regardless of whether an upstream is already set.
- git push to origin branch (origin) from current working branch (HEAD)
- `HEAD`: Refers to the current commit on your currently checked-out branch, no matter what its name is.
- So explicitly, push to origin branch (local checkouted branch -> remote origin branch), from current branch commits
- Git will push your local feature-x branch to origin. If origin doesn't already have a feature-x branch, Git will create origin/feature-x automatically.

## Except for .gitignore, are there any other ways to ignore file update
git update-index: This command modifies the Git index (also called the staging area). It's used for low-level operations, such as marking certain files in a particular way or controlling how Git tracks changes in the working directory.

--skip-worktree: This flag tells Git to ignore future changes to the specified file in the working directory. When a file is marked as "skip-worktree", Git assumes the file is not supposed to be modified or committed in future changes. It effectively "freezes" that file from being tracked by Git for any changes, even though it's still part of the repository. This is useful when you have local configuration files (e.g., credentials or environment-specific settings) that you don’t want to accidentally commit but still need them for local development.
```
git update-index --skip-worktree <filePath>
```

Undoing --skip-worktree: If you later want Git to track the file again, you can undo the --skip-worktree command by running:
```
git update-index --no-skip-worktree <file>
```





# Check current branch in git
git branch --show-current


-u is the same as - - set-upstream
In Git, the -u option is used with the git push command. It stands for --set-upstream and its purpose is to set the remote branch that the local branch will track. This means that the local branch will have a corresponding remote branch, and future git push and git pull commands will know which remote branch to push to and pull from by default.
git push -u origin <branch-name>
…or create a new repository on the command line
echo "# randomDocs" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:Jerrysuper123/randomDocs.git
git push -u origin main








# The command git fetch --all in Git is used to retrieve all changes from all remote repositories.
Here's what it does:
Fetch: It contacts all remote repositories associated with your local repository and fetches any new branches or commits from them.
Updates remote-tracking branches: After fetching, Git updates the remote-tracking branches (such as origin/master, origin/develop, etc.) in your local repository to reflect any changes in the remote repositories.




Fetch the latest changes from the remote repository: 
Use git fetch to fetch the latest changes from the remote repository. This will update your local copy of the remote branches without merging them into your current branch.
bash
git fetch origin


Reset your local branch to match the remote branch: Use git reset --hard to reset your local branch to match the state of the corresponding remote branch. This will discard any local changes that you have not committed and make your local branch identical to the remote branch.
bash
git reset --hard origin/<branch_name>
Replace <branch_name> with the name of the branch you want to reset to match the remote repository. For example, if you're working on the main branch, you would use origin/main.
What is the difference between fetch –all and fetch origin?
git fetch --all and git fetch origin both perform Git fetch operations, but they have different scopes:
git fetch --all:
This command fetches changes from all remote repositories associated with your local repository.
It updates remote-tracking branches for all remote repositories.
It's useful when you have multiple remotes and want to fetch changes from all of them.
git fetch origin:
This command fetches changes only from the remote repository named "origin".
It updates remote-tracking branches for the "origin" remote repository only.
It's useful when you primarily work with a single remote repository named "origin".
In summary, git fetch --all fetches changes from all remote repositories, while git fetch origin fetches changes from a specific remote repository named "origin". Use git fetch --all when you have multiple remotes, and use git fetch origin when you're only interested in updates from the "origin" remote.


Git stash (stack somewhere temporarily)
git stash: Stash changes in the working directory that are not ready to be committed.
git stash push -m "message": Stash changes with a custom message describing the stash.
git stash apply: Apply the most recently stashed changes to the working directory. The stash will still be available after applying.
git stash apply stash@{n}: Apply a specific stash by its index number (n).
git stash list: List all stashes along with their index numbers and descriptions.
git stash show: Show the changes in the most recently stashed entry.
git stash show -p: Show the patch representing the changes in the most recently stashed entry.
git stash pop: Apply the most recently stashed changes to the working directory and remove the stash from the stash list.
git stash drop: Discard the most recently stashed changes.
git stash drop stash@{n}: Discard a specific stash by its index number (n).
git stash clear: Remove all stashed entries.



Git squash
Git rebase -i head~3
Merge conflict
This pull request has conflicts.
You must resolve the conflicts by manually merging master into this branch. After the conflicts are resolved you will be able to merge the pull requ	est.
Step 1: Checkout the source branch and merge in the changes from the target branch. Resolve conflicts.
git checkout feature-jms-9.0 
git pull origin master
Step 2: After the merge conflicts are resolved, stage the changes accordingly, commit the changes and push.
git commit 
git push origin HEAD
Step 3: Merge the updated pull request.


Git diff
To use git diff to see the differences between two commits, you need to provide the commit hashes or references for the two commits you want to compare. The basic syntax for git diff between two commits is:
bash
Copy code
git diff <commit1> <commit2>

Replace <commit1> and <commit2> with the actual commit hashes, branch names, or other commit references.

How to Force git pull
To force “git pull” to overwrite local files, you can use the following command:
⚠ This code is experimental content and was generated by AI. Please refer to this code as experimental only since we cannot currently guarantee its validity
git fetch --all
git reset --hard origin/<branch-name>

Let’s break down this command:
git fetch --all: This command fetches the latest changes from the remote repository. The “–all” option ensures that all branches are fetched, not just the current branch.
git reset --hard origin/<branch-name>: This command resets the current branch to the state of the remote repository. The “–hard” option overwrites local changes and the “origin/” specifies the remote branch that you want to pull changes from.
After running these commands, your local branch will be updated to match the state of the remote repository, and any local changes will be overwritten. It is worth noting that this is a destructive operation, and any local changes that have not been committed will be lost.

git reset --hard origin/AJ-15226


git fetch --all
git reset --hard origin/setup

How to revert git rebase master
git reset --hard ORIG_HEAD

How to connect local project to remote server
//below create a .git file, this file tracks all changes and help to sync with origin 
Git init

//this is just to add a reference, then u “git push -u origin master” to push up stream to a master branch
Git remote add origin url




