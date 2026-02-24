# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P111：19_在Tableau中导入和准备数据.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

At this stage of the lesson， your next question might be how do I use Tableau In this video。

 you'll learn how to connect Tableau to your data sources。

 then clean and prepare your data for analysis。 Global superstore needs to use Tableau to analyze the records of a large Excel file。

 but they first need to clean and prepare the existing data。

 Let's help global superstore to connect their Excel data source to Tableau。

 then clean and prepare the data for analysis。 to perform data analysis in tableableau。

 you first need to establish a live connection to a data source。 to establish a live connection。

 First open Tableau on the connection page under the Connect tab on the left hand side。

 click Microsoft Excel。 This opens a dialog box that you can use to navigate to the Excel file on your machine。

 Select and open the file。 The Excel file name appears on the left hand side of the screen。😊。

The data from the Excel file is displayed in the data pane with a live connection。

 you can make sure that any updates to the original source are automatically reflected in your database。

 However， it's faster to process a data extract， particularly when dealing with large amounts of data。

On the left side of the data pane is the metadata grid。

This shows relevant information about the different data fields you can keep or hide the metadata grid by clicking the related button now that you've connected to the data that you need。

 you can begin to clean it and prepare it for analysis。

 This process involves fixing errors in the data and shaping it so that it's easier to understand and analyze you can do this by performing different types of operations like filtering。

 sorting and renaming the data。You'll cover these operations in more detail in a later video。

 The top of each column specifies the column's data type， along with a suitable symbol。

 You can change these data types as required。 Let's take the order date column as an example。

 Select the small arrow next to the symbol above the column。

 Click De on the list of options that appear。This action shows key information about this field of data。

 click the ABC data type and select the date data type The data type has now been changed。

 you can also hide a relevant table details so that you can focus only on the necessary data you can also change the number of rows displayed within the data pane。

Let's hide the order date column， select the small arrow again， then select hide。

 the column is now hidden to show the data again， click the Tau settingstting icon。

 then select the show hidden fields option。 This action displays faded versions of the fields to indicate what has been hidden。

To restore these fields， click the small arrow and select Unhide。

Your next task is to split the customer name column into two separate columns。

 One for each customer's full name and another for their last name。

 Click the small arrow and then select the split option。 This automatically creates two new fields。

 You can rename them as required。 Click the corresponding small arrow。

 select rename and call the columns first name and last name。

 Global superstore also need you to create a new data field for their returns。

 The field must include the final date by which each product can be returned under the company's returns policy。

 This is 15 days from the date purchase。 Select the small arrow in the orders date column and click create a calculated field。

 Na this new field return date in the calculation editor。

 enter the following basic formula order date plus 15。

 This formula adds 15 days to each order order date value。 This creates a new returns column。😊。

Populated with the relevant data When finished， click O the new calculated field is added to the data pane。

 Global superstore data has now been cleaned and prepared for analysis。

 and you should now be familiar with how to connect to data sources in Tableau and clean and prepare your own data for data analysis。

 Great work。

![](img/10b50ee5b76e448c622a7d1c58b77178_1.png)

![](img/10b50ee5b76e448c622a7d1c58b77178_2.png)