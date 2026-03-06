# 加州大学伯克利分校【中英⚡全栈开发｜Spring 2023, Full Stack Decal】 p07 P7 Lecture 6, JS 3 - Spring 2023 -BV1ddBTBrEo2_p7-

Okay。That。行是吗？あます。That。辛苦ですね。你时感受。其实会。在。Yeah。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_1.png)

。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_3.png)

个。No。那给。我们。不是先。Okay。我。So。对个。我。Okay。在对。Okay。Yeah。嗯。嗯。Yeah。那我看一下。Okay。No。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_5.png)

嗯。说了呢。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_7.png)

Thank。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_9.png)

最个人。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_11.png)

是的。这个。ok。Hello， everyone。Welcome to lectureture6， Yeah，6， okay。都是这时间你。

There's a reminder that there's a social at nine today and they have food， we have free food。ok。

Or just， I'll just get right into it。Does anyone have any starting questions？Yeah。

 where here or you're talking about this right， Yeah here。Okay。Yeah。I don't know。

 but I'm hungry so like。Yeah， okay。And。Okay， I will go on。Today we're going to talk about actually。

 we're talking about scopes and async stuff。 So the first thing we're going to talk about is functions。

 Okay， so this is a regular function， and that's anarrow function。😊，Yeah。

 they're similar to they're the same thing as most other like you've done Python functions。

 slightly different syntax， but you don't need to type anything， so it's not like Java。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_13.png)

嗯。I'm going to start with the demo already。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_15.png)

Yeah。嗯。Okay。I make this。Yeah。Hopefully， that's big enough for everyone to see。是。Okay， so。Oh。

 my thing is in the way， who should say。I'll put this down here。So that's a regular function。

You don want to get bigger。It's regular function right there， add two is an arrow function。

It looks slightly different， so the main difference is。

The way thearrow function works is you make the function and you have to assign it to a variable。

 whereas the non arrow function is like you're saying this is my label for the function。

When you debug your code。With like a deep， like a debugger that this one's easier to。

Like if you have a stack trace or something the thing that tells you the stack trace will say that you have something in the add function that's going on if something false like if something throws an exception inside the error function。

 it won't tell you that it will say some anonymous function has an exception so it's slightly more annoying to debug error functions。

That's like the main difference， otherwise they're essentially the same thing。

We can go ahead and run this。Oh nice， it's kind of what we expected because this is what I'm printing out console。

log is like the main way you print out stuff。嗯。I'm using the first named function。

 I'm also using the arrow function， you know you expect the same thing and so it's the same thing。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_17.png)

Now， let's talk about。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_19.png)

Oh， yeah， any questions？好。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_21.png)

Oh yeah。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_23.png)

有个啊。ます。Talk about scope。 Okay， so。You have a bunch of different kinds of scopes you don't have to memorize any of this the global scope is like you can access it from anywhere the local block or function scope is like you can't access it from everywhere。

 but you can access it wherever you need to access it JavaScriptscript variables use lexical scoping I don't know if 61a still talks about this but basically you can pretend that anything that's undeclared in your current scope your current like pairbas if it's not declared within those you can just pretend that it's preended with non localal you know in Python use say non localal and it's like going pull the value from an outer scope。

Javascript does that by default unless you declare the variable。啊。Oh yeah。

 there's like three different ways to declare variables。Var Latin con， don't use Var。

 even though like everyone uses Var used to use Var because it was the only way to declare variables。

 the reason why is that it's very hard to debug your issues when you use Var because the behavior of Var is very weird。

嗯m。Yeah， like for example， if you if you declare a variable with var at the top of your script。

Like outside at the global scope， then it's in the global scope。

 but if you define inside of a function， it's in the function scope。Whereas let is what you expect。

So use。I think， I have。Okay， okay， I'll talk about that later， but yeah， let you can reassign stuff。

 but you can't redeclar it within the same scope。And the con is you cannot be reassigned。

 it cannot be reassigned， but it's a bit of a misnomer。

 it's not like cont in C++ so you can still mute。The data is so mutable， you just can't reassign it。

Any questions。Yeah。这么咋回说？No local if not declared oh that's that's the way that JavaScript like resolves variable values so what that means is like if you see a variable somewhere in your code and you're like what is the value of this variable。

You can pretend that it has non local propended to it if it's not declared in that school。Yeah。

So which one was the。So the thing that I recommend you would probably try never using is Varr。

 don't use Varr。UmBut I think yeah， okay， okay， so basically when you write code。

 you want to always start by using cost。But if you need to redefine that reassign that variable。

 then okay， change that cost to let。And then if you need a Var for some reason。

 I guess you can change it to Var， but that's like a huge red flag。

 something your designs probably wrong。You should be able to change your code such that you never have to use before。

Okay。I do have a demo， oh wait， any more questions？Yeah，Constant what？What上。对一下。Oh， oh。

 like you want me to show you an example of like me using cons， okay？



![](img/2c08eb44f71fd5e70b78fc82e83f390d_25.png)

嗯。I can do that real quick right here。I can say a cost of this is just a random name is five and then if I try reassigning that。

教 you。Should not be able to do that。Yeah， okay， so assign to constant variable is not allowed。

Exactly， yeah。I can say like property5， and I can say a R that property is 10。

Let let's see if that worked。Yeah， no errors thrownone even that it's constant so it's like in Java if you've taken 61b or anything or something else。

 the final keyword is similar to this。2。Oh yeah， the next。So this is one of the weird var behaviors。

 right？Don't comment this out， well no errors shown。

Even though you defined it before you declared it， and it's because var declared variables are hoisted up to the top of the script。

So yeah， like if you comment this out。You know， if there's an error because it's not declared。

 but it's hard to tell that you like if I have a bunch of code in between these two statements。

 like there's a bunch of stuff in between I can't see you within the script。

 it's kind of hard to debug。So yeah， don't use bar。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_27.png)

Okay， now we talk about this， so in Python a very similar thing is self。In Java。

 it's also called this， it's usually you know if you have a class and you have like it's instantiable。

 it's not a static class， it's not an abstract class。

 then the this inside the method refers to the current instance of that class， right？

So but in JavaScript it's very dynamic the value depends on the current on how the current function is called that runtime。

 which means that you can bind the this value， the keyword this。Dynaically。So for most functions。

 the owning object if there's any， is what this refers to。Otherwise， it's undefined or。Yeah。

 the global object otherwise， the global object is an object that has a bunch of global variable properties。

 you shouldn't you don't want to use you don't want to rely on those properties if you use a strict mode。

 which you probably should be doing。But so usually this refers to the owning object or undefined yeah。

 what do you mean by own object？

![](img/2c08eb44f71fd5e70b78fc82e83f390d_29.png)

So wait， I think I have an example。Okay。Wait， do I know it。So something like this， this is an object。

 the thing between the races， it's a in JavaScript。

 an object that's basically like a dictionary and Python。

And I have this property here that has a dysfunction。So this property inside this object， yeah。

 so the owning object will be this whole thing， this is the owner of this function。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_31.png)

Yeah。The returned okay， so that's like the first case， if that's not the case。

 maybe your function was returned from a call to the bind method on a function that was not an arrow function。

So the bind method lets you pass in a value explicitly that you want this to point to。

You have an arrow function， this will not be assigned inside thatarrow function。

 so it's like it's you know the default variable behavior you go into the lexxiocope and see where this was most recently defined in your parent scopepe。

And there's like other things that would change the value of this。

 but you shouldn't have to worry about it for most of the time I've never had to use it。那你过选一下。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_33.png)

こ。So where was I。嗯。Okay， so here we have a function。Oh wait， I forgot to talk， oh wait。

 this is from the previous example where I say var inside of a function and then I call that function to try like defining food inside of that function and see if it's like let me just around that quickly。

哦。Oh， I actually have a bunch of， oh， this is from the previous example。Okay。

 we can go for that later， I guess。Wtifully now。Yeah， okay， so this is an object。

And if this refers to me so here I'm calling me dot get pet pet name。

 so that's me dot get pet name if this refers to me this object the me object I should be able to get my pet's name because I'm returning this dot pet name。

 which is what I'm printing here so。If this refers to me。

 I should be able to give my pet's name and I do I get dog。Which is the vet name right here。

Now let's see if I steal this more pets。Property of that me object。

 so I take me do more pets and assign to this variable。And then I call。

More pets ands see let's see what would happen。Yeah。

 so it's not what I expect I call I call stolen more pets twice。

So you would think that maybe I call this function twice and if you didn't know about how this worked。

 then you would think that number of pets would be incremented twice so this should be three。

 this number of pets value inside of me， but when I print this actual me dot number of pets value I got one here。

So that's interesting， right？And the reason why that happens is because when I take out that property。

 the function from that property and science to something else， I no longer have that disbanded。

 there is no more owning object。So now I have an object called you。😡。

And I'm going to bind stolen more pets， which is remember that unbound function that I got from more pets。

 I'm going to bind， I'm calling the bind method on a nonarrow function passing in U as the object。

So that's what the bind method does or what the bind method does is that would。

Assign this value inside of that function to you。So if you call that you can have them function twice and I try to look at the U dot number of pets。

So you don't number past this value right here。Maybe you would expect it to be three and if you do expect that then you're correct。

So maybe that's a bit tricky because。It's not clear that this bind method will reassigned this value。

Okay。I have I think I have like two more examples， this is a property on you called Defying FN later。

 so it's currently undefined and I'm going to take get pet name。See what get pet name was， oh yeah。

 it was this， it was the thing that returns the pet name。And assigns it to。

Define as then later and if this is correctly rebound。

You should see your pet's name when I call you dot define I later。And let's see if it does。

It says cat， which is not dog， cat from the U object。

So that's kind of interesting if you directly assign a property that has a function from another object to。

This object。Then calling this function。W。Oh yeah， colon dysfunction gets you capped now so that this is rebound correctly。

 which is what we expected。And finally， I have just a little silly thing。Which yeah。

 so I call get pet name， but I am lying。嗯。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_35.png)

That is so like if you didn't know about the difference in behavior between regular functions and arrow functions。

 then maybe you would expect this to return hamster。嗯。And let's see if it does。

you get undefined so the reason being that inside of an arrow function that this value is not bound to the owning object。

 it takes in value from the lexical scope and in this case in the lexo scope in the parent scope this is not defined。

Okay。I think， yeah， so that's this demo。Any questions Yeah。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_37.png)

Still there。I would not use anarrow function， yeah。But you could call。Ohm。

 I'm just wondering what this is actually referring。个事号。So in this case。

 it takes in whatever this value is in the parent scope， in the lexical scope。

So if this whole object， this whole constant sign， this whole call， this call right here。

 this whole thing was inside of a named nonarrow function that's owned by another object。

 so if this whole thing was inside of another object with a function。

 then this would refer to that object because in the parent lexicalco， that object。

 the function in that object will have。Founded this。In this case wouldt almost be like the yeah。

 and it turns out that this is not defined in in the global scope if you're using strict mode。

 which yeah。Yeah。For the you got defined FM later equals to me happening。 so it does work。

If you're signing it， something very has at this。I think that。诶日 same we cant。嗯。在 the这。Yeah。

And the reason is here you have an owning object， which is you here， you don't have an owning object。

 it's just a lo variable。有 questionss。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_39.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_40.png)

Now we get to talk about Async JavaScriptscript Oh uses it's so that your code is more maintainable。

 which is not a big goal， so it's not too important that you use cons everywhere unless you need to but。

If you have a variable that you expect to never reassign。

But it's declared with let and you have bug somewhere else in your goat that reassigns that variable。

 if you use cost， the interpreter will tell you that you have reassigned somewhere else。

 whereas let won't。对。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_42.png)

So you can write concurrent code in JavaScript， which is very good because usually when you do web devev。

 you're probably building something for an end user that has that's looking at a page and they're probably interacting with that page。

 so you want it to be interactiveed right？But the problem is if you want to load something from a network。

 that usually takes a bit of time。So if you wait until everything is loaded from the internet before you make your page interactive。

 it's super annoying for the user right because it's like the page is frozen while everything is being loaded So what you really want to do is asynchronous asynchous asynchronous。

Asynccly， load your data。Into your web page， but keep your page fully interactive the entire time and you know before your page is loaded。

 you're not going to have like all of the assets you need。

So you're probably gonna put in like a fake thing When you open YouTube。

 you see that like that ghost thing。I don't know if I should have taken a screenshot for here。

 but as code is very good， concurrent code is very good for interactivity。😊。

But writing a code is very hard。So。Yeah。Okay， we talked about race conditions so like you've taken 61 no 162 I don't and 61c deadlocks might be one of your questions like is that like do I have to worry about deadlocks no because JavaScript is single credit but do you have to worry about data races yes because concurt code can cause data racists if one Enc code modifies your data at a time that you don't expect it to。

That's a database race。So。The first way that the person who create that。

 I guess during the development of JavaScript thought of in order to write asyncN code is to use callbacks。

So in 61A， you will or have learned about higher order functions， and that's exactly what this is。

So when you have a function where if an async event occurs。

 the function that gets passed into that function will get called。

So an asynch code can be changed using by nesting these callbacks。

 so if you want like after event A happens and function A gets called you want to want to do event B and get function B called and if you want to chain those together。

 you can nest these callbacks and you can change them。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_44.png)

So here is a demo for that。是。So we have a function called callback help。

And this is a function set timeout， it's built into JavaScript where if you you call it by passing in a callback function as the first argument。

 and then you have a number of milliseconds as a second argument， so this is the first argument。

And this is the second argument。And what this does is when you call this function。

This first argument will be put onto the queue， the job queue， there's a better name for it。

 but you can think of it as a queue and then it will。Call that function after 1000 milliseconds。

 so one second， so after one second this function will get called。I have another function here。

 or I have a variable here that's an arrow function。That takes in。

A higher order function because it gets passing to sit time out。

So this is something that takes a while because the function that you pass into it won't get called for at least one more second。

Now I'm going to call something that takes a while， and this is my goal。

 I want to be able to do three。Callbacks change in succession I want them I want them to be async because they take a while right they take one second to run。

 but I also don't want function number two to be called before function number one and I don't want function number three to be called before function number two。

The exact function is this。This。And this。So。When this function gets called。

 we all know that the first function was called so that finishes that job。

And since we finished that job， we want to call this second function， which is this function。啊。

 and so on。And you can see that very this is not very readable， right。

If you want to chain like five functions together， you're going to have to indent like seven times words or so so this this is called a callback code now if you if I run this code right now。

 you should be able to see that it does what I described。

Okay so every second there was like a new line that printed right So that's that's the magic of the set timeout。

 And we have this， this line appeared at the very beginning。

 that's kind of interesting because we call callback hell。 This is call back hell。

 This whole thing is callback hell。 We call callback hell first， and then we print this text。😊。

But this text appeared before the things before this。Before these console logs。

 so that's kind of interesting。Now， late for school got called at the very beginning and it was at the same time as finished' first job because this was timed out for one second。

The first thing was also timed out for one second because that's what something that takes about does。

いな。Oh yeah， this appears before everything else because I call it synchronousy， yeah。Oh。

 so when when the function reaches， the line was like set I now comes while late to school when it's waiting that  a000 bill second is just keep text code or it just sit there。

It keeps executing code yeah。You can think of it as。Okay。

 so how JavaScript runs code is it uses a similar event loop。

So basically every line of code is done synchronously through the event loop and then at some point you'll find some lines of code will be like push this to the asyN queue。

And it gets pushed into the asyNQ and how that async queue gets depleted。

 so all the async code that gets run， how those code gets run is whenever the event loop isn't actually doing anything synchronously it will run those codes。

So we had like five set headouts then each with like a shorter amount of time， but they print back。

Yes， if I call all those at time out synchronously， yeah。

 which means like if I call those at the same time yeah。We can do that right now， maybe， let's see。

 I'll comment this out。So this one I'm going to put at like three and two。Let's see if this works。Oh。

 wait， we can't tell it。But this one's one。This one is two。 and this one is。对你去。Yes， three， two， one。

 even though the one wasn't the beginning。Yeah。Okay。Any questions？more questions。Yeah。

 is there anything that you？Theyy kind to start with。我白 sorry。But as soon as possible。

 sort of setting like that at the blade。Yeah， or is that what's happening and it's just taking that hard of time。

嗯。Wait， so you're asking is there a way to queue something up like instantly？Like have this be zero。

 essentially， is that the question I get？Yeah， you can you can do that and then they will execute simultaneously。

But it's not actually， it's still in async， it's still async yeah。😊，But。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_46.png)

Okay。Okay， so we we just looked at callback hell， it's like I'll maintainable if you want to change anything more than a few。

Callback functions so we're going to look at promises。

The reason being that callbacks have disadvantages， you already saw with a callback hell。

It's hard to debug because it looks like that and we can make。

Are deving workflow a bit easier with promises， which is actually human readable。

So what our promise is， it's another way to write async code。

They promise that your code will be resolved later that's why they're called promises actually I don't I think they should be called futures but whatever like some other languages call it futures。

It's a good way to remember what they do right like they promise I promise you that your cooking will run later。

 just not right now。Promises are objects。They they're just objects。

 they're not like a special primitive type， they're just objects。哦。

Yeah and they have you can if you're like thinking of stuff in states。

 they have three possible states， they can be fulfilled， which means they were resolved。

 they could be rejected so something went wrong while the callback was or while the job was being done or pending。

 which is the thing still hasn't been called yet。You can change your promises using then and catch methods。

 we will see an example of that。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_48.png)

Yeah。Okay， so this is a。This is an arrow function。So better job is a function that takes in as input a Boolean variable and time in milliseconds。

And it returns a promise so it's like it's a hopeer function I mean a hopeer function to make it easier to make the following code order。

 but what it does is it returns a promise。New promise。

And the first argument of the promise is a callback function。

 so this is really hard to understand but。I have a good mental model for you。

 which is Res is the object that you need to call with the resolving value if nothing happens that goes wrong。

 so if things don't go wrong， you want to call res with the resolving value if things go wrong。

 you want to call reject which is the second argument with information about why things went wrong。

And if we， I just say like if it succeeds， I call res， if it doesn't succeed。

 I call reject and you for demonstration purposes， I made so I can set that easily。Okay。

So I have this promised change example that I call it immediately after I define it。

Do the better job， which is a better job that will succeed。In one second。嗯。

See that' that's a cost variable right there and then on that very wide just assigned I call it then which is a method on promises。

So what the then method does and promises is it takes in two arguments。

 one is a higher order function that would be called if it's resolved。

 another is the higher order function that would be called if it's rejected。

In this particular example， I didn't put anything in these parentheses because I don't actually pass in any value inside。

The resolve the reject like hi functions in the promise。

 but normally if you want to pass actual information along thing。

 then this is where it would appear in the arguments of the then method or in the callback of the then of the then method。

So that's what this is， so like if it's successful， I call this callback， if it's rejected。

 I call this callback， and there's also this catch chain method。This is。

You can think of it as the catch block of a tri catch block。

 what that means is if your error isn't caught。Before this catch method is called。

 then this is where it will fall。So this will be an interesting thing to see in a bit because you would think that you would just call this and you're done which。

You could be， but this will catch more errors。嗯。Do the better job too is something that will reject and I I put the chains after that promise the same chains as here so do better do the better job and do the better job too both have the same then and catch chains。

Do the better job three， I change things a little bit。The job itself。

 the promise itself is still supposed to resolve， not reject， be successful， true in three seconds。

 but in the first。Argument to the then。Method， the callback calls promise to reject。So， in。

When this outer promise resolves successfully， this first argument callback will be called in a thenM method。

 that's how the them method works。And then， but that callback will。Return， a promise not reject。

So that will be interesting to see。あ。Okay， so。One， two three because I one second。

 two second and two second and three second so successfully did the job。

 I guess thats we did expect that right because it was true was supposed to resolve correctly so it was supposed to call the first argument first callback of the De method and that's why we see successfully did the job。

At second two， we see job failed， which we also kind of expected right like I said this promise should fail。

 it should reject and so they should call the second callback argument of the thenM method which it did。

 that's why we see job failed。And we don't see the catch thing that's that's from second three。

 So so when you call this。Callback the second argument to the then method。

We didn't go to the callback that was passed into the catch method this wasn't called。

In better job 3， this was called。Um that's because what catch does is catch all of the errors right if you have an error inside of a callback that was passed into the then method。

You can't catch that error within the then method that's not how code works like cyclly。

 so if you throw an error in this case， if you return or promise reject object。In anywhere actually。

We we need to we need to call this。The catch method will catch that rejection here。

So we can actually see the never mind job failed if I pass in。

 if I say this call actually should take one argument。

The reject object will pass this shrink into into this callback because it's going to reject and I can try printing that out right here。

时候得。Yeah， so now we can confirm that this callback was first called。

 which then rejected and then the catch caught that rejection and then called this callback。

 which doesn't reject。Let's see what happens if we reject again， so we throw that error again。

Yeah okay， so that's bad because you didn't handle that rejection so you should always handle all your rejections and that's why you need a catchwalk at the end of your promises。

Oh。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_50.png)

你 questions。吃。😔，冇呀。

![](img/2c08eb44f71fd5e70b78fc82e83f390d_52.png)

Yes， any questions？Yeah， so we can， we can never use one like。You can。You want to use it if you。

When you write your logic and you're like okay， this is a bad case I need to reject this promise because this isn't supposed to happen that's when you purposely call reject it's just that every reject object that you return you want to make sure that it's always caught with a catch like。

Some sort of etcing catching mechanism in this case。

 it's the catch method that's changed at the very end。So because it's at the very end。

 it's going to catch it Now this， you know， if you reject inside of the catch callback。

 then that that's also bad， but you can change multiple catches if you really wanted to， but。Yeah。

Yeah。Better which one， Oh， this one， Wait， this one。Yeah。

It's it's a helper function in this time you should think of better job as a helper function that takes in whether it to succeeds。

 whether the problems I'm about to return succeeds and how much time I should delay。对吧。Oh sorry。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_54.png)

Okay， so。TheresThere are a few disadvantages to promise training， which is that。

It is not very common to need to not need a value that you're going to resolve inside of a promise。

After you。Called then right so what that means is like you know you load on an object you call you make a promise that's like okay。

 let me load this object from the network they think after that call after that creation of that promise what else would you do in that in that scope in your code you're going to want to use the thing that you wanted to you know pull from the promise right so。

Typically like the rest of your important code gets pushed into the then callback which is not great right that's like one or two additional indentations and you have a new problem which is promise callback how which is。

When you have promises within the callback of the then callback， so that's not very good。

 we didn't really tell the callback hell problem and this is also still hard to debug because you're still writing async code。

啊。You're always going to be writing asynch code， but you're writing asyynncch code in the style of code that's not very synchronous。

Which hopefully foreshadows what I'm about to talk about， which is asyncs and awaits so this is。

Another way to use resolved values from a promise， right？

A weight hoistists the remainder of your current block to be async。

So if you have a block of code that's inside of an naSync function。And the first time you call wait。

 from that point on， the rest of the function will now be from the point of the view of the JavaScript interpreter will be async。

 not synchronous code。And since this is a very common pattern， by the way。

It covers the common pattern and this is very easy to debug because now your code looks synchronous。

 you just put a weight you know， whenever you need asN code and then everything else just looks like regular synchronous code。

The downside is if you really， really wanted to continue executing synchronously after。啊。

Your await weight call you can't right because after that await keyword。

 everything else in your function becomes async so everything that's synchronous you want everything that you want to be synchronous needs to come before the first await keyword in your function。

But that's not a very common situations， so I' wouldn't worry too much about it。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_56.png)

哦。Oh， that was the end Oh wait， no， I didn't talk about this yet Okay okay。

 so I have a promised async function that gets called right after I define it I label this function as async because in JavaScriptscript every time you want to await use the weight keyword inside you know somewhere。

 the surrounding block needs to be declared as async。So I have this constant。Object here。

 which is an arrow function。Exe me。It's a error function Ill take three arguments。We will succeed。

 which is similar to the better job error function from before。

s me it's a helper function it lets me control if I want this promise to resolve or reject。

The amount of time it will take。For the set time up to execute and then the values so this time I'm actually like returning something you know when I resolve so this is what I was talking about earlier。

The two arguments to the callback function you pass the promise object right those are also callback functions and then you call the value that you want to pass into the thing that's consuming the promise。

So I say。If I want to resolve， I call resolve with the value， if I want to reject。

 I reject with the value that。All right。1，2。Give。To the consumer。

And now we can write synchronous code， even though our code is actually async。

 see this try and catch block， right， that's a very classic synchronous thing for catching exceptions。

But now instead of chain bends and catch。Methods， I can just say await。

And I want to actually resolve something that's the helper function from here。

 by passenger so I want this promise to resolve successfully in one second the value five so the consumer this better job for。

Technically， it's a promise object， right， Proms are objects。 you create。

A new promise here and assign it to this variable， that variable will be a promise object。

But as a mental model， what you should think of it as is a value that will eventually。

Resolve to the value that you wanted to resolve to so in this case i'm saying that it will the promise will result to five。

 so i'm saying that in your in your head the mental model you should have is this variable will eventually become five。

嗯。Yeah。Its a week， oh yeah。Quion about the variable given that。我利的。Yeah。

Then what solution focus for writing actually resolve something if you've already determined it。

 like why would you meet the actual function。So this is like a textbook example。

 like for demonstration purposes。In actual promises。

 you won't be able to specify if your promise will succeed or not。

 it's inside every promise you're going to make a network call。

That network call can succeed or fail and it's out of your control right and you're going to have to be able to handle that inside of here so right now I'm making a very synthetic like lab example where I check the will succeed variable which I define so I can control the outcome of the promise。

Yeah。So that's why you need a resulting objective。Any other questions？Yeah。

 when should we use basic versus one versus。All of them at the same time。You can。

 so the thing that you don't have to use is then catch versus asynco weight。

I would use asyco weight as much as I can， and if I really need to。

 I would use then catchch because there are some features in then catchch that you can't do with asyco weight。

But normally in modern JavaScript， you want to use asyynco weights， promises， and callbacks。Okay， so。

Yeah， this a weight call basically unwraps the object， so I kind of like like。30 seconds ago。

 this is not a。Promise object， the O weight call wraps that promise object into the resolving value。

So this is actually just on the number or the promise will reject and you you know get kicked out of the trip block and you have to go into the catch block let's see so you can see that like here this promise should resolve correctly so I should be able to see this get printed。

This promise will not resolve I said false， it will reject。

So you shouldn't see this text because when you await a promise that rejects。

 your try block will get will catch the error and you go to the catch block and you should be able to see this so that's what you will expect。

Like。也会。So if it wasn't in a tribo， your exception。

 your rejection will bubble up until it does find a tribo yeah if it never finds a tribo。

 then you will see an error like the one we saw previously where we were not handling。系呢到唔系即系。Okay。

 it's like it would say something like this like it's unhandled。Yeah， see okay。

 so this is what we said we would expect right， we see the on success， we see the five。

We see the LO with the air。The value that was returned on rejection， which is 10。And。Yeah。Yeah， okay。

 I think that's the end of this demo。Oh yeah， this doesn't print less because this is a synchronous。

嗯。Call to this function。Which will execute before， probably before your async calls。我 is yeah。

Thiss the reason why。Like a second of the between mark is the first case to awake the first case inclined client to。

Resol work。Yeah， so the weight in your mental model you can think of it as it will block the thread。

 which it doesn't， but it's a good mental model to have here。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_58.png)

Okay。Ech is a thing that you should use I don't have a demo code and I'm not going to talk too much about it because there's documentation。

 but it's and it's also like web only I can't really run it here。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_60.png)

![](img/2c08eb44f71fd5e70b78fc82e83f390d_61.png)

Yeah， it lets you call data from another API so like you can make a web request。诶。

And the returns are promised， so if you want to handle things that gets returned from the fetch call。

 then you'll have to handle。Just like any other promise。ya okay。Oh， final question。M word。

 I had a magic。Oh， the magic word is pinky。はい。So。There is。Okay。Okay。No。Yeah。咁呢时系。对。嗯。P嚏。O。嗯。



![](img/2c08eb44f71fd5e70b78fc82e83f390d_63.png)