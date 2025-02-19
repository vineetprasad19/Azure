You have two Azure SQL databases named DB1 and DB2.
DB1 contains a table named Tabid. Table! contains a timestamp column named LastModifiedOn.
LastModifiedOn contains the timestamp of the most recent update for each individual row.
DB2 contains a table named Watermark. Watermark contains a single timestamp column named **WatermarkValue**.
You plan to create an Azure Data Factory pipeline that will incrementally **upload into Azure Blob Storage** all the rows in Tablel for which the LastModifiedOn column contains a timestamp newer than the most recent value of the WatermarkValue column in Watermark.
You need to identify which activities to include in the pipeline. The solution must meet the following
requirements:
• Minimize the effort to author the pipeline.
• Ensure that the number of data integration units allocated to the upload operation can be controlled.
**Answer:** to get most recent value of the WatermarkValue, use **Lookup** and to perform upload, use **Copy Data**

You use Azure Data Factory to create data pipelines. You are evaluating whether to integrate Data Factory and GitHub for source and version control What are two advantages of the integration? 
**Answer:**
**A. the ability to save without publishing**
**B. lower pipeline execution times**

You have an Azure subscription that contains an Azure Synapse Analytics account and a Microsoft
Purview account.
You create a pipeline named Pipeline1 for data ingestion to a dedicated SQL pool.
You need to generate data lineage from Pipeline1 to Microsoft Purview.
Which two activities generate data lineage? **Answer: Web** and **Dataflow**

You need to read the TSV files by using ad-hoc queries and the openrowset function The solution must assign a name and **override** the inferred data type of each column. What should you include in the openrowset function? **Answer: the rowsetoptions bulk option**

You have an Azure Blob storage account named storage! and an Azure Synapse Analytics serverless SQL pool named Pool! From Pool1., you plan to run ad-hoc queries that target storage! You need to ensure that you can use shared access signature (SAS) authorization without defining a data source. What should you create first? **Answer: a stored access policy**

You have an Azure data factory named ADM. You currently publish all pipeline authoring changes directly to ADF1.
You need to implement version control for the changes made to pipeline artifacts The solution must ensure that you can apply version control to the resources currently defined in the Azure Data Factory Studio for AOFl
Which two actions should you perform? **Answer: 1. Create a Git repository and 2.From the Azure Data Factory Studio, select up code respository**

