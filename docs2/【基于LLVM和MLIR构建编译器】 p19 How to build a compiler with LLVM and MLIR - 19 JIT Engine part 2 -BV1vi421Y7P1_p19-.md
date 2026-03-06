# 【基于LLVM和MLIR构建编译器】 p19 How to build a compiler with LLVM and MLIR - 19 JIT Engine part 2 -BV1vi421Y7P1_p19-

Hey friends， welcome back to the channel。In today's episode ofHow to build a compiler with LLVM and MLR we're going to have the second part of the Jt engine in the part1 we discussed the Serins Jit engine and basically I showed you some of the implementations that I had for the Jitt engine and in today's episode we're going to wrap things up and kind of talking about the bigger picture and for and the future plan I'm going to show you some of the code that we escaped in the previous part so let's get things going by talking about the differences that Serin has with other programming languages。

First of all， Ser is a lisp and being a lisp means that its dynamic by nature。

 unlike other programming languages like sorry， unlike other compilers like I don't know like C plus plus compilers。

 rush compilers， go golan compilers Serene compiler is dynamic it should be dynamic so。For example。

 when you use a C compiler， let's say clG and you try to compile your project。

 what happens is the compiler actually reads your code like read all the source codes in your project and。

Pass it to a parer， parse it， compiles it to some sort of I and finally compiles it to native code。

 some target code。 sorry， and dump it into a binary file。

 We talked about this in very first episodes。Few first episodes， but in general。

A C compiler never runs your code right your code only runs at run time。

 so there's a like a clear distinction between compile time like the time that your compiler is active and compiles your code into a target code and run time which is the time that your compile code is running。

 right。But。Sene is different since it's a least。The compile。

 like we need to run code and compile time as well。I'm going to show you。Kind of how we do it。

 we want to do it， but that means we have to take care of our compilation time as well。

 we have to run a stuff in our compilation time so our like our compile time is kind of the same thing as the run time can be the same thing right。

So on its core， setting is just the jetit engine。We're going we're going to work on our Gi engine。

 make it better and add functionalities to it and run that Jit engine on compiled time to achieve the same thing as a static compiler will do for us。

And then。When we do that， it opens the door for other possibilities as well。

 so we can actually run the same jet engine engine only on run time and forget about the compile time。

That kinds like that the notion of running theit engine at compile time versus run time kind of。

Makes it harder to like to draw the borderline between like compile time and runtime in case of 3。

I drew a diagram and please excuse my。Lack of。

![](img/8dd58d52dae6fed43a2eb72a55874504_1.png)

What do you call it。Technical skills to create fancy diagrams。



![](img/8dd58d52dae6fed43a2eb72a55874504_3.png)

So。This is really hand wav and only the purpose of this diagram is to show you where the g engine sits。

 right？

![](img/8dd58d52dae6fed43a2eb72a55874504_5.png)

都。In terms of serene we have two kind of getways to our compiler。

 one is a CLI interface like Serin C， we pass parameters to it we ask we ask it to compile a name ofspace for us。

 for example we say yeah go go ahead and find the name ofspace food。t bar and compile it for me。

 right？

![](img/8dd58d52dae6fed43a2eb72a55874504_7.png)

And another another input， like another gateway that we have is the raple environment。



![](img/8dd58d52dae6fed43a2eb72a55874504_9.png)

Either beyond interactive mode or beyond like a network socket or something users can actually spin up a rapple and interact with the compiler with the language。

 not the compiler that way。 they inter forms into okay interactive rapple and。

Ask the language to actually evaluate the forms。

![](img/8dd58d52dae6fed43a2eb72a55874504_11.png)

So。First of all， let's talk about the CI interface。When when we try to。



![](img/8dd58d52dae6fed43a2eb72a55874504_13.png)

Use the CI interface to compile a name and space。 What happens is the the。

CLI interface or the CLI program actually will resolve the name and space name into a file。

 it's going to read the file and pass the content to our browserer via the read function and gets like a form of ASD and then it's going to pass thatD to the semantic analysis and run the analysis like a semantic analysis phase on it。

To generate some validate AsD。 So by this point， the validate AD contains a semantically correct AsD that represents the input program like the name and space。

 or in terms of in case of raple the input for。嗯。So as we saw in the previous part。

 like in part one of the J engine， our J engine had a function。

 like two functions actually add ASD and add NS， we can call either of those functions to add the valid ASD into our J engine。

You might remember when we call that any of those functions。

 what happens is like we used to we compile the ASD into LLVMIR indirectly like via SLI or。

 MLIR and LLVMIR and sorry。

![](img/8dd58d52dae6fed43a2eb72a55874504_15.png)

I can't use the mouse， I have to use the keyboard。Basically。When you。

In the previous episode we ended everything around here。

 we compiled everything into LLVMIR and we added that like we compiled the LLVMIR into native code as well and add that to the GLi j leap。

 but we ignored and we escaped over this part。Let's move back and start over from the Valley ASD。

Eventually when we add the notion of macros into serene。

 what happens like in this step is that we're going to look for macros in our ASD。

You don't know what a list micro is， basically it's a function that runs on compile time and it returns like valid list forms and we replace the like macro call with the return value which is like a valid list code and since it happens on compile time。

 that's like a neat way to extend your compiler it's really useful if you're a lister。

 you already love macros I'm pretty sure。But。We're going to go over the details in the future when we get to macros。

 but for now， just。A function that runs on compiled time and returns returns a list of valid。

List forms。So we try to find any macro calls in our valid ASD if there was any macro calls。

 we're going to look up the required symbols to compile。

 basically it should be already compiled any symbols that we want to look for in our Giitdi。

If you remember from the previous episode Giittalib is like and every name of space might have few Giit Giitilelibs attached to it。

 so we have to look over all the Gita lipss， find the symbols that we want if there wasn't there it means。

We have to kind of throw an error to the user， but we're going to find， if we want find the symbols。

 we're going to actually pass the symbols to。嗯。pas the symbols to like we're going to execute the symbols right execute the functions that assign to that symbol and since it's a macro we're going to get like a least form back basically and we're going to again parse that one and we're going to end up with a valid AST then this cycle is going to like loop we're going to loop over this cycle until there's no macro left in our valid ASD like this thing is like this loop is called macro expansion right we're going to expand the macros to the original like to the form that they evaluate to。

So when we take care of all the macros， then we're going to go through the same process as the previous episode。

 compile everything to LLVM IR and wrap any top level function into a new function and function called and finally compiles everything to a target code native code。

 and if like in this case since were running the Jit engine in compile time。

 we're going to execute a function called compile for example， let's name it compile or dump。

 which is going to dump it to a binary format。And like that binaryer file can be executable file。

 shared libraries， whatever。Or in case of a repulition。

 we're going to print the like execute the code， execute that form since we already wrapped it in a function called function and function call executing the code means call that function to like print out the print the result to the user and finally。

Since it's a raple， loop over and read more input forms and pass it to the parts that and semanttic on analysis。

So。This is how like I picture it and eventually in the future we're going to have a fancy G engine that takes care of everything for us。

 We run it on compile time to actually compile the code and generate binaries for us just like any other compiler and actually this thing opens so many like open the door to so many possibilities for us for example。

 we can actually run the same GT engine at runtime we won't have any compile time anymore so the runtime and compile time would be the same and that makes our G engine like to act like an interpreter right to act like an interpreter we can pass it some serene code and it's going to run the the code as it goes along like on the fly。

That's quite exciting， it makes it quite flexible， actually like another possibility the is to run multiple g genes alongside each other for different purposes。

嗯。In。In my head， it like。This single feature makes it like makes itene really exciting。

 it makes it really flexible， but at the same time it makes it more like makes the compiler itself more complicated than like a static language。

 because we have to take care of more details， especially when we're trying to compile this stuff。

That's why like in the past two months， I tried to wrap my head around some of the ideas that I have for the Jit engine to implement them in MLIR。

 but。I had a hard time doing it， but I'm going to get there eventually。

That that's that's the big picture， let's move on and I'm going to show you some of the code that we escape in a previous episode。

 but as a heads up， I'm going to show like the identical code from MLR's jet engine。

 not sirens because I had to disable some of the parts，You know， because of the wiring singing again。

 like we want a basic compiler wired up。So I can't like if I want to go with the Ser version。

 which is identical kind of to the MLLIRs version since I disabled some parts。

 it won't be useful to you folks， but if you check out the Gtupository afterward。

 you'll see that they're quite similar to each other。

So we have to move to the LLDM project directory MLlIR include MLlIR again， and execution engine。

 There's a header part called execution engine dot H。



![](img/8dd58d52dae6fed43a2eb72a55874504_17.png)

This is actually a J engine for MLR it reads MLR and executes the MLR code right any day like you password it it's really similar to the J engine that we have it wraps around LG as well it has a long object cache really similar right I chose to show you this because I actually use some of this code in our J engine I modified it to work with the name and spaces I add the addS and the ASD functions but like with。



![](img/8dd58d52dae6fed43a2eb72a55874504_19.png)

Some ser specific stuff or J gene is built around this version。So there's like two lookup functions。

 one is to look up a symbol normally and the other one is to look up the packed version of the the same symbol I'm going to show you the definition as well。

 there's a invoke packed function that I'm going to show you。

 but as you can see there's like a term packed here it's kind of。Common error。Around these functions。

So to get there， we need to go where some data structures。

 the first one is a data structure called argument that represents all the arguments that we pass to a function。

It has a member function called PA， which gets an like a vector of arguments that contains fake pointers and the value of type T。

And all it does， it just adds that the pointer of that tie to the list of arguments。

 the vector of arguments we pass to it， right since it's O since the。

A vector contains only opaque pointers。 that should be fine。Similarly。

 we have another structure called。Result that represent the result value sorry。

 the return value of the function that we're trying to invoke。

It has a like it holds a pointer to that to the return value as well。



![](img/8dd58d52dae6fed43a2eb72a55874504_21.png)

A result function， the retainer result type right this thing like we use this function to actually before I tell you how it works。

 I need to show you the invo function itself and specialization for the argument extract that gets the result type it just return the pointer to the value。

What you call it in value attribute of the result， right， and finally。

 the most important function invo。 So as I showed you in the diagram。

 whenever we add something to the。

![](img/8dd58d52dae6fed43a2eb72a55874504_23.png)

To the Jinging。We can use the invoke function to actually invoke the compiled code and。

Call the function， right。So here it takes a function name and a vector a collection of arguments。

But we have a like adopter name that's not important。

But we actually create a new array like we create a small vector。

 small vector is a type in LLVM which is faster supposed to be more efficient than city vectors。

 it contains opaque pointers and。We just pack all the function we call the pack member function on the argument extract and all the arcs that we got from here。

 we pass it to the a to the pack member function to create and create a vector of opaque pointers to those arguments。

 right？And we we call invoke packed function， we passed the adapter name。

 which is basically the function name， a modifiedified version of the function name and the new vector of our opaque pointers to all the。

All the arguments， right？嗯。Easy till now， nothing special。 Oh， by the way。

 since were talking about the invoking process， we assume that we already packed the functions right。

 I'm going to show you how do we pack the functions at the end for first。

 let's look at how we invoke how we can inke a packed function。



![](img/8dd58d52dae6fed43a2eb72a55874504_25.png)

So if we have a look at the packed version。Of invo， basically， we get the name as the first。

Argument and we get that vector of opaque pointers that points to the argument as the second argument of this function。

Then we use a lookup pack to look up the function name since we like the way we pack the function is to wrap it in another function。

 we give that another like that wrapper function a new name。

 I'm going to show you in a little bit and the lookup pack is just the lookup。

 but it's going to look up for that wrapper function， not the function that we wrapped。

If the function pointer wasn't there， like if there wasn't any symbol like that， return on an error。

 otherwise call that function pointer and return the data of the arguments the function pointer。

So and finally， return success because。If it returns that， if it writes in the error。

Doesn't matter because if we call the function normally as well it's going to throw some exceptions。

 so that's fine and it returns the return type in a different way。

 I'm going to show you how it's going to work in a bit。

 but basically that's how we run we invoke a function in our g engine。

The tricky part is how to how we can actually wrap the function， but invoking it is not that hard。

 The only thing that is remaining that I'm going to show you is actually。

Let let's have an example of how this invoke function works。

 let's say we have a function4 takes an argument， only one argument of type I 32 return on I 32 as a result。

 right？The way we can use the invoke function is to first。

We need a variable to distort the result value， right， we create。

 since we know it already returns on I 32， we create a。

We define a variable of type in 32 store0 in it， and then we invoke we use the invoke function to call that F function。

 we pass it the name as a string。The only argument， which is like 42。 and finally。

 we use the result function that we defined here， right to mark。

Kind of to mark the where do we want to store the result of that function called？

So function call sorry， so we have we defined a function sorry a variable result here。

 and that's where we want to store the return value。 that's how we market as。Like。

 that's how we tell in work to store the result。 What it how like， basically。

 when we pack the function， we're going to create an array of。

Pointers to all the arguments and the final element would be a pointer to the return type if it's not void right so the final argument is going to be a pointer to a variable that we want to store the return value in it。

So that's how we use in Voocboard let's have a look at how do we actually pack your stuff。Good to do。

 so。Yes。So， I may。还没什。So here's how we actually pack stuff。

Pass it like we have a function called pack function arguments and we pass an pass LV module to that function。

First of all， if you don't like this might sound like looks a little bit intimidating to you but don't worry about it if you don't understand some of the concepts in this function it's totally fine it's all about like LLVMIR and how it works in the near future in like few2 tri episodes in the future we're going to talk about MLIR LLVM like you're going to get them eventually but for now the main purpose is for you to know how do we actually wrap the function the details we're going to like I'm going to show you in the future or you can study in your own time。

So we get the LLVM context started in the CTEs， we create a the builder object basically is just an object that creates the LVMIR for us。

 and then we create a set like dense set， it's just a LVM type similar to a set that holds pointers to the function type。

 like LLVM function type， and we name it interface function。

Whenever we process a function we're going to insert it in this function to keep track of what function did we already process and then we're going to go through iterate over all the functions in the module that we want to actually pack so for each function it's either a declaration。

 it means that it's just a signature like the definition lies somewhere else and we're not like we don't care。

For those functions， we don't want to pack them because they're external to our measure。

 they might be already packed， we don't know。嗯。And finally， if you already process the function。

 let's just skip over that one answer。

![](img/8dd58d52dae6fed43a2eb72a55874504_27.png)

And here's where the magic happens。 We create a new function type， right， we call it new type。

 It's it's a function type that returns actually one。 Yes， that's true。 It returns。Vd returns void。

 It doesn't return anything。 And the only argument that it has is a。Pointer， I have to use the mouse。

 It's a pointer to a pointer of type I 8 a byte， right， So basically this thing in here。

So a pointer to a pointer of type I8 or a pointer to an array of type I8 pointers， right？嗯。And， oh。

 yeah。 And whenever we like you。If the function name is F。

 since we're going to wrap it in we're going to name the Raper function ML or under life。

 basically we changed the name to avoid any collisions。So we have a new function type。

 we pack the name， the way we pack the name is super easy。

 we just add ML or stringing as a prefix to the name。And then we add that function to our module。

 we didn't add the body yet， but we just add the function name and the type to our module and then we create the function itself like the body of the function we create the function first we inserted into the set that we have we had already just to keep track and finally。

Down to the body。First we create the basic block， the entry block。

 we add the basic block to the function that we just created。

Then we asked the bill there to start inserting the instructions into our building block sorry。

Rightrry。Basic block and finally like don't worry if you don't notice understand this。

 we're going to get there like talk about it in the future， like near future。

 but what happens is we create a small vector of type pointer to values we name it as this eight here is basically with a small vectors you can say preallocate like this number like this many slots in my vector right which is8 here and then we go like we iterate over all the function argument。

 we create a pointer to that argument and use that pointer like the way I described earlier like we're going to create an array of pointers for arguments and the very last one is going to be the return time and this is how we actually create the return type we get the。

We create the call to the function this is where where actually we call the function right right now we created the function tab like the function signature。

 we created the basic blockss， we took care of all the arguments and at the end we create like a function call to the original function like that's how we wrap things like wrap a function right we get the result if the result type wasn't void if it's void we don't care right but if it wasn't void and the function actually returns the type returns the value。

 we create we go the go over similar process as our arguments and we create a new pointer for that return type as the final argument to this function so we look at like we take the final argument if it was like a。

It should be a pointer， be just a store value in that pointer。Right。

 we restore the value in the pointer， but you probably don't know what is a store。

 what's load gap or other stuff。 Again， I'm going to show you in the near future。

 But in order to understand that， we need to know some of the basics about compilers like。Cf Gs。

 basically some data flow graphs and stuff like that。 like compile there stuff， right， it's it。

 it would be better to go through them first and then talk about a littleium OR like。

It would be much easier to understand all this， but for now you got the bigger picture of how to like why do we wrap the functions and how do we do it And finally。

 since our wrapper function is not going to return anything we create a return。

And that's how we actually。Rap functions。 But why do we do it。

 The first thing is we need to wrap all the top level forms in serene because， you know， you can。

 in at least， you can just in。In the file， you can just start to write some list like this。

 for example， right？Nothing prevents you from doing that。 like， you know， it's very similar to L。

Dynamic language like Python， you can just start writing in a file and pass it to the interpreter。

 We should be able to compile all this， so we're going to wrap any top level， this has a return type。

 it's an expression right we wrap it in a function we call it we get the return type of this same and that would be the return time for this for that's one reason the other reason is because we want to like when we want to use the invoke function。

 it would be easier for us to have a uniform signature for all the functions right and use everything in the same like call everything in the same bay rather than trying to guess like what the return type actually we have to guess the look up the return type of everything plot。

It would be on us to do it。 not on the jeting jet。 That's one of the other reasons that we do it， so。

That's it for today and basically for our discussion about。

Giting at this point I guess like we're done with the wiring with the compiler wiring that it took us like 19 episode to get there。

 we have all this like important components of a compiler in place with the minimal set of features they connect to each other they work more or less and we have we have a better insight into different。



![](img/8dd58d52dae6fed43a2eb72a55874504_29.png)

Subys now it would be a good time to start working on like details of each section。

 make every sub like make different subsystems the way we want。

 but again I think like the better design would be to move like to expand our compile little by little we can't spend a lot of time in just one subsystem。

 make it perfect and move the another one。 we have to kind of work on all of them at the same time with that in mind in the next episode like next two maybe episode。

 I'm going to talk about table gen which is not related like is which is not the next step in our。

Process， but in our like。Journey to create a compiler。

 but that's something that would be really helpful we're going to create the error messages that we want using tableGin and after that we're going to go through some of the basics of compilers that I mentioned like CFGs。

 data flows like different type of optimizations and things like that and finally get to build the SLIR make SLIR better。

 use MLLR and LLVM together and move toward our goal， which is working sharing compiler。嗯。Thank you。

It's episode number 19 it's amazing that I couldn't believe that I can make 19 episodes on compilers and it's all time to you folks if you like what I do please consider to subscribe to my channel and leave a log it's going to help me a lot with my work and hope to see you in other episodes as well。

Thank you。

![](img/8dd58d52dae6fed43a2eb72a55874504_31.png)