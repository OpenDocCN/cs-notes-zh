# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p102 13_01_05_代码检查与格式化.zh_en -BV11y411z7Dn_p102-

![](img/2613361d98a23a1d09988b4057ff3b61_0.png)

Sometimes engineers don't agree with each other on formatting and what requires what makes sense in a way to write code write applications and software in a way that is normalized and everybody will adhere to these conventions and LinkedIn and formatting is one of these main important things so we have here one of our applications here is a rust application and you could very well do things like these and this is perfectly fine in rust and youll be like no you know what like I really like them like defining my work in this way now that might you might be happy to define it in that way but for others you might be like what is what is going on here like this is this looks very odd or it looks very messy why is health check。

Dstruct like all the way here and the health status is all in this way。

 so that looks kind of weird actually you can even do this。

 you can even put them in one line and and not be consistent like the key here is consistency。

So when these things happen。In cargo， you have format and we'm going to toggle the terminal。

And I'm going to do cargo， but I'm gonna to make this slightly slightly smaller so that you can see the changes right away。

 So I'm gonna scroll here and you're gonna see these things all get normalized。

 I're gonna to see cargo format and run that and boom like everything's great。

 Now it did leave this gap in here so that that's not not ideal but you start getting the idea。

 And why is this important a bit because you want to have normalized code that will look consistent across organizations and teams and and try to enable like kind of like this normal will allow you to understand code because things are in a place that you're expecting to be in the format that you're expecting those to be。

Now that is great， that is good and allows you to create automation。

 so you will see later how we're going to make this cargo format command that formats things in a consistent way to happen automatically and when things are not quite formatted。

 we can actually reject changes so if I come here and starts saying that I really want to have it like these and then save it then if the system。

 if the automated system runs again and puts it back and the text that there's a difference then you can project the change you can say hey。

 you better make these changes consistent。Now cargo format is one， but we also have。

 And when I make this bigger cargo format cargo and the command。

 which we'll see later in more detail， has a way to Lint and why is Lnt Well。

 I'm going to clear here if I say cargo the Liter， one of the most popularlinters for rust is called clippy So if we run this you will see that there's several different things here Now this application runs this application build if I actually say cargo build。

It will build no problem that's the compiler is very happy right This is compiled and says finished。

 no problem there。 like so what's the problem。 So one my argue is like why do I need Ling well。

 take a look at here what is going on so I'm saying hey you know you don't really need this two string applied to a type that implements this plain form an arcs。

 this is completely unnecessary So what's the deal there？

 Well when you're adding unnecessary things then you're making code redundant and prone to air and add confusion and increases the complexity to maintain code。

 this is not only true for rust but for any other programming language as well。

 actually in fact I used to work with someone that would refuse to use a Li and said you would say things like I write beautiful code like I don't need a Li to tell me how to do things but I think that's a misconception。

From his part and that you can always have the assistance。

 why not like take these free assistance to try to make your code better。

 more consistent and remove things。That might make it more confusing or increase the ability or decrease rather the ability to maintain a project。

 So these are two things that are useful to understand and we'll see how we can hook them up instead of like someone having to run all of these to try to inspect how it affects your code。

 we were going to try to make sure that that is automated。

 but in summary you know doing this LinkedIn and formatting is a good way to keep things consistent and increase the maintainability of your software projects。



![](img/2613361d98a23a1d09988b4057ff3b61_2.png)