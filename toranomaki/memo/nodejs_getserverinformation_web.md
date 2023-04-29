
```
var http = require('http');
	var server = http.createServer(function(req, res) {
		// Export to console.
		console.log("URL: " + req.url);
		console.log("Method: " + req.method);
		console.log("Header[Content-Type]: " + req.headers['content-type']);
		// Export to Web Browser.
		res.write("UrL " + req.url);
		res.write("\nMethod: " + req.method);
		res.write("\nHeader[Content-Type]: " + req.headers['content-type']);
		res.end();
	}
).listen(8080);
// # node <FileName>
//
// Example:
// # node app.js
```