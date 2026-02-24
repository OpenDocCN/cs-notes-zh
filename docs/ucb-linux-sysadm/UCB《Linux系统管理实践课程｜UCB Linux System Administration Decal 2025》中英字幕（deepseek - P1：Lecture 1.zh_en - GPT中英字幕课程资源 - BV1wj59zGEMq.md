# UCB《Linux系统管理实践课程｜UCB Linux System Administration Decal 2025》中英字幕（deepseek - P1：Lecture 1.zh_en - GPT中英字幕课程资源 - BV1wj59zGEMq

And just some general。

![](img/94797f2fae1cab7559970e801461ca53_1.png)

Fun stuff about the history of Uniix and Linux as a whole。

 some fun facts about what Berkeley had to do in the history of this development and also the general idea of free and open source software Okay so let's get started。

People on zoom if you have any questions just throw them in the chat I'm looking at it and we also have someone else looking at it please don't unmute yourself it'll get very chaotic people in person if you have a question just raise your hand and we will take your questions okay a couple logistics lab1 and vitaminmin1 should be released basically right now they should be on greatcope and lab one should also be available on the website if not right now itll update like a couple minutes you should have access to theed and the greatcope so if you don't have access to either ed or greatcope please let us know and we'll have to figure something out just reach out to decalf。

 edu and you'll figure it out and along with this you should have also received an email from us with regards to how you log into your decal Vm if you have not received that at this point again reach out to us and we will get you started and then just a very quick note on treating everyone over here with respect you know generally。

When you interact with other students or staff members。

 just be respectful even on ed or on discord we don't want to have any kind of you know weird going on because it's harder to actually help you out when you need the help and all the staff members over here are voluntary stuff Nobody's getting paid for this people are doing it basically because they want to so sometimes they might be a bit more busy but you know we are here to help you and if things are not working well。

 let us know but just be kind about it and we will help you you know if you're going to be rude it just makes it harder for us to help you out just be kind and it'll be okay and the same thing applies to your interactions with fellow students。

Next the lecture slides recording and the lab itself will be posted at decal。ocf。

io this is the normal decal website that you're used to seeing so everything that we see today including in the recording will be posted there and final point is the experimental track info we will be posting out aned blast today later tonight so if you're interested in experimental track from next week onwards you will be attending a different lecture and you will not have to come in here today if you don't know what I'm talking about just wait for the Edpost and that'll explain it Any questions whatsoever at this point。

so the question for people on Zoom if you didn't hear it was if you want to do the experimental track is lab one gear for you on Saturday and yes it is La one is common for everyone irrespector what you want to do you will have to complete lab one any other questions。

Oh， wait for the experimental track do we work on lab like during the lab are still。

You can work on okay so the question was for the experimental track do you work on lab during the lab part I think the question with regarding when do you work on the lab and if if I understood it correctly you can work on lab whenever you want to you don't have to wait for lecture to start or you don't have to wait for a designated lab time to start working on the lab you can start working on it whenever you're free we do have a designated lab time every week after the lecture itself and what that's therefore is basically there's always going to be a person during that time over here in the lab so if you have any questions you can come in and ask us questions but you're free to work on a lab at any point whatsoever that your question Okay perfect okay we move on at this point if you have other questions just find one of us either me or the people over there and we will help you out。

Okay， moving on。Okay engaging with this lecture so this lecture is gonna be a lot more hands on and we want you to actually play around with stuff as we go ahead with the lecture so what we want you to do is SSs into our login shelf so it'll be SS so open up a terminal if you're on Macs just if you search terminal in your find in your applications you should bring it up and the same goes for Windows I think or if you're using some other getbash or something you can use that on Windows so yeah just go ahead type ss Of user name at s。

partly eduu and you will be able to SS into what we call tsunami which is our login server and a quick question on zoom will there be any lab help online if you attend lecture online。

You can throw questions in the chat， but we will not be waiting in the Zoom room after the lecture for the lab help so if you really need help online a couple options are making a post on Ed but really I would encourage you to come in person if possible if at all possible because things are so much more easier if you come in person just because things are faster for the people you are here。

 Thank you for the people online， if you have the chance to come in person。

 especially if you have questions with that week's lab it'll be far more easier to help here in person just far more quicker rather than making an a post and someone responding to that and then you respond to that again so SSH in will have demos sprinkled in at different points。

And what we want you to do is ask questions， you can even ask questions in the Discord decal general。

 but usually if you're live just ask them in person and that's about it。系体啫。

That should be replaced with your username。Okay， so the dollar okay， so when you SSH。

 if anyone typed what you saw on the slide directly with the dollar OCF username。

 just replace the dollar OCF username with your actual OCF username so in my case that would be lockxit so I would type in LK SITH at assist OCF birth3 deal。

日鬼。Okay， perfect help that a safeing and let follow along with the lab， raise your hand。

 I can come over and help。Oh everyone's got it okay people in person， if you at any point need help。

 just raise your hand。Someone will get to you。Okay。

Hopefully most people are following along if you're still stuck just raise your hand。

 someone will come help up Okay so what is the shell so the shell is what we call a CLI or a command line interface right so it's how you interact with the computer and what you normally use every day is called the GUi or the GI right which is the graphical user interface so these are just different ways in which people can interact with a machine and in fact the command line or the terminal used to be the original way in which you know the old old time people in like mainframe era where people had massive computers or supercomputers actually interact with this you know computer itself and in the very very old days it's called a terminal window because you literally had like a terminal that you type things into which is more like so much like a very old teleprompto which is not a computer entirely which would just like get data in。

but data out it resembles like a typewriter with a screen attached to it it's very cool if you have a chance to take a look at it and then we have common shells so these are like how you actually so these are different versions of like the shell that you interact with you'll see a couple versions but the most common one is bash ZshH and fish they're mostly the same each one has like some nuances and some differences to it for example fish is supposed to be the friendly interactive shell so it is supposedly more big friendly but personally if I were you just stick to the default one which is bash or ZsH on MacOS and both of them will for the most part be the same they are like some small differences but for the purpose of this class and like 99% of use cases their differences should not matter。

嗯。And any questions at this point？Okay。有。一。Okay， so next we'll take a look at。😡，Oh okay。

 there was a question in zoom。 the question was who creates these different shells and the answer is。

A lot of different people， lot of。Very smart people in the past so if you look at like bash it approation is the B again shell because there used to be the bone shellll before and there are other different shells shell variations like this so at every point when someone feels like oh this specific shell does not fit my use case they're going to be like okay I'm going to reimplement a shell and someone decides to create a new one and if it gets popular enough a lot of people start using it so as we'll discuss later on when we get to like the history of Linux and everything in the world of open source。

Popularity is everything so the more popular your project gets more people are going to use it and then it' will become the standard so why is bash the standard because it is the most popular shell right by default almost every Linux distro uses bash we'll get to what a distro means later but everyone uses bash so it is the most widely used version who can create a shell。

If you want to， you can also go ahead and create your own shell will people use it though that'll depend on how good the shell is hopefully that answered the question。

 but if not put something else in the chat again。Okay。

The basic structure of a shell command so when we interact with shell commands there are different ways or like there's a common structure that every shell command follows irrespective of like what that specific shell command is and the structure is going to be the command so it's going to be let's say you're doing LS which is like list all the files in the directory so the command will be LS and then the flags are going to be different variations on how you want to modify this command right like if you want to list all the hidden directories or do you want to list all the directories or all the files that were inside another directory all of those things if you want to list more information you will put in flags and arguments are basically what do you want to list right so if you leave that blank for LS specifically itll list whatever directory you're on but you can pass in some other directory as an argument and it list that specific directory we'll take a look at that in a bit here in the demo but idea is it'll always follow this general。

Stucture command flags an argument and the next point is basically read the manual so usually if you want to look up what a command does。

 you could Google it yes this is possible this is very helpful but also every Linux program comes with a manual attached to it right so if you put man and man is also a command so you could put man space any command so in fact you can also do man man which is going bring up the manual page for man you could try that right now and you will get a manual page of like what the man command is solicit it'll usually give you a synopsis of like you know the general things that it does and also the flags that you can pass in and what it expects as arguments so man is a very good command so when any facilitator is actually helping you out do not for a second even think that we all know these commands by hot like this is not possible this is not true in your life or like in this course in general。

You'll always be constantly looking things up either at the man page or just on Google in general。

 looking things up is always increased and is completely fine。

 this is not a test of memorization it's just you get used to things。

Okay so now get into common shell commands again， if you have any questions。

 just raise your hand at any point， don't worry about interrupting me and the same list for zoo just put it on the chat Common She commands So we have common commands you might have seen these before but you might not have first one is CD so this is going to change directory so if you want to C into some of the directory if you have directory and you want to move into it you're going to use CD just another note is before we can get to C there's something called MDirr which is make directory so if you do MDr space some name so you're going actually create that directory so if you're in your like if you log into your shell right now there will be no directories So if you put CD you can't actually go anywhere so before you do that if you want to actually try it out make a directory with MDirR and put any name and then C into it and see what happens LS would list your directory so it'll just give you a listing of everything that's inside thats specific directory。

basicallysically will print out the same whatever file that you have。 so if you have multiple files。

 it'll cabinet all of those and print them together head would read the first1 lines of any given file less basically is a way in which you can read a lot like a huge massive file right so if you type in man by default the man uses less internally to actually give you like a neat view of a big file right so if you just do CA and if it's a large file。

 it's going to print it all allowed and you can't actually read it but less iss going to allow you to like step through the file use J and K to move up and down or down arrow and our arrow to move up and down and you can also do fancy stuff like searching first things and so on and then MV is going to move files so move also does rename it so if you want to rename a file you're going to move it to a different name so that's going to just move the file or you could also move it from a directory to another directory so that's move。

CP is just copying a file and RM is delet in a file a big note before like you use RM when you're using a graphical user interface。

 deleteleting a file is not that dangerous right if you delete it it's gonna go into the trash but if you're in a terminal RM does not have a recycle bin it does not have a crash if you remove it it is gone right so be extremely careful with RM don't like okay don't like delete very important things。

 especially on your laptop on your VM go ahead do whatever you want， it's fine。

 we can reset it for you but on tsunami or on your laptop tsunami is our SSH then so in those places don't do this but on the login instructions that you gave via email over there do whatever you want that's okay we can fix things but just be very careful with RM Any questions so far。

Okay。

![](img/94797f2fae1cab7559970e801461ca53_3.png)

Okay， next let's get to editors。😡，Some common editors if we use from the terminal itself so an editor is just some program that can modify text files and when you're working from the terminal or in principle almost anything that you do in Linux for the most part is going to be dealing with text files and text files are like the root of everything in Linux or just in general and using an editor is a very common aspect of interacting with the terminal itself so some common terminals that people use in general or nano which is the most common one so this will be the simplest one for you to use which I would suggest using if you're just getting started just do nano and any file name and you should be able to like type things out。

 move with the arrow keys and so on next you have Vm Vm is a meme to be notoriously hard to learn but if you give it the time you can type in VIm tutor which is actually going go through like a sequence of Tea use some basic WiIm key bindingings and so on but it's a very。

Very good tool to have because it just makes your life a lot more faster。

Or that's what a lot of people claim and I believe that next you have EmX EmX is also a very commonly used editor。

 a lot of people feel very strongly about Emax like the Emax people like they believe it it's you a godgiven piece of software and they do everything with an EmAC emX is more of an operating system itself rather than just an editor so it can do a lot of things and that's why there's like a bit of controversy between VIm and Emax where VIm is like do very simple things but emax is like do everything and yeah so basically try running whatever editor you like VIm or nano or emX and just putting a file name it can be a file that exists it can be a file name that doesn't exist if it doesn't exist it'll create a new file for you。

And on Google you can try searching VI and VI is basically the older version of VIm so VIm is shortened for VI improved。

 so VI is the actual original one or Emax on Google and just look at there's an erego there for you to find out but also adding on this I will go modify the slides as of right now I would say yes Wim nano very important still but they're not as absolutely necessary as they used to be because VS code is pretty decent and VS code has this extension for like SSH so if you want to use VS code there is an SSH extension that you could get and just on any Linux machine you can SS into it and actually edit files there and it iss actually really good so don't be thrown off by having to use a specific terminal editor like Vm or Nano or Emax if you don't want to do it that's completely fine。

is perfectly okay for our use cases and actually works very well and has become for the most part。

 even an industry standard。 so don't worry about using BS code because as of this year or like from like two years ago。

 I would say it has been pretty decent Any questions。嗯后。Okay。

 it seems like there are some issues with the course website。

Crashing because of too many people logging and we will figure that out sorry about that please get off the course website if you're on it right now but we will figure that out I don't think there were any other the questions as a right Any questions in person。

ok。Okay， and this is not that important。😡，We will okay。

 we will get to this in a bit after I do a demo wait。Okay。So let's do a demo。

 Can people on Zoom still see my screen。Okay， people in person， can you see my screen？

If the font is okay， okay。Okay so this is the terminal and as you can see whatever is to the left you can ignore for now all of that is modifiable and you can look up how to change the shell prompt online and all of those things can be modified but usually what you would see in like the default settings is a username at whatever machine connected to in this case my machine is called coniffa and you can have some kind of a path so in this case we are in my home directory which is a tildeign under demo and under data so let me move up one directory so I can do c dot dot and what that dot dot indicates is that I'm going to move up one directory right so just a single period means your reference in the same directory two periods means you want to its' parent and let's do L and see what happens so right now in LS we have a folder called data some。

of a She script called Hello world and a file called not so secret file and the reason we have this not so secret file is you'll see a bit so let's first try looking at what's in the not so secret file so for that we will use this command called CA which is going to just print whatever the file has and let's do not so secret and oh it just has high so we can see that the not so secret file has high in it and let's see what the hell world She script is aity right so。

It is a shell script you will learn a bit more about this in the second lab。

 but basically from our expectation it's going to just print out echo hello world so it's going to print out hello world so let's try running it so we're running。

Hello world from the terminal， so that's basically how youd run a script and it prints a Hello world。

😊，Okay， any questions at this one？YesYes， okay， so the question was what's the difference between doing dot slash a script or S or bash a script so I could have done。

Butush。Beello world， and that will still work。 And if I do S stageage。

Hello well that will also work so what's the difference between all of these three things The only difference is in this case when I do dot slash it only works because and again you will cover this in a bit later lab because I have permissions to run this shell script as an executable so there's permission set where it says hey this is an executable file I can run it and by default what it does is it looks at the very first line in the script so if you look at the very first line over here。

Like there， so it tells that it's going to run this with the bash。

You know shell right so it's going say okay， you're going to use bash for this and with bash start running everything that's underneath。

 So in this case it's just going run it with that。 But what you could also do is you could just run a shell script by passing it in as an argument to another shell command right so in this case the shell command was bash and you pass in an argument hellello world S So what it's going do is so bash is actually going open up and it's going to read this file and run it as though it was a script right and you could do the same thing with S there's like very mild differences as to how they're different but。

In principle， it should be exactly the same it shouldn't change too many things。

 it's just you know small intrericacies about file commissions and stuff like that。

 but as of right now don't worry about it it'll make a bit more sense I think by next lab yeah another question that。

Yes， this is the Hollywood file， so you can see it right here so you can let's open it up and them actually。

嗯。Just so that people can see it a bit better so yeah that's a hellwell file and you have just the first line。

 which is again， as we discussed which shell you're going to use in this case in this case we using bash and you have this just one line over here we printprints out ao work。

Yes， how you get when to show the lines of the lines over here。 Okay， so okay， this， this is。

 these are good questions。 Okay， so how do we get when to show the line numbers。 So let's open。呃。饿。🤢。

Okay， sorry about that， it's just painful。So let's ignore most of it， okay， actually， you know what？

There we go so what I opened up over here is I opened up the WiMRC file in my terminal so the WMRC file is basically so all RRC files in general are hidden files that will be in your home directory that or these are like config files or dot files that tell how this pressfi program is supposed to run so in this case because I like having numbers in them and I like having relative numbers in WiIM we have these two options over here which is set NU and set RNU don't worry too much about this this is just like additional but the idea is both of these together gives you line numbering like this where you'll have the exact line number displayed on the line you're on and it will give you relative lines up and down so right now we're in line number 20 and those are like minus one to34 and these are plus whatever and that's relative number and so if I remove the relative number it'll just be straight line numbers。

Any other questions？And also yes， pull and Q is to quit Wim if you get stuck in wh。

 you can press colon and Q， sometimes an exclam mark to quit。O。

Any other questions that are written on？嗯。Yes， you have to install them to use it。Okay。

 great question。 So the question was， do you have to install whim to use it in most cases， no。

 but sometimes yes。嗯。In most machines WiIM is available by default， if WiIM is not available。

 VI will always be there， so if WiIM doesn't exist you can be like VI and VIm will always be there VI will always be there WiIM is a bit you know sometimes you might have in it sometimes it'll be present depending on what machine you're on and what it was configured for。

O。Okay let's continue so we were talking about you know commands and passing flags right so so far we've just been saying LS and we have this thing called not so secret file so does that mean there is a secret file that exists so let's try doing an LS with some other option so if it do Ls have an a you can see what has happened right so you can see that you have yes not so secret file data and hello world exists but you can also see two new things that have popped up which is super secret folder and we have a super secret file。



![](img/94797f2fae1cab7559970e801461ca53_5.png)

So anything that has a dot in front of a Linux file or folder will be hidden by default right similar to if you look at the previous command over here where I used to open my VmConfig it has a dot in front of it right so those things are usually hidden by default so that it doesn't clutter your you know general LS but if you want to take a look at it you can pass in the a flag right so you do LS and then pass in iPhone a and that actually splitits out hidden files so let's take a look at what's a part of the super secret file super secret file。

Yeah and and and it's surprise that you found it sale so that's L and looking at you know files inside and let's actually go inside the super secret directory actually super secret folder yeah so we are in super secret folder and we have something called move so let's take a look at what Mo is。

嗯。Oh， and there's a cow that says move。If anyone can figure out how you get this， I don't know。

 I will I will give you a candy Okay， any questions so far。😊，Yes。

I'm wondering but if there' something help add a point that they're very impact for it。

out that because of just Ire every document。Yes， okay great question So the question was in LS。

 do we have to specify which directory that you're spitting out right Yes。

 usually if you want to you know spit out some other directory other than your working directory so usually the directory that you are in so right now my home directory demo and dot super super folder is where we are at and how we would see what a directory is we could say PwD and if you have in PwD it's going to spit out what directory we are in so by default Ls is going to list all the files in your current working directory right so the working directory that you're in right now is what LS is going to use but you could also pass in a different document So if I did Ls slash home slash lovees that's going to spit out everything that's in my current home directory So where you have demo we have some kind of a homework we have some other random stuff but yeah。

Does that answer your question？对。But you'll see let's say actually I see are these students that have a lower file and a file can document and then if I turn out as pages。

 it's just going to sit out the name of the phone。Okay。

 I am not too familiar with exactly what Els does in Windows。

 I will come talk to you in a bit after this， is that okay？Okay， yeah perfect。

Because as far as I'm aware， yeah， because like Windows uses something entirely different but。Yeah。

 okay。TryingIt didn't work。Okay， yeah， I'll come to you in a bit， but any other questions？Yes。

 so you SSH， youre already in Linux。If I SH， I'm already Linux， is that true？Okay， this is SHS。

 but I am also already here。But。哦。Okay， what was your question if you have sage are you in Linux。

 I don't know。No sorry no you're okay。 no no Okay， I'll come back to a bit。 that'。

 usually if you have a stage，99% of the times the machines are Linux Windows usually does not support put a stage。

 it could be Mac。 but if you are SS into a machine。

Onlyly on an extremely rare occasion is it going to be a Windows like 99% of the time it's going to be a Linux mixed machine so if at any point you type in SS and you went somewhere you're most likely going to find yourself in a Linux shell environment but hopefully that answered your question but if not I will come talk to you but okay moving on with the demo so let's。

Move out of the super secret folder and let's go to our data directory。

Okay so we can take a look at this data directory if anyone is in 61 B right now this is going to be some of the data that you're going to be using for Project2 I'm sorry I couldn't find better data to work with but generally so let's take a look at this protocol called top 49000 words right so this is supposed to be like a massive list of words like the most commonly used words in the English language and when it says it's 49000 so there are 49。

000 entries in this file so let's try to chat that。And it's gonna be painful。 So yeah。

 it's just gonna be a random spit of everything。 And we're still just at like B。

 So if you want to actually wait for this toca， it's going to take a while for it to complete And if you want to break out of this。

 you can always press control C and control C just terminates anything that you're running right now。

 So if you mess up and type something that's going take a while or something is hanging just control C will allow you to just break whatever So yeah。

 the problem is that was not very helpful for us to look at what was inside that you know folder right So let's do something different。

 So instead of caden， let's use less instead。So if you do less。

 so as you can see we're at the top of the file so you can see like a cr of something is on top。

 but you can use。You know， different keys， you can use J&K to move up and down。

 or you can also use the arrow keys and you can type slash and type in something。

Hopefully hello is there what okay it's going to take a while to search because it's a massive file and yes hello exists and it has founded for you see so if you want to go through a larger file something like less is more appropriate than just cadding right if a small file just cat it look at it but if you think it's going to be multiple pages something like less is going be much more handy and press quick。

😊，O。Any questions whatsoever at this point？YesLe use like Viy Le could use JK and you to slash for circle。

Like any else， friend。Okay the question was does lesss use winIkey bindings yes， by default。

 lesss uses winkey bindings， I am not sure if you can change that to some other key bindings but I am like knowing the Linux world I am fairly certain it will allow you to do like an emax key binding and if you want or also some kind of custom key binding should be available but yes that should definitely exist there a way to check how big a file is you can I mean you can definitely check how big a file is in different ways there are multiple ways in which you can check how big a file is I'm fairly sure there is a way to exactly get the number of lines in a file do I note of the top of my head no but a fairly common way of checking how big a file is would be you can do LS andm passing another option called long format which is with hyphen L and if you do that it's okay because。

To zoom in right now， it's a bit annoying。Let's actually do。Okay。

 let's say that so if you do LS hyphen L is what I did previously and it's put out something that was hard to read because it was not quite and good human readable。

 so all the file sizes were displayed in bytes but you can pass in LS hyphen LH so the H makes it human readable and that you know makes those things display things in like megabytes or gigabytes so as you can see the top or1000 words was like。

300 megabytes， which is like massive compared that to like wordss that start with Q。

 which is only like 400 kilobytes and there are like other smaller ones like the very like the top 14000 with like 100 megabytes which is also still very huge yeah depending on how big the size is you can kind of get a sense of how big the file is but usually if it's beyond like kilobytes it's already too massive for you to like look at yeah what's the first column what is the first column great question we will cover that later but the first column is the permissions of every given file right so the first column has in this case permissions for readr for the user that is me read only for the group which is alter me and read for public people which is like anyone who is not either me or does not belong to the group that owns the file。

Mction the。Your screen is taking。It's not。嗯。

![](img/94797f2fae1cab7559970e801461ca53_7.png)

I is is is， is it better now。Okay， okay， okay， thanks， Okay， Sam。

 and if you want to take a look at something interesting on that note。😊。

If you do Ls hyphen L for this work， you can see that Holello world actually has。

Executable permissions so it has an X over that so yeah that's just basically permissions for what different users are allowed to do with that specific file。

 but you'll learn a lot more about that in detail in a bit like next week or two weeks from now any other questions。

Okay there's a question on Zoom if you're using a local VM what Linuxist would you recommend for us to use if you local VM if you're out in the class or you just want to play around with VMs。

 I would say start with the window it is the default a lot of people don't like it。

 it is controversial but just start with it it's the default option but if you don't want to start with it。

 you can also use Deion Debbion is what we use at the OCF commonly for the most but see if you're starting out I would say either U to a Deian if you want like a graphical interface U2 is probably better suited it's a lot more user friendly to install but if you're comfortable with other stuff or like a terminal window Deion is very good it's what I personally also use in a lot of cases。

If you're already on Linux that we still need to SS into the VM， if you're already using Linux。

 well great， you don't have to SS into a VM for like this lab specifically。

 but for some future lab assignments， we will be asking you to do different things that would just be generally better that you do it on the specific VM that we give you you don't have to do it there you can do it on some other machine but it's generally easier if you do it on the VM because you'll have like other stuff you know。

😊，Pigure it out for you that you wouldn't have to worry about on your local machine and also if you're playing around with stuff and you break things。

 it's much more convenient if it's on a VM that we can reset for you instead of breaking your own local machine。

Any other questions？Yes， there's a question on zoom which says it doesn't show when I'm actively typing on the shell i'm sorry about that like I think that's like a connectivity issue it seems to update in like random periodic delays I think that's a lot of people it's not just you。

I don't know how to fix that， but hopefully the recording is fine。

 if not I'll go make another recording and I'll publish it。😊。

Yes the zoom screen share is I'm sorry just to verify we can complete all coursework via ss。ocf。

ed no that is not true ats。ocf。edduu is our login server where we have admin control and you guys are just users on there you should have received an email from us at some your username decaldeal hosted or something where it's a specific vm that you have full admin access to full route access to so you can just type in pseudo which is like root access and whatever and do whatever you want which you cannot do on ssh。

ocf。ed so you will have to use your student Vm that we give you and if you don't have that tell us and we'll figure that out but okay any other question that this one。

All right。We are kind of close at time， but。I don't care。

We will try to finish this quickly there will be no that's like the end of demos and now it's all。诶。

I don't know。 brainwashing people， So what is open source software right So the idea of open source software is。

You know， it's free for people to use in。Almost all use case， it's not just。

 you know free in terms of the price， but it's also free in terms of what youre can do with this。

And sends it out they don't allow you to change the code， they don't allow you to look into the code。

 they don't allow you to redistribute this code and so on。

 but most of the things that you use within the Linux space are what we call free and open source software so basically the source code of the special software is open for anyone to modify change publish redistribute created on projects etc。

是啊呃。Yeah and sometimes you have yeah so that's free in open source software and sometimes you have specifically just open source software and this is the term that's used by certain companies where you do have access to the code but you're not allowed to you know freely redistribute it or change it or you know you sell it again or package it or whatever so they are like different times of like licenses that they exist in the open source world and we'll take a look at some of them right now。

 but the general idea is you know there are two different distinctions between software that is just free to use something like。

Steam right so steamam is free to use yes you have to like pay to buy games on it。

 but it is still software that is available to you。

 but you can't actually look at the source code or modify it or make changes or distributed it。

 but you also have things like Linux and almost everything that we at the OF run。

 which is both free and open source in the sense that you have access to everything and you can do whatever you want with it。

O。Okay， and then there is Guinea and the free software movement so there was this or is there is this person called Richard Staolman who kind of created the whole free software movement so there used to be a time where free software as we know today Linux as we know today did not exist and Richard Staman was a person who had this idea that we should have。

You know， software that was independent from specific companies controls that was available for the general you know hacker community or like a community to just use。

 modify and play around with and Richard Staulman was one of the first people to come up with those ideas and he created what we all canoe or the initial package of new don't worry too much about it right now if you're interested just take a look at it。

 all of this is like you know kind of the ethers of the thing and that is Richard Stalman for people who are in familiar with。

So， there's like a slide on the for freedoms so the freedom to run the program as you wish for any purpose。

 it doesn't matter what the purpose is the freedom to study how the program works。

 So if you want the reverse engineer it poke around see if it has any bugs in it see if it has any security vulnerability it is in it so you're free to do that there is no precondition did there's a freedom to distribute it。

 So if you want to redistribute copies of this code。

 you're free to do so and this was radical at that time because like dis code or like IP code that was like not restricted was kind of very radical before and the freedom to distribute your modified version So if you can get the code change it and make it better and distribute it again that is also increased So this is the four know freedoms that people expect the software foundation so you can go take a look at their website and they usually have metrics as to always this free software and this is not free software like how compatible with free software are different。

Pieces of code out there。Yeah and then thiss like the coolest part so there is BSD so BD is Berkeley standard distribution so the history goes like this so there was a period of time where Linux did not exist and the only thing that existed was what we call unX now which is basically dead so Uniix used to be a flavor of computer operating systems。

Wwhich had a lot of different companies that had their own flavors of UniX so one of the big ones was by AT&T so they had a specific lab called Bell Labs where they had a flavor of UniX that they distributor which is very popular at the time and among academic circles it was very limited so you can't actually change things in this code phase you can't make your own versions etc and Berkeley was one of the first people to like create a reimplementation of UniX and actually make that open source called BSD which is very popular even at that to variable at the time very reliable and I think even SSH or like open SSH and things and like a lot of networking stuff to this day are actually from the BSD era。

And also all modern MacOS is based on BSD like BSD to Darwin and then MacOS so everything uses BSD in the background sometimes in fact the initial version of Wiim called VI was initially created in Berkeley in what is the I forget the name of the hall but basically the math building that we're destroying Evans yes that's where this stuff was created and basically what happened was it was sued into a legal limbo so they sued BSD so AT kind of just said。

 we don't like what you're doing because well you seem to have based a lot of things on our code and it just stuck you know could not get popular because of that and in the same period。

Linux happened like someone created Linux， not someone Las Toals created Linux all the way I think at Finland and that gained popularity over BSD and people started using it。

And then why did UniX kind of beat out all the non-unix systems， especially in the server space。

 so if you like using a regular computer you might think that Windows is the most popular operating system and this is true on the desktop space but everything on the server side is done in UniX or UniX like operating systems and it had some real clear advantages over other systems that were competing in the space。

 which is basically primarily the idea of everything is a file。

 so interacting with different processes etctera， if you end up taking 162 eventually that'll make sense and a lot of things which is simplified into like one common structure so everything was part of the foli directory the use of sockets。

 etc was invented in UniX at that point and having modeled code and all of those things were like veryrudimentary in that time to actually set it up with success in the future。

And that's why it's kind of taken over everything at this point。

 so if you want to do anything systems oriented in the computer space right now。

 Linux is the default option。嗯。And why false so why do people actually want to use free and open source software The first one is security and this might be kind of countertuitive and the reason being is that you might think oh the code is available for everyone to look at so does that make it insecure but actually that just means that there are a lot more people who can take a look at the code to figure out if there are security vulnerabilities in it so because Linux is open so academic research is worldwide have the option to actually do penetration testing on it to actually look at the code and be like oh this seems in and I think this probably has a flaw let me test it out and so on but for close those software like Windows or something because the code is not open。

 you can do some level of testing but it's nowhere near as comprehensive as what you could do if the source code was open itself and then cost obviously instead of having to pay for licenses it's just free you can use it。

Privacy again， because you're not making any contract with a company， nobody knows what you're using。

 so you know you have everything that is owned by you so if you get into things like selfhosin and so on。

 you can have like your own server that runs things like Google Drive for you when I see Google Drive is just like a different version but you can have all of those hosted by yourself and you can have a much more private lifestyle especially in this day where almost everything is being sold for advertisement purposes and so on you get more control so when you have your own software。

 especially when it's free and open source， if you don't like something you can go change it it might take some while and if you can't change it it's a very high likelihood that someone else also once that specific within and someone else has already created that for you so if you look up stuff you will have someone who had a similar use case and created something for you that you could use and obviously collaboration because it's open source in right now basically。

It's used all over the world， things like Linux and like open source software in general have collaborators from across the world that pool in their resources to come and make。

This piece of software， So that's why people use force in general。

Okay and then we have open source licenses I will go very quickly over this so the first one is what we call copy left licenses and this is basically the opposite of copyright and Linux is on a copy left license and this is basically like Richard Stallman。

 the ninu person the person we saw recently was a very big fan of the GPL because what the GPL specialifies is that。

Yes， you're free to modify and reddibute this code。

 but on the condition that any modification of that specific code is also open source right so if any person。

 if any company wants to make modifications to it， they have to recontribute whatever changes they've made again back to the public so you can't you make some kind of a modification and keep it just private to yourself right and Steve Burmer Bamer who used to be the CEO of Microsoft before the current person call it a cancer that attaches itself to an IP in a sense to everything inpches which which is fair I guess if you're Microsoft and you want to sell your piece of software。

 it is a cancerous thing that exists that can make any IP illegal unless you make it open source as well。

 and then you have the permissive licenses， which is MIT BSD Apache and so on。

And the idea with this is basically you can do whatever you want。

 you can use it in a project that is close and that is fine so that's why MIT licensing is like the most popular license that people use and if you want to read more about this I was going to like do a demo where we poked around this website but we don't have time for that just go ahead it's chooselic。

com life licenses there are some very funny ones on there that you can take a look at but yeah that's no demo。

Okay， additional resources， Google co exists， you can always go things and especially once you're done with this decal you know it's only for a semester that you're gonna to be here always Google things Google is a very good resource or you can always find things on Google but otherwise in a more serious notes There's a lot of other things you can have firstly you can always ask us while you're taking the decal we are here to help you out so if at any point you get stuck just put something on decal general in the Discord or like oned and it'll do our best to help you but know even better come in person for lab and be like hey。

 I have this question and it'll be very easy to help you and then there's just like some resources in general that gets you some point isn like how to ask better questions and so on take a look at that if you're interested。

More technical resources if you want to look at some specific things the archwiiki is really good so the arch Linux is a specific you know Linux distribution it's known to be it is a meme in the Linux space but the documentation on there is really good I would also say the De and wki or the Deian handbook is really good otherwise things that I would throw on there also is like the gen wiki is also good but yeah generally general links for people like look at other resources but that's about it for today thank you all for coming if you have any questions just stick around come find me if you're on zoom you know just put something on Ed and we'll come figure it out or just put something on decal general and that would be easier for us to help you out on there rather than an post but either works thank you for coming see and if you have any quick questions just put them in the chat I'll take them now any questions before or people can leave if you have questions this come one up see thank you。

拜拜。you guysWai what？

![](img/94797f2fae1cab7559970e801461ca53_9.png)