# pythonnetworkscanner
## **Simple Network Scanner**

### ICMP Echo Request

It is also known by using ‘ping command’. An ICMP packet is sent to a host using the IP address and if the ICMP echo is received, that means that the host is online and is receiving the signals. For this, it necessary to get all the IP addresses for which you wish to test that the host is connected or not. This method works on the assumption that network devices have ICMP enabled.

This code iterates over all the available IP addresses, ping them and check for the reply. If the echo is received, that means the host is connected and in case, no echo is received, then it looks like that the host is down.
Note: Personal firewalls or general firewalls are often set to so called “stealth mode” which is used not to react to ICMP echo requests.

This article is contributed by **Rishabh Bansal** & [geeksforgeeks.org]() & Kristoffer InTheCloud. 

##### Take the code below and use a text editor or Python3, paste it in, or type it in, and save it. Make sure to input your IP address range before saving or you will have errors.

import subprocess
  
for ping in range(1,10):
    address = "10.0.0." + str(ping)
    res = subprocess.call(['ping', '-c', '3', address])
    if res == 0:
        print( "ping to", address, "OK")
    elif res == 2:
        print("no response from", address)
    else:
        print("ping to", address, "failed!")
        
        #### The code above will give the outpout below, . At least it did with a 2019 Macbook Pro, with macOS El Monterey 12.3.1
        
![Screen Shot 2022-04-06 at 9 37 15 PM](https://user-images.githubusercontent.com/90732110/162346763-a36ef8c3-348a-42db-8018-aab7acd71577.png)

