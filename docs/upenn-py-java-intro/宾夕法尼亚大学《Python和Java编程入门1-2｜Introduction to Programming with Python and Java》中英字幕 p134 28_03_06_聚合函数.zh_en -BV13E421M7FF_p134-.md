# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p134 28_03_06_聚合函数.zh_en -BV13E421M7FF_p134-

To display summary statistics other than the mean， use the Ag funk parameter to specify the aggregation functions。

Use the values parameter to specify the columns for agfunk， Like before。

 use the aggregation methods from the Numpy package。In our data。

 how many reviews does each city have？Create a pivot table in index on state and city。

For the values to aggregate， specify the review count column because that's the column we're going to get the sum of。

For Agfunk， specify the aggregation method to apply， we'll use the sum method from the Nmpy package。



![](img/98f343c197afc71b3657bf6b2fd5f389_1.png)

It's possible to further segment the results by using the columns parameter here again。

 we create a pivot table in index on state and city。



![](img/98f343c197afc71b3657bf6b2fd5f389_3.png)

Then we specify the values to aggregate， review count， and the aggregation method to apply。



![](img/98f343c197afc71b3657bf6b2fd5f389_5.png)

We also specify the columns parameter for further segmenting the results based on takeout。

We can see the number of review counts per city。And then separated based on whether or not the business provides takeout。



![](img/98f343c197afc71b3657bf6b2fd5f389_7.png)

We can also pass as an argument to Agfunk in the form of a dictionary object containing different aggregate functions to perform on different values。

You can have multiple keys and values。

![](img/98f343c197afc71b3657bf6b2fd5f389_9.png)

If we want to see the total number of review counts and average ratings。

 we can specify it using this format。Create a pivot table。

 passing a dictionary object with the name of a column as the key。

 and the aggregate method to apply to that column as the value。In this case。

 review count is a key and NumpI's sum method is the value to apply to the Review count column。



![](img/98f343c197afc71b3657bf6b2fd5f389_11.png)

Stars is another key， and Numpy's mean method is the value to apply to the starss column。



![](img/98f343c197afc71b3657bf6b2fd5f389_13.png)

![](img/98f343c197afc71b3657bf6b2fd5f389_14.png)