# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p24 -24- L19_ GPU Architectures (Spring 2025).zh_en -BV1iV1XBWEJW_p24-

![](img/00f85e609c5e524ebfc4fb5264a656cf_0.png)

Thats wake。这概有一。🎼Yeah。Can you hear me good。Is it good， you can hear okay。快来了。Okay。没有了。哦我是。我哋做。我。什么。嗯。

我这。🎼，🎼Yes。没。Okay。Everything is good， right still？Okay， let's get started。

We're already at lecture 19 I calculated and I think we have 25 lectures this semester。

 is that correct？It used to be 26， but I think one of them is eaten up by one of the holidays。So。

The good news is we still have some interesting things to cover and today is probably the last lecture where we will cover execution paradigms we've been covering a lot of execution paradigms。

 we've been very procentric and then we're going to move to memory today we're going to cover GP architectures but this is just a reminder of what we've covered so far in terms of execution paradigms we looked at some irregular paradigms like data flow。

😊，That is good at extracting irregular parallelism， supersscale execution， VLIW。

 they're all very good at extracting irregular parallelism in different ways。😊。

And then we talked about systolic arrays， switch to accelerators， regular parallelism。😊。

And then we talked about SD processing last time， which I'm going to continue a little bit today and give you some examples from both real systems and the importance of memory in SD processing。

 which you had seen last time， butre we're going to cover a little bit more and then we're going to jump to a special case of CD processing。

 which a very interesting case and a very successful perhaps the most successful case of CD processing in。

😊，Computing， which is GPU architectures。 How many， How many people know about GPUs there。

You're aware of the existence of those things， who doesn't know about GPUs， existence of GPs。

It's okay if you don't know that's okay， you know， so GPUs are graphics processinging units。

 but they're used for many things other than graphics today。

 any kind of parallel computation that fits okay， so this is why I find really fascinating and exciting because these are very interesting paradigms they're all employed in real systems today and then sometimes their combinations of it are employed as we will see today。

😊，Okay， but let's these are the readings that you have seen last time。😊。

And we were covering SD processors， I'm going to finish SD processors first and SD processinging is all about exploiting regular data parallels。

 you basically specify many operations on different data elements using a single instruction that's the idea single instruction operates on multiple data right if you remember the taxonomy of computers that we discussed last time we were looking at SMD I'm not going to go over this again。

 but we're going to look at MIMD also multiple instructions operate on multiple data elements to introduce some of the processors that are designed today。

😊，Okay， in fact， you have seen MID before like fine grade multi threadding is an example of MID right you use a single pipeline and that pipeline is multiple different threads are interleaved on the same pipeline such that there are no instructions from the same thread at a given cycle in the same pipeline you don't need to do dependence checking。

 you don't need to do branch prediction etc that's an example of a MID processor。

 multiple instruction multiple data meaning yeah multiple instruction streams executing on the same pipeline GPUs are like that GPUs are actually MIMD processors but each thread actually is a SD operation as we will see or each set of threads。

😊，So these different paradigms are combined in existing systems in various ways and novel combinations of it can actually lead to novel architectures that can do things that are not capable with today's architecture。

 so it's good to think about this， it's good to exercise your critical thinking skills。😊。

But let's review what SD is a single instruction operates on multiple data elements and mean I've seen two let's say purest distinction of two different types of SD processors。

 array processors and vector processors if you look at they all execute code a single instruction works on multiple data elements vector registers if you remember from last time in this case four data elements the difference between the extreme ends in the array processor you perform the same operation at the same time on different data elements on different processing elements as you can see all loads on the four vector elements are done concurrently and then you do the ads and then you do the multiplies and then you do the storage if you look at the same space you use different operations whereas a vector processor。

😊，Changes the space time compared to an array processor。

It's not as difficult to understand as spacetime in physics if you know what I mean in astrophysics。

 it's a little bit easier， but I think the concepts are actually somewhat transferable at some point。

 but if you look at a vector processor， what you do is you start different elements of the load in consecutive cycles。

😊，And you start the next operation on the first element after you start the first load。

 meaning you perform same operation。At the same space。Where is different operations across time。

 right， does that make sense？Hopefully， that's clear。

So basically the benefit of this is your functional units don't need to do all of the operations at the same time。

 you can have a single functional unit， single load。😊，Which can be only doing loads。

 You can have another ad unit， which can be doing ads， you can multiply units。

 which can be doing only multiplies。 and then pipeline the start of different operations at different cycles。

 Hopefully that makes sense for it。 So you can see that the vector processor is more frugal。😊。

It doesn't need a processing element that's capable of doing everything。😡。

Or it doesn't need a processing element that's capable of doing the same operation concurrently at the same time right it can be a pipeline processing unit a ray processor is a little bit more expensive。

 but it has a little bit better parallelism as you can see because you can actually finish all four operations in this particular case in the same cycle okay。

😡，Modern GPUs， as we will see， is a combination of both。

 you do both array processing and vector processing because an instruction specifies many operations on many data elements。

😡，You have some width of number of elements， we' call it lanes as you will see。

 you have some processinging elements that can be can execute the same operation in parallel。

 but then instruction specifies more operations than the number of processinging elements you have so you do array processing and then pipeline the array processing over time。

😡，Okay， this is fun to think about， but you'll see this better we also talked about memory banking。

 this is really important because if you look at this， especially if you look at an array processor。

 for example， you're doing four loads at the same time right for memory accesses concurrently if your memory is not able to satisfy this concurrently then you have a problem even in vector processing you need to you need to be able to start one。

😊，Load from memory at a given cycle， so every cycle you need to get one data element from memory。😡。

And we have seen this last time on SD architectures and we actually went through code where you figured out how long it takes to get the eight elements。

 assuming you have memory banking， right？😊，So we have seen bank memory and we divided memory into banks such that they can be accessed independently。

😡，These can be completely independent assuming you have completely parallel data buses That is not the case in this picture in this picture。

 it's a less expensive memory。 more expensive memories have completely independent banks where you have different data buses。

 different address buses going to each of them and that's extremely parallel that's good for array processor This is more of a vector processor type of memory where you divide the banks banks share address and data buses to reduce the pins to the memory chip assuming this's a separate chip you want to reduce the pins because pins are actually expensive。

 pins are input output ports to a chip and these are actually really expensive because you need to they need to be big they need to be very power hungry so that you can drive the data out of the chip or into the chip through the interconnect。

Those are some of the most expensive structures that you have in a chip。😡。

So you want to minimize that， so if you have this sort of structure each bank can start an access every cycle。

 but you can send an address to a bank or you can send only one address to a given bank every cycle。

 meaning you can start one access in bank zero in cycle zero。

 you can start the next access in web one in cycle one。😊，Nextback access in bank2 and cycle 2， etc。

 right assuming that's what you want， right？So this means that you can sustain and concurrent excesses if all and go to different bankss。

😡，Makes sense so this is very important because if all N don't go to different banks。

 you'll get what's called a bank conflict， meaning that you started one access in bank zero。

 the next access also goes to bank zero so in to wait for the bank access latency you cannot get the data every cycle right if you want to sustain a throughput of one data element per cycle coming out of memory you'd better start one access to a different bank every cycle and have enough banks so that you can sustain that throughput。

😡，Hopefully this makes sense right we have seen that last time again with some examples if you have any questions you can go back to those examples that's why memory systems is extremely important so GPUs put a lot of pressure on the memory system because they generate a lot of accesses in parallel that's why some of the most expensive memory systems that we have today are actually present in GPU systems you may have heard of for example high bandwidth with memory high bandwidth memory operates based on somewhat similar principles lots of banks over there so that you can actually get lots of accesses started in parallel in fact concurrently so that you can complete lots of accesses in parallel so that you can satisfy these many loads that are happening concurrently in the same cycle okay now you know why we need these expensive memories in GPUs right。

Okay， we'll see more of that。Okay， so this is the review kind of from last lecture。

 let's talk about some issues here， I'll start with some memory issues。😊。

So you've learned about stride， stride is the distance of elements that your program is accessing in memory right if your stride is one consecutive elements are locating consecutive locations。

 if your stride is four， the first vector element is that location zero。

 the next one is that location4， et cetera， et ceter。😊，Now， if you're strip and bank count。😡。

Are not relatively prime to each other， then you may likely get bank conflicts。 So for example。

 if my stride is 16 and I have only 16 banks。😡，And if my memory is laid out such that every 16th element goes to the 16th bank。

 you always access only one bank， right， then you have a problem。

So laying out your data is important right essentially our goal is to in a vector processor。

 our goal is to sustain one element per cycle throughput。😡，And for this to happen。

 your stride needs to be relatively prime。 What is relatively prime means the lowest common divisor of two numbers that are relatively prime to each other is one。

😡，Basically， they don't divide each other except for going down to the one right， for example。

 if my stride is one and I have 16 banks。😡，I don't have a problem， right， straight one is nice。

Now if I strta 16 and I have 16 banks I have a problem as I said right because these divide each other at 16 right so it's very difficult to allocate data nicely or you need to do something special to allocate data such that you don't get bank conflicts that I discussed。

😡，Okay， you can keep doing the calculation right if my str is three and I have 16 banks。

 that's also okay， three is a prime number and the lowest common division between three and 16 is one。

 right？😡，That sounds good so you can do many， many interesting things Okay let's take a look at an example why does this matter give you a very concrete example we're going to look at a matrix and matrices can be stored in different ways one way of storing a matrix matrix is a two dimensional array as we know row major storage means consecutive elements in a matrix row are laid out consecutively meaning in consecutive memory locations or in consecutive memory addresses in memory。

😊，Column majors is exactly opposite， consecutive elements in a column are laid out consecutively。

In consecutive address syn， we are going to look at draw major matrices。

 but call major you can think about also。Essentially， when you're if。😊。

If your matrix is laid out row major and you're actually accessing consecutive elements in a row first。

 your stride is one， right？😡，But if you want to start accessing consecutive rows。

 meaning consecutive elements say column， if your matrix is laid out in a row major order。

 your stride will become different， we will see that as an example soon。😡，Yes。

 does it make sense to somebody。确实。If the first one is kind of change the second one you can you can potentially do that。

 but then the problem is， what if you want to access the other matrix， the second matrix？

As the first multiplier later in therov wise order。Exact。

 it's expensive to shift this is called matrix transposing transposition of a matrix。

 and you may actually have hardware units to support that， but we're not going to get into that。😊。

Okay youre thinking ahead that's good so let's take a look at two matrices A and B stored both in memory row matrix order this is matrix a you can see that the rows these are the consecutive addresses the base address is a0 the first element is at index0 after a0 so a0 plus0 the second element is a0 plus1 a0 plus2 so you can see that the consecutive addresses in a row are in consecutive locations in memory and then the column when you go to the next row it becomes a0 plus6 if you will and the second matrix looks like this also very similarly except it's just a bigger matrix and you do a multiplication the first one is a four by6 matrix the second one is a6 by 10 matrix so you get a4 by 10 C matrix when you multiply these two which I'm not going to show。

😊，And the way you do multiplication is you take the dot product of each row， which is a0。

 essentially with each column of vector B， so the first dot product is a0 B0 that becomes the first element。

😊，Of the C4 by 10 matrix。 Now， let's take a look at the strides when we do this。

You first need to if you have a vector processor， youll need to load a00 into vector register v1。

 that's called V1， it could be any vector register and to be able to do that each time whenever you access memory you increment address by one to access the next column。

 right？😡，That makes sense next column in the role。Now your strto is one。

 this is nice excess of a stto one。Now this is nice， as we discussed。

 Stride one is nice because prime it's relatively prime to every number。Okay。😊。

But you still need to have enough banks to sustain the number of parallel operations you want。

 of course， if you have only a stride one and if your memory latency is long。

 you still need to have enough banks to cover the memory latency。😊，Yes。

 makes sense to the prime number is as the。Number of banks。 That's a good idea。

 We'll get back to that。Okay。How do you do that is another question but that's one of the ideas to make things relatively prime but let's take a look at load Bs column0 to be able to do this dot product you need to load Bs column 0 into vector register v2 now when you do that you can see that each time you increment the address is by 10 right because the first element is at B0 plus0 the second element says b0 plus 10 B0 plus 20 etcter now your str is 10。

😊，Now you can see that you have a problem over here right you have different strides whenever you're accessing memory either concurrently with these two loads or load D itself accessing with a stride of 10。

 even if you have 16 banks at some point you'll get bank conflict because your stride is 10 and the lowest common divor between 10 and 16 is something you can calculate which is two I think。

Okay。Okay， so hopefully this is clear now the problem is not easy to solve because you want to eliminate the conflicts as much as possible。

 so as we discussed for example， you can lay out be and column major order。😡，As you suggested。

 such that it looks like this element is 0， this element is one， this element is 2。

 this element is  three， this element is4， this element is5， that sounds fine。

 it will solve this problem the stride will be one when you access when you access this matrix B in this order。

 but if matrix B becomes the first multiplant in some other multiplication now you go through the matrix B row wise and you're back to the same problem your stride is large when you go from the first column in the first row to the second column in the first row right。

😊，So it's a matter of basically how the are how the data is laid out and how you're accessing the matrix and theres no perfect solution to this。

 that's why sometimes machines have transposition units。

 you transpose the matrices so that you can actually try to get we reduce the bank conflicts as much as possible okay so basically the question is how do we minimize bank conflicts and you suggest an idea which is not a bad idea actually one solution is more banks。

Add more banks， this will help you。More ports in each bank that could also help you right that way。

 even if you have a bank conflict， you have a different port to satisfy things。😡。

Better data layout to match the access pattern， this is not an easy thing to do and who does this is a question is's not always possible as we kind of discussed earlier。

😡，Better mapping of address to bank Ken this is kind of similar to what you said。

 but you can also have a prime number of banks， but then how do you lay out the data on the banks becomes an issue so having a number of banks that's true to the power of N is nice because you can divide your memory address space nicely。

But people have actually proposed more randomized mapping using prime numbers， prime hashing。

 et cetera， such that you get an address， and then you run it through a deterministic function that randomizes the mapping between an address to a bank。

😡，So that you minimize the conflicts as much as possible so that's a mathematical problem and there's a beautiful paper that talks about it and many processors today。

 including GPUs have this sort of randomization functions。

 they're relatively simple randomization functions but the goal is to reduce the bank conflicts reduced the probability of two accesses go to the same bank again leave you with this beautiful paper from Bob Rau if you remember Bob Rau he was one of the developers of the VIW processors and he also worked a lot of memory systems because in VIW memory systems is also a problem memory systems is always a problem and you can read that beautiful work if you're interested。

Okay， now we've covered bank conflicts， There's a lot more to come on this because we're going to start memory starting from tomorrow and the remaining five lectures。

 actually five， six lectures， I think right， if I'm correct， Yes。

 six lectures will be dedicated to the memory system。For this reason， well partly for this reason。

 at least， because memory is so important。Okay， now let me go back to array versus vector processor if you as I said earlier。

 array versus vector processor distinction is really a purest distinction most modern S processor are really a combination of both they exploit data parallels in both in time and space as opposed to only one。

😊，GPUs are a prime example that we will soon see， but remember this was the array processor。

 this was the vector processor， array processor executes the same or different operations at the same space and same operation at the same time。

 vector processor executes same operation at the same space but different operations time at the same time。

😡，Okay let's take a look at how we can combine them This is a vector addition you're adding a B vectors AB and showing the result into C if you have a single functional unit that's pipeline this is vector processinging essentially you basically send compute consecutive elements of vector C by adding consecutive elements of vector A and B basically add a0 b0 a 1 b1 a2 b2 A2 b3 you kind of pipeline the execution of those additions right so this is like a vector functional unit。

😊，Now， if you want to make this， as you can see， at time。

 you execute the same operation except consecutive。Now if you want to have both time and space。

 essentially you have a vector functional unit。😡，But you also have many functional units。

 so this is not that difficult to think about， but essentially across of functional units you do different operations so element C element zero is computed in this function element 1 is computed on this functional unit element2 in this one。

 element three in this one and then you go to element 4，5，6。

7 and then you keep doing this now you can see that this is an array processorer and also a vector press。

😊，So you're doing things in both space and time， the same outpat。😡。

Hopefully that makes sense right now modern GPUs are going to look like this。😡。

So you're doing things in both time and space actually this is a kind of an internal view of a GPU to be able to support this or to be able to support this combined array and vector processor you need a register file you partition the vector registers such that elements 048 do dot dot can be accessible only from here elements 159 dot dot can be accessible here so you basically partition your register file instead of having your register files to be shared across all of these functions you can partition your register file you can have smaller register files and it can access them much faster that way as well essentially you partition things across lanes。

😡，We're going to see that again laterra hopefully this makes sense also right because on this lane if you a lane is really a functional unit vector functional unit and there could be two of them as you can see over here。

 you can actually multiply those if you want you basically。😊。

Access only index zero that is inside your vector register here you can access only index one。

 so if you want to access index one the you'd better send your operation over here。

This will make more sense when we come to it。Okay， let's take a look at the parallel unleashed by this sort of machine that's both array and vector。

😡，So we're going to look at an example machine， we're going to overlap the execution of multiple vector instructions。

 We're going to have three units load to multiply and a。😊。

And we're going to have 32 elements per vector register and eight lanes。

 so here I show you four lanes or kind of eight lanes over here also。

 but here we have four lanes if you wish， we're going to look at eight planes essentially we're going to look at 24 operations per cycle in the steady state and we are going to issue only one vector instruction per cycle。

😊，So let's say you the first one， this is the first load。

It has 32 elements per vector register eight planes。

 meaning the first eight elements are operated on in the first cycle。

 the next eight and the next cycle， the next eight and the next cycle。

 the next eight and the next cycle okay that's the first cycle in the next cycle you issue the multiply so while the second eight elements of the load are operated on the first eight elements of the multiply are operated on concurrent。

😊，So you can do multiply on the elements that the load produced， for example。

 assuming there's a dependency over here， right？And then you issue add in the next cycle and you can see that you now you be un least to complete parallelism in this machine while these eight elements are being operated on for with the load。

 these elements eight elements are being operated on with the multiply and these eight elements with the ad。

 so now you have 24 operations going on per cycle。😊，And then you can issue one more load。

 it could be a different one and one more multiply and one more ad and it could keep doing that right。

😊，So that's a lot of parallelism as you can see and in modern GPU， this is much larger than that。😡。

Okay， it's kind of nice to look at it。But it's it's a simple concept it's not that difficult but if you have questions let me know okay let's talk about something very interesting so how do you actually program these things we're going to actually talk more and more about programming or generating code for these things a little bit more when we get to GPUus especially。

😡，So we're going to talk about automatic code vectorization have you covered automatic code vectorization at any place yes no not that much okay I'm going to give you a very simple example so we look at this vector edition right yeah two vectors A B you're adding them element twice and writing the result into vector C this is very highly parallelizable because every loop is independent of every loop iteration is independent of the preus one right there is no loop carry dependency。

😊，In other words， any loop iteration is independent of the other one right and you can because they're operating different loop iterations are operating on different elements。

😊，Okay so this is a scalar sequential code for it， I'm showing you only two its， you have two loads。

 each element for A and B I don't distinguish A and B over here and then you do an addition and then you do the store of the result into C。

😡，Basically， only four instructions per， I am not showing you the branch because we're going to paralyze that's an a vector machine。

 which eliminates branches， as you know earlier。😡，And then the second iteration， basically。

 you can execute the sequentially。😊，With many， many iterations， depending on N。

Vectized code looks like this， you can have an intelligent programmer or an intelligent compiler that analyze the code and that says all these iterations are independent。

😡，And because I can guarantee you that these iterations are independent。

 what I'm going to do is I'm going to parallellyze these iterations。😡。

What I will do is put them like this， you can see that iteration one， iteration2。😊。

These two loads can be executed in the same cycle。😡，These two on different data elements。

These two loads to B can be executed in the next cycle。😡。

These two ads can be executed in the same cycle after loads produce their data。

 and these two stores can be executed in the same cycle after ads produce their data， right。Now。

 if a smart compiler or a smart programmer can recognize this and what they can do is they can vectorize this code。

 right？😡，They can essentially say because these are independent。

 I'm going to express these loads from different iterations as a vector load instruction。😡。

And then I'm going to allocate vector register for it and then I'm going to vectorize this code so this is possible to it's essentially vectorization is a compile time reordering of sequencing of operations as opposed to sequentially ordering the iterations youre actually parallellyzing the iterations and figuring out what can be executed in parallel clearly to be able to do this you need to be able to guarantee that there are no dependencies across the loop iterations and this is a very nice example if this loop look like C equals AI plus B I minus1 then you would have some trouble because now you have a dependency between the previous iteration and the next iteration。

😊，Okay， so if we're going to get back to this， so remember this。

 we're going to have some fun with this execution model。😊，Well。

 this is actually we're going to have some fun with this vectorization and figure out how to execute this code in different models Okay。

 let me summarize vector and SD processinging and then we're going to talk about how this is executed in actually general purpose process how this has impacted general purpose process。

😊，As opposed to data flow， data flow was very irregular if you remember right out of order execution machines。

 very irregular parallelism， they discover irregular parallelism by keeping track of dependencies across instructions。

 all of this machinery that we added here。😡，It's kind of simple and beautiful we're exploiting regular data parallels if your program has a lot of regular data parallelism。

😡，You can express it with vector instructions。Same operation performed on many data elements。

 you can improve performance and simplify design because there are no intro vectoror dependencies。

 you assume and we discussed a lot of these， so I'm not going to go through these again。😡。

The difficulties， of course。How common is this， right。

 What fraction of your code is perfectly irreular like this。

 This is called the vectorizability of code。 In the end。

 your performance is limited oronic by how vectorizable your code is。😡。

There are two questions over here right you have a program and this program you want to execute on a SD machine to be able to extract performance out of it。

 you want to figure out the maximum parallelizable clearly in a vector way。😊。

And that will determine the performance of this code and then if you look at a more global scale。

 there are many， many applications， what fraction of the applications can actually benefit at what level from these machines and this is a very good question to ask。

😡，In the end。The operations that cannot be executed as a data parallel manner limit your performance。

😡，So you have a scalar operation meaning you do your vector length is one for the operation right you're wasting a lot of your machine resources。

 you may have 32 functional units but you're using only one of them we will see that in GPUs you'll actually do some exercise with that they limit vector machine performance so this is really MDda's law in the end right。

😡，え。In fact， because of this， this was also discussed， I think last time， for who design K1。

 K1 was one of the fastest supercomputers of its time in 1970s。😡。

And they actually designed a scalar part。 It was a heterogeneous machine。

 It was edit vector unit component， but it also had a scalar component。 And these folks said。😊。

Our performance is really limited， we have a very great vector machine。😡。

But our parallelism is were limited by how often we execute on the scalar part。

 so we're going to make the scalar part extremely fast。

 so they were not only the fastest vectorter machine。

 they were also the fastest scalar machine of their times。😡，So this is MDd's law in the end。

 you know about Md's law， right， I many people know about MDd's law， you read MDd paper， that's good。

So many existing Is actually include vector like operations and we' were going to see that soon a little bit。

 these are not the latest but we will see so recall MDda's law。

 I like this picture over here basically you have a parallellyizable fraction of the program it could be vectorable data parallel in this case and then you have a more serial version of the program it's a simplistic way of thinking about program where it's very powerful。

😊，And assuming f is a parallellyizable fraction of a program and n is the number of processors。

 you can think of it as number of parallel units that you have in a vector processor。

 the speed up looks like this。😊，呃。Essentially， the speed up with n processors look like this or n functional units。

 n vector units， assuming you have a vectorizable code， so the paralyizable part is divided by n。😡。

And nonparlyizzable part remains because you cannot。Palllyze it on a vector machine。

And your speed up is one divided by1 minus f non parallellyizable part plus parallellyizable part divided by n。

 So as n goes to infinity。😡，Meaning you have infinite number of vector units or vector lanes。

Your speed up approach is one divide by one minus f。😡，So if you're paralyizable fraction， F is 50%。

If it's an infinite number of vector lanes， you have2 x performance improvement sounds terrible right。

😡，So what do you do， you either improve your parallellyizable fraction。

 which may be tough with programming techniques。😡，Or you design a tailor processor that's extremely good at also speeding up 1 minus f。

😡，Hopefully that makes sense its a lot of order execution， for example。

 speeds up with the one minus F part if you think about it。Okay。

 this is a beautiful thing to think about in the end what says is maximum speed up is limited by serial portion and this is called the serial balneck of these vector processors and all parallel machines suffer from the serial balneck。

😊，GPUs， as we will see， they also suffer from the serial bottlene if you cannot paralyze your program。

 so let's let's say let's do another example over here if F is 99%。😡，And n is infinite。

The speed up that you get， the maximum speed out you get is what？😡，Yes。10， yes。

 exactly if so basically with an infinite number of processors， even with 99% parallelizability。

 the maximum you can get is 100 x speed up。😡，Its if it's sad。

Think about it 99% is a very large number actually， put it make it 99。9% do you get 1 thousand00。😡。

Still， if you want a million。You really need to paralyze your program extremely well and that's very difficult。

 that's a very， very difficult task to paralyze your program to the level of 99。999 percentage。😡。

So that that serial part， even the distribution of tax to parallel processors may take more than 1%。

 depending on how you distribute the tasks。Okay， so I like the slide a lot。It's very fundamental。

It experiences a lot of things in life also actually。Okay， let's talk about。

 unless there are questions， let's talk about Sdi operations in modern ISAs。😡，So aside from GPUs。

 CD operations were actually implementing general purpose processor as well。

 so these were not just supercomputers， general purpose processors over time said oh。

 can we actually pull in some of these SD operations to improve our efficiency？😡。

So these are called CD instructions set extensions。

 single instruction multipied extension instructions。😡。

Where single instruction unsurprisingly acts on multiple pieces of data at once。

 they're in a limited form and the reason they were introduced is because of graphics。

 essentially multimedia image processinging graphics， This is very heavily parallel。

 That's why GPUs were also built and people said that these are very parallel operations。

 Why are we spending a sequential instructions stream on that。 Let's have some parallel instructions。

 C parallel instructions。😡，What they do is they perform short arimetic operations also called tech arithmetic。

😡，Actually there are a lot of packed operations in X86 I say for example， for example。

 you can add four or8 bit numbers。😊，To be able to if you're ALU with 32 bits。

 you're able to do a 32 bit a， you can partition that ALU to also do eight or four8 bit ats right you just need to make sure that the carries are not propagated。

😡，Between these different4，8 pit units， right， That's the idea over here。

 So with a single 32 bit A U， you can partition it into。Essentially48 bitta values。

 you can also par to 2， 16 bitta valuess， you can also par to 8，4 bitta valuess， 162 bitta valuess。

 321 bitta values， right？😡，So with a 32 bit L actually you can exploit smaller bit with parallels so this' is an example over here。

 this a packed ad8 bit and you can see that at 32 bit there are two registers as CRS1。

 these are actually scalar registers treated as in a vector way。😡。

You look at different pieces of the registers they are different date elements。

 you can see that these are four date elements， As A3， A2， A1， A0， and then B3， B2， B1， B0。

 and then you add them concurrently and this is the result that you get。😊，Sounds cool， right。

 You're treating a scalar register as a vector register this way。😊，Okay。

 so a Pen toium MMX Intel was the first one to actually introduce these vigorously。

 essentially one instruction operates on multiple data elements simultaneously similar to what I just showed you。

 this is very similar to array processing yet it's much more limited and it was designed with a multimedia operations in mind essentially there's no vector length register。

😊，Programming is sequential very similar to what we do today Upcode determines the data type you can have 88 bit bytes416 bit words。

232 bit double words or1 64 bit quadword this is scalar the others are all let's say vector or SD stride is always equal to one essentially so these are the different ways in which you can treat the data in a given single register so it can pack eight8 bit elements for example I'm going to show you examples and this is a beautiful paper that talks about it that's why it's one of the readings that I suggested。

😊，So let's take a look at one example， this is we have two registers over here。

 the top register and the bottom register and we execute an operation called pack compare greater than word。

 so each of them is a word and you treat these registers as four words each and then compare whether the top register word is greater than the bottom register's word in this case 51 is not greater than 73 so the result the word length result and the result register is all zeros。

😊，It's kind of a mask that you will use later on， right？Oh。If you look over here。

 three is greater than two， so the result is all once。😊，Okay。

 so you can imagine this for many different comparisons。

This is a packed multiply and add which is good for matrix vector multiplication。

 so here again we have two registers， you express them as four values a3 A2 A1 a0。

 the second register B3 B2 B1 v0， you multiply them and the result actually goes to two different registers because multiplication expands the value right？

😊，So this is a3 times B3， this is a2 times v2， this is another register a1 times v1 a0 times b0 because the result of this this multiplication it's called packC multiply add word to double word in x8 to6 terminology again two registers and then you can do an addition multiply and accumulate right you can actually add with another operation。

😊，You can actually do a3 times B3 plus A2 times B2。

And then a1 times b1 plus a0 times b0 so this could be one or two instructions essentially and you can see that this is one way of doing it for a matrix vector multiplication I'm not going to go through this。

 but it is essentially what I just showed you over here with two instructions。😡。

You can actually generate a matrix vector multiplication at least this length， of course。

 if your matrix is larger and vector is larger need to partition it into the many registers。😊。

So you can see that this is actually pretty powerful this is before the machine learning times and people wanted to do matrix vector multiplication let me give you one example one full example I like this one because this is the reason why things were developed image processing people said image processing is highly parallel let's take a look at one example our goal let's say is to overlay the human image x this is the human image assume that there's blue over here it's black and white but you got to imagine a little bit behind this lady there's blue background and then there's some image y it's a blossom background it's a tree actually and let's assume that the background looks like this what we want to do is we want to merge these two images such that the blue pixels in this image are replaced by the blossom pixels today AI can do many many interesting things than this but this was all stuff that people used to do。

😊，Oh， you can see that this is the image that we want。

 and this is the source code of it at C type of language。

So what do we do basically if you have these SD instructions， what you can do is this is the image X。

 these are eight pixels from the human image。😊，The MM3， it's an MM3。

And then we compare those pixels to。E blue， let's say， pixel。

So and then we generate a bit mask so using a packed compare equal bytes because the pixel is eight bits bytes。

😡，Each pixel in the human image is compared to blue， right， You can see that these are the blue ones。

So once you do the comparisons， blue ones will match and the bit masks at the appropriate pixel locations will be FFFF if that location actually has a blue background。

Okay。😊，So this is how you can identify which locations in an image。

 which pixel location and an image are actually blue by going through the entire image。

 I'm showing you only eight pixels， of course， you need to do this for the entire image of a four loop。

😊，Okay， or if you have larger registerries， you could also do that。😊，Okay， so that's the bits。

 the bitmass basically shows something like this if you imagine it。😡，Now now you have the bitm。

 you can use this bit mask to collect different parts of the image you're trying to construct right this is our bitmask and MM1。

😊，And then this is our blossom image。😡，These are the pixels in our blossom image and we use the pixels corresponding to the same pixels in the bitmask and if the pixel is FFFF。

 if the bitmask is FFFF， that means that that the original image was blue at that location。

 we essentially replaced that with the blossom apart from the blossom image and to be able to do that you need a packed end。

 you're really ending the bitmask。😊，Concurrently with the eight pixels that are coming from the blossom image。

Because end means that the positions at the bestmas are F are actually now contain the blossom。😡。

For the other one， if you want to actually get the ladies image now。

 what you want to do is a packed and not， meaning for the locations that are actually blue in MM1。

 you figured out that these are the locations that are blue， you don't want to replace them。

 you want to actually replace the other locations， or you want to keep in the other locations。

 the ladies image， right。So these are the red ones so what you do is basically you form two things one contains the parts of the image that are blosssomeom。

 the other contains the parts of the image that are lady and you basically or them in the end and then you get eight pixels from your image that image that you're trying to form so that sounds cool it's only eight pixels you could imagine doing this at a million pixels at a time and that's kind of a GPU for you。

😡，Okay， this is8 because we're limited to SMD operation in a scalar IA。

 mostly scalar IA and this is actually nice because you can see that one，2， three，4，5。

 six instructions can do this across eight pixels at a time and again if you think about a GPU think about doing it at a million pixels at a time if it's powerful enough so you can actually process this image very quickly if your parallelism level is large。

😊，Okay so I like this a lot because this is actually from the paper that I mentioned this paper was published before intellectually implemented the MMX technology。

 there was a lot of actually a lot of discussions at Intel should we implement this。

 should we not implement this and it's good that people were very forward lookinging and they decided okay we're going to implement it and after they implemented all of the other process start implementing the MX or this type of vector instructions S instructions because this was a good idea there are a lot of applications out there that are doing image and video processing。

😊，And it's a chicken and the egg problem right if you implement this and no one use it。

 it's wasted hardware it's also wasted ISA instructions so it's kind of a bet that you're making as a designer。

 computer designer that people will use it。😡，But there was enough analysis that show that there are so many applications and clearly today。

😊，Almost all of the applications can use this sort of extension， especially machine learning。

 so the architect's decision makes a big difference as you can see。

 just reading this paper if you're interested。😊，Okay， so essentially these have improved a lot。

 this is the Intel story if you will or x86 story X86 story moved from MMx which was limited and then they added a lot more support double floating point etc cea new instructions shuffle operation I'm not going to talk about that and then they move to AVx vector extensions over time and things became larger and larger 512 bits GPUs are going to be even larger than this as we will see soon and then more recently they added the advanced matrix extensions so that they have actually two dimensional register so that they can actually do multiplication matrix multiplication nicely I will not go into any of these but this is kind of the history of Cdi type of operations in modern ISs and all other ISas actually have this sort of extensions。

😊，hopefully it's interesting now we applied the concept to general purpose before I go into GPUs actually I would like to talk about other CMD operations applied to other machine learning excccelerators very quickly I'm not going to spend a lot of time it's not going to be thiss just for fun。

 let's say you have a way for scalar processor and these people have designed the way for scalar processor so that they can put a lot of memory and a lot of compute together。

😡，And to accelerate machine learning， that's our main goal。

 and you can see that there are lots of transistors， etter。😊。

But basically this machine at a high level， let me finish this and then we're going to take a break。

 what you do is you map a neural network on it。😊，To map a neural network is not easy and you can read papers about it。

 I'm not going to talk about that， but this machine is a combination of a MIMD machine and a SD machine kind of similar to GPUs actually GPUs are also a combination of MID and SD in a different way as we will see but this is the way for scale engine they divide into dies normally a die itself is actually a processor now you have actually the entire 84 dies as your processor。

😊，Each tie is divided into 4500 tiles， 45， 39， each tie looks like this。😡。

So different pieces of code execute in different tiles and different ties。

 so that's the MIMD part multiple instruction multiple data you distribute the memory and there's some fabric that enables communication internally which we're not going to talk about but if you look internally into each tile each tile is actually four way relatively simple and not so big SD engine single instruction multiple data it's an array processor essentially with 16 bit floating point opera and there's some memory associate with it so it has a floating point multiply and accumulate units so everything that we've seen kind of applies to this machine also and if you're interested in more you can take a look at their presentation。

😊，So people do also FPGAs very quickly， FPGA machine learning exccalators also operate using similar principles。

 some of them use systolic arrays， which we talked about already。

 but some of them like Microsoft's Brawave， if you're interested。

 they categorize as a megaimD vector processor architecture again。

 you don't need to know about this in detail， except knowing that the SID principles that we discuss。

😊，Are actually applicable to FPGs also you can implement a CID unit in FPG essentially。😡，Okay。

So this brings me to GPUs， so we're going to take a break until the bell rings。

 and then we're going to continue with GPUs。对。但是。而且。啊这个快。はい。No。No。Okay。Okay。

Now now you know how CMdy processors operate and we've seen the combination of array and vector。

Processors。Now we're ready to go into GPUs。I think GPUs is going to be easy after this because they're essentially Sti units Sti units。

 but we're going to describe them and GPUs have been very successful as you know these are some fancy pictures I will tell you what I'm not going to talk about unfortunately we're going to talk about how processing is done inside these things。

 not the entire piece but a good chunk of it。😊，We're not going to talk about the interconnect that enables connecting these things to each other。

 which is really important actually for scaling up a system， a single GPU is powerful。😊。

But if the scale your application is much larger， if the parallel that you have in your application and the scale you have is much larger than what can be done a single GPU。

 you need to scale up the system to be able to scale up。

 you need to connect many of these GPUs together in some way and there's been a lot of improvements in interconnect technology and these are some example。

 let's say electrical signaling graphs that shows how fast you can operate etctera。

 the interconnect technology between these chips so I'm not going to talk about interconnect technology it's very important。

😡，And you know one of the reasons why this has been taken off the machine learning models have been growing and growing so you need to connect many GPUs together and these are some examples in which GPUs were connected this was 2016 for example and if you see the green parts are GPUs and they were connected with some interconnect over here and PCIE switches and over time the interconnections became different and different and these are another example you have some GPUs over here you may call them pods and you can see that these are a lot of GPUs four times8 I think and then theyre connection mechanisms like NVlink andV calls them that are quite fast across this cluster of GPUs and this cluster of GPUs and you can connect many of them together so you can see that I think they say 72 GPUs over here so if we're not going to talk about interconnect unfortunately because we don't have time but interconnect is a very important component of computing systems and architecture today if you're interested we cover interconnects in a lot of detail。

In our later courses。We're going to look at the compute part because we're still compute centric。

 let's say。😊，We're going to change that hopefully in the memory parts of the course of bit okay basically GPUs。

 the compute part is and we're not going to talk about memory yet。

 we're going to talk about memory later， although I did talk about memory so what's not shown exactly in this picture actually shown over here the high bandwidth memory chips there are a lot of high bandwidth memory chips in a GPU board today to get to actually satisfy the data requirements of highly parallel processing engines。

😊，Okay， don't forget the memory。But if you look at the processing part。

 the instruction pipeline of a GPU operates like a CM pipeline。

 essentially it's very similar to a reprocessor。But the programming is not done using SD instructions。

 it's not similar to a vector processor， it's not similar to the SD instructions that we discussed earlier。

 it's actually much easier， I would say it's done using threads。😡，You know about threads right。

 it's essentially a context software a piece of software context and a thread can do some tasks。

 right？😊，Okay， this makes it easier and this programming model has made GPs quite successful。😡。

So let's take a look at to understand what this programming model is。

 let's take a look at our paralyizable code example， I told you that we were going to get back to it。

 but before that I'm going to distinguish between two things。😡，One is the programming model。

 this is software， what the programmer sees and what the programmer does to program a machine。😡。

And the execution model， which is what the hardware does to execute the program。

 these are two different things， they could be completely different and we've kind of seen that right you can program a machine using a single scalar threat and then underneath the machine can operate using a data flow execution model using auto order execution right。

😡，The programming model can be very different from the execution model。

 so let's take a look at this distinction a little bit more programming model refers to how the programmer expresses the code。

😊，It could be sequential single threaded， one Neman type of programming model。

 data parallel SD model， you have vector instructions， it could be data flow purely data flow。

 it could be multi threaded， MIMD， we're going to see SPMD soon， single program multiple data。😊。

Execution modeler refers to how the hardware executes the code underneath。Again。

 we've seen many examples of this it could be automotive order execution。

 it could be vector processor， every processor， data flow processor， some sort of multi processor。

 or multi threaded processor。😊，There could be many， many things， sytolic rate。

 which is not shown over here， right？😡，Cystolic area can be programmed using a pipeline parallel model or some other model。

 et ceter， so basically the execution model can be very different from the programming model。😊。

And I've already given you this example one Neman model implemented by an out of order execution processor in that case out of order execution is the execution model whereas one Neumman single instruction the one Neman principles right sequential instruction processing single thread can is the execution model and now we're going to see how a GPU works GPU is essentially an underlying SD processor with some MID components as we will also see but the programming model is SPMd which is single program multiple data so let's take a look at what that is so we're going to go back to our code example。

 this is the simple parallelizable almost perfectly vectorizable code example and this is our scalar sequential code for it right each it。

😊，Executed sequentially， in fact， each instruction executed sequentially， right？😊。

So we're going to look at three programming options to exploit the instruction level parallels present in the sequential code。

 not hardware execution options， we're going to look at just programming first。What is sequential？

One is data parallel MD and the other is multi threaded meMD SPMD。

 actually you've seen alreadyD1 and two， now but I'm going to go over that again。

 and then we're going to see the multi threaded version of it also。😊。

So this is the first programming model sequential and the code is over here。

 this is the scalar sequential code， we're not going to change anything。

 this is what it is basically。😊，This is sequential， as you can see scalar sequential。

 this can be executed on a pipeline processor， as we have seen in the past。😊。

It can be executed on Autoward execution processor。Now this becomes interesting。

 pipeline process of course， interesting， but out of word execution is also interesting。

 independent instructions executed when ready。😊，And different iterations present in the instruction window can execute imp parallelel and multiple functioning units。

 So an auto order execution processor。😊，for example， if you have a long latency instruction here。

 load load， while you're waiting for these loads to come back， you go ahead and fetch these loads。

 put them into the reservation stations， and these loads can also start。😡。

So you basically what an out of our execution processor does based on its execution principles is to look ahead in the program。

😡，And execute。The next iteration assuming there's enough latency so that you can get to the next iteration so you can actually parallellyze code purely in hardware using out of order execution。

 maybe not so efficiently but it's doable that's what an out ofward execution processor does right imagine each load taking 500 cycles imagine you have enough resources in your reservation stations you can actually parallelze these load instructions in different iterations and also parallellyze the ad and store as well later。

😊，So basically， in other words， the hardware is actually dynamically looking ahead and unrolling the loop because we're looking at a single loop over here。

 you're really unrolling means you're actually going through the later iterations of the loop。

 not just a single iteration。😡，Okay， so that's the beauty of auto order execution。

 but it's expensive you can execute this on a superscalealar or via IW processor as well right via IW processor a compiler can try to figure out pack different instructions that can be executed independently we've seen that also it's possible to do or it could be a combination right auto order superscalealar etc。

😊，And as you remember， the concept and supersscale MBIWs can fetch and execute multiple instructions per cycle。

😊，So this is one programming model and how it can be executed。

Let's take a look at CIdy data parallel， we've seen this， this is your scalar sequential code。😊，呃。

You realize each iteration is independent。😡，And you basically。Put them next to each other。

And either the programmer or the compiler generates a SD instruction to execute the same instruction from all iterations across different data we've already seen this earlier。

 somebody creates these vector instructions。😊，And the vectorice code looks like this。😊。

You basically figure out a vector length。 you need to set the vector length， et cetera。

 and you do have vector load from。RA A into vector register1 and then another vector load from A B into vector register2 vector add between those two registers right the result into register 3 and then vector store register 3 into C and then you do this for if your vector length is small and you have lots of data elements you basically iterate over this many times also Okay so this is nice this is what we've seen so far in the past。

😊，This is best executed on a CM processor， clearly， either or A processor。

 depending on your resources and the trade offs that you make。😊，Okay。

Now the third programming model of how you program this is using threadreading right you don't generate load vector instructions。

 but you basically realize， oh， I have these iterations that are independent。😡，So why don't I？

Generate the either of the programmer or the compiler， generate a threat to execute each generation。

😡，So this is one threat。This is another threat they' are completely independent of each other。

 except they operate on different registers， which means that they're completely independent of each other right they're operating on different pieces of the array。

 different registers， so registers and arrays are partitioned across these different threads。😡。

And each thread does the same thing， except they do it on different data。😊。

That's the idea so we don't have extra instructions anymore this could be executed on a MID machine and your MID machine can be two different processors if you have two iterations the scooot processor one the scooode processor two and you will get the result in memory correctly。

😡，If you have a million iterations， if you have a million processors。

 each iteration goes to a different processor and it can parallelze the thing。😊，That sounds good。

 right？It could be executed in a fine grain multi threaded manner in a pipeline processor。

 as we have seen with fine grain multi threading。Every thread goes through the pipeline with one instruction at a time。

 right， and then you can pipeline that。😊，We're going to see that with GPUs because GPUs actually employ fine great multi thread in addition to the S principles。

😊，Okay， so this particular model is called single program multiple data。

 this is not as general threading right general threading means you can have multiple different tests they are doing completely different things。

😡，Here each thread is identical， right each thread is doing exactly the same thing。😡。

That's why it is called single program， single program。

Is essentially that program if you think about the thread as's a program。

 except it's operating on multiple different data chunks。😡。

Each thread is operating on a different chunk， the first thread is operating on let's say element zero right the second is element1。

 et cetera， and you can actually make it even chunk you can change the grand la of the iterations of course right？

😊，Okay， and this can be executed， the realization that GPUs have made is that this programming model SPMD is easy for the programmer。

 easy for the compiler， you don't need to have vector registers， etc。😊。

And you can execute this on a CD machine。And that's the beauty of GPUs essentially。

 and we're going to see how we do that this can also be executed on a ST machine。

 single instruction multiple threads。😊，You can argue whether it's the same as CD or whether it's not。

 but GPU sometimes use this terminology called single instruction multiple threads。

 because you have multiple threads and they are actually executing this single instruction at the same time as we will see because we're going to group。

😊，The way you execute the single program multiple data like each different thread is actually executing the same code。

 you realize this can be executed in a SD machine， how do you do that basically you say that oh each thread is executing the same load same program counter。

😊，I'm going to group them together and send a single load and operating on different locations。😡。

This is not done at the IA level。 This is like the Simdi Sdy says oh。

 I have a vector register and I do a vector load。 I'm not doing a vector load。

 I'm going to do something else， which is。I'm going to put together these different threads into the same instruction dynamically。

 I'm going to group them together。😡，Okay we'll see how it's done。

 but that's the basic idea as opposed to expressing this at the ISA level。

 somebody groups these loads that do the same thing on different data elements together。

 but the programming model that doesn't get exposed to the programmer the programmer programs with threads they don't need to deal with vector instructions。

 vector length etc， all of that headache goes away from the programmer if you programme GPUs probably you know what do I mean how many people you program GPUs。

😡，Okay， not many。Not yet if you go outside， you'll probably program GPUs。

And if you're interested I'm going to tell you resources about programming GPUs。

 but we cannot cover that unfortunately okay， basically a GPU is a SD or ST machine。

 I use these interchangeably at this point， but you will see hopefully except it's not programmed using S instructions。

😊，It is programmed using threats， meaning the SPMD programming model。😡，Which I introduced。

 each set executes the same code， but operates on a different piece of data。😡。

Each thread has its own context。😡，Meaning it is its own register set。😡，And it can be treated。

 restarted and executed independently， which is very interesting because that way you can actually group these threads differently together。

 so we will see that also。😡，Okay， so one concept that's really important is how to group them together is a set of threads executing the same instruction are dynamically in hardware。

 using hardware software support together， grouped into warp。😡。

It's also called wavefront and video calls it Warp。

 AMD calls it wavefront and they clash with each other， but it's the same thing by the hardware。

 essentially there's a set of threads that are executing the same instruction。😊。

That are grouped together at this point in time， right？😡，Essential。

 a warp is a C operation formed by hardware。😡，Hardware figures out which threads are at the same program counter and puts them together。

😡，Okay。So essentially let's take a look at what the warps may be so hardware there's some hardware support for this that needs to happen。

 which we're not going to go into a whole lot of detail but you can imagine what that could be you have a set of threads that execute the same instruction in other words the threads are at the same program count。

😡，So I assume that this thread is at program counter， whatever the program counter or the load is。😡。

This thread is executing the same thing， so the program counter is also the same right hardware figures this out。

😊，And says this is warp 0 at PCX right assume that that is PCx program contracts X。

 and this is warp 0 at PCx plus one。This is warps you at PCx plus2。

 assuming you increment the PC by one right as you go to the next instruction and the instructions are sequential like this。

😊，And then this is Warp2 at PCx plus3。Okay。😊，And each warp is executing is the same instruction from different threads。

Meaning the same instruction on different data elements。Okay。

So let's go into a little bit more detail， so essentially graphics processinging units are C at least the core of it are C that are not exposed to the programmer that's why it's called S also a single instruction multiple thread。

😊，Okay， so let's take a look at the difference between SMD versus Sti execution model。

SM single sequential instruction stream of SMD instructions is in the strict sense。

 each instruction specifies multiple data inputs， right？😊，So we do have vector load， vector load。

 vector addd vector store， vector length， for example， these are some instructions。😡。

Syme teamme means you have multiple instruction streams of scalar instructions。😊，In other words。

 threads are grouped dynamically into these wars。😡，So basically， you don't have vectors anymore。

 you don't have vector lengths。😡，What you have is scalar instructions， load load a store。

 assuming you're doing the previous thing。😊，And we specify the number of threads。

 So what the programmer does it specifies the number of threads。 So if you have a million iterations。

 you say， I have a million threads。It's a bit more complicated than that in modern GPUs。

 but this is the gist of it in the end。 You don't need to deal with the vector length。

You don't need to know the vector length of the hardware。 You just say I have a million threads。😡。

And the GPU deals with it。So what are the major advantages so one advantages you can treat each thread separately in other words you can execute each thread independently on any type of scalar pipeline it doesn't need to be actually SD pipeline it could be any type of scalar pipeline this going to be multiple instruction multid acrossing as we will see I'm going to talk about this first。

😊，You can also group threads into warps flexibly。😡，You will see this better when we get to it。

 but you can group threads that are supposed to truly execute the same instruction together。😡。

You can dynamically find the out， You may let's say have 500 threads in your machine。😡。

And you know the PCs of all of them， and you have some hardware that checks which threads have the same PC。

😡，And then it combines those threads into a single warp。 send us down to a pipeline that has。

That has multiple Sd lanes， as we have seen。 So you execute like just like a processor。

 except you group things。😊，That's happened to be at the same program counter。

That sounds very powerful right Of course， you need some hardware to be able to detect that。😡，Okay。

 we're going to look at the second one later， but the benefit of this is you can dynamically obtain and maximize benefits of C processing you don't need to have a vector length。

 you don't need to have vector load， you don't need to have vector registers， you have scalar。

 everything is scalar。😡，Everybody is used to scalar， we use sequential programming。

 you program that way， hardware dynamically figures out which of these actually can be combined together and dynamically vectorizes the code in other words。

😡，It works only if you have the SPMD programming model， single program multiple data。

 you cannot do it easily。😡，Or I would argue almost you cannot do it at all with the hardware support that is there。

 if the different threads are doing completely different things。

 they have to be doing exactly the same thing。Okay。Okay， let's take a look at the first one。

So we're going to talk about fine grain multi threading of wars。

 you remember fine grain multi threadreading I've said that multiple times。

 essentially you can have different in the pipeline。

 you have instructions from different threads such that the pipeline is very simple and you can do this in a scalar pipeline clearly。

😊，So assume that a warp consists of 32 threads， you're grouping 32 threads at the same program counter。

😡，If you have 32，000 iterations and you're doing one iteration in each thread， you have 1，000 warps。

 right？And you can interleave these warps on the same pipeline。

 with essentially the fine grain multi threeing those warps as opposed to。Essentially。

 you're changing the graularrity at which you're interleaving things in the pipeline。😡。

As opposed to having a single thread， you're actually combining 32 threads together called a warp。

 and these 32 threads are interleaved as they go through the pipeline。😊，So for example， again。

 I'm looking at the code over here， but these are different iterations。😊，This is Warp0 at PCX。

 we call load at PCX。😡，And then you fetch that load， you fetch that warp， you execute it。

 and then you fetch warp 1 at PCX。😡，呃。Let's because weve assume that a warp is 32 threads。

 the reason a warp maybe be 32 threads is you may have 32 functional units that can be operated concurrently。

 right？😡，That's one reason there could be other reasons。

 but essentially the first 32 iterations are grouped into warp War 1， that's called Warp 1。

 oh don't know， that's warp 0 and the next 32 iterations are grouped into warp 1。😊，Okay。😊。

And then you may also have Warp 20 at PC x plus 2 at some point。

 and the way you understand what iterations it may be executing is you multiply the warp size with the iteration count。

 essentially Warp 20 is executing iteration 20 times 32 up to 21 times 32， non inclusive at the end。

Okay， so if you look at this at a given pipeline。😡，Things may look like this。

 essentially all threads in a war are independent of each other。😡。

Meaning they can be executed seamlessly in a fine grain multi threadreaded pipeline。

 right if you remember fine grain multi threadreading。😡。

The assumption that we made was threads are independent of each other completely here。😡。

We have warps that are completely independent of each other because they're executing they're operating on different state elements。

 so for example， if you start from the latest instruction。

 this is warps zero at PC x plus3 executing iteration 0 to 31。😡，Pipeline like before it。

 in the pipeline stages before it， you may have Warp one。

At PCx plus2 executing iterations 32 through 63， for example right so basically you may be executing different things as you can see and Warp 2 is executing some other iterations War3 is executing other iterations so you could be doing you could be pipelineing these warps across the execution pipeline over here so hopefully this is clear。

😊，If not， they'll become more clear， but feel free to ask questions also。Okay。

So a basic idea is very similar to what we have seen in the past fine grain multi threadreading。

 except the pipeline is not scalar pipeline is a vector pipeline， right meaning。😡。

This threat that's executing each warp。😡，Goes to a different lane。So for example。

 this store is in lane  zero， this store is in lane 1， this store is in lane 2， et ceter， right？Okay。

 so if you're interested in multithreading， we've covered it okay let me go into this a little bit more because this is really important because we're gonna to see more interesting things that build on it soon so warp warp just to remind it's a set of threads that execute the same instruction on different data elements This is what's really the Sty nature and video calls it Sty single instruction multiple threadread but this is essentially what enable Sty all threads run the same code we said why is it called a warp because warp happens to be defined as threads that run lengthwise and woven fabric so they play with the words actually thread is like a woven fabric when you actually do clothing a warp tends to be essentially these are warps kind of you can think of it that way they're doing the same thing on different data elements if you think about I guess I wore the right thing I didn't think of that intentionally but you may be wearing something that's like warps but mine is perfect。

😊，I think。Yeah， okay。Okay， that's the kind of the joke of it， but it's true actually。

 that's why it was named Warp。😡，AMD named it wavefront because they actually do the same thing like a away。

 but it's a bit harder to imagine I think I can imagine this one Okay so if you look at this this is actually a nice picture each。

😊，WP consists of multiple scalar threats that are at the same common program counter。😡，And they get。

There are many warps。That are in hardware that you keep track of and then you basically schedule them to a SD pipeline。

 So this is a nice picture because it says that it says that there is a pool of warps。😡。

That can be fetched into the pipeline and inside the pipeline there are also some other warps that are executing we will see that also。

😡，So what does that scalar pipeline look like this actually from your reading actually part of this was from your reading also essentially this is a high level view of a GPU so far what we've been talking about is there is what is called the shader course。

 these are the cores that do the execution and of course clear there's memory that we will get to later on there's some interconnection network but if you look at the shader core these are the warps。

 you have a program counter and mask we will see what that mask is soon。

 which which things which data elements within a warp you should operate on and we will see why soon because of branching that happens and threats and at any given point the GPU picks a warp。

😊，It knows that everything is independent over there， that's nice， it sizes， let's say。

 in this case four。😡，It basically fetches instructions for the warp。

 it's going to be the same instruction， it basically fetches once from a program culture。

 you know the program culture and distributes it。It decos it so fetch and deco are actually very simple in a GPU because you don't fetch even though your warp size may be 32 you fetch only one instruction right because it's the same program counting okay and then it distributes the execution across four different pipelines that are all doing the same thing right this is the S execution part this is essentially the vector units that we will see and then writes the results back and the warp goes back to this pool of warps that are executing and then it can get scheduled again for the next instruction because PC is incremented for that warp。

😡，So at any given point of time， you may have hundreds of warps over here and this job of the hardware schedule and GP appears to select which one will go next。

😡，And can decide which one willll go next based on whatever policies， there are a lot of policies。

 we will see some of them if we have time， I've worked on a lot of these interesting things actually。

 a of some of these have gone into real hardware。😡。

But they're actually very sophisticated policies to decide which wars the schedule because Nmi is a problem don't forget about Nmi branches are a problem as we will see also soon so all of those things that we discussed for scalar process come back。

😡，In GPUs also branches are a problem， memory is a problem， okay？

Okay so let's take a look at latency hiding a little bit more detail now we already to discuss what a warp is a set of threads that execute the same instruction on different data elements fine grain multifiing。

 you do one instruction per in pipeline at a time no interlocking we interleave warp execution tide latencies so this is warps that are available for scheduling this is in a little bit more detail the S pipeline fetch thecode now we have partition register file which is very similar to the vector processor we're going to see and then you have AL use if the wars access to memory hiarchy and you get a cachemiss。

😊，They get taken out of the pipeline then they wait。So that other warps can come into the pipeline。

So there is some latency tolerance that are added that is added if you have a cacheist for example。

 we'll talk about cache assume， but if your data is not there and you need to access memory。

 the warp gets taken out。😡，And then other wars come in。

 hopefully many other wars don't need to access memory or if many other wars access memory。

 then they all go to memory and they all parallellyze their memory accesses right so a memory becomes a problem over here because you have so many wars。

😡，Okay， register values of all the threads stay in the register file。

 so register files are big because you need to support so many wars， like these are threads right。

 you need to support all of them that are currently executing and for that you need huge register files。

😡，So if you look at a GPU register files， there' a big component of it。

And fine grain multi thread enables a very simple pipeline， pipeline is very simple。

 no order order execution， a small number of stages。😡，Except you have very good latency tolerance。

 no branch prediction， et ceter， forget about that because you want to keep this visible you have a lot of parallelism and whenever you have because you're doing fine multi threadread essentially whenever you have a memory miss。

 you need to take things out to a special pool of wars。😊。

So basically you can think of millions of threads operating on the same large image or video or a huge。

 let's say， matrix。😡，Okay now let me draw the analogy a little bit more。

 so this was what we had seen this is the vector instruction right vector add ABC。

 we executed in a vector processor using a single function unit like this。

 we executed in a combined array plus vector processor using four functional units like this。😡。

A GPU you have a 32 thread warp executing a thread ID， B thread ID， C thread ID。

 this is our vector ad essentially you're doing an ad except you're specifying thread Is now that's how the programmer programs right programmer uses thread Is programmer doesn't use。

😡，Vectctor instructions。And we know how to use thread ideas， we basically partition our program。

 partition our data across different threads， and write the same code。Okay。Basically。

 this is execution using one pipeline functioning unit。😊，And this is。

The execution using four pipeline function units， essentially。😊。

Different instructions from different threads are executed in different functions。 This is thread 0。

 This is thread1。 This is thread 2。 This is thread 3。Threread four， threadread5， thread six， thread7。

 so you have massive multi threading essentially。And。

This could be a warp essentially for instructions or this entire thing could be a warp that's broken down into the hardware constraints。

 meaning you have four functional units and you break the same warp meaning it could be in this particular case we see 28 of them right 28。

😡，Threads are doing exactly the same thing。 They're at the same program counter。

 you fetch the instruction， you decode the instruction， and then you send it to this pipeline。😡。

Four threads at a time， four elements at a time， right？So basically。

 there's a lot of power to this model， as you can see。Okay， so for this。

 we've seen the vector unit in the vector unit， we partition the vector registers。

 so we part the element0，4，8 go here， 14，1，5，9 go here。😡，Here， you do the same thing essentially。

 except the programming model is different。😡，Instead of elements。

 you have registers for third ID 048。Here in this lane， 1，59 in this lane， 2610 in this lane， 37。

11 in this lane， and they need to be loaded to these registers， of course。

 at some point before you start execution or you generate the registers。

So clearly thread IDs 048 should execute peer， thread IDs 15，9 should execute here，26。

9 should execute here， 3711 should execute here。😡，Hopefully this makes sense。

 basically I'm drawing an analogy between vector processor and or vector plus LA processors。

 S processors and GPUs。😊，We saw this also earlier in the previous part of this lecture。

 this was a vector instruction level parallelism， we have 32 elements per vector and eight planes and we see how much parallelism is unleashed and you can see that this is load multiply at load to multiply and at and this is essentially a vector instruction。

😊，In a given program counter， right vector load， each vector load specifies 32 elements。😡，Now。

 if you use the same thing， assume 32 threads per warp and eight planes。Now， Warp  zero。

This isYou can think of it this as WarP you or executing at program counter that specifies a load。😡。

This warp0 unleashes 32 our patients。Each of them happen concurrently。

 and they get pipelines in the eight load units over four cycles。😡，Instead。

 instead of having a vector load， we basically create it。😡。

Aggregation of threads that are executing the load instruction at the same program counter and turn them into a warp。

 and a GPPU does that dynamically。😊，Similarly， we multiply this could be Warp1， this could be Warp 2。

😡，This could be Warp 3， Warp 4， Warp 5。 So these are all different wars executing。

Each warp executes the same instruction and each warp is formed by combining different threads that are at the same program counter。

 you can think of it that way。😡，Okay， so basically it's the same thing as SD processing。

 except the programming is different， you just need to change your mind slightly to think about it。😡。

Okay let's talk about memory access a little bit， so if you have you have same instruction different threads and you use thread ID to index and access different data elements for this you need to partition your data across different threads right for example。

😊，You have 16 threads over here accessing 16 data elements。

 each that is accessing the corresponding data element as an easy example。😊。

N is 16 you have four thread per warp， which means that you have four warps and each warp needs to access the corresponding data element essentially so you basically partition your register file such that。

Data elements are at the right places， so this requires work。

 this requires some work from the programmer， some work from the GPU hardware。

 but this needs to be done when you actually program a GPU。😡，For maximum performance。

 memory also should provide enough bandwidth to enable this essentially elements per cycle throughput should match the computation in the throughput。

😡，And this always an issue， as we discussed earlier。 So there's nothing magic over here。

 I just want to jump into a programming model。 That's why I want to talk about this， also。😊。

So warps are not exposed to GP programmers， so if you look at CPU threats and GPU kernels。

 these are sequential or model parallel sections， you execute sequential or modest parallel sections on the CPU。

😡，And you have massively parallel sections that go on the GPU， so blocks of threads。

 if you're doing image processing， you execute them on the GPU， for example。

So let's say this is serial code， you execute them on the host， this is a sequential thread。

 let's say。😊，And then you launch。Blocks of threads and you usually specify it this way depending on what type of GPU you have you can basically specify you're launching a kernel this number of blocks。

 this number of threads with some arguments on the GP device you can see that there's no warp over here right I have this number of blocks this number of threads and these are defined by the GPU programming model but there are no warps wars are all dynamic that's the good part and then you may actually execute some serial code and then you can launch another parallel kernel now you can see the sequential bottleneck over here also right if you have a CPU and a GPU and if you want to actually accelerate something by launching things on the GPU you need to do some serial code and this serial code in the end limits your performance back time does law this picture is real this is how current GPUs are used。

And yeah， why do they just。Figure out the blocks dynamically and all statically， for example。

 that you pixel and shading。Yeah。Could kind of food status。Yeah。

 you could do this statically yes no problem you mean the number of warps dynamically Yeah yeah。

 so you could do that statically also， but you don't need to do it in the general model。Yeah。

 there are ways of doing that statically as well。Dynaically。

 we will see the benefits of dynamically soon okay。

 so if it's really regular and everything is allocated nicely and everything is really doing the same thing statically is good。

 but dynamically we will see some benefits。😊，Okay， hopefully these are clear again these are very high level how to program and if you look at the programming model I don't expect you to know the GPU programming et ceter。

 that's not a course on GPU programming my whole point over here is if you write a CPU code that looks like this which is very similar to what we have examined。

In a GPU Kuda， which is the programming model that's used by Aiddia， it's very similar。😡。

You don't need to change much there is no vector load vector store etc ceter。

 you can see that basically you just need to add some thread I。

 you just need to do some calculation as to where what your thread ID is。😡。

You too you can learn that that's not that hard。But the function is。

Very similar to sequential code right scalar code and that's the beauty of this model they have figured out how to make this work on a parallel machine。

Okay， and then another example， I don't expect you to know this also。

 but the point over here is the code here and here are very similar。

 except there are some extra calculations to decide what your thread ID is in this case thread ID is indexed over here。

😡。

![](img/00f85e609c5e524ebfc4fb5264a656cf_2.png)

Okay， if you want to learn more about GPU programming， we have lectures。

 we're not going to cover them if you're interested in actually in more detail on GPU programming。

 we have a heterogeneous systems course that talks about it。😊，Any questions？

Let's see how much time we have。We slept sometime。No questions。Okay， let me continue that。

So I'm going to give you some examples of real systems。😡，So a GPU core is really a CM pipeline。

 it's also called a streaming process terminology here is a bit terrible。

 unfortunately essentially you can have many such streaming processors so NviDdia terminology this is NIDdia is one of the architectures a streaming processor is really a CM pipeline and then you have a streaming multiproces that has many streaming processors。

😊，So this streaming processor can be， let's say， I don't know， an eight pipeline。

 eight white SID unit。And then there's load storage units and then there's some special functional units which actually do some complicated operations which we're not going to talk about and you can see there's also Warp schedulers over here。

 there's instruction cache there's dispatch unit， there are register files and there's shared memory there's some constant caches etc。

 which we're not going to talk about a lot of the complexity over here。😊，But essentially。

 you divide the blocks， programmer programs using blocks。😡。

And they're divided into warps and could be essentially 32 threads right so it kind of looks like this。

 it's a hierarchical model。😊，Now let me let's discuss the differences between warp SD and traditional SD if you want to learn about GPP programming this is not the course。

 but it's actually is interesting also you may make it useful so traditional CMD just to up wrap up the differences traditional SD contains a single thread right？

😡，We didn't say this explicitly so far， but if you think about it in traditional CMD there's no multi threadreading that。

 you could have it， no question about that， but when we looked at our programs earlier last time or even today。

 you do vector load。😡，This is a single threat。 you have vector load， vector load。

 vector a vector store， that's a single threat。Except each operation is the S instruction。😡。

Sequ you have sequential instruction execution in traditional SMD you have lockstep operations and SMD instruction we've discussed all of these in the last lecture programming model is really S there are no extra threats software needs to know the vector length。

 meaning somebody needs to specify the vector length usually the programmer sometimes a compiler if it can do it。

😡，ISA contains vector or SD instructions， vector， load vector， or， et ceter。😡，W based Sd。

 which is what we've been discussing with GPUs。😡，Has threats， it consists of multiple scalar threats。

Except they execute in a MD manner， so the execution model is C， but the programming model is not C。

😡，Meaning same instructions executed by all threats。So it doesn't have to be lockstep。😡。

Meaning you can regroup things as we will see。Each str can be treated completely individually。

 meaning they can be placed in different wars。😡，So programming model is completely not sdy that's because of that。

😡，And software doesn't need to know the vector length， there is no notion of vector length。😡。

It doesn't exist。You just have a thread count。😡，These are the number of threats。

 this is the amount of work that I need to get done， right？😡，I don't need to care about vector light。

😡，So this enables multi threadreading and flexible， dynamic grouping of threats。😡。

And importantly the ISA is scalar， basically we didn't change anything in the underlying ISA。

 you can use the MIPS ISA that you're working on in your labs for example。

 and that could be your ISA in a GPU GPUs don't expose their internal ISAs to outside world。

 but there's an internal ISA that's very simple scalar， nothing sophisticated， let's say。😡。

SIMD operations are all formed dynamically。😡，So it's an interesting model that combines multiple concepts in a nice way making programming easier right so if you want your ideas to get adopted。

 making programming easier is good thats one of the reasons GPUs have been quite successful with their programming model。

😡，So essentially， as I said earlier， and as I harped on multiple times in this lecture。

 a war based SMD is really SPMD programming model implement on CD hardware。😊。

So what is the SPM deal let's take a look at that again before we finish it's really single procedure you may have you may people may call single procedure。

 multiple data， single program multiple data， this is really a programming model than a computer organization or architecture each processing element executes the same procedure except on different data elements。

😊，And procedures can synchronize at certain points in a program at barriers for example。

 so you divide your program into like many threads doing the same thing at some point you want to aggregate the results right so for example you're trying to so okay one way of actually one of my favorite examples is counting characters in a book。

😡，You have a thousand page book。呃。You can actually have a sequential program that goes through every single page and counts each character in an alphabet。

 how many times ICA， how many times ICB， how many times ICCs right or you can have a single program multiple data model。

😡，You have this same program。😡，And give it to it first。Four pages and then another fit。

Next gets the next four pages。 Another thread gets the next four pages。

 Another thread gets the next four pages。 another thread gets the next four pages。

 So now we have 250 threads doing exactly the same thing。On different pages。

In the end what they form each thread forms the histogram。

 the first thread forms a histogram of ABC D EFGs in first four pages。

 the next thread has its own histogram in the next four pages。

 the next thread has its own histogram in the next pages。

 but at some point if you only to get actually the full histogram across  thousand pages you need to aggregate the results right you need to merge these histograms so when do you start merging the histograms。

 you need to synchronize， meaning you need to know when each thread has completed at in the let's say not so efficient。

 not so high performance model， you wait until all 250 threads finish their histograms。

 and when all of them finish， you say， okay now I can merge the histograms right you have another thread doing the merging of the histograms。

😡，So I have a very parallel part， you do some weighting， and then you have a somewhat serial part。

 but you can also parallelze that somewhat as well， right？

So that's the synchronization this is an example of an SPMD programming model applied to the problem of counting characters in a book。

 right it can be executed on a GPU。😡，Okay， so basically multiple instructional streams execute the same program。

😡，Each program or procedure works on different data and can execute a different control flow path at runtime。

 so we're going to start with this next time because this is going to be important so these programs that are so for example first four pages contain only pictures that are no characters to count。

😡，This program ends quickly right this thread ends quickly the next four pages are heavy with text。

 but it's all ace。😡，Somebody was crazy， they wrote all a。

So there's a different control flow path these two different threads take， right？😊。

The next four pages maybe， I don't know， a very complicated， lots lots of different characters。

 so they all take different control flow paths right to actually compute their histograms。😡。

So I've given you an application program this way。😡，But essentially。

 modern GPUs are programmed this way and execute on C hardware。😊。

So in the next tomorrow I'm at the right place， we're going to talk about an even more complicated part of GPUs which is actually quite powerful。

 so we'll start from here， I'll see you tomorrow and hopefully you'll remember some of what that we discussed so that we can continue。

😡。

![](img/00f85e609c5e524ebfc4fb5264a656cf_4.png)

And。