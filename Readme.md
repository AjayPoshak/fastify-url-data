# fastify-url-data

A plugin for [Fastify](https://fastify.io/) that adds support for getting raw
URL information from the request.

## Example

```js
const fastify = require('fastify')()

fastify.register(require('fastify-url-data'), (err) => {
  if (err) throw err
})

fastify.get('/foo', (req, reply) => {
  const urlData = req.urlData()
  req.log.info(urlData.path) // '/foo'
  req.log.info(urlData.query) // 'a=b&c=d'
  req.log.info(urlData.host) // '127.0.0.1'
  req.log.info(urlData.port) // 8080

  reply.send({hello: 'world'})
})

// GET: 'http://127.0.0.1:8080/foo?a=b&c=d
```

## License

[MIT License](http://jsumners.mit-license.org/)
