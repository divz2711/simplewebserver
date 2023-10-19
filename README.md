# EX01 Developing a Simple Webserver
## Date: 07/10/2023

## AIM:
To develop a simple webserver to serve html pages.

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
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top five Revenue generating Software Companies.</h1>
    <ol>
        <li>Apple</li>
        <li>Microsoft</li>
        <li>Alphabet</li>
        <li>Amazon</li>
        <li>Tesla</li>
    </ol>
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
server_address = ('',8001)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![image](https://github.com/divz2711/simplewebserver/assets/121245222/c269596e-faae-48dd-927d-6fd438d04dd3)


## RESULT:
The program for implementing simple webserver is executed successfully.
