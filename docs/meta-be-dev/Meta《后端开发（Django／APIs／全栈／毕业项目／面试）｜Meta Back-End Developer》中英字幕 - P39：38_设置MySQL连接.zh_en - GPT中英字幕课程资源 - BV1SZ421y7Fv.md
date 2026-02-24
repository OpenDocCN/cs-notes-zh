# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P39：38_设置MySQL连接.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Jengo is so popular because it's open source with a rich set of tools that allow for easy scalability and rapid development。

MySQL is one of the many databases which Django supports。

Recall that databases help store data from different sources that can be used for different purposes。

 such as adding content to a webage。 The Django development framework has internal support for connecting with different databases。

Previous， you learned that Django uses something called an object relational Maper R OM and OM facilitates the mapping of data between databases and the application model without the need to write any SQL queries。

 MysqL is a popular database management system。 and can be used with Django。

 when there is a heavy data load， Let's quickly recap some of the features of MysqL。

It's open source and well documented。It's reliable and quick as data storage is done efficiently in memory。

It's scalable and can work with small to vast amounts of data； Finally。

 it's secure and provides a layer of security with encrypted password protection that is flexible and verification based。

It's important to know that before you begin working with models。

 you need to have a database installed。Jngo provides the SQLI database by default。

 and no pre installation is required。

![](img/b146a37e7413154c248c4e6ec47fe6ab_1.png)

However， if you want to use another database， you must install and configure it。

Let's now explore the steps to install and configure my SQL within ajangle project。

Before you can begin using MySQL with Django， ensure that MySQL is installed on your computer。

Depending on the operating system and use， you can use the different site packages that are available on the MySQL website。

The examples in this video refer to Mac OS you can find commands specific to other operating systems from the additional reading at the end of this lesson。

For Mac OS， you can use a package manager such as HomeBrew to manage your installation。

Begin by typing the command， B installs MySQL。This installs the MySQL database。Next。

 go into MySQL to access the databases， note that there are specific commands when using Mac OS。

Now type the command MySQL， dash U root P。Dashu refers to the username， whereas RoP is the password。

Now press enterter to action a password request。Notice that the password entered here matches the password set for the route inside the MySQL database。

Inside the shell， go ahead and type the command show databases。And end your query with a semicolon。

This generates a list of all the MySQL databases on your MySQL server。For example。

 create a database called Fe。😊，To do this， type the command， createate database feedback semicolon。

Now run the show databases command again， and now your list includes the new feedback database you've just created。

The next step is to create a user for the Djangle project。Okay， so run a command labeled Cate user。

 apostrophe， admin Django， apostrophe identified by apostrophe， password， apostrophe， semicolon。

The password is the word password。Note that there may be variations to this particular command。

 but this is one of the simplified versions。Now， press enter。Next。

 you enter the command to grant permissions to the user。

The final command here is flushush privileges。Now， the database is ready to use。

The next step is to install a database connector。This is used to allow the MysQL database to interact with the Django orRM。

In this example， you'll use MySQL clientient Library。There are alternative options you can use。

 such as any of the Python 3 database connector libraries that are compatible with Django。For now。

 exit the MySQL shell and type the command， PipP3， install MySQL client。

Note that you may need to install extra files that allow this specific library to work on this operating system。

Once the database and the database connector are in place， go to the settingstting。

pi file inside the My project folder。Here， Janngo will reference information about the database connection。

To use MySQL， the database needs to be in a specific format。

Replace the database code with that of the settings for MySQL and replace the database name with feedback。

It's important to note that in this example， the database name is feedback。

 always check the name of the database that you want to connect to。Next。

 replace the user with admin Django。And the password with password。

The final step before you can use the database is to run the migrations。

 so let's run the following two commands。First， type the query Python3， manage dot Pi。

 make migrations， and press enterter。Next， type Python 3 manage。 pi， migrate。

Notice the list of migrations you've just performed， however。

 your view of this is limited because there are no entries inside the database。

In the absence of using MySQL database for the majority of the course。

 it is always good to know that there are alternatives available to the SQLI database。

 and these are installed by default inside Django。

![](img/b146a37e7413154c248c4e6ec47fe6ab_3.png)

In this video， you learned how to set up a MysQL database connection in Django。

