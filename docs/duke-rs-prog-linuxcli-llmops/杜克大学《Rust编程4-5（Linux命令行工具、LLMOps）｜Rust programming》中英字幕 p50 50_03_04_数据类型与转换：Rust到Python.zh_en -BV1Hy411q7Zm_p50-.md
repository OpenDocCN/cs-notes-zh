# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p50 50_03_04_数据类型与转换：Rust到Python.zh_en -BV1Hy411q7Zm_p50-

![](img/23beebbe736a3e23297071426d5a9724_0.png)

Here we have a project that does something that is very common when you're converting between Python and rust。

 which is you have a particular data type and you want to convert it into a Python data structure。

 So how do we do this first up here。 you can see that the lib is the location where all the cota。

 So inside of source Lib dos inside of a directory called data hyphen conversion。

 I've got a import here that says use P03， and there's some libraries that are imported。

 including the Python dictionary。 Next step， what we do is we have a Python function here。

 which is going to do the heavy lifting and we say function data types example pi and then we have a P result object right here and then we define our rust types here。

 So we say text and this is a string we have integer， this is I32。 we have floating F 64 and we have。

Boool， now， what we do is we create a Python dictionary。 So， again。

 this is a traditional Python dictionary people are used to， but we're doing it from inside of rust。

 And we're using lead here。And then what we do next is we say Python diict dot set item。

 and we actually go through here and insert a key value pair one by one。

 So we say set the integer to integer， the floating to floating， the Boolean to Boolean。

 and then finally we go through and return that Python dictionary。Now。

 in order to use it as a rust module， all we need to do here is say pi module and say FN Lib data conversion。

Pass that inside of here and return back a pi result。 And this is the magic part right here。

 which is that data types example function with the input。Again， right here。

 this is actually being called down below。 Now， if we go over to a make file。

 which I think is a great way to build things， we have a cargo build release。

 and then I copy the dot So file into the current working directory。 So let's go ahead and run that。

If I type in。Make build。There we go。 Pretty easy。 We're able to actually get this thing working。

 And if I look inside as well， we should see an S file， and there we do see this S file。

 Now all I need to do is go to Python and actually build a little bit of code。 In this case。

 I just import the name of that dot S file without， of course。

 the dot So and then I call the function that's associated。 So again。

 the function is what lives right here。 This is the function that we're exposing。😊。

Then if I go back here and I say print data type， we should get something like this。

 So all I need to do because I've already made this executable is type in convert。And here we go。

 we're able to convert the rust data types into Python and then print that out so you can see here it's pretty straightforward to actually take something that is originating for rust。

 let's say you're doing a bunch of fancy， computationally expensive operations。

 put those into this Pio3 system， go ahead and create a dot So file。

 put that So file in your directory， go ahead in and call it from inside of a Python script and you're ready to go。



![](img/23beebbe736a3e23297071426d5a9724_2.png)