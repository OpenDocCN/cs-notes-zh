# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P98：21_MySQL CREATE VIEW.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Lucky Srub have had particularly good sales so far this year。

 they now need to identify the top three bestsel products to make sure they have enough quantity in stock for the next few months。

There's a lot of data to pass through in their database。

 so they've decided the easiest way to identify the best selling products is with the use of a virtual table or view。

In this video you'll explore views and then use what you've learned to help Luc Shroub。

 and by the end of this video you'll be able to explain the concept of views in database and demonstrate how to create。

 rename and drop views in MySQL database。Let's begin by developing an understanding of what database engineers mean by the term viewss Views are virtual tables created from one or multiple tables depending on the requirements。

The view presents a table interface that lets the database users access and manipulate the data within the table using MySQL。

So why do database engineers use views？Let's look at some common use cases。

Views can be used to create a subset of a tables data； for example， a table might have seven columns。

 but you only need data from three， so you could create a subset from these three columns。

And views can also be used to combine data from multiple tables。

You might need to query two columns from one table and four from another。

You can use views to combine both sets of columns into one virtual table。

Now do you understand what views are， let's review the syntax。

The syntax begins with a createate command， followed by the view keyword and the name of the view or virtual table。

The as keyword is then used to define the view table functionality。Next。

 use the select command to specify the columns the table must be built from。

You can specify these columns using dot notation， making sure to include both the table and column name。

 for example， table 1 dot column1 to select the first column in the first table。

Then use the Fr keyword to specify the tables that the datat must be extracted from。Finally。

 you can use the wear clauses and a condition to set data order and filtering rules。

That's how you can create a view by extracting data from one table。However。

 creating a virtual view based on multiple tables requires a bit more effort， let's find out more。

When creating a view from multiple tables， much of the syntax remains the same。

The key difference is after the select command。You must list the columns that you require from both tables using dot notation。

You then need to create an inner join after the Fr keyword in which you join the two tables together。

Then use the on keyword to determine the matching columns used to create the join。

Let's take a closer look at the use of dot notation。

Dot notation is used to link columns with tables this is particularly important if you're dealing with multiple tables。

Multiple tables might give rise to a potential conflict in names； for example。

 two tables could use the same name for a specific column。To avoid this。

 you can establish a link between each column and its respective table by placing a dot in between them。

However， dot notation is optional if your query is only dealing with one table。

The View syntax presents a clear five step process for creating a virtual table or view。

Create the virtual table using the Cre View syntax。

 list the columns to be moved from the original table to the virtual one。

 specify the original table from which data must be extracted to create the view， set the conditions。

 and finally set the data order and filtering rule。



![](img/6ac570e992e151329141f2840eaa79d2_1.png)

Now that you've been introduced to what a view is and been shown how to create one。

 it's time to see if you can assist Luc Shrb。As you discovered earlier。

 Lucy Shrub need to identify their top three best sellingel products with the use of a virtual table or view to make sure they have enough quantity in stock for the next few months。

Let's use your new knowledge of views to help them out。

You can create a virtual table or view for Lucy Shub using the data in the orders and products tables in their database。

Let's take a moment to familiarize ourselves with these tables before using them to create the view。

The orders table has five columns that include information about the order ID， client ID， product ID。

 quantity， and cost。While the products table has three columns that include information about the product ID。

 item name and price。Ly Shrub want to identify their top three best sellingel products。

 so to create the view you only need data from the item name column from the products table。

 the order， quantity， and total cost columns from the orders table。As you learned earlier。

 the key steps for creating the view lie in the syntax。

So write a create command and the view keyword。Then write the name of the view。

 which you can call top three products。Include the as keyword to define the view table's functionality。

Then use the select command and dot notation to target the required columns for your view。Next。

 use the Fr keyword to identify the tables。However， the view is created from two separate tables。

 so you'll need to join these tables together using inner join based on their matching product ID value。

Finally， use Order by to list the products based on the highest cost with only the top three products appearing on screen in the sending order。

Execute the query to generate a new virtual table called Top three Products with the three required columns。

 item， quantity and cost。You can now query this virtual table just like any other normal table using the following basic SQL statement。

 select asterisk from top three products。The table prints the top three best selling products along with their name。

 quantity and cost。Why don't you try rename the table to something shorter， like top products？

You can rename a virtual table using the MySQL Rename command。To rename the table， write。

 rename table， top three products， two top products。

This syntax is used to rename all types of tables in MysQL。In this statement。

 you just specify the View's current name after the renamed table clause。

 then you specify the View's new name after the two keyword。Finally。

 click Enter to execute the query。The table has now been renamed top products。

What if you no longer require a virtual table？You can just drop it using the SQL droprop command。

 droprop View top products。Click Enter to execute the query。

The view has now been removed and there's no impact on the original table it was created from。



![](img/6ac570e992e151329141f2840eaa79d2_3.png)

Thanks to the view， Lucy Shub now know what their top three best selling products are。

 and they can make sure that they have enough quantity in stock for the next sales period。

You should now be able to explain the concept of views in database and demonstrate how to create。

 rename， and drop views in MySQL database， well done。

