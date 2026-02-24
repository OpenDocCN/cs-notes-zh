# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P24：23_删除数据.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

In this example， I'll demonstrate how to delete a single record from a table in a database。

I'm using the student table from a college database and leading the record of a student with the last name of Miller。

I go to the SQl tab and P P my admin。And I write a delete statement beginning with the keywords delete from。

Then I specify the table name as student table。I add a where clause and the condition to delete the data I want。

I need the database to scan the list of students and identify the last name or value of Miller。

And then delete that record from the table。So I type。Where。Followed by last name。Equal to Miller。

I then run this statement by pressing the go button。

I get a confirmation that the record Miller has been deleted from the database。

I can then access the student table on the left panel to ensure that the record or instance of Miller has been removed。

Let's explore another example this time by deleting multiple records from the student table。

Now I want to delete the records for the two students within the engineering department。

The beginning of the statement is the same as the previous example。

I begin with the delete and from keywords， followed by the name of the table I'm working with。

 which is student T。The wear clause is the key difference in this example。

I type where followed by department equalqu。To engineering。

This instructs SQL to identify all records that have a value of engineering within the department column。

And remove those rows from the table。But I need to be careful。

If I don't correctly specify the where clauses， then all the records in the table will be deleted。

So now that I've completed my statement， I selectGo to Run it。😊。

I then check the table by clicking it on the left panel。

And confirm that the records for the two engineering students have been deleted from the table。

Finally， let's quickly explore how to delete all records from a table。In this task。

 the syntax remains largely the same as in the previous examples。

The key difference is that I remove the wear clauses so that now my syntax just states。

Delete from student table。I remove the wear clauses。

So that now My synyntax just states delete from student T。In other words。

 I'm instructing the database to remove all records from the student table。Then I click go。😮。

And confirm the deletion。Once the deletion has been confirmed， I check the student table。



![](img/c024a3161a454fc2c48fa5afba0564d7_1.png)

Which is now empty。

![](img/c024a3161a454fc2c48fa5afba0564d7_3.png)

I now know that all records have been deleted。