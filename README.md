# gitNotes

##  git push origin head will auto set up origin branch while git push will trigger an error if origin branch does not exist
`git push`: Pushes to the current branch’s upstream if it's already set up (default origin branch).
- If not upstream branch is set up, there is will be error in the terminal.

`git push origin HEAD`: Pushes the current branch (HEAD) explicitly to the origin remote, regardless of whether an upstream is already set.
- git push to origin branch (origin) from current working branch (HEAD)
- `HEAD`: Refers to the current commit on your currently checked-out branch, no matter what its name is.
- So explicitly, push to origin branch (local checkouted branch -> remote origin branch), from current branch commits
- Git will push your local feature-x branch to origin. If origin doesn't already have a feature-x branch, Git will create origin/feature-x automatically.
