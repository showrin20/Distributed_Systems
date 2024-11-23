
# [Above the Clouds: A Berkeley View of Cloud Computing](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2009/EECS-2009-28.html)

### **Question 1: What is Cloud Computing, and what are its main features?**

**Answer:**  
Cloud Computing is a system where **applications** are delivered as services over the Internet, and the necessary hardware and **datacenters** reside in the cloud. Its main features are:  

1. **Elasticity:** Resources can be scaled up or down based on demand.  
2. **Pay-as-you-go Model:** Costs are incurred based on the usage of resources.  
3. **Scalability:** Systems can grow or shrink easily to handle changing workloads.  
4. **Utility Computing:** Resources are rented in public clouds.  

### **Question 2: What is the difference between Public Cloud and Private Cloud?**

**Answer:**  
- **Public Cloud:**  
  Open to the general public, with resources available on a pay-as-you-go basis.  
  **Examples:** Amazon Web Services (AWS), Google AppEngine.  

- **Private Cloud:**  
  Designed for exclusive use by a single organization and not accessible to the public.  
  **Examples:** Data storage for banks or healthcare organizations.  

### **Question 3: What is Elasticity, and why is it important?**

**Answer:**  
**Elasticity** in Cloud Computing refers to the ability to quickly scale resources up or down as needed.  
**Importance:**  
1. Prevents waste by reducing unused resources.  
2. Accommodates sudden increases in demand.  
3. Helps control costs efficiently.  

### **Question 4: What are the Top 10 Obstacles to Cloud Computing?**

**Answer:**  
1. **Availability of Service:** Ensuring consistent service uptime.  
2. **Data Lock-in:** Difficulty in transferring data between providers.  
3. **Data Confidentiality:** Security and compliance concerns.  
4. **Data Transfer Bottlenecks:** High time and costs for large data transfers.  
5. **Performance Unpredictability:** Variability in system performance.  
6. **Scalable Storage:** Lack of advanced storage solutions.  
7. **Bugs in Distributed Systems:** Errors in large-scale systems.  
8. **Scaling Quickly:** Challenges in rapid scaling.  
9. **Reputation Fate Sharing:** Dependence on shared infrastructure.  
10. **Software Licensing:** Need for pay-as-you-go licensing models.  

### **Question 5: When is Utility Computing more effective than Private Cloud?**

**Answer:**  
Utility Computing is more effective in scenarios such as:  

1. **Variable Demand:** When demand fluctuates over time.  
   **Example:** E-commerce websites during the holiday season.  

2. **Unknown Demand:** When future demand cannot be predicted.  
   **Example:** Launching a new application.  

3. **Batch Processing:** For analyzing large datasets efficiently.  
   **Example:** Running simulations or data analytics.  

### **Question 6: What is the difference between Amazon EC2 and Google AppEngine?**

**Answer:**  

1. **Amazon EC2:**  
   - Operates like physical hardware.  
   - Allows users full control over the software stack.  
   - Offers limited automatic scaling.  

2. **Google AppEngine:**  
   - Provides automatic scaling capabilities within a specific structure.  
   - Separates **stateless** and **stateful** storage.  
   - Best suited for standard web applications.  

### **Question 7: Why is Cloud Computing so popular now?**

**Answer:**  

1. **Large Datacenters:** The ability to build massive datacenters has improved.  
2. **Technology Trends:** The rise of Web 2.0 has made cloud technology accessible.  
3. **Cost Efficiency:** Capital expenses (CapEx) are converted to operational expenses (OpEx).  
4. **New Business Models:** The **pay-as-you-go** model has gained acceptance.  

### **Question 8: What kind of economic model is used in Cloud Computing?**

**Answer:**  

**Pay-as-you-go Model:**  
1. Users pay for resources as they consume them.  
2. **Elasticity** reduces costs by avoiding unused resources.  
3. **Risk Transfer:** Shifts risks of over or under-provisioning to the cloud provider.  

### **Question 9: What are the challenges in achieving Scalability?**

**Answer:**  

1. Systems may not scale up or down quickly.  
2. Lack of automation tools for scaling.  
3. Need for **Machine Learning-based Autoscalers** to predict and manage scaling effectively.  

### **Question 10: How can Data Transfer Bottlenecks be resolved?**

**Answer:**  

1. **FedEx Disks:** Shipping hard drives for large data transfers.  
2. **Optimized Data Placement:** Strategically placing data close to where it is needed.  
3. **Cheaper WAN Bandwidth:** Developing cost-effective wide-area network solutions.  
