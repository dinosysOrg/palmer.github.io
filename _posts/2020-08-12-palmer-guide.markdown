---
layout: post
title:  "Guide"
date:   2020-08-12 09:39:02 +0700
categories: Introduction
featured_image: /assets/img/sections/pawel-nolbert.jpg
---

# Table of contents
- [The Before You Start](#the-before-you-start)
- [The Connector](#the-connector)
- [The Embulk Task](#the-embulk-task)
- [The SQL Task](#the-sql-task)
- [The Visualization Task](#the-visualization)

Here are some step by step guide to show how to use Palmer:

# [The Before You Start](#the-before-you-start)
## Login:
Currently you can connect our admin to create a new Login credential for yourself. In the future everyone will be able to join Palmer and use the pipeline until you hit a paywall.
![My helpful screenshot](/assets/login.png){:width="500px"}

## Create your project:
For each user, you will belong to a company. In each company you will be able to create multiple Project if you have multiple pipeline running at the same time. It is useful for segmentation of business logic (depends on the scale of the company).
![My helpful screenshot](/assets/project.png){:width="750px"}

Congratulation! Once you get into a project, you will be able to see all the tools related to the project
![My helpful screenshot](/assets/navigation.png){:width="500px"}


# [The Connector](#the-connector)
A data connector is the source of the data and it can be one of 2 kinds:
**Input Source**
: Input Source is normally where your transactional system data is lying. It is normally the source feeding information into a pipeline.

**Output Source**
: Output Source is your Data Lake/ Data Warehouse, the destination target where you migrate and store all your analytical data.
![My helpful screenshot](/assets/datasource.png){:width="500px"}

Clicking on **Add Datasource** you will be able to see all the supported data sources at the moment.

![My helpful screenshot](/assets/connector_type.png){:width="750px"}

Selecting each data source type will open up the data source configuration view. Depends on your own data source type you will have to key in the necessary information so Palmer can access the data and move your data inbetween data sources.
![My helpful screenshot](/assets/data_type/data1.png){:width="250px"}
![My helpful screenshot](/assets/data_type/data2.png){:width="250px"}
![My helpful screenshot](/assets/data_type/data3.png){:width="250px"}
![My helpful screenshot](/assets/data_type/data4.png){:width="250px"}


# [The Embulk Task](#the-embulk-task)
Embulk task (which name will be changed in the future) is currently the pipeline inbetween your data sources. Embulk task purpose is to maintain and run the job periodically and will report back the progress of those to the user
![My helpful screenshot](/assets/embulk.png){:width="750px"}

As you can see in the screenshot, when settinging up of the job, you need to tell us **how often** you want the pipeline to run, from which **input connector** to which **output connector**
![My helpful screenshot](/assets/embulk_detail.png){:width="500px"}

At the end of the day, we understand the importance of the progress of the embulk task since it guarantees the integrity of the data. For each run, we have a detailed report of which table has been failed and when.
![My helpful screenshot](/assets/embulk_status.png){:width="500px"}


# [The SQL Task](#the-sql-task)
![My helpful screenshot](/assets/sql_task.png){:width="750px"}
SQL Task is another type of job handler that can help the user run SQL Commands on each data connectors periodically. The main usage of this is to build Data Mart on top of the Data Warehouse Connecter which will be useful in reducing query time and will allow better data governance to the company.

For each SQL Task the user needs to define the **connector** where the task is being executed and the frequency of it being called. e.g You can setup the SQL Task to run right after the Embulk Task finish.
![My helpful screenshot](/assets/sql_task_detail.png){:width="500px"}


# [The Visualization](#the-visualization)
The whole pipeline can be visualized to provide an overview of your ETL infrastructure.
![My helpful screenshot](/assets/tasks.png){:width="500px"}