# EX01 Developing a Simple Webserver

# Date:18.09.2025

# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from django.shortcuts import render
from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TCP/IP Protocol Suite</title>
</head>
<body bgcolor="#f000fabc">
  <h1 style="color: rgba(82, 241, 14, 0.843);">TCP/IP Protocol Suite</h1>
  <p style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;font-size:large">The TCP/IP (Transmission Control Protocol/Internet Protocol) suite is a collection of communication protocols used to connect devices over the internet and other networks. It is the foundational model for network communication, providing the rules for how data should be addressed, transmitted, and received. </p>
  <h2 style="color: blueviolet;">Application Layer</h2>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ul type="square">
  <li>HTTPS/HTTP</li>
  <li>SMTP</li>
  <li>FTP</li>
  <li>DNS</li>
  </ul>
  <h3 style="color: brown;">Transport Layer</h3>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ul type="circle">
  <li>Transmission Control Protocol(TCP)</li>
  <li>User Datagram Protocol(UDP)</li>
  </ul>
  <h4 style="color: aqua; font-size:large">Internet Layer</h4>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol type="1" start="1">
  <li>Internet Protocol(IP)</li>
  <li>Address Resolution Protocol(ARP)</li>
  </ol>
  <h5 style="color: chartreuse; font-size:large">Network Access Layer</h5>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol start="1" type="I">
  <li>Data-link Protocol</li>
  <li>Physical-link Protocol</li>
  </ol>
  <p style="font-size: large;font-weight:bold; margin-left:2vw">e.g:Ethernet and WI-FI</p>

</body>
</html>

'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request recieved...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=('',8000)
httpd=HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

# OUTPUT:
![alt text](<Screenshot (7).png>)
![alt text](<Screenshot (8).png>)

![alt text](<Screenshot (3).png>)



# RESULT:
The program for implementing simple webserver is executed successfully.
