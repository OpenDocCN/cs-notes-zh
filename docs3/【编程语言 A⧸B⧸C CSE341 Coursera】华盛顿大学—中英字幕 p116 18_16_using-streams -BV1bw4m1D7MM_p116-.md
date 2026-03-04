# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p116 18_16_using-streams -BV1bw4m1D7MM_p116-

In this segment and the next， we're going to talk about streams。

 which are a different programming idiom that also needs some notion of delaying evaluation。

 and the implementation will use ths in order to accomplish that。



![](img/f3fd1f80528ec24ef6ae7171c3a55b38_1.png)

So a stream is a word that we use in computer science to mean an infinite sequence of values。

 something that can go on for as long as you need， it behaves like something infinitely big。Now。

 one thing about infinite- sizeized things， you can't actually make them right。

 We need something that's going to represent something that could go on forever。

 and the key idea we're going to use is to use a funk to delay the evaluation of most of the sequence and only generates some prefix of the sequence that some other computation needs。

 We're not going to need any new language constructs。

 This is just a programming in using thks and things like that。

 but it's a powerful concept for dividing labor up in a way that works in a lot of different software systems。

 So the idea is that the part of the program producing a stream。

 creating the stream knows how to create any number of values you need。

 but does not know how many you need。Whereas the stream consumer can ask for these values as it goes along without knowing anything about the process that is generating them。

So it turns out this comes up a lot in software systems。

 it's okay if you're not familiar with any of these examples。

 but I thought I would mention them for those of you are one way is if you're implementing code that needs to respond to a whole bunch of user events。

 mouse clicks， keyboard presses， things like that we saw earlier in the course we could do that with callbacks。

 but another way could do it is to think of that as some stream of events。

 we'll ask for each one as we need it and then we'll compute some result with that thing so far and someone else will generate those events as they occur。

If you've ever programmed with pipes in the UniX shellll system。

 it turns out that the second command pulls data from the first command as it needs it。

 so it views the first command as a stream and the first commands output is generating that stream。

 there's also a nice connection with electrical engineering and circuits that if you think of a timed circuit with feedback。

 you can think of the different output values it's sending on its output wires as forming an infinitely long sequence。

 and then the circuits reading those values can read the ones that they're interested in。Anyway。

 just optional things showing this is kind of a universal concept。

 even if you find it a bit abstract， you'll also see some simpler and more fun examples on the homework assignment associated with this material。



![](img/f3fd1f80528ec24ef6ae7171c3a55b38_3.png)

Okay， so we want to represent a stream in some way that we don't actually generate an infinitely long list or something like that。

 so here's how we will do it。We are going to represent a stream as a thunk。😡。

So a stream will just be a thk， but not just any kind of thunk， a thk that when you call it。

Gives back a pair。Where the car is the next thing in the sequence， the first thing in the sequence。

 and the cutter。Is a stream for values2 through infinity。So it is a stream that if you use it。

 you get the next value。😡，So in this segment， I'm just going to show you how to use these things。

Then in the next segment， we'll see how to define our own using them usually helps explain what they are and get a little better sense before we try to create them。



![](img/f3fd1f80528ec24ef6ae7171c3a55b38_5.png)

So I've already loaded the file where I've created the streams I will show you in the next segment and one of the streams is the infinite sequence of powers of two。

 So you know the first thing this thing returns， I forget if it starts at one or two and then  four and then 8 and then 16 and then 32 on forever because we don't know how many powers of two we need。

 but when I said powers of two。As you saw here， all I got back was a procedure because our streams are ths that when you call them。

 return a pair。So how do you call a thk， you put it in parentheses。Powers of two。And look at that。

I got back a pair。Whose first component is 2。 So I did set it up to start it，2。

 And his second component is another procedure。 It turns out that's a thk。

 So if I wanted the first thing in the sequence， I could just say car of。Calling that。

And if I wanted the second sequence， let's think about this。

 I need to call the cutter to get another stream。A stream is a thunk， so I need to call it。

And then I need the car of that。And that gets me four。

What if I wanted the next element of the sequence， Well， this thing is 4。

 The cutter is another stream。 A stream is a thk。 So you call it。That gives back a pair。

 and I need the car of that， and that would give me 8。

Now of course we wouldn't keep programming like this to get 16 or 32。

 The idea is we would have some sort of recursive function that is passing this next stream on to say some recursive call。

 and then we apply that stream to get a pair and we take car to get the next thing and so if you wanted to say add up the first 100 powers of two。

 you would just have some little recursive function that would be using this stream as you go along。

So what I thought I would do instead of showing you that is show you something even more general。

Let's define a recursive function that I'll call number until。

That's going to take in a stream and a function， which I'll call tester。

 All right And the idea of what this is going to do is it's going to count how many stream elements you need to process before tester returns true for the first time。

 So if Teer never returns true， we'll go into an infinite loop。

 But otherwise we'll stop as soon as we get our first true and well return the count of how many we've gotten。

 So I'm going to do this with a little tail recursive helper function。 So I have a little letre here。

 So I'm going to take in my current stream， the stream that has all the elements I haven't processed so far。

 my accumulator， which is my answer so far。 and I'm going to have to put some stuff in here。

 And then I'm just going to call F with the stream I started with and one that's my initial accumulator。

So now the idea is all the body of F has to do where I've left this dot dot dot is see， well。

 what does Tester have to say on the first element of the stream， if that's true。

 return answer otherwise。Call F again with one more and with the tail， if you will， of the stream。

 the rest of the values。 So here's how I'm going to do this。Let's first of all。Call that stream。

 We know a stream is a thk。Alright。I'll get rid of these。 So you can see this。

 So I know a stream is a thk。 So if I call it， I should get back this pair of the first element。

 and then the stream that is the rest of the elements。Now that I have that pair。

 let's call Tester on the car。If I get back true， I'm done， return ants。otherwise。Call F。

On the cutter of the pair， that's my new stream。 right， Don't call it yet， right。

 We don't want a pair， right， This would be a pair。But F expects the stream， and then F itself。

Calls that th to get back a pair。 So just with the cutter。And then one more for the accumulator。

 that's my call to F that finishes my if， my let， my definition of the lambda for F。

 and this let rec that I then use to start by calling F with the stream that was past the number until end1。

So， and then I need to end my define， my let wreck and my define。

 and now I've just defined a function， that's all I did。

So now if I call number until with the stream powers of two。

 and how about a little function that takes in a number and says， does that number equal 16？



![](img/f3fd1f80528ec24ef6ae7171c3a55b38_7.png)

I get back four， took me four times through the stream until I got something that equald 16。

 Let's have a little more fun。 How about I keep going until I get a number that is bigger than。😊。



![](img/f3fd1f80528ec24ef6ae7171c3a55b38_9.png)

This number。The great thing about powers of two is they grow really fast， so that took 339 tries。

 if I come up with a number 10 times bigger， it'll take 343 triess and 10 times bigger than that it will probably take 346 tries because powers of two multiply really fast。

😊，LetWe point out that when you're programming streams。

 you tend to make lots of mistakes with parentheses， think very carefully about。

 do I want to pass in a stream or a pair that I get back when I call the funk。If I get this wrong。

 and I put parentheses here and a passing to number until a pair。And therefore。

 right here you can just see at the top of the screen。

 that's going to be a pair when you try to treat a pair as a function。

 you get a big nastyty error message， so says procedure application， expected procedure。

 given the pair2 and some string。So you have to think very carefully about the difference between a thk and a pair。

 and if you do that， you can do some beautiful programming by using streams with beautiful recursive functions to get interesting results。

