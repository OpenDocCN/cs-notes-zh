# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p03 03_01_08_在PythonAnywhere上安装Django.zh_en -BV1Kt421V7EE_p3-

Hello and welcome to another walkthrough for Django for everybody。

 This walkthrough is pretty much the setup。 It's both the first assignment in the class and the first thing you would do to get your Django application working on Python anywhere。

 Python anywhere， of course， is a hosted environment and you do all your work in Python anywhere。

 And so with this， I'm starting with a brand new fresh account that I just created and going to walk through this thing。

 Now。Importantly， you should always check the latest install documentation because as time passes。

 we use later and later versions of Python and later and later versions of Django。

While this video this video may or may not match what the actual instructions are。

 so you need to be both looking at the instructions and the video in a sense if there's a conflict between the instructions and the video that I'm doing right now。

You should go with the instructions so here we go so the first thing we're going to do is start a bash shell and so we're going to go into consoles and start a bash shell a column consoles it takes a bit for this to start up this is a Linux environment and we are using the bash shell。



![](img/825a89318166c23adc10940472ef192e_1.png)

And so the first thing we've got to do is choose the version of Python that we're going to use and we're going to do this with a virtual environment。

 and so this virtual environment， I'm going to name it and I'm going to choose an initial Python version。



![](img/825a89318166c23adc10940472ef192e_3.png)

![](img/825a89318166c23adc10940472ef192e_4.png)

And so away we go， so we're going to run this， now this can take a little while。

 especially when you're using a free account， so don't you have to wait until you get the dollar sign prompt back and so you should basically be patient。

Okay so that took about a minute， about 50 seconds。

 you can see that that one took 50 seconds so I've edited to make it a little bit shorter but that's how long it takes the next one tends to take even a little bit longer we're going to use the Python install process you'll notice that it's also activated this Django4 so we had to do that first and we have to be in Django 4 and then this PIP command actually downloads and installs the Django library into our virtual environment and again this takes a little time。



![](img/825a89318166c23adc10940472ef192e_6.png)

![](img/825a89318166c23adc10940472ef192e_7.png)

![](img/825a89318166c23adc10940472ef192e_8.png)

So that just finished and it took about from 54 to 02。

 so it took8 minutes for that to finish so that takes a while， so back to the instructions。

I'm going to， I don't have to say work on Django4 because whenever you see Django4 there。

 you're already in the virtual environment， so I'm going to do Python version。

And I make sure that I have version 3。9 Now see these things are fast。

 I think we are writing a lot of disk space， check the version of Django 4。2。

 of course you know we maybe have moved to a new version of Python or new version of Django by the time you're watching this so again。

 always come back and look at the instructions。

![](img/825a89318166c23adc10940472ef192e_10.png)

![](img/825a89318166c23adc10940472ef192e_11.png)

Now。You have to type this command work on Django4 all the time。

 or we can make it so that every time you start a new console we're going to make this happen so lets let's do that so I like to use a lot of tabs。



![](img/825a89318166c23adc10940472ef192e_13.png)

So I'm going to go into the files tab and open this in a new tab right so go to files。

 So now I have my files here， and this is my home directory like virtual environments。

 That's where I put that django。 But the file I'm going to edit right now is the bashar C file。

 and this is the start file When you start a new shell。 and I'm going to copy。



![](img/825a89318166c23adc10940472ef192e_15.png)

These two lines auto switch into the django for once a comment。And I'm going to put them here。

I will even put like echocho。Hi， Chuck。In this to show kind of where this thing starts up。

 and then I'm just going to save it。And I'm going to go back into my home directory。

 and this means if I go into a console and open a link in a new tab and I start a new bash console。



![](img/825a89318166c23adc10940472ef192e_17.png)

You will see that it starts it up but then runs the commands from that dot baash RRC。

 This is just kind of a Linux bash thing。 Bash stands for the Born again shellll。

 and you see it says high chuck that means it was running and actually ran it twice so I'll take that out later but that that makes it so that like this shell that I'm in now is already in Django4。

 but that basically mean that was the code that was running。

 It's an echo that came out right after the print statement for bashhell。

 but I'm in my virtual environment。 and that students make all kinds of mistakes all the time where they forget to go into the virtual environment and that's a first thing in like office hours or help or talking to the course staff they're in the wrong virtual environment。

 So if you just put it in this dot bash RRC。 according to the instructions， life is a lot simpler。



![](img/825a89318166c23adc10940472ef192e_19.png)

![](img/825a89318166c23adc10940472ef192e_20.png)

So we are sitting here in the Django。We're in our Django virtual environment and we've got all the software installed。

 so now we're going to install some sample code。

![](img/825a89318166c23adc10940472ef192e_22.png)

![](img/825a89318166c23adc10940472ef192e_23.png)

And this is going to do some more work。 And there might be some。

 There's another thing that's going to take a little while that C detailed。

 you'll see I do that a lot that goes into your home directory。

 And I'm going to download from Github a bunch of sample code。

 And this is the sample code that's used in the。

![](img/825a89318166c23adc10940472ef192e_25.png)

![](img/825a89318166c23adc10940472ef192e_26.png)

it's the sample code that's used in the course， but it also is going to give you a copy for your own self to go look at and copy from you can like open these files up and copy stuff into your own files and so if we let me go ahead and close I'm going to type exit to close this console and now the consoles close I'll close the window So if I go into consoles you see I've only got one that's this console right here but if I go back into files you see this DJfree samples folder and I am now filling up this DJfr samples folder with all the data from the DJfr samples repository in Github and again now you can go edit those files。



![](img/825a89318166c23adc10940472ef192e_28.png)

![](img/825a89318166c23adc10940472ef192e_29.png)

![](img/825a89318166c23adc10940472ef192e_30.png)

It's almost done Okay， so now I could go in here and look into DJ free samples。

So you see all these samples， there's a cat sample and all the codes here and you'll see that these are quite a bit of you know things and there's the models file I mean we're getting way ahead of it so all this DJ free samples I just checked that out and so that finished the checkout and I'm going to go back here and make sure tilled slash DJ free samples is like double making sure。



![](img/825a89318166c23adc10940472ef192e_32.png)

To make sure PwD where I'm at and so you'll see that I'm in this working directory of Home C7 DJ for samples。

 Home C7 DJ for samples， so you kind of got to know when you're working in your shell and you're working in the files which files are where and you can always type PwD print working directory in a shell to figure out where you're at and then you could navigate to that same place So of working through these folders here but back to our instructions now we're going to do another thing that takes potentially a long time。

 so we're going to start it seven minutes after。

![](img/825a89318166c23adc10940472ef192e_34.png)

![](img/825a89318166c23adc10940472ef192e_35.png)

![](img/825a89318166c23adc10940472ef192e_36.png)

![](img/825a89318166c23adc10940472ef192e_37.png)

And we are going to install now what this is doing is pulling in a whole bunch of library code that you're going to require throughout this whole semester Now my thing is running a little faster now。

 so that's nice。

![](img/825a89318166c23adc10940472ef192e_39.png)

We'll see， this might take a little bit while because now it's download and its going to write it all to disk。

Okay， so that finished， let's just see how long it took。Oh， 1907。It took about three minutes for me。

 Okay， so back to our instructions， just be patient。 And then we're going to run Python manage Pyche。

 and you're going to use Python managed Pyche a lot in this course。 It's a way to basically take a。啊。

APython ajangu application and sort of preloaded all into memory and see if there's like syntax errors。

 et ce， now you didn't write this code， this is my sample code if this fails at this point given all those other commands that have't worked。

That's bad because this is code Iro， but we're basically verifying kind of that all Django and Python and all the dependencies are properly installed。

And so that's good， so we kind of now know that we've done。

 this is most of the long running stuff is now done， so we don't have to things will go a lot faster。

So sometimes。

![](img/825a89318166c23adc10940472ef192e_41.png)

If you don't have your virtual environment set up right， I don't know if I can fake it right now。

 Python 2。I don't know if I can run Python 2 or not， there's no Python 2。Oh， I can do Python。

 Let's see if I can do Python， too。If I诶。Check。So if I mistakenly run Python 2， please don't do this。

 if I mistakenly run Python 2， it will get a syntax error so but the Python I'm running。

Right now is Python 3 and so if you see a syntax error。

 it probably means you're running the wrong version of Python and that's because this managed。

 py file Now here's the thing that will confuse you is if you go into DJ free samples and then you decide that you're going to open up the managed do Py to read it because you figure oh。

 there's a syntax error look at this， it says there's a syntax error。

 The problem is is this text editor is seeing。

![](img/825a89318166c23adc10940472ef192e_43.png)

Python 2 syntax， and that's a Python 2 syntax error， not a Python。3 syntax here。

 so don't make that mistake and that's why I've put these explicit instructions if you see a syntax error。

 don't freak out and do not edit manage。 Py do not do not， not now， not anywhere else in this class。

Okay， so now we're going to just test our ability to create a database。

 we're going to run the make migrations command。

![](img/825a89318166c23adc10940472ef192e_45.png)

And this is much you'll learn more about this much later。

 This is basically reading all the models do py in the samples。

 and then it is going to the migrate is going to actually create a database。 And again。

 you're not really going to use this database much。

 but it is a way to make sure by using my code to verify that all of your installation is working well and your virtual environment's in good place。

 and so that's good good shape and so that's why I basically do that。

 we're probably not going to run this code， but this this will。

Just really test to make sure that that the overall setup works well。

 And so that's not really that big of a deal。 So now what we're going to do is we've really got the installation right。



![](img/825a89318166c23adc10940472ef192e_47.png)

![](img/825a89318166c23adc10940472ef192e_48.png)

We're in the Django 4 and we've installed a whole bunch of stuff。

 and so now let's go into our home directory CD Tild。



![](img/825a89318166c23adc10940472ef192e_50.png)

![](img/825a89318166c23adc10940472ef192e_51.png)

So to go into our home directory and you only have to do this once。

 we're going to make a directory called Django projects， make Dujago projects。



![](img/825a89318166c23adc10940472ef192e_53.png)

So now if I look in here， you're going to see that I have a new folder called Django Projects。Then。

I'm going to go into that Django projects and start。



![](img/825a89318166c23adc10940472ef192e_55.png)

チ추추了。

![](img/825a89318166c23adc10940472ef192e_57.png)

And then I'm going to create。My sight。

![](img/825a89318166c23adc10940472ef192e_59.png)

So what this is doing is this is starting on empty。



![](img/825a89318166c23adc10940472ef192e_61.png)

Jango application。My site。 so now I can go into Django projects and see my site。 You should be in。

Your home directory Django Project My site if you are in your home directory and you see a my site here。

 that's bad， you're not supposed to have done that that means that somehow you sort of got it confused and you ran this command twice or something。

But now we're going to start editing this file and so you're going to have to figure out like these folders that I give you。

 you're going to have to go find them。 So Django projects my site， my site。

And you got to go in twice because that's where the settings file is。 Now， the thing is。

 the settings file is only one place。 So if you find the settings file， you're good。

 So we're going to go into settings and it tells you on or about line 28。

You've got to add this little asterisk， otherwise it will not accept connections from around the world。

 they're very conservative when they first set your project up。So now we are going to save this file。

 okay， so that's the first thing that you've got to do。Eventually。

 if you were running this on your local computer， you do this thing called run server。

 which would start this up， but we're not going to do that。

 so we are going to go into the web tab and I am going to again start this up in a new tab so I still have my console。

 I still have my file editing and now I have this web tab and so now we're going to set things up so I'm going to add a new web app。



![](img/825a89318166c23adc10940472ef192e_63.png)

![](img/825a89318166c23adc10940472ef192e_64.png)

嗯。And I'm using the free account and I'm going to say manual configuration here。

 and I'm going to use Python 3。9 because in the beginning we started with Python 3。9 okay。

 so you do want to match that， so we're going to say we're going to make a web app， Python 3。9。

So it's setting it all up， so here we are okay， and that's the this is the domain name of my page。

And so now we continue in our instructions and it's telling us the instructions say how to do this。

 So let's go back running check， building application， starting it。 Okay。

 so then you got to go down to see。Here where your application is。Okay。

 so we're going to make our application。 this is going to be slash home。Pong。I can't type slash C Se。

 which is my my account， S E V， slash Django。Undersco projects。Slash my site。

Now I'm going to highlight this because I'm going to use it twice。

And I must set the working director to the exact same thing。Okay， so that should work。

And so then the virtual environment is going to be， I'll just copy this。

The virtual environment has got to be that virtual environment that we just created。

Except it's not Doctor。 Chuck， this is the account here is CSav。So now I have a virtual environment。

 now it might complain like if you got the version wrong or whatever。

 but right now I'm getting no errors and so that's a good sign。

Now the other thing we've got to do in this just a little bit weird and you're only going to have to do this once is this Wkey configuration file。

I'm going to edit this and I'm going to use。Control A or command A and delete the whole thing。

And then I'm going to take this bit of code right here。

 and I'm going to put it in this Wkey file and then save it。

And then I'm want to hit back and I'm back here， so I've edited this whiskey file and again。

 I'm just carefully following away right， away you go。And now it should work。 I mean。

 we'll see if I did it right。 So I'm going to hit this reload button。 So what this is。

 is this is basically reading all these files that are sitting in this folder that we put in and starting。

Zango up。And then hopefully connecting all the requests that are going to come in from the outside world into this C do Python anywherewhere。

com。 So let's take a look。 ho， and it worked and it works successfully。 So that's good。 Now。

 you know， there's all kind of things that might happen badly。

 and and let's just let's just start by making a mistake。 Okay。

 I'm going to take this settings file and I'm going to put in here。

I want to put in let's make a mistake。This is a Python file， and I am。呵。This is not good syntax。

 allowed host equals is a list that debug equals true。 that's an assignment statement。

 so let's just put like bad code in here。So then what would happen is I would say save。

And then I would come and I would reload C Python anywherewhere。com。

And now it's reading all those files again， including that setting stop PI file。 And then I would。

Go here。And I would hit refresh。And would say something went wrong， and this is really， really scary。

 but the way to best debug these is to go in here， jnangle projects my site into into the Djanangle projects folder。

 and then you got to be in the folder has set managed at Py and then you say Python。



![](img/825a89318166c23adc10940472ef192e_66.png)

Manage that Pi， check。I told you before that what this does is preloads everything and does a whole bunch of checking。

 and so this basically is a trace back。

![](img/825a89318166c23adc10940472ef192e_68.png)

And it's got a bunch of stuff in it， but the one that matters is here this is my code。

 the rest of these things are Python libraries etc ceter。

 and it's like oh let's make a mistake and it's on line 30 of settings。pyy so you go find settings。

pyy let's make a mistake look oh there's a syntax there so I'll take this back out and then I will save it。

And away we go。And then after I've saved it， I've got to go back and I've got to reload it again。

Wait until this little spin thing has finished。And then refresh this。

 And now my application is working。 That error we got that something with wrongs called a 500 error。

 which means that the server Pyth then we received a request。

 But the code to respond to its not working right。 So oh， may we go。 So I believe at this point。

 we are in。Pretty good shape， oh， then we're going to add our polls application。

So now we're going to go back to our console。And I'm going to say CD this， which is oops。Xidi。Paste。

 Cd。I've got to be in Dngo Project My site， and now I'm going to start an application。



![](img/825a89318166c23adc10940472ef192e_70.png)

Python manage P， start app。And you got to be in the right folder for this to work。



![](img/825a89318166c23adc10940472ef192e_72.png)

And so this is going to create another folder。 so if I go take a look at my Django projects folder in my site。

 you will see that now this polls folder is currently there okay。So let's continue， that's right。

And then you're supposed to follow the steps in the Django tutorial， but in general。

 the one thing that you get wrong is if you then go down， you do all this stuff。

 we created a start app， the one place where this thing will take you awry is when it says run server。



![](img/825a89318166c23adc10940472ef192e_74.png)

![](img/825a89318166c23adc10940472ef192e_75.png)

Whenever these tutorials tell you run server， you've got to come back to these instructions to say。

 oh， instead do a Python managed P check。In your console。

 that basically makes sure that everything's kind of syntactically correct and then go back to your web app and do a reload。

 and that's the same as a run server， So run Python managed P check and then do the reload and that's the same as whatever it's telling you to do when it's telling you in a djanangle project。

 This is a jnangle project right when he's telling you to do that， don't do run server。

 do Python P manage P check。

![](img/825a89318166c23adc10940472ef192e_77.png)

![](img/825a89318166c23adc10940472ef192e_78.png)

![](img/825a89318166c23adc10940472ef192e_79.png)

![](img/825a89318166c23adc10940472ef192e_80.png)

And then go and test your things。Okay， so I think that that kind of gets us to the point where you can go through those things。

 I've got some possible errors。Don't have two my sites if you see a second one。

 get rid of it and make sure your my site is inside of Django projects。

And so it tells a bunch of things， et cetera， et cetera， et cetera。

 so I hope this has been helpful to you， see online cheers。



![](img/825a89318166c23adc10940472ef192e_82.png)

![](img/825a89318166c23adc10940472ef192e_83.png)