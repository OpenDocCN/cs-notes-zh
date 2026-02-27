# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p13 2024-10-07 - CIS 5650 GPU Programming Fall 2024 Guest Lecture 3.zh_en -BV1sRtresE67_p13-

An official representative of Google。

![](img/27abea06e675c0ec2dc4e187af5c1777_1.png)

These slides were not written by me mostly， they were written by Michael worker Brandrennon Jones who gave this lecture for the past two years。

But they're really good slides， so I just took them。I I'm Kay， I use heham。

 they them pronounce I am a softwareft engineering at Google since 2016 on the Chrome GPPU team working on Web GPU for most of that time。

I am also a Panduama I was in computer science in 2015 and master's of Comp science in 2016。

so as Raza said， this is our team's 11th years this is 10 years since the first time that I was presented in this course and I was in that first course I was there the first time that my team presented incidentally and we are all the way down there now there are three penallum represented on this list。

We one of them left recently， but we currently had two people on the team from Penn。诶。

Me and trackre and Austin A here left recently， but yeah。

 are we have always been really excited to support this course， obviously。

I've been on both sides of it， so it is。you know， an interesting interesting experience to like give back in this way。

 but I just wanted to celebrate that and for fun I pulled together all the links for all the slides。

 all the past videos that exist some there's some really good stuff in there and I'll mention some of that later。

啊。So I'll be talking about generally like why we developed Web GPU and then the important stuff like core Web GPU concepts。

 some like examples and demos and like obviously pretty demos are great。

And the stuff that Branan had had in these slides was feature aid and debugging and best practices I kept both of those because they are both really useful things there's a lot of stuff that we have from past we have so much material from past lectures so there's a lot of stuff in past lectures。

That is like here's some conceptual stuff about like how these how this style of API works and all this stuff I'm not covering a ton of that。

 I do have some bonus slides at the end which I'm pretty sure I will not cover because I'm pretty sure this lecture is long enough as it is。

 but there will be links to a lot of useful resources so this will not be the only info that you get about WebG。

First， let's talk about WebGL。嗯。We GL is。The sort of。Thing that that WebGU is the successor to。

 right， Like WebgL' has been around forever at this point， it's very ubiquitous ubiquitous。

 It's been on。Every major browser on every major platform for a good long while now。

 and that has allowed。A lot of customers at WebG to do a lot with it。嗯。

It is used on products that are like used by millions of people I guess probably like billion of people I don't know what the numbers are like Google Maps for example it's been using this for a long time for the like various rendering of course I'm sure you're familiar with Cium and like Google Earth and all these other things that also use WebGL there's tons of sites out there I literally it was just like I want to add an example of like how influential WebGL is a stuck Google Maps there so I did this half an hour ago but there's so much stuff out there it's a standard it's an open standard at the Chronos group kindos group is is the organization did openGL and OpengelS and Vulcan and openCL and a tons of other things GL stuff that you're probably familiar with the timeline here at WebGL2 so when I started at my job I was actually working on WebGL2 it was far along in the process but we were trying to get。

Out the door on Android fully conformant passing like passing all the tests， all that stuff。

 so that was what I initially worked on at Google。嗯。But as you can tell。

 these some of these numbers are， some of these years are a pretty long time ago， right。

 So WebGil1 was based on OpenGil E。In 2007。嗯。That was， in turn， based on。

Open GL from which originally came out in 1992。 So' we're like going really， we're digging really。

 really deep into like the history of this API and there's been breaking。

 there's multiple breaking changes represented there。

 So it's not like we it's not like we grew a thing starting in 1992。

 but it is still like there's still a lot of concepts in there。

 there really baked into the way that a graphics accel is worked in the 90s。 and that is。

Not or like maybe the 200s。 And that is not very。That's not a very good way to program a GPU these days。

嗯。And just for fun， I will note that openG is based to some degree on unclear。

 I don't know exactly on Silicon Graphs I G， which came about in 1983。

 so digging really far back there。Real time graphics have obviously evolved a laws since then。

 this is just from 1993 to 2002。So not even representing that whole range。

And that's Hizon forbidden West， PlayStation 5。 So like。For a bit of context， right。

 like this thing on the left。Was。Could be rendered on a $250，000 workstation in 1993。

And obviously the thing on the right on a brand new console in 2022 was on a $500 piece of hardware。

So there have been a lot of advances and of course there have been huge architectural changes。

 many huge architectural changes over that time。So around 2014 to 2016。

 everybody agreed that it was time to change things。嗯。

So I will go upwards since that's chronological in 2014 metal was released by Apple。

 it is only for Apple devices， they built it as a successor to open GL。

For a lot of reasons and of course， we soon found out that they wanted to build something that would work better with Apple Sil。

 which had not yet been released at that time。USimilarly， Microsoft created D312。

 released that in 2015， that's of course only for Windows and Xbox。

That was a successor at D3D11 Director3 had evolved more along with the time than OpenGle had。

 so it was not quite as much of a departure but it did change quite a lot and then Vulcan was a huge departure from OpenG this took con us a good number of years to produce but it has cross platform across every architecture except for apples because Apple doesn't implement it。

诶。And it is a successor just something that was fundamentally built in 1992。So。他。

The patterns of the a it was agreed by everybody in the industry that the patterns。

That were used to designing these APIs needed to change， even in the case of like D3011。

 which wasn't too far too far too long in the tooth yet， yeah。Yeah， it works。

Im wondering like how for a that look of that， he said it was in appears to。

How does that even work when the industry changes so quickly？That's a really good question。

The things that needed to be represented in these APIs like the fundamental architecture changes。

Have been around for a good while at this point， I would say most of them。Let's see。

 what did I say about Open jail？Like by the time of OpenGES 2。0 in 2007。That's。

 that was the hardware people were making。 So people were making hardware that was like。

Fundamentally。Getting there in 2007。And。Vulcan targets open generallyus 3。1， which is 20。

4ish or something for mobile， but desktop was way ahead of that so there was there was like。

Probably a decade or close to a decade of of like。The modern graphics hardware design before we got to the point where we were redesigning the software to match it。

So。Things don't haven't didn't actually move that fast basically is what I'm saying I don't know that much about the history of this。

 I'm not super familiar with it， but I do know that like。For example， if we look at。

At like a desktop GPU。They were evolving their architecture continuously for decades。

 they were making their software work with that and they were making it fast and they were doing a lot of work to take the old software and run it fast on the new stuff。

So they were able to push the hardware forward incrementally as they went。But the fundamental change。

Were things like creating more power efficient architectures on mobile。

 which I don't have any slides about， but there are past lectures that talk more about this。啊明。

That really like the concepts became ubiquitous across multiple vendors， across multiple companies。

 a good while before we actually push those out into into standards。

I hope that answers your question a little rambly， but I think in the case of something like。Welcome。

 that was also the contribution that A& D made was the predecesor to。That's right yes。

 so MD had internally developed a thing called Mantle。

 which was a an API that was designed to match their hardware。Every。Well most of the of the。

Most of the graphics vendors， the GP of vendors do。

Have their own like vendor specific APIs this is what you will find on console these not publicly available。

 but if you sign an NA with like Sony or whatever， then you will get the architecture specific API for PlayStation5 or whatever。

And so those those evolved with every console like every console was not worrying at all about compatibility because the console generation is quite long so they could build one thing everybody could build the game against that until the next console generation so in console things were also evolving in a very different way than than on desktop。

嗯。And so they had been already continuously working on this API design stuff for a long time。

AMD designed a thing that was。that they owned rather than Sony owning or something and they released that like they gave that to the Kronos group and said here all the IP in here。

 you can use this design an API and they worked together with the other vendors to add all the things that were necessary to like generalize it across different vendors。

There's a lot of history there and I wasn't there for any of it。

 so I only know of it like secondhand， but it was quite a long process。嗯。So yeah。

 I think I basically said all of this stuff， but important part here。

 opengel and Open GS more or less aren't girls receiving major new features at this point。It。

Also didn't fit super well onto the web it worked actually surprisingly well。

 it turns out that this sort of 1992 model that was baked into the very foundation of GL。

 which is we're going to send commands， you're going to buy this code processor that this graphics and you're going to send your commands to that and it's going to produce an image like you had your workstation that didn't have graphics。

Text terminal。 and it would send commands to some other machine that was sitting here and it had the。

 the nice display attached to it。Turns out that works really well with the modern browser model that came about with Chrome in like 2008 or so。

We need to put these in separate processes so we actually need to send commands to another process。

 turns out that work pretty well but it's still like there's still problems like well like we often call it an impedance mismatch。

 like you've got two different things you need to somehow get from one to the other。

 make that design work。嗯。That's also all that said， open jail and webG are everywhere。

 like if you want to build something that is everywhere right now。

WebG and open gel are although apples continually。Potentially threatening to remove open shell they deprecated it a couple of years ago and have been totally radio asylum to whether they're actually going to remove it。

 but they might do that。So。You I think you all probably have learned up in jail with Adam and that is not a bad thing like there are really good reasons to learn up in jail。

 although if you think it should change， you can bother Adam about it and you can tell them to take it up with me。

Because I would think it would be really cool to move off up in jail。

 but there are really good reasons to learn up in jail。嗯。In any case。

 we the web needed to move along with the industry， and thus we have Web GPPU， a project。

 which one we first。Started presenting it we thought would take us two years and it took us six and a half years I think so we were like。

 oh yeah we're going to get this thing out the door no time it'll be great。

 we'll be way ahead of where we were we're not going to be four years behind native anymore it didn' not work that way but we have it now and it took a lot of design work。

It is fundamentally an abstraction over metalal Direct 312 and Vulcan， it's a web native API。

 it fits into the web platform and fits into JavaScript much better。

 fits well into languages other than JavaScript， and it has all the modern features that were necessary in the modern API design。

And of course， it was built with an extenibility in mind because this is the platform we intend to continue building on for at least a decade。

 like this is where all of the new features as they come through native and as they percolate and as they become available on enough devices that we're going to need to expose to the web。

These are so new， important web GPU features relative to WebGil2。Include many things。

 compute shaders， indirect drawing render bundles， as well as some things that are not fundamental to WebGPU but which we kind of figured out how to put in their external textures so that you can like have a video playing and then accessed directly from a WebG application it has more flexible canvas integration so it no longer has like a one to one canvas to context relationship like webGL。

 we worked a lot on since we're building something from the ground up we did a lot of work on debugging features and that kind of thing it's not great but we have good errors and that kind of thing。

And the most important thing about Web GPpU handle all these other B APIpis。

It's the the hidden global like internal state of open shell not there anymore。

 the like the nightmare that made open shell so difficult to learn like you could pick it up and you could do some stuff and then when you want and then every time you tried to change something like some horrible disaster would happen。

Was due to this like very complex internal state machine of open gel。No more of that。

 so that's great， far more usable as well in addition to having all of these great other other great things。

I feel like this slide should be retitled， but the standard has support the standard process has support from all major browser vendors。

 so we have shipped in Chrome on Mac Windows and Android sorry our Linux users。I used to be one。

 I still sort of am， you will get it untruly。You might be able to use it on Linux if you need to。

 let us know。But yes， Missilla and Apple are actively working on the air implementations。

And they're working pretty well Apple's implementation is working quite well Missilla is good。

 but a little bit behind on some syntax changes to the shading language and so a lot of demos don't work on it。

 but otherwise is' in quite good shape， so we are expecting pretty。

we're expecting wide support pretty soon， like we don't know when Apple never announces when they're going to release anything and Firefox doesn't know yet。

 but like pretty soon。You can test it in all the browsers so you can download the technology preview of Safari on Mac and iOS and enable Web GPPU。

 you can download Firefox nightly and I think it's on by default in Firefox nightly so you can try those but ours has been shipped for a while。

 so it's like pretty stable。嗯。So it's probably the one that you will be developing against。

 but I do encourage you to try your stuff against other browsers because if you can make it work on Safari。

 that's great because your stuff will work on an iPhone， which is really nice once they ship it。Sen。

There are a bunch of important early adopters。 I put this slide together to get today。

 so I don't know if it's a very complete list， but。Babylon JS， 3JS， Unity， Play Canvas， Autodesk。

 and Chrome itself are using Web GPU。There's tons of others， but these are some very notable ones。

 TensorFlow JS， which is the like web version of TensorFlow。

 which can take like a TensorFlow model and run in on formerly on WebGL now also on WebGPU that was contributed by the Intel open source Center who we work closely with they're like kind of the other half of our team。

In Shanghai。So we've been working with them for a long time on that as well。

 so some some really good stuff and there's also support there's been some work in like Apache TVM and a couple other machine learning frameworks。

 so there's a lot of good work going on out there。I will also mention like so far I'll talk a little about the webinnot because Web is not fundamentally a web API。

It is in browsers as a JavaScript API， and like you can use it from JavaScript or Typescript。

 you can use it from Webassembly as well。You can use it in node， so again， from JavaScript。

 but you can also use from other languages。Our implementation is written in C++ it has a C++ and a CApi the the implementation that Missula uses is called WGPU it's written in rust and it has a rust and a CApiI these are not quite we're not quite there on having them be interoperable yet but that's the thing I'm working on right now so we are。

Going to have two implementations of this sea header。I don't know why I have speaker notes on。

 I'm not reading them。

![](img/27abea06e675c0ec2dc4e187af5c1777_3.png)

Let's share some demo of us。

![](img/27abea06e675c0ec2dc4e187af5c1777_5.png)

Do I have this， yes， so this is one that Brennan who presented this course last year wrote。

 this is using compute to produce a mesh some from like a particle system essentially a small particle system。

Using a technique called metas， this is。There's various techniques that you can play with to experiment how this work with the performance。

But this's a nice demo it's doing it's got some nice， you know。

 some nice lighting and all that going on， so it's integrating compute and rendering。嗯。This one。

 oh yeah， sorry， go ahead。

![](img/27abea06e675c0ec2dc4e187af5c1777_7.png)

I think so， but I don't remember like I don't metaballs is a specific technique。

 you should look up how it works， I do not know how the meshification step of metaballs works。

 I think it ising marching cubes because I remember Brandon talking about marching cubes for some demo as probably this one but feel free to look it up it's easy to look up。

Thank。还搜索。Yes。This is just the webpage version of if it's on Github。

o and there should be a link to the source on the slide by the way I completely forgot to mention there is a link up there you probably saw the slides are there theyre also on the website already I think so if you want to open these slides there's a ton of links in here that you're probably going to want to click later so so you'll have them on the course site。



![](img/27abea06e675c0ec2dc4e187af5c1777_9.png)

嗯。Yeah， so this next one is unities demo。

![](img/27abea06e675c0ec2dc4e187af5c1777_11.png)

friends。Last year， I think was one year ago。This was they like easier of like。We're gonna。

This's audio， you know。Yeah。Ohello。This is still using extra I don't know anything about but you probably some of you might be familiar with they're doing a particle system obviously here to put together this scene and like 3D text and stuff so this is a nice demo this takes a little longer to load because it's unity。



![](img/27abea06e675c0ec2dc4e187af5c1777_13.png)

Not it's not that long it's not that long because it's a small demo but it is， you know。

 of course you get you the engine you have a lot of power。

 you have a lot of there's a lot of stuff there to build with so that is。

A really important partnership for us。Another one Babylon Js， so this is a。Demo。

 this is one of their very， very nice graphics demos that they。

That was part of Babylon JS and they wanted to， if I remember。

 correctly optimize this wave simulation thing。With compute。And various web GPU features。

 there's a ton of parameters to the simulation。But it produces a very nice image and if I remember correctly。

 they were able to do it reasonably like pretty more efficiently than WebGL。

 but I don't have the numbers unfortunately。嗯。Okay， so。Big question， like， why did you do that， Like。

 okay， so I haven't I haven't mentioned this。 I havent I haven't explained this explicitly yet。

 the Webjuki is not the same as any of the other APIs。

Like so WebGL was fundamentally extremely similar to OpenGL had small differences。

 it was a JavaScript API， whatever。But why did we build？

A whole new API which took us six and a half years。



![](img/27abea06e675c0ec2dc4e187af5c1777_15.png)

Um， why didn't we just make what Vulcanum so Vulcan is you may be a little familiar with it。

 it's a bit much。

![](img/27abea06e675c0ec2dc4e187af5c1777_17.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_18.png)

It is very powerful and there are good reasons for it to exist。



![](img/27abea06e675c0ec2dc4e187af5c1777_20.png)

But。It's the kind of thing that you fundamentally want to use an engine that supports Folcon rather than actually use most of the time。



![](img/27abea06e675c0ec2dc4e187af5c1777_22.png)

嗯。

![](img/27abea06e675c0ec2dc4e187af5c1777_24.png)

This slide。Is some。It was posted on Twitter by a some graphics person there's a link in the notes actually the broken link I was gonna update anyway I'll fix that link later yeah so like opengel1 you would just like start your start your start your triangle and you go point point end your triangle and it would show up on the screen OpenG3 had to set of your shaders and there was put stuff in buffers and all this stuff was a little bit more complicated DX9 had like I don't know what Dx9 was like exactly but Dx9 has like to the X11 was sort of similar。

Progression。But you can see DX 12， like they're making you do a lot of stuff more like there's a lot of stuff happening inside Z driver。

 though they're not making you handle yourself。And Vulcan takes that。A little bit farther。嗯。

And that is， the minimal amount that you needed to do roughly the same thing。



![](img/27abea06e675c0ec2dc4e187af5c1777_26.png)

嗯。But that's not the only reason we fundamentally like having a complex API on the web is not impossible。

But there are a bunch of reasons relating to the complexity of Vulcan。So on the web。

Cody right on one device should have some reasonable expectation of running in every device。

There's lots of cases where this isn't true it's like you know screen sizes， performance， et ceter。

 it's definitely not true in webGL because like it's in WebGL you can use the maximum capabilities of the device and then it won't work on your phone you need to dial down the sizes of some things or whatever。

But with WebGQ， since we were designing it from scratch as a Web API， we said， okay。

 incompatibility should be opt in。嗯。So。We you change things a little bit so you write WebG application。

 hopefully。There are some behavior differences， but hopefully it will just run it in device， right。

 you develop it on your laptop。You develop it on your powerful machine， powerful desktop。

 it will also be on your phone。 It might be really slow but。It will something will show up。

And it will work， then you can go ahead and optimize it for mobile， however you need to do。

And not the other。Really big thing。嗯。Is that Web APIs need to be safe， right。

 you're opening websites。Totally not trusted like the model of browsing the web now is that you do not have to trust the website in order to visit it it will not be able to infect your computer just by going to it that's different from how things were in the past that's how it is and that's how it should be so of course webGPU needs to be safe so no one defined behavior no ways to access data owned by other sites so no like you know。

Creating a resource without initializing and then reading the values out of it。And， you know。

 of course， we want to make sure that you don't get data owned by other sites。

 You don't want to want to get sensitive data and all that stuff can come in through undefined behavior and undefined contents and things like that。

Native APIs are very different than what they're trying to achieve， right？

Different devices have different APIs， right we've got metal and we've got D3D that are platform specific。

嗯。And they also want to expose like platform differences in order to so that like engines and games can get deep performance。

And they don't really care about data races and undefined behavior and all this stuff because they they'll give you debugging tools to find that stuff so you don't have undefined behavior in your application。

 but then you ship your game without any of that。Because you don't want that overhead。

 we cannot do that on the web。 We have to keep that in there。

 and so our validation has to be fast because it needs to be on all the time。嗯。

Web GPP also takes advantage of the web platform so we're taking advantage of the fact that the web has image decoding。

 video decoding， Can， HTML， all this stuff， and also an asynchronous execution model。

 which I won't talk too much about， but it does。But it is used in WebPVi in some very key ways。



![](img/27abea06e675c0ec2dc4e187af5c1777_28.png)

The complexity of Web GPPU is not too bad。There's a little bit more boiltlatelate than webGL just to get something on the screen however。

As complexity increases， you are dealing with a lot less of the internal complexity of open jail。

 so it's a little bit of it trade off， but it's definitely nicer。嗯。

These again are good for your own one triangle。

![](img/27abea06e675c0ec2dc4e187af5c1777_30.png)

So。Wb GPP needs to be simpler for a bunch of reasons than the native APIs。That are summarized here。

 that one additional point here is the philosophy of the web。

 which is that like you should be able to view source on a web page。And sort of see what it's doing。

 Obviously， this is not true on every web page because there's a lot of stuff that's obfuscated。But。

The style of the web of building something on the web is that you write your app。

You can debug it as it is。And then you can minify it if you want to。And that。

Is a philosophy that was pushed by some members and not other members of the community group early on。

 but we came up with something that was in the end very nice。So yes。

 it's a little bit more complex than webGL， yet in my opinion， it's a lot less complex to use。

And another important point here is that WebGPU is teaching you core concepts that apply to other APIs。

Don't worry about the fact that you're not learning Ban。

Because you will be learning the same concepts， the concepts are common across E3 12 and middle and bulklkan。

And the concepts are what matters。In Vulcan the API gets in the way of using the concept。

 so when you are learning them， it is。It can be quite a challenge because you're like banging your head against this。

This like up to C API， you don't want to be dealing with C at all， much less， you know， all of the。

Cash management and all this stuff that Vulcan makes you do I used to have a slide in a past presentation。

Of a screenshot of the Vulcan inspect that says。Basically in order to use Vulcan。

 you should be intimately familiar with this entire chapter the chapter is like 60 pages long so we don't want that either so yeah Vulcan。

It will get you a long way toward learning Vulcan then of course when you pick up Vulcan。

There's going to be a lot more to deal with。But。嗯。It's， it's。Fundamentally。

And like an easier way of learning these concepts and not everything is there because we're limited by what's available on all the platforms。

But。But the core concepts are there。And these are still key concepts if you don't end up on the Vulcan side or like if you don't end up using Vulcan or D3D or metal or console API or any of these things。

 a lot of these concepts are still very core because they show up at higher levels of game engines。

 so if you work on a game engine or even if you work on a game using a big game engine。

 a lot of these concepts will be key to getting performance out of the engine。

So a lot of these are very useful and I think that they're at an appropriate level。

 like a very good level in Web GPU to pick them up and learn them。



![](img/27abea06e675c0ec2dc4e187af5c1777_32.png)

So let's go through a。A hello triangle。This is like a code walkthrough it'll be a little bit boring but but we'll have a bunch of the core web GPU concepts in here so very useful stuff obviously you'll have these slides as a reference。



![](img/27abea06e675c0ec2dc4e187af5c1777_34.png)

So first things initialization rather than so in WebGL you would just create a canvas and then a get a context from it and then now you're just render to the screen immediately here we create something called first create something called an adapter。

This represents some GPU or adapter on the system。That provides an implementation of Web GPPU。

It could be a software implementation， it could be an integrated GPU， it could be a discrete GPU。

 and you can get some basic intoto about it。And then once you have that。

 you're going to create a device， device is the primary interface for the API。

 this is what creates all the resources， it gives you the cue to submit commands to and all that。

In between here， we have what I mentioned earlier the features and limits。

 so by default you will get the base features and limits so that your code will run everywhere you have the opportunity to enable things at this step so that you know if you want to use texture compression。

 which is like BC texture compression which is desktop only。

 you can turn it on here and on mobile device device creation or the adapter want to have it and so you'll hit this fallback path and you'll have to have some way to handle that。

嗯。Similarly limits， like we've got a bunch of limits in the API textures mentioned the numbers of things you combined。

 number of vertex buffers you combined all this stuff。

 everything has a default baseline that that you get by default and you're guaranteed to have on every system the adapter tells you what the maximum available is and you can upgrade to that if you need to do but generally we encourage people to not do that so their stuff will run everywhere。

Now in order to actually put something on the screen。

 because we did not start with a canvas what we do in WebGL。You。

createate this you create a GPU canvas context and you attach it to the device。

 so now that device is able to get a texture from that canvas， write things into that texture。

 and then it will show up on the screen。And you can do a bunch of these。

 you can have like as many canvas as you want， you can have zero canvases。

 very popular course for ML and all that kind of thing。

And you can reconfigure them as your need of like no。

 none of the you probably haven't dealt with this， but in web gel there's a lot of like， oh。

 we need to replace the context on the canvas， so I guess we have to take the canvas out and put a new canvas in its place when we have to make sure that layout of the screen doesn't get screwed up while you're doing that so it's a little bit simpler。

Yeah， yes， no， no worries。点路。嗯。Can you share why adapter and device are different。Yeah。

 essentially the same hardware， yeah， so the adapter is is just there to tell you what the hardware is like it's it's it's just a thing that contains like。

You know， then some information about the name of the thing。

 the limits the the features of the of the thing so that you can then go on and create your context like create your device。

 which has。A set of features and limits baked into it that your application will run against。

So it's really just it's just an arbitrary name for an object that you need during initialization。

The other question I had was。Being able to。嗯。Switch your default device I didn' I couldn't figure out if there's a way。

 and maybe I didn't look long enough。Like the power preference thing。Okay。

I don't know if it was Power patterns because I was running on my laptop I was running the browser and it would default to Intel and I went in on Windows and changed the graphic settings then it uses Nvidia。

I think that should be a version device Yeah so there is a way to choose between low power and high performance。

I didn't cover this very much because unfortunately we don't implement it on Windows。

 it is implemented on Mac。But that is not relevant on any Mac newer than like 2018 or 2019 or whatever right so unfortunately we don't implement enough and like you can't I believe right now you can't get at the discrete GPU if Chrome is running on the integrated GPU on Windows and this is just due to a bunch of complicated interruptopers that we have to like deal with yes that is correct and in the current implementation there is also no way to like enumerate the adapters right so if you had to unid adapters you're not going be able to pick both of that unfortunately but the reasons for that are basically like we don't want to give that much information to the page because this。

Fundamentally everybody is like this part of the API。

 the main purpose of this is going to be for people lifting yourprint your device。

 which is something we don't want anybody to do actually they will do it nonetheless and we will you know track the amount that people are doing this。

 but it isn't something that we。You know， we want to avoid we don't want to make it easy for people to do that。

m so so yeah that's why it's a little bit limited， there's very few devices out there that have two GPs if you did have one you'd be like basically uniquely identified immediately。

 although you know， if you go to the like various websites out there that show like heres your finger。

 here's your browser fingerprint， you know， they'll be able to uniquely identify you anyway but。

We're trying to fix that probably it's a very difficult problem。

 including the one where your IP address， well not here。

 but your IP address is pretty unique in most situations。嗯。Anyway， that's it。

Totally unrelated side topic。Finished that okay canvas context gives you a texture to render into okay vertext buffers we're going to create some data the standard javascript way of creating a packed array of binary data and now we create a buffer that's a web GPU buffer creates that on the GPU and you specify the size and you can't you can never change the size you specify the usage you can't change that So everything about the everything about a resources is fixed after fixed that creation time except for the actual contents so here you get an empty buffer it's full of zeros。

And then you write your data into it。嗯。And similar things for other types of resource initialization。

嗯。We also of course need shaders， so Wigel WgSL is the web GPU shading language。

 it is a new shading language designed for web GPpU has a sort of rust like syntax。

It allows you to have multiple entry points in a single module so here we have a vertexent fragmentment shader in the same module that can share code。

 it's useful for a bunch of reasons they can share binding points kind handy。

 you can also put like multiple vertex entry points or multiple fragment entry points or compute entry points in a single file and so you can share a bunch of stuff that way。

It's a it's a new language， you have to use it unfortunately like for better or worse right there's good there's good reasons that we ended up ended up where we did with a new language。

 it's not too hard to use look at examples。You'll be able to figure it out。So。Yeah， yeah。

 it's not too hard to pick up。does this mean that you want to create something。你解的。Yeah。

 if your data is a variable in the size， you either need it to be large enough to hold all of the like different sizes of data so you can allocate it too big and use only part of it。

Um， or you can read it allocateator allocation is not too expensive generally。

 like it's something you want don't want to be doing a lot。But if like you load in a new model。

Like you have a model viewer and you put it in and drop in a new model totally fine that you're recreating a bunch of buffers。

But you will have to and it's a little bit more complicated that you have to red it and all that stuff。

 but it also simplifies a lot of the like state tracking right we don't have you can't resize it so you't so we don't have to propagate a resize through the entire API。

So it's simpler for us and faster at the detriment of the like。

You're going to allocate some things sometimes ahead。

Oh yes that means copy destination I I should have mentioned that yes so there's a bunch of vertex buffer sorry a bunch of buffer usages and texture usage for various things。

These influence things like what actual section of memory or which physical memory chip the thing gets allocated on。

It affects the cache like cache behavior and that kind of thing for textures。

 it affects the pixel layout or like the available set of pixel layouts。

 this is all happening internally， but we need to know this stuff ahead of time because for example。

 if you need to use a texture from a shader，You'll want it to be in a format where。

Where text where texts pixels are not too far away from each other。

 so they use like a funny sizzling layout to make it so that things are cache local。

 whereas if you're copying from a buffer into a texture。

 you might want it to be linear or whatever is various reasons for this and it's different on every piece of hardware so we just have this high level description of like what you're going to use it for。

嗯。And you just， if you don't have it， you get an error message and it tells you what to add so。嗯。

Yeah， so。I cover this more on Wednesday when I talk about the Qa developers in web GPPU， but in Qa。

 we can say this buffer response and this buffer， you know kuda and copy device or host device and stuff like that。

We can do that for traders， this is how you do it by setting these flags。

 so we'll cover more of that on about how these things matter。I realized accidentally skipped it。

The section， the Q is the thing， sorry， was there。The queue is the thing where you actually submit data for or submit commands。

 submit work for the GPU to execute here we are telling it to write some data it's taking some data from the CPU。

Putting into the queue to write into the buffer on the GPU。嗯。



![](img/27abea06e675c0ec2dc4e187af5c1777_36.png)

Right this is Slaimmus list beyond to talk about the neoshading language but but yes it is there was a lot of criticism there were a lot of fights on the internet about about the neo shaing language thing it was a little stressful。

 a lot stressful so it could took us several years to get this all worked out but。Fundamentally。

 we had JLSL and HLSL， which were existing shedding languages we use JLSL for WebGL of course HLSL is from Direct3D。

 it's the most popular like most engines use that as they're like authoring little format and then compile down to whatever they need。

嗯。And then there were binary formats like SpearV， which is an intermediate format that Vulcan uses。

 so Vulcan rather than taking a text format expects you to compile to a binary format first and then pass that to Vulcan。

嗯。There。This was a really long， really long debate to determine how we should do the sharing language。

Like there was a lot of like political and like IP concerns and like all this stuff that nobody wants to think about。

But。At the same time， none of the existing languages really worked very well for us。

 and I know that's kind of like non inventedvent here syndrome。

But you know on top of all of the other constraints and all the other philosophies and opinions。嗯。

This is what worked well， so metal uses C++ as a shittdding language that wouldn't have worked for a number of reasons。

嗯。It's like it's an unsafe language。GLS and HLSO would have been safe， but we needed to sort of。

What we would have had to do is design a language that looks exactly like HLL or GLSL。

And have that be the language because we needed to fully specify it， We needed to have。

Like not have certain features， we needed its binding model to match with our API， all this stuff。

So it would have you wouldn't have in practice been able to just drop a shader in because things would have been actually a little bit different。

 you wouldn't be able to take like a shader from your HLS like Unity Shar or whatever and drop it in。

嗯。It would be nice if you were able to do that it would be nice if our tax was the same。

 I think but there are good reasons for designing this the way we did we wanted to design something that was simple to parse because one of the biggest problems with。

GLSL in our experience。Has been that。None of the drivers get it right。

They're all wrong in some way okay they're mostly right these days。

 but seven years ago they were all wrong they're still all wrong but it's hard to find the bugs。

 but they were like there were there were all sorts of problems like youd give it astruct and it had to lay out thestruct and it would just have bugs in weird situations。

There would be like weird issues with like reordering。

In instructions and the language and that kind of thing。 and we just didn't want to deal with that。

 so we wanted to a syntax was relatively simple and that would go down to representation where we were able to。

Masage things that we could avoid those bugs。This is what we ended up with。It is。Our own language。

 so it evolves along with WebGPU， it does what we need。Um。

 we are able to design everything into it that matches along with API name is match and that kind of thing。

 so that's also nice。So。It sounds like that's a great question right I should mention that so of course we have to transple this on the implementation side into what the native APIs accept。

Because we're an abstraction layer。 So， so our implementation and missile implementation both have their own shadedr compilers。

That take and Apple's implementation that take Wigel and convert it into the into another language。

 We also have both like both nozs and our projects also have。

The ability to take other languages as front ends so we can take Spearv。

 which is that binary format that Vcan uses。And ingest that and convert it into our internal implementation for Wigel。

Our internal representation for Wigel。And then spit it out as wigel again。

 like not everything is quite the same so there's weird little things that you have to deal with。

 but yes， you can take other shaders and convert them。嗯。

Smaller applications can't take the cost of putting that compiler in the web page because it's like binary size。

Larger applications like I'm pretty sure that unity I'm pretty certain that unity is compiling is like transpiing shaders at one time right so like Unity has a bunch of shaders in HLSL and they have this complicated layering like series of layers of like seven different representations to get down to openGL or metal or whatever they need and of course they had to add a new a new backend for for Wigel。

And so somewhere in in the many stages of translation is like our compiler， which takes there。Searv。

 I think， and converts it into Wigel so they can run in the browser and that makes the that makes the page a little bit more heavy weight because it taking that compiler along with it。

 it can also in principle be done offline， but most engines are。

From most instance can be difficult because a fund compilation typically means。

That you generate thousands of different versions or tens of thousands of different versions of the shader。

 and then compile all of them。Which can be like gigabytes in size， which is worse than a compiler。Um。

 like it's very common to see with like PC gamesum， or even like even comfortable games。

A stage of initial launch which is we're compiling all the shaders we have like 10。

000 different versions we're going to generate all of them we're going compile all of them and it's going to take a take up a couple gigabytes on your disk like so that's not something that works super well。

On the web， but you know people usually transpile this stuff at runtime and they just， you know。

 you don't want to load communiators， you don't want to be loading shadeators constantly runtime anyway because it's expensive not just on that side。

 but also inside the browser and inside the driver。So。So it's a bit of a heavyweight process。

 but generally it works pretty well for the way that people use the API。跟。

And what do you think about。Vixel's capability for， I may be using the wrong print of programmer。

Or more dynamic shaded generation。不累。Things you'll figure out that wrong time and you'll p negotiate shade from that yeah。

So that's a good question GLSL has a preprocessor， which is commonly used for this purpose。

Wakeel does not have a preprocessor， we decided that was complexity what you wanted to push out of the language for the same reason that we made a lot of other decisions about Wigel。

But JavaScript hasn't built in like simple templating like like template strengths where you can paste in values。

 so if you need the bacon of value into the shader。

 we need to pick between the two different code paths。Statically， you can do that。

 but we also have some like more modern static。Type things in the language where you can say like。

 here's a constant that I can define later。And here's an if block like an if else that depends on the constant and we'll pick like during compilation we'll pick one of those two and it'll be optimized when it gets compiled so there's some features like thats not it's not the story is not really strong right now often people are compiling shade is like more often than is ideal。

but that is also extremely common with other with like engines and shaders on other API so it's not unique。

 it is more of a an unsolved industry like research problem than it is a web GPU problem， but yes。

 we have some features。And JavaScript has some features to deal with some of that dynamic shader generation。

I will mention that it does help a lot that you can have multiple entry points in a shader because you can share code rather than having to be like。

 oh I need my implementation of that helper function， I'm going to paste it in here into the string。

 I'm going to build up the library of stuff I need to be in the shader。

 paste it all at the top have the shader at the bottom。

 so a lot of the stuff that you typically need to do with dynamic shader generation is not necessary but a lot of it of course is。



![](img/27abea06e675c0ec2dc4e187af5c1777_38.png)

嗯。I mentioned that you could change some things later。

 so you compile your shader and then later you're creating the render pipeline。

 the render pipeline takes your shader stager， you know your vertex shader， your fragment shader。

 and it takes a whole bunch of other information So in WebGL all of this stuff would have been like dynamic state like you set some state here and there and then when you do your draw call。

 the driver would look at the current state and say okay。

 I need to compile a pipeline that does what you asked。

Here you have to put it all up like you have to declare it all upfront。So， the。

Ring render pipeline configuration can get pretty big，s a there's a lot of things in there。

 this is just like this is smallish because we're using a lot of defaults。There's a lot of options。

 there's a lot you know the ability to find a lot of different buffers。

 a lot of different attributes and a lot and that kind of thing。

But it has but all the state is in one place or most of the state is in one place you've got all these things like primitive topology。

 you know triangles lines， your all of your blending state is in there all of your multi samplingling state all of your depthtencil state and a bunch of other stuff is in there this is。

How most of them， the sort of explicit graphics APIs the nativeative APIs work。

Um although there are it's it matches better with some hardware than with others。

 so there is some like it's it's evolving still within the native space as well。

But in what would you view because we have to be on top of everything？

We have to take the most limiting version， so we take as much state ahead of time as we need for all of the APIs。

 for all hardware。And so it ends up being a pretty large amount of stuff。Command encoder。

 so this is the other this is the sort of。One of the other key features is that rather than just doing a draw call and it having to like assemble all of the state。

We're creating a command buffer， a command buffer is a thing that contains a bunch of commands that get encoded into a nice format that the GPU can understand。

 so like the driver will encode it into a nice format and then send it to the GPU and the GPU will interpret the format。

So this is the thing that you put all your actual like drawing commands and that kind of thing on so who we have a command encoder。

The top level thing can do copies and it can start passes， so as render passes。

 a render pass is another one of these things which we have bundled a bunch of state up into a single thing。

This is a section of a command buffer， which does rendering commands。

Here we are setting up all of the attachment state at the beginning。

And this has to match with the pipeline that you created。

So you get to take a texture like from the canvas。And say， okay。

 I'm going to this pass is going to render into here。At the beginning of the pass。

 we're going to clear it。And then we're going to like clear it to this value。

 and the end of the pass， we're going to store it into the texture so that we can put it on the screen。

And the reasons for that have to do with mobile architectures， which benefit from。

So mobile architectures， there， like I said， there are slides， other slides about this。

 I don't have them here， but mobile architectures are what's called tile based。

So the rendering will happen inside of a small tile will be like 16 by 16 tiles or something like that。

And so if you had to load all of the data， you have a cleared texture。

And you're going to load that onto the tile， which is just like far away from the memory about your memory that contains the whole texture。

 you're going to load that into into the little tile through your window。

And you're going to write over all of it so you don't actually want to do that so here this is a key feature of render passes that lets you avoid that that like memory moving that memory the tile just clears it and then when it's done it can write it back it doesn't have to it can avoid one of those transfers。

So we take the current canvas texture。Put that in the vendor pass。

And then we start doing some things on the past， we set up state。

 so there is a little bit of state here， but it's not complex like an open jail。You set the pipeline。

 you set your vertex buffer like so zero is the vertex buffer slot。

 you can also set things like the index buffer， bind groups， view of port rectangle。

 like various state， it's all local to the render pass。

And so it all gets reset next time you're in a past， so you know， like once you end the past。

 you don't have to worry about it anymore。And then you can do your draw call that takes those couple of pieces of state that we just set and actually applies them。

 does the draw call you know takes the data from the vertex buffer executes the pipeline。

 executes the vertex buffer or the vertator， you know goes through all the raurization and all that stuff。

 does all those steps。At that point， in the command buffer。

And this is a simple example that just draws three vertices。

There's also a bunch of other types of draw commands， there's like you can use index index buffers。

 you can use an indirect buffer where the arguments， the draw call are in a buffer on the GPU。

We're also working on multid indirect and multi dry index indirect。Prototype。

 which is something that might be very interesting for， for， for projects to like。

Do performance analysis on how much faster can you make it if we have a。

If we have we're able to generate all of our rendering commands on the GPU。

A variableable amount of them and issue them with very little CPU overhead。So those are interesting。

 essentially。And then we're done with the rendernderpas encoder， we end that。

 we're done with the command encoders we finished that nothing has been sent to this GP use like I mentioned this is just serializing some data。

It's just creating a list of stuff for the GPU to do。That the GPU itself can understand。

Then you can submit， you can make as many of these as you want， you can do them。

 you know in native APIs， you can do these on multiple threads。

 this is a key thing about this pattern is that you can create you can do your command buffers across multiple threads and then you can go and submit all of them we do not have multithreading yet。

In web GPU， but it is something it is a very important。

Part of the design of web GPU that things are compatible with multi threading。

 but as you may know multi threading on the web is very complicated， so it is not in there yet。

 but and in a case submit you submit that and。嗯。

![](img/27abea06e675c0ec2dc4e187af5c1777_40.png)

You。Go and run your app and you see this。

![](img/27abea06e675c0ec2dc4e187af5c1777_42.png)

Because。You always get a black screen on the first try。

But if you actually took that code from the actual slides， it would work。

 you would get a red triangle。So after you fix whatever silly typepo was in there。

 which inevitably there will be hopefully you got an error for that because errors error messages are very helpful。

 you fix it， you get a triangle so great not too much code just set up a triangle。



![](img/27abea06e675c0ec2dc4e187af5c1777_44.png)

嗯。Let's we'll talk about some more webC concepts next so are there any questions I know I said it was going boring and I spent like half an hour on it because there was a lot but。

It's very core stuff。So thinking back to this slide about like how line？like lines。

 bulk and first triangle is sort like all the others。As like。

Are there waiting which whether the P is submitted？I mean， obviously it's。But like。Yeah so。

Some of the things that Vulcan， for example， lets you do that we just don't have are things like。

Configuring your。Pipline cache。So that you can have a。An object that has like some shared state。

 so when you can pile similar pipelines， it can reuse some of that state。

 and if you do something wrong， it will do totally unde defined behavior。

The the more the even the more scariest stuff is things like。Like actual caches。

 like actual memory caches where。In what GPU， we will automatically say， okay。You know。

 we need to take this data from the tile and put it into main memory like I was saying earlier in Vulcan that is。

It is more complicated to configure that actually that example that's probably not a good example because not too complicated in Ban but there are various ways where like you know there's different sections of memory like abstractly there's different sections of memory of the GPU and you need to like flush a cache so that when you write this data it shows up over there rather than getting some old cache data like you need to flush the cache and you also need to invalid that cache to get between two different units of the GPU。

嗯。There are other examples I can't think about off the top of my head。

 but there's a lot of that kind of stuff， a lot of memory management that if you do it wrong will。

Break， will just break。Just give you bad data fair to that flexibility Yeah， so the。

 the point of the flexibility is to let you。It's to let you squeeze out performance right and so it's not limiting to what you can do。

 but it's limiting to what you how fast you can do it。

 which is of course limiting to how much you can do in a frame。嗯。In practice。

 I don't know how much of it instrument that is。嗯。One of the reasons for the wave Vulcan。

Like one of the reasons Vulcan is the way it is is because。

Console developers had a single piece of hardware。And they wanted control over all that stuff。

Because they were going to， because they knew exactly what the piece of hardware was。

 they could optimize for that piece of hardware and it would work and it would be the fastest it could be on every PS5。

嗯。Falcon。Provides every knob that every piece of hardware could need and not every hardware needs every knob。

So。You end up with。Like all of the complexity you could possibly have。Some of it。

 which is optional to use。And some of it and also some of it。

 which will be completely ignored by some drivers， by some devices， like NVIDdia in particular。

 actually ignores a lot of that stuff that I just said you could configure in V because they have a really good coprocessor that deals with like optimizing that kind of stuff for open jail。

And so in practice， we've seen that。When we get stuff wrong on NVIDdia， it just works anyway。

 whereas if you get something wrong on AMD。Then it actually paid attention to what you said and it actually breaks so like that's context for why the complexity exists so like if you use Vulcan to target a console then you still have all the knobs and you can still optimize it perfectly for that piece of hardware if you are a AAA game developer you can optimize for every common GPU architecture and you can switch you can switch your codepas depending on which architecture you use and you know you get in a room with an AMD engineer and they help you like。

Do the correct optimization for the andDcode path。But none of that stuff is practical on the web。

So that's part of the reason it doesn't exist。Like you're never going to be writing a web page that's for a single piece of hardware。

 right？Almost never technically possible happens， happens in some enterprise scenarios。

 but basically never， so yeah。好，我楚。All right， oh yes， of course。Eation。一般上在那就上。Any that is。嗯。Yeah。

 so。Typically， multi threading has the problem of like data racists， right。

 you've got multiple threads and if they do things。

And they interact with the same piece of data and you get undefined results because of that JavaScript does not want you to see that as much as possible。

Languages like CNC++ will just let you do it and we'll give you no safeguards。

 languages like you know manage languages and languages like Ru。

U will and Sw and like all these newer languages will deal with that stuff for you will will either。

We'll usually have some static checks for you from doing that kind of thing。The way that JavaScript。

 the way that multi thread was put on the web。Was that JavaScript is still singled credit。

This is web dev stuff， but JavaScript is single threaded。

 you can create a separate context that runs its own single threaded JavaScript and you can send stuff between them。

So it is a very different model from what you get in typical C+。嗯。And the。There's a bunch of。

There's a bunch of reasons that like it's difficult for us to do this like we have we have a design for how GP works in multithreaded JavaScript。

 but we are dealing with this like message passing interface where like in order to get a thing to another thread。

 you have to send it over there。You can't just have it and use it。

And that is difficult for graphics applications in a lot of ways。

 especially web assemblymbly applications， which are implementing like C+ plus multi thread on top of this weird JavaScript multi multi thread model and so for example。

 if you create a。GPU buffer on one thread in order to use it on another thread and C++ you just use it nobody cares right but in or even in Ro like you sent you consent you can have it have it be you know shareable because it's an immutable pointer so it's fine you can you can now use it on another thread but。

The web GPU stuff doesn't exist inside of Webassembly。

 it's not happening inside your C++ application that's running on top of JavaScript。

It's in the browser， and so we have to go out to the multiple JavaScript threads。

 and then the two JavaScript threads have to somehow conjure up a reference to the same object。

Which again， we don't have a way to do， right， we have to send it explicitly。

And so the bunch of complexity shows up， especially when Webassembly is involved。

But it is there's a bunch of reasons for why the web is the way it is fundamentally like the main one is that JavaScript was not designed to be multithreaded and because it is a very dynamic language。

 would it becomes extremely expensive when you need to like synchronize all of the constant dynamic state like dynamic types and all this stuff that needs to be synchronized between threads。

Um， and so the model of the web instead chose to do this kind of weird thing。Yeah。

Any more questions about any of that stuff？I' am getting there。

 but it's up in an hour and 10 minutes already， so we will keep moving。

If there are no more questions。So yeah that's what you need to draw a triangle there's a bunch of other stuff so of course textures like I mentioned created in a similar way。

 different parameters， but again fixed size fixed format。

 all this stuff has fixed at creation you can you can only change the contents。

So this here is a 1024 by 1024 texture， it's a default to 2D， six layers， so we have six layers here。

 it's MI mapps so we're allocating space forward for successively smaller images for sampling。嗯。

And then we create a view onto that thing， which is used for various purposes。

 this particular one is a 2D view that is taking only layer。2。

Like the third layer of the array the of the array of。Arrayve images。And only the only one MI level。

The second one is creating a cube map view onto the same array。

 so it's taking the six textures andrranging them onto the faces of a cube。

Which is used for a bunch of things in a bunch of techniques。And。

You can also specify like when you're rendering to the thing。

 you can also specify a slice of a 3D texture or like an array layer of a view whatever or a array layer of a texture or whatever you need to do so you can appropriate get into the appropriate sections of the texture。

Sampler is just the it's pretty simple， it's just a piece of state that holds ors just a state object that holds all the state of a sampler object。

In open jelities。Sure traditionalally are properties as the texture that you can change dynamically。

 so you have your texture object， you set all the sampler parameters on it， and then you use it。

And then you need to use it in a different way， you overide those sample of parameters。

 use it again here the sample and the texture are totally separate so that things like address mode and magnification and magnification filters andm filters and all this stuff。

Get put into the single state object that you can bind separately and use along with it next year。

There's also of course compute compute is very important， we have compute pipelines。

 these are very simple to create， they don't have any of all。

 they don't have any of that stuff that render pipelines have。It's just a shader。

And a layout for the stuff you're going to buy into it。

And then compute passes are similar render passes， but again simpler， couple pieces of state。

 you set a pipeline set a bind group dispatch the shader。嗯。So here we're dispatching 32 by 16。

Work groups， and then the size of the work group， the number of threads in the work groups。Is。

Defined by the shader itself。The trader might say， you know。

 each one is four by four and you're going to do 3 or2 by 16 of those blocks or something like that。

so in in you lock and the number of lock right。In while couldn open C， Web GQ。

 all of these other pipeline， you do。Block size and then the total launch sum。

And we would actually specify the number of blocks So actually in WebGP， we did this differently。

 I don't really， I don't remember why it was a long time ago。

 but this is this one is actually a number of blocks。嗯。Which is the same as something。

most APIs they say the number of threads and then if it's not a multiple of the block size it will be an error。

 you kind of want it to eliminate that part of it and so here you're dispatching a number of blocks that is different from a lot of the other APIs so that's a thing to be aware of。

No， no worries。嗯。Yes， unfortunately， I don't remember any of my kuda language so I can't give you this stuff in terms of things you've learned already。

 but hopefully you'll be able to map them。They're a lot of the same concepts。

And I keep referring to binding data to shaders， but I have not explained that at all。

 this is the whole topic， and it's one of the trickier parts of the API is like how to actually attach resources to shaders so you can use them from the GPU。

What did you use the thing we call bind groups？It's not exactly the same as any of the native APIs。

 but it's fundamentally very similar， especially to Vulcan。

 it's very similar to the way the Vulcan works。So in the shader， it will something like this。

 you have either- so you' if you're rendering you can get data into the shader。In one of two ways。

 and of course， the shader is a program that runs Perth like runs many threads in parallel。

Just like a coA program。So you a you have a couple ways of getting input into the shadedr。

 you have a couple ways of getting output from the shader。

You can either get data from attachments or you can get them from vertex buffers。

 yeah vertex data from vertex buffers and output'll put them into the to either either other bindings or to the output attachments。

 like for example， in the example， the canvas。嗯。So binding are declared in the shader like this details not important。

 but you can see here that we have like。So a couple of various arrays of data that we're going to use to do some simulation。

And some state that we're using to configure our simulation。Oh。嗯。Right there。And then。

The second thing is the group number， so。I mentioned that we have bind groups and bindings。

 so a bind group is a group of bindings， so this first one is in bind group zero。

Like binding binding group slot is zero， binding slot is zero。

 and we have another binding group binding group one with two binding slots in it。Okay。

And that all can be represented on the API side outside the shader with this layout。

So this is the layout of one of those two group bind groups that were defined in the shader。

 we have an input buffer and output buffer so the input buffer is read only output buffer is writeriable。

I guess we're going to do some simulation and put the result into the rightriable buffer。

As I was learning this， the best way I could think about binding new layout is these are the function parameters you're setting cons not cons and stuff within the layout Yeah yeah so the bindings。

A。Yeah， the bindings are all like the resources that are going to be bound for all threads。Right。

 so these are the you're going to put some buffers in there and all threads are going to have access to the same buffers。

 whereas like vertex attributes are different for each invocation。

So this is those like a couple of pointers， essentially that you're passing to everything so they can access the contents of the resources。



![](img/27abea06e675c0ec2dc4e187af5c1777_46.png)

So here this is the mapping from those binding zero binding ones， those binding zero binding one。

And then the type of the thing corresponds to the of the type in the shader。

So we've got read only and readtable storage and those are just。Essentially byta arrays。

 but you can only look at what they are a arrays of this struct called particle that contains some particle debate in it。



![](img/27abea06e675c0ec2dc4e187af5c1777_48.png)

Pippeline layout is a。List of bindine group layouts。

 so we've got bind group layout A in bind group slot zero， bind group layout B and bind group slot1。

 corresponding with group zero and group one in the shader。

And those are these are part of the pipeline。 so so one the other important thing in both compute and render pipelines is the layout of the data that you're going to attach to them。

 and this allows the。Driver。2。Compile the shader in a way that leaves a space for those pointers to be bound so they can be bound at runtime。

And so that's why the layout needs to be known ahead of time。嗯。

You can also avoid creating a you can also avoid doing this stuff explicitly by using auto there's some there's some。

Some limitations to that， but it does let you avoid that in a lot of cases for like cases where you just need where you just have a single shader that's not going to be shared。

 not going to be sharing anybody with anything else。

Bine group itself contains the actual resources so here we have a bind group play of course。

 and two bindings， so we have the actual buffers。That we can bind into those。

 we can bind them with offsets， they can find ranges of those resources。



![](img/27abea06e675c0ec2dc4e187af5c1777_50.png)

嗯。And those correspond to。You know，Again， to binding zero binding one in the shader。

 and that's where they weren't going to get bound into so you can access them at runtime。



![](img/27abea06e675c0ec2dc4e187af5c1777_52.png)

In order to actually set those， those a part of the state that you set up when you're creating the encoder。

 so here we just set a bind group so the thing that gets set is the whole bind group。

We have our uniformous binding group we our particle spine group。That have the。

 that have those pointers that we need in order to。Oneun thing。Um these again get reset every pass。

 there's no like global state or anything， so it is just something you set， draw。

 forget about you don't need the state anymore。嗯。Bine groups are just pointers， like I mentioned。

 they don't snapshot the contents of the resource。Just give the shader a reference to that resource。

 so is a readable resource and they can change it。U when you change the buffer。

 it becomes visible to the next trader that gets executed。Typically。

 something will be written like some resource is going to be updated every frame because you need to do something different every frame。

So here， for example， we just have our uniform array that has our time of the simulation and we。

Plug it into the thing。Write it into that buffer so it'll be visible when the shader executes。

So yeah， we'll learn tour， you'll figure it out it's not too complicated， it's just a little messy。

But any questions about bindinging？Yes。Yes I。Have a second about that later。第五。Yes。

 so I definitely have a section about that later， I will explain。

But basically the reason is that it reduces the number of binding calls that we need to make。

Here we only need to set two rather than three。And if we needed to reuse some of those。

 we wouldn't have to set them again。

![](img/27abea06e675c0ec2dc4e187af5c1777_54.png)

Debugging APIs， and this was especially relevant last year when Branon wrote this because he had just implemented a lot of this stuff。



![](img/27abea06e675c0ec2dc4e187af5c1777_56.png)

So you will， of course。You need to deg your code。This is the WebGL version。

 this variant of this hello triangle doesn't draw anything。Can you figure out why？



![](img/27abea06e675c0ec2dc4e187af5c1777_58.png)

I'm not going to ask you actually figure out why， but open gel will helpful tell you gel invalid operation。

 and I'm sure that you have all dealt with this and it is a nightmare sometimes。嗯。

You will probably have stuck a lot of GL get error calls all over the place to figure out which actual call the thing came from。

Although to be fair， WebGL will print will actually print an error message by default in OpenGL you have to like set it up。

 there's like some like you know callbacks that you have to call to get the thing printed so it's not the worst。

 but you know you have to figure out where where the error came from so you end up doing this get error thing。

And of course， getter is super slow so you can't leave it in there。

 you got to take it out when you're done。

![](img/27abea06e675c0ec2dc4e187af5c1777_60.png)

嗯。This is Brandon's self portrait that I kept。He was like， okay。

 I'm really unhappy with this situation of finding finding finding your errors and your code right so we're going to give you messages that are useful。

So here's the Web GPP version of the thing。Of roughly the same bug， again。

 like not at all obvious what the problem is here， but Chrome will tell you that your buffer is missing the vertex usage。

And it will tell you when。It found out like when you tried to use vertex use it as a vertex buffer and you couldn't。

 so it tells you here like you did a set vertex buffer call， here are the arguments。And。

This was there。So of course， you can see that right here， the usage didn't have vertex easy。嗯。

And that's the that's the context point it won't give you a line number。

 unfortunately because of reasons involving like how the how these commands get from JavaScript to another process to be executed。

But usually it's enough information to identify。

![](img/27abea06e675c0ec2dc4e187af5c1777_62.png)

If it's a big program， though， that it can be quite hard。

 especially if you've like messed something up deep in some like helper code or something。

So the more context you can get from that error， the better you may have noticed everything in there said like buffer unlabeled command brother underpas andr unlabeled。

 that is strongly encouraging you to label things。

![](img/27abea06e675c0ec2dc4e187af5c1777_64.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_65.png)

So everything can be labeled。So here we would say like this vertex buffer contains play over vertices and this is our primary underpass。

 and then when we get our error message it's going to say。

Your player vertices buffer didn't have this usage when you were encoding the primary renderpa。

 and then you can just go look at those two places。



![](img/27abea06e675c0ec2dc4e187af5c1777_67.png)

So use labels is very helpful。Also debug groups， another another fun debug debugging feature that all that like we brought in from a lot of the native APIs。

 they all have they all have these concepts and so we you know these are not unique to Web GPU but they're extremely useful so now we can also say like in our main。



![](img/27abea06e675c0ec2dc4e187af5c1777_69.png)

You know command encoder or whatever， we've got our main render loop。

 this section is the scene as part of the UI， we want to submit it all as one command encoder like because we don't there's no reason to split it up。

But we can group it up for debugging purposes only， and the console will tell you。

Here's where you were in the debug groups like you were rendering the player， which was in the scene。

 which was part of the main render loop and then you can find the thing that you were looking for and you don't have to take these out when you're done because they're not very slow。

I'm like get there because。Get air has to go。All the way to the other process。

 wait for it to finish everything and come back。So these are fine to keep in there。



![](img/27abea06e675c0ec2dc4e187af5c1777_71.png)

tinyly bit overhead but。Not too big。Here is a。More complex example from one of Brandon's apps。

I forgott to change my to Brandon's on this slide。So we've got binding offset。

Which is too big for the buffer， like we're trying to bind in some place past the end of the buffer。

It's in the frame bind group。Well， like while we're creating the buying group。And。

It happens during like drawing meta balls in the main render pass。



![](img/27abea06e675c0ec2dc4e187af5c1777_73.png)

In the frame loop。So you know exactly what you're looking for。



![](img/27abea06e675c0ec2dc4e187af5c1777_75.png)

嗯。This is the slides version of a guide that Brandon wrote about best practices for performance in WebGPU。

 so that's another section and questions about this debugging stuff you will use it all you'll use this stuff so don't worry about it too much just know that it exists because you're going to want it。



![](img/27abea06e675c0ec2dc4e187af5c1777_77.png)

，All right， yes， oh sorry。

![](img/27abea06e675c0ec2dc4e187af5c1777_79.png)

That。Proably and I think I见 as算。Ed a reporting。some of the best Ive seen across any yes。

 Brandon did I mean， we we built a lot of infrastructure to be able to do that。

 but Brandon like went through and like made everything good。Which was like really helpful。

 it's been super helpful to developers and like。It means that the number of people we get coming to us being like what the hell is wrong with my app is a lot less。

It's very nice。Yeah， I guess this is more question about like common idioms。

 but like I know in Vkin generally when you have like a validation layer that's something that you only put in like within your Depot build。

 but like in WebDPU is it like generally more acceptable to like have validation for like all even like in production？

嗯。Like like labels and that kind of thing， debug groups and all that。Yeah。There is。

 it definitely makes sense to take those out in production if you have like a high performance app and you have the ability to take them out。

嗯。But it's just a couple of bytes that we're in like it's just it's just a small string right compared with the other overheads of Web GPPU。

 which include the fact that we have to validate everything for security reasons。

Copying colobit surround is really not a big deal。So there might be a point where taking them out will help。

But if you're like bottlenecked in certain places at that point you probably won these API。

potentiallytenti， like， I don't know。 I don't know how far。 I don't know how。

I don't know like exactly what the level of overhead of these is， but if you're if you're。

If need you need to squeeze out the performance， there's probably other things that will give you back a lot more performance than that。

Potentially switching to native if you really have to。

 but obviously there's reasons that you want to be on WebGP if you started there。All right。

 I will try to get through this。Were quick because I feel like it' we're going a little。



![](img/27abea06e675c0ec2dc4e187af5c1777_81.png)

It's gone a little long， but I don't have too many slides left， so it's all good。

These are just some tips that probably will not mean a ton to you right now。

 but you might want to revisit them after you've worked with WebGPU a bit might especially be helpful when you're working on the performance optimization stages of projects。

So one， minimize the number of pipelines you use。More pipelines means more state switching and there's a lot of states that comes along with a pipeline。

 which means less performance。Additionally， compiling pipelines also quite expensive。

So this may not be trivial depending on where your assets come from or like how your engine works。

 what techniques you're using。But Brandon has a whole article focused mostly on this。

 he has he had a GLTF model viewer and he's talking about like， okay， you know。

We have different materials within the model。Um， or whatever or different， you know。

 different textures or whatever， and we want to reduce same like we want to reduce the overhead of like dealing with rendering all this stuff within a frame。

嗯。But。Hい， how many is more。嗯。I just more or two is， I would say two is not more。嗯。😊。

It is not uncommon in larger apps to end up with like hundreds of pipelines。嗯。

It depends a lot on what your app is doing right if you have if you fundamentally have a rendering architecture that is like PVR and you can have it。

 you can have like relatively few shaders that can represent relatively many materials then。

That's great and it allows you to reduce the number of pipeline switches。But。

If that's not how your engine works， then you know。

 you're limited by by what you can optimize so it's really just like use。

The number use roughly the minimum number for the technique that you're using。

It really depends on what you're actually doing。嗯。There is an important note that I almost forgot to read。

 an example of this in the real world is the developer of Doom E。

 which is a very well performing Balkan game， has said that the entire game uses 50 pipelines。

Whi is really impressive and I do not know very much about the details of that。

 but if you are interested you should look it up， I'm sure that it involves a lot of like U shaders or like you know。

 shaders that are able to take care of a lot of different things。

 a lot of different types of materials， that kind of thing。



![](img/27abea06e675c0ec2dc4e187af5c1777_83.png)

嗯。In Web GPpU， we have something called asynchronous pipeline creation， so in this example code。We。

Can create a pipeline and then immediately use it， but like I mentioned。

 creating a pipeline can be a pretty expensive operation， especially if you have a large shader。

The create compute pipeline function will just return immediately。

 it will just say here's your compute pipeline， but the compute pipeline is not actually ready yet。

So when you want to use it。If you go ahead and use it immediately and then you submit。

Then that submit is going to have to wait for the compute pipeline to finish being create。

This is a major source of change。Um， especiallyspec with large shaders， especially if you need to。

 for example， load in a new object with a new material because you turn the camera。

 it's a very common situation。If you can possibly avoid that， you would like to， of course。

 you know compilrs compiling shaders and pipelines early helps support doing it on the frame of in WebGPU we have ASync versions of these so I know I just said that like it returns immediately and happens later so they're all async but we call this one async because it returns a promise。

 a promise is a JavaScript。Like fundamental type， which。Let which says like in the future。

 I think we'll be ready and you can you can like do something when it becomes ready so this returns a promise the promise resolves when the pipeline is ready to use。

So if you use it， then there will be no stall because you already know that the thing is compiled and ready to use。

Chrome will also use this as a hint to compile your pipelines in parallel so you can kick off multiple of them and they will have it on multiple threads internally Fundly this doesn't have to be the case we could do this we could use multiple threads even if you didn't use asnc but it's currently used as a hint for that。

Because typically an application。If it's going to create a lot of pipelines。

It's going to want to kick off a lot of pipeline creation at the beginning and then know when like when all those pipelines become available。



![](img/27abea06e675c0ec2dc4e187af5c1777_85.png)

Here's a trace of Chrome。As screenshot， the brain into when is working on system performance tests。

He found that almost all the time spent in the test was waiting for a pipeline compilation to finish because it's a test so it has different it like runs through a loop of many different test cases and it compiles ther slightly different shader each time。

嗯。Doing it with async made everyone run in parallel because Grme took that hint。

And so we were able to use a bunch of threads of the CPU to do that compilation work。

And the test that's a quick refactor and the test ran four times faster and of course this is like a weird case because it's a test that's specifically trying to create a lot of pipelines that is not usually going to be the case。

 but you can see that like if you have a lot of pipelines this works really well or if you even have a few pipelines。

 this works really well。

![](img/27abea06e675c0ec2dc4e187af5c1777_87.png)

嗯。Next one， share buying groups between pipelines。 I'm finally back to the thing that somebody that you asked buying groups can be shared between pipelines use the same bind group layout。

 So a common pattern is to have things like。Camerry uniforms are going to be constant for the entire frame。

In a bind group that you set one time at the top。And then。You go through your materials。

 each material has some material properties， or rather a pipeline for that material and some material properties。

And la mehes that you want to render with that material。

 and this reduces the total number of state setting calls because you only had to set thats the camera parameters once。

You only had to set the material data once per material， you only had to set the。

 or then you had to set the vertex buffer once per mesh at the end or in the innermost loop。

So try generally try to group。Bindings between bind groups so that the number of binding calls you need to make will be reduced and so that is this is basically why bind group exists so that you can group them in this way and then have just one call for each group。

嗯。Another one used the right attachment format， so weird quirk of history is that for some reason。

 even though everything is RGBA。For most purposes。Putting stuff on the screen is BGRA on every piece of hardware。

 except for Android hardware。 It's， it's a mess。 This is how it is。

 So we have this extra format called B GRA 8 Uor， which is the same as RGBA Unor。

 except the B and R flip。And each platform has a different preference， like I said。

 I'm pretty sure there'll all be G except for Android that you can ask for the preferred Canva format and then use that when you're setting up your context。

And use that when setting up your pipelines， and it will avoid a potential， potentially costly。

Conversion into the other format before we put it on the display and that's just it's just details of like there is a thing called the display controller which read just has a piece of memory and it just dumps the data straight onto the screen and it needs to be in the right format immediately because it's not doing any processing during that during that stage where it pushes it into the display play。

嗯。Reendnder bundles are a feature of WebGPU that I have not mentioned at all yet。

 they are prerecorded partial reusable render passes so you can take some of the commands from an encoder from like a render pass encoder and put them into a bundle and then you only need one call to do it so if that's something you're going to use a few times。

Um， like if you're going to use it every frame or something。

 then that saves you a lot of overhead on the application side， like on the JavaScript side。

These can contain most rendering commands， some of them can't be inside of the bundles for various reasons regarding。

How like what like regarding the native features so this is abstracting。

 but it works well for a lot of purposes。嗯。So you you create this on bundle and then there's a function to read to。

Replay it during your render pass so you have your render pass you set up some state and draw and then your bundle can set up some other state and draw and then you can set up some more state and draw so it takes all those commands and squishes them into one。

嗯。All the state resets when that happens。 So like there's no state that's crossing the boundary between the bundle and the render pass。

 except for the state， which is。On the pass that you can't sit in the render bundle。

 which is a couple of things like beautyport and stuff。嗯。

The main purpose of this is really to reduce JavaScript overhead。

But it does correspond to native features as well， so it reduces overheadheaded other layers of the stack as well。

The GPU performance will be approximately the same either way because the。

GPU will be doing the same amount of work。Except basically instead of an array of a couple commands might have a pointer to a list of commands。

 not a big deal。

![](img/27abea06e675c0ec2dc4e187af5c1777_89.png)

There's a couple of demo， we have a couple demos over our render bundles so back to demos。



![](img/27abea06e675c0ec2dc4e187af5c1777_91.png)

This is a is a Babylon jazz playground。Showing like a big complex model。

 they're able because it's a static scene， they're able to able to take all of the static stuff and put it into a single render bundle。

嗯。And here， so they have a couple of mode， like a couple of different ways in their engine that they build up these render bundles。

But we can see that without using these snapshots， which are implementing hover render bottles。

 we're getting 2。6 milliseconds per frame and then。They can。

 depending on the properties of the scene， you can use different levels of optimization in Babylon jazz。

This is a very static scene， so standard gets us down to 1。9 and fast gets us down to。

5So we're able to save a lot of time on the JavaScript side by doing this。

 and the JavaScript is very often the limiting like the bottleneck。Um。

 for the application because usually there's a lot of other stuff to do in there as well。Second demo。

This one is doing callinging using render bundles。You would， you know potentially have。

Frusstum calling you want to draw only the objects that are inside of the thrustum。

 so on the left side we have our actual application on the right side， we have our debug view。嗯。

You could say for every individual object in here we're going to do frost coloring separately right but that's a lot of objects。

 we can build up some kind of tree fallinging volume higher or you of some kind。

And then each object we can bundle a few objects into a render bundle。

 and we can do it at a slightly higher granularity。So。嗯。Let's see。

This one I believe is calling on a per objectic basis。嗯。Unfortunately， I don't have a oh， okay， yes。

 frame JavaScript milliseconds。If we draw everything， we're doing like 2。6 milliseconds。

 if we cu stuff here， we're getting like 0。2 pretty fast。But if we reduce things into。F those we。

And call the render bundles， which are a bit larger then we're reducing it a bit more it's a little noisy so it's kind of hard to see but we're seeing like 0。

14 or something here， so it's a bit faster。嗯。And you can animated too， just for fun。Yeah。

 so here this is dont I't know what machine this is from the 2。4 to 。5 on that one。And。

There's a whole article that goes along with this one， so if Li。

 if you want to see what went into creating this demo， like how this actually works technically。

 read the article very good， Brandan wrote that。

![](img/27abea06e675c0ec2dc4e187af5c1777_93.png)

Okay， that is basically it for content I have lots of links in here if I come up with any more links I will add them here so like use this use this slide as your reference。

To find all these things， there's samples。There's a bunch of tutorials。

 there's a bunch of articles for various various things that you might want to do for a Wigel。

 there is this thing called To of Wigsel that my team built。

 which is a tutorial of like how to do things in Wigsel built giving you a lot of the， you know。

Tre through a lot of the syntax stuff so if you're familiar with GLSL will be useful to like go through that quickly and just see what the syntax looks like。

This past this particular one， elements of design of explicit graphics APIs is a past lecture from。

Fiveish years ago in this course from my team。This was before we had Web GPU as a concrete thing that we could talk about we were talking about。

What were how were the explicit graphics APIs designed like why are they the way they are I like couldn't help myself and got into some of those but like without slides it was probably very confusing if you were interested in that it's very useful you probably will not need to reference that but there's some very interesting stuff in there in particular talking about things like tile- based rendering which I mentioned like mobile power saving architecture。

As well as prevalidation， like which is what we're doing when we're putting all the all the state into a render pipeline validating it once so that you can use it later without revalating all of that stuff and so a lot of those concepts come from the designs of the native APIs。

More tutorials， various things， links to the best practices if you would really like to read like 200 whatever pages or something of specification。

For just one of those I don't have like you know thousand pages。

 a couple hundred pages of specification you can go to there now actually these are very useful references though if you want to learn details of how a call works or like what the validation is check it out that is the thing that is the thing that I work on or like one the one of the main things that I work on。

 I think it is a pretty decent。诶。Sort of。Reference for developers in addition to being what it primarily is。

 which is a reference for browser implementers to implement WebGU。So。If。

It is likely that you will want to look at that because there aren't a ton of resources online about WebGPU。

 there are some， but if you try to Google a specific question。

 you may or may not get the answer because somebody may or may not have asked it because WebGPU hasn't been around for that long。

 but all of the details of the WebGPU are in the spec and Wsel are in the specs。So。

Take a look at those if you need to find a detail， that isn't easily available somewhere else。

Also a couple of tools you might want to look at for debugging and that kind of thing。

 web GPU inspector it' like a like record replay based tool for webGPU。

can do very nice things like show you that the intermediate state of your frame while you were rendering so you can see the exact point where something went wrong and the exact state at that point。

SimilarThere's a similar tool for WebGL。And similar tools for a lot of graphics APIs。

Wigs will offset computer is for。Figuring out how to get your data into weaselstructs because you may have noticed that data was bound intostructs and arrays and that kind of thing you need to get the data。

 you need to write the data into the appropriate format so it will be read correctly from the shader。

Link to this guide and about profiling with GPU on Windows with a tool called Pix， which is。

Part of visual Studio and also it has a standone version may be useful if you want to do profiling work or optimization work on a project。

And finally。There's the community stuff， if you have questions please feel free to join there's a bunch of community members in there a bunch of team members in there and there's also like the stackco overflow style Q&A on GitHub。

 whichever one you want to use。And not for your projects， but in general for general purpose。

 there are a number of libraries with WebG G， I'm getting tired。

 a number of libraries with WebGPU support， including Unity， Babylon3， Blake Canvas。

 and more that I didn't list here。嗯。That is everything about what GPU that I have。

Time to talk about substantially longer than I hoped it would be。

 but we got into a lot of good questions， so I'm glad that we got a chance to talk about those。

Any questions on any of the last stuff that I talked about？you don't mind。 Let's give it。できまし。

Thank you。😊，Yes， should we that before we go into open Q&A sure， yeah。You can。

So my disclaimer and career advice is I am one person， I've had one job。

 one fulltime job in my career， so my career experience is pretty narrow。

 I also have no experience getting a job in a bad job market I'm sorry this is the question that everyone wants to ask me and I really have no idea。

 I can tell you。Some vague feelings I have about what hiring is like at Google right now it's not great。

 it's not as bad as it was。So advice。嗯。I dumped a lot of stuff in here。

 but it's kind of stuff that I。Feel like is has been valuable to me。

 things that I've either figured out over time or that have proven to work well for me。It's it。

It is really important to pay attention to your mental and physical health。Not like I burned out。

Fortunately。Like I didn't burn out during school， but。I would have。嗯。

Don't let that happen to you be mindful pay attention make sure that you're gonna like be okay right that's the most important thing I like my back is not good because I use my laptop way too much for many years not a good not not a good way to be second thing give yourself time for personal development like literally i'm。

Don't。Focus all your work on like all your time on academics， it is really important。

To have social relationships。嗯。While you're in school。

 because those are really important friendships that are going to stick with you for a long time。

And that's a network that。Will bring more connections into your life。m at Siggra。

 so I went to Sgra this year for the first time in five years because I just。Didn't。

Feel like going to a giant conference for many years。And。

There were so many people there that I know from school that I haven't seen since last day graph or longer。

 but it's just like it's so good to see these people again and I remember that I have these connections with all these people。

Because I made those connections while I was in school。mAnd I made every time I go to SGgra。

 I make a bunch of new friends because all of them have friends like， you know。

 I've got my like 10 friends or whatever they work at Disney and。

They have like all my cool friends have also have cool friends， right。

 like like every time I go to S I make a bunch of friends's。

It's great like this is something that nobody else on our team has other than the Penn folks because we just have such a strong community it's really important not just to be connected with like your graphics community or your degree community or whatever。

 but just generally like have people that。You want to see again right this is this is this helps you a lot。

All the time。Also， don't neglect personal relationships after school， it is pretty easy to do that。

But making new friends after school is quite hard。And the relationships that you have that you make in school are probably going to last for a long time。

 so those are important to maintain。But you don't have to like put a lot of effort into maintaining them because they are。

There are connections that last a long time right like I didn't see a lot of these people for five years I didn't talk to them at all。

 they're still my friends because because we had a strong connection to begin with。Next thing。

 starting to get into job advice。Don't expect to find a dream job dont don't even expect to know what a dream job is like when I was graduating I was like really like what the heck am I going to do with my life there are so many things I would like to do I was really interested in teaching I was really interested in maybe I wanted to do something in physics or like do a PhD program in physics or something like that and I was like really worried。

About what I was going to do。And now to be fair， I got really lucky in what I ended up doing。mBut。

Like like。I got lucky at Way training stages， but I。Book this course and。Ken Russell。

Gueests lectured in the course and then when I got an offer at Google。Patrick Cozy was like。

Would you like me to put you in touch with Ken Russell and see if he has any openings on his team and then I was like。

 I'll wait until I'm starting to do team matching then he sent the email anyway instead of waiting and that is how I ended up on my team。

Um and it has been wonderful， so I got super lucky， but I will mention actually。

 this is my partner's advice I was asking him earlier。

When you hear about somebody of's career trajectory。

 it will seem to form a coherent artrc like will seem somehow unintentional。

But it wasn't right like the arc of your career happened doesn't exist until after until after like until until it's in progress。

So don't expect your vision of the future to look anything like。

The arc of a person's career over many years。You will have no idea where it's going until it happens。

Um，Or you know， have a very rough idea where it's going。Um， in like when you're looking for a career。

 look for good experiences， it is very useful to make decent money， especially early in your career。

 you can pay off your loans。And you can not worry about like if you get laid off or something that's really valuable。

 cannot emphasize enough how much money is useful。嗯。But。In any case， look for good experiences。

 don't expect a job to be the center of your life， like don't feel like you're compromising if you go to big tech and make a bunch of money。

 but aren't working on the thing that you love。You will have an opportunity do that later if you want。

 you will also have an opportunity to not do it if you don't want to。Um。

 this is especially relevant right now because I feel like probably a lot of the jobs that are available are going to be in big tech because I think they are starting to a lot of the jobs are starting to pick up there。

 but a lot of them are also going to be in a startup and you're like， you know。

 this is a startup that's like， maybe interesting to me。

But if if startup culture if startup life is something that you would do， which I wouldn't。

 but then you know take the opportunity it's fine， you probably won't make a ton of money。

 but you will make。You will get ahead on things that you need to pay for。Um。

 a nine to five job with like a good work life balance。Can。Also teach you a lot。

 even if it's like not a passion， if it's just like a nine to five job， you will still learn a lot。

It will also leave a decent amount of time outside of your job。For whatever you want to do。

 but consider that five even a  nine to five job is quite draining in terms of energy。

 so don't expect to get a ton of stuff done outside of work。

 but like work life balance generally it's a very nice thing。

 if you are really passionate about a specific thing that's okay。But if you do。

 then you probably know and if you don't， then this is more general advice。嗯。Also。

 last's very unrelated thing， but like。There is a lot of really good stuff to learn about。

 like as an adult， like as somebody who isn't constantly surrounded by learning。

 like isn't constantly taking classes。I found myself at some point being like， okay。

 I'm learning about stuff at work， but like。Maybe I should take this opportunity to learn about other stuff in like a lower stakes environment than taking a class than we're going to be graded on。

There's a lot of good stuff， just like on YouTube， like random blogs。

It doesn't take a lot of effort to like passively learn some of this stuff over time it can be very interesting if it's a topic you're interested in。

 I learned tons of stuff like since graduating I've learned ton of stuff about urbanism and like science is outside of the one side studied labor history was way outside of anything I was ever thinking about when I was a student but has become extremely relevant to me a lot of the stuff that's really valuable to my life so that's a big side of advice。

Um but that is what that is the stuff I came up with literally like the whole week and I was like I don't know what I'm going to say and then last night I came up with all of this stuff I don't know like。

I just had to ruminate on it。But in any case。嗯。Speaking of jobs。

Possible maybe intern opening on our team this summer this coming summer。

 we have applied to host an intern literally on Friday。

 we applied to host an intern that's when the applications went out so no guarantees but it's likely we're hoping that we'll be able to host an intern so please be in touch with us if you're applying to Google's internship program。



![](img/27abea06e675c0ec2dc4e187af5c1777_95.png)

We do not have full time job openings at this time。I don't。For see us having any honestly， but T。

Be in touch， we would love to work with students from this course， obviously we have。

Had many like had worked with a lot of very successful students from this course and from Penn on our team。

And of course， when you're doing our projects， also be in touch with us because we're happy to help you with。

Stuff， bugs， whatever you're into too。Yes， I should also mention that， so the web。

 the webT view samples page that I linked to here， this first one， this。

 I should open this bunch samples on here。

![](img/27abea06e675c0ec2dc4e187af5c1777_97.png)

Most a lot of ones are written by our team， but there's a lot of useful stuff like look at this when you're trying to figure out how to do something。

 we have external samples， so a couple of here couple of them here。

 like including this one written by Brandon， a couple of written by Brandon。

 various ones contributed by random random and community members。



![](img/27abea06e675c0ec2dc4e187af5c1777_99.png)

啊。These are this is a place where we want to put samples that you like things that you build right if you build something cool you put it up online we can just embed it here that's the beauty of the web right like we can put your sample up on this website people will be able to use it as a reference people will be able to check it out so we would love to put your stuff here whatever you build。

Yes， Cha， why not？It's a， you know， you've created a teaching resource that people are going to look at and get value from。

嗯。

![](img/27abea06e675c0ec2dc4e187af5c1777_101.png)

So。Yeah。Thank you happy to take questions on whatever's left feel free to reach out there's my email you can if you want to ask about webGPU or specific questions or final project stuff or whatever email me and Brandon presumably one of us will not be on vacation or whatever at the time and we'll be able to help you。

So。Let's go up for questions both on the Q as well as anything that help。Yes。

I didn't listen to podcast that。But it has you it and Brandon， I think it's likesium， yeah。

 the open open metaverse one yeah and it said you said that。This passed up three times。Yes。

 so I sat in on this course when I had too many， I' had way too many classes this that semester。

 I sat sit sat in on the course and I heard how it was difficult so I was like， okay。

 I'll just absorb a little bit of knowledge。Set in on the course。

And then I actually took the course and then I did。So I was sitting in the class， okay。

 I might not have sat in the class every time when I was Ting。

 but I did sit in the class like substantial amount three different times。It was a little silly。

 but it worked out。You have a favorite assignment。嗯。What even were they assignments then？

of the so I don't know if you have this one anymore。

 but one the one of the assignments that I thought was very interesting and taught me a lot was the kuda Rasterizer。

Yeah， so it was a software raurizer where you would put in vertex data。

And run some kuda code for a shader。And then deal with getting the results out into the buffer。

And so you had to do like， you know，' you' you'd have a bunch of threads and then you'd be competing to write a pixel and so it flicker and had to fix the flicker by like putting in either some kind you'd put in some kind of law or some kind of like a depth buffer check or something like that prevent that from happening。

 but you kind of get a better picture of like wow that GPU is doing a ton of stuff for me。

That was a pretty cool assignment I liked that it was especially relevant because。

I was interested in the kind and like in in the pipeline of the GPU。

 like the stuff that it was doing that I。wasnn't really it wasn't wasn't necessarily so visible。

 but would then become really relevant to me like having that experience with things like that was very became very relevant for me just。

Understanding like how the heck does this thing work so that I can like go and write a spec about it。

Right。That one sticks in my mind another thing I did was my final project was with another student who's a friend of mine and we built a thing on top of webCL webCL was a web version of openCL that was proposed by some companies I don't remember who anymore of a beat。

Implementation of it was a plugin for Firefox implemented by Nokia， I believe。

 and by the time we did this project， it was already super dead， but it still worked。

And so we're like this would be kind of fun to like learn how this thing worked and so that was kind of an interesting project we did not do any like fun interruptop stuff but we did like do some open seal on the web back like in in the brief window when that was possible a couple of years ago I actually afforded that project to web GPU and it is still exactly as jay as before because I didn't fix any of the problems。

It's actually really slow， not like a good demo of anything， but it's cool looking kind of。

Those are the two projects I remember off the top of I head。And then the。I think。

The deferred rendering。Then the first version of of the WebG deferred rendering project was the one that I wrote。

 but I don't remember it's been so long， it's been nine years or whatever， nine years since I。

So wonderful。last。Yeah。好这。It was buggy， actually it had there were bugs in the template code。

 I didn't do it anyway， it's fine。Is there anything really looking forward to adding。

Do worry have right now that you。嗯。There's not much we can change because it has to be a stable web platform thing。

 we are like fixing a couple of things here and there we're like oh。

 actually this doesn't work as well as we thought it did like actually implementations of this are not consistent or whatever。

Right now， we don't have a ton of。Stuff going into the API there's like little features here in there like enable S so with Suna format or whatever。

 but we do have some big things going on with the shading language one of them is subgroup operations so I don't work on the shader team so I'm not like working on this stuff but there's there's subgroup operations which are a bunch of like like sort of like similar to atomics but like but specific to the single instruction multiple thread model。

Of things like like ballots where you have like each thread can like vote on which value to use。

 like weird stuff like that that apparently are very useful for certain algorithms。So there's that。

 which is a very tricky one because again， behavior is not very consistent across hardware。And。

There has been some work on cooperative matrix multiply。

 which is sort of a a feature like like a feature of。

Some GPUs where you can say like I want to multiply this matrix here's a section of the matrix please do that section for me and then you can build a big matrix multiply out of it for machine learning stuff so interesting stuff。

Things I would love to see。Are like meshing and things like this they're like exciting new things。

 but like they're hard to put into the platform because like they're not going to be supporteded on very much hardware and so it's just not going to happen for a long time cool stuff but。

Yeah， that's what comes to mind all the stuff in my head。

mostly we are trying to fill in all the gaps where like you know。

 unity or unreal or something like can't be fully ported like some parts of it can't be ported because we're missing。

 we have some problem。And we still have some of those。

 so that's like the important stuff that we're working on。Like in terms of features。怎么般的生么过。来我好单。

Yeah， I don't even know， so you'll you'll find out you'll know more than me R。

Same problem as mesh shaders， like not enough support。A lot of people are excited about it。

 a lot of people will keep asking about it， right？I。

Think that at some point we will see more prototyping work happen on it There was somebody a couple of years ago who like long before WebupP even was out。

Fruit呃。Prototyped， a proof of concept of。Bray tracing shaders。That worked on both D3 and Vulcan。

The metal。APpiI for ray tracing is apparently substantially different。In terms of its structure。

So it becomes very difficult to abstract and it is like this is this this becomes a research problem like this is a difficult thing to solve so we're both。

Stuck on the problem of design， like somebody needs to spend a lot of time designing it。

And the stuck on the problem is's not going to reach for many people。

And also ray tracing kind of requires a future called bindless。

 which lets you use like arbitrary pointers to resources rather than having to bind everything。

Also something we can't do in WebGVi basically because we can't have arbitrary pointer。

 we can't have UD referencing arbitrary pointers。So a bunch of reasons that that's farther off。

But so is mesh st and all this other cool stuff。We're inherently， like a little bit behind this。

Behind behindhind like the hardware， the bleeding edge of hard。

 because we are trying to reach everything。like not every feature recipe be on every device。

 but it has to be like pretty widespread and we have to see a future word's going to be on most devices。

On the very。在这。In will step back from extensions and profile。So it doesn't doesn't doesn't。

We still have quite a lot of that kind of stuff， there will always be fragmentation。But what。

 but something we don't want to see is like we've put out a feature。 and then like。

A D never implements it。 Like we can never put it on。

 like it can never run on AM D on AM D hardware or something like that， or like。Even on mobile。

 like you know， we put out a future and then it works it never works on mobile or it never works on one of the mobile architectures。

There are some things that will be desktop only like there are some features that will go in that are valuable enough。

That they will go in nonetheless， but generally we don't want to put in something that's going to end up in practice being vendor specific in some way。

嗯。我们说。懂。Yeah， I guess kind of was not。Immediately relevant question but how did Wigel end up with something that's like most similar when it's you know or web？

It just kind of， yeah， it kind of it kind of just happened that way。So there are some。

 some specific reasons that that that type of syntax like has。

Become more popular in newer languages regarding specifically how difficult it is to parse the complexity of the parser。

And so the like you know， the type， like the type variable order and that kind of thing。

Are adopted from a lot of languages that realize， oh， that we can simplify our parsing。

 We can make our parser faster by doing this。Also， we have a bunch of people designing a language。

 which means we have people who are interested in designing languages and they like language design like they like they're interested in modern language design。

 so we just kind of ended up with something that way。嗯。

We it's probably it probably would have been possible to build something that looked like GLSL or HLSL I'm sure we could have done it。

Um， but it just wasn't the way things went like just， you know。

 a matter of of like people need to sit down and need to crank out a language I like it yeah it is a little it's a little bit an oddible on the web yeah。

あ。What made been picked for it for years， like what were the unexpected challenges or was it like mini？

Well， okay， so the shading language thing actually took us two years。

 like like agreeing on which direction to take to the shaing language because we had this big disagreement between different companies on whether we should just use Spearv use a binary format or whether we should adopt HLSL or if we should adopt a thing that looks like HLSL or if we should build a new thing。

And it took us approximately two years to get through that discussion。

We weren't working on it the whole time we were doing it because we had lots of other details to work out we just kind of be like。

 okay， we're tired of this conversation right now we're going to do other stuff for a while。

 but that was one of it one of the things。Another one was just that it was a standardization effort。

We didn't really think hard enough about the fact that WebGP was going to be a new thing。Like webGL。

It tookook a while with standardized as well， but it was fundamentally the same as Open GLES。

 and so you were just binding it to the web and you had to find all the little things that needed to change。

Whereas we were building。We were designing something from scratch because。

Vulcan metal and D312 are not the same like we couldn't just say okay there's there's a common API that we're going to adopt it was nothing no such thing existed we had to design something。

And so a lot of past thoughts about how to do this kind of thing like came into the project and so that we didn't start from nothing。

Like the first prototype we built was my lead carrants。

Like vision of how here's what it's going to look like it changed a lot after that。But fundamentally。

 it was like standardization， like the fact that we had to have a bunch of companies agree。

 we had to have three browsers， four browsers when we started agree like four browser engines when we started agree on the design of the thing。

 agree that they were going to implement it like。If if at any point。

 it was a serious enough problem that a browser says we're not going to implement the thing。

Then it becomes a problem if we've alreadyshaped it。So。We。

 I think did the standardization process in a very cautious way。The。嗯。Like it it took us a long。

 I think the reason it took us a lot longer than expected was just that we planned that like we we made a bad estimate。

Like。😊，Fundamentally。Other than the sharing language thing。

 which we probably didn't expect was going to take two years just。Didn't。

Picture the amount of work that it was to do well enough at the beginning of the project。

We were just way too optimistic that it was going to take the amount of time that we thought。

It was was it just didn't it didn't make sense we worked so on。系 I I hadま so。嗯。

Some of us who go on to work as let's say key and an animation studio software that interview by hundreds of few thousand people。

Those of us like for driving open operation to millions。 you're shipping to millions。 Yes。

 What's that like。嗯。For our team， okay， there's there's two things， one is common to all of Chrome。

 which is that you are writing a piece of software that in most of Chrome is going to run on a bunch of different pieces。

 like bunch of different devices。And it's going to run on a bunch of different weird platforms and like weirdly set up user devices and you just don't know what's going to happen until you put it out there。

 yes。嗯。And。Also one of the most scrutinized like projects for security holes。In the world， right。

 because it's one of the highest stakes。m so dealing with like like the security culture and Chrome is very strong。

 we receive bugs， we drop everything， we fix the security bug， we push out the fix。

 we merge it back to earlier branches， we push them out to users， we do a lot of that。

The thing that is sort of unique to the GPU team。Is that we。

In addition to dealing with many different like operating systems and all this stuff we're also dealing with a bunch of different。

GPUs with a bunch of different driver versions that all have different bugs， they all have bugs。

 every different version of the driver has different bugs。

 you ask them you report a bug to them and they fix the bug and they introduce a new bug or they have fixed the bug like。

The whole history like the whole time I worked on Webjeello was that kind of stuff like aside from the very beginning where we were just trying to get it out the door。

 even even then like the thing， the problems we were looking at were like there's a bug on this hardware。

We have to out figure out a workaround for that so that the platform will be consistent so that applications will have run on that hardware。

And we do a lot of that we have not done quite as much of it with webGPU。

 I would say as we have done with webGL yet。But we we see that it is going certainly going to be on the same trajectory as what gel it is going to be weird driver problems forever I I am optimistic that it is better like one of the things one of the ideas of Vcan was that。

Less stuff would have to be in the driver so there's less opportunity for bugs。

It's unclear whether this is panning out， I think it is certainly the initial implementations of Vulcan were quite buggy。

 but they were very new， so it can be for。嗯。I think that they have reached stability faster。

 probably there were a lot of problems in open GL drivers and JLSL compilers because of the complexity of those things。

So。I'm somewhat optimistic that the trajectory for Web GPU will be better。

 plus between the time of WebGL and Web GPPU， GPUs have become more important。Companies consider。

Graphics acceleration and especially AI acceleration on even on GP to be critically important like it used to just be like。

A little division， they're like。Of a company that would be responsible for like we're going to show the user stuff。

 right？I think it's taken a lot more seriously now and so the quality of this stuff I think is better。

Industry wide because it's taken more seriously than it was。

It's given more resources people are worried more about failing tests and that kind of thing。

 so it's definitely a very different landscape than it was when what J was in it's and it's like equivalent this。

哎要是。好。好。Ha that XC comment hook on the door about standards？Yes。😊，嗯。

Certainly about week right Web GPU we fundamentally had to build a anything thing because we couldn't。

We couldn't take any of the existing things。 like we were in we were we were in a tough spot where we couldn't do that with Wigel。

Yes， it's like it's it's it's a kind of a low hanging joke I think。

 but like yeah it's brought up a lot and it's like not wrong。

 I would say not at least not entirely like this circumstancess made it difficult to avoid that kind of situation but。

嗯。But it's nonetheless。Kind of true。I'm pretty sure there's a past version of like a lecture that we gave in this course that has that comic on it。

 speaking of which I was just talking about all of this the process of standardizing this thing。

The first time that I gave a guest lecture was about the process of standardizing the thing because we were like right in the middle of it at that time。

 we didn't have the thing yet。And so I gave a guest lecture on like， here's the deal。

It'sInizing and that was only。Two years into it， probably。

So if you're interested in that process and how it took six and a half years。

 or I don't remember I should I should remember what the exact exact amount of time was。

 but something like that。You should take a look at those slides so that yeah。

 take a look at those slides， it's probably kind of interesting。

But it's very historical at this point。Yeah， not relevant to everybody。

 but if we do want to have the potential to intern on your team next summer。

 is there any like separate application for that or just like the Google it's it's just the Google software engineering internship。

 but let us know because I literally don't know。How the intern like the team selection process works。

Think。There is some way for us to be like we're expecting an application from this person let us know or something like that。

 I don't know how it works but let us know if you apply and make we'll figure out whatever it is we need to figure out it's been too many years since we did an internship and I don't remember how it works anymore。

And it's probably changed， so yeah， just be in touch。There is no additional application though。

 just to tell us who you are。And make sure that we know。Okay。뭘。喂，你这他被抓的。And the。Project for today。

 but given the time。I know all of you probably checked out by now。 let's do it bursting。

 but before the。诶我到呢太过咧会哋咁样。

![](img/27abea06e675c0ec2dc4e187af5c1777_103.png)

嗯谁关 project我你说的当作。社会い？the project0 x the project4。

![](img/27abea06e675c0ec2dc4e187af5c1777_105.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_106.png)