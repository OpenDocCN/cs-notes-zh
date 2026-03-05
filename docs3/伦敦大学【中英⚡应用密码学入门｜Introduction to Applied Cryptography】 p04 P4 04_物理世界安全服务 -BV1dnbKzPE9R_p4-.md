# 伦敦大学【中英⚡应用密码学入门｜Introduction to Applied Cryptography】 p04 P4 04_物理世界安全服务 -BV1dnbKzPE9R_p4-

![](img/0d393fe9587adcd6ab7714116760a561_0.png)

So in lesson one， we're going to consider why we need cryptography in the first place。

And the best way of doing this is to actually look at the physical world。

 the world with no computers， no email， no iPads， and imagine how information exists in that world and what security of that information is so at the end of this lesson you should be able to identify a range of security mechanisms used in the physical world。

And appreciate why we need cryptographic security mechanisms in the digital world。

So let's start by thinking about the way information is represented in this physical world of no computers。

 iPads， etc。What does information look like and in what forms does it take？

And two of the most obvious ones are the spoken word。

And information written down or represented physically in terms of objects。

So what does security mean for that information？And perhaps the first thing that springs to mind is secrecy。

The need to restrict who can access a particular type of information。

We think about this for the spoken word in the spoken word we can achieve secrecy by whispering。

 and we use the physical proximity of two people to restrict a conversation amongst only them。

Similarly， if we have a meeting in a physical room， we shut the door。

 All those present in that room can hear the conversations that take place。

 People outside the room cannot。 So we use physical presence often to guide secrecy。

 If information is written down， we have a range of techniques we use。We put letters and envelopes。

 we might put pieces of paper in a filing cabinet， and we might even lock that cabinet。

And once again， we're using the physical mechanisms of the physical world to protect information that's written down。

Okay another security mechanism we want in the physical world is to make sure that information has not changed in any way。

 either deliberate or accidentally since the time it was first created。

And we have a raft of different techniques we use in the physical world to do this。

 Perhaps one of the most obvious ones is we stick a letter in an envelope and we seal that。 Now。

 placing the letter in the envelope is obviously for secrecy reasons。But if you think about it。

The actual seal on the envelope is basically a property which allows us to detect if someone has opened that and perhaps changed the contents。

In olden times， they also used wax seals for a similar reason。

There are all sorts of other mechanisms we use in the physical world。Take， for example。

 a 200 euro note。This is information written down in a physical object。

 and it's covered with protection mechanisms， physical protection mechanisms so that it cannot be forged and cannot be altered；

 it features watermarks， it features holograms。If you look carefully。

 there's a dark stripe down the central area of this note and that itself is a physical security mechanism。

 and even the way the note feels is designed to detect changes and to detect forgery。

Another physical security mechanism we use is the handwritten signature。

We place our signature and documents in all sorts of situations。Interestingly。

 this means lots of different security properties， but one thing we often take it to mean is that the person who signed this document attests that the information in that document is correct and has not changed。

Now that may not be the case， but we use signatures in that context a lot。

And there are other security mechanisms。Think again about the need to identify somebody。

We might identify somebody by their face visually， we identify people by the sound of their voice。

 but there are many times we need to identify somebody that we don't know， so take， for example。

 the reception desk in an office or hotel，Somebody presents himself， you need to take a decision。

 do you admit this person or do you not？And we use all sorts of proxies to decide whether this is an appropriate pass or not。

 we ask people to present a passport。A driving license， maybe even a letter of welcome。

So we use all these different security mechanisms in the physical world to make information safe。

 So we've given a few examples of isolated mechanisms we use for securing physical information。

But we also rely a lot on context。So imagine this scenario you're invited to attend a presentation in a room。

From somebody you don't know， you turn up at the expected time。

 somebody you don't know takes to the stage and starts talking。

How do you know this is the right person， how do you know the information you're getting is correct？

Well， the short answer is， you don't， of course。 But we're relying on a lot of context。

 The speaker turned up at the right time， somehow got into the building， somehow got on the stage。

 somehowhow sounds like they're making sense。 Everybody else seems to be accepting that this is normal and that this is valid。

 We can all imagine disaster scenarios where the real speaker was kidnapped on the way to the room。

 This is rather unlikely。 We relying on the the difficulty in the physical world of somebody actually turning up and appearing to do the right thing at the right place at the right time。

We're relying on the physical context to make security decisions。

 Now let's map the digital world and reflect on all these things we've just talked about。

 and that physical context is completely gone。Most importantly。

 information can reach anyone any place any time in the digital world。

 we have no way of recognizingogni faces and sounds。

 we have no ways of physically locking information away。It's very easy to modify digital documents。

 it's very easy to copy digital documents without anyone realizing even that's been done。

And it's very easy to make contact across the internet， across the world。

 without people having any real idea who's trying to make contact。

 So it's this absence of all these physical security controls in the digital world which is needing replaced。

 and that's precisely what cryptography is going to be doing。So in summary。

No physical security mechanisms and physical context is what delivers security in the physical world。

😊，That's what we're going to have to replace in the digital world with cryptography。



![](img/0d393fe9587adcd6ab7714116760a561_2.png)