# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P38：37_数据库选项.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

When creating a Django project， the default configuration uses an SQLite database。

It is automatically set inside the file， Se dot Pi file。

This means that you can directly start working with the database immediately。

SQLL is known as a user friendly Ze configuration database。

 and there are many advantages to using it。

![](img/d82370bae92dff6030dcbc2968a2e94e_1.png)

You don't need to install anything to support the database as it doesn't run as a server process。

This means the database does not need to be started or stopped or require additional configuration files。

As a result， this type of database is suitable for small projects or rapid prototyping。



![](img/d82370bae92dff6030dcbc2968a2e94e_3.png)

Suppose you are developing projects that need a quick test environment。



![](img/d82370bae92dff6030dcbc2968a2e94e_5.png)

In that case， SQLite is a solid option as it doesn't require running a separate server。



![](img/d82370bae92dff6030dcbc2968a2e94e_7.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_8.png)

There may be occasions when a more scalable， robust database is needed， for example。

 when moving from a development to a production environment。



![](img/d82370bae92dff6030dcbc2968a2e94e_10.png)

In this video， you will learn how to configure database options to work with a MysQL database in a Django project。



![](img/d82370bae92dff6030dcbc2968a2e94e_12.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_13.png)

Jengo supports the use of many databases with minimal configuration。These include P square SQL。

 Maria Db， MySQL， Oracle， and SQLite。

![](img/d82370bae92dff6030dcbc2968a2e94e_15.png)

Among these Postgres SQL and MySQL are most commonly used Django has features to support each database that make it easy to connect and work with。



![](img/d82370bae92dff6030dcbc2968a2e94e_17.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_18.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_19.png)

It provides a generic way to access the different types of databases。

 and a connection to a database is established by knowing the type of database Within this lesson。

 you will deal with one of the most popular and widely used databases MySQL。😊。



![](img/d82370bae92dff6030dcbc2968a2e94e_21.png)

Let's begin by exploring how to set up database connections to a MysQL database。

To connect to a MySQL database， you need to provide the address where the database is running。



![](img/d82370bae92dff6030dcbc2968a2e94e_23.png)

The port number and the database name you wish to connect to。

 you also need a database driver which is responsible for mapping all the models and translating Python queries into SQL instructions via the model。



![](img/d82370bae92dff6030dcbc2968a2e94e_25.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_26.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_27.png)

To use MySQL， the driver or connector， MySQL client needs to be installed。



![](img/d82370bae92dff6030dcbc2968a2e94e_29.png)

When you connect to a database， the connection opens on each request and is kept open for a specific time。



![](img/d82370bae92dff6030dcbc2968a2e94e_31.png)

The connection is controlled by the Kmax age parameter and represents a certain time before the connection is automatically closed。



![](img/d82370bae92dff6030dcbc2968a2e94e_33.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_34.png)

To establish a connection you must configure parameters under the database's option of the Setting。

pi file By default， the configuration is for SQLite。



![](img/d82370bae92dff6030dcbc2968a2e94e_36.png)

You can also use an options file for MySQL to store the database connection credentials。



![](img/d82370bae92dff6030dcbc2968a2e94e_38.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_39.png)

And you will learn about it later in this lesson。The credentials can include the database name。

 username and password and are stored in a separate configuration file inside the file a Se。

 Pi the MysqL connection reference looks for the connection file in the directory ETC forward s MysqL and notice that this is not within the Jngle project。

 This is a deliberate security measure。

![](img/d82370bae92dff6030dcbc2968a2e94e_41.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_42.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_43.png)

ok。Now that you know the steps needed to connect to a MySQL database。

 let's explore database creation while Django creates all the tables based on the models you have from the migration scripts。

 the initial setup requires you to manually create the database。

 creating a database requires a connection to the database itself and sufficient permissions for authentication and authorization。



![](img/d82370bae92dff6030dcbc2968a2e94e_45.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_46.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_47.png)

It's important to remember that you must keep the database secure by assigning security roles and using strong usernames and passwords。

 the data stored may contain end user' personal information。

 so keeping it private and safe is of the utmost importance。



![](img/d82370bae92dff6030dcbc2968a2e94e_49.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_50.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_51.png)

As a developer， you need to be aware of potential security risks。

 and one significant risk is the security of the credentials of your database。

 allowing someone to know or access the username and password of your database can have major consequences。



![](img/d82370bae92dff6030dcbc2968a2e94e_53.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_54.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_55.png)

The database connection credentials are only accessible on the virtual machine or server where the web application is running in this video you learned how to configure database options to work with a MySQL database in a Django project。



![](img/d82370bae92dff6030dcbc2968a2e94e_57.png)

![](img/d82370bae92dff6030dcbc2968a2e94e_58.png)