# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P19：-19-COMP6771 21T2 - 8.2 - Advanced Types - Part 2.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

Hi everyone， I realized before the break that I thought this was the end of a lecture but we still want to chalk about Stan forward so this's is going to be two part recording whoops。

However。We're just gonna chat about this quite briefly。 And then we're gonna jump into。



![](img/c5b786ae30180b097472785c09c117dc_1.png)

Assignment。Three， in fact， I might just put this as the assignment 3 recording and say to whoever's watching this。

 skip the first 10 minutes of this video and go straight to assignment 3 might be the easiest thing。

I think the first thing to preface with。The standard forward topic is that standard forward is not accessible。

嗯。In this course， the， the sad reality of Covid is that。

All of your exams now are basically open book， which I think is great for some courses and is kind of good for this course but。

You know， it makes it really hard to ask theoretical questions anymore and test your knowledge because everything's Googleable。

 Now， that's not a bad thing。 You know， I'm a big fan of like you know， if you can Google it。

 what's the point of expecting you to know it， though it does mean that your exams are mostly going to be。

Practical， your exam will be practical。😊，Standard forward doesn't really appear much in that exam and it's not really required for assignment 3。

 but let's just kind of quickly take a look through the steps that lead us to this magical function called standard forward or forwarding functions。

U。The thing about forwarding functions。I'm just looking whether we want to talk about that or not is that remember how we said because of reference collapsing before that and because of binding。

 what actually often happens is that when you do something such as。You know， this。

 you can sometimes lose a particular property of a type。

 So go in this scenario might be an R value reference。 But once we pass it into this function。

At this point here， when we're printing out a， a behaves like a constant L value reference。

The fact that it was an R value reference previously is kind of lost by the binding。

 So sometimes what we want to do is we want to be able to forward or like retain that particular you know。

 the。How that type is without losing it。 So we're basically going to go through some steps here。

 It's like， if you have a templated function called a wrapper。

That takes in a type T value and then what it does is what it returns the result of calling another function。

All that's going to happen is here is things are just going to be like copyable or if you try and pass in a type that's not copyable then。

You know， I mean， this is just like your standard copy case。

 We don't need to to kind of dwell on that too much。 We've。

 we've learned that a more robust way to define some kind of function is with something like a reference to a a conty or an L value。

 a constant L value reference and。This is kind of okay， and it mostly works。

 though the only problem is that it doesn't work in scenarios where we want to pass in a value and our value reference that is non constant and we want it to be modifiable。

Because in the previous examples here， while something like this did work。

 it doesn't work for times when we actually need to modify a。

 It only works for times when you know we want to deal with it as like a cont because it is cont so。

Something like this， while it does pretty much take most things， allow most things to bind to it。

 it leads us to a problem。Where if we try and pass in a non K store in this case and a non or in our value reference。

 you you just can't modify it because it gets binded to like an L value reference in this case。

Other ways we can look at things like we've seen before is that you could just use like a reference to T。

 just like a T L value reference。😊，This allows things to be modified， you know。

 so we're kind of just recapping what we learned previously。

 though the problem with this is that now。Now， what happens is that。Ch。

It like we can't pass constant things into it。 It's the problem we saw before。 So sure it's mutable。

 sure it can take in。 I mean， gonna take in our values。I don't remember， but you know now it doesn't。

 so if we pass in a constant object， we're going to have a problem if we try and take a constant N and we pass in it there。

 we're going to have a problem and I think it doesn't really work well for our values either。嗯。

This is another thing I thought we cut out of the course， but we didn't。 Sorry， I。

 I always forget this when I'm prepping it'cause I delete lots of slides。 And then I。

 I forget it every time。 So we talked about reference clllapsing before。

And how there are lots of different cases where pretty much an R value reference of an R value reference collapses into an R value reference。

 but all other kinds of things end up collapsing into an L value reference。Which， you know。

 is kind of semi interesting and semi boring， though， the relevance of that。

Is that we need to think about this when we are calling certain functions。

 So what did we say in the previous slide， We looked at the binding examples and we said。

 you know what， both a reference to a constant T and a reference to a templated T。

 everything combined bind to it。The good thing about a reference to a templated tea， though， is that。

嗯。It's。It's nonconst in these cases。So。If we created a templated function like this。

 template type name T Auto wrappper takes in a templated R value reference of a value。

 and then it calls function on that value。In the left hand side here。

How this will work is that if I had an int eye。😊，And I called Rapper with that int I if I called this function。

 how is the template instantiation going to work Well it's going to create two instantiation。

 well it's going to create one instantiation for me here。

 which is that it'll create a you know an explicit like well。

 you know an instantiation is like an explicit specialization essentially right。

 It's saying that we have a template at type， let's create an instance of that function。

And all it does is it replaces that T here。Right， with the type， which is a L value reference。

 Now that's the case because when we're dealing with all these reference types。

 just a standard old variable is an L value reference， you know this。

 like if you just declare an into I and you pass it into a function that's expecting a reference。

 it just takes it by reference。And it replaces the T in this function here with an int reference。

 Now the reason we care about reference collapsing rules is because this will tell us what kind of type it is。

 which in this case collapses to a L value reference because the I value reference of an L value reference is itself just an L value reference。

嗯。So。Basically。This is kind of like roughly what it collapses to here and then on the other side。

 if we created it in I and then we passed into wrap R value reference。

 a non con star value reference。Right。And I think I've just。Yes， okay。 Nathaniel's spotted that， too。

 So it's like。Yeah， so this one is a little bit weird。 but essentially， I mean， the same， the same。

 the same thing can be taken away from it。 I think the only thing here is that this T。

 like standard moved doesn't actually。Like while it makes it an R value reference in the literal sense of what happens here。

 it's actually just an int。 but forgetting that for a moment'ca this is just a little bit more demonstrative is like。

This is just another example of how reference collapsing might work from a compiler level in terms of a compiler will get you know it'll try and instantiate a particular templated function like this。

 It'll put in the values if it can， in this case as an end。

 But if you assume that it's like an R value reference， then it does collapse at something like this。

 and then you're left with these two kinds of function。 So if this was the case here。 And I mean。

 it still collapses to the same thing。 Well it doesn't collapse， but it still ends up at the same。

neearly the same thing this is an example of how like if you have a wrapper function like this and you call it with two different types。

 you're going to get two different instantiations depending on that now。😊，Where things get weird。

Is that。嗯。Just moving on here， so。If we want to generate something like this。Right。

 auto wrappper L value referencer takes in an L value reference。

And then we cast before we take into this function， another L value reference。

And then the other side we do that the opposite for R value reference。

 the reason we might want something like this， with R value references。

 we force the value to be passed in as an R value reference and for this one we force it as an L value reference is to essentially preserve the reference type because the reason this example kind of has a wrapper and a function is because essentially because of reference collapsing and binding and stuff as you're passing things through and they bind you can sometimes lose the information associated with it。

And。That is why we have this mystical function， which I don't know。 is stand forward。

 Is it is it a built in。 I can't remember if it's what library it's part of。



![](img/c5b786ae30180b097472785c09c117dc_3.png)

![](img/c5b786ae30180b097472785c09c117dc_4.png)

Utility is it？Yeah， it's defined in utility。 And what Stan For essentially does is Stan forward tries to preserve。



![](img/c5b786ae30180b097472785c09c117dc_6.png)

The specific reference meaning in terms of here， we have our wrapper that is a templated T R value reference and it you know it takes in that templated R value reference type。

 though by putting standard forward around the value we're passing in like we' we're kind of calling that underlying function。

 this here all this really does for us is ensures that in cases where this。Collapses or， you know。

 just turns into an L value reference that we make sure we're calling function with an L value reference。

 And in this case here， it makes sure we're calling it with an R value reference。

 So essentially what this is saying is that if you have stand forward in a function， if this。

 if an instantiation of this templated function wrappper。Instiates with an L value reference。

 then standard forward will make sure that whatever your passing to function is static costed as that。

 And if it's an R value reference， it's static costed as that。

 It's essentially ensuring that like L value references are you know。

Transferred through and the same for R value references。



![](img/c5b786ae30180b097472785c09c117dc_8.png)

Now， let me just see how many more we got yeah。So。Generally speaking。

 this is mostly useful in scenarios where you're writing like a generic function that takes in like an R value reference to a template where you don't really know how it's going to get used or you know in this case here you' like look at this like make unique right so we're doing a little like mini case study on like a simplification to make unique and make unique is just to say a function and it's using veryic templates which we talked about last night to take in a number of arguments which makes sense right because if you think about。

Make unique as a function， you can say make unique on。Standard vector of int。

 and then you can just give it like 1，2，3，4，5。 and suddenly it just takes in any number of arguments。

 and that's because it's using the veryic template stuff。 So it can take in any number of arguments。

 but to make sure that it can take in R values L values， constant values etc。

 we not only use the veryatic templates， but we also use the R value references of a template type here。

 which ensures that everything combined to it The return type of make unique is obviously a standard unique pointer of type T that makes sense because you know make unique returns a unique pointer but you can see here and this is a simplification again。

 make unique will actually return a new unique pointer where it will do the new forest itll memory allocate that forest a type T but we use standard forward here to make sure that all of the L value references or R value references of these as are preserved because there's the chance that a particular instantiation of make。

You know， depending on whether it generates certain as as L values or R values might， you know。

 restrict us and lose that。That I don't know what to call like the old value referenceness。

 the referenceness of of a particular type。 So， again。

 this stuff is very academic in the sense that we're going into quite a lot of weeds here and quite particular use cases that most of you wouldn't have really come across。

 and a lot of it。A lot of is mainly relevant when you're trying to deal with。

Situations where you're working with L values and our values， though。Again。

 it's not something we're assessing， so please don't please don't stress out if you're。

Value category is a technical time， I like referenceness。What are some uses of stand forward Well。

 the really specific use of standard forward is when you want to wrap a function with a parameterised type so let's say you're creating a function like make unique or make Sha。

 but it's a templated function。You know， and。It's really just when you are like because thing is templated functions tend to operate or themselves call functions that you don't understand or have context of Like the key thing to notice here is that we're creating a new T。

 but you don't know what T is。 You don't know if T is expecting L values or R values。

 you don't know if it matters。 So by using standard forward， it's kind of like you know。

 I guess the way I think about it in my head is like you're trying to create like a true middleman for lack of a better phrase that。

Can， you know， it's templated enough to be called an a range of scenarios。

 And you're just passing stuff through。 It's not， it's not opinionated。

 It's not trying to say that we're going to collapse this or do this。 It's just like。

 I want to try and preserve a lot of the original meaning and。

Value category of our types as much as possible and again。

 like full disclosure generally anytime I refer to a topic as academic。

 what that means is that I understand it because I've read about it and studied it and poked around with it or taught it。

 but I've never really come across a scenario personally and I'm not I'm not at a。You know。

 daily C+ plus programme where I'm like， oh cool， I really need something like that。

 but I hope that gives some context on what Stan For is。 I mean， if you want more information。

 you can obviously just Google Stan forward and read about it。😊。



![](img/c5b786ae30180b097472785c09c117dc_10.png)

cause there's a lot of information and CPP reference and there'd be a whole bunch of other examples online。

 though generally speaking， this is one of those things where you're very unlikely to run into a scenario where you're like。

 do I need to use stand forward here Like if you aren't sure you need to use it then the answer is probably no like it's not something that's going to creep up on you like smart pointers where things you were doing before without smart pointers you should now do with smart pointers or anything like that。

There's some context to keep it in mind That's technically the end of this lecture。

 I will actually stop the recording and start another recording mainly just I was thinking as I was talking that that's probably better。

 So if you could leave feedback on。

![](img/c5b786ae30180b097472785c09c117dc_12.png)

This is just the。Advanced types lecture， that would be really great。

 Thank you would really appreciate that。 see how you're all feeling about it。

 see what we got to change for next year potentially。😊。

Then we'll get on to assignment3 just seeing how many people have filled it in I've had。

One person filled it in， someone says a lot of ampersans。So if you're sitting there。

 if you're lying in your bed， if you're sitting on the toilet， if you're making dinner right now。

 I don't mind， just grab your phone out， snap it。Takes all of all of a moment just to。

 to give it a general feel for what you thought was interesting。 I mean， the general。

 if you do fill this out， I mean， this is the same for people watching the recording。

The main thing I'm interested in is like how much you find these。

Do you find these topics interesting， even if you feel like they won't have an immediate practical benefit to you a lot of the time。

 you know， like， are you like， this is just really interesting to think about the language。

 That's kind of the thing I'm most interested in anyway， thank you。



![](img/c5b786ae30180b097472785c09c117dc_14.png)