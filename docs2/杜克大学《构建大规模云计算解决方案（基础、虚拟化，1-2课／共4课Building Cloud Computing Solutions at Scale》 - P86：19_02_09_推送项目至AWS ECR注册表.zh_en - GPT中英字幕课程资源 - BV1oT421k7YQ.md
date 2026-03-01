# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P86：19_02_09_推送项目至AWS ECR注册表.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's dive into how to use a container workflow in AWS。 First。

 what we're gonna do is use our cloud 9 environment here as the core development place。

 and then we'll build our container and push it to E， which stands for elastic container registry。

 So this is a private cloudbased container registry。

 all major cloud providers have them in this case it's called Ecr。 Next。

 I'll spin up a second cloud 9 instance。 although this could be maybe a virtual machine or some other location on AWS。

 and then I'll pull that container and I'll run the exact code without needing to install anything。

 So really this is the power of a container is you build it in a development environment。

 push it to the container registry and then pull it into another environment。

 So let's go ahead and do that。 So first up what I'm going to do here is go to AWs and build a new container registry。

 So I'll go to E。 and say fully managed Docker container registry and then create a。

So let's go ahead and call this container。Scratch， there we go。

And I'll go through here and say create repo great so container scratch that looks like it works now to push something I would need to look at the push commands and you'll see these are all the push commands and I'll come back to those in a second。

 So next up what I can do is go back to my container that has a project that has a Docker file here。

That has this location and then it has the application source code。

 which is right here a very simple application， and that's all I need to actually push this to the ECR region so what I'm going to do is I'm going to step by step go through those commands so I'm going to first copy this and this will allow me to log in。

So go ahead and put that in there。Great， so now I've logged in next up。

 I'll build this container and I'll go ahead and copy this so we'll build this container。Great。

 so it uses a local Docker demon and then pushes that tag to that location。Great。

 and then let's go ahead and finalize the tag so we'll go through here and do this perfect and then next up what I'll do is actually。

G。Push the command exactly to the container so this push command here pushes it to that remote container location。

 so let's go ahead and do that。There we go。 So now this is going to push this locally built image into the Amazon container registry。

 Now while this is going， what I'm going to do is I'm going to go back to cloud 9 and I'm going to spin up a new one right So I'll go here and say create new environment and we'll call this pull container。

And there's this will be a brand new fresh environment I don't need to do anything I can just go through here say next step create environment and then this thing will spin up so while this is spinning up let's go back to the other project here and you can see it takes a little bit of time to push it。

 but one of the advantages of pushing it inside of。

A cloud environment like this is that it's got a very fast bandwidth between the cloud9 environment and the container registry。

 which really will save you a lot of time when you're doing container development and it's a huge advantage versus let's say you're on a laptop somewhere in another country or somewhere with bad bandwidth this is a great way to solve that problem because the network traffic is actually going between the cloud9 instance and the registry not between your local slow network connection and the remote location and AWS so that's a huge win there。

So it looks like it's almost done here， we'll just wait for this for a second。And once this is done。

 I'll be able to log into the second instance and then pull down that container image。Great。

 looks like it's pushed， so let's go ahead and go here and refresh this section。

So just the first thing that we'll check out here is that there's nothing on this local machine in fact you can see that's just a brand new environment and what I'll need to do is log into ECR to be able to pull the container so one trick you can do is you can actually just type in the history command and this will actually show you the last time you ran a command and I can take the login command here so this logs me in。

Right。And now all I need to do after I've logged in here。Give it a second。

Great is to pull that container locally， so what I can do is say Docker pull。

And then I'll need to change it to this comm in here， so we'll say pull this。

And let's go ahead and try this out。And so what this does is it downloads that container that I pushed earlier to this local machine。

 and then once it's set up， all I need to do is look at the readme file for how I ran it before。

And we can look at a command here， so it looks something like this and we'll just tweak it a little bit。

So let's go ahead and go back here and I'll maybe even put this into the read me so it'll be ready for us。

So I'm going to change this though if I scroll back to this command。Which will be this。Right here。

 so instead of it pulling from a remote location， it's going to pull from the private container registry right so this will take just a second。

There we go， so we've downloaded this container now to run it again。

 I'll just put this command together right here。And。We'll go ahead and do this。

There we go and we're able to actually run this locally and I can do it more than one time。

 I can say Jim。So the key learning here is that if we go back to this architectural diagram is that。

You can develop in one location， push those changes and another developer and your team can easily grab those changes and reproduce exactly what you did。

 or you can push it potentially to a production environment right here right so it's a great workflow for development and it's a new cloud native way to develop applications。



![](img/15d2df057afb669d5b5af3a28a9564c7_1.png)

![](img/15d2df057afb669d5b5af3a28a9564c7_2.png)