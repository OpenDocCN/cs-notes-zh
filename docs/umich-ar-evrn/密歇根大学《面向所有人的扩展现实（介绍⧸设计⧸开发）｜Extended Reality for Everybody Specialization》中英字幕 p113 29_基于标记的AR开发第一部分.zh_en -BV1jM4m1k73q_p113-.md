# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p113 29_基于标记的AR开发第一部分.zh_en -BV1jM4m1k73q_p113-

![](img/5e7b14dbb06ada3a4e508a52b1b6d446_0.png)

![](img/5e7b14dbb06ada3a4e508a52b1b6d446_1.png)

In this lecture， we're going to talk about Mac based augmented reality。

 So now we're going to really focus on markers， Macb design， What are the interactions。

 What does this mean for the content， And we're going do this again based on our case study。

 you know， Kplla law of planetary motion。 So while we actually designed the Macer less version first。

 you know， as I was discussing thistra， we explained why we wanted to do that first。

 we then in the last part of that independent study。

 actually then implemented the Mac based AR version。

And we realized how cool it is really designing around paper。

 doing these Mac based augmentations around paper。 And actually。

 it is a current theme in our latest research。 One of Srita's first projects is part of a PhD thesis。

 so it's gonna to be exciting。😊，I'm gonna show you what we have created at the time。

It is the Mac based A version。 It's a longer video of what you've seen before。

So I'm gonna zoom in a little bit。 First law， you can really go in there。 You can lean in。

And there you see it。It's pretty cool。And you can see how the values are actually projected on paper and also how some of the values change as I started interacting。

With these flags， they determine the orbit。And that changes the values for the law。

 And so that's pretty cool。You can see how I'm touching。 I'm Z， I'm switching between what you。

 what I see directly through the camera。And then you sometimes see a little bit more in context as I'm wearing the GoPro to show you this stuff。

So the second law， did， Did you notice how to switch between the laws。

 I was just bringing a different sheet of paper。And so that means we can actually use to we can deploy an application like this and actually make it very easy for。

 for， for example， students to operate it。Because like we don't actually have to learn too much about the interface。

 okay， maybe that you can click this to stop wasn't exactly clear。

 but that's something I could show as an instructor as well as I'm guiding my students through this。



![](img/5e7b14dbb06ada3a4e508a52b1b6d446_3.png)

And here is the， here's a lot of stuff going on。 We have a couple of the law of harmonies always sounds funny when I say。

 But anyway， that's just me。 It's pretty cool。 so these actually then。😊，The， the way they rotate。

 the way they orbit around the sun。嗯。Is constant。 I didn't actually say this right。

 but this law is just fascinating to me， so。It's， it's cool。 and it's actually cool。

 when you drag this out really out of paper。 Let's focus on the interactions more than me trying to explain what's really going on。

 That's not as important。😊，But here I'm showing like how we can transition between these。

We could probably also implement a version where we can show all three laws next to each other。

 doing multi market tracking。But this works as well， right， as we switch the focus。 actually。

 keep in mind， these actually are relatively complex simulations that trade implemented in unity。

 So there's actually some math and computation involved。

 I remember her complaining a little bit about this in our independent study。

 but she did a really good job。 And I think it's cool。 Like， it looks really nice。

 that transition is very smooth。😊，It does remember state so。



![](img/5e7b14dbb06ada3a4e508a52b1b6d446_5.png)

There's a lot of stuff going on there that we need to learn about。 and so let's just do that。

Mka based A。 So we're gonna talk about Mac based tracking。

 is really clearly the enabling part of of this， enabling technology。

 We're going talk a little bit about Mac design。 And I think in this case study。

 we can learn quite a bit because of the way were making use of paper and how we are printing information on paper。

 I mean， sorry， yes， we are printing information on paper， but we are also projecting using A。

 So we're visualizing things on paper。 And that's what I'm particularly excited about。

 And we're gonna also learn about a few Mac based applications。

 This is the part where then release a little bit from that case study and look at other examples as well。

 So let's start with Mac based tracking。😊。

![](img/5e7b14dbb06ada3a4e508a52b1b6d446_7.png)

So Mac Bay is tracking here as an example with ARGS。

What I'm showing here is place the marker on this surface。

And I'm showing a virtual copy of that marker。 That virtual copy disappears as I o the paper。

 The tracking then stops working。 So no extended tracking。But that's just how it is。 In this case。

 we， when the marker is lost， we hide it。When the marker is found， we show it。

 and then we constantly track it and adapt the scale and the size。 Sorry。

 the scale and size is the same。 But the pose。 So the orientation and the rotation。

 Thats also the same。 What am I doing， So the position， the orientation and the scale。

 That's the transformation matrix。 Okay， you see it better in this example。

 so we're gonna we're gonna show this virtual cube here that is supposed to fit perfectly onto that marker。

 the red cube sticking out。😊，And I'm showing both。The marker， how it's tracked。

 So a virtual copy of the marker， then the actual virtual object， which is not too interesting。

Since in this example， it's just designed to show you how tracking works。 When I pick it up。

 it's also interesting。You can actually move a marker， especially a marker this size。

 If it's smaller， it's harder to track， so。But you can move it。 and it actually works。

 It's very robust， to be honest， even though this is a technology from 1999 AR Tookit。

 That's what it's based on。Cool work from University of Washington。



![](img/5e7b14dbb06ada3a4e508a52b1b6d446_9.png)

And。It actually did enable quite a bit。 So we're gonna learn about A Tookit。

 A lot of people probably now just go ahead and use Bforia and Bforia and unity because it has nice nice ne of unity。

 But AR J S is based on J S Air toolkit and JS A toolki。 It's actually Javascript port of A toolkit。

 So it makes sense to learn a little bit about this。 So how does it actually work。

 So I'm gonna walk you through the steps。😊，So here we see one of the frames from the video just before when I bring the marker into view and I already show the virtual object。

 So we are expectinging the original image。And then we are building some kind of， well not we。

 But A Tookit is building a threshold image。 So it's actually， I'm approximating this year。

 This is not exactly how this looks to the algorithm。 but basically。

 you're doing a a threshold image。Then you're looking for the connected components。 In this case。

 the label inside there is actually significant。 You building contours。 So get a rough shape。

 I illustrated this year using my amazing paint dotnet skills， not even Photoshop。😊。

This is roughly what it looks to the system。 So just getting the contour， the shape。

 actually the outline， Think of getting the outline of the marker。 So getting the rough shape。

 and then detecting the marker edges。 So we have both the connected components。

 So the hero in there and the edges And so then we can extract the marker。

 and then we can fit the square on it。 So it's a fitted square。 so this one is the bottom plane。

 Okay， if you were like I had an optical illusion for one second， as I was looking at the screen。

 But so this is the bottom plane。 and this is the top plane。 Okay， so it's really sticking on top。

 And then when I put all the pieces of the algorithm together， this is the result of it。😊。

And that was a quick rundown of the algorithm。 So here we have the marker that we just saw before。

 It's called the hero pattern。 It is one that is a default pattern。As part of A Tookit。

 And so let's talk a little about macrob design。 So this one is really significant。

 The continuous black borders around it are important。 They are key。 Okay。

 so don't includecclude them。So don't hold it like this or cut things away。 Okay。

 so I've actually built a little latch here at the back so I can just hold it。

 And so that's how I'm doing it。 And I'm gonna use that later。 have something funny prepared for you。

 I mean， funny， relatively funny。 The experience I really wanted to show。

 which is Disney's toy story and couldn't do it。 But I'm gonna show you something else instead。

 anyway， So marker based tracking。 So back to back to the the rules here。

 So you should design these markers And when you print them out， they should be bigger。

 the smaller they are， the harder they are to detect。 Dete is one thing。

 but tracking is really hard even And the size of the marker really determines the object scale。

 That's something when it comes to implementation。😊，So one unit is actually， this is one。

This is one unit。 So a， a， if you put a box on it of scale 1， it actually fits nicely onto that box。

Okay， so I'm trying to do this in a way so it make sense for you。 So I have my marker here。 Okay。

 and I was talking about scale。 So if I actually bring in a different size marker。

 it'll be smaller scale。 Okay， so I now happen to have a different marker here。

1 did I always carry with me my favorite marker。😊，You see the difference， harder to track。

 smaller in scale。I， I didn't change the code。 It's still a 1，0，1，0，1，0 scale， but。You get it。

Let's go back andm glad I was able to show you this。😊，So I'm gonna now go back to my slides here。

 So that I was just illustrating how the size of the market determines the object scale。

 So pay attention to that。And the content inside the marker can be customized。

 That's really important。 So inside the marker， right， it says hero here。

 but it could say something else in there。 I don't mean the virtual content that you place on the marker。

 That's obviously completely cost customizable。 But I'm talking about the marker design。

So we can also do custom markers so there is a number of patterns。 ARJS， for example。

 has a pattern generator tool and bforia be used to generate markers actually here。

 well we generated this part of the marker and we built identity in this marker and then we printed that marker on the sheet of paper and then we are aligning some of the augmentations relative to that marker so that it appears on the paper including filling in some of the formulas here and some of the values down here。

 doesn't always work perfectly， but I thought it was a really cool idea。And then here。

 what we're doing is we have the explanation here and we're running the simulation up there。

 What we could also have done is actually not occlude this marker， occe this content。

 Use this marker for tracking and actually show the content here。 But we wanted to be。

Consistent as we were always running the simulation up there。

 but we could have done more to this lower part of the marker。

 and that's something that Raydon and I had discussed。

 but we were just running out of time at the end of the independent study。

And it is not necessary because the project is cool enough anyway。😊。

So and then we had Kepller's third law。 There was a lot of stuff going on here。

 He had multiple things you could manipulate the law of harmonies。 I'm going to say it again。

 And then we felt in the values down here。 again， using that marker to track in that marker。

 you can see how they look different。 I mean， maybe maybe you cannot see。 But the marker engine。

 the tracking engine can see these are different patterns。

 And you can see it if you focus on specific aspects of these patterns。

 Then you can see like a focus on this area then it looks different here and looks different here。

 Do you know this kind of games。 we have to look like compare two pictures and find all the differences and then highlight them。

 These detective image games。 I don't know。 Anyway， So that's what we just did here for a second。😊。

And then we are running I'm showing here。 I'm showing you a little bit me going towards these markers。

 Nothing is happening here。 I'm just showing you actually the paper that we used with a little GoPro here。

 And this is how it appears to the student。 Let's say I distribute the sheets of paper to the students。

 This is what it would look like。😊，And you can see the marker pattern printed up there and then think of that whole paper as the marker。

 not just the pattern up there， because we're designing the content relative to that paper。

 So the whole paper functions as a marker， But we identify it based on that pattern up there that's printed up there。

So the sheet of paper is the marker， if you will。 So basically， any object can be a marker。 Okay。

 if you're using the right frameworks and tools， you can do all of this。

 You can use Qura codes and barcode scanners So they can also encode a URL。

 So you can use it both for tracking。 but also for redirecting people to a specific website。

 Fs can work as markers。 imagess and photos。 you can train existing tools like before you， on images。

 photos and even more。 And there is actually facebased marker tracking。 So snapnapchas， then studio。

 It does that significantly air kit and air core have support now for face tracking and so you can do all that。

😊，You can have 3D models function as markers。So it could be any 3D object， but it could also just be。

 So maybe you saw this guy from time to time。 Thiss actually a present from my mom when I graduated with a PhD。

 and I still have it。 And so this owl was supposed to be visible from time to time。's。

 it's quite cute。 And we could use this as a marker。 Yeah， we could train。

 some software on an object like this。 And it's not straightforward。 because this is a stuff toy。

 but it would work。 And beforeia， for example， has some basic support for that。😊。

You could use indoor locations。 So using environmental recognition in then pre scan these areas。

 So it could be based on photos， but you need a series of photos needs to build really 3D geometry。

 So photogrammetry would be used to really understand and detect these areas from different angles。

And then buildings like usually like a facade， like like the front of the building。

 the principal front could be detected。 And there's really。

 that's really cool stuff you can do with that。 especially when you combine it with projection based they are。

 So you could actually project and augment against that building。 That's really cool stuff out there。

 Disney is a master of this。 And so that's that's how this stuff works， okay。😊。



![](img/5e7b14dbb06ada3a4e508a52b1b6d446_11.png)

![](img/5e7b14dbb06ada3a4e508a52b1b6d446_12.png)

![](img/5e7b14dbb06ada3a4e508a52b1b6d446_13.png)