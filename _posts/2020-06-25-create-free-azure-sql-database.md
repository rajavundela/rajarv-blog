---
title: "[Archive]How to create a Free Azure SQL Database (SQL Server Database)"
date: 2020-06-25T17:03:38.866Z
last_modified_at: 2023-11-05
tags:
  - "#Azure"
comments: true
---

<span style="color:red;">Hi there, these steps doesn't work anymore as <i>Web App + SQL</i> option was removed by Azure.</span>

In this post, we go through on how to create a free Azure SQL Database.

[Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/sql-database-paas-overview) runs on the stable version of Microsoft SQL Server database engine. If we follow the Microsoft Docs [tutorial](https://docs.microsoft.com/en-us/azure/azure-sql/database/single-database-create-quickstart?tabs=azure-portal) on how to create an Azure SQL Database, there is no free tier available. The least tier is basic with approximately $5 US Dollar per month.

![Basic tier SQL Database Pricing](/assets/images/uploads/2020-06-25-pricing.png)

There is a little workaround here. We have to create a combo of **Web App + SQL** to get a free database. Then, delete the Web App (because it is not needed), after that you can use database.

## Steps to create free database:

Go to [Azure Portal](https://portal.azure.com/) and click on **create a resource** icon. Search for `Web App + SQL`.

![Web App + SQL](/assets/images/uploads/2020-06-25-search-database.png)

Click on create button to create **Web App + SQL** resource.

[![create Web App + SQL](/assets/images/uploads/2020-06-25-create.png)](/assets/images/uploads/2020-06-25-create.png)

In **Web App + SQL create** Page, fill all the data that is required.

If you click on `SQL Database` you can create a new database or select existing databases. In our case we create a new database. Before creating database configure `Target Server` settings for database.

click on `SQL Database`

[![Web App + SQL data entry](/assets/images/uploads/2020-06-25-data-entry-database.png)](/assets/images/uploads/2020-06-25-data-entry-database.png)

select `create a new database`.

Enter database name and select `Target Server`.

![select target server](/assets/images/uploads/2020-06-25-sql-database.png)

Enter new server details and click select.

![new server details](/assets/images/uploads/2020-06-25-new-server.png)

Now change Pricing tier. click on Pricing tier.

![select pricing tier](/assets/images/uploads/2020-06-25-at-11.09.57-am-compressor.png)

click on `Looking for basic, standard, premium` tab.

![basic, standard, premium tab](/assets/images/uploads/2020-06-25-at-11.10.15-am-compressor.png)

click on free tab and apply.

![free tab](/assets/images/uploads/2020-06-25-at-11.10.40-am-compressor.png)

Now click on apply in `SQL Database` page.

![SQL database](/assets/images/uploads/2020-06-25-at-11.14.41-am-compressor.png)

Create a free App Service Plan for web app. It would be better if you create web app and database in same location. And press `Create` button.

![create web app +SQL](/assets/images/uploads/2020-06-25-create-webapp-sql.png)



## Limitations of free database

The maximum size of database is **32 MB of shared storage** and compute is 5 **[Database Transaction Units (DTUs)](https://docs.microsoft.com/en-us/azure/azure-sql/database/service-tiers-dtu).**

This database is a trial for one year and after a year it gets upgraded to **Basic** tier.

This database is useful for learning and testing purposes only as it has low storage.