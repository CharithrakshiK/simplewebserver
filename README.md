# EX01 Developing a Simple Webserver
## Date:16.10.2024

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
<html>
  <head>
     <title>device specifications</title>
</head>
<body bgcolor="yellow">
    <h1 align="center">DEVICE SPECIFICATIONS</h1>
    <h3 align="center">Name:charithrakshi</h3>
    <h3 align="center">Ref no:24900651</h3>
    <ol>
        <li>device name  :charithra</li>
        <li>processor    :13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
        <li>installed ram:16.0 GB (15.7 GB usable)</li>
        <li>device id    :15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
        <li>product id   :00342-42709-00586-AAOEM</li>
        <li>system type   :64-bit operating system, x64-based processor</li>
        <li>pen and touch :No pen or touch input is available for this display</li>
    </ol>
    <hr>
    <ul>
        <li>edition</li>
        <li>version</li>
        <li>installed on</li>
        <li>os build</li>
        <li>experience</li>
    </ul>

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

```


## OUTPUT:
![alt text](<Screenshot 2024-11-11 144505.png>)
![alt text](<Screenshot 2024-11-11 144540.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
