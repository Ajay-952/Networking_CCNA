# What is MAC address?
- The MAC or media access control address is an identifier that every network device uses to uniquely identify itself on a network.

# What is the difference between the ipv4 address and MAC address? 
- A COM contains both MAC address and a IP address, where ip address is to identify in which network the device is located in and a MAC address is to identify the exact location of the device. 

# Why do we have MAC address to the COM? 
- Evry device has it's own permenent MAC address to share the resources with the devices in the network. 
- whenever we search for a webpage a request is genearted from our devices and the request gets the reply from the server no matter wether the server is in same network or different network. 
- Ex. When you type google.com into your browser and press Enter, your laptop first needs to find the IP address associated with that domain name, so it sends a DNS request to a DNS server. Once it gets Google's IP address, your laptop checks whether that destination is on the same local network. Since Google is on a different network, your laptop sends the traffic to its default gateway, which is usually your home router. To communicate with the router on the local network, your laptop uses ARP to find the router's MAC address. Your browser then establishes a connection with Google's server

```text
                YOU                    
                 │                        
                 ▼                        
        Type google.com                   
                 │                        
                 ▼                        
                DNS                        
                 │                        
                 ▼                        
       Find Google's IP                   
                 │                        
                 ▼                        
      Is Google on my LAN?                
                 │                        
                NO                        
                 │                        
                 ▼                        
       Send to Gateway                    
                 │                        
                 ▼                        
               ARP                        
                 │                         
                 ▼                         
       Find router's MAC                  
                 │                        
                 ▼                        
             Router                       
                 │                        
                 ▼                        
                ISP                       
                 │                        
                 ▼                        
       Multiple Routers                   
                 │                        
                 ▼                        
          Google Network                  
                 │                        
                 ▼                        
          Google Server                   
                 │                        
                 ▼                        
            Response                      
                 │                        
                 ▼                        
              Laptop                      
                 │                        
                 ▼                        
          Google appears
```                  

# What is Subnet mask ? 
- A subnet mask tells a computer which part of an IP address represents the network and which part represents the host/device.

Ex: 
```text
     IP address:   192.168.1.10   
     Subnet mask:  255.255.255.0  
```

So: 
```text
       IP:           192.168.1.10        
       Subnet mask:  255.255.255.0   
              ─────────────               
        Network:      192.168.1.0     
        Host:         10              
```

# Why is this important?

- The subnet mask allows a device to determine:

      "Is the destination device on my local network, or do I need to send the traffic to my router?"

- If the destination device is found in same LAN network then no need to go to the "Default Router" we can directly get the mac address of the desination device.

   Ex:
```text
       Your PC:          
       192.168.1.10      
       255.255.255.0     
                             
       Another PC:       
       192.168.1.20      
```

       "In the above exmaple it's clearly mentioned that both the client and server both are in same network." 
  
- In the other case if the destination device is located in the different network 

   Then 
```text
        192.168.1.10 → Network 192.168.1.0   
        192.168.2.20 → Network 192.168.2.0   
```

       " So your pc needs to send the traffic through a router "

🧠 One sentence to remember
   - IP address identifies the device/interface, while the subnet mask tells you which part of that IP identifies the network and which part identifies the host.