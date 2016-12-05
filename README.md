# Unit-11

Problem 1

Node.js uses a module architecture to simplify the creation of complex applicaions. With Node.js everything that would normally block the thread is instead executed in the background. Node.js is only an environment - meaning that you have to do everything yourself. There is not a default HTTP server, or any server for that matter.


Problem 3

var http = require('http');
var fs = require('fs');

var server = http.createServer(function(request,response) {

    fs.readFile('my_pic.jpg', function(error, file) {
        response.writeHead(200, {'content-type':'text/html'});
        response.write('<p>'Hello World, my name is Darin Glenn'!</p>');

        response.writeHead(200, {'content-type':'image/jpg'});
        response.write(file, 'image');

        response.end();
    });

});

var port = process.env.PORT || 8001;

server.listen(port, function() {
    console.log('Listening on port ' + port);
});
