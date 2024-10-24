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
