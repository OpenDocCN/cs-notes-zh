# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p65 p64_04_jpa-architecture -BV1fryaYgEqb_p65-

Yeah。

![](img/d3ccd28a13af43662254739bdefca4d1_1.png)

Hey guys， here we will discuss the architecture which is scored classes and interfaces of GPA specifications。

 so let's get started。

![](img/d3ccd28a13af43662254739bdefca4d1_3.png)

So basically， Java Perence API is the Java standard for mapping Java objects to the relational database as I discuss。

 and mapping Java objects to the database tables are vice versa that's called object relation mapping。

The Perence API is one possible approach to OM via J the developers can map， store， update。

 and retrieve data from relational database to the Java operates in vice versa。

And one important thing， Java JPA specification can be used with Java enterprise Ed and standard Ed applications as well。

And GPs specification and several implementations are available。

 popular implementations such as hibernet， Eclipse， Li and Apache， open GPA， etc。

 are available to be implemented。This JP is a source to store business entities as relational entities and shows how to define plain old Java object。

 which is a pojo as an identity and how to manage the entities with relation。

This image shows the class level architecture of JP here you can see that entity manager factory is there。

 This is a factory class of entity manager it creates and manages the multiple entity manager instances。

The entity manager is an interface， it manages the persistence operations on object and it works like a factory for query instance。

Next we have an entity entity is basically persistentence objects stored as records in the database。

 we do have entity transaction it has one to one relationship with entity manager for each entity manager operations are maintained by entity transaction class。

Persistence class contains some static methods to obtain entity manager factory instance。

Qury interface is implemented by each JpaA vendor to obtain relational operates that meets the criteria。



![](img/d3ccd28a13af43662254739bdefca4d1_5.png)

So these are the things that we need to it and what we have used in our JpaA architecture。

The relationship between in this architecture ads we has with the En manager factory。

And the entity manager， which is one， too many。It is a factory class to entity manager instances in the relationship between the entity manager and entity transaction transaction is one to one and for each entity manager operation。

 there is an entity transaction。The relationship between entity manager and the query is one to many because many number of queries can execute using entity manager instance。

And the relationship between entity manager and entity。

Is one too many because our entity manager instance can manage multiple entities。

How to create this entityD manager instance and communicate with the transactions and query would be more clear to you once you will come into the implementation。

 so stay tuned to learn more about the concepts or this architecture in practical see in in next session。



![](img/d3ccd28a13af43662254739bdefca4d1_7.png)