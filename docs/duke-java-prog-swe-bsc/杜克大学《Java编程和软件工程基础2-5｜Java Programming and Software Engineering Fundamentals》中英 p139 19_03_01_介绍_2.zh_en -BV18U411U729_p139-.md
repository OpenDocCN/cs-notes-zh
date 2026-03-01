# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p139 19_03_01_介绍_2.zh_en -BV18U411U729_p139-

![](img/b4c3306d7c6998443c0166bb7d3b34c0_0.png)

Hi， in this coding demonstration， we're going to see both how to sort items like strings in quake entries and then how to sort efficiently。

 You've already seen some information about using selection sort and a preview using the builtin system collections do sort。

 So we're going to take a look at those more closely。

 What you've already seen with quake entries is how to sort by magnitude using the selection sort algorithm。

 So what I' would like to do first is see how can I sort strings using the same algorithm。

 So I've got my code here that I'm going to try to run selection sort on。

 I've created a very small array just for demonstration purposes that has the name of some cats。

 ti line， cheetah Puma and leopard。 I'm going to sort them using selection sort。

 I just copied that code from the quake entries where we sorted by magnitude and I'm going to sort the strings by just replacing the array of qua entries with an array of strings。

 So I've got a very simple code here。 I'm ready to compile it and test it。O oh。

Here's my selection sort algorithm， which is just like the one that we had in the one of the previous lessons。

 and it says bad operaan types for binary operator less than string and string。

 and it's highlighted this entry where I'm comparing the current element I'm iterating over with the minimal element and I did that with the quake entries to compare them by magnitude here it's saying I can't use less than to compare strings。

 And that's what happens with Java and anything other than the primitive types in doubles。Care。

 I can compare those using the less than operator， as I have here， but for。

Object or quake entry or other more complicated types like string。

 I'm not allowed to use the less than operator。 Java won't let me。

 So I'm going to show you what's going to be the topic of this next group of lessons。

 I'm going to use the compare to method。 And I replace the less than sign with compare to and ask if this less than 0。

 That may seem a little mysterious right now。 but we're going to explain that in the next sequence of lessons that you see。

 So list J dot compare to list Min less than 0。 I'm going to compile this and now it compiled。

And no problems running it， I'm going to come in and make an object on my object workbench。

AndNow there are many methods in here I want to do run select。

 that's the one I just had that sorted cats。And I can see cheetah， leopard， lion， Puma and ti。

 which is exactly what I wanted。 The strings were printed in alphabetical order so that compare2 method did what the less then method did for ins。

 But compare two works with strings and quake entries， as we'll see in the next group of lessons。

 That shows me that I need this other method。 compare to in order to compare strings or quake entries and any other things besides int and doubles。

 What I'd like to do now is look at the efficiency of the sort。 Now that I've seen。

 I can compare strings with compare to I'm going to look at efficiency of methods。

 What we've done here in the sort timings class that you heard a little bit about of before。

 is create some timings。 I'm going to sort 10000 random strings。



![](img/b4c3306d7c6998443c0166bb7d3b34c0_2.png)

And then 20，000 random strengths all the way up to 100，000。 I've created a method to do that。

 and I'm going to run that method now。I'm going to select my object and I'm going to call runner。

 which calls my sort methods for several different array lists。For 10000 strings。

 it took 035 seconds to sort them with selection sort。 But the built in collections do sort。

 as we'll see in a minute， took 1 hundred0th of a second for 30000 strings。 I'm almost at 3 seconds。

10th of a section。 Ex me，100th of a second for selections do sort。



![](img/b4c3306d7c6998443c0166bb7d3b34c0_4.png)

40，000 more， still hundreds of a second。

![](img/b4c3306d7c6998443c0166bb7d3b34c0_6.png)

I could keep this running， but it's going to take a while。

 So I'm going to stop running by shutting down my Java virtual machine。

 and I'm going to show you the output of this program that I ran before and let it run to completion。

 Here's a screenshot of me running that sort timing Java class。 And for 10000。

 you can see selection sort was fine。 It took 035 seconds。 By the time I got up to 100000 strings。



![](img/b4c3306d7c6998443c0166bb7d3b34c0_8.png)

It took nearly a minute for selection sort to run and4 hundredth of a second for collections。

 sort to run， let me make sure I've pointed that out 100，000， I could take a minute or 0。

04 seconds and as you saw in one of the previous lessons that timing gets worse and worse the more elements you have。



![](img/b4c3306d7c6998443c0166bb7d3b34c0_10.png)

![](img/b4c3306d7c6998443c0166bb7d3b34c0_11.png)

ToSee what I did。I've taken the call to select sort。And run it。

And I printed out the time that it took using system do nanotime。

 a convenient method that Java provides for timing code segments。

 and then I called collections dot sort。You'll be able to study this code on your own if you look at the sorttings。

 Java class that we provide。But collections do sort works with array list of strings precisely because I have the compare to method。

 Here's my select sort。 again。 Let me remind you， compare to， that's the method we use when sorting。

 We'll see more of that in this lesson。 Happy sorting efficiently。

