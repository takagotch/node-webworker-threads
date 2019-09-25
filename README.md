### node-webworker-threads
---
https://github.com/audreyt/node-webworker-threads


```js
// test/test08_sigkill_leaks.js
var Thread= require('../');

function cb (e,m) {
  this.destroy();
  console.log('['+this.id+'].destory()');
  again();
}

function again () {
  Thread.create().eval('0', cb);
}

var i= +process.argv[2] || 1;
console.log('Using '+ i+ ' threads');

while (i--) {
  again();
}

process.on('exit', function () {
  console.log("process.on('exit') -> BYE!");
});
```

```
```

```
```


