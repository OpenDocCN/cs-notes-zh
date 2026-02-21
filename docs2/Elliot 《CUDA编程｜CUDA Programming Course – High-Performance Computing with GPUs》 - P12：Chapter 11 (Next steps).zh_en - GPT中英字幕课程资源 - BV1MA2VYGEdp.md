# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P12：Chapter 11 (Next steps).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

![](img/a4063da9cdbb2b488ffb61a88b4b82bf_0.png)

Geaive yourself a pat on the back if you made it this spa。 It's pretty much the end of the course。

 You made it。 Good job。We're just going to go over some quick little。

Little tips points in the right direction。 if you want to continue with this stuff， you know。

 it probably was hard to grasp everything。 So I understand if you don't。But if you do。

 I have some extra resources support you。 So inside of the readme file here。I have a section on。

 you know， like what is unified memory and memory architectures， which I thought would be， you know。

 kind of useful and you might be interested in， but mainly what what I want to cover right now is I'm going to add to this。

 I'm going to add to this read file as well in the future。

 But there's this is a section on dive deeper。 And this is like if you want to take that extra step and really figure out how you can apply deep。

 deep。Deep optimizations and advancements in whatever you want to call in Ka and GPU programming。

 especially in deep learning。 This is， this is what you can do。

 So there's this thing called quantization， which I'm going to start with。 Quaitization is where you。

Is where you go from， say， FP32。And you go down to， say F P 16 or and 8。

You can you can actually go down， you can actually go from F32 to end 8。

 and you can still have really， really good performance and quality of the of the precision on models。

 right？ So there are specific ways you can you can do tricks around this。

But a lot of it has to do with， you know， if you're。If your range is limited， so if you。

 if you can hit like a maximum of say， like， I don't know。A 10 and a minimum of negative 10。

 then you don't actually have to worry about a lot of those exponent values， right。

 If your weights are initialized and your training is stable and nothing's going to go like above or below 10。

 you don't have to worry about it。 You could literally just cap that as your precision right。

 and that'll be the maximum it can go。Those will be like the sparse values right So quantization is pretty much just the art of doing that。

 which is like taking numbers that are really high precision and then moving them down to lower precision。

 doing really， really fast operations with those because I can tell you for a fact into 8 is a lot faster than F P 32 like not just by four times。

By quite a lot。 and we saw that in the Kublo versus Kublos Lt section。

 where we compared 32 B versus 16 bit， and the performance was pretty substantial。

So you can imagine what in8 would be because it's just integers。

 there's no floating point numbers to worry about there's no decimal places， right？That's just in。

 so。Aitization is pretty cool。 It's used a lot in current models like， you know。

 say G 4 or like Lama Lama 4 or5 B。 if you've heard of that one。

 like a lot of these actually use quantization， right。

 So most likely like B F 16 or like F P 8 or something like that。 Some of them even use float 4。

 which is cool。 And there's tensor cores， which I talked about already， but I can't。

 I can't leave it out。 Tensor cores are great。 I'm just not covering it in this because this is kind of like an intro kind of an intro course。

 So I tried to like pack as much as possible into into a certain amount of hours that you could。

 you know digest。 And then if you want to continue with that。 There's obviously Tensor courses too。😊。

Sparrssity is a cool one， so sparsity is。You can think of sparsity as if I have like an array。嗯。

See like。It'll be like 0，0，0，0。Negative 7。0，0。0，0，0。 And then say over here。

 we'd have like a like a six， right。This this is what sparse means。So there's a bunch of zeros。And。

There's an occasional， like very big number that represents a lot， right， based on its position。

 maybe based on its position relative to other numbers。

 But the idea here is that you can actually store these in much smaller memory。 So it's。

 it's more of a memory and compute thing more than just like， why is this。

 like what quality do you get from this。 It's really performance。

 So what we can actually do is we can say。You know， we're going to have two matrices。

 one with the values and one with the coordinates。 So we go negative 7。And 6。

 And then this other matrix would be。You know， zero，1，2，3，4。事实B。4our， and then5，6，7，8，9，10，11，12，13。

14，15，16。Right， and so you would end up storing only  four integers instead of instead of 16 integers and you reduce everything by a lot。

 Now， imagine this when you scale up to you know，2 d or 3D structures。

 You're saving like orders of magnitude of memory， and it can be really， really efficient， right。

 So this is something to consider when you're when you're designing highly perform neural networks is can we capitalize on things like sparsity。

 right， that might be encouraged by the， you know， the people who are writing the neural net outside。

 So when they're just writing the pitorrch architecture， if it favors sparsity。

 if it does really well with that And that's what it runs on， then this is really good for you。

 This makes your job easy。 But sparsity is just a performance hack， you you， take it when you can。

 right。Then there's this book， Kuda by example。嗯。That this literally just a book intro to general purpose GP programming。

 I found this off of a Google search。 So it's just like one of those E do websites。 And yeah， it has。

 it has a bunch of things in it。 So like。

![](img/a4063da9cdbb2b488ffb61a88b4b82bf_2.png)

CPs rise of GPU computing， right， a lot of what I covered like what is the coupa architecture。

Pretty much a lot of a lot of what I said or a lot of a lot of the a lot of the important parts in here are compressed out the course。

 right， So obviously not all of it is。 And I didn't。 I haven't read this book either， 300 pages。

Oh I haven't read this book。But。A lot of what you're going to find in here is going to be compressed down into this course。

Now。There's this other article by Simon， the guy who works at Anthropic。

On data parallel distributed training of deep learning models。

 So that other that other chapter where we were talking about getting getting a big。

Big algorithms to train across multiple instances。This。This is a good example of it。

So distributed training is' a big problem right now is getting like data centers into one compact place。

 there is research around it and helping reduce that distributed aspect。But when you have。女人。

When you have a massive data center of a bunch of models and you have to get them to talk a bunch of bunch of GPU。

 sorry， and you have to get the model talk to each other a certain way。 It's hard。

 right So this kind of goes into that。 I'm not going to go through this entire thing。

 but if this does go through more performance optimizations， things like all reduce。

 which are used for the actual optimization process。

 So you'll see like an atom W all reduce or something， there's a。Yeah， it's。

There is a lot to consider here， but I don't even have a cluster to train this on。

 so I can't really teach this part。嗯。We go back。 There's a few projects that I found that were really cool。

 One of them was Mnes Kuta， Er Kti and ensor， I did Ms Kuta， which was this。😊。



![](img/a4063da9cdbb2b488ffb61a88b4b82bf_4.png)

And then。This is the actual coD and N CoudD and N and Kubloss for training on the Ms data set。

 This uses， I believe， convolutions。 So if we like were to go into， yeah， see。

 it's like a visual studio code project or whatever。 So this might be easier if you're on Windows。

 but。Like， if you go into， for example， the。The network C++ file。Yeah。

I'm not going to dig through this， but this is a cool little project that I found。

 feel free to do whatever you want with it， but it it came up in the Github search results when I served for Ms Kuta。

 so。Do what you want with that。嗯。I'm not gonna go coude mode right now。

 That's I'm going to save the best for last。Micrograd kuda is very similar to micrograd micropathy。

So this is something I touched on earlier， and this is something you should review heavily or understanding how things like back propagation work。

So， it's pretty much like a。Like a， like a pieytorrch autograd， but very， very small。

 So if we actually go into the files for it， go into the micrograd files itself。

There's an engine for it。 So the values， there's like like a value thing for it。

 So with like with operations you can do like like a power。 So when you go double asterisk。

 it's going to call this underscoresponderers square power as a method， right。

And then the ad is this like same thing you have the plus。 and that's going all the the add method。

Then outside of engine， you have the actual neural net Py。

 which is like brings up all the abstraction of like going from neurons to layer。

 So you have like a single neuron with a set of weights in it that take， you know。

 all the different X values and then dot product and then output1。 That's a neuron， right so。

You know， it does like a do product there， and we can see that very clearly。

 and then there's you know， like a layer where it does a bunch of neurons。嗯。And then， it will。

And then it'll just like a layer of neurons， just like that， right。

 a bunch of neurons stacked on top of each other。 and then the MLP， which is like that layer。

 but there's multiple。That。嗯。And then microcrogra Kuda is just that but implemented in Kuda。Right。

 there had to be one， so yeah， feel free to like have fun with this and everything。

It's supposed to be faster so you can kind of just understand things on a level of compute unified device architecture。

There's， like operations， all the co operations。 So move to GP is like Malic and Mem copy。 You know。

 it's very simple interface。 You can imagine pieytor being similar to this。

Probably more performance optimal， but。嗯。You don't want to do like akuom M copy and a Malic every time you want to move something or use a piece of data。

 you know， you have the naive Ma kernel， of course。The 10 H kernel， right， all this。But yeah。

 so a bunch of cool project people are doing。And then there's this other interesting1 I found second。

 second best one， add GPU puzzles so you can use the Q Pi library go。



![](img/a4063da9cdbb2b488ffb61a88b4b82bf_6.png)

去排白咗。

![](img/a4063da9cdbb2b488ffb61a88b4b82bf_8.png)

So QI open source GPU accelerated computing with Python， sos essentially kuda。

 but you get to use it through a Python interface， which is awesome。嗯m。We go to the GitHub for this。

Cupal。Right。There's a bunch of cool stuff on this。You know。

 you would just import it and then you can you can make like shapes and stuff and do stuff with that similar to something like P torch or nu pie。

 right？Yeah， so these GPU puzzles are just like going through， you know。

 solving like essentially the logic problems where we had a kernel solve an issue for us。

 but doing that or a bunch of different examples， right， So instead of just matrix multiplication。

 there's like a lot of other things in here， which you might find fun to practice。嗯。

And then the last one， which I decided to save for last， is couta mode。So。They have have a GiHub。

 they have a YouTube channel。They have a Discord server。And。

Pretty much a bunch of this is it like actually contains a lot of material and beyond what I covered in my course。

 This one was more to be like video assistive， but the community behind Kuta mode is amazing。

 They have really， really good engineers and researchers here just like building cool stuff constantly people being super active in the community。

 It's a great place so。😊，This is something I'd absolutely recommend you check out。And yeah， there's。

 there's a lot of chapters like， you know， see， like flash attention， right。

 They have everything cutless， Triton， beed kernels， data processing。Tensor cores， right？

So a bunch of cool things， I'd recommend that you join our Discord server。

 you can find that or their Discord server。Here。Yeah， bunch of essentially。

B of cool bunch of cool groups and everything。 like begin。Right。Super active。Like today。

 the last message was， the last message was like， not even。W like a few hours ago。

And that's just one channel， right。 So you go down here， last message， what's like one hour ago。

