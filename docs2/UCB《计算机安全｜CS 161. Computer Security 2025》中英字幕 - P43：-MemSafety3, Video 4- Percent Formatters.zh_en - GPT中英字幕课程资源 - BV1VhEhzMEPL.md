# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P43：-MemSafety3, Video 4- Percent Formatters.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/4f61d6bf9fa96bbb4c5c3b395bf14571_0.png)

So what can the attacker do if they have control over this allimportant zeroth argument？ Well。

 suddenly they can start inputting any string that they want and potentially strings that have percent formatters in them。

 So， for example， maybe they input this string， which just so happens to have a percent D inside of it。

 And so printf will do is printe will say， well， looks like there's a percent。

 So I'm gonna have to grab another argument off the stack to match with this percent。 Now。

 this printf did not provide any additional arguments。

 So this percent formater will match up with some other value on the stack。

 Who knows what And likewise here if the user input contains a percent S。 Well。

 that's a problem because now printf is going to go on the stack。

 try to match something up with a percent S again， more problems。

 the user could even provide something like percent X percent X percent X percent X。

 and what this will do is for every single percent formater。

 The printe function will go on the stack。 look for the next argument that it thinks is on the stack。

It actually isn't an argument。 It's some other value on the stack and print out those values。

 So all of these are ways in which the user could input malicious data or a malicious input to printf。

 And because it has these percent format matters， it causes printf to have mismatched arguments and bad things can happen。

So one thing I haven't answered so far is what do these letters actually mean after the percent。

 what's the difference between a percent D or a percent S， so let's go through those now。

So the letter you put after the percent tells you the type of。

Variable or value that you want to print out。 So when you say percent D。

 I think it stands for decimal， but don't quote me on that。

 but percent D prints out an integer on the stack。 So if print F sees percent D。

 what it will do is it will go on the stack， read four bys corresponding to the next argument that hasn't been used yet。

 and it will print out those four bytes as an integer。 So if I write something like this。

 print up will say okay it looks like the user wants to match this percent D with another integer。

 Now we did not pass in another integer。 So instead what will happen is this percent D will get matched up with something else on the stack who knows what and that value will get printed out as an integer。

 possibly a secret value。 What about percent S， S stands for string。 that 1 I am pretty sure about。

 But I guess if I'm wrong。 its now in a video foreverops But percent S， I think stands for string。

 And remember in C， strings are stored as the address of the start of a character array。

That's just how you store strings in C。 So instead of storing the string itself。

 you write an address。 And when you go to that address， it's the first character of the string。

 That's just by definition， how you store strings in C。 So when print have C's percent S。

 What it will do is it will go on the stack。 It will take the next four bytes that haven't been matched up yet。

 Remember， we're matching up every argument with a percent formatter。 So we'll go on the stack。

 take the next thing that hasn't been matched up yet。 we will read it like an address。

 because like we just said， strings are addresses。 So I'm going read the next four bytes as an address。

 I'm going to go to that address。 And I'm going to print out a string。 And remember。

 string is just a big character array， and we print until we see the null terminator。

 That's what marks the end of a string。😊，So when I see percent S， I go to the stack。

 take the next argument， I read it like an address because a string is an address that points to the first character of a character array。

 go to that address， read out the character array， print it out until I see the Nollbyte and I stop so that's what this percent S would do。

What about percent X， Well， X stands for hexadeadecimal。

 I probably should have looked these up beforehand。 So I wasn't guessing。

 but I think percent X stands for hexadecimal。 What they stand for is not too important。

 But what percent X will do is it will go on the stack。

 take4 bytes and print them out in hexadeadeimmal。 So if you provided an input like percent X。

 percent X， percent X。Now what printntf will do is for each of these arguments。

 it will go on the stack and look for an argument to match this percent formater and print that value out in exodescimal。

So what this light is trying to tell you is just that the letter that comes after the percent sign tells you the type of the value that you want to match up with this printf formatter。

 and depending on the variable type， whether it's a string or integer printf will do slightly different things。

 for example， the percent S， dereference and address， but with percent D， there's no dereferencing。

 we just read the integer and print it up。

![](img/4f61d6bf9fa96bbb4c5c3b395bf14571_2.png)