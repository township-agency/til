# Opening and Booting Multiple Repositories in Terminal, Using ZSH

As the technological purveyors that we are, we often rely on many microservices in order to create a whole project. In the simplest form, this usually means an REST API that lives in a repository, as well as a separate frontend application that's built on the fly.

This is great! Yay microservices (and serving static assets over CDNs :)! But sometimes it can be a bit cumbersumb to really dig in to a project when it takes ~10 minutes just to `cd` and get things moving.

This is a quick script/alias (using ZSH) that will `cd` into multiple repos, open new tabs in Terminal (in my case iTerm 2) and start the codebases with the commands you provide. There's room for improvement here, but it'll get the job done. 

In `.zshrc`, ensure you have `ttab` installed globally with `npm install -g ttab`

```
openCleverstack() {
  ttab -G eval 'cd ~/Documents/Code/cs-api && yarn debug'
  ttab -G eval 'cd ~/Documents/Code/cs-auth && yarn debug'
  ttab -G eval 'cd ~/Documents/Code/cs-vue && yarn dev'
}
alias cs="openCleverstack"
```

This command will open the three codebases I need and start 'em up. Just type:

```
$ cs
```

and you'll see three tabs open, all starting up with your commands :)
