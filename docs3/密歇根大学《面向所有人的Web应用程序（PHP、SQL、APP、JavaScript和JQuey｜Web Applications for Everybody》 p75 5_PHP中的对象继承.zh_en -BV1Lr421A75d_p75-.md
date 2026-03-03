# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p75 5_PHP中的对象继承.zh_en -BV1Lr421A75d_p75-

![](img/4433eee30dc6b194fd9929db4ac1ab9b_0.png)

![](img/4433eee30dc6b194fd9929db4ac1ab9b_1.png)

So now we're going to talk about inheritance inheritance is another basic object or a concept。

 we're going to talk about it in the scope of PhP， but if you're in any other language we use inheritance in PhP。

 it's a powerful notion that really makes it so that we don't have to repeat ourselves and we end up with these class hierarchies and again I'm not asking you to write all this stuff I just want to listen in so I can use the word inheritance later okay。

So it's another form of story we use it's kind of like a function we do it once。

 we're going to do it over and over， but if we have a class and we're going to make many children classes and it's a way to reuse class capability。

Another word for this is a concept called subclass。

 there's a class and then another class that subclasses it which adds value。

 you can think of this as a parent class and child class， all of these ideas are the same。

 one is sort of the original and the other sort of the extended copy。

And so we use the word extends and so we'll take this very simple example where we have this class hello that we used from the previous example。

 it has a value inside of it called Lang， we take a constructor that copies that value in it's the stuff we did all before。

 and we have a function in there so we have a class called hello。Now。

 if we want to make a new class called social that extends hello。

 So this extends hello basically says take all this stuff and put it in that pulls it all in。

 And so social doesn't start as an empty class。 Hello started here kind of with nothing then we added stuff to it。

 but social doesn't。 Social has all this stuff pulled in。

It's it's as if we typed it all there and it's a form of not repeating yourself right with these things are all in there so there's a dollar laying and there's an under constructstruct all this stuff and now we can add a thing we're going to add the buy function。

And it's just another bit of code that looks at the current language in a way we go so that we've made a new class。

 so we have two templates， we have a hello template and a social template。 so now we say oh。

Let's go ahead and make a social and pass in E。So that calls this constructor， it's a social。

 but this is part of social as well， so they're emerged together in social。Runs the constructor。

 we can then call the greet method， which comes out of here。Runs that code。

 which was the code we used before。 but then it's because it's a social。 It also in addition。

 has the by method， which is now in here。 So it's a way to take and pull all this capability。

In to a class， so you don't have to repeat yourself。 So these are often called base classes。

And these are called extensions or class。Subclass。But you can see it's a powerful notion。

 Now you still don't know why you want to make classes， but trust me， when you get around to it。

 we will build these things and you'll find them to be quite useful。

 mostly in the name of not repeating yourself and doing the same thing twice。

 So inheritance is an important aspect of object orientation。

So another thing I've sort of been glossing over is the notion of the visibility of an attribute。

 so attributes are the data， so the variables that we put in there and then methods are the code that we put in there。

 There is a concept of visibility and part of the idea of a class is to hide complexity from the outside world。

And so if you think about a class， it's got data。And it's got methods。And up till now。

 we can play with the data inside the class and we've been able to play with the data outside the class。

 and that's because we have marked all these things as public。

Public means it's equivalent to access them inside and outside the class。Private is the strictest。

 which basically says it can only be accessed inside the class， and it stops this access。

 And there's kind of an in between state。 If you make a derived class， which is a sub class。

 this is a parent。This is a child。So if this is a child， this inherits all this stuff。

This class can always talk to its own member variables， but this class cannot。 So if it's private。

 it can be accessed only inside the class， not from a subclass。 If it's protected。

 you can access it in the class and the subclass private， you can't access it from the subclass。 And。

 you know， public access outside the class inside the class and any drive class protected inside the class and in drive classes。

 but not outside and private is only inside the class and no drive classes。

 And the reason is is sometimes you want to have a variable that's really just for this use only。

 and you don't want anybody messing with it because maybe two variables have to be set a certain way。

 And so you put a really bright line around them and say these are private。

And if you really don't care if someone's messing with it， you just。

 I'll open the door up and I'll let you in to come in and change those things。

 so all market is public。So here's just a really simple example of showing how this works。

 there are three keywords public protected in private。

 you'll notice I sort of slid that into the very beginning of the public and then I was playing with it so in this class you can see that this is outside。

And this is inside。So inside， we can talk to the public。

 to the protected and the private that all works， you can always talk to your member variables inside。

But。Outside this is way outside because it's not a drive class。 It's way outside。

 The only thing we can talk to is the public。 we can't talk to the private or the protected。

 So if you say private or protected， these are not accessible。 So we got a bright line。

 and the only thing that's allowed outside this line is that and the function comes out as well。

But you can make private functions if you want as well。

 so that you get control when you're building it because you're the class maker at this point and you're saying these things are internal。

 I'm going to use them for my own purpose inside of this little space。

 These things are external meaning that I'm going to let someone else mess with them。

And then to understand how protected works， we just take a new class that extends it。

 so my class2 extends my class from the previous slide。And all we can do is the public。

 we can't see anything there， we can call the print hellello function from outside because that's just a member function that's public by default。

It can't talk to private from that other class， right。

 that was the private variable from the previous class。

 it can talk to the protected variable from the previous class and the public variable from the previous class。

 but just not the private。Okay， and so that kind of summarizes it。Public outside the class。

 inside the class and in drive classes protected inside and inri and private is only in the class。

Okay， so one last thing that I want to show you is。Sometimes programmers will want to。

Not actually use the class keyword to make a new object。

 And so you can sort of make a class and dynamically put stuff into it at runtime。

 And so you will see this code sometimes sometimes I use this。

 I'm not sure it's the greatest thing to do， but there is a way to say make a class that has nothing in it has no code。

 no nothing。 And so you just that's an empty class。 So it's a template for a class that's empty。

 but it is a class。And so you can encode code now， say put a variable name inside here and then put a variable score inside there。

 and it does it。 It sort of opens it up and puts these variables in and assign some data into them。

 they're kind of by definition at this point public because we're outside the class and we're putting data in。

 but you can do that。 And so you don't some languages。

 you have to predeefine the class and have everything defined in a classlike thing， but in PhHP。

 you just kind of extend it right， and you can do all kinds of things。

 So that' I basically created an access to public variables there。

And so this basically is a standard class with key and value。 It's not an array。

 but it's still kind of showing you the attribute， name， name and score。

 And in a print our statement。 But sort of a more elegant way to do this would be to make a class。

 which is then a template that says there are two things in players in general， a name in a score。

 And you can set it to some value and you can say new player which creates now right off the bat a class an object with two things in it with names and then you can you know add one to the score。

 And if you print it out， you see that this is the object that we defined。

 So it knows that that's a different thing than a standard class。

 this was a standard class when we first created it， but it's a pattern。 I just want。

 if you see this code， I don't want you to freak out when you see that code because that's how some of us old school people made objects in the first place。

 We kind of treated them。Kind of like arrays that were kind of prettier in a way。

 that was another way to do arrays without putting quotes in the arrays。So。

The whole purpose of this lecture and the series of object or lectures is not necessary to make you a solid object orient programmer because that takes a lot of sophistication。

 Hopefully maybe you've taken my Python course and you learned a bit about object orientation there and we get to see it again。

 So for me， the idea of objectient programming is something that comes to you more slowly than programming in general。

 So I hope that when the time comes that you're facing more complex problems and now you really have to use oh0 in a more significant way。

 this kind of prepares you to understand that better。

 And so that's the whole goal of this and we'll see in the next lecture。



![](img/4433eee30dc6b194fd9929db4ac1ab9b_3.png)

![](img/4433eee30dc6b194fd9929db4ac1ab9b_4.png)