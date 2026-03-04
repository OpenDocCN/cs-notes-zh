# CppCon【中英⚡CppCon 2024】 p43 P45 Blazing Trails： Building the World's Fastest GameBoy Emulator in Modern C++ -BV1NHEEzdE92_p43-

From game development to high frequency trading， thanks to QDC， the Qua Develop Cer。Good afternoon。

 everyone。My name is Tomtesh。 When I don't fly a starship， which unfortunately， is most of the time。



![](img/ee8b27b8a6010521aeceaabad40afdcf_1.png)

I teach C+ plus algorithms。Comput system fundamentals and retro console and emator programming。

 That's a new one to aspiring game de。😊，Students， some contact information is there for both my organization and me。

 don't be afraid to hit me up on LinkedIn or send me a mail。 I am very open to talking。

I some good news， too。The people from Pact asked me to distribute a book。 I have several of them。

 So if anybody asks a particularly smart question。Or gives a particularly smart answer。

You are getting a book for it。I actually bought the same book here from the thing a couple of days ago。

 so。I could have stolen one for me， but it's too late now。Oh。

 I have to mention that I don't officially endorse the book。

 I have become jet like read two chapters of the tenants。 It's O。Okay。

Writing the world's fastest game Boy emulator and modern C plus plus。First question is， why。Why。

 well。I kind of want to break up my answer into several parts of that statement。

 Why modern than C plus plus， Well， this is C plus plus N CPP co。

 I thought I thought you wouldn't be interested in if I tried to write the fastest one in Java。

I didn't want to do that， either， so。We're fine。Whyite writes an emulator。As a programmer。

I feel that。 and I， and I noticed that with my students as well。

 some of them have written emulators of part of emulators。For their grad work。

 and this gives them much deeper understanding of the hardware。 If you have to emulate the hardware。

 you have to understand what the hardware does。The whole mystery of I put my C plus plus into something and actions come out becomes。

 no， I understand what these steps do。Okay。Wow， two words in would great。Gamebo。Why the game boy。

 by the way， Happ birthday Game Boy， It was launched in the US 25 years ago。

So a quarter quarter of a century， who ever played on a game boy。That is great。

 That makes this stock a bit。Easier， about 120 million were sold，197 million。

 if you included Gamebo advance。 that was backward compatible。

 And it wasn't really backward compatible。 that it was actually a gamebo built into the thing， so。

200 million more or less。 They were up to the PlayStation to the best sellingling console。

Of all time。But now theyre the fort or something。 So a very important piece of technology。

To have a terrible screen。People who say it's not true。 It's been a long time since you played one。

 I have several。 The original is terrible。 That screenshot is really well taken。

 I found it on the Internet。 I don't know what they did with the lighting。When it starts moving。

 everything blurs。 So the， the resolution is pretty low。 It has eight buttons， a Dpa Star flex M B。

stereo sound。If you have the headphones because it's a monope。嗯。

So you all know what what it is There we are。 So it was important。It's pretty simple technology。

 Sc is not too high resolution。 Those are advantages。

A lot of people have noticed that it's easy to make an emulator for a gamebo。If you。

 if you want to write your own， you will not be the first。 There's a lot of open source。

 there that's a great advantage。 If you get stuck somewhere， you can look up how other people did it。

There's also a plethora of technical information available， very detailed。 We all wish we had this。

I don't know how many of you went to the unit test talk。 The person who gave it it was great talk。

 And he said， the most important thing you should take away is you need to write unit tests。

That is true。 We need to write unit tests。 Who doesn't write unit tests。

A bunch of liars in this crowd。For hobby projects。Good news is。The gamebo has a bunch of tests。

It's not as good as you test， but still， right， you put that into your emulator。 If it works。

 you know where you stand， it actually gives pretty detailed information about what went right or wrong。

 So that's。That's all in all great。This is great。Well。It has a huge library of games。

That's interesting for what we're gonna do with it eventually。 And also， this huge library is tiny。

No， I haven't lost my mind。 It's tiny in size。The entire thousand00 games fits into 800 MB。

 which makes it reasonable to do stuff。How much fun can you have with just 800 MB Well quite a bit if you have a game boy M Retor。

There's also surprisingly。I looked up the numbers this morning。

 a very active home brewrew scene with this little graph there。 blue is for original game Boy。😊。

There's 807 home brewre projects available online。 So on top of those thousand games。

 on top of the 30% of those 576 that are backwards compatible。

All these games are there for you to enjoy some of the mar。😊，Not all of them。 These homebre projects。

 sometimes it's also just a demo or something。 Well， I say just a demo。

 The demo can be really interesting。 It's like the Commodore 64 demo scene。

 People do crazy stuff with these thing。😊，Also important when you make an emulator。

It's sexually quite simple。The， the game Boy was launched。At the end of the 80s。Actually。

 after the8 bit period。What does that mean， It means that when they were designing it。

 everybody knew a lot about how to design a good and clever aid bit system。

And that's why you get such a clean design。 If you look at the PCB here or have some labels on it。

Yeah， it can't be much simpler than that。 right， some Ram， some V Ram。

And then everything connects to the connector， and。Mostly you're there。 There's。

 there's almost no other chips on there。 Why is that because way ahead of its time。

 this was a system on chip。It had built in。AGras device。Nowadays， we call， wouldd call that the GPU。

 But then it was called the PU， the pixel。Processing unit。

 the clock frequency was 4194 and 30194304 Hz or 4 MHz。That number seems special。

 Does everybody know why it's special。海无人机。Is that what relevant What power or N TS I know it's not related to power or N TSC。

 Actually， the， the game boy is not region locked。You can buy them from anywhere。

 I actually the game Boy lights， fantastic with built and light， only the least in Japan。

 A student of mine brought me once。😊，What he was doing in his internship there。

 So now it's not that Nobody， nobody react， Yes， Yeah，s power 22。s due of power 22。 Here you go。诶。

I don't think this book is good for you。Beginning C plus plus， that will probably be way too easy。

 yes。And the book I bought， I see， you can also download the P Df from it。 So it's very nice， so。The。

 the clock is a power of two as a programmer that makes me happy。

 but also makes me happy as a C plus plus programmer， There's no iop port instructions。😊。

The Intel 8080 had these annoying IO port instructions。

 which you then have to map to intrinsic functions to call or something like that。As you can see。

That chip is a sub chip subset of the Ntel 8080， the Xilox Z 80 and some own stuff they added。

 What they left out from the Ntel 8080 is mostly that port stuff。Thebo is fully memory maps， yay。

That makes our lives way easier。It has the 8080 set of registers and some extra bit manipulation that the Z 80 does and some additional new instructions that should help with graphical stuff。

Now， the system on a chip。It's super， super simple。Because of this， right。

 it's easy to understand what happens。There's a memory map。 You can take a look at whats。



![](img/ee8b27b8a6010521aeceaabad40afdcf_3.png)