### NAME: SURYA P <br>
### REG NO: 212224230280 <br> 
### Date: 14/08/2025

## EX. No. 1 : SIMPLE WEB SERVER

## AIM :
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:

### Step 1
HTML content creation.

### Step 2
Design of webserver workflow.

### Step 3
Implementation using Python code.

### Step 4
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6
Start an HTTP server on a specific port.

### Step 7
Run the Python script to serve web pages.

### Step 8
Serve the HTML pages.

### Step 9
Start the server script and check for errors.

### Step 10
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM :

```python
from http.server import HTTPServer, BaseHTTPRequestHandler

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>TCP/IP Protocol Suite – Protocol List</title>

<style>
  :root{
    --card-bg: #ffffff;
    --page-bg-from: #fff4e6;
    --page-bg-to: #ffe6f0;
    --header: #40312f;
    --accent: #ffb366;
    --accent-2: #ffd699;
  }

  body{
    margin:0;
    padding:18px;
    font-family: "Segoe UI", Roboto, Arial, sans-serif;
    background: linear-gradient(135deg, var(--page-bg-from), var(--page-bg-to));
  }

  .container{
    max-width:900px;
    margin: 30px auto;
    background: var(--card-bg);
    border-radius:12px;
    padding:25px;
    box-shadow: 0 10px 32px rgba(0,0,0,0.15);
  }

  h2{
    text-align:center;
    color: var(--header);
    font-size:26px;
    margin-bottom:10px;
    text-decoration:underline;
  }

  table{
    width:100%;
    border-collapse:collapse;
    font-size:15px;
    margin-top:15px;
  }

  th{
    background: var(--accent);
    padding:10px;
    border:1px solid rgba(0,0,0,0.2);
    font-weight:bold;
  }

  td{
    padding:10px;
    border:1px solid rgba(0,0,0,0.15);
    text-align:center;
  }

  caption{
    font-size:18px;
    margin-bottom:10px;
    font-weight:bold;
    color:var(--header);
    text-decoration:underline;
  }
</style>

</head>
<body>

<div class="container">

  <h2>TCP/IP Protocol Suite – Protocol List</h2>

  <table>
    <caption>List of Protocols in TCP/IP Protocol Suite</caption>
    <tr>
      <th>S.No.</th>
      <th>Name of the Layer</th>
      <th>Name of the Protocol</th>
    </tr>
    <tr>
      <td>1</td>
      <td>Application Layer</td>
      <td>HTTP, FTP, DNS, Telnet &amp; SSH</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Transport Layer</td>
      <td>TCP / UDP</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Network Layer</td>
      <td>IPv4 / IPv6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Link Layer</td>
      <td>Ethernet</td>
    </tr>
  </table>

</div>

</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("GET request received...")
        self.send_response(200)
        self.send_header("Content-Type", "text/html; charset=utf-8")
        self.end_headers()
        self.wfile.write(content.encode("utf-8"))

if __name__ == "__main__":
    print("This is my webserver (listening on port 8000)...")
    server_address = ('', 8000)
    httpd = HTTPServer(server_address, MyServer)
    try:
        httpd.serve_forever()
    except KeyboardInterrupt:
        print("\nShutting down server...")
        httpd.server_close()
```

## OUTPUT :
<img width="1465" height="587" alt="image" src="https://github.com/user-attachments/assets/1e997f89-f92d-4c71-876f-5c60886cafa1" />

## RESULT :
The program for implementing simple webserver is executed successfully.
