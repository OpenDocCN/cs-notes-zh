# 【从零开始学习 ARM 汇编语言II Udemy】 p45 p44 10.4. Coding  Testing the UART Driver -BV1RJU6YwEM8_p45-

Hello， welcome back。 So let's。Test out our U U driver。

 I'm gonna create symbolic names for some commonly used keys that。We use keys such as delete space。

 escape back space。Courage， return， line feet， etc ce。These aren't keys like ABC。

 So I'll say C are here for courage return。 These are standard AS symbols。This one is represented。

By 0 x0 d。And then I'm going to have B S for backspace to clean something。This is represented by0 x。

Sure 8。 And then we're going to have LF for line feed。一QU。This is going to be represented by 0 x，0 a。

And we're going to have escape， E S C。E Q U， this is going to be represented by 0 x。完毕。

And then we're going to have space。This is going to be represented by。So x2，0。

And then we're going to have delete。😔，Which we should。Represent by。一Q you。Through x，7 F。Okay。7 F。

 right。 So to to go to the new line， we need to send carriage return and line feed。

 So we need to send two characters。 I'm going to create。 I'm gonna create。

I'm going create a label or a subrout for new line， cause it takes two characters to send a new line。

 I'm going to come over here and just put a label here。New line。And this。

 we were use to send new lines。 We start off by saving the。The link register， push。L伦。And then。

We start off by， and then we move。I will courage to return into register RC row。Yeah， courage return。

 and then once we've moved it， remember r0 is like the variable is the register I holds the argument for a while。

You at right character subroutine。 So then once we've moved this interor。

 we can branch to the subroutine， too。Send it。And then once we've done。We do move。R0， line feet。

And then。别。Out。You are。Right character， and then。Okay， so when we push link register， we got a pop。

The program counter register， which is PC。And then。Over here， we pop a PC in our。In our U at In。

 we start by pushing link register and then we pop the program counter register。Okay， over here。

 also we forgot to align。This is the last sub routineout。 This the end of the fall。And over here。

 and then I'm going to clean the space， we create it。😔，Goodness。😔，Anyway， I'm going to go up。

And then we've got this for new line so we can try this out。

We can simply we start off by initializing ourU at。And then we can。😔。

We can send a character A and see， what we get。I'm going to come over here。😔，I'm gonna do。

How about rather than send a， we going to send ABC D A to Z out send a to Z。 So do move our4。

Over here， there should be a BO here。😔，Or to move。二 for。The character E。And then once that is done。😔。

I'm gonna take。What is in R4 input put into our0 move。Into r0， what is in our4？And then once I stand。

 I'm going to write it below。What。Right， character。Right， and once that is done， I'm going to。

Add one to what is in alpha to go to the next character in the alphabet。I can simply do。U。R 4， R 4。

 add1 to r4 and store the results back into our4 like this。And then I'll check what。The character Z。

 I wan to stop at Z， so I can do CP。R 4， compare what is in r 4。Re character Z。If so， skip。Compare。

 if it's not Z， then we can keep going。Wait， I'm gonna use capital Z here D PL S。P。At P0， okay。

 we'll come back to the top here。This is L P 0， okay。Then。Once we are done， we can。 yeah。

 we can go to a new line if we want or do BL。Pranrunch， we created a label for new line。

 so we can simply see new line。 and then Ill do move。R0， I'm going to write exclamation sign here。

Like this and then。😔，We can be out。😔，To to you at。😔，And I score right character。And then。Yeah。think。

We can put a loop somewhere， and try this out。Okay， so let's see how this operates。Start from here。😔。

Come over here， and then。We run to the end。Okay， so let's build and see I suspect we may have a number of  errors。

Click over here。 we have two arrows symbol not defined。 Which symbol is this。

You add zero FR register。😔，Okay。That should be an equal sign here。Come on Miss。Okay。

Click here to build， it's build successfully。System control R CGC GPIO underscore are not defined。

RC GC G P I U R unless you want the name， one name we gave the register， RC GC G P I O。

Is from the word ci controltro， no problem。I'll just copy it and bring it over here。😔，Yeah。

 this should be RRC， no RG。IC GC， okay。F CGC， okay， build。

Now let's download onto our board and see what we have。Actually， before we download onto a board。

 there are number of things we need to take care of。

 come to your come over here device and then start up that S file in the reset handler。

 I'd like you to comment on this these two lines。 There is something in the system in it that interferes with our U at driver。

 as it is currently。So we need to commentend these two instructions。

 these two lines from the reset handler once you've done that。Let's inspect our will code again。

Over here， I realized there was an anomaly over here。

When we came and we loaded the line control register， and I did。Add Arro Arro here。 this word here。

 I suspect initially， it was an end。 It has to be add a mistyped add。 And then over here。

Were using line control word length underscore 8 plus50。En内able。

So verify that you have this corrected over here like this。Right。

 so this has to be done and over here too。In the PC T R， when we。When we did a configuration。

 remember to store it back into the register， the store statement here and over here。In our U at。

 in our read character and write character sub routine。

 the end here has an S at the end as and S and and S over here， right。

 So once you verified all of these changes， then we can build again。

And then once it's built successfully。We can download onto a board。一登录。

I'm going to open my serial program。Com 8， and then O。 and then I'll come to set up0 port。

 and then I'll set a speed to。115200。 And then okay。 And then I'll press to reset my port。

 And as you can see， this is what we said， we said。

 we are writing a through Z and then exclamation sign and then new line。

 So this is a our U art driver is working just like we've configured it。 So in the next lesson。

 what we're going to do is we going to。

![](img/d4f6c3f905374e249edf3dafb91e2789_1.png)

Make our U U driver accessible the from a C file。 I think that is much more practical。

 It's much more practical to have the driver's initialization and subrouts written in assembly and then calling them in C。

 So in C language， we're going to test prints scanf we see both we see by directional U at you know communication essentially。

 we'll be able to read and write characters there。Right so this order is for this lesson and I'm going to attach my project to the video。

 So if you face any errors or yours is not working like mine。

 you can simply download the project attached to the video and try it out right So this order there is and I shall see you in the next lesson。



![](img/d4f6c3f905374e249edf3dafb91e2789_3.png)