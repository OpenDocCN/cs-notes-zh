# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P101：9_数据仓库概述.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

A regular database collects stores and processes data from transactions in real time。

 but what if you need to aggregate and analyze data from multiple sources In these instances。

 a data warehouse is the perfect solution。 It can aggregate data from a range of sources and analyze it using different tools。

 Over the next few minutes， you'll learn what a data warehouse is。

 explore its main characteristics and review the different types of data that can be used in data analytics The online e-commerce platform global superstore has seen a significant drop in sales recently。

They want to perform data analytics to identify the reasons behind this downturn。

 The company has large amounts of data from multiple different sources like online transactions。

 social media interactions and website data Analying all this data requires powerful tools a data warehouse is the perfect solution。

Let's explore the concept of data warehousing in more detail and find out how global Superstoreory can make use of it。

 A data warehouse is a centralized data repository that aggregates。

 stores and processes large amounts of data from multiple sources。

 It separates the data analysis workload from the standard transaction workload of a regular database management system。



![](img/d5816081273919240cf6887e18df1b66_1.png)

Users can then query this data to perform data analysis。

 This type of database is called online analytical processing or O A。

 a regular database focuses on collecting， storing and processing data in real time。

 It's also known as online transactional processing or OLTP。

 There are four key characteristics of a data warehouse。 Their subject oriented。

 integrated nonvolat and time variant。 Let's explore these characteristics starting with subject oriented。

 When building a data warehouse， you need to choose one or more subject areas to explore。

 For example， global superstore can build a data warehouse that focuses on sales。

 They can then use the warehouse to find all relevant information on their sales processes like best and worst selling products integrated means that a data warehouse integrates data from a range of different sources。



![](img/d5816081273919240cf6887e18df1b66_3.png)

Data must be integrated in a consistent format。Integrated data must also resolve issues such as naming conflicts and data types Global superstores data warehouse integrates data from online purchases。

 website interactions and social media。The next characteristic is nonvolat。

 Novolatile means data should not be deleted once it's loaded to the data warehouse。

 The purpose of a data warehouse is to analyze data as it exists。 The more data you have。

 the better the results of your analysis。 So the data that global superstore integrates must not be deleted。

 The final characteristic is time variant。 A data warehouse aggregates data over a long period。

 so that it can measure changes in data over time。 This helps users to discover trends。

 patternss and relationships between data elements。 For example。

 global superstore can use data from the last few years of sales to find out why their profits have declined。

 Now that you're familiar with the characteristics of a data warehouse。

 Let's look at the different forms of data that it encounters。 Their structured data。

 semistructured data and unstructured data。Let's start with a look at structured data。

 This is data that's presented in a structured format within a well definedfined data model。

 The relational database model is commonly used for structured data。

 The organized tables help users to access， manage and search for data using SQL。

A data warehouse typically uses structured data。 This data type is organized for a specific purpose。

 so it's easier to gain insights from and uncover answers to specific questions。

Semistructured data is data that's only partially structured。

 It requires more effort to perform data analysis。 An example of semistructured data is an email message。

 It can contain structured data like a sender and subject。

 but the body is unstructured and can contain several different kinds of data like text。

 images and videos。 The final type of data is unstructured data。

 This data type doesn't adhere to any specific predefined data model。

 It can include any kind of data like text， video or audio。

This data can be collected and stored without applying any form of data model。

 but analyzing unstructured data requires advanced data analytics mechanisms like machine learning and data mining you'll explore these techniques later in this course semistructured and unstructured data are more suited to a data lake This is like a data warehouse。

 but it can handle unstructured data。Data Lake is used more widely by data scientists。

Businesses prefer working with structured data and data warehouses because of its accuracy。

 you should now be able to explain what a data warehouse is。

 outline its main characteristics and the different types of data that can be used in data analytics that's great progress I look forward to guiding you further through these topics。



![](img/d5816081273919240cf6887e18df1b66_5.png)