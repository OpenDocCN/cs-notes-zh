# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p76 75_03_are-all-pls-the-same -BV1bw4m1D7MM_p76-

In this segment， I want to talk about the question， are all programming languages the same。

 After all， if the general concepts come up in every programming language。

 then wouldn't it be enough to learn just one And there are arguments in both ways here。

 You don't need to learn every programming language there's ever been to understand what's going on in programming languages。

 but I also think there's value in learning more than one。



![](img/5a33042c9195be0fea733d10856a5062_1.png)

So let me return to the car analogy， I started in the previous segment for a second and then we'll get more technical when you go to rent an automobile or get in a friend's car that you've never driven before。

 you can actually kind of drive it if you know how to drive it's actually a great thing that there's kind of worldwide standardization on what the steering wheel does where the brakes are。

 how to open the windows， the fact that there are headlights in front of the car this sort of standardization is helpful it makes it easier to read code in another language even if you're not familiar with all the details。

 but it can also get you into a lot of trouble somethings not in quite the right place。

 you don't really understand how a particular language construct or car feature works it can be very uncomfortable and your comfort level increases as you learn the standard general concepts as well as get experience with different cars or different programming languages so programming languages are probably。

More different from each other than cars are different from each other。

 Maybe they're more like cars or trucks or boats。 I'm not really sure how to measure。

 But nonetheless， I feel that the analogy is fairly decent there。 You could also argue。

That for all the benefits of standardization， it actually impedes progress that if someone had a much better way to design a car。

 but for it to work， the gas pedal and the brake pedal had to be in different positions than people are used to。

 it would be very hard to get that idea adopted because people would have a lot of trouble using that car and would find it very dangerous。

So that's the analogy Now let me get to actually something much more computer science and technical that you really should know if you're going to study programming languages。

 and that is that on a very technical level， all programming languages actually are the same in the following way。



![](img/5a33042c9195be0fea733d10856a5062_3.png)

Anything you can write in language X， you can write in language Y if what I mean by a program is given some arguments。

 what does it return as a result if it takes in some input and returns an output and there's some way to implement it in Java。

 there's a way to implement it in ML， there's a way to implement in Python。

 there's a way to implement it in PhP。 In fact there's a way to implement it in a programming language where all you have is one while loop and three numbers that can three variables that can hold numbers of infinitely large size。

Okay，That's a truth。 It's something essentially known as the church Turing thesis。

 and it's something that weve found to be true that for every programming language。

 we can think of with sufficient power。 and you have to take another course to study exactly what that power is。

 I'm not going to get into it here。 There is a translation from any program in one language to a program in the other language。

 So in that sense， all programming languages are equally powerful。In another sense， in practice。

 all the languages that we actually use around the world to develop software have the same fundamentals。

 There's some notion of variables， there's some way to hide things from other parts of the code。

 There's some notion of one of types。 later in the course we'll see how object orient programming does one of types。

 There's some support for recursive definitions。 So all languages are the same。

 they're just combining these same features in different ways。

But now let me argue it the other way and say just because all languages share these similarities。

 they have the same expressive power， they're built for many of the same concepts。

 that doesn't mean they're exactly the same。The analogy I like to make here is that I actually believe on a lot of levels。

 people are people， it doesn't matter what country you live in， what language you speak。

 what society you're in， there are certain things that make us happy， make us sad。

 certain things that are hard for us in terms of intelligence， certain things that are easy。

 There's a lot of similarities and yet no one would deny the large cultural differences we have around the world it's why I love to travel it's why I love to have friends who grew up from all around the world。

 it's because those differences are exciting too。And in fact。

 one of the best reasons to travel to another part of the world or to learn another language is because you appreciate more about where you come from and how your language works and programming languages work the same way。

 and that's why， as I've said before， I think this course makes you a better programmer in any programme language。

More on the software side， what often happens in programming languages is the primitive or default in one language can be done in another。

 but it's very awkward。That there is。A way to program like case expressions in another language。

 But without the support for case expressions， it's a lot more wordy。

 you have to go through extra hoops。 You have to add extra variables， and conversely。

 if you want to do something like objects in M。 It's frankly， not particularly pleasant。

 It's a lot of extra work。 you have to get a lot of details right。

 you don't get convenient error messages because the compiler doesn't understand the idiom you're using。

 and that's okay。 And often the best way to understand a language construct is to understand how you would code it up in terms of other language constructs in another language。

 And we will see examples of that in this course。So the last line here on the slide。

 beware the Tring tarpit。 This is exactly getting back。 This is a famous expression， the Tring tarpi。

 And what it refers to is we know that your programming language can implement everything that needs to be implemented。

 The church Tring thesis gives us that that is going to be the case。

 The tarpit is you are not using convenient features you're saying， well， I have a way to do it。

 And it's beautiful to me。 it's good enough to me。 I can get this done。

 but you end up using awkward error prone features that are complicated or less efficient or less straightforward to get the job done。

 And so part of a programming languages course is to draw out the elegant way of thinking of the ideas rather than always just finding a way to code it up in terms of some other ideas。

😊，And so that's our summary of how programming languages have universal similarities。

 but it would be an exaggeration and a counterproductive exaggeration to dismiss the diversity of programming languages by saying。

 oh， they're all the same。

![](img/5a33042c9195be0fea733d10856a5062_5.png)