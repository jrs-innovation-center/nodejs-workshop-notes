# http - (Express/Request)

* http server

```
const http = require('http')

const server = http.createServer((req, res) => {
  res.end('Hello World')
})

server.listen(3000)
console.log('server listening on port 3000')
```

* serve html

```
const http = require('http')

const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/html'})
  res.end('<h1>Hello World</h1>')
})

server.listen(3000)
console.log('server listening on port 3000')
```

* http clientRequest

https://nodejs.org/dist/latest-v7.x/docs/api/http.html#http_class_http_clientrequest

> Userland makes http clients easy

`npm install request`

```
const request = require('request')

request('https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1', {
  json: true
}, (err, response, body) => {
  if (err) { return console.log(err) }
  console.log(body)
})
```

### RESTful API's (ExpressJS)

`npm install express --save`

```
const express = require('express')
const app = express()

app.get('/', (req, res) => {
  res.send('Hello World')
})

app.listen(3000)
```

Basic Routing

https://expressjs.com/en/starter/basic-routing.html


Handling url params

```
app.post('/docs/:id', (req, res) => {
  console.log(req.params.id)
  res.send('Ticket number ' + req.params.id)  
})
```

Sending Errors

```
app.get('/foo', (req, res) => {
  res.status(500).send('Application Error')
})
```

Handling body

`npm install body-parser`

```
const bodyParser = require('body-parser')

app.post('/docs', bodyParser.json(), (req, res) => {
  console.log(req.body)
  res.send({ok: true})
})
```

Middleware

https://expressjs.com/en/guide/using-middleware.html

https://expressjs.com/en/guide/writing-middleware.html

```
function (req, res, next) {
  //... doStuff
  next()
}
```

Security

https://expressjs.com/en/advanced/best-practice-security.html

Cors

https://www.npmjs.com/package/cors

---

Other Mentions

* micro - https://github.com/zeit/micro
* nextjs - https://zeit.co/blog/next
* hapi - https://hapijs.com/
* restify - http://restify.com/

---

* [Exercises](exercises)
* [Index](../)
