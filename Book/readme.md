# [Chapter 1](https://drive.google.com/file/d/1lsY0n-Ov5AiL6pCv7tv2U4vI3WyI6h9_/view?usp=sharing)

##  Introduction to Distributed Systems


#### **1. Introduction: From Networked Systems to Distributed Systems**
- **Key Categories**:
  1. **Centralized Systems**:
     - Processes and resources are managed by a single central node.
  2. **Decentralized Systems**:
     - Processes and resources are distributed across multiple nodes, but without complete coordination.
  3. **Distributed Systems**:
     - Processes and resources are sufficiently distributed and coordinated to act as a single cohesive system.

- **Transition from Decentralized to Distributed Systems**:
  - Determined by the addition of interconnections:
    - Adding **1 link** between two nodes in a decentralized system.
    - Adding **2 links** between two other nodes.
    - In general: adding \(k > 0\) links can shift a decentralized system to a distributed one.


#### **2. Alternative Approaches to Distributed Systems**
- **Two Views of Realization**:
  1. **Integrative View**:
     - Combines existing networked computer systems into a unified larger system.
  2. **Expansive View**:
     - Extends existing systems by adding new computers or resources.

- **Definitions**:
  - **Decentralized System**: Resources and processes are necessarily spread across multiple computers.
  - **Distributed System**: Resources and processes are sufficiently distributed to enable effective coordination.


#### **3. Common Misconceptions about Distributed Systems**
- **Scalability of Centralized Solutions**:
  - Centralized systems often believed to be unscalable.
  - Example: The **Domain Name System (DNS)** is:
    - Logically centralized.
    - Physically distributed across multiple locations.
    - Decentralized across organizations.

- **Single Point of Failure in Centralized Systems**:
  - Misconception: Centralized systems are prone to single points of failure.
  - Reality: Robust designs can mitigate this, and centralized systems are:
    - Easier to manage.
    - Easier to make robust.

- **Understanding Misconceptions**:
  - Many beliefs about scalability, fault tolerance, and security are poorly founded.
  - A systematic approach is needed to evaluate these claims.


#### **4. Perspectives on Distributed Systems**
- Distributed systems are complex and require multiple perspectives:
  1. **Architecture**: Overall organization of the system.
  2. **Processes**: Types of processes and their interactions.
  3. **Communication**: Mechanisms for data exchange.
  4. **Coordination**: Algorithms independent of specific applications.
  5. **Naming**: Identifying resources within the system.
  6. **Consistency and Replication**: Ensuring data uniformity across the system.
  7. **Fault Tolerance**: Ability to function despite partial failures.
  8. **Security**: Ensuring controlled and authorized access to resources.


#### **5. Design Goals of Distributed Systems**
- **Primary Goals**:
  1. **Resource Sharing**:
     - Examples:
       - Cloud storage.
       - Peer-to-peer streaming.
       - Outsourced email systems.
       - Content distribution networks.
     - Observation: *“The network is the computer”* (John Gage, Sun Microsystems).

  2. **Distribution Transparency**:
     - **Definition**: Hides the fact that resources and processes are distributed across multiple locations.
     - **Types of Transparency**:
       - **Access**: Hides differences in data representation and access methods.
       - **Location**: Hides the physical location of resources.
       - **Relocation**: Hides that resources may be moved during use.
       - **Migration**: Hides the movement of processes across systems.
       - **Replication**: Hides that resources are duplicated.
       - **Concurrency**: Hides concurrent use of resources by multiple users.
       - **Failure**: Hides resource or process failures and recoveries.

     - **Challenges**:
       - Communication latencies and failures cannot always be hidden.
       - Full transparency may degrade performance.
       - Keeping replicas up-to-date introduces delays and costs.

     - **Scenarios Where Exposing Distribution Helps**:
       - Location-based services (e.g., finding nearby friends).
       - Handling users in different time zones.
       - Better user experience during failures (e.g., notifying users about server downtimes).

  3. **Openness**:
     - Open systems allow components to integrate seamlessly.
     - Characteristics:
       - Well-defined interfaces.
       - Interoperability with other systems.
       - Portability and extensibility of applications.

  4. **Dependability**:
     - Dependability involves ensuring system reliability and fault tolerance.
     - **Metrics**:
       - **Availability**: System readiness for use.
       - **Reliability**: Continuity of service over time.
       - **Safety**: Very low probability of catastrophic failures.
       - **Maintainability**: Ease of repairs and system upgrades.

  5. **Scalability**:
     - Distributed systems must scale across:
       - **Size**: Number of users or processes.
       - **Geographical Distance**: Physical spread of nodes.
       - **Administrative Domains**: Inter-organizational collaboration.


#### **6. Security in Distributed Systems**
- **Key Aspects**:
  1. **Confidentiality**: Information is only accessible to authorized entities.
  2. **Integrity**: Ensures resources are altered only through authorized means.
  3. **Authentication**: Verifying the identity of a user or process.
  4. **Authorization**: Checking access rights of an authenticated entity.
  5. **Trust**: Ensuring entities perform as expected under specific conditions.

- **Mechanisms**:
  - Symmetric encryption: Single shared key for encryption/decryption.
  - Asymmetric encryption: Public/private key pairs for secure communication.
  - Secure hashing: Produces fixed-length outputs to verify data integrity.
  - Digital signatures: Ensures message authenticity and origin.

---

#### **7. Scalability Techniques**
- **Strategies for Scaling**:
  1. **Hide Communication Latencies**:
     - Asynchronous communication.
     - Separate handlers for responses.
  2. **Partition Data and Computations**:
     - Distribute tasks across nodes.
     - Use decentralized systems like DNS.
  3. **Replication and Caching**:
     - Store multiple copies of data to reduce load.
     - Challenges:
       - Maintaining consistency across replicas.
       - Requires synchronization, which limits scalability.


#### **8. Classification of Distributed Systems**
- **Types**:
  1. **High-Performance Computing**:
     - Evolved from parallel computing systems.
     - Examples: Multiprocessor, multicore, and grid systems.
  2. **Distributed Information Systems**:
     - Middleware facilitates system integration.
     - Examples:
       - Remote Procedure Calls (RPC).
       - Message-Oriented Middleware (MOM).
  3. **Distributed Pervasive Systems**:
     - Emerging systems with mobile and embedded nodes.
     - Subcategories:
       - **Ubiquitous Computing**: Continuous interaction with users.
       - **Mobile Systems**: Adapt to changing locations.
       - **Sensor Networks**: Collaboratively monitor and act on the environment.


#### **9. Pitfalls in Developing Distributed Systems**
- **Common False Assumptions**:
  - The network is reliable.
  - The network is secure.
  - The network topology does not change.
  - Latency is zero, and bandwidth is infinite.
  - Transport costs are zero.
  - Only one administrator exists for the system.

- **Consequence**:
  - These misconceptions often lead to unnecessary complexity and flawed designs that require extensive patching later.

### **Conclusion**
This chapter establishes a strong foundation for understanding distributed systems. It emphasizes their goals, misconceptions, classifications, and challenges, providing a roadmap for designing scalable, dependable, and secure systems.



# Chapter 2


### Highlights -📜
1. **Architectural Styles**: Different styles define how components interact in distributed systems. 
2. **Layered Architectures**: Organizes systems into application, processing, and data layers for clarity and separation of concerns. 
3. **Service-Oriented Architectures**: Focuses on resources managed by components, allowing for operations like PUT, GET, and DELETE.
4. **Peer-to-Peer Networks**: All nodes act as both clients and servers, enhancing resource sharing and redundancy.
5. **Middleware**: Simplifies complex system interactions by providing common functions and components.
6. **Cloud Computing**: Layers from hardware to application, allowing flexible resource management and deployment.
7. **Blockchain**: Ensures data integrity through distributed consensus mechanisms, vital for decentralized applications.

### Key Insights -💡
1. **Component Interaction**: The effectiveness of a distributed system largely depends on how components are designed to interact with each other. Properly defined interfaces and connectors ensure smooth communication, which is crucial for system performance. 🔗
   
2. **Layered Architecture Benefits**: Layering helps in organizing complex systems, making them easier to manage and evolve. Each layer has defined responsibilities, allowing developers to modify one layer without affecting others, thereby enhancing maintainability. 📊

3. **Service Orientation**: By treating resources as services, distributed systems can achieve greater flexibility and scalability. This architecture allows for dynamic resource management and easy integration of new services, fostering innovation. 🌐

4. **Peer-to-Peer Dynamics**: Peer-to-peer systems eliminate single points of failure and enable efficient resource distribution. However, they introduce challenges in managing data consistency and search efficiency due to their decentralized nature. 🤝

5. **Middleware's Role**: Middleware acts as the "glue" in distributed systems, simplifying the development process by providing reusable components. This allows developers to focus on application logic rather than underlying infrastructure complexities. 🛠️

6. **Cloud Computing Layers**: Understanding the distinct layers of cloud computing—from hardware to applications—helps organizations to optimize their resource usage and deploy services effectively, catering to diverse user needs. ☁️

7. **Blockchain Consensus Mechanisms**: The choice of consensus mechanism in blockchain systems impacts scalability and security. Distributed solutions are more resilient but complex, while centralized solutions may compromise decentralization principles. 🔒

# Slide 2


### **Architectural Styles**

**Basic Idea**  
An architectural style is defined by the following aspects:
1. **Components**: Replaceable elements with well-defined interfaces.  
2. **Connectors**: Mechanisms that mediate communication, coordination, or cooperation among components. Examples include facilities for (remote) procedure calls, messaging, or streaming.  
3. **Data Exchange**: The way data is shared between components.  
4. **System Configuration**: The overall organization of components and connectors within the system.  

### **Connectors**
A connector acts as a communication facilitator between components.  
**Examples**:  
- Remote procedure calls  
- Messaging systems  
- Streaming protocols  


### **Layered Architecture**
Layered architecture organizes the system into distinct layers, where each layer is responsible for specific tasks or functionality.  

#### **Different Layered Organizations**  
Layered architecture can have various configurations depending on the system's requirements.



### **Example: Communication Protocols**

#### **Key Concepts**
- **Protocol**: Rules for communication.  
- **Service**: Functions provided by a layer.  
- **Interface**: Boundary for interaction between layers.  

#### **Layered Communication Example**  
- A client-server model demonstrates layered communication effectively.  
- Below is an example implementation in Python:  

**Server**  
```python
from socket import *

s = socket(AF_INET, SOCK_STREAM)
s.bind((HOST, PORT))
s.listen(5)
(conn, addr) = s.accept()  # Accepts connection and returns socket and address

while True:  # Run indefinitely
    data = conn.recv(1024)  # Receive data from the client
    if not data:
        break  # Stop if client disconnects
    msg = data.decode() + "*"  # Process the data
    conn.send(msg.encode())  # Send response back to the client
conn.close()  # Close connection
```

**Client**  
```python
from socket import *

s = socket(AF_INET, SOCK_STREAM)
s.connect((HOST, PORT))  # Connect to the server
msg = "Hello World"  # Message to send
s.send(msg.encode())  # Send the message
data = s.recv(1024)  # Receive server response
print(data.decode())  # Display response
s.close()  # Close connection
```



### **Application Layering**

#### **Traditional Three-Layered Architecture**  
1. **Application-Interface Layer**  
   - Provides interaction with users or external systems.  
2. **Processing Layer**  
   - Contains core functionalities of the application, independent of data.  
3. **Data Layer**  
   - Manages and stores data accessed or manipulated by the application.  

#### **Observation**  
This structure is widely used in distributed information systems, often with traditional database technologies.



### **Architectural Styles**

#### **Layered Architectures**
Layered architectures organize systems into distinct layers, with each layer focusing on a specific functionality.  
Example: A simple search engine implementation where layers include:  
1. User Interface Layer handles user input and displays results.  
2. Processing Layer performs indexing and search algorithms.  
3. Data Layer stores the indexed data.  

#### **Object-Based Style**
Components are treated as objects.  
Objects interact via procedure calls, which may execute across a network.  
Objects encapsulate data and expose methods to interact with the data without revealing the internal implementation.

#### **Service-Oriented Architectures (SOA)**

**RESTful Architectures**  
REST views a distributed system as a collection of resources. These resources can be added, retrieved, modified, or deleted.  

Resources are identified through a uniform naming scheme such as URIs.  
Services provide a consistent interface.  
Messages are self-descriptive.  
After executing an operation, the service does not retain the caller’s state.  

**Basic RESTful Operations**  
| Operation | Description                          |  
|-----------|--------------------------------------|  
| PUT       | Create a new resource.              |  
| GET       | Retrieve the state of a resource.   |  
| DELETE    | Remove a resource.                  |  
| POST      | Modify or update a resource’s state.|  

**Example: Amazon S3**  
Amazon’s Simple Storage Service (S3) is a practical example.  
Objects (files) are placed in buckets (directories).  
Buckets cannot contain other buckets.  
Objects are identified by `http://BucketName.s3.amazonaws.com/ObjectName`.  

**Operations in S3**  
Create a bucket or object using PUT with a URI.  
List objects using GET on a bucket name.  
Retrieve an object using GET with a full URI.  

**RESTful Interfaces**  
RESTful interfaces are simple but require precise handling of parameters.  

**Simplification Example**  
An interface for creating a bucket named "mybucket."  

**SOAP Example**  
```python
import bucket
bucket.create("mybucket")
```  

### **Architectural Styles**

#### **Service-Oriented Architectures (SOA)**  

**On Interfaces**  
Simplified interfaces enable straightforward interactions.  

**Examples**:  
1. **SOAP**  
   ```python
   import bucket
   bucket.create("mybucket")
   ```  
   This creates a bucket named "mybucket" using a method call.  

2. **RESTful Interface**  
   ```
   PUT "https://mybucket.s3.amazonaws.com/"
   ```  
   This sends an HTTP PUT request to create a bucket named "mybucket."  

**Conclusions**  
Both SOAP and RESTful interfaces achieve similar goals but differ in implementation. REST is lightweight and flexible, while SOAP offers more structured messaging with built-in error handling and security features.  

---

#### **Coordination in Architectures**  

**Temporal and Referential Coupling**  
1. **Temporally Coupled**  
   - Communication happens in real-time.  
   - Direct interactions, such as method calls or socket communication.  

2. **Referentially Coupled**  
   - Components directly reference each other. Example: Direct method invocation.  

3. **Referentially Decoupled**  
   - Components do not directly reference each other.  

   **Examples**:  
   - **Event-Based Communication**: Messages published and subscribed to by components.  
   - **Shared Data Space**: Components interact by reading and writing to a common storage.  

---

#### **Publish-Subscribe Architectures**  

**Example: Linda Tuple Space**  
Linda is a coordination model where components interact through a shared "tuple space."  

**Operations**:  
- **`in(t)`**: Removes a tuple matching template `t`.  
- **`rd(t)`**: Copies a tuple matching template `t`.  
- **`out(t)`**: Adds a tuple `t` to the tuple space.  

**Details**:  
- **Tuple Space as a Multiset**: Calling `out(t)` twice stores two identical tuples.  
- **Blocking Operations**: `in` and `rd` block until a matching tuple becomes available.  

---

**Example Code**  

**Bob**  
```python
import linda
linda.connect()

blog = linda.TupleSpace()
linda.universe._out(("MicroBlog", blog))
blog._out(("bob", "distsys", "I am studying chap 2"))
blog._out(("bob", "distsys", "The linda example’s pretty simple"))
blog._out(("bob", "gtcn", "Cool book!"))
```

**Alice**  
```python
import linda
linda.connect()

blog = linda.universe._rd(("MicroBlog", linda.TupleSpace))[1]
blog._out(("alice", "gtcn", "This graph theory stuff is not easy"))
blog._out(("alice", "distsys", "I like systems more than graphs"))
```

**Chuck**  
```python
import linda
linda.connect()

blog = linda.universe._rd(("MicroBlog", linda.TupleSpace))[1]
t1 = blog._rd(("bob", "distsys", str))
t2 = blog._rd(("alice", "gtcn", str))
t3 = blog._rd(("bob", "gtcn", str))

print(t1)
print(t2)
print(t3)
```



### **Publish-Subscribe Architectures**

**Issue: How to Match Events?**  
- **Event Description**: Events are described as `(attribute, value)` pairs.  
- **Matching Methods**:  
  - **Topic-based Subscription**: Specify attributes and values (e.g., `attribute = value`).  
  - **Content-based Subscription**: Define attributes within a range (e.g., `attribute ∈ range`).  

**Observation**:  
- **Scalability Challenge**:  
  - Content-based subscriptions may face serious scalability issues due to the need for continuous filtering and matching of ranges across numerous events, especially in large-scale distributed systems.



### **Middleware and Distributed Systems**

**Middleware as the OS of Distributed Systems**  
- Provides common components and functions, reducing the need for separate implementations in applications.  

**Using Legacy Systems for Middleware**  
- **Problem**: Legacy component interfaces may not suit all applications.  
- **Solution**: Use wrappers or adapters to translate client requests into functions compatible with the component.  

**Wrapper Organization**  
1. **1-on-1 Wrappers**:  
   - Complexity: \(O(N^2)\), requiring \(N \times (N - 1)\) wrappers.  
2. **Broker-based Wrappers**:  
   - Complexity: \(O(N)\), requiring only \(2N\) wrappers.  

**Developing Adaptable Middleware**  
- Problem: Middleware is often designed for general use, but may need behavior adjustments for specific applications.  
- Solution: Intercept and modify the control flow to adapt functionality as needed.



### **Layered-System Architectures**

**Centralized Systems**  
- **Basic Client-Server Model**:  
  - Servers provide services; clients use them.  
  - Follows a request/reply model.  
- **Multi-Tiered Configurations**:  
  - Single-tier: Mainframe/dumb terminal.  
  - Two-tier: Client-server.  
  - Three-tier: Separate machines for presentation, logic, and data.  

**Example: Network File System (NFS)**  
- **Features**:  
  - Standardized local file system views.  
  - Remote access for uploading/downloading files.  
- **Comparison**:  
  - FTP uses a similar upload/download model.  



### **Symmetrically Distributed Architectures**

**Peer-to-Peer (P2P) Systems**  
- **Horizontal Distribution**:  
  - Logical parts operate on separate data shares.  
- **Peer-to-Peer Features**:  
  - All processes act as both client and server.  

**Structured P2P (e.g., Chord)**  
- **Principles**:  
  - Nodes in a ring structure, each with a unique identifier.  
  - Data is hashed and stored at the node with the closest matching identifier.  
- **Shortcut Links**: Speed up lookups.  

**Unstructured P2P**  
- **Flooding**:  
  - Broadcast requests to all neighbors; can limit via TTL.  
- **Random Walk**:  
  - Forward requests randomly until the desired data is found.  

**Comparison**:  
- Flooding is faster but less efficient.  
- Random walks save bandwidth but take longer.  

**Super-Peer Networks**  
- Break symmetry by introducing indexing servers for improved performance and efficient data storage decisions.



### **Hybrid Architectures**

**Cloud Computing**  
- **Layers**:  
  1. **Hardware**: Processors, routers, etc.  
  2. **Infrastructure**: Virtualization of servers and storage.  
  3. **Platform**: APIs for higher-level abstractions.  
  4. **Application**: User-facing software like office suites.  

**Edge Computing**  
- **Essence**: Servers deployed at network boundaries for latency reduction, reliability, and security.  
- **Challenges**:  
  - Resource allocation and service placement decisions.  
  - Selecting appropriate edge infrastructures.



### **Blockchain Architectures**

**Principles**  
- Immutable, append-only blocks organized in a chain.  
- Requires distributed consensus for appending blocks.  

**Consensus Mechanisms**  
1. **Centralized**: Single entity decides (not aligned with blockchain's decentralized goals).  
2. **Distributed (Permissioned)**:  
   - Consensus by a small, trusted group of servers.  
   - Suitable for smaller, permissioned systems.  
3. **Decentralized (Permissionless)**:  
   - Large-scale leader election for appending blocks.  
   - Requires robust mechanisms for fairness and security.



# Chapter 3

### Summary  
This text provides an overview of distributed systems, focusing on the concepts of processes and threads. It explains how threads function as lightweight processes, enabling efficient execution through context switching. The document discusses the advantages of multithreading, including improved performance, parallelism, and reduced blocking. It also contrasts kernel-level and user-level threading, explores the virtualization of processes, and touches on the implications for server-client interactions, code migration, and networked applications.

### Highlights -🖥️  
- **Threads vs. Processes:** Threads are lightweight, allowing efficient context switching without OS intervention.  
- **Performance Benefits:** Multithreading reduces blocking and enhances parallel execution, especially on multiprocessor systems.  
- **Context Switching Costs:** Thread context switching is cheaper than process switching, benefiting system performance.  
- **User vs. Kernel Threads:** User-level threads provide efficiency, while kernel threads manage blocking more effectively.  
- **Virtualization Importance:** Virtualization enables portability and isolation of applications across different environments.  
- **Stateless vs. Stateful Servers:** Stateless servers enhance reliability, while stateful servers can improve performance through caching.  
- **Code Migration:** Moving code instead of data can address privacy issues and optimize resource usage in distributed systems.

### Key Insights -📊  
- **Thread Sharing:** Threads within the same process share memory space, which simplifies communication but increases error risk. This characteristic allows for faster inter-thread communication compared to inter-process communication.  
- **Blocking Behavior:** Multithreading can prevent a single-threaded process from blocking during I/O operations, significantly improving responsiveness in applications like web servers. This can lead to better resource utilization and user experience.  
- **Context Switching Dynamics:** The overhead of context switching can impact performance, particularly with CPU cache effects. Efficient context management is crucial for optimizing system throughput and minimizing latency.  
- **Kernel vs. User Space:** The choice between kernel-level and user-level threads involves trade-offs between performance and complexity, influencing how applications manage concurrency and responsiveness.  
- **Virtualization Techniques:** Virtualization allows for resource allocation and management across distributed systems, enhancing flexibility and scalability. This is vital for cloud computing applications, where resources must be dynamically allocated.  
- **Server Design Considerations:** The design of servers—whether stateful or stateless—affects their reliability and performance. Understanding these trade-offs is key for system architects when designing scalable services.  
- **Code Mobility Strategies:** The ability to migrate code rather than data can optimize performance and ensure compliance with data privacy regulations, highlighting the need for adaptable architectures in distributed systems.






### Processes and Threads

#### Introduction to Threads
**Basic Idea:**
Virtual processors are created in software on top of physical processors.

- **Processor:** Provides a set of instructions and the capability to automatically execute a series of those instructions.
- **Thread:** A minimal software processor that executes a series of instructions in its context. 
  - Saving a thread context involves stopping the current execution and storing all necessary data to resume later.
- **Process:** A software processor that can execute one or more threads. Executing a thread means running a sequence of instructions within the context of that thread.

#### Context Switching
**Contexts:**
- **Processor Context:** The minimal collection of values stored in the processor’s registers required to execute a series of instructions (e.g., stack pointer, addressing registers, program counter).
- **Thread Context:** The minimal collection of values stored in registers and memory required for thread execution (essentially the processor context plus its state).
- **Process Context:** The minimal collection of values stored in registers and memory required for thread execution, including additional information such as MMU (Memory Management Unit) register values.

#### Observations on Context Switching
1. **Threads:**
   - Share the same address space.
   - Thread context switching is lightweight and does not require operating system (OS) involvement.
2. **Processes:**
   - Process switching requires OS involvement, making it relatively more expensive (e.g., trapping to the kernel).
3. **Creation and Destruction:**
   - Threads are faster and cheaper to create and destroy compared to processes.

This text expands on the concepts of **processes**, **threads**, and their use cases, focusing on the benefits and observations about threads. Here's an organized explanation:

---

### Context Switching
**Definition of Contexts**:
1. **Processor Context**: Minimal data in processor registers required for executing instructions (e.g., stack pointer, program counter, addressing registers).
2. **Thread Context**: Extends processor context with memory state required for thread execution.
3. **Process Context**: Encompasses thread context plus additional data like MMU (Memory Management Unit) register values.

---

### Observations
1. **Threads**:
   - Share the same address space within a process.
   - Context switching is lightweight and can occur without OS intervention.
2. **Processes**:
   - Switching between processes requires OS involvement, which makes it resource-intensive.
3. **Thread Creation/Destruction**:
   - Less resource-intensive compared to process creation and destruction.

---

### Why Use Threads?
1. **Avoid Needless Blocking**:
   - A single-threaded process blocks during I/O operations, but multithreaded processes allow the OS to switch the CPU to another thread.
2. **Exploit Parallelism**:
   - Threads in a multithreaded process can run in parallel on multi-core or multi-processor systems.
3. **Avoid Process Switching**:
   - Large applications can be structured as multithreaded processes rather than multiple processes, reducing process switching overhead.



### **Trade-offs of Threads vs. Processes**
1. **Advantages of Threads**:
   - **Faster Context Switching**: Thread context switching is faster than process context switching.
   - **Efficiency**: Avoids expensive process-switching overhead.

2. **Disadvantages of Threads**:
   - **Shared Address Space**:
     - Threads share memory, which increases the risk of bugs (e.g., unintended overwrites).
   - **No Built-in Memory Protection**:
     - Threads lack OS or hardware support to prevent one thread from interfering with another's memory.

---

### **Cost of Context Switching**
1. **Direct Costs**:
   - Includes the time required for the actual context switch and executing the clock-interrupt handler code.

2. **Indirect Costs**:
   - Cache performance is affected due to switching, causing:
     - **Cache misses** when switching between contexts.
     - Re-loading of data (e.g., block D in the cache example), which slows performance.

---

### **Python Example: Multithreading with `multiprocessing`**

The provided code demonstrates the use of Python's `multiprocessing` module to create and run multiple threads (or processes) executing concurrently.

```python
from multiprocessing import Process
from time import sleep, gmtime
from random import randint

def sleeper(name):
    t = gmtime()
    s = randint(1, 20)
    txt = f"{t.tm_min}:{t.tm_sec} {name} is going to sleep for {s} seconds"
    print(txt)
    sleep(s)
    t = gmtime()
    txt = f"{t.tm_min}:{t.tm_sec} {name} has woken up"
    print(txt)

if __name__ == '__main__':
    p = Process(target=sleeper, args=('eve',))
    q = Process(target=sleeper, args=('bob',))
    p.start()
    q.start()
    p.join()
    q.join()
```

**Output Example**:
- Threads execute independently and concurrently:
  ```
  40:23 eve is going to sleep for 14 seconds
  40:23 bob is going to sleep for 4 seconds
  40:27 bob has woken up
  40:37 eve has woken up
  ```


## The concepts and trade-offs of implementing threads in operating systems, focusing on user-level threads, kernel-level threads, and a combined approach.

### Key Points:

1. **User-Level Threads**:
   - **Advantages**:
     - All operations are handled within a process, making implementations efficient.
     - No need for system calls, reducing overhead.
   - **Disadvantages**:
     - If the kernel blocks a thread, the entire process is blocked since the kernel is unaware of individual threads.
     - Handling external events is challenging because the kernel cannot signal specific threads.

2. **Kernel-Level Threads**:
   - **Advantages**:
     - The kernel manages thread blocking independently, allowing other threads within the process to continue execution.
     - Simplified handling of external events, as the kernel schedules threads linked to those events.
   - **Disadvantages**:
     - Requires system calls for thread operations, leading to efficiency loss.

3. **Combining User-Level and Kernel-Level Threads**:
   - Introduces a two-level threading model:
     - Kernel threads execute user threads.
     - A blocked kernel thread does not stop the process; another kernel thread can execute a different user thread.
   - **Operation**:
     - A user thread performing a system call blocks its associated kernel thread.
     - The kernel thread schedules other runnable user threads.
     - User-level context switching occurs when a user thread calls a blocking operation.
   - **Challenges**:
     - Increased complexity in the implementation.
     - Performance gains are not always significant enough to justify this complexity.

While mixing user-level and kernel-level threads offers theoretical benefits, the practical performance improvements often fail to outweigh the added complexity. Each approach has distinct advantages and is chosen based on the specific requirements of the operating system or application.


### Detailed Summary of Threads and Virtualization Concepts:

---

#### **User and Kernel Threads Combined**
- **Operation**:
  1. A user thread making a system call blocks its associated kernel thread, keeping the user thread bound to that kernel thread.
  2. If a user thread is runnable, the kernel can switch it to another kernel thread.
  3. A blocking user-level operation causes a context switch to another runnable user thread, while remaining bound to the same kernel thread.
  4. If no runnable user threads exist, a kernel thread might stay idle or be destroyed by the kernel.
  
---

#### **Threads in Clients**
- **Multithreaded Web Clients**:
  - **Purpose**: To hide network latency and improve user experience.
  - **Example**: A web browser scans an HTML page, spawns threads for fetching additional files via blocking HTTP requests, and displays the files as they arrive.

- **Remote Procedure Calls (RPC)**:
  - Threads enable multiple simultaneous request-response interactions with servers.
  - This can lead to linear speed-up when dealing with independent servers.

---

#### **Thread-Level Parallelism (TLP)**
- **Definition**: A measure of thread utilization efficiency:
  \[
  TLP = \frac{\sum_{i=1}^{N} i \cdot c_i}{1 - c_0}
  \]
  - \(i\): Number of threads executing simultaneously.
  - \(c_i\): Fraction of time \(i\) threads are running.
  - \(c_0\): Fraction of time no threads are running.
  - \(N\): Maximum number of threads.
  
- **Observation**: 
  - Typical TLP for web browsers ranges from **1.5 to 2.5**.
  - Threads are primarily used for logical organization rather than maximizing hardware utilization.

---

#### **Threads in Servers**
- **Performance Advantages**:
  - Cheaper to start threads than processes.
  - Multithreading allows scalability to multiprocessor systems.
  - Hides network latency by overlapping processing and response preparation.

- **Structural Benefits**:
  - High I/O demands benefit from simple blocking calls.
  - Simplified flow of control makes multithreaded programs smaller and more maintainable.

---

#### **Dispatcher/Worker Model**:
- **Comparison of Models**:
  - **Multithreading**: Offers parallelism with blocking system calls.
  - **Single-threaded Process**: No parallelism, blocking calls dominate.
  - **Finite-State Machine**: Parallelism achieved via non-blocking calls but requires complex design.

---

#### **Virtualization Concepts**:
- **Importance**:
  - Adapts to rapid hardware evolution.
  - Facilitates portability and code migration.
  - Enhances isolation for resilience against attacks or failures.

- **Principle**:
  - Virtualization mimics hardware interfaces, enabling multiple virtual machines to share the same physical resources.





### **Principle of Virtualization**
Virtualization enables multiple, isolated instances of computing environments or systems to run on shared physical hardware. The key principles include:

1. **Interface Mimicking**:
   - **Instruction Set Architecture (ISA)**: Divided into privileged and general instructions.
   - **System Calls**: Provided by the operating system.
   - **Library Calls**: APIs that applications use.

2. **Types of Virtualization**:
   - **Process VM**: Uses interpreters/emulators on an OS.
   - **Native VMM**: Minimal OS with low-level instructions.
   - **Hosted VMM**: Relies on a full-fledged OS but handles low-level instructions.

3. **Performance Considerations**:
   - **Privileged Instructions**: Cause traps when executed in user mode.
   - **Sensitive Instructions**:
     - **Control-Sensitive**: Affect machine configuration.
     - **Behavior-Sensitive**: Depend on execution context.

4. **Conditions for Virtualization**:
   - Virtualization is possible if sensitive instructions are a subset of privileged instructions.
   - **Challenges**: Some sensitive instructions don't trigger traps in user mode.
   - **Solutions**:
     - Instruction emulation.
     - Wrapping sensitive instructions to divert control to the VMM.
     - **Paravirtualization**: Modifies the guest OS.

### **Virtualization Techniques**
1. **Virtual Machines (VMs)**:
   - Abstract physical hardware, allowing multiple VMs on a single machine.
   - Applied to **cloud computing**, enabling:
     - **IaaS**: Infrastructure as a Service.
     - **PaaS**: Platform as a Service.
     - **SaaS**: Software as a Service.

2. **Containers**:
   - Lightweight, isolated environments for processes.
   - Technologies like **Namespaces**, **Union File Systems**, and **Control Groups** restrict resources and maintain separation.
   - Example: **PlanetLab**:
     - Uses **Vservers** for independent environments and slices for resource distribution across machines.

---

### **Applications**
1. **Cloud Computing**:
   - Utilizes VMs for customer isolation and flexibility.
   - VMs underpin distributed systems and cloud services.

2. **Client-Server Interaction**:
   - Networked interfaces facilitate middleware and application-level solutions.


### Processes and Clients
- **X Window System**: An example of a networked user interface where the application acts as a client to the X-kernel, which operates as a server.
- **Improving X**: 
  - Applications often mix logic and user-interface commands and can operate synchronously with the X-kernel.
  - Alternatives include allowing applications full control over display (e.g., VNC) or providing high-level display operations for efficiency.

### Virtual Desktop Environment
- With the rise of cloud applications, there’s a focus on creating seamless user experiences through web browsers (e.g., Google Chromebook).

### Client-Side Software
- Designed for distribution transparency:
  - **Access Transparency**: Uses client-side stubs for RPCs.
  - **Location/Migration Transparency**: Manages actual locations of services.
  - **Replication Transparency**: Handles multiple invocations via stubs.
  - **Failure Transparency**: Masks server and communication failures.

### Servers
- **General Organization**:
  - Servers implement specific services, handling incoming requests.
  - Types:
    - **Iterative Server**: Handles one request at a time.
    - **Concurrent Server**: Uses threads or processes to handle multiple requests, suitable for blocking operations.

- **Contacting a Server**:
  - Services typically use specific ports (e.g., FTP on ports 20/21).
  - Dynamic endpoint assignment can be achieved via approaches like DNS.

- **Out-of-Band Communication**:
  - Urgent messages can be handled using separate ports or transport layer facilities (e.g., TCP).

- **Stateless vs. Stateful Servers**:
  - **Stateless Servers**: Do not retain client state, which reduces state inconsistencies but may impact performance (e.g., inability to prefetch).
  - **Stateful Servers**: Retain client information, allowing optimizations like prefetching, leading to better performance.

### Object Servers
- Focus on activation policies and threading models to handle requests.
- Example of an object server implementation using the Ice runtime system in Python, demonstrating object registration and request handling.

### Server Clusters
- A common architecture to handle requests efficiently:
  - Crucial to manage request dispatching to avoid bottlenecks.
  - Using DNS for client transparency, ensuring clients remain unaware of distribution issues.



### **Processes in Code Migration**  
Code migration refers to the transfer of code and execution between systems, often driven by the following reasons:  

#### **Reasons to Migrate Code**
1. **Load Distribution**:
   - Ensures balanced server load in data centers to avoid energy wastage.
   - Minimizes communication latency by moving computations closer to the data source (e.g., in mobile computing).  
2. **Flexibility**:
   - Facilitates on-demand software deployment without requiring pre-installation, enabling dynamic configuration.  
3. **Privacy and Security**:
   - Addresses restrictions on data movement due to legal or security constraints by moving code instead of data (e.g., in federated machine learning).  

---

### **Paradigms and Models for Code Mobility**  
1. **Code Mobility Paradigms**:  
   - **Weak Mobility**:
     - Transfers only the **code** and **data segments** of a process.
     - Execution starts afresh at the destination.
     - Commonly involves *code shipping* (push) or *code fetching* (pull).
   - **Strong Mobility**:
     - Transfers the **code**, **data**, and the **execution state** (the running context).
     - Methods include:
       - **Migration**: Moves the complete process to another system.
       - **Cloning**: Creates a replica with the same execution state.



### **Migration in Heterogeneous Systems**  
1. **Challenges**:
   - Compatibility issues due to differences in hardware, operating systems, or runtime environments.
   - Variability in definitions of process/thread/processor contexts.  
2. **Solutions**:
   - Use **abstract machines** (e.g., virtual machines or interpreted languages) for platform independence.
   - Virtual Machine Monitors (VMMs) provide partial solutions but are limited by OS dependencies.



### **Virtual Machine (VM) Migration**  
1. **Methods**:
   - **Pushing Pages**:
     - Sends memory pages to the new VM and resends modified pages during migration.
   - **Stop-and-Copy**:
     - Stops the source VM, migrates its memory, and starts the destination VM.
   - **Demand Paging**:
     - Starts the destination VM immediately and copies memory pages as needed.
2. **Performance Concerns**:
   - Complete migrations can take several seconds, rendering services unavailable during the process.
   - Response time measurements show service interruptions during migration.


# Chapter 4
# Communication in Distributed Systems

## Foundations of Communication

### Basic Networking Model
- Focuses on message-passing.
- Drawbacks:
  - Often unneeded or unwanted functionality.
  - Violates access transparency.

### Layered Protocols
#### Low-Level Layers
- **Physical Layer**: Specifies and implements bit transmission.
- **Data Link Layer**: Manages framing for error and flow control.
- **Network Layer**: Handles packet routing in a computer network.
  - **Observation**: Many distributed systems use the network layer as the lowest-level interface.

#### Transport Layer
- **Importance**: Provides communication facilities for distributed systems.
- **Standard Internet Protocols**:
  - **TCP**: Connection-oriented, reliable, stream-oriented.
  - **UDP**: Unreliable, best-effort, datagram communication.

#### Middleware Layer
- Provides common services and protocols for diverse applications:
  - Rich communication protocols.
  - (Un)marshaling of data for integrated systems.
  - Naming and security protocols.
  - Scaling mechanisms like replication and caching.
- Application-specific protocols remain.

---

## Types of Communication

### Transient vs. Persistent Communication
- **Transient**: Messages discarded if undelivered.
- **Persistent**: Messages stored until successfully delivered.

### Synchronization Points
- At request submission.
- At request delivery.
- After request processing.

### Client/Server Communication
- **Observations**:
  - Transient synchronous communication.
  - Client and server must be active simultaneously.
  - Drawbacks:
    - Client blocked while waiting.
    - Failures handled immediately.
    - Not suitable for certain use cases (e.g., mail, news).

### Messaging
- **Message-Oriented Middleware**:
  - Enables high-level persistent asynchronous communication.
  - Processes send queued messages.
  - Middleware ensures fault tolerance.

---

## Remote Procedure Call (RPC)

### Basic RPC Operation
1. Client procedure calls client stub.
2. Stub builds message; calls local OS.
3. OS sends message to remote OS.
4. Remote OS gives message to server stub.
5. Stub unpacks parameters; calls server.
6. Server processes and returns result to stub.
7. Stub builds reply message; calls OS.
8. OS sends reply to client’s OS.
9. Client’s OS passes reply to client stub.
10. Client stub returns result to client.

### Parameter Passing in RPC
- Challenges:
  - Different data representations (e.g., byte ordering).
  - Encoding and decoding parameters.
  - **Copy-in/copy-out semantics**: Ensures independence during execution.
- Limitations:
  - Full access transparency not realizable.
  - Remote reference mechanisms enhance access transparency.

### Asynchronous RPC
- Allows client to proceed without waiting for server reply.

### Multiple RPCs
- Sending requests to multiple servers concurrently.

---

## Message-Oriented Communication

### Sockets
#### Berkeley Socket Interface
- Key Operations:
  - `socket`: Create a communication endpoint.
  - `bind`: Attach local address.
  - `listen`: Specify maximum pending requests.
  - `accept`: Block until connection request.
  - `connect`: Establish connection.
  - `send` and `receive`: Data transmission.
  - `close`: Release connection.

#### Example: Python Socket Code
- Server and client implementations using socket programming.

### Advanced Messaging with ZeroMQ
- Patterns:
  - Request-reply.
  - Publish-subscribe.
  - Pipeline.
- Code examples for each pattern.

### MPI
- Flexibility with operations:
  - `MPI_SEND`: Send message and wait.
  - `MPI_RECV`: Receive message.
  - Non-blocking options available (e.g., `MPI_ISEND`, `MPI_IRECV`).

### Queue-Based Messaging
- Operations:
  - `PUT`: Append message to queue.
  - `GET`: Block until queue is nonempty.
  - `POLL`: Non-blocking message retrieval.
  - `NOTIFY`: Trigger handler when new message arrives.
- **Message Broker**:
  - Handles heterogeneity by transforming message formats.
  - Provides subject-based routing for publish-subscribe models.



## Example: Advanced Message Queuing Protocol (AMQP)

### Overview
- Protocol for high-level messaging.
- Basic Model:
  - Stable connection contains one-way channels.
  - Channels form sessions for communication.

### Code Examples
#### Producer
- Creates exchanges and queues, binds them, and publishes messages.

#### Consumer
- Connects to queue, retrieves messages, and processes them.

