# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P10：Chapter 9 (PyTorch Extensions).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/dd25078a2fc15d30f8e1481cd2cfe1e3_0.png)

Now it might be a good idea to actually dig into pietorrch or not even dig into it。

 but rather understand how you can add on top of it。

 make things a little bit faster for your own custom use cases and whatnot。

We just finished up the Tri chapter。 I hope you enjoyed that。

 but now we're going to go a little bit more into Python and more on the torch side。

 So I've written a few files here。I have some descriptions about what's going on。

What's going on with all these like different types and names and stuff in in the Readme as well as some intuitive examples of what we're going to be looking at？

I wrote a。Set up script for just compiling a separate pyor extension。

 a separate function that we're going to use to do a polynomial。 It's a very simple operation。

And then a coup de script that is going to compile and bind into Pythtorch so that we can actually use it in Python and then the Python script itself。

 which we benchmark against。And naive pytorch。 So just all we're really doing here is x squared plus x plus 1。

 that's all we're doing。So going here。We have this include and this is giving us errors。

 but don't worry about this when we set up it's going to actually it's going to handle this properly。

 so we don't actually need a dedicated include file or any arguments for this we don't need to specify where the extension do H file is but going into the actual kernel itself so just like top to bottom we have this new thing called a template。

 I didn't go over this yet， but I did I guess I did in the in the Mamal section but。Templates。Is。

It essentially， if we go down， it'll help if we kind of go down and look at where this applies。

 So when we call this kernel。We do this， and then we provide our arguments， right。

 We have the kernel configuration here， and then we have this， this。

 This is where the template comes in。 So we specify this scalar underscore T type。

 And that essentially means。We're just going to make sure that。This， the X。The y or the input。

 the output are of this type。 And so this type is essentially going to be handled by pietorrch。

 And instead of specifying like a float or a double or like I don't know some other some other like maybe quantize like F P 16 pipe It's going to handle that for us。

 And it's going to just automatically recognize which one it is。

 and it's going to compile that down and deal with it appropriately。

 So this is something built into Ptorrch and it's custom type that we have。

 So this is kind of just like the default to use here。 easiest。 And then we have this restrict。

 So restrict。In short， essentially means we're not going to be overlapping memory。

 We're not going to be overlapping memory accesses。 So we have， we have X here。

 We have an output here。 All we're doing is we're doing an operation on this thing。

And then we're storing that in here。 We're not， we're not mixing things over。

 We're not doing two things on like the same location and then having some output that's stored。

 We're not doing anything messy like that。 So we can just say， restrict。

And that'll allow the compiler to aggressively optimize。Essentially what the binary code is。

 And so in here we simply just do a we do this over the x dimension。

 the typical k kernelnal depth indexing。And then we do you know the square the plus and then the plus one so that's the I mean the the kernel is surprisingly simple。

 there's just some new colors and new keywords to attention to pay attention for but。啊。

Then we scroll down a bit。 and that we got some C plus plus syntax going on。 What the heck does to。

 Well， we have this auto， which essentially figures out like which， which type to set this to。

 So it's going to recognize that this is going to be some torch type。

 And it's going to automatically select that。 And this is just torch dog and empty like。

 So it's going to have the same shape as X， the input， which is a torch tensor type。

 So auto is going to recognize， it's going to essentially going to。It's gonna。It's going to do this。

We'll just leave it at auto for now because it looks nicer。

And then we have our threads which the typical 10024 threads per block as per the maximum。

 and then we have our， you know numb elements plus the threads -1 and divided by number of threads。

 So this is the typical we already went over this。 There should be very trivial stuff。

And then we have。Essentially， just some， some extra stuff about。How the kernel is going to be called。

 so which which what things are we feeding into it？We return an output based on that。

 And then down here， we just have our Python bindings so。Don't worry about this too much。

 Just kind of trust the process。 I can kind of read off of like what I was able to find about this exactly。

 so。嗯。Pie Min 11 module， this。This is a macro that defines the entry point for the Python module。

 torch extension name。呃。It's a macro defined by pieytorrch that expands the name of the extension。

That's so usually defined from the setup do P Y file over here。Then we have an M and an M dot de。

So that adds a new function to the module。 So the first argument， polynomial activation。

Is the name of the function in Python？So that's the functional work and I'm calling green to be of polynomial activation。

 open close parenthe。嗯。The polynomial activation kuta pointer。诶。

Or it is a pointer to the C plus plus function to be called。

 and then the last argument is a dock string for the function。 So it's just like a simple doc string。

 It's not like entirely required， but we put it there anyways。So。Anyways。

 this is the this is the full kudos script。 this is essentially as simple as it gets。

 You can't really do anything more simple than this。

 So this is kind of like a template you can work off of。

And then in here we import our compiled polynomial kuda function。

 which we'll compile in a second here。We have a class， so we use torch autograd and。

By default when we do one autograd when we do an autograd function。

 we have to include a forward and backward method these are both going to be static so we just add this decorator that says this is compiled elsewhere。

And then forward， we're going to do。Just this polynomial activation。

 So comes from the binary error that we compiled and then。Plynomial activation of x， right。

 as we said before， and then backward。Backward， we just no't support it yet。

 so we could just say not implemented error， backward pass， not implemented。

And then in here where we actually do our in dot module that Pyth should be familiar or two。

 of course， this should look， this should be super easy to understand。

From from a separate standpoint， but we just do the init， we do the forward in here， we say。

 you know implementation is going to be the pi we just set it to a string pitorr。

 so it's kind of easy to read and then if the implementation is pitorrch。

 we do this raw and if it's not then we do this if it's ka。

 then we do this this other one which we specified up here so it's going to do this。

And it's going to apply that to X。And then else， we just， we just say， oh， if you did like。

 if you like miss the T， it would be like， oh you。Pie or is not implemented， right。

 under an implementationation。And then so we go down。

And let's just go to the main function first and then to the benchmark， so in here， random seed。

Normally distributed random tensor on device。Implementation on Pytorch implementation on Kuda。

 we move these to the device。 So to Kuda， this is just like essentially。

Saying that this function is going to be executed on that， you should have probably seen this before。

 it's not too bad。And then we do。We can actually just print out whatever that input was。

And then here we do Moly。Here we essentially just benchmark。

 so we go the actual activation function itself， the input we're doing it on。

 and then just a string that we're going to print in the in the name here。

 So here we just set a time， we go for a number of runs。

And then we coupa synchronize so we ensure everything is all caught up and then we end the time。

 and then we essentially return the name so whatever whichever these it was。嗯。The deelta time。

 so like the essentially the not the delta time but the difference。

 And then we divide that by the number of runs because we're doing an average at times a thousand so we can get it in milliseconds format and that just that just kind of works as we expected to now to actually compile this。

We to we go to the ReadMe and literally all you have to do is just Ion set up dot PY。



![](img/dd25078a2fc15d30f8e1481cd2cfe1e3_2.png)

Install， give that a second。It's going to use Ninja to build。嗯。So we'll give that a moment。

 but this is going to create see build a build folder in here。

I we'll print out forward and backward in a second。 we're going to print both of these so。Okay。

 awesome。 it just， it just wrote that out。 So now we can go ahead and iPhone poly nomin activation。

And it'll dill do these。 This couda activation， not forward of x。

And then it'll print whatever that output was。And so we get like a tensor and it actually formates properly。

 which you're like， oh my gosh， we just， we wrote this in Kuta and C。

 And now it prints so nicely like this。 Yeah， that's what Pytorrque does for you。

 And then we see that the pytorrch built in gets about 10。

47 milliseconds over over 1000 runs on average。 And then the kuta extension gets about 0。0。2，4。

3 milliseconds。So if we actually compare these。 So if I go。um。The this divided by。This。

 we will see the speed up that we get from Kuda。 So we get about a 4。31 x speed up。

 which is pretty good if you ask me， especially on bigger tensors， right， This would be awesome。😊。

So so that's that。 And if we actually do a do backward here， you'll see that it's both。

 you know a changed to white so that that's a good good sign that it doesn't work And if we actually run this it'll say has no attribute backward right so potentially raise the attribute error doesn't work。

And then we default back to forward。And it'll pop back to this to this end end do module。 Asome。

 Okay， so that's that's Pytor extensions for you。 You can feel free to add whatever you want to this。

So， you know， if you have your own custom like research that you want to add and make it super easy for others and yourself and your organization to use。

 To feel free to go down this route， copy this， copy this template code。

 do whatever you want with it。 this is just the easy， the easiest example I found to both you know。

 write and explain。 So yeah， thats that that is pretty much the first。The first， I don't even know。

 I'm not going to unify a per cent， but that was the majority of the course。 Now。

 we actually have a final project to go into。 So this final project is super exciting and is going to help you understand neural networks from scratch。

 how to optimize them for performance。😊，As well as like data loaders。

 we're going to add a bunch of things， a bunch of optimizations into making a real world training run。

