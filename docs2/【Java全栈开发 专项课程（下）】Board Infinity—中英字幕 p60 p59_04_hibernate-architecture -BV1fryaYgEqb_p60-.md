# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p60 p59_04_hibernate-architecture -BV1fryaYgEqb_p60-

![](img/f117778e8c7a58fc0b77d1017f8e0314_0.png)

Hey guys， today in this session I will talk about hibernate architecture hiber hibernet architecture is categorized in four layers。

 one is a Java application layer， second is a hibernet framework layer third is a backened API layer and the fourth is a database layer。



![](img/f117778e8c7a58fc0b77d1017f8e0314_2.png)

When we talk about these four layers。This implementation comes with the real time implementation and also helps in3 tier architecture hibernet framework uses many objects such as session factory session transaction along with existing Java API such as JDBC。

 JTN JNDI， but generally we use Java database connectivity。



![](img/f117778e8c7a58fc0b77d1017f8e0314_4.png)

This is a high level hinate architecture where the entire flow is to be demonstrated。

 whatever Java application you create， you create a persistent objects in the form of Java entities。

Then you configure your hibernate properties and where you create your session factory object starts your session and within each session you can create multiple transactions inside that depend whatever query and criteria you wanted to run across to complete your transaction make sure your entity should have one primary keyet and the APIs it's completely your choice as I told you you can use JNDI。

 JBC or JTA but JBC is most to be used in the real time in nowadays projects。

 I also recommend the same。

![](img/f117778e8c7a58fc0b77d1017f8e0314_6.png)

This is how the flow of hibernet works， first of all， you will be。

Creating the model classes in which you wanted to work it up。

 then you would be configuring the session factory you will open within the session factory once gets built and the database configuration gets provided to the configuration by building the session factory within a session factory you will open a session。

Within the session you will open the transaction and within the transaction you will write a query depends you wanted to write down the SQL query。

 wanted to communicate in terms of object or you wanted to write down the criteria or HQL query and that get passes through the section and once the transaction gets completed by writing these queries you will either commit the transaction or roll back it if any error comes in。

 that's how your hibernate request completes。

![](img/f117778e8c7a58fc0b77d1017f8e0314_8.png)

Session factory is an interface to hold optional second level caches such as session objects。

 sessionession interface to hold mandatory first level cacheier where we start the transactions and write up the queries。

 transaction interface basically follows the principle of asset。Atutonomomicity， consistency。

 integration and。嗯。Implementation of durability。Where the transaction begins and commits either completes either by commits or roll back。

Transaction factory is an options factory of the transaction。

Then there is a connection provider we need to close our session and session factory to complete our request so that other can use my session factory option。



![](img/f117778e8c7a58fc0b77d1017f8e0314_10.png)

That's how the hibernate architecture works。 See you in the next session until next time， Stay tuned。



![](img/f117778e8c7a58fc0b77d1017f8e0314_12.png)