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
<body>
  <h1 style="color: rgba(82, 241, 14, 0.843);">TCP/IP Protocol Suite</h1>
  <p style="font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;font-size:large">The TCP/IP (Transmission Control Protocol/Internet Protocol) suite is a collection of communication protocols used to connect devices over the internet and other networks. It is the foundational model for network communication, providing the rules for how data should be addressed, transmitted, and received. </p>
  <h2>Application Layer</h2>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol>HTTPS/HTTP</ol>
  <ol>SMTP</ol>
  <ol>FTP</ol>
  <ol>DNS</ol>
  <h3>Transport Layer</h3>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol>Transmission Control Protocol(TCP)</ol>
  <ol>User Datagram Protocol(UDP)</ol>
  <h4>Internet Layer</h4>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol>Internet Protocol(IP)</ol>
  <ol>Address Resolution Protocol(ARP)</ol>
  <h5>Network Access Layer</h5>
  <p style="font-size: large;font-weight:bold">Protocol:</p>
  <ol>Data-link Protocol</ol>
  <ol>Physical-link Protocol</ol>
  <p style="font-size: large;font-weight:bold">e.g:Ethernet and WI-FI</p>

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
![alt text](<Screenshot (5).png>)
![alt text](<Screenshot (6).png>)

![alt text](<Screenshot (3).png>)



# RESULT:
The program for implementing simple webserver is executed successfully.
