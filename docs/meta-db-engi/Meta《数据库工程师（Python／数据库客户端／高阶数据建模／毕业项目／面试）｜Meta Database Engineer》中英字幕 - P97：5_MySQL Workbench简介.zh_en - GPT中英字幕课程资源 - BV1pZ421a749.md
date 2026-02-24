# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P97：5_MySQL Workbench简介.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

As a database engineer， you need to create， implement and manage a database system that meets the specific requirements of your business or organization。

 These can be complicated tasks to carry out。 but there are a range of tools and technologies you can use to support your work。

 One example of the tools that you will make use of is the Mysql workbench tool。 In this video。

 you'll explore the basics of the Mysql workbench tool。

 You'll also learn how the tool can be used to help model and manage your databases。 Over at MG。

 the company is developing a new Mysql database management system。

 The database system must follow some key requirements。

 particularly in relation to operating systems。 Data migration and editing tools。

 MG can build a database that meets these requirements using MysqL workbench。

 Take a few minutes to review the basics of MysqL workbench。 Then see if you can help them out。

 Let's start with an overview of MysqL workbench MysQL。😊。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_1.png)

Workbench is a unified visual tool developed by Oracle for database modeling and management。

 It contains several key features that are useful for creating， editing and managing databases。😊。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_3.png)

Let's review some of My SQL Workbench's key features。

MySQL Workbench is open source and cross platform， it can be used with multiple operating systems。

It simplifies database design and maintenance， and it offers a visual SQL editor and other tools that support developers。

 it provides autocomp and highlighting features for writing SQL statements。

 and it facilitates data migration between different versions of MySQL and between MySQL and other relational database systems。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_5.png)

You'll make use of MysqL Workbench in this course to model and manage data in your MySqL database。

 but first you need to download， install and set up MySqL Workbench on your operating system。

 download a copy of MysqL workbench from dev。mysql。com/ downloads。

 make sure that you download the correct copy for your specific operating system。

Once you've downloaded a copy， you then need to double click the file to install it on your machine Next。

 follow the installation wizard with the custom setup When you run the wizard make sure that you install the following software MySQL Ser。

 MySQL Workbench and MySQL She if you encounter any difficulties。

 read the MySQL Workbench installation file for guidance。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_7.png)

Next， let's open the MysQL Workbench and find out more about how you can use it to establish connections。

 Once you've downloaded a copy of MysQl Workbench， you need to set it up。

 Laun the program and view the MysQL workbench home screen The home screen contains a welcome message links to documentation blogs and discussion forums and provides access to various tools and features。

 You can use the home screen side panel to access MysqL connections。

 models and MysQL Workbench migration wizard。 Select the connections option to view a list of connections to local and remote instances of MysQL。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_9.png)

You can use connections to load， configure， group， and view information about each of your MySQL connections。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_11.png)

Models displays the most recently used models。Each entry lists the date and time the model was last opened。

 along with its associated database， you can also select the plus sign to add a new model。

 select the folder button to browse and open Save models and select the More button to access additional commands。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_13.png)

You can also open the Mi tab to display an overview of prerequisites for using the wizard。

 starter migration process， open the ODBC administrator or view documentation Let's look at the process steps for creating a new user creating a new user is the most secure way to connect to your MySQL database because you can manage user roles and privileges。

 make sure MySQL connections is selected。

![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_15.png)

![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_16.png)

First， log into the MySQL server using the root user。

 enter the root user password you set when installing MySqL。

 saveve the password for future reference if required， Next。

 select Use and privileges under the management menu to view a list of current database users。

 select add account to add a new user This opens a new window in which you can enter the new user details。

 name the new user amin 1。

![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_18.png)

Enter a password， confirmr the password。 You can also use this window to control user privileges。

Let's review these privileges Account limits is used to limit a user's maximum number of queries。

 updates and connections。The Adr roles tab lets you assign a role to a new user or assign them associate privileges in this case。

 select DBA that grants the right to perform all tasks。

Schema Privis lets you control new user access privileges。

 select the apply button to create the new user。The next task is to create a new MysQL connection from the MySQL Workbench home screen。

 select the plus icon to open the setup new connection form。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_20.png)

Fill in the form to create a new server instance， you can now use the following values。

 use test server as a server instance name in the username text field type amin 1。

You can use the default settings for all other parts of the form。 Finally。

 make sure your host name is 127。0。0。1 and the port number is 3306。

 Click the test connection button to check that the settings work is required。

 En the password you set for admin one user。 If you set it up correctly。

 then My SQL workbench should confirm that the connection was successful。

 If not return to the form and check that you've entered the information correctly。

 select O to save the connection。

![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_22.png)

Your new MySQL connection is added to the home screen You can now use this connection to begin working with database schemas and SQL queries you should now be familiar with the basic features of the MySQL Workbench tool and know how to use it to help model and manage your databases you're well on your way to understanding advanced data modeling。



![](img/c01c6a3abe0c3836c31bcfbdcaae30f9_24.png)