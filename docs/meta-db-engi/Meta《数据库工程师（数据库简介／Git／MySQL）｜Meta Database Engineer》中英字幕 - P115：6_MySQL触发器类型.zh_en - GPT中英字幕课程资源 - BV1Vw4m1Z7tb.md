# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P115：6_MySQL触发器类型.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

As you might know by now， a MysQl trigger is a set of actions that can be invoked automatically when certain events occur。

 But how do you determine when and how these triggers are executed， Well。

 you can control the behavior of your triggers by using different types over the next few minutes。

 you'll explore the different types of triggers available and learn when to use them。😊。

Lucky Shrub are rebuilding their orders table， which records orders within their database。

 They need to assign a new set of constraints or rules on this table。

 Maybe they can create these rules using triggers。 Let's find out which types of triggers Lucky shhrub can make use of。

 and in what order these triggers should occur。First。

 let's explore the two main types of triggers defined in SQL。

 row level triggers and statement level triggers。😊。



![](img/38caa60bfe0b052787b1b731e5f8be26_1.png)

A row level SQL trigger is invoked for every row inserted， updated or deleted in a table。

 So if 100 rows are added to a table， then the row level trigger is invoked 100 times。

 a statement level trigger on the other hand， is invoked once for each action。

 and it occurs just once， no matter how many rows are inserted， updated or deleted。

 So a single insert statement could add 100 rows to a table。

 but it only activates once for all 100 rows。😊。

![](img/38caa60bfe0b052787b1b731e5f8be26_3.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_4.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_5.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_6.png)

It's important to be aware of both types of triggers。 However。

 My SQL only supports row level triggers， so they'll be the focus of this lesson。

As you learned earlier， triggers are typically used to perform three types of actions。

 insert data into a table， update data in a table and delete data from a table。

 but how can you determine when an insert update or delete trigger occurs Well。

 depending on when a trigger is action， it can be classified as either a before or after trigger let's find out what this means。

😊。

![](img/38caa60bfe0b052787b1b731e5f8be26_8.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_9.png)

The before keyword or modifier indicates that a trigger must be invoked before any action is performed on a table row。

 while after indicates that the trigger is invoked after the action is performed on each row。😊。



![](img/38caa60bfe0b052787b1b731e5f8be26_11.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_12.png)

By combining these modifiers with the insert， update and delete keywords。

 you can create different types of triggers。 For example。

 the before insert trigger is automatically invoked before an insert event occurs on a table。

 while after insert is invoked after an insert event。 Similarlyly。

 a before update trigger is invoked before an update event occurs。

 and an after update trigger is invoked after the event。 Finally。

 before delete triggers are invoked before data is deleted in a table。

 and after delete triggers are invoked after data is deleted In each instance。

 the syntax is largely the same for each type of trigger。 begin with a create trigger command。

 followed by the name of your trigger。 Next， add the modifier and keyword to determine when your trigger must occur and on what action it must take place。

 For example， before insert instructs My SQL to invoke the trigger before an insert event occurs on the table。

 then type the on keyword and the name of the table。 This is followed by the for each。😊。



![](img/38caa60bfe0b052787b1b731e5f8be26_14.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_15.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_16.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_17.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_18.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_19.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_20.png)

Row keyword。 This instructs my sQL to carry out the action for each row in the table。 Finally。

 type the logic of the trigger。 As you might recall， this is usually typed within a begin end block。

 particularly if you need to specify multiple statements。 Let's look to Luc shrub for an example。

 They want to impose a new constraint on their orders table。

 This new rule must state that no minus values can be inserted in the tables order quantity field。

 So Luc shrub can begin with the create trigger command。

 They can then name the trigger order quantity check。 Next。

 they add the modifier and keyword before insert。 Then they assign the trigger to the orders tab and make sure it applies to each row。

 Finally， they create the trigger logic within begin and end statements。

 The logic states that if the table encounters an order with a value of less than 0。

 then it must set the value to0 by default。 Now， each time a new row is inserted into the table。

 The before insert trigger carries out the required action。😊。



![](img/38caa60bfe0b052787b1b731e5f8be26_22.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_23.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_24.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_25.png)

Before it inserts a new value， let's take a moment to explore some more types of triggers that luckyky Srub can use。

😊，Lucky shhrub want to maintain an audit trail of all updates made to their orders table with an after insert trigger。

 they can send a log message from the orders table to the audits table each time a new order is inserted。

 The company also needs to create a log that captures the date and time and order record is deleted from the orders table。

 They can use an after delete trigger for this task。 After a record is deleted。

 the trigger inserts a record in the log with the date and time。😊。



![](img/38caa60bfe0b052787b1b731e5f8be26_27.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_28.png)

![](img/38caa60bfe0b052787b1b731e5f8be26_29.png)

These are just a few examples of how the different types of triggers work in MySQL you'll explore them all in more detail later in this course。

 but for now you should be familiar with the different types of triggers available and know how to create them Good work。

😊。