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

```
req.pipe(request({
  method: req.method,
  url: process.env.DB_SERVER + req.url
})).pipe(res)

```

> https://github.com/twilson63/cms/blob/master/db/server.js#L27

### Pull Streams

* http://dominictarr.com/post/149248845122/pull-streams-pull-streams-are-a-very-simple
* https://github.com/dominictarr/pull-stream-examples
* https://github.com/pull-stream/pull-stream-workshop




---

* [Exercises](exercises)
* [Index](../)
