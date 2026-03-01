# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P88：21_02_13_Rust Distroless PyTorch项目详解.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/8da4333d75f77755015994079029c0a4_0.png)

Here we have an architectural diagram of using a pretrained pytors model with rust。

 Let's talk through how some of the key advantages of rust combine along with pretrain models to build out a very compelling story for Mops To start with in this example。

 we have actics which is a web microservice that at one point in time。

 was ranked as the fastest in the world。 So you could say effectively。

 it's one of the fastest web services in the world。

 We also have the T C HRrs or rust bindings for pytorch。

 These bindings are very complete and give you access to the underlying py towards C plus plus infrastructure。

 So you have really a low level interface to the pytors library。

 We also can interact with excellent pretrain models for computer vision or natural language processing that are all ready to go with。

😊，Pytorch and some of the other things to consider for。

A production environment or logging right if you're going to be running something in production with millions of requests。

 you know， a month and you have maybe accuracy or business logic or other things you want to have info level logging。

 debug level logging exception level logging， all of these things will help you maintain the model while is deployed into production。

 a couple other things that are interesting to consider when you're dealing with a microservice or smoke test and unit tests。

 So the idea here with a unit test is it's going to catch business logic problems。

 So when I'm developing an application， I may want to write a unit test for a key component of the application that I'm worried about and develop a few different unit test and I even may want to build a unit test that tests。

 let's say the bindings to pipeywars itself just to make sure that the installation。

Was successful Also， a smoke test is pretty interesting because the idea here is that you could call the API endpoints yourself。

 maybe four or 5 or 10 or 20 different API endpoints， you could send a image， for example。

 and make sure that the prediction that comes back is what you expect and there's no errors these are really good ideas when you're building an end to end model like a machine learning model that you're serving out into production。

 So that's the local environment and what's great about rust as well。

 unlike scripting languages like Python is that the binary is all you need。

 other than let's say access to the underlying Pytorch do So。

Once you have Pytorch binary and you've got it all set up。

 what you can do next to make it even more efficient is to use the distreis Docker images and what's really nice about the distreis is that there are images that contain only the application in the runtime。

 So there's at least two key advantages here。 The first advantage is that there's less of a security hole right so you're only including your application in the case of Rus。

 you're only including the binary and maybe the Pytorch and pretrain model here。 And that's it。

 And you can keep a very tiny container image， and it makes it trivial to deploy to many different cloudbased services in a production environment。

 So this is really an ideal workflow。 Let's take a look at this Google container tool here。

 You can see here this is called distreist container images and this is available from Google container tools right。

We take a look at this。 Why would you want to use this。 Well。

 the idea here is that they contain only the application and the rundown dependencies and a few things that you can look at that are pretty cool is that these are tiny right。

 in the case of， let's say， a rust based commandline tool。 you could make one that was。

 let's say three or four mebytes and give that to somebody and you also could。😊。

Really be less concerned about some of the issues that happen with containers because you're only including the binary in a very tiny manner。

 So this is an ideal scenario here for embedding a pretrain model in rust。

 Now let's go ahead and walk through the code real quick and we take a look at this rusty deploy and look at this Rtorrch disk here。

 some of the things that we include in the project would be the cargo file this is where all of the dependencies are listed we also have the Docker file and you can see that unlike some docker files you'll see this is tiny right。

 this is just using from rust as build environment， we download by torch。

 we set some paths here I copy the binary here and then I put it into the dis list image and all I'm copying here is the pretrain model and some images for testing and then I set the environmental path and and I'm ready to go。

 So this is 30。Six lines of code。 and this is a computer vision model。

 and this is the nice thing about using language like Rus。

 It's just tiny when you're deploying this into production。

Also if we take a look at the source code here， we have a library， we have the logic。

 So really these are library type files。 we have a main file that invokes everything。 in this case。

 this would be the Acts web service and each of these routes is registered and then finally we have the routes themselves and you can see what these actually do in terms of the unit testing I have a test directory right here and then I have different kinds of tests。

 I have some fixtures as well， maybe an image to do a prediction with， I could include again。

 the bindings from the library that I'm using just to verify that the installation is correct when I'm doing a deployment。

 and when you set up this kind of a structure makes it really trivial to do an installation Now one other thing that I did like to do in installation step is if we click on this I actually created a small little installation script that allows me to bootstrap in environment so it makes it trivial to set up a new production deploy as well。

Here just does some setup commands， moves Pytorch around。

 And the reason for doing this is so that if I create many different versions of Pytorch in this particular repo。

 I don't have to copy huge Pytorch libraries over and over and over again。

 I can set it once and actually forget it。 So really。

 that's the structure here that we care about when we're thinking about building a pretrain model with rust and so many companies that need to deploy。

 for example， large language models should heavily consider this workflow。

 And of course I've done a lot of the heavy lifting for you。

 you can just take a look at this and go to rusty deploy and try to do this deployment yourself。



![](img/8da4333d75f77755015994079029c0a4_2.png)