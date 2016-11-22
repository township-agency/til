# NPM Install respects your exported NODE_ENV

Seems obvious right? Of course this has to be true. Here's a real life example:

You're coding before bed one night (would not recommend) and you run `export NODE_ENV=production` because you're a crazy person.
The next morning you pull down a new project, run `npm install`, but several of your dependencies are missing! Where could they be?
Dependencies in `devDependencies` will not be installed because your NODE_ENV is set to production.
