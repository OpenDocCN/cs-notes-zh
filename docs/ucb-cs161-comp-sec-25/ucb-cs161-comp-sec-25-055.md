# 055：-MemSafety3, Video 16- Off-by-One - Setup.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay so in this set of videos we are going to cover and exploit that I like to call the off by one exploit。

 I don't know if that's the official term， but it's something you'll see in the projects and it really tests your understanding of how the call stack works so if you haven't already I would definitely recommend going back to the second lecture and really making sure you have a good grasp on how the EBP。

 the EP and the EIP change around when a function gets called and when the function returns because that's really critical to understanding this particular exploit。



![](img/8239f39b7b965b771a71ddbbc61d594f_1.png)

So what exploit am I talking about， so let's consider some code like the one down here。

A main function。 And it calls a vulnerable function。 And then the vulnerable function defines。

name array of size 20 and then it calls F rate which writes from the user input into the name character array and specifically it looks like whoever wrote this code made a typo and instead of writing that you can write 20 characters into the name array they said you can write 21 characters So that's kind of an issue And in particular。

 what issue does this cause how do we exploit this So whenever I see a kind of unfamiliar exploit like this one where I'm not really sure what's happening。

 something that I find useful is I like to first draw the stack diagram So if you don't have one of these pictures it might be kind of hopeless to try and exploit this so I find these really helpful so this diagram says well when I first call main it has an RIP and an SFP those are my saved register values like always and then there's no local variables in main so I don't have to put anything here when I call vulnerable it takes no arguments so don't have to put anything there either and now。

Ca vulnerable and when I call vulnerable there were no arguments。

 So I go straight to pushing the RIP on the stack， the SFP on the stack。

 and then the user defines name and when they define name。

 that's a local variable it's 20 bys so it takes some five rows。

 each row is four bys So that's my stack diagram and I've also noted in this particular case that the EBP points at the top of the vulnerable stack frame。

 which is right here and the ESP points at the bottom of the vulnerable stack frame。

 which is down here。 one tiny little note that sometimes people bring up。

 but it is not the most important thing here， if you take an operating systems class like C162。

 you might realize okay actually when the operating system calls mainine it doesn't really have an RP and an SFP。

 It does some other fancy thing so that you can return back to the operating system for this class we're not an operating systems class so I don't really care So we'll just abstract it away and say that main has。

An RIP and SFP like everyone else， but if you really care。

 you can go take an operating systems class and learn the real truths behind how Maine is called。

 but for our purposes， we'll just say RIP Maine SFP Maine， it's good enough for this exploit。

So that's the stack diagram， it's always the first thing that I do， I draw the stack diagram。

Then the next thing I do now that I have my stack diagram is I can start asking myself， well。

 what parts of memory can I overwrite so as an attacker。

 the only thing I can do is I can provide some input and the input gets written onto the stack So something useful whenever I see these unfamiliar exploits is I ask myself what parts of memory can I overwrite and what parts of memory can I not overwrite and that gives me some idea of the things I should be looking out for。

 I can overwrite this part of memory so I should really think about what dangerous things I can do here or I can't overwrite this part of memory so I don't even have to think about this exploit It's not going to work because I can't touch this part of memory。

So in this case， it looks like， well， I can write 21 bytes of data into a 20 byte character array。

 so if I start writing it name and I write 4，8，12，1620 I can write one extra byte the 21st one and that's it。

 So what I've shown here is this stuff in yellow that I've highlighted。

 that's the only stuff I can overwrite， I can overwrite all the bytes of name to whatever I want and I can overwrite this one byte of the SFP。

 not all four of them just one and also kind of crucially I can't overwrite the RIP so I can't play my usual trick where I take RP and I change it to point at shell code that's no longer going to work because I can't overwrite the RP So just by writing down what I can and cannot exploit。

 I've already ruled out my favorite classic buffer overflow where I just overrite the RP pointed at shell code it's not going to work in this case because I cannot overwrite that part of memory。



![](img/8239f39b7b965b771a71ddbbc61d594f_3.png)

So just by setting up the question like this， drawing a very good。

 careful stack diagram and highlighting the things that I can and cannot exploit。

 this already gives me a pretty good idea of where I should be looking for exploits in particular。

 probably right there。 So that's the setup of this question。 And coming up next。

 we'll see how you can actually exploit this code， even though you can overwrite one single byte only。

😊。