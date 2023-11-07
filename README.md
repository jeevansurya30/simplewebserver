# EX01 Developing a Simple Webserver
## Date:09.9.23
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
```py
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top Five Software Companies<h1>
<ul>
<li>WIPRO</li>
<li>Google</li>
<li>Microsoft</li>
<li>Infosyss</li>
<li>JP Morgan</li>
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
![web 1](https://github.com/jeevansurya30/simplewebserver/assets/129417865/f86eaa89-8cbb-426c-9c17-ba8fa664c188)

![web 2](https://github.com/jeevansurya30/simplewebserver/assets/129417865/95a7d82f-7753-44d8-930c-53373425e179)



## RESULT:
The program for implementing simple webserver is executed successfully.
