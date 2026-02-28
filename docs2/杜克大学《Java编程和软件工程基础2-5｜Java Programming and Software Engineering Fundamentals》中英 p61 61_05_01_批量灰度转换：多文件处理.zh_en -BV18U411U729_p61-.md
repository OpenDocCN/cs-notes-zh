# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p61 61_05_01_批量灰度转换：多文件处理.zh_en -BV18U411U729_p61-

![](img/db7f41611f6bf3622a9fc86933f72ffa_0.png)

Welcome back。In this lesson， you're going to look at the problem of converting images to gray scale。

 This is an example of solving a real problem by writing two programs and combining them into a single program。

😡，Why might you want to convert an image to grayscale， there are several reasons。



![](img/db7f41611f6bf3622a9fc86933f72ffa_2.png)

You may want to see how images would look if you print them in grayscale。

 grayscale printing is much cheaper than color printing。

 and some publications require that all images be converted to grayscale。

Or you might be planning to do some other， more complex image processing。

That processing could be simplified or even sped up by working with grayscale images。

If you just need to convert one image to grayscale。

 the easiest thing might be to use an image editing program。 you already know， you'd open the image。

 the one you want to convert， and then you'd use the program to create a grayscale copy。😡。

But what if you need to convert many images to grayscale？



![](img/db7f41611f6bf3622a9fc86933f72ffa_4.png)

It can be quite tedious and time consuming to open each image up。

Transform it to grayscale and then save it。For a few images， this may not be a big problem。

But what if you need to operate on 1 thousand images， it would take days to do this by hand。

If you could even make yourself complete this repetitive task over and over and over。Instead。

 you could write a program to convert many images to grayscale。In particular。

 you might ask the user to select some group of images to convert。😡。

Perform the grayscale conversion on each of the selected images。

And then save the results using file names， which were similar In our example。

 you'll add a gray dash prefix to the beginning of each image file name to distinguish the new grayscale copy from the original。

 This is exactly what we're going to work with you on in this lesson in particular。

 we're going to break this large task down into a few smaller tasks。

 One aspect of the problem is to allow the user to select a group of files and to do something to each of the selected files。

😡，While you ultimately want to convert image files to a grayscale version。

 we'll start out by simply printing the selected file name。

 a small step toward the solution to the larger problem。Next。

 you'll work through how to convert one image to grayscale using our seven step process。



![](img/db7f41611f6bf3622a9fc86933f72ffa_6.png)

After that， you'll combine these first two ideas and programs。

Into a single program that allows the user to select many files and convert each of these files to grayscale。

Finally， you'll make your program save the results。

To new files with the appropriately named file names。

