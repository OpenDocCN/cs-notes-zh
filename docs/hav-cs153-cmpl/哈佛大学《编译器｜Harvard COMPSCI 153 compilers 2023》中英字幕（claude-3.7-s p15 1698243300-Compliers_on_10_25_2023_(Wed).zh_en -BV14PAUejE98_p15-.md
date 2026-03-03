# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p15 1698243300-Compliers_on_10_25_2023_(Wed).zh_en -BV14PAUejE98_p15-

So I will be teaching a new graduate level course CS S254 formal methods for computer security。

 You can take a look on canvas for some information about it and a proposed schedule。

 I will point out as the first time the course is being taught。

 So it'll be a bit of a bumpy ride so don't expect the same smooth well owe machine you're seeing in the compilers course。

 it'll be。呃。Things will be much more last minute。Also。

 Professorta Arman is teaching CS152 the programming languagengus course in the spring。

 and for those who haven't taken it， it's a really nice compliment to the stuff you're learning here in compilers。

 but it's more on the formal and mathematical side。

 it's really the mathematical foundations of programming languages。

And we see some of that seeping in to the work that we're seeing in compilers。 really。

 I think some of these algorithms that you're seeing perhaps have the most complex abstractions going on。

 And so that way of。Thinking about a programming language in order to make it tractable。

 in order to actually be able to figure out how we implement it and implement it correctly。

 the basis for those ideas are really coming from the formal study of programming languages。

 which you can see more often than 152。😊，嗯。Related to that， today。

 we're going to be continuing talking about compiling functions。

 but as of next week for two or three lectures， we'll be talking about typing typing rules。

 So we'll be seeing more inference rules and learning more about that formal logical approach。



![](img/71163bc805ce2f473979896db9aba9d2_1.png)

To typing。 And that's also something that's a key part of 1，52。

 So if you're up liking next week's lectures， you might enjoy taking 1，52。

Any questions at the moment。Okay。So as I mentioned。

 we're going to be continuing to talk about compiling functions today。

 and we touched on closure conversion and Lada lifting at the end of last class。

 I'll talk a little bit more about those。 and then we'll see a little bit about implementation details。

 how we actually go about doing this。Alright， this is actually the slide we saw at the end of last class going about compiling closures by representing function values as that pair of a pointer to the code。

 a function pointer and the environment that is a binding of variables to the values to use within that code。

We explicitly make all functions take an environment as an additional argument and then access variables using that environment。

And once we've actually put our functions， our nested functions into that form。

They're actually no longer directly referring to variables in the enclosing function so we can actually lift them to the top level。

So called Lada lifting。And we walk through a simple example in C like code。

 We'll see a more detailed walkthrough of this in just a moment。

 But the key idea that from this nested function。Fun X， fun y， Y plus X。

 We can turn this nested function， Fun y to Y plus X into this top level C like function that takes an environment and the argument Y and ends up accessing the variables X and Y through an environment data structure。

Okay。Any questions about this high level view of closure conversion。

 We're going to look into it in a bit more detail and make it a bit more concrete。

 but any questions at the moment。Okay。嗯。So let's see this idea of closure conversion on a in slightly more detail。

 let's actually think about having a in our functional language。

 having an nested function and performing this closure conversion step by step。

 So that is we're going to remain in our functional programming language。😊。

But we're going to explicitly have an environment。 So here we are explicitly modifying these two functions to take E and V as an additional argument。

We'll get into what this is。 But you know， if we're thinking of an Ocal like language。

Maybe this is some data structure， some abstract type from a module。We're able to do things with it。

 such as extend the environment。 So here we're seeing extending the environment with the binding for x。

We're able to look up using the environment， so here we're passing in the name of the variable to look up in an appropriate environment。

Okay。So， this transformation。Adding an explicit environment and looking up the variable using the environment。

 you can imagine this you know， happening in one pass of the compiler still at the functional programming language level。

Okay。Now。Because we've managed to put。Access our variables through this environment data structure。

This is the same code that we saw previously。You'll actually see that inside this nested function。

Function that takes the argument way。 We're not actually directly referring to the program variable X anymore。

What was a reference to the variable x has now actually turned into this lookup of a string in the environment。

So what that means is there's no reason why this function down here in the closure。Actually。

 needs to be nested down here。 We're going to lift it out to the top level。So we do that。

 Let F to equal function。 So this is exactly the definition of that function in the closure。

 But now we've lifted it up to the top level。Clled it F2。And replaced it in the closure with。

The name， F2。Reference。And now， when it's in this form， still in a functional programming language。

When we see it in this form with only top level functions。

It becomes much clearer how we can convert this into a sea like language that doesn't have nested functions。

So here is that same sea light code that we saw a few slides back。

 but now the connection between this gradually transformed functional program into this is hopefully much clearer。

 it didn't happen in one big step it happened and some nice， easy。

 simple passes on the language that are hopefully clear and straightforward。

Any questions about this notion of compiling closures， closure conversion， Lambda lifting？Great。

So now that we have this idea， this high level idea of how we going to take a functional programming language。

Do the closure conversion。 Do the lambda lift lifting。

 Let's actually think about how we're gonna do this efficiently， right。

 more than just how we accomplish it。 What are some of the ways that。

We can make things more efficient。So one of the things that I mentioned is where do variables live。

 And at the moment， with this simple approach to closure conversion。

 we just put all of the variables into the environment。 That is essentially。

The variables are all living on the heap now。So that's not great。

We're going to see later how we can take。localally allocated variables and put them into registers a lot of the time to make access to them very fast。

 But when we have storage in the heap， that's much harder for us to do in part because we don't know who else is referencing those variables and so on。

The good news is that we don't actually need to allocate all the variables inside inside a function。

 Instead， we can do an analysis to figure out， well， which variables might escape。

 Which variables might end up being used by a nested function that's going to be converted into a closure sometime in the future。

😊，So what that means is a lot of the variables that you actually write in a function in your functional programming language will never actually escape and as a result we can treat them the same as local variables in a non-functional language and don't have to allocate them in the environment。

 so we only need to do this for the variables that might actually be used by closures。😊。

I'm not going to look into this anymore。 just be aware that this is an optimization we can perform。

So how do we end up implementing these environments？And variables efficiently。So again。

 the example transformation I gave。Was actually really inefficient。

RightWe were kind of I didn't go into the details of the data structure that we were using for environments。

 but essentially it was associating strings， the name of the variable with the value to use for that variable。

So what this means is， you know， let's suppose it was an associative list。

 But even if it was something else， some other data structure。

 what we're still doing is taking in a string and performing some kind of string comparison or say。

 computing a hash of a string or something like that。So this is going to be expensive。

 the fact that we're referring to variables by a string at runtime。

Is it going to be providing some amount of overhead？So。We can avoid that。

And there's this nice encoding。Instead of using strings to name variables。

 we're going to use natural numbers。 This known as debrain indexing， dein indices。嗯。

More than just using numbers to represent the variables。

 we're actually going to use a pretty clever way of numbering the variables。So that it turns out。嗯。

A lot of the time， we never need to explicitly talk about the variable at all。

So let's see what I mean by working through。And introducing this idea of de indices。Okay。

 so let's suppose that we have。Our new intermediate representation。

It's going to be the same as our mini L language。 We have integers。 We have function definitions。

 these lambda terms。 we have function applications。 We still have variables。

 But instead of using a string to identify a variable， we're gonna use an integer index。Okay。Now。

 what we're going to do is。Convert our an original program。

 Let's suppose we had an original program where variables were named with strings， Fund X， fun Y。

 Fund Z， X plus Y plus C。Conceptually， we can imagine that we simply rename the program variables。

Right， x2。X1， x0 okay， this is a straightforward transformation now on the body of the innermost function。

 where it's the same computation， we're just referring to the variables by their new names。

 x2 plus x1 plus x0 instead of x plus y plus c。But then because all of our variables are going to be numbered。

😡，We don't need a name at all， right， We can actually just。When we define a function。

 we don't actually need to provide a name for the function。Right， instead。

 we're just going to use the index where the integer index is referring to the lexical depth of the function definition。

 So that is。The variable。Within x0。Is the variable that was bound by the innermost function definition。

The variable with index1。Was the next and amost function。And same with the index2， right？So。

 there is。Once we've gone to this indexing scheme， the idea is we use an integer to refer to the variable。

Based on lexical depth。Of the function definition。Then we don't even need any kind of name of an argument。

For a function。Okay， we simply。Know implicitly by the index。

 which argument we're referring to of the innermost， the zero with function definition。

 the one function definition， second function definition and so on。

Any questions about this Dene index andcoding？Of variables。

like why do you have two parameters to a function？Oh， great。

 We can actually extend the dein indices in a straightforward way to allow functions to take multiple arguments。

😊，嗯。We'll get to it later， but imagine that you have a pair of indices that's say with the first indexes。

 which function definition are you referring to。And then the second index is which argument from that function definition do you want？

But we'll see a worked example of that soon。Thanks， yeah， William， technically。

 wouldn't this function in some sense already taken multiple arguments？

Because you can think of it as add3 numbers， so it takes three arguments and ads。Well。

 these are carried functions。 If you remember that from from 51。

 in the sense that these are actually nested functions， right， and you can partially apply them。

 So given this function， I could。Apply the outermost function。In siating X。

 and then it'll be left with。Still， I still have a function left over。

So there might be optimizations you can use locally and realize if you realize that this function is only ever used with all of its arguments and when the closures never actually going anywhere were interesting。

 you could perform local optimizations that treat it as a function that takes all the arguments。

 but in general， when you see this kind of thing， you should think about it as being nested functions。

Jry， what about local？Locally， declared variables。I'm going to say for the moment in compilation。

 you can just end up。Referring to them by name or you know if you think about the LOVM representation。

 you might imagine using that UID way of naming the local variable and referring to it。

 you can use de indices for handling local variable say defined in allette。

 but that's often because you can think about letters as being shorthand for a function definition and application。

But， but we typically。From a compilation perspective， were arise much more strongly。

 locally within a function。And might be able to and don't necessarily need to use this encoding for efficiency。

 but in that case we have to extend the type。Vable both of Oh， I see。 Yeah。

 So for the representation， maybe we end up using。嗯。Yes。

 the way we end up representing the use of variables might be。We need to make sure now。

Intermedia representation that we're。If we're having different kinds of variables that we're referring to them appropriately。

Thanks。I will say it actually。The way this often works on a compiler pipeline is that you might be doing this sort of closure conversion and Lada lifting as we kind of hinted at。

Still at a functional programming language level。And then converting into a lower level intermediate representation where you're dealing with sort of function bodies in a separate way。

 like in an LVM like way。 And interestingly， we have a visitor， Professor Aola。

 who's visiting from the University of Oregon and some of her research is actually based on extending intermediate representations So it more directly expresses some of these functional representations like closures。

or。Is that correct。Yeah， so we're glad she's in the class and it's very relevant。

To what we're talking about today。Yeah， thanks for the question。Any other questions at the moment？

Okay， so we have this。De Bruin index encoding。嗯。Let's think about just how we convert。

From a programming language with variable names。Into the Dein index。It's not too difficult。

 to be honest， we have a recursive function to。To convert。Let's see。呃。

So we're going to convert an expression in our language with variable names。

Into an expression with the de Bruin and disease。We're going to use an environment that maps program variable names。

🤢，Into their de Bru index。Okay， so when this translation integers straightforward variables。

 We have a variable with the name with a string X。 We simply look that up in the environment to tell us which index it's currently mapped to。

And that's the debroine variable index that we're going to use for it。For application。

 E1 to apply to E2， the conversion， we just recurse on the sub expressionions。

 So convert E1 and E2 and constructs the application。Function definitions are a little interesting。

So， lambda X E。Within the body E， it might be referring to the program variable X。

 So we're going to extend our environment， create a new environment。That we're going to。

That we're going to use。And this new environment， a function from variable names to indices。

It takes in a name Y。 If y is equal to the name X that we're defining。Then the index is 0。

 It's the innermost。Variable definition。Otherwise ways。

 we look up in our existing environment to see what an index it is。And add one。Right。

 so this plus one here， this is kind of key to this idea that the de index is referring to the lexical depth。

And when we go into an nested function， the de Bruin indices of all of the other variables increase by one。

Okay。And then with this new environment， we simply convert the body of the。Of the function。 And。

 of course， you'll note that in our De Bruin index representation， we don't have a variable name。

It's just the variable is implicitly to zero width index。So down here。

 we simply convert the expression E with a new environment。Any questions about this conversion。Yeah。

'm comes。Oh， so we're defining here new in， which is a function。From var string。To int。

Why is the string argument to this new end function that we are defining。Of we don't know it。No。

 we so this will be used later on when were when we're recursing into E。

And converting variable names to dein indices， we're going to be looking up variable names using this line of code right here。

 So eventually， we'll get into a sub expressionion that's nested in there。 That's a variable。

 and we'll be going to the environment to say， hey， I've got a variable name fo。

What index is that at the moment？And we're looking up the environment。 So end here is the function。

This is the function we're going to use when we recurse them into the body。

If the verbal name way that you're looking up is。X， the variable name we're defining right here。

 Then it's in x 0。 otherwise， it's。Whatever end said it was， plus one。Does that clarify thanks。

William， why do we default index0 within that all the way to beginning the chain of functions so this is the interesting point that the zeroeth index is the innermost function definition rather than the outermost one and essentially what this does is enables more local reasoning。

😊，Right， that you can have。That in some ways， if you have a function that's referring to the zero with index。

 that sort of doesn't matter and only the zero with index。

 it doesn't matter where that definition occurs。 It might be deeply nested。

 It might be the top level， the indices makes sense。 whereas if you number from the。Outermost。

Function definition to the innermost then the meaning of the variable very much depends on the entire context of where it's sitting。

Great。Thanks for the questions。Okay， this is converting into Dein index form。

 I did just want to quickly talk about evaluation。If we were interpreting this in De indices。

First of all， values here。When we're interpreting this language integers and closures。

 closures consist now of an environment。 And remember the function， the function definition。

 But because we don't need to explicitly name the argument of the function。

The closure really just needs the code， right， The body of the function， no need for a variable name。

In this simple representation， let's suppose that environments are just a list of values with the idea being that where the index within that list is the appropriate dein corresponds to the De Bruin index。

 So what that means is when were evaluating an expression。If we see variable。X， remember here。

 x is number an integer， a number。We simply go to our environment and look up the n number。

 the X number， rather within the。With an our list。And otherwise， things are。Pty straightforward。

Inteagegers evaluate to integers， function definitions evaluate to closures with the current environment application E1 apply to E2。

 E1 should evaluate to a closure， E2 will evaluate to the argument。

 and then we simply evaluate the function body E prime with an extended environment where V is put on the beginning of the list becomes the new zero width element of the list。

Any questions about the evaluation。No。why lambmbda here only has one。Okay。

 so remember with the dein inices， we don't actually need an explicit name of the variable instead the。

Argument。The variable for that function is just the zero width index。

So it's kind of cool right you have these function definitions that don't explicitly need a name of the variable and our conversion from named variables to dein indices sort of was where we saw the a function definition going from a pair of a variable name and function body to simply a function body and we see that reflected here in closures as well for our closure。

 we just need a function body We don't actually need the name of the variable for the function。😊。

And then this idea that the。The argument for the function is the  zeroth de index。

 We see that reflected down here when we apply a function。嗯。Okay， have a copy pastetypo here， sorry。

Bod should just be E prime。 V is the actual argument to the function。

 and we simply put it as the new zero with index of the list of the in the environment list。

And everything else that was in the environment， its index gets bumped up by one now。

 since we added something else to the front of the list。Right。Okay。So。We have these de indices。

We have the intuition for what it means to execute a program that uses the brain indices。Okay。

 let's actually。Think in a little more detail about the implementation of this。 Like how， let's say。

 when we are going from this functional programming language， which now has， let's say。

 only top level functions because we did the Lambda lifting。 We did the closure conversion。

 We did the De Bruin index conversion。Our next step might be to implement that。

 to translate that into an LOVM like language， essentially a C like representation。

And where we using environments。We're going to be using some data structure。So the question is。

 what kind of data structure do we want to use to represent environments。 And there's two。

Main approaches to this。So let's see an example。嗯。First of all， let's take a look at this。

This function definition， we have some nested functions。诶。3，2 nested functions。

3 function definitions。 And we're just adding the arguments together。 So the  zero width。

 the1 and the second index。 Let's suppose that we took this function and we applied it to 21。

Then we took the result of that。A closure and applied it to 17。

Click the result of that and applied it to four。So that you can imagine when it's executing。

 this means that we're going to have a couple of closures floating around。

 we're going to need some environments around that we're going to be using at runtime when we evaluate this expression。

Okay。Let's think about the。Environment that we're going to be using for this first application。

 right， it is。Has only a single index in scope。 sorry， a single variable in scope。

 So the environment。Is essentially going to be a consist of a single element。

We're going to represent environments using linked lists。Which means that when we think about the。

Environment that would use。for this application。When we have two variables in scope。

Our environment is going to  point to。This link list， right， The first element of the link list。

 the0 with index， is 17。The next element of the linked list is the one。Index in the environment， 21。

And in a similar way， when we construct an environment for the last function application。

We can construct a new environment just by。Putting a new element at the front of this linked list。

Okay， where the zeroF element is4， the next one is 17， the next one is 21。Right。

 so when we think about how to implement lists， fantastic。 Li list is。😊，An obvious solution。What is？

Well， let me ask， what would be an alternate way of implementing the list。So brush off you of CS50。

 maybe 51 knowledge。Okay， you have a。You Maxwell。I was going to see you could also do like a stacked。

Stack like instead if you're accessing bar 0 about is zero。Great， so。嗯。Let me， I're gonna say， yeah。

 we're gonna treat as an array， though， because when we think about a stack。

 we actually have a number of choices for how to implement a stack as well。

 You could use the link list to implement a stack in array。

 But I appreciate the idea that you're saying， you know， we have this。

 We're gonna push something on the top。 We're going to add something else。

 It's an alternate representation。😊，Would be using an array。So if we were using an array。

If we think about that first application。Would have an array representing a list with one element？

Right， so our pointer would be to an array with one element。When we have the。Sinened application。

We'd need an array with two elements。And similarly， for that third application。

 we' have an array with three elements。So。Do with some interesting things going on here。嗯。

With the linked list environments。When we created a new environment。

Kind of all we needed to do was create a new head node。

And then refer to the previous environment with the next link。In some ways。

 we got to reuse the existing environment。By contrast with this flat environment。

 with the array ray based environment。We typically can't do that sharing。

We're going to create a new array。For each environment。

So what are the advantages and disadvantages of these two approaches？William。

 like there's more copying。 you just mentioned Okay。

 so in the array method where there's more copying going on， we're creating new arrays。

 We're needing to copy elements from one array to another。 That's true。 So why would this might。

So there's got to be some like payoff。 this as an implementation strategy。

 did you ever if you use like a lot of。Great， so you've got better locality。

 so it's quite reasonable that within a function you're going be if you're accessing one local variable。

 you might be accessing sorry if you'ing one variable， you might be accessing another。

 So having those variables located close to each other in memory is likely to help performance。

 know it'll be in the cache when you need it。😊，Maxwell， you can access the plate the。

Last variable along with the linked list you're going to have to to of Ireland。Right。

 so with a linked list， we saved on the copying。 it was easy to create a new environment。

But traversing the environment might be expensive， right， We may need to follow these links。

 meaning both more memory accesses and possibly worse locality， getting back to Abe's point。 Thanks。

 these are all really great points。 Thanks， Maxwell， thanks Abe。嗯。Thanks William， for the first one。

Any others？黑色。We use less space。Which one uses less space？The flattery。That's interesting。

Don't actually know if that's the case or not。Let me think about that。

 The thing about the environment。These nesting environments， rather， is that you get reuse。

So imagine that you actually had。Let's say some deeply nested function。 within that。

 you declared two local functions that were converted into closures。

 They would actually share a lot of the environment。😊，Right， they would actually have。

A whole big part of the linked list could actually be sharing memory because remember in a functional programming language。

 typically， you know， in many languages， the variables are immutable。

 Once you've got a binding for them， that binding doesn't change。 And what that means is。You know。

You could actually end up with a tree of nest environments。

 by contrast with the arrays because you're copying each time。You might。

 even though maybe each individual environment uses less memory because it isn't value pointer。

 value pointer value pointer， the sharing might mean the total memory is less and to be honest with it。

 I don't actually know in practice。Whichhich tends to use less memory。If anyone has a thought。

 feel free to。Chairman Bden。Are there cases where you need multiple branches of the tree to sort of be live at the same time？

You could definitely write programs。Where you do， right， Imagine that you。

 you could write some nested functions， you have closures that escape that get used。

 may be stored in the heap and use sometime later in the program。 right。

 so you could definitely write a program that did it。 This is one of the interesting things。

 And this is to be honest with you， Part of what I really like about programming languages as an area of research is that you've got some beautiful theory。

😊，You've got some practical engineering needs going on。

 but a lot of things with like compilation or program analysis and things。

 it actually comes down to well， how do people actually empirically use programming languages？Right。

 and so this is in some ways。An empirical question， right。

 How often is it the case that you have sharing in the environment。

 How often is it the case that you have multiple branches of a nest environment being live at the same time。

 How much redundancy is there due to copying of flat environments。

 And because you can imagine writing programs that definitely are one end of an extreme scale。

 you know， work great for links。For linked lists work terribly for arrays and vice versa。

 And it really comes down to an empirical question about。

But which might be better for a particular situation or better in general as a heuristic to use for an entire language Max well。

会。I was thinking the same question about the same question and I feel like。It's。

I feel because in the same way that you can keep a function stack which has like a very linear progression of like these are the functions that are。

You should also be able to only ever have like one。

Line of variables that are currently active because like yeah。

 you could have like multiple functions inside another one。

 but once one end that branch no longer matters so you can just ignore that So in that regard there's not multiple like active branches。

Well remember you can have closures， so the closure is going to be a pair of a pointer to an environment。

And a code pointer， right to the function。And those closures we in a functional programming language。

 right those closures。Of values。And they could be passed around。

This is what I was meaning by putting to the heap， you know， stored in to。You know。

 a binary tree that you created somewhere。 live there for。

A whole lot of the execution of the program。 Maybe sometime later， somebody goes to that tree。

 pulls out their closure and invokes it。 right， So you're right。

 even though at least in a single threaded program， there's only ever one。One function。

 one piece of code that's actively executing at any time。嗯。These closures are kind of。

Almost like paused computations， that you could go back to later and you need the bindings for the variables。

 those environments to be correct and available。When you end up invoking that code？错。

Thanks for the questions and the discussion。嗯。Anything else at the moment about this？

This high level sketch。Yeah， Mari。It's like which one does Z count？That's a great question。

I don't actually know， honest do a lot of the compiler work I do。

 the research that I've done is actually in not in functional programming languages。😊。

So I don't have to top my head now it you actually have a。

I didn't hear the question you know which is used in practice and whys of of Andrewreop Pe？Zoe。

 something that I think they have a for people a few years ago where they analyzed。

 but I don't know the answer。That's great。 Mario， or if somebody wants to post this on the Ed discussion board。

 well we'll find a link to that paper and put it there and we can have a discussion。About it。

But it's a relatively recent paper a few years back， so active area of research and exploration。Yeah。

 I'm wondering whether the order of sting the variables in the linked this really matter。

 so suppose we are using the linked where we put like the four in a head in the handle of the linked。

 so if we if we tend to frequently use the four we might save more iterations during the lookup。

Then if we put the foreigner in the table。Yeah。呃。So that's a good point that when you have the Sed environments。

 the performance of it will really depend on which variables you're accessing。

And with the de Bruin indices where we're having the zeroF or the head of theus being the innermost one。

嗯。This probably comes down to an empirical question，But I think。

It is likely the case that you quite often access the innermost。Defined variable。All right。But again。

 it's an empirical question。I thought like。Which， which indices do you tend to？Exs and the frequency。

Thanks。Madie brought up the design question of multiple arguments， and I mentioned that we could。

 in fact， extend indices in a pretty straightforward way to allow multiple arguments。

So using a pair to indicate which。The lexico dip。Of the binding。

 and then a second element to indicate which variable。 So here we have the two functions。

 definitions， X， Y， Z and M， N。 here。 we're adding X。X is defined in the zeroeth1。Definition。

 so the outermost definition and the zero with index， which is， of course， the x。Z is the。

We go out to the1 definition，0，1， and then the 0。Wn。2。Index for the variable the Z。

 similarly with the in here。Ind X 0，1， the innermost binding。And the zeroth one。嗯。Ement in。

So what that might mean is for our nested environments。

 we might actually change it to be a linked list of arrays。RightWhere for each function definition。

 we have an array and the array is the variables。For H。嗯。

The are variables for that function definition， so conceptually M and N and then the enclosing one containing variables for X Y Z。

嗯。I will say that you can also have flat environments with multiple arguments。

 you just need to be maybe maintaining a map and to compute which index you need to access。

But let's walk through an example using this nested array based environments。

So here we have a function。Some serial nested functions， X， Y， Z， M， N， P， Q。

Adding imp Z inside here。 on there's an application X applied to。This function Q。Right。

 so let's think， first of all， about the A S T for this， right， and。嗯。Just indicating。

Some of the lexical depth here on the。With these for convenience， zero， F。

 the month and second with respect to this application。嗯。And so just providing names appropriate X。

 Y， Z and MP。So let's consider two of the closures that we're going to be seeing this one here。

 the closure for the function P and another one， the closure for the function Q。With argument name Q。

So if we think about the encoding for environments。This would be an appropriate environment for。

Bindings for X， Y and Z。There's no next pointer， since this is the outermost。Function。

For the function， M in。We'd represent an appropriate environment for that with this array。

 space for M and N。And then pointing to the enclosing environment。For the next function。

The defines P， the closure that we're interested in。嗯。Wed have the environment pointer。Sorry。

 let me rerase this。嗯。The closure for， the closure A。

 the closure for this function consists of a pair of the environment and the code。

The environment would simply point to this environment， the enclosing environment。

 defining M N and X， Y Z。So these are different。Tys， if you， this is a closure。

This is an environment。嗯。If we think about the setting up the environment for closure B。Down in here。

We're going to be extending this environment with a mapping for P。

And that's the environment we'd be using for our closure for B。

So the closure for B would have the environment pointer would point to this environment would have a code pointer to the appropriate code。

For B。Namely the M plus x。Okay。Now， if we look at the debrain indices for the variable uses。嗯。

What we'll see is。That the pair are essentially providing you with an address relative to the closure。

So how to access the variable。So for example。To access the element， the variable x。

correspondres down here to the right upper end of the application， the index is 10。

And you can think about that as follow one next pointer。 So here's the environment。

 We follow one next pointer， and then we look up index 0。 and that gives us x。

 the variable we were interested in。Now， by contrast， this， this useful， let's say M。

This also has index 1 and zero。But if we think about it as from the environment。

 follow one next pointer。And then get the zero width index that takes us to the position for variable M。

Okay， so that de Bruin index is kind of giving us。A relative address。

 directions for how to find the appropriate location。

 And run times we follow a next pointer in the index within the array。In a similar way。

 this use of the program variable Z here got converted into the De Bruin index 2 comma 2。

And relative to the environment for closure B， that says follow two next pointers， one。2。

 and then look up the index 2，0，1，2。That's Z exactly as intended。

So we can kind of see how we can set up data structures for the environments that allow these elegant encodings can allow for relatively efficient implementations。

 although we do have a number of implementation choices， even with multiple arguments。

 we could instead of having these nested environments have a flat environment with slightly smarter mapping of variables into array disease。

Any questions on this example。A few Walden。Yeah， confuse as to why we don't have closure A。2。

Like the next P block。Given that。Closure A has access the earliest so if you remember when we had a closure。

It was the enclosing environment， plus appointed to the code。

And the code is expecting a new argument P。 And if you remember the code for this。

 this function would end up taking its argument。Extending the environment appropriately。 So that is。

The code for this would take its environment pointer extend it， Ie construct this environment。

And that would be the environment used to execute。The body of the function definition。

 and to use and closures the closure for Q。So we don't need to allocate storage for P in this closure because P is the formal argument to the code。

We don't have an actual value for it yet。Does that make sense？So if it' that code had used P。

 like let's say， it was like P plus X。Over there， like how would PV index。嗯。

If the x here was replaced with p plus x。That would。呃22。That would be indexed with0。One，0， zero。

I believe it'd be Han。The这 the。Mm。You're right， it's being treated differently。Isn't it。Yeah。I great。

 these。X。Yeah， you're right。I think if we actually use our De index conversion algorithm。

This address is not quite right。Because it's occurring within the body here and it's referring to the 01。

Two， the second and closing。So I might have it off by one error。In this， in this code。嗯。

Let's take a step back and make sure we have the key underlying idea here。

 which is that we're able to use the brainian disease and a data structure from the environment that kind of allow us to navigate to the correct location。

 But you're right。Yeah， this index doesn't look right， does it？Thanks。

There was also a question from Maddie in their name。That was it。 Thank you， Habe。

 I was just wondering about so the clerk here this local variables Thursday。

ization to be made there that if you don't use the seven variables okay I'm just going point back absolutelyolutely so you can definitely get more complicated with the conversion and we talked about this idea that we only really need to allocate。

Put a variable into an environment if it ends up escaping。So you could even。诶。

So you can imagine doing something like even if I use P here， even if I say it X plus P。

That I would be careful with my Dein index conversion。And treat it as a local variable。

 not actually put it in the environment。And so。呃。You know。

 and the fact that P is not actually used at all here means that， you know， with a。

With a more intelligent approach to constructing these environments and reasoning about it。

 we wouldn't need an environment to store P。Maybe we don't even need to allocate this at all。 We。

 the environment could point directly to here。 We need， of course。

 to be careful with the dein indices to make sure that we're referring to the correct thing。

 But really the goal of making sure that we're。Putting as little stuff as possible into the environment。

Makes a lot of sense。So that we avoid runtime overhead。

 so we avoid following pointers so that we can perform more optimizations on local variables and we'll see later on in the course。

That we're going to be able to reason much more powerfully about local variables than about values in the heatap。

And so the more things we can keep local， the better。

I will look into this and see if I can fix this example and put a new version that the slides up online。

Some time。Thanks， any more questions。Okay， so that is actually all that I have to say about compiling functions。

 I will say。We're not going to be doing that in one of the homeworks。

 but if you're excited about this you could absolutely figure out how to extend a version of the Oat programming language。

So with some simple functions and think about how you compile it as a。

Purely that have fun additional exercise。嗯。As I mentioned on Monday。

 we're going to start a new topic looking at type checking。

And as we dig into type checking some of those last few pages of the Oat language specification will make more sense in Home 5 you'll actually be implementing a type system for it as well as some additional language features。

 we'll be giving you a new type system for the next version of Ote which is a little more complicated than the one presented for O version  one。

Okay， thanks very much everyone， good luck with finishing up homework three。

 working on homework four， working on embedded embedded ethics。😊，I will see you all on Monday。ま。し。ます。



![](img/71163bc805ce2f473979896db9aba9d2_3.png)

で like。to sixty。系听边个四。It waiting for the the。你 is okay I guess because自己心呢种。あのいです。This is the deal。

Like it's not look。So人 just one of up。即系咗你系。選日なでも。Thats the journalist。是 done你是说以外快。日方す。Yeah。

我 still that。め。Yeah完。そ。直食比接他时间系赛。That's good， that's good。I没。Thanks。Yes。No。

 we've finished it we didn' will be。So when we constructed constructed。Here's closure A。

 so when we invoke that we'll have this will be in the environment and then from here this tells us the address。

So from here， we follow。One next point。A one。Twoers。And then the zero elements， that should be x。

 yes。And then in that environment we created， that's the environment we use for closure。

vo that will we have a mining for Q。And then this is telling us to access and we go。One， two，0。

1 and Phizzy， we go one， two， three。At0 one。So， this is flow。Yeah， I think any components for。

Three next point great。So this is great。😊，又听睇够。sh， no， thanks。Sitting with me moment。Did this。

And export them。Great Frank， thank you very much。那新问题。Do cannot access your slides。

They're almost the same as last year， which should be accessible。Yeah，2019。我意思等睇诶。But want to get。

このクリックね。诶跳。So， if you。你处理处理。Should be accessible。嗯。So this， I think should be。So from 2021 should be。

記録。Okay， so that should work。 I can also try just adding you。I don't know if it's still come up。

Find out so15 three。Do you use。Do you use canvas。They we like turn had。It's not sitting。

 It's manage people。 It's people， but they dont look。嗯。W people。系い诶。Okay， now， what is your。

You still me even have I go， but that one I don't know So it's not I。 is it my is my idea you think。

Yeah， wow， so is6 yes， I think this might actually work to get Yeah， let me， I think so。 so60282，8。

65，9，0。Yeah， so it will be a kissed。And so when you log， and I should take you to a canvas。あでパす。そ。

So here's another NAto window。So if you go here。Look at the schedule and try and download。

It should take you to。No， you might to you need to click login。

 but then you can just log in with your。You have this right， the have a key。呃有。嗯。

So what you might need to do then is go to。a呢啲U。啊。And claim you'll have a key so this is kind of the but then how do I get the。

So if you click claim you have a key。我啲人谂啊。Yeah， so。I think you actually have an HUID。

 so I think this would probably work so that number that you just used。

Would probably work so you can go through this and I say have a try with it because if this I think this might we just might be able to give you access to the building and tour room instead of setting up at appointment they have really。

For some reason crack down on appointments and like only collaborators like you know。

 you can't just have a as a courtesy guest as like this one then we're trying so we're going to see if that perfect。

But hopefully it looks like because this one is see with the library。Yeah， I know。

 but it looks very similar。 It's got the。You know， so it looks like it might have the same。

There's things like you can put crimson cash on it， you know to eat it。

Now you need to swa so it should have the chip andt。

 the RFID that let's use should so we're hoping that just from the HUID we'll just be able to give you access to an office。

あ。Because the office used this one to enter that's the thing because otherwise you say I don't come working during the weekend but instead to open the office so I hope it's just that idea。

あちざす。So as you can see like it， so when you claim the Harvard key， I would suggest， first of all。

 try。Just new to have a queue with an HUAD if that doesn't work， then try the。

Yeah so that's interestingly so why do people do not use this point because I remember a long time ago when I was looking at this。

 they didn't likely because every bit reduction， you had to change the I things I mean what's。

It depends on the abstraction you want， right？You know。

 it's annoying from an interprettuver to because you know we a substitution based sort of things。

You end up changing the industry。 But with the data structure， it's great， right because Yeah。

 and the localness is nice。 I know I don't follow it too closely， but。嗯You know the。

Program verification and reasoning。They ended up going with this know Penn had like a big investigation multi year project on like what's a good representation to an and they went with something called locally nameless was dein indices except for free variables free variables had but if there were bound variables then it was dein indices and I think it was the local reasoning the fact that you could with de indices。

 you could reason locally you could take that code relocate it somewhere else and you didn't need to change anything about the proof the reasoning how you referring variables with formal reasoning dealing with names as a real pain the indices end up being nice's because naming you have to be careful instead because almost economical representation。

Of a term， because even if I change the name， the internal presentation is the same。

 but I always use pointers。Okay， then pointers， okay， is that the windowss。

Its the same the same right the lambda and then you form to the lambda node so then you see that if you change without renaming internal code the internal is the same you so right because yeah you don't you change the name but the binder the back pointer So when you when you straight at closures to the intermediate representation that was the representation no no no no we use yeah no the we use value because we do it at the high level So the main point that there was that we want to type preserve the type right instead of going down to。

Payers and that， and then all the equation have to hold。

And if you translate it using pairs like this， even the data action is no sounding longer。

 it's not equal， so if M is equal to n after you do closure conversion。

Those suit term they are not provable if longer。 So then， and that's why they do closure conversion。

Indeed translation。In the first they do all at least or Ascoalt orca， I don't know。

 but Ascot does all the optimization in code and then it goes down to see light on the G machine。

They do closure conversion。During those。Low level transformation。

Because all the optimization in coal， they prove the meatball right。

 So they wanting to have this powerful equational reason exactly exactly So then we just added we just add the type of。

Contract and we use。but to shame you， just because we wanted do。

We better with the evaluations strategy。And then quit works Yeah， but we use names still。And。

So you know the next year。Most probably， we will have O P S S in Boston。 Oh， yeah。

 Mattam That's great。 Yeah， yeah， yeah。So， that the。诶。Ofully been sitting my。Withて。这个什么。Sorry。

 just describing this。Sorry， just grabbing this。

![](img/71163bc805ce2f473979896db9aba9d2_5.png)

你把你讲た呢。