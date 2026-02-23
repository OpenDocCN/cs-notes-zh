# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P112：20_在Tableau中过滤和可视化数据.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Once you've imported your data into Tableau， you then need to prepare it for analysis， however。

 the process is more efficient if you focus only on the data you need to analyze with Tableau。

 you can focus on relevant data using the software's filtering and visualization features In this video。

 you'll learn how to filter data and create a data analysis chart in Tableau。

Over at global superstore， they're preparing to launch a new marketing campaign in Canada。 But first。

 they need to analyze their sales data to optimize their campaign。

 They can use data filtering techniques to arrange and exclude data so that their records are focused only on Canada。

 This provides a more relevant， reliable and accurate level of information。

 you can help global superstore to complete this task by using Tableau。 in Tableau。

 you can filter data in either the data source page or the worksheet。 However。

 filtering data directly in the data source page limits your data analysis and all worksheets to the filtered criteria only。

 For example， if global superstore filter their categories to include only office furniture。

 then they can't perform data analytics in other categories in the worksheet。

 Let's begin by applying data filtering in the data source page。 Click the add option under filters。

 This opens a dialog box that lists all filtered fields in the data source。

 Click add again to add an。

![](img/bb0aace7113b971246929f235a9c6f18_1.png)

![](img/bb0aace7113b971246929f235a9c6f18_2.png)

New filter field。Next， select Region and click OK。

![](img/bb0aace7113b971246929f235a9c6f18_4.png)

Click the select from list option in the general tab area， check Canada， then click OK。



![](img/bb0aace7113b971246929f235a9c6f18_6.png)

The data pane now shows filtered records from Canada only you can repeat this process to add more data source filters if required。



![](img/bb0aace7113b971246929f235a9c6f18_8.png)

To remove a filter， click Edit filter， select Canada， then remove and OK。

 you can also filter data in the worksheet。

![](img/bb0aace7113b971246929f235a9c6f18_10.png)

![](img/bb0aace7113b971246929f235a9c6f18_11.png)

Open the sheet tab at the bottom of the page in the worksheet。

 the columns from your data source are displayed as fields on the left side of the data pane。

 The data pane contains a variety of fields。 The fields above the gray line or dimension fields。

 The fields below the gray line are measure fields。 dimension fields hold categorical data。

 In the case of global superstore。 This includes product categories， types and dates。



![](img/bb0aace7113b971246929f235a9c6f18_13.png)

![](img/bb0aace7113b971246929f235a9c6f18_14.png)

![](img/bb0aace7113b971246929f235a9c6f18_15.png)

Measure fields hold numeric data like sales， profit and quantity。

Global superstore want to compare sales of all category products sold in Canada to help them with this task。

 drag the category field from the dimension section of the data pane to the rows in the shelf area。

 then drag the sales field from the measure section in the data pane into the columns in the shelf area。

 the horizontal bar chart that appears shows information about different product categories。



![](img/bb0aace7113b971246929f235a9c6f18_17.png)

![](img/bb0aace7113b971246929f235a9c6f18_18.png)

You need to filter this data to show only products sold within Canada。

 drag the region dimension from the data pane to the filter card This opens a pop up window。



![](img/bb0aace7113b971246929f235a9c6f18_20.png)

In the general tab， select Canada， then click applyly and OK。



![](img/bb0aace7113b971246929f235a9c6f18_22.png)

Your data is now filtered to show sales in Canada only。

 you can also take further steps to make your chart easier to read and understand。

 Click the swap icon to change the horizontal bar to a vertical chart。

 Click the descending order icon to filter data from maximum sales to minimum sales。

 drag sales to the color part in the mark section of the screen to change the bar colors based on sales。

 drag profits from the data panes measuresure section to the label mark。

 This shows the profit of each category in the chart。 You can also provide a title for the sheet。

 In this instance， you can call the sheet sales in Canada。

 A lot of the information in the chart is generic。

![](img/bb0aace7113b971246929f235a9c6f18_24.png)

![](img/bb0aace7113b971246929f235a9c6f18_25.png)

![](img/bb0aace7113b971246929f235a9c6f18_26.png)

![](img/bb0aace7113b971246929f235a9c6f18_27.png)

![](img/bb0aace7113b971246929f235a9c6f18_28.png)

![](img/bb0aace7113b971246929f235a9c6f18_29.png)

![](img/bb0aace7113b971246929f235a9c6f18_30.png)

![](img/bb0aace7113b971246929f235a9c6f18_31.png)

It might be better to add the subcategory to the view to provide more detail around the sales and profits。

 drag the subcategory field from the dimension section of the data pane to the columns in the shelf area。



![](img/bb0aace7113b971246929f235a9c6f18_33.png)

![](img/bb0aace7113b971246929f235a9c6f18_34.png)

Then click on the descending order icon to filter data from the maximum to the minimum values。

You can now view all categories and subcategories， you can even focus on one category like furniture。

Drag the category dimension from the left data pane to the filter card。

 then use the filter categorical data option to retain the furniture category while unchecking the technology and office supply categories。

 click applyly then OK。

![](img/bb0aace7113b971246929f235a9c6f18_36.png)

You can also filter categories according to best selling items。

 drag the subcategory to the filter card， then select the top tab。

 tick by field and enter a numerical value of two to view the top two categories， then click Apply。



![](img/bb0aace7113b971246929f235a9c6f18_38.png)

![](img/bb0aace7113b971246929f235a9c6f18_39.png)

![](img/bb0aace7113b971246929f235a9c6f18_40.png)

The wild card can also be used to filter data on specific patterns。 For example。

 you can type chair in the text field to include subcategories that contain this text value。



![](img/bb0aace7113b971246929f235a9c6f18_42.png)

![](img/bb0aace7113b971246929f235a9c6f18_43.png)

![](img/bb0aace7113b971246929f235a9c6f18_44.png)

In this instance， the data returns the chair subcategory。

Another filtering technique is condition filtering you can use condition filtering to select a field of data and define specific rules to be applied。



![](img/bb0aace7113b971246929f235a9c6f18_46.png)

![](img/bb0aace7113b971246929f235a9c6f18_47.png)

For example， you can select the sales field， then specify a sum value greater than 500，000。

 click apply and then O。 This returns all values within your data greater than 500。

000 to remove all subcategory filters just right click the subcategory and click remove。

 You can also remove the category and keep the region to focus on Canada。



![](img/bb0aace7113b971246929f235a9c6f18_49.png)

![](img/bb0aace7113b971246929f235a9c6f18_50.png)

![](img/bb0aace7113b971246929f235a9c6f18_51.png)

![](img/bb0aace7113b971246929f235a9c6f18_52.png)

You can now view all sales data related to the furniture category and subcategories in Canada。

Global Superstore has now filtered the required data for data analysis using Tableau。

 and you should now also be able to apply different filtering techniques to your data using Tableau you're making great progress on your data analytics journey。

