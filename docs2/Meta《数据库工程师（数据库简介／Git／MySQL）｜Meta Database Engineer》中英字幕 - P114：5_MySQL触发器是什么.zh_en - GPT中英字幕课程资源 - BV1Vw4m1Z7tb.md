# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P114：5_MySQL触发器是什么.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

As a database engineer， you'll often need certain actions to occur automatically when specific events take place。

 like when data is inserted， updated or deleted from a table。

 But how can you make sure that these actions happen automatically and avoid the need to rewrite code each time they must be invoked You can do this with the use of MysQL triggers。

 In this video， you'll learn what a MysQL trigger is and how to code and use them。😊。

Lucky Srub's sales team are adding discounts to products。 However。

 any discounts over 25% must be reviewed by a manager。

 This means that the sales team needs to add a trigger to the database that flags items when they're assigned a discount above the 25% threshold。

 Let's explore MysQL triggers and find out how lucky shrub can use them to complete this task。

 The first question to answer is what's a Mysql trigger。

 A Mysql trigger is a set of actions available in the form of a stored program。

 These set of actions are invoked automatically when certain events occur。

 Examples of these events include inserting， updating and deleting data from a table in a Mysql database。

 However， before you can use a trigger， you need to create。

 and you'll also often need to drop or delete a trigger once it served its purpose。

 Let's take a moment to explore the syntax for creating and dropping triggers。

 A trigger is created using the create trigger statement。😊。



![](img/fa1a1ec7511dd336d153423ec3fab457_1.png)

To create the trigger type that create trigger statement followed by the name of your trigger。

 because a trigger is often user defined。 you can create a custom name。 However。

 make sure that each trigger's name is unique within the database。 then define a trigger type。

 For example， is it an insert， update or delete trigger and should it execute before or after。

 Don't worry about this for now， you'll explore trigger types in a later video。 Next。

 specify which table the trigger must be assigned to。

 and identify how it should be applied to the table。😊，Next， you need to define the trigger's logic。

 In other words， specify what it is that the trigger must achieve。 The trigger can insert。

 update or delete data。 It can even combine these actions as required。

 If it requires multiple statements， then these must be enclosed within a begin end block。

 Then execute the statement to create the trigger。 Again。

 this part of the syntax isn't a concern at this stage in the lesson。

 You'll review different types of triggers and what they can achieve in a later video。😊。

To drop or delete a trigger that you've created， you can use the drop trigger command to use this command。

 just write drop trigger。 then add that if exists clause。

 This clause makes sure that the drop command only works。

 If my SQL can locate the trigger within the database。

 If you try to drop a nonexistent trigger without this clause， then my SQL returns an error。 Next。

 identify the schema that the trigger belongs to using dot notation to identify both the schema and trigger names。

 This makes sure that My SQL only deletes the trigger from the specified schema and not the entire database。

😊，Finally， type the name of your trigger， then execute the statement to drop the trigger。😊。



![](img/fa1a1ec7511dd336d153423ec3fab457_3.png)

It's also important to remember that if you drop or delete a table from your database。

 then MySQL automatically removes all triggers associated with that table。😊。

So how can Luc Shubs sales team make use of these methods。 As you learned earlier。

 the team need to add a trigger to their database that flags when employees attempt to add a discount of more than 25% to an item。

 and approval request must then be sent to a manager for any flagged items。

 Lucy shhrub can use create trigger commands to create this trigger。

 They can name the trigger approval request。 They then assign a trigger type of after update so that the trigger executes the logic after an update operation has occurred within the table。

 Finally， they place the trigger logic within a begin end block。😊。



![](img/fa1a1ec7511dd336d153423ec3fab457_5.png)

Finally， let's look at a few more benefits of triggers。

 Triggs are useful for keeping a log of records or changes made within a database。

 It's basically a way of maintaining audit trails where a record is inserted into the database each time a change is made。

 Triggers are also an alternative to constraints。 They can be a useful way to help maintain data integrity by making sure all data is updated as required。

 They are also useful for performing tasks automatically on specified actions on a database table。😊。



![](img/fa1a1ec7511dd336d153423ec3fab457_7.png)

You should now know what a MySQL trigger is and understand the basics of how to create and drop them within a database。

😊。