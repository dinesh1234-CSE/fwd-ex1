# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<table border="1">
    <tr>
        <th>Layer</th>
        <th>Protocols</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>Application Layer</td>
        <td>HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, TELNET, SNMP</td>
        <td>Handles high-level protocols, including web browsing, email, and remote access.</td>
    </tr>
    <tr>
        <td>Transport Layer</td>
        <td>TCP, UDP</td>
        <td>Provides end-to-end communication and error recovery.</td>
    </tr>
    <tr>
        <td>Internet Layer</td>
        <td>IP, ICMP, ARP, IGMP</td>
        <td>Handles addressing, routing, and error reporting.</td>
    </tr>
    <tr>
        <td>Network Access Layer</td>
        <td>Ethernet, Wi-Fi, PPP, SLIP</td>
        <td>Defines how data is physically transmitted over the network.</td>
    </tr>
</table>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![Screenshot (3)](https://github.com/user-attachments/assets/7a463ce4-5532-4e1b-8299-f5f516d52b58)
![Screenshot (2)](https://github.com/user-attachments/assets/62505852-cb37-4668-9573-9785a32bb400)

## RESULT:
The program for implementing simple webserver is executed successfully.


