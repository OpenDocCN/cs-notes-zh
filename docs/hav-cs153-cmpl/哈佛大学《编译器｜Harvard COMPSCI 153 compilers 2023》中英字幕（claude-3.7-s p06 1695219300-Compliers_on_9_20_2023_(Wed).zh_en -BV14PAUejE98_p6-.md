# 哈佛大学《编译器｜Harvard COMPSCI 153 compilers 2023》中英字幕（claude-3.7-s p06 1695219300-Compliers_on_9_20_2023_(Wed).zh_en -BV14PAUejE98_p6-

Hands up if you strongly prefer classroom。上开。Just let get like。All right， I might end upload。

At least to me personally field。Being able to。Get to know you。know but names with faces。说完了。

All right。Thank you for the information about。About that。Let's get back to the content of。

 of class today。Before we jump into what we're covering today。We are announcements， as always。

 homework 2 is out， as you know。 it is due a week from today， Wednesday， September 27。

How are the study groups going？Almost everyone in the class is in a study group and got matched up。

 hands up if you're a study group。Put your hand down。 if people have exchanged emails。

So everyone with a hands up， there's been no email communication for your study group。Alright。

 I'm going ask the people who have their hands up to take that scary first step of actually replying to the email and making contact with members of your study group and try and find a time to meet this coming week。

 this coming week。嗯。We will be forming new study groups for homework 3。

Email me if you want to opt out if you did not fill in the study form yet。And one， please fill it。

 regardless。 And if you opt into study groups， I'll put you in a homework  three study group。嗯。

A reminder about academic integrity。啊。Just a friendly reminder to disable Copit or any other generative AI in your IDE。

So the reason for this is， as you might remember， the goal of the academic integrity policy is to treat geneative AI the same as you would appear。

High level discussions are okay。 So using words， not code is good。Low level things。

 How do I use this API， What does the syntax error mean also good。

But the middle thing about sharing large pieces of code， accepting pieces of code is not okay。

Or has to be treated with the care。 And so enabling code pilot it in your ID DE and allowing it to suggest large pieces of code based on comments and based on the context of the rest of the code is too easy to cross the line and to see the suggested code things。

 you can in you know， visualual studio code， disable coil on a project by project basis。

 you can just disable it for your C S 1，53 projects and still use it for your startup or whatever else it is that you're that you're writing code for。

嗯，So。You can， of course， use general AI if you're wanting to do it for code。

 kind of treating it outside of the context of the project that you're working on。

 So asking it specifically for。How do I use the Ocal set module， for example。

 might be a way where you can。Short circuit， some of the the pain of trying to get the right syntax without running risk of is suggesting how to solve the problem set for you。

Any questions on that about the academic integrity or about how to treat geneative AI appropriately。

I'll say it applies for not just for the code， but also for the test cases that you're submitting。

So don't use it to produce the test cases that you end up submitting in your homeworks or or posting to Web。

 And， of course， the reason for that is the value of both the test cases and writing the code is to。

Put in those mental cycles about thinking through the problems。

 thinking about what are we trying to achieve， What is the correctness thing。

 Gene AI is incredibly valuable。 I hope you use it a lot， but just not within。

Certain parts of this class。同。Okay， we're going to be releasing homework 3 a week from today。

 So Wednesday September 27。And what we're going to be doing today is continuing to talk about IRs and intermediate representations。

And really， the goal of today is that we're going to motivate。A lot of the design of L O V M。

So that on Monday， we'll actually look at L VM， But a lot of the concepts in there are going be clear。

 or at least familiar due to today's lecture， as we kind of talk through a sequence of I Rs to lead us to。

L O VM's design choices。Now， when I say a sequence of ARs。

 I don't mean a sequence within the compiler pipeline going from high level source through a sequence into low level languages。

 Instead， I in a sequence where we're going to start off with the really simple intermediate representations that's suitable for really simple source languages。

 So just starting off with just expressions。But then going through and adding more and more features to the source language and seeing how we want to extend。

The intermediate representation language to accommodate that and thus motivate the design of the intermediate representation。

Okay， so。One fundamental issue。In intermediate representations。

Is that we ultimately need to get to flat representations of computations。That is。

 we can't have nested expressions at the assembly level。

 which means that at some level of our intermediate representation。

 we're going have to get rid of nested expressions。嗯。So， the key idea。

That we're going to be doing for this。Is to provide names on the intermediate values。Okay， so in。

I guess in Monday's class， the intermediate representation we were using， was using a stack。

 So those intermediate values would end up pushing onto a stack and popping off as we needed。

But the approach we're going take here， though， is to provide names。On those intermediate values。

Moreover。We're going to be making the sequence。The order of evaluation， explicit。

And the sequence of operations that we're doing。Whereas at a high level language。嗯。

The order of operations is often implicit。Based on， let's say， left or right evaluation。

Or sometimes it's actually left unspecified。So indeed， in the C programming language。

There isn't actually in order， a specific order that you should evaluate sub expressionions and opera ends of binary operations。

 There tends to be some。Common practices and compiler implementation。

 but the language spec allows a lot more flexibility。O。

So the idea is that given this nested expression represented as an A T here。

 we're going be translating it into this form， something like this。



![](img/41a464e9f1eb68439d7584445f5a464e_1.png)

Where we have both。

![](img/41a464e9f1eb68439d7584445f5a464e_3.png)

Names for the intermediate values。 So T 0， T 1， T 2， a naming。The little individual sub expressions。

And moreover， we've got a explicit order that we're evaluating the sub expressions in。

 because these lead expressions are， in fact。Sequential telling us do the let temp 0 equals。Addd。

 so we're doing the addition first。Of add 1 and R X  X before we move onwards。

One thing to note here is that these temporary variables。There， you know。

 a phrase this an O camel code， right， to really underscore these temporary variables are not modified。

Once they're assigned to。Okay， so they're providing us with names of intermediate values。

But they're different from the sort of mutable variables that would use in in a high level programming language where we might be updating the contents of a variable。

Yeah， what is alone。I forget。呃，我知。Simple lead language。 Thank you。slide。

I've only had one coffee today。 thats my excuse。But， you know， you have the slide in front of you。um。

Alright。Let's let's take a look at code。Okay， so we're going to be going through a sequence of intermediate representations。

 These files are in canvas。 if you want to take a look at them sometime。嗯。

So we're going be defining the source language。Will be defining the intermediate representation。

And then we'll look at compiling from the source to the intermediate representation。

 We're gonna do that for a sequence of about 4 or 5。Languages。So let's see。

 the source language we're dealing with is these simple arithmetic expressions， variables， constants。

 addition multiplication， negation。 Great， here's a example。Of an A S T representing this expression。

The intermediate representation that we're going to use。嗯。Let me scroll down a little。

We're going to have our instructions。 We're going to use the constructor let。

To be reminiscent of an ocal LED expression， just like the little sample code I showed you。

So it's gonna take in。Thiss tuple U I D， unique identifier。 This is going to be the name。

 if you will， of the temporary value。The we are assigning。Okay。

 I'll show you the definition of UAD in just a moment。嗯。We're gonna take a binary operation。

 either add or multiply and to opera ends。 Okay， the opera ends are gonna either be。A constant。

constantstant 64 B， a variable。Or it's going to be。

One of these I Ds that is referring to one of the temporary results we computed previously。

Right and defined using one of the late instructions。UI Ds， for the moment。

 they're just gonna be integers。 So our' type U I D isntt。

 And we're gonna have this handy little function to give us a fresh。A unique identifier。

 And so this is a side effecting thing。 We just keep a counter。Of accounted account， how many。

Unique I Ds were handed out and grab the next one。So a program then is simply a list of instructions。

As well as。The upper end， which contains the result of the whole expression。Right right。

 so this will typically be。A U I。The temporary variable that is the contains the result of the top level expression。

Any questions about this representation。Could you explain again what。

Oh so this program here is simply a record。So a program has two fields on it。 One field is called。

Instructions， I N S， N S。And that's just a list of instructions of these let。Constructs。

The second name of the field， the name of the second field is rat， and it's an opera end。And it is。

 if you will， the return value of the program。It's the upper end that contains the the final result of the expression。

Wch as I mentioned， will typically just be a UA D。Of the， the temporary variable that we。

That holds the the final value。OK。We got some code for pretty printing。

 I'll skip over that for the moment，cause I'll just be showing you an example。

 And in this code and in the others， just to try and clarify the meaning of stuff。

 I'll be having this M L meaningstruct that shows。呃。

Gives a hint for the intended meaning of the intermediate representation。

 although I haven't gone as far as to actually provide you with an executable。

With an interpreter for the intermediate representation。Okay， let's quickly say， whoops。

 that was the wrong one。呃。So an example， we have。An AST， representing source level expression。嗯。

Let's think about compiling。The source level expression into our intermediate representation。

Just gonna hide away the terminal。 Go back to the code。

The result of compiling an expression is simply going be a list of the instructions。

 There's going to be a program， a list of instructions to compute it and the return opera。

 the opera that contains the result。It's pretty straightforward。We're gonna have this。

Compile expression function。Takes an expression E that it's going to compile。

And it returns a list of instructions。To compute E。

And an upper end that contains the result or refers to the result of computing。So。For variables。

 nice and straightforward， No instructions needed。 It's simply the opera end is the variable itself。

 same with constants。For add multiply in the gate， we're going to make use of this utility function。

 compiled binary operation， compiled B。嗯。Compile BO takes the binary operation we're going to use。

And the two and two sub expressionions， you want to E2。

It recursively calls compile expression for E1 and E2。So， instructions，1。

Is the instructions to compute E1。And the result of E1 is in the upper end rate  one。Similarly。

 for expression E2。So to compute E1 binary operation E2。

We're going to return a sequence of instructions。It's going to be the instructions to compute E1。

Followed by the instructions to compute E2。Followed by a new instruction。Where we。

Compute the binary operation for the result of E1 and E to read 1 and read 2 respectively。

And we created a new， unique I D， a new U I D in order to put the result in a new temporary。

 that's right。Okay， so here's the sequence of instructions。Compute E1， then E2。

 then the result of E1。Boary operation， E 2。And the result of it is stored in red。In the unique I D。

Awesome。That's it。It's pretty much it。 So to compile a program， we， to compile an expression E。

 we call compile X to get the instructions and the return result。

 And that is the record that we have。 the list of instructions and the resulting opera。

So let's go back to the terminal to U top and actually call compile。What's I instead of IR。

There it is。 It's not that easy to read。 So we're gonna print。But， instead。嗯。

So a pretty printed program。And here it is。Right， so。

Showing it is pretty similar to the Ochemo notation。Let temp 0 equal。

Addition of1 and the variable X4 and so on。 And then the final result in here is stored in T 3。

Any questions。About this initial intermediate representation。And the compilation。O。

So let's have a more complicated source language。嗯。So， in this language。

We're gonna have expressions still， but we're also gonna have commands。

So we have three kinds of commands skip， which just says nothing。Assignment。Of X equals E。

 So think about this as we are going to evaluate the expression E。

And store the result into the variable X。And then we can have a sequence of commands。Right。

 do command C 1， followed by command C2。Okay， so slightly more complicated source language。

 It's got the expression language as a， as a。嗯。Sub language here。 But now we can actually。

Wriite to variables， in addition to reading them。Here's an example command。

 an assignment followed assignment of X1 into of this example expression。Followed by a skip。

 followed by an assignment of x1 times x1 into x2。分走。Com慢。Becauseuse eventually。

 we'll get to the point where some of the commands we have are things like if expressions or wh expressions and the sub command that we want there might itself be a sequence。

So we want a sequence of commands to itself be a command。So it can be nested appropriately。

Thanks for the question。What is the point this。 does absolutely It does absolutely nothing。

 It's not that useful here in this language。 But again。

 we're gonna be adding in more complicated construct soon。 So imagine that you have an if statement。

 an if， yeah， an if command。That doesn't have an else branch。Right。

 you could either have two flavors of if commands， one with a then branch and an mouse branch and another another one that only has the then branch。

But part of the idea of an intermediate representation is that we have a small interface。

 We have fewer constructs。 So one of the simple ways of doing this is to have always have both a true and a false branch。

And maybe the false branch contains skip。Like， no of。

And I'll also point out that most high level languages have something like S。Right，And C。

 it's a semi colonlon by itself。 in Python， it's pass。嗯。

Can't think of any others off the top of my head。 But most languages have something like that。A。

 also also had a question。And this is probably the answer is probably related to the last one。

 but just on its own， this language isn't really。啊。

Like if you're just interested in getting an answer from like a single variable。

 this isn't really more expressive from the previous one， is it？我的是呃。

Sos what we mean by more expressive。 Can we compute things here that we couldn't compute using just expressions。

No。But it's more expressive in the sense that it has language features。

 It actually has mutable memory， memory that we can write to with that we can update， so。

Expressions were kind of essentially pure， right， They didn't actually modify anything in the state of the machine。

Whereas now that we can assign into a variable。It's， it's qualitatively different。I agree that it's。

 this isn't very useful as a programming language。But it's starting to add in the things that are getting us to real interesting。

 imperative languages。只在。Suffly kick the can down the road。 We'll get there and。In a couple of。

One more language。Yeah。Any other questions at the moment about the source language。对。Okay。

So for our intermediate representation。We're going need not just a way to compute the expressions and store those temporary variables。

 those temporary results。 But we're also going to be able to need to represent。呃。

Loading and storing of variables。 maybe we already had load。 yes。

 but definitely we can store variables now。Okay， so instructions， in addition to including let。

We're also going to include store。Right， so take care of the assignment。

To be symmetric and a bit closer to real intermediate representations。

 we're also gonna have a separate instruction for load。Right。

 so load is gonna read the contents of a variable。 store in a temporary。And a temporary variable。

And now， our opera ends are only going allow constants and temporaries。Right。

 so we've removed variables as， as one of the possible opera。 Instead。

 you have to do an explicit load。To get the result。Otherwise， things are pretty similar。

 We still have our handy utility function to get a fresh， unique identifier。

Add to multiply binary operations。呃。What's interesting now is for our purposes。

 the program is just going to be the list of instructions。

We're going to say that the point of a program is， if you will， the memory that results at the end。

Right， maybe the result of the computation could be put in some well known variable， for example。

So our program is a little simpler。We have pretty printing again。

 I'll skip over that for your reference， some。Sketches of what the meaning of things are loading is。

 you know， dereferencing a memory location， Storing is assigning into it。Compilation。So。

 compiling of expressions is。Pretty much the same， right to compileil an expression。

 we return a list of instructions to compute it and the upper end where the result of that expression is。

嗯。Interestingly。When we are compiling a variable。We are going to explicitly put in the load。

And store the result in some new temporary。But otherwise。

 things are pretty much the same for expressions。So now how do we go about compiling commands。

Oh it's also pretty straightforward。 right， Sk is just an empty list。Of commands。

An assignment X as a sign D。 We， first of all， compute the expression E。

So get these sequence of instructions for compiling。 get the sequence of instructions。

 That's the result of compiling E。And。To that list of instructions， we append。A store instruction。

Sttoring the result of the of the expression。The temporary ript one。

Will the opera and run rather into the variable X。Sequences nice and straightforward。 C 1。

 followed by C 2， simply compile C1， compile C 2， concatenate the lists of the list of instructions。

And so that's all compiling of programmers。Right， just compile the command。

Any questions about the compilation。This is a question why there sometimes superb brackets after like IR。

I can hire store their blanket。 Oh this is a list。It's a list with a singleton。

Elements so that we could。Nice and so that we could use the。Concatenation。嗯。

What's the iron dot like before it supposed be。This means。Within here。

 this is going be the I dot store。 Yeah， let's try。嗯。All right。Here's our example command。嗯。

And let's compile it。And pretty printed。Do we actually see what they see the source code of that example command。

Do you want to see what the source code was。But do you remember it。哎。Who cares about the details。

Okay， so what we have here is we can see it going through and computing the expression。

 doing a load of Expr into a temp。You know， adding one to that value， putting in T4 and so on。

You'll note that in our instructions， a store instruction didn't need a U I D。

 There's no result to store for the UI D。 We're pretty printing that by using the。

 you know Ocal let underscore syntax to， you know， clarify that。 put it in the same syntax form。

 Cla that it's in a sequence， but there's no result to use。And same with this last store。

And in our project printing will always， the result of the program will always be unit。 You know。

 there's no value to to return。 It's going to be the， as I mentioned。

 essentially the effects to memory and now the point of a program。Okay。Ready for the next one。Okay。

 let's take a look at。Adding some more interesting control flow。That was not what it was。Okay。

So we have expressions， but now we have more interesting commands。 Okay。

 in addition to skip and assignments and sequence， we're now gonna have conditionals， if not 0。

And while loops， while not 0。 So intuitively， if not 0， takes test condition expression。

If that expression is non zero， it's gonna execute the first command。 Otherwise。

 it's gonna to execute the second command。Intuitively。

 the smants for well not 0 takes a guard expression。 It's going to evaluate that expression。

 If the expression is non0。It's going to execute the body of the world loop， the command。

Then it's gonna go back and re execute the while loop。 So that is， it's gonna reevaluate the guard。

 If it's non0， would to keep going。 when the guard becomes 0， it'll exit the loop。

Itll finish executing the w statement。So here's a sample program。 X 2 equals x 1 plus x 2。

And then testing the value of X2 and branching appropriately。 X 1 equals x 1 plus 1。

 or x 2 equals x 1。Then。At the end of this， if command， theres。Another assignment。

X2 equals x2 times x 1。Here's an AST representation of that program。factorial。

Ex examplele of using while loop。And an AST representation。Okay， so our's immediate representation。

Clearly， the path about evaluating expressions are good。Our sequence of instructions that included。

Scarpe assignments， load stores。 That's all good。But now we have these control flow constructs。

 We have these if commands。 We have these well loops。So where we previously had a simple list。

Of instruction。We're going need something more sophisticated。



![](img/41a464e9f1eb68439d7584445f5a464e_5.png)

So， let me。

![](img/41a464e9f1eb68439d7584445f5a464e_7.png)

Go back to my slides。We're going to talk about control flow graphs。This is。

We're gonna be representing in our intermediate language。

 We're gonna be representing control flow graphs as a way of capturing the control flow of a program。

 So those if commands， those while loops。对。So before I end up showing how we represent the intermediate representation。

 we need to wrap our head around what is a control flow graph。 How shall we think about it。

It's going to be， as the name might suggest， a graphical， a graph， nodes and edges。

 representation of a program。Edges in the graph are going to represent control flow。

 and nodes are going to represent statements。嗯。So， for example， if we have。



![](img/41a464e9f1eb68439d7584445f5a464e_9.png)

This program， Okay， starts off x is a s 0， Y is a assign 0。

 Then we have a whale loop with a pretty large body at the end of the while loop。

 we're printing out X。

![](img/41a464e9f1eb68439d7584445f5a464e_11.png)

可以。Let's take a look at a control flow graph。That represents this program。So， here we have。

Nodes and edges。 The nodes in this graph are commands。And edges represent。Execution。

Of a command moving to another command， control flow。So our entry point。

 the first node of our graph is x equals 0。 It's the first command in the original program。



![](img/41a464e9f1eb68439d7584445f5a464e_13.png)

There's only one successor。 There's only one outgoing edge from that。

 And that takes us to a node y as a sign 0。Which is the second command。



![](img/41a464e9f1eb68439d7584445f5a464e_15.png)

This next part of the graph is interesting。 This is the representation of the wall loop。Now。

 you recall from the semantics of the wild loop。 We're going to test the guard expression。

 If it's nonze， we'll execute the body。And we'll keep on doing that until the guard expression evaluate to 0。

 whereupon we exit the loop。

![](img/41a464e9f1eb68439d7584445f5a464e_17.png)

So let's take a look at the graph。Right， this node here in greater than 0。 That's the guard。 Sorry。

 the， yeah， the loop guard that we're evaluating。

![](img/41a464e9f1eb68439d7584445f5a464e_19.png)

Now， this has two outgoing edges。One fool in that guard is true or non zero。

One for that God is false。Let's take a look at the edge where it's true。



![](img/41a464e9f1eb68439d7584445f5a464e_21.png)

We're taking this control flow edge to a node that represents the start of the body of the wall loop。



![](img/41a464e9f1eb68439d7584445f5a464e_23.png)

Okay， so if the guard is non zero， it's true。 we're gonna start executing the body of the world loop。

The body of the wall loop is an if statement。Okay， the test for the astatement。In modo 2 equals 0。

Is this node right here。

![](img/41a464e9f1eb68439d7584445f5a464e_25.png)

And again， it has two。Successor edges， two outgoing edges，1 for when that expression is true。

 non zero， one for when it's false or 0。If the expression is true， we execute these two statements。

X equals x times n。

![](img/41a464e9f1eb68439d7584445f5a464e_27.png)

Y equals y plus 1。And those， of course， are the commands and the true branch。Similarly。

 if the God is false， we execute commands in the false branch。



![](img/41a464e9f1eb68439d7584445f5a464e_29.png)

Regardless of which branch we took。We eventually get to this node。 n equals n -1。

And that is the command immediately after the Fstatement， but still in the body of the wild loop。



![](img/41a464e9f1eb68439d7584445f5a464e_31.png)

That's the end of the body of the wild loop。And after that exp after that command has been executed。

Intuitively， we know that we go back up and we re execute the while expression， the while command。

 And we can see that in the control flow graph， right， We have this edge。

 meaningan after we exclude n equals n -1。

![](img/41a464e9f1eb68439d7584445f5a464e_33.png)

We follow this edge， back up to。

![](img/41a464e9f1eb68439d7584445f5a464e_35.png)

Evaluating the guard of the wild loopop。That means we're going continue doing that。

 doing the loop until that guard in greater than 0， evaluates to 0 to false。

Whereupon we'll take this control flow edge。

![](img/41a464e9f1eb68439d7584445f5a464e_37.png)

Down to print X。

![](img/41a464e9f1eb68439d7584445f5a464e_39.png)

The salmon that immediately follows the wild loop。And that's the last statement in this program。O。

There was a lot of detail。For what is maybe a simple graph。

But what's really important is that we have a really good intuitive understanding of how this control flow graph represents the program。

Because we're going to be taking this idea of a control flow graph and。

Manipulating it in various ways。 So we want to make sure we're comfortable with this notion。

Any questions at the moment about control flow graphs。Okay。The first thing that we're going to do。

As we change or extend our idea of control flow graph。Is it our nodes of the graph。

Instead of as being S， single commands or expressions。

What we're gonna do is combine sequences of commands into what are called basic blocks。So。

A basic block is gonna be a sequence of statements with the following properties。

You only have a start executing that sequence of statements by starting at the very top。

That is you enter the basic block only at the beginning of the basic block。

You execute the entirety of the basic block。And the last instruction of the basic block。

Either unconditionally goes to another basic block。Or it might be a branch。Say figuring out which。

Basic block for an F statement to go into or going to the body of a well， wh loop。

Or it's going to be the return of a function。Okay， so we would like a return。

 a return command where we done with a function。 we're returning to the caller。

So using these basic blocks is going to make our life easier as compiler writers。

 both when we represent programs， we when we analyze programs。

So let's see that same control flow graph。But now， using basic blocks。

So our initial note of the program is the sequence。 x equals 0， y equals 0。



![](img/41a464e9f1eb68439d7584445f5a464e_41.png)

And then the last thing the basic block does is unconditionally jump。To n greater than 0。



![](img/41a464e9f1eb68439d7584445f5a464e_43.png)

That in greater than 0。 That's a basic block that just has the one expression in it。Right。

 so basic blocks can consist of just a single instruction or expression。嗯。



![](img/41a464e9f1eb68439d7584445f5a464e_45.png)

And the end of the basic block is a conditional jump based on whether in greater than 0 is true or false。

Right， if it's true， here's the F statement， the。True and the false branches are these basic blocks consisting of a sequence of two assignments each。



![](img/41a464e9f1eb68439d7584445f5a464e_47.png)

可以。In general， we're going to want our basic blocks to be as large as possible。Right。

 we're gonna want our basic blocks to be the maximal sequence of instructions that we can have such that you always enter at the top。

Exece the entirety of the basic block。 and the last instruction jumps to another basic block。

Any questions about。This concept。O。The last tweak we're gonna make with control flow graphs。

Is that we're gonna give each basic block a unique label。K， a unique name。

And then we're gonna be really explicit about jumping to the next block。

 We're actually going to have an instruction。At the end of the basic block， that makes explicit。

 What is the next basic block we're going to。So that's either going to be a rat for returning from the function。

Or it's going to be an unconditional jump to a basic block。 So this says branch to a label。



![](img/41a464e9f1eb68439d7584445f5a464e_49.png)

For example， up here。L 0， the entry block。 at the end of the basic block。

 we're branching to the basic block labeled L 1。That is we're going to this basic block right here。



![](img/41a464e9f1eb68439d7584445f5a464e_51.png)

Or it's a conditional branch。

![](img/41a464e9f1eb68439d7584445f5a464e_53.png)

The conditional branch takes a U I D， a temporary。

![](img/41a464e9f1eb68439d7584445f5a464e_55.png)

And gives us two labels， the blocks to go to if the condition is satisfied and if the condition isn't satisfied。

And so what that means here in this version of the basic blocks。

We're actually explicitly showing the temporaries， these lead expressions。 So here we see that。



![](img/41a464e9f1eb68439d7584445f5a464e_57.png)

I say I have an error in my graph。 I'm sorry。

![](img/41a464e9f1eb68439d7584445f5a464e_59.png)

呃。Let me fix this quick。确认了。So you see here for the guard of the of the while loop。

 we're computing n greater than 0， the expression， the comparison。

 putting the result into the temporary T1。 And then our last instruction is this conditional branch saying if T 1 is nonze。

 go to L2， other ways go to L 3。

![](img/41a464e9f1eb68439d7584445f5a464e_61.png)

![](img/41a464e9f1eb68439d7584445f5a464e_62.png)

对二。あ先生。不要防身。Call the function。That function式。This。So we aren't quite yet at functions。

 So It always said we have R， which is returning from a function。 but we don't at the moment。

 have function andvocation。Right now we just think of bread as likey。Good way。 think for it。

 R is like ending the program， given that we。Only have our one function slash program。 Yeah， thanks。

Thanks for the question。 We'll get to functions。 Don't worry。Any questions at the moment about this。

O。Yeah， Tu。嗯。Does our intermediate representation change depending on how our source language treats functions。

 Is that the question or you mean like whether they are C like functions or or camel like functions。

Yeah。嗯。There's going to be a。Sequence of intermediate representations。

Some of which are closer to the higher level language， some of which are close to assembly code。

L O VM is。呃。Let's call it three4 of the way down sort of thing。 It's， it has C like functions。

And so it turns out that to go from a functional programming language like Ocal。Into an L O V M。

 like representation。We'll end up going through a couple of intermediate representations to。

What's called defalize the program。To， to take away the functions as first class values and convert them to something else。

So you'll be doing that in one of the homeworks， I think。Maybe we're not this year。

You might be doing it in one of the homework。But what I'm gonna be presenting with L of VM doesn't really treat functions as first class values in a。

 in a straightforward way。 You kind of have to compile down to that and you'd have intermediate representations to make that easier as you go along。

 We'll definitely be talking about it in lecture to get an idea of how you do that。呃， yeah。Okay。

 thanks for the question。 Any other questions about this representation。Of control flow graphs。

 labeled basic blocks。So what you might note is that in this representation。

 where each basic block has a label。And the last instruction of each basic block is telling us where to go。

That is a branch or a conditional branch to a particular label。We kind of。

 those arrows are kind of redundant now。Right， I could take those arrows away and you could figure out what the relationship between the basic blocks is meant to be。

Alright， becauseuse you could just look at the labels， look at the branches。

 the conditional branches and so on。So this essentially leads us to our representation of control flow graphs in our intermediate representation。

We're going be having labeled basic blocks。And the end of a basic block will tell us， you know。

 which basic block we're going to jump to or conditionally jump to。

But we're just going list these labeled basic blocks in a sequence。Right。

 there's no need to actually have them。Represented as a graph with actual arrows connecting them。

 right， The arrows don't provide any additional information at this point。

So let's go back to our code， our intermediate representation。

And see how we're going to represent these labeled basic blocks。Okay， first of all， U I Ds。

Let's use strings now。 So we went from integers to strings。呃。Labels are gonna be strings as well。

 where。Goonna make a unique I D by passing in a string and sticking on a number at the end of it just to make sure it's unique。

Guaranteed unique。嗯。Our expression language is。The same。Unique identifier it。 So the temporaries。

 the constants add and multiply。We're gonna have some comparison operations now。

 So quality and less than。 you can imagine adding more here in a straightforward way。

Our instructions are going to be。Pretty similar to what we had previously。Computing a temporary。

 a let expression， a load。A store。We， we are also adding in a comparison operation。K。

 which simply compares two opera ends， puts the result into the temporary。U I d。

Our basic block is going to consist of a list of instructions。And a terminator。

 The terminator is the last instruction of a basic block， And it has to be one of these three things。

 right， return。From a return from the function from the program。

 an unconditional branch to the label or a conditional branch based on the temporary on the opera and rather to label 1 or label 2。

Our control flow graph is now going be。A distinguished entry block。

This block is the where we start executing the program。And it's going to be a list of labeled blocks。

Otherwise， okay。So， I would say this。Is a complete representation of the control flow graphs that we saw previously。

RightThat we saw graphically and hopefully build up a good intuition on。Right。

 but it's just laid out in this data structure of a distinguished entry block。

 and then a list of labeled basic blocks。Any questions。About this， so far。

I'm gonna jump to the console to show you an example of the output。Of， of this。

 So we get an idea about what the representation。Actually， is。And then we'll look at the compilation。

嗯。对。So I'm going to take an example program。That example branch we saw previously。嗯。

And then we're gonna pretty print the program， really， just so that you can see what the。

Output of it is like。So we're still kind of using our Ocal style。Of representation here， right， so。嗯。

One of the interesting things。Is that you can。Kind of think about a basic block。

As being like a function。With a tail call。Right， so that is。You know。

 if we wanted to represent this an Ochemel like code。For each basic block。

 we could represent it as a function。Where you execute the sequence of instructions in the basic block。

 And then the last thing you do is jump to another basic block。 That is you invoke。

Another function that represents a basic block。So here we actually have。

So the way we're pretty printing this list of basic blocks is actually。

Pretty much an executable M L program。Or camel program。嗯。Here's the entry block。

Performing its sequence of instructions。It tests the guard。The F command guard。

 and then there a conditional branch。Right， and that conditional branch is either going to go to。呃。

The block of code labeled Z branch 9 or the code labeled N Z branch8。In Z branch。

 this basic block does some computation。And does an unconditional branch。To merge 10。Okay。

 so this is just showing you。Another way of thinking about this intermediate representation， right。

 the distinguished entry。The list of labeled blocks。 we're printing it out here as。啊。

As these mutually recursive functions。None of which take any arguments。

 or rather take unit as an argument and all have a tail callil that is jumping to another basic block。

So help。We not to。It's actually。This is syntax to declare some mutually recursive functions。

So this is， you note that the end here。So we're kind of defining entry， and we're defining。

N Z branch。 and we're defining Z branch。 and we're defining merge 10 all as functions。

 which can mutually refer to each other。 And you're right。

You can't ever jump back to the entry block， but。For simplicity， it's easier to。

To define them mutually recursively。不。All right。So。嗯。Here's the。If you could define these。

 you can actually end up executing that。This code， so that load and mole。Actually， mean things。

 multiplication。And so on。All right。Compiling it。This is really interesting。嗯。

This is going to take us a while to talk through。 There's going be a few concepts。呃。To get clear。

You will actually end up using essentially this compilation approach in homework 4。 homework 4。

 you're gonna be compiling from a source language into L O V M。And so。

 so it is okay to go back and look at these notes and figure out what's going on。Okay。The basic idea。

Is when we go through and compile our source program。What we're going to do is emit。

A stream of elements。 So that is as we go and we are compiling the source program。

 we're going to emit。Elements。Elements are either going to be a label。An instruction。

Or a terminator for a block。嗯。Once we've emitmted the stream of elements。

We're going to process that stream by going。Backwards over it。

And turning it into a list of labeled basic blocks。哎。

That's the high level idea of the compilation approach we're going to take。

 Admit a stream of elements。And then we're going to process that to turn it into basic blocks。嗯。

A minor implementation detail。We're producing the stream of elements。

We're going to represent it as a list。However。From 51。

You know that it's much easier for us to add things to the head of a list。Right。

 so we're actually gonna treat the stream of elements。 We're gonna kind of build it backwards。Right。

 so conceptually， the actual implementation of the stream of elements。

The last element is going to be the head of the list。

And so adding to the end of our stream of elements， we're just going to append to the head。

 So we're building up this backwards list of elements。

 But that's great because also when we process the list of elements and we want to process it from the back to the beginning。

 fantastic that means we can recurse， take the head elements off and so on。

 So minor implementation detail that our our stream of elements is kind of represented backwards using a list to make things look a little more intuitive。

 we're just defining a couple of operations to let append and cons allow us to put things in the natural order。

😊，Okay， so that we can think of this stream of elements as being。啊。

The the stream of elements is growing in the correct order。All right。

Let's think about building up this sequence of elements， first。And then we will look at。

Taking the sequence of elements and boot up the list of labeled blocks。

 That is boot up the control flow。 So that is when we compile a program， C， we're gonna compile it。

Into a stream of elements。Tack on this very last terminator， R at the end。

And then we're going take that stream of elements and process it to build the control flow graph。

Let's look at producing the stream of elements， first。O。So， to compile a command。

Skip is just an empty。Sequence of elements。To compile an assignment。

 we're going to get compile the expression E， that's going give us a sequence of elements。

Or rather a sequence of instructions。To compute the expression。

And the opera end that the result of the expression is in。

We're going to turn lift that list of instructions into a list of elements。Okay。

 becauseuse if you remember， our element constructors were labels， instructions and terminators。Okay。

 so this is just taking a list of instructions and turning it into a list of elements。

 All of them using the I instruction data constructor。Okay， so this is a list of elements。

Though we are emitting the stream of elements。 And at the end of that， we're also adding a store。

Okay， putting the result of the expression into the variable V。Okay so that's straightforward。

 That's similar to the previous translation we saw。Same with sequence。

 the stream of elements for command 1 and command 2， just recursively compile command 1， command 2。

Concatenate them。Let's think about。An if expression。Okay。We're going to compile the expression E。

So I S and result are going be instructions to compute the the test。And the result of the test。

 we recursively compile C 1 and C 2。The true and the false branch。

We are then going to make some labels。Okay， we're going to make a label for the guard。

We're gonna make a label for the non zero branch。A label for the0 branch and a label for the merge。

 where to go to when you've finished the F statement。Here is our。

Here is the sequence of elements for the F statement。First of all。

 we lift the list of instructions to elements。 So that is we're computing the guard。We then。

 perform the comparison。Because we're doing if not 0， we test whether the expression is equal to 0。

We put the result in this U I D that we created， God。

And then we do a conditional branch based on that temporary。Right， the result of the comparison。

If God is， if this is true。That is the guard is equal to 0。

 We're gonna go to the code labeled Z branch。Right， the new label we created for。

When the expression was 0。Otherwise， we're gonna jump to the nonzero branch。We then emit a label。

For the non zero。For the non zero block of code。Right。

 so here we're emitting this element as a label。And after that label。

 we put the sequence of instructions。嗯。The sequence of elements。For C one。Right， the true branch。

Then we terminate that by an unconditional branch to merge。

 which is going to be the end of the F statement。We do a similar thing for the other branch。

 We emit the label。We o the instructions for that branch。

 and we emit an unconditional branch to the end of the of statement。With inimate， the label。Merge。

 that is， this is the control flow point at the end of the instructions。So this is kind of cool。

 right？We're compiling the if command。We don't know what instruction is going to follow the if command。

But this setup， this idea of a sequence of elements， allowed us to emit a label。

Without ottting any code that follows after it。 So what that means is we're able to we're able to jump to the point at the end of the F statement。

 and then whatever gets compiled after the F statement is going to admit more elements。

 and that will be the。呃。And that will be the， the instructions in the basic block following the F statement。

So is this idea clear。The way that we're emitting these elements allows us to emit labels。

 emit sequences of instructions， emitit a label， even though we don't yet know what the instructions are going to be for that labeled basic block。

Any questions about this translation of the F command。Tranlation of a while。Is。Similar。RightWell。

 not0， E do C。We compile the expression E。We compile the loop body C。 We get some new。

 unique identifiers， some of which are going to be used for temporaries， guard。

 others of which are going to be used as labels for basic block， entry， body and exit。

Here's the code that we emitmit。嗯。We're going to start with a。Unconditional branch to entry。

Which is going to be the start of the world loop。 This is really just to simplify our life and make sure we never。

We never emitit two labels in a row that'll just make our next past a little more complicated if we had that。

嗯。Entry is the top of the wh loop。 What it does is it evaluates the guard。

 the instructions to compute the expression comparison of that to0。

 the result of the comparison is stored in guard， and we do a conditional branch based on guard。

 If guard is0， we exit the while loop。 that is we branch to the exit label。

 Other ways we branch to the body。We then emitit the label for the body and the instructions for the body。

And at the end of executing the loop body。We do an unconditional branch， back up to the entry。

That is back to the top of the world loop， where we're going to reevaluate the guard。And continue。

The exit block。The exit label is for the thing that immediately follows the world loop。

So here we're emitting the exit label。And the compilation of other things will take care of oting instructions that go at that program point。

O。Are we comfortable with this idea。Of the sequence of elements。Great。

 because what we're going to do now is process that sequence of elements。

From the end to the beginning。To turn it into essentially， a list of labeled blocks。

With a distinguished entry block。And so we do that in this build C FG。

 build control flow graph function。It's brief， but complicated。嗯。The basic idea。

Is that we are going to be taking our stream of elements。And we're going to be folding over it。Okay。

 now remember that we build it。 We're folding over from the end of the sequence of elements。

Which turns out to be the head of the list because of the representation we chose。

 which is why it's a fold lift fold left。 But you should think about this as starting at the end of our sequence of emitted elements and working backwards。

The accumulator we're going to use is。The instructor， we're going to be building up a basic block。

Instructions is the instructions in this basic block that we're currently constructing。

An optional terminator is the terminator for the basic block that we are currently constructing。

And then the last thing， locks is a list of labeled blocks。

 Theyre the blocks that we've already successfully constructed。Okay， so we start off with。

Essentially， all of those being empty。And no terminator。 And we're going over our。

 we're folding over our list。Our sequence of elements from the， from the ends back to the beginning。

Let's start with a simple one。 If we have an instruction， great， that's going be another instruction。

 now in the basic block we're building up。 So we put that at the。

Beginning of our list of instructions we're building up， becauseuse remember。

 we're doing it in reverse order。If we encounter a termminator。what that means is that we。

Due to the invariance that we're going to have in here， what this means is that we are。

Just beginning to process a new basic block。 We're at the end of a basic block。

And so we're going to set T to be the optional termminator and empty list of instructions that we're going to be building up。

The interesting case is when we encounter a label。So the way to think about this。

 when we encounter a label。Instructions is the list of instructions for the basic block。

With an optional terminator。And。L is the label of the basic block。So。嗯。

Let's look at the simple case first。 If we have a terminator in there。Fantastic。

We've got a well formed basic block。 and we just append to our list of labeled basic blocks。

 a new one。 label L instructions， I N S and S and the terminator。Right。

 so we've just constructed a labeled basic block。If we don't have a terminator。呃。

Things might still be okay， or things might have gone wrong in our compilation。

If we don't have any instructions， that's okay。 We've got a labeled basic block with no instructions。

Let's just ignore it。And so we essentially just discard it。Reet our。List of instructions。 and our。

In our optional terminator， Otherwise， we fail。Allright。

 we've broken in an invari that we intended to maintain in our compilation。I'll also say。呃。Yeah。

 it'll do for a moment。那这。So we build up， we am the stream of elements。

 We process that elements from the end to the beginning to build up the list of label blocks。

And we've already seen the result。Of， of doing that。 it was able to。Essentially。You know。

 turn this into a basic block by processing the sequence of elements that represent those things and then processing the label merge10。

All right， let's。That was the main thing in this class， actually， getting up to this point。

 giving you this idea of labeled basic blocks。Broadbr strokes for a compilation。嗯。

We have a couple more intermediate representations。

 This fourth one is essentially adding top level functions。To it。 So in our source language。

We're going to allow a call instruction。Right，The core instruction is going to give the name of a function。

 a list of opera ends， the argument to the function and temporary I D for the result of the function。

 if you return a value。嗯。Which to me， I said the moment。

 our language doesn't let you return values from function， so。But it's a placeholder。You can also。

What are we doing with Alec here。嗯。Allocating a local variable。嗯。Let me just。Yeah，O。嗯。

Our basic blocks the same。And。I'm not going to dig into the source code too much。

 but we're going to have。A program is gonna be a list of function declarations。

 where a function declaration is the name of a function。嗯。

A list of the variables that contain the arguments and the control flow graph that is。

The list of label basic blocks and the distinguished entry block。嗯。呃。Say。The only other thing。

The want to show you is。We can just clean this up a little。 We can have。呃。

Can factor out UI Ds and global variables。So the idea of having global identifiers。

 as opposed to names of temporaries labels。 So global identifiers would be suitable， for example。

 for functions。For function names。嗯。And for the names of variables that we're creating。

 and we're gonna use U I Ds just for temporaries for those intermediate results。嗯。But otherwise。

 this。Is looking。 This is pretty similar to the previous language。We're always going to factor out。

In our instructions， previously， some of the instructions took a U A D to store the temp result of。

Of， of that instruction， like the evaluating expression。

We're actually going to factor that out and make sure that every instruction has a U A D associated with it。

So this is a design choice。 This U I D will make sense for things like the result of a binary operation。

 but won't really make sense for things like a store expression。Right。

 the reason why we're doing this is we're getting closer to L O VM here。

So this IR5 is actually pretty close。To LO VM。And I should add。

It's close to our Ocal version of L O VM。 L O VM is actually written in C plus plus when we're using U I D here。

L O V M actually uses a reference。which is maybe why， having a。Essentially。

 a U I D for every instruction and L V M's implementation might make a bit more sense as a design choice than it does here in O camel。

But were wanting to make this O camel。Vion of L O VM。

Be close enough to the actual LL VM that we're gonna be able to limit LLVM code and pass till the LLVM compiler。

 That's useful for this。嗯。Right。A program is now a list of global declarations。Where these are。嗯。

Think of these as global constants。They're going to wind up in the data。Segment of your assembly。

And function declarations， which is going be G I D。

 the name of the function and function declaration。

 So know that the function declaration itself doesn't have a name of the function。

 It just has the parameter list and the control flow graph。So the name is kind of pulled out。

 factored out into here， the list of function declarations。

And so this intermediate representation is pretty close to L O VM。

 which is what we're gonna look at on Monday and dig into a bit of the history of that compiler and the representation。

That it uses。Okay， thanks so much， everyone。 good luck with homework 2。 you continue to work on that。

😊，Don't forget to make contact with your study groups。And you know， if it easier， if it's easy。

 there's C S nights， office hours tonight， 8 PMm in the Winthrop dining hall。And otherwise。

 I' will catch you on Monday。

![](img/41a464e9f1eb68439d7584445f5a464e_64.png)

差不多。わです。第二位。これ。这是。后边。我在明。

![](img/41a464e9f1eb68439d7584445f5a464e_66.png)