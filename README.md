# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```python
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''

<!DOCTYPE html>
<html>
<head>
    <title>College Details</title>
</head>
<body>
    <table border="5" align="center" cellspacing="20" cellpadding="20" bgcolor="red">
        <caption><b>Department Information</b></caption>
        <tr bgcolor="blue">
            <th>S.No</th>
            <th>Name of the layer</th>
            <th>Name of the protocol</th>
        </tr>
        <tr bgcolor="green">
            <td>1</td>
            <td>application layer</td>
            <td>HTTP,FTP,DNS,Telnet,SSH</td>
        </tr>
        <tr bgcolor="yellow">
            <td>2</td>
            <td>Transport Layer</td>
            <td>TCP/UDP</td>
        </tr>
        <tr bgcolor="white">
            <td>3</td>
            <td>Network Layer</td>
            <td>IPV4/IPv6</td>
        </tr>
        <tr bgcolor="pink">
            <td>3</td>
            <td>Link Layer</td>
            <td>Ethernet</td>
        </tr>
    </table>
</body>
</html>'''

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
```


## OUTPUT:
<img width="1920" height="1200" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/c4f8c6f9-4eec-48ae-994f-1d259b87cb1c" />
<img width="1920" height="1200" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/eea8d5bf-3b75-4ba5-a3b6-2334aa909b75" />
## RESULT:
The program for implementing simple webserver is executed successfully.
