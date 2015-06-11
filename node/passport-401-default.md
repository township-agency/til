# Passport is not dumb.

Passport is an authentication package that integrates nicely with the Express server framework. Because most of its examples
and documentation are geared toward Express's more traditional webserver structure, I used that structure to build out APIs like so:

```coffeescript
app.put '/api/admin/shows/:show_id/image', passport.authenticate('localapikey', failureRedirect: '/api/unauthorized'),
    AdminApiController.upload_show_image
```

What the above does is redirect the API request to '/api/unauthorized' if the auth failed. That route is then directed to an API
method that returns a 401. Sometimes I'm real dumb.

```coffeescript
app.put '/api/admin/shows/:show_id/image', passport.authenticate('localapikey'),
    AdminApiController.upload_show_image
```

Removing the failureRedirect lets Passport do its default bits, which is obviously just return a 401. Thanks Passport, you're the best.
