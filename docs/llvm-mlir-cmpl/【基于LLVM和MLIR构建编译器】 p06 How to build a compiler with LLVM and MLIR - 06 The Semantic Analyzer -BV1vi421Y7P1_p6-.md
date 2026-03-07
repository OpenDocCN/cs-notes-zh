# 【基于LLVM和MLIR构建编译器】 p06 How to build a compiler with LLVM and MLIR - 06 The Semantic Analyzer -BV1vi421Y7P1_p6-

Hello everyone and welcome back to the Cha in today's episode of How to build the compiler with LLVM and MLOR。

We're going to talk about the semantic analyzer。Before we start。

 I received a couple of questions regarding to the previous episode that I need to answer。

So let's just start by them and then move to the main topic。

The first question I got was why didn't we implement a linked list。

 so if you remember from the previous episode。The implementation that we have for a list contains a vector。

 like it's a wrapper around the CD vector。So。Since we're going to since our goal is to actually create a really simple compiler to begin with and build on top of that。

 we at this stage we really don't have to create like a actual linked list。

So I chose to use just a wrapper around the vector type。But if like。

The right answer is in the near future， we have to kind of make a link list。

 but not a linked list in C++ so we have plug。When we this， when we get to the type system， I， I did。

 I it didn't。Decide on the type system details and like。Anything around that yet， I'm still。

In a study phase。 But when we get to that phase to actually implement the。Type system。

We need to create a。Proper list type。 that list type has to be in in the MLIR type。

 So it would be different。 It would be different than a link list in C plus plus。 But for now。

 since the AD has to represent the。synyntactic structure of our source code。

And not the semantic structure。 you know what I mean right。

 we really don't care about the implementation of the list。

 It can be anything as long as it has some。Collection attributes。But in the near future。

 we definitely have to implement a list。The second question I got was。

 why are we using the STD vector instead of LLVM collections？嗯。

If you read the programming manual of LLVM， the LLVM provides like many different alternative types to the well known STD type。

 like four vectors， LLVM has a small vector， dense vector or some other types of even like a string vector if I'm not mistaken。

 and different alternative for a string types， for maps for popular data structures， right？嗯。

The reason LLVM provide their own implementation is that。

They're basically they they want to have a data structure that suits their needs。

 in most cases the alternative data structures are faster and more efficient。

 so they highly recommend everyone to use them。And。Frankly， we have to do it as well。

 we've done it in some places， but in the near future when we get to the phase that we start to refactoror the code。

 we have to replace the vectors with like a proper alternative。

But for now since I try to avoid any confusion， any point of confusion in the source code。

 I decided to seate the vector type or other wellknow types that everyone who uses C++ might know about and there's tons of information about this standard libraries around。

 but for the LLVM stuff you have to dig into the source code and read some pieces in the LLVM programming programmers manual。

I think it's easier and simpler to understand for now。

 but in the future we obviously were going to move away from vectors and use the alternative types。

Okay。呃。Now it's time to actually talk about the。Main topic of today， which is the semantic analyzer。

So in the previous episodes， we have talked about the reader and the ASD officer in today's episode。

We're going to move to the next phase， which is the semantic analysis。Again， as usual。

 I expect you to know about the semantic analysis and the different concepts around it。In the。

In both of the compilers books that I。Introduce to you in previous episodes。

There's plenty of information about automatic analysis， but just in case just do。呃。

Be true to our kind of tradition of going through a very basic overview of the topic。

 let's talk about what is the semantic analysis。So。

We have talked about the ASD and how it represents the syntactic form of the source code。But。

We never talked about what if the syntax， what if we have a code that the syntax is sound。

 but semantically it's meaningless， right？So the semantic analysis job is to make sure that our program is semantically correct。

For example。In a list。As you can see in the good example that I I。Wrote here。

Having a list like this is total like syn it is syntactically correct。

 so the first element is number four and the second element is a of symbol called main。

So there's nothing wrong with it syntactically， but semantically it doesn't make sense or to call a function called。

f。How do you call a function sorry， how do you call a number？

That's like catching these type of semantic errors is the job for the semantic analyzer。

Traditionally。The type checker and other types of checks that you might need to do。

On your source code comes in the same like applies in the same phase， right？So。

To wrap it up basically the semantic analysis phase is a phase that we look into the source code。

 look into the ASD that we have and try to make sense of it。

 we want to check whether it according to our language specification， does it make sense。

 is it correct， is like is it going to work basically？So in the in the。

Theiagram that you see on the screen basically the ASD will look like this。

 we have a list with two elements， the first element is a number and the second one is a symbol。

The ASD itself is kind of correct， there's nothing wrong with it， right？

This is actually the correct representation of the source code that we have in here。

 so the reader has nothing to complain about and the ASD is fine。

 but it doesn't make sense according to the least specification， right？

Traditionally in semantic analysis phase。

![](img/a4f2cba96bb70490c3b21f4895f7607b_1.png)

It's。Different compilers actually look for like semantic errors and try to make sure that the ASD is well formed and the semantic of the language is fine。

 right？But in our compiler in Ser compiler， we have some other steps in them。Semantic analysis phase。

 which is the rewrites。So。If you remember up until now， we have only few ASD nodes。

 like list symbols and numbers and nothing else， right from the previous episode。

But let's have a look at the same exact example that we had from the previous episode。

With define a function， we call it main basically to be more precise。

 we create an anonymous function， then we bind the symbol main to that function so it's kind of like defining a function called main。

 and then we call a function called PRN。And may at the same time。

To print the output of the main function， right？

![](img/a4f2cba96bb70490c3b21f4895f7607b_3.png)

Okay， I made a mistake here， but。

![](img/a4f2cba96bb70490c3b21f4895f7607b_5.png)

It's fine out for now。So， in the。Diagram is that my care study is on right now。

You can see the ASD that represent the syntax， we talked about it in the previous episode。

 it's just the syntactic representation of the source code above。But。

When we run the same ASD through the semantic analysis， semantic analysis， sorry， we're going to get。



![](img/a4f2cba96bb70490c3b21f4895f7607b_7.png)

The blue diagram， right？What happens this。We。Workalk through the AS TG node by node and then try to。

Find a specific patterns， right， for example， at least with a symbol depth。As the first argument。

As the first element sorry， is a pattern。It means we want to define a new binding in our program right so when we hit when we see such a pattern we rewrite that pattern to use a different node instead of the list node right so this list node in here。



![](img/a4f2cba96bb70490c3b21f4895f7607b_9.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_10.png)

Will be rewritten into a deaf node I'm going to show you the de node and other types of ASD nodes that we have for the semantic analysis phase we have like three more and de is one of them so we remove the entire three entire node。

 sorry with with its children and replace place it with the deaf。Note。

 the depth itself contains a symbol to the。Obviously the name of the binding and a value which in this case is an anonymous function。

 right， it might be a difference， it might be not be like a function， it might be a number， whatever。

 right？By the way， when we reach to this when the semanttic analyzer。

Reached this point basically to this list in here， it looks for another pattern right this list matches another pattern and that pattern is of anonymous function when at least it starts with a symbol called fN we're trying to define a function right so it rewrites this tree。



![](img/a4f2cba96bb70490c3b21f4895f7607b_12.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_13.png)

And replace it with a note called FN that I didn't put the extra details in here。

 but for now it's fine。

![](img/a4f2cba96bb70490c3b21f4895f7607b_15.png)

And obviously on the second line， which is represented by the tree on the right。

We have a list that starts with a symbol a periodn as the first element and another list。

 which is a function called on main。

![](img/a4f2cba96bb70490c3b21f4895f7607b_17.png)

I made a mistake in this diagram， so I'm going to just fix it in。Is it live？Actually， if I do this。

 then the this diagram on the right would not be correct。

 but whatever like it's a temporary fix yeah。😊，And I'm going to explain what's wrong here。So。

The tree on the right is the。Is a smaller tree with a new note。On top as the root。

 which is called coal。Funny。The call node itself represents a function call。

 a call site or a function call， right？What happens in here is that we looked for a pattern。

 which is the most common pattern for a list。We like basically anything any expression in list evaluates to something right numbers evaluate to themselves strings the same symbols evaluate to the value there that the name is 0。

20。2 and lists evaluate to a function call right so the。In a least， when you see a list like this。

 basically the first element has to be a function。And that this implementation is going to find that function and call that function by passing the rest of the list as the elements as the arguments to that function。

So it's a common pattern as soon as we see such such a pattern。

 we rewrite that tree with a call node， so basically this new node is。

kindind of represents a function call and I'm going to show you the node again。

 but it has a target right now it has like a what we are trying to call。

The first element is a symbol。So we have to do something about that symbol。

What happens is we look into the scope that we are in and we try to resolve the symbol PRN to a value and that value has to be a function or has to be a col entity right and a list of argument so the mistake I made in this diagram is that。

Previously。It was like this right so we had two functions called function calls。

 but I just created one function call here， so the right diagram for for this syntax in here would be a call function in here and instead of this list it would be another call that would be calling the main function right？

But I may maybe I'm going to fix that in the future， I don't know， but for now。

 you can see that how the semantic analyzer will rewrite the common patterns to use different node types。



![](img/a4f2cba96bb70490c3b21f4895f7607b_19.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_20.png)

Why why are we doing this。The to put it simply is that later on。

 when we want to generate the SLIR based on the ASD， it's easier to actually。

Map the different node types to different SLIR operations rather than trying to be ca and find the patterns there。

Besides that。

![](img/a4f2cba96bb70490c3b21f4895f7607b_22.png)

In this phase， we should actually check for the types to match and run the type checker here as well。



![](img/a4f2cba96bb70490c3b21f4895f7607b_24.png)

By doing that， we need more information on the node types and what we're doing here let us to like give us more insight into the tree and into the syntax basically。

It makes our life much easier to run the type checks and stuff like that on the ASD。Um， okay。

Let me show you how the semantic analyzer works and how you can actually interact。Oops。



![](img/a4f2cba96bb70490c3b21f4895f7607b_26.png)

Interact with it with the compiler itself。So。As you can see， I already compiled the source code。

And I already ran this one as well。I added some stuff to the compiler after the previous episode but we're going to talk about them in the future。

 they're not important at the moment like the build directory and stuff like that but for now we haven't emit action called semantic if you remember for the ASD stuff we had the ASD action that basically prints out the raw ASD and now there's another action called semantic there's a bunch of actions which we didn't talk about。

About most of them， but for now， AST and semantic are all unique need。So。

What happens in here is that we pass a new the source file， helloor。srN。

 we ask the compiler to print out the ASD after the semantic analyzer phase。

This dash O is just the output that doesn't apply to semantic action and finally。

Build directory is obvious where do you want me to build the source code。

 again it doesn't apply to the semantic action。So here you see the raw ASD and here is the ASD after semantic analysis phase。

As you can see， oh， by the way， let me show you the source code as well。Was it in thes now？嗯。

This is a source code we're trying to work on like quite simple and dumb， right？As you can see here。

We have a list with a symbol depth as the first element， that's a pattern。

Symbol main as the second one， which is the binding。

 the name of the binding and another list that represent a。

Function sorry anonymous must function as the third element。 So there's two patterns in here。

 One is for a function and the second one is for a binding Oh， by the way。

 I said F n first and the F second right so the rules is when we walk a tree we always start from。

The inner node right so we get to the leaf of the tree and then we find our way back to the root。

 that's why FN would be first all the time。So as you can see， when we rewrite the entire tree。

 the result would be a deaf note that we're going to talk about shortly。From Maine。

To another node that that node is itself is a FN node， a new type of node that I'm going to show you。

 So we rewrote the entire list here。To a de node。 And similarly， we have another de here that。

Its kind of。Let' represent the second line。So。As you can see we have ASD rewrite in place now the ASD is much simpler and kind of obvious in instead of bunch of nested lists we have two deaf notes。

 two notes， that's it， it makes reasoning about the ASD much easier and simpler。



![](img/a4f2cba96bb70490c3b21f4895f7607b_28.png)

Okay。Let's go back to。Again， it's time to talk about thecode itself。To begin it。

 I need to show you the code like the entry point of the semantic analyzer。

So in the include directory。There and in the reader package。

 so semantic analyzer is part of this reader name and space。



![](img/a4f2cba96bb70490c3b21f4895f7607b_30.png)

It might change in the future， but for now it's fine。Okay， as you can see。

 the entry point is quite simple。We have a type that it's like it。What do you call it？TypeD， right。

 we have a typey DF， which is called Ana result。It's just an for a result type that the success cases is an ASD and the failure case is a vector of error pointers。

 right？We talked about the result type quite a lot in previous episodes if you don't know how it works。

Check out the previous episode， right？So the main entry point is a function called analyze。

It takes two arguments， the first one is a reference to a setting context that I'm going to talk about it in the next episode。

And the second argument is a tree is an ASD tree， right？What it returns is the analyze result。

 that type of that we just talked about， right， let's look at the implementation。

The implementation itself is quite simple。Don't。Like don't be bothered by the todo like we have tons of todos in the source code。

 if you're interested you can actually fix them and patch send some patches to me。

 by the waym right now I'm working on the just in time compiler so this to do actually you can't actually fix this to do here because the JIT is not ready yet。

 but maybe in the future。So what happens in the？Semantic analyzer is that we walked the tree node by node and then。

As you can see here basically we walked the tree node by node。

 if you remember from the previous episode the AST data structure itself is analyzed for a vector of nodes so AST here is actually a vector right so when we say like in this for loop basically each element would be a root of a tree right？

Oops。So we worked at3 node by node and we called the analyze function on the root node。Right。So。

Again， from the previous episode。We know that each L H expression。

Each type of expression has to have a analyze function， it's part of the expression interface。

So by calling it。We might get a note back。That maybe node。

 as you can see on the top right of my screen， that maybe node is a type for a result that the success case is a node and the failure case is a vector of error pointers。

 right？So。Here's the rules for our semantic analyzer。A disclaimer， I have to have a disclaimer here。

The design that I have here is not perfect it's actually。Kind of， I don't know what to say like。

Unpleasant， because we use null pointers。And I don't like it， but again。

 since we want to have our minimal version of the compiler already as soon as possible。

 let's go with it， we might replace it in the future with like a more sophisticated version and avoid using null pointers。

 but for now it's fine。That was the disclaimer， right？

So when we get back a maybe node that maybe node has three estates， its either is a success case。

 so a maybe node being the success case of a maybe node means，The return value has node in it， right？

So we get the value by getting the value we get backend node。

 so again if you remember node is a shared pointer to a expression type and that expression can be a symbol。

 can be a least， can be anything， anything that implements the expression interface。

If you don't remember about the expression and how its interface works。Sorry。

If you don't remember about the expression， check out the previous episode on the ASD。If the， if the。

So if then note that we got back。Wasn't a null pointer since the node itself is a shared pointer it can be a null pointer as well。

 so if there was a node we just push it back to ASD so we defined like a empty ASD here and by doing this we put the node the new node that we got into the new ASD that we're going to return it later。

But if the return value， if the node that we expect， we got back from the maybe node。

Was actually a null pointer， it implies that we don't want to rewrite， right。Basically the。

this if that we have here， the success branch。Is a rewrite and the failure branch is not a rewrite。

 it means that okay， we don't want to rewrite this note， put it back its grant。But。

If they maybe node that actually didn't contain any success value and it contained a failure value。

 right， failure case， it means that there was some semantic errors in the ASD。

 so what happens is we get the error we put it in the error stack and move on。At this point。

 we don't have like a。Proper implementation of like error like error system and error handling at the moment。

 that's the next thing I'm going to do after the just done compiler。

 we have some pieces in place like we have some trade and error implementation。

 some a way to actually mark errors and differentiate them。

 but I need to be more precise and provide more utilities around errors。But for now， it's fine。So。

 to kind of。Go over the whole。I'll grade them one more time。

We call the analyze function on each expression on each node of the。A S C。

If it return a success case and that success case contained a node。

 it means that we want to actually rewrite the current node with the new node that we got from the analyze function。

 so we put it in the ASD。And by doing this， basically were replacing the current element。

 but if it was a success case with a null pointer， it means that we don't want to rewrite and the current element is good enough。

 so we just put the current element of the current AST3 into the resolved not resolved sorry into the new ASD3 that we want to return。

And if the maybe be node， if the return value of the analyze function contained the failure case。

 it means that there was a semantic error， we need to get there or put it back into the error stack and move on。

And finally， we checked the error stack if it was empty， there is no error。

 so return a success case and return the new generated ASD， right？Biscuits。And。If it wasn't empty。

 we have some errors， retain a failure case with the error stack。It's really simple。

 the only tricky part is that null pointer here and to make it better in the future。

We need to actually replace the the。null pointer probably with a new type of expression。

 I didn't think of it yet， but using a null pointer is kind of icky to me。

If you're interested in this， please feel free to work on it， fix it and send me a patch。

 I would be really glad。Moving on。So from the previous episode， we talked about the expression。

 where is it？Yeah。We， we have talked about the expression class， which is the。Kind of the。

Interface for every expression and ASD nodes that we have in string。



![](img/a4f2cba96bb70490c3b21f4895f7607b_32.png)

As you can see， all the expressions has to implement the analyze function， we talked about it。



![](img/a4f2cba96bb70490c3b21f4895f7607b_34.png)

In the previous episode， we talked about symbol number and list。 Let's look at the。S， oops， sorry。

Let's look at the。

![](img/a4f2cba96bb70490c3b21f4895f7607b_36.png)

Mingbo。You see， how did we actually implemented there？Ana like function。As you can see。

 we just returned a success case with the null pointer。

So that means based on the rule that we saw just earlier， that means we never rewrite a symbol。

A symbol is when we want to analyze that it doesn't get rewrite。

 it doesn't get rewritten into anything else。

![](img/a4f2cba96bb70490c3b21f4895f7607b_38.png)

The same thing applies to。あ what does it。Numbers。In case of have a number， again。

 a number node would。Would be itself， you don't rewrite it to anything else。

But that's not the case for the list。Okay， it's a bit long as well。

What we're going to do in case of list。First of all， we。Make sure that the list is not empty。

If the list is not empty。Get the first element。Since the you know elements itself is like a attribute of the least class。

 it's a vector， so wereing we are getting the first element and since it's a share pointer。

 we want to have access to the value itself， not the pointer。

So first would be a pointer to that value， and then we check the type。

So here we are actually looking for the patterns。If the type of the first element was。

If the first sorry if the type of the first element is a symbol。

We try to dynamically cast it to a symbol we talked about the LLVM dynamic cast in the previous episode and how it works。

 I hope you had a look at the LLVMs programmer manual to read more about dynamic casting and how LLVM does it。

But basically what happens here is that。If。The variable first is actually symbol。

 The same pointer would be a pointer。To a symbol， otherwise， if it's not a symbol。

 it's going to be null。 So we check for it， whether if it's null or not， if it's not null。

 then we check the name。So if the name of the first element was de， so we have a pattern， right。

 we call de。We call the make aesthetic function on the deaf class， we're going to look at it soon。

If it was FN， we do the same， but this time for the FN class。

 the F and FN both are new like an expression type。



![](img/a4f2cba96bb70490c3b21f4895f7607b_40.png)

I didn't mention them in the previous episode because they belong here。

 but basically they're the same as least symbol number and other expression types there's just another node in our AST tree but they have this make aesthetic static function that makes it easier to。

Create a new function， new， sorry， new instance of that type of node。So here is another to do。

I didn't mention it here， but probably I have it in the data。org file。

We need to make sure that we have this like we have an interface for this behavior。

 either this or create a new function， like the make function from earlier in the expression fog to have a unified interface to create this type of nodes。

But right now， it's a bit。Pin of a sparse， I don't like it， but for now it's okay again。

Feel free to fix it and send me a patch。And finally， if。It was Neil。If it wasn't a symbol。

Which we already tested it， it should be a symbol， but anyway。If the first element。Wasn't a symbol。

 Were going to create a new， sorry。My bat， I'm getting out of my head。

If we couldn't find any pattern。But the first element was is still a symbol。

 what we're going to do is to create a new node call like a new call node。

Basically the first element is not a special form， special form is the concept of this。

 look it up in like Google it。So FN and the F both are special forms。

 so if we couldn't find a pattern。And the first element wasn't a special form。

 it must be a function call， so we create the function call node here by using the call expression。

And return it and if the finally， if the list was empty， just return an empty node。

 what is an empty node。

![](img/a4f2cba96bb70490c3b21f4895f7607b_42.png)

Empty node is just maybe node success node。 So basically what we can do in。Here。

 instead of having this， we can， oops， sorry。Keyboard macros doesn't work sometimestime。



![](img/a4f2cba96bb70490c3b21f4895f7607b_44.png)

We can do。Empty。No， right。It would be exactly the same。

I hate it when I increase the font size and the warnings， interrupt my work。And also。

 the same applies to what was the other one。Eimbo， yeah。So we can go oops， sop， sop， sop， ss。

Can go here and say empty。Me two。Doneone， right， so they're the same theyre equivalent of each other。

So。Now we know how do we actually find the patterns for a list？

Let's have a look at the Dave deaf expression。As you can see。

 its a depth itself is an another expression， so it implements the expression interface or to be precise。

 it inherits from the expression abstract class。It has a binding。

That is the name of the binding we're going to create or。To put it better。

The binding itself is the name of the binding we represent and the value。Is just a node。

 so it can be any type of node it doesn't have to be a function。

 but it can be anything right as long as it's an expression， it's fine for us。It has。L job。

 normal constructor， nothing special here， the only thing you need to know we talked about the location range that's fine and heres the new maybe a new concept I can't remember that we talked about a string ref maybe in the previous episode I don't know well it's just a reference type from the LLVM one of those alternative types that is better for us to use so weve used I used it here and finally a reference to a node that we want to represent in our binding。

The risk is just the same as before we talked about Git type onto a stringing。

 we're going to take a look at the analyze right now and the generate IR。

 we're going to talk about it in the future class of。

 again it's for the dynamic casting and aesthetically casting of the LLVM， we talked about it。



![](img/a4f2cba96bb70490c3b21f4895f7607b_46.png)

And here's that make aesthetic function that I was talking about earlier。So basically。

 we just use this make function in any expression that we have only in the semantic analysis phase。

But。It's fine for it's fine， but we can make it better。

If someone else comes in today and want to create a new expression type。

 since it's not part of the interface that new person might not know about。

Creating this make function， so it's easy to miss at the same time it's optional。

But it's better to have like a structure and kind of a rule for this type of stuff。Okay。So。

Let's move to the implementation of de。 Where is it。



![](img/a4f2cba96bb70490c3b21f4895f7607b_48.png)

Okay， as you can see the。The expression type itself is a de， obviously。

 to a string is kind of simple。It says a deaf note from。The binding to the value。

 so we call the to a string of the value here as well。But for the analyze phase。

 that is the topic of the day， as you can see again， we return an empty note here， let me。Actually。

 fix， not fixed it。 it was correct。 Just make it more。P size empty note。Okay。

So when we reach a deaf node in our ASD while were looping through the elements of the ASD。

 we don't do anything with it， we don't want to rewrite a deaf node。Obviously。

 get the result if we get the ASD from the reader， we shouldn't really run into a deaf node because reader doesn't understand the semantic of the language。

 so it's unlikely to happen， but since we want to satisfy the interface of expressions。

 we have to have analyzed function and it has to return an empty node。You know the rest。

 the most important part here is this make function。What is the ser context， we talk about it in the。

Next episode part。The second argument is a list， so if we go back to the list implementation。

 as you can see。When we call the make function， we pass it the context and a pointer to the current list。

 this is a pointer to the object right so it would be a pointer to the list。

What happens in here when we want to create this def and we need to create it but create an actual def note right so we need to run some checks。

 the first check here is to make sure that the number of arguments is not three。Actually。

 we need to change this here。This should be something like。呃。Oops。Something like this。

It driveris me crazy when it jumps， but you know， I need to increase the font size anyway。Okay， so。

A death in a list works like this， and it should be a least with death。

Name of the binding and value right in the future in the future。

 we might have a doer string here as well， but for now we don't so we don't want to。Check for that。

 So it， it should always have。Qi。Elements， the list has to have three elements oh。

 you know what I was right in the first place。😊，So it has it should have。

Three elements if the number of elements wasn't three isn't three。

 return a failure case with a nice message。The message is like。

We expect three three arguments for DF special form， but like you provided this many。And we create a。

Notode an error full node we talked about make errorful in the previous episode。

Basically what it does is to point to the location of the error and。

We have a new error called the Fron number Ar， I'm going to talk about the errors as well in the next episode。

 but basically it's just a class of a subtype of errors right with a message that we provided to it。

So if the number of arguments to de wasn' in three。

 we are going to return an error and if you remember from the root analyze function。

 returning an error full value result in failing the analysis phase and we're going to put this error error stack and return it to whatever that is calling the analyze function to handle。

But if we had exactly three elements， we're going to get the first element dynamically cast to a symbol。

 obviously this depth symbol has to be a if it's a symbol it's going to be a pointer to a symbol。

 otherwise it's going to be null so weoo so we checked the de here。

I let me just write the to do here really quick。They place this song。Yeah。Untimetime check。Okay。

So we make sure that de is not null and the name is deaf， right？

But I don't want to use A because it's going to go away in a release。Build。

 so we need to replace it with a run time check to make sure that this never happens。

Because like who knows we might call this make function from some other places。

 so we have to make sure that it doesn't happen and as it would be on the debug mode。

 like it's a debug mode only so it won't check the entire thing in release mode。Okay。

 when we made sure that deaf S is actually a symbol and the name is deaf。

 then we have to look for the binding， so the binding is the second element we get the pointer。

 try to dynamic off God。tryry to dynamically cast it to a symbol and if it was a symbol。

 if it wasn't a symbol， return a new error， new type of error which is called def expect symbol and the message is empty because it's obvious like this error type already has a message inside of it we don't need a like extra message so we're going to fail the semantic analysis phase with this error type。

 oh， by the way if you remember from earlier。Even if we return an error。

 it doesn't mean we're going to stop the loop we're going to walk the entire tree and find all all the error messages。

 but obviously some of the error messages like an an error message like this if we fail to create a de it means like they're not going to be a binding that we expect so later on when in some other places when we want to use that binding for example in a function called since the binding is not there then we're going to generate another error so it would be like a。

Butterfly effect， when we fail the semantic analysis here。

 then it causes some other issues down the line。 but the plan is to actually。

Connect these error types together so stack them on top of each other so you can see from like when you see the first error。

 you can understand what caused that error。 There's another error and you can。

Visually iterate through the errors to get to the very first error that caused the whole arm mag in your program。



![](img/a4f2cba96bb70490c3b21f4895f7607b_50.png)

So if the binding was actually a symbol， then we try to get the value。

Here we call the analyze function on the value itself， so we want the value to be analyzed as well。

 right？When we do this。The value that we get like the value here is actually a maybe value。

 as you can see it's a maybe node so it might。The same rule of semantic analysis works here as well。

And then we do kind of the same thing again， I don't like this logic in here because if we change the semantic analysis。



![](img/a4f2cba96bb70490c3b21f4895f7607b_52.png)

Logic in the future， for example， the one with the null pointer。Then we have to remember that。 Okay。

 we have the same logic somewhere else。 So we need to fix， fix it as well。

 So the better thing to do here。

![](img/a4f2cba96bb70490c3b21f4895f7607b_54.png)

Sorry， is to。Re factor this logic。😔，Into a January。All right。

 so the better thing to do here is to actually provide generic function that gives us the same kind of behavior and use it here so when we want to change the behavior。

 we just change it in one place and it reflects on the entire source code。



![](img/a4f2cba96bb70490c3b21f4895f7607b_56.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_57.png)

But anyway， so if the value， when we analyze the second element， which is the value。

 if it was a success case and it has a new node， it means that we need to rewrite the value。

 so we set the analyze value to the new node， otherwise we set it to the current element current second element。

 obviously if it was an null pointer we don't want to rewrite right， otherwise we return the error。



![](img/a4f2cba96bb70490c3b21f4895f7607b_59.png)

And finally， here's a bit of it's a crazy thing to do， but I'm going to describe。Like my。

Not a chain of thoughts， but exactly about this piece。都。We check for the type of the second element。

 the one after。The semantic analysis。So we semantically analyzed the second element。

 which is the value if it was a function。Then we cast it to the function type。Again。

 it if it was a nail， you know， this thing， as you can see it shouldn't， it should never happens。

 but in order to keep the L happy we have like I had to put it here a littleV un reachable。

 it's just an like a。Function that write the exception if。

We ever reached to this point which we shouldn't really， so to make the L happy。

 I had to include this。Condition in here。So。When we cast the second element。

 the value into a pointer of function， then I set the name。

 so the function expression has a member function called set name and we pass the bindinging name to it。

The reason I'm doing this， if you look into other type of list like closure， for example， there's a。

Function called I don't remember whether it's it's a function or a macro。

 but there's a there's something called F n， which you can actually in in I'm talking about closure right now。

 you can actually create a function like this， right， so it it would create a new binding。

To a function with the name that's。Use a better name。诶。NPC， right。Oh， by the way。

 if you see me typing really weird， I'm using a new keyboard layout called Hemock or something like that。

That is。Awesome， it's perfect and I'm not used to it that much yet so I make so many mistakes。

 check it out， it's really good I'm going to put a link to it in the description。Anyway。

So in closure， we have a macro like this， right？In order to do this in serene， first of all。

 we need to。Of something like this， right， ABC。Yeah， F and and blah， blah， blah， blah， right。

But when we。Translate this syntax into an ASD。This function here doesn't know about ABC at all。

 so if something bad happens in this function and we want to fail somehow shown like a stack trace or whatever。

 this function itself doesn't know about ABC， what should we do？

That's one of the things that we do in the semanttic analyzer right when we make sure that this function is fine semantically correct and we we detect the depth pattern then we just as you can see here set the name of this anonymousan function that I'm going like the next thing that we're going to talk is the function node you get to see the set name as well。

 so it might look it might looks a little bit strange， but here's the reason。Okay。And finally。

 a good part。We're not going to talk about the context here and。

Like nameless spaces or semantic environment， blah， blah。

 blah now I'm going to talk about it in the next episode， but。Basically what we're doing in this。

In this。Line here， we create a new binding in our currentoscope， that's it。

 that's all you need to know， we create a new binding in our currentoscope。

 the currentosco of the current name and space， what is the name and space。

 what is the scope wait for the next episode。And finally， if we successfully created that binding。

 we return a successful node called De with the location of the list。

The list being the current list that de is in like is the first element。

 so it makes sense to use the same location with the binding name， come on。

With the bun name name and the analyzer value， Otherwise， there should be an error。

 we shouldn't get here。 so to make the。Linter happy we use a little on reachable here， okay。

Moving on， I guess it's a long episode。Second， no， sorry。The next one is。Oops and H。

Again fN dot H is like quite simple， it has a name a list of arguments and an ASD of body right so body itself is a vector of expressions arguments or a list we have a to do here that says in itself using a list use a collection here。

 we don't have a collection yet， we're going to have a collection in the future that is going to be。

Family of types right so list would be a collection vector would be a collection map would be a collection so we should be able to use any of that instead of list here and。

They would have different meanings， especially math。Moving on。The rest is quite simple。

 like the stuff that we had for death and other expression。

There's another member function called setname that we saw earlier。

 we get on a string and set the name to that string。Going to the implement。 Oh， sorry， it's wrong。

Wrong project。um。嗯，Yeses。Okay， so I'm not going to talk about the obvious stuff you can read about them yourself。

 they're quite similar to the other expression that we talked about。But the make function。

Is really important to us。Here's the to do right now our functions doesn't support D strings。

 but in the future we want to support D strings so when we introduce D strings into our function we need to expect more elements。

 not just three。So。We check for the number of arguments， a function needs at least two arguments。

 the name of the function and the list of arguments， sorry。If the number of arguments is sorry。

 less than two， then return a new error type， so fail live semantic analysis again with that error。

Otherwise。Let's。Like create， let's get the first。

![](img/a4f2cba96bb70490c3b21f4895f7607b_61.png)

Eleement dynamically cast to a symbol， so FN seam has to be a symbol and if it wasn't a symbol。

 it will be nail， sorry no and same thing here again we need to replace this check with that runtime check。

Heres the to do and then cast the。Arguments， sorry。

The reason that it happens is that I have one of those fancy mechanical keyboards and I have some macro on some specific keys when I sometimes when I move really fast。

The macro can't catch up。That happens。Anyway。So we get the second argument。

 second element of the list。 again， this list here is the input list to the make function。

 and it comes from。Here， though it would be a pointer to the current list that FN is the first element of it。



![](img/a4f2cba96bb70490c3b21f4895f7607b_63.png)

So we get the second element that。The second element has to be a list of arguments， right？If。

 if there wasn't a list of argument， we return an error full case， a failure case， sorry。

 with the new type of error that says FNRs must be at least I'm going to talk about the different types of error in the next episode and。

Up until here it was fine， from here it gets a little bit different。

 so we define a new ASD which is an empty vector， an empty ASD。Then if we had a third or more。

 we had more than two elements， it means that we have a body。We create a new body。

If you remember body was just a vector of node right， so since it's the vector。

 we can create a vector out of another vector like this。It means， okay。

 create a vector from this third element and tilt the end of the current vector。And name it body。

 right and put it in the body variable。Then we call the analyze function on that body。

So if you can see that we call the actual analyze function。

 the entry point to the analysis phase to the semantic analysis phase right since the body itself is just another ASD so we can use the same function here。

 nothing prevents us from doing that。We need to the same we need to do the same thing in the。

Daf expression where I put that new to do， right？So。We get back and maybe ASD if there wasn't an ASD。

 so there's some type of errors， just create a new failure case， return the error types。H。

 you know what？We can actually。 it's redundant here。 can just say。Maybe a see。

Because they're the same， they should be the same type， right？Oh no， no， no， no， no， sorry， my。

My bad make actually has to return a node， but semantic analysis returns a maybe ASD So what we're doing here is to get the error from maybe ASD and then return it as a node here。

The error here might be like it's a stack of error， it might be one， two， three， whatever。

And if if there may be ASD。Has the had a success case， then we get the value and put it in the body。

 So the new value of body when we get to here is actually。

A new ASD that is semantically correct and we ran the semantic analyzer on it， so it should be fine。

 so finally by this point we have the location， we have the arcs and we have a semantically correct body so we can create actually a new function node。

And return it done。That was the function。Not， and finally， let's。诶。

Talk about the final piece of the puzzle。Cool。

![](img/a4f2cba96bb70490c3b21f4895f7607b_65.png)

So at this point， when we talk about the no， no， no， let's talk about the coal first。So。Again。

 call is another expression， it has a target node and a list of an ASD of pro。

The target node can be any expression right， so the target node can be number。

 the target node can be symbol， can be function， can be deaf， whatever。先至进录。AndThe poems。Sorry。😔。

That is a。That is an AST。Is a vector of notes， right。We could have write。Soorrry。

We could have write like which tour of no like basically。Be literal and say vector of notes here。

 but obviously AS is just smaller and。Easier to understand。Again， the constructor is not a big deal。

 nothing special just initializes the object， same set of function member functions as the other expressions。

So let's move to the actual implementation that is important to us。



![](img/a4f2cba96bb70490c3b21f4895f7607b_67.png)

Again， I'm not going to talk about the obvious stuff yet tied to a string and things like that。

But in the analyze phase， like the other。Experions like FN and other stuff。

 we just return empty node because we don't want to rewrite the call node and again。

 when we get ASD from the reader， it shouldn't contain any call node so basically it doesn't happen。

 it shouldn't happen it just for making the interface happy。But啲啊。Make aesthetic function。

It comes from here， so in case that we couldn't find any special form pattern。

 we suppose that it's a called， it's a function call， so we create a column。



![](img/a4f2cba96bb70490c3b21f4895f7607b_69.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_70.png)

So。First of all， we don't again， we need to replace the az with a like run time check。

 but what happens in here is that。Calling an empty like empty list。Doesn't make sense here。

 how do you want to call an empty list with no target。

 so it doesn't make sense we just have to make sure that we have one at least one element in our list that is the function function it might not have an it might be like a function with no argument。

 but empty list doesn't make sense here。と。That's what we're doing here。

 we get the first element run the analyzing it and get the value after semantic analysis did his job。

Why we do why do we want to analyze the first argument that's because we。

So we have different types of function calls， right， The simplest one is like this。

 We call the function， H and T。That's it。 No argument， right。Another type is something like this。

 We call anonymous function。 We define an anonymous function。

 and then we call it with some arguments， right， So since the。

FN node itself returns an anonymous function to that we cant call it in place immediately that's another type or we have some other types like I don't know if we do a de。

Deaf should return the binding， so when when we define a binding。When we define a binding。

 basically what happens is。The return value of this step has to be the binding。

 the binding refers to a function， so we should be able to call it， right。

Since we have different types of function calls， we want to analyze the first argument to make sure that like we know what's going on。

If the return value wasn't there， if it was like a full case， failure case， we just returned。F value。

 simple。But if it was a success case， then we get the value。If the value was null， sorry。

 we don't need to rewrite， so we put it back， it should be the first element。

It happens when the first element is a symbol or a number， right。

 so we don't rewrite it we just put it back。But as you can see。

 we didn't weput it back by setting the first value， the first variable to that element。

We have to do some other stuff。So we create a target node， raw parameters。

 and then we check for the number of elements we have。

 so do we have arguments for this function code or not？If you remember from previous episode。

 from is basically like。Create a new。List for me from the first first sorry element of this list till the end。

 so the raw parameters will be every element beside the first spot first， you know？

And then we look for the type of that first element if it was a symbol。Pasy P。

 it should be we should look it up in the scope and then call create a function call for that so we dynamically cast it to a symbol if it wasn't a symbol。

 just fail， make the link happy。Otherwise， again， I'm not going to talk about the。

Name aspace stuff here， what we're doing here is to look into the current scope to find that binding。

 to find the function with that name with the name inside the same variable。If it there。

 if it wasn't there， sorry， we return a new error message thing that we can't resolve the symbol bh。

Blah being like the name of the symbol we're trying to resolve right so what happens here is basically we there's no such pointing in our scope anywhere。

 so there must be a mistake and we return that  error。Otherwise， if we found that binding。

 we get the value， put it in a target node。But if the type of the first element was is de or call or function。

 we just use the same thing as the target node because the rule the same rule applies to all three right so in case of de de has to return a new binding so if the new binding would be our target。

The call itself means that。We want to run want to call the return value of a function call。

 so that call itself would be the target and same goes for Fn for a function tag。Otherwise。

 if it wasn't any of those， we just failed the semantic analysis thing that like stating that we don't know how to call。

The first element。 So if the first element was is a。

Stringing or we don't have a string yet is a number， for example， we don't know how to call a number。

 so we fail here。And， finally。We analyze the。Any possible。

Parameterters that we might have if we don't have any parameter， basically。

 it would be fine again because we don't have anything to loop over so。Everything would be good。

 we won't have any error if we had any error in our arguments， fail a semantic analyzer。

 otherwise create a new note。Readit the name call。The given location of the。Leist itself。

 the target node and finally the value of。The arguments。

So here is all the things you need to know about these new expression types that we didn't talk about in the previous episode。

In the next episode， we are going to talk about the context， the serene context， name of spaces。

 scopes， things like that that we escaped over in this episode。I guess it was like a long episode。

 I don't know how long it is but。嗯。After this episode and probably the next one。

We're going to enter the MLOR realm though。Some of the stuff that we talked about in this episodeod is around the semantic analysis。

They had different node types。They're useful to us。

 they make our life much easier to create a new dialect of MLIR。

 we're going to see about that in the future， but the whole purpose of semantic analysis besides checking for the the semantic correctness of program is to actually be ready and get ready for mapping our nodes into MLIRs basically the SLIRs ser intermediate representation。

To map the。No types to operations in our SLIR， we're going to see about that in future episodes。

That's it for today folks， thank you for sticking around it was a long episode hope to you in the future episode as well。

 have a great day and see you in the next episode。

![](img/a4f2cba96bb70490c3b21f4895f7607b_72.png)