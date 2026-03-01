# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P96：29_02_09_Kubernetes演示.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Okay， let's talk through some of the key issues with Kubernetes and why it on one hand。

 has incredible power， it's essentially a cloud and a box it can run billions of instances each week at Google but that complexity also can cause problems and let's take a look at what a Kubernetes cluster really is from the onset you see that there's this large cluster here and where can this cluster run well it can run locally if you have Docker desktop installed and you've installed Kubernetes that's actually one of the simplest ways to get Kubernetes cluster running。

You can see that in fact， it also needs to create this Kubernetes master node with the Kubernetes API。

 so that's how everything works， that's how the cube CTL command is able to communicate with everything and then next up is this pod here and you can see that there are mini pods typically in a cluster and unfortunately there's even more complexity in that each pod can contain many different containers up until now we've been working with just this one Docker container but in a large scale system there's often going to be many containers located inside of one pod。

And then there will be potentially mini pods inside of one Kubernetes node and then inside of the Kubernetes cluster there's mini Kubernetes nodes。

 so there's a lot going on now why would you want to do this and what's the point well one of the reasons why you may want to have separate pods in a node is that potentially one pod contains your web application and you can scale it specific to those needs it could be you know maybe it has certain CPU requirements and then potentially another pod in a Kubernetes node could be maybe the monitoring and so you could have some monitoring that goes and sends it to let's say Prometheus or it sends it to stackdriver。

And potentially in a different system here， you could have a pod that has maybe a relational database or a specialized queuing system。

 so it's really a way to identify what components fit naturally together and it's not necessarily at the application level it could be from a resource perspective so let's go ahead and get rid of some of this complexity and walk through how to actually use Kubernetes on my desktop so I'm going to move this screen away。



![](img/1221bb00736995f02ab3d6e3ecefdd70_1.png)

And I'm going to briefly look at what the final project would look like。

Let's look at the structure here， you can see there's all the good things we've talked about。

 a Docker file， a make file， an app file Now one of the things that I typically do when there's a complex series of commands is I will go through and create a script here and so let's go ahead and look at one of these script I'm going to look at this run Kubernetes script let's go ahead and look at that。



![](img/1221bb00736995f02ab3d6e3ecefdd70_3.png)

And if you look at it。I I have to set a Docker path and again this is for a local Kubernetes cluster。

 I then have to run the cubeB CTL command and again that's the API。

And then it's really in a way similar except for in this case。

 I have to tell it which port I'm going to run on and actually label what the name of the app is Next up I run this command Git pods just to get a list of what pods are actually running and what's inside of them and then finally I forward the container port to the host right so you can see that is going to allow me to test it so first up let's see if anything's running so what I can do is I can say Q CTtl git pods。

This allows me to query and see， oh great。 I have this thing a pod running right and remember a pod can contain mini containers in this case we just have one and next up what I'll do is I'll see you know what about what port it's running on so we know that the app can we'll listen eventually on port 80 so let me go ahead and curl that or I'm sorry 8000 let me go ahead and curl that and see if anything is running currently。

So if I curl that you can see nothing's running so I'm not foring those ports。

 so let's go ahead and run potentially this whole script here so I'm going to go through here and do this run Kubernetes command。

There we go and now what you can see is that it is， in fact， this po was already running。

 so it gave me an error。But it did now forward this next port here right and so that's what this command is right here。

 So next up I can leave this in the foreground and I can open up a new tab。In this new tab。

 whyhy don't I go ahead and try to run that curl command again？

There we go and now you can see that in fact they've been able to expose that port so this this is one of the best ways to really experiment with Kubernetes is to in my opinion。

 put the commands into a bass script step by step play around with it and there was no way to hide it Kubernetes is extremely complex and emerging technology and it's going to take some skill to walk through and step by step figure out what's happening and the best way to do that is in the smallest possible environment so that you can limit the complexity of what you're doing。



![](img/1221bb00736995f02ab3d6e3ecefdd70_5.png)

All right， why don't you go ahead and do this on your own？



![](img/1221bb00736995f02ab3d6e3ecefdd70_7.png)

![](img/1221bb00736995f02ab3d6e3ecefdd70_8.png)