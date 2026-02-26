# 004：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p04 4 CS169 4.zh_en -BV1UsB7YPEMj_p4-

Thank。

![](img/188385e4e33c07762ebb26c392632fa9_1.png)

All right， so let's get started。Little bit dwindling lecture attendance。

 So that will probably change because Thursday there will be a micro quiz。

 They will not always be announced， but we'll try to announce them just so people aren't like too surprised。

But。Sort of short one question on material so far， it should only take you a minute or two to answer。

 but so don't stress about it。And as a reminder， microquizzes are。You know。

 like they are a very small component of your grade。 So if you answer， you know。

 a reasonable portion of them correctly throughout the semester。

 then you'll get full credits for that。 We don't expect you to get every single one right， we。

 you know， are okay if you miss a lecture or two。But， you know。

 they should be there for attendance and tracking。 So the other thing that we're gonna try。

 And if this ends up working out， you can tell your other professors that it might be fun to try。

 But this is a throwable microphone。 So if you have a question， we can kind of just pass it around。

 But the top here is a mic。 So if you just so speaking to it， it'll record your voice。

 And then the thing that's useful for that is on a webcast， people can hear a question。

 So if you want to say something insulting on the webcast， you no longer have that option。

 But otherwise， you know， you can pass it around。 And if someone has a question。

 you can just toss it to them。 It's very squishy and very light。 so。😊，It's easy to pass around。

 but I'm just going to hand this to Jeremy so。You know， he'll have that。

 And then when someone has a question， you can pass it around。 It also auto mutes while you toss it。

 So that's kind of fun。😊，And。As far as some other colleagues I've heard。

 no one has died yet by being hit by one。

![](img/188385e4e33c07762ebb26c392632fa9_3.png)

You know， progress。 But yeah。 So let's get started today。

 We're going to start off with that should actually say Ruby and R， not Snacha。 We will be doing。



![](img/188385e4e33c07762ebb26c392632fa9_5.png)

Also， actually， take that back。 We will not be using these slides because those are。

 those are the start of Thursday's slides。

![](img/188385e4e33c07762ebb26c392632fa9_7.png)

嗯。Hey， where do my slides go？well， I didn't do that right。All。

 so aside from the fact that I misnumb of the slides。

 we're gonna to start off today with some Ruby and this is a fun video that hopefully cooperates。

 It is about five minutes long。 don't worry about the actual rubby in this video。

 but just as a reminder of how fun and odd programming languages are， we're gonna play this。😊。



![](img/188385e4e33c07762ebb26c392632fa9_9.png)

Hi， good。

![](img/188385e4e33c07762ebb26c392632fa9_11.png)

You guys know what Wt means？

![](img/188385e4e33c07762ebb26c392632fa9_13.png)

W。Exactly， exactly。Let's talk about Ruby。And Ruby。If you reference an undefined variable， of course。

 it name errors as you would expect， and if you try to assign B to a with them undefined， of course。

 it name errors as you would expect， and what happens if you try to assign a to a with a undefined。

 correct？No。Wt？Let's talk about Ruby。Ruby， unlike some other dynamic languages does not have bare words。

 so you cannot just type words in and have strings come out unless you define a particular method missing that does the right thing。

 and then if you type bare words， suddenly Ruby sports bare words and in fact it will even support bare words with bangs in them。

And this is not deserving of what， this is actually a result of how awesome Ruby is。



![](img/188385e4e33c07762ebb26c392632fa9_15.png)

![](img/188385e4e33c07762ebb26c392632fa9_16.png)

But if you ever actually do this， then wh？Let's talk about JavaScript。😀。😊。

Does anyone know in JavaScript what array plus array， Well， let me ask you this first。

 What should array plus array be empty array， I would also accept type error。

 That is not what array plus array is wrong， wrong， array plus array is empty string。Obviously。

 I think that the thing that's obvious to everyone Now what would a rate cause object be。

 this should obviously be type error because those are completely disparate types。

 Does anyone know what this is？No， close， no， far away。It's object。 right right， Nice done。 Now。

 of course， because this is plus， so you can flip the operarans and the same thing comes out。

 So if we do what， no， that's just an object。 If you do object plus array。

 you get exactly the same thing， which as you can see， you do。😊，は。And finally。

 the only one of these that's actually true is because， you。

 you add a array you get empty string that doesn't make sense。

 but an object plus an object is actually not a number technically。So this one's actually right。



![](img/188385e4e33c07762ebb26c392632fa9_18.png)

And exactly right， like what is even going on in this。

 just I don't even understand what Carson with a brain in their head would think that any of this is a good idea。



![](img/188385e4e33c07762ebb26c392632fa9_20.png)

あ。Okay， okay， enough making fun of language isn that suck。 Let's talk about jascript。

If I say array dot new 16 or just array 16， I get an array of 16 things。

 which it represents as 16 commas， which is obvious。And。If I then join those with a string。

 then I get this string 16 times。 This is actually the only line in this entire presentation that's reasonable。

 Now， if I take that string and then add a one to it。

 it interprets the one as cast the one to a string and then we get wt one a bunch of times fine。

 Does anyone know what will happen if I subtract one from the string。😊，I'm assuming no one does。

 me I'll give you a hint， does this help？Does anyone know？Yeah。



![](img/188385e4e33c07762ebb26c392632fa9_22.png)

Blat now。That's all I got， thank you guys。

![](img/188385e4e33c07762ebb26c392632fa9_24.png)

So。Oh。系。Okay， okay， it's back now。 So aside with the fact that that's funny。

 you don't need to know about the specifics of what was shown there， but。

Point being that in this course you will get experience with Ruby。

 we will not be teaching you very much JavaScript， but you will definitely get experience with a bunch of JavaScript when it comes to the frontend components of our projects both of them I think are amazing languages and both of them have significant quirks today when we talk about Ruby。

 we're going to talk about some of the more fun things of Ruby some of the things that if you focus on the simple elements of Ruby actually will help you sort of simplify and understand what's going on。

B point being that every language has its oddities。 neither of these are white space sensitive。

 So you can say， you know， inconsistent tabs and spaces and kiss that air goodbye。

 which makes me very happy。😊，But you know， you trade that for some other things。

 So Ruby inherits like pretty much all modern languages from previous languages that existed so。

Adele Goldberg and Aen Ka developed small talk in the 70s。 Alan K was they were both at Xerox Park。

 Alllan Ka is also famous for developing some of the original graphical user interfaces that。😊。

End up becoming the basis for the Macintosh in the 80s and Windows。

 So sort of the very ancestors of what modern computing looks like among many other achievements that he's done。

 But small talk is this kind of odd language， but it's very object oriented。

 It has some really cool object hierarchies and exploration。

 and the place that it actually lives on sort of most directly，😊。

Or that I would say most people have seen something is objective C if you're doing iOS or Macintosh programming。

 objective C is kind of taking pure C that you know and probably don't love。

 but some people certainly do and adding all the object bits from small talk on top of it。

 So small talk use square braces， message passing those were things that you would see there。

So Ruby inherits a lot of those ideas， but in a little bit more different syntax。

 but the objectness is definitely a key thing。 So we're going go through this kind of quickly。

 The homework will give you sort of practice with these。 Please start that if you haven't。嗯。But。

 you know， there are a bunch of things。 So in Ruby， technically， there are no， you know。

 there are no declarations。 you， you create a variable， you assign it。

 you use it all in one time time frame。 These are all okay。 You can do multiple。 You know。

 you can assign a variable to anything。 You don't need to tell it a type。

Arays use square brackets like most modern languages do these things with a colon are symbols which are basically immutable strings。

 you will become very familiar with symbols。 they are a great way to have some structure to your data without necessarily。

 you know creating a formalized constant or without you know creating。An enum or something like that。

 although all those things are options。 So hashes use curly braces。

 they are mapping of keys and values like other languages。

 you know keys in hashes can be strings or symbols and they can have anything as their value so it all works pretty similar whoops did not mean to go back there。

 And you know thearrow syntax， sometimes called a hash rocket because I guess it looks a little bit like a rocket and unsl or using a colon both work equally well。

 it's sort of whatever you prefer when you work on projects。

 I would kind of try to push in the direction of sticking with whatever style that project is in just because it is a little bit more readable but you both of these options work。

 I tend to prefer the second one just because it's a little bit easier to type but totally your preference。

 So in Ruby， this is the important thing。 everything is a method call。😊，When you do A dot B。😡。

B is a method of the object A， so。If there's one rule to take away from sort of debugging Ruby understanding what's going on。

 this is an important one because it's very simple， but because of that。

 it means that it's also very powerful in what you can do so。B is a method of a。

 So what this importantly does not mean no B cannot be an instance variable。

 it's not a class variable， it's not you know some other hidden property。😡。

B is a method of the object A， it is not you know。Something else and we'll see in fact。

 a little bit how Ruby interprets some method calls。You know， it's not a data structure。

 There are interesting things when we get to some data structures of how those methods are implemented but。

You know， if you're， if you see A dot B， my class dot initialize， you know， student dot first name。

 those things are all methods。 they will often manifest themselves in ways that look like variable。

 So Ruby has。Ways of doing setters and getters。 Ex me， and so。We'll see some of those。

 but everything is a method call， so just remember that。

So Ruby has classes and that build did not work。 So we'll get to the clicker question in a second。

 But classes in Ruby are pretty simple。 They work a lot like classes do in other languages。

 there are two things that are important here。 So initialize every class。

Can have an initialized method。 and that is the main way that you start making a class in Ruby。

 So if we wanted a new savings account， the savings account has this initialized method。

 we would call this with savings account do new。And that would give us a new instance of the savings account。

 and we can go through this as well。 We'll do a demo in a second。 But then importantly。

 if we want to update our balance， we have an instance variable with the at sign。

 So a single at is an instance variable in Ruby， so。😊，We create our account with a starting balance。

 we read the balance by having a method called balance that just returns the value of the instance variable。

 and we update our balance by setting it to a new value。Now。

 what's also worth mentioning is that Ruby has implicit returns。

 So the last line of a method in Ruby， you can just add the keyword return and that is what the method will return。

 So this method here name balance returns the value of the balance instance variable if you wrote the word return there right before it would behave exactly the same way。

 one of the things that Ruby tries to call itself is that it's optimized for programmer happiness and while there is a wide array of implementations of what programmer happiness means One of the things that Ruby tries to do is get out of your way。

 So the return being optional。😊，Is one of those things that a lot of people really like。

 It can be a little bit confusing at first。 but so when you get to a line， you know。

 where a function is going to stop， just insert the word return there。 And you know。

 that's the value that will be returned by the function。 that can be nil。

 but it could be anything else。 So we you're going to go ahead and play around with some ruby。



![](img/188385e4e33c07762ebb26c392632fa9_26.png)

And what I'm going to do is just paste this in an interpreter。



![](img/188385e4e33c07762ebb26c392632fa9_28.png)

So IRB， the Ruby interpreter， this class inherits from an account。

 so what we're just going to do to make sure that there's no errors is create a very simple class called Ac count that doesn't really do anything and I'm going to go ahead and paste in our savings account and it just outputs some basic error。

Yeah， if we want a new savings account。Where you can just call do new。

And it's gonna to give me an error because I didn't pass in the argument that was required。

 So we're not going to go through all the details， but if an argument doesn't have an equal sign after it。

 it's going to be a required argument， Ruby supports optional arguments。

 It supports keyword arguments。 it supports array arguments。

 So similar to star args and star star Kw as normally and Python Ruby has sort of the same kind of conventions around there。

 But yeah， so if you don't see anything to indicate otherwise a method an argument will be required。

 and let's say I start off with 100。 and I get back a savings account instance so。So far。

 that makes sense。 You know， I get back a Sam's account and。I can do count top balance。

 and I get back that value。So far， pretty standard， I have a method。And I can read back the value。

What I can also do is。诶。So。So let's say I want to update the balance in this account， right。

 So I am going to insert a new amount。 This method is special。 It has an equal sign。

 So this is commonly referred to as a set method， similar convention to Python， so。

What it could do is this， please don't actually write your code this way。

 but to show you what's going on。You know， let's give myself a lot of money because wouldn't that be nice？

I put a new number。 I do account dot balance equals this。 It's a method。 I call it with parentheses。

 And， you know， I have given myself more money。 We can verify that this works by calling account dot balance。

 and if。Assuming that I type things correctly。You know， it will what？All right， wow。呃。There we go。

Yeah， so plenty of typo while programming that is par for the course。 We all do it。

 But so I get back the new value。 So calling a method with。You know， equals like this is pretty ugly。

 You wouldn't want to do this to assign values all the time。

 So Ruby does a bunch of nice things for you。 What I'm going to do is this。

You know and I can even remove the parentheses and Ruby does some really fun things with numbers So this is just a trick for readability if I really want to you know have a lot of fun here so you can put underscores in numbers to just make them readable you can't put commas in number literals but I can just separate things out and so right now I have an account with a ton of money and classes canceled for the rest of the semester I'm kidding。

😊，But you， so what Ruby did here is。It took the method name equals and four equals and a few methods there。

😡，It knows some things about how to handle spacing， but so balance space equals。

 translates to the method balance equals， and then parentheses in Ruby are optional。If we did。

You know， let's say count2 equals savings。Account dot new。So in this case。

 this is a more typical method call savings account dot new of 500。 We get a new savings account。

 So parentheses in Ruby are optional。 The general convention that I tend to follow is methods where you are using the return value。

 So in this case， I am using the return value。 You should use parentheses methods where you're kind of discarding it。

 that you're treating as sort of at。A bare language feature， a primitive。 You'll see these in Ruby。

 You'll see an example with the method ater accessor in the next slide。 You know。

 you can leave them off but。You know， parentheses optional are being nice when it sort of makes the code easy to read。

 but if you ever start stacking multiple method calls， if you have complex boolean expressions。

Please just insert the parentheses because it makes the logic way more clear as to what is actually being passed into which method。

You know， they sort of stack right word and then go left right。 So if I had multiple methods。

 we would put the parentheses on the right first and then keep going forward。

 which I guess I should probably do it this way since you're facing me。

But if you have multiple method calls， I would certainly encourage you to use the parentheses there。

And just if you ever get stuck， you see a bunch of code without with a method name or some key what looks like a language keyword and some value on the right side of it。

 insert parentheses because it's almost certainly a method that theheses are just optional。诶。

 this is some basic ruby。Some other things that are really useful just to know while you're exploring Ruby。

 Ruby has a lot of really good introspection features。 So every object has a method named methods。

 And this returns an array of methods that this object responds to。

 So you can do this throughout the entire sort of， you know， set of methods。

 So the number one is an object。 So numbers are also objects。 it。😊。

And I can call methods on the number one。 I could do this for any number as well。 but you can see。

 you know， it responds to some common methods， star， star equals。You know。

 all the things that you might expect and then a bunch of， you know， other random methods。

 So one thing that's interesting。 So I can do one plus2， right， This gives us back 3。

 No surprises there。Because everything is a method， the plus operator， which is。

In the list up there is a method on one。 So this is equivalent to the syntax1 dot plus inns 2。

And that gives us back 3。 So what Ruby is actually doing。

 because it is very tolerant of spaces and optional parentheses。

 One plus 2 is the equivalent of one dot plus 2 in parentheses。 And now you can see why。😊，You know。

 the， the cases for always using parentheses is definitely， you know。

 you're not gonna always use them， like， have some common sense here。

 No one should ever write the following last line other than to demo and understand what Ruby is you know。

 doing。 because it just looks odd。1 plus 2 is a lot clear， you know。

 it helps you just get the distracting syntax out of the way。 But if you're wondering， you know。

 what happens when I do something like， you know。Hello plus three， right？Yeah， what， like what。

 what does Ruby do when there are mixed types。 Well， what does the plus method on the string do。

 And we could just， you know， run it to to， But it doesn't like that because hello plus 3， you know。

 it， the， the plus method on string is going to warn us that。Now we can't do this， but of course。

 we could， you know。Add the word world here。 And the plus method on string does the right thing。

 But where did that error come from， It came from the plus method that is defined on the string class。

 So if you're ever wondering， you know， when I call something。

 when I have this operator it is a method that is called on the left side of the operator with the arguments on the right side。

 So whether this is， you know， equals method， an exponent of floor， whatever， you know， you can。

You can do that。 so that is a little bit of ruby， and we're going to jump back over here。



![](img/188385e4e33c07762ebb26c392632fa9_30.png)

![](img/188385e4e33c07762ebb26c392632fa9_31.png)

And so when we talk about instance variables in Ruby， So we're going vote。

 and then we'll have you talk with。Partre say voting is open which of the following。

Options are correct for how we would access the balance value of this account。

And especially something I just showed you the video。

 but do always remember that E is the option for what is the option for I want more clarification。

 let's take a step back。Always available， no harm in selecting it。Yeah， that's a good question。 Yeah。

Just like the map that's connected to our。So。I believe if you use the Icler app。

 you would have to pay for it。Oh so it， so it's a two week free trial， I think。 or if， yeah。 So yeah。

 you can use it for like the two weeks or whatever if you forget。

 right then you probably don't want to pay for both。

 but you can also miss like the way the I clicker works is that if you're attending most of the lectures。

 you'll get like the maximum credit within the eye clicker category。

 So if you ever forget a couple times， it's not gonna be a big deal。Yeah。Cool。

 so we have about 60 responses， and that's not bad。 So if you can still get eye clickers。

 that's good。こ。So most of you selected C so。Which ones are correct， so yeah。C options， two and three。

 so。Basically， yeah， my account do app balance is not going to work because there is no method named app balance。

 We can do a few things to explore this， but。

![](img/188385e4e33c07762ebb26c392632fa9_33.png)

The first thing that's， you know。Pretty。Pretty clear when we say there's no method is my account to app balance。

Is going to tell us a couple things。 So in Ruby， it actually knows。

That methods cannot start with an at symbol。 So things that start with a single at are reserved for instance variables of a class。

 Things that start with two at are static or class variables。 They are not at ads， like in Star Wars。

 but。You know， so Ruby tells us in this case it's a syntax error because there's no。

 because it's not allowed。 So you can't even define this method if you wanted to and。

But because it's an instance variable， we would just access it using the balance method。

 and then because parentheses are optional。

![](img/188385e4e33c07762ebb26c392632fa9_35.png)

You know， both two and three work。 you know， again。

 normally the convention is for a method that doesn't take any arguments where you're just returning the value。

 you would just leave off those parentheses。 but I've seen apps kind of pick whichever convention and they kind of go with it。

 It's really up to you。 So。We have these two methods balance and balance equals and you。

You can imagine that in our own applications， we're going to be doing this a lot， right。

 we have a property of let's say a student， we have a first name， a last name。Maybe an email address。

And。We want to be able to update that。 So what we can do is we can take all that code and replace it with this one method at our accessor。

 so。What is adder accessor， It is a rubby method that is part of the Ruby standard library。

 and it does the work of defining the same two methods。 So this becomes ater accessor balance。

 So adder accessor defines two methods balance and balance equals they take an argument in the case of balance equals and it will set that to the balance instance variable。

 So the instance variable is going to be the same name as your method name to keep things consistent So。

In this case， you know， we could。Yeah， we would，d automatically be using the same instance variable。

 and we can kind of prove this by。

![](img/188385e4e33c07762ebb26c392632fa9_37.png)

Actually， let's do one thing really quick just so that we have a different class for clarity。



![](img/188385e4e33c07762ebb26c392632fa9_39.png)

So I'm going to paste this in， we have savingsaving account2。And so。You know， account three equals。

So we start this account with a little bit of money。And we do account three dot methods。

And what we see here is we start off with a balance and a balance equals method。

 So what adder accessor did is it took the symbol that was balance。

 So it is roughly an immutable string。 You could pass it an actual string name balance。

 and it created two methods balance and balance equals。

 Both of those update the same instance variable。 So， you know， I could do。Account3。Whoops。Yeah。

 set it to three。And then if I go back and access the balance， it's updated that variable for me。

 So you， if you're writing your own classes， can take advantage of this。

 There is a similar method to adder accessor called adder reader。

 which just defines the getter method。But， you know， for， for the most part， when you're writing。



![](img/188385e4e33c07762ebb26c392632fa9_41.png)

When you're working on， you know， your applications and your writing classes at our accessor will do what you need when you get to rails。

 Ras provides a whole bunch of stuff that is an additional level of meta programming that will go ahead and define。



![](img/188385e4e33c07762ebb26c392632fa9_43.png)

All these methods for you。 So most of your applications are going to be connected to a database。

 In fact， I believe all of them should be。 And so each row in your database will correspond to an instance of some class right so a student will have you know a name and email and so on。

 there will be a student class。 and so student dot name would return the value that is in the database student do name equals will be a method that rails defines that will actually update the value and that database and then it also ends up defining methods like save and update so that you actually persist the data。

 but rails takes it a step farther and will even define your basic setters and getters for you but。

You know， in the spirit of programmer happiness， you， take these six lines， turn them into one line。

 and you're good to go。And because you could do just about anything in Ruby。

 you could even overwrite at our accessor to do your own stuff。 I would not recommend that。

 but Ruby will let you sort of do your own thing there。So。Clicker question。Let's open it up again。

All right， so which？Of these， is it legal， illegal and why。

 So all plausible reasons for why it might be illegal， why it might be legal。 So take。

Read through them， and then。I will vote and then we'll check in with your peers。Cool， so we have。

 I believe that's a cool。 It's a little bit more than what we got to last time。

 There is a nice power of two。 And so here is the distribution so far。 So pretty interesting。

 some good votes for everything。 We'll go ahead and review this at the end。 but talk to your con。

 talk to your peers and convince them why you are right or wrong。

 and then we'll start a new set of voting。 So take about a minute or so and talk of the options。😊。

あります。Yeah yeah。呢。あそだ。反嚟。过。Yeah。から如。我收而且。第个。Yeah。相序的道理啊这个案子表示。果唔。あです。三十万啦。我。我。啊，系有嘅。咁。系。Do inquiry。

It very。は。きま。这も。All right， so if you have a clicker， keep on voting。

So the voting is open and then we'll go ahead and review this together。

But revote if you get a chance。See if we can get a couple more in。Okay， seems to be stabilizing。

 so we'll call it there。Nice， Sue。D is， in fact， the correct answer for this one。

They're all very reasonable。 So let's go through them。

 So option A illegal because a getter method must have the same name as the instance variable。

 in general， I would encourage you to follow that convention。 if a getter method is。

Returning exactly the data that is in the instance variable。

 then you should probably name it the same way， but because。Everything is a method on an object。

 We can have a method that returns anything that we want。

 So there's no distinction in Ruby about necessarily setters and getters as methods。

 they can set any data they want。 In fact， the balance equals method could set a variable an instance variable that is not all name balance。

 it could set a whole bunch of things， it can do some additional checks。

 know if you are writing a real bank account class。

 where real still means you know some more realistic but not an actual bank account example。

 you would probably do some checks。 know that the person actually owns the account that they're not inserting too much money if they withdraw money you would check that you can't overdraft your bank account and something like that。

 So the methods themselves can do whatever they really need to do and they can access and return data So there's nothing particularly special in this case about setters and getters。

So， yeah， and because of that， the fact that they must return a raw value， you can， you。

 generally modify that data。 So option C， so。You know。

 you can also use student name to get the raw value of the student name instance variable based on only these five lines of code。

 there is no student name method。 So based on the example here， that's not an option。

 If you were doing this， you could certainly define a student name method to return the raw value。

 then you would have a name method and a student name method。 and you would have to wrestle with。

 you know， which one to use when。The unfortunate reality of， you know。

 legacy software and real world applications is that there will be plenty of cases where you have a name method and a student name method。

 I may pull up some grade scope examples later in the semester。Seeing what I can。

 But what I will tell you is that that is actually a pretty common case。 We have an original name。

 a full name， a first name， a last name， and just a name。

 depending on where in the application you are。 And it is something you have to keep straight， but。

 you know。Coode isn't always as perfect as we want it to be。

 so you know Ruby and Rails will sort of let you do whatever you want and it's legal for the objects that we said。

 So you know if the convention that I would encourage you is that if you're modifying return the attribute or the instance variable to you know so in this case to capitalize it。

 then a separate method name is more common， but you absolutely could define a setter for student name that capitalized it before returning the value but usually this is a fairly common convention the applications go through so questions on this so far。

Any questions？Okay。H。That is a bit about Ruby。 So this is Bertra and Meyer。

 who is another famous software engineer。 And this is one of the things that also inherits a little bit from small talk。

 But the idea of this is known as a uniform access principle。

 which is that there is one way to get at something within an object。

 And that one way to get at something is through a method。 And so everything you know。

 in Ruby is an object and setting and accessing values on those objects requires doing it through a method。

 So the uniform access principle basically just says that， you know。

 there should be one consistent way to do that。 And for， you know， the quirks that Ruby has。

 this is one piece that is incredibly consistent。 A do B is。😊，Calling method B on the object A。

 you know， A dot B equals C is a B equals method so you can。You know。

 name methods if you want to look into it things like an array where square brackets。

 there is a method name square brackets on the array class。

 There's also a method named square brackets equals So array brackets 4 equals， you know。

100 is calling a method on the array object， So， you know， Ruby takes this pretty deep into its core。

 And you know， when you use Ruby， it feels a lot like another language。

 But if you're trying to work through a problem debu that is where you can remember that。 So，😊。

Another ruby question that we can go through， so let's see if it's open。Come on， I clicker。

reallyally， because you worked like a minute ago。

![](img/188385e4e33c07762ebb26c392632fa9_45.png)

Okay， well。That's interesting。Oh I just stop in the middle of class。

For an application that's very simple， it sure complains a lot。



![](img/188385e4e33c07762ebb26c392632fa9_47.png)

Okay， now it is open。And people are going，So which of the following is false regarding expressions in Ruby？

Cool， so we have just about everyone in。And we have a pretty wide range of answers。

 so spend about 30 seconds and talk with a peer and then we'll just go through a live demo to work out the options for this one。

 so take 30 seconds talk with your peer if you have your laptop open。

 you don't need to open it if it's not already open。

 but I encourage you to see if you can answer at least some of these by just trying it out because that's what we'll do。

咗。对呀小二块钱的。gracious。我哋而家关注系你全体公司啊。做。I。系。Yeah。し。あ。会管啦。这也是。街公司你。嗰度有系发。就。我哋该都。飞。Yeah。哦呀。个最信就。佢系咧。意啊知啊。

It wasVR。系我我嘢。あ。他。ありがごいありがとうござ。います。系。来点。系呢个。你。Yeah。も回。かね。咁个就家。All right， so if you can。

 let's start voting and then we'll go through and we'll work some of these out。

See if we get 10 more votes in。All right， so that's about 60。And okay。

 so most people are going for a B。 Let's go through these options here。

 So we're going jump over to the interpreter and then we'll start with the and work our way up。



![](img/188385e4e33c07762ebb26c392632fa9_49.png)

So。A Ruby interpreter。So。Nil， niil is the special value in Ruby， so I guess start starting with C。

 but whatever， just because we'll need that， so how do we test this。If noil。Puts， yes。Else。

It's going to bug me about that。Oh系。New。not。 What am I got。 I'm not awake today。Yeah。

 this is the problem with teaching two classes that used to different languages。嗯。

But the good thing is， computers tell you when they get mad at you。 So nil is falsey， right。

 that is that makes sense。 So the object， the options in。

In part D we're around zero and the empty string， so the other thing that we can do is use the ternary operator。

 right。诶。Oh， hey， what are you mad at me for？Fine， I don't know why you don't like that。Yeah。I not。

Or I can I dieer。So the empty string in this case is something that Ruby treats as truthy。

 and that is。One of those， so let's see about zero。Zero is also truthy。 So option D。

 if we go back to it， nil and false evaluate to bullolean false everything else。

 including zero and the empty string evaluate to bullolean truth。

 So this is one of those ruby rules that will get you compared to a language like C when we start doing JavaScriptscript and you start working on the frontend stuff it will also get you because JavaScriptscript has different rules。

 In fact， JavaScriptscript has so many rules with truthy and falsey you know。

 you'll get to experience those for as long as you know you do web development。



![](img/188385e4e33c07762ebb26c392632fa9_51.png)

![](img/188385e4e33c07762ebb26c392632fa9_52.png)

But Ruby， the rules are pretty simple。 Nil and false are false， everything else is truthy。

 nil is the special value so。

![](img/188385e4e33c07762ebb26c392632fa9_54.png)

Option B， every ruby method returns a well defined value。 even if there's no return statement。

 So I mentioned that returns are optional， so。

![](img/188385e4e33c07762ebb26c392632fa9_56.png)

诶。Yeah， we can。 we can define this method here。 semicollonons and Ruby are optional unless you're gonna do something weird and put stuff on one line。

 they sort of work in， you know， in place of a new line。 so I can say hi。

 and I get back the value nil。 So the wording is a little bit funny on this one。

 but nil is still a welldefined value。 It means nothing。

 So the option that's left is has to evaluate to some value。 So nil is not。



![](img/188385e4e33c07762ebb26c392632fa9_58.png)

呃。Nil is not a value。 any expression can turn nil when it needs to。

 you could get into a debate of whether something is， in fact， nothing。

You can wrestle with that one for a while， go take a philosophy course if you'd like to debate that further。

 That's the best option for this question。 This is a useful example to think about what Ruby can do。

 it's also useful in that the way to verify this one is to test it in the interpreter。

 but this is also not something that we would ask you on an exam and because is something nothing is not necessarily a question that you know we need to get into in this class。

 but for the purposes of that question。You know， what we're trying to get at is， you。

 you don't have to return a value， but if you don't return a value。

 Ruby is going to put nil in there for you。 So Ruby's dynamic collections。

 So hashes contain can contain things of various types。 We didn't go through too much of that， but。

You know。They they're there in Ruby。 So we didn't I didn't go through this in the interpreter。

 but upper and lowercase things do matter。 So class names have to start with an uppercase letter。

 variable names and method names。2。Don't need to， but they can。

Constance and rubby can be all capitalized。Is a common thing to do。

 Meths can have optional arguments。 So I didn't show that by day briefly mention that。 And， you know。

 don't necessarily try and memorize all the syntax of Ruby right away。

 But you will pick this up and learn it as you go along。 So questions on Ruby。 Yeah。

 you wantna toss the mic。Nice。the other side， yeah， hello。y。Alright， so for the last question。

 what's， what's the answer。Oh， the answer the answer to this one is a。

 every rubby expression has to evaluate to some value。

The reason that it's a is that nil is generally not considered a value。

 The wording with B is a little funny because every method ends up returning nil if you don't do anything else。

 There's not a great way to distinguish what。Sarah， you could also very。

You could argue that nil is a value and that you know it means something。

But I would say a is the most correct for this question。

 The the one that's just worth remembering is that like。Everything in Ruby。

 if you don't end up doing something， nil will come back。

 So every method ends up returning nil if you don't do it。 And also， if there is no return statement。

 the last expression that the method used or evaluated will be there， so。



![](img/188385e4e33c07762ebb26c392632fa9_60.png)

The thing about B that we can do is。So I can define a new method and I can just do have a string。

So this method just as the name Hello world， all it does is in there。

 there is a string called Hello world， and you see that after I define it I get it back and I can just call it。

By， you know， calling the nametyping the name of the method。

 And what I get back as a result of this method is a string。

 So the last expression in Ruby that was in this method was the string hellello world。

 And that's what the method returns。 If I don't have anything else in that method。

 such as my boringly la method high， you know， which I defined。Up here， that method just returns nil。

 So every method does end up having something consistent that is returned。 So， you know。

 this is a distinction to languages that use void。 you know。

 for something that doesn't have a return statement。 So because Ruby is not compiled you know。

 there's no， you know， method there's no way of declaring what a method should return。But， you know。

 it， it will always return back at least a value nil if you don't do anything else。

 So that leaves option A as the most correct answer。

 though I'll grant you the wording on this one is a bit funny。



![](img/188385e4e33c07762ebb26c392632fa9_62.png)

Other questions on Ruby， yeah， I want to pass it towards the back。Next。

What exactly do you mean by well defined So yeah。呃。Granting that the wording is a little funny。

 So this is well defined means a value that Ruby understands。

 So I would like to find another word than value in this case to count for nil， but。

How well defined is an object， it is the thing n， anything like that。

So that's really what it's trying to account for there。

You can't just put the one thing that you can't do is you know return like some undefined method。

 which because Ruby would try and call it and you would get a syntax error or a method missing error in fact。

 but it has to be something that Ruby understands， but nils the case there。Other questions？Oh yeah。

 in the front here。Yeah。 wow this is cool so for a would another explanation be that like if we have something like say like object plus string or something something that clearly doesn't evaluate Yeah。

 so yeah， if if a ruby expression doesn't evaluate。

 you'll get an error would be another way to look at it so。😊，But it's not going to actually。

 you know， like if you're going error in that case unless you're doing something， well。

 it depends on what the area is。 if it's a syntax error， your programs not even gonna run， right。

 if it is a runtime error where you're evaluating that expression then unless you are using the equivalent of tricach。

 which in Ruby is called rescue。 you know， your program would stop executing。

 So we're kind of exempting for that fact。 but yeah， you could。

 you could also consider the fact that you know， an error would be。

Would also not evaluate or it's not necessarily the result of。

 I wouldn't say it's a result of an expression， although if you think about it in a rescue block。

 maybe you could。You could consider that way， that makes sense。Cool， any other Ruy questions？

Oh in the back。I think right，No。If there was one in the back， raise your hand again。Cool。

Just some minor admin notes just remember homework1 do Friday， homework 2 is going to be out soon。

 there's not going to be an auto grader， it will be peer reviewed。

 it's a set of questions using curl APIs， the command line some tools so that's what we're going to show you a bit more today。

And then microquiz Thursday， so the rest of this course or of this lecture is about rest and。

Last lecture we talked about using the MoDB API。APpiI docs give you some background about what the API is expecting。

 you know they usually have some base that includes a version， sometimes this is a number。

 sometimes this is V1， sometimes it is in the subdomain but oftentimes it's nice to have a version there。

 the corollary of oftentimes it is nice to have a version there is if you're building an API for your projects。

 I encourage you to put a version towards the beginning of the API if you're building one because it will not matter for this course。

 but if your application lives on you will be doing a favor to whoever takes on that application in the future because if you don't version your API and then you want to version your API。

 things get a little messy and you're stuck with maintaining backwards compatible code most APIs require authentication。

 so in the past that was an API token at some point in the semester Ill probably demo the B courses API。

hi you know if you're really sick of submitting assignments to the B course's website。

 I'll show you how you could like write a command line tool to do that for you。

 but it uses an authentication method as well that's slightly different but pretty common and for the most part the APIs that we're working with will return JSON but know that's not a strict requirement。

呃。Based on the information that is here for some mythical API that returns something about books。

 what do we know about this API call so get books， it has a parameter book ID and it has a format so which of these book ID and format are required are they optional。

 do we just have literally no clue。Cool， we have about the same number of responses。

We have a pretty good distribution of responses here， so again。

 take about 30 seconds and talk with a partner and then I'll start a new question。So all right。

Convince your partner that they should change their answer。Or not。それそ。Yeah。I。あそ。これ。咁备。到佢。So。度啦。多。

Yeah。我系打。四个人俾。哦，你系得。有0点老是比较。So。な候。かしか。个。我入。All right。

 so if you get a chance click in an answer and then we'll talk about the options。O。Kong。I听。

Let's see if we can get a few more votes in。呢边。All right。

 so if you have like 10 more seconds and you want to vote， go ahead and vote。

And then we'll cut it off。谁。Okay。So cool， let's see where we got。So a lot of you set up on B。

 we have a。A few Es so we'll go through that。嗯。😊，And。I'm going to say that in this case。

 E is the one that we can't we can't necessarily know anything。

 so don't be fooled by the fact that the color of the parameter is in red。

 that is the document So in the past lecture we use red to denote the you know the the URL parameters that are in there。

But in you know， in an application， there's a lot of ways to structure an API。 So in reality。

 we can't know without checking the API documentation or if this were a production application。

 we could hopefully you know have the ability to test it ourselves and you know there's one thing that you will also learn is that documentation is a wonderful resource。

 but there' is no greater truth than what the code is actually doing。 So during my time。

 more so as a T than now， but when you do things with the B courses API。

 you will sometimes find that the documentation is confusing。 It's an open source application。

 So reading their Ruby code is actually the easiest way to figure out what's going on sometimes。

 or at least easiest when you have that ability。😊，So yeah， in this case。

 we can't know without reading the documentation。 Why might the book ID parameter be optional。

 So get slash books might very well just return and what is known as an index or a list of a whole bunch of books。

 So this will be a common thing depending on how you structure your API documentation。

 you might separate them into two different sections of your documentation presumably get books slash book ID should operate or give you information about a single resource and a query parameter that's format rails is not going to enforce that。

 you know this parameter is you know required， but you as the programmer could enforce that。

 you know， if you don't see a format parameter you could absolutely return an error code that says like this request is not good。

And that would be up to whoever's building this API。 So really。

 we don't know anything to say based on one example line of an API documentation。But， you know。

For the most part， I would say that depending on how you structure your documentation and your API。

 there will be a use for returning something about all books。

 and then there will be a use for returning something about an individual book。

 So you would very likely have。I had two things there。So when we talk about APIs。

 there are a long history of ways to design APIs， so don't worry about the acronyms。

Soap is one that still exists today in some cases， but it's based on XM L。 Most of these are。

 in fact， based on XM L。 There's this other object。Method API called Corba。

 but basically they all have a。Well， they're all way more complicated than rest is really the gist of that。

 And so， you know， how do we decide what API design， what structure to use Well， over time。

 web developers， you know， application authors， API users you know。

 design tools and sort of come to you know， a consensus consensus on what structures and frameworks work best and so。

For the past 15 to 20 years， that answer has been rest。 if you've heard of GraphqL。

 it is a new sort of rest like API structure is one way of putting it but that originally started from Facebook and it aims to address some of the complexities that you can get by having giant networks of resources but for now the answer for the best API design the stuff that we'll be practicing is rest。

 and if you get nothing out of this course， practicing。

 designing an API will be something that will probably be helpful in the future。

 and then later in the semester will hopefully talk about some new stuff like GraphqL so。

R stands for representational state transfer， which， again， acronyms。It doesnn't matter too much。

 but it may be helpful to remember。So there are three questions that you can hopefully answer when you're talking about at API。

 what is the primary resource that is affected so in that last example that would be a book。

What is the operation that's happening。 So this is often going to be， you know。

 encoded in the route with the verb or HtTP method that we're going to be using。 So in that case。

 that was get。 and what other data are needed， so。knowIn this case。

 the format option or parameter may be needed， it may not be needed。

 but between those three things we're operating。😡，On a single resource。

 we're deciding what we're going to do with that resource。

And then we need to decide what other information？Do we need to know so these three things together。

A the。Most important bits of a rest API。 So a resource could be anything in your application。

 So in this example， it was a book。 we've seen a movie our savings account if there were a bank API。

 a savings account could be its own resource。 you know。

 a checking account could be another kind of resource。 you know， you might reuse some routes。

 you might have separate routes when you actually build an API。

 but you can have multiple representations of any of these resources。 So， you know。

 that could be a Json API as a representation。 So。Rails makes things very nice by default if you're working on a new application or something using。

You know that's kind of kept the railils conventions。

 you can apply dot JSON to a URL and you'll get back sort of a nicely encoded JSsonN structure of that object you could you by default。

 it will give you an HTML representation of a web page when you load it so there's plenty different representations that we could have for those objects if it's an HTML page。

 it could include hyperlinks your API could return a PDF file that would be a proper response depending on the API you know and the resource that you're designing that PDF file could include links。

 it could be a download to something else。And， you know， in general。

 nice wrestful APIs will follow these guidelines。 So the trick is， you know， when things get messy。

 how you， how do you decide what， you know， what to do so。If you come away from nothing else。

 three things about rest， operating on a。On a single object。

 returning some data and then having routes that respond to specific types of actions。As I mentioned。

 restful APIs are usually JSON XML is still relatively common depending on the structure of the data or the other types of processing that are used。

 you'll find it more common amongst legacy applications。

 partially because XML is amongst older standard， JSON is in terms of you know internet standards in the web relatively young but。

Well known， and HTML is certainly going to be a common format for anything that is human readable。

You know what we also might talk about later in the semester， but you know， GitHub。

 which sure I'll be using， has a very robust API。 and for their application。

 there are API calls that return pre renderndered HTML fragments that they can just use in parts of GitHub to simplify sort of their structure so。

You know， again， just ask yourself those questions。 What am I operating on。

 What should I be doing and what information do I need to know and go through that step by step。

 and that will help you design an API。 So rails is set up to make it very easy to follow these conventions。

 So when we get to rails， you'll see there is a routes RB file。

 and that will define the entry points for all of the routes in your application。

 So a U and a method an HttP method that goes with it。

 those Ht TP methods will correspond to standard names of rails methods as well。 So rails makes it。

Pretty helpful to get set up for these conventions。 So you have probably heard of C before。

 and this is。ItKind of the point where we'll。You know， leave things for today。

 but so CRd stands for create， read， update and delete。

 So these are sort of the four basic operations that you could do on a single entity。

And it's sort of been extended to separate out now index。An index is just a list of items。

 so when you start a rails project， you will have a resource， so maybe students。

 one of the methods that will come for you in your controller so railils has an awesome function called rails generate that scaffolds the start of new code for you and one of those methods is the index So index is just a list of objects it's been separated out from create。

 read， update and delete to kind of indicate that the first four letters of crud really distinguish a single a single resource of a similar type。

 so when we create a student we're creating a student record when we do get students slash student ID we are reading that single record。

When we update， you know， a student， we're updating on a single student。 and then， you know。

 depending on the API， we can probably delete。 So these correspond to typical H TTP verbs。

 So post is the most common H TP verb for creating something new。 that is the rails convention。

 when you when we get into Hl， you'll see how forms will use the post method get should always do something that returns data。

You can certainly have a get API that modifies some stuff。

But it's not necessarily recommended and then put and patch。

 don't worry about the distinction between the two， the intricacies of the H。

Of the HtP RFC are really not worth going through unless you're working you know for a very large company。

 but there are two similar methods that basically say update a resource that already exists in my application。

 so if you have a student and you want to change let's say their email address。

 maybe you're changing your name that would typically be a put or a patch request。

The delete method is really handy， and it should really only do one thing。

 which is to delete a resource。 And then again， for an index， you would typically do get。

 and the distinction for most routes between what's an index and what is a single resource is that in an index method。

 you would be leaving off the specific resource I。 So that is the basics of。Of CRD of APIs。

 we'll talk a little bit more about that later on Thursday， we'll get into some Sinatra APIs。

 so you'll start to see how that works in Ruby， and then that will be the basis of your next homeworks。



![](img/188385e4e33c07762ebb26c392632fa9_64.png)