# CppCon【中英⚡CppCon 2024】 p12 P13 Boosting Software Efficiency in C++： 100% Performance Improvement in a  C++ -BV1NHEEzdE92_p12-

![](img/b557ea0c0d5fb5ca7f7530232018f3aa_0.png)

The talk today is about software development。 I worked on a product for two years。

 and during this time， I drastically improved its capabilities。

 I wanted to share with you the journey Ied。 I hope you will get some useful ideas and inspiration to improve your own product。

😊。

![](img/b557ea0c0d5fb5ca7f7530232018f3aa_2.png)

So my name is Gilicma。 I have 20 years of experience in the industry。

 I have B science in electronics， but I prefer software。 I love to improve things and solve problems。

 and currently， I am team leader the right priority software。😊，My story begins several years ago。

 I moved to Denmark with my family， and I've started to walk in camp stop。

And the business of catop is metals。 And when I'm saying mes， I'm not speaking about distance。

 I'm I'm speaking about water， heat and electricity mes。😊，And specifically， smart metering。

Smart metering is a system that uses digital devices to automatically send your utility data to the provider。

So this is the system end to end。 In one side， we have the water metals。

It installed in the houses and measure your water consumption。

 And all the time it's transmitting in wireless the measurements。

 So every 16 seconds or one minute or two minute depends on configuration in the adult side。

We have the reading manager。The ready manager is the becon。 This is the billing system。

 So they are the one who responsible in the end of the month to send you the bill。And in the middle。

 this is the middleman。 This is the product I worked on， the ready concentrator。

And his job was to collect metal measurement from the water me。Wirelessly。

 and send them to the cloud by cellular or mode or etthernet。

And what is important to understand is that the business is data。

 So loss of data means loss of money。And in general， we have two interfaces， one。

To the water metals that all the time submit in data。

 So we are getting in throw you out in the ready concentrator， the frames。

 And the other interface is for the ready manager。😊，Falgo baconant。The problems。Originally。

 it built to work with less than 1000 water mes， and it worked perfectly fine。

 But after several years。😊，It was expected to walk with 7500 M Ms。

 Some small engineer did some calculation and find out this is possible。

So that was they sold to the customer。And what we got when， we tried to walk with 7500 mes。

Their product was unstable。And then when the product unstable。

 it means that our customers are not happy。And then， of course。

 also the developers are not happy right。And if to be more specific about the technical issues。

 So I had memo issues。We didn't have enough memory in the system。

And I had some unexplained crhes in that I didn't know why。

And sometimes we also lose data during a network problem。But it， but it was only sometimes。 And。

 of course， none of the errors were seen in the lab。Technologiesistic。Linux kernelnel。

 yok to distribution， all the image， no sources。 So it worked very well， but we couldn't touch it。

32 MBby Ram。 It's important because later I'm going to speak about numbers。It was seen as plus min。

But not really。 it more， it was more in a style of C plus plus 11 even a little bit earlier。

 So even we didn't use smart pointer at all。And they are also heavily used in Qie。

QT is an application framework。 This is a appeal to low level programming。

And the good thing about Qie that it feels like C sharp。 So even if you are not a embedded expert。

 you can write your code on embeddedbed the bad news about Qie that it feels like C sharp。

 but you don't really have a garbage collector okay so the perform us not so good。

 and it's also really encourage you to send to create dynamically objects all the time。

 but it doesn't encourage you to delete them。😊，Okay， so what was my goal。

Reduce to  zero loss of data and create a stable product。 Sound simple， right。 So the question。

 how am I going to do that。😊，Okay， so it was for me a new company， a new product。 So I start to look。

 of course， no documentation is always right， that the way it works。😊。

And that was my first impression。 After several days， I started to look at the code。😊。

I saw a lot of news and delete。 And I was like。What they supposed to do with the write its embedded system。

And I was really shocked about it。 like I didn't see it before。But then it， it clicked me。 O， it's。

 it， it made sense to me because as I said， okay， I have a lot of news and deletes。

 It means that probably I have me leaks。 It's when I forget to release everything I'mocating。😊。

And probably， I have memory fragmentation。 And this is 20 seconds on memory fragmentation。

 Let's assume we have 100 B of memory。😊，And now I am allocating 40 B and then 20 B and then 40 B。

 And now I am releasing 40 B and 40 B。And now I want to allocate 50 B， later problematic， right。

 even though I have the memory。 Now， imagine all your memories like this。

 This is memory fragmentation。😊，Okay， and that explain why I don't have enough memory。

And it explain why allocation fails。And， of course。

 I'm not checking anywhere that if Im trying to allocate， I succeed。 So I'm accessing N， right。And I。

 and then I got this uncontrolled reset， the， Q E D。Great， right， wrong， wrong。 It's not wrong wrong。

 but it's wrong in this case。 So let's go back to this line。So， after investigation。I。

 I didn't have a lot of me relics。 So that wasn't my problem。

 And I also didn't have memory fragmentation。 But in this point of time。

 I was sure this is the problem。 So all what I need to do clean the memo relics。

Find the problem of the memory fragmentation， and everything will be finite light。😊，But anyway。

 I needed to test my assumptions， right。So for that， I developed memory portfolio。

The memory profiler gave me a good understanding of the sizes and the quantities of allocations。😊。

And it's important to say that I couldn't use standard memory profiler as the Linuxux kernelnel was old。

 very old。So in general， when I have a location and releases， it's supposed to look like this。 Okay。

 so I have some maximum value。 And in some point， I， I just expect it to be stable。😊。

But when I have memoics， it's going to look like this。

 It just getting up every time because I'm not releasing everything。 I'm okay。😊，Okay。

 so let's speak about interesting measurements when I'm using my memory profile。

 So one interesting thing， is's number of allocation， allocations per second。😊。

Let's assume I have only two dynamical location per second。 Okay， so I don't like it。

But we understand that this is not a problem right。

 My system can live with this to to dynamical location per second。 Now， let's take the adult side。

 Let's assume I have 2000 allocation location per seconds。 Okay， so at this point。

 I think the system is not going to work at all。 right， So it really depends。Also。

 interesting current and maximum number of allocations。Because if I have me leaks。

 it just the maximum， supposed just to get I and higher and higher all the time。

 And if everything is good， it just suppose in some point to be stable and consed。😊。

And it's also very interesting to see the gaps， the difference between the current and the maximum and see how it breaks and how its changing over time。

😊，The same thing about the bys that are allocated。 So they are the numbers of the allocation location and the bite themselves。

 similar， but not exactly the same。And I think this is super interesting。

 current and maximum allocations， perarl size value。 It means how many a location of 100 by。

 how many a location of 1000 by， Why this is so interesting。😊，2 reason。One。

 it's very easy to find memo relics。When， when you have these values， because if everything is。



![](img/b557ea0c0d5fb5ca7f7530232018f3aa_4.png)