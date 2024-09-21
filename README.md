# gitNotes

No significant differencet between git push and git push origin head
`git push`: Pushes to the current branch’s upstream if it's already set up.

`git push origin HEAD`: Pushes the current branch (HEAD) explicitly to the origin remote, regardless of whether an upstream is already set.
- git push to origin branch (origin) from current working branch (HEAD)
- `HEAD`: Refers to the current commit on your currently checked-out branch, no matter what its name is.
- So explicitly, push to origin branch, from current branch commits
