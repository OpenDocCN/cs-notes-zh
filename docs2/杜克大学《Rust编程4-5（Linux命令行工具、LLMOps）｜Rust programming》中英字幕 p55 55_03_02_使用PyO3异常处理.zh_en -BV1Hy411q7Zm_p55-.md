# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p55 55_03_02_使用PyO3异常处理.zh_en -BV1Hy411q7Zm_p55-

![](img/d5e0da94a79de75bf623e06cee0df5af_0.png)

Python exception handling in rust is an interesting problem to deal with because of the fact that you are able to get a different type of response in rust right where you have errors。

 But in Python， you have exceptions。 So how do you do this。 Well。

 first up in raising exceptions here。 you can see here that you can use a new pi error instance or pi error from type to create a Python exception。

 And then pi error raiseds to then raise it in Python。 On the other hand， to handle the exceptions。

 You can use dot map error。😊，To move a rust result error into a Python exception or use P function attribute and return pi result。

 And you can see this in this function from rust below。

 So let's go ahead and take a look at how this works in action here with some real code。



![](img/d5e0da94a79de75bf623e06cee0df5af_2.png)

I have a project here calledR Excepts。And inside of this rust exceptions here。

 I have some Python code。 But first， let's look at the lib here。 So we are using pio3。

 and I'm using piyo3 exceptions here， and I have a pi0 division error。 So this particular function。

 it raises a zero division error， if B is0。 So we do a divide here。 and it says if B is 0。

 then go ahead and return a division by ear by0 exception。

 and I put whatever exception message I want to make it useful for someone in Python。

 and then I put this into a module here。 So I say a Python module implemented in rust。

 and I say p module function， Lib rust exception， and then all this does is expose the function from above right this rust function into Python。

Now， in order to use it， what I typically do is I go to a make file and I have a build process that creates a cargo build release and then I copy that do So file into the current working directory so I can import it from Python so let's go ahead and do that I'll just type in make build there we go。

 it compiles afterwards， it'll copy the successful compilation dos file into the current working directory and you can see that right here。

 we have Libras exceptions。 we're ready to go now all I need to do is call from Python so let's go ahead and look at this pydiv。

 Py。First， I import Lib rust underscore exceptions。 again， this is the same name as that dot So file。

 and also if we look at Lib RRS， we can see here that that function is the same。

 So if we go back here， then I print that divide function which has the exception hidden inside and again we go back here。

This is that rust function。 So once I've done that， all I need to do is just do a try block。

 and I say try， and I say Lib rust exceptions dot divide divide by 0。 And then we see that there is。

 in fact， a exception handle that I'm doing here。 So I'm saying， look， let's go ahead and try this。

 But if there is a zero division error。 Let's go ahead and capture it。 And let's do some other thing。

 In this case， I'm just printing。 But it could be some other operation or some other function。

 whatever it is whatever logic you want to do to handle that exception。

 So let's go ahead and run this if I type in pdiv。There we go。 We see that it says 5。

0 is the first one， right， we know that it works。 But then when I try to divide by 0。

 which is invalid， it says triggered exception from rust。

 and then we see the embedded message as well that's included inside of LibarRS， which could be。

 again， anything that we wanted to do。 So you can see there's a pretty sophisticated by simple way to handle the errors in rust。

 and then propagate them as exceptions in Pythlon。

![](img/d5e0da94a79de75bf623e06cee0df5af_4.png)