# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P116：7_在MySQL中创建和删除触发器.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

At this stage of the lesson you should be familiar with MySQL triggers and the different types of triggers available to database engineers Now let's take a few moments to find out how you can create and drop these triggers into your databases。

😊。

![](img/45427df6134f3568b94c02769a4ce3ea_1.png)

To help you understand these concepts， let's look at how they're used in Lucky Srub。

 Lucky Srubb's database contains an orders table with several columns that record information on each order placed with the business。

 Lucky shrub want to make sure that no minus values are inserted in the tables quantity column when a new order is recorded。

 Any minus values that the table encounters， must be set to a default value of 0。

 They can complete this task using a before insert trigger。

 The trigger syntax begins with a create trigger command。

 This is then followed by the name of the trigger， which is order quantity check。

 Always make sure that the trigger name is unique within the database。 Next。

 assign the trigger type and specify when it must be invoked。 In this instance， it's before insert。

 In other words， it's invote before an insert command。

 Then type the on keyword followed by the table name。 This lets Mysql know which table to target。😊。

You'll also need to type for each row so that my sQL targets each row within the table。 Finally。

 write the trigger's main logic。 This must be a series of one or more sQL statements that execute when the trigger activates。

 If you have multiple statement， then enclose them within a begin end block。

 The triggers logic checks if a minus value is about to be inserted into the quantity column。

 This action requires an if statement so that it can access the quantity column。

 to create this if statement， you need to use one of two modifiers。

 new and old New suits our purposes here as it targets the value of a column after the operation。

 In other words， the value to be inserted。 If you needed to access the column value before the operation。

 you'd use the old modifier。 So type a statement that says if the new order。

 quantity value is less than 0， then set the new value to 0。😊。

Don't worry if you don't quite understand these modifiers。

 They're covered in more detail later in this lesson。 Now。

 let's find out how to run our trigger before running this trigger。

 make sure you redefine the Mysql delimiter semicolon to a double forward slash。

 then execute the trigger。 Once executed， change the delimiter back to a semicolon。

 Lucky shrub now have the required trigger in their orders table。

Lucky shhrub now need to delete this trigger from the table。

 You can delete or drop the trigger using the drop trigger statement。 type， drop trigger。

 then type the if exists condition to prevent My SQL from returning an error。 Next。

 provide both the schema name and the trigger name using dot notation。 The schema name is optional。

 but still recommended。 It helps my SQL target the correct trigger。

 And don't forget that if you drop the orders table， then all related triggers are also deleted。

 You've now helped lucky shrub to create and drop the required trigger from their database。

 And you should now be familiar with how to create and drop triggers from your own databases。

 Great work。😊。

![](img/45427df6134f3568b94c02769a4ce3ea_3.png)

![](img/45427df6134f3568b94c02769a4ce3ea_4.png)