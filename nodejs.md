
# Node TDD: Test Driven Development

Plugin in vscode NODE TDD, prashaantt.node-tdd

### NW JS with Node.js

https://github.com/nwjs/nw.js/issues/2066

Note the usage of 'main' with server address and 'node-main'


Yep, it's possible. Trivial example:

``` js
package.json
{
  "name": "nw-server-example",
  "main": "http://127.0.0.1:9000",
  "node-main": "server.js"
}
server.js
#!/usr/bin/env node

require('http').createServer(function(req, res) {
  res.writeHead(200, {'content-type': 'text/html'});
  res.end('<h1>sup</h1>');
}).listen(9000, '127.0.0.1');


# Connection
## Trust 

https://superuser.com/questions/582624/how-to-access-nodejs-server-on-lan

### Method 1: 
First, you need to add C:\Program Files (x86)\node to the list of trusted applications in your firewall.

### Method 2: 
Doing following worked for me on a windows PC. Try this : open

Control Panel\System and Security\Windows Defender Firewall\Allowed apps

Next look for node.js in the list and click change settings > Make sure private access is checked and then click ok.

### Method 3:
Rather than doing all the configurations (Setting firewall, forwarding port etc) I used localtunnel which is an utility for exposing local node server over Internet. You can use it for development,testing,sharing purpose, just don't use it for production.

First you have to install localtunnel as follows:
```console
$npm install -g localtunnel
```
After that configure your node app such that your node server should be running on localhost. For ex:
```javascript
server.listen(3000, function () {
console.log('Listening to port:  ' + port);
});
```
Note down your_port which in my case was 3000, and start your node server.

Open another terminal and type following command for running localtunnel.

```console
$lt --port 3000
```
After this , in terminal you will get an URL which you can use it for development/testing purpose. This URL will be available on Internet so you can share it with others too. As long as your localtunnel is running, others can access your local node server.

For more configuration options/help you can go through documentation: https://www.npmjs.com/package/localtunnel

### Method 3 tested okay:
Test tunnel method and was able to send a image from Device to PC server.

```console
KK@MINGW64 /c/prj/nodejs/flutter_node/server
$ node index.js
[Object: null prototype] { WLAN: [ '192.168.0.20' ] }
Started server: http://192.168.0.20:3000/upload


Received fileimage_picker5837641810884788501.jpg
```
Note down the port and give the same port during the creation of tunnel.

```console
KK@MINGW64 /c/prj/nodejs/flutter_node/server
$ ./node_modules/localtunnel/bin/lt.js --port 3000
your url is: https://horrible-warthog-78.loca.lt
```

Send an image/file from client using url:
<pre>
https://horrible-warthog-78.loca.lt/upload
</pre>

File received at server side. console log:

```console
KK@MINGW64 /c/prj/nodejs/flutter_node/server
$ node index.js
[Object: null prototype] { WLAN: [ '192.168.0.20' ] }
Started server: http://192.168.0.20:3000/upload


Received fileimage_picker5837641810884788501.jpg
```

```Console
KK@MINGW64 /c/prj/nodejs/flutter_node/server
$ ls uploads/
image_picker5837641810884788501.jpg
```
The flle is saved in folder 'uploads'.

How localtunnel works: https://stackoverflow.com/questions/53170115/how-localtunnel-works-under-the-hood/53180742#53180742

Here is a diagram of all he services involved in localtunnel, grouped by host.
```java
       localhost:             [localtunnel client]  --- [HTTP client] --- [your server]
                               |                |  
                               |                | 
localtunnel host:      [express server] --- [TCP server]
                                                    |
                                                    |
   internet user:                                 [app]
```  
Basically when you type lt --port 8000 in your console, it launches the localtunnel client. This connects to the express server located in the cloud. This express server gives you back the address where your app should connect. Then it launches the tcp server that listens for connections from your app. The tcp server also opens 10 sockets with the localtunnel client, for sending data. When a connection comes from the app, the tcp server sends the data to the localtunnel client on one of the 10 sockets. The data is then piped to a local http client that issues the request to your server.

### Socket tunnel

To read: https://ericbarch.com/post/sockettunnel/

## Socket TCP/UDP

https://gist.github.com/tedmiston/5935757

```js
var net = require('net');

var server = net.createServer(function(socket) {
	socket.write('Echo server\r\n');
	socket.pipe(socket);
});

server.listen(1337, '127.0.0.1');
/* Command line client
$ netcat 127.0.0.1 1337
*/
var net = require('net');

var client = new net.Socket();
client.connect(1337, '127.0.0.1', function() {
	console.log('Connected');
	client.write('Hello, server! Love, Client.');
});

client.on('data', function(data) {
	console.log('Received: ' + data);
	client.destroy(); // kill client after server's response
});

client.on('close', function() {
	console.log('Connection closed');
});

```
