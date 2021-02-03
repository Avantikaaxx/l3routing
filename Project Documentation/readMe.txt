Implementation and Execution - For details refer Report

Note: Instructions to run mininet:
Single SDN switch - sudo ./run_mininet.py single,3
This command will create a topology with a single SDN switch (s1) and three hosts (h1 - h3) directly connected to the switch

1) A layer-3 routing application will install rules in SDN switches to forward traffic to hosts using the shortest, valid path through the network.
The code for the layer-3 routing application resides in L3Routing.java in the edu.wisc.cs.sdn.apps.l3routing package.
 To run the shortest path project: 
a. cd /openflow/
b. ant
c. java -jar FloodlightWithApps.jar -cf shortestPathSwitch.prop

2) Load Balancer:
Networks employ load balancing to distribute client requests among a collection of hosts running a specific service (e.g., a web server). 
A hardware load balancer is placed in the network and configured with an IP address and a set of hosts among which it should distribute requests. 
Clients wanting to communicate with a service (e.g., a web server) running on those hosts are provided with the IP address of the load balancer, 
not the IP address of a specific host. Clients initiate a TCP connection to the IP address of the load balancer (10.0.100.1) and the TCP port associated with the service. For each new TCP connection, the load balancer selects one of the specified hosts (usually in round robin order). The load balancer maintains a mapping of active connections—identified by the client’s IP and TCP port—to the assigned hosts.  
The code for the load balancer application resides in LoadBalancer.java in the edu.wisc.cs.sdn.apps.loadbalancer package.
To run the loadbalancing project:
a. cd /overflow/
b. ant
c. java -jar FloodlightWithApps.jar -cf loadbalancer.prop
