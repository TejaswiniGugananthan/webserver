# Developing a Simple Webserver

# AIM:

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
```python
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1. Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React</h2>
<h2>4. ASP.NET.</h2>
<h2>5. Meteor. </h2>
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
## SERVER OUTPUT:
![image](https://user-images.githubusercontent.com/121222763/228719286-a2d5234c-47c9-4aef-ba5b-f978d8c7e540.png)
## CLIENT OUTPUT:
![WhatsApp Image 2023-03-30 at 19 21 57](https://user-images.githubusercontent.com/121222763/228859923-7347ff7c-e341-4827-a02b-810163beed52.jpg)
## RESULT:
The program is executed succesfully
