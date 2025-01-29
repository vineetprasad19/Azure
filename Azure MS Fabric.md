# Azure Microsoft Fabric
With Microsoft Fabric, you don't have to spend all of your time combining various services from different vendors. Instead, you can use a single product that is easy to understand, set up, create, and manage. Fabric offers persona-optimized experiences and tools in an integrated user interface.
In addition to a simple, shared user experience, Fabric is a unified software-as-a-service (SaaS) offering, with all your data stored in a single open format in OneLake. OneLake is accessible by all of the analytics engines in the platform. Fabric offers scalability, cost-effectiveness, accessibility from anywhere with an internet connection, and continuous updates and maintenance provided by Microsoft.

**Explore OneLake**  
OneLake is Fabric's lake-centric architecture that provides a single, integrated environment for data professionals and the business to collaborate on data projects. Fabric's OneLake architecture facilitates collaboration between data team members and saves time by eliminating the need to move and copy data between different systems and teams. OneCopy is a key component of OneLake that allows you to read data from a single copy, without moving or duplicating data.  
Think of it like OneDrive for data; OneLake combines storage locations across different regions and clouds into a single logical lake, without moving or duplicating data. Similar to how Office applications are prewired to use your organizational OneDrive, all the compute workloads in Fabric are preconfigured to work with OneLake. Fabric's data warehousing, data engineering (lakehouses and notebooks), data integration (pipelines and dataflows), real-time intelligence, and Power BI all use OneLake as their native store without needing any extra configuration.

![image](https://github.com/user-attachments/assets/20878605-ffe7-4e56-94aa-148d65c78b88)

OneLake is built on top of Azure Data Lake Storage (ADLS) and data can be stored in any format, including Delta, Parquet, CSV, JSON, and more.  

What this means is that all of the compute engines in Fabric automatically store their data in OneLake. Data that is stored in OneLake is then directly accessible by all of the compute engines without needing to be moved or copied. For tabular data, the analytical engines in Fabric write data in delta-parquet format and all engines interact with the format seamlessly.  

One important feature of OneLake is the ability to create shortcuts, which are embedded references within OneLake that point to other files or storage locations. Shortcuts allow you to quickly source your existing cloud data without having to copy it, and enables Fabric experiences to derive data from the same source to always be in sync.  

![image](https://github.com/user-attachments/assets/ba7e1900-592d-4dc0-9cef-78f7bf130b2e)

**Explore Fabric's experiences**  
Fabric offers a set of analytics experiences that are designed to accomplish specific tasks and work together seamlessly. Fabric's experiences include:  

**Synapse Data Engineering:** data engineering with a Spark platform for data transformation at scale.  
**Synapse Data Warehouse:** data warehousing with industry-leading SQL performance and scale to support data use.  
**Synapse Data Science:** data science with Azure Machine Learning and Spark for model training and execution tracking in a scalable environment.  
**Synapse Real-Time Intelligence**: real-time intelligence to query and analyze large volumes of data in real-time.  
**Data Factory:** data integration combining Power Query with the scale of Azure Data Factory to move and transform data.  
**Power BI:** business intelligence for translating data to decisions through interactive reports.  
Fabric provides a comprehensive data analytics solution by unifying all these experiences on a single platform.  

**Explore workspaces**  
Fabric uses workspaces to contain the different items created across the different experiences. Each organization can customize how to separate and control access to the items. Some possibilities include a dedicated workspace for lakehouse development and a separate workspace for the production lakehouse.  

In **Microsoft Fabric**, workspaces serve as logical containers that help you organize and manage your data, reports, and other assets. They provide a clear separation of resources, making it easier to control access and maintain security. Each workspace can have its own set of permissions, ensuring that only authorized users can view or modify the contents. This structure supports collaboration within teams while maintaining strict access control, which is crucial for both business and IT users.  

Workspaces in Microsoft Fabric also offer settings to manage compute resources and integrate with Git for version control. You can configure compute settings to optimize performance and cost, ensuring that your resources are used efficiently. Git integration allows you to track changes, collaborate on code, and maintain a history of your work, which is essential for development and data management. Additionally, workspaces support features like data lineage and impact analysis, providing a comprehensive view of data flow and dependencies, which enhances transparency and decision-making.  

**Explore security and governance**  
Fabric's OneLake is centrally governed and open for collaboration. Data is secured and governed in one place, which allows users to easily find and access the data they need. Fabric administration is centralized in the admin center.  

In the admin center you can manage groups and permissions, configure data sources and gateways, and monitor usage and performance. You can also access the Fabric admin APIs and SDKs in the admin center, which you'd use to automate common tasks and integrate Fabric with other systems.  

**Evolution of collaborative workflows**  
Microsoft Fabric transforms the analytics development process by unifying tools into a SaaS platform, allowing flexibility for different roles to perform necessary skills without duplicating efforts.  

**Data engineers** can now ingest, transform, and load large amounts of data into OneLake and present it in whichever data store makes most sense. Data loading patterns are simplified using pipelines and architectures, such as medallion, can be easily configured using workspaces.  
**Data analysts** gain greater context and streamline processes, transforming data upstream with Data Factory and connecting with data more directly using DirectLake mode.  
**Data scientists** Integrate native data science techniques more easily and use Power BI's interactive reporting to provide data-informed insights.  
**Analytics engineers** bridge the gap between data engineering and data analysis by curating data store assets, ensuring data quality, and enabling self-service analytics.  
**Low-to-no-code** users and citizen developers can now discover curated data through the OneLake hub, and further process and analyze it to suit their needs without being dependent on data engineers or duplicating data.  
**Enable Microsoft Fabric**  
If you have admin privileges, you can access the Admin center from the Settings menu in the upper right corner of the Power BI service. From here, you enable Fabric in the Tenant settings.
**Admins** can make Fabric available to either the entire organization or specific groups of users, who can be organized based on their Microsoft 365 or Microsoft Entra security groups. Admins can also delegate the ability to enable Fabric to other users, at the capacity level.  

**Create workspaces**  
Workspaces are collaborative environments where you create and manage items like lakehouses, warehouses, and reports. All data is stored in OneLake, and is accessed through workspaces. Items are displayed in a list or lineage view, which is a visual representation of the dependency between items.  

In the Workspace settings, you can configure the license type to use Fabric features. There are several other settings you can configure in this area, some of which include:  
OneDrive access for the workspace  
Azure Data Lake Gen2 Storage connection  
Integration with Git for version control  
Spark workload settings  

![image](https://github.com/user-attachments/assets/f566ea70-f7db-49fc-a0d7-947da4d0d7d4)

![image](https://github.com/user-attachments/assets/481cde68-8b13-4735-8fdd-05d89d2a0c7b)

**Create items in Fabric**  
After you create your Fabric enabled workspace, you can start creating items in Fabric. You can create items in Fabric using the Create menu in the upper left corner of the Power BI service.  
![image](https://github.com/user-attachments/assets/21d7a67b-96ca-4d16-8f50-3eea1da3fbbf)

**Knowledge Check**  
![image](https://github.com/user-attachments/assets/7e70da1b-9308-4001-a6da-ed2c44822948)
