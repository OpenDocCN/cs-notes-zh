# 【基于LLVM和MLIR构建编译器】 p10 How to build a compiler with LLVM and MLIR - 10 Pass Infrastructure -BV1vi421Y7P1_p10-

Welcome to another episode of How to build a compiler with LLVM and MLOR。



![](img/175e489c9e191d7e5631039ecf128480_1.png)

In the previous episode we had a brief look over how to create a new dialect in MLIR and how to use that dialect to generate some IR we created a new dialect called SLIR with just few operations and we managed to generate IR we want based of SLIR。

That was the first step into the MLIR worlds and as the next step for us。

 we need to use that dialect and lower that dialect into other dialects of MLIR built in dialects of MLIR。

 or even directly lower it to LLVMIR。

![](img/175e489c9e191d7e5631039ecf128480_3.png)

But before we can do that， we need to know more about the pass infrastructure。



![](img/175e489c9e191d7e5631039ecf128480_5.png)

So our episode today is all about passes and we're going to postpone the lowering and the concept of lowering to the next episode。



![](img/175e489c9e191d7e5631039ecf128480_7.png)

Before we continue with our discussion today， a quick update about what happened in past two weeks。

 I was working like I was working on the JIT。嗯。Out of nowhere randomly I noticed that the binary size of serene is quite large。

 it was like 85 megabytes。I was like， okay， I need to investigate this thing and during the course of investigation I had to refactor the entire peel system so I refactored the CM files and everything they're quite nice now。

 much cleaner and very structured。

![](img/175e489c9e191d7e5631039ecf128480_9.png)

And I managed to lower it down to 60 megabytes， but as a result。

 so the reason why the binary is so big at the moment is that，In order to link the object files。

 I use Kang， not as like a dynamic process， I link against some of the libraries inside Kang to figure out what linker is in installing the host machine and use that linker to link all the object files together。



![](img/175e489c9e191d7e5631039ecf128480_11.png)

![](img/175e489c9e191d7e5631039ecf128480_12.png)

It's not like optimal， but I had to do it because I didn't want to deal with discovering different linkers and to deal with the different interface they might expose and all that Kang already does it so I use the same stuff in Kang。



![](img/175e489c9e191d7e5631039ecf128480_14.png)

But recently in LLV and 14， apparently LLD actually exposes an API for the front end to use LLD directly。

 so I can call to that API and ask LLD to link all the object files I have and。

I can actually link aesthetically against that interface， so a part of LLD will be in my binary。



![](img/175e489c9e191d7e5631039ecf128480_16.png)

嗯。Which， in turn， is going to be。Like， I guess， smaller than clang。That's just a guess。

Based on some quick calculation and some estimates。

 I guess like the binary size will be down to 20 megabytes or so。But， we'll see。

As a result of changing the pill system and refactoring the。



![](img/175e489c9e191d7e5631039ecf128480_18.png)

Smic files now I moved some directories around， so we used to have a pin directory in the root directory that contained the serring sea binary now I moved it to。



![](img/175e489c9e191d7e5631039ecf128480_20.png)

SRC directory so if you look into the SRC we have two new directories lip serin and serin C lip serin is like the core functionality as we had before I just renamed it to lip serin。

 it's an object object library meaning that CMake。

![](img/175e489c9e191d7e5631039ecf128480_22.png)

![](img/175e489c9e191d7e5631039ecf128480_23.png)

Willll just。Compile all the CPP files into objects and then link them with any target that we have any binary target that we have。

 And at the moment， we have just one binary target。

 which is like not binary target that's around there， but I mean。

Native executable binary right now and that's there you see。

This is like the old bin directory in the route， I moved it in here and。



![](img/175e489c9e191d7e5631039ecf128480_25.png)

I'm pretty sure I'm going to refactor this thing in the future， it's not nice at the moment。

 it just gets a job done and yeah that's it like that's the entire thing I did in past week it mostly I was investigating the size issue and this week I have to go back working on the JIT a little bit。



![](img/175e489c9e191d7e5631039ecf128480_27.png)

![](img/175e489c9e191d7e5631039ecf128480_28.png)

Anyway。

![](img/175e489c9e191d7e5631039ecf128480_30.png)

Continuing on the topic of today， what is a path？

![](img/175e489c9e191d7e5631039ecf128480_32.png)

A pass pass is a concept in both LLVM and MLOR， and a pass is the unit of transformation and optimization in both LLVM and MLOR。

While both of them have a concept of PA and they're quite similar to each other。

 even the API is identical， almost identical。

![](img/175e489c9e191d7e5631039ecf128480_34.png)

But the， the thing is。Passsses in MLIR since MLIR is like a high level IR and like。

It can like any IR， any dial like N MLIR contains operations and some stuff that LLVMIR doesn't。



![](img/175e489c9e191d7e5631039ecf128480_36.png)

That makes the passes in MLIR a bit different than LLVM， but the concept is the same。

 the pass is some entity that we use to transform and optimize a formal IR to another form。



![](img/175e489c9e191d7e5631039ecf128480_38.png)

![](img/175e489c9e191d7e5631039ecf128480_39.png)

If we have a look at， oh by the way， today we're going to spend most of our time talking about MLIR passes。

 but most of the things that we talk about today applies to LLVM Pass as well。

 but we might have another episode in the future talking about LLVM passes。



![](img/175e489c9e191d7e5631039ecf128480_41.png)

![](img/175e489c9e191d7e5631039ecf128480_42.png)

Only， but really。

![](img/175e489c9e191d7e5631039ecf128480_44.png)

If you look at the if we look at any compiler around us。

 like the main thing that a compiler does is to read some code。Do something with it， and。

Created like a result。That do something with it is kind of。

Like the big hair picture is really simple， it reads the file。

 transform that input source code to an ASD， then transform that ASD to maybe another form of ASD。

 then transform the ASD into a form of IR and。

![](img/175e489c9e191d7e5631039ecf128480_46.png)

![](img/175e489c9e191d7e5631039ecf128480_47.png)

This loop goes on till we get to the target code。

![](img/175e489c9e191d7e5631039ecf128480_49.png)

It's kind of obvious to see that the whole compilation process is like we can break it down into a smaller pieces。

 a smaller logic， like pieces of logic that we can apply on each step。



![](img/175e489c9e191d7e5631039ecf128480_51.png)

And generate a new result of the result of the previous， right？



![](img/175e489c9e191d7e5631039ecf128480_53.png)

嗯。It's kind of similar to function composition in math。

It's like we can abstract every the logic and only think about different stage。

 different stages in the compilation process。

![](img/175e489c9e191d7e5631039ecf128480_55.png)

![](img/175e489c9e191d7e5631039ecf128480_56.png)

We can kind of abstractly think about it as a pipeline of functions。

 a function composition that each function is responsible for reading the result of the previous function as the input and do some optimization or transformation to that input and generate a new output and pass it down to another function。



![](img/175e489c9e191d7e5631039ecf128480_58.png)

![](img/175e489c9e191d7e5631039ecf128480_59.png)

Basically， each function that were talking right now talking about right now。

 each abstraction that we kind of encapsulate some logic in it is similar as passes。

 So passes are some abstractions in MO or and LLBM that。



![](img/175e489c9e191d7e5631039ecf128480_61.png)

![](img/175e489c9e191d7e5631039ecf128480_62.png)

Operate operate on the IR level and read the IR related to them or corresponding them and do some transformation and generate a new one。



![](img/175e489c9e191d7e5631039ecf128480_64.png)

In order to like categorize and group those passes together， we need something called pass manager。



![](img/175e489c9e191d7e5631039ecf128480_66.png)

Or as I like to call them pipelines， because that's how MLIR documentation refers to them sometimes。

And makes more sense to be honest， so we can create pipelines of transformation out of different passes。

 each pass has a logic to do some sort of transformation on the IR itself。



![](img/175e489c9e191d7e5631039ecf128480_68.png)

So we can group them together on past managers and create pipelines。

 we can have several pipelines and we can nest them inside each other to get what we want out of our major pipeline。



![](img/175e489c9e191d7e5631039ecf128480_70.png)

![](img/175e489c9e191d7e5631039ecf128480_71.png)

![](img/175e489c9e191d7e5631039ecf128480_72.png)

So。We know that all what。Like we know that most of the thing that a compiler does happens in stages and happens in passes。



![](img/175e489c9e191d7e5631039ecf128480_74.png)

Sorry。😔，It's kind of obvious to see that most we're going to spend our majority of time in。

Writing passes or working on different passes。Basically to transform our different shapes of IR into a final IR that we need。

 which is LLVMIR in our case， and even on LLVMIR， we're going to optimize it。

 run some passes on it to get to like a optimal version of optimal and finalized version of LLVMIR and finally pass it down again to another pass manager to generate object files out of that IR。



![](img/175e489c9e191d7e5631039ecf128480_76.png)

![](img/175e489c9e191d7e5631039ecf128480_77.png)

![](img/175e489c9e191d7e5631039ecf128480_78.png)

![](img/175e489c9e191d7e5631039ecf128480_79.png)

So from now on， of course， when we're finished with the compiler wiring and the bare minimum compiler that we need。

 we're going to spend most of our time writing different passes。



![](img/175e489c9e191d7e5631039ecf128480_81.png)

That was the big picture， that was like gist of how Passs works in MLIR。

 but now let's have a look at how we can actually define a path。



![](img/175e489c9e191d7e5631039ecf128480_83.png)

![](img/175e489c9e191d7e5631039ecf128480_84.png)

So there's two like any other places in LLVM and MLIR， there's two way to actually define a path。



![](img/175e489c9e191d7e5631039ecf128480_86.png)

Either in C++， purely in C++ or via ODS。

![](img/175e489c9e191d7e5631039ecf128480_88.png)

I。

![](img/175e489c9e191d7e5631039ecf128480_90.png)

I didn't use ODS for generating a pass yet， but based on the documentation and based on my previous experience with ODS。



![](img/175e489c9e191d7e5631039ecf128480_92.png)

It must be much nicer than writing everything in C++ it helps us to avoid a lot of boilerplate。

 but for now since all the passes that I have in the Ser compiler right now。

 they all are kind of specialized in lowering SLIR and other dialectgs to each other to LLVMIR。

 I didn't need to use ODS， but in the future I'm reckon that it's going to be much nicer to write passes in ODS in compared C++。



![](img/175e489c9e191d7e5631039ecf128480_94.png)

![](img/175e489c9e191d7e5631039ecf128480_95.png)

![](img/175e489c9e191d7e5631039ecf128480_96.png)

![](img/175e489c9e191d7e5631039ecf128480_97.png)

Look at the documentation， there's plenty of documentation around how to define a passing ODS spot today we're going to look at the C++ stuff because that's what we're going to use in the next episode。



![](img/175e489c9e191d7e5631039ecf128480_99.png)

So in in MLIR passes operate on operation level， so the operation itself is the main abstraction unit for transformation when we create a pass that pass。



![](img/175e489c9e191d7e5631039ecf128480_101.png)

Opers on one。Operation at a time depends on the pass type I'm going to talk about that in a bit。

 but it's not like that we can write a pass to operate like on and a specific attribute like among operations that's not the case so we can only write passage for on operation level。

 not any further than。

![](img/175e489c9e191d7e5631039ecf128480_103.png)

![](img/175e489c9e191d7e5631039ecf128480_104.png)

So in order to create a new pass， we have to create a class that is a subclass of operation path。



![](img/175e489c9e191d7e5631039ecf128480_106.png)

![](img/175e489c9e191d7e5631039ecf128480_107.png)

There's some intermediate based classes that we can use。

Kind of in from operation pass and do some boiler sorry。Do some boilerplate。There。

 and then we can sub class from them and take advantage of all the things that they've done。



![](img/175e489c9e191d7e5631039ecf128480_109.png)

But for now。We all we need to know is that we need to subclass from Pre paths and overwride a function called run on operation。

 that's all we need to do， that's how we create a path。



![](img/175e489c9e191d7e5631039ecf128480_111.png)

![](img/175e489c9e191d7e5631039ecf128480_112.png)

Before we have a look at the actual implementation， not implementation， how we can define a。

Pass in C++ there's a bunch of rules that a pass needs to follow。



![](img/175e489c9e191d7e5631039ecf128480_114.png)

I just mentioned two of them， but there's a complete list in the documentation if you have a look。



![](img/175e489c9e191d7e5631039ecf128480_116.png)

Basically， the reason behind these rules is that pass manager and MLIR in general when。

They tried Q run passes on the source code on the。A sorry， they use a multi threaded model。

 so in order to escape threat drive and kind of avoid any unnecessary issues in a multi threaded environment。

 we need to follow these rules， for example we don't have to we shouldn't。

 we must not have a global estate global mut estate for a pass。



![](img/175e489c9e191d7e5631039ecf128480_118.png)

![](img/175e489c9e191d7e5631039ecf128480_119.png)

Or we shouldn't really modify the state of another operation。

 which we are not working on as the current operation unless it's nested inside the current operation。



![](img/175e489c9e191d7e5631039ecf128480_121.png)

And some other rules have a look at the dogs to figure out more about these rules。



![](img/175e489c9e191d7e5631039ecf128480_123.png)

And finally， we have two type types of。Passes， one are operational specific and the other one is Operation agnostic。



![](img/175e489c9e191d7e5631039ecf128480_125.png)

![](img/175e489c9e191d7e5631039ecf128480_126.png)

If we take a look at how we can define a path。Sorry， how can we define？



![](img/175e489c9e191d7e5631039ecf128480_128.png)

Operation specific paths。 I actually， I took this example from the official documentation， so。

You can read more about it there。

![](img/175e489c9e191d7e5631039ecf128480_130.png)

But it's quite simple， there's a base class for， which is like a what's the term？C T S。

 I never get that acronym right， It's kind of。Interface like technique in C++ so this is just a base class we pass the concrete type to it。

 which is our in our case is my function pass and then here is the actual base class operation base and as the template argument we passed function operation to it so。



![](img/175e489c9e191d7e5631039ecf128480_132.png)

![](img/175e489c9e191d7e5631039ecf128480_133.png)

Our new pass， which is called my function pass only operates on function operations so when the pass manager is actually applying passes on the IR。

 whenever it reaches to a function operation， it will apply this pass on that operation and it only works on function operation。

 for example， if we get to I don't know like a constant operation。



![](img/175e489c9e191d7e5631039ecf128480_135.png)

![](img/175e489c9e191d7e5631039ecf128480_136.png)

This paths won't be applied to that one。

![](img/175e489c9e191d7e5631039ecf128480_138.png)

And as I mentioned earlier， we overwride the run on operation function number。

 we get the current operation which should be a function operation。

 and then since a function has like nested operations in them。

 we can walk down the graph walk down the tree and do some transformation there or even run another pipeline on the nested operations。



![](img/175e489c9e191d7e5631039ecf128480_140.png)

![](img/175e489c9e191d7e5631039ecf128480_141.png)

![](img/175e489c9e191d7e5631039ecf128480_142.png)

Sorry。

![](img/175e489c9e191d7e5631039ecf128480_144.png)

So finally we can register our path， it's not mandatory to do so。For example。

 right now in Ser compiler， I didn't register any of my passes because if you the whole purpose of pass registration is that when you register your pass。

 you can actually construct that pass via some like in a textual format like CLI right。

 you can actually have some noise CLI flags and arguments for your specific pass。

 you can construct it， you can ask your compiler to run this specific pass。



![](img/175e489c9e191d7e5631039ecf128480_146.png)

But since like inserting itself， since all the passes we have right now is dedicated to lowering the SLIR and other dialects to each other and to LLVMOR。

 they're kind of mandatory， we don't have to register them because it doesn't make sense。

 to enable and dislu them via CLI they're mandatory， they have to be there。



![](img/175e489c9e191d7e5631039ecf128480_148.png)

So that's why we that's why I didn't register them but。Here's an option。

You can register your pass actually， I'm going to talk about pass management at the end but。

We can group some passes together for specific purpose and register them that way so for example I can have a group of passes called O2 for optimization level2 right and then when when I register them with like a CLI argument then it would be kind of niceE I don't need to handle the CLI argument and parse them and things like that I just can use that flag which is like enable this pass manager O2 and run the pass manager with all the passes dedicated to optimization level2 on the IR that's another actually that's a common use case for registering the Pass and pass management pass managers。



![](img/175e489c9e191d7e5631039ecf128480_150.png)

![](img/175e489c9e191d7e5631039ecf128480_151.png)

![](img/175e489c9e191d7e5631039ecf128480_152.png)

And another type of path we have is Operation agnostic。



![](img/175e489c9e191d7e5631039ecf128480_154.png)

Meaning that it can run on any operation and the logic in this past is not operational specific。

The definition is quite the same as。My function pass or an operation specific pass。

 the only difference is that we don't pass any template argument。

 so we're not kind of specifying what operation to operate on。Again。

 we should overwrite the run on operation and when we ask for the current operation with get operation。

And instead of getting like a specific operation back， we get。A pointer to the operation class。

 and then we can do the transformation here， vice versa。



![](img/175e489c9e191d7e5631039ecf128480_156.png)

![](img/175e489c9e191d7e5631039ecf128480_157.png)

So creating passes are quite simple， but the tricky thing is how the transformation works in passes。

I'm not going to talk about them today because they deserve their own episode they can be quite complicated there's like different few different ways like pattern rewrite we can like match against a certain pattern and rewrite it to an like a specific rewrite it in a specific way and like basically different solutions we're going to have a look at one of them in the future episode。



![](img/175e489c9e191d7e5631039ecf128480_159.png)

Besidesside like。In the past infrastructure， beside passes， there are some other entities as well。

 like analysis and。

![](img/175e489c9e191d7e5631039ecf128480_161.png)

Passing instrumentation， if I'm not。Brong， I can't remember what that thing is called precisely but。

Basically analysis are just like passes but they don't transform anything。

 they're just the whole purpose of analysis is that like they collect metrics and data。

 about the OR and passes can actually reach out to them。

 query them and get their state from them to do their magic， right？



![](img/175e489c9e191d7e5631039ecf128480_163.png)

뭐。At usage stage we didn't use any of analysis in our lowering process and all that。

 but in the future we're going to use them and obviously talk about them in the video series and the passing instrumentation is like we can hook into the pass infrastructure。

 there's like some hooks when pass manager runs runs different passes on the IR level。

 it's like its more it works like web what it's called。



![](img/175e489c9e191d7e5631039ecf128480_165.png)

![](img/175e489c9e191d7e5631039ecf128480_166.png)

![](img/175e489c9e191d7e5631039ecf128480_167.png)

Middleverse， right， so there's different hooks like you。

Before running a pass after running a pass before like starting a pipeline after starting a pipeline on the entire IR we can use those hooks to run some code there I don't know print out some stuff actually MLIR itself provide some nice feature there there's a flag we can to the compiler and ask for like print out the result doc transformation after each pass like print the IR after each pass this kind of stuff which we're going to have a look in the next episode so there's plenty there I recommend you to have a look at the documentation and finally one of the most important topics we want like we need to talk about today is pass management so again I took this code from the official shell docs。



![](img/175e489c9e191d7e5631039ecf128480_169.png)

![](img/175e489c9e191d7e5631039ecf128480_170.png)

This is how we actually define a pass manager， obviously since it's from the dock。

 we need something like this here， right or？

![](img/175e489c9e191d7e5631039ecf128480_172.png)

You know what I mean？So here we're creating a pass manager by passing a context to。

 this context is in fact MLIR context。So。

![](img/175e489c9e191d7e5631039ecf128480_174.png)

PM here is actually a pass manager which is our root pass manager or which like beside this we can define it like this pass a context to it and then define what operation we want this pass manager to operate on so like in this example were asking the pass manager to operate on built in module like MLIR module they're kind of synonym to each other。



![](img/175e489c9e191d7e5631039ecf128480_176.png)

![](img/175e489c9e191d7e5631039ecf128480_177.png)

And then we add our passes with add pass member function right now we're adding a pass called module or pass my module pass we have to pass a unique pointer to our pass and heres here's the nice thing about pass manager we can actually nest pass manager inside each other so PM this PM here is our root pass manager right it's the top level one。



![](img/175e489c9e191d7e5631039ecf128480_179.png)

![](img/175e489c9e191d7e5631039ecf128480_180.png)

We create a new pass manager called NISed module PM， which is like an O specific pass manager， right？



![](img/175e489c9e191d7e5631039ecf128480_182.png)

Then。We want that new Pass manager to operate only on SPI RV always really hard to burn us。



![](img/175e489c9e191d7e5631039ecf128480_184.png)

In the like we want that new pass manager to work only on module O operations of this specific dialect in here right and we add some passes to that new。



![](img/175e489c9e191d7e5631039ecf128480_186.png)

Operation new pass manager， sorry， and then we can create another pass manager and nest it to the previous one that operates only on function operations with some passes right so we created like a tree of pass managers tree of pipeline that each operate on a like a specific level of the tree and do some stuff and leave the rest to other passes and finally。



![](img/175e489c9e191d7e5631039ecf128480_188.png)

![](img/175e489c9e191d7e5631039ecf128480_189.png)

![](img/175e489c9e191d7e5631039ecf128480_190.png)

We have we would end up with like a module when we generate our first level of IR。

 somehow like we're going to see a concrete example in the next episode。

 but I mean since module operation is the root operation for any MLIR dial。

 we end up our dialect and our IR must have a module。



![](img/175e489c9e191d7e5631039ecf128480_192.png)

![](img/175e489c9e191d7e5631039ecf128480_193.png)

We can then call the run member function on that module。So this way。

 our route pass manager will start applying the passes on the module itself and do the rers in place right。

 So after if this thing doesn't fail after this。

![](img/175e489c9e191d7e5631039ecf128480_195.png)

R like after invoking Ron here， our module will be a transform version of the previous one。

So that's how past management works in MLIR， we're going to see an example in the next episode。

I guess that's enough for past infrastructure and the stuff that we need to know before we can talk about lowering in the next episode。

Please， if you find find my work interesting， please leave a like and subscribe to my channel。

 if you have any questions please reach out to me and I'm looking I look forward to your feedback as well。

Have a great day， see you in the next episode。

![](img/175e489c9e191d7e5631039ecf128480_197.png)