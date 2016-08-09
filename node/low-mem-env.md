# Using low-memory flag in node

If you need to reproduce a memory error locally, where your environment is very different from staging or production servers, it turns out that node has some useful tools in doing so! For example, my local setup does not have the database size to recreate a memory issue encountered on a production server, but I can simulate a low memory environment using a flag to limit the amount of memory available to node: 

```
node --max_old_space_size=128 index.js
```

This will limit us to 128 Mb when running `index.js` in my npm start script. You can increase or even decrease this value further, or configure additional limitations using some of the [other flags available for node](http://erikcorry.blogspot.ru/2012/11/memory-management-flags-in-v8.html).
