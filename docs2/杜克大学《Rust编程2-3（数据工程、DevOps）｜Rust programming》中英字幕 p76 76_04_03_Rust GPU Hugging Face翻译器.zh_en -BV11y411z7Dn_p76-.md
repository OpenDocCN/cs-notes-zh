# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p76 76_04_03_Rust GPU Hugging Face翻译器.zh_en -BV11y411z7Dn_p76-

![](img/f19a5deb674e6fded74f183ad3bd02bb_0.png)

One of the things I hear a lot about using rust is there's this kind of hesitancy about， you know。

 well， it's a newer language， even though it's been around since 2010 and maybe people are concerned about can it be used in the real world。

 Well I wanted to dispel a few things First， I'm going walk you through how to train models with Pytorch and invoke them using GPUus with the rust Py towards bys。

 And I'm also going to talk a little bit about firecracker。 So what is firecrackercker。

 it is a serverbased technology that powers AWS Lambda written by AWS。

 if I could imagine the biggest possible serverbased execution environment arm in the world。

 It's going to be on AWS they are the 800 gorilla of cloud computing。 And in fact。

 one of their most popular services is AWS Lambda and what is it written in is written in rust。

 And so I think that should dispel this idea that you can't。R in production is really nonsquiur。

 and I'm also going to show you why if you're going to build Pytorch。

 one of the technologies used to heavily consider is using the same kind of technology that can scale to millions and millions of simultaneous requests like Abus Lada。

And use a technology like rust。 So let's go ahead and dive right in and show how you can use Pytors with GPU bindings in rust Here I'm at the AWS blog post where originally on 2018 firecracker。

 a lightweight virtualization for serverless was announced。

 And you can see here that there's a bunch of really big benefits to it。

 you can launch a microvm in 125 milliseconds， it's battle tested low overhead open source project。

 right when AWs uses it to power a service like Lambda， you know it's a big deal。

 If I go over to the source code here， we can actually take a look at all of this production source code that's actively being developed inside of the firecracker microvm。

If I take a look at the actual architectural page here。

 you can see this is a very sophisticated service that's built in rust。

 And this firecracker scales to thousands of multitenant microvms on one instance。

 So it's an extremely efficient way to build a microvm。 Now。

 this technology is obviously well suited for inference。 And in fact。

 because we know that Pytorch has bindingine to rust。

 We can go ahead and use this powerful rust based technology。

 So let's go ahead and go to rust Pytorch GPU template here。 I'm going to go again to my codespace。



![](img/f19a5deb674e6fded74f183ad3bd02bb_2.png)

And what I'm going to do is show you how it's very trivial to use Pytorch with GPUs。

 And so if I go through here and I look at some of the different things I have here。

 we have a portable Pytorch is something I've been working on。 We also have a Pytorrch MNist。

Ass another one。 And if I go to the readme， we can take a look at some of the different projects that I've been playing around with。

 So let's go ahead and do this。 We'll go go through here。And we'll go to the read me。

 So we have at the very beginning here an exploration of those bindings。

 And if I want to do a stress test， this is kind of a fun one to play around with。

The first thing I'll do is Cd into this directory。 And if I just type in cargo run GPU like that。

 I can also open up another shell above here。

![](img/f19a5deb674e6fded74f183ad3bd02bb_4.png)

And what I can do is do Nvidia。SMI L1 and we'll see that in fact this GPU will get saturated in just a second and that's actually a fun way to really see some of the things that you can do there we go we're saturating this GPU by running this Ru code and if I want to take a look at the code itself it's not too bad。

 And if we go to this directory P towards GPU。Let's go to U and we look at the source code。

 It's a very small function， right， so just a few lines of code。

 you can actually target the GPU and play around with it， right。

 And this is really just copying the code that was from the main author。

 And then if I want to look at Iniist CI GPU， we could take a look at that as well。

 And if I want to C D into that one。

![](img/f19a5deb674e6fded74f183ad3bd02bb_6.png)

We can go into that and say INist CLI GPU。And what does this code do。

 We'll have a library here that says， you know here's my original code and then I can pull it into a command and execute it。

 Sos there's a very small amount of code here to get stuff working I think another example that I think is is kind of a fun one is this is the ability to actually train a model。

 And so let's go ahead and go to Pytorch MNT So I'm going to go up here。

I'm going to go to Pytorch Iniist。 and again， we can take a look at the source code just to see。

That is not too bad。 and we go to Pythtorch Imnsist and we look at the source code here。

 There's several different files here， but the main one that's important is the convolutional neural network here。

 and you can see here that you import those bindings you set up the structure to play around with a couple different iterations and then finally this is the part where I actually build out the neural network and then I go through here and I run my code。

 So it's not that much different and looking at Python code here。

 And if we want to go through and reproduce it all we need to do is just run this command and if we go through and we train it。

It's going to go through and run that run that convolutional neural network training job。

 And then again， we should be able to see that the GPU is being targeted while this is actually running。

 There we go。 We see it's been hit a little bit。 It should wake up in just a second。 All right。

 here we go。

![](img/f19a5deb674e6fded74f183ad3bd02bb_8.png)

We see this thing rapidly saturating the GPU， Go this thing cranking。

 and we' were able to train this model。 So it's really a pretty good。😊。

toolol for people that want to use high performance systems programming languages to train deep learning models。

 My experience with the Pythtorage bondings for rust is that they're extremely good。

 And you can see here that it also has this nice side effect of the packaging as much more simple than Python because it uses cargo。

 which really makes things very easy to play around with whenever you need to install something。

 you just use the cargo ecosystem and package together tools。 And finally。

 the big takeaway as well that's really fun about using Pytorch is you can make reproducible models。

 And a good example this， while this thing's running that I'll take a look at is there's something called Soos track。

 This is really an emerging trend here， which is that people I think are seriously considering how to actually package together models using portable formats like Onyx and actually put together tools and then give those tools to other people。

 And I think this is really the。

![](img/f19a5deb674e6fded74f183ad3bd02bb_10.png)

Of one version of MLops is to package your models together and actually distribute them to other people。

I would heavily encourage people to take a look at this， the more people do demos。

 the more we take a look at these kinds of examples with a system programming language like Ru。

 I think the MLOs community will deeply benefit from these kinds of Kamean tools All right。

 see you next time。

![](img/f19a5deb674e6fded74f183ad3bd02bb_12.png)