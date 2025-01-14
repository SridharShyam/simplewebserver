# EX01 Developing a Simple Webserver
## Date:06/10/2023

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
	<title> Revenue Table </title>
	<body>
		<table border="2" cellspacing="5" cell padding="5">>
		<caption> Top 5 Revenue Generating Companies </caption>
		<tr>
			<th> S.NO </th>
			<th> COMPANY </th>
			<th> REVENUE </th>
		</tr>
		<tr>
			<th> 1. </th>
			<td> Microsoft Corp </td>
			<td> $203.08 billion </td>
		</tr>
		<tr>
			<th> 2. </th>
			<td> Oracle Corp </td>
			<td> $46.07 billion </td>
		</tr>
		<tr>
			<th> 3. </th>
			<td> SAP SE </td>
			<td>  $32.97 billion </td>
		</tr>
		<tr>
			<th> 4. </th>
			<td> SALESFORCE Inc </td>
			<td> $30.29 billion </td>
		</tr>
		<tr>
			<th> 5. </th>
			<td> Adobe Inc </td>
			<td> $17.61 billion </td>
		</tr>
		</table>
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
![Screenshot (17)](https://github.com/SridharShyam/simplewebserver/assets/144871368/e919da0f-8915-4adc-a8bd-028804054a6c)
![Screenshot (18)](https://github.com/SridharShyam/simplewebserver/assets/144871368/30291597-fe06-4d78-a94f-05416c1c7028)

## RESULT:
The program for implementing simple webserver is executed successfully.
