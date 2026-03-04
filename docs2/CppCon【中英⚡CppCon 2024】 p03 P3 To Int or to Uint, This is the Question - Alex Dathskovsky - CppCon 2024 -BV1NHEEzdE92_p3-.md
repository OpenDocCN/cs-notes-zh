# CppCon【中英⚡CppCon 2024】 p03 P3 To Int or to Uint, This is the Question - Alex Dathskovsky - CppCon 2024 -BV1NHEEzdE92_p3-

🎼In fact， I just。Bumped into somebody in the hallway earlier and we ended up talking about it and he had a very different perspective on the whole talk than I did that just happens because we had a collective experience and we're walking around。



![](img/79984fce4486f9627ade910c68bba163_1.png)

![](img/79984fce4486f9627ade910c68bba163_2.png)

Okay。Let's start。 So，1st of all， I want to say thank you， everyone for coming and choosing my talk。

 There are so many great， great talks in this conference。

 and you choosing in being here in this big room。😊。



![](img/79984fce4486f9627ade910c68bba163_4.png)

I am amazed。 Thank you very much for coming。And。Few words about myself。 I'm Alex Zovsky。

 I have more than 17 years of system programming。 I did a lot of different system from medical system that save lives to security system that take life。

You have to do both， you know。I work right now。 I work in a company that's called speedeed Data。

 We are a great startup， and we are developing the next big thing in big data。So basically。

 what we are doing is we are creating a new CPU， a general pul CPU that will accelerate your analytics。

😊，By a lot。 And maybe in CPP cone next year， I will finally have a chip。

 and I will do something about the chip， finally。😊，And I have a Liedin。

 So there I speak a lot about C plus plus things， riddles， things that people hate。

And if you want to join there， you can do that。 That's gonna be really great if you just follow me。

I started a blog because LinkedIn is just small posts。

 And I wanted to post more and explain more that people would understand。 So CPP next。

That's a site that I started。 And I have a YouTube channel。 I already have 7 videos。

 So after this talk， go， like and subscribe， I will appreciate it a lot， but not now， right。😊。

And now we can start with2 int or two U int。EWhat can you expect from this talk。 So，1st of all。

 I want to say it's not gonna be a talk。 It's going be a ran me ranting about C plus+ and how horrible all those rules about ins and U ins are。

And it's not bad for people。 So we have to understand those types to really appreciate them and really understand what they are doing to our program。

 Any of you ever started looking at these types and just like。

How do would they say the first thing that comes to your mind when you do it is just putting an int everywhere。

 right。Put your hands if you're thinking about integers， int。I don't know if' it's wrong or right。

 but it's a problem。 Our mindset is like from school is going to in。

 and it's not always the right type for the job。 So we will talk about that。I will show you many。

 many pitfalls of what can happen if you select the the wrong type。Bad things can happen。

 There can could be undefined behavior。 There are so many small， small rules。

That it's pretty amazing。 How can you fall with the simplest thing in the language。😊，So， let's start。

And I selected to start with quotes for unknown people for， for reason， for sorry， for here。

 we have Gurne， which is an anonymous person in C plus plus。 Nobody knows him， right。

So B is saying there are far too many integral types。

 There are far too many lineient rules to understand how to work with them。And he is saying。

 basically， from all this is， stay simple。 always use sign types。Is he right？We will see。

Then we have Dale。 Dale is a very known blogger， he works it at media。

 He uses integral types a lot with graphics and floating point types。

 and he is basically saying something totally different。

 He's saying you don't have to use sine integers。 you almost never have to use s integers。

Indexes sizes， everything is unsed。 So why is our mental state is saying always use an integer。

 It's not always correct。 So he saying， stop using that。 use only unsed types。Is he correct。

 I'm not sure about that， as well。So just for you to understand。

 this talk is not gonna to be controversial。 You will not get of it like use only this type。

 This is not the point of it。 The point is for you to understand the importance of the selection for the correct integral type that something so simple can be so complicated。

And there is a disclaimer， everything I'm going to show you will be compiled for X 86。

Each machine has a different eyesa， and it works a little bit different。

 I selected X 86 because most of you probably use X 86， right。

 Someone works on something that is not X 86。Some people， O， but most of you use X 66。

 So it's gonna be beneficial for most of you to understand the machine that you are using。

And most of the compilation will be done with Cl 12。And there reason for that， wait for it。

And to get us started， let's start with a simple example for a simple， simple function。

 Basically two functions。 One is for sine integers， One is for sine integers。

 All this function is doing is receiving two parameters， sine or sign， but the same type。😊。

EIt's doing a sum of A And B， and then divide it by two。Same functionality， different type。Now。

 I want to see hands。 Who thinks that the unsigned version will be faster。

Better assembly fe on times。Almost no one sign。 Who thinks the sign will be better。

You think both will be the same。Okay，2， the one will do better。 Okay， let's try to look at it。And。

 of course。Let's try and start with the disassembly of the first unsigned version。Already。

 we can see that the assembly for this is pretty simple。 Three lines of code。That's amazing。Now。

 for this talk， you will have to understand X 86 assembly a little bit。 But don't worry。

 I will teach you some assembly。First thing that you need to know that X 86 machines have resists。

 they have different size registers and they are built with 8 bit resists。

 16 bit registers and so on until 64 bit registers and that is because it has historical reasons。

 they just build the processor one on top of the other。

 So they start with 8 bits and went to 64 bits which is the standard right now。

 But you have all of those inside your machine today。

 the most important thing just to understand the code is to see that things that start with R。😊。

Are the 64 beat registers， things that start with E and have3 letters are the 32 beat registers。

 Other things will not be covered so much。 So you will be fine。

 And if you want to know more about this， you can see Dave Sca's very good talk from CPP now 2023 under the hood。

 So I I think it's going to be very beneficial for everyone to understand how those things work。😊。

Now let's start。The first instruction from this disassembly is L E A。

 L E A is an instruction that said load effective address。

 This instruction doesn't load an effective address。 This instruction is basically used。

To calculate and speed up calculation for registers。 So as you can see。

 instead of using two add instructions， the compiler could generate this instruction with RD I plus R S I with one as。

 one as code line。 So that's cool。 And you can even use more registers in the same instruction。

 I don't have those here。 But you can。 And the compiler actually generate those things。😊。

The next thing is， shift right。No division here， A shift。 And then we just return。

Anyone can say why shift and not division？We will talk about it， but I want to see if you understand。

Sorry。Yes， but we will understand why it's faster as well。Okay， now let's look at the signed version。

T it's bigger， and it's slower。Not by that much。But still， it has more asmb code lines。

And if we will start looking at it， we can see it does the same thing with the L E A。

 It still loads the effective address。But then， it does something peculiar。

It takes a copy from the sum that it just did and copies it to R A X。

