# 宾夕法尼亚大学《Python和Java编程入门1-2｜Introduction to Programming with Python and Java》中英字幕 p104 104_04_10_编程演示-打开读取并写入新文件.zh_en -BV13E421M7FF_p104-

Now let's create an open Readrite new file function that copies the text in one file to another file。

😡。

![](img/ddd874c6daaa910f47eac3a16a83f812_1.png)

Let's create our function to， open， read。Right new file， which opens one file， reads it。

 and then copies it to another file。Opens the first file， and reads all。Taxed as a string。Coopies or。

Right。All text 2。The second file。We only need to read the first file， so we'll open it in read mode。

 We'll use the with keyword， open file 1。I'm not going to provide the mode。

 So it's going to default to read as F I N。 That's our variable。And again。

 this is open the first file for reading。And I'm going to read all the lines in the file as a single string。

 so FIN dot。Read。And then we'll call that。Text。Reads all lines as a single。String。😔。

Then we'll open the second file for writing， so open。File 2 in right mode。Open second file in。

Right mode。We'll call that F O U T。We'll writeite the text to that file。 F O U T dot right。

The given text。So write single string to second file。And then， close the second file。

Close second file。 Since we're using width with the first file， we don't need to explicitly close it。

Now let's call our function。 Let's go ahead and comment this out。 We're going to call open， Read。

 write new file， the file to open and read news TXT。

 the file to write to is going to be news underscore copy do TXT。 It doesn't yet exist。

 but we're opening it in write mode， So it'll actually create it for us。run this。

And here I see a new file in my directory， newsscopy。 And if I take a look at that。

 that looks just like our original news file here， which has been copied here。



![](img/ddd874c6daaa910f47eac3a16a83f812_3.png)