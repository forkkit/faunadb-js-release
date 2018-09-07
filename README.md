# FaunaDB Javascript Driver - Browser Release

FaunaDB Javascript Driver packaged for the browser.

Please, check https://github.com/fauna/faunadb-js for more information.

## Install

### Bower

`bower install faunadb`

### CDN

```html
<script src="//cdn.jsdelivr.net/faunadb/2.5.1/faunadb.js"></script>
```

The minified version is also available:

```html
<script src="//cdn.jsdelivr.net/faunadb/2.5.1/faunadb-min.js"></script>
```

### Usage

Here is [a JSFiddle of the same content.](https://jsfiddle.net/9kpwrL0u/3/)
Replace `CHANGE-database-secret` with your database secret to run.

```js
var q = faunadb.query, client = new faunadb.Client({
  secret: 'CHANGE-database-secret'
 });

client.query(q.Paginate(q.Ref("indexes"))).then(function(result) {
  result.data.forEach(function(index) {
    var p = document.createElement("p");
    p.innerText = index.value;
    document.body.appendChild(p);
  });
});
```
