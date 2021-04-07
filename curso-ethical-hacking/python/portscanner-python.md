# 10 - PortScanner Python



```python
#!/bin/python
import sys
import socket
from datetime import datetime

#Target def
if len(sys.argv) == 2:
    target = socket.gethostbyname(sys.argv[1]) # correct ip to ipv4
else:
    print("invalid amount of arguments. Syntax: python3 scanner.py <ip>")

print("-" * 50)
print("Scanning target " + target)
print("Time started:" + str(datetime.now()))

try:
    for port in range(50,85):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        socket.setdefaulttimeout(1)
        result = s.connect_ex((target,port)) #returns error if not connect
        if result == 0:
            print("Port " + port + " is open")
            s.close()
except KeyboardInterrupt:
    print("\n Exiting program")
    sys.exit()
    
except socket.gaierror:
    print("Hostname could not be resolved")
    
except socket.error:
    print("Could not connect to server")
    sys.exit()
            
```

