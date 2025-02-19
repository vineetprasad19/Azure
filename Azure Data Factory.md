# AZURE DATA FACTORY    
Microsoft's definition of Data Factory is that it is fully managed serverless data integration solution for ingesting, preparing and transforming all of your data at scale.   
Data factory also provides the ability to transform and analyze the data. Microsoft have been adding more and more functionality to its transformation capability called Data Flow, but it is slightly still limited.     
If we need a transformation that's not available in data factory or it's too complex to achieve in data factory, we can create transformations in external solutions such as Spark to run on **HD Insight or Azure Databricks**. We can then orchestrate those transformations from the Data Factory. It provides specific activities to perform these transformations. Also, if we created machine learning models in Azure ML or in Databricks, we can then orchestrate the execution of those from Data Factory as well.   
Data factory also lets us orchestrate the publishing of dashboards created in tools such as **Power BI** to the data consumers. Basically, Data Factory provides an end to end solution for our data integration, transformation and orchestration.  

Data factory is not a data migration tool. If you are doing one of migrations of data from one database to another, it's easier and faster to use tools such as **Azure Database migration service**. Data Factories meant for loading and transforming data periodically.  
Data Factory is not designed for supporting streaming workloads. For that, we can use Azure pass services such as **Event Hub, Iot Hub or external applications such as Spark streaming, Kafka,** etc.  
Like other ETL tools with code free development capability, ADF also lacks support for complex transformations. So you should do complex transformations in things like **Azure Databricks** or **HD Insight**and use Azure Data Factory to only orchestrate the workflow.  
Data factory is not a data storage solution. It doesn't store any data. It merely provides the compute required to process our data. Once processed, the data is written to a storage solution such as SQL database or Azure Data Lake or Synapse Analytics or Cosmos DB, just to name a few examples here.  

![image](https://github.com/user-attachments/assets/3ce6f2c0-e6bd-47d6-ae02-8378deabce9c)  

**OLD LOOK**  
![image](https://github.com/user-attachments/assets/03552a56-7cdf-4f37-bacb-5438cdfb3644)  

**LATEST LOOK**  
![image](https://github.com/user-attachments/assets/9a838e18-a537-41fb-94d9-ee8bbcbc6b9f)  

![image](https://github.com/user-attachments/assets/4c08261d-f8e4-4f2b-8f9e-cf36e005e229)  

![image](https://github.com/user-attachments/assets/85cebfe2-ed56-4684-9671-6fbfe45e72ba)  

**Pipelines Activities**  

![image](https://github.com/user-attachments/assets/f24f1637-e779-4a39-bfbe-edeef10e054d)  
