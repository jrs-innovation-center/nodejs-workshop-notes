# Stream all the things

* What are Streams?
* filed

> smallest static streaming file server

```
http.createServer(function (req, resp) {
  req.pipe(filed(req.url)).pipe(resp)
})
```

* Get Data from CouchDB

`npm install request --save`


https://github.com/twilson63/cms/blob/master/db/server.js#L27




---

* [Exercises](exercises)
* [Index](../)
