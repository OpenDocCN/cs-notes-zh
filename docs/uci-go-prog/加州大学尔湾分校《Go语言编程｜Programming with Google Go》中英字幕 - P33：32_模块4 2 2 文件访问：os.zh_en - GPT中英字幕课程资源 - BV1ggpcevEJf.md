# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P33：32_模块4 2 2 文件访问：os.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/08c1f9f8c9472bab420f0f34cff3e70a_1.png)

🎼う。🎼Yeah。So when you're accessing files， we talked about the IUU Ti。

 it gives you some simple functions， but if you want to have a little bit more precise control over file access。

 then you're probably going to use the OS package the OS package provides a bunch of functions to access files too and you can access you have more control so with IOU Ti you could read the whole file and write the whole file and that was about it with OS package you can do a little bit more read a little bit。

 write a little bit do different things。

![](img/08c1f9f8c9472bab420f0f34cff3e70a_3.png)

So here are some of the functions in there， first you've got OS。 open that opens a file。

 so you pass it the name of the file and it'll return a file descriptor， a file。

 a file struck to basically call it F， let's say and return a file descriptor that you can use to access the file。

Now OS dot close， it closes the file when you're done OS do read reads from a file into a byte array okay now and it reads to fill the byte array so you can control how much you read unlike with read file and I utility tell you had to read the whole file if you only want to read 10 bytes out of it。

 you can make a byte array a size 10 and pass that to read and read will fill that byte so it'll read 10 out。

Read however much you need to fill the by array and write is a similar thing。

 you can take a by array and write that into a file and it'll just write as much as the by array is long。

😡，So here's an example of file reading。Using the OS package。

 So first thing we do is we open the file。 So we call OS do open pass it the name of the file。

 which is completely arbitrary。 So we pass it this file name Dt dot text。 It opens it。

 It returns this F， this file handle that we can use to access the file and an error if if there's an error like the file doesn't exist as something like that。

 then it'll throw an error， but otherwise it'll return this file handle。

Now now I'm going for this file I want to read right I want to read into some byte array so let's say I want to read 10 bytes out of this file so I can make a byte array B array colon equal make I call make I make it a byte。

 I give it the type and I say comma 10， So I now I have this byte array， empty byte array。

Then I can call F dot read， F is the file handle that was returned by open， called F dot read。

 pass it the by array as the argument。And it will then fill that byte array with the first 10 bytes out of this file。

Now， note that if I called it again with that same by the array。

 it would fill by the array with the next 10， right every time it would would the read head actually move。

 So the first， I read the first 10， if I read again， it's not going to read the first 10 again。

 it'll read the next 10 until I close it and resets the head。

This function returns two things an error if there's an error So if you're trying to read something and you're out of space's you know it's empty or something like that you reach end to file it might throw an error。

 but otherwise it returns nb which is the number of bytes that it red Now sometimes the number of bytes should be equal to the size of the by array but it doesn't have to be you can have what's called a short read maybe the by array assign sizes 10。

 but there are only five bytes left in the file， then you only read5 out so Nb would equal5 in that case and then when you're done reading you just call f dot close and it closes the file and resets the head for the next time。

So next example is right。This time using using the OS package as well。

 So first thing we're going to do is we want to write a byte array into a file。

 So we first create the file in this case， OS do create， we could have opened a file。

 we could have opened existing file and opened it for a pen to aend to it。 But in this case。

 we're just going create just for an example。 We're going create a new file， call it out file text。😊。

And then we get this file handle F that refers to that file。

 Then we make a byte array with using a using a。Sorry， we make actually this is a slice。

 but we make a slice byte we're calling it B， but it's a slice， has three elements in it1，2 and 3。

 we want to write these So we call write F dot right。

 we pass it the byte array and it just writes those three bytes into the file。

 Now another thing that we can do there's another function for write called write string that takes an entire string instead of a byte array it takes an explicit string and writes that so you can call write string and high or something like that。

 pass it a string it writes that into the file。And which has to be a Uniiccode sequence。



![](img/08c1f9f8c9472bab420f0f34cff3e70a_5.png)