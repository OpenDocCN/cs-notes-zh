# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p61 61_03_03_Python与Rust的GCP入门.zh_en -BV11y411z7Dn_p61-

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_0.png)

Let's take a look at the Google Cloud free tier here。

 You can see if you start up on the Google Cloud free tier， you have access to 20 free products。

 $300 in free credits， although you do need to use them within three months and some of the tier products include the compute engine。

 cloud storage， BigQury， Kubernetes， app engine， cloud Run， cloud build， stackdriver， file store。

 pubsub， cloud functions， Vi AI， speech tot， natural language API， Automle， etc cea， etc cetera。

 really there's just a ton of free tier services here， so let's go ahead and get started。

 I'm going go into the cloud dashboard right here， you can see an overview of everything inside first we have the project info and inside the project info you could decide for example。

 what it is you're going to to do in terms of adding people to the project configuring project settings。

Also， this dashboard here in the middle shows some of the services that are last accessed。

And then you also have a resources tab that shows different resources you could toggle to。

 for example， if you wanted to launch a virtual machine。

 and then you also have the status here on the right。

 so this is really the start that you'll be using most of the time when you're inside and notice that I have a project selected right here right here we have select project and if I wanted to create a new project I would go ahead and create a new project there。

What I would recommend when you first get started with the Google Cloud platform is to launch the Cloud shellll。

 so let's go ahead and do that and Cloud Shell is nice because you can immediately start building solutions。

 try out ideas inside of this Cloud shell environment。

 The first thing that I like to do is create a Python virtual environment so that I can test out Python projects and run them inside of Cloud She so I'm going to go ahead and do that first I'm going to say Python 3 M V E and V。



![](img/74c9f1d693ec3b729bef41d85bbf5cc8_2.png)

Then I'll put a virtual environment inside a hidden home directory。All right。

That was able to be successful。 And then what I like to do is edit my bash RRC。In this case。

 we go right down here。And I can just go ahead and say， let's source a Python virtual environment。

 source V E and V。And we can type in source。Till the V E and V bin activate。

This is a nice little trick here in that every time now I open up this environment。

 we've got a Python and virtual environment source which solves a lot of weird problems with Python and then if I wanted to go to a repo where I have some code in this case I have some Python code here and I go to HCPS if I don't want to push changes back。



![](img/74c9f1d693ec3b729bef41d85bbf5cc8_4.png)

I can go into this environment and I can actually just do a get clone。 So let's go ahead and do that。

 Let's type in get clonelog。

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_6.png)

And now I've got my Python code。 and if I Cd into this repo here。

We can see that I've got a test file， I've got some other things here。

 I like to do things with a make file because it allows me to have shortcuts and we can even go to the editor and take a look at the code。

 which is a nice resource inside of the Google Cloud platform Here we go we see inside of this directory we have a make file right here and you see I can do install test format Lnt container L refactor right so it's kind of got all of the things that are really common when you're working with the Google Cloud environment and if you go to a tutorial you're going to see something similar and so let's go ahead and go back here and let's test this out by just doing a make install and then a make L and see if this works。



![](img/74c9f1d693ec3b729bef41d85bbf5cc8_8.png)

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_9.png)

So if we go here， we say make install and this is going to go inside my requirements file and install all the packages perfect and once the packages are installed。

 then I can go through and I can link my code。 So this is a formula that works actually with any language not just Python and we can go ahead and see make Li。

And it looks like our code has been successful。 And you can even look inside of this file if you wanted to and look at the main and just see what's going on。

 very simple application。 Allright， so now that we've got Python working， Well， what else can we do。

 Well， we also can install rust So I'm going to go here。 I'm going to go to rust up， copy it。

 go to here and we just paste this can in and this will go through and download the rust environment。

 including cargo。

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_11.png)

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_12.png)

And the Lnter clippy。 So basically everything we need to be a rust developer。

 One of the reasons I like programming a rust is that it can have anywhere from you know，40 to。

 you know，1 thousand times better performance of Python， depending on what you're doing。

 So if you want to do high performance computing。 This is often a really good choice。 And again。

 it added it to my path。 And so if I go here， we can actually run cargo。

 So I can actually do another hello world project。 we can say cargo new， and we can call this hello。

😊，And this will create a sample directory here。And once I go inside， what's nice is unlike Python。

 I don't have to do any steps， really， I can just go ahead and just say cargo run。

If we say cargo Run， it compiles it in here's our hellello world。

 And if we want to take a look at the structure of that project。

 we can go through here and you can see here that it's a very simple hellello world file inside of cargo do2ml if I wanted to add dependencies right here like for example。

 the GCP SDK I could do it there so this is a good overview of some of the things that you are going to need to do as a developer And again。

 I think Python rustt or two of the options for programming that are really desirable so。



![](img/74c9f1d693ec3b729bef41d85bbf5cc8_14.png)

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_15.png)

The last thing I'm going to do is to onboard here is go to a virtual machine launch it and we'll take a look at that。

 so oh here we go， we see one is already launched right here if I wanted to create a new one I could go through here and say create instance and launch some type of machine for example。

 if I wanted to launch a micro instance you could see in fact the cost savings of what what I would spend would be right here。

 the monthly estimate and you can see that it's actually build hourly and I get a good overview if I wanted to go to a really large machine here and I take a look at this you can see here that in this particular environment。

For a $32 core machine， it would be $500。 So it is important to make sure you're looking at the different metrics here in terms of the machines you're launching。

 but since I already have one running， all I need to do is to interrogate it via the command line。

 And this is going to be very common when you look at the tutorial with the Google cloud is to look at really the command line overview of how to list the machine so。

I already have one in my history here and we can actually take a look at a recent。You knowCom。

 which is also a nice way to have shortcuts is just run history。

 and if I type in GCud compute instance list。There we go。

 We can see that I can actually control it so I can even launch things as well if I wanted to by using this base command。

 G cloud compute instances， and you can actually run help if you want to to get more information about a particular command so。

Really is a command line oriented service and so if you do understand the command line you're going to have a great experience using the Google Cloud All right。

 that's a good overview of where to get started and I hope you can go ahead and try these commands out on your own。



![](img/74c9f1d693ec3b729bef41d85bbf5cc8_17.png)

![](img/74c9f1d693ec3b729bef41d85bbf5cc8_18.png)