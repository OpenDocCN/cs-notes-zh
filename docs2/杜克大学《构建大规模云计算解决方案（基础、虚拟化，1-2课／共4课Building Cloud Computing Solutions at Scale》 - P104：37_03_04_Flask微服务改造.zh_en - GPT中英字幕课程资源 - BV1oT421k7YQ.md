# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P104：37_03_04_Flask微服务改造.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's walk through a realistic microservice step by step。

 So what we're going to do in looking at this project is see that there's an application file for a flask application。

 there's a test file， an installation requirements TXT and a make fileile so to run this and get this set up I'm going to scroll up to the feature called Codespaces in Github。

 and I'm going to build a new codespace。 So this is very similar to let's say Vi Studio code or AWs Cloud 9 or Google Cloud shellll or Azure Cloud shellll。

 It's a place where I can execute code in a Docker container， so I'm going to select new codespace。

And go here and look for that flask change microservice and go ahead and create a new repository。

 so again this can work on any cloud platform or even your local laptop just for this particular demo I'll be using GitHub codespaces。

Okay， so now that this codespace is set up， what I'm going to do is look through each of the parts of the application first up here。

 I've got a application right here and inside this application。

You can see that it does very specific task so I have from flask import import flask I have Jsonify and it has a change piece of code that's pretty straightforward to look at it all it does is take an amount in and gives us the proper change and so in fact that can even test this out and returns the result here by using my terminal here to test interactively the code and notice that it created a virtual environment for me so I'm going to go ahead and source that I'll say source Python3 virtual environment activate。

Great， okay， so that's been installed for me。 And so what I'm going to do is say make install。

And notice that this make install command， all it does is look in my requirements file and installs these packages。

 so let's go ahead and do that make install。Great， okay， those are all set up。

 So the next thing that I'm going to do is interactively query this thing。

 So I'm going to install Pip install。Of i Python。And this will allow me to basically test out this function first to make sure I understand what it does。

 so I'll type in I Python。And going from。App import change。

And you'll be able to see what this does if 5。134。It just gives me back the correct change if I put in some other amount。

 we'll say $2。56 you can see it gives me back a different amount right so it's a highleve API that all does just like a normal microservice is it does one thing make change and then it returns back to this value so let's test out how this service works if I scroll down here you can see that I create two routes the first route is just a hello world route and the way we do this is we say app dot route and have a slash and then hello here。

And noticeice that it says I can make change of this route and then a dot route change dollar cents。

 This takes two parameters， a dollar parameter and a cent parameter。

 and it just passes that into that function that I test it earlier right and it converts it to a float and then it returns back my result so I can test this out locally here So how do I do this Well I can just say Python。

Apt PY and this will run this application in foreground mode on port 8080 notice that this particular development environment allows me to test it out so I'm going to go ahead and say open browser。

And it's going to forward this to this location。 There we go。 We can see that it says change。

 So now if I want to test it out， I'll say change。And I'll put in the same thing one。

And then the parameter 34。And we can see that it in fact。

 made the correct change and returned it back as adjacent payload right so it's a fully functioning API now if I want to try a new value。

 let's say $5 and 89。It gives back a different result so in a nutshell you can easily test out microservices by。

 you know， this is only let's say less than 50 liness of code here by using both i Python to test out the pieces of code。

And then also running it locally Now one thing I'll also show you is I built a small test here and this small test here just ensures that the core logic of my code works so I can go ahead and run that and I can say make test and you can see that I've got test coverage and if I say make L we can see that I've also passed the L so I've got all these things working by using this really simple microservice architecture。



![](img/abd6fdb4592b86a9f001cf2a023cdc94_1.png)

![](img/abd6fdb4592b86a9f001cf2a023cdc94_2.png)

![](img/abd6fdb4592b86a9f001cf2a023cdc94_3.png)