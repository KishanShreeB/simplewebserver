# EX01 Developing a Simple Webserver
## Date: 7/10/23

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
<html>
<title>Revenue table</title>
<body>
<center>
<table border="1" cellpadding="5">
<caption> <b><u>Top five Revenue Generating Software Companies</u></b></caption>
<tr>
<th>S.No</th>
<th>Company</th>
<th>Revenue</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft</td>
<td>65 Billion</td>
</tr>
<tr>
<td>2</td>
<td>Oracle</td>
<td>29.6 Billion</td>
</tr>
<tr>
<td>3</td>
<td>IBM</td>
<td>29.1 Billion</td>
</tr>
<tr>
<td>4</td>
<td>SAP</td>
<td>6.4 Billion</td>
</tr>
<tr>
<td>5</td>
<td>Symantec</td>
<td>5.6 Billion</td>
</tr>
</center>
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

![Alt text](<Screenshot (5).png>)

![Alt text](<Screenshot (7).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
