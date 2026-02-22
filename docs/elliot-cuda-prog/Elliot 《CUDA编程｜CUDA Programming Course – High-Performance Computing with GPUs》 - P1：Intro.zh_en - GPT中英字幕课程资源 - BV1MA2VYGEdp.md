# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P1：Intro.zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

Welcome to this coUa programming course where you will learn to leverage GPUus for high performance computing。

 The course starts with an overview of the deep learning ecosystem and guides you through setting up couta and reviewing essential C and C plus plus concepts。

 Youll explore GPU architecture and write your first couta kernels。

 Advanced topics include optimizing matrix multiplication and extending pitorrch with practical applications like implementing a multilay perception for the Ini data set。

 Elliot Olridge create this course。 So what is Ka or compute unified device architecture by Nvidia。

 My name is Elliot。 and I'm an instructor on freecodec。

 as well as a student studying for my computer science degree。 So in this course。

 I bring to you Kuta for deep learning。 But don't let that repel you if you're not in deep learning because there's still a lot that we're going to be able to cover。

😊。

![](img/ca297cf685558c5ae02d28f9929b4c4e_1.png)

And many other fields of parallel programming。 So this is more oriented for deep learning。

 but not specifically aimed at it。 There's going to be a lot covered here。

 So I'll show what the final project， what the final project is first so you can get a few forward and see kind of what we're going to end up building by the end。

 And then we'll just kind of go from there。 So before we get started with anything crazy。

 I should include a disclaimer。This course may not be fully up to date by the time you're watching this。

 If you're watching this 10 years down the line from when I've released it。

 it might not all be the same。 There might be things that are updated。

 The new compute capabilities might be， you know way better。

 there might be a bunch of different stuff happening。

 So I'm not too sure where the ecosystem will be added in 10 years。 But as of 2024。

 This is pretty much the best you're gonna get。 So just try to include that。

 And I thought I'd try to make everything not entirely centered around time。

 So you can go back into this version or certain code of versions and reproduce all the same stuff。

 It just might be a little bit different down the line。 if you're watching this later on。

 So why did I create this course exactly。 Well， a lot of these performance and kernel engineering jobs require a lot of knowledge。

 they require a lot of experience in the industry， And it's just really hard to get up to that point where you're able to compete with the top and the best of the best performance engineers。

 So these are the people that are writing the training runs for like。😊，GPT 4， GT5， all of this。

 you need a lot of skill to actually optimize a massive neural network training run and inference on a large data center or a compute cluster。

So this aims to prevent some of that manual weaving on your part。

 still encouraging you to do so on your own， but prevent some of that hardcore labor of going through and really figuring things out on your own from scratch。

 That's one of the reasons why I created this。 Another one is。Like generally speaking。

 the point of writing GPU kernels or playing with code at all on the GPU is to run something faster。

 So if you have a nested loop。 you know it's like 4 I range 4 J and range for4K and range。

 whatever however many you want to put essentially what parallel programming and couta allows to do is unroll those。

 So if you take like， for example，4 I range， you could take each little thing in that and run that instruction on a different couda core。

 So if you have 10000 couda courses and you have 10000 different iterations in your loop。

 then you can effectively do each iteration in a single instruction or a single thread on on the GPU。

 So this is some of the things it allows us to do。You're going use your job of you're going to use your knowledge of GPU architecture。

 kernel launch configurations and a bunch of other cool stuff we end up learning in this course to make that code run as fast as possible。

And then the last one is， really， there's so much data nowadays。 They say we have way too much data。

 but very little cleaned data。 I've taken everything from all the other video courses。

 everything on the Internet and YouTube。 And I put them in a single course。

 So I filtered out a bunch of the nonsense， a lot of， you know， the old stuff。

 A lot of the new stuff that maybe isn't covered as well。

 and kind of just projected into this one masterpiece。

So this includes topics covered by paid courses as well。 I haven't actually paid for them。

 but I kind of just looked at， you know what are the chapters that they cover and then include some of those important concepts in this course。

 I do have links for YouTube videos and all of these resources。

 which I've gone through only the high quality ones。

 but I've gone through a lot of these videos and resources and these are all going to be put in links inside of the Github link in the description。

 So everything you need is going to be there and I put a lot all of those links in that in that link。

So what are some use cases for Kuta， parallel GPU programming。

 What are some of the use cases for this Well you have graphics and ray tracing。

 so the computer graphics that you're seeing in video games， you know user interfaces， all of this。

 you have fluid simulation for like physics and modeling， you know engine dynamics。

You have video editing， so the video that I'm editing for this right now is using parallel computing to render crypto mining。

 which a lot of you might be doing already， that's going to be using you know your GPU hardware and some of the advantages of that to like mine through the crypto mining problems。

And then you have 3D modeling and software like blender。

 So when you have a bunch of different points going on and you have to render things。

 it's essentially the same as video editing， but just 3D instead of 2D so。The last one。

 which you probably guessed already， is deep learning。

 So the number one use case for couda right now is primarily what I'll be covering in this course。

 which is deep learning， so。We're not going to go as deep into like， say， convolutions。

 but to kind of understand how to optimize an algorithm like matrix multiplication。

 we're going to go quite in depth with that。So now you might ask Eliliot。

 what are the requirements or the prerequisites for this course。

 So there are some that are more intellectual and academic， and there are some that aren't so。

This is strictly for NviDdia GPUus in case you didn't catch on that earlier。 if you don't have one。

 you can always consider renting the cheapest ones in the cloud。

 I advise you to look into the pricing before giving a definite no on the pricing for some of these cloud GPUus At first。

 I was actually surprised how low the cost was for some cloud instances especially the noncompute demanding ones。

 So if you have like only a CPU or like a Ram intensive machine。

 It might actually cost significantly less than one with GPUus on it。 The GPs1 are still very cheap。

 you can use things like vast AI， which I'll cover a little bit more you can use this for actually getting really cheap consumer grade hardware that you can SSH into in the cloud and then just do all of your experiments and go through the course on that。

You can continue you can continue running with any you know NviIDdia， GTX。

 RTX or data center level GPU， so all of the NviDdia cards are pretty much supported for this。

 maybe like the lower ones that are like 15 years old。

 those might not work but generally if you have like a GTX like 1660 or something like that it's like it's going to be fine。

As for course prerequisites Python programming will help an understanding while we're implementing in lower languages so just understanding the whole programming concepts is really what's going to be needed here again。

 all these different languages is just like a change in syntax right you know we're going to use basic differentiation and vector calculus that'll make learning easier if you know it already it's really only required for intuition behind back propagation and some of the stuff we're going to use to build neural networks from scratch linear algebra definitely make your life easier by not having to learn fundamental algorithms from scratch so like if you're not really intuitively you know into matrix multiplication yet if you haven't really you know gone into that extensively it might be a little hard for you to catch up but matrix multiplication is very easy it's quite trivial in retrospect it's very easy to understand but just the intuition there and optimizing。

It might be a little hard if you haven't worked with it a lot already。Then if you really care。

 I would recommend just reviewing， you know matrix transpose， matrix multiplication。

 chain wheel from calculus， and then difference between gradients and derivatives。

 There's maybe a few more that I miss， but those are like the general ideas that you're going to need for going into this。

And then just the heads up， if you are on a Windows machine， this might be a little harder for you。

 So I do have a little setup guide on Windows hardware， but I do everything here on you Bundu Linux。

 So this is what I'm running just on my local machine here。

 and this is what we're going to go through the course with。

You can always use WSL on Windows to simulate a Linux system or you can use Docker。

 so Docker is an awesome tool thatll allow you to essentially fire up a little simulated Linux machine just in your terminal on Windows and you can just do everything through that I think it supports NviIdia GPUus directly through Windows。

 I'm not entirely sure yet haven't tested that， but if you're on a Windows machine。

 I would recommend WSL or Docker。If you do run into errors or issues throughout this。

 I do suggest you check Github， stack overflow， Invidia developer forums， Pytorch docs。

 If your issue is related to any of this course material。

 So you have a lot of resources at your disposal if you need to resolve an error that doesn't come up in the course material。

 you also have really powerful language models to use。

 There's a lot of language models that have been released recently that are really。

 really good at solving and addressing coding problems， So I do suggest you try those out if all。

 if all goes wrong， right。All the all the code and notes for this are kept in the Gitth repo in the description。

 The ecosystem is going to change all the time。 So in case this video isn't up to date。

 the Gitthub repo will be because I'm able to push that and actually make changes。

 So if something is little often here， you might want to go check in the repo and see like what it actually looks like so that you can actually write it properly and maybe there's a more optimized version。

 things will change。 but you get the point。I do suggest following the repo for maintaining a structured learning approach。

 I include xcalally draw diagrams， so this is going to help illustrate like high level ideas。

 how we're going to approach things as well as how to do things on the level of kernel optimization so all the way top down all of it Xcalally draw is awesome for illustrating things and it's completely free。

 So all the diagrams there will be included in the in the good of repo and in the course too。

You know， you can always reach out to me through my Discord server。

 which will also be in the GitHub repo and you can reach out to me through there and talk with the community。

 there's going to be a lot of other students learning。

 there's going to be a dedicated set of channels for this so in case you get stuck or wanted to discuss something or just have a cool chat in the server you can totally join that。

I do want to note early on that this course isn't on kuda only。

 So there's a few things that I cover outside of it， including pytorch referencing。

 going into like triton and C and C plus plus with like externally not including Kuta just to help illustrate things on how how the naive version of an algorithm works。

 But so there' there's the code side。 And then there's also I'm going to provide some prerequisites or not even prerequisites。

 but rather just a good understanding about the whole deep learning ecosystem。

 So this is actually what one of the next chapter is gonna to be about is how does the whole ecosystem work。

 And where can I apply Kuta。 It would be a little silly of me to say here's how you optimize a kernel and make it run really。

 really fast on your hardware， but not actually give you some solidd use cases for that。

 So you might already know what the use cases。 But in case you're just trying to learn couta。

 and you might look at some ways that you can apply it。 I provide that resource as well。

So spoiler alert， but some takeaways you might get from this course is that through experiment experimentation and research。

 you'll learn that the main GPU performance bottleneck is memory bandwidth。 So in deep learning。

 we have these giant inscrutable matrices that cannot fit into the on chip memory at once。

 So think about if you have like a giant cluster of GPus。 And each of them have really。

 really fast tensor cores， these are like super optimized for doing tensor operations in deep learning。

 But if you're doing these across many GPus。 you really have to exchange and mix and manage information between them。

 So you end up sending electrons。 you know， from this node to this node to this node to right。

 then there's a lot of this communication that's going on。

 So you really get a ton of speed from the compute inside of the chips。

 But when it comes to communicating， there's actually a pretty big bottleneck there。 And that's。

 you know， one thing that you might take away from this。😊，There's also on chip constraints， too。

 So you have like GPU V Ram， which is going to be， you know。

 actually comparatively slow to what the on chip stuff is。 So V RamM is like off the actual。

 you know， cores and all this。 And then it has to communicate with the cores and all of the the。

 the shared memory on chip and all of the registers。And that ends up being a bottleneck， too。

 So it's not just the， the massive。The massive matrices communicating across a lot of GPUs。

 it's actually a lot of the on chip communication too。

 So there's multiple bottlene that's arise rise or that arise。

 but these are just things that you'll end up coming across and being able to address later on through optimizations。

 Another key takeaway is would be to take an existing implementation and make it faster。

 So a lot of the times you'll see a new research paper come out and you'll see a really cool algorithm。

 but you might not know exactly how it works and so or you maybe maybe you know how it works and you just want to make it fast and you want to integrate it into Pytorrch for example So this is something we're actually going to do in this course。

 we're going to we're going to build up an algorithm and we're going to optimize it and then we're going actually port it into a Pytorrch extension so that you can call it in Python。

 which is super cool。 but just learning how to integrate your own research into things to make them faster to have it operate at production scale These are some really important things that you'll have to do。

😊，When you start working， you know， very deeply with Kuta， another thing is。Carpathhi's LM dot C。

 A lot of you haveve probably heard of this。 if you go search up LLM do C LLM dot C on not not on YouTube on Google。

 you'll come across a guy named Audrey Carpathy， and he pretty much built up a giant GT2 training run in C from scratch。

 So it uses C and Kuda and all of it。 And there's a ton of definite。

And I really felt like it's hard to understand that at first， you know， someone who's not like super。

 super enriched and having done Kuda for like 20 years。It's kind of hard to understand that at first。

 so having a really nice basis like this where you can actually understand how to use Kuda and where the real benefits are from it and how to use it。

 that will allow you to read and approach Carpaththeus LLM。

c a little better So that was one of the reasons why actually made this is to make it easier for people to go into LM。

c and understand what's going on。

![](img/ca297cf685558c5ae02d28f9929b4c4e_3.png)

So in the Github link and the Not document inside of my Github repo。

 you will see this in the intersection。 So just a bunch of cool videos on how Kuda works。

 how transformers work， a bunch of just really cool fun videos to you know。

 really get you motivated and upbeat on all of this。 So got some technical stuff。

 We've got some fun videos by fireship。😊，But generally speaking。

 these are some cool resources you can check out Kuda programming。

 Kuda mode is a really good server actually I highly recommend you join this。

 It's just a discord community of a bunch of people who are really into Kuta so I believe Andrich orpathhi is in here a bunch of really cool know coders is a bunch of engineers are in here just discussing how to how to get certain kernels working and generally just kuta stuff hence why it's called Kuda mode right So really cool server I highly recommend you join that as well as my server。

 which is also in the Github repo but that's。

![](img/ca297cf685558c5ae02d28f9929b4c4e_5.png)