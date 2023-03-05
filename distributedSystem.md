### Distributed Systems
---
###### Definition. 
- Definition 1: A distributed system is a collection of autonomous hosts that are
connected through a computer network.   
Each host executes components and operates a distribution middleware,
which enables the components to coordinate their activities in such a way
that users perceive the system as a single, integrated computing facility.   
- Definition 2: A distributed system is one in which components located at networked computers
communicate and coordinate their actions only by passing messages.   
###### Goals
- Resource sharing    
Sharing of hardware and software resources.
- Openness  
Use of equipment and software from different vendors.  
- Concurrency  
Concurrent processing to enhance performance.  
- Scalability  
Increased throughput by adding new resources.  
- Fault tolerance  
The ability to continue in operation after a fault has occurred.
- Complexity
Typically, distributed systems are more complex than
centralised systems.
- Security
More susceptible to external attack.
- Manageability
More effort required for system management.
- Unpredictability
Unpredictable responses depending on the system organisation and network load.
###### Distributed System Characteristics
- Multiple autonomous components
- Components are not shared by all users
- Resources may not be accessible
- Software runs in concurrent processes on different processors
- Multiple points of control
- Multiple points of failure

![image](https://user-images.githubusercontent.com/88880169/222974231-9214991f-e39b-4990-a922-5777e08a76cd.png)

##### Middleware
- Software that manages and supports the different components of a distributed system.
In essence, it sits in the middle of the system.
- is usually off-the-shelf rather than specially written software. 
- Examples
  - Transaction processing monitors;
  - Data converters;
  - Communication controllers.
![image](https://user-images.githubusercontent.com/88880169/222974366-b39878a2-6667-404f-82da-2f17fdbb1c56.png)

