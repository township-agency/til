# Invalidating files in Cloudfront via Command Line
## Use Case: Deploying Serverless Frontend Applications

We build a lot of front end stuff. It can be a really smart idea to use static hosting like S3 to serve these files, instead of a dedicated server. If you want, you can even use Cloudfront as your CDN!

When you do this, you usually serve a single `index.html` file. When the app is rebuilt/updated, our build tools will hash any assets we have, breaking any cache we had, and serving the most recent version from our updated code.

Problem is, we can't hash the `index.html` file like this, _but_ we do need the updated file, because it references the updated hashed assets. We need a way to tell Cloudfront to use the most recent version of `index.html`, not a cached version. 

Cloudfront provides validations, a certain amount per month are included, then you need to start paying. Lucky for us, we only have one file we need to invalidate. One of the more graceful solutions I found was to just invalidate this single file from the command line in our CI's server configuration.

In this case, we're using Semaphore CI, which is running commands like `yarn`, `yarn build`, etc. Once it's done building, I just run this little command:

```
aws cloudfront create-invalidation --distribution-id $CLOUDFRONT_DIST --paths /index.html
```

Where `$CLOUDFRONT_DIST` is an `env` variable set in another file. 

Now we get a fresh copy of our `index.html` and everything is right in the world!
