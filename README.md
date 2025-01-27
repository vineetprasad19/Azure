# Azure-Databricks
Azure Databricks is an Apache Spark-based analytics platform optimized for the Microsoft Azure cloud. It is a collaborative, cloud-based environment designed for data engineering, machine learning, and analytics workloads. Azure Databricks integrates seamlessly with Azure services like Azure Data Lake Storage, Azure SQL Database, Azure Machine Learning, and Power BI, making it a powerful tool for modern data processing and analytics.  

# What is Azure Databricks Used For? 
**Data Engineering:**  
Ingesting, cleaning, and transforming large datasets for further analysis.  
ETL (Extract, Transform, Load) processes at scale.  
Real-time and batch processing of data.  
**Data Science & Machine Learning:**  
Experimentation with machine learning models using distributed computing.  
Training large-scale machine learning models.  
Deploying models for real-time or batch inference.  
**Big Data Analytics:**  
Processing large-scale structured and unstructured datasets.  
Running SQL queries on massive datasets using Spark SQL.  
Creating interactive dashboards and visualizations.  
**Business Intelligence:**  
Enabling advanced analytics for decision-making.  
Integrating with Power BI for visualization of processed data.  
**Streaming Analytics:**  
Handling real-time data streams from IoT devices or event hubs.  
Building real-time analytics pipelines.  

**Steps**  
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

**1 What is databricks cluster**  
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

**2 Cluster Types**  
![image](https://github.com/user-attachments/assets/413b2984-4bfc-4a05-a085-73dab87d079f)

**3 cluster configuration**  
First, we have the option to choose whether we want to create a **Single Node** or a **Multi Node Cluster**.  
**Multi Node Cluster** will have one Driver Node and one or more Worker Nodes.  
When you run a Spark Job against a Multi Node Cluster, the Driver Node will distribute the tasks to run on the Worker Nodes in parallel, and returns the result.  
They give us the ability to horizontally scale the Cluster depending on your workload.We can basically keep adding Worker Nodes as we need.  
These are the default type of Clusters used for Spark Jobs and suitable for large workloads.  

On the other hand, S**ingle Node Cluster** will have only one node, which is the Driver Node and there are no Worker Nodes.  
Even though, there are no Worker Nodes, Single Node Clusters also supports Spark workloads.  
When you run a Spark Job, the Driver Node acts as both the driver and the worker. As there are no Worker node, the Single Node Clusters are not horizontally scalable, so they're not suitable for large ETL workloads. They're mainly targeted for lightweight Machine Learning and Data Analysis workloads which don't require, any distributed compute capacity.

We then need to define the **Access Mode.**  
There are **3 different types of Access Modes** available at the moment for the Cluster.  
As the name suggests, **Single User access** mode only allows a single user to access the Cluster. **It supports all four languages Python, SQL, Scala, and R**.  
**Shared access mode** allows the Cluster to be shared amongst more than one user, but it provides process isolation. Each process gets its environment, so one process can't see the data or the credential used by the other one.  
It's only available on premium workspaces. Also, **it only supports Python and SQL workloads.**  
**No Isolation Shared** also allows the Cluster to be shared amongst more than one user. It's available on both standard and premium workspaces. Also, **it supports all four languages Python, Scala, SQL and R.**  
The main difference between this and the Shard access mode is that, No Isolation Shared access mode doesn't provide any process isolation. So failure in one user's process may affect the others. Also, they don't offer any task preemption, so one running process may use all the resources and the others may fail.

And most importantly, as everything is shared, it's considered less secure. **Custom access mode** is not an option, when you create the Cluster using the latest user interface. You're only likely to see this if you have already created a Cluster using the **legacy configurations.** 

![image](https://github.com/user-attachments/assets/78c712b3-c00c-422c-9472-dc8fdce7fb27)

**Databricks runtimes**  
Databricks runtimes are the set of core libraries that run on Databricks Clusters.  
**Databricks Runtime, Databricks Runtime ML, Photon Runtime and Databricks Runtime Light.**  

Databricks Runtime includes an optimized version of Apache Spark Library. Java, Scala, Python and R Libraries, Ubuntu and its accompanying system Libraries, GPU Libraries for GPU enabled Clusters, Delta Lake Libraries and also other Libraries for Databricks services  that integrate with other components of the platform such as **Notebooks, Jobs and Cluster Manager.**  

**Databricks Runtime ML** includes all the libraries from the Databricks Runtime, plus the popular ML Libraries such as PyTorch, Keras, TensorFlow, XGBoost, etc..  

**Photon Runtime** also includes all the libraries from the Databricks runtime, plus the Photon Engine, which is the Databricks native vectorized query engine, that runs SQL workloads faster and reduces your cost per workload.  

**Databricks Runtime Light** is the runtime option for only jobs not requiring advanced features such as auto scaling, reliability and improved performance. Also, it's only suitable for Automated Workloads.  
You can't use it for Interactive Workloads or Notebook Jobs.  
Auto Termination is a nice feature that will avoid unnecessary costs on idle Clusters.  
It's especially useful on Ad-hoc clusters for preventing them, running during evenings and weekends when they're not in use.  
You can specify when to terminate your Databricks Cluster, if the cluster has not been in use. It will be terminated after the number of minutes specified.  

![image](https://github.com/user-attachments/assets/d982e44e-bc8c-4cd2-9299-cd51f98d8568)

Default value for **Auto Termination is 120 minutes**, but you can change the value.  
The accepted values range from 10 to 10000 minutes.  
When you create a Multi Node Cluster, you can specify the minimum and the maximum number of Worker Nodes.  
**Auto Scaling** will automatically add or remove nodes from the Cluster depending on your workload. This can result in optimum utilization of the Cluster.  
This is especially useful if you're unsure about the workload upfront or your workload changes throughout the process.  
They're not recommended for streaming workloads, even if specified Databricks defaults to the maximum number of Worker Nodes.  
There are a wide array of **Azure VM types** available for us to use.  
Databricks groups them into small number of easy to understand groups.  
**Memory Optimized instance types** are recommended for memory intensive applications. For example, a Machine Learning workload that caches a lot of data in memory.  
**Compute Optimized instance types** can be useful for structured streaming applications, where you need to make sure that the processing rate is above the input rate at peak times of the day.  
These can also be used for Distributed Analytics and Data Science Applications.  
**Storage Optimized instance types** are recommended for use cases requiring high disk throughput and I/O.  
**General Purpose instance types are** are recommended for Enterprise Grade applications and analytics with In-memory caching.  
**GPU Accelerated instance types** are recommended for Deep Learning Models, that are data and compute intensive.  
**Cluster Policy Configuration** This could easily overwhelm a Data Engineer or a Machine Learning Engineer, and creating Clusters become the sole responsibility of the administrator. Because it's too difficult to configure for a Standard Data Engineer or a Machine Learning Engineer. Also, without careful consideration, users could accidentally create Clusters which are oversized and too expensive to run. Cluster Policies help us avoid these common issues. Administrators can create Cluster policies with restrictions, and assign them to users or groups. When a Cluster Policy is selected, the configuration becomes much more simplified. In summary, Cluster policies simplify the user interface, thus enabling standard users to create Clusters and take away the need for administrators to be involved in every decision. And most importantly, it achieves cost control by limiting the maximum size of the Clusters. But please note that this is only available on premium tier.  

Hope you now have a good understanding about the **configurations** you can specify for a Cluster.  

**4 Creating Databricks Cluster**  

![image](https://github.com/user-attachments/assets/7724b84a-e4e6-4236-a2ab-5a316527ae73)

![image](https://github.com/user-attachments/assets/ed38e93a-607d-475f-9b72-39050d569ef1)

![image](https://github.com/user-attachments/assets/81a49047-66bc-456f-a6b8-90046ac44b4e)

**5 Cluster Pools**  
A Cluster Pool is basically a set of idle ready to use virtual machines, that allow us to reduce the Cluster start and Auto Scaling times.  
For example, let's assume that we have created a Pool with a minimum of 1 idle instance and 2 maximum instances. What this means, is the pool will always keep at least one instance ready for Clusters to consume until, it reaches the maximum limit, which is two in this case. Let's say Cluster 1 comes along and requests for one node. Pool gives the one instance to the Cluster and spins up another one ready.  
If Cluster 2 requests for one more node, then it gives that one to the Cluster 2. But instead, if Cluster 2 requests for two more, it will fail to start with error that there are enough instances available to allocate.  

![image](https://github.com/user-attachments/assets/1929ea4c-423b-4de9-b843-9512645db4bb)

![image](https://github.com/user-attachments/assets/3a87b8fe-c7f1-4f60-bb74-d9ef8d24aced)

**6 Cluster Policy**  
Creating the wrong type of Cluster could increase the cost of running the project and also can affect data security. So if we expect standard users to create the Cluster and keep the cost down, we should simplify the interface and make it easier for them.
That's where Cluster Policies come in. Policies are basically a set of rules which allows us to hide or take out the configuration options, that are not required on the user interface. They allow us to fix the values of some of the configuration parameters and restrict access for the users so that they're not changing them. Also, in a set of values, a policy allows us to select default values on the user interface.
An administrator can create a policy and assign that to a set of users. When the user chooses the policy, they'll now have a Simpler User Interface because some of the options are now hidden or pre-populated with fixed values. Only allowing the users to select certain type of nodes or setting Auto Termination by Default, allows us to keep the cost down.
It helps us having standard type of Clusters created by all users in a specific group. And finally, cluster policies take away the need for an administrator to be involved in every cluster creation decision and empowers standard users to create them.

![image](https://github.com/user-attachments/assets/4f63ae81-449e-4f05-82d6-fa11639518c9)

![image](https://github.com/user-attachments/assets/c95eea7d-b6b9-43e5-ac37-42f2d86d3a00)

![image](https://github.com/user-attachments/assets/ec114ff6-70d1-4fba-80b5-7f334f6ba5fd)

# Databricks Notebooks  

We are going to see below things, 
1. What's a notebooks  
2. Creating a notebook  
3. Magic commands  
4. Databricks utilities  

**1. What's a notebooks**  
A notebook is a collection of cells, that run commands on a Databricks Cluster.  

**2. Creating a notebook**  

![image](https://github.com/user-attachments/assets/3b692fd5-bfe9-4ba2-937b-848a440f699d)

**You can Export in**  
![image](https://github.com/user-attachments/assets/0be68078-3e2f-42d9-af65-fd3d97c170f9)

**Notebook formats**  

You can export the notebook in any of these four format specified here. If you're not familiar with the DBC file format, that's the Databricks Binary File format, which allows us to export not only individual notebooks, you can also export the entire folder and also it can contain any types of files in it. And you can then import that DBC file into another Databricks workspace or within the same Databricks workspace into another folder later. So that's really really useful, if you're working with Databricks. If you choose the Source file format, each notebook will be exported as separate files in Source file format.  
For example, . py for this notebook, as it's a Python Notebook.  
If you had a SQL notebook, you will have a file with the extension of .SQL.  
IPython will export the file in IPython format. By default notbooks are in Python format.  
Finally, HTML will export as a single HTML file for each of the notebook. Edit menu gives you the standard edit options such as cut, copy, paste and things like that.  
And also, if you're working with Python, you have the option here to set your indentation to be two spaces or four spaces depending on your preference. And View, lets you view your notebook in different ways.  
![image](https://github.com/user-attachments/assets/f60fcd9e-7aa9-43eb-97bb-296b088353f3)

**Notebooks Keyboard Shortcuts**  
![image](https://github.com/user-attachments/assets/0290e01d-e15d-4100-98a0-8e3a94a2b3dd)

**3. Magic commands**  
The primary purpose of the Magic Commands, is to override the default language in a Notebook. For example, you may want to switch from Python to Scala within the same notebook. There are also some auxiliary magic commands which allow us to create documentation in our notebooks and access the file system, etc..  

As we know, the default language for this notebook is Python. And let's say I want to run a SQL statement, so let me try that. And as you can see here, we've got an error saying invalid syntax.  
That's because, Python doesn't know how to execute a SQL statement. So we need to execute this as a SQL statement. So in order to do that, Databricks offers something called a Magic Command.  
So you just have to specify a **%SQL** and then run the Select statement. Now, the context of this cell alone has changed from **Python to SQL**.  
However now if you just write **Select * ,the notebook** automatically recognize that this is SQL language and it changes the notebook **language to SQL**.  

![image](https://github.com/user-attachments/assets/6e182794-0798-4bc5-b96d-f4576c667142)

Similarly, if you wanted to run a Scala statement, you would use the magic command **%Scala**  
Apart from being able to switch between these four languages, Databricks also offers few auxiliary magic commands, which are quite handy.  
**%md** So this gives you the ability to document your notebook quite nicely and make it usable for everyone, particularly someone not familiar with this notebook. You can also embed HTML images, etc., which is really good.  

**file system magic command, which is percentage %fs.**  
![image](https://github.com/user-attachments/assets/98f92c64-5ee4-40e3-a74c-b34345b15115)

**Finally, the last magic command I want to talk you through is the Shell command %sh.**  
Let's say we want to see all the processes that are running. I can just use the ps command to do that. And that's showing us all the processes that are running in this Cluster.  
![image](https://github.com/user-attachments/assets/fd577964-b872-478f-b213-28dee4ddc1e4)

**4. Databricks utilities**  
Databricks Utilities make it easier to combine different types of tasks in a Single notebook. For example, they allow us to combine file operations with ETL tasks.
These utilities can only be run from Python, Scala or R cells in a Notebook. They cannot be run from a SQL cell.
Databricks have been coming up with a number of utilities recently. Some are in preview and others are available for general availability. Amongst those, the following are the most commonly used utilities.
Secrets Utilities allow us to get secret values from secrets, which are stored in secret scopes backed by Databricks or Azure Key Vault. Widget Utilities allows us to parameterized notebooks so that a calling notebook or another application, for example, a Data Factory Pipeline can pass a parameter value to the notebook at runtime. This is really useful to make a notebook reusable. Notebook Workflow Utilities allow us to invoke one notebook from another and chain them together.

![image](https://github.com/user-attachments/assets/ecceb684-4e79-41f1-bd16-b19314011c74)

![image](https://github.com/user-attachments/assets/7264a2b8-3706-4c4d-ad26-7f8f01b8bd89)

If you ask me when to use the %fs command and when to use the dbutils package, I tend to use %fs magic command if I'm doing some ad-hoc queries, and I use the dbutils.fs package if I'm doing something programmatically like this. So far we've only been working with Python, but you can do the same with Scala and R, but you can't do this with SQL.  

![image](https://github.com/user-attachments/assets/242f5026-d6dd-4682-86f9-5025619d7030)

![image](https://github.com/user-attachments/assets/2781a389-5969-4972-80a3-5106777b3db6)
