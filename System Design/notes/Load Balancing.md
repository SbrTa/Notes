# Load Balancing

### Where to add load balancer?
We can add load balancer at three places:
  - Between the user and the web server
  - Between web servers and an internal platform layer, like application servers or cache servers
  - Between internal platform layer and database

![image](https://user-images.githubusercontent.com/8649145/184546226-3d089371-4c23-4c5f-ae83-0fb5bd3186a1.png)


### How does the load balancer choose the backend server?
Load balancers consider two factors to forward traffic -
  - Health check
  - Load balancing algorithm

Some of the common load balancing algorithms
  - Round Robin: sequential or rotational manner.
  - Weighted Round Robin
  - Least Connection Method: the fewest active connections.
  - Least Response Time Method: fewest active connections and the least average response time.
  - Source IP Hash: the request is sent to the server based on the client’s IP address. The IP address of the client and the receiving compute instance are computed with a cryptographic algorithm. 

### Is your load balancer is a single point of failure?
The load balancer can be a single point of failure. To overcome this, a second load balancer can be connected to the first to form a cluster. 
Each LB monitors the health of the other and, since both of them are equally capable of serving traffic and failure detection, in the event 
the main load balancer fails, the second load balancer takes over.

