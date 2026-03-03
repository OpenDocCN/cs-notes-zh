# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p05 05_01_01_吉多·范罗苏姆：Python的早年岁月.zh_en -BV1Kt421V7EE_p5-

🎼你。🎼Okay。🎼你行。🎼宝宝。I worked at this place， CW Y。 and for my then current project。

 which was the amoeba operating system， which I was working under Saapppa Melor。

 One of our projects was to write。Application level utilities for this new Aoeba operating system。

And so there was an operating system kernel， and it was very good at talking to the network。

 and it was very good at managing processes。 But there wasn't much user level software。

 There was barely a shell。 I think there was a ported。Very old Uniix shell。

 something like the original version Unix version 6 shell。

 but because the file system model on Amoeba was so very different。

We couldn't take an existing suite of Unix utilities。And so we wanted it to be self hosting。

And in order to do that， we realized we needed a large amount of user level， sort of applications。

 utilities， tools， whatever you call it from an editor to a mail program。

To a login utility and a backup tool。And one of the things I realized as we had a small team of people sort of working on those things that it was very slowgo in writing all that stuff in C。

 And it wasn't particularly interesting or sort of novel， or。Difficult， and often。

 we also didn't really care how fast the code ran。 All the reasons why you would write a piece of software in C didn't really apply。

 The only reason left was that C was the only language that for which we had a compiler。

 There was this ABC language that I had in the back of my mind that would be。

A much better language to write a whole bunch of。Utility application tools for amEba。

Except that ABC was so high an abstract that it really。

It wasn't a good language to talk to servers and file systems and processes。

 and sort of the whole operating system thing was abstracted away from ABC。

It was almost something like it。I don't know in an alternate universe。

 ABC could have become the language of spreadsheets。

 it was very good for talking about a user's data。And doing all sorts of clever stuff with that data。

 And it did that， using very sort of。General， all purpose data structures。

 like lists and dictionaries。 And of course， it had。Very nice code structuring devices。

 like a small number of simple statements that could be combined in any way you wanted to create other constructs。

The usual function and procedure。Abstractions， it was not at all an object oriented language。

 although the implementation had some objects sort of shining through。Anyway， ABC S。

As it existed still wasn't usable。But。I somehow， since I had worked on the ABC project。

I knew exactly how it was built。And I had this idea my head， that。

Given how much time we had available for our project， I could actually build a whole new language。

 design and implement it from scratch。Given what I learned about both the design and the implementation of ABC。

And start using it to implement our suite of tools and still be ahead of the game compared to a situation where we would just have sort of。

Cluked on writing the things we wanted to write in C。For three months。

I did my day job and at night and whenever I got a chance， I kept working on Python。

 I believed that within three months I was to the point where I could tell people， look， here。

 this is what I built。And it had an interactive interpreter loop。So the first demos were all。

Let's assign an expression to a variable and print it back。



![](img/463a728fa2ec89d7df1665e801137d90_1.png)

And let's define a small function and call it， and let's put some things in an array and it rate over the array。

And all those things worked。And。Somehow， and I I。I don't exactly know sort of how fast this happened。

But。Certainly， my two office mates were almost instantly taken with it and started helping out。

And they and the few otherss within the instute。Were very excited about this thing that I'd built。

And started sort of。Of course， we， we didn't instantly use it on amoeba because it wasn't mature enough to actually write the amoeba utilities that we wanted。

 but it was already instantly useful enough。For to run on our Uni system， people within CWI。

 even outside my own apartment。Started using it and recognizing that it was fun and productive to use。

 And they used it for small scripts。 And people started contributing things like。😊，Bug fixes。Somehow。

 things went very quickly during that first year， because I think by the end of 1990。

 so a year after I started， we developed a plan to do an open source release of this language。

And this was before the word open source had even been coined。So we didn't call it that。 but we。

 we did have some models。 We had like。X 11， the window system at the time。呃。

Had a distribution that was。One of the the sort of open source examples with two colleagues。

 I worked on sort of building a distribution， and we， we actually， I。

It turned out to be very simple to get management to sign off on this release。

That was an incredibly lucky stroke。I just sort of。I asked my manager's manager。

 what shall we do about this。 And he said， oh， you got to talk to this and this person in the administrative branch of the。

Institute， and I talked to this woman and she was like in charge of all legal affairs， I believe。

And I said， well， I have written this source code， and I would like to release that。

 And I have sort of made up a license that。Like identical to the MIT license， I could say。

 MIT releases software under exactly this license。 And we just put like。

The affordable name of our institute in there instead of。The regions of the institute。

 She asked me some questions like。Did someone pay for for this to be developed？ And my answer was。

 no， I， I started this all in my own， my own time。And it was for this research project。

 that's sort of。My manager is fine with it。And so she said， sure， go ahead and we did it。

And that's so that in February 91。We did the first Python release。And it。

 it felt like at the time like an incredible milestone。 we， we needed to post it to UseNe。

There was this UseNe news group that。Would receive。Source code for random free projects。

I got immediately started getting useful positive feedback from， well。

 initially just from random people who picked up free software from UsezNe。

 and we quickly sort of got into a routine of doing new Python releases。And every time。I mean。

 there were the obvious improvements to the language and the library and bug fixes。

 a very important category of things that were often contributed were ports or porting fixes。

Where people had different architectures， different compilers。

 the the Unix world was much less homogeneous at the time。

 There were lots of small Unix vendors that had their own compilers or their own hardware。

All sorts of things。 So the the big things that happened during， say， the first half of the 90s was。

A community of Python users and developers self organized。

Then came the invitation to come to the United States for a couple months。呃。From NISistT。

 the National Institute for Standards and Technology。 So I spent two months there。

 we organized the first Python workshop， which was hosted by NISist。 through that Python workshop。

 I met people who offered me a job and from 95 I mean。

 I went back to the Netherlands for a few months and then from 95 to 2000。

 I worked in the US in Northern Virginia at CNI。

![](img/463a728fa2ec89d7df1665e801137d90_3.png)

And so there we worked through a lot of growth of the community and the infrastructure。

 we created the Python website， I got in touch with a bunch of people who are still active in the Python community like Barry Warsaw。

 I think when I started there， Python， 1。3 was about to be released。And then while I was there。

 we released several subsequent versions leading up to 1，5，2。Which for some reason，11，5。

0 was nothing but 1，5，2 remained that sort of the standard。

 the gold standard of python for a very long time afterwards。🎼。

