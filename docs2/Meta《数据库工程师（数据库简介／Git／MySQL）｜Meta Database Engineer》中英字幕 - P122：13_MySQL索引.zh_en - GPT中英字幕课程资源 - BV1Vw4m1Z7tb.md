# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P122：13_MySQL索引.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

When performing data retrieval， MySQL often scans an entire table。

 even though it only needs to locate specific column values。

 these queries take a lot of time to execute and place extra load on the database。

 but MySQL can execute these data retrieval queries faster with the use of indexes that target specific column values。

 In this video， you'll learn how to use indexes to speed up data retrieval。 Over at Lucky Shrub。

 the sales department needs to retrieve the contact numbers of clients from the database。

 but there are thousands of clients and phone numbers to sort through。 Fortunatelyly。

 Lucky Shrub can make use of indexes to retrieve this data faster。

 Before you explore Lucky Sru's process， let's take a few moments to get a better understanding of indexes。

😊，An index is a data structure that helps to maintain pointers that lead to sorted data。

 although you can't see an index within a database。

 it's still helpful to visualize it as a table that contains two columns。

 One for pointers and another for sorted data。 For example。

 Lucky shrug can use an index that lists pointers in one column and the full names of clients as sorted data in a second column。

 There are two types of indexes used in a MysqL database。

 The first is a primary index also called a clustered index。

 The second is a secondary or nonclstered index。 A primary index is an index that is stored within the table itself。

 It's generated automatically once you create a table that contains a primary or unique key。

 The index enforces the order of rows in the table within the table itself。

 A secondary index is created using the MysqL create index statement。

 The syntax begins with create index。 Then write the name of the index。😊。

A commonly used approach is to write the name of the column you want to create the index on prefaced by IDX for index Next。

 use the on keyword to assign the index to a table and finally add a pair of parentheses and write a list of columns that the index is to be used against an index can be created using one or more columns from a table but you should only create indexes on columns that you'll frequently perform searches against this is because when you update or insert data into the table that same data must also be added to or updated within the index which takes time。

😊，Lucky Shrub can use a secondary index to optimize their SQL select query。

 they can create an index on the full name column so that client details can be located faster。😊。



![](img/bb523e3d9268ac0cb389a966499615f8_1.png)

Now that you're more familiar with the concept of an index。

 let's see if you can use your new knowledge to help lucky Shrub。

Lucky shrugrub need to find the contact number for the client。 Jane Delgado。 However。

 there are many client names to search against， and Mysql must scan all rows until it locates the correct name。

 Let's quickly review the approach that MysQqL usually takes to complete this task。 First。

 type the explain clause to output data that explains how the database executed the query。

 You can pinpoint potential bottlenecks and suboptimal queries by reviewing the output。

 Then type a select statement that selects a contact number from the client's table that matches the value of Jane Delgado。

 Press enter to execute the query。 The query returns the contact number for Jane Delgado。😊。



![](img/bb523e3d9268ac0cb389a966499615f8_3.png)

But as the output results have shown， my SQL had to scan and filter 10 records before it found a matching value。

 The possible keys column also shows a null value。 This means that there's no key or pointer that can help to make the search easier。

😊，So the solution is for lucky Srub to speed up the search process by creating a secondary index。

 First， type create index， then add Ix for index to the full name column。 Next。

 target the client's table using the on keyword and then place the full name column name in parentheses。

 Finally， execute the statement to create the index。 to test the efficiency of the index。

 you can create and execute another explained statement。 This time。

 the output result shows that My SQL only had to locate one row。

 and it was able to locate possible keys using the index full name index。

 This means that Luc shruub SQL select query can now search the index and locate the data faster instead of searching through all records in the client's table。

😊，And you should now be able to explain what an index is。

 outline the differences between primary and secondary indexes。

 and describe the process for creating an index well done。😊。

