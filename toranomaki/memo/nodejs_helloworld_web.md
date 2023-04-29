```
var http = require('http');
var server = http.createServer(function(req, res){
	res.write("Hello world\n");
	res.end();
}).listen(8080);
// node <filename>
//
// Example
// # node apps.js
```

