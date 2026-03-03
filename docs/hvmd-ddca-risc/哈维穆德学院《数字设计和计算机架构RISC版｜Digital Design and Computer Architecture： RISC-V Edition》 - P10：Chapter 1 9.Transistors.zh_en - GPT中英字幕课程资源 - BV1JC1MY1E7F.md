# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P10：Chapter 1 9.Transistors.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Greetings， and welcome to the next exciting installment of digital design。😊。



![](img/714b69c9f535ff21a2acbe1e4fbfda49_1.png)

Topic of this video is Cmos Transistors。So logic gates are built from transistors。

And a transistor can be viewed as a three ported voltage controlled switch。So ordinary。

 something like a light switch is a two terminal device has two sides that are either connected or not connected。

 depending on how you flip the switch。In a transistor。

 we have a third terminal that receives a voltage， and that controls whether the switch is on or off。

So this is called an en moss transistor。 We'll talk in more detail in a moment why it got that name。

 but it's got。Two terminals called the source and drain that are either connected or not based on the control voltage of the gate。

If the gate is at a low value。Then the source and drain are disconnected。 We say the transistors off。

If the gate is at a high value， then the source and drain are connected。

 and we say the transistor is on。So integrated circuits were co inventedvented by Robert Nois。

A noise was known as the mayor of Silicon Valley。He was very influential。

 He a co founded a fairchild Semi in 1957。And then many engineers who were from the early days of Fairchild went off and founded other companies that went on to be quite important in Silicon Valley。

And one of the most prominent was Intel。Noise and some of his colleagues left Fairchild in 1968 and started another small company that became Intel。

Noise is known for coininventing the integrated circuit。So let's talk about how this works。

 And when need to begin with some chemistry， Transistors are built from silicon。

Which is a semiconductor。So pure silicon by itself， is a poor conductor。

It forms a diamond shaped lattice。It's hard to draw that in three dimensions。

 So we'll draw it on a plane in which each silicon atom。

Has four electrons in its vence shell and therefore bonds to 4。Adjacent Adams。

Because every one of these bonds is used， there are no free electrons to readily move around the lattice。

 And so pureer siliconili by is a poor conductor。But if we introduce some impurities。

 we call that doping， and a silicon can become a good conductor with the dops。So， for example。

 if we add a group 5 element， such as arsenic。To our silicon。

Arsenic has five electrons in the valence shell it's a group of five。Element。

And so there's one electron。That is not tightly bound。

And it could leave the atom and start wandering around the lattice。

 leaving a positively charged arsenica ion and a free electron。And so now。

 electricity could be carried around。A semiconductoror with these free electrons。

 electrons have a negative charge， so we call this n type。On the other hand。

 if we introduced a group3 impurity， such as Boron。

A group 3 element is has only three electrons in the vence shell。

So we could borrow an electron from a nearby atom。That would give us a negatively charged boron and a missing electron。

At the nearby Adam。That missing electron is called a hole。

And it could be filled by an electron from another。Near by Adam， filling that hole。

 leaving the positive charge here。And so forth。So the hole can propagate around in just like an electron and a missing electron。

 a missing negative charge behaves like a positive charge。 So we call this P type silicon。

So N and P type silicon are just silicon doped with a small percentage of the atoms replaced by something in group。

3 or 5。Now， we can build transistors。And the far and away most common type of transistor today is the metal oxide semiconductor transistor M O。

It's made from a stack。Meddle。Sililione dioxide。And semiconductor。

The top terminal is called the gate。Historically， it was made out of metal。 More recently。

 it was made by polycrystalline silicon， also known as polysilicon， which acts like a conductor。

And then even more recently， we've started using metal on these gates again。In between， is a layerir。

Of silicon dioxide， S I， O 2。It's also known as glass， and it's an excellent insulator。

And then underneath， we have the silicon substrate。Which will do P type。

Will make a source in a drain next to the gate and dope those in type。

Any time you have a petta injunction， that forms what we call a dietode。We'll ground our substrate。

 so these diodes normally won't turn on。And so， we have a source。The substrate and the drain。

 because these diodes are off。 There is no path between source and drain。

And we say that the transistor is off。When the gate。Is just sitting at 0。On the other hand。

If we apply a positive voltage to the gate。Bdi。That will put some positive charge。

On to the gate terminal。Remember that when you have a conductor and another conductor separated by an insulator。

 that's known as a capacitor。And when you apply a positive voltage to one terminal of the capacitor。

 you get a negative charge on the other terminal。So we attract some electrons into a channel underneath the gate。

Now we have N type silicon in in the source， N type silicon in the drain。

 and we have electrons in this small channel right underneath the gate。

And now there's a path for electrons to flow from the source。To the drain。And current can flow。

 So we say that transistor turns off。So in summary， for this enmoss transistor。第一。When the gate is 0。

The transistor is off， source and drainer disconnected。When the gate is one。

 the transistor turns on and the source and drain become connected。

And we call this N mos because the conduction is through n type3 electrons。

And it's a metal oxide semiconductor transistor。A pimas transistor is just the opposite。

 It's got P type source and drain with an n type substrate。

And the pmas turns on when the gate is at a low voltage。

 and it turns off when the gate is at a high voltage。

So the symbol for the pima is just like the enma。Except it has a bubble on the gate。

 indicating that it turns on when the gate is 0 instead of one。So， in summary。

We can think of a transistor as a three terminal switch。

With a gate that controls whether the switch is on。

And a source in a drain that are either connected or disconnected。For an enmost transistor。

 when the gate is 0， the transistors off， source and drain are disconnected。When the gate is1。

 the transistor turns on， source and drain are connected。For a pimas transistor。

 it's just the opposite when the gate is 0。Sur and drainer connected。 It's on when the gate is one。

 it's off。Another thing that's important to know from some of the underlying physics is that enmoss transistors are good at passing zeroes。

They pull down to a low voltage， well。But they don't pass ones， quite as well。

Pmas transistors are good at passing ones and not so good at passing zeroes。

So if we want to build up a logic gate。Willll have some inputs and an output。

 We'll build a network of inmost transistors between the output and ground。

 So the inmoss will do their good direction， pulling the output down towards ground。

Pulling it towards 0。We build a network of Pmas transistors between the output and power。

And that way， we'll be able to pull the output up too high。Because the Pimat pass one Sw。

And in just a moment， we'll take a look at an example。



![](img/714b69c9f535ff21a2acbe1e4fbfda49_3.png)