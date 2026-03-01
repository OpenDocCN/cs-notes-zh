# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P83：16_02_04_Docker概述.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/e828f909ea36c7a7e7790f2f1175f66f_0.png)

What is Docker， this is a great question that is a very common question when you're first starting out with containers and Docker is a particular product that's composed of both Docker desktop。

And Docker hubub So you can see that Docker desktop here is really an application that installs on your computer and it's for a local development workflow。

 So this Docker desktop will have a container runtime that's one key component it'll also have developer tools that allow you to do things like launch Kubernetes and configure different stacks to go up and down and then also there's an application。

 So there's a gui that you can control things and then as I mentioned before it can interface with Kubernetes and you can actually launch clusters and control them inside of Docker。

 So really it's a local development workflow。 Also there's Docker hub which allows you to check things into a public or private repository Also you can automate the build of containers via Github you can pull and certify and use certified images So for example。

 you can take the official version of a database and pull it down and you know that the developers that created。

That database where the people that certified it also there's teams and organizations。

 so this is a lot more of a coab kind of environment。

Where the Docker desktop is the development environment。

 so let's dive a little bit deeper into this Docker desktop here and talk about a little bit so one of the things that you'll see when you're using a Dockerbased workflow is that you'll let's say first start off with using something that's from a core developer so even though I have many years of experience with Python the Python core developers are much more knowledgeable than me and I would like to leverage their knowledge of Python by pulling that base image down into my file right here so you can see that when I develop a Python project I say from Python 373 and what that does is it leverages the core developers knowledge of Python which is much greater than mine so let's say there's 100 years of experience that I could never recreate in my lifetime they've run all the correct Bsh commands。

The build commands and I can just leverage that right of my project then what I do is I create a new composite project based on that original base image and then push those changes into my private Docker hubub repo what that means is that I could then if I wanted to pull that out and let's say test it out in the cloud。

And run that new project or potentially it could give that to some new developer for onboarding and that new developer could you know use my code and deploy it。

 So this idea is very similar to let's say， source control except for it's the runtime itself just like a lot of times people will leverage the power of a library from an expert developer you can leverage the power of a runtime from an expert developer。

 So that's really Docker in a nutshell and you can see the Docker format file here is really the key takeaway。

 So next let's actually dive into looking at Docker in a desktop itself and see how that guI tool works。



![](img/e828f909ea36c7a7e7790f2f1175f66f_2.png)

Let's dive into how Docker works itself on a OS 10 machine。

 which will be similar on any operating system。 If I go up here。

 you can see that there is a menu bar that shows me that Docker desktop is running and Kubernetes is running as well。

 This comes as part of the Docker installation。 If I want to look at further things。

 I can click on this dashboard and it gives me some more detailed controls over everything that's running in the Docker environment。

 So one of the things that I can see here， for example。

 is that Docker has some images that I can use if I want to， I could pull one of those up。

 for example， look at and inspect it， run it so it's got controls I can start it。



![](img/e828f909ea36c7a7e7790f2f1175f66f_4.png)

And additionally， one of the things I can do is if I go back here to my Docker desktop environment and I go to the settings menu。

 I can also configure。

![](img/e828f909ea36c7a7e7790f2f1175f66f_6.png)

Different options。 So maybe I want to start Docker desktop when I log in。

 let's say I'm doing a lot of active development， or maybe I have limited resource on my on my machine。

 So I don't want to start it。 That's what I typically do。And also under resources。

 I can configure what options I want for my machine， so I happen to have a fairly powerful machine。

 so I have told Docker that it can use 16 of the 32 CPUs I have available and it can use 50 gigs of the 300 gigabtes of Ram I have available。

And then I could go through here and change other parameters like swap or disk size。

 So this would be a way where you could customize your local development environment to allow you to have more or less control a few other things as well with Docker is you can actually map Docker containers to physical locations on disk and also you can configure other options as well like Docker image you could tell it how you wanted to launch the Docker image and then also you could tell it what experimental features you want。

 So for example， more cloud experience or a fuse file system also with Kubernetes。

 which is included here， you could see whether you want it to be enabled by default or not and then also whether you want Docker to deploy to local Kubernetes cluster So in a nutshell again it's really a development environment plus a GuI and this GuI has many different options for you to configure。



![](img/e828f909ea36c7a7e7790f2f1175f66f_8.png)

![](img/e828f909ea36c7a7e7790f2f1175f66f_9.png)