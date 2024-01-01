# Developing a Simple Webserver

# AIM:

```
To develop a simple webserver to serve html programming pages.


## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```py
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
### Server output
![serveroutput](https://github.com/RESHMA22C/webserver/assets/147474426/0a25a967-9521-4ee8-905e-6ed878380fe5)
### Client output
![clientoutput](https://github.com/RESHMA22C/webserver/assets/147474426/9482848e-0dd3-4792-9716-f1579e18aa09)

## RESULT
The program is executed successfully



