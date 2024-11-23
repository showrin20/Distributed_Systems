
# [**Event-Driven Architecture: Best Practices, Pitfalls, and Lessons Learned**](https://www.youtube.com/watch?v=A_mstzRGfIE)


## **Introduction:**

### **Presenter:**  
- **Name:** Tim Berglund  
- **Role:** Developer Advocate Team Lead at Confluent  
- **Experience:** Specializes in Apache Kafka and event-driven systems.  
- **Event:** Devoxx Poland  
- **Background Context:**  
  - Tim shares insights gained from working with Apache Kafka and helping developers adopt Event-Driven Architecture (EDA) in real-world systems.  
  - This presentation is based on practical experience, lessons learned, and recurring patterns observed in the industry.  

## **Purpose of the Talk:**  
- To explore **Event-Driven Architecture (EDA):**
  - What it is and why it matters.  
  - Common mistakes developers make when implementing EDA.  
  - Practical lessons to ensure success with EDA systems.  

- The talk also touches on:  
  - When **not** to use EDA.  
  - Best practices for avoiding pitfalls.  


## **What is Event-Driven Architecture (EDA)?**

### **Definition:**  
EDA is a system design paradigm where software components communicate through **events** instead of direct calls or shared databases.  

### **Key Characteristics:**  
1. **Asynchronous Communication:**  
   - Components interact via event logs, avoiding synchronous dependencies.  
   - Improves scalability and fault tolerance.  

2. **Decoupled Microservices:**  
   - Each service handles its own logic and data, communicating indirectly through events.  
   - Reduces interdependencies and facilitates independent scaling.  

3. **Durable Logs:**  
   - A log acts as a **system of record**, capturing all events over time.  
   - Example: Kafka topics are durable logs that retain all events for reprocessing and analysis.  

### **Reference Example: An E-Commerce System**  
The architecture includes microservices for Orders, Users, Payments, and Shipping:  

- **Order Service:** Validates orders and writes them to an event log (e.g., Kafka topic).  
- **Payment Service:** Consumes events from the order log, processes payments, and writes payment status to another log.  
- **Shipping Service:** Listens to the payment log, fetches user details asynchronously, and fulfills orders.  

This structure enables asynchronous workflows, where each service processes events independently, ensuring scalability and resilience.  


## **Benefits of Event-Driven Architecture:**

1. **Scalability:**  
   - Each service can scale independently based on workload.  

2. **Resilience:**  
   - Asynchronous communication reduces the impact of failures in one service on others.  

3. **Flexibility:**  
   - Durable logs allow events to be replayed for debugging, reprocessing, or analytics.  

4. **Decentralized Data Ownership:**  
   - Services maintain local databases for their own use, ensuring data autonomy and reducing shared dependencies.  


## **Five Common Pitfalls in EDA and How to Avoid Them**

### **Pitfall 1: Using EDA When It's Not Needed**  
- **Problem:**  
  - Overcomplicating simple systems with unnecessary event-driven architecture.  

- **Solution:**  
  - Use a monolithic architecture for:  
    - Small systems with low complexity.  
    - Projects where requirements are unclear, or the system is expected to evolve.  

- **Key Insights:**  
  - "Monolith" doesn’t mean bad. It can be appropriate for small-scale systems.  
  - Avoid the temptation to break a small project into microservices unnecessarily.  

### **Pitfall 2: Avoiding Databases Entirely**  
- **Problem:**  
  - Misconception that event-driven systems eliminate the need for databases.  
  - Leads to overly complex state management within services.  

- **Solution:**  
  - Databases are still crucial for specific views and key lookups.  
  - Use tools like **Change Data Capture (CDC)** to synchronize traditional databases with event logs.  

- **Key Insights:**  
  - Event logs (e.g., Kafka topics) act as the **system of record**, but databases serve as **views** of that record.  
  - Avoid building distributed state management solutions yourself; use frameworks like **Kafka Streams** for this purpose.  

### **Pitfall 3: Neglecting Schema Management**  
- **Problem:**  
  - Poorly managed or inconsistent schemas can lead to compatibility issues and downstream failures.  

- **Solution:**  
  - Adopt tools like **Schema Registry** to manage schema evolution and versioning.  
  - Treat schema as a first-class concern to ensure compatibility between producers and consumers.  

- **Key Insights:**  
  - Schemas are essential for maintaining compatibility as systems evolve.  
  - Schema Registry ensures a smooth evolution of event formats without breaking consumers.  

### **Pitfall 4: Over-Customizing Consumers**  
- **Problem:**  
  - Writing custom code for consuming events can lead to unmanageable complexity.  

- **Solution:**  
  - Use frameworks like **Kafka Streams** or **KSQL DB** for handling aggregations, joins, and stateful operations.  

- **Key Insights:**  
  - Avoid over-engineering consumers with custom logic for state management.  
  - Let specialized tools handle the complexities of state and time management.  

### **Pitfall 5: Underestimating Scalability Challenges**  
- **Problem:**  
  - Failing to plan for scaling storage and compute independently.  

- **Solution:**  
  - Use **tiered storage** for cost-effective handling of historical data.  
  - Design systems to scale compute resources elastically based on demand.  

- **Key Insights:**  
  - Scaling compute and storage are distinct challenges that require separate solutions.  
  - Use managed services (e.g., **Confluent Cloud**) to simplify scaling operations.  

---

## **Practical Lessons for Successful EDA Implementation:**

1. **Durable Logs as System of Record:**  
   - Event logs capture the authoritative history of events.  
   - Databases are derived views of this log.  

2. **Distributed State Management:**  
   - Avoid custom solutions for state management.  
   - Use built-in frameworks like Kafka Streams for managing state across distributed systems.  

3. **Elastic Scalability:**  
   - Design systems to scale horizontally by adding more nodes.  
   - Use cloud storage (e.g., AWS S3) for older data to reduce costs.  

4. **Schema Evolution:**  
   - Ensure that schemas are versioned and compatible to support long-term system evolution.  

## **Best Practices:**

1. **Start Small:**  
   - Begin with simple architectures and evolve into EDA as complexity grows.  

2. **Embrace Managed Services:**  
   - Use cloud-based solutions (e.g., **Confluent Cloud**) to offload operational burdens.  

3. **Balance "Events" and "Things":**  
   - Prioritize "what happens" (events) but don’t neglect "what is" (state).  

4. **Adopt Tiered Storage:**  
   - Use low-cost storage solutions for older data while keeping recent data in high-performance systems.  


## **When to Avoid Event-Driven Architecture:**

1. **For Small, Simple Systems:**  
   - Low-complexity systems can work well with a single database and a monolithic design.  

2. **In High-Uncertainty Projects:**  
   - Avoid EDA when requirements are unclear; instead, build incrementally and iterate.  

## **Key Tools for EDA:**

1. **Kafka and Kafka Streams:** For event streaming and processing.  
2. **KSQL DB:** SQL-based interface for querying event streams.  
3. **Schema Registry:** For managing schema evolution and compatibility.  
4. **Change Data Capture (CDC):** For integrating traditional databases with event logs.  

## **Takeaways:**

- Event-Driven Architecture is a powerful design paradigm but not universally applicable.  
- Success lies in balancing simplicity, scalability, and schema management.  
- Managed services and existing tools can reduce complexity and operational burden.
  
![mindmap](mind.png)
