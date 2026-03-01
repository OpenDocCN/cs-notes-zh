# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p96 096_04_02_文件打开方法模式基础.zh_en -BV13E421M7FF_p96-

More about the file open modes。R is read mode， which is the default mode。

 The format is the open function with a given path to file and the R mode。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_1.png)

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_2.png)

This opens the file for reading and returns in error if the file doesn't exist。 Note。

 since this is the default mode， you can leave out the optional R like so。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_4.png)

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_5.png)

W indicates right mode， the format is the open function with a given path to file and the W mode。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_7.png)

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_8.png)

This opens the file for writing and removes all old data if the file already exists。

It also creates the file if it doesn't exist。

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_10.png)

A is for a pen mode。The format is the open function with a given path to file and the A mode。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_12.png)

This opens the file for app pending and creates the file if it doesn't exist。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_14.png)

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_15.png)

R+ is rewrite mode， the format is the open function with a given path to file and the R+ mode。



![](img/ecfdd5352c9eef91a1fa613d3558cfe0_17.png)

This opens a file for reading and writing at the same time and returns an error if the file doesn't exist。

 it does not remove old data from the file。

![](img/ecfdd5352c9eef91a1fa613d3558cfe0_19.png)