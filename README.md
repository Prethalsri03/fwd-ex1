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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TCP/IP Protocols Table</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            font-family: Arial, sans-serif;
        }
        th, td {
            border: 1px solid #dddddd;
            text-align: left;
            padding: 10px;
        }
        th {
            background-color: #f2f2f2;
            color: #333333;
        }
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
    </style>
</head>
<body>

    <h2>TCP/IP Protocol Suite</h2>
    <table>
        <thead>
            <tr>
                <th>TCP/IP Layer</th>
                <th>Protocol Name</th>
                <th>Acronym</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td rowspan="6">Application Layer</td>
                <td>Hypertext Transfer Protocol</td>
                <td>HTTP / HTTPS</td>
                <td>Used for transferring web pages securely or insecurely on the World Wide Web.</td>
            </tr>
            <tr>
                <td>File Transfer Protocol</td>
                <td>FTP</td>
                <td>Used for transferring files between a client and a server.</td>
            </tr>
            <tr>
                <td>Domain Name System</td>
                <td>DNS</td>
                <td>Translates human-readable domain names into numeric IP addresses.</td>
            </tr>
            <tr>
                <td>Simple Mail Transfer Protocol</td>
                <td>SMTP</td>
                <td>Used for sending and routing electronic mail (email).</td>
            </tr>
            <tr>
                <td>Dynamic Host Configuration Protocol</td>
                <td>DHCP</td>
                <td>Automatically assigns IP addresses to devices on a network.</td>
            </tr>
            <tr>
                <td>Simple Network Management Protocol</td>
                <td>SNMP</td>
                <td>Used for monitoring and managing network devices.</td>
            </tr>
            <tr>
                <td rowspan="2">Transport Layer</td>
                <td>Transmission Control Protocol</td>
                <td>TCP</td>
                <td>Provides reliable, connection-oriented data delivery.</td>
            </tr>
            <tr>
                <td>User Datagram Protocol</td>
                <td>UDP</td>
                <td>Provides lightweight, connectionless, fast data delivery.</td>
            </tr>
            <tr>
                <td rowspan="4">Internet Layer</td>
                <td>Internet Protocol (v4 / v6)</td>
                <td>IP</td>
                <td>Routes packets across interconnected networks using unique addresses.</td>
            </tr>
            <tr>
                <td>Internet Control Message Protocol</td>
                <td>ICMP</td>
                <td>Used for network diagnostics, error reporting, and ping tools.</td>
            </tr>
            <tr>
                <td>Address Resolution Protocol</td>
                <td>ARP</td>
                <td>Maps IP addresses to physical hardware (MAC) addresses.</td>
            </tr>
            <tr>
                <td>Routing Information Protocol</td>
                <td>RIP</td>
                <td>A dynamic routing protocol used to find the best path for data.</td>
            </tr>
            <tr>
                <td rowspan="2">Network Access Layer</td>
                <td>Ethernet</td>
                <td>—</td>
                <td>Defines wired LAN cabling and data frame transmissions.</td>
            </tr>
            <tr>
                <td>Point-to-Point Protocol</td>
                <td>PPP</td>
                <td>Used to establish a direct connection between two networking nodes.</td>
            </tr>
        </tbody>
    </table>

</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~

## OUTPUT:

![alt text](<Screenshot 2026-11-24 105718.png>)
![alt text](<Screenshot 2026-11-24 105734.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

