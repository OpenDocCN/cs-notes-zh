# 【从零开始用C语言制作游戏】 p01 Making a game in C from scratch! Ep 01： -Platform Layer and Softwar -BV18i421a7DD_p1-

Okay， welcome everyone to my first ever live stream。

Hopefully we're going to start building a game from scratch in C。

 and I'm going to show the whole process and we're going to learn a lot and hopefully have a lot of fun too。

Okay， so。First of all， I'm going to give you a little context as to what we're building。

 why we're building and how we're building。It all started when I released my first big commercial game called Eliliis Hunt。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_1.png)

We released it for PS4 and PC on 2017。And it was a great deal of work。

 it was like three and a half years of development， and it was， you know。

 it changed me completely by the end of the development。And I was great because I learned a lot。呃。

Because by the end， actually， because I started just hacking a little bit of a scripts together。

 using Rio engine， so I used mostly visual programming。

So by the end I realized that I actually didn't know how to program and in order to release the game robustly on PS4 and PC。

 I had to go down there and do some low level stuff like integrating the SDK。

For the consoles with F modD that we used for the sound library as well as Un versions and all that stuff。

So I realized that。I didn't actually know what I was doing in terms of programming。

 but we released the game and that was really hard but we did it and so when we did finding a release I was like。

 okay， I think I'm going to take a step back and actually learn。

Programming for real and use' a lot of YouTube videos and tweet streams to learn mostly from people who know have been doing it for a long time。

 like Jonathan B and Casey Muri。And I was very grateful for that opportunity and then I started building small projects in C++。

 things like that。And until。I started going back to Rome Rio and started using that programming experience to build more robust things。

In a。In a real using no C++， I build a game， a term base game with a LeO editor， a monster editor。

 a skill editor。And then I started coming across all these problems that people usually talk about when they say C++ that it's a complicated and messy language and all the friction that comes with it。

 like long time to compile and weird bugs like even with incremental builds。

 you know sometimes things don't work and with real I have to build you I have to use the debug editor to see where I think crashes and stuff and it takes a long time to start up and it's not a very fun process。

So at that time， approximately when I was you getting deeper into programming games programming。

 I had the opportunity to have an investment on a startup which had nothing to do with games so I was like I took the chance and started working on that。

So I was like， okay， so I'm going to take a break as a professional game developer， let's say。

 and focus on games as a hobby， so at that time I started to program you with no engines to really learn and start having fun and that's why I found the C programming language more interesting。

And you can see on my HIO page。Small games I built those three here on top with this idea in mind。

 you know taking。I even open source to one of them， which like a simple pun。

 and then I released this new one， which was。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_3.png)

Fretty recently which built upon the idea of Pong by making it a lot more fun hopefully and so that was the challenge making it as a hobby I decided to you know go deeper into programming as well as design so it's trying you know crazy things like that so I think now I'm going to do one step further that and actually do a more complex game than I did with Pong so we have like a lower benchmark which is what I did in that case。

And we can build it on top of that on top， I mean we can build it。

We can do a new game based on the skills I learned Okay， so I'm going to show you the game。

For a little bit。Okay， so the idea is that you play with both hands。

You control them with both hands and the goal is to not let the ball score a goal。

 so it's kind of the opposite of the normal goal。And then the game modes change。

As you can see in this mode， I'm getting closer to one another， so I have less time to react。い。

So that was the spirit of the game， I tookong and then did a lot of。这块。Game modes based on that。

 Okay， I can see if I can。🎼That this is。And if I catch like balls with a lot of us。

a lot of movement and velocity。It's actually a。I score more points， okay， this one's kind of tricky。

They kind to to here in the bottom， which is good as power。

I only have to worry about one you at time。And you can kind of control the direction of the ball based upon the R speed。

 okay， this one is strictly inverted controls。Okay so as you can see， it's a simple game。

But it was good all using C and we're going to。You know。

Kind of based our ideas on that as a minimal level。

 but I think you can experience making more things like。Bit mapps and it thisuse is like async。

🎼Audio and that was pretty cool we're going to build so so this is kind of the idea that we're going to build but more complex in terms of design and in terms of programming。

Okay。Yeah， lose now yeah I just lost I had to let one bulb go through so if you found that interesting you can download it for free on HI and check it out。

😊，Okay。嗯。Okay， so that's what we're building so we're going to build a breakout like kind of game we're going like we started with Bong and then built upon that in game design ideas。

 we're going to do that same with breakout。 we're going to start with a breakout clone。

 then I'm going to do some pretty interesting game design things I think。Okay。

 but why are we doing this okay so we kind of got the idea from what I told but to make it more explicit。

 we have three goals in mind the first one is for me to learn more things about programming and game programming and so I'm going to challenge myself to do no more interesting things。

And the second goal is for you guys to learn because I was very grateful you know that I could learn with so much things。

 you know， through the internet， but most of the things I learned is kind of a very know complicated things in terms of it was hard to get started that that was the main point。

So I'm going to do a super game and it's going to be easier for you to get along even if you don't understand like a lot of programming。

Although this is not going to be a tutorial per se。

 this is just going to be in least programming and talking about what and why I'm doing the things I'm doing。

And the final goal is to have fun。And of all of the decisions actually that we take is' going to be based off these goals。

 for example， why are do we're going to use the C programming language as opposed to like C++ or stuff like that。

 well because I think C is more fun than C++ as simple as that because C++ is really complicated I think。

And。Yeah， I kind of I really got along with C， so that's what we're going to use。

Another thing that you can think about is why aren't we using a game engine if it's going to be easier to deal with a game like that？

And that goes pretty much through all the three points。

 you know it's way better to learn by building yourself the whole game and engine so you understand the whole process。

 you know， I've built games with most engines， commercial engines like that。

 and it's really a different process， you know when you're building with a game engine you're mostly searching for solutions that people already came up with for specific problems。

Like oh how do I do that this engine and things like that how do they want me to do it right but in this case it's actually we come up with the solutions to the problems that we come up with in terms of design so I think we have more freedom in this sense so you're going to learn a lot more and it's also a lot more fun so you're going to be constrained by your skills and we're going to try to improve that。

Okay， so that is。Though what and why we're doing， the how how we're going to do it。

 so I have the Visual Studio compiler installed I'm using Windows here。

 so in this command prompt you can see that I initialized you know the Vi Studio a developer command prompt。

So I can know UCL， which is the compiler， we're going to compile it using that。And。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_5.png)

We're going to， I'm going to use forcodeder as a text editor。

 but you can use whatever you want if you want to follow along， things like that。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_7.png)

呃。Okay， and the basic idea that we're going to do let me just pull over paint here just so we can draw some。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_9.png)

Thats my， okay， so first thing we're going to do is a platform layer。And it's going to be W 32。Okay。

 we're going to do this simple things like how we're going to do the window。

 we're going to do the input， we're going to do the rendering。

Just for us to have a playground to experiment with a gameplay， which is the first part。

We're going to experiment with the gameplay。We're going to build a breakout clone and then start you know doing some semantic compressions。

 see what works and you're going to see that's a very open kind of development we're not going to do like very top down I'm going to just play around with it and see what is interesting in terms of programming and in terms of design。

So after we play around a little bit with the gameplay， we're going to do a more robust。Engine pass。

So we're going to start doing bitnps and audio and things like that， multi threadreading things。

 just to make sure that all the ideas that come up when we experiment with a gameplay will be able to be expressed through the game engine。

And then we're going to do a more gameplay。惊佢。We're going to do a more focused gameplay stage at this point。

 we're going to create ladders different ladders to see that I have a lot of ideas and maybe you guys will be able to come up with ideas too。

And then at the end we're going to do a Po pass to publish the game so if you download the other game that I said as a benchmark。

 the 200 pound on HIO you can go Dan Zd。hi。h。o you'll see that's a single executable and I put all the songs inside that executable you know it was compressed using Vus do OgG and things like that and。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_11.png)

He had all that stuff we're going to do in the polish pass， which will be able to you know。

 do like an asset cooker and do a profiler。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_13.png)

To see where we can optimize。And yeah that's the basic idea。

 So now we're going to start doing the platform basic layer with window input and rendering things okay。

 so first of all， I'm going to create a directory I'm going to call it this breakout。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_15.png)

Just be easy to remember。诶。Work out and then I'm going to。

 I have I created an empty repository here SVN， I'm going to check out that repository。

Let me just get the link here one second。And you guys will be able to download the source code too。

I'm going to create an HIO page for this game and I'm going to post each stream。

I'm going to post the。The progress， so you guys will be able to download and。

Follow along and add to the game and have fun too， know programming。Okay。

 so I have here N repository and now let's start your name， I'm going to open four coder。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_17.png)

With the break count。I'm going to create actually another photo， I'm going to create a code photo。

 right usually。I can do that， okay。Breakout code， okay， I'm going to create a win 32 platform。

Because the way I usually structured platforms basically the way Casey notatory taught。

 which is the game as a service to the platform layer。

 so the platform is going to do whatever it it wants and then call the game like to update and renderr。

 that's it。Okay， so the first thing I'm going to do is just to make sure that the compilation orgs and everything's smooth。

 are're going to do a simple hello world program。I'm going to do actually a hello sailor。Saailor。

Okay。Okay and how I'm going to do this， so I'm going to use the CL command line prompt。

 but instead of typing it all the time， I'm going to create a batch file。

And if I call this bed file build。B'ill got that here in the far codeder。

I can call it by pressing out M。So I'm going to do like C132 platform。That's see。

 so this is the very basic thing。Okay， so if I do that andll see that I created the file and if I go here inside the code folder。

It created the executable and the object model。But I'm going to organize this a little bit better。

Andm going to。Turn off all these messages and pass the node logo。Flag and the debugging flag to。

To it okay， so this is the basic things that we're going to do after going we're going to drop everything in the build folder too。

 maybe I can do this。I'm going to create a build folder here too。

And then I'm going to push the director。The build folder。And at the end。

 I'm going to pop the director。Okay， we're go back inside。Cold。So this way。

 all the build files will go inside the build folder push directory。Okay。Okay。

I have to go back a folder。Okay， that's it so now inside the build folder I have the executable so if I try to run。

I have the hello seal Okay， so this is the basic setup we're going to do and。

Now we're going to start actually doing the game， so to build a window in Windows。We're going to use。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_19.png)

A couplele things first of all， I'm going to search for MS SDDN a Win Ma because we don't use main to when we're doing graphical applications inside of Windows。

 we use Win Main。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_21.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_22.png)

Which is this call like here， so I'm going to remove the main。

 I also going to remove the SDDIO and do the windows。The age。Okay， so this is the。

Entry point of our application。Okay。😊，Okay。So you can fix that later。And let me see if compiles okay。

 looking good。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_24.png)

And the call we want to do to create a window is to create。Window EX。MsdN。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_26.png)

Okay， so this is the basic thing we want to do to create a window and returns a window handle。Right。

And I'm going to try not to copy a lot of code from my previous project just so you guys can follow along a little bit better。

 maybe at the end'm going to get some more complicated things I'll do it but。At the beginning。

 I think it's nice to do it by hence it' going to take a little bit longer than you used to if you guys have like a reference project which also it's okay。

 so I'm going to create a window and this is the things that it's asking。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_28.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_29.png)

Asking for extended Windows styles， and I think we don't need any of that in terms of extended Windows style and a class name。

 okay， so that's the thing before creating a window。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_31.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_32.png)

We have to create a widow class。That's how。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_34.png)

We knows structure things， so we're going to create and register。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_36.png)

A weo class。All right， so this is it。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_38.png)

We're going to。Register class and I'm going to pass a。Wind class A。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_40.png)

Okay。😊，No class。 and let's see what。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_42.png)

This structure is made up of a lot of stuff， actually。But most of， it's going to be。Z。

 so I'm going to initialize it to zero。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_44.png)

Okay， the style。We know clients got style。啊。I'll see our options。Clas styles or right there。Okay。Yes。

 we're going to have to do。At least。Yeah， we're going to do H redraw， stands for horizontal redraw。

 and we're going to do vertical redraw。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_46.png)

Because we're going to do the painting by， we're going to do software rendering for this project because it's simply enough。

 it's educational and it's a lot fun， it's a lot more fun to debug software rendering where you can see exactly everything that you're doing and instead of a hardware rendering which is。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_48.png)

かきける。Okay， so this is what we need。In terms of style， okay？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_50.png)

Class name。The class names were we have to pass to the window。The great window， Okay， so it's called。

LP class name。I'm going to call this game。To those class。Okay， and we can pass。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_52.png)

Class name now down here too。Okay。The windowow name， Okay， now I'm back to the。'Sorry， I confused。

 okay。And。This is it。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_54.png)

We don't okay we have the window procedure because the way it works on Windows that we have callbacks all the time for the window messages。

 so window class， we have to create a procedure。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_56.png)

Specified like this。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_58.png)

Okay。And this procedure， we're going to pass it as a pointer here and this is going to receive all the the messages。

 the main messages， we can also you know peak message you we'm going to do that for input。

 but we have to do this okay so I'm going to create。A procedure I'm going to call this。不许考好 back。

Okay。Okay， and let's just see how we're doing in terms of。

Come highly just to make sure that we don't have。回来了不来。A real definition。Return。Allright。

If window Proc eight。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_60.png)

Which is what we have to do。Two a few arguments for a call。

 we have an example here if I'm not mistaken。Of。For winter Prague。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_62.png)

Yeah， I think we got it wrong， we got people from the wrong place。

This is the procedure that we want to do closely。Yes。😊，We no call back and it has all of these。

Craranmers， okay。Okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_64.png)

Okay。And then we're going to。To do as a default going to。

Call the default Windows procedure that's going to make it maximized properly。

 you know and all that stuff without us having to or too much so you're going to pass you know all the four things that we receive here so you're going to press。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_66.png)

The message。TheW。要。Tam， that everything name goes just to be a。S。We know。啊数去。W you correct。And L for。

 okay。And lets see where we're at。Yeah， so we got the name wrong。Because a copy from the wrong place。

 this is the correct name。Or the class name， and there was no procedure， okay？Yeah。

And then we're going to do here as well。Okay， so now we're specifying the window class。

Eric wants us to do okay， and it has a linker error because we have to do user。32。lib。

The thinker okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_68.png)

Okay， so we're progressing。 Let's go back and see what we're missing in the。诶。In the window。You know。

 we know class。Strucd。Okay。Extra， extra instance， I think all these can be zero。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_70.png)

Yep， I'm going to try doing all of this。This for。To start with。All right。Okay。

 then I're going to register the class。We' going to test this do window class。The pointer。呃。Okay。

 and then we're going to finish。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_72.png)

Our create window。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_74.png)

We don name。I'm going to call this break count for now， maybe you're going to find that。

 come up with it。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_76.png)

More interesting name later on。Okay， style， this style is always tricky because we have to。

To quite least they're visible。Style， at least。And I'm also going to do the overlap。We know。Stking。

OverOver window， yeah。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_78.png)

Over left window。And okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_80.png)

Let's see what else。X，Y， and with high X Y， I'm going to do the default。If you're not mistaken。

 it's the yes CW US default， so we just will know see the best place for I'm going to do 128 by 720 for now。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_82.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_83.png)

Then we can do a full screen later when you do the。Other path。We no parents， no parents， no menu。

These， I don't think we need any of that。So， it's going to be。zero肉 zero zero zero。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_85.png)

Okay， let's see what we have。I'm going to try launching。The build。

Okay and yeah you guys can see right there's a window it's fucking up really fast that's what we wanted for the time we created the window it's not much cold and you know it's like the first time we're doing this right because they could could have copied it from another place and okay so that's start。

now we're going to a loop。Forever， basically。啊。I'm going a， I'm going to create a global variable。

It's going to be aesthetic。It's running。Actually， what I'm going to do is I'm going to define like true and false。

Just so it's easy。And then we can type de。Bll and stuff。呃。

We're going to type F hint we call it being 32。For booleion， so we can。

You can also do a define for static because static doesn't mean much to me。I like to define。

 you know。Global variableable。Variable。Anthe and also do a like internal。

Or whenever we were using that。Internal functions like static functions。

 because we're going to do a unity build， we're going to build everything in this file。

 so it's way easier in。That's complicated， Okay， so now it's a global variable low running and the default is false。

Actually， the default is truth， right？Okay， true macro redfin。Does Windows haven a tool already？

I'm going to drop windows all the way down here。So that doesn't matter。I'm also going to pass。

I think it's LCC。That it wass not L。It's a LD。No， I'm going to cheat now and I'm going to see that。

The puns code。ACompr flag， because。If I don't pass the full path here。

 I can actually just copy this reference that I usually use。It's pretty useful。

 It's just a comment of。The most common compiler flags。And。Gs Fc full path on Earth。

 so see that the path is just relative， so four quarterder doesn't earth stand that。If I pass。F here。

Now I can definitely see that this is a problem and just because I。

Tle and nothing to do with windows。Okay， expected to follow。Is there a same color here， okay？

Now we're going to do a while running。And this is the main loop of the program。

That basic thing of input simulation and render。That games are structured。

 that's what we're going to do for input， we're going to create a message。And I'm going to call。

Peak message A， which is good because we opened the wing user。

h so we can do like autocomplete home windows those functions。

 I'm going to do a peak message and I don't remember what it requires so I'm going to search the documentation of a SD effort。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_87.png)

Okay， let's see the message as a pointer， the window and the futures。

 I don't think we need any futures。嗯。About0。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_89.png)

Yeah， that's what I'm going to do， and then I'm going to remove the message。

So I'm going to pass the pointer to the message。So window，0，0 and remove。Okay。Yes。

 so that's the idea so for every message we're going to see type right we can do a switch。Actually。

 we don't actually need to do anything here from now。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_91.png)

Except pass it as the。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_93.png)

As to adhere to the callback， if we don't manually do it， we're going to use the translate message a。

 right？I think it has the message。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_95.png)

And。And's see if there's an example here。嗯。Yeah， there's the exam message here。Yeah。

 dispatch dispatch message， please。those are the two。For instance。

 so this is the basic thing we're going to。B Cor get message， right and then。

We're going to do the input here in order to get that。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_97.png)

We've got a callback and here we're going to do the translated and this message。Okay。😊。

So all the messages are coming through here， okay， so now we can treat them。

 we're going to do a switch on the message。And in case， it's like a WAM close or a WM this tro。

We are going to set running。To house， okay。And then I can actually create a add result here。

Can I do this as a？Which means aesthetic。呃。The results is going to be zero。And then。The default case。

It' going be this one。Okay， then I return results。Okay。

 looks good now we should be able to actually close the window。

 make it full screen all that stuff because we're going to keep you know reading the messages。

In the main loop， in the infinite loop。And here， the close and destroyed message will actually stop the game from running。

 going to turn the running to false， and then it's going to stop。That's the basic idea。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_99.png)

Let's see what happens when we catch around the game， okay， so we have the window。

 we can move it all right， we can make it full screen。We can change the size， minimize it， and close。

 okay， and if you go see the process in the task manager。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_101.png)

It is not running。Okay。So this is the basic thing we need for a window to follow about now we have。

Everything we need to get starting the game。So window is done， now we need to render to that window。

Okay， and we couldn't know create an open GI context and all that stuff。

We're going to do at least for now software rendering， if the games get a little more complex。

 we can do hardware rendering later through OpenGL or direct act。But for now。

 all we have to do is get a buffer， let me you guys understand。So this is what we need。

 we need a buffer， which is basically some memory。You to can draw to。Okay。

 so this is the Windowsows part， it's going to give us the memory。

And the draw part is up to us up to the game。So we can do like pick some independent drawing or you can change based on the screen and we're going to do all that stuff。

Okay， that's the buffer。That we need for the memory。

And we Emma need to see Sa2 Windows views the buffer。Like draw to the screen。

 And this use the buffer， we can use like the stretch， stretch。The IBS call。

 which is our starting point in order to look at the documentation and that's the renderry。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_103.png)

All right， so let's go here and' going to see this documentation for a stretch。PI bits。

And if you guys have any question， you know， can just。

I'm looking at the chat here so you you guys can ask any question and hopefully I'll be able to answer them。

Let me just see here if I can see the chat properly and not。You know， I I think I can see it， yeah。

 okay。So this is the call we're going to use to tell Windows to use our memory and put it on the screen。

And there's a lot of stuff but you can see that's not。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_105.png)

Pretty。Common things Okay， so the first thing we need it's called it HTC。

 it's a handle to a device context。 So the way windows work in terms of drawing using a。You know。

 the old libraries， you know， like GDI and things like that。

It uses device context to reference to what I'm going to draw to。

We just created a window here so we can do a GT DC to get the device context of that window and we can see it。

Variable a handle to a device context now this we can only we should only do it once because we only have one window。

 so if you pass that here we shouldn't need to do any more work。

I'm going to have zero thats for now just to make sure that are。I'm compiling me。Hey。

 I see a lot of new people in the chat。Nice。I'm going to do a endy few。Okay。

 so see so I got the device context here， which is the reference that we need for Windows to to tell it。

 okay， draw use this to draw draw in this window， okay， so that's the device context。

 the destination X and y is going to be zero and zero。And the destination width and height。

 we're going to have to save that because the user can change the size of the screen right so we're going to have to say I'm going to call this width and height for now。

But we're going to do a little bit more a structure thing。As well as the source X and source Y。

 we're going to do a straight copy to the buffer so we're going to keep the buffer exactly the size we need。

 we're not going to do like an off screen buffer with a different size and then downscale things like that at least for now because we won't just get started and focus of the gameplay right so we have to do the minimum to get it up and running。

Okay， so that was the and the first and height， this is the pixels remember when I told you that we need a memory and give that memory to Windows。

 this is the memory。I call this memory。And and then it needs a bit info。

 and that's the little bit of a。The not so fun part。If I go to the documentation。😡。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_107.png)

And go to the bitnet Efo， we have to fill thisstruct。Which has an bitmap info header。

And then we have to fill all this stuff with the size and they have to do the planes and compression and what kind of color we use that's the more。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_109.png)

Andind about the more elbow grease part， okay， so let's assume we have to give map info here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_111.png)

All right， and the usage of the stretch DI bits。呃。ok 啊。Specifies whether。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_113.png)

Okay， yeah the usage is RGB colors， yeah I was confused that for a moment。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_115.png)

And now we have the final thing is what are we going to do with that buffer？We want。

We can see the rest operations that it has for us。We want to do a copy， right， a source copy。

 we're going to copy from the source， which is what we're going to give in the memory。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_117.png)

To。The actual buffer that Windows uses to put things on the screen and then it's going to send to the video card and all that stuff。

Okay， so that's the basic idea now I have to fill all those variables， right？Right。

 and I'm going to create empty ones just to see if we compile。

 I'm going to create a width and height here。And we have to create a memory。

And we have to create a bitmap E。Okay。Take out that int。Cannot convert， okay。

 we have we passed as a pointer to a bit code。Okay， that's it， and we also have to tell the linker。

We have to tell the linker。To。To use the GDI。32。 lid this lid is the one that we use for。

For these kinds of operation， for software kind of operations in terms of renderry and just。

Since we open the build here， I'm going to copy this if there's no build directory。

 create a build directory。And delete all the old PDBs and stuff。Because。

Because I think it's way better。Uh to you know， have the system to create the directory instead of have to manually do this and then I'm going to delete。

The files that we don't need like。This temp that we get this information from and the object file。

And then later we can do more things like。Saing Cmano no。

And don't put like unused things on the exact circuitable。

But we're going to do that one step for a time， okay？And now we have to feel those。

 since all those referred to our buffer to our let's say raining buffer。

 I'm going to create a stroke for that。Im want to call this a。Reer。Bffer。It's going to have a width。

And a height。And then I's going to have a memory I'm going to do as a。Unsigned 32 bit pointer。

I'm going to call it this pixels。We're going to have to create these types here in a moment。

And we have the dipmatap heho。Okay， and since we just created all these tech appss。

 I'm also going to do。Going to include。SDD。It。That age， I believe that's yes。

 and then'm going to do type death。I believe it's int。In 32 of the score T。I'm not mistaken。

The semicolon here， yes， okay。So I'm going to do a unsigned two。Now let's see the problems， okay。

 the problems are solved。So I'm going to just quickly do。All the rest you going to do the8 bit。け的。32。

 a bit。It's going to be 16 bit。Thank you， and this is going to be the。Okay。

 and actually this thing I'm going to。I'm going to make our first actually file I'm called。Utilities。

 Ps or utilities that seat。Just so we can。Just so you can you know organize it a little bit so if you do like multiplform things this part of the code can be used for all the platforms。

 we don't have to we don't have to keep this in the Windows specific file。O。😊，ok。呃。

Now we're going to create for now， at least as a global variable。Our render buffer。

I'm probably Sper Bford。Okay， and then I'm going to do the render buffer doive。

And the same things for the height。Memory， we call it pixels。And the bit。Hefo to， okay。Okay。

 bitmap infoflow， I think I just call it bitmap。気持ちい？I'm going to go back to you。Okay。See。

 performing full link， this is the things that we should。Improving that build that bat。

Because since we're doing a unity build。We can pass to the linker。The incremental no。Flag。Let's see。

Pass。这可以。呃。Okay cheat。See。How I set up the。The linkquor flags。cr。Yeah呀。Oh。

 we have to pass before the lips。That's it。I'm not sure why it's okay。Yes， okay。

 Now I'm going to do opt graph 2， just like a。Here don't put useless things in executable and the other things we're going to do as time progresses。

ok。Now we are looking good now all it have to do is fill this。

Thing with this structure with useful structure useful data and this is in the case of a change in size of the window and this is cool because this is going to be called when the windows created。

So we'll have to initialize these variables elsewhere， we can do everything here。

And the basic idea is to get with。And height。😊，And then allocate。And of course， you know fill。

The bitmap info。Okay， so these are the three things we need to do here。

And now when we pass should be good to go。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_119.png)

I'm not sure what's going to happen if we try to run， yeah nothing。

 I suppose that maybe we should have like a black screen， but we're going to get that in time。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_121.png)

Okay， so to get the width and height。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_123.png)

I'm going to go back to MSDN， we have to get。We direct。Yep。And we just passed the window。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_125.png)

And erect pointer， so I'm going to create erect。Right。That's correct。

And I'm going to get to interact best in the node。And the pointer to erect。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_127.png)

Okay， now direct。Has a top left， right and bottom。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_129.png)

So the way we're going to do the。喂。It's going to be direct。Dot right， minus the right， dot left。

And the way we're going to do the height。iss there个。

Now I don't remember it the bottom line is the top。Or the other way around？

Okay now maybe a good time for us to start debugging our program。

So I'm going to do this I'm going to open。Visual Studio with Devin。

And I'm going to pass the executable as a parameter。Gev and okay for development environments， right？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_131.png)

And then hopefully we'll be able to just adjust the size of the screen here。Okay。

And now we should be able to step the code with F10。Okay， maybe it's a bit too big here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_133.png)

Okay close， okay。Nice， I'm going to put a break point here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_135.png)

So when we create a window， this is called。And then the right。

 these are the values as as the bottom and the top so the width。

Can you guys read the toe tip maybe a little bit too small？The width is 1280 and the height 720。

So this is the basic。Set up we need， okay， so we got the window。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_137.png)

The window size， width height， all right， now with that， we can allocate the pixels。

We're going to have a uncir to be the integer for each pixel。

So this is how we'm going to do if we have already。诶。哎や。

If you have already allocated at Texas previously， we have to free them。

Because the user resized the window and then now we can allocate again since we don't expect the user to keep changing。

The size all the time。Of the。Although we know we can actually do this allocation。

 even though it's going to be a little bit big depending on the resolution。Hey Nikcolai， yes we can。

 I'm not sure the context of what you just said maybe I was in doubt of something。呃。Yeah。

So to allocate， we could use MalEC and free， which are the standard C library things。However。

 since we are in the Windows layer， I'm going to use。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_139.png)

The virtual alloc function。Which is good for allocating a big chunk of mammo。

 which is exactly what we're going to do。And。Yeah， this is what we need， we pass the address or not。

Of the memory we need remember that's just a virtual memory right size。

 what type of allocation we're doing and if we're going to protect that memory or not so the basic idea is。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_141.png)

And it returns the boy pointer。 So what we're going to do is a。The renderer of dot。嗯。That pixels。

Because the virtuality so I'm not going to as an address， the size is going to be a size of U 32。

Times the width that we just calculated。Your reminder buffer talk with。Times are in buffer。he。Okay。

 so this is the size。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_143.png)

And the allocation type， we're going to do both a commit and a reserve， right？

Because we're going to commit the memory and start using it。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_145.png)

What type of a game are you coding， okay， so were going to start as a benchmark。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_147.png)

We have this palm game that I built a couple months ago。And it's a very simple game。

 let me just show you。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_149.png)

I'm going to show you the screenshot， you can go on HOdazam。

H do IO and see this is the kind of a technical challenge that we're going to face maybe a little bit more we're going to do bitmps too。

 but this time around we're going to start with breakout as a base for a game design and we're going to start creating all these crazy ideas on top of that just like this game I created a lot of crazy ideas on top of P so we're going to do like a breakout clone to start with。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_151.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_152.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_153.png)

And then we're going to do interesting gameplay things。

 so this is the plan we're going to do the platform stuff that we're doing we already done we already did the window。

And we're working on the Rary， which is not going to take a lot of a lot of time。

 and then we're going to do the base gameplay， which is the fun part right we're going to do the。

The Bout colonists are playing around with some ideas。Yeah。

 breakakout is pretty a pretty interesting game to make you know someone just said I may breakout this semester breakreakout is a nice game to program but the challenge I want to do with this version of breakout is you want to go beyond the know just you know you destroy the blocks and things like that and you' going to start giving like more behavior to the blocks like they they move certain patterns or some behaviors and they chase you and things like that you know that's the basic gameplay craziness。

 this is the gameplay craziness so after we do the basic gameplay。

 we're going to do a more robustness pass on the engine making it a faster and bitmap support and make it a audio and multithreaded audio or things like that。

And then we're going to go back and finish the gameplay with all those crazy ideas that we're going to come up with in terms of making the breakout。

 which is that simple game that people are used to。

 but making it more interesting and then we're going to do the final polishcast so that's the plan。

And I'm going to guess it's going to take like one or two months of development。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_155.png)

This is like my free time and streaming is's my first time streaming it's going to take a toll in my productivity。

 but the point is to learn a lot both you guys and myself and also have a lot of fun。

 So that's the point and。😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_157.png)

Yeah， we are finishing the call， we did the Str DI bits call。

 which basically tells that we knows that we're going to。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_159.png)

Display that buffer， that pixel buffer in the screen Now what we're doing is that we're getting the buffer using virtual aoc。

 so we're allocating this size of a buffer。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_161.png)

And the good thing about virtual analog， let me go back to the here is that it also zeros the memory by default so we can test like a black screen。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_163.png)

Normal resistance and bonus block， yeah， that's the thing you know that's the interesting thing about programming and game Z that I find most engaging is that you start out the simple idea and then when you start doing it you come up with more ideas like you start doing new blog and maybe oh。

 what if the blog do different behaviors and things like that？

And I think that's the most engaging thing， so we have to you know get off the base for us to experiment with the gameplay and then dictate what we're going to do engine R which is a lot of fun Yeah it is Hemi heroro 2。

0 because Hem here is a lot of it's pretty much where I learned to program。

But the scope of this game is way smaller than he hero， first of all， because Casey， you know。

 it's been programming for more time than I've been alive right。

 so he's a lot more experience than me being a professional game developer for a long， long time。

 so he can take a bigger game as a scope， but this game is going be really short in terms of。😊。

Programming challenges just for us to release and you guys can see the whole process of getting the game published on HIO from the very first line of code that we're doing today to the  polish and the game played crazy ideas in the audio and things like that。

 so it's like kind of a smaller handmade hero like a hand heroro light version and then we can do like bigger projects you know 3D and with lighting and all that crazy stuff that Ca has been doing which is I think that's the biggest compliment。

 handmade heroro to point0 you could give me。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_165.png)

Okay。So then reserve and then commit and then we're going to。

I'm not sure we need okay yet the protection。So let's see the protection， I think's just like me。

 right。呃。ToRead。Execute readw write， okay， we have a page readwr， that's what we're going to do。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_167.png)

Okay。Let's see if this。Compileles， okay， nice。 And now if we do have a buffer already。

 all we're going to do is the map free， the the virtual free。Virtual free。Passing the pixels。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_169.png)

And I don't think there's any more parameters I do， oh yeah， actually I do。Virtual free。Yes。Yeah。

 I think that's zero as the size and then a free type。I can do a ma release。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_171.png)

Yeah。Okay， so if I test zero as the size， it you know frees the whole block， Okay。

 so this is the basic thing that we need now we're going to have to fill the bitmap in。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_173.png)

And if I'm not mistaken， most of it is。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_175.png)

Not very interesting for us。Let's see啊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_177.png)

Genator B Gnetapp。Evo doheader。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_179.png)

Let's see exactly， yeah， BMI header。Because that's how its specified。

 so it does have a long chain of strokerubs and tests。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_181.png)

Okay， the size， you have to pass the size of the Bimap header stroke， right？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_183.png)

Yeah， it's kind of weird。Just for them to check out the version so they ask us to do this。Okay。

The width and the height we have just calculated。Okay， just。

The width's going to be the render buffer。Talt with and the rendered buffer。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_185.png)

Dot height。Okay， planes， I don't remember if we need planes。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_187.png)

Must be set to one， okay？If that's the case， I'm going to add it to one。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_189.png)

A bitit count， yes， the number of bits。Each of each pixel yeah， I'm going to do four。嗯。Actually。

 I think it's 30 A， I'm sorry， 32 bits。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_191.png)

I don't know what I thought there。32 bits per pixel so that's what we allocated here。

 that's what we're specifying， okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_193.png)

And okay， with count compression， we're going to do no compression， which I suppose is RGV8。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_195.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_196.png)

Okay， and the size image。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_198.png)

This may be set zero if okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_200.png)

If you see can't be set to zero， just set it to zero。

 that's basically my rule with Windows documentation per per meter。

 we don't use that to keep it as zero actually free。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_202.png)

Since this is on the global stack， I'm going to obviously the global variable。

It's already initialized to zero， so I don't need to set it to zero。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_204.png)

Right， so。Control used。I don't think we need that and they important okay。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_206.png)

So I'm going to try and do that。Bip met if is not a member of。Oh， we did underscore you。Okay。

 now I'm not sure what's going to happen， so we're going to step in the deder just to make sure。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_208.png)

That nothing explodes。Okay， so the width and heights is as we expected。And we should have no pixel。

 so we're not going to free。Okay， so if I if I calculate。あ。Yeah， let me just see。

Pixels so we do have a bunch of memory。And it's zero， so we can do all the things we want。

 so if we display this name， we expect a black screen at this point。

Let's just see what we see a size of thestruct， okay with height planes to one， day counted 32。

 compression2。The R toB， which is zero， so we could just do nothing。

So let's see if we have a black screen， we do have a black screenen。And if you change size。

 it automatically allocates and des， let me put a break point here。

 so I'm going to put it a full screen， see so it stopped here。Because we do have pixels。

 so we're going to free the pixels。And then'm going to allocate the size， as I told you。

 since we don't really。We don't really expect that players to keep changing the size of the screen。

 like at all， we don't care about having to do all that stuff again and allocating things。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_210.png)

Okay。So that's it。 We have the base for our rendering and our window Now we should be able to create our own rendering functions to like change color and do pixel of things Now it's going to start being interesting。

 you know we're going to exit the Windows part I're going to create a new file I'm going to call this software error。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_212.png)

没点。😊，C and as I told you， we're doing a unity build， so all of the files are included here。

 so I'm going to include the host C file。呃。小出。Rry。D see， and for now。

 we're going to have a basics function。 I'm going to do a。Eternal void clear screen。

Screen andm going to receive a call。And'm going to set all the pixels of that color and so this is the doubt。

 maybe we should pass。The Rainer buffer as a parameter， like where do we want a renderiner to？

However， I think it's going to be better just to。Have these as a global for the game as well。

So this is going to be the W32 Rainer buffer。And I'm going to create。A type de。Ga Rainer buffer。

That the game is going to access。Or not， I'm not sure。Maybe for now， I'm just going to。

Comment is like platform。啊。Nonspec。Okay， and this is the platform。To that form。Okay。

 so we're going to use the Ragraph as normal here as the supposing we only have one in the global。go。

Okay， did I do late？Acccidentally。然好我。Yes， it became did。Yeah， I don't know why I did that。Okay so。

This going to recon it。Gner buffer。All right， here we go。Now clear screen， what we're going to do。

 we are going to get a pixel， right？And we' going just set it to the pixels in the Rer buffer。

And just as aclaim， if we find out that this is a bad idea and should。

Do a little more organized thing， you can， you know， this is not like headstone。

 this is the first version。And， and now we're going to do A4。We're going to do for each pixel。

 so let's call it， let's do it for y first。W and Y render buffer do height。Quiet was close。

The same thing for the X。Okay。就可以。And then we're going to set the pixel to the color and increment the pointer。

 that's it。That's the only thing we're going to do equals zero。Okay， yeah， in this case， we should。

Have the softwareine after the globals。Okay， and now if we come here in the simulation part。

And call the clear screen。Passing， I don't know。Let's do a orange。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_214.png)

Hopefully we'll see an orange screen， I see， I'm sorry that was a yellow screen and it's not actually working。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_216.png)

To nice that， you only feel like about a little bit over half the screen。 Actually。

 we're setting a fixed number of pixels。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_218.png)

Okay。😊，呃。First of all， let's do it orange， just for fun。And。Yeah， because you do high twice， okay。

Copy and taste。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_220.png)

Typ okay， now let's see we have an orange screen， okay， now you can see the orange screen。😊。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_222.png)

And now I hopefully you can see that all we need to do now is to do like helper functions。

To draw you know player and player pixel of dependent things and things like that we're going just start with just rectangles to do the first gameplay part note and then we can。

Who can go ahead and do more of that。Bit map Mar polish King later on。Okay。I'm going to do a slide。

 a slightly darker shade of that。Orange just so it's not like super blindly orange。

And we're going to create more questions now， we're going to do internal void。D。

And for now it iss going to be in Dels， so it's going to be draw act in pixels。

We're going to pass the first position X。Deportation， why。

And then I'm going to do the second position X and the second position one。Okay。

And the idea is the same thing。Here we're going to start， we're going to have a pixel that we will。

你 draw啊。In this case it's going to be the pixels。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_224.png)

I'm going show you guys what I mean。So let's see we have a rectangle here that we want to draw。

 correct？The pointer is here， the pixelels pointer， right？And we want to set it。To hear。

How are we going to do that， the x offset just to add the number of x pixels that we start with。

 Now I could also call me an X， not sure which one's better。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_226.png)

So the Pix is going to start at the Minex。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_228.png)

Plus x0。Okay。😊，Now this is the first part and now the second part is to do the Y。

 since we're doing a per row movement here just to end here and then just increment a pixel again。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_230.png)

What I'm going to do is a。We you add your width？Which is a render buffer dot with。

Times the actual Y that we're going through， okay？Colllor and if I a， we're also going toic。Okay。😊。

It color。Actually，O。Now， if we should clear the screen and then draw a rectangic pixels。

 I'm going to do a 50， 50， 150， 200， and now we're going to do that yellow。Okay。

 let's see what we have。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_232.png)

Okay， we do crash， let's see， first of all。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_234.png)

Yeah， actually we did Ron， we started pixelixo correctly， but we have to do limited number of runs。

 right？I don't know why I just expect it to work， so it's going to start in the x0 and it's going to end in the x1。

Start in the y1 nm in sorry starting in the y0 andm in y1 net。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_236.png)

Okay。Now we see our yellow rectangle is the position correct？呃。I guess， I mean， starting at 50， 50。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_238.png)

Going to 150 to200， I'm not sure though， I kind of expected it to be。呃。The same distance。

Let's start here。Are using a program to code it up to， yes， I am using the text editor for coder。

 you can download for free， it's pretty cool。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_240.png)

On even for code each。O。Which I think is a great editor， very simple to use and you can buy。

 there's a paid version， there's also the demo version， which does everything you want。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_242.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_243.png)

But I am running in the。Visual studio because I know I can。Debug it here。

 so I've had break coins in run and all that stuff。So yeah。

 I use kind of these two programs and I do compile here by pressing。

 I expanded data a little bit earlier in the stream I press al M。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_245.png)

I run this batch script， I'm sorry， not this batch script， this one。

Which basically just set the compiling flag。A couple of combining flags and compile the code。So yeah。

 two programs。To program。I like this work for quite a lot。I'm going to do a。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_247.png)

A。5050 or 100 100 just to make sure that our other rectangle is in the correct spot， Yeah。

 I kind of expected。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_249.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_250.png)

A little bit different approach I'm going to use paint just to see。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_252.png)

If I'm completely crazy or not， hopefully you guys can see that。How many pixels is that。 Okay。

 so in the Y， I only have like 14 pixels。 and here I have the。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_254.png)

The somewhat 50 pixels。So yeah。Not working to well our code here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_256.png)

So let me just review quickly。We start off。In that specific pixel。Okay。And then， yeah。

 go to that thing。I'm going to try like 200， 200。5005。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_258.png)

See， now it looks correct。Yeah， I'm I'm also going to clip。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_260.png)

呃。We don't have a clam function as just see if。X， Y， or we can do a clamp。

 I'm going to do a clam function。 I'm going to create a math。Dot C file。

And I'm going to do a internal。Internal has the internal end clam。啊。Min， A， C， Val and。Its if well。

It's less than min。有ね？If fell。W在 next。And then in the windows going to include。假期ok。

So I'm going to do this guy equals clamp。And then I'm going to do zero。Hisse。And the。你的伟。

And then why。就会再海一。To do the same thing。With the X1。And。我爱玩。Now， we shouldn't you know。

We shouldn't crash if we get office game。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_262.png)

Okay。We are coming along， right？Okay， yeah， I do think it's great。

 I'm not sure why putting clothes here was a problem。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_264.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_265.png)

We can test it。More， you know， calmly later on， just excited to get things on the screen now what we are going to do。

Is just have a basic input system to be able to control this。

 I'm going to make it a little bit smaller， right？To be able to control this guy。

With our keyboard and then it's going to be more obvious if there's a problem or not， yeah。

 I do think there's a problem。嗯。Without our software rendering。With the Y software rendering， right？

Why starts off as a。买 zero。Thats than y1。My plus+ in here。Is the width times the y？Yeah。

 it does look correct。Yeah， okay if you guys do spot there make sure to tell me right。

 but let's focus on input， which is the last thing we need。

 we're also going to know make this a little bit better before we focus on gameplay。

 but making input。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_267.png)

Is the。K of the less major thing we need in the first version of the platform layer。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_269.png)

Then we can start doing the gameplay。呃O。Input now we do have the peak message here and we can do a switch。

On the message dot message， I believe。Let's see， yes。

 and if the message is a window message of key down。For instance。八。Ts it down。Let's see if that's it。

 okay。But we're also going to test the key up。Messages。アドリ。O。And in this case。

 we don't actually need。To run the default。就是。Because we want the input to be processed here and not taking the call end。

All right， okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_271.png)

Now， what are we going to do， We have to。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_273.png)

Have to get the specifics bit of the。Of the message here。Yes。

 I I love forcodeta for thatmorph yes the auto indent is crazy。

 I've never had to type a tab again and it's so much more fun to write this way and it's varies more I've never have a problem if if we do like。

😊，like if something。And then we want know to do in this line。

 it also indents the other one if we you know。I to go into the other lane need to dance the if。

If we open the the。No the curly brackets， so yes， the other dance is great and that's pretty much the main reason I love for COver。

It's called it like I think it calls it virtual white spacing， things like that。

And it works great and if we do open that in externalial editor like Vi Studio， it also it works。

 you know， it does have the actual spaces of inten so if people want to program here and have all sorts of hard time。

 you know。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_275.png)

Rein datingating things。They can do so。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_277.png)

If like you have more people in the T， things like that。Yeah。

 I'm not sure maybe someone did that in VIM， I don't know， but it's one of the reasons that you know。

 I stick with4 coder because。That alone， yeah， so much more fun to write okay。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_279.png)

So yeah， about the window messages that we're going to do。

 if we do look in the peak message documentation。We're going to see the message type。

And then we can extract the inputs that we are looking for。

 We have to basically see I'm not I don't remember exactly if it's in the W parameter of the message。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_281.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_282.png)

The VK code， let me see MSDN VK code， you can also do that。Okay， virtual key codes。Yes。

 let's see if there's a reference。就。Where it is used。嗯。Okay， for virtual key codes and WMS problems。

Okay， let's see an example someone did。Yeah， if we're going to see an example。

 we might as well cheat with our own code。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_284.png)

Yeah， I think I'm going to do that just for the sake of it。That interesting anyways。

So I'm going to open the palm code。呃。Okay， and I also add the system downs and ups for F4 and。

These other kinds of messages you you also do that Okay。

 so this is the three things I extract from the message the rest is my old code I extract the the VK code which is the W parameter of the message right and if the button was down and if it is down at the moment。

This is the three things we do need。The rest we going to write by ourselves。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_286.png)

Just for demonstration purposes， if you do like big message here。Dig message to the SDN。

 we should be able to find the message specification。I like message type。Yes， math is structured。

 okay。嗯。Yeah， I'm not sure where to follow documentation to to get exactly where this W prem got the message from and all these bits specifically in this。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_288.png)

Be an array is a bitfield， right？But the basic idea is now we can see which key was pressed。

If it is down at the moment like a key up or key down and whether it's released or not。

 so just for the sake of testing， I'm going to do a Boolean running。It would also have running up。

Charac。I'm to set it to false。And we're going to do if。The VK code。Equals to VK left ti。

We're going to do a vector because we're going to improve on that。Just to start iterating， okay？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_290.png)

Now。So no character， I'm going to press left and we do see the character。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_292.png)

And now we don't see the can turning him off anymore。

Because that's the only thing we do we just set it to true now if I press the button。

 I could set it to is down。Yeah， but the auto indent in VIM， if I'm not mistaken。

 it's different from this virtual white spacing kind of thing。

 like it automatically indents the whole thing I'm doing。And it works great actually， yeah。

 that's where I told Morus there may be a plugor in08。Add on things like that to them。

 I'm pretty sure there is to make it easier， but I don't know one that does exactly like this。

 it's kind of a crazy automatic thing and runs really， really smoothly too。Okay。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_294.png)

So now we're going to set only fits down。 Okay， now that's the basic functionality we have and we can also do things like get that the key up and key down。

 but how are we going to structure。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_296.png)

This input because now we have the basics of we need， we have the input。

 we have the rendering and we have the windows， the window right and now we're going to improve on that as well。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_298.png)

It's not not done for the gameplay， but we are going to do all of thequ， I suppose。

 so what I am going to do now is in our photo here I'm going to create a game dot C file and as I told in the beginning of the stream。

 the way I like to structure the platform layer is even taught by case meritory from Haman Hero。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_300.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_301.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_302.png)

Is that the platform layer， which is our Windows here file？This file。I'm sorry not this file。

This file， this file is the main file we compile and rules the。The program。

 let say let's put it that way and at a certain point here in the simulation， it calls it a game。

So the game doesn't worry about creating a window and doing all that stuff。

 saving the window and all the game wants to do is to get the input and tell you know the platform layers to draw stuff。

So that's what we're going to do， we're going to do the simulatelate gain here。And for now。

Just as a cheat， we're going to pass the input。In quotes right to the game。

 which is now just this variable we created。And the game can now do the。Simulate game。

 going to receive the move。Okay， and if to move together。With this so this is the basic structure。

 you know the Windows file can worry all that that can worry about all the the window stuff and the game can focus on the gameplay and I think it's a great way to separate these two。

Pracical， and we also have to add。The date file we're going to add after the software render。O。

Now we should have the same thing we had before， okay we do have。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_304.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_305.png)

呃。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_307.png)

And now what were going to do is。Focus on extracting the input more specifically because we want maybe we wanted to use like the mouse for to control the pad。

 the pedal in the breakout game， or maybe we want to deal with W ASD or the keys。

 but the idea is the same we're going to have a platform。他们。3来哦。

This is the specification of what a platform layer uses to interact with the game。 for example。

 you're going to have a input structure。That has， for example， the mouse position。Muse X and mouse。O。

😊，We're going to do a little bit of a better job with this in a couple seconds we're also going button。

That the game is going to process， so if you do have a button。But I don't know why I type buffer。

Okay， if you do have this button， it's going to have like is down。And。And I'm going to do the。

The trick of saving the half transition count。I'm going to explain this briefly。

The basic idea is we're going to know whether or not it was pressed or it keeps using down or if you know it's just down by using how many transitions。

Or half transition rate， which is from up to down or from down to up， it had on this frame。

So if the user presses like the button really fast and one frame he does like an up and down。

 we can see that processed。down。But he did up in that frame， we can do all sorts of crazy things。

 but I don't know we're going to get to do that we could just save a bullet and like changed。

Things like that。If we want to。Do a more simple version first。Which I think is wise。Okay。

 and I'm also going to do a an inum。I'm going to。It's going to be an anonymousony。

 I'm going to call this like button left。But。Right。Up and down。Okay。

 and I'm also going to do the button count。So I can here create a button array。

The second type button。Oh my god。发张。这块。O。So this is the basic idea now the game will receive this input and be able to process it as so instead of creating all this character thing。

 we're going to create an input。Okay。😊，And here， if the character is down。I'm going to。You would。

Dot buttons。In the button left。Dot is down， okay， it's going to be equal to is down。

And the happiness count is going to be， oh， I didn't put the I just put the。that changed。To true。

 okay。So this is the basic idea。Of。Of theWe can do like a macro here just be just to type less。

 but that's the basic idea of our input。And I'm going to try and see if the game can process that。

Okay， I'm also going to import that platform。来帮你看看。175。

Character and I'm going to pass a point to the input。And then the game。

 they're going to be a applying。And then here I'm going to test if。

We're also going to have macros to type less here， but the idea is。You put buttons button left。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_309.png)

Dot is down。Okay， let's see if we get the functionality back。Yes， the difference is it started。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_311.png)

Already started。He's down true for some reason。If it down。I'm not sure because， okay。

 I need to initialize that to zero。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_313.png)

Good thing we caught that okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_315.png)

Okay， now we have。Now， what we have to do？One more things that we have to change that changed。

To false every frame because the basic idea that we're doing just today for you guys to understand。

 let's see let's say this is a button， let me just draw a button here okay。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_317.png)

这是。Good looking man。呃。I'm going to type this in different states， okay， so it starts off。

UAnd then he presses it and then he keeps it pressed for a few frames。And then he releases it。Okay。

 we want to know at these point that it's down。And we want to know at this point that it was pressed and at this point it was released what is the game you are making。

We are just to get started， were doing a breakout clone。

So it's going to start you really simple just like breakout。

 but we were going to add to the gameplay a lot， just like I did to the Pong game and release on eachchi we can play that game here。

 the basic idea is that we have this， you know simple game arcade game people used to do like a p or breakout。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_319.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_320.png)

And that's the like the first part we're going to do in the gameplay， right。

 we're finishing this part， then we're going to do the basic gameplay。

Then we can do like crazy gameplay things later on right which is I did a little bit of crazy things in the palm game。

 but the breakout I really want to do like a lot just to get better at writing gameplay code so yeah it's going to start out as a breakout clone but hopefullyll be interesting but the scope it is pretty small I don't want to do like I don't want to keep doing this for like years and ears is not really the game the idea of this stream is to show you guys the process of making a game from scratch in C。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_322.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_323.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_324.png)

We know we started this stream with a node code whatsoever， and we're tagging every piece of code。

And hopefully by the end， after a few streams， I don't want to spend like a lot of time。

 we'll be able to publish that game and you guys can download this sports code and play around with it all that good stuff。

Okay。Now。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_326.png)

We we do have let just go back to the game。We do have the input。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_328.png)

Being being processed correctly by the game。But we do have to reset the change because that's the thing。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_330.png)

This。It's saying that it's not pressed， so pressed false， zero， not pressed， not pressed， pressed。

 pressed， pressed， not pressed， Okay， this is the is down， actually。

 not pressed is down is down false， false2，2，2 false。

And the changed tells us if there was a change from the previous stage， so there was no change。

 no change， there was a change， no change， no change。

 there was a change so we can see by this combination。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_332.png)

We can see like we can do in the game， the ideas to do things like this impressed。Button left。

Do this， okay？Or if is down。Or if released。We want to have this kind of expressiveness。

 you know if you say so in the game code and let the platform code worry about these specific details okay。

 so how are we going to do that we're going to save these two variables which is enough for us to know there was the problem though that if for instance he presses and release the game the button really quickly in one frame。

 we can probably miss that。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_334.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_335.png)

So we're going to oh we're not going to be this， we're going to probably do a wrong push so the idea later on're going to do a rough robustness pass is to change this from a booleium to an integer and see how many times this frame changed the state。

Okay， but we can do this for now， so we just changed this to true。

 we're already doing this when we do change， right？Actually， if it's down， it's different。

From the old is down， right， So if there was a change， we started changed to true。

 that's the basic idea， right？就是。Okay。The change words like this。

 but we do have to reset it every frame right because let's say there was a change right it was zero now it's once or we set it to true now we have to set it to zero in the beginning of the frame。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_337.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_338.png)

So when I start processing the frame， I'm going to。Run through the whole buffer， the whole。

Butom count。all the buttons。If for everybody button I'm going to change。

 I'm going to set changed to house， okay， I can even do it like this。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_340.png)

Now we shouldn't have any change。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_342.png)

Yeah， we don't， right？But now we could do things like。呃。If is down and。Changed。

 so this is the pressed state， right？

![](img/65cad47fe79d6d7fa64b4e5575d06d39_344.png)

Now we should only have， I think it's going to be hard to see， yeah。

 it's going to be hard to see because we are liking a thousand million frames per second。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_346.png)

Right now so。Yeah， I can change the position right， I'm going to do this I'm going to set。Pos。

T equals 20。P。😊，And if。It changed， we're going to set B to plus equals 2。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_348.png)

So。Every time I press the button。I'm going to move up a library。Yeah， see how weird that was。

 so yeah， our renderer does have a problem。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_350.png)

No， I guess I guess not， actually the。I should change both these guys， right？

So I'm going to do like 30 plus feet here， yeah。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_352.png)

It's not our array greens， actually our game code。Okay。So this pretty cool now you can just click。

To move the。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_354.png)

Like we're doing now， like if I hold nothing changes now， if I do the。If I remove this part。

 if it's down， now if I hold it， you it's going to be crazy， yeah。Okay。Now。

 as you can imagine this is pretty weird culture to right， we want it to be simple for the game。

 right but that's。Really easy for us to fix all we have to do that's seeing the platform column。

 for example。We have like a couple of macros here to pressedest。

And we're going to receive the button。And we are going to return this。Okay， pressed。Button。Okay。

 so this is the pressed。And we can also have a release。O。😊，If it's not down and changed。

And we have a is。Which is just if it's down。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_356.png)

Okay， that's the basic things we need to be able to do nice and clean input in our game。

 see how easy that was we've been streaming for like one and a half hours and we already have。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_358.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_359.png)

Like a very basic engine to work in our game， which is like great。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_361.png)

The input is great， we can also do these really quickly， the left right up and down。

 just for just for it。Fun of it。I'm also going to do a。Process button microki。A press。Buty。

 and I'm going to receive the UKK code。The button。I think that's it。And I'm going to。いです。

And now I can do like process button。PK left。啊不来。Did I do like。Right。I do up。And I do。

And then I change here from button left to B。And from PK to PK。可以。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_363.png)

Okay。Let's see if we still have okay I we still have everything thing now we can start actually doing the game code。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_365.png)

No， you can save like a player。X， right， it's going to start out， let's say third。

And then I play your why。If we press left。呃。Player P minus equals 10。

It's going to be a blocky movement for now。Right。Player plus equals this。そんな？Laer。Why。

Minus equals this。Play right plus equals。Clear X。Okay， so this is going to be player X。

It's going to be clear lot。This is going to be 30 plus player X。Its gonna be 30 plus。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_367.png)

Player right， okay。Let's see if you have a basic group。Okay， and we do have a basic book。

That's pretty cool。Okay， oh man， that's great。啊。See， even doing like a basic thing like this。

 like this movement。We can always think about all these crazy ideas， you know？

That's why I like doing it by hand。Okay， oh we're just adding every press and we can play around with this。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_369.png)

It changed like from trust。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_371.png)

To release。And I have a very weird movement where you have to like first press and bend when we release it counts。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_373.png)

Could I think about some games and ideas？

![](img/65cad47fe79d6d7fa64b4e5575d06d39_375.png)

Play around with this， okay。However， there's a problem。In our。

 before we can actually do our game play code。There is a small problem。Which is？

We are not picking dependent。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_377.png)

What does that supposed to mean， that means if we have a very small screen。

Our player moves quite dramatically。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_379.png)

1。😊，And if you have like a full screen， like a giant screen here。

 it takes a long time to improve the end of the screen， what we do want。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_381.png)

Is that if we have a small screen， the play is going to be smaller right and if you have a huge screen。

 the play is going to be bigger， so we have to focus on a pixel of independent render。

 that's the idea。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_383.png)

So how are we supposed to do that and that's not very hard actually when you think about it？

I'm going to do a internal void。A draw。Correct。And what I want to do actually。

 is receive a vector2 I we're going to see like a next。

And they Y as floating point variables because that's what I want the game world to talk about in terms of coordinates。

And then thenda color and a size， probably。So we are going to create this vector too。Ststruct。

 so it's going to be vector 2 P vector 2 half size， right， and then we're going to do the hole。

So the basic thing we're going to do here is convert convert the units。Two pixelel。And call。Dawect。

So that's what we have to do here in the draw。And in a math， I'm going to create our vector two。Well。

 not class strips， really。But it was pretty much the same。And for now， I'm going to do a union。Of a。

Anonymousstruct。Of X and Y。At 32 or we don't have app 32。 I was going to do that as well。

 And then we're also going to do a effect。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_385.png)

A array of two。two guys like this， this is pretty cool， I think。

Because we can't like iterate through that， we can get the number of elements and we can。

And do all sorts of stuff。By doing this evening， so they occupied the same space memory， right？

So yeah， that's the basic idea for that I'm going to have to here。Fities， nows。And we going to do a。

Float will be F 32。And we're also going to do F64 for double， but I'm not going to use the double。

Okay， okay， sounds good now。They direct。Okay let's just try to compile。

 okay we do compile So the basic idea we're going to do， we're going to do a couple of operations。

 right？And guys will tell me if it'll make sense。First off。

We are going to center our coordinate system because right now our00 is at the bottom left of the screen。

Right right here。And this is very unintuitive。To no program。You know。

 especially if you want to do like a camera stuff， what does that mean I mean。

 even where is that in terms of coordinates right we want the zero zero to start at the center if you want to do a camera which I do want to do a camera later on when I do like some crazy gameplay ideas。

When I do do a camera， we can just change that from 00 to whatever the camera position is。

 which is going to be pretty easy and pretty cool to so that's the first part we're going to do we have to center our coordinates the second thing we want to do is。

To make it， actually I want to do three things。The other thing we want to do。

 that we want to do big so independent。Basically， we want to make our coordinate。

Change based on the width。 if， if you draw， it makes really easy。 So if we have like 100 pixels。

 right， as a width。 and I want to talk find half of the screen， it's going to be like 50 pixels。

 correct， Okay， now， if I have a 10 pixel。It's cream。

I want to not quite to have the screens going to be five。So the fewer pixels we have in on screen。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_387.png)

We have to know decrease right the number of the guys， so the number of the conversion。

 so basically I have to calculate like these values to call this function， right？

The basic idea is going to be the P x。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_389.png)

Minus half size dot x。See， because the P here is the standard P。And then we go to the half size。

 so we have to go back。The amount half the amount right， is end up here， okay？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_391.png)

Okay， actually， we're going to do step by step。Just so we don't， you know kind of lose ourselves。

Okay yeah。And this is plus。And we also have to。Do some sort of a conversion or a truncation。

For now it's not going to be they so perfect。But I don't think。

 I don't think it's really going to matter if the guy plays it like a。fullll screen 1098 monitor。

 I don't think you ever noticed the exo imperfection。We can do like subt of things with a。

With the biline filterting stuff， but at this point we should just use the hardware arrangement if comes to that。

 Okay， so now we're going to call the draw rack in pixels。Incorrect。Passing all these parametersers。

One by one color。Okay， let's see what happens。 Now our game。😊。

It's not going to start the player position as this iss going to be a factor two player P and then we're going to have a struck player and all that stuff。

 so we're slowly building up what we need。The tools and the game itself， okay。

So instead of doing a player on the score， I'm going to do player dot。X。Oh。

 instead of doing player god， actually player your feet right player。Only' just score P of dot。Okay。

 now I start calling draw right and pixels， I'm going to call draw right。

I'm going to pass the player key and for a size， let's say 10，10。And the color。Let's do green。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_393.png)

I like green。行。😊，呃。Okay， where's the payer， lets Steve like that？Not sure we are passing。Minus 20。16。

Yeah， because it starts out as 0，0。 So what I'm going to do is I'm going to。

I'm move up to the right little bit。Let make sureO。26，2，60。Havelf size，10，10。

So the we're going to start as as a 250 to50 to 70 to 70， okay。The numbers look good。

I'm not sure why I'm not drawing， though。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_395.png)

And。Okay， let's。Let's try to do the draw acting pixels here。We to 50 to 50 to 7 to 70。And three。Okay。

 I did X， yeah。うん。Okay， thanks for catching that， but okay。No， where did I get that wrong？啊。Did。X 0。

Why want。Yes， okay， thank you。😊，See， now I'm starting to reap the benefits of programming on stream because people do catch these errors and these are the the errors right no one wants to spend our time debugging things like that nice catch porn feelingin。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_397.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_398.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_399.png)

Okay。Now， I'm not moving。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_401.png)

For some reason。呃。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_403.png)

Just try compiling again， okay， let's see。Okay， now I do I am okay。

 so I start off here in the bottom。Right yeah， human deep burgerer， that's kind of deep burgerer。

 right？It catches all the weird areas that the deburger has to needs a human to debug with right。

 okay， this is pretty cool now。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_405.png)

呃。Now we have we have not done anything yet with this， Okay， so what we have to do first off。

Is just to offset our position by the drug buffer。Not draw surrender buffer with hat with actually。

 right， so I'm going to convert it to F 32。And multiply it by half。So this。First step。

It's just to offset the standard now if I start a player at 00， which is what I'm doing。

 I expect him to be exactly in the mirror of the screen see。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_407.png)

So that's the first step。Now， if you see， if I do change this， it's still not big so independent。ok。

😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_409.png)

Okay， now。The other step。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_411.png)

Which is changing the position。To make it a match the。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_413.png)

This that I drew。 Okay， so the basic basic idea。I， I'm going to multiply that。Or to buy that。

 actually， I'm going to maybe do some tri narrative。那有啥的。And I'm going to do the half size first。

And then we're going to do the position， have size first。Okay， divided by a width and a height。

How actually have I done this， by the way？I'm not sure I started doing this， not li ago。Yeah， thanks。

Let's see， I did a couple of very weird prototypes that I didn't even published。

 but the first time I actually did this。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_415.png)

Understanding what I did was in this palm game poll and C and I really I even open source it。

 but it's not very good that it feels weird let's see if there's a date okay so that was September 180 2018 so it was last year。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_417.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_418.png)

So it's been like。Like like eight months。Of knowing this kind of stuff。

Which is the point is to practice， you know， because before that， if you see this other game。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_420.png)

And I did N C++。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_422.png)

Yes， I am going to， this is myI， you can download all the Pro games。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_424.png)

But this is my my the game I actually spend three and a half years of my life making the the other one。

 the one that's on steam， so this the brief story is that。I did this game。

 spent three and a half years building it， and released it in 2017。But by the end。

 I realized that I didn't actually know how to program。

 all I did was like hack a few things together to try to make the scripts and when they're trying to build a game。

呃And。A really polished and robust game and publish that it's really really hard to not know what you're doing so at that time I was just you know programming you know Ri using blueprints no it wasn't alone yeah no I didn't do that alone I had a it was like a 10 people team I started alone and if you go to my YouTube channel I can throw that off too I'm going to post the live streams on the YouTube later on you can see on the videos。

How the game started and I started out all by myself， so this I did by myself in this game。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_426.png)

Its kind of the first idea so it's kind of ugly and it doesn't feel very nice right but the basic idea is there right so this segment I spent one year just playing around in unrealre and learning how to program using blueprints and all that stuff and animation and modeling Okay yeah and then I started doing no more complicated levels in unreal for this game I built the monsters and the gameplay and。

😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_428.png)

And that started to become an interesting game so at this point I started to you know help my dad you know make a team and actually do this real game。

 so we had it for two years a company and weublish other games too we did a VR game。

But we didn't publish that on the story it was like an out of home experience。

 so we had a presentation at a mall that was pretty cool。

But we had to close the company after two years。So and hadn we hadn't released the game yet。

 so at this point I went back on my own to finish the game。

 so it was kind of a full circle I started， I started alone and then had a team and then finished loan。

And the last like year or so or eight months of development was really， really hard。

 not only because of motivation because like I've been doing this for three years and I was super tired。

 but I had no one else like to count on in this sense。

But it was also hard because I didn't know what I was doing in terms of programming at this point when I was pointing the game to the PS4。

 which we also released the game for the PS4， that was pretty cool， Pris4 Gililioseosis Hunt。

 which is the name of the game。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_430.png)

呃。Yeah， you can see our pageon Playations。And it's pretty cheap， actually， you can get it for。

For a few bucks， Ya see， pretty cool。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_432.png)

So when I was doing the port。I had to do it in C++ and I didn't actually know C++ at that time so that was really weird。

 I had to really know Google everything and that was a point where I had to upgrade the unreal version to get the latest version of the PS4 SDK。

 but F mod which is the middleware we use it for the audio。Han't updated the yet。

 but we had to start certification process in the PS4 because the SDK expired right was going to expire so I contacted people at a。

No， this game I used on Rio， I used on Rio Age4。So at this point。

 I had no idea actually how to write games from scratch when I did this game。

I just know look for tutorials and start doing that if you go to my YouTube page。

 you'll see the process was pretty interesting， you know I started modeling the character。

And then okay how do I move him Okay now how do I make him shoot。

 how do I enemies there was a very slow process in the beginning but these engines are good at making progress tangible right so I managed to build this game you know if you see what I did alone before people came along was a lot of things and and it wasn't like experienced people either we just know was like a few students that we want to come together to finish the game that was pretty cool and by having the prototype。

Yeah， I also did the modelss and textures and in the final game we actually had people who could do a better job than I did to build the characters and environments and all that stuff。

Yeah， it was great， it was a great experience， Marcus it was great because by knowing all the process。

 even though people came along， they did a better version of everything I did before。If you compare。

 you with my version of the game。You know， you can see on YouTube， you know my。Yeah。

 you can see the other videos like I did this character and Iimate made him if you see the final results。

 people were like。You know， people who had a lot more experience than me and a lot more interest in those areas managed to do a better job。

But because I had been doing this for a few months and know a little bit about it。

 I could not only direct him better but I could make the game more cohesive and that's。

 I think a very important thing， you know when the programme doesn't understand or doesn't care about design or art。

 the game really suffers and vice versa， so if the artist just create crazy art doesn't care about it's very evident when you see like professional big developers like Jonathan Blow saying about the great art and how he had a really hard time making not control the gameplay in the sense that I shouldn't focus too much attention of the player。

You see that it's a very thin balance between being able to。

To create good art for the game or in good art you see those are things are different。 So yeah。

 it was a great experience to do that。 but at the end I was like， oh my God。

 I can't really the program I had a hard time shooting the game because I didn actually know what I was doing know when I went to the C++ part of the on Ri engine I was just hacking things I just Google and copied code from one place to another I had no idea what I was doing So when I finished the game in 2017。

😊，I started to learn programming， so I spent a few months you know learning S++ and then I started applying C++ inside of Ri。

 which I had a lot of family。F had a lot of experience with， let's put it that way and then。

And then I had all these problems with C++ that oh it's a very complicated and big mass。

 it takes a long time to compile and on real crashes and I'm not sure so I have to run the de bugg build。

 it's crazy so in order to avoid that。And also because I had an opportunity to work outside the games industry。

 I took an opportunity， so my day job is not related to games。

So I took okay since game is gonna be a hobby for now I'm going to start exploring other things like building games from scratch and things that I really really enjoyed so I fell in love with writing games in C so at this point I started building these games so this game I built using SQL+ but I didn't actually understand much of it I was still like copying a lot of tutorials let's see when was that。

😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_434.png)

That was a little bit of over a year ago， like yeah， a year and a month ago， the beginning of。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_436.png)

Last year， so by the end of the last year， I was able to make games like P from scratch。

 I did a lot I did like。Space invades and I help my friends you know I taught them how to do it so I did practice a lot so at this point I was thinking okay。

 I think I'm comfortable doing that on stream and it's hard yeah yeah I have to get used to that。

But I think I'm learning a lot English too because English is not my first language and you know talking in English for like hours and hours。

 it's yeah， I'm also gathering a lot of experience in that as well， that's going to be fun。

So let's see what we have if we try to attach our half size to width and height。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_438.png)

Okay。😊，What makes switch from C+， Okay， so I did C++ for a long time。A long time， like a few months。

 I'm very young， so when I say a long time， you can imagine like a short amount of time， right？😊。

And I realized I was using pretty much just C。In C plus plus， I wasn't using templates。

 I wasn't using classes。 I wasn't using all these crazy things， The C plus。Give you。😊。

And I think C was a lot cleaner in terms of like， I could just。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_440.png)

Quickly， see the code and know what's doing。 I don't have to get， okay， what does that do。

 You don't what's the reference versus the pointer。 No， it's very easy the rules。 I can。

 I can talk about the rules of C really quickly。 And the rest is how do you use the rules。

 And that's what appealing to me。 You know， it's kind of like a game like you teach。

 you learn the basic mechanics。 But the interesting part is how the mechanics combine， right。

 So I think that's why I like。See a lot， but I also have in my plan to learn a little bit more about C++。

Because you know people in the industry use C++， right， there's no escape。

Because the more complex the game is， the more features it need like main spaces and things like that。

It's definitely if you have a big team here the game。Yeah。

 so for this scale of game we're building in industry stream。

 C is fine and I love it because it's simple。I don't have to think too much about what feature of the language I'm going to use right if you get to the point where we're building more complex games。

Yeah， you are a C fan but yeah， Cs great。 Yeah， I really like it， especially you know。

 although there are a couple things in see places that I wish there were in C。

 like I think everybody who wrote in C wished was that were a feature or two。😊。

But I don't think it's worth， you know。Using C++ at least for now I to I like to get the hang of things you know before doing more advanced things so yeah maybe at some point when you start doing more advanced games on stream that'll be fun we can start doing this on C++ but I don't know I like see。

Let's let's see now I don't know what's going to happen exactly， so we have a tiny tiny square。

 I don't know if you can see。😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_442.png)

And if we increase， if we increase the size， it actually decreases， right？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_444.png)

So we probably include it。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_446.png)

Yeah， the bigger， the size， the more pieces we need， yeah， it was kind of crazy。Okay。

 now we have a huge square。Let's see， yeah。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_448.png)

I'll do a constant scale here。Just to have like a reference for our unit system， let's call it that。

So I'm also going to offset it by the scale， not offset I mean。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_450.png)

Change the scale。Okay， now I have a very small。Rectangle and。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_452.png)

Having a bigger one， small1%， I could have cheat with the other code because I'm not a big math guy。

In case you haven't tell， haven't seen， right？But what I am going to do is I'm going to offset the P。

After I offset it in the this， they also have to do that， right， because this is in pixels， right。

 we're removing half the screen width to the side。If we do that before we change the scale of the the P。

 we're going to do that in our units system， which is going to be a lot more。

 so if you offset like100 units to the site it's going to be like a lot more than just offsetting。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_454.png)

You know， in dies， that's the plan。Okay。It's a little bit weird can make it full screen。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_456.png)

I don't know if you guys can see， but we do have a little bit of a guy here。

 so I don't think it's entirely wrong。I just think it scares a bit off， let's see， okay。

This is the basic size， but let's see how small it gets。Okay， it gets decently small。

And if you larger， it goes larger so that's the basic idea， we do have the basic idea right。

 but there's a problem。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_458.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_459.png)

Which is a small error and the way we choose to resolve this error is going to be interesting， right？

呃。We can't make the X dependent on the width。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_461.png)

And why on the height？Because if we have like a super wide display， it makes everything you know。

 flatter and squashed and things， right， but if you have a super tall display it makes it thin。

 so we have to stick with one。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_463.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_464.png)

And the question is， which one will we stick because we could？Stick with a random one。

 let's say the width。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_466.png)

Okay。😊，And then let's see the result， the result is we have like a square oh wait a minute。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_468.png)

That was wrong。I also have to change it here， okay。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_470.png)

Okay。😊，Got offset by the position but don't worry about that what I want to show you is that if you choose the width for example。

 if I change the height， the size is not going to change so the taller the display the more screen real estate let's call it that I have right so if I make it super tall。

I can get more view up here。But if I change the width here， it gets smaller。Okay。

 so this is the difference if we change from with。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_472.png)

To hide。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_474.png)

The opposite will have it。We'll have a。If you change the height， it's going to get smaller， right。

 and if you change the width， not it going to happen。The question is， which one should we choose？

The more intuitive thing is to keep it like this， right。

 because if people have like super wide display， they can see more instead of being cropped。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_476.png)

However， I do think a more interesting solution is too。You know。

 take the 16 by9 aspect ratio as a standard。And see， well， if I'm wider than that。

 I should gain real estate， but if I'm taller than that， I should gain real estate too。

 So what I'm going to do is I'm going to。Create a variable called， I don't know。

That's called it aspect。Multipliier。Which is a really bad name， honestly。That's just。Do it for now。

And okay， what I'm going to do is I'm going to change。Banger buffer。Dot height。Two aspect multiplied。

喂 ok。Now， in illegal interaction。Expect， so nothing is changed， right。

 except I can play around with it。 So the idea is， I'm going to use the height， but if。

The width divided by the height。Right， yes。Okay， so if the width divided by the height。

It's less than 1。77， which is the normal F ratio let's call it the 16 by 9。

 I will change the base of the aspect multiplier to the width。瘦。Hopefully you guys will understand。

 and let me show you what I mean in the game。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_478.png)

So this is not the base thing if I were to this is 16 by9 right。

 this is 1280 by 720 if I were to change the height the width。A little bit。Okay， nothing happens。

 I think I may have messed。Yeah， if I make it， yeah， it's the other way around。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_480.png)

I would start off with a width and change it to the height。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_482.png)

Let me show you if I change the， yes， if I gain with I actually gain real estate。

 it's getting off the screen because these syn were wrong， right？But that's the basic idea。

 we are getting more space when we do that， okay？And if you do this。

 we also gain our space now in the height， okay， yes， we get smallered。That's pretty cool， however。

 there' is a point。In which we we。We're kind of a net， right， you see the difference here。

That's because we change from using the height to the width and they have a 1。77。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_484.png)

You know， fraction of difference。So if we change a scale in this case。

To also don we not change we don't need to change the scale， I'm going to change it here directly。

 so if we offset this。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_486.png)

By this guy， I think I have to divide in those。呃。Hopefully， yes， I'll get a smooth transition this。

 so at this point if I increase the width。I get more。Stuff， actually， it was right。Well。

 and here if I change the height， I'll get Mariio estate， okay？So this is basically what we want。

 but let me fix this position， okay。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_488.png)

Yeah， this one I wasn't supposed to change， this one was really supposed to be the。The Rainer buffer。

5月。And Ra go。So this is a part of programming that I need to get more fun music。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_490.png)

I all this math。But。Okay。I see now it's standard。If I were to you know change， yes， make it flatter。

 I'm losing， I'm losing a。Loing space， right， because if I have a taller device， for instance。

I'll be able to gain that， I don't think it's right， let's see。No。

 it' not right see that this is increasing size。Yes， in with。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_492.png)

It was right， I suppose， so this is the height and this is the with I'll review the code and what I mean just for you guys to understand。

 so so this is the base game。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_494.png)

This is the player player size of the player， let's say that I'm playing on a very wide display。

 What I want to do is that to keep the player， maybe I should draw more。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_496.png)

So。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_498.png)

It's green。😊，Okay。So let let's say that I have more things to have a tree over here， okay？

If I have a wider display like this。What I want is be able to see a new tree。

I don't want to make everything bigger like this。And push that tree to the side。

 I don't want to do that， I want to see more。This in the case that we are wider than 16 by9， however。

 if we have like a 16 by 10。This play， in this case we want to see more things on the top and the bottom。

If I have a wirelessbleed。See the size doesn't change all it changes is the position right so I get more things on this side and on this other side as well。

If I do that。Vertically。So， but if I do decrease the size， I do see the change， right？

And the vertical is the same thing right here I am gaining space。

And here I'm changing the actual science。Hopefully that was clear。

 just that's just make it more pixel independent。And。And now so that you can write， you。

 gameplay code， not worrying about the aspect ratio， okay？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_500.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_501.png)

What I'm going to do is I'm going to now make the final thing we need。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_503.png)

One last thing that I forgot to write here， but it's timing。Time， okay， we need to know。

How much time passed between last frame and this frame？So we could。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_505.png)

Your proper gameplay， let's say， frame independent movement， so this is the problem we have。

If I change here from Pre。To is down。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_507.png)

This first of all， I'm going to be super fast， right， Yeah super fast， but if I make it full screen。

 I don't have guess see， I'm not as fast。Because I have to process more pixels。

 so a frame takes longer， so I'm doing this less fewer times per second。But in this case。

 I'm too small， right？Oh now I was so fast that actually got off the screen so that's the problem。

 I'm super fast here if I make it smaller see。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_509.png)

I'm going really， really fast， so the idea and this is the same when you use like a commercial engine too。

Is to receive。Like a deelta time here。And then you multiply this by the deelta time。

 the delta means the amount of time that passed since last frame and since this unit。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_511.png)

Is。Now what we want to do actually， is we want to do units per second， correct？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_513.png)

So we have units， so the de time is how many seconds passed？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_515.png)

Since last frame。 So if we're doing this every frame， and we do this and we multiply that by the。

One over the seconds that passed。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_517.png)

I'm basically going to get this， I'm going to get the units per frame， so 20 units per frame。

So this makes it very clear。It's a very easy note to change gameplay related things， Okay。

 so how are we going to do that going to go back in the platform code。And well， if you want to cheat。

 but it's not going to work， right， but just first to get a sense of it。

 if you have like a DT here and we set to 0。016， which is like 60 frames per second。Can we pass that。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_519.png)

就 the心的变。Now it's slower but still not independent of the frame rate right。

 so this is pretty slow as you guys can see。If I make it very small。

See that I'm really faster in my movement。And Im the hair is slow。I'm not entirely。Convined， yeah。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_521.png)

The transition didn't work in terms of the rain。Maybe I have to defy it。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_523.png)

分想一下。Yeah， I think that's correct。Yeah， okay。呃。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_525.png)

So now we have to actually change this number。Correct。

 how are we going to do that in the Windows and the same thing when you use a framework like SDL。

 you're going to have to call these things。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_527.png)

They have a。They have a function called query Performance current。Okay。😊。

And this is pretty much it we pass。What they call a large integer basically point to that。

 and then they return the time in CPU clock cycles approximately right with this pretty one nanosecond of precision。

Not an nanosecond， or microsecond of position。And then we can compare how much time passed from the previous frame to this frame and how we know how much time the last frame took and then there's a great talk talk about frame rate independence and how you really shouldn't use。

呃。The last frame frames time as the current frame projected time because maybe last frame was low just because I don't know something happened。

 there was a wiggles update download or something like that。

We should actually just project to a target deelta time。😡。

And if we have for several thingss in behind that， we change that。

 but that's more advanced by from we're not going to do now for now， all we have to do is after。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_529.png)

We feature our frame， we're going to get that frame。H。O。😊，So it's a large integer。

 and we're going to call it this。防治。Now we're going to pass a point to that。对。😊，Okay。

 and then we also have to have a last counter， right？A less counter is the one that was less framed。

As counter and now is going to be a current counter。Okay。And we're going to start off。Our loop here。

Getting the the time。Last counter。So you start off。We get the tank。Every time the frame ends。

 we're going to do。Why make it a game in C language we use it， yeah。

 C++ is pretty much like C in at least in the terms that I use it。😊。

But I should probably use C++ in the sense that most people in the games in this industry use C++。

However， I think it's very complicated， it's more complicated than it needs to be， in my opinion。

 so I like see better and since one of the goals of this stream is just to have fun。

I decided to you see if the game not this game if in we finished this game because this game pretty simple。

 we can do it and see pretty easily， but if we start doing more complicated games and we see that we need more features。

 language features， maybe we should do maybe I should do a C++ no。

I don't know live stream or ever we change things stuff， but yeah。

 I think say it's cleaner so we can you know see quickly see the code and realize okay， this to this。

 I can quickly understand my mind see+ at least for me that I don't have much experience with modern C++。

I see a lot of different things and I have to think， okay。

 this is this what does that mean stuff and the compiler time is longer。

 so I don't know I just like see simpler。I don't know， but yeah。

 a lot to be used to C++ and if I you know wasn't doing this for a more of a commercial objective。

 like to make it a，To learn more experience， to get a job and things like that。

 I suppose I should using C++， but it's not a very big difference。

 you see you'll be able to understand the game pretty easily making our game in C++。

But that's pretty cool。呃。Doing low level things I like and yes he is really fast。

 I really like it and simple too Okay， so the DT we're going to drop here on top。😊。

When we first query so the first frames is we don't know for now we're going to assume it' 60 frames。

 but when we do the platform robustness pass， we're going to actually query Windows to CO tell me the refresh rate mine of this guy okay then we can do a target E we also have to do that for the audio system which is going to run in parallel another thread okay。

So now we get the cr performance calendar， we have the difference。Right here。

 right we can do one minus the other。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_531.png)

However， they are in a crazy unit， they are in， I don't know if it basically says what unit is is。呃。

Yeah。😊，It's a performance counter unit right so what we have to do is we have to transform that to seconds in order to do that。

 all we have to do is a query performance。frequency款器。😊，This frequency guy tells us。

Kind of but a baseline for the queer performance things。Yeah。

 it's going to be great to the programming and you'll see that it's not very complicated once you get the hang of it。

We most plus on it， yeah， I agree， drink vodka， play daka。😊，Nice name。Yeah。

I do like Google Z in terms of a features and it's going to be pretty cool moreous so if you want to follow along when you do audio。

 we're going to do threaded audio and that's pretty cool。Because thread threading has this。

 I don't know。 mysticism behind it。 like， oh， we have to thread because everything's super slow。

 When in a program see， you see that things are not very slow。

 but sometimes you do have to thread and you do want to do that as a performance thing or just because you want to run。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_533.png)

You want to do this with a window and you don't want the audio to be all messed up， right？



![](img/65cad47fe79d6d7fa64b4e5575d06d39_535.png)

This is also interesting， another benefit of using threaded audio。

And if you miss a frame rate the audio wasnt is not going to clip right there's several benefits and once you get off this mysism behind threaded things that people usually have like oh complicated systems oh well have to use job system for that and for that new taxes all over the place we can do like a very simple threaded system but a very effective one so that's what I'm aiming at for this project later on we can do like threaded rendering with more complex things。

But yeah， what's that of time， that's pretty cool。I'm currently using the thread section of the book Adv programming in the EIX environment。

 it's hard to understand if' never done thread programming yeah， it could be very hard to understand。

 I suggest。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_537.png)

Hammet hero is where I learned。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_539.png)

To actually， you know all of those more advanced。Handy here withor。

 I'm going to drop here in the chat。呃。I don't remember threading， let's see。Threaded。Yeah。Yeah。

 around day 122， episode 122 of Hand heroro。He， he teaches about。Mo to threading and it's great。

 he goes really smoothly， and then he builds a full on job system。In in a few episodes。

 we're not going to do that yet that advanced for this game at least that's why I like this series in terms of getting our feet wet instead of doing all this complex stuff。

 but I think it's going to be way better for you to watch those videos instead of，Reading。

 I don't know E En book I know， I haven't read that book， so I'm not sure。

 but this where I learned and I don't know it took pretty well。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_541.png)

It's to figure out。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_543.png)

Yeah， it a。God threw out of my head， okay。Yeah， but for now。

 all I have to do is finish this so we're going to use。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_545.png)

The query performance frequency。看着吧。Cry first。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_547.png)

In the MSDN， let's see， okay。And this function。 Yeah， say the books amazing amazing。

 I will take a look at this book。 Yeah， and complex。

 complex projects like threading and stuff can be really can get really out of hand quickly。 So yeah。

 it really depends on how they tackle it。 But if you say it's good， that's great， yeah。😊，do。

 I did read a book called Ga Gente， that's a classic one， right， being engineed。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_549.png)

Architecture。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_551.png)

The guy who wrote this book is the lead Engine guy in Unitedar。So yeah， it's a pretty big book。

 it has over  a thousand0 pages。But it's very much worth it， yeah。I read it twice， honestly， yeah。

I don't like too much the practical side， you know when he shows cold and things like that。

 I think that's too complicated。At least for further level when I was reading the book。

 however the theory where he explains every topic it's fantastic， you know he's a really。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_553.png)

He's already no great programmer， so it's a great book， yeah。So this is the basic thing。

 if we call this function query performance frequency。😊，Here， let's say， yeah， in the beginning。

And we pass another large integer， I'm going to call it this a frequency frequency con。佢分始。

And that's a pointer to that。Now what we can do is we can divide these guys。By the by the。

The frequency counter， and we get the the the seconds， right。

 because the frequency counter is the amount of。Couns， let's say the cycles。

 the CPU clocks per second， right， And we have the amount of CPU clocks because we just got it here。

 right， So we are going to do is Dt。Equals， actually， I'm going to call this last Dt。

Because that's the last frame Dt。 Maybe we should have a target Dt later on。

 but for now let's just use the last Dt。 last DT is going to be equal to the current counter do quad part。

That's how this large inger is structured minus less counter quad part。This， divided by。

And I want to do the division in Institute。Because it has a lot of a。It's a very wide imageteger。

 right， divided by the performance of the frequency counter。A quick part。

 and now I'm going to convert that to float。Okay。😊，So in the first frame， we should have the La T。

Okay看 left。Then here I'm going to analyzeize it。So in the first train。

 if we run our build here in the game。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_555.png)

Okay， let's just see here where to simulate game。Here it is。In the first time。

The frame rate is the one we set up， it' 0。016， that's a 660， yeahs one divided by 60。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_557.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_558.png)

So in terms of sex， right， okay？But。If we run this for a time， and then we breakpoint this。See。

 the numbers think is。think's wrong， it's zero， right。

To to bug that it's supposed to be very small but not zero Why do you use this IDE forder I use it for just text adding I think it's great for fast iterative。

😊。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_560.png)

Programming， wordflow， I suppose。One of the reasons I really like it is。

Ghost indentation virtual indentation， so if I open like a bracket here。

It automatically actually indents everything below it。And I think this is really great。

 so I don't have to worry error at all about indentting code。

 which I think is just a giant waste of time。And it works great， like if I do it a myth here。

 it will indent this line。Then I can put it like this and then it will not then the other line。

 it's pretty smart， you know I can do like in these two lines。

 so this is the main reason I really like this invitation it also works great right off the bat。

With the way I do builds。I created in the beginning of the stream this build dot that file。

That just run the CLA compiler。And if I press all that LM。

 it automatically looks where the building runs it。So yeah， it's pretty pretty and it's fast， right。

 it's really， really fast， really good。But for debugging and I use Viual Studio because I could use another debugger。

 like there's another one， I thinks remedy。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_562.png)

Remed BD， I think。That is getting pretty good。I should probably try that out。

 but since I have to use We3 for compiling the game， I might as well use it to thebu right。

 but note that they're not compiling a project here。I didn't create a project inside Vi Studio。

 I just literally you knowll use a command line argument here just send my file for a visual studio to comply。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_564.png)

So I use it because I think it's pretty fast in terms of- and it's free too。

 I showed previous mainstream so on HI of it if you search for For coder。呃。

On eachI you can download the demo which is the version I'm using which is fully featured。

 it's pretty cool and if you want to pay it's pretty cheap too。

 but if you pay I think it's $12 or $15 you have the full customization layer in C plus plus I suppose C。

 I'm not sure。And then you can change then do whatever you want you know people have done all sorts of crazy things with this editor。

 but I really like it， know the way it is right love the band， Okay。

 so we are almost done we have to debug this small problem let's see here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_566.png)

The quad part is kind of a reasonable number， I suppose。TheThis guy is greater， Yeah。

 I suppose if I subtract it too。I'm going to show here the watch window I some track it too， yeah。

 I got this number， sounds good。And the frequency this guy， okay， yeah。

 I's going have to do this in float if I okay， if I divide。These guys。By this guy。Yeah。

 I have zero because it says small number of key， so I'm going to do this in float。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_568.png)

The division。I'm going to do the subtraction in int。And the division inflows。

 so I might as well store this guy as floats， right？I do a frequency counter。呃。Previous the Conor。

 I'm going to store this as a quote。And I don't have to convert everything to a float。Okay。诶。😊。

Illegal for a union。嗯。Oh yeah， because I have to change the type here again frequency。

Previousriacy counter。I'm going to call this because counter of large。

Large and then we're going to create F32 frequency conor。Equals。There two frequency car， large。Oh。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_570.png)

哇。Okay。Now this should be a more reasonable number， let's see L DT okay， now our LDT is 0。003。

That's more interesting， right？

![](img/65cad47fe79d6d7fa64b4e5575d06d39_572.png)

Now， if we try， now were really really is low， right because。哼。😊。

We're in real units I suppose for now。So if I go to the game。I'm going to create a variable like。

I' going to set it to 100， maybe a little more， and I'm going to change 20 to speed。O。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_574.png)

Now I should now have browse to still just vote。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_576.png)

Maybe I should change the scale。I'll have the guide you one by one。And in our render。

 I'm going to change the scale。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_578.png)

Lets。Okay， that's more like it。Okay， this is not a perfect movement system yet。

 because I think I'm going to use the mouse actually to make the actual gameplay。But for now。

 it will work just for a test of our systems。呃。Now let's test a very small screen should still be okay it's approximately the same speed in a super large screen。

ItStill the same。Okay， that was a lot， right， There's like two and a half hours of streaming。

So I'm going to wrap up this stream。And the next stream， which is probably going to be tomorrow。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_580.png)

We're going to do the gameplay part， so if I go back to this plan， I can even type this。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_582.png)

In the the game here。I'm going to type what you do。HereTo do。I'm going to do it okay。initial。

Platform。没有。呃那。Lalayyer。Which is window rendering。inputput。Time is about it。

Then we have to do basic gameplay。That's for next time we're already going to start doing our basic game。

 see how easy it is to get a small engine started， and that's because we wrote all the code。

Next time， if you were to do another game and we can start off copying things from this， not even。

Getting this guy。 just copying code。 we're going to do like way faster。

 Ba gameplay is gonna be another breakout thing。 And then we're going to do an engine。Improvement。

Maybe we're going to do AI， we are going to do audio threading。And let's see what else。

The map mat for menus， I'm not sure this is going to be like a live let's see。

 a live iterative process， we're not going to finish the basic game to start doing that。

 we're going to do all them in parallel。But the idea is we're going to do a little bit of gameplay。

 a little bit more engine。 then we're going do we're going to do like say gameplay Explor initial。

Peopleme exploration。They are going to do the。The more game exp。Okay， and then we're going to do。

The Po pack。Both in the any。And。看点。Okay， so that's the basic things we already did the first。

 which is the initial platform layer， so let me just show you guys what we have。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_584.png)

When we play the game， we have a window and we have a little guy that moves if we use thearrow keys。

 which probably also do the。WSデ key。Yeah， okay。呃。And this we create our software render right。

 it' it so independent， so if we make the window know really small， it works great。

 if we make it really wide， it still works great， we can have more view， if we make it really tall。

 we have more view up and down， that was a pretty cool thing we did in the renderry。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_586.png)

If you do like a suit of full screen。It will still work great in terms of rendering and in terms of time because we are running really slowly。

 not really slow if I make it like full screen on night display here and I pause here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_588.png)

Let's say the DT is like 0。019。O。😊，And if I do like a very small display。And plotted here， Dt is 0。

0003。All， so we do have a huge difference because of our renderry。And still。

 the speed is the same and our energy rate is good。

So is there any question regarding what we did in this first stream？

What we can do now is just a quick code review。And I'm going to post this code on HIO now。

If you guys are interested to download it， you can download it for free and what we did today and play around。

 hopefully you guys understood what we did。And you can improve。

 you can already start building your own games with this， like this game dot C file。

 we can start doing a lot of cool stuff。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_590.png)

Right with that's what we're going to do the next time start doing gameplay this basic setup we did。

 but it's pretty cool in terms of API design， I think it's really nice。

 you know it's nice to get the input， nice to draw things。

The game doesn't have to worry about anything at all， you know。

 just get the input and start doing gameplay stuff that's what we need Okay， so let's see。

The basic idea is， so we have one compilation unit， so we compile just one file。

 which is this win32 do。just close this one yeah win3tubetform。c， this is the main file。

 so it includes all other files as a pure text。So utilities we did for our types， math。

 for our vectors， platform common for the button and stuff， and then we start doing we know stuff。

 we had to do this werena call back that up。Close the window plays around with the size。We did a。

We do remain remain， right？Wch is the Windows entry point？

First thing we do was create we know that was pretty cool， pretty easy。

And then start to editing things like now we added an input。

 now we added the performance counter and then the basic idea for our game loop is input and each platform can do its own input you know in its own way right we also have this nice interface to do more input and simulate the game now this is the idea of the game as a service right？

We just say， okay， the platform is the software。But it says， okay， game now you can do its own。

 then the game does its own game， right？And then our render is just to tell Windows with this stretch DI bits function to use our pixels。

 our buffer here to draw on the screen。And then we got the frame time and I'll do just a quick note。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_592.png)

If we run a game and we can see the process running。It's using one corere， its max speed。Here。

Just okay。Here see it's using like 10%。Which is like。Like going all crazy， you know。

 on the score because。We're not sleeping or anything right。

 as soon as we say to the Windows API to draw this。

 we start getting the input again in the more robustness path in the engine we are going to sleep here。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_594.png)

There's a ton of stuff to do， but we are going to do the game next time okay so I hope you enjoy this if you do be sure to follow me I'm going to share a lot of links right now okay you can follow me on Twitch right right now。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_596.png)

You can follow me on T。So you can。It's going to be a weird thing。If I' going to switch。

 so you see when。I stream next time， it's probably going to be tomorrow， know。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_598.png)

You can also follow me on YouTube， which is YouTube。com。Slash dam， Zam。

And I'm going to post all the streams on YouTube if you want to rewatch it。

 and if you want to get the game， which is going to be free， you can go on HO dayd。com。



![](img/65cad47fe79d6d7fa64b4e5575d06d39_600.png)

sorryrry dzi。h。o and I haven't created yet have to create it now。

And you can download it and have fun。With the version we have now， and if you want to expand on it。

 great is whatever you want to do with it。But next time we're going to focus on a gameplay and that's going to be fun。

 so I hope to see you next time， hope you enjoyed it and maybe learned a couple things。

And I'll see you then。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_602.png)