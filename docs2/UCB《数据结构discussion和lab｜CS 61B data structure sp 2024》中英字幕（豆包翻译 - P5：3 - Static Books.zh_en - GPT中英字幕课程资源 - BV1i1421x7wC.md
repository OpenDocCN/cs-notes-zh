# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P5：3 - Static Books.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/3a2f1a93695fab433e565dc7b9eade34_0.png)

What is up， ladies and gentlemen， This is gonna be a walkthrough video for question 3 on C 6 U and B spring 2021 exam prep worksheet number two。

 or for week2。😊，Cool， so this problem is on the challenging side and it rigorously tests you's understanding of the keyword static。

😊，So before we dive in， let's first take a couple minutes to understand static methods and static variables。

😊，So right here we see a static variable。So what exactly is a static variable and how does it differ from instance variables？

😊，Which are these ones up here。These are instances and this is a static variable， okay。

So when we think about instance variables to put it very simply。

 an instance variable is specific to each instance of the class。😊。

What that means is every time we create a book， the title of that book is unique to that book。 right。

 On the other hand， when we think about static variables like the static variable last。😊。

A static variable is not specific to an instance。 It's specific to the class。

 So what that means is that all instances of a class all share the same static variables。

In this example， the static variable last will be shared with all instances of the book class。😊。

So if one instance decides to change the last static variable。

 then another instance who tries to access last。We'll see that changed version。Okay。

 so that's a quick introduction to static variables and instance variables。

 let's move on to static methods versus instance methods okay。😊，So right here。

 we see this is a static。Method， and then this is like an instance method。O。

So a static method in the same light， we could think about a static method as a method that belongs to the class。

😊，Again， an instance method belongs to an instance， okay？But。There's a couple like catches here。

An instance of a class has access to both instances。

Methods and variables and static methods and variables。 Okay， an instance。

 you can think about them as all powerful beings， they have access to static variables。

 They have access to non static variables。 Okay， on the other hand， if we ever have a class。

 let's say book。😊，And we're trying to access an instance variable。 let's say title。

 This isn't going to work。ok。We can think about I'll keep the colors going the same。

The class name only has access to static variables and methods， okay？And。In terms of code。

 it's often beneficial to make a method static if it's not really specific to an instance。

 it's rather specific to the whole class。😊，So that's a little spielel on static methods and instance methods as well as static variables and instance variabless。

 and there's a lot more intricacies that we'll explore in the following two parts。

 so let's get started with part A。😊，Cool。The first change that we will entertain is what if we change the total books variable to non static。

O。What that's actually going to look like。Is this total box variable。

We'll now lose that static modifier。ok。And we're going to ask ourselvesse， is this fine。

So in order to like figure out if it's fine or not。

 the intuitive way to solve this problem is let's look at all the places that the total books variable is currently getting called。

😊，O。😊，And we see right here is the only place。So if total books is non aesthetic static。

 are we allowed to access it in an instance method， right？And the answer to that is， yeah， right。

 you're allowed to access instance variables in instance methods。😊。

So we can see that this is totally fine， this will compile。Or this will allow the code to compile。

Nice， so jumping to the next instance or next。Like idea that we're entertaining is what if we make last book title non static。

🎼And now this is a method， so maybe it might be a bit different。

 So if we make this an instance method。We ask ourselveslf。

Is the stuff that I'm accessing in here allowed to be accessed in an instance method？😊。

So all that we're accessing in the code of last book title is a static。Invalable。

And we are allowed to access static variables in instance methods。

 right because instances of a class have access to static variables。😊，Cool。

So what we can see here is that。This will compile。Okay， I'm going to get a quick sip water。

Voice is tired。 My mouth is tired。 I'll be back。Okay， so。This probably seemed instantaneous to you。

 but I went， got water， and now I'm ready to tackle the next part。Okay， so for this next part。

 what we're going to be doing is we're going to change the add a book method to now be static。😊，Okay。

So what we're going to be doing more specifically is we will be adding the static keyword right here。

😊，O。Is this allowed。So this is actually not allowed。

 the reason it's not allowed is that we're not allowed to access instance variables in a static method。

😊，ok。We're not allowed to access the variable index。

 which is an instance variable in a static method。 The reason for that intuitively is。

 if we can invoke。A static method with the class name。Such as library。Dot add book。

It wouldn't make any sense for。The library class to have access to instance variables。

That just doesn't make any sense because an instance variable is specific to an instance。

 so if a class tries to access it the class is like I have no idea what you are。😊，ok。😊，So this。

Will air。Nice， looking at the next part， what we're going to be doing is changing the last variable to non static。

Okay， so how that looks is over here， we will change this last variable to now make it an instance variable。

 right， we're removing that static modifier。😊，How that's going to play out is in this method is the only method where we actually access the last variable and in here by that。

😊，So。And here it's actually totally fine to access an instance variable in the constructor。

 right 100% okay。😊，The problem that arises。He said this is a static method and we can't access。

Instance variables in a static method， so this will also error。ok。😊。

The last one is what if we make the library variable static？This is a very interesting case。

Right here we have this library variable， so what if we add in that static modifier？😊。

What's going to happen？Is right here。When we set library equal to null。

 that's totally fine because we're allowed to access static variables in the constructor， right？😊。

The one maybe potential complication you guys will see is right here， right。

 Are we allowed to access。A static variable width。An instance of a class。Right， so the answer here。

Is that this is actually allowed。 It's just not considered good programming practice。

 What that means is if we ever want to access a static variable。 in this case。

 library is hypothetically static。 we should access it using the class name just to be very clear as a programmer。

 So although。😊，This code works， it's not considered good practice， but it will compile。Cool。😊。

So this part was on the trickiert side， so congratulations if you guys got it。

Let's dive into the next part。ok。So part B， using the book and library classes from before。

 write the output of the main method below， if aligned errors。

 put the precise reason and errors and continue execution。😊。

So we have this main method right here and we to try to figure out like what's going to happen when we execute all of this code。

😊，ok。And2。Kind of visualize all of the components here。I kind of drew up this。

Starting diagram of where we can go off them， okay。

So all I did is I copied the book in library classes。

 I put them at the top and then what I did is I created。Some areas for gone Girlir fight club。

 and I also added in the static variables， book class and library class。

 and I put them at the top okay。So。After diving in， the first thing that we're going to do here。

Is we're going to try to access or try to execute these three lines。

So the first thing that we do is we try accessing library。

total books and these both have been set to null and zero respectively so when we access total books off the library class。

That's totally fine because total books is a static variable and we're allow it to access it。

So this will print out。0。The next two ones are a bit。Tricky， so when we do book do last book title。

 what's going to happen is that we will call this method。

And we're totally allowed to call this method， right， It's a static method。

 The problem that arises is that last is currently set to null。

And you're not allowed to access an attribute of a null object， right， Intuly。

 that should also make sense because。If something is null， it doesn't have a dot title， right。

 So this will error and more rigorously。It will。嗯。Throw this thing called a null。Pointer。Exception。系。

So moving on to the next one， this one errors and it's a bit simpler why it errors is that you're not allowed to access instance methods with the class name。

So this is air， and then we could put for the reason， not allowed。To access。Instance。Methods。Oh， man。

With class。Okay， notability is getting mad at me for some reason。Okay。

 so that's the reason it errors and just to keep things a bit more clean， I'm going to erase this。😊。

Always put error and then for like the sake of conciseness， will always put compile error。Okay。

 moving on to the next part， we see here that we're going to create two book instances。

 goneone Girl and fight club。Brief aside， gone Girl is a good book， it's a little twisted。

 but I recommend。ok。So over here， we create two book instances， gone go。

 And let's just walk through this constructor。 So we see what happens when we actually create a book。

 We set the title equal to。😊，Gone， girl。We set last， which is a static variable equal to this。

So what is this in Java， This refers to the current object。 Okay， in this case。

 the current object is。啊。嗯。This book instance。So what we do when we set last equal to this is now last is pointing to gone girl as the book object。

 okay？And then we could set Gon Girl's library as null because it hasn't been added to any library yet。

ok。😊，So after creating fightight Club， what we will do is set the title of fightight Club。

To fight club。We will set the library。To know。Right， and then we will set last to now point。

If I club， okay？The order was actually different， we do the last first。

 we do the last before library， but doesn't really matter。😊，Okay， cool。

So now we can tackle these four parts right here。Extracting gone Girl's title shouldn't be too tricky。

 We just do gone。Girl， right， comes in right here。The next parts may get a bit trickier。

 So what we're doing next is that we extract。Or we call the static method last book title。

The last book， title， static method， all that it does is that it returns the title off the static variable last。

😊，So the static variable will last。After creating F club， right。

 recall that we set it equal to fight club， which I missed the air before。😊，Okay。

 so what we're going to do is。Return fight club's title， right， which is fight club。And then。

What we'll notice is that for this next part。We're basically doing the exact same thing we did before。

 Now， instead of invoking the last book title with the class name。

 we're invoking the last book title method with this。😊，Instance， right with fight club。

 which is an instance。So it's actually just going to do the same exact thing。

 they're just two different ways of invoking the same method， which produces the same result。😊，Cool。

And then what we're going to notice here is that gone girl dot last。

 This is a bit trick here is the static variable last。

Right which is shared by all instances of the book class。 so goil dot last is actually。😊。

That fight club instance。 So when we extract the title， we're just really。Extracting the fight club。

Trade。Cool。So moving on to the next part， now we're diving into the world of libraries， right。

 we're creating two libraries， library A and Library B。😊，Right， library A。

Willll have a books array of length 1。 So over here。We will create the books array of length 1。

Let's see what else this library constructor does。The library constructor also。

Setets index equal to zero。An index is just used to tell us where we should put the next book in the book survey。

ok。So what we see here is that。The index。Will be zero， okay。And then similarly。

 when we create library2， its book survey is of length2， and index is zero for it。ok。

Then what we're going to do is we're going to call library a do a book gone Girl。

What that's going to do is。To this books array， we will add goal。Right。More precisely。

 we're going to execute this a book method。Which sets books at that index equal to book。

 which is that first thing I did。 The next thing that we do is we increment the index。

 We increment total books。😊，Right let's do those quickly。Incrementing total books。

Total books is now one。And we increment the index。Let's keep the index。At one。Right。

 and then the next thing that we do is we set the library of gone girl。

 which is the book that we just added equal to this。😊，What is this， this is the current library。8。

 library A。So right here， what we're going to do is set G Girl's library to point to library A。O。

Because we added G girl to Library A。So this corresponds to library A。

Now what we're going to do is print out library As index and library A's total books。

So the index of library A is one。The total books static variable。

We're allowed to access static variables through an instance， not considered good practice。

 but we're allowed to do it。😊，It is going to be one。Let's put that in black just for。

Consistency of coloring。Okay， so right here， this is also one cool。

The next thing that we're going to be doing is we set library A do total books equal to 0。

What is that doing， it's setting the static variable total books。

 which is shared amongst all instances of the library class。😊，Right equal to zero。

 So what that's doing is's turning make this variable to zero。The next thing that we do。

Is we add two books to the library B， We add fight club and gone girl in that order respectively in that order。

 Okay， so how that's gonna pan out。We'll use purple because there's a lot at play here。

Instead so we first call add a book on F Clubub。What that does。Is we add five club。

And then we're going to increment the index and total books。So。This becomes one。

And then this becomes。Still one， I bad。 I meant to change this index。说完了。

And then we set the library of fight club。Let's use purple steel chair。To be。Library B， right。

 Then we're going to do the same thing with gone girl， right。Sorry if this gets a bit repetitive。

 but I'll try to be very precise。So we add gone girl。To this array。

 the next thing that we do is that。We increment total books and index， right。

The next thing and final thing that we do is that we're going to change the library of Ggo， right？

Right now go and Girl and fight club are both part of library B。Finally。

 let's walk through these statements right here。 libraryb。

 indexdex is simply going to be two right That is the index of library B right now。😊。

When we look at libraryb。toal books， that's going to be accessing the static variable total books。

Right。😊，Which is currently set us two？You can see that it's currently set to two right here。ok。

Finally， what we're going to be doing is we're going to be accessing the library attribute of Ggo right。

 so let's figure out what that is。😊，We know that gone Girls library。Is library B。ok。😊。

So we can say that gone girlir。lib is library B。

![](img/3a2f1a93695fab433e565dc7b9eade34_2.png)

Now what we're going to be doing is accessing the book Sur at index0。Right， so this。Right。

 gives us fight club。Because the first element in this boxer array is。Fight club。

And then we're going to be accessing the title of F Club， which gives us P Club here。😊，Cool。😊。

So that is all for CS631b Spring 2021 exam prep worksheet number two。

 Thank you guys for watching and I'll see you guys next week。😊。

