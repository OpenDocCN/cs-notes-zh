# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P21：21_03_06_构建Python项目脚手架.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's get started with creating a Python project scaffold。

 What's important about this setup is that it's a repeatable process that you can do for every new project that you create。

 Let's suppose theres a Github repo， and you check it out in this case。

 it'll be in the cloud9 environment， but to any environment。

 What are the things you need to do to be successful。 Well。

 the first thing is I would recommend creating a make file。

And this make file will hold a series of recipes Next up， we should create a requirements file。

 so that'll be the next step here。And it'll be called requirements dot Txt。

After that we can create some kind of a script， I'll start with a hello。pyY file。Also。

 we can create a test file， so we'll test our code。

And then the final bit here would be that inside of this environment here we could create a Python virtual environment。

 so really these are the key components in order to test your code。

 get it set up so that later we can do continuous integration and we can do continuous delivery so let's go ahead and do this in the AWS Cloud9 environment。

Let's get started with creating this basic scaffolding for our project。

The first thing that we'll need to do is create a new Git repo。

 so I'm going to go ahead and go to GitHub， I'm going to create a new repo called scaffold。

And then I'll put a description， this is a project scaffold。For Python。All right。

 and then a few things to point out here would be that it's always a good idea to add a readme file and also to add a Git ignore file。

 I'm going to go ahead and select this and select the default Python template。

What this does is make sure that。Irrtating files like dot PYC files or other files like eggs don't show up inside of your git repo。

 they'll automatically basically be ignored。Okay， next I'll go ahead and say createre repo。

Now that I've got that set up， I can go back to my cloud9 environment。

I'm going to go ahead and select this icon code and I want to select SSH This will allow me to do encrypted bidirectional communication and I don't have to have a password if I set up SSH keys so first let me just show you how this would work before I set up the SSH keys so I'll go ahead and copy this go back to cloud9 and I'll type in Git clone。

Here we go。Notice after it tries to connect， it says I can't do it right。

 I have no way of connecting to this repo because I never told this environment how to communicate what I'll need to do then is set up SSH keys。

 so I'm going to go ahead and clear the screen and set up SSH keys and give those to my GiHub account。

So step one is， let's type in SSH hyphen keygenin。Dash T RSA。

And notice that it'll put a public and a private key pair in this directory。

 which is my home directory。Now what I can do if I scroll up a little bit is you'll see this public key。

 that's the key that I want to print out。Into foreground and then upload to Gitthub。

 so I'll go ahead and run the word CA， which is basically print it out and print out that key。

From here I'll copy this string and this is not secret。

 I can actually put it on a website somewhere if I wanted to。

 but I want to put this into GitHub and so I'll go back to GitHub here and I will look at my profile and I'll go to settings。

And from here， I'll go to the section called SSH and GPG Keys。

And then I'll go ahead and create a new SSH key。I'll go ahead and paste it in here and then call this scaffold。

All right， you'll ask me for my password， great。I'll go ahead and log this in and now if I go back to cloud9。

 I should be able to check this out。So notice how if you use the up arrow or down arrow。

 you don't have to type in a command again， this is a great idea in general。Perfect。

 we've got this checked out， so we're ready to build out the scaffold so I'm gonna see the CD command is change directory into scaffold and then I'll run an LS notice there's nothing inside of here So the next thing that I'll do is I'll use this touch command which will create empty file So what are the files I'll need initially well I want to make a make file。

 so I'll say touch make file I'll also want a script file so we'll make one called hello。

I'll also want a test file， so I'll say test Hello WY， I'll also want a requirements file。

Requirements at TXT， and this is pretty much all I need to get started。

And then from here what I can do as well is create a Python virtual environment again。

 remember that the Python virtual environment isolates my code to a specific directory。

I always like to name whatever the project is that I've created in GiHub the same name as the virtual environment that way it's easier to remember so for example if I type in Git remoteotev you can see that the name of my project is called scaffold right so let's go ahead and create a virtual environment that's in my home directory that's invisible and that way I don't have to accidentally check it in as well so if we go through here and we type in Python3。

Dash M， this stands for module。Create a virtual environment。

 or use the virtual environment module and put this in Tilda， which is my home directory。

 slash dot scaffold。There we go， so this is a good convention to use so that you never have to remember what it is that you call your virtual verment。

 just call it the same thing as your gett repo。Okay， now that we've created that， I can source it。

And I'll go ahead and do that next。And the source that I would type in source， Tilda。

 slash dot scaffold。Been activate and activate is a shell script that activates the environment。

Once I do this， if I type in which Python you can see that it'll be living now in this directory。

 it'll be living inside of tilda slash dot scaffold bin Python 3。 So again。

 this is a really good best practice so that you don't have all these problems of there's packages that are conflicting with each other or the system Python has problems so in general always recommend you do a Python virtual environment now that we've got that set up。

 let's go to step two which is let's look at that make file and if we look at this make file we can do a couple things here first always make your make file use tabs because make files like tabs。

And then what I'll do here is I'll just cut and paste one that I've created earlier that's boilerplate and what you'll probably find is that you can use the same kind of make files over and over again in your project so a lot of times it's good to just copy it and change it a little bit from a previous project let me walk through what all of these steps are so the first step is that I would do a Pip install dash upgrade Pip Pip is the Python packaging tool that's actually included in a virtual environment notice if I go here and I say which PP。

It'll show that it's actually using the Python packaging tool in the virtual environment so that's yet another reason to use the virtual environment is that you get the greatest version of PIPS or the newest version that's installed with that version of Python I also like to install it though and with an upgrade so that I always get the latest version and then I use this requirements file to grab whatever packages my project will need。

Next， there's a format section here that allows me to format my code using a formatting tool called Python black。

 This is optional， but I like to do it just so that my code is up to standard next there's a L section and I use a tool called Pylin and I tell it to disable two of the warnings that are extra verbose these are recommended in configuration what it'll do is it'll only give me then warning and error messages。

 which is what I really care about and then I'll tell it to run the li on this hello pi file the fourth step here is testing so what I'll do is i'll use the pyt thirdpart library and I'll run Python in Py test give me some verbose output give me a little bit of coverage here and then run this test for this test code so that's really the basic structure and I would recommend this structure in every single project that you do so now that we've got that set up the next thing we can do is move on。

the requirements which will be the packages so I'm going to double click this and then now I could go back and decide what packages I want in my project so I would recommend probably just a few commands here that that I typically find or libraries that I find in most projects Py Lit as we discussed is a popular Linting tool an alternative would be Pflake or flake8。

There's also P test， which is the testing library， there's click， which is a Camulan tool library。

 there's black， which is the formatting library and P test Cove。

 which is a coverage tool that shows me。How much of my code has got covered So really these five packages I would recommend probably in all projects they're generally going to be useful I don't pin them and give them a specific number you know like a particular version at first。

 but later that could be a good idea if I wanted to specifically call out a very specific version of the library you could do that right here。

 but let's go ahead and save this。Now we're ready to go， we can do an installation。

 so this would be step one， let's go ahead and say make install。There we go。

 and then this will go through， look at the requirements file and install those packages as well as upgrading the version of PIP if there's an upgrade to be had。

And this typically will take you know let's say 30 seconds or so depending on what you've got in your requirements file perfect so that was pretty pretty quick here so the next step is let's move on to creating some code so I'm going to go to a hello file and from here a good one to start out with and it's probably not a bad idea to build the scaffolding out for every project is just something that kind of gets things going so。

I'm going to build a add function that accepts an x and a y and what it will do is it will return。A。

And x and a y， and then I can again basically print this out so I can say print and I can say。

 you know， this is the sum。And then put in。The and we'll put in。The X。And then we'll put in the Y。

 and then we'll put in the final result， which will be the function that's returned with X and Y。

 there we go。Perfect， so that looks like we'll be able to print this out here and notice that。

It may be by default here。We'll need to be told what the x and the y are and so what I can do is put in a x is equal to1 and y is equal to2 there we go and so this should kind of get things going here and let's go ahead and say Python hello dopyI there we go。

 this is the sum 1 and 2 notice that in this particular example I'm going to need to maybe get the result first so let's go ahead and say results is equal to add and then I also need to change this to plus。

And so then from here， we can see that x。And why will give us the result。

 And if to make it a little bit easier， I could actually say result There we go。 perfect。

 So if I go ahead and I run this， it should go1，2，3 perfect。

 So we've got we've got something going here and I have kind of a basic structure for my code。

 So now that I've been able to demonstrate that that works。

The next thing that I can do is actually get Lint working and so how would I do this well it's already built into the make file right it says Lint by Lint so I can just say make Lnt。

And if things are successful， oh oh it says redefining X from outer scope。

 redefining y from outer scope， so I was a little bit naughty here and I have some messy code so how could we actually fix this if we wanted to you know make things a little bit easier well what I could do is that I could actually change around my code so that Lint wouldn't have a problem with it so what are the ways that I could do this well。

One of the ways that we could do this is that I could actually say in this particular scenario here。

 instead of defining x and y， I could actually do this， I could say this is the sum。

And I could do this， I could say one。And 2。And then this would clean it up because I wouldn't specifically put that in there。

 I would actually put the numbers inside and now this would be acceptable because I'm not redefining those variables let's go ahead and run my make Lint here。

And notice now I cleaned it up。 So this is just generally a good way to make sure that you're not making silly mistakes in your code and it checks the syntax without me even needing to write tests So now that we've got that step up right so we've got step one and we've got step two here。

 let's actually run this format tool So I'm gonna to say make format and you'll notice what'll happen is it it'll clean this up So if I say make format。

There we go， it said。One file formatted and noticed that it made some extra spaces here and it basically just made it look a little bit more pleasant to the eye。

 So it' is an optional step， but I find it to be pretty useful。

 Now let's look at the last step here which would be to test our code。

 So in order to do that I'm going need to create a test file So go ahead and。

Look at this test file here and say from hello， so I'll need to import my other code， import add。

Next， I can say make a test statement， so I'll say test。Add。

And then it's actually pretty straightforward to test when you're using this pi test tool。

 I can assert that two values are what I expect， so I can say， for example， add。

 which we know will add two numbers together if I add one and two that that should equal three。

Right and and I'll need to say assert， I'll need to say assert。

 so basically make sure that when I put in one and two in here that it'll come back with three。

 so let's go ahead and do this， we'll say make test。

And there we go and I've got 100% test coverage now notice if I you know basically made an incorrect test that it'll go and fail there we go。

 we can say that oh oh looks like there's a failure here you know four doesn't equal three so I now have basically a complete setup where I can actually test everything at once and one other thing you can do with a make file that's kind of neat。

I if you wanted to， you could actually run an all statement and run several of these commands all at once to really simplify how you had set up a project。

 so if I said all I could say maybe I want to install this code and then I want to Li it and then I want to test it right so if we go ahead and do that if I say make all it should run all those at the same time。

Perfect， so in a nutshell this is a basic setup for a Python scaffolding。

 we've got everything ready to go locally and we're ready to later set up continuous integration so the final thing to do would be to push my code to GiHub so let's go ahead and do that so I'll type in Git status。



![](img/e46bf82c3bcc6004cd8231bbee24ed7b_1.png)

And you'll notice that there's four files here that need to be added。

 so because I have included that get ignore file， I can actually do this。

 I can say get add star and it'll add all four at the same time。And then if I type in get status。

 you'll see it are now green， so they're ready to be pushed now I'll go ahead and I'll commit this。

 so I'll type in get commit， which commits it locally， so adding initial structure。

And then notice that it's asking me to do some setup。 the first time you set up your project。

 you'll need to do this configuration， either in a file or manually like I'm going to do it here。

 so I'll go ahead and put my name。And then I'll put in my email address here next。

 let's go ahead and do that。Here we go and the main reason for this is so that you get good tracking and you know what's happening in terms of metrics in your project。

 which is a good idea， so I'll go through here and we'll run this perfect and it opens up to the default editor which in this case is nano and I'll type in a control key and then an O to write it out and then I'll do control X to exit and then from here I can push it and this has been committed locally but when I push it pushes all of these files to GiHub so it's go ahead and say get push。

And here we go。 How do we test this out， Well I can go back to Github。 And if I do a refresh。

 you'll see that all those files are located here。 So it's all set up for me to do a cloud based continuous integration。

😊。

![](img/e46bf82c3bcc6004cd8231bbee24ed7b_3.png)