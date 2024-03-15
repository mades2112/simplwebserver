# EX01 Developing a Simple Webserver
## Date:28/02/2024

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
      <head> 
            <title>Top Software Companies Revenue</title>
      </head>
      <body>
      <table border="4" cellspacing="5" width="40" heigth="50"
        <caption>REVENUE</caption>
        <tr>
             <th>Rank</th>
             <th>company name</th>
             <th>Revenue</th>
             <th>Market cap</th>
        </tr>
        <tr>
             <td>1</td>
             <td>Microsoft</td>
             <td>$86.8</td>
             <td>$370.3</td>
        </tr>
        <tr>
             <td>2</td>
             <td>Oracle</td>
             <td>$37.1</td>
             <td>$79.4</td>
        </tr>
        <tr>
             <td>3</td>
             <td>SAP</td>
             <td>$20.9</td>
             <td>$35.5</td>
        </tr>
        <tr>
             <td>4</td>
             <td>Symantec</td>
             <td>$6.8</td>
             <td>$14</td>
        </tr>
        <tr>
             <td>5</td>
             <td>vMware</td>
             <td>$5.2</td>
             <td>$41.03</td>  
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

## OUTPUT:
![alt text](<Screenshot 2024-03-15 095400.png>)
![alt text](<Screenshot 2024-03-15 101604-1.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
