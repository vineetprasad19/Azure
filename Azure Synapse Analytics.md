# What is Azure Synapse Analytics  

The technological research and consulting firm Gartner defines four common types of analytical technique that organizations commonly use:  
**Descriptive analytics**, which answers the question “What is happening in my business?”. The data to answer this question is typically answered through the creation of a data warehouse in which historical data is persisted in relational tables for multidimensional modeling and reporting.  
**Diagnostic analytics**, which deals with answering the question “Why is it happening?”. This may involve exploring information that already exists in a data warehouse, but typically involves a wider search of your data estate to find more data to support this type of analysis.  
**Predictive analytics**, which enables you to answer the question “What is likely to happen in the future based on previous trends and patterns?"  
**Prescriptive analytics**, which enables autonomous decision making based on real-time or near real-time analysis of data, using predictive analytics.  

![image](https://github.com/user-attachments/assets/cc1d6d61-14b4-4006-a06b-0a68741469c6)

Azure Synapse Analytics provides a cloud platform for all of these analytical workloads through support for multiple data storage, processing, and analysis technologies in a single, integrated solution. The integrated design of Azure Synapse Analytics enables organizations to leverage investments and skills in multiple commonly used data technologies, including SQL, Apache Spark, and others; while providing a centrally managed service and a single, consistent user interface.  

# How Azure Synapse Analytics works    
To support the analytics needs of today's organizations, Azure Synapse Analytics combines a centralized service for data storage and processing with an extensible architecture through which linked services enable you to integrate commonly used data stores, processing platforms, and visualization tools.  

# Creating and using an Azure Synapse Analytics workspace  
A **Synapse Analytics workspace** defines an instance of the Synapse Analytics service in which you can manage the services and data resources needed for your analytics solution. You can create a Synapse Analytics workspace in an Azure subscription interactively by using the Azure portal, or you can **automate deployment by using Azure PowerShell**, the Azure command-line interface (CLI), or with an Azure Resource Manager or Bicep template.  

After creating a Synapse Analytics workspace, you can manage the services in it and perform data analytics tasks with them by using **Synapse Studio**; a web-based portal for Azure Synapse Analytics.
![image](https://github.com/user-attachments/assets/c7d72f2b-187a-4439-ba36-a4fa81f7d5b9)

# Working with files in a data lake  
One of the core resources in a Synapse Analytics workspace is a data lake, in which data files can be stored and processed at scale. A workspace typically has a default data lake, which is implemented as a linked service to an Azure Data Lake Storage Gen2 container. You can add linked services for multiple data lakes that are based on different storage platforms as required.  
![image](https://github.com/user-attachments/assets/c27ac063-aa47-4cca-a1de-e2a310145e5e)

# Ingesting and transforming data with pipelines
In most enterprise data analytics solutions, data is extracted from multiple operational sources and transferred to a central data lake or data warehouse for analysis. Azure Synapse Analytics includes built-in support for creating, running, and managing pipelines that orchestrate the activities necessary to retrieve data from a range of sources, transform the data as required, and load the resulting transformed data into an analytical store.  
![image](https://github.com/user-attachments/assets/88b73b16-0906-490e-b009-31aca75bed0c)

**Note:** Pipelines in Azure Synapse Analytics are based on the same underlying technology as Azure Data Factory. If you are already familiar with Azure Data Factory, you can leverage your existing skills to build data ingestion and transformation solutions in Azure Synapse Analytics.  

# Querying and manipulating data with SQL
Structured Query Language (SQL) is a ubiquitous language for querying and manipulating data, and is the foundation for relational databases, including the popular Microsoft SQL Server database platform. Azure Synapse Analytics supports SQL-based data querying and manipulation through two kinds of SQL pool that are based on the SQL Server relational database engine:  

A built-in serverless pool that is optimized for using relational SQL semantics to query file-based data in a data lake.  
Custom dedicated SQL pools that host relational data warehouses.  

The Azure Synapse SQL system uses a distributed query processing model to parallelize SQL operations, resulting in a highly scalable solution for relational data processing. You can use the built-in serverless pool for cost-effective analysis and processing of file data in the data lake, and use dedicated SQL pools to create relational data warehouses for enterprise data modeling and reporting.  
![image](https://github.com/user-attachments/assets/1c88fd1c-33d9-4c3a-adf2-ec7a558cdf61)

# Processing and analyzing data with Apache Spark  
Apache Spark is an open source platform for big data analytics. Spark performs distributed processing of files in a data lake by running jobs that can be implemented using any of a range of supported programming languages. Languages supported in Spark include Python, Scala, Java, SQL, and C#.  

In Azure Synapse Analytics, you can create one or more Spark pools and use interactive notebooks to combine code and notes as you build solutions for data analytics, machine learning, and data visualization.  
![image](https://github.com/user-attachments/assets/5f0d447a-fadd-4cfb-8863-bce98f7a8dec)

# Exploring data with Data Explorer
Azure Synapse Data Explorer is a data processing engine in Azure Synapse Analytics that is based on the Azure Data Explorer service. Data Explorer uses an intuitive query syntax named **Kusto Query Language (KQL)** to enable high performance, low-latency analysis of batch and streaming data.  
![image](https://github.com/user-attachments/assets/071dc2c4-38df-4589-a3e9-0acf4a64a99e)

# Integrating with other Azure data services
Azure Synapse Analytics can be integrated with other Azure data services for end-to-end analytics solutions. Integrated solutions include:  

**Azure Synapse Link** enables near-realtime synchronization between operational data in Azure Cosmos DB, Azure SQL Database, SQL Server, and Microsoft Power Platform Dataverse and analytical data storage that can be queried in Azure Synapse Analytics.  
**Microsoft Power BI** integration enables data analysts to integrate a Power BI workspace into a Synapse workspace, and perform interactive data visualization in Azure Synapse Studio.  
**Microsoft Purview** integration enables organizations to catalog data assets in Azure Synapse Analytics, and makes it easier for data engineers to find data assets and track data lineage when implementing data pipelines that ingest data into Azure Synapse Analytics.  
**Azure Machine Learning** integration enables data analysts and data scientists to integrate predictive model training and consumption into analytical solutions.  

# When to use Azure Synapse Analytics
![image](https://github.com/user-attachments/assets/42f6d350-191a-4242-b860-0ceb59f02a23)

# Understand data streams
A data stream consists of a perpetual series of data, typically related to specific point-in-time events. For example, a stream of data might contain details of messages submitted to a social media micro-blogging site, or a series of environmental measurements recorded by an internet-connected weather sensor. Streaming data analytics is most often used to better understand change over time. For example, a marketing organization may perform sentiment analysis on social media messages to see if an advertising campaign results in more positive comments about the company or its products, or an agricultural business might monitor trends in temperature and rainfall to optimize irrigation and crop harvesting.  

Common goals for stream analytics include  

Continuously analyzing data to report issues or trends.  
Understanding component or system behavior under various conditions to help plan future enhancements.  
Triggering specific actions or alerts when certain events occur or thresholds are exceeded.  
![image](https://github.com/user-attachments/assets/d2c9db53-c8c3-4f2e-aa3f-b05da4326620)

# Understand event processing 
![image](https://github.com/user-attachments/assets/dc135841-d729-4984-91bd-db5495761d76)

# Azure Stream Analytics jobs and clusters
The easiest way to use Azure Stream Analytics is to create a Stream Analytics job in an Azure subscription, configure its input(s) and output(s), and define the query that the job will use to process the data. The query is expressed using structured query language (SQL) syntax, and can incorporate static reference data from multiple data sources to supply lookup values that can be combined with the streaming data ingested from an input.  
  
If your stream process requirements are complex or resource-intensive, you can create a Stream Analysis cluster, which uses the same underlying processing engine as a Stream Analytics job, but in a dedicated tenant (so your processing is not affected by other customers) and with configurable scalability that enables you to define the right balance of throughput and cost for your specific scenario.  

**Inputs**  
Azure Stream Analytics can ingest data from the following kinds of input:  
Azure Event Hubs  
Azure IoT Hub  
Azure Blob storage  
Azure Data Lake Storage Gen2  

Inputs are generally used to reference a source of streaming data, which is processed as new event records are added. Additionally, you can define reference inputs that are used to ingest static data to augment the real-time event stream data. For example, you could ingest a stream of real-time weather observation data that includes a unique ID for each weather station, and augment that data with a static reference input that matches the weather station ID to a more meaningful name.  

**Outputs**
Outputs are destinations to which the results of stream processing are sent. Azure Stream Analytics supports a wide range of outputs, which can be used to:  
Persist the results of stream processing for further analysis; for example by loading them into a data lake or data warehouse.  
Display a real-time visualization of the data stream; for example by appending data to a dataset in Microsoft Power BI.  

Generate filtered or summarized events for downstream processing; for example by writing the results of stream processing to an event hub.  

If you need to load the results of your stream processing into a table in a dedicated SQL pool, use an Azure Synapse Analytics output. The output configuration includes the identity of the dedicated SQL pool in an Azure Synapse Analytics workspace, details of how the Azure Stream Analytics job should establish an authenticated connection to it, and the existing table into which the data should be loaded.  
  
Authentication to Azure Synapse Analytics is usually accomplished through SQL Server authentication, which requires a username and password. Alternatively, you can use a managed identity to authenticate. When using an Azure Synapse Analytics output, your Azure Stream Analytics job configuration must include an Azure Storage account in which authentication metadata for the job is stored securely.  

If you need to write the results of stream processing to an Azure Data Lake Storage Gen2 container that hosts a data lake in an Azure Synapse Analytics workspace, use a Blob storage/ADLS Gen2 output. The output configuration includes details of the storage account in which the container is defined, authentication settings to connect to it, and details of the files to be created. You can specify the file format, including CSV, JSON, Parquet, and Delta formats. You can also specify custom patterns to define the folder hierarchy in which the files are saved - for example using a pattern such as YYYY/MM/DD to generate a folder hierarchy based on the current year, month, and day.  
  
You can specify minimum and maximum row counts for each batch, which determines the number of output files generated (each batch creates a new file). You can also configure the write mode to control when the data is written for a time window - appending each row as it arrives or writing all rows once (which ensures "exactly once" delivery).  

# Queries
![image](https://github.com/user-attachments/assets/b80622b8-9291-4567-868a-b3851d2e86f0)

# Understand window functions
A common goal of stream processing is to aggregate events into temporal intervals, or windows. For example, to count the number of social media posts per minute or to calculate the average rainfall per hour.  
  
Azure Stream Analytics includes native support for five kinds of temporal windowing functions. These functions enable you to define temporal intervals into which data is aggregated in a query. The supported windowing functions are Tumbling, Hopping, Sliding, Session, and Snapshot.  

# Tumbling
![image](https://github.com/user-attachments/assets/21f83f48-4f1c-407e-b02b-5e9b2264c0de)

# Hopping
![image](https://github.com/user-attachments/assets/2b121f11-7979-4234-9007-f83b571a20fa)

# Sliding
![image](https://github.com/user-attachments/assets/879c6d9a-949c-4235-a47c-a193933ad823)

# Session
![image](https://github.com/user-attachments/assets/b0bc7ccd-195c-4029-ba5b-6f9e835d308e)

# Snapshot
![image](https://github.com/user-attachments/assets/aa8d9949-987f-4570-bdf2-0fcc3721f264)

# Data lakes in Azure Synapse Analytics

An Azure Synapse Analytics workspace typically includes at least one storage service that is used as a data lake. Most commonly, the data lake is hosted in an Azure Storage account using a container configured to support Azure Data Lake Storage Gen2. Files in the data lake are organized hierarchically in directories (folders), and can be stored in multiple file formats, including delimited text (such as comma-separated values, or CSV), Parquet, and JSON.  
  
When ingesting real-time data into a data lake, your Azure Stream Analytics query must write its results to an output that references the location in the Azure Data Lake Gen2 storage container where you want to save the data files. Data analysts, engineers, and scientists can then process and query the files in the data lake by running code in an Apache Spark pool, or by running SQL queries using a serverless SQL pool.  
![image](https://github.com/user-attachments/assets/1c9abd70-6efa-4d9f-b6e8-03952d614b00)

# Define a query to select, filter, and aggregate data  
After defining the input(s) and output(s) for your Azure Stream Analytics job, you can define a query to process the incoming data from an input and write the results to an output.  
![image](https://github.com/user-attachments/assets/137057d4-85a1-418a-b246-804b85f28006)

![image](https://github.com/user-attachments/assets/0221a05d-09c2-4ebd-82f7-096962817cf0)

# Run a job to ingest data
When you've created and saved your query, you can run the Azure Stream Analytics job to process events in the input(s) and write the results to output(s). Once started, the query will run perpetually until stopped; constantly ingesting new event data into your Azure Synapse Analytics workspace (into a table in relational data warehouse or files in a data lake, depending on the output type).  

# Working with ingested data
You can work with the ingested streaming data like any other data in Azure Synapse Analytics, combining it with data ingested using batch processing techniques or synchronized from operational data sources by using Azure Synapse Link.  
![image](https://github.com/user-attachments/assets/55ac376d-70ce-4a6d-b075-7bfde8523589)

# Querying data in a data lake
As streaming data is ingested into files in a data lake, you can query those files by using a serverless SQL pool in Azure Synapse Analytics. For example, the following query reads all fields from all Parquet files under the sensors folder in the data file system container.  
SELECT *  
FROM OPENROWSET(  
    BULK 'https://mydatalake.blob.core.windows.net/data/sensors/*',  
    FORMAT = 'parquet') AS rows  
  
You can also query the data lake by using code running in an Apache Spark pool, as shown in this example:  
%%pyspark  
df = spark.read.load('abfss://data@datalake.dfs.core.windows.net/sensors/*', format='parquet'  
)  
display(df)  

#  Visualize real-time data with Azure Stream Analytics and Power BI
Microsoft Power BI is used by organizations all around the world to create dynamic, interactive data visualizations that reveal insights on which important business decisions are based. Access to timely data can be the difference between failure and success, so the ability to capture and visualize data in real-time, or as near as possible, is critical in many scenarios.  
  
Azure Stream Analytics provides a way to process a stream of real-time data from an input such as Azure Event Hubs, and direct the results to an output. One possible output is a Power BI dataset, from which dashboards can consume data for real-time visualization.  
![image](https://github.com/user-attachments/assets/cea8271e-705f-444e-9b26-f1ba3591aac9)

**Power BI outputs**  

You can use a Power BI output to write the results of a Stream Analytics query to a table in a Power BI streaming dataset, from where it can be visualized in a dashboard. When adding a Power BI output to a Stream Analytics job, you need to specify the following properties:  
  
**Output alias:** A name for the output that can be used in a query.  
**Group workspace:** The Power BI workspace in which you want to create the resulting dataset.  
**Dataset name:** The name of the dataset to be generated by the output. You shouldn't pre-create this dataset as it will be created automatically (replacing any existing dataset with the same name).  
**Table name:** The name of the table to be created in the dataset.  
**Authorize connection:** You must authenticate the connection to your Power BI tenant so that the Stream Analytics job can write data to the workspace.  
  
# Create a query for real-time visualization
To send streaming data to Power BI, your Azure Stream Analytics job uses a query that writes its results to a Power BI output. A simple query that forwards event data from an event hub directly to Power BI might look something like this:  
  
SELECT  
    EventEnqueuedUtcTime AS ReadingTime,  
    SensorID,  
    ReadingValue  
INTO  
    [powerbi-output]  
FROM  
    [eventhub-input] TIMESTAMP BY EventEnqueuedUtcTime  
  
The results of the query determine the schema of the table in the output dataset in Power BI.  
  
Alternatively, you might use your query to filter and/or aggregate the data, sending only relevant or summarized data to the Power BI dataset. For example, the following query calculates the maximum reading for each sensor other than sensor 0 for each consecutive minute in which an event occurs.  

SELECT  
    DateAdd(second, -60, System.TimeStamp) AS StartTime,  
    System.TimeStamp AS EndTime,  
    SensorID,  
    MAX(ReadingValue) AS MaxReading  
INTO  
    [powerbi-output]  
FROM  
    [eventhub-input] TIMESTAMP BY EventEnqueuedUtcTime  
WHERE SensorID <> 0  
GROUP BY SensorID, TumblingWindow(second, 60)  
HAVING COUNT(*) > 1  
  
When working with window functions (such as the TumblingWindow function in the previous example), consider that Power BI is capable of handling a call every second. Additionally, streaming visualizations support packets with a maximum size of 15 KB. As a general rule, use window functions to ensure data is sent to Power BI no more frequently than every second, and minimize the fields included in the results to optimize the size of the data load.  
  
# Creating real-time visualizations in a dashboard
To visualize data in real-time, you can create a dashboard with a real-time visualization tile. Real-time visualizations on a dashboard show data from a streaming dataset, and are updated dynamically as new data flows into the dataset.  
![image](https://github.com/user-attachments/assets/7d0ace7d-b443-403d-99c4-1a110fe65683)
