# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P40：40_10_02_基础构件.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/3f53c1553d50229b9fdd8795c0ba094a_0.png)

Now we're going to start to talk about circuits in the next two lectures we're going to cover precisely how a computer is built and you'll be surprised at how simple the basic underlying mechanism of our computers is。

We're going to begin by describing some of the basic building blocks。

 just the elements that we need in order to be able to describe the circuits that build our computers。

So first thing today， we're going to talk about combinational circuits。 and specifically。

 this is a digital circuit。 So that's all signals in the circuit are 0，1 with no feedback。

In the early days of computation people considered analog circuits which are quite different and very continuously。

 but nowadays everything's digital and no feedback。

 the alternative to that is circuits with loops and that's what we're going to talk about in the next lecture。

 So for this lecture is no feedback and all signals are 01 and we'll get more specific about this。

So why do we have this kind of circuit Well， the fact is that they're very accurate。

 they're very reliable， we can do a lot with them， their general purpose and they can be fast and they can be cheap and that's held for decades and that's why all our computers are built with this kind of circuit。

The basic abstractions that we use are extremely simple， everything is either on or off。

 and we've talked about that before， that's because it's so easy to map these abstractions on and off to the physical world like a switch is on or off or somes that connected to power or not。

And then we have a thing called a wire that propagates an on or off value。

 so that's definitely a basic abstraction in a circuit is a wire。

And then there's one other thing that we'll talk about at the beginning called a switch that we use to control the propagation of values through wires。

That's it， those are the basic abstractions we work with and we'll talk about them in detail and then use them to build more complicated circuits。

And the fact is that any kind of device that we have nowadays that has any kind of computer inside it is going to be a digital circuit like this。

 including the brakes in your car， but in particular。

 what we want to talk about is the microprocessor or the central processing unit of your computer。

So what about wires， Well， we're just going to use a really simple representation where a wire is either on。

 connected to power or off， not connected to power。

We'll draw a power connection as a black dot anywhere in the circuit that's got a black dot is somehow connected to power。

 And when we want to indicate the value of a wire， we'll make it thick。

 So a thick wire is ones that's connected to a dot， and we interpret that to have the value 1。

 Thin wires are not connected to power。 they're off that we interpret them to have the value 0。

And if we connected any wire to a wire that's on then that one's on too and similarly for off。

 so it's a quite intuitive and natural representation and the power connections are going to be all over the place in our circuit in real circuits。

 you might think of it as a punch through to another layer that's connected to power。

Usually when we draw our circuits we think of the information is flowing from the top and the left to the bottom and the right and we try to adhere to those conventions so that it's easier to figure out what's going on in the circuit of course electrically doesn't matter what direction we draw things but you'll see that that convention helps makes it easier to understand a bit easier to understand what's going on so that's wires now the basic unit that we construct everything from it's called a controlled switch it's a way to control the propagation of information through wires。

The very simplest case involves two connections， so we call one of them the control that's an input at the top and then the other connection is to output and in this diagram。

 the gray thing gray circle in the middle is the switch it's got a control input that's off if the control input is off then the output is on so in this case that output wire is connected to power。

 the switch is off so it has no impact on that connection from power at the left to the output at the right。

But the main thing about a switch is that if you turn the control input on。

 then it has the effect of blocking the connection from power to the output。

That's a controlled switch by turning the control input off or on。

 we can control what happens in the output and we'll talk in a minute about different ways in which that might be realized。

 but that's a basic abstraction that our computing circuits are built on。

AS more general case involves three connections where instead of a connection to power。

 we might have a wire coming through that's maybe the output of another switch。So in that case。

 if we have the control off then the outputs connected to the input。

 the output at the left is connected to the output at the right's connected at the input at the left。

 if it's off as shown at the top， then inputs off outputs off， as shown at the bottom， inputs on。

 outputs on。Data input off， output off， data input on， output on if the controls off。

But if the controls on just as before， then it blocks the connection from the data and the input on the left to the output。

 the output's always zero。 the data inputs off， the output's off if the data inputs on the output is also off。

The controlled switch just cuts across a wire， and if it's got power in it。

 then it blocks the connection。And that's our basic abstraction。

 and it's quite amazing that really everything is built from this。

 and we'll talk more about that in just a minute。So this is an idealized model that actually comes from what's called a pass transistor in real integrated circuits。

 where the wire that goes across is one material and the wire that cuts it is a different material。

 and they have the physical property that if you turn one the control one on。

 it physically stops the connection between the input at the left and the output at the right。

So we're not going to worry about those physical details。

 we're going to use this abstract model because there's actually lots of different ways to build controlled switches like this。

So just as a physical example to give you something grounded in the real world。

 we'll talk about a relay and that actually was one of the earliest controlled switches that was used to build calculating devices。

So what a relay is it's a physical device that controls a switch with a magnet。

 so it's got the three connections input， output and control that we just talked about。

 but it uses electromagnetic force to pull a contact that cuts the electric flow。

 so there's our schematic so from top to bottom we have a wire that indicates our control wire and it stops that's how we know it's a control wire coming across is the wire that might get switched or not。

So if the control is off， then the black square near the top is supposed to indicate a magnet that's off and there's a spring that's holding a contact down to make sure that we've got a connection going across from left to right。

It controls off so that's zero at the top in the schematic and then if the wire is off at the left it's off at the right。

 it's got the same connection if it's on at the left it's on at the right that's shown in the little diagram at right。

But now if controls on， what happens is the magnet pulls up the contact and breaks the connection。

So if that's done， controls on， then the connection at right is zero， no matter what the input is。

 that's the idea of a relay， a physical realization of a controlled switch。

So that's our first level of abstraction again， there's many different ways to implement switches。

 but just thinking about the abstract idea of a switch in a wire。

 that's a model that separates us from the physical world。

 we can start working in the logical world where we assume that these things operate as we just specified。

That's the only assumption that we make that we have these switches in that the wires connect intuitively as we describe。

It doesn't matter how the switch is actually implemented and actually the basic design that we're going to look at was developed many decades ago and has been effective through many。

 many different switch technologies it's a whole purpose of abstraction we have the idea of a controlled switch in a wire。

 we use that to build our computer and all the computers that we've talked about from the PDP8 to the EdVAC and so forth to the microprocessor and computer are all built on the idea of controlled switch Now the physical thing does dictate the performance and that's a topic that we don't cover that's an engineering topic that's certainly important if you get a smaller switch。

 you get a faster switch you get one that draws less power。

 you get a better computer and that's really。The point is that with new technology。

 since we only depend on that one abstraction， we immediately almost immediately get a fast new computer。

 We don't have to change our design because it's all built on that simple abstraction。

 If you have a better switch， you have a better computer。

 And really often when you hear that scientists have developed the technology that means that computers will be faster。

 Really， what it means is that somebody found a better switch。

That's the basis of Moore's law that we've talked about that computers will get bigger and faster on a regular basis。

 is's because switches get smaller and faster and better。

So just to drive home the idea that it doesn't matter what the technology is。

 you can look out on the web and find all kinds of examples where people use switches like there a pneumatic one at the top that depends on air pressure or one depending on water pressure or nowadays you can use a relay and you're not going to build a computer with a billion words with these technologies。

 but they kind of prove the point that the technology doesn't matter you can build people have built whole computers out of these kinds of technologies。

 and actually as I mentioned the relay was a real worldor example that was one of the first computational devices was built with the relays and then vacuum tubes came along which were faster and cheaper and smaller than relays and then the transistor and then eventually the integrated circuits。

We have materials two different materials that cross one another and implement are in controlled switch and nowadays people talk about atom thick transistors and really the concept of a transistor is really the concept of our controlled switch in fact for the last several decades most computers have been built with what's called VLSi or very large scale integration and again as I've been saying that's built by depositing materials of different types on a substrate in this diagram the blue lines are wires are connecting wires and then the red and green ones have to do with switches so certain crossing lines are controlled switches so in the physical world the key challenge is fabricating these circuits that are going to work reliably switch has to work every time wire has to be connected every。

And there might be billions of wires and control， which is this is actually a small one。

 We'll look at a bigger one later on。But we're more interested in the abstract world。

 We're just trying to understand the behavior of circuits that might have billions of wires and controlled switches。

 That's what we're going to be talking about in the next couple of lectures。

But one thing that I want to impress on everyone from the beginning is that really nowadays there's not that much of a distinction between a circuit and a drawing of a circuit。

 actually when people， ever since VLSI came along， building a computer really is specifying a drawing of a circuit that gets taken to a a fabrication facility that takes that drawing and uses it to make these geometric。

Devices with different materials on a substrate， but from a design standpoint。

 what we're interested in in the drawing。And the way that we're going to look at circuits really keeps that in mind we're always thinking about the space that the circuit elements that we look at occupy and how it directly translates from the logic world to the abstract world because the circuit is a drawing。

Now even with these simple abstractions and these are just the few that we've discussed where we've got our dot is connection to power。

 our a line that little tabs that cross a line are controlled switches and wires might cross or they might be connected。

Even with that very simple set of abstractions， the behavior of what goes on can get quite complicated and we give you a drawing built with these abstractions。

 It's not immediate how to figure out exactly which wires become connected in which ones don't and that's why we need to be careful about building our layers of abstraction。

 to really understand circuit behavior。 we're going to start at the beginning and build small devices out of switches and then bigger devices out of those small devices。

 that's going to be a very key part of how we get to a design of a complete computer。



![](img/3f53c1553d50229b9fdd8795c0ba094a_2.png)

![](img/3f53c1553d50229b9fdd8795c0ba094a_3.png)