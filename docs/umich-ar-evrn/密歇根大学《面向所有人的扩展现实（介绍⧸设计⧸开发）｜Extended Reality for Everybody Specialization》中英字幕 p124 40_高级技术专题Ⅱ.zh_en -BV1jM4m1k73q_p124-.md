# 密歇根大学《面向所有人的扩展现实（介绍⧸设计⧸开发）｜Extended Reality for Everybody Specialization》中英字幕 p124 40_高级技术专题Ⅱ.zh_en -BV1jM4m1k73q_p124-

![](img/9838773593a7682eeb76a33db52d66ee_0.png)

![](img/9838773593a7682eeb76a33db52d66ee_1.png)

We want to talk about， the advanced topic of accessibility。 Unfortunately， it's here。

 So let me just say accessibility shouldn't be listed here。

 It shouldn't be in the advanced topics lecture。 Unfortunately it is because it does require advanced techniques。

 It doesn't require actually seen understanding。 So the system really needs to perceive the world around the user It needs to understand it like a human。

 So it needs to know that well， this behind me is a wall。 So don't run into it。 There's a shelf。

 There are actually different objects in there。 maybe you placed it there。 and I hope you find it。

 And I mean， it's not like we don't we probably don't need that kind of support because that's the problem with accessibility。

 A lot of us researchers always think we have to help the blind people and they don't know how to navigate the world。

 very well how to navigate in the world。 It's just for environments that actually haven't seen before。

 That's when it's tricky。 and so seen understanding。😊，actually help， right。

 So you have a holo on your head and that display now and that device now looks looks into the world for you and actually reads it。

 It may actually read it out to you。😊，And so it's really hard to get this right。

 both on the tracking and understanding and sense making kind of parts。

 so the semantic perception part， as well as the user experience。

 so the system now actually needs to describe the world to the user。😊。

I think that would be really cool， we have some research proposals in the making and currently being reviewed。

 it would be really cool if I could get to work on this an AR screen reader that would be really awesome I'm not going to talk about it in my X research lecture but I think it would be a really cool research project。

😊，And would require some advanced techniques definitely text input， okay？

So most of the time we have a virtual keyboard， it's usually not very efficient and effective and neither in VR nor AR。

 okay。What is actually still the best way is to just use the physical keyboard。

 But these are not really well integrated into current experiences。 So that's the problem。

 Physical keys are usually not part of the AR VR setup。

 There's actually no way to really most VR interfaces。 If you type into your keyboard。

 even though you run it from your computer， like with aft rift S or a quest Fiulus link。Nope。

 not going to work unless you're in some kind of mode， which is pretty sad。

Sppeeech command Yeah okay you're saying okay， you can use voice or speech recognition fine and cool The problem with those is that as a user usually don't know what kinds of commands are available on the Hol lens for example。

 there is a difference between a dictation mode which is kind of like a lookup against a dictionary speech recognition mode and all voice recognition let's say。

😊，Well， actually， is speech recognition and not voice。 voice would be identity。

And multimodel input would be the combination of these。

 So these are some of the advanced topics that I think we have to work on in the future。

 Vulcher keywords。 I have seen many different designs and layouts。

 The one on the Hollens with the midair tapping。 I out I kind of find an like interesting。

 I still don't feel it's much better than Hollens one so don't get me wrong。

 but I still don't feel very efficient typeraser is a game that I play sometimes and because I'm actually really good on the physical keyboard I usually well not usually but I do play it on the tablet sometimes to make it fair to my students and I should do it on HolLs。

 I'm sure I'll be the slowest like snail in the typeraer game anyway。

 so we haven't really figured out text input。😊，Now， I want to talk about collaboration。

 Collaboration is something we are figuring out when you're getting better。 Most AR experiences。

 at least and also VR experiences as a single user。

 just like you your poor little person in your environment wherever you're trying it out。

 And you could do it co locatedated。 So if you have a friend with you in there。

 It's really hard to just like share an AR of VR experience。

 even though we have all the technologies most， as I said， are still designed for single user。

 So first step would be to support colocated VR and AR。

 but it's also very interesting is do kind of like a remote setup。

 So now we are spliting up these people here on the right， we have a remote setup。

 And so now we're gonna to do collaboration between the two。 obviously， this is remote。

 So you need to think more about networking and different quality they don't share the same physical layout。

 I mean， to be honest。 I drew it exactly。 but it's unusual that we have exact copies of the physical world。

 actually， that's something we are working on right now。😊。

How do we actually address these differences between different physical worlds and then have a seamless remote collaboration I find it very interesting So on the conceptual level this would be a shared session and this would require some kind of cloud anchors and some kind of like where you actually in each of these you would obviously define some kind of shared origin between the coordinate systems。

😊，And then exchange that information。 and cloud Anchs is one way to do it。

 at least on the A core platform。So I also wanted to talk about adaptive layout and customization。

 so as you know， most AI experiences can be classified into a tabletop room or world scale。

 So how does it work for adaptive layout。 So in this case。

 you would have just like the cube could appear here right So if you have that experience and let's say we design this experience where you can move cubes around。

 I don't know kind of like in minecraft in this case。

 we adapting the content to really fit under the tabletop。 Now if you're doing room scale， well。

 we can make the content larger。 Okay and we can use more of the space here。 we can also treat this。

 let's say if this is your starting scene， we're taking this scene and we're scaling it up to fit the room。

 This sounds trivial。 And this actually relatively easy to do。

 but most experiences don't even do that。 most AI experiences are designed for one of these do not allow you to to move between these they don't。

😊，Are you going to do room scale or are you going to do tabletop No。

 the designer or the system developer decides for you and as a user and that's not great。😊。

If you wanted to do a world experience， a world scale experience。

 it actually becomes more tricky because you then need kind of like some of the collaboration platform from before because nobody has a whole read on the environment unless we share that data。

 the AR cloud aka dangerous， but we'll get there and and then it could be interesting in this case。

 you're entering maybe a multiuser collaborative environment and I wanted to really just focus on layout。

 if you see what we just did， we scaled up the scene。

 we adapt it to different room sizes and we can do this more or less automatically because like here we know that's the shape that we can register that the user wants to interact with on our room scale so we can scan the room can build the spatial mesh and then adapt the content accordingly and then it could also be interesting as you go between different rooms。

 How would the content。 How would the interface then change and adapt and you could do this actually user driven So customization that's how would draw the line So this is this idea of grace for degradation。

😊，So really making it a minimum kind of experience for small， maybe you don't have all the content。

 or you scale everything down。 and a progressive enhancement one is like。

 oh now we're actually really scaling up the content and we are adding layers of functionality because we probably use a more powerful device as well。

 and we actually blow up in some sense， the functionality and making use of this environment。

 So I'm thinking in terms of these two concepts because this is concepts that I'm familiar with when it comes to progressive web and responsive web design。

 So we're gonna look at progressive Xr。 Here's the case study that friends and colleagues at Mozilla did Charlotte to Bla Mccintyya。

 really cool person。 and they were actually going through a number of displays here and just thinking it through like how would we actually adapt an existing interface。

 let's say we are doing this kind of like Xr store and example of。😊。

You can go shopping and buy virtual objects and preview them in your space。

At least in one of the modes， you can preview them in your space in AR and in another mode。

 you can actually do something more in VR。 So they really thought through what's the whole design space of displays that we have。

 And then how do the not only the not only the the layout and all these kinds of things adapt。

 but also obviously the interaction because on one device， you touch like a smartphone。

But then if you're moving to a Holloens in AR using primary hand interactions and then if you're doing VR version。

 you probably use either a lot of controllers or you have access to hand tracking or eye tracking and then actually work with those kinds of inputs so it's really interesting thing to think about how do we design interfaces that adapt to all these kinds of interaction modalities I would say pretty advanced techniques at this stage。

 maybe in a few years down the road we just have a few kind of different templates or aiming for some cascadic style sheets。

Approach applied here could be very interesting。 The W3 C Web XR specification is also going to be built out more and more to enable this in the future。

 and this will be very interesting for us to look at。



![](img/9838773593a7682eeb76a33db52d66ee_3.png)

Finally， I wanted to really talk about mixed reality capture。

 Maybe you have seen me throughout the second course in this X MOO this doing this 3D sketch。

So in this is a mixed reality capture。 Okay， we're using some kind of virtual production here。

 if you will。 I'm actually in front of a green screen。 I'm gonna show you that in a second。

 And I'm sketching out actually what I'm doing in this example。 I'm sketching out the world。

 the room in which I am。 Okay， so that's me。 I'm the yellow guy in there。😊。

And that's where I'm roughly in the world waving at you and。

I'm going to probably sketch where the camera is， so for virtual production or mixed realityD capture。

 we actually have to tell the camera that is capturing us where it is in the 3D world okay so usually have some kind of calibration and there was an actually extensive calibration procedure in this mixed realityLD live capture tool that we had here。

And then once you tell the camera where it is， it can actually sync with the virtual world。

 and then if you have a green screen， that's the easiest way to do it。

 we can extract the background and fill it in with the virtual world as we do here。

And so I'm actually in tiltbrush， which is an immersive authoring tool we are using in the second course as well。

 if you buy it， it's not for free。And there are alternatives to it， like Google Blocks。

 we could have captured that way as well。 Mi reality capture is still a bit experimental if you play around with tools like live。

In my research， I'm actually aiming to build something that would allow an instructor to go into the room like I'm doing it here。

 sketch out my content or whatever， I'm bringing any kind of virtual content into the world and allowing my students without a headset to actually observe or with a headset。

 I mean if they want to we also are working on modes to actually join the 3D scene with a headset or with a phone。

 but let's say even without a headset right， that would be cool because let's face it。



![](img/9838773593a7682eeb76a33db52d66ee_5.png)

If you are giving a lot of demos， like I was giving so many demos in the X MO and I work with mother cameras。

 I'm also going to do a little bit of a making of later。😊，It's hard。

 How do you communicate that virtual reality experience to users。 Now。

 the whole point of virtual production and filmmaking is to just like make people believe that wow。

 they were in Mandalorian， and they were actually there。 And actually， the actors were。

 they felt like they were there because there was a volume capture。 They had actually LED balls。

 So really big displays behind， not green screen， but really big displays。 And in in real time。

 they rendered the virtual world in there。 And that's also pretty cool。

 This whole field of virtual production mixed reality capture， I find very exciting。

 So if you could remove the background， please。 And bring in some really cool virtual content behind me。

 then you would get a sense of what this looks like。 And yeah。

 so these were all the concepts that I wanted to capture mixed reality capture。

 all the concepts that I wanted to cover advanced techniques。😊，There's so much more to learn。 And。

 well， in a few years from now， hopefully， this is like， let's do a basics。

 rather than advanced techniques， especially accessibility。

 I we don't wantna have to say accessibility requires advanced techniques。

 So let's all work together。 to actually make it easier for developers and designers。

 but also for users。 Okay， so。😊，I hope somebody hears this and is interested in working on this together with me and with the community。



![](img/9838773593a7682eeb76a33db52d66ee_7.png)