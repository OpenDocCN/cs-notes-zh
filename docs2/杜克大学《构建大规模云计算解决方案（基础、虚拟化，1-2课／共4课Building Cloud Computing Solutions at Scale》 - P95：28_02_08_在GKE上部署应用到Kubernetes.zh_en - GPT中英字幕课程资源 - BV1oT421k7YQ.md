# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P95：28_02_08_在GKE上部署应用到Kubernetes.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go into the cloud and run Kubernetes on the Google。

Kubernetes engine or GKE first what we're going to do is create a shell by launching Google Cloud Shell and then we'll provision a Kubernetes cluster once we provision the cluster。

 we'll talk to the container registry called Google container registry and we'll push out an application back into this Kubernetes engine cluster。

Once that's done， we can expose the port and have a lowbalance application waiting for us。

 So just a reminder of what Kubernetes cluster looks like。

 it's something quite large right so you would create this abstraction here where there would be a cluster with a master so that would be what Google Kubernetes engine is doing and it's controlling these nodes and these nodes have multiple containers inside and so a pod has multiple containers and then inside of the node there's multiple pod so it's a very complex structure that can scale up and down and that's really what we're doing here by provisioning this Google container engine and also allowing Kubernetes to run in it。

 so next up what we'll do is go to the Google cloud here and kind set things up so really the first step in running something on the Google Cloud shell is to set the proper compute zone So we want to know where' working will work in。



![](img/8321873a59c9af27744d9bb00637460f_1.png)

![](img/8321873a59c9af27744d9bb00637460f_2.png)

Central region。Great， once that's set up， then I'll create a cluster and this will take a little bit of time to create a cluster here。

 it'll take a few minutes， so we go through here and we say cloud container。

 actually G cloud container cluster create， and we'll say cloud for data there we go。

I'll go ahead and authorize the Cloudhell and then this will go through behind the scenes here and set up the pod。

Set up the different parts of the architecture and again it's a very complex system that's being provisioned for us。

 but fortunately we can interact with it at a very high level because of the automation around the API。

Okay， great， so we have our cluster running and you can see the key items here where here's the name。

 the location in the central region， we also show the version of the master software the IP address of the master node the machine type and the node version and the number of nodes so there's three nodes running and again if we go back to this diagram here you can see here how each of these nodes could contain mini pods which also can contain mini containers。

 so let's go back here to authenticate now so if I run GCud container clusters create that would create it。

 but what I want to do next here is actually authenticate to this environment so I can control it so I'm going to type in G cloudud container clusters get credentials and then the name of my cluster which is cloud for data。



![](img/8321873a59c9af27744d9bb00637460f_4.png)

Great， so that looks like we're set here and the next thing I'll need to do is deploy an application so let's go ahead and do this。

 so I'll paste in this command cube CTL， create deployment hello server image equals GCR。

 and then the name of the image so this is the actual container registry right here。

 so this is where you would need to point things if you're deploying them to the Kubernetes hosted service。

All right， that looked like that was very straightforward next up here what I can do is create a service and this service will create a load balanced environment so that I can handle traffic and it will scale up and down for me and I'm going to expose it via port 8080。

Perfect， now that that's set up here， what I'm going to do is I'm going to look at the output of Git service。

Cub CTL get service， if you notice here that look the external IP address is pending。

 that means it's still provisioning this load balanced environment it's not yet ready to be exposed to the outside world。

So if I run this again。You can see it's still pending。

 so I would need to keep refreshing this until it gave me an external IP address and once this external IP address is available。

 that means that I can actually access that service。



![](img/8321873a59c9af27744d9bb00637460f_6.png)

There we go， so now our service is available and you can see that its the external IP address is 35。

222。100。99 and this is the external port which is port 8080 so let's go ahead and take a look at that service。

We'll put this IP address in here。Put in 8080 and you'll notice that there we go。

 I'm able to run this service。 So in a nutshell， it's fairly straightforward to run things with Kubernetes as long as you're using a high level abstraction in the cloud。

 and this is one of the key advantages of cloud computing。

 Now the final step for us here would be to delete the cluster。

 So what I'm going to do here is run a command that will delete this and we'll say G cloudud container clusters delete and will put in the name of our cluster。



![](img/8321873a59c9af27744d9bb00637460f_8.png)

And yes， we do， and now it's very important to note that if this was a production environment。

 you want to be very careful about just you know ad hoc deleting clusters back and forth。

 but this is a sandbox environment and I want to delete it。There we go。

 so I have now cleaned up the Kubernetes service。

![](img/8321873a59c9af27744d9bb00637460f_10.png)