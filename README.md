
# EX01 Developing a Simple Webserver
## Date:26.10.2024

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
'''
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<!doctype html>
<html>
<head>
<title>Laptop specification</title>
</head>
<body> 
<table border='4' cell spacing="12" cell padding="6">
<tr>
  <th>s.no</th>
  <th>configuration</th>
</tr>
<tr>
  <th>1</th>
  <th>Name</th>
  <th>Lenovo thinkpad</th>   
</tr>
<tr>
  <th>2</th>
  <th>processor</th>
  <th>intel i5</th>
</tr>
<tr>
  <th>3</th>
  <th>Graphics</th>
  <th>Nvidia Geforce Mx550</th>
</tr>
<tr>
  <th>4</th>
  <th>Edition</th>
  <th>Windows 11 </th>
</tr>
<tr>
  <th>5</th>
  <th>Installed Ram</th>
  <th>Windows 11 Home Single Language</th>  
</tr>
<tr>
  <th>6</th>
  <th>Version</th>
  <th>23H2</th>
</tr>
<tr>
  <th>7</th>
  <th>colour</th>
  <th>Black</th>
 </tr> 
 <tr>
  <th>8</th>
  <th>Os Build</th>
  <th>22631.4169</th>  

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
server_address =('',5000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

'''
## OUTPUT:
![image](https://github.com/user-attachments/assets/2551c1f5-c4b5-4071-b67f-334991332bed)


## RESULT:
The program for implementing simple webserver is executed successfully.
