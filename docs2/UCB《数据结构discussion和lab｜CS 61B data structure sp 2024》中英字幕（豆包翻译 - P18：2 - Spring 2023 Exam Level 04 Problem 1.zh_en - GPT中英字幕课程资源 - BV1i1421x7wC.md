# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P18：2 - Spring 2023 Exam Level 04 Problem 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼哈比哈比。🎼我比。🎼And。

![](img/f442735b7a46c247868aabb343068599_1.png)

Hi everyone， this is Sherry， and this is the spring 2023 exam Mo 4 walkthrough。

In this problem we'll be going over problem one， forget it， weball。

This question is basically a lot of inheritance practice with both both interfaces and extends。

 just as a note， extends will not be in scope and casting will also not be in scope for the upcoming mid termm。

 but it's still really good practice because we will not be covering inheritance in future weeks。

So with that， let's jump into this problem。Just for a quick overview of this problem。

 we noticed that we have three classes， we have the person interface and we have the athlete and soccer player classes。

 and the hierarchy is that the athlete class implements the person interface and the soccer player class extends athlete。

So if we look here， I've kind of condensed everything into one page。

 but there is also a table on the other page， if you like to fill that out， I will not be doing that。

 but I will just write the table beneath each line。

And the question is asking us what is going to be printed by each of these lines or if nothing is printed。

 we have to identify if there's like any errors or issues。So。If we fill out this table。

 if we start looking at the table， the table asks for the compile time or static type and the runtime or dynamic type and the output。

 so we're just going to jump in and start with part one。

We'll notice that the left hand side is declaring AyI as a person。

 so we can say that the static type is。personerson， but if we go to the right hand side。

 we see that we're trying to instantiate a person and that person is an interface。

We can't instantiate interfaces， they're not technically objects that we can instantiate。

 so this is actually going to just be a compilation error。Okay。

 let's move on to the next line and let's find the static and dynamic type of this declaration。

So on the left hand side we see that we're declaring Drrove to be an athlete。

 so the static type is athletes and on the right hand side we actually instantiaterove to be a soccer player so that means when we create an object and assign it to Drrove。

 the runtime is actually a soccer player which I'm just going to abbreviate as。

So this is a case where we have a different runtime and compile type。

Now if we move on to the next slide， we try to assign soccer player V equals Drve and you might think that this will work because at runtime Drrove is a soccer player。

 however， the compiler doesn't know about runtime the compiler only knows about static types so it thinks that Drro is an athlete and since soccer player is a subclass of athlete。

We can't necessarily assign a soccer player to an athlete object because what if Drve is actually an athlete。

Then it would be a super class of soccer player and it wouldn't make sense to assign declare that it is a soccer player。

 so we can say that this is also a compilation error and we don't really have to write the static and dynamic types because they don't exist。

Okay， on the next line we say person Eric equals new athlete and this is valid because we're not trying to instantiate in an interface。

 we're just saying that Eric is a type person。So Eric has static type person and dynamic type athlete。

On the final line we say that athlete Sus equals new athlete。

 and this is an easier case where the static and dynamic types are the same。😊，And then finally。

 for Yaofuo， we have the same where the static and dynamic types of Yaoo are both soccer player。Okay。

 now let's move on to some of the method calls and again。

 we're going to write down the static method call that's chosen and the dynamic method call that's chosen。

So if we look at Eric。watchtro， we notice that Eric has the static type person。

 so at compile time we're going to pick person。Dot watch。However， at runtime。

 we're going to notice that the dynamic type of Eric is an athlete。

 so instead of running the person dot watch method， which actually isn't even a method。

 it's just a declaration because。It's in the person interface。We're going to call athlete。Dotwa。

And the athlete dot watch method is going to print ball is life。So finally at runtime。

 even though we chose the person。 watcht method at compile time。

 we're going to override that with the A。watch method at runtime and run Ba is life。

Let's do a few more just so we can kind of see get the hang of inheritance and overriding so in this next line we say sreya nott speak to Yaofu and again Sreya has the same static and dynamic type of athlete so。

At both compile and runtime， we're going to choose the athlete。 speakak to。Method。

 and then we're going to print， I love sports。Okay， if we move on to the next case。

 we see that we have a very similar case to 15 where Yaofu is both a soccer player at runtime and compile time。

 so we're going to pick the soccer playerer。 speakak2 method。

And this is going to print join 61 bowlers。In the next couple lines we start doing casting and what I want you guys to remember about casting is that it basically it tells the compiler this is the type of something。

 so basically it tells the compiler ignore what I declared earlier for this line only just listen to me and I'm going to say that the statictype is an athlete I'm going to say that the staticotype is a person。

So basically it kind of。It kind of tricks the compiler， but for one line only。

So if you look at line 19， we have athlete Yaofu。speak to Eric。Over here。

 we declared the static type of Yaofu to be a soccer player， but actually here。

We've kind of told the compiler the static type is an athlete。

What's going to happen is we're going to consider the static type to be an athlete I'm going to choose the athlete。

 speakak2 method。And then at runtime， of course Yaofu hasn't actually changed into an athlete。

 it's still a soccer player， so we're going to pick the soccerplayer。 speakak2 method。

And what's going to get printed is join 61 ballers again。Okay。

Let's look at line 21 again we're going to cast Yaofu to person。

 so at compile time we're going to pick person。peeak2。And then at runtime， we're going to again。

 Ya runtime Yaoo's dynamic type is a soccer player， nothing has changed。

 so we're still going to pick the soccerplayer。 speakak2 method and we're going to print join 61 ballers。

So something I want you to notice about these three lines with Yaofoo is that。

We never change the dynamic type of Ya food casting does not affect the dynamic type。

 it only momentarily tricks the compiler into thinking that the static of type is something else and this only lasts for one line。

 so if I cast Yaofuo to a person， it's not like Yaofo permanently becomes a person for the rest of the code。

 it only lasts for one line。Okay， let's move on to the last two lines which also have casting and in this line line 23 we cast Eric to an athlete so at compile time we're going to pick the athlete dot speakak2 method。

At runtime we're going to check can we actually cast Eric to an athlete and this is fine because Eric's dynamic type is an athlete so we're not trying to cast to like a soccer player or anything。

So at runtime， we're going to pick the athlete。 speakak2 method。And this is going to print。

 I love sports。Okay， for the final line， we noticed that we're kind of doing the same thing where we're casting Eric again。

 but this time we're casting Eric to soccer player。And if you notice， Eric。

 the real type of Eric at runtime is an athlete。The athlete is a super class of soccer player so we can't cast Eric down to a soccer player because an athlete is not necessarily a soccer player。

 you can imagine that we have many types of athletes like basketball players， golfers。

 so we can't necessarily cast an athlete down to a soccer player and when we have a casting error。

 this is going to be a runtime error。That's it for this problem and for my weekly exam tip。

You'll notice that on this worksheet we provide you with this table。

 which I'm kind of filled out kind of ad hoc beneath each line on an exam we may not provide you with an entire table。

 but it's always good to be very clear and write out the static and dynamic types of everything in order to figure out what the print output is going to be or if there's going to be some kind of error。

Good luck in the rest of this week and in the rest of 61b and if you have any comments or questions。

 please leave them below。

![](img/f442735b7a46c247868aabb343068599_3.png)