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
'''
from django.shortcuts import render
from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Experiment 1</title>
</head>
<body>

    <h1 style="text-align :center;margin-top:12vh;font-weight:bold;" class="">Laptop Configuration Details</h1>
    <p style="text-align: center;margin-top:9vh;font-size:larger;"><strong>* Laptop Name:</strong>HP Pavillion 15</p>
    <p style="text-align: center;font-size:larger"><strong>CPU:</strong>13th Gen Intel(R) Core(TM) i5-1334U</p>
    <p style="text-align: center;font-size:larger"><strong>RAM:</strong>16GB</p>
    <p style="text-align: center;font-size:larger"><strong>Storage:</strong>512GB</p>
    <p style="text-align: center;font-size:larger"><strong>Graphics Card:</strong>intel iRIS Xe</p>
    <p style="text-align: center;font-size:larger"><strong>Display Resolution:</strong>1920x1080</p>
    <p style="text-align: center;font-size:larger"><strong>Battery Life:</strong>7.5 to 10 hours</p>
    <p style="text-align: center;font-size:larger"><strong>Ports:</strong>USB-C,HDMI,USB-A</p>
    
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

'''
# OUTPUT:
![alt text](<Screenshot (4).png>)


![alt text](<Screenshot (3).png>)


# RESULT:
The program for implementing simple webserver is executed successfully.
