# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P61：14_grep.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

Gre stands for Global regularular expression print。

 and it's used for searching across files and folders as well as the contents of files。



![](img/dd76b9e4662dc6bd395eb3d374f5f5a9_1.png)

On my local machine， I enter the command LSl and see that theres a file called names。

ttxt If I access that file using the last command， it displays a list of first names in nonsequential order as in not arranged alphabetically。



![](img/dd76b9e4662dc6bd395eb3d374f5f5a9_3.png)

So what I'll do first is use Gr to find some patterns of names that start with similar matches。

 Then I'll also show how Gr can be passed with different flags to get different results。 First。

 I'll perform a standard search using Gr。 So what I'm going to do is look for names that begin with Sam。

 by entering the command Gr Sam names dot T X D。 This then returns a list of names that begin with Sam。

 Keep in mind that Grp is case sensitive。 which means if I run the same query with a lowercase S。

 It returns a completely different set of results。 because this query doesn't match the capital S。

 It returns partial matches in which Sam appears in the middle or end of a name rather than the beginning。

 Fortunately， I can pass in a flag to ignore case sensitivity。

I can do this with a command Gr minus I， followed by the keyword Sam， and then the file name。

 names dot TXT again。This time I get back both users that begin with SamM and also with SamM as a partial match in the middle or the end of the name。

 so the result set changes based on the type of query that I pass through with different flags。

 we can also do an exact match by passing in a different flag and that's the dashw。

 which means it'll match exactly what I'm looking for。

 so I'll input grab dash W and then pass in the keyword Sam with a capital S and finally our file name。

 names do TXD。In this case， we only get back a single result with the name Sam as any partial matches are ignored。

Lastly， I can use a pipe command to combine different searches for GP itself For example。

 let's say I went to search across a list of directories for certain executable files。

 I can combine that with different commands and search across the file structure to find exactly what I'm looking for if I check all the executable files inside the bin directory by running LS forward slash bin It returns a long list of results。

 in order to filter that down I can run the same query of LS forward slash bin but this time I'm going to pipe it。

Pass in a grip and then enter the keyword zip you'll find that in this case I get a much smaller subset back in the results。

 and if I need to refine it further then I can also apply the different flags to look for an exact match。

 a partial match or ignore case sensitivity。

![](img/dd76b9e4662dc6bd395eb3d374f5f5a9_5.png)