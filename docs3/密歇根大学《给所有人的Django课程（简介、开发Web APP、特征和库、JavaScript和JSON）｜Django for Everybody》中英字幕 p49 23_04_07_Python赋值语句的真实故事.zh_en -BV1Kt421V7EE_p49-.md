# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p49 23_04_07_Python赋值语句的真实故事.zh_en -BV1Kt421V7EE_p49-

![](img/abbafe424d25d07754c8bba4f1a6d19d_0.png)

![](img/abbafe424d25d07754c8bba4f1a6d19d_1.png)

🎼Yeah。Yeah。🎼Yeah。Hello。🎼I have a confession to make。

Perhaps you've taken a class from me where I misled you on what's going on in Python。



![](img/abbafe424d25d07754c8bba4f1a6d19d_3.png)

🎼But first， we got to take a look into the past。 The following two slides from Chapter 2 of my Python for everybody textbook and course that's available all over the place。

 It's introduced more people to programming。

![](img/abbafe424d25d07754c8bba4f1a6d19d_5.png)

In the millions than any other course in the world， these slides are misleading， and at worst。

 they are 100 per cent wrong。 Let's take a look at the slides and see why。



![](img/abbafe424d25d07754c8bba4f1a6d19d_7.png)

Here's a slide。It's like the fifth slide of that class。

 A variable is a named place in memory where a programmer can store data and then later retrieve it using the name of the variable。

 programmegrammerrs get to choose the names of the variables。 They're like labels in memory location。

 you can change the contents of a variable in a later statement。

 So X equals 12 takes little drawer labels at X puts a 12 in there。 X equals 14。

 puts a 14 in a drawer and labels it。 Y。😊，But then if you change it like x equals 100 later。

 that replaces the value 12。2 with the value100。

![](img/abbafe424d25d07754c8bba4f1a6d19d_9.png)

This is what's really happening。 A Python variable is a symbolic name that is a pointer or reference to an object。

You can kind of see why I didn't explain this in the very beginning。

 We actually can use the I D function to say， where is this variable pointing to Now。

 not all Pythons。 This is the C Python， The Python that is written in C， the C Python， We can ask it。

 Where is it。 So if we say x equals 42， and then y equals x。

 you'd think that'd be two locations in memory， but it's not。

 It's two pointers to one location in memory， And we can figure this out by saying print I D of x。

 which is like， hey， where where would we find x in memory， And it's got a number。

 And then we say print I D of Y。

![](img/abbafe424d25d07754c8bba4f1a6d19d_11.png)

![](img/abbafe424d25d07754c8bba4f1a6d19d_12.png)

And it's the same place。 Okay， so we only have。1，42， we don't have 2，42s。

 but we have an X pointer and a Y pointer that points to it。 So， for example， we can say， you know。

 take the object 300。 It's an integer。

![](img/abbafe424d25d07754c8bba4f1a6d19d_14.png)

We say x equals 300。 the 300 exists somewhere。And x。When we s equals 300。

 it points at that object that exists somewhere， and it has a location。

And then what happens if we say x equals 2000， the 2000 is a different object in a different location。

 and x then points to the 2000。 the old object integer 300 may still be there。

 But it's on what we'd call a free list。 Some might be on a free list。

 but the idea is that you're changing the pointer x to point to the integer 2000 rather than changing the contents of a drawer labeled X to be 2000。

 Again， if we say y equals x， you'll see that y does not make a copy of 2000。

 It simply points to where the same 2000 that x is pointing to。

 So y equals x says take the address that x points to and put that address in Y。



![](img/abbafe424d25d07754c8bba4f1a6d19d_16.png)

Okay。😊，Now， if we switch to more complex objects like a list。



![](img/abbafe424d25d07754c8bba4f1a6d19d_18.png)

It makes a little more sense。X equals list says let's make a list， and we can say print I D of X。

 and that says this is where it's at。And we can append hello to it。 Now。

 the thing is that didn't change where X was， but it did change what was in x。

 So X append hello adds hello to the end of my list。

 and I can say where's X print Id of X and it's in the same location。



![](img/abbafe424d25d07754c8bba4f1a6d19d_20.png)

Okay， now， if I make a copy， not exactly a copy when I say y equals X。

 that makes a new y that points at the same place。 And that's why if we do an x dot append world and print Y。

 we see Ho world， even though we appended to X。 and that is because Y and X are pointing to the same place。



![](img/abbafe424d25d07754c8bba4f1a6d19d_22.png)

![](img/abbafe424d25d07754c8bba4f1a6d19d_23.png)

So y equals x is not copying。As we might expect in the drawer analogy， it's not copying it。

 It's just adding a new pointer now。Sometimes you actually want to make a full copy of something。

 You want an you got a list。 You want an independent list。

 And so this is a pattern that we would call copy constructor。 There's other ways to describe this。

 We make a list。 X equals list。 print I D of X。 It's it at location， we append hello to it。

 X is in the same place。 Now， instead of saying y equals x。

 we say Y equals list print X list is the constructor for lists。

 And that says read through the list X and make full and independent copies of everything in that list and make a new list and have y point to that。

 That's what it's say。 So if we say where is Y print I D of Y。

 we see that the x is in one location and the y is a list that's in another location。😊。



![](img/abbafe424d25d07754c8bba4f1a6d19d_25.png)

![](img/abbafe424d25d07754c8bba4f1a6d19d_26.png)

![](img/abbafe424d25d07754c8bba4f1a6d19d_27.png)

And then if we add world to X and we print it， we see hellello world， but y。

 because it's an independent copy stored at a different location。



![](img/abbafe424d25d07754c8bba4f1a6d19d_29.png)

Print Y just says hello， Okay， so that is a copy constructor。So if you ask chat GPT， like。

 what's a Python variable？Chppet TP T is wrong。 It is bought into the simplification。 Now。

 if you dig in a little deeper， you can say， are you sure it's not a location。

 but it really a pointer to a location。 blah， blah， blah， blah， bh， blah， bla， bla， blah。

 But perhaps it's because so many textbooks like mine start in the beginning with that grand oversimplification now。

I'm very， very sorry to have misled you back in Python for everybody。

 But the notion of a variable being a drawer is not wrong。 It's just wrong in Python。

Things like languages like C or Fortrann or cobal。 They tend to have this drawer model where the variable x is one draw and the variable Y is another draw。

 and they have independent things。

![](img/abbafe424d25d07754c8bba4f1a6d19d_31.png)

When you get it around to it， when you learn C， and I recommend my C programming for everybody course。

 www。cc3。 com。In chapters 5 and 6 of that， you learn about pointers and data。



![](img/abbafe424d25d07754c8bba4f1a6d19d_33.png)

And the difference， the key here is that Python was written in C in the internal implementation of Python。

 its C code。 And so the notion of a pointer and the data that the pointer points to is completely natural in C。

 It's just been sort of hidden for us。 We can take a look at it using the I D function and get a sense of how variables and assignment statements really work。

 So again。Sorry to have misled you。 I guess it's better late than ever for me to talk to you about the real way that assignment statements work in Python cheers。



![](img/abbafe424d25d07754c8bba4f1a6d19d_35.png)