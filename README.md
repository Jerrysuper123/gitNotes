# gitNotes

git push: Pushes to the current branch’s upstream if it's already set up.
git push origin HEAD: Pushes the current branch (HEAD) explicitly to the origin remote, regardless of whether an upstream is already set.
- git push to origin branch (origin) from current working branch (HEAD)

git push origin HEAD: Pushes the current branch to the remote origin. If the branch doesn't exist on the remote, it will create it but won't set the upstream automatically.
git push -u origin HEAD: Pushes the current branch to the remote origin and sets the upstream tracking branch, ensuring future git push/git pull works without extra arguments.
