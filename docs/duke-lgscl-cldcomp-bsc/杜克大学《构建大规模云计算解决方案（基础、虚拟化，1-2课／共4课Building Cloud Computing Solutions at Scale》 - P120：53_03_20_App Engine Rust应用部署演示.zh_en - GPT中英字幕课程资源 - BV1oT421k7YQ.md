# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P120：53_03_20_App Engine Rust应用部署演示.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/2db2b5617642e0efe1098497dd52340c_0.png)

Here we have an app engine environment， and I've configured it so that it is going to tell me about how to run other environment。

 So this flexible environment， what I'm going to do here is actually use the rest language to deploy a microservice with this particular app engine framework。

 So what do we do First up， I'm going to go ahead and make a directory called web docker。

And I'm going to see the into it。Next up， I'm going to need to create that particular config file for app Engine。

 So let's go ahead and do that。 I'm going to go ahead and touch a file called app Yaml。



![](img/2db2b5617642e0efe1098497dd52340c_2.png)

And this app dot Yaml is important because this is how we tell app engine what it is we're doing。

 So we're going to say runtime。And we're to say custom。 And then we're going to say E And V。

 we're going to say flex。 And that's really all we need to do， other than。

Creating the files for a rust project。 So in order to do that， what I'll do is I'll type in。

Cargo in it。And then for name， I'm going to go ahead and call this， we'll say equals。Web Docker。

There we go and then this created the cargo files here。

 So next up I can just paste in some things I have from another project inside of here。

 let's go ahead and add the dependencies right there。

I'm also going to go ahead and add the Docker file， which has everything we need for it。

 Let's go ahead and do that next。 So I'll say touch Docker file。

And we'll just paste in the Docker file here， and you can see that what it does is it uses the rust builder。

Uses Deie and Buster slim as a target， and it makes this smaller version of the build process by putting the binary inside。

Next up， what I'm going to do is build out the source code。

 So we'll create a lib file inside of source。Here。😔，And。We'll go ahead and add that end。Here。

Let's go ahead and do that。 Per。 So this is just a random fruit generator。

And for the main file as well， I'm going to go ahead and do my routes for my web service。

 and we'll just go ahead and grab this。And go ahead and put that in。 great。

 we got everything cooking here。 We have routes like a health check version。

 we have we have all them registered。 And then again， if we look at the cargo file。

 we've got our dependencies at this point， what I like to typically do is also throw in a make file and a make file it can be nice because it just helps things orchestras and。

It keeps really a log of all the different actions that I need to take。

 So we'll go ahead and put that in there perfect now from here。All I need to do actually。

 is type in cargo run to double check that it even works。 so let's go ahead and do that first。Okay。

 now that we've got this running to double check it， I just go to the web preview。

 And if I say preview on。

![](img/2db2b5617642e0efe1098497dd52340c_4.png)

![](img/2db2b5617642e0efe1098497dd52340c_5.png)

This port， there we go。 It says welcome random fruit。 And if I want to， I can actually put in。

You know， different routes and check out other things if I want to， but in a nutshell。

 we've got everything working here inside of this application。

 So the next step would be to go to app Engine again and let's find that command。

 which is G cloud app deploy。

![](img/2db2b5617642e0efe1098497dd52340c_7.png)

![](img/2db2b5617642e0efe1098497dd52340c_8.png)

![](img/2db2b5617642e0efe1098497dd52340c_9.png)

All right， so we're here and one of the things that we should do is also delete the target directory so that you don't check in those files and then we also need to set the GCud config build time out and we're going to set it to 1600 because it could take a little bit longer。

And once we've done that， all we need to do is go to app deploy and it'll deploy the reason for doing this is because it is a longer compile process and it'll take a little bit of time to deploy this application Now all we have to do is wait and once it's done。

 it'll be deployed into production。

![](img/2db2b5617642e0efe1098497dd52340c_11.png)

And when you're finished， you can also see how other types of languages help you with the app engine deployed process。

 for example， in Python， I could select the official runtime Python 37 or if I wanted to do automatic deployment。

 I could even add individual steps by adding a cloud build。

 yaml file So the idea here is that it's a very flexible environment for doing deployments and you can easily switch from language to language either rust or Python go。

 it has lots of options available for you and it all starts with the shell and the shell then turns into a continuous delivery process depending on what kind of technique you want to use。



![](img/2db2b5617642e0efe1098497dd52340c_13.png)

![](img/2db2b5617642e0efe1098497dd52340c_14.png)