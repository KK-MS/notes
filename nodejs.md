
# Node TDD: Test Driven Development

Plugin in vscode NODE TDD, prashaantt.node-tdd

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
Krishnakumar.Mayanna@IFMNB09 MINGW64 /c/prj/nodejs/flutter_node/server
$ node index.js
[Object: null prototype] { WLAN: [ '192.168.0.20' ] }
Started server: http://192.168.0.20:3000/upload


Received fileimage_picker5837641810884788501.jpg
```
Note down the port and give the same port during the creation of tunnel.

```console
Krishnakumar.Mayanna@IFMNB09 MINGW64 /c/prj/nodejs/flutter_node/server
$ ./node_modules/localtunnel/bin/lt.js --port 3000
your url is: https://horrible-warthog-78.loca.lt
```

Send an image/file from client using url:
<pre>
https://horrible-warthog-78.loca.lt/upload
<\pre>

File received at server side. console log:

```console
Krishnakumar.Mayanna@IFMNB09 MINGW64 /c/prj/nodejs/flutter_node/server
$ node index.js
[Object: null prototype] { WLAN: [ '192.168.0.20' ] }
Started server: http://192.168.0.20:3000/upload


Received fileimage_picker5837641810884788501.jpg
```

```Console
Krishnakumar.Mayanna@IFMNB09 MINGW64 /c/prj/nodejs/flutter_node/server
$ ls uploads/
image_picker5837641810884788501.jpg
```
The flle is saved in folder 'uploads'.

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
