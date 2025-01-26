# Azure-Databricks
Azure Databricks

Create Azure Account
Create Resouce group
Create Work Space

![image](https://github.com/user-attachments/assets/2e2440ab-0a85-47e8-a9e4-5a76e1a40fc2)

Once the Resource is created, pin it to the dashboard. 
![image](https://github.com/user-attachments/assets/369ec083-de3f-4bbb-b4d4-d92b94d0da2a)

Go back in the dashbaord and databricks and launch it.
![image](https://github.com/user-attachments/assets/f421c3a7-3f91-427c-889c-e2156477308d)

**Azure Databricks Architecture**  
![image](https://github.com/user-attachments/assets/1a03dfc7-68ec-455e-886a-f11709f78e9b)

![image](https://github.com/user-attachments/assets/a6b6db04-8649-4d89-8b21-cf2eb3fd5249)

# Databricks Clusters  
1. What is databricks cluster  
2. Cluster types  
3. cluster configuration  
4. creating a cluster
5. cluster pools
6. cluster policy

**What is databricks cluster**  
It is a distributed computing system designed to efficiently process large-scale data. Databricks clusters are highly configurable and can automatically scale to accommodate workload requirements.  

Key Components of a Databricks Cluster:  
**Driver Node:**  
Orchestrates the execution of tasks and manages the distribution of work across worker nodes.  
Responsible for managing the cluster state and communicating with the Databricks control plane.  
**Worker Nodes:**  
Perform the actual computation and data processing tasks.  
Each worker node has a set of executors that execute the tasks assigned by the driver node.  
**Cluster Manager:**  
Allocates resources across the nodes and monitors cluster health.  
Ensures that tasks are scheduled efficiently.  
**Databricks Runtime:**  
Includes Apache Spark and additional libraries optimized for Databricks.  
Pre-configured to support common data science and engineering workflows.  

![image](https://github.com/user-attachments/assets/8f198209-1d10-4f39-80a6-9c83b23b1d3b)

**Cluster Types**  
![image](https://github.com/user-attachments/assets/413b2984-4bfc-4a05-a085-73dab87d079f)

