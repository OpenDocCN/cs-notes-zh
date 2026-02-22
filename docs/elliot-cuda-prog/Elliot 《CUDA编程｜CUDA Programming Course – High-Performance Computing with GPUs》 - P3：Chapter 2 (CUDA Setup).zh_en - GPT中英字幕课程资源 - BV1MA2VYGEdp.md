# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P3：Chapter 2 (CUDA Setup).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

🎼So doing the setup on Windows， we just need to open up our terminal and run as administrator。

 starting with Windows。 we just enable permissions。Ensure that it's the system 32 directory。

You'm going to navigate over to the turn Windows features on and off。

We're going to scroll up and look for hyper V。Ensure that box is checked off。

 and then we're going to look for virtual machine platform。 ensure that is checked off。

And then or checked on rather。 And then you have a Windows subsystem for Linux。

 Make sure that's also checked on。In order to get this working。

 you will need to enable virtualization on your machine。So， you know。

 once the Windows subsystem is on， you can do wsl。🎼And you'll see， you know。

 a bunch of options So install distribution， and we see an example there， WSL install distribution。

 Ubo2， we can go ahead and enter。Enable。And we'll just wait for that to complete。

 I've sped this up a little bit because it takes some time realisticistally。 It takes more than。

 you know， a few seconds to do this。 So I'll speed some of these things up。

You who has been installed， awesome。Tnges will not be effective until system is rebooted。嗯。Yeah。

 so we run it again。 We have this command that it's asking us to run。

 So WSL do EX C install no distribution。 that installs correctly。 And we get the same thing again。

 So we just do a system restart。

![](img/155041a2b182c91d4d6d26f768ae8f23_1.png)

![](img/155041a2b182c91d4d6d26f768ae8f23_2.png)

Now， after we've restarted， you might be greeted with this terminal。Ybuuntu and then。

🎼The other command prompt。 So when you're greeted with that。

 if you're disc greeted with the command prompt， you do WSL and you can get it here and just enter username and a password that you're going to use。

 Now， you should be logged into your little simulated Linux environment。 So once we're in here。

 there's a few commands beneath run。So we're going to update and we're going to upgrade everything。

 So just type in the commands as you see them。 there's some we're going to be able to copy and paste in。

 So this end that password you said earlier。Ive time lapse， this are not time lapse。

 but I've sp this one up again。 So that was just a bunch of things updating if we go in and install some other packages that we'll need later like W get curl and Gis。

 we'll see that those are also installed as a part of the update and upgrade commands。嗯。

And then we just installed Python 3 Pip。 This is just going to be Python。

 essentially for our machine。And。That also runs， too。So that does not come by default apparently。

 So we just need to install that manually。But that's okay。

We navigate over to Chrome and we search up Ka toolkit。 This is what we're looking for。

 Kuda toolkit download。 So you just navigate to the latest one。 It might be 12。5， It might be 12。6。

 whatever it is for you。Go to Linux， pick your architecture and use WSL you been to。

 Remember we're using WSL， and then just do the run file。 It's the easiest one。

 least amount of instructions you have to do。So I'm going to do the first one， so W get。

 you can just right click in the terminal if normal pasting doesn't work。嗯。

Let's maybe highlight the whole thing。Awesome， so that's going to take some time to upgrade。And。

I'll see you guys， on the other side。Okay。So now we're in the little accept part。

 so just only check off the coa toolkit there and then should be good to install。

Now we've done the run S H file， which was the second part of the command。

And it tells us in the summary that we need to add some things to our path。

 So I've just pulled up this here。 but this wasn't really working too much。

 So I went off and generated some other， you know， more up to date commands with Chad GBT and figured out the proper ones。

So。You'll see those in a second here once I pulled them up， but is this is just a reference。

 so this is one of the things we have to do。🎼So we could just vim into our bash our C file。

 and then I'll just just pretty much type along with me here， and then we'll save this file。

 So feel free to use nano or vim whatever you feel comfortable with， I'm using vim here。

 but you know Na isn't too hard either。 So going to set a coup to home。User local/ kuta。

 and then we're going to export another one。Called path and。As a part of that path。

We're just essentially going to include kuta home。And then the binary for that。

And then last but not least。We're just going export the。LD library， like it also said in the summary。

And then lived 64 to end it off。Awesome。So now we can just control C， control W and control Q。A。

 Col W kind cute。We exit that。And then we can oh， I notice we missed something。 So kuda 12。

5 instead of just kuda so we can go ahead and go back into this and then just find that part and add。

And just right click and paste that back in。 then just delete the last cut part， A。Could at 12。

5 sweet。 Now we can just exit that again。And source。Then we just do NVCC version。

 which is the NviDdiaA coa compiler， so that's working。

 and then NviDdia SMmiI so we can actually track our GPU stats as long as these are both working。

 we've done the job correctly。 So if you're not if you're getting errors with NVCC or Nvi SM that that's not good。

 you need to figure that out。 I don't， of course， cover all the errors， but。嗯。That aside。

 we're going to go ahead and set up a little kuda test just to make sure that everything's working properly and that we can execute a dot C or kuda script。

So I just made a directory called Kuda setup test and we're going to just vim into that directory and we're going to edit and we're going to make a new main dot C file and as that of here I'm just going to go ahead and paste some functions so we include the kuda runtime header。

 we include the IO stream which is a part of C++ that allows us to use things like C out we declare the namespace STD for a standard and then we see out hello world in our in mainin function。

So if we do NVCC out main binary and then main docu。

 we should be able to run this binary and get Hello world， awesome。



![](img/155041a2b182c91d4d6d26f768ae8f23_4.png)

So if this works first try for you， that's awesome。 if it didn't， that's not so awesome。

 but you should be able to figure it out just by navigating forums。 So like Github。

 the stuff I recommended before， just navigate around and figure out how to install the kuda toolkit for Windows。

 It pretty much applies the same to Uuntu。 I'm gonna go over some brief instructions here。

 But I'm going to switch over to Ubuntu because that's what my whole thing is based on。

 that's where I do all of my stuff and where everything is set up and optimized for。

 So I'll see on the other side。 we can go ahead and open a Chrome tab here and just type in kuda toolkit download。

😊，So we go to this one on Younntu， same thing。We go Linux x64 is mine might be different for you。

 youuntu。This one。Or file local， you can do this。 You can also do network or local。 So for me。

 I did network， but that was a little while back and having to uninstall it and then reinstall it again just gives me a bunch of weird graphics errors。

 So I'm not going do that and mess with my operating system too much。But。



![](img/155041a2b182c91d4d6d26f768ae8f23_6.png)

You should be able to just plug this directly into terminal。

 so you should be able to just pop into here。And。Put these in。 W get the。The Wian file。

And then just the rest of this and install the kudo toolki and then just get the。

 the legacy kudo drivers。 I just did this， this legacy kudo drivers。 If that doesn't work。

 do this one。 And then you would， of course， want to just do do。



![](img/155041a2b182c91d4d6d26f768ae8f23_8.png)

NBCC version， and then NVIDdia SMMI， and you should see some useful stuff pop up here。

So if these don't work for you right away。You know， you might want to just restart your computer。

 that's usually the best option and then try something again。 If you do already have these installed。

 you don't even have to worry about it， so I would probably check these first。

Pro we should have said that first， but yeah， ensure theca compiler works and then NVD SMI。

