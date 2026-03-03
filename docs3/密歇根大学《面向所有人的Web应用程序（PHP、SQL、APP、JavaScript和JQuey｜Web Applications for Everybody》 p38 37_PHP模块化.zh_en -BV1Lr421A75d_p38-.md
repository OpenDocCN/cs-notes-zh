# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p38 37_PHP模块化.zh_en -BV1Lr421A75d_p38-

![](img/909c2344a6c93865da6b74142c763b47_0.png)

![](img/909c2344a6c93865da6b74142c763b47_1.png)

So now we're going to talk about modularity in a different way。

 so we've been talking about functions， which is a way for you to rewrite code and use it over and over again。

 Now now we're going to talk about modularity from a perspective of files。

 Everything we talked about up to now is like one PhP file。

 but you can have functionality that might be across multiple files that you want to include over and over。

 and so there is a capability。

![](img/909c2344a6c93865da6b74142c763b47_3.png)

Include and require， include looks for a file and if it's there。

 it pulls it in and if it's not as non fatal。Require， looks for a file， pulls it in。

 and if it's not there， it is fatal， I tend to use require almost always。

And so there are things that you're going to require like that actually are navigation stuff。

 but then there's kind of library code。Where you might be actually in multiple files。

 you want to require some functions's not that are not actually markup and you want to do that over and over again。

 There's this thing called require once， which is really cool because you can be requiring a file。

 it requires a file， it requires this file It requires this utility code and then requires a different file and requires the same utility code and as long as it's the same thing it says。

 you know what Ive already got that。 I don't have to do it。

 Otherwise you have to put all this if code in and we were doing that。

 So require once is something PhB gives to you that says no matter how many things we go and how many times we ask for this file once it's been required we're only going to do it once。

 don't required again， which is really super nice。

![](img/909c2344a6c93865da6b74142c763b47_5.png)

Okay， so if we take a look at one of the common uses require。

 the common uses requires to have sort of repeating elements on page after page。

 so here I have a website and this menu shows up both places。

 it shows up both on the main page and on the installed PhP page and I want this menu and I get tired because these are this is the index。

 PhP file。This is the installed PhP， but I need the same darn menu on both of them right so how do we do that？



![](img/909c2344a6c93865da6b74142c763b47_7.png)

So what we do is we basically use this require to do this over and over。

 so this is the indext PhP code and it starts in PhP and it says， okay。

 let's require this top bit and then require nav and the top is the nonprinting stuff like the title in the head and all that stuff and then nav is this little navigation bar and so there are two files top dot PhP and navt PhP and then I have the body of it which is right from here to here and then I include a footer in this case the footer I have this automatic Google translation thing that I put in my little web page which translates this page into various it uses Google's automated translation translates that page into a various languages so we can sort of see how that works。

And so this is something I want to do on every page。 and I saw I have foot PhP。

 So there are three files， top PhP NA PhP and foot dot PhP that then I can put different content。

 So this is the unique content And so if we take a look at a different page That page here。

 which is installed on PhP has the same top part of the two requires and the same bottom part so that this stuff is the same and then this stuff is the same and then in the body part I have this div which is from here to there。

 this happens to be an iframe that's pulling in a different file yada yada know so that comes in。

 So it allows you to have these consistent elements over and over again that put markup and repeat it so that's a way to break things into more than one file and to not repeat yourself。

 Don't repeat yourself。 That's what you want modularity is really just the idea of capturing something once and reusing it over and over。

So in this series of lectures we talked about modularity in general。

 we talked about using functions that exist like the string functions or the array functions。

 making new functions， how to pass by value and pass by reference。

 and that's kind of a unique thing to PhP and how we include and require files and then the idea of writing code that works on various versions given that PhP unabashedly makes changes that are not present in all versions either adding or removing functionality as the PhP version kind of increases so I hope that's been useful to you and we'll see you in the next lecture。



![](img/909c2344a6c93865da6b74142c763b47_9.png)

![](img/909c2344a6c93865da6b74142c763b47_10.png)