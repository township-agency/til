# Checkout and Track Remote Branch

Need to pull down a remote branch?  On repos where we're practicing Git Flow,
you can `git flow feature track <branch-name>` to let git flow do its magic.

On repos where we're not using git flow, you can `git checkout -b <branch-name>`
but this won't track the branch.  So when you run `git pull` you'll get:

```
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
```

Instead you can run `git checkout -t <branch-name>` to both checkout the remote
branch and track it.
