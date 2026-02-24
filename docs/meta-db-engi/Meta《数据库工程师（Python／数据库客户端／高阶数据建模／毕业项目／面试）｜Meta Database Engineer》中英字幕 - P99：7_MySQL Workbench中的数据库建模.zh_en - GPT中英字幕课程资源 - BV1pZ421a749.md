# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P99：7_MySQL Workbench中的数据库建模.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this stage of the course， you understand the importance of database models。

 But how do you create these models， You can create database models using professional data modeling tools such as Mysql workbench。

 In this video， you'll learn how to use MysQL workbench and make use of the forward and the reverse engineer features。

 M and G need to develop a basic database to maintain information about their customers and orders。

 They can use MysqL workbench to create the model。 Then they can use Mysql workbench's forwardward engineer feature to transform the data model into a SQL schema and implement it automatically into MysqL。

Let's help M and G create their database using MySQL Workbench in the MySQL Workbench home screen。

 click the Models view from the left sidebar， then click the plus icon next to the models to display a new window。

This action creates a new schema called My Db。 Do click the schema name and change a to mengeta underscorestore gallo。

 The next step is to create the data model diagram。

 This diagram is essential for using the forward engineer feature。

 You can create the data model in MysQL workbench and then transform it into a SQL schema that can be implemented automatically in MysqL。

 First， double click add diagram to create the Er diagram。

 This action opens the Er diagram designer page。 Now you need to create the tables。

 Click the add table icon and then click a square within the view。

 This action creates a table entity。 Do click the entity to load the table editor。

 Change the default table one name to customers。 Now you need to add columns to the customers table。

😊，Double click a cell This creates a default ID customers column， change its name to customer ID。

 Keep the data type as integer， Check the primary key， Not null and auto increment boxes。

 then add three more columns， full name， contact number and email。

 set the data types as required and mark all three columns as not null。

Follow the same steps to create the orders table and set the data types as required。

You also need to create the orders table foreign key。

 define the table's customer ID column as the For key using the For keys tab at the bottom of the window。

 typeCustom ID FK in the For key text field。Double click the corresponding field in the reference table。

 then select theCustoms table， check the customer ID referenced column。

Then mark it as on update Cascade and on deletete Cascade。

 you now have a visual representation of the MG schema ER diagram with the customers and orders tables。

Save your work by clicking fileile saveve as and name it Mangeta_ Gallo_ model。

Now that you've created the data model， you can synchronize it to the MySQL server using the forwardward Engineer feature。

Select the database tab， then the forwardward Engine option from the menu。

 this opens the forward Engine to database Wiizard。

Select the connection that you created earlier to connect to the MySQL server。

 leave the default setting as is click Next。The wizard lists some advanced options。

 You can ignore these for now。 Just click next。 A new window appears called select objects to forwardward engineer with a series of options。

 Check the export MysQL table objects box。 Then click next。

 The next step displays the SQL script to be executed on the MysqL server to create the internal schema。

 Review the script to ensure that it creates the schema as required。

 Click next to forward engineer the SQL script。 A message appears stating forward engineer finished successfully。

 Click close to close the wizard。 The M and G database has now been created in MysQqL。

 You can confirm this by examining the schema list in the navigator section。

 or executing a show databases statement inside the workbenchsQL editor。😊。

MNG also need to use MySQL Workbench to reverse engineer a data model。

 this means building a data model ER diagram from an existing database。

The first step is to go to the database tab， then select the reverse engineer option Once you're happy with the connection details。

 click Next Each connection must be configured appropriately to connect with MySQL server。

If you're not happy with the existing connection， you can choose another one and click Next。

 A message appears stating execution completed successfully， Click Next。

 a list of available schemas on the server is displayed。

 select the database schema you want to reverse Engine， then click next。

A message appears on screen statingRetrieval completed successfully， click Next。

 a new screen appears in which you are presented with the option to select all objects。

The screen confirms that all objects have been retrieved， click execute。

Once the retrieval process has been successfully executed。

 a message is displayed which states operation completed successfully。

The selected objects have now been reverse engineered successfully。 Click Next again。

 a final screen is displayed which shows a summary of the import。

 Click finish to complete the process。 MysQL workbench creates the new ER diagram from the internal MysqL schema。

 You can print the data model as a PG image。 Share it with others or apply changes and push it to the database using the forward engineer feature。



![](img/20d1faf0496822167f5edb62e6b01174_1.png)

M and G have now developed a basic schema in their database using MySQL Workbench。

 and you should now know how to make use of the reverse Engineer feature in MySQL Workbench to develop a data model diagram。

 well done。

![](img/20d1faf0496822167f5edb62e6b01174_3.png)