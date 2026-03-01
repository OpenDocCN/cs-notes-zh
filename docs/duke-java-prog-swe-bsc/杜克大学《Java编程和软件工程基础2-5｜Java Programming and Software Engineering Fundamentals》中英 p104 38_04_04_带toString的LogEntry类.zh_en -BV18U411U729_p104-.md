# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p104 38_04_04_带toString的LogEntry类.zh_en -BV18U411U729_p104-

Hi， so today what we're going to do is we have this log entry class and I want to show you two string。

So the log entry class， notice it has these five fields here， IP address and so on。

 We've got our constructor。And we've got all these methods， and I've written two string down here。

 and you can see that it returns those five fields as one big long string。

And what I've done is I've got a tester over here。That is creating two log entries， L and L2。

 and I've just kind of made up some information for each of them， so they're different。

And then it prints out the actual object。 It prints out L E， and it prints out L E2。

 So let's run it and see what happens when we do this。So I'm going to come over here。

 notice I need to compile both of these， I'm going to compile Tester。

And it actually compiles both of them for me。 I'm going to now run Tester。Test log entry。

 and there you can see it printed out the five pieces of information for each log entry， very nice。

So now what I'm going to do is I'm going to come back to my class。

And instead of calling it two string， I'm going to change the name。I'm going to call it。Get log info。

And compile again and run it。Now let's see what happens。

So I've got my object and now I'm running Te log entry。Oh。So I ran it， but it just printed out。

Something else。 Let's see what it printed。 It actually printed out the memory location of each of those objects。

 So let's go back to test our tester here。 and you can see。When I print out an object， L。

 it doesn't know how to print it out。So it just prints out its address location。It's not calling。

The method we wrote， which is called。Let's see here right here， we called it get log info。

It's not calling that because we didn't specify it。

 So let's come back over here and we'll specify to print out。A log entry with that method。

 we need to actually write log entry dot。Get。😔，Log info。

And I'll just do that for the first object and I'll leave the other one L2 like that and let's see what happens。

We'll compile it， and we'll come over here and run Tester。

And so you can see what here in the for the first object I called Git log info and it prints calls git log info and it prints the five pieces of information。

 But for the second， I just said print the object and so it just shows the memory location of it。

 So what's going on here。嗯。It turns out that every class。Has。A two string method。By default。 And。

 but it only knows to print out the memory address of an object unless you actually specify a two string class。

 So I'm going to change this name back to two string。And I'll come back over here in our tester。

And get rid of this because notice I didn't actually call two string here。

 I just said print out the object。 And again， if I show you what happens here。We don't need the。

There we go。 So we're just going to print out the object。 We're not saying how or anything。

 but it just knows go look in my class。 And if there's a two string method。

 that's how I'm specifying how I want to print it out。 So again， we call it here。

And even though I didn't call two string， it knows。 it says， oh， you've got a two string methods。

 I'll use yours and it prints out the five pieces of information。

 The way I specified I wanted the object printed out。 Now I want to show you one more thing。

 I'm going to come over here。That name two stringing is very important。

It has to be spelled exactly two string with a capital S。

 because I'm going to show you if you change it。To lowercase S， so it says two string。

Then when I come over here and I run it。Let's see what happens it goes back and write the memory address because it says if there's a two string in there are spelled with a capital S。

 it's going to use that， but that's the only thing it looks for since I don't have it spelled correctly。

 it doesn't find it。 And so it says， I'll just print out the memory address location。

So just remember that all objects have a default two string method。And if you don't like it。

 it's just going to print out the object address， then you can write your own。 And so when it runs。

 it'll see if there is a two string method in there， then it will call it。



![](img/ddbcfd02845f822276810c2181f9ca32_1.png)

That's it。 That's for two string， thanks。

![](img/ddbcfd02845f822276810c2181f9ca32_3.png)