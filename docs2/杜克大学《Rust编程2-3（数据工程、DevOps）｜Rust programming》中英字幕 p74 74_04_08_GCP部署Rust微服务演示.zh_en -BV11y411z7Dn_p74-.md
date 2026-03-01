# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p74 74_04_08_GCP部署Rust微服务演示.zh_en -BV11y411z7Dn_p74-

![](img/15ceb8e07cf2394b2553faa998b5cbd7_0.png)

Here we have a repository that has a rust microservice that's already been built inside。

 And you can see here when it's deployed。 It will look like this。 There'll be a cloud run interface。

 Therell be a microservice。 and we're able to access that microservice。

 So what does the architecture look like for this application to start with。

 we have this concept of a continuous delivery of a containerized rust microservice on the Google Cloud platform。

😊。

![](img/15ceb8e07cf2394b2553faa998b5cbd7_2.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_3.png)

The code will live in Github， Any change that's made will be triggered into the GCP Cloud build environment。

 which in turn can auto deploy into the containerized container as a service cloud run application。

Here you have rust， which is a microserv framework that is able to do low memory high performance compute。

 And we're able to push this constantly as it updates into production。

 So that's what we're going to build。 Let's go ahead and get started。😊。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_5.png)

What I'm going to do is I'm going to go to this cloud shell， I'm going to select open Ed。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_7.png)

What's nice about the editor is it has some customized capabilities that allow you to easily build a cloud run microservice and test it out locally。

 If we select this icon right here， Cloudcode， notice that there is a cloud run icon right here。

 We have to authorize once we authorize it will go through here and allow us to build out a new application。

 Let's go ahead and select create new cloud run app。😊，Next step， what I can do is select a template。

 It doesn't really matter because we can change the code I'm going to select go for now since it's the closest to what I'm doing。

 and I'm going to go ahead and say create new application。

I also can change the color theme if I want， which often can be a nice habit to get into if you're used to using one color or another。

 I'm going to go ahead and select the dark theme and go to new terminal。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_9.png)

Now that we've got this set up here， all I would need to do is just clean this up a little bit in order to modify it so that it runs the rust code so I can go and select the things I want to get rid of。

Which would be these directories here。 we also could get rid of the go code since I'm not going to be coding and go go and we can go through here and clean all that up。

 And it looks like we're pretty much ready to go here。

 And so what I can do next is go over to my application and just cut and paste and put things inside。

 So first we have a Docker file。 I'm going to go ahead and copy that code and paste it inside of this repository。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_11.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_12.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_13.png)

There we go， we'll change the go Docker file to a rust Docker file and notice what we have here is a very simple build process that is able to create a binary and push it into a slim container and expose something from port 8080。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_15.png)

Next up， what I'll do is I'll also get the source code so we can go to the source directory and do Lib and main。

 Now， an easy thing to do for a rust project is to just run cargo。

 And so let's first see if it's installed up。 It's not installed easyy to fix。

 all we have to do is go to a rust up and with rust up。 we just do a one liner here to install it。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_17.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_18.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_19.png)

Perfect， and rust up is a way of installing rust into a terminal based environment。 You can see here。

 it's very good at。Getting this done quickly， it's a very efficient process。

 And once the rust ecosystem is installed， all I have to do is type in cargo new and then do a knit So we'll go ahead and do that。

 Let's source this environment here。 All we have to do is type in cargo a knit dash name It will type in web Docker。

 So this will initialize a project structure locally perfect。

 Now I'm also going to create a lib file here in the source。Touch source。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_21.png)

L Rs。And now that we've got those two files here， what I can do is go back to my project and just grab the code that I had before。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_23.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_24.png)

And it's always a nice way to do installations is to first test it somewhere get it working。

 you can see here the server code is pretty straightforward is there's some imports。

 I have some web handlers here， and in this case it returns back a health check aversion， etc cea。

 a random fruit， and then also if I want to go over to the lib directory which returns the random fruit。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_26.png)

We can also grab that right so a very simple straightforward rest application that we're able to use Now。

 the only other thing we need to do with rest is also grab the dependencies which are in cargo do2 Ml。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_28.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_29.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_30.png)

Inside of here， we just grab these， we can do raw。

![](img/15ceb8e07cf2394b2553faa998b5cbd7_32.png)

Grab those inside and we'll go in and paste those into the cargo file。 And that's it。

 And once you've done that， all you have to do is just type in cargo run and it will go through and install all the dependencies and run the web microservice。

 And once you've tested it locally， the only other thing you need to do is actually go to the deployment process and do a deployment。

 Now， how do you do the deployment pretty straightforward。 We go ahead and we select this。

 we can say。Go down to cloud run here and we can actually select this icon right here。

 which says upload to cloud Run。 Let's go ahead and select that。

 It's going to go okay upload and then it's going to go through the process of analyzing the workspace building the containers application and then pushing it into production。

 what it's done， you'll be able to see again， you go through the wizard。

 do all the things that it asked you to do the next step here will be that it will deploy a service that looks like this。

 and then you can actually curl that service and let's go ahead and take a look at that if we go to cloud run here and and we take a look at that service here。

 notice here here we go， it's up and running I can copy this And if I wanted to if I open up a new terminal。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_34.png)

I can actually do a curl command and you can see that it's running right a production service。

 and if I type in you know fruit， it'll get a random fruit here and return it over and over again。

 So very straightforward process to do this you know containerized microservice type process with with the Google Cloud platform again。

 it all starts with GiHub you keep your code in there。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_36.png)

![](img/15ceb8e07cf2394b2553faa998b5cbd7_37.png)

Later， when you want to do continuous delivery， you can hook up the cloud build process to do continuous delivery and it'll push it into production。



![](img/15ceb8e07cf2394b2553faa998b5cbd7_39.png)