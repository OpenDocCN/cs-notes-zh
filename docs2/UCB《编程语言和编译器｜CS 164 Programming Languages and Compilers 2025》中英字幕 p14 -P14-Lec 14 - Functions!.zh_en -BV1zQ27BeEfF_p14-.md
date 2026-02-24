# UCB《编程语言和编译器｜CS 164 Programming Languages and Compilers 2025》中英字幕 p14 -P14-Lec 14 - Functions!.zh_en -BV1zQ27BeEfF_p14-

![](img/a3ef23f31cb4997ad70de84abccf370b_0.png)

![](img/a3ef23f31cb4997ad70de84abccf370b_1.png)

Alright， hello， everybody。 Obviously， it is always an exciting day in compilers and interpreters land。

 but it isn't especially exciting for us today， because today。

 we get one of our all time favorite language constructs。 At least in the interpreter。

 we're still gonna have to wait for a little while for the compiler。

 But it's gonna be a big one today。 So I want to dive in real quick with just some drill review。😊。

There were a couple of things that came up。One was there was that program that I had y'all predict what would happen in compiler versus interpreter。

 and I think we were always taking the true branch of a conditional and down the false branch。

 there was a construct that we didn't actually have star star and we had a little bit of confusion。

 So I just want to real quick over that， this is connected to that sort of what's happening compile time versus what's happening at runtime broader question。

 And so basically the main confusion that came up was some folks were looking at that program and thinking that okay。

 this is actually going to not be okay in the interpreter。 Actually。

 this is gonna be totally fine in the interpreter right because we're never going even go down and expect that path that had the construct that doesn't exist。

But also， some people were thinking， okay， this is going to be totally fine in the compiler。

 not totally fine And the compiler。 The compiler is thinking， oof。

 I've got to go through and generate code for all of this， right。

 regardless of whether we're ever actually going run it。

 It's trying to figure out what kind of assembly should I produce for the star star thing。

So that was the big thing that was happening there with that example。

What other compile time versus runtime things， Oh， okay。

 compile time error versus runtime error Forly in this class。

 we have a very simple model for ourselves of what is happening。 compile time versus runtime， right。

 because basically we can think about the fact that there are actually two different languages that are running those things。

 right， we have this compiled Ml file， sort of loaded up so we can all look at it， right。

 We have this Ocal file that we have written， that is our compiler compiled M， right。

 And when we are actually running that， that program， that Ocal program， that is compile time。

 So if Ocal is the thing that is doing stuff。😊，We know that's something that's happening in compile time。

 On the other hand， if we have emitted assembly and the assembly， once it runs。

 is the thing that is doing something， right， raising error or whatever it may be。

 that is going to be runtime。Right， because at compile time。

 we go ahead and we actually om the assembly At run time。

 we actually run the assembly we have omitted。So that's our nice distinction that we've got for ourselves。

Questions about that。Okay， a quick sort of review reflection question in that general area。

 I want you to think about where does our symbol table live at runtime for a compiler？

We already know that our interpreter has a symbol table available。

 it's using it as we're doing interpretation when we have our compiler and it's using the symbol table。

 where does it live at runtime， go ahead and discuss with folks nearby。All right。

 So here's the simpler version of that review question。

 Does the symbol table exist at runtime for the compiler， Hu， if you think it exists at runtime。H。

 if you think it does not。Yeah， I totally agree right so we are using the symbol table right here inside our Ocal program。

 strong hint to ourselves。 Okay， that's compile time right And by the time we are actually running the generated assembly any information we needed out of that symbol table has been baked right into those instructions So we no longer have just something that is sitting there and representing the symbol table by the time we are actually running that assembly It's all gotten baked into the instructions。

Questions on that before I cover one more thing that came up in the free response for the drill。Okay。

 cool。 So the one other big thing that was coming up was this idea about how is the compiler and the runtime Like how are these talking together。

 How are we able to use these C functions that we keep making。

 right we're making this thing inside this C program and somehow we're managing to use it from inside our generated assembly。

 How is that happening。 Well， the main answer is we have actually told our assembly that it is allowed to rely on the fact that these things are going to exist。

 right we said， okay， this print value thing that's going to be available to you。

 I promise it's going be available to you。 And then if you recall what we do inside compile and run。

 the thing that we're doing is okay， we go ahead and generate our machine code。

 but we also use Gcc's linker， not anything else about Gcc， just the linker in order to tell it， hey。

 go ahead and pair these two things together so that they can talk to each other。

 If you're feeling confused about what's going on in there。

 This is something we talked about on the very first session in lecture and we also talked a little bit about it last week。

So please do feel free to go back through those if you have questions about it or feel free to ask questions right now。

Okay， cool in that case。嗯。There's one other thing I want to mention， brief logistics note。

 The midterm is coming up。 I want to say a date， but I also don't want to say a date without looking at the schedule。

 I think it's October 28。 look at the official class schedule to be sure sure there's a B course's announcement about extra support。

 I'm not really going dive into it in much detail right now because we're going to talk about it in a lot more detail next week。

 but I just wanted to make sure that's on everyone's sort of mental agenda that that is going to be coming up。

Questions or we're feeling good。 We're excited to think about functions。Alright。

 let's start thinking about functions。 By the end of this very day。

 we will be able to use our interpreter to run the functions you see before you。

 This is very exciting。 But before we actually dive in on making that happen。

 I want to get you to actually take a look at these programs。

 And I want you to see if there are any patterns to the particular ways that we are using functions here。

 the particular ways that we've sort of laid things out。

 are there any sort of commonalities that are gonna make things easier for us that are going to make things hard for us。

 I just want you to see if there are any patterns here。😊。

Go ahead and discuss with folks nearby for a minute。All right， what are we noticing？

It doesnn't have to line up with how I've highlighted stuff。 I'm just curious what y'all are。

I think our first time is seeing。神病逼的。Different size。I love this。 So this is so exciting， right。

 previously， when we had names and we were going to go ahead and make those names available。

 we had the parentheses clearly explicitly guiding us about where we were gonna have that name available。

 And now， suddenly， we've got these definitions。 And we're just going refer to those sort of wherever。

 I love that observation。 What else we got。😊，I' like to define function can it explicitly。

Like there's no dueday。I love it。 Okay， so this is saying。

 I think what this is saying is we've got this one body that's appearing within each of these。

 So if we take a look， we can see that， okay， this seems to be， well， actually。

 I' there highlighted these arguments。 We've got the body inside this， We've got the body here。

 the body here。 We're sort of noticing that there's gonna be one expression。 right。

 We're not having some special thing that's saying， oh， yeah， here stands the body。

 We're just going right in， diving right in on the expression that is going to actually give us our return value。

 Is that what we're thinking about。😊，What度？拒人。If it was a less statement， you would stop back。

Like there's no due。Oh， great。 Okay。 So this is saying， hey， suddenly。

 we don't have just one thing in the program as a whole， right， So previously。

 we really only had programs that looked kind of like maybe just that or just that。

 We sort of had the one expression that represented the program and in its entirety。

 And now we're getting definition。 and then definition。 And then this body that appears at the end。

 Absolutely great observation。😊，What else have we got？Okay， cool。 I'm gonna， I'm gonna， oh， please。

Andド base。Oh， I'm not sure I've understood that one。 Can you give me that one again？

It's like defined and that is。Okay， we'll keep thinking on that one。

 So here are the things that I'm going try to draw our attention to。

 and we'll see if they make sense to us。 So first back to what you observed multiple expressions。

 right， we've got these definitions， and then we've got the body that appearss at the end。

 I love this。 We're also getting， you know， this was maybe a little too basic to even mention。

 We're getting function calls。 right？ And so some of these are appearing in the places where maybe we would expect。

 right So we're going and seeing that， but we're also getting function calls within the function themselves within the bodies of the function。

 So we can see we've got a function call there。 We've got a function call here。

 And so this is actually a call to the same function that we are currently defining。

 which means we have recursive functions。 In fact， we can see that we also have mutually recursive functions。

 because odd is calling odd even is calling even right。

 So we've got these function calls indicating to us that we are going to have recursion。

Another thing that I'm noticing you can see sort of this yellow zone versus this pink zone。

 we are putting our definitions first we've sort of divided out these programs into a couple of sections and in fact。

 there's something even deeper there which is that all of our functions so far are appearing at the top level right we don't have a way for them to be nested inside something else。

This's a little bit weird right if we think about the programs y'all have been writing in Ocaml。

 youre constantly writing these functions that are actually nested inside other things。

 right You're in the midst of doing something else。

 and then you make a little function that you're passing into map。

 You're using it as a value right We are not able to do that yet here， right。

 We can see that these functions。 we are never going ahead and using one of these functions as say an argument to another function using it sort of in the way that we would use our firstclass functions in Ocamel。

 We are eventually going to implement that。 But for today。

 we're going to have this slightly simplified version where okay。

 we're going to make these functions at the top level。

 we are not going to use them as values and we are going to just sort of have them sitting there at these tople definitions lists。

Do we have questions about。Those constraints yet， or that feels like an okay starting point。Co。

All right。Well， let's go ahead and see now we'll do sort of our standard thing that we do。

 which is we go into interpreter。Ml and we see if we can make this happen。So。

Couple of things that we're going to want to change。 So up until now。If we take a look inside inp。

 we've just had this thing where we said parse program right and the program was just the one expression right it was just going to be one S expression that comes out of parse program so that then when we got over here。

 we would just have one S expression going in all of a sudden now we've got definitions and then this one expression。

So I think we're going to want to do something a little bit differently。

 I'm going to take us over to U， where we have made ourselves some utilities。

 The main one that I'm going to draw our attention to is we have this new type。

It's not anything particularly surprising， probably。

 but this is going to represent the information we need about each of the definitions that we're writing down in our programs。

 And so okay， we seem to have this name， that seems to be a string。 We have some arguments。

 that seems to be just a list of strings。 That's maybe a little bit weird。

 We're maybe used to thinking about the fact that arguments are actually mapping from a name to a list of values。

 but of course， when we're just looking at the definition。 No。

 we're just hearing the names of those parameters。 And then we've got the body。

 which is the one S expression associated with actually executing the function。

 So we can go ahead and highlight that if we look at one of these。

 I don't think it's going to be surprising what these are。 So we've got our little keyword defined。

 that's not appearing inside our definition type， but then we have。Our name。hi is a string。

We have our arguments。List of string。And then， we have the body。She's an S expression。

So flash good on our new type that we've made available。Lovely。

And then we're going to have some little helper functions that are going to help us out a little bit。

 So this one is basically just a way to actually go ahead and take in these S expression lists and grab out the definitions of body。

 make us some things that have this type if we pass in the appropriate S expressions to it。

 pretty boring， but pretty useful for us。😊，And then we're also going to keep track of a list of definitions that we'll have available。

 so we will occasionally want to figure out if a particular definition is， in fact。

 in that list of definitions， and we will also occasionally want to sort of get the definition associated with a particular name。

Nothing too wild in there， but I want to make sure that we all know those are available。Okay， cool。

So now that we know about that， we're ready to change how we call inter X because now we're going to want to go ahead and call this not on the program as a whole。

 but instead just on the body。 So let's go ahead and make that change first。

So we'll use our new helper function。Parse many is just going to let us get multiple S expressions out instead of only one S expression out。

Let's go ahead and pipe that into deinens。And body in。

 And then we're gonna want to actually use those。 So I'm clear on where we want to use the body。

 right， So let's go ahead And instead of calling parse program here。

 Let's go ahead and interpret X on the body。 That feels good。😊。

This defens thing is a little more confusing。 So here's our first decision that we have to make。

 We do have a way previously of sort of keeping track of things that we know we have available。

 We've previously done these things of using the symbol table in order to keep track of the names that we have bound a particular values。

 So my question for you to discuss for 30 seconds， Should we add all these names associated with these function definitions。

 Should we add those into our environment into our symbol table。😊，Discuss。What do we think。Hum。

 if you think， let's add these to the symbol table。Hum if you think let's not。Yeah， I totally agree。

 right， Like previously， we've been adding these let bound names into our symbol table。

 It's important that we be able to use those as values。 right， for example。

 we might want to pass one of those as an argument into one of our function calls。

 But we have just talked about the fact that at least so far。

 even though eventually we're gonna to implement this。 at least so far。

 we cannot just treat these new functions as values。

 So we don't just want to add them into the symbol table。 So instead。

 we're going play our usual trick that we play for making something available to inter X。

 We're going add a new argument into Interbs。 So let's go ahead and everywhere we call inter X。😊。

Let's also pass in the definitions。Oh， can you not see？

What if we want the output from running a function to be something that we put in the symbol table？

Is there anything that would constrain us from doing that， right？

 So what we'll get out the other end of actually evaluating a function is going to be a value。

 We do have a symbol table that maps names to values。

 Is there anything that would hold us back from that。Yeah， I agree， that's going to be totally fine。

 we can absolutely use names to refer to what we get back from calling a function。有局在。

Could we do that in the same line， Like， could we inside when we have our sort of let expression and we say let N be and then the call。

 Yeah， no problem。 Yeah， absolutely。Okay， cool。 So we have strung through definitions。

 What is this definitions thing going be， Well， it's just going to be a list。Of our definition type。

 not too surprising， probably。 So now it is time for us to make。An interesting design decision。

 But as we will see in another few moments， we're about to make an even bigger one。

 So this one's going to feel like a big deal， but not compared to what we will do after。

 But one of the choices that we're about to make is where in these match cases。

 we put the match for a call。😊，RightWe could go ahead。

 think about the situation where our programmer writing a program in our language makes a function and they give it the name plus sign。

If we go ahead and we put our match case right here。Suddenly。

 this might be a little bit different than if we go ahead and we put our match case down here。

 So go ahead and discuss with folks nearby。 where would we like to put our match case。ですね。All right。

 who thinks let's put it here where I've put my little cursor hum for this spot？Hum for。This spot。

Okay， we're not feeling a lot of commitment to one or the others。

 And that totally makes sense because there isn't actually a wrong answer here。 Like。

 where're the language designers。 We get to decide what should happen。

 Should the programmer be allowed to overwrite Plus， I think that's more interesting。

 I'm gonna put it up here。 This sounds good to me。 Let's do it。I know all of our work。

 all of a sudden in the program are come in and induced shenanigans， but hey。

 they can do shenanigans， it's okay。We've got to go ahead and say， okay。

 we might see the symbol F and it's going to take some arguments in， okay。😊。

So we're going to want to go ahead and do some kind of filtering to make sure that the programmers are doing too many shenanigans。

 So what are some things that we could check already right now。

 I think there are at least two things that we could already check to figure out if this is a reasonable function call。

So go ahead and discuss with folks nearby， what are two things we could check right here to see if the programmer is doing a function call that makes any sense。

还有一个。All right， what kind of ideas do we have， What might be able to check right here。Yeah。I love it。

 right， We know the list of definitions that's available， right。

 There's a fixed set of definitions They appeared at the start of the program。

 Let's check if it's in there。 That sounds great。 So let's go ahead and say， is this F thing。

 Does that actually correspond to a real one。 So when is defin。😊，D's F。 And remember。

 that's just one of our little helper functions is Dafin， which is just checking if it's in there。

Okay。That feels good。 What else might we be able to check right now？I love it。

 We have passed in a particular number of arguments。 Here we are。 We're at the cost site。

 We know the particular arguments that have been passed in。

 and we know how many arguments our functions allow。

 So let's go ahead and check if those actually mass。 So if list at length。Args， right。

 so that's the ones that we're actually using here when we're doing the call。

 if that matches list do length。Deend dot orgs。 So that's taking a look at this definition that we have stored for associated with this name F。

 How many arguments is it expecting to get。Then， okay， so then something， not totally sure what yet。

 But definitely， if that doesn't match， then we're going to want to go ahead and raise that expression on X。

 So okay， we're starting to get close。What would we like to do in the middle here。

 I think I have a pretty good idea of a starting point that I might like。 So one is。

 I am pretty sure we're going to want to call interbacks on the body。

RightThat's sort of what we expect。 We're getting to the point where we are now ready to do a function call。

 What does it mean to do the function call Well， it would involve actually running the body。

 So let's start setting that up Inter X。We're going to have to make some decisions right about here。

 right， So we're going have to decide what is going to be in our definitions list that we provide。

 We're going to have to decide what is going to be in our environment that we provide。

 And then we're going to want to go ahead and actually call it on defin dot body。So okay。

 we're getting really close， but we obviously have to actually make the decisions about these two blanks that I've left in here。

 So the first blank that I want you to make the decision about is this one right what sorry。

 this first one， What is it that we should provide as our definitions list that should be available inside the body of the function。

 discuss for 40 seconds。So like， I want like like maybe I want something。で。find。ァシです。

I guess if I just named it by the name and I had two different hat。And one was like very。

Then like don't I need to not call them by just the name that you have？

The number right store the milk is a pair。I think I understand the question。

 So the way we are storing it right now， we are expecting that functions have unique names。

We could easily just change how we store that list of definitions so that we have something like name and type signature right like we could go ahead and sort of retrieve these names in some other way that would be totally fine the way we have it implemented right now we can't do them。

All right， what do we think， what would we like to make available as our list of definitions inside the function body？

We have ideas。I'm hearing some whisperings of same。Does that feel good， everyone thinks that yep。

 keep the same definitions list， hum for ya。Home for something else。Yeah。

 I agree right so like the whole thing that we've been talking about so far is we've got just this fixed list of definitions。

 we're allowed to use all of them inside the body of all the functions totally fine to just pass that in unchanged so let's go ahead and pass that in unchanged and now we get to something a little bit harder。

😊，Right， so now we're thinking about。That symbol table， that environment。

 What do we want to make available inside the body of the function。 And to help us think about this。

 I'm going to show us。A nice little program。I want you to decide with folks nearby。

 what would you like to have happen when we run this program？All right。

 who would like to see this error out？Hum for that。Humphrey， you would like to get back six。Okay。

 a little bit of interest in both overall。 I'd say we've got some more interest in error。 Yeah。

 I agree。 So probably。😊，Almost every language that you have ever interacted with would error out on this。

😡，Right， so if we think about what's happening here， if we look around at。What's sort of in the。

 the space of the program here， right like。If we look around， do we have a definition of x？

That is actually surrounding this space in just the source code， right？ We have this text file。

 If we look at this text file， are we seeing a definition for X there， No， On the other hand。

 if we think about what has been happening on the call stack， right。

 What has been happening in execution so far， have we seen a definition for X，Well， in fact。

 there we have。 it's in this other part of the program。 And in。

 there could be all kinds of other stuff in between here。

 there could be a bunch of stuff in between here。 This could be like hundreds of lines down。okay。

 most of the languages that you have ever interacted with， for some of you。

 probably all of the languages you've ever interacted with， this would error out。

 So now that we've thought about this program。I want us to take a moment to think again about what we want to put inside this blank。

 and then I'll tell you about the decision that we're actually making here。Go ahead and discuss。

 decide what you want to have going in there。All right。

 So who thinks we should start with the environment in which we are actually exuding the call and then extend it with our arguments。

 hum， if you think that。Hum， if you think we should make a brand new environment that will just go here。

 and all it will have is the arguments for the function。 hum for that。Yeah， I agree。 right。

 So if we actually want to enforce that this behaves like the other programming languages we know。

Then the thing that we are going to do here is make sure that the only names that the function body has access to。

 because remember， our functions are actually defined at the top level right now。

 there's no way to actually have some kind of let valueing on the outside and then put the function inside。

 again， eventually we'll get to that。 But for now， the only names that these functions should be aware of are the names that are actually provided in their arguments。

 So let's put that together and then we'll talk a little bit about why this is so。 So first。

 let's go ahead and figure out。 what are the values of the the arguments that were provided。

 So let's do vows equals list map。Intert X。Duffins。

 and now we have to figure out what environment do we use to actually get the value of the arguments。

 What environment should we use there for getting the value of the arguments。

Think about it for 10 seconds。I'll leave that blank。Go ahead and discuss。Of list， not list stuff。

Okay， so what is the environment that we should use as we are figuring out the values associated with those arguments？

Anyone want to shout it out？I'm hearing same thing。 Yeah。

 so we want to go ahead and use the environment in which these arguments have been provided， right。

 we're going along。 we see this function call about to happen。

 what are the names that are available here， Well it's going to be whatever the names are that have sort of surrounded the function call。

 So let's go ahead and use the environment that we already had access to there。

 But now we are making this brand new environment and the only thing inside this brand new environment。

 Fn right function N the only thing inside it is the mapping between the argument names that we see in the definition and the values associated with actually evaluating as right so ags is what we see right here。

 And so we're just making the mapping between those turning that into a brand new symbol table and now we can use that right here。

Okay， so the decision that we just made is the decision between lexical scope and dynamic scope。

Maybe you have heard about dynamic scope and all of the many problems that it can cause。

 So originally way back during the history of interpreters in compilers land。

 a lot of folks thought that dynamic scope might actually be the thing that programmers expect And so it's not surprising that some of you were looking at this program and saying maybe I would like this to produce6 right Like I'm thinking about a particular trace and in this particular trace I have。

 in fact mapped X to 2。 And so when I get here， why shouldn't I expect that it's going to be two。

 And so very， very early on in the process of implementing languages。

 people were thinking to themselves maybe dynamic scope is the way。

 turns out this is incredibly hard for programmers to reason about just unbelievably hard for programmers to reason about And this kind of makes sense because maybe some of the time we are calling F from right here but maybe we have another call you know 300 lines down where we haven't mapped X to anything or we've mapped X to some other thing or there's some other definition for X that we didn't actually expect to be there now。

That's showing up right here This turns out to be just really。

 really difficult for programmers to reason about the other big reason why it fell out of favor。

 at least to some extent， is even though this is very easy to implement in the interpreter right。

 we can take a look at what we did right here and if instead of just putting in FN we had mashed together FN and our original environment。

 we would have implemented dynamic scope right away so this is pretty easy for us to implement in an interpreter。

 it turns out to be actually really hard to implement in a compiler。



![](img/a3ef23f31cb4997ad70de84abccf370b_3.png)

![](img/a3ef23f31cb4997ad70de84abccf370b_4.png)

So what we have done instead is said， okay。The definitions that are available inside our function depend on where it is in this text file right And so this is where I'm going draw our attention back to these names。

 right， Lexicalco or static scope versus dynamic scope。 Lexicalco or static scope。 again。

 We're hearing that word that we're used to thinking of as being associated with compile time used to thinking about it as。

 hey， there's this program， this program is this tree。

 and we're thinking about the shape of the tree as it was sort of written down in our source file。

 right， Sta scope is thinking about that。 We can just look at this program and figure out， okay。

 what are the names available to us right here。 versus dynamic scope。 Okay。

 it's thinking about what has already happened so far during runtime。

 What are the bindings that we have seen during execution so far。

 So that's how these names relate back to these terms that we have been seeing over and over this static versus dynamic。

So I know that static versus dynamic scope， lexical versus dynamic scope is very， very confusing。

 now would be a great time for questions。😊，Well maybe we've all got it， this is a very good。

 clear illustrative example， so maybe we're feeling good。Yes。😊，😊，I love this。 So this question was。

 hey， why are we saying， let's just go ahead and pass in these definitions。

 just sort of wholesale in here。 Like， why are we making all of the function definitions available inside the bodies of all of the functions。

 And basically， that's just the decision that we made， So we sort of looked through。And said， okay。

 we want to be able to write programs like this where even is allowed to call odd and odd is allowed to call even where we can have that sort of mutual recursion。

 which is only possible if we are making both of these functions available to each other。

 even though one of them is in fact defined before the other。So right now。

 we can only introduce function definitions at this top level。

 We are having this sort of fixed set that appears in sort of the first half of the program and all of those are going to be available throughout。

 Now， later on， we are going to actually add firstclass functions。

 and when we add firstclass functions。 So treating functions like values we are， in fact。

 going to be able to create them inside a defined scope。 So for example。

 inside the body of a function and then that function will only be available within that scope within the body of that function where it was defined。

 So we are eventually going to have the option to introduce definitions that will only be available some places But for now。

 the way we have said that these definitions are going to work all the definitions that we have are available everywhere。

Oh， okay， so this question is sort of thinking about when do we get access to these functions。

 Are we ever going to have the problem where we are trying to call a function。

 but it hasn't been defined yet for this， no， right。

 So we have all these function definitions that are provided at the top of the program。

 We can think of it as though the very first thing that happens is we make those things available。

 right， We make those functions available。Other questions。 Are we feeling good about。

Dynamic versus lexical scope。各就。That calls。Is that dynamic？

I'm not totally sure I understand the question。 So I think the question is basically about this program。

 So right here we have a function F， and then inside function G， we can call F。

So it functions you we call F。Value。 and then like。Calculation and would that like。在点。

I'm not totally I didn't understand the question， come up during the break， we'll chat。等长。Okay。

 we are gonna do a nice activity on。😊，Static versus dynamic scope after the break。

 So we are not leaving this topic。But we're feeling kind of okay， maybe。Okay， in that case。

 let's go ahead and come back together at 429 if you have questions， come up。

See you all after you stretch and get water。Is it helpful to see this？Yes， yes， thank you Okay。

 so I guess with the function like defined geobacks， like it's calling alphabes。没配是的。带两 makes。

So that might be the issue， would that be dynamics， that a dynamic scope？

It's kind of a disconnected question。 actually。 So if you think about the decision。

 like the decision that we were looking at， right。Right。Here， right。

 like what we choose to feed into this。Is the thing that decides if we are doing dynamic versus static scope。

 right， So if we choose to make available all of the definitions that were available where we made the call。

We have done dynamic scope。 Okay If instead we choose to make available only the definitions that are available within the the sort of scope in which the function is defined right。

 so for us， that's always going to be the top level。



![](img/a3ef23f31cb4997ad70de84abccf370b_6.png)

![](img/a3ef23f31cb4997ad70de84abccf370b_7.png)

Right。The only things that are going to be。Available to F are going to be its own arguments。

 plus any other definitions that exist， plus also itself。Right， likewise for G。

 the only things that are going to be available are the other definitions plus its own definition plus this value x right that's what makes it lexicalco is that we are sort of looking at the source code in order to figure out what should be available inside the body。

Make sense。 thumbs up。I had a question。 I mean， oh。

 what is that curly bracket thing that we used today definition。

The curly bracket that we used to create the definition， like you said。

 like something name ors and body。 Yeah， Do you remember like way， way， way， way。

 way back when when we introduced types that we actually used in order to to。



![](img/a3ef23f31cb4997ad70de84abccf370b_9.png)

Sometimes we made types where we were just like， oh， it's all the order。

 but sometimes we made types where we were allowed to give names。



![](img/a3ef23f31cb4997ad70de84abccf370b_11.png)

呃。That's what we're doing。 Okay， so is it uniquely identified by the first one？

Is it uniquely identified by the first one？as aOh like could we actually treat it just based on order or do we have to provide the name we have to provide the leg example。

As in like，1。Like could we one。does our current definition of a function then allow us to overload a function having the same symbol。

 different number of arguments？This definition would allow that。 Now。

 the way that we actually retrieve definitions does not。

 because if we take a look at what we're doing here， all we're doing is saying if the name matches。

 if the is unique Yeah， otherwise we're like we could try putting in multiple things that have the same name。

 we'll grab one of them。But we could just change how we do this， right。

 like if we wanted to get it based on name plus number of arguments。

 if we wanted to get it based on name plus， you know， function signature。We could do that。

 we just haven't。it possible to pass functions as part the argument or Well we are implementing now No right so if we take a look at how we have actually implemented it。

 we can see that our environment right is only going to have like the definitions are passed in separately and then the other names that we can use in that way are here now eventually in about two。

 three weeks， I'm not sure exactly when， but two three weeks or so we are going to implement first class functions and then yes。

 absolutely right then suddenly our functions are values we've passed them all throughout。Alright。

 I'm gonna bring us back together， and we will run some of these lovely functions that we now have available。

 So our interpreter is ready to go。 We can now run programs in our Cs 164 L that actually use functions。

 So let's do it。 This one is pretty simple。 right， We just make the identity function。 We pass in 4。

 We get back 4。 Not super exciting， but whatever。 You know。

 we're working towards more interesting stuff。 Let's try this one。

 I'm expecting to get 9 out the other end。😊，Let's see if I do。Oh yep。

 we're getting nine out the other end， that looks good。What about this nice Fibonacci program。

 So we've got recursion going， That's nice。 It's going to ask me what number I want to call it on。

 So let's go ahead and do interpretp。All right， let's try it on 10。 Okay， nice， getting an answer。

Let's try it on 20。Okay， yeah， it's slowing down a little。

 but yeah it's working and let's try it on 30。H。Well， that started to get pretty slow。

 Let's try it again now。 Let's try it with 40。嗯嗯嗯嗯。This is sure starting to take a long time。

 And so hopefully this is at least a little bit satisfying to us because way back at the very beginning of class。

 I talked about how， hey， were gonna be able to use compilers to make programs that run real quick。

 but interpreters in contrast， maybe sometimes they're going be slow。

 and then we sort of talked about that for a bit。 But then this whole time we've just been running all these tiny little programs。

 and we never actually saw it。 And now finally， we're actually at the point where we can run something big。

 right， This is just going。 This is just going and going and going。

 and it's taking a while and we are gonna figure out that we're gonna be able to make this run a lot more quickly on our compiler。

 So we're moving towards bigger and better things here。😊。

I'm going to go ahead and stop it just so we can run that fourth example and then we'll do our little activity。

It takes a while。 It takes a really long time。 So let's go ahead and do interpretp。

And this has our mutual recursion。 Let's see if four is even， four is even a shock to us all。

 I'm sure let's try5。 A，5 is not even。5 is odd， fantastic。😊，Okay。

 our programs are behaving the way we would probably I think， expect。

 So now I'm going to have us think a little bit more about static versus lexical scope。

 sorry static slashxical versus dynamic scope， very important。Okay。

So what I want you to do with folks nearby is basically walk through filling out all of these， well。

 not the ones that have the dashes in all of these little cells。

 You don't have to actually write it down in this table form。

 You just have to decide for yourselves what will go in there。

 And then I'm going give you one little bonus question， which is are the two。Columns。The same。

Discuss for。Let's give it a minute and a half I think this one will be quick。All right。

 let's first make sure we're on the same page about this first row。

 Does someone please shout out what should be in this cell？I'm hearing six。I'm hearing error。Okay。

 let's keep thinking about it。 Feel free to whip out the interpreter， the Python interpreter。

 totally fine。All right， let's hum4，6。Let's home for error。Yeah， I agree。

 We're gonna get an error there。 What about for our list， Han， if you think 6。

Howome if you think error。Yeah， this is the decision that we just made right we said， hey， no。

 we're not keeping around those things that we already saw in the environment in which we made the call。

 we're throwing all of those away， and instead we're only going to have access to the arguments to the function itself。

So now let's take a look at this sort of blue spot that we've got right here。

 we've got highlighted is Arg1 in scope if we are in Python， hum， if you think it is in scope。

How if you think it is not in scope？Yeah， I totally agree。 right， Like we can see that right here。

 we've gone ahead and actually provided that as the， the argument。 I would say that is in scope。

 What about for our list， Is that in scope， Humphre yes。Hm Ver no？Totally agree。

What about x in Python， if we tried to use x at that blue line， is x in scope。Home for yes。

Home for no。Yeah， I agree， right， We do not have access to that。 What about in our listsp。

 Hu for yes。Hum for no。Okay。Sooo， I was taking us through the wrong thing。

 I was taking us through the answers if this is just the actual language。

 let's go back and pretend that we are using dynamic scope。 I'll give you an extra 10。

20 seconds to chat with folks if we pretend that we are using dynamic scope as X and scope。All right。

 now that we are pretending that we're in dynamic scope land。

Do we have access to X at the blue line hum for yes。Hum for no。Yeah， I agree。 We do have access。

 What about an our list， P for yes。Hm for no。Yeah， I agree。Okay。

 but now let's swap into lexical scope land， right。

 Let's assume now that it doesn't matter sort of what bindings we've had available sort of up to this point during the execution。

 What matters is what is in scope when we actually look at the source code。

 So let's go ahead and think about for Python is arg1 in scope。 Hu for yes。Hum for no。Yeah， I agree。

 We can see that's right there， right， so we can take a look。 Ar one's right there。

 We're using it right there。 No problem。Okay， what about in our list is R1 in scope？Not in scope。

Yeah， okay， we are all on the same page there。 Now， what about X， So in actual in in Python， when。

 if we assume that Python is using lexical scope， is X in scope hum for us。He for no。Yeah， I agree。

 What about for our list， if we assume that we are using lexical scope， Hu for yes。Hum for no。Yeah。

 I agree。 if we are using lexicalco， which is the thing that we just implemented， right。

 we just went through the process of saying， okay， within the function body when we are actually doing the interpretation on the function body。

 the only things we're going to make available are the arguments。

 right That's all we're going to make available so。

We know the difference between lexical and dynamic scope。 So now we can think about。

 assume that the language uses dynamic scope。 So here， assume that Python uses dynamic scope。

 What output will we get。I'm hearing six， hum if you think six。If you think error。Yeah， I agree。

 And what about if our Lsp uses dynamic scope， what do we get back。if you think six？

Hom me if you thinking of anything else？Love it。 I love them We're on the same page。 That's so nice。

 And assume the language uses lexical scope。 Then what is the output。😊，I'm hearing error。

 how if you think error。How if you think6？All right。And what about in our list。

 if we are using lexicalco， what is the output going to be。I'm hearing error， how if you think error。

Home， if you think something else。Fantastic， it looks like we're all on the same page， right。

 So this is telling us what these languages are actually using， not too surprising。

 given that I just told you that probably every language you've ever used does， in fact。

 use lexical scope。 But we can tell now that our languages that we are reasoning about right here are both using lexical scope。

 And that's why for the real programming languages。 If we actually run these。

 We're going get our sad faces in both of those columns。 And we can also， of course， see。😊。

That these columns are the same for each of these， right This is really just the way that we can answer these questions。

 It almost doesn't have anything to do with the underlying languages， except for this row。

 So that row obviously did have to do with the underlying language。 but other than that。

 we can answer this question just based on knowing whether we are using dynamic scope versus lexical scope。

Hows this brought up for us， new questions？About dynamic versus。Lexical scope。我列。

I love this question。 So this question was if I have a global variable in our LP program。

Would this still say the same， basically， So I'm going to give a two part answer。 So one is。

 is there a way for us to actually introduce a global variable in our list。

So we can do a lead expression， but we promised ourselves that we were always going to make。

 at least for our current version that we've implemented right now。

 we were always going to have our definitions at the top level。So as soon as we， you know。

 start a let expression out here， right， let X 3， whatever， right， suddenly。

 that's not at top level anymore。 So we are currently not allowed to do that。 Again， eventually。

 we're gonna implement first class functions， and then we will become allowed to do that。

 So that is going to happen down the line。 But for now。

 there is simply no way for us to actually introduce a let binding that would then actually surround the function definitions。

 But， yes， absolutely， if we have lexical scope。 So the same kindoscope that we actually have。

 And then we have a let binding that appears around some definitions。

 that value is absolutely available within those definitions。Yeah， because again。

 we're thinking about where is this in the code in the program in the source？

Which is why when you see all the programming languages you've interacted with。

 they would have X available。Other questions。 sorry， this X。

 the the X that I'm talking about right here is this one， so。Not that one。

 that one would still not be available。And so in fact， yeah。

 that's actually a really interesting question。 when we then would see this， right。

 we would see that that would actually refer to that one and not to this one。This one。

Other questions we're feeling pretty okay about that so far。Okay， cool。

 So I'm going to bring us back to looking at our interpreter because now we are ready to do our usual thing of moving on to the compiler。

And often we do something where we sort of take some inspiration from the interpreter about how we might then implement something in the compiler。

 So if we sort of squint at what we have done here。We've done this thing where， okay。

 as soon as I see。The the call to a particular function， I then find the body for that。

 and then I go ahead and figure out how to actually run the body。I can imagine。

Doing the same thing in the compiler， right， I come across a call to odd or even。 And at that stage。

 I go in and I grab the assembly associated with the body of odd or even。 And I submit it。

 just sub that right into our assembly。 Would that be a good strategy。

 It kind of resembles what we're doing in interpreter land。

Would that be a good strategy in compiler land， discuss with folks nearby？All right。

 so hum if you think that's a good strategy？Home， if you think that's going to be a bad strategy。

Yeah， I have to agree。 That is gonna be a bad strategy， right。

 And we can think about it from the context of that Fibonacci program that we were just running。

 right if what we're doing as we go along， we've got our first Fibonacci call fantastic。

 We go find the body of Fibonacci。 We sub the assembly we're going through and generating the assembly for that。

 And we find this call to Fibonacci。 okay， well now we go we get the body for Fibonacci and we start generating these go again。

 find another call。 We go again， right Like we end up with this infinite space program。

 That's not gonna to work right We can't just have infinite assembly。 that is not gonna work for us。

 So we're gonna have to find some other way to deal with this。😊。

So what might be something we've been thinking about maybe for the past week or so？

That could potentially help us out here。 Go ahead and discuss with Fols near by。 halflf a minute。

 What have we got。All right， what do we think， what's something that we have learned about that might help us out here？

Please feel free to yell it out。I'm hearing call。 I totally agree， right， Up until this point。

 we've been using call in kind of a wacky way where we were in charge of actually generating the assembly for doing the call。

 But we were not actually in charge of generating the assembly that was getting called。

 getting jumped to， right， So if we take a look at， say， our use of print value。



![](img/a3ef23f31cb4997ad70de84abccf370b_13.png)

![](img/a3ef23f31cb4997ad70de84abccf370b_14.png)

呃。Oh， that's the interpreter。 Let's look in the compiler where we would actually do this。 Pri value。

 great。 So we were in charge of actually emitting that call instruction。

But we were not actually in charge of making the runtime for print value that was being done by when we compiled our runtime so the C compiler was doing that work。

So now I think we're in the situation where we maybe want to think about both sides and so here I want us to think for maybe 10。

15 seconds， which of these things the yellow highlighted thing looks like the thing that's going to be called to that's going to be jumped to versus which thing looks like the thing that's going to be doing the calling right。

 which thing is going to admit that call instruction and which thing is going to emit the Re instruction。

Alright， I don't think this is going to be too surprising。

 but what we see right here is what we call a call site right。

 The things that you have seen in the past where you talk about calling a function just colloquially。

 it all kind of means what you're going expect it to mean。 And then this。

 the things that are going to get called， the things that we are going to jump to when we do the calling。

 we have obviously already been giving the name definitions。

So the reason that I'm harping so much on this is that previously when we've added a new language feature。

 we've always been able to just go into our compiler and sort of add one new case and call it right。

 That's sort of always been enough。 We've just added one new match case and we've always been able to make that work。

 Now suddenly we're in a different kind of weirder situation。

 where we are going have to generate one thing that is in charge of doing calling and a different thing that is in charge of getting called right。

 and we have to make sure that those are going to play nice together right。

 we're going to have to have a way for them to sort of talk to each other。

And so what do I mean when I say that they're going to have to talk to each other Well。

 I mean that all of a sudden， if we're using call， we remember what the call instruction does。

 actually starts messing around with what's on the stack right So let's go ahead and think about this program here we've got our call to display right we're going ahead and providing two arguments to display and then we have this definition of our display function。

And that is going to be seeing a different version of the stack。

RightIn the same way that the runtime that was calling our programs was seeing a different version of the stack now suddenly different parts of our code are going to be seeing different versions of the stack right so here is the return address that we've already been sort of thinking about right previously up in town out this entire time we've just been making up the assembly for a single function entry That's it and now at last we are going to go ahead and have multiple labels for multiple functions。

 we are going to have different little segments of our code that we can be jumping around to that well see different versions of the stack。

And so one of the things that the call sites are going to have to wrangle is making sure that the arguments that say display is going to need。

 that those are available within its section of the stack right， because remember。

 we've talked a long time about the fact that we're not allowed to sort of look under return address。

 There's all these other things happening down below here。

 and we're not allowed to mess around with those。 The same is going to hold true。

For our display stack， right， the stack frame associated with the function that we are now compiling。

 It's not allowed to look down below at anything we've been doing inside here。

So what I want you to talk about with folks nearby is where should we put， in this case， M and N。

In order to make sure that we are going to have access to it when we are actually executing the body of display。

 and the other question I want you to ask is who is going to put the values associated with M and N there。

 Is it when we encounter a call site that we will put the values there。

 Is it when we encounter a function definition that we will put the values there。

 Go ahead and talk about those two questions。Al right。

 so hopefully everyone came up with a scheme something like this， right。

 It doesn't really matter if we put these on the stack top to bottom， bottom to top。

 What's important is mostly just that the two sides that are communicating agree。

So it's important that when we are compiling that definition。

 it is expecting to find the appropriate values at the same place where the thing that is doing the calling has actually put them。

And so that brings me to a point that I think all of you are already going to be familiar with the fact that we might call a function multiple times。

 right so when we see a definition for a function， we can't just bake in particular values。

 like maybe here we you're calling M and N on whatever it is 4 and 6。

 but somewhere else we're calling it on 12 and 18。RightSo we don't get to go ahead and bake those in when we are making this function definition。

 when we are producing the assembly that's going to correspond to that。 So instead。

 we're just going to have to make assembly that assumes someone else has set up this region of the stack for us。

So okay， hopefully that also answers that second question I said to you of who is going to be in charge of putting those there。

 It is going to be the call site that is in charge of putting those there。

 because this is going to actually vary depending on the different call sites。

 We're going to get different values for those arguments。

Are there questions about that before we start actually implementing it。

 we won't get all the way through， but we'll start。

So let's go ahead and dive in on making some changes that are going to look a lot like what we actually did in the interpreter。



![](img/a3ef23f31cb4997ad70de84abccf370b_16.png)

So the first thing we're going to want to do is go ahead and again we have now the definition span and then the body。

 let's go ahead and do sort of that same equivalent thing that we were doing for the interpreter where we were saying。

 okay， first let's go ahead and parse many so let's go down to where we're parsing So now we no longer want to do the same thing there。

 we're going to go ahead and actually compile。

![](img/a3ef23f31cb4997ad70de84abccf370b_18.png)

The par many。Great， now we're going to have access to those multiple S expressions。

 Let's go ahead and make compile ready to actually accept that。 So let's see。

 let's go to compile right here。 It is currently expecting just a single S expression。

 Let's instead make it accept a list of S expressions。 And now it's saying， hey。

 this is a list of S expressions。 I don't want it to be a list of S expressions。

 So let's go ahead and grab out the definitions versus the body。😊，Deens and body applied to program。

 And okay， so what do we actually want to do here， Well， we want to apply that on just the body。

 right， That's something that we know we're actually already comfortable with。

 We already know how to compile just the body。What is the other big change well。

 in the same way that we changed interpret。 ML such that we were stringing through definitions in our interpreter。

 we're going to have to actually do the same deal with our compiler。

So let's go ahead and come up to compile X。 and where we have。

This our first thing previously was the symbol table， we will now have Dens， which is a Din list。

So again， we do our thing where we。Replace compile X。With compile X applied do defens。

Oh let's go through， is that working？No。😔，嗯。Great。Okay， so let's go look at that last one。 Great。

 We are going ahead。 We are calling our compile expression。

 We are making all the definitions available。 We are using that empty Sim tab。

 We are using our negative8 offset and we are compiling the body。

 The other big change we're going make here in our last three minutes is let's just pretend to ourselves。

 We don't yet have this。 But let's pretend to ourselves that we do， in fact。

 have something that is going to handle making definitions for us。 So let's go ahead and conca in。

Can cat map。Compile dein。Apply it to all of the definitions。And then apply to all the definitions。

 So let's real quick make the signature for that， and then we'll call it a day。

So here's the thing that is going to be in charge of actually compiling the definitions。fileile。

 defin。Deence。Din， that's a lot of deinens。 I'm just gonna real quick talk about what we're saying here。

 So this is in charge of keeping track of all the definitions are available。 This is talking about。

 couldn't spell。 let's spell that right。 This is talking about the particular definition whose body we are now going to turn into assembly。

 So that's what's happening right there。I don't think this is going to be super surprising what happens in here。

 but since we have already sort of talked about the fact that we are going to be calling to this。

 we are going to be jumping to this， let's add in just one of the lines of assembly that's going to be relevant to us。

 and that is going to be the label。So what we are actually going to do is we are going to go ahead and use something that looks a little bit like gensim in that it is going to make a version of the name that is useful to us。

 Now， we cannot actually use gensim。So why can we not use Gensim， I want you to take 20。

30 seconds to chat with folks nearby about why that won't work for us。All right， What do we got。

 Why can't we just use Gensim。It's a little bit weird。Exactly， so this answer was， hey。

 Gensim is intentionally trying to make a brand new version， right。

 it's going to use the string that we provide as input。

 but it is always adding this new counter on every single time that we call Gensim it's adding this new counter on and here we have this situation where we know that we are making this definition here but other somewhere else。

 we're going to have a bunch of call sites that are going to to be able to reach this label so we'd better be able to actually deterministically get from the string associated with that function name to whatever label we are going to use And so we'll have our little defafin label to do that。

All right， happy five o'clock everybody and we will wrap this up on Thursday。



![](img/a3ef23f31cb4997ad70de84abccf370b_20.png)

Oh。ちて。I， ladies。I'm very sorry。 That's okay。 I have like。

