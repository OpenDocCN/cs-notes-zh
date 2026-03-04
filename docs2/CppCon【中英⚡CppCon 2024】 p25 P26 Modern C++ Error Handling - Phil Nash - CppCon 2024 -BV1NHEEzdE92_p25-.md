# CppCon【中英⚡CppCon 2024】 p25 P26 Modern C++ Error Handling - Phil Nash - CppCon 2024 -BV1NHEEzdE92_p25-

It's my first time at CPPCon， I've thought about going for a lot of years and now kind of regretting that they didn't go sooner。



![](img/c42794e3499069accf82d0c293195fda_1.png)

![](img/c42794e3499069accf82d0c293195fda_2.png)

![](img/c42794e3499069accf82d0c293195fda_3.png)

A little bit of a warning about this talk。 There's going to be a lot of code。

And some of it's going to be a lot on screen at once。 So I try to make it as readable as possible。

 Sometimes the font size is going to dip a little bit below what I would be comfortable with so。

If you are sitting towards the back of the room， especially there really small people right at the back。

Might want to consider coming forwards a bit， we're in the big room。

And we've got a big crowd here today for those watching on YouTube。

 it's about the size of the football field and it's completely packed， at least with chairs。

And quite a few people as well。So get do is of coming forwards。

 especially if you've struggled to read the code because every side is going to have a lot of code on just to warn you now。

So given that it is going to be mostly code。Just to make it a bit more visually interesting。

 I also asked Jack GBT to generate me a whole series of robots that are going to help guide us through the code。

 So， so watch for those， including this one。 I particularly like how this one came out on the title slide。

😊，So I Phil Nash， I am now an independent consultant， trainer， conference organizer。

On the subject of training that's now my main source of income， so if you have any training needs。

 especially test driven development， coouts or effective C++， do come and see me。

 be here till Friday morning or you can reach me on discord or watch me next year。

 next CPPcon for my class。But enough about me， topic today， modern C+ plus era handling。😡。

And I chose this name very deliberately。Because this is not the first time I've done a talk on error handlingling。

😡，Back in 2018， I did optional with not a failure and 2019。

 the next year followed up with the dawn of a new era。And while I still stand by these talks。

 in some ways I're a bit dated now， ironically， because they're a bit too forward looking。

Not quite so much the first one， which started off with a bit of a review of existing error handling techniques。

 and we're going to do a bit of it again now with a bit of a fresh click。But towards the end。

 we built up to what we could do in the future， finally introducing Herbatters P 0709。

 his value based exceptions paper， sometimes called static exceptions。

 which hasn't really gone anywhere in the meantime。 so maybe that was a bit of a dead end。

Unfortunately， the second talk really dug deep into that one。

 So a little bit more more of a dead end， but that one didn at least touch on stood optional。

 stood expected for error handling and the magnetic operations， which with the time。

 was still off in the future， will except stood optional。Now they're actually in C++ 23。

 so we're definitely go look at those today。Have a fresh take on them。

 They're slightly different to what I talked about before。

 And we're also going dig into them a bit more。And as part as the language features。

 I'm also going to look at some of my own ideas about effective error handling and how we can merge some of these things together。

😊，And I'm going to talk about one feature that's still coming。 just towards the end。

 we will touch on contracts a bit。It's not going to be a deep talk on contracts。

 You should have seen Tima Doumbler's talk earlier today on that。 Lisa Lipingcock has won tomorrow。

 a bit more of the philosophy， but I'm going to talk about how it fits in with the other error handling techniques and how to make sense of them。

 So that's what we're going to do and we're going to do it in two parts。The first part。

 we're going to talk about what I'm going to call disappointments。

Ithich is a term coin a few years ago to talk about any type of error condition that is predictable。

 something you expect。 you just don't necessarily want。 You're disappointed if it happens。

 but you can work around it。 you can go on and you know what to expect。So that's a disappointment。

 and that covers pretty much all forms of control flow error handling， as well as sixs。

As we'll see it will come under this umbrella and that's going to be the first half and then in the second half we're going to talk about things that are more logic errors。

 often bugs in the code， things that you can't really predict you don't really know what state you're in and now are really more the domain of contracts both conceptually and finally the language feature and we'll see how that fits in。

And the total on this slide here is a bit of a play on words because it turns out that if you use disappointments for your error handling。

You will generally end up with a total function。 All possible inputs have a valid output。

 even if some of those might be represented as an error。

Whereas a partial function is one that's only valued for side inputs。

 and that's what a narrow contract will give you， we'll come on onto to that later。let's get started。

So for this first half， we're going to be using one particular code example to hope that's。Readable。

It going to be the evolution of this as we go through， but it's going to be the same basic idea。

 we're just parsing a string into an integer， nice and simple so we can focus on the error handling。

And we're going to use this implementation。😊，Nothing complex is they oversimplified for the purpose of。

This slide that。But it serves the purpose。So there's some extra things you might want to do。

What you can see there， hopefully， is that there there's two exit points。

 and only the last one will give you a full， fully parsed integer。But there's no error handling here。

 so if we were to call that with different inputs like this。Different strings。

We will at different outputs。Now I've used the stood print LM here that C+ plus 23 don't let that distract you。

 Obviously that's just for printing the result you could use C out or printf or whatever I'm not trying to be modern where I can。

So if we give it， a string that is fully an integer。😊，Then it will， of course。

 convert that faithfully to an integer。If you give us something that's followed by some nonnumeric digits。

 it's still going to give you an interteger， because if you can see in the implementation。

 it just stops pasing at that point and returns what it's got so far。

Which is incidentally what IOStreams does as well if you use that for string housing。

So it should be familiar。 And finally， if we start with a non numeric digit。

Then we get zero because that was what we started our accumulator with， and we never got any further。

Again， that's what our own streams give you。And that actually might be a valid approach。

 in some cases， just getting a best effort and carrying on regardless is the right thing to do。

But very often， we're going to want to distinguish these error conditions and take appropriate action。

 So that's what we'll do next。There's a problem with this。

It's very often the case because this is computing something for you returning a result。

 you can't use the return value to signal the error。 and it's not in a straightforward way。

So stick with old school approaches。One thing we could do is just have a separate function that just。

The pause is integer just enough to see whether actually pausees the string to see whether it is an integer or not。

And then they can return the boolean result。😊，And you can write some test code that will just。

Take a call to that， and I haven't been here， but could then follow with a quarter pass it。

That's a valid approach， it might not look right the best approach here。

 in some cases it's perfectly valid， in fact， we're going to look at something like this a bit later in a different context。

But it does work。One other problem with this is we're not distinguishing in between。



![](img/c42794e3499069accf82d0c293195fda_5.png)

The the case where we're starting with。Nummeric digits or where we're starting with non numeric digits。

 that may be important as well。The Boolean only give us。Obviously， the two results。

So we me introduce。Some sort of error code， an em arm， an integer， whatever it is。

 an emar is a good choice。 So now we can distinguish between three states。

AndThe code gets a little bit more complex， but still pretty straightforward。😊。

Hopefully no surprises this yet。The usage code would still switch over that and we can get。

The expected results now we've got three different possibilities。And notice now。

The implementation code is not really making a judgment about whether it's an error or not。

 It's actually leaving it to the calling code。To make that judgment。So this starts with it。

 it may not actually be an error in your case。So that is a common pattern we're going to look at。

 trying to defer the decision of how to interpret and handle the error to the calling code。All right。

But。Obviously， there's a lot of duplicated code here。😊，And duplicateupd effort。

So this is probably not what you want to do with a string parsing function。

So kids keeping to older techniques。We might use what we call an out parameter。

Of in this case to take the integer by reference， and they're going to use that as the accumminator。

And finally。Return a， in this case， it's going to be the enum to tell us the passing status。

 And the result is in the argument that you pass in。

Sure we've all used techniques like this before as well。And that works。

 so we've removed the duplication。😊，We can signal different errors。And having good。

Except it's a little bit ugly， doesn't compose very well， doesn't feel very modern。So。Now we get two。

Oh， we have one other approaches。