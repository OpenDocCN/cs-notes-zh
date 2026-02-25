# UCB《计算机安全｜CS 161. Computer Security 2025》中英字幕 - P24：-MemSafety1, Video 10- Steps of Function Call (Detailed).zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， so。Last time in the last video， the last lecture。

 we showed you kind of a high level overview of what happens when you call a function in X86。

 So in this section， we're really going to break it down and make sure we have a really good grasp on how function calling works because this is the difference between you spending 10 hours on Project1 and 20 hours on Project1。

 So really understanding this is going to be key for a lot of the attacks that we're about to see。😊。

So remember from last time what we were doing was we were trying to call a function。

 So there was a function called main that was the caller。 and it was calling Fo。

 and we called that the callee。 and all of these steps were in service of calling the function and the three things that we had to do or we had to shift all three of those registers so that they were pointing at different places So remember that the EBP and ESP。

 they point at the top and the bottom of our current stack frame if we're calling a new function。

 those two registers have to shift down that is the addresses in those registers have to decrease so that they now point at the new stack frame。

 and we also had to change EIP， the instruction pointer to point at the instructions of the new function And the important thing was when F returned when we were all done and we return from the function。

 everything had to go back to where it used to be。 And the way that we are able to restore everything is we put the old values of the register。

On the stack。 So we put the old value of EIP on the stack。 We put the old value of E BP on the stack。

 And only after those two things happened， could we then start changing up all the registers。

 So we saved our work as we went。So now we're going to show to you with all the details。

 we're going to show you exactly how every register changes and what it looks like in X86 assembly。

 so it's going to be 11 steps in total， we're going to walk through all of them。



![](img/96a2b540d8438e6efd3f6cc6e51a7095_1.png)

And in case you're wondering the first few steps are done by Ma。

 as soon as we update the instruction pointer， control shifts over to F。

 and now it is Fo's job to do all of this stuff。 and as soon as we restore the original instruction pointer。

 we go back to mainine and Maine takes care of the last bit of cleanup。

 So in case you're wondering who does what。It depends on where the instruction pointer is。



![](img/96a2b540d8438e6efd3f6cc6e51a7095_3.png)

Okay， so here we go。 up here at the very top， we have a piece of C code that someone wrote。

 And over here on the right， we have that exact same code compiled into X 86 assembly。

 So the compiler took this code and it spit out this corresponding assembly。

 And we're gonna run this one by one to see exactly what happens when the caller function calls the call function。

 So here we go。😊，And as along the way， we are going to use this EIP kind of little arrow to show us what instruction is executing。

 So remember the EIP that's a register。 it holds an address。 If you go to that address。

 it's the current instruction， or I guess the next instruction that's executing。

 So this will remind us of where we are in the code。

 And in the program the EIP is a register tells us where we are。

 Here's our old favorite stack diagram， nothing new about it。

 Every row is4 bys addresses increase as I go from the bottom up。 And if I need more space。

 I allocate more memory at lower addresses。 that's what it means for the stack to grow down。

 Remember， the EBP points at the top of the stack frame。 ESP points at the bottom of the stack frame。

 This is all review from the last few videos。 So here we are in the call。

 the instruction pointers pointing at the call instructions。

 EBP and EP are denoting the caller stack frame。 Now it's time to shift control over to callee。

 I want to call。

![](img/96a2b540d8438e6efd3f6cc6e51a7095_5.png)

The function。 So what am I going to do。 The very first thing I need to do is push the arguments。

 So the caller has to tell Collie， I have two arguments for you。 The number one and the number two。

 I have to give those arguments to you。 And the way that I give you those arguments is I put them on the stack。

 So the caller is going to push the number two on the stack。

 and then it's going to push the number one on the stack。 And now these two values are on the stack。

 So later， if Collie wants to access them。 Collie can look on the stack。

 There are the arguments that the caller wanted to give to me。 So there they are。

 we push the arguments on the stack。 We did so in reverse order， that's just X 86 convention。

 nothing too interesting about it。 But there they are。 And remember。

 anytime you push something on the stack， you have to drop EP down because EP tells us the bottom of the entire stack。

 So if we didn't drop ESP。 These two values would have been floating off below ESP in the abyss。

 and we don't want that。 So we have to drop this stack。

To remind ourselves that these two values are also now part of the stack。

 So that's the very first step。 We pushed arguments onto the stack。So now we're ready to go to colli。

 We're going to shift control from caller to Colli。 In other words， I want to take this EIP register。

 which is currently pointing here。 and I want to put some new value in EIP。

 so that it points down here instead。 I wanted to point at the instructions of colli。 But remember。

 I can't just go to EIP and rewrite the data and EIP because then I'm losing my place。

 I want to remember that EIP used to be here。 And when I'm done， you should come back here。

 So before I can change the value of EIP。 I'm going to save the old value in EIP and only after I save the old value。

 can I change EIP to point into colli。 So that's what this next instruction is going to do。

 So this instruction did a lot of things。 So I'm gonna walk you through it。

 The first thing it did is it went onto the stack and it pushed a value。

 This value tells us what used to be an EIP。 Another way of thinking of it equivalently is when I'm done with this callee function。

 go back。😊，HereThis is where you left up。 It's like a bookmark。 So when I'm done with colee。

 go back here and start executing this thing again。 So that's the value that I put on the stack。

 It's an address。 If I go to that address， I'll find the next instruction in the collar that I have to execute after I'm done with the function。

 And remember， any time I push EP drops down。 So that's why ESP went down。

 used to be up there now it's down here。 And only after I wrote this value down， I saved my work。

 only then could I take EIP and change it so that it now points a call。

 So the call instruction in X 86， does all the hard work for you。 It pushes the value。😊。

Of the old EIP， so that I remember it for later， it shifts E S。

 E SP down so that I remember that it's part of the stack。

 And then it moves EIP over to point of the callly instructions。 So EIP now has a different value。

 but that's okay。 I remember the old value。 It's right there。So that's step 2。And step 3， I guess。

 in our numbering。Okay， so now it's time for Collie to do some stuff as well。

 So what does the colley want to do， The colley wants to change its stack frame right now。

 EBP and EP is still pointing up here at the call stack frame。 I don't want that。

 I want a new brand new stack frame all for myself。

 So I want to change EBP and EP to point at the bottom。

 I want them to create a new stack frame for me。 So these three instructions are going to do that for us。

 Almost every function that you'd ever write， starts with these instructions。

 So we sometimes call them the prologue。So you'll see them all the time。 But anyway。

 let's start with these prolo instructions。 So the very first one says push EBP。 What does that do。

 It takes the value in EBP。 It's an address。 It's the address of whatever this is。 I take that value。

 and I push it onto the stack。 So here's the value。 I copy those bits onto the stack。

 So basically what I've done is I've taken the value in EBP。 I've copied the bits onto the stack。

 So now if I change EBP。 Its old value is sitting right there on the stack for me later。

 So that's what I did。 And now that EBP has this old value saved。 I remember the old value of EBP。

 It's whatever this address is。 now I'm safe to take EBP and change it。

 So it no longer points up here。 I rewrite it and now it points down here。

 So that's what this second instruction did。 It basically said。

 take EBP used to point up here and drop it down here。 And in particular。

 we'll drop it down to wherever the EP is。 So they both now。😊，Hold the same address。

 They are pointing at the same place。 Both of those statements mean the same thing。So what did I do。

 I took E BP。 I put its old value on the stack， so I don't forget it。

 And then I changed its value so that it now points。Further down on the stack。

 I'm in the process of creating a brand new stack frame。Okay， I'm almost done。

 So two of my registers got changed。 EIP and now points over here。

 EVP points down here and both of the registers that I changed have saved values on the stack so I can put them back later。

 So now the last register I have to change this EP。

 So what I'll do is I'll take ESP and I'll subtract， say4 from it。

 So now I've created this new stack frame。 this new area that the callee is able to use。

 So this is a brand new stack frame。 This is the top of the stack frame。

 This is the bottom of the stack frame and the call is free to use this space for whatever it wants。

 It can use it for scratch space， local variables， it can draw on it， whatever it wants to do。

 This is the call dedicated stack frame。 Now question you might have how did I decide this was for and not8 or 100。

 And it turns out when the compiler changes this C code into X 86 code。

 The compiler can think about how complicated this callee function is， say how many local variables。

Does it have What sort of computations does it have to do And the compiler can substitute the appropriate number here。

 So when the compiler is translating this C code to this X 86 code。

 the compiler can write whatever code it wants。 And if it thinks that the col is a super complicated function。

 it could put the number100 here or 200。 But in this case， it's a tiny， simple little function。

 So we just put the number for。 But that's the choice of the compiler。

 So in case you're wondering where the four comes from， the compiler picks。Okay， so we did it。

 All of the registers have changed。 EBP and EP now point further down。 EIP points in the colee。

 So now it's time to do whatever the collie wants to do。 If it has local variables， great。

 put them on the stack。 If it wants to do additions， multiplications。

 bit shifting whatever collie wants to do， it's free to do so now。

 So anything that col wants to do we'll do it here。 In this case， the colgue just does two things。

 It creates a local variable。 Okay， great， we stick it there。 and it returns 42。

 why because colgue said so。 So all we'll do is we'll just take 42。 put it in a register。

 turns out EA X just happens to be aware you put the return value， not the most important detail。

 But basically think of this as the col is doing stuff。 And whatever stuff it is。

 I don't really care。 It's just the collie doing stuff。😊，Okay， so now the col is all done。

 And the col says it's time to return。 I'm all done。 It's time to return back to the caller。

 but all this stuff is messed up。 EBP is not in its original place。 Neither is EP， neither is E IP。

 I need to put all these registers back where I found them so that the caller can keep executing its own code like nothing happen。

 So now it's time to go back and put everything back where it used to be。

 and the instructions for doing that。 sometimes are called the function epilogue。

 So every function we write ends in these three instructions。 And you can think of this as cleanup。

 It's putting everything back where it's supposed to be so that the caller can continue on with its life and executing whatever code it wants to do。

 So the epilo has three steps corresponding to putting these three registers back where they used to be。

 So the first thing I have to do is EP。 Remember when we moved EP down to make a new stack frame。

 I don't need that stack frame anymore。 Coley is all done。

 So I'm going to take EP and move it back up。😊，So my first step in this epiloggue， I'll take ESP。

 which used to point down here。 I will move it back up。 So here I just said， take ESP。

 drag it up to wherever EBP is。 these two registers now point at the same address and basically what I've done is I've cleared out the old stack frame。

 All this stuff is now below ESP。 It's in the void。

 If you want to replace it with zeros you could I didn't bother because I'm lazy。

 but basically it doesn't exist anymore。 It's below EP， we don't care about it。

 So that's the first step。 EP went back up。 Now let's take EBP and move it back to its original place and put the original value back。

 Now， where did I put the original value of EBP。 If only I didn't overrite it。

 What was its original value。 remember， that's what we put on the stack。

 This value on the stack just so happens to be the old value of EBP。

 So all I have to do is take these bits， the old value and just stick it back in the EBP register And that's what this next instruction does。

Pop EVP。 So what does that do， It says take the next value on this stack。

 which is this old EVP value， put it back in the EVP register。 And when I do that， look。

 EVP used to be down here。 now it goes back to its original place。

 and how did I know the original place because I saved it on the stack And remember。

 anytime you pop something， ESP goes up by4。 So I'm done using this value， ESP goes up by4。So great。

 EP is now back up。 The stack frame is deleted。 EBP is back to its original place。

 Now I just have to get EIP back in its original place， the instruction pointer。

 So I want this to go back to its original place。 Now， where was the original place。

 If only I had written it down somewhere。 Well I did， It's right here。

 This is the original value of EIP before I overrote it。

 So all I have to do is pop this value off the stack。 copy the bits into the EIP register。

 that's gonna put EIP back where it's supposed to go。 So that's my last step。 I will take EIP。

 I'll take these bits on the stack， and I'll copy them into EIP。

 that puts EIP back where it used to be。 So you see how these bits pointed over here。 Well。

 when I put those bits back in EIP EIP points back here， too。 So EIP is back where it used to be。

 So that's great。 Now the caller can continue executing whatever it wants to do。

 So we're almost done。😊，One tiny little thing we have to do at the end is we push those arguments。

 Remember when caller started by pushing the arguments。 we don't need those anymore。

 Caller done with them。 Col is done with them。 So I'll just move ESP up to delete those arguments off the stack。

 And I'm done。 if you stare at this and you go all the way back to step 1。

 these diagrams are exactly the same。 EBP is back at the top。

 EP is back at the bottom of the caller stack frame。 and EIP is back in call where it belongs。

 So I put everything back where it used to be。 So that was the process。 It's a lot of steps。

 And if you're confused it's totally okay。 This is pretty involved and watch it a couple times stare at it a bit。

 But these are the steps that it takes to call a function and return from a function。

 And when you get the hang of this project when will be a breeze。 Well， it's a little tricky。

 but not as tricky as it would be if we didn't totally get this。



![](img/96a2b540d8438e6efd3f6cc6e51a7095_7.png)