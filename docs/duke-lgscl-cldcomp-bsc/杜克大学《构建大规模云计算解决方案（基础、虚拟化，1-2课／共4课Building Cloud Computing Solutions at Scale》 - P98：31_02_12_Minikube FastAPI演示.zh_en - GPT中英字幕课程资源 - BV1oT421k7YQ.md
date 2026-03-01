# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P98：31_02_12_Minikube FastAPI演示.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/c3d52efe9f385ef3020a310450688bf6_0.png)

Here I have a Github repo that has a fast API microservice inside of it that has a container file as well。

 Let's go ahead and take a look at the structure。 In this， we have a main dipyy。

 and this is where the main microservice code lives and I also have logic built into a directory inside this directory。

 I have a couple of functions here。 I have something that will randomly give me different fruits。

 I also have a little bit of logic。 You can build up as many pieces of logic as you want。

 and then incorporate it into routes。 At this point as well because I'm using fast API。

 I have access to slash docs， which is a swagger implementation。

 This allows me to look at the API endpoints and experiment with them without having to have a UI built。

 Finally， we have a Docker file right here， which is great。

 and this allows me to containerize my application and push it either into a container registry and let it run。

😊，Inside of the container registry， or also I can run it locally with Kubernetes。

 or actually I could push it to another system like the cloud and push it into a cloud based build system and run it in the cloud based environment。

 Finally， if I wanted to， I could do low testing。 So really。

 this is a high level overview of what we're going to build。

 So now let's go over to Github codespaces。

![](img/c3d52efe9f385ef3020a310450688bf6_2.png)

I actually have the same application running right here and if we take a look at the source code。

 you can see here these are the initial imports essentially boilerplay code and in fact I have a little bit of code here as well that sets up the base model so that I can use it for an endpoint and if we scroll down here we have a default route I have some random fruit that I grab and I also grab the ability to search Wikipedia endpoint In this case this would allow me to look for different names and potentially in this particular post request I could also grab information about a player or I could grab keywords as well from Wikipedia so I can add as much logic as I want Here's a calculator。

 this is more of a show app here just to show the different kind of things you can do。

And then finally， I run it with this command right here。 So if I go ahead and run this thing。

 I I just say Python main。This will run fast API here locally。



![](img/c3d52efe9f385ef3020a310450688bf6_4.png)

And you can see here that， oh， there we go running on port 8080。 If I click on a browser。

 I have a hello world， And then if I go to docs， we can see the swagger documentation。

 which is useful to experiment with my application。 So， for example。

 if I wanted to get a random piece of fruit， we would execute。

 and you can see that it returns back in orange。 or if I wanted to go to a different route。

 For example， I wanted to。

![](img/c3d52efe9f385ef3020a310450688bf6_6.png)

Search Wikipedia， for example， and look for something I could put in a request body here and look for a term like Obama。

Here we go， Ex。And we see that Barack Obama is one of the results here。

 so I could do any kind of query that I wanted to inside of this endpoint。



![](img/c3d52efe9f385ef3020a310450688bf6_8.png)

Now， the other thing to keep in mind here is that。Now that I've done this that I have this Docker file local and this allows me to containerize it。

 Now I could just build it locally the container and then push the container image over to a registry in fact。

 if we take a look at Docker hubub here one of the things that we can do is take a look at a container that I've actually put here previously I logged into this environment here and I was able to push this container into the Docker hub。

 Now the nice thing about this is that it means that I can pull it down and run it whenever I want。

 So if I wanted to look at the public view right here。

 I just run this command and I can run the exact same thing that I ran before。

 but I don't have to worry about installing any packages。 so that's one option。



![](img/c3d52efe9f385ef3020a310450688bf6_10.png)

![](img/c3d52efe9f385ef3020a310450688bf6_11.png)

The option that we're going to explore next year though is actually to run this inside of Kubernetes because Kubernetes can orchestrate an ecosystem that is around containers and we could also run the same thing using Kubernetes in a cloud-based environment。

 So I'm going to go ahead and click on the readme here and let's go ahead and follow the instruction。

 So the first thing that I'll do to run this is I'll say mini Cuubbe start。



![](img/c3d52efe9f385ef3020a310450688bf6_13.png)

Okay， now that Min cubes started， let's go ahead and add the metrics server here so I can get additional metrics。

Great， and then what I can do is look at the dashboard。

 And what's nice about this is it lets me see what's going on with my application inside of Kubernetes。

 And this URL tag or option allows me to go and log directly into the dashboard。 So it's got a。😊。

Start for a second and then once it's launched， I'll get this URL。Okay。

 the next thing that I'm going to do is I'm going to create a deployment using my。Registry here。

 so I'm going to go ahead and run this command， which says cube CTL C deployment。

 hell low fast API dash image registry， and I put in the registry of Docker Hub。Here。

 and I put in the location that I listed earlier。 so this location right here in Docker Hub。

 I just use this to actually be the target that I'm going to pull a deployment from。And so oh。

 it already exists， a， so we've already got this deployment running， which is great。

 and now all I need to do is go ahead and run get deployments。There we go。

 We see that that fast API deployment is already running。And then similarly。

 in this particular scenario， I would go ahead and expose。The service and says up， look。

 it already exists。 So if you've already run it。 you've already set it up。

 then you'll get either a start or you'll get in this case， and already exists。

 And then if I wanted to view this， all we need to do is go here and say cube CL get service hellello fast API。

 and we can actually see this particular service。 the last step here that would be fun to try out is to do mini cubebe service hellello fast API URL。

 and this will give me the URL， then I can actually preview。 So if I hover over this。

 I can select follow the link。😊，And this will allow me to。

 inside of GitHub codespaces play around with this particular application。



![](img/c3d52efe9f385ef3020a310450688bf6_15.png)

Now， if I wanted to make sure that this service is running pretty easy to do。

 I could run the curl command and this will show me that in fact。This service is up and running。

 There we go。Hello， fast API。 Allright， so what would would we do to clean this up？ Well。

 pretty easy。 I can run a cleanup command by doing the cube C TL delete service。There we go。

 I can also delete the deployment。

![](img/c3d52efe9f385ef3020a310450688bf6_17.png)

And then finally， I can stop Min cubebe。