# Shortcut around `--save-exact` when managing NPM Dependencies

When you're doing web-app dev, you often want to save the version of the dependency you're using, so everyone (including your servers) are using the same stuff.

When you do `--save` or `--save-dev` you don't always get the right version (you'll get a `^`). So typically, you'd have to use a `--save-exact` if you did in fact want to save... exact.

If you create a `.npmrc` file, you can add this preference:

```
save-exact=true
```

So now when you do `npm install express` you'll get the exact version saved in `package.json`

[More cases here.](https://gist.github.com/kentcdodds/5352dcce1c62630fe9d0)
