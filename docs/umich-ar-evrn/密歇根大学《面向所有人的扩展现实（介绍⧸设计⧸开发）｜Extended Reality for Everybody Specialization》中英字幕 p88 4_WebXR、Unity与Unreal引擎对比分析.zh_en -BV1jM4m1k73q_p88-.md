# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p88 4_WebXR、Unity与Unreal引擎对比分析.zh_en -BV1jM4m1k73q_p88-

![](img/cfaaaed7ccad6d58791a497f91d42a4e_0.png)

![](img/cfaaaed7ccad6d58791a497f91d42a4e_1.png)

So I've introduced you to WebexR， Unity and Unre， and I've told you more about Web XR。

 and I explained why a frame and how that relates to Web XR and actually 3GS and also HTML CSS and JavaScriptscript。

 so the whole Web layer。And now let's compare unity in aframe。 So unity is actually a game engine。

 but it is also now grown into an Xr development platform。 In fact。

 it's a de facto standard for Xr apps， I would say that many Xr apps So AR and VR apps that you try out were probably done in unity Unity actually has increasingly built in support for XR So the Xr plugin and the XR interaction toolkit as well as AR Foundation all part of unity。

 the whole ecosystem of unity。 So most Xr people will ask you about your unity skills before they consider hiring you nobody at this stage is going to ask you So what's your experience with Web XR people may ask you obviously how do you think about unity in Unreal and what's your experience with both these tools and often it really depends what people are after So for example。

 in my interactions with Disney it became pretty clear that Disney really swears are unreal almost doesn't do anything in unity I mean they have done some things in unity but most of the recent stuff。

Donone in Unre， and that just has to do with the graphics。

 the visual quality in Unreal that is still very， really amazing。But when it comes to XR， yeah。

 maybe we don't actually need that yet， and we can get away with a lot of different techniques and unity is actually really well equipped there。

So it actually supports all kinds of AR， VR devices， every vendor provides a unity SDK。

Aframe is a declarative Web XR framework and actually is more or less in line with the WebXR specifications。

 so I don't say it loosely， so it is webAR and VR it started out as VR only and then it became more and more AR through ARJS which was really a library developed separately but it's kind of really popularized also aframe because that was the most accessible way3 JS is really as I said Aframe sits on top of3JS a lot of my students really。

Like a frame， at least in the beginning。 And then when you create something more complex。

 it becomes a little tedious。 unless you really know your way around in these tools。

 And that's what I'm also gonna talk about。 Finally， in aframe， we have support for most X devices。

 So we have full web X support in Firefox。 So when you see me code in the following lectures。

 and I then just press the Vr button and it goes directly into my Ocus headset， then I use Firefox。

 Chrome not on desktop Chrome on mobile。 So when I show you things on my mobile phone。

 I usually use an AR core capable P phone。 and then I'm running Chrome there， the Chrome web browser。

 at this stage， you really have to pay attention to which browsers you're using on which devices。

 If I'm showing you an example on the Oculus Que， I'm actually using the Oculus browser。

 So for Rift S I'm using Firefox for Oululus quest。

 I'm running actually the Ocus browser inside the Ocus quest。 when I show you later。😊。

Also maybe perhaps some Hollen examples aframe can also be used to actually get content onto the Hollolens at this stage I'm using Edge。

 which is the inbuilt Hollenens browser but since Microsoft kind of like abandoned the whole edge and Internet Explorr thing and is now in the process of moving towards Chroium which is also behind OQuss browser。

 these browsers will all be well unified in some sense and will all provide support and one day I can actually say all X devices So unity versus unrealre that is a tough one it really depends who you are I personally。

 as I said， have more experience with unity but that's just like because at the time when I started Unre wasn't actually that well equipped with Xr things and unity was really like ahead and that's why I have more experience with unity and so I'm going to try to answer this which one is kind of better by asking you。

Kind of four questions and those four questions you should ask yourself So the first question is what level of visuals are you after and if youre after high quality visuals you would probably often just pick unreal Unity won't produce quite the same quality and they are getting better They have this scriptable render pipeline and HDR extensions and all kinds of really interesting things so but at this stage people would still say that unrealal is a high quality visuals。

I would ask you whether you're a developer or a designer， I would say if you're a developer。

 you may prefer unity， it's just something that I have seen with a lot of my students and then if you're a designer I think you might lean towards Unal and that is because at least initially Unreal has a lot more visual scripting facilities they call them blueprints and we will talk about this a little bit。

And while they look more intuitive and accessible initially， they're actually， I don't know。

 from my perspective， because I can program， I guess it's hard for me to say。

 but I actually prefer coding over visual scripting in any case to designers。

 the visual scripting approach might be initially at least more appealing。

 so I would say designers are leaning towards unreal， may not be true for everybody。

What is your development environment is the next question I will ask you in here， I mean。

 based on my experience。 and I actually really have good equipment。

 but unity enables you to create complex projects for even low end devices and on even low end devices。

 So even on your on your MacBook if you have it and which sorry， but in the X space is a low end。😊。

An Unal requires a powerful PC and broad internet setup because you really have to download like everything all the time and you're talking about gigabytes of gigabytes of content。

 it's just crazy and so I would say this is really important like what kind of equipment do you have available for development and then if you're not super well equipped like a studio。

 then Un will be hard。And finally， what device is your project aimed at。

 so what are you targeting and here I would say Unreal supports XR。

 but there is actually quite a bit of overhead， so unrealal is not like this native。

Geared towards X platform， Unal is really like for games and super quality visuals。

 Unity now actually has native X support。 So has really changed quite a bit and evolved over the last few years。

 So let me wrap up this lecture。😊，So this was a first overview I threw out a lot of terms。

 so to be honest for some of these terms like SDK So development kit and I don't always like provide the definitions and this is a course that is geared towards people that are thinking a little bit more technically。

😊，My previous courses， course one and Co two， focused on all the fundamental concepts and then focused on design really allowed us to build some of the terminology in that space and get familiar with that language。

And in this course， I'm just going to you know talk to developers or those who want to aspire to become a developer and it's just like with a different language you don't have to understand every single world word the other person says but you have to find we have to know your ways around and so googling not so difficult So if SDK is something that you don't say or API on a regular basis which is an application programming interface then you can ignore those terms so you can just Google them in your free time。

 they're not that important they're just technical terms I will actually really introduce you to all the important technical terms and we will focus on actually making the jump from 2D to 3 that's like one of our main accomplishments in this module in this first week of this course。

But initially to give you a little bit of a development overview。

 I also like if I if I scared you a little bit， that's fine。 Maybe I wanted to do that。

 but you should really be able to take this course。 So let's keep the following things in mind。

There are many viable paths to being an XR creator I've covered quite a bit in this course。

 however we'll focus on three of them， so we're going to do WebXR。

 Unity and Un and when it comes to WebXR and Aframe I told you that aframe is a declarative Web XR framework so it's actually more and less implementing the upcoming WebXR standard and it's sitting on top of 3JS so that's something to keep in mind。

We will use this actually throughout you will see me use a lot of aframe even just to introduce you to some key concepts。

 it's so easy for me to create these examples in aframe so I've always done it in my classes I have this huge code pen library I mean huge just a little bit of overstatement but I do have lots of examples on code pen out there so check those out and I'll also link them and then you can actually do these things in parallel as you watch me go over some of these concepts as well。

A frame， unity and unreal。 Well， then it's hard， really。

 I would say the learning curve if you will experience depends really on your background。

I actually picked up the tools in this way。 First aframe， then unity and then Un。

 I was working on Web XR projects and unity projects almost at the same time。 So web VR with aframe。

 But I found unity so scary and so overwhelming initially。 And I actually have you know。

 PhD in computer science。 But the world is quite different。

 This is never done a lot of unity stuff before。 and I feel like aframe helped me go into these tools。

 So I strongly believe on that。 And that's why I've chosen these three tools to making this kind of transition from aframe to unity and then maybe from unity to unreal。

Finally， there are many other tools or people may tell you they use very specific Mac based AR libraries or they do anything and everything in kind of like a 360 prototyping tool like tool creator from Google so lots of tools out there。

 but the ones that I've chosen here are actually really the ones that I think have a critical mass and behind them aframe is a little debatable in terms of critical mass。

But I say Web X are okay And so I do think of aframe as a tool to bring you closer to Webex R。

 And one thing that is currently happening as I'm developing this MOoc is react the react framework is actually adding more and more X support。

 and so it's quite competitive to aframe。 and yeah， and3Gs obviously is still around。

 there are also some other alternatives for anyway， there are many other tools out there。

 these are the three that I chose keep in mind that every tool has a threshold。

 So like a barrier to entry and that is often quite high。

 and it also has a seeding like really like that is the upper bounds。

 So what you can actually do with these tools。 and no matter which tool is recommended to you。

 they each have these and they often trade them off for each other So if the seeding is really high。

 that means the threshold is often also very high you won't find a tool where the threshold is。

allow the barrier to entry everybody can use it and you can do everything with it those tools actually don't exist like they would be everybody's dream but they don't exist and that's also something I've talked about in previous courses as well。

😊。

![](img/cfaaaed7ccad6d58791a497f91d42a4e_3.png)

Let's get started。 And the next few lectures， we're going get our hands dirty with Web X R unity and Un。

 and we're going do VR。 and we're going do A R。 and it's going to be a lot of fun promise。



![](img/cfaaaed7ccad6d58791a497f91d42a4e_5.png)