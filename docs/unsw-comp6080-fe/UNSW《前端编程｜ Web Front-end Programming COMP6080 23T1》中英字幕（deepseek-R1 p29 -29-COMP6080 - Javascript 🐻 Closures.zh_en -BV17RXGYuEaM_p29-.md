# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p29 -29-COMP6080 - Javascript 🐻 Closures.zh_en -BV17RXGYuEaM_p29-

Hi everyone， My name is Hayden and today we're going to be learning very briefly about jascript closures closuresures are a concept you may have heard of before and essentially it's a concept that a very small set of programming languages have JavaScriptscript as an example of one Python is to you won't see it in languages like C for instance。

 in a bunch of others and what closures allow us to do is to create execution environments which are very similar to what you'd see with objects and classes so if you've used an objectoriented language before。

 you know that you can kind of define a template a class and then when you go and create instances of that class you're creating its own little what we call an execution environment or what you could call a closure so when you hear the word closure it's essentially an execution environment and there's a whole lot of detail on the MDN about what closures are that I would recommend if you're interested you go。



![](img/0f94778c11a5922b80c76fa45c59f00a_1.png)

Read it It's very it's very thorough and theoretical。

 A lot of the things here aren't as critical to use anymore。

 And that's because prior to E 6 ECma script 6， a lot of it was needed。

 a lot of this use of closures was needed， particularly through。



![](img/0f94778c11a5922b80c76fa45c59f00a_3.png)

Through the poorcooping rules that jascript had， a really common example of this was the immediately invoked function expression。

 This is something you might see around the internet。

Essential this was here this was used substantially more before variables sorry before terms like let and cont existed which helped get around some of this you can go and read into this if you want go and read into closures some more go and read into IifFEs but nowadays since E6 a lot of it isn't actually needed very much in terms of you can give someone like yourselves an introduction to jascript and you can go and build things and you might have an intuitive sense of what a closure is maybe from Python or just from your own programming intuition but it's just not really something you have to think about as much these days that's why it's not a big deal in this course you can go and read some more on an example of it。

 there's an article they linked here from last year called closures in their practical use they kind of covered it in a bit more of a light fun detail。



![](img/0f94778c11a5922b80c76fa45c59f00a_5.png)

![](img/0f94778c11a5922b80c76fa45c59f00a_6.png)

![](img/0f94778c11a5922b80c76fa45c59f00a_7.png)

Give an example about how you could create some dynamic。HtML generator with it。 But again。

 mostly this stuff is kind of if you don't read it， nothing bad is going to happen。

 But what we're going to do today is just a very quick demo。

 essentially highlighting what a closure is and an example of its usage， so。



![](img/0f94778c11a5922b80c76fa45c59f00a_9.png)

One， the the example that I want to run you through， we've got a really simple HM page here。

 and I've got this closure HTML page up。 This code will be with all of the other code in the course。

 of course， but in the course， of course， But let's say we've got ourselves a really simple HML page here。

 and we're going to use a little bit of dom manipulation。



![](img/0f94778c11a5922b80c76fa45c59f00a_11.png)

Just because it's kind of easy。I'm not sure what's up with the syntax highlighting。 But you say here。

 like， hello， okay， I've got my really simple web page。 Now。

 what we want to do on this web page is we want to create a button。

 And every time that button is clicked， essentially， what we would like to do is。Create a new little。

 new little section that starts a timer。 So imagine it's like a button that we can click as many times as we want。

 And every time we click it， a new like timer pops up as a dom element。

 So this mixes it a little bit of dom creation。 So first thing I'm gonna do is I'm gonna create a button that says create timer right And this button will be here。

 We're gonna give that button and I D so we can add an event listener to it。😊，Create timer。

And then I'm going to come along， let me just make this page of it smaller so we can see more of the code。

I'm gonna go and create a get element by I D on the create timer。 I'm gonna add an event listener。

 and it's gonna be a click。 And when that happens， I'm going to call a function， right。

 So there's me passing in an anonymous function。 and I will console log clicked。

 so we can kind of test how this goes as we do it。 I'm going open up dev tools。

Which you should all be more than familiar with now。 See how small I can make this。

 So now when I click that， we're getting clicked。 Now。

 what I want to have happen is that every time I click it。

 I want a new little box to come up with a timer starting and it counts every second。

 So we're gonna have to use a set timeout。 Let's just do that once to start， for instance。

 So I'm gonna make a box called timers。So I can kind of append elements there。

 And what I want to happen is that I will create a new variable called timer equals zero as in like or time。

 this can be my like time counter。So it'll start at 0 and increment its way up。

 And what I'm gonna do is I'm gonna create a new dom element。 I'll say。You know。

 constant new timer equals document dot create element。So again。

 this is a little bit of don manipulation stuff。 I'll say new timer dot inner text equals time。

And then what I'll do is I'll go and get my create timer， and I will simply append child。

I will just add my new child to it。 Actually， I don't want to add it to create time where I want to add it to timers like this。

 So now this should work in theory， It should create a div with a zero inside of it like that。 Okay。

 and every time I click this I get this effect。 Let's only worry about clicking it once to start。

 And to click it once to start what we want to have happen is that every single time once it's loaded。

 we want to have a essentially like a set interval that'll start counting。

 So what I could say is that just after I just before I say a pen this child。

 I could say set interval， which is like set time out， if you haven't seen set interval。

 it's like set time out except it keeps going。 like it's like a set timeout that repeats。

 And what I'm going to say is that。I wanted to do every， you know。

 thousand milliseconds and I'll simply increment time and then I will just set this element here。

 right new timer equals in text like that。 So now it we've got an error right So already I've started to get some problems here。

The oops lost that window。 The issue here， though is， is nothing to do with closures。

 It's actually just to do with like a。Just a consteled example， where。

I have set something to be cons， so I need to make this let。 Now we'll see what happens。

So I click create timer， creates a timer 1，2。 So it's counting up， right， This is good the。

The problem here is that what happens if I want to create more timers， right。

 Becauseuse you notice if I click this again， now they're all kind of。You know。

 they're all using the same number。 And if if you reason with the code here。

 you can kind of make sense of it because we've only got one time variable。

 And what happens is that time variable is is always a certain value。 And when I click create timer。

 It's just taking that time variable as the starting point。

 and then we have an interval that's increasing it。

 You'll also notice that this stuff is going crazy because now we have five separate。

 essentially intervals that are all like not quite in sync， they're all incrementing the timer。

 So the time is actually kind of going up five tick a second。 So that's not really good。

 how can we get around that， Well， you might be thinking， oh， I could create an array。

That makes sense。 I'll say times， let's create a times array。

 And now what I'm going to do is every time I create a new timer， I will actually say。

Times do push zero。Okay， and now we've got like a new index to that times0。

 So when I click this button five times， I want to populate this array with。5， it's a terrible name。

 When I click it on five occasions， I w to populate it with five values from the times array。

 And each time I create a new timer。I'm going to push a new value to it。Okay。

 now what's the problem here， Well， I can't use time anymore。 I have to use。 I have to use。Times。

 and then a certain， you know， index。But what's the index， well。That's hard。 It's， you know， So like。

 what do I set the index to be， Well， the index could be， say0。

 but then it would always do the first one， but I can actually just say times dot length。-1， which。

 which actually makes sense because the initially， the times are raised empty。When I push to it。

 its length is1， so the index I once index 0， and when I push my second element to it。

 it's length is 2， which means the second element is index 1。 so let's try that out。Okay，1，2。Okay。

 so this is seeming to work now。So I can create lots of timers and they're all kind of。

 it's kind of cute。Cool， so I got all these like time is going crazy here and。

You know what in your head before when we talked about closure and we talked about execution environments。

 whether there's these like segmented different objects or， you know。

 working separately from another， you might look at this and thing while they all seem like a little separate timers。

 but at the end， these are all just a whole bunch of event listeners and set intervals。

That are all operating off the same times array。Now this code is perfectly fine。

 you don't need closures to solve this， you don't need closures to solve much。

 there are closures at play here， but I'll show you an example how we can do this without the times array。

 for instance。Now。A really simple example of a closure is if I say create。

 I'm going to create a function called C time。And what it's going to do is it's going to have two really important elements in it。

The first one is it going to have a local scoped variable。

 which I might I might say let time equals 0。 And then secondly， it's going to have a function。

 And quite often this might be a function that you actually return。

 So I might return a new function here。 and all this function are going to do is increase time by one or time plus plus。

Like this。And we can， we can go and do some。 We can go and fiddle around with this some other ways。

 But what I'm gonna do now is I'll comment out all this code here so that you can look at it later。

 but I'm going to go and。嗯。Copy a few parts of it here。 So I've got my on click again。

 So we've really simplified our code down。Go back to basics。When I click it。

 I just want to say hello。But what I'm going to do now is is I'm going to create a new variable called this timer equals create time。

So I'm actually calling the Create time function and what it's returning。

Is it's returning a new function， right， the whole function and function thing。

 I think gets very confusing very quickly。 But if you pay attention。

 this function's job is to return you another function。

 If you've used decorators in Python or you know， you've been through that experience。

 this is actually very similar to that in a lot of ways， decorators kind of use closures。

 But what this returns is a this anonymous function here。

 So if I actually console log what this timer is。Right I get this function。

 It's actually just printing out the source code for me and you might be thinking， well。

 isn't it returning all of this stuff， Well， no it's not because that's not how a function works right。

 If you have a function， there's like three local variables and some code。

 all it does is return the return value and the return value in this case is a function。

What's really interesting about this， though。Is that this function here actually has。

This variable in scope and this is basically what a closure is。 And in fact。

 if you go to the MDN website， it says a closure is a combination of a function。

This enclosed with references to its surrounding state， which is this。 And it says， in other words。

 a closure gives you access to an outer function when you think outer function think create time an outer function scope。

 which is this。From an inner function。 So essentially， like in a nutshell。

 a closure is a function that returns you some variables and more functions。Or another function。

 And that inner function has access to those variables on the outside。

 And you'll actually notice it is very similar to a class in a lot of ways。

 And I'll show you what I mean。 What I want to do here is instead of return just a function。

 I'm actually going to return a couple of functions。

 And the first function I'm gonna return is called get time。😊。

And that's gonna be I'll write it in the function syntax。 So it's a little bit clearer。

 All get time is gonna do is。Returned me time。Like that。

 And I'll create another function called increment time。

And all increment time is going to do is it's going to set time to increase itself by one。

Now let's have a look at what happens when I console log this timer。

RightAnd remember this timer is the result of create time When I click it。

 you can see that it actually returns like what this timer becomes as two functions。

 and I can call those two functions。 And again if you're familiar with object oriented programming。

 this is the point where you start to think， okay this actually looks a lot like a class this is my private fields and these are my kind of methods and that's actually the best way to kind of model closures is the kind of lightweight class objects because when you think about a class。

 all a class is the capacity to manage scope and to create little execution environments where you have a series of methods all operating on some kind of scope that's not quite global and it's not quite local to a function right because these functions here don't have local variables but it's also not operating on a global variable because if I here is to say consoles log time time doesn't exist because it only exist within you know within the closures that are created。

😊，Now， I've got my this timer function， and suddenly it actually becomes a lot easier what I want to do。

 So I'm gonna go and copy those， those dom elements that I created。😊，Right， so new timer was that。

 I can get rid of all this other stuff。 for now， I'll leave the set interval to do nothing。

 And then I go and populate my timers with the new timer now。

What you'll notice up dot get rid of a critical line。Yeah， I did。 I got rid of that critical line。

Now， what you'll notice here is that I don't have a times index to start anything with。

 So if I set this as0， we get it， we get an okay start and you can see that comes up。

 but I don't want to set it to the literal 0。 I want to set it too。This timer dot get time。

Because what do we remember about what this kind of。

Generator does create time returns us these two functions。

 It returns us an object with these two functions， and you saw that before when I console logged this timer。

 what this timer gave us was two functions， get time and increment time。

So I can simply call this timer dot get time。 and that will that should in theory， right。

 give me the0。 Now it's not giving me the0 because I just console log time instead of returning time。

 That was a bit silly。 But now you'll see I actually get that0。

 So that zero is coming from this time here。 And when I click this five times。

 this create time function is creating five separate closures，5 separate execution environments。

 because it's like it's packaging something up and giving it back to me。

 And then that's very powerful because here。😊，Every 1000 interval。

 I can just call this time a dot set time。Like this。Oops， yeah， no set time， increment time。 My bad。

 That doesn't exist。Okay， that's not working。Clearly， got a problem here。 Let's quickly debug it。

Right， so let's I'll write call and then I'll write time。

 It's probably just something simple I've missed。Coal1， cold  zero。 Oh。

 we're just not updating the dome， so it's totally fine。So we need to update the dom， obviously。Um。

W which means increment time probably needs actually， I think I could just call get time。Yeah。

 let's try that。Yeah。So now we have that。 Now we have it's like， alright， Well。

 we set the interval and then it just。Updates it。With that。

So what you'll notice immediately is that if I get rid of the console logs here because they were probably a bit distracting that this code is is somewhat easier to read in a way。

 particularly when you take into account that we're not dealing with indexes and loops and stuff because previously we weren't creating execution environments in the first example。

 we were just storing a list and that list was managing all these different environments。

 whereas in this one we're leveraging the essentially the usefulness of jascript closures。

 and you could simplify this further if you want to。

 like I could go and make an anonymous function called update text and all that function will do is it will just set new time as in a text to this dot time as get time。

 So now it's like well I could just actually instead call update text there and update text here。

You know， and now it's just gonna， now it's just that， you know， it is an extra line of code。

 but you're actually， you've obviously got a lot less repetition here。

 closuresures exist everywhere in our code。 It's very interesting。

 you you can kind of start to see them when you pay attention to it。 For instance。

 You have noticed that to look at this set interval here。 How is this accessing this timer。😊。

That that is a variable that is not in this function scope because remember this is a function and the function itself is a closure because it's accessing something from the outer scope。

 So remember， a closure is essentially like the pattern you see is a function， this out here。

That contains local variables， and other functions。That's kind of the pattern you look for。

 just like up here。 And the point is that those inner functions can access the scope of the outer function。

 So this inner function can access the scope of this outer function。Easily， like this。

You could clean this up further， but you get the idea。 Now we could go and create all these timers。

 I'm not dealing with arrays and indexes and lengths-1。 Is this necessary， No。

 should you probably think about it all the time， Maybe。

 but I don't think it's going change your life。 You know， don't stress about it。

 You got a lot of other things to learn early on with jascript。

 But did this allow us to create somewhat more readable code。 Yes， what's the downside of this， Well。

 we don't have the capacity to， for instance， go and update all of these at once。

 So the upside of the original method was， for instance。

 we could go and zero out all those times if we needed to。 So if I say get rid of this for a second。

 and we go look at our bottom method that we had before。Like this。

The plus side of doing things with these these arrays is that I could actually do something such as do a set time out。

 And what I want it to do is after。You know。After five seconds。

I would like it to go get the time array and I could say， you know， times equals。

Times dot map number。Returned 0。 Does that work。Let me try that。

So essentially what I'm trying to say here is that the times array is equal to the old times array。

 but I'm going to change every value to0。 so in theory， it should zero them out， maybe。Now。

 that didn't work， but you can kind of you can kind of you could do this with a loop pretty easily。

 right， You could say4 that I equals0 I is less than times dot length I plus plus。

 And then you could just say that times of I is equal to 0。If I even made the set interval。

 it might become clearer。Where I go and create all these times and after every three seconds it actually resets them to zero and it's hard to tell because。

😊，As soon as it resets to zero the very next loop， the interval actually increases it again by a tick so you never actually see it as zero because it always increments it before it prints it out but the point is that with this kind of array approach it becomes a lot easier to manage these because now you are you've kind of got some central place you can refer to them of course you could actually do the exact same thing by combining these two methods as well by saying you know what let's actually let's actually saw these in a list。

😊，Right， so I'm just going to combine these two ideas together now。 St these in a list whereby I say。

 well。With my times， So let's get rid of， let's get rid of。All of this。And copy and paste。

Let's copy and paste this one。With all of these times， instead of actually pushing a zero。

 I'm actually gonna push a new。Create time。 So instead。

 I could actually kind of combine these and say， well， I got to this timer。

 And what I'm gonna do is every time that happens， I'm gonna push it to an array。

 Why would you do that， Well， I'm actually not gonna use the array in my code anymore because。

I can just do what I did before， in fact， I can copy most of the code here。嗯。

Because most of it's identical， I could actually do something like this where the only difference between this example and the next example is that this one I have this times line and this one I have this times push line where I'm actually kind of saving these execution environments as I'm creating them and then we could be even kind of cleaner and we could go along and say you know what。

 well， after after every five seconds。😊，What I would really like to do。

Iuse I would like to go and get4 each time。I would like to say time dot reset and then this is great because I can actually just go and expand the what's in my like closure creation function here where I can just say that time is equal to0。

 So now every time I do this one I go and create these。

 we are storing all these execution environments and then this interval is just going through and sweeping them shut。

😊，So again， you can see that it's not so much a case if closures are better or worse。

 there's just different ways of doing things， some will have better style， some will not。

It's not so much about as versus closures。 It's actually just because you can use closures with array arrays。

 They're all just different programming styles。 Sometimes this is overkill。 generally。

 generally what happens is a lot of functions you write don't need to be don't need to consider themselves too heavily as a closure because they're not using some surrounding scope And on the other end of the spectrum if you're writing something really complex。

 you might want to use a jascript class because they they might be more powerful and and a little bit clearer to someone because you know。

 when people see things like class that becomes a little bit clearer than this than you know this kinds of like functions within functions。

 But anyway， hope that really kind of paints the landscape of different kinds of ways you can interact with these。

These examples， whether it's using lists and doing what we did first。

 or whether it's just using closures and throwing out the need to access it or whether it's combining it all together。

 these are all tools at your disposal。

![](img/0f94778c11a5922b80c76fa45c59f00a_13.png)

And thank you very much。