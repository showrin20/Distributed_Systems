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



# Chapter 1


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
