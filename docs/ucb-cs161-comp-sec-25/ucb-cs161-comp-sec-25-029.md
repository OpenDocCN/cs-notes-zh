# 029：-MemSafety2, Video 4- Overwriting Commands and Function Pointers.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/598d15814f22130e809b90df048f89e1_0.png)

Okay。Here's another example。 So we're basically just switching out variables to see all these different ways that code can go wrong。

 So here I have， again， some character buffer。 this time is 512 bys。

 And then I have another character array called command。 And in here。

 I am storing some terminal command。 So if you go into your terminal， you can type commands。

 This is storing a terminal command。 right now， it's just storing L S， which says list all my files。

 But just like before， because we called get us online。

 we are allowing the user to start at line and write up and write upwards on the stack。

 However much they want to write， possibly clobbering out the value of command。

 and maybe instead of running a command that says list everything。

 the user could replace this with a terminal command that says something like email the passwords file to me or delete all the files on your system。

 or send a spam email to everyone， you know。 So the attacker could replace this command with something more malicious。

😊，So we're starting to get a bit more dangerous by changing this。

 We're letting the attacker pick whatever terminal command they want。 And then this exact V function。

 which is a C library function， opens the terminal， runs that command。

 And if that command has been replaced with something malicious， bad things are going to happen。Okay。

 one more。 This one's kind of exotic。 So maybe in 61 C or some other prerequisite class。

 you might remember that you can write a variable in C called a function pointer。

 So what's a function pointer。 This is an address， you store an address in this box。

 And what happens if you go to that address。 you'll find the code for some function that you want to run。

 So， for example， I could have this function point ad the instructions for addd。

 or I could have this function point at the instructions for multiply。

 And I can change between add and multiply， depending on what address I put in this box。

 So this is kind of a useful thing for programmers in C。 whenever I call function pointer。

 What actually happens is I go to that address， whether it the address of addd or multiply or subtract。

 and I do that function on whatever arguments are I pass it here are no arguments。

 but could have fast an arguments。 So that's what function pointer is it's an address。

 I go to that address， I will find some C instructions that I can execute。😊，So what can happen here。

 It's kind of the same pattern as before。 I start that name。

 The get as function lets me write as much as I want。 And when I get to function pointer。

 what should I write， I shouldn't write champagne。 I shouldn't write。Delete everything。

 What I could write here。 It's not like an instruction or it's not like give me champagne。

 It's not a terminal instruction。 What I'm going to write here is what it's an address because function pointer。

 we know this box holds an address。 So if I overwrite this with another address。

 I could overwrite this with the address of some malicious function that I want to execute。

 So right now， this holds the address of something probably harmless like add or multiply。

 But I could change this。 I could change this to hold the address of something malicious。

 like the address of delete everything or the address of print out all your secrets or whatever malicious functions or dangerous functions exist in my program。

 So in all of these pieces of code， I'm basically doing the same thing。

 I'm overr past the end of the buffer。 And depending on what variable comes next。

 I am writing something malicious into that variable。 Sometimes it's an English instruction like。

 give me champagne。 Sometimes it's。😊，A terminal instruction， like delete everything here。

 it just happens to be the address of a function。So at this point， you might stop and say， okay。

 I see that this is dangerous， but you seem to be making up these examples。

 And I don't think this is going to happen in real life。

 Like what programmer is going to be silly enough to write a character array and then immediately put a function pointer past it。

 Who would ever do something like this when something like this ever even happen in C code turns out。

This does happen。 It happens everywhere。

![](img/598d15814f22130e809b90df048f89e1_2.png)

Happens in every piece of C code that you write。 So look at this。 This is like the leaderboard。

 These are the top 10 most dangerous software vulnerabilities that people have found through the years。

 Some organization publishes it。 You can click on the link。 if you're curious。

 And we're starting you right off the top。 So if you drop this class。

 You got the number one vulnerability。 It's the out of bounds right。

 It's what we've been talking about writing past the end， It is consistently in the top 5， I guess。

 as of 2023。 It is number one， the most dangerous one。O。So this happens all the time。

 And we're going to take a look at how it happens for Project 1， by the way。

 where you'll be using Python syntax。 Here's a reference slide that I will not read out loud。

 but you can come back to it if you need to。

![](img/598d15814f22130e809b90df048f89e1_4.png)

More reference lightss， I forgot I had to。