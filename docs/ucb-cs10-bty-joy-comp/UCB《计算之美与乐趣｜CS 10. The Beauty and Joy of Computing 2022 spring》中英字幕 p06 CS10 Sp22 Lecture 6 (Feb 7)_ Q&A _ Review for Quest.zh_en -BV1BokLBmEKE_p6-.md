# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p06 CS10 Sp22 Lecture 6 (Feb 7)_ Q&A _ Review for Quest.zh_en -BV1BokLBmEKE_p6-

嗯。

![](img/65d7bfeed0b465833a59f3f755e31abd_1.png)

Okay， that's fine。😔。

![](img/65d7bfeed0b465833a59f3f755e31abd_3.png)

All right， so。I'm just going to try and speak loudly because there are。

About a dozen batteries and all of them seem to be dead in this room。Of。So that's great。😊。

So what I was going to do mostly today is just go over some review and some Q&A for the Que there was a thread on Ed and if you haven't had a chance to see it during the next like I guess till noon or whatever feel free to put additional questions there because I'm going to start off with the ones that are in that thread and then I'm going to go over a couple past quest questions as well as just some review but before I do that I just want to。



![](img/65d7bfeed0b465833a59f3f755e31abd_5.png)

To go over some logistical things。So I'll link these afterwards。

 but there's no real slides for today， just some references。

The form that should actually say for ultimate and remote not extensions， but if you need。

If you do need to take the quest remotely， please make sure you fill out the form it's been on the website。

 everyone who has filled it out so far we have your responses， there hasn't been that many。

 otherwise if you don't fill it out you can assume that you're taking the quest tomorrow night。

 7 pm 155 boll that part should be pretty straightforward it's 50 minutes it's going to be a few pages long right now it's all multiple choice。

😡，The midterm final will have non multiple choice questions。

 but the quest all multiple choice it's eight questions。

 15 inh parts so you can think of that as you know 15 sets of bubbles that you have to fill and you have about 50 minutes to do it so so far I think it's pretty reasonable there is a great scope of self checkck for today。

It's just four questions that are meant to be reviewed i'm not going to do those today。

 but they are good。You know， good options and I'll publish the results so that everyone can。

Can't see the correct answers。And。With that a reminder that the。There's the Ed thread。

 okay and how is this computer thing set up now with this monitor？嗯。Cool so。哦。

And now I need to figure out which way。The mouse goes， okay， that's true okay， that's backwards。

 nice。So， let's see。Get。GetZoom out of the way。

![](img/65d7bfeed0b465833a59f3f755e31abd_7.png)

Yeah。啊。So the first question that was on Ed was reviewing combined。And。

I think when we're being combined， we'll go over a couple things which are going to be useful regardless that I think willll hopefully。

This help think about how we should practice， think about functions。

 thinking about running through scripts and so on。嗯。In the case。Of。OK好吧，啊我试下。So。呃。诶。

In the case of higher functions， we have three primary ones that we're focusing on for the quest。

 these are not all the higher functions that there are in SNAP but they're the ones that we're going to be working with。

 I will just highlight that if you are studying from past examples，嗯。

The quest this year is the beginning of the fourth week many previous years it was the fifth week。

 so some of the topics like algorithmic complexity or runtime analysis asked we're going to cover that after the quest this semester。

 but it's definitely something that。😡，You know was was on some of them so if there's a topic that you know that you see when you're studying。

It might not be on on this semester's quest if we haven't got to it yet。

 so just just have that warning。 so for higher functions we have。

Very primary functions map keep and combine and each of these functions it's worth thinking about the domain and range of how they operate and I think think about domain and range is helpful as a way of。

😡，Reducing sort of the uncertainty or the questions that we have to ask about what each function does。

😡，All of these functions， map combined taken two arguments， one is a function and one is a list。😡。

Combine the order swapped， so the list ispers function a second。

But that they work essentially the same way。It's worth remembering that whenever we see a round block or a gray round ring。

 what we're talking about is a reporter block or reporter block is。Any block that returns some value？

It could return a list， it could return a number as that math blocks do， it could return some text。

 it could later on the semester return things like a function or another sprite。

 but basically a reporter block can report anything。😡。

And so these blocks right here where we see these gray round rings。

What we're thinking about are blocks that report some individual value。😡。

As the types of blocks that will work。In a case of keep。When when we see this hexagonal shape。

 we're thinking about our predicate blocks and our predicate blocks are really a special type of reporter block that can。

Report specifically true or false as the value so。Staff if you make your imp predicate blocks won't enforce this。

 but if you see a predicate you should think this block returns true or false yes or no answers that's the only result that should make sense so if you ever see this gray hexagonal shape what we should be thinking is a block that returns。

😡，A true or false value。ThatThat we can use。嗯。Inside inside keep and it turns out because it returns。

A true false value it still reports result we can actually use predicates inside map。

 but we're not going to really do that very much so the first thing that was asked which I do think is。

Here我 the。Which what is the mouse going here okay？So I do think it's worth spending time on is。

How does Com work and what are some examples that we use it for？sec。Thank you， watch。

Combined is a really useful function for taking a list of items。And reducing them down to what is。

 in a sense， a single value。So when we take combined functions or combiners they're sometimes called。

We have two inputs。And together， they will successively apply that function to each input。

 So a really common thing。We might do。Is。There are easier ways of doing this now in Snap。😡，对。诶。

Is if we take a list of text， so we'll actually do this probably in lab。At some point but。

Let's say we take。You know， a sentence like the University of California at Berkeley。

 we can split it。Into a。A list where each item of the list is one word。OhYes， sorry about that。

 thank you for checking that box。And。And so what we have in this case。

 this is going to look very similar is the result of our。Let me get that other the way。

The result of our combined block in this case is just the same sentence so what we did is we took a list of words。

We joined it using a join block and we get a sentenceend back so combine one way of thinking about it is just let me take whatever kind of data I have in my list。

And stick it back together in some form， so this is one type of operation I'll just duplicate this out。

All rightSo taking this list。And。joining it back into a。

A single sentence now we can one of the nice things about a block like join that allows us to have multiple inputs is that we can kind of start to see how combined works so wherever there is a blank input right this first blank here。

 the second blank。Those will become the items。University you know of and so on。

 so if we wanted to adjust what our sentence looks like。We could really sort of see that， you know。

In between each word is combined is taking。The word u the word university sticking them together。

 it gets its result and it sticks another long series of underscores， whatever it might be inside。

At the middle of our word， so combined is useful for a lot of operations like that。

But there's a couple other。Sort of useful tricks that combine has。So。Actually。

 we're going to get rid of join。And let me see if。嗯。We have in S。啊。酷ol。So in Snap。

 there's a library that gives us。Some handy additional math blocks。

These are ones that we could build ourselves。But for now。

 I'm just going to grab the minimum block that exists in this library。And the minimum block does。

Okay， that。没睡。😊，嗯。屌啊。Why wouldn't。All right， well， that's a terrible example then。Oh。All right， fine。

Well我。New what computer。We're going to make a new block in this case。Yeah。So。

I sure're just going to use this one。Yeah。I actually know what I want if let's do this。

If x is less than y。Report X。I also support why。But we have got another man oh， that's fine。

I did not。All right， cool， well now we have two all right。

 now we have a minimum block that actually works， so we'll explore this。😊，呃 so。

One of the useful things about combined that we can think about is we're looking at operations that we could do multiple times in a row that each still get us the same result。

 so if I ask for。Let's say the list of numbers。From let's say 50。220。

This gives me just a bunch of numbers in a row。Of course， in this case， right。

 like we're putting the number 20 in is our input。系，不。

What I get back here is the number 20 has my output so what combined again is doing is taking the minimum of two numbers at a time and the min of 50 and 49 in this case it 49 and it's going to keep doing this until it gets to the end of the list of inputs and it says okay ultimately at the end a list like this will say the minimum of 21 and 20 is 20 there's no more items in the list to check and so combine。

😡，呃。Combinine reports 20 basically anything where this comparison of two items can work independently combined is a really good option。

 so if we have a list of let's say boolean values we could say are all of these items in our list true by saying using something like and we could say is any true by using or we could find if we can find them min right we can find the max of a list。

😡，Those are the types of things that combine is really useful far on。

On individual lists where we're not talking about nesting lists， usually it's mathematical functions。

 combining and joining text together， things like Min Max， some。

 those are the types of operations that combine。😡，Is。It's really useful for。嗯。😊，Yeah， so that is。系。

Check Ed oh no， stay on that page。啊。I Chris个。Yeah， so that that's a little bit of。

How I would approach what we can do。With with combine other questions either in the room or on zoom about how how combined works from from these examples。

Yeah， go ahead。And。Oh yeah， so depending on the way the block is set up， you could， but what is my。

Once sec masses are here。This block。哎。This block right here only。啊。

Only it takes in two items at a time so if。诶。If we were to do something like this。

Snap is not really going to know how to handle this result。

So if a function really only takes two items as inputs we need to use。😡。

We need to use combine to handle that。In the case of。

 and now I have no idea if this is going to work。This minimum block。

Which accepts any number of inputs。Well， so this minimum block is not working for some reason。

 so I'm going to figure out。Why that is after lecture。

 but in theory if a block accepts a list as inputs， you can use that instead of combine。But。

It really depends on the specific function。OfOf the block and so it。Okay， yeah。

 I don't know why that's not cooperating。嗯。😊，Yeah， so most often with combined。

 that's what you would want to do， I will mention something like join。嗯。

Join is a really good case to think about how we might want to。Use combine。With join。

I can actually drop this list as an argument to join。And join。

 because it takes any number of of arguments， well just swish the text together。😡。

And so that can be really useful， but if I want to turn something into a sentence where there's a space between each word。

 what I would need to do with join a say give me a function which actually specifically has two blank input。

And in the middle， I get to choose to use a space， so it really depends on。On the function， what's。

What's allowed there？Yeah， that's a good question other questions on combined。Zoom chat。

 no questions yet。 Okay， cool。嗯。So。Few additional things。在。嗯。

We can do actually before before I pull up a previous quest， are there any questions in the room。

 just general topics that we have covered， yeah。Hyperblex， yeah， good question cool。

Let me just hide this out of the way。So make a new sprayrite right here， yeah。

 so hyper blockslocks are blocks and snap。That when given a list as an input to that block。

 do some operation with each item of the list and so。Again， we'll take our favorite。

Members from one to10 block。Because。That's pretty easy。We's take our plus block。And let's take a。

Now less than block。诶。And。Let's see。 Yeah， we can use the。Perhaps you can use the is a number block。

Numbers from one to 10， right pretty simple， one to 10， we're just going to keep using this。是。我。

If we think about so one thing is before we try Hyfl， right， if we think about domain and range。😡。

If I tell you that the plus block only accepts numbers as inputs， we would normally expect that。😡。

Adding a list。And a number results in an error and up until summer 2020， that was the case。嗯。

But what hyperblocks do is they say if I'm given a list。😡，And some other inputs。

 S will try and say what makes sense to do in this case。

 so the numbers one to 10 is a list of 10 items and with plus and five snap is going to say for each item of the list。

😡，Add five to that item。And。What this is really equivalent to。你啊。

It'sNot equivalent to dragging my window。嗯。These two expressions here。😡。

Numbers one to 10 plus five map plus five over the list numbers one to 10 are equivalent expressions because essentially what a hyperblock is doing。

😡，Is it's sort of taking a math expression and making it implicit in the way that。

That be the block operates so it really depends。 So in snap for the most part， we can say。

W duplicate this again， that hyper blocks if we give a function to lists instead of taking each item one to 10 and adding。

Just five， these two lists are the same length。And so what we get back is by adding the items of the list together item one。

 two， three， and so on， and so hyperblocks in this case。

Allow us to do operations with lists much more efficiently and they sort of reduce the amount of code that we need to write。

 but it's always going to try and do something with respect to each item of a list so。

I actually have no idea。What will happen here？Okay because it's only five items back so you know snaple let us do things like this。

 which is it won't give us an errorback， but in general if we're thinking about items one to 10 plus some other list。

What we want is to have two lists that are the same are the same size and the same type of data so all of our。

All of our operators should be hyperblocks， we could ask questions。like。Numbers one to 10。

Which of them are less than five。And so this is kind of an interesting list because we just get was a list of boolean values back and so what we see here right is one。

 two， three， and four。It is true that those are less than five， five and greater apart。

Great than or equal to five， so that expression is false。

 so anywhere that we can make some comparisons。You know， snap。

Snap would let us drop a list in like a predicate block， for example。Yeah。

 for the most part we're talking about mathematical operators are sort of where we'll limit the scope of hyperblocks。

 there are a few additional reporter blocks and SNAP that use hyperblocks。

 but we're not going to use those and if it's a command block you can't command blocks don't support hyperblock so you can't like drop a list into like a move block and have a sprite move a bunch of places。

So that is。Yeah， that's how hyperx works， but yeah， good。

 or if you have additional questions feel free to ask other questions。

 just general questions and then we'll spend some time going over some previous quests。一咩。Back there。

Okay。O。Yeah， so once sec let me got， so map map is always going to give us if we give a if we have map over a list of 10 items。

Map is always going to give us 10 items as a result。嗯。The way to think about math is。😡，呃。

For each item of the list， I'm always going to apply this function。😡，If。If this function is a number。

😡，Then what I should get back are numbers my output list。

But that list should always have the same number of items we can。嗯。你啊。

One way we can also do the same thing。Is a。Just to illustrate that this is indeed possible。

We can we can still map of a predicate so because of predicate reports。系 value。This works correctly。

U。But。We always get back 10 items， the range of our map function is a list where each on the list maps to the range of whatever our input block was。

 so if this is a predicate， then we'll have a list of booleyan values。Yeah。

Other questions in the room。They could be about hydro functions or anything else too。Okay。

 let's see what。啊啊。

![](img/65d7bfeed0b465833a59f3f755e31abd_9.png)

ok。在。

![](img/65d7bfeed0b465833a59f3f755e31abd_11.png)

Are there any operator blocks that can't be hyperfl I going move this？I'll to the aside for now。



![](img/65d7bfeed0b465833a59f3f755e31abd_13.png)

Are any operator blocks that can't be hyperpls right now？哎。Okay， one sec， where is my。First sir。

 I don't believe。I don't believe there are any built in operators that。Well， okay， so。Things like。

Split don't really make sense as a form of hyperblock so split takes in some text and it splits it by a word or spaces or whatever you want to。

😡，嗯。Split doesn't really make sense as a form of hyperblocks， so I don't believe it does。

Anything useful？Right now so that would be the one example。

 you get some really interesting results so。呃。I believe this still works。

Like letters one to three of a word will actually give you a list with those individual letters back。

 so there are places that support hyperblocks in kind of unexpected ways。But for the most part。

 I would say we're going to stick to things where we're thinking about items of a list and we're going to either be adding subtracting。

😡，You know， we might do something if it's a function。like。诶 the。

And these square root function over here， which has a bunch of operators right this function。

Of course， is something where we could just say give me a list of numbers。

 return the square root of each of these things。Those are the types of places that we're going to stick。

Two hyper blockslocks。Yeah。Good question though。You could I would also say another point is this won't help you on the quest。

 but in general， right， are there any operative blocks that aren't hyper of blocks？😡。

The other way to definitely try this or to answer this question snap is to just try things out。

It's impossible to you know seriously break something in Sap at least you might get an error。

 you the most you would have to do is refresh the browser page， but for the most part in snapap，😡。

you can click around and try anything and you'll find an answer。Yeah yeah， good questions there。

If anyone else on Zoom wants to a。Add questions in I'm happy to take those it looks like。Let's see。

Okay， cool。Nothing， nothing known Eddie yet， yeah， other question back there。Scoping， yeah， perfect。

Let's seeing how we're doing for time cool 15 minutes， so let's spend about。

A few minutes on scoping and then I can talk about some past quest questions。U。

One thing that I'll say is for the quest， we're not going to talk about scoping and lists because lists do have different rules。

😡，For scoping。But the rest of scoping with regular variables is in scope。So。Actually， before I。这样。

Two monitor fingers。Okay， computer， what are you doing today。There we go。

 so in snap variables exists in。A few different places。We have。诶。We have all sorts of。

Of different levels of variables that。That we have access to so the first thing， of course are。

Global variables， One thing is kind of nice about S is S doesn't explicitly tell you。

When a variable is global or whether it's a script variable。😡，Or a block variable。

 but if we look at a set block， we can sort of see up here。This thing is global。

We're not going to deal with any of the spr properties， but those are kind of interesting later on。

And within a script variable， if we have a set block attached beneath the script。😡。

We have access now。To all those additional script variables that we might declare。So I could say A。

This could be 100。One thing that's kind of neat about S as well。嗯。

You might kind of start to expect this after this using Snapbook。😡，If I have。Now。

 an additional set block。I drag it down here。Think about what you would expect to see in this dropdown of variables。

😡，So I take it in this case， we now have access to our global variable。

 our variable C and our variable A， so script variables， once they're declared。

 they're accessible to anything。😡，In the remainder。Of a that script and importantly， right。If I。

Do something like that over here。I cannot set the variables A or C to anything。😡，诶。

If I try and click on this， someone wants to shout out what do they think will happen。

 by try and click on this right now。What do you think this will do？A， yeah。

 yeah so a script variable rate or excuse a set block， if we're trying to set a script variable。

 if we drag it from somewhere else， it might still say set a to some value or set my variable to some value。

😡，But it's not going to let us perform that operation。

And so one of things to be mindful of is just because we see something。

That code might not be perfect， but if we were to go and try and update this block。

 we would see that A is not an option。That's。A pretty brief set about how script variables work。

 but they're only available within that script。嗯。If we define a variable with a new name。😡。

So we could change this thing again to a。And now we've just declared a twice。

 whatever we set A to most recently is a thing that takes the value。

IfNap will let you do something like this， there's not really good reason to。

 but we could just redefine A as many times as we needed， even though I would not recommend that。😡。

Scoping， though， however， gets。诶。Scoping gets most interesting。When we think about。How。呃。

How blocks work and this is a place where。嗯。We can definitely do things in SNap that are intentionally a little bit misleading。

If you want them to be， but in general， I think you can avoid。嗯。

Avoid Moosis so one thing I'll say is there's almost never reason to make a block that you would call change variable by something。

😡，And make it like work on global variables。Later in the semester， perhaps。

Wheres next there go we can talk about how to。Break the rules of scoping。That's not what I wanted。嗯。

So。Okay。Okay。我事。嗯。Oh。All right， so。What we're going to do is we're going to try and change our value A。

Let's say， by 50。And。我咩。Duplicate this all right， so and let me go ahead and make this look larger again。

呃。So with the rules of scoping。We start off， okay， that's not Laine's book。Before we have it's 100。

 we set it to 50 at the end it's back to 100， so every time we pass a regular variable into a block。

😡，What gets passed into the block is the value event variable。😡，Innence。This value a。is。干嘛啦。

Edit block， this value a is just the number 50 inside my new change block。

 the value variable or the name variable has the value 50。

 it probably should have named it something other than variable because like it's hard to talk about。

😡，And what happens is when I access update， modify。

Whatever words do you want to use the variable named variable。

 I'm only applying that change to this block， so that's because a sort of lives outside the block inside the block what we have is a new copy of that value and they are two distinct copies。

😡，With。In that case， so this applies to block variable block variables if of course we had。

A global variable。Over here， right where we said。Actually。Let's。Just。Changenge this as well。

 that might be a little bit。Simpler。Things that are global variables， we'll get to it。

We can then modify those anywhere within a block within any script， within。

 of course multiple sprites， so each sprite has access to all the things that we consider to be in that global list of variables。

😡，And for the most part， I think that those are。Those are the rules that you need to be aware of。

 one thing I'll add。So if we search for like。Or the word is。啊。Yeah。

 so if we get if we have like a four each block。each variable is also like a script variable that just lives within the context of this for each block。

诶 if i。哎。If I try and do something。Well， actually， let's grab。This。And I can grab a new set block。

I would not actually recommend that you do this with a set block because for a for loop。

 because the purpose of a for loop is to count numbers。

 but inside our for loop we have the ability to modify that variable I because it's essentially a script variable for that specific loop。

And really， the most important thing that I think about is anytime we make a block where we pass in a variable。

 we have a copy of that data。Yeah嗯。Yeah， okay， so that's a good question， Zoom。

 How does changing a variable to global affect it， So one thing to know in S is you can't change the value or excuse you can't。

嗯。😊，诶。We don't have an easy way in snap to say take this thing。😡，And make it oops。

And make it a global variable。But what we can do is。诶。

We could just make a new global variable with the name A。😡，And if we do this。

This is something that I am not going to run through all the rules of how SNAP handles this right now。

2。呃。The rules are pretty predictable， but snap snap essentially tries to use whatever is most recently defined。

 so this variable a is now different。From this variable a which should be different from a block with a variable a so scoping really lets us narrow down the focus of what our variables are。

 but the big thing that I would spend time on is when we have a new function or a new block。

 those variables are independent but。I can promise you for this time。

 but there won't be any ridiculously tricky scoping questions on the quest。The one last thing that。呃。

I was going to， and I'll add this link to the slides in the homep page later today。



![](img/65d7bfeed0b465833a59f3f755e31abd_15.png)

Cs10。org/resources。Slash exams。诶 f块。So all this links to the slides， but CS10。

org/resources/ examams has all of the past exams， which are public。All right so。

You can look at past Ques。嗯。

![](img/65d7bfeed0b465833a59f3f755e31abd_17.png)

I would start with some of the more recent ones， but something like fall 2019。



![](img/65d7bfeed0b465833a59f3f755e31abd_19.png)

Has a pretty reasonable representation of the types of things that you might expect。

This very last question here is a higher functions question which you'll probably want to like open the PDF and rotate the page if you're doing another computer。

 but I think this is a really good example of working through a higher function question。

And thinking about in an abstract way， what are all the possibilities of something that might happen so this question is asking you to consider。

😡，Any possible version of map， keep or Com？😡，Where is there any possible predicate function is there any possible combiner function or any possible map or function which allows this output to potentially exist so if you're looking for some good practice I would spend some time with this question because I think it goes through thinking through the process of you know which of these things are actually possible with with map key combined I'm not going to spend too much time putting up here but all the answers for these past quests。

😡，Are on so yeah good luck you know 50 minutes， 10 to 15 multiple choice questions won't be too bad it's only 20 points of your grade so need no need distress stress and please do a post on Ed if you have questions and we'll be sending out an email with logistics later today。

7even to 8 pm on zoom not7 to if you have accommodations it could be seven to nine。

 but it's a 150 minute exam， thank you。Yeah。Thanks everyone on Zoom， I'll see you tomorrow。



![](img/65d7bfeed0b465833a59f3f755e31abd_21.png)