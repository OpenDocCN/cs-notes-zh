# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P74：07_02_03_容器与虚拟机对比.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's talk through containers versus virtual machines。

 This is a common source of confusion when someone's just getting started with cloud computing。

 When do you use a container， When you use a virtual machine and what's the difference Well let's dive into that。

 Well first off in terms of a VM which we'll put right here， a VM has a host operating system。

And it has a guest operating system。 So let's say you're running abuuntu Linux as the host。

 you could have a guest operating system that runs， let's say red Hat Linux。

 And then inside you have some kind of application running on this guest operating system。

 So that's really the key version of a virtual machine is it's a full operating system cloned any run application。

 So what is this suitable for So really monolithic application are really the way to go for a virtual machine。

 let's say you have let's say a PhP content management system or a web framework that's been around for 10 years and it's already working。

 well， you can convert it from a physical machine by cloning it and putting it into a virtual machine。

 So really they're great for lift and shift or legacy applications。

 right So those are the key differences of a virtual machine。 Now let's get into a container。

 What's the big difference。 Well， one of the big differences is that again， it has a host。 but。

The runtime is what's important for the container。 It's not an operating system。

 It's a subset of the operating system。 So it's a lot more like a process than it is a operating system。

 and only the files necessary for that application to run or actually packaged in the container。

 So as a result， they are a lot more lightweight。 So they're smaller， they're faster。

 And in addition， their Devops best practice compliance。

 So what this means is that they fit really well with continuous integration。

 they're also they fit really well for microservices where that's where the small comes in。

 So the key difference between a virtual machine。And in this case， this is the container over here。

 is this portability aspect of it where virtual machine really is a copy of everything。

 and then a container is a much smaller version that's packaged and that fits well with the concept of continuous integration or continuous delivery。



![](img/9e824ba297fc0b0ac76b380b8166a737_1.png)

![](img/9e824ba297fc0b0ac76b380b8166a737_2.png)