## NodeJS Basics

### Install

http://nodejs.org

### JavaScript on the Server

<div class="tonic">
  <pre>
console.log('Hello World ')
  </pre>
</div>


### NodeJS file

index.js

```
console.log('hello world')
```

```
node index.js
```

### Async API (callbacks)

```
const fs = require('fs')

fs.readFile('./index.js', 'utf-8', (err, data) => {
  if (err) { return console.log(err) }
  console.log(data)
})
```

> Every Api in NodeJS is callback based

https://nodejs.org/en/docs/

### Event Emitter

EventEmitter allows you to take any Object and enable it to emit events
as well as allow your program to listen to events. This pattern allows
for loose coupling inside your application, but it is a synchronous api.

<div class="tonic">
  <pre>
const EventEmitter = require('events')

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter()

myEmitter.on('echo', (saying) => console.log(saying))

myEmitter.emit('echo', 'Hello')

  </pre>
</div>


## Streams

```
const fs = require('fs')

fs.createReadStream('./index.js', 'utf-8')
  .pipe(process.stdout)
```

Pull-Streams

https://pull-stream.github.io/


---

* [Exercises](exercises)
* [Index](../)
