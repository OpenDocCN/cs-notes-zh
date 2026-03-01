# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p159 70_04_05_容器应用的打包与发布.zh_en -BV11y411z7Dn_p159-

Package and release our project。 We want to we know we can containerize it no problem。

 but we want to make sure that we're building the container and we're releasing it and we're sending it over to a container registry in this case。

 we're going to rely on the Github container registry。

 So how do we do that for our little project here。 We're going to do that with automation。

 That's right。 we're going to go here and we're going to say new file。



![](img/a56098a698338f88508e83288cd3b34b_1.png)

And our new file is going to say we're going to say Docker registry。

That Yaml and we're going to start building building our Yaml file here。

 we're going to say Docker image C perfect and we're going to do we're not going to do on push because we don't want on every single push but we are going to say only we're going to say only on a workflow dispatch right we're going to do this manually you can definitely put this on every commit or whenever you have a tag and all kinds of different things so workflow dispatch is fine and then we're going to say jobs。

And here we're going to say release that's going to be our job。

 and then I'm going to actually copy pastees and I am going to give you a little bit of like save you from seeing me type absolutely everything here So what is it that we have here we have we're setting up well we're getting our code as always。

 we're setting up build X。 this will bring in all of the tools that comes from the Github action for working with Docker in a normalized way。

 all of the tools that we will need。 we will log in to the Github container registry。

 what does that mean well Github can also has has its own container register where we can build our packages and put them there。

 Now in your case this might be Dockerhub， but like the same the same concept applies we will have to in this case we're specifying the registry in this is GHC data。

That is the actual domain for the GiHub registry， the Github actor and token are actually required that's the username and password to authenticate to the Github container registry for my account。

 The beautiful thing is that this wouldn't change for your account because these are abstracted away and again that dollar sign and double curly brackets that means these is a variable。

Moving on on line 23 and 24 were actually lower casing the repository name in my case。

 it doesn't have upper casing， but I always leave that there because the GiHub container registry does not like things that are camel case with certain words capitalized and other it' not everything has to be lowercase Finally we built and push the container registry So now you can see here that I'm doing push push is true and the tags which is how we identify where is this going it's going to be GHC that I owe the repo is going to be the name of the repo that is available for me from the environment。

 I'm retrieving that name in this case is going to be Cicd rust which is the name of my project here and the Sha1 or the chat2 56 I think it is is the commit the commit check on that's going to be my tag this could be if you're actually cut in or release this could be like an actual version like 001。

Something similar that is relative to semantic versioning。

 but the last thing is going to be that it's going to use the Docker file， the router repository。

 So if I save these and commit and push create。Docker Docker automation and I'm going to do that and commit and push and then once I do that。

 we should see these on the project so let's go to the project All right so if I go there and go to actions you'll see that I had to make a commit I had the invalidbal syntax because if I click here you will see right now that I had some some syntax problems and with a my Yal that's something that you have to be aware of so if I click here now you will see that there's a Linting there's some annotations so that's the Docker check as you know。

 but we don't want the Docker check right we want to have the Docker image C。

And let me show you before like the C Docker automation。

 like what happened so that you can take a look。 see， you have an error in your Yal syntax。

 I fixed that very quickly and push it again。 you don't need to see exactly well all of the things that I have changed to make this work but it is something to be aware of because you might get into the problem as well So I'm when I run the workflow manually and this is going to take a while because it will have to build the image from scratch and then push it to the registry All so this is running release is running if I click here again。

 we'll have to wait。 you'll see it's building everything is pulling all of the layers and then it will build our container and push it to the Github container regitry let's wait until this completes and come back and verify everything is working correctly All so this is completing we've been successful there you go it took about three minutes and 32 seconds Now before this was successful I was getting for3 for billion daddies because Github made changes recently。



![](img/a56098a698338f88508e83288cd3b34b_3.png)

![](img/a56098a698338f88508e83288cd3b34b_4.png)

Youll have to go to your settings in general and then go to actions， find general again。

 and then scroll the way down and workflow permissions。

 You will have to add read and write permissions。 Otherwise。

 you won't be able to push to your packages。 So if we go back all the way to the top back to CicD rust。

 which is this project。 Now you will see that I actually have a release。

 That is our package here and CicCD rust now can be pulled as a docker container。

 So there you go that is a fully fleshed out end to end。Deployment， packaging。

 LinkIn and everything else that needs to happen for this Ru project to be properly containerized and deployed to container registry。



![](img/a56098a698338f88508e83288cd3b34b_6.png)