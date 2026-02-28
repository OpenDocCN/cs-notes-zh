# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p39 039_01_03_多重条件判断.zh_en -BV13E421M7FF_p39-

We can have multiple if conditionals， which means each condition will be tested separately。First。

 we ask the user to input an integer to evaluate in general。

 its good practice to confirm an input is numeric before casting it to an int。

 So here the isnumeric method checks if all characters in the string are numeric characters or digits。

😡。

![](img/a0bdadb1d76870811c20a62f9d276b5f_1.png)

![](img/a0bdadb1d76870811c20a62f9d276b5f_2.png)

![](img/a0bdadb1d76870811c20a62f9d276b5f_3.png)

![](img/a0bdadb1d76870811c20a62f9d276b5f_4.png)

If so， then we can cast to an int and then run through all of the separate if conditional tests。

First， we test if the number is greater than 20， if so， print the value。



![](img/a0bdadb1d76870811c20a62f9d276b5f_6.png)

Then we test if the number is also greater than 10。 If so， print the value again。



![](img/a0bdadb1d76870811c20a62f9d276b5f_8.png)

![](img/a0bdadb1d76870811c20a62f9d276b5f_9.png)

Finally， we test if the number is also greater than zero and print it again。



![](img/a0bdadb1d76870811c20a62f9d276b5f_11.png)

If the value is not numeric， meaning it failed， the initial is numeric test。

 print a friendly message。

![](img/a0bdadb1d76870811c20a62f9d276b5f_13.png)

![](img/a0bdadb1d76870811c20a62f9d276b5f_14.png)

Note that the isnumeric method only works with positive integers。



![](img/a0bdadb1d76870811c20a62f9d276b5f_16.png)