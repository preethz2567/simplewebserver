# EX01 Developing a Simple Webserver
## Date:
   18-10-2024
## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html lang="eng">
    
    <title>pcproject</title>
    <body bgcolor="cyan">
        <h1 align="center"> DEVICE SPECIFICATIONS (Name: Preethi D 24007817)</h1>
        <hr color="black">
        <h2>
           
        <ul>
            <li>Device name - PReetz</li>
            <li>Processor - 13th Gen Intel(R) Core(TM) i5-1335U 1.30GHz</li>
            <li>Installed RAM - 16.0 GB(15.7 GB usable)</li>
            <li>Device ID - 15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
            <li>Product ID - 00342-42708-86879-AAOEM</li>
            <li>System type - 64-bit operating system , x64-based processor</li>
            <li>Pen and touch - No pen or touch is available for this display</li>
        </ul>
    
        </h2>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```g


## OUTPUT:
![alt text](<Screenshot 2024-11-11 145242.png>)

![alt text](<Screenshot 2024-11-11 150025.png>)




## RESULT:
The program for implementing simple webserver is executed successfully.
