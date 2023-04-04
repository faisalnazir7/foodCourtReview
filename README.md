# foodCourtReview

# Environment Variables(.env):
Example:
```
PORT=8000
```

Install
```
$ npm install pg
```
Supporters
node-postgres continued development and support is made possible by the many supporters.

If you or your company would like to sponsor node-postgres stop by github sponsors and sign up or feel free to email me if you want to add your logo to the documentation or discuss higher tiers of sponsorship!

Version compatibility
node-postgres strives to be compatible with all recent lts versions of node & the most recent "stable" version. At the time of this writing node-postgres is compatible with node 8.x, 10.x, 12.x and 14.x To use node >= 14.x you will need to install pg@8.2.x or later due to some internal stream changes on the node 14 branch. Dropping support for an old node lts version will always be considered a breaking change in node-postgres and will be done on major version number changes only, and we will try to keep support for 8.x for as long as reasonably possible.

Getting started
This is the simplest possible way to connect, query, and disconnect with async/await:
```
const { Client } = require('pg')
const client = new Client()
await client.connect()
 
const res = await client.query('SELECT $1::text as message', ['Hello world!'])
console.log(res.rows[0].message) // Hello world!
await client.end()
```
And here's the same thing with callbacks:
```
const { Client } = require('pg')
const client = new Client()
 
client.connect()
 
client.query('SELECT $1::text as message', ['Hello world!'], (err, res) => {
  console.log(err ? err.stack : res.rows[0].message) // Hello World!
  client.end()
})
```
