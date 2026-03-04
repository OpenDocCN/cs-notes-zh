# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p51 14_XR伦理审查机制.zh_en -BV1jM4m1k73q_p51-

![](img/1ee991993eef85cf7487fc005ff827ba_0.png)

![](img/1ee991993eef85cf7487fc005ff827ba_1.png)

So I'm going to walk you through ethical review and I'm going to try to apply that process as far as I understand it to Xr。

 So when you want to do a new user study， you really have to define the purpose the procedure and the duration So that's really key information So what is the purpose of any data that we acquire That's what I would like to ask you here and then also what is the procedure for you to collect that data really you think this through and then also how long do we need to collect that data。

 So is it just one session I it every session and how long do we keep it and do we intend future use。

And do we tell our users and not in the small print of some kind of really long document about the policy and the terms of use and all that。

 No， we probably need to think about better ways of integrating and incorporating those kinds of things in the user interface。

 Well if you're a little bit more advanced as a designer use you know the consequences of each of these things。

 But as a user， you may not。 And so is the user really making an informed decision。 Well。

 all they want is run your app。Both cases。 so but that's not good enough from an ethical perspective。

That's not good enough。 It has to be informedal consent。

The other main goal with an ethical review is to really understand whether there are direct benefits to users and so what you want to do is actually maximize the benefits and limit the tradeoffs So what are the expected benefits to users and are they direct so can they perceive them so what are and I'm going to inject acceptable tradeoffs in realism。

 comfort and safety。And are these reasonable The third aspect of an ethical review is really a demonstrated effort that you're trying to minimize the risks of your participants So what are the contenteduc risks to users and associated with that is the question of how to limit the data and any entities that collect process and manage it and by entities I really mean like the algorithms。

 all the steps in the pipeline all the kinds of different solutions and service providers that are involved in making you track the gestures and understand the speech commands and all of that really want to keep that very。

 very small as a researcher I usually say， okay the only person or people that have access to the research data is me as the investigator and then my research team。

And finally， I think， and this is maybe a little bit unique here or a little bit of a different view on ethical review。

 this idea of agency and autonomy to really empower participants。

 so how do you enable your users to stay in control？Well， as a designer， for example。

 you may really strive for this high level of immersion just because you think virtual reality has to be like really realistic。

 but like imagine ways for users to control the level of detail just like you have in any computer game you can usually control the graphics。

 So now this was my version of an ethical review of Xr。

 And now I want to switch gears and actually talk about this idea of doing a design ethics review and provide a couple of ideas of how to approach it and think about it。

 So the first really big thing to think about and there are four in total in my opinion。

 at least is context and situation。 Where's the X device being used。

 who is around the user The second important thing is the sensory information and the data that we are collecting So what does the X device see what kind of data is acquired。

 So these are really important questions that you should be answering for your design and it may really。

😊，Very depending on context and situations。 So there's an interesting dependency between the first and the second kind of quadrant here。

So then we need to think about the processing pipeline。 And this is something as a designer。

 you may struggle a little bit maybe because you're using all kinds of solutions that are kind of like a black box to you。

 but that's where I would encourage you to really learn more about the technology。

 So what happens on device is a really， really important question to be answered。

 So what kind of data is collected and then processed on device。

 And how is that data processed otherwise， if not on device。 Well。

 it has to be somewhere online in the cloud。 And that means it's going to be transferred to a third party。

 I mean， from the user's perspective， it's a third party because that's maybe something they didn't know that party is involved。

 And and so that's a little bit of a risk， isn't it？

 So what happens in the cloud who manages the cloud。 What kind of。

What kind of protection is provided， What is the service level agreement。

 So these are all kinds of things you need to think about。

 So the fourth big topic of our design ethics review has to be about data ownership and governance。

 So who owns and manages the data and how is the data act and how is the user informed about this。

And is it explicit or implicit or do we never tell them or have you not thought about it so I'll stop teasing you there。

 But really this is something that we should think about and really。

 really important is that this design ethics review happens continuously throughout design。

 not just at the end when all the decisions have been made。

 So this is something this is a mindset that you have to apply as you're making design decisions and forming a rationale about those design decisions。

 my first example is home decoration this is inspired from the IkeA place app And so now we have a family here。

 they're all using their devices and they're deciding together what kind of furniture to get and where to place it and the example here is a living room。

 but there could be all kinds of other rooms。 So let's analyze there's a little bit do a little bit of a design ethics review。

 given what we just learned。😊，So the contacting situation here， Okay。

 I said it's living room in its family。 So let's just say as the family and every member of that family agreed that they will all want to come together and use the devices in this interesting way。

And then the sensory information and data， well user bystanders and these bystanders are family members。

 We do see furniture。 We may be able to infer something from that furniture。

 Is it expensive furniture， how much furniture， how old furniture， so。

That is something that is potentially sensitive information。And then the geometry。 Yes。

 so the app needs to understand the geometry of the environment and then it can do a basic object detection mostly in terms of the furniture that it knows。

 So in this case， probably Ikea furniture that it has like access to as a catalog。

 So but lots of things could go wrong here in terms of like other kinds of objects being introduced and then misclassification。

 etcter。 So then we're looking at the processing pipeline。 So in this example。

 actually the original was marker based。 but now we have mark less implementations。

 So basically the devices do their own scanning of the environment。

 relatively limited at the moment in terms of seen understanding。 finally。

Data ownership and governance。 So here， obviously the data ownership might be with the app developer。

 I don't actually know who developed Ikea place。 Maybe it was Ikea。

 And then when it comes to the question of how is the user informed obviously that is through some kind of language terms of use when you like find that application and downloaded and then a little bit through visualization because for example。

 it'll render a little bit of a pattern across the surfaces that it detects and it gives you a sense of what the device sees。

 but don't be fooled that is just a visualization of the kinds of information that the device is relatively positive about。

 relatively sure that this is a surface。 It still sees many other things that it may not visualize to the user。

So keep that in mind and that's our first this is our first little design ethics review for this scenario so now I'm going to pour us into a different scenario we're still kind of like in the same realm people together in a living room for example。

 and now they are playing a collaborative game so one of the big differences in this scenario is that you're not paying as much attention to what kind of things you are looking at when when you' are designing and decorating your home you're really in control of that device but when you're playing a game and that game makes you like makes like objects appear there and there and even places that maybe you didn't want the camera to see but just to participate in that game you do this and obviously your movement is a lot faster so it makes it a lot harder for devices to sense things and understand it but we are getting there so the other thing I wanted to express in this scenario is now we're actually using very different display technologies you see a OL user here。

On the left， some kind of Holens is actually Hollins one here and we're using some kind of projection and camerabased system so I connect here so this is a prom setup and so that a user even without device can participate and see this kinds of experience and then we see a smartphone user here on the right so all kinds of very different display technologies and each of these have very different tracking technologies involved now that is interesting Now I want to bring in another consideration which is like if these were in different environments and now each user in their own home are participating in this collaborative game。

What does that mean for the data？ And now there is no way to handle it locally。 Well。

 this kind of information gathering and processing and coordination among these devices。

 So to get them into the same coordinate frames and making sure that these devices can collaborate that already requires some kind of serverside infrastructure but that server could still be part of the home network。

Now， in this remote setup， that's different。Now we have to go online and now we have to leak no process。

 and now we have to transfer that data between participants between users。

 and now that introduces interesting new issues。So for this scenario。

 I'm not going to do a design ethics review。 I just wanted to point out a few differences。

 and I'm going to do the same for two more variations of a second scenario。

 So the second scenario imagine a classroom lecture。 So this is now more like a public context。

 So you're like going to a lecture hall， maybe you're a student or you're going to a conference and there's a speaker upfront and so that speaker wants you to participate in this really cool AR experience where you can see the solar system。

And you're using all kinds of devices here， They're different users， and they're kind of engaged。

 So pretty cool。 So public space， all kinds of different devices。

 both handheld and headw could also be kind of Mac based。

 And now a different variation of this scenario。 it's now a team meeting。

 So you're going with team members into a smaller room。

 It could be some office space or some public building or even your' a home。

 So how would that change， how you would use this air application。

 So things to consider here are this could be a more private or still a public environment。

 you may or may not know those users and you don't know what kinds of applications that have installed on these devices。

 And also you need to think about。😊，These different devices coming together here and all that to support a human anatomy application so that we can learn about human anatomy。

So all kinds of interesting things to consider here。



![](img/1ee991993eef85cf7487fc005ff827ba_3.png)

![](img/1ee991993eef85cf7487fc005ff827ba_4.png)