# CppCon【中英⚡CppCon 2024】 p33 P35 Session Types in C++ - A Programmer's Journey - Miodrag Misha Djukic - CppCo -BV1NHEEzdE92_p33-

![](img/413a1d3a15a1f3658325bf8f74f3a53b_0.png)

Honestly it's the hallway track， like the biggest the spaces where I've learned the most at CPPCon have been in the evenings。

 hanging out with people over a drink there at dinner and just chatting。



![](img/413a1d3a15a1f3658325bf8f74f3a53b_2.png)

![](img/413a1d3a15a1f3658325bf8f74f3a53b_3.png)

Hello everyone， thank you for coming to this talk， I'm glad that you came。

 although I find it just a little bit strange since I would much rather like to be on these other talks where。



![](img/413a1d3a15a1f3658325bf8f74f3a53b_5.png)

![](img/413a1d3a15a1f3658325bf8f74f3a53b_6.png)

Where I listen and other people talk。啊。But。Just first few words about me。

I work at the University of Novisa the Serbia， I do teaching a lot。But besides teaching。

 I also have some background in industry work in compilers and embedded assistants， and in general。

 like I tried to live up to Bs ideals about teaching。

 programming and also practically doing programming。Now this topic of session types。As you've seen。

 it's titled like a Jour。But programmer journey， and that's important because the session types are a mathematical term。

 which we will try to use in pretty practical。Circumstances， of course。

 their users usually have to be some kind of motive。Besides just being interesting。

 but in this particular case， a motive was unexpectedly strong。And。

It was that a friend of mine told me that it cannot be done in C+， plus。So。You know。

As the commonplace goes， people say， hold my beer， right？

It was not quite like that because I like to hold my beer while I cold。Yeah。

 I'm a bit slower that way， but at least I know where my beer is。

Because I had a lot of bad experience。 I don't know if you had bad experience with leaving beer with a friend because I usually say to people who didn't have bad experience with that。

 you just didn't do it a lot and on scale。 right， So it's like shared pointers and dynamic location。

 you have new beers， deleting beers， leaking problems， all that stuff。 So anyway。The question was。

 can it be done in C++ you will see later？It has been done in many different ways and with different levels of practical usability in many other languages。

 But in C++， at least Im not aware that anyone tried。 So I did try。

And the idea is for you to be judges， whether I managed to do this or not。嗯。

Totally unrelated stuff to the fact that you're gonna be judges for this。

 I have really nice sweets here。 really， really cool stuff from Serbia。

 Just if you have opportunity to try that sometimes to not miss it， right。 But anyway。

 coming back to the。😊，Topic in order for you to be judges。

 I need to kind of explain what is the task， what are these session types。

 and how I'm going to implement them sort of in C++。So this will be interesting journey。

 I hope you will have some interesting insights together with me， nothing revolutionary。

 nothing too complicated。But I think you'll like it。 Anyway， the term session type， of course。

 has this part type and type is one of those terms that is used a lot and has a bunch of overloaded meanings。

So different meanings overlap。Just enough for it to be complicated to understand when are we talking about which meaning。

 right， but still are different enough that they don't mean the same thing and。

It's not by accident that great Albert Einstein said that normal adult programmer never gives a thought about types that's something which he has taught and learned as a child。

 and he on the other hand developed so slowly that he did not begin to wonder about types until he was an adult。

That was similar to what he was saying about space and time。 He said that on a CPP cast。

That's the same occasion when he said donut trust internet quotes。So。

Let's start with the definition of type in a mathematical sense， and。Clearly。

 you will see that that's not going to be the path you're going take， because that reminds me to one。

Let's say older question。 when I was in high school。

 we had a teacher who liked to ask us this from time to time to define a set。

 and the expected answer was。Well。Set is a primitive thing。

 yet like we define other things based on sets。It not something that we do。

 We can describe a set in a sense， But trying to grasp the formal definition is a bit harder thing。

 Of course， now， if you go into the history of。Type theory。

 we have an idea to overcome Russell's paradox。You probably know about that。In any case。

 that's a different way of looking at things which type is a primitive thing， not a set。

 but we're not going to go down that rabbit hole。 The point is that we will try to pose the question differently。

So in the next step， we ask。Just what is a type without formal definition。

 But that question will also not get us。Too far because the honest answer would be depends on who you ask right。

 so jokingly， we can say that those are so called dependent types。

But we're not going to go down this rabbit hole either， right？So the third question that we'll ask。

 and I think we will get the best mileage out of it is what are types use for in programming and in programming languages and the next slide I added just at the conference I was kind of inspired by the talks about Bitcoinins and cryptocurrencies and it was mentioned the amount of these talks。

Because。It's very analog， in my opinion， to money。 So when we talk about money， we consider money。

 currency that we use， but it's often very good to。

Remind ourselves are to know that there are actually different roles that money plays。

 There are three to four different roles depending on the literature you are consulting。

 but money is used as a media of exchange as a store of value and as a unit of account。

 So each of these three roles is slightly different。

 And then almost for engineering practical reasons in most cases。

 we use single currency for all three roles right but in many cases many。In some of the cases。

 we actually tend to use something else， most obviously for store of value。

We change to some other currency or some commodity or that kind of stuff so in that vein。

These are some things that types are used for。 I kind of compile that from different literature。

 People will mention5，6， or maybe even7。Things that types are used in program programming。

 So let's go quickly to through these。For these things just to get the better idea。

 So one thing that prototypes are used for is abstraction。So。It's much easier when we know a type。

Type gives us enough information so that we know how to work with something。

 and then we don't need to know all the details behind that。 So that's one role the types play。

Another role is documentation， I kind of extend that a bit and I think it's pretty important role because types inform us how we should use things。

 how we should interact with something and the most obvious and most popular thing that I think shows that。

🤢，Is this？ACompletion thing when you start with the name of your object。

 you add dot operator and usually development environments will offer you。



![](img/413a1d3a15a1f3658325bf8f74f3a53b_8.png)