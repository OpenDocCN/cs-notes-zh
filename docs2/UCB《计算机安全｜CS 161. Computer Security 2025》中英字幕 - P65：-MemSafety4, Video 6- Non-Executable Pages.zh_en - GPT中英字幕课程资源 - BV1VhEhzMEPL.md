# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P65：-MemSafety4, Video 6- Non-Executable Pages.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

![](img/ae614902f4e7a3d877b8221ad1b3124c_0.png)

Okay， so the very first mitigation that we'll look at is something called nonexecutable pages。

 So thinking back to our five steps of the attack， we are now going to really focus in on step number 5。

 where the attacker starts executing malicious shell code。

 We're going to try to make this really hard for the attacker。

 And the way we're going to do that is we're going to exploit the fact that the memory layout consists of four separate sections。

 Remember the stack， the heap， the data and the code。😊。



![](img/ae614902f4e7a3d877b8221ad1b3124c_2.png)

![](img/ae614902f4e7a3d877b8221ad1b3124c_3.png)

And something we'll notice is if you look at these four sections。

 only some of the sections will ever contain program instructions in normal function execution。

 So remember， what are the program instructions。 That's the X86 code that you write that you then assemble into ones and zeros and write into memory and the program CPU executes those ones and zeros as instructions。

 That kind of executable data。 That is the actual instructions of the program。

 they don't live just anywhere in this memory layout， they always live down here in code。

 And so when the program is executing normally， you should never have to execute instructions up here。

 The CPU should never have to read data up here in the stack。

 read it as an X 86 instructions and then execute because that's not where you put the instructions。

 You put them down here。 And so we're gonna take advantage of this fact to set some permission bits so that some of these sections are simply not allowed to be executable。

What that means is if the program goes to that address。

 reads it as an instruction and tries to execute it。 the operating system will say no。

 you can't do that。 The instructions don't live here。

 You should never be reading these things as X 86 instructions。 So that's the idea。

 And so looking at these four sections， we can reason and say the code section that probably has to be executable。

 That's where you put the actual ones and zeros corresponding to X 86 instructions。

 So we should really set the code to be executable。 What about the data。

That's where we put global variables。 Global variables aren't instructions that we should execute。

 So this part should not be executable。 And likewise， the heap。

 where you put dynamically allocated data， should not be executable。

 And the stack where you write local variables should not be executable。 So these top three sections。

 they should never have X 86 instructions living in them。 that's just not where they go。

 So the operating system can set these three sections of memory to be not executable。

 And if the CPU tries to execute instructions that are written in any of these three sections。

 the operating system will say no， and will stop you from doing that。

Something else we can do since we're here in setting permission bits is we can also set some of these sections to be read only。

 So some of these sections， the program needs to modify those sections because the user wants to write data or they want to assign a variable。

 But some of these sections never really have to be changed。 So again。

 thinking through each of the sections one by one， the stack that does have to be writeable if someone defines a local variable and they change the value of the variable。

 We have to overwrite some data in the stack。 So that section should be writeable。

 What about the heap。 Well same thing if someone now uses malic to allocate some data and they want to write data into that space。

 They should be able to write to that data and in the data section。

 user should be able to write to global variables。 But the code section。

 when you're running a piece of。Software， you're not rewriting the code while the code is running。

 You write the piece of code， and then you run it。 It shouldn't be the case that you write a piece of code。

And then you're changing the code while it's running。 That's not how we program things。

 So this code section， we can actually set it to be read only when the program is running。

 nobody should be touching this code section。 The program itself should not be editing its own code while it's running。

 There are some very strange programs out there that might want to do this。 But in general。

 there really isn't any reason to do this。 You should write a piece of code and run it。

 You should not change pieces of code while you're running it。 That's very weird。 And so in summary。

 what we've learned about setting permission bits is。😊。

If you're thinking about what section should be executable。

 only the code section should be executable， these three sections should not be。 And by contrast。

 when you're thinking about sections being writeriable。

 these top three sections should be writeriable， but the code section should not be。

 And so putting all of these permission bits together gives us something called nonexecutable pages。

 And the idea here is。You can actually set each part of memory to be executable or writeriable。

 but not both。 So what you'll notice with the permission bits that we set is that each of these sections is either writeriable or executable。

 but there is no section that needs both permissions。 For example， the code has to be executable。

 but it doesn't have to be writeable。 And these three sections have to be writeable。

 but they don't have to be executable。 So that's something we've noticed this when you're setting these permission bits。

 you'll get the behavior that one of the bits is on， but not both at the same time。 And by the way。

 how do you implement this。 If you think back to virtual memory。

 which is something you might have heard from C S 60 and C or some other prerequisite course。

Virtual memory has to keep track of these permission bits for different parts of memory。

 So this is something that the hardware has to already do。

 Your operating system already has these permission bits built in。

 So you might as well set them properly instead of turning all the bits on。

 You should carefully set the bits so that each page is writeable or executable but not both。

 And this is something that the operating system already implements。

 So you don't have to do anything extra。 You just have to do what the operating system already supports。

 By the way， this thing has a bunch of different names。 Sometimes people call it write X or execute。

 which reflects the fact that everything is writeable or executable but not both。

 Windows gives it this special name and the bit itself is called no execute。

 So people tend to use different names for the same thing。

 but they all refer to the same idea or you set permission bits on the pages so that everything is writeable or executable but never both at the same time。

Okay， so now that we know what non executable pages are。

 we should probably talk about why they're useful。😡，I should probably go back to this slide。

 So why is this thing useful， Why is it useful to have things executable or writeable， but not both。

 Let's think back to those five steps of executing a buffer overflow attack。

 What is the attacker want to do， they want to write shell code into memory。

 and then execute that same code。 That's what it means to do one of those buffer overflow attacks。

 you write the shell code into memory， those ones and zeros。

 and then you execute those ones and zeros as code。 But if we have non-executable pages turned on。

 you cannot have both， the attacker wants both， they want to write the data and then execute that same data。

 But if we turn this defense on the attacker is not allowed to do both。

 if they write the data into memory， they can execute it。 So now they're stuck。

 and this is how we stop the attacker from this fifth step。

 even if the attacker is able to write the shell code into memory。

 they will not be able to execute it because this defense says if you write something into memory。

 it is not。

![](img/ae614902f4e7a3d877b8221ad1b3124c_5.png)

Excutable。 It's not allowed。 So that's why this defense is so effective。

 It's because now attackers cannot write something and then try to execute it at the same time。

 If they write something into memory， it's going into one of these three sections。

 which we've marked to be not executable。 So that's why non executable pages stops。

At least some memory safety attacks。