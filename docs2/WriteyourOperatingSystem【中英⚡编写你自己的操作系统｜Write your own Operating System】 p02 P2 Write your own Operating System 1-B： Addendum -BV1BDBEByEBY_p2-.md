# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p02 P2 Write your own Operating System 1-B： Addendum -BV1BDBEByEBY_p2-

Hello and welcome back to the tutorial on Writing Your own operating system。So this is a bit awkward。

In the last video， I forgot something， and I want to fix this error。 now。

 I'm recording this video after I've recorded video 5。 So the thing I forgot isn't。Yeah。

 it didn't cause any problems。Really， but it's somehow because of the way I program。

 So the problem is that I told you in the in the linka script， we put all the constructors。

Into those script and。So they are in the binary， but they are never called and。

This only is a problem for global objects and static objects in classes。And。

And also only for composite objects。 So class instances， and I'm not even sure if。

 if it affects structure instances。嗯。Probably it should affect structure instances。嗯。But， you know。

 I usually don't work with static composite objects。 If anything， I work with a pointer to it。

 and the pointer is。It's a primitive data type。Then the problem doesn't occur， you know。

 so that's why I really got it through through the videos until part five without even running into a problem。

But let's fix this。 Let's fix this quickly so。

![](img/d7952cfc3f079aabc9e3d87b895421ec_1.png)

So as I've told you， we are putting the constructors here。And。We also。P these。Two things here。Right。

 so。These two things we， we put here actually point us， which will be known outside to。

 They will be known to the。To the other object files。Right， so。So here we have star C tos。

Start constructors， and then。In the kernel CPP， we can have something like。Next time。See。

Pointed to a constructor， called it。

![](img/d7952cfc3f079aabc9e3d87b895421ec_3.png)

Start Cs。 So， so that， so then we can use this start see as as a pointer to。



![](img/d7952cfc3f079aabc9e3d87b895421ec_5.png)

To the constructor， right， and。You can also do the same thing with the end。And CTs， which is。

Which is this point I here。Okay， so now we have these pointers to the constructors so。



![](img/d7952cfc3f079aabc9e3d87b895421ec_7.png)

The thing is the following。If we have something like a global object。

 so here we have the kernel main。Function， right in the kernel dot CP。

 And let's say we have an instance of class。Have a call bar。 and this actually has parameters like。

42。Okay。So the the constructor gets a parameter。Now。

 what the compiler does is so this is a global object， and it's supposed to be。

It's supposed to be available everywhere in in the program。 right。

 So what the compiler does is it creates something like。Like a function void。X， Y， Z。

 I don't know It doesn't get a name actually without a parameter that' is important。

And in this parameter， it just calls this constructor。Okay， so。We do something like。

Its42s or whatever。 So so inside this anonymous function。

 this parameter is pushed and the function itself doesn't have a parameter okay and then the address of this X。

 Y， Z is just put between。This start C to and and sea to pointer， Okay， so。In the binary。

 we will have。We will have an address。Ill stop CT tos。And the address enter Cs。

And then we would have the address of this X， Y Z in here。Okay， so。The problem now is。

So we have this address， but we have never called this so。

So that this object isn't actually initialized， Okay， so we need to do that now explicitly。



![](img/d7952cfc3f079aabc9e3d87b895421ec_9.png)

Okay。So now we have defined what this constructor means。 So this is just a function pointer。

And start C tos is the address of the first constructor call and N CTs is the call behind the address of the last constructor。

So。So now we can put another function here， but it。嗯。Call your constructors。Okay。

 and this just iterates over， over the space between start Cs and N Cs and calls call and jumps into all the。



![](img/d7952cfc3f079aabc9e3d87b895421ec_11.png)

Into all the the address point the function pointers。



![](img/d7952cfc3f079aabc9e3d87b895421ec_13.png)

So。Okay， so we it over them。 And then in here， we just。We just invoke his constructor cards。Okay。

So we just have to add this and。In the in the loader dot S。嗯。嗯。Yeah， we。

 we tell it that there is this。This function called constructors， and。嗯。

After we have initialized the stack， we can just。嗯。Call this function。 And after we did that。

 then everything is set up。 and then we can jump into the kernel main okay。



![](img/d7952cfc3f079aabc9e3d87b895421ec_15.png)

So， yeah， this is all we need to do to fix this little mistake and。So， sorry about that。

See you next time or next time we will。Talk about the global descriptor table， and。Yeah。

 that's a bit tedious， but。We need to get through that in order to get to the interesting part。

 So we'll see you next time。

![](img/d7952cfc3f079aabc9e3d87b895421ec_17.png)