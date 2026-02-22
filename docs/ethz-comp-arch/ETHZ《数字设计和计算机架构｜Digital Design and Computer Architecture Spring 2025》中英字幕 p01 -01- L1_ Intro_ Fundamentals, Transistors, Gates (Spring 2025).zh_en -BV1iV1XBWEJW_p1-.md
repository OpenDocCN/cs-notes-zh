# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p01 -01- L1_ Intro_ Fundamentals, Transistors, Gates (Spring 2025).zh_en -BV1iV1XBWEJW_p1-

![](img/cfb6fa359400b052df023df1c6899380_0.png)

You you heard it， okay， wow， I didn't hear it。You guys are all very crowded， so that's good。

Are you guys all excited about the lecture？Semester， okay， that's great， yeah。So we're going to。

 let's see， I think the issues are finally resolved。

With live streaming is that good and you can hear me online？Okay。

 so it's good to see a lot of people this room is full。

 I don't know if there is anyone in the other room， but I cannot see。😊，There are some people， hey。

 good。Welcome this is our first lecture of digital design and computer architecture。

 I hope you'll like the course because this is how modern we're going to talk about how modern computers work and how they're built from the ground up we're going to start with transistor。

😊，As an abstraction and we're going to talk about as a switch。

 hopefully we'll get to that today after some introductory material and then we're going to build logic gates on top of that on top of that we're going to build combinational and sequential logic and memories。

 and then we're going to build microprocessors， and then we're going to talk about how to build GPUs。

 sytolic arrays， machine learning accelerators， all quite hot topics， today in executing workloads。

 we're going to talk about a lot of issues in terms of efficiency， performance， energy。

 how to build more scalable microarchitectures and systems so that we can hopefully do good in the world。

😊，That's the goal， right， make our lives better and more efficient， more effective。Okay。

 so that's kind of the lay of the land， I'm going to give you a better lay of the land as we progress。

 but before I start that I'll introduce myself。Well， let's see。

Hopefully yeah I can introduce without the slide also probably but okay so I'm owner Mulu。

 I'm a professor here， I've been here for almost nine years before that I was at Carnegie Mellon University。

 I was a professor over there for some time and before that I was at Microsoft research I started the computer architecture group in Seattle and Redmond actually more accurately and before or during my career。

 I also worked at different places like Google we amware Microsoft。

 as I said Intel AMD and spend some time at Stanford before that I got my PhD at the University of Texas at Austin working on some topics that we'll cover in lecture 25 or so prefetching how to tolerate how to design micro Architures microcroprotorors that can tolerate memory latencies better。

😊，And before that， I was kind of in your shoes。I was a bachelor' student at the University of Michigan between 97 and 2000。

 and actually I took a version of this course from my later tobe PhD advisor， in 1998。

 winter of 1998， and we're going to cover essentially some similar material to what I took what I took at the time。

 but the field has progressed a lot over 25 years， so we're going to actually cover some more advanced material as well like GPU's systoic arrays。

 modern memory systems。😊，So。Looking back I think there's a lot of exciting stuff where we will learn you can contact me with my email address。

 Gmail is much more reliable and you can find more information about me online on the webpage if you don't get a response don't despair because I get a lot of emails unfortunately or fortunate I don't know which one to think depends on your point of view probably but feel free to send email again but you also can talk to me over here during lecture or after in the breaks so I work in computer architecture which is a subject of this course Comp systems hardware security bioinformatics we do a lot of research on these topics I'm going to cover some of this later on but before I do that I will introduce my coininstructor who's over there Muhammad Sader hes a senior researcher and lecture in my group he's been involved in this course for many years and he's been co-teaching it for some time and he got his degrees。

😊，From the top University in Iran， Shariff University of Technology， again。

 his email address is over here， but you can also reach him on any matter over here and he's also doing a lot of exciting research on these topics that are listed here。

😊，And I will also introduce the head teaching and lab assistants over here。

 Constantina is at the front over here， she's been involved in this course also last year and this time。

 and she's also a senior research and lecturer in my group and she got her PhD from Athens Greece。

 a top university there。😊，And Atterbek over there who I guess they're nicely sequenced。

 Utterak is in the middle， he's the head lab assistant， so if you have any questions on labs。

 you should go to Utterbek but you can ask any of the Ts and instructors as well。😊。

I as a PhD student with me and he's doing a lot of exciting research on memory systems。

Okay now you know at least major people involved we're going to talk about the Ts and essays later on so this is my group I will very quickly go over what we do so that you have a good context these are some pictures you can learn more about us online I will not bore you we have a lot of videos etc ce online you can find and I'm proud of my students and postdocs etc cetera you can find more information about us online and me as well。

😊，If you're interested in suggestions I'd be happy to talk with any of you if you're interested in future career in computing etc。

 so this is what we are interested in doing in our research and I'll tell you why I'm talking about this basically we want to enable fundamentally better computers better in many aspects。

 performance， efficiency， robustness， security， reliability。

 safety and we really want better computers going into the future because we're going to rely on these computers we already I think relying on these in many aspects of our lives including safety critical aspects so we need to make computing much better and the course I think this course is very important because it really builds on the fundamentals of how computers work and as a result if you really want to make computing much better。

 you really need to know about those fundamentals。Because if you don't build the fundamentals right。

 then you cannot improve things at higher levels at the software stack。

 you can only program things potentially， but you cannot really change the safety properties。

 security properties that are built potentially badly underneath。😡。

Okay so these are some research actions that we're following I kind of said some of these robustness energy efficiency today we actually are very limited by power and energy in terms of how big of computers we can build and how much power we can supply to a chip so if we can make the chips much more energy efficient this is good for of course energy but this is also good for performance because as you reduce the energy of a single processor you can use more processor to do much better parallel processing and we will see this example over and over in this course so energy and performance are actually very tightly coupled in the design of our systems today。

 improving energy is always better in general。Where we actually are doing a lot of research on low latency and predictable architectures。

 can we actually get predictable responses and some of the other topics that are quite interesting is can we actually have fundamentally intelligent architectures that can over time become better by learning from their environment we call these ML or AI assisted microarchits or architectures that can do better management of the resources。

 better performance so over time you buy a computer for example。

 over time it just gets better it's more efficient higher performance etcter。

 because it's learning your usage patterns or based on the environmental usage patterns。

 the application patterns etc today it doesn't happen much over time the computers get slower and slower unfortunately we want to make it exactly the opposite。

😊，Okay and we're also very interested and doing research in architectures for machine learning。

 artificial intelligence， medicine， genomics， and I will kind of sprinkle some of these during some of these lectures because I like mixing teaching and research for reasons I will tell you later we're going to see this picture a lot today I'm going to introduce it more formally later but we want to solve problems in the end and this is the transformation hierarchy that we have built in systems today about computing systems and traditionally computer architecture is focused on the interface between hardware and software you write some software it gets executed on hardware but there needs to be some interface such that the software gets compiled into the hardware this is called the software hardware interface or IA and at the underlying level this gets implemented using a microarchitect we're going to dedicate multiple lectures on these topics and I'm going to more formally define these in a little bit and this is a narrow view today basically what。

😊，You can do today is you can improve each of these different levels independently and if you do that you get some benefit but today it's become very difficult to get very large benefits by improving one level。

 for example， let's take the system software， if you improve system software alone you get some benefit in terms of performance or energy。

 let's say， but you could get much better benefit if you take a much more expanded view and co-design things across the stack。

 for example， you take an algorithm and you take some hardware and you kind of change both of them such that they meet in the middle and they get much better efficiency and performance。

 if you actually customize your algorithm to the underlying hardware and customize the hardware to the underlying algorithm that you keep modifying。

And this is actually happening a lot in today's systems。

 I will show you some examples but you will see this more and more as we progress in the lectures。😡。

So okay， this is what we do in our research also actually。

 basically to achieve the highest efficiency performance， robustness， I believe security also。

 we really want to take this expanded view and I would like to set this stage early on in this lecture so that you understand the bigger picture that we're operating it。

😊，We're going to see a lot about logic gates， et cetera， lower level things。

 but we're going to connect it to the higher levels also， especially in later parts of this course。😊。

So basically if you can design the algorithm and the devices together and specialize your hardware to the particular algorithm that you're executing。

 for example， in machine learning， people do a lot of matrix vector multiplication。

 matrix matrix multiplication today if you have very customized hardware that can do that in the analog domain for example。

 you can be much more efficient it will be very customized application specific as we will see in this lecture later on。

 maybe it's not very programmable， maybe it cannot execute other things really well like databases。

 but it will execute matrix vector multiplication extremely efficiently and that way you can actually get much higher performance and efficiency and robustness in for example。

 many machine learning applications。😊，Does that sound interesting？Okay cool。

 so this is already happening so I'm going to show you some pictures soon。

 so before I go into that I should say that why am I talking about some of these more advanced topics right now。

 I believe that teaching and research are coupled， meaning teaching drives research like now you're being you're perhaps taking your first course in computing systems design and maybe 10 years down the road based on what you learned you would be designing the best computing systems that no one has designed in the past right？

😊，So this is an enabling and research also drives teaching because when you actually do research。

 you are the first one to discover something， andvent something。😡。

But this is kind of useless if you don't educate the community about it。

 you basically tell your results， write papers， describe your results in conferences like lectures like this。

 and after that point what you have found becomes a domain of teaching because it's known at that point and this is really a nice cycle where teaching and research are coupled so it's good to know the existing in my courses I usually emphasize both fundamentals as well as research so that you actually make the connection between what is fundamental and what is happening today and maybe hopefully you can invent the future going into as you progress toward your career。

😡，给 are三 good。Okay good okay， so courses so if we have a bunch of courses we'll talk about this more。

 but this is essentially the basic the first course that we have。

 I think this is the most basic course that we have where we start with as little assumption as possible based on what you know some of the things we will assign readings on。

 for example I'm not going to talk about binary numbers， binary edition。😊，It's in your readings。

I assume people have seen binary numbers， number systems addition in high school。

 How many people have seen that？Okay， that's great that's I actually took this poll in many classes before and that's one of the reasons we don't cover the binary numbers。

 so that's good if you have not seen it， don't worry you can it's in your readings it's relatively simple we'll go over some of that also in lectures。

 especially when we talk about combinational logic。😊，Tomorrow or the probably tomorrow， actually。

 let's see。Okay， we have other courses also but I'm not going to talk about that now now let's talk about DDCA。

😡，What are we going to learn as I said we're going to learn how computers work from the ground up hopefully it'll be fun and in the end we're going to study different components that go into a system like this this's actually a pretty complicated system you have a system on a chip with lots of computation and caches we're going to look at many components that are in there and this system is actually quiet heterogeneous inside this you see general purpose core。

 special purpose core etc we're going to talk about memory and we're going to talk about basics of how storage is built。

😊。

![](img/cfb6fa359400b052df023df1c6899380_2.png)

![](img/cfb6fa359400b052df023df1c6899380_3.png)

Essentially， as I said we're going to focus on basics， principles of design， I like principal design。

 so hopefully I'll give you some examples of principles and we're going to talk about what has happened。

 meaning precedentnce。😊，And my goal is to enable you to learn how a modern computer works underneath clearly that's knowledge。

 but more importantly， think critically， basically figure out how to evaluate trade offs of different designs。

 different ideas because people actually are very creative， they develop many ideas。😊。

And many ideas have merits as well as downsides， upsides， strengths and weaknesses。

 and developing this capability or ability to actually evaluate these tradeoffs in a scientific and methodical way is very important to me and I hope you get this sort of ability out of this course。

 and I believe this is very useful in anything， not just computer design。😡。

And we're going to implement a principal design a simple microproor in the labs。

 and hopefully you're going to learn to systematically debug this design and this will become increasingly complex as the labs progress。

 you're going to have FPGA labs， you're going to implement on FPGA。😡。

And Albeak is going to talk about that in a few lectures。😊。

And hopefully this background and this hands on labs will enable you to develop novel out of the box designs at some point when youre not expected to do that during this lecture。

 but if you develop it， let me know。😊，So the focus on basics， principles and precedes。

 how to use them to create and implement good designs。😡，You can ask why？Well。

 because you're here for a computer science degree， that's my answer to this question。

How many people are here for a computer science degree？Okay， that's good。 I'm not drunk。

 How many people are not。Because there are usually some small number of people who take this course externally。

 but don't be shy。I'm not going to put you on the spot， it's not a problem。

So in regardlesss of your future direction， I think learning the principles of digital design and computer architectial will be useful for many things。

 you can design better hardware， better software， better systems together。

 make better tradeoffs in design。😊，Understand why computers behave the way they do because these are very very complex systems。

 sometimes it's difficult to understand but you may actually get more insight into why computers behave they do if you know the underlying workings if you don't know how a machine executes instructions whether there are caches。

 whether theres a memory hierarchy whether the processing is done in a GPU CPU or a machine learning accelerator things may be very mysterious when you execute a program and you get some sort of performance knowing underneath always helps you to solve problems better especially if your goal is to solve that kind of problems hopefully you will think in parallel because you're going to design hardware and hardware is inherently very parallel there's a lot of parallel everything is happening at the same time in one clock cycle as we will see soon and hopefully you will think critically and I think these are useful skills to have beyond computer design。

😡，And at this point， I think I should also say that more recently there was this deep seek。

 right deep seek was quite interesting to many people， it challenge chat GT and I think these folks。

Understood some of the fundamental principles of how hardware works and how software works。

 and they actually optimize things in a really nice way so that they could get。😡。

The highest efficiency well maybe highest is to much of an ore claim。

 but they could get much better efficiency than some other folks did。

 so if you can really understand how things work underneath you can optimize the systems and not waste a lot of energy and power for example。

😊，Okay so these are the components of the course clearly we at lectures willll have readings。

 we'll have homeworks， labs and exam i'm going to talk more about that and we'll also have extra credit assignments i'll encourage you to do them I will also say that don't use chatTPT when doing them。

😊，Sorry。It doesn't help you to think critically， but we'll have some guidelines on that later on。

Basically， in all， you will have freedom to adapt your learning style if you use chatTPT。

 make it personalized to you so that it doesn't sound like chatTPT。😡。

So my advice is focus on learning and sky and understanding and not just getting a grade。😊。

That's he used to say for me。I understand that。Okay。

 so learning an exam I already said this I thing basically try to focus on understanding will enable you to learn and prepare you for the exam。

 but during the lectures I would suggest focus on the lectures。

 don't think about will this be on the exam or not that's something we will discuss later on it may be on the exam it may not be on the exam but you don't know that。

😡，It's better to actually focus on the lectures and learn master the material。

 all of the structure of the course， lectures， readings， labs， hardware， not hardware。

 HWs hardware as you can see right I use some lookup table over here and HW translate to hardware。

 but it's really homework in this case homeworks enable this and prepare you for that。😊。

Basically we're going to reinforce problem solving scheme with homeworks。

 and most of you will pass this course， historically it's 80， 85% or so。😊，You can always say， okay。

 what if I'm in the 10 to 15%， well， don't worry about that now。不是。

Because if you worry about the worst change all the time， you can never enjoy things， right？😡。

It's good to think about it that way I think we only release a lot of material to help you with the exam well have problem solving sessions exam guidance and all past exams are actually already online so actually all problem solving sessions except for the new ones that are going to be put are already on YouTube you can actually study for the exam right now but that may not be the most interesting thing to do。

😊，Okay， so I think my summary is learning is for life， it never ends。Exam ends August 2025。

 hopefully and you'll pass。Okay。So basically， that's， I think this is also kind of a summary。

 of course this course is a learning experience， develop your critical thinking and decision making skills。

 long term trade off analysis skills， et cetera。😊，And worry about the exam when the time really comes to worry about it。

 And I think I also believe that there is no one single way of learning。

And we try to enable you to choose and use the learning style that works best for you。

 but it's kind of limited in an environment like this right we have 500 students lectures but at least we can enable the lectures to be like online so it's great that you come to class that's great。

 but if choose you can also watch the class online etc ceter。

 but if you want to ask questions this is probably the best medium to come。

And also we'll have extra credit assignments that will enable you to dig deeper。😊，Okay。

 any questions， I'm going to talk a little bit more about logistics later on。Okay。

 now let's go into a little bit technical material， not transistors yet。

 basically as I said we're going to know how computers work and why we care hopefully at different parts。

 but I'll ask the first question， why do we have computers？😊，Yes， to calculate stuff， what else？

That's a good reason。Why do you calculate stuff， yes？Okay， that's good to make our life easier。Yes。

 problems so solve problems that's why I would come with first， but yes。

 I agree all of those are there to calculate stuff to solve problems and I think automating our life is a problem also we want to solve that problem also basically more most generally I think we do computing to solve problems。

😊，If you reword this insight， why do we solve problems。

 we want to gain insight so that we can solve problemss。

 maybe the computer computing will not solve the problem that we want but we can get the insight so that we can solve the problem right and this is what havingming said when people are actually focusing too much on the numbers that are generated by computer as opposed to the insight that comes out of the numbers。

If you extend it to enable a better life and future， you can define it in different ways。😡，Okay。

 we can go about that， but I'm not going to continue then the question is how does a computer solve problems？

😊，In today's dominant technologies we orchestrate electrons right that doesn't necessarily need to be the case。

 but that's what's dominant today in technology， maybe 10 years down the road。

 20 years down the road it'll be different， unlikely I think this is going to be here to stay for a long time。

 but let's see then the question is how does the problem get solved by electrons right？😡。

Now we come back to the transformation hierarchy that I showed you earlier。

 we have some problem to solve and we have electrons。

And now we have a problem how do I get the problem solved by the electrons I can talk to the electron and say electron go here and solve my problem right that'd be nice and we're not at that stage yet unfortunately maybe at some point humanity will go to that stage where we could actually talk to the electrons and somehow and we're kind of progressing slowly。

 very slowly in that direction maybe but because we cannot do that we have built a transformation hierarchy where we translate the problem。

😡，Into an algorithm。And then we program the algorithm using some sort of language， and then we。

execute this program on target of some system software that can run programs and that system software and the program together gets translated into a software hardware interface which is really the interface between the hardware and software such that the hardware can understand what the program is saying and we will cover a lot of this and then that interface gets the instructions in that interface get implemented using some micro architectectural structures which we will discuss a lot and those micro architectectural structures get in turn implemented using some sort of logic。

😡，We're going to talk about gates today and that logic gets implemented using some sort of devices。

 we're going to talk about transistors， for example today， later on。

 and then those devices operate based on principles of physics， essentially electrons。😊。

So this is the transformation hierarchy as I discussed earlier。

 but now I kind of giving you a more in depthepth treatment。

 and I already said that this is the narrow view of computer architecture。

 but we're going to focus a lot on that narrow view。

 but we're going to look at the expanded view also。😊，Okay， I've already said this。

 this is hemming with this cat， how many people know about heming， which Taming， okay？😊。

Where did you learn about hemming and okay that's great yes， so hemming codes， hem distance。

 hem distance and heming codes he is really the father of coding coding theory， I would say。

 and the work he has done has enabled air collecting codes that are used essentially all computing systems for reliability today。

😊，But that's his cat。Okay。So basically we already said this so I'll go through this trail really quickly。

 you probably have taken some algorithm course right okay so you know what an algorithm is I'm not going to define this because we don't have a lot of time but here's a definition you can read about it。

😊，Programming， you've already taken courses on that topic， right， okay， that's good。😊。

You have not taken system software yet if I'm correct that's good you're going to take it later we're going to cover some system software in this lecture but we're going to system software builds on architecture so you're going to take it later so let me define IA very quickly I've already kind of define it i'm going to deconstruct this definition in later lecture so it's always good to think critically so this is really a contract it's really the interface between software and hardware what the programmer assumes the hardware will satisfy。

😊，That's an interface and we're going to see much more about ISA later on and micro architectureure is really an implementation of the ISA。

 so the same ISA can be implemented a million different ways。😊。

And we will see many different ways of implementing the same ISA。😡。

So you can actually innovate at different levels， ISA is a bit difficult to change because a lot of software is built on top of it。

 whereas micro architectureitecture is easier to change in hardware easier in the sense that you can change it。

 but you need to build the hardware executed， of course， without changing the software。😡，Logic。

 as we will see today， these are digital logic circuits。

 these are building blocks of the micro architecture， for example， gates， as we will see。

 we'll build increasingly complicated logic gates soon， and that's built on devices。😊，Okay。

 so we're going to focus a lot on this area in this course， especially to begin with。😡。

So what is computer architecture， I'll give you multiple definitions， but this is a broad definition。

😊，It's really the science and artrc of designing computing platforms in the end。

 the main traditional focus is over here， ISA and micro architectureiture。

 but today it's really expanded to system software programming model as well as I will show you with some nice pictures soon。

😡，I say science and art because it's not only science， it's not only engineering。

 because there's always an element of things that you don't know whenever you build something。

 especially something that will execute workloads in the future， so you design some hardware。

 you design some platform， it will be out running in the field for five to 10 years， maybe 20 years。

 you have no idea what it may execute。😡，So if you actually have some experience and have some intuition。

 you may actually design a much better system by combining science and art。😡，Okay。

 the goal is of course to achieve a set of design goals and there could be different design goals for different systems for example。

 you may want to achieve the highest performance on Earth on workloads X Y Z today AI is hot。😊，LLMs。

 for example， I want to achieve the highest inference performance on LLMs or training performance that's a super this is a supercomputer essentially。

😊，Or you can actually well you may want to achieve the longest battery life at a swar factor that fits in your pocket with cost less than some Swiss francs。

 this is kind of a mobile computer a cell phone for example right or you may want to achieve the best average performance across all known workloads at some good or best performance and cost ratio this is more general purpose computer it can execute everything but it cannot execute anything the best way。

 let's say but it may not be the worst in everything also。😡。

So these are very different design goals clearly and you could come up with many。

 many different things over here， potentially once you start adding more metrics， for example。

 robustness security， et cetera， this becomes more multifaceted than a multi objective optimization。

😊，So in the end designing these different kind of systems for different goals is different and you need to optimize things differently。

 but many fundamental principles are similar so that's why we're going to start with the fundamental principles in this course now I'll kind of start exercising your let's say brain by showing you some pictures these are different platforms that we have this a computing system also another computing system。

😊，As I mentioned by Mr。 Bean， I mean， we have real ones today， of course， but I think Mr。

 Bean trusts his computing system a bit too much maybe。This is an early self driving car。

 there are newer ones also that I'm not showing， this is a data center。

 it could be executing general purpose workloads or special workloads。

 this is a supercomputer which was the best of its time at some point。😊，It's another supercomputer。

 it has as you can see over here， it has multiple types of processors and GPUs， et cetera。

 I think they've added quantum computers also to this one recently。😊。

This is a chip that's designed to accelerate machine learning computations。

 this is designed by Google， we're going to talk about that in lectures 1718 or so。

 it's operating based on some principles， systoic array， it's a very specialized computer。

 it's not general purpose， but the goal is to achieve highest efficiency and performance on machine learning workloads。

😊，And this is a new version of it you don't need to understand how it works right now we're going to talk about how it's designed later this is just to show you that there are different systems and this is actually designed it's very special purpose。

 but it's not just about hardware this software stack is also designed on top of it meaning Google design compilers programming models etc ceter so that this could be used in data centers this is an example of this cross layer design that's happening right now。

😊。

![](img/cfb6fa359400b052df023df1c6899380_5.png)

This is another computer that's in self driving cars， for example。

 there are multiple of that for safety， I don't know if it's safe enough。

 but it's better than one for sure。😊，But safety is a big issue in general and this is one of the chips that goes into actually the training of data that are actually coming from self-driving cars and you can see that there's a lot of specialization in this chip and the reason people are designing these specialized systems is because there's a lot of data that comes for training and people design actually data centers to do this sort of training with many。

 many chips together and I like this picture from Tesla because this kind of is similar to what I showed you earlier。

 it's not just about the chip it's not just about the software it's really about the system design。

 system stack design so that this whole thing is enabled by doing a better system stack。😊。



![](img/cfb6fa359400b052df023df1c6899380_7.png)

![](img/cfb6fa359400b052df023df1c6899380_8.png)

![](img/cfb6fa359400b052df023df1c6899380_9.png)

Okay， this is a GPU， one of the GPUus of the past。 clearly this is used in machine learning a lot today。

 but also many other workloads and these have evolved very nicely over the years。

 but also it's not just the compute technology， but also memory technology and the interconnect technology。

 These are i charts that show how good your interconnect is don't worry about that。

 you don't need to know all of these at this point。

 is' just to show the example of different computing platforms。 but we're going to look at。

 for example， how a GPU operates fundamentally underneath how does the execute instructions。

 So it's been quite successful because of the way it executes instructions in parallel。

 And because of the way it can actually specify one instruction which can operate on millions of elements concurrently without requiring one instruction per every element。

😊，So it's very efficient in terms of parallel computation compared to CPUs that we will examine first。

 but we're going to get to that and one of the reasons why GPUs have been extremely popular is because of machine learning workloads and they've over time specialized for these workloads。

And it's not just about computers as I said， networking also plays a role。

 we're going to talk a little bit about this， but if you really want to know about networking。

 you need to take a more advanced course because there's not enough time to talk about things。

 we're going to talk a lot about memory。😊，This is another chip。

 which is kind of unconventional because it's this big。

It's basically a wayaf for scale chip and these folks from the Serrera startup designed this so that they can put a lot of memory and a lot of computingness together again for machine learning workload specifically and if you don't believe me this picture kind of shows you how big this is as you can see again this operates based on some principles like CD principles that are kind of similar to GPUs except it's much more distributed across this entire thing it's expensive now think about how to power this huge thing right they actually have a huge system design。

😡，How do you actually program this， so this is all across the stack designs basically。

 which is very interesting。😡，Okay these are potentially future systems where you can do a genome analysis using your cell phone。

 this is an area that my group works on a lot and I'm quite excited about it。

 they don't exist yet but we're actually working on it maybe in the future。

 maybe 10 years down the road， some of you may be teaching this course and you may be talking about genome analysis systems right who knows？

😊，That's my hope。Or bioinformatic systems this is another system that does processing inside the memory chips we're going to talk about that later on these are more recent topics and these are areas that we have been working on for a decade or so finally this already happening in industry I believe so many people have been developing compute units that are inside the memory chips which。

may talk about later on so these are all examples of what I just said earlier。

 basically all of these especially the more recent interesting things require not just the design of the hardware but design of the software together with the hardware so that you can harness the capabilities of the underlying hardware in a much better way。

😡，Okay。Any questions？Yes， when you showed the big chip there was like as big as a wafer Yes like what's the yield oh that's a great question they won't tell you because that's a business secret。

 but yes， that's a problem as you make your chips bigger the probability of faults increase so what they have done in that particular chip is they have some reconfigurability internally so if they find faults they can route around and not use that part of the chip but that's a great question basically yield is always a problem。

😊，Any questions， any others？Okay。Okay so let me give you another definition of computer architecture。

 maybe this is more restricted to the hardware software interface and the micro architecture part。

 essentially it's the science and art of designing。

 selecting interconnecting hardware components and designing the hardware software interface to create a computing system that means many different goals。

 functionality is important performance， energy cost， again safety， security， robustness， etc ceter。

 you could add many different goals over here。😊，And we will see some of these goals as we progress。

 so why should we study it？😡，You can say why actually。

 people have said this interestingly some at different points in time， people have said。

 this is the best chip we have we don't need anything better。

This was said in 1980s you're going to use MIPS IA in this course。

 this was said for MIPS R 2000 for example， this is the best chip we could ever design。

 let's not do anything else。😡，And people are very creative。

 they always come up with new applications， new use cases， et cetera。

 so people are pushing the performance requirements of underlying hardware right。

This was said earlier also， and then workloads always become harder and harder。 Basically。

 we want to make computers faster， cheaper， smaller， more reliable。

For hopefully good we want to use it for good purposes right and we want to exploit advanced and change in underlying technology on circuits also we're going to talk about that later on we want to enable new applications。

 for example self-driving cars is enabled because of the computing technology not just because but in good part because and they're not enabled yet we still have a long way to go I think lifelike 3D visualization 20 years ago it was not。

Easy to think about today actually very close virtual reality personalized genomics。

 this is something that we would like I would like at least maybe you don't like。

 but so basically there are many applications that could actually enable better lives right if I could have a device。

 for example， that could tell me what what my health is going to look like。😊，Next year。

 I could actually take action nicely。😡，And based on my personal characteristics， of course。

 right if you could understand my DNA， what's going on in my body monitor me， that sounds nice。😡。

Maybe we don't want that because you don't want to learn right but that's a personal choice that you can make okay we want to enable better solutions to problems because even old problems need better solutions right we've been using databases for example。

 for 70 80 years and these database are becoming bigger and bigger and bigger and bigger and we cannot really scale them to huge sizes if we don't actually have better computing power underneath better memories。

 better storage devices， better compute devices。😊，And if nothing else。

 we also want to understand why computers work the way they do so that we can optimize things better So there are many reasons。

 I think I think today is actually a special time to study computer architecture because computer architecture has become very heterogeneous when I was studying when I was in your shoes。

 for example， in bachelor's times。😊，CPUus were the dominant thing。

 You had a general purpose computer Intel was actually the dominant company。

 EMMD was small at that time。General purpose computing was a dominant thing GPUs were extreme niche today the landscape is very different CPU is actually much less dominant than GPUs。

 but there is actually a lot of heterogeneity in the systems we build we build a lot of accelerators。

 a lot of different types of compute units， a lot of different types of memories etcter。

So industry is in a large paradigm shift and also research。😡。

And there are many difficult problems to solve， I' will not go through all of these。

 but complexity of design is important power， as we discussed。

 there's a huge hunger for data and new applications， there are difficulties in technology scaling。

 memory bineck we will talk about and a bunch of different issues。

And there are no clear definitive answers to these problems that's why there's a lot of room for innovation that's why you see a lot of startups also trying to solve different types of problems in the hardware software interface and hardware so our computing landscape is very different today as a result every component and its interfaces as well as the entire system designs are being re-examined。

😡，So if you don't have just a CPU， we have many different heterogeneous things over here and we're going to cover a lot of this actually。

 we're going to cover most of what you see over here。😡，Does that sound exciting？Okay， great。



![](img/cfb6fa359400b052df023df1c6899380_11.png)

Okay， so this as I said earlier， even this is very heterogeneous if we're going to look inside that as we progress in this course。

😡。

![](img/cfb6fa359400b052df023df1c6899380_13.png)

Before。Okay， I didn't miss anything， right。😊，Before I go into more detail。

 I should also give you some perspective。 So I showed you this picture， right。

 there's innovation that goes on at across the different levels of the stack。 Sometimes people say。

 okay， innovation that devices have stopped so we should stop investigating it。

I think that's not nice because if you stop research at a fundamental level， you will never progress。

😊，And this is the bottom if you look at this picture， this is the bottom this is the top。

 so I believe there's a lot of opportunity at the bottom today in the past also。

 even though older technologies may have difficulties in scaling to a very small sizes as we will see transistors are becoming harder and harder to build reliably at very small sizes。

 there could be other technologies， in fact I think recently Microsoft announced some quantum technology that they have developed。

 it remains to be seen how real it is， but people are actually doing research and that's great。

 there could be other technologies like carbon nanotube type of transistors etc cea that are actually quite interesting so this is actually a quote from Richard Feynman who's a famous physicist he was a famous educator also he said there's plenty of room at the bottom meaning we should investigate what we can do by manipulating atoms which is really fascinating and he is actually developed a lot of ideas that became more and more。

Over time， for example， denser computing circuitry， better microscopes， swallowing the doctor。

 if you can swallow a circuitry that can actually figure out what's going on in your body。

 that sounds good。😊，Hopefully you'll be still alive after that。Yeah。

 but basically there's a lot of room in the bottom today and it's good to understand the underlying technology today we're going to talk about transitions a lot。

 SeemostOS technology later in the second part of this part of today。

 but keep in mind that there could be other technologies also。😊。

But I believe other technologies can also be harnessed based on the knowledge that you had developed in this course。

😡，And then also there's plenty of room at the top， meaning assuming that the bottom doesn't change that much。

 even if you don't assume that you can actually improve a lot at the higher levels of the stack。

 so if the technology the underlying device technology doesn't become more efficient， faster， etc。

 by changing your algorithms to adapt to the underlying hardware by changing your architecture to be much more efficient。

 you can gain lot and that's what these faults from MIT argue。😡。

So I would actually say you really need to do both。😡。

Basically there's plenty of room both at the top and the bottom。

 but much more so when you communicate well between and optimize across the top and bottom。

 meaning if you can actually design some very fancy device。

 but you may not be able to program it in a nice way。

 I think this is what quantum computing is kind of today。😡，Theyre fancy devices。

 but they're not very friendly in terms of how we can program them if you can figure out how to actually build a stack on top of that just like people have've been doing for machine learning for example you can do much better in that regard so this is kind of the cross layer approach that we have discussed that's why we take this expanded view in this course。

😡，Yeah I should also say that this course might seem only like its' computer hardware。

 and it's true mostly we're going to talk a lot about hardware。😡。

But you will be much more able if you master both hardware and software and the interface between them so we're going to have the interface。

 but we're going to talk about how to actually program things as well a little bit。😡。

So you can develop better software if you understand the hardware and its  quickeriness and underlying principles。

😡，You can design better hardware if you understand the software。😡。

And you can design a better computing system if you understand both， actually。

 So this is something that's in great demand today。

 how do we actually design much more efficient systems。😊。

So we cover the hardware software interface in micro architectureiture and as I said。

 we'll focus on trade offs and how they affect software。

 you'll see that especially in later parts of the course。😡。

And we've kind of surveyed some of these examples。Okay。

 let me go a little bit more into course and logistics。 I've already introduced myself。

 my coin instructor， the head teaching and lab assistants。🎼We also have， let me finish a good point。

Assistants and potential guest lecturers who are part of my group actually。

 who will assist you in many different things， I don't know if any of them are here。Even if they are。

 I may not be able to see them with my old eyes。Okay， I see some over there， Okay。

 there are some myanca is there， Hahiitas there。Okay。😊。

there's maybe hiding and we also have a bunch of student assistants。

 most of whom have actually taken this course in the past and they've actually done well in the labs。

 et cetera， so these folks are going to help you with the labs and I think this course is very successful because these people who take the course later become student assistants and actually help future generations。

Okay， I'll skip some of these if you need help， Moodle is really what's preferred and you can write an email to the list。

 but Moodle is much easier unless you have something pretty personal that you need to discuss with me and the coin instructors come to office hours well provide off our links。

😊，The website is up， how many people have visited it？Okay。

 that's good so you know it you can learn all about this theres everything is going to be on the website this is your single point of access to all resources。

 but we also send you email。😊，So you know lectures are happening clearly you're here。

 that's good attendance is not required but for your benefit and there will be lab sessions。

 you'll be informed about these and you should definitely attend the lab sessions labs will start March 4th。

😊，And you can find the handouts already online。Okay， lab organization。

 you need to choose your preferred group in Moodle and there's a deadline for this these slides are already online so I don't want to go over what's already online you need to choose a partner。

😡，And yeah， you need to feel that if you have a partner， if you don't have a partner。

 I think Albark will assign you a random partner。😊，You can talk， is that correct？Okay。

 you need to partner by the 25th， so this is important， 25th is next week。😡。

So if you want to use grades from previous years， there is a procedure for doing that。

 you can follow it。😊，There's a final exam， as I said， don't worry about it。

 the instructions are there and some of the exam questions are similar to questions。

 optional homeworks and past exam them will give you a lot of information about the final exam。😡。

Okay， maybe this is a good place to stop because this is going to enable us to go into the meat of the technical material。

😡，So let's be back when the。Thing rings。 and we're going to continue。 And if you have questions。

 you can come over here and ask me and the assistant。さ。这说。Yes。す。Oh。上。反 like好。😊，ok。私た。

Let's get started。なせ。好的的。这还是。Oh。こはい。谢谢了。那财我。あはい。我才。This。Okay， can everyone hear me？

And are we okay online？I'll let people come in also。Let's see online looks。Okay。あ。Let me see。Okay。

Okay。ま。Okay， some of you asked about labs willll give you more information about labs very soon。

 but you can find some information also。Labbs should be very interesting hopefully because you're going to actually work with hardware。

 initially not hardware， but over time you're going to work you're going to implement a small simple microprocessor on an FPGA we're going to talk about FPGAs in the lab session but I'm going to introduce pictures of it soon also FPGs are programgamble or reconfigurable architectures on top of which you can instantiate different types of hardware Auto will talk more about that in the lab session。

😊，Okay these slides are online as I said so you can look at them so these are some reading assignments the front end of the course will be reading heavy sorry so we'll have a lot of readings and you can do the readings if you choose to do the readings from only one book I recommend Harris and Harris but both books have very different styles that's why I use both of them in the lectures I actually have a combination and also a complete different style of my own and unfortunately we don't have a book yet maybe at some point we'll have our own book but that remains to be seen。

😊，But I think these two books are actually quite nice books that introduce the material in a basic way so that hopefully you can understand things nicely。

 and we also have supplementary lecture slides on binary numbers but Harris and Harris covers that and also Patam Patel covers that to a lesser extent。

😊，So this is these are the reading assigned for this and next week。

Even though the chapters sound like chapters， there some of them are not that long。

 but this week we're going to cover combination logic next week we're going to cover hardware description languages。

 very log and sequential logic。😊，And within two to three weeks we will be done with earlier chapters in both books。

So if you can， I would suggest。😡，Doing the readings in both books because I'll give you a better perspective。

 but if you have to choose one， I would suggest doing it in Harrison Harris。

And the books actually provide you a lot of information beyond what we cover。

I'm also going to give you your first extract creditd assignment。😊，Which is a good opportunity。

 there a talk that I delivered in June last year that gives you an idea of research。

 hopefully it's a short talk only 30 minutes。😡，And I would like you to write then， well。

 if you choose to， it's an optional assignment， it's not a required thing。

 but if you choose to do a good summary， not chat TPT。😡，呃。Then you can get 1% extra credit。

 1% meaning this is 1% of the grade in the course。😡，It's actually quite substantial， right？

Does that sound good？And I'd like to hear like your what are your key takeaways from this talk。

 what did you learn， what surprised you about the content that's presented， what excited you？😡。

What do you think the solutions should be like based on what you heard hopefully that'll be interesting it's a problem that we have been working on for a long time in my research group and it's a problem that is a lot a lot of impact on industry but I'm not going to give you more you can watch the talk and figure out what it is about。

😊，那在上 good。Who is excited about the talk？Who's excited about the 1% credit， Okay。

 I see more hands there。Kind of expected。😊，Okay。So there will be future lectures and assignments。

You can anticipate and plan for some future lectures based on our spring 2023 schedule。

 I say spring 2023 because I was on sabbatical in spring 2024 and I didn't teach the course spring 23 is more representative of what we're going to cover in spring 2025 so if you want to look ahead as to what may be coming you may want to look at spring 2023 lectures。

😊，And this is kind of a nice example of last time prediction。

Last time prediction is that prediction technique that we will see is heavily used in。

Underlying hardware， underlying hardware executes something， and if it doesn't know what to do。

 it says， oh， what did I do last time when I saw this instruction？😡，It basically does the same thing。

 so it speculates this called speculative execution。

 it's really the concept of doing something before you know that。😊。

That thing is needed and we're going to see this within the context of branch prediction it's really a key concept we will cover in the design of microproors so assuming last time is spring 2023 and if you actually anticipate based on what you see in the spring 2023 list oh we're going to cover。

😊，Let's say combination logic tomorrow。You'll be probably right。Okay。😊。

Does that sound good so we have a lot of resources to you another way of looking at it and these are the additions of DDCA which have evolved over time。

 even this lecture is actually quite different from the EDCA that we taught in 2023 but we're going to be a little bit more efficient in these lectures in 2025。

😊，Okay， so let's start with fundamentals now we're going to go into the material。

 so basically I'd like to build a fundamental understanding to begin with because you can change the world only if you understand it well enough and hopefully our goal is to change the world in a good way。

😊，Especially the basics， past and present dominant paradigms。

 we're going to look at a lot of that and their advantage and shortcomings。

 what remains fundamental across generation is very important， I think。

 and some of the things we're going to build on are going to be really fundamentals that have not changed that much。

😊，And this enables you to figure out what techniques you can use and develop to solve problems。

So I'll start with what is a computer， this is onean Neiman。

 he designed some of the earliest computers in the world。

 and if you think about a computer it really consists of three different components。

 computation units， communication units and storage and memory units。😊。

This is kind of a my my picture of looking at it you have computing units you have communication units and yeah memory and storage units and memory can be memory and stored separate if you look at a computing unit inside it also has some memory units communication units and compute units so these different units may actually incorporate。

😊，Other components as well， and things may be changing as well。Okay。

So we will cover all three components， initially we'll start a lot with processing。

 meaning compute units， we're going to talk about data path control。

 and we're going to look at different ways of designing these processing units。😡。

We're going to talk about memory a little bit initially。

 but we're going to especially focus on memory toward the end of the course。😡。

We're going to not maybe focus a whole lot on IO or communication。

 but you will see this in everything that we do because you need to if you actually generate a result from a compute unit。

 you need to route it somewhere and there needs to be a wire that routes that result to somewhere else right so that's really communication in the end。

😡，But there could be other communication substrates that we may not be able to get into in this course because there's just too much。

Okay， recall the transformation Iarchy I already said this。

 So what people will cover today we're going to start with a transistor as an abstraction to a wall switch。

😊，This is going to be the lowest level lecture except for timing and verification in maybe next week。

 maybe not next week the week after， but lowest level lecture where we will go a little bit into device properties but not too much and then on top of that we're going to build combinational logic。

😡，That doesn't have memory。And we're going to talk about hardware description languages。

 how do you describe hardware which you're going to use in your labs。😡。

We're going to talk about sequential logic that has memory。😡。

And then we're going to talk about timing and verification。

 how to analyze the latency and how to verify circuits。😊。

And then these are at the logic level essentially， and then we're going to move up。

 describe the ISA In set architecture with multiple examples。😊。

You're going to build your labs and MIPS， for example， MIPS ISA。

 we're going to talk about assembly programming， how many of you have done assembly programming before。

😊，Okay， here at EthH or somewhere else。else somewhere else。Not at E age。Okay， somewhere else。

 that's what I expect。Okay this is the ISA level I would say and then we're going to go a lot into micro architectureitecture。

 which is the design of a modern processor， basically we're going to talk about fundamentals build simple and not so let's say not realistic micro architectureectures and then we'll build more and more realistic micro architectureures。

 we'll talk about pipelineing， different issues， we'll talk about predicting branches。

 we'll talk about out of order execution， executing instructions out of order which is essentially what all modern processors do superscale execution。

 essentially we're going to build up to what a modern CPU looks like give or take some which is going to be fascinating hopefully。

😊，But we're going to also look at other paradigms that are actually out there today。

 some of them we're going to talk about data flow， very long instruction word architectures。

 this is going to be actually trade offs between hardware and software in a lot of them。

 systolic arrays， which are machine learning excators that are used in the field a lot。

 and SIMD and GPUs clearly have become quite dominant in recent years。😊。

And then that's the compute part， and then we're going to switch to Memi。

 we're going to talk about memorymy technology and organization。😡，Build a memory hierarchy。

 talk about caches， talk about caches in multi core systems， talk about prefeting。

 and then virtual memory which is really the domain of both hardware and software system software。

 so we're going to expand toward the end of the lectures a little bit more。😊，Does that sound good？

Okay， so you're going to learn a lot， but hopefully you'll have fun。😊。

So these are some of the pressing paradigms we will cover along this。

 so again I' will not to go through this right now。

 but we're going to cover a lot of different ways people have thought how to do computation and processing and I haven't added processing in memory here because I'm not sure you will cover it。

 but I will give you some ideas at some point， but that's another paradigm as well that's being investigated and that's kind of happening today after a long time。

😡，Okay， so these paradigms actually span across the stack because， for example。

 SD processinging and GPUs have a particular way of programming。😡。

And they actually have different ways of designing the micro architecture internally so this is what I mean by across the stack if you think about different processinging paradigms。

 they all have implications across the stack。Okay now let's jump into combination logic。

 so this is what I expect we will cover today and tomorrow probably today we will not get to Boolean algebra we're going to talk about basic building blocks of modern computers transistors and then logic gates and tomorrow we'll continue with Boolean algebra we'll talk about combination logic we'll talk about how to use Boolean algebra to represent combinational circuits。

😡，And we will also talk about minimizing logic circuits， well， I guess tomorrow time will permit。

 but let's see。😊，Whenever I say time will permit， time doesn't permit。Okay。Okay。

But before I go into that， I want to show this picture because I kind of discussed general purpose for special purpose。

 but I want to make it a little bit more formal， essentially these are different types of systems。

 these are just examples and they're all built using the same components。

 they're all built using CMOS transistors that I will introduce on top of that you have combination logic on top next to it you have sequential logic so essentially the building process of all of these are very。

 very similar。😊，But they are actually quite different from a programming and use perspective on the left side over here you have CPUs。

 these are general purpose processor， that's not a great example actually because inside this SOC you have accelerators also。

 but they're focus on the general purpose processor over there， maybe someone let me see。😡。

I cannot even see well， where's the even general per proor doesn't exist over there as you can see right there's GP。

 but there's a CPU over there。There are some efficiency core et。

 okay there you go performance course and then efficiency course。

 these are the general purpose arm processors here。

 but if you look at this SOC it really has a GPU also over here and it also has a neural engine accelerator so this' is not the best picture for a CPU。

😊，But there's a CPU so this shows you also that existing systems are quite complicated。

 even though there is a general purpose component in it， which really drives a lot of things。

 people because of the ability to integrate many transistors on the same chip。

 people are integrated GPUs in there people are integrating machine learning excators。

 people are integrating video processing excccelators， compression。

 the compression excccelators etc ceter， so today's systems even though that's called CPUUs over there。

 it's really a heterogeneous system。😊，But what I meant is really the CPU over there。

 so CPU is general purpose。So the upside of general purposes it's flexible。

 it can execute any program as we have discussed， it's easy to program and use。

 unfortunately it doesn't get to the best performance and efficiency。😊，On the right。

 most side of the spectrum， you have something that looks like this very special purpose。

 it can execute， for example， matrix vector multiplication really well and so it's very efficient and high performance in what it's designed to do。

😊，But it's usually difficult to program and use。😡，And it's inflexible。

 it's limited to a set of programs that do matrix vector multiplication if you want to do a database search and execute it over there。

 good luck。😡，You could potentially， but you have to do a lot of work to figure out how you map your database search to the special circuitry and in many cases that may not be possible or efficient。

😡，So basically this is very special purpose， so that's of course there is a good benefit over here because if you really want to design a most efficient system for machine learning。

 for example， you want special purpose or for genomic analysis， you want special purpose。😊。

But if you。You wantant to execute everything in the world and you want general purpose。

Okay so GPUs are kind of somewhere in the middle this is not GPUs are actually both general purpose and special purpose。

 initially they were special purpose for graphics， but over time they became more general purpose and they're also heterogeneous architectures we're going to cover them if PGAs are more general purpose。

 but also they could be specialized to fit what kind of hardware you want to build their general purpose in the sense that you can put any hardware logic on top of them as you will see in your labs。

😊，But you need to specialize that circuit， Of course。

 you could build a general purpose CPU on the PGA substrate as well as we will briefly discuss in the labs and you will do a part of that actually。

😊，Okay， I like analogies， this is my analogy for a general purpose。

 how many of you have used an adjustable range。Okay， that's very general purpose， right？😊。

So and then there's a special purpose version of it。😊。

If your bolt doesn't fit that special purpose thing， good luck。

You're not going to make it work right so this is this can work with any bolt it's easy to use unfortunately if you actually know what you're doing this is not the best fit for your bolt right so you don't get the best results best efficiency but you can make it work。

😊，Special purpose， it's very efficient than eye perform， it could be it's usually difficult to use。😡。

Unless you're an expert。😊，This is actually a very good analogy， I think if you're an expert。

 you can program a special purpose machine really well if you're not an expert this may be difficult to use at least initially over time you develop that expertise maybe。

😡，Unfortunately， it's very inflexible， it works only for fitting bolts。😡。

That's why you have many of these， right？

![](img/cfb6fa359400b052df023df1c6899380_15.png)

Okay， this is a good example of the trade off and you can think about that， but yeah， so as I said。

 modern general purpose microproors are quite heterogeneous， so they have general purpose core。😊。



![](img/cfb6fa359400b052df023df1c6899380_17.png)

Actually， different types of general purpose course， some of them are optimized for high performance。

 some of them are optimized for low power， they have GPUs。

 they have neural engines which are machine learning accelerators and there other stuff that are not actually marked here。

 but video accelerators， etc ce。😊，So you can see that there is a lot of heterogeneity within a microprocesor。

 okay， you can have fun with it。😊，This is another example from Intel and again you can see something similar over here right you see high performance CPUs。

 low performance and lowpower CPUs， media engines， there's a neural accelerator somewhere but you can find it there are pretty complicated systems modern GPs also have similar things there could be CPUUs there could be GPs well there are GPUs so we have a lot of heterogeneating existing systems so what you'll learn in this course goes into a single microproor in many cases today except for the memory site。

😊，Memory is very interesting， but it's usually separate。

 but we may actually look at models where memory and pro are also designed together。😡。

So FPG this is the FPJ you're gonna to work with we're going to talk more about that and again I'll not go through this so this is a special purpose AsIic that we have looked at I'll go through this relatively quickly because I've already introduced some of these Asics so this is another ASIic for example this is ASIic that Google built for YouTube essentially for video encoding and decoding because they have lots of data and if you use a general purpose CPU or an FPG you don't get good efficiency in encoding and decoding these videos so they built a special purpose processor that can do video encoding and decoding so that they could maximize efficiency and performance and get good cost also at the same time。

😊，Okay， all of these look the same actually， yeah microprocesors at PG A six is a summary general summary slides。

 but they are very different in what you can do here it's very general purpose here you can customize everything for a single application。

😊，The year program development time is very fast here。

 this could be very long unless you're an expert。Performance here。

 so also performance here is great for the application it's designed for。😊。

But I guess if it's not for the application you're design for this is terrible because it may not work so this is good for essentially everything this is good for maximum performance and efficiency and again programming can be done in different ways I will not go through this in detail don't worry about this but you use different languages to program things also for example here use highlevel languages to program here you use lowlevel languages like we're going to use although people have tried actually to use highlevel languages to program low levelvel hardware as well except you don't get a lot of efficiency with high level languages because we don't have very good software support for it Asics are usually programmed with very log etca but don't worry about that right now so basically in the labs what we're going to do is we're going to build a micro pro of FPG we're going to use very log as a language we're going to introduce that and we're going to essentially learn a lot about how these things work in the lectures and you're going implement one of those things or version of general。

😊，On top of FPGA hardware。 So we're going to get used to doing different kinds of things， which is。

 I think， great learning experience。 but it may be initially not so easy to get used to the FPGA。

Okay， and we're going to use the very log language and we're going to talk about why we use the very log language in later lectures next week。

😡，Okay， now's， let's start with these building blocks。😡，Transistors essentially。

So all computers today are built from very large numbers of small and relatively simple structures called transistors。

 I'm going to show you a picture of it。😊，In 1971， the first general purpose microprocessor had only 2000 orrsal。

 2，300 MOS metalloxide semiconductor transistors。P4 in 2000 had 42 million of those。More recently。

 Apple's M2 Max， whose pictures you have seen had 67 billion of those and that has enabled us to put lots of computation capability on a single chip。

 iss actually fascinating， I think。In this lecture。

 we're going to talk about how the most transistor works as a logic element。😡。

We're going to abstract it as a switch。And this is the lowest level， as I said。

 we're going to talk about how these transitionors are connected to form logic gates。😡。

So that and then we're going to talk about how logic gates are interconnected to form larger units that are needed to construct the computer。

😡，The reason we start with a transistor is because it's a very nice abstraction level I think we can abstract as a switch if you go below that things become a bit murky。

 there's a lot of analog characteristics and if you really want to learn about how a transistor really works you should really take a microelectrons design course。

😊，And the reason we don't start with logic gates is to make sure that you have some notion of reality。

 if you start with logic gates， you don't exactly know how a logic gates operates。

 but if you start with a transistor。😡，You will hopefully get an idea。

How a transistor is used to enable a logic gate I'm not going to test you on transistors， et cetera。

 in this course， but the reason we start with the transistor so that we kind of get rid of the mystery of how a logic gate might work how many of you have seen logic gates。

😡，Okay， you've probably seen it where。In a course here or no， okay， high school。

 how many of you have seen have have a logic gate is built using transistors。😡，Okay。

 much smaller number， okay， that's good。Okay this is basically MOS transistor or mouse transistor is built by combining conducts。

 metals， insulators， oxides and semiconductors， and this is what an example looks like this is an old version but they all kind of look the same you have a source。

 you have a drain you have a gates we're going to look at how these actually conduct current soon based on the voltage that you apply to the gate source and drain may or may not get connected to each other so this transistor acts like a wire if you apply the right voltage to the gate。

😊，And doesn't act like a wire， it acts like an open circuit if you apply some other voltage to the gate。

So why is this useful， basically we can combine many of these to realize simple logic gates as we will see。

😡，As I said， the electrical properties of these metal upside semiconductors are beyond the scope of what we want to understand in this course。

 if we get into that then there's a whole new world that opens， which is fascinating。

 but that's not the subject of this course。😡，Meaning they're below our lowest level of abstraction。

 remember that transformation hierarchy， we're going to draw a level of abstraction。😡，But sections 1。

6 and 1。7 and Harris and Harris provide some lower level explanations I will also go into a little bit。

 but not too much。So we're going to look at different types of most transors。

 there are actually two types of most transistors， N type and P type。😡，N moss and Pmos。

En type looks like this。Well it's actually shown like this， you have gates， you have drain。

 you have source， we're going to connect them soon P type looks like this basically gate as a bubble in front of it。

 which means that。For this to be enabled， meaning act like a wire， you apply some voltage。

 for this to be enabled， you apply the inverted version of that voltage。

 so a bubble in logic design always means inversion。😡，Okay。

 so these both operate logically very similar to the way wall switches work。

 how many of you have used wall switches。😡，Lilip the switch right they may not be a switch exactly。

 they may be something you press on， but it's the same principle。😊，Okay。

 so I'm going to go through this in a bit more detail soon， but let me show you this in this case。

 if you apply to the gates， threevolts， high voltage to the end type transistor。

 the circuit is closed， meaning drain and source get connected and this ax axis like a wire so they share the voltage that they are connected。

😊，Pmo is exactly the opposite。 The circuit is closed if the gate is supplied with。Zero wts。

 exactly opposite voltage。😡，Now you may ask me what if I supply somewhere in between， good luck。

There's always a noise margin， I'm going to give you examples of 3 volts，0 volts， if you're 2。

9 volts， you may still be okay if you're 1。1。5 volts。

 that's bad because you may be within the noise margin。

 that's the analog operational characteristics that we're not going to get into。😡。

We're going to treat these as digitally as if you apply。High voltage， low voltage。😡。

Think about as a logical one and logical zero。😡，Okay， yes。Okay。

 that's a different question than the transistor then Taaccca is going to assign you randomly。😀H。😊。

Okay。Did the transistor trigger that question？Okay。😊，は。😊，Okay。So okay， if you didn't understand yet。

 that's fine， we're going to look at a wall switch now。😊，So this is a power supply。

 this is me and I'm going to operate a wall switch and there's a light bulb over here。

 sorry for the rough picture。😡，In order for the lamp。To glow over here。

 electrons must flow from the power supply to the lamp and back， and they should keep flowing。😡。

In order for the electrons to flow， there must be a closed circuit from the power supply to the lamp and back to the power supply。

 so meaning that this wall switch should be a closed circuit act like a wire。😡。

The lamp can be turned on and off by simply manipulating the wall switch to make or bake the closed circuit。

 I guess I could go and try that over there。😡，But。😊，Essentially， for this to glow。

 you need to press on the wall switch， flip the switch， essentially， if you flip it back。

 it will stop glowing， right？😊，This is basic electronics and this is the most basic thing you need you could go into of course the lower level operation of these electronics。

 but we're not going to do that in this course probably you covered that in physics in high school right？

😊，A little bit， maybe。Okay， so instead of a wall switch。

 we're going to replace with a transistor base。😊，Transistor， essentially。

 if you operate it at the levels， voltage levels that we are going to operate them at。

 it acts as a voltage switch。😡，We could use an N type or P type mouse transistor to make or break the closed circuit essentially。

So this is the schematic of an N type mouse transistor that I showed you earlier。😡。

If the gates is supplied with a high voltage， the connection from the source and drain acts like a piece of wire。

 meaning the circuit is closed that way the lamp will glow。😡，Okay， depending on the technology。

 high voltage can range from some small volts to largevolts now we're and talk about power consumption time permits small volts are good for low energy。

😡，High wals our bad for energy ideally people want to reduce the voltage as much as possible so if you look at existing microprocesors。

 people try to reduce the voltage as much as possible so that you don't waste energy。😡。

Does that make sense？Okay， so if we're in the lower end， we're getting to the lower end。

 but of course， with small voltage noise margin meaning whether you can actually distinguish between a 0 versus 0。

3 becomes harder。😡，Distinguishing between 0 and3 is easier because they are very separate from each other。

 distinguishing between 0 and 0。3 is harder， you need much more precise voltage control。😡。

So as you reduce the voltage， things become less and less reliable， so I keep things in mind。😡，Okay。

 so if the gate of the n type transistor is supplied with zero voltage。

 the connection between the source and drain is broken， meaning the circuit is open。

 that's an open circuit so you don't get the lamp to glow。😡，Okay。

 so this is our abstraction basically we're going to build on this abstraction transor as a switch now let's take look at anti transistor in a circuit with a battery and a bulb。

 I replaced the wall switch with my transistor over here。😊，My head became different also。

So if I apply zero volt to this。😡，It will not glow because based on the principle that I described。

 when you apply zerovolt to this is a this is an open circuit。

 meaning source and drain are not connected to each other。

 there's no conductance that happens between source and drain。😡，But now if I apply threevolts。

 source and drain get connected， so current flows over here and as a result， you get a glowing bulb。

😡，So this is our short ten notation before the gate， you could also think of it this way。😊，Okay。

 so key type transistor works exactly the opposite fashion in exactly the opposite fashion from an N type transistor。

😡，It basically acts as a close circuit if you apply low voltage。

 its acts as an open circuit if you apply high voltage。😡。

So it's exactly the opposite and I already showed you this picture and type the circuit is closed if you apply high voltage。

 he type， the circuit is closed， meaning it's the Dan and source act as a wire together。

 connected to each other if they apply low voltage。😡，N sense， all the basics are good。That's good。

 This is all you need Basically， this is the wall switch。

 Now we're going to build some fascinating logic gates out of these。Is everybody ready？Okay。

So we're going to go one level higher in the abstraction now now that we know how a mouse transistor works。

😡，How do we build logic structures out of most transistors？😡，So we're done with the device level。

 except we may actually have a 4a into it a little bit。😊。

We're going to construct basic logical units， these logical units are called logic gates。

 they implement simple Boolean functions， how many of you have seen Boolean algebra。😡，Okay。

 that's good in high school。No， or here， here， okay， that's good。Maybe in high school also。Okay。

You can read George Bull's paper about it。Okay。😊，So a modern computer is used both N type and P type transistors。

 this is called CMOS technology you may have heard the term CMOS complementary metalloxide semiconductor and there is a reason why we use CMOSs as we will see it's again a lower device level reason。

 but I'm going to show you how it works first and then we will go briefly into the lower device level reason and then we're going to assume that after that。

😊，And we're gonna， we're not going to touch transistors that much until we get to some other parts of the lecture。

 So basically， N Mo plus P most is C most。I'm going to show you the simplest logic structure that exists in a modern computer。

 now simplest is kind of an overstatement， but simplest CMOS structure， I should say。😡。

It looks like this。So as you can see here we have an Nmost transistor。😊。

Here we have a Pmo transistor， the bottom part of the Nmost transistor is connected to zero volts。

The top part of the POOS transistor is connected to three volts， high voltage。😡。

And these trendss are connected to an output over here。Well， let's call Y。 and then we have an input。

 Let's call a that's supplied to both of these。 So I have a single input， single output gate。

With two transistors， it's complementary metalloxide semiconductor transistors。Now。

 my question to you is what does the circuit do？Maybe tough to initially。 Okay， I kind of said yeah。

 what does the circuit do。Anybody。😊，Yes。Okay， that's good， it immers the signal。

Does anybody else agree， who said it in words the signal？It basicallyically a。

 y is the complement of a， essentially。Yes， no， okay， who says no， it does something else。

Don't be shy you're just learning Okay fine maybe you don't know it's good to say don't know Okay so that's essentially what it does And let's take a look at why it emerged a signal based on what I just described earlier。

 what happens when the input is connected to zero wts This is me again coming in applying zero wts to the circuit that's our input。

😊，And this is let's see what happens to the outputs。So if this is zero wts， remember。

 based on the operational principles of the NOOS， this acts as a。😡，Open circuit。

 meaning this wire is not connected based on the operational principles of the pimo。

Transistor this act as a closed circuit， meaning this is a wire。

So what happens is output gets connected to three volts and based on the current flow。

 output becomes three volts。😡，Make sense。So now if you put input is zerovolts， you get three volts。😡。

Looks like it emerged now let's take a look at the other。Things that we can supply to the input。

 and I'm going to restrict the inputs to only zero  wts to three  wts。😡，Sorry， you cannot do 1。

5 volts。Or anything in between。 So the reason is P type transistor pulls up the output。

 you can also think about it。 And I there's a reason why I do a PP over here because P type transistor is actually good。

😊，At pulling up the output based on the operational principles of electrons and holes。

 which we're not going to get into right now。So you want P transistors pulling up。

 you don't want anti transistors up there。😡，We'll see that。

So a p type pans are good at pulling up the voltage okay。

 what happens when the input is connected to three  wts to look at the other case？😡。

A is threevolts here and it's kind of exactly opposite as expected right because P type transistors based on so operational principles。

 it becomes an open circuit at high voltage applied to the gate so this high voltage disconnected from the output n type transistor if you apply high voltage to the gate it becomes a close circuit so this becomes a wire and essentially the output gets connected to zerovolts and this n type transistor pulls down。

😡，The output。Nicely in and down， share an n。It's good for memorizing。

Because it's it's easy to could get confused。 But anti parameterss are actually good at pulling down the voltage。

 So I've， I've shown you a basic circuit right now。 This is called the CMmo not gate inverter。

 It consists of one P type transistor connected to。😊。

The high voltage so that it can pull up the output， it consists of one anti transistors。

 it's connected to the low voltage shot it can pull down。

So we call it nots because it really inverts the signal。 If a is 0， you get。Threevolts in output。

 if a is 3， you get zerovolt。😡，So one possible interpretation is interpret  zero volts as a binary or logical zero value。

 Boolean zero value， interpret3 walts as logical binary1 value now you can do Boolean algebra with this。

😡，So let's take a look at a truth table， I'm going to design truth table。

 a truth table basically shows you the output that you will get in a logic circuit for all possible input combinations here we have only one input。

😡，So there are only two possible combinations in Boolean algebra，01。

I'm going to show you the intermediate states of the transistors also。

 but we're going to compact this later on。😊，So if the input is0， p type transfer is on n type is off。

 you get one at the end at the output， if the input is one， p type is off。

 n type is on so it gets zero because the output gets pulled down。😡，Makes sense， right？

So this is the Boolean representation y is equal to complement of a。😡，This is also shown like this。

 it's an inverter， remember inversion is always with a bubble， we'll see those bubbles later。

 don't forget that bubble because if you don't have this bubble this is a buffer。

 why should be equal to8 if you don't have that bubble？O给。So truth table。

 as I said shows the logical output of the circuit for each possible input combination and in this case our truth table is very simple。

 this is the input a could be 01 and y is a complement of it。😡，都在上课。Yes。

Use impact system do we need ground here。あし要も。Okay， that's a great question， we'll get back to that。

 keep that in mind， okay。😊，We're going to talk about pseudo andmos。

 but let's not get into that right now。Okay， let's build a little bit more complex gates。

 You can actually imagine different ways of doing that。

 but they are different they because transistors are not perfect。

 We don't use one transistor in general， but there are some special cases。 Now。

 let's build a more complex gate。 Now， what is this。😊，Can anybody figure this out？

Quickly because we're running out of time。And I want to cover this so that you can think about it。

 yes， like an okay。😊，And gate。Any other？Yeses。You're close， but not exactly correct， yes。And Ngate。

 okay？You had something else？嗯。是这分の什す啊。Okay， that's all right， it's a end gate actually。

 but don't worry if you don't guess it basically now we have two Pmost transistors in parallel connected to the output over here and connected to three volts and two n most transistors in series connected to the output and connected to zero volts and we have two inputs A and B supplied to both。

😊，N most transistors and P most transistors。Now let's take a look at this operation。Again。

 I'm going there because you have two inputs each of them can be taking values of0 or1。

 you have two to the two input combinations， both AM andmb can be0。

 well00011011 so the realization is that P1 and P2 are in parallel。😡。

Only one of them must be on to pull up the output to three ones， so if， for example， t1 is turned on。

 which means that you get a zero。😡，Input over here。Three wts will be connected to the output。😡，And。

At that point， you will hopefully get disconnected circuits over here because this is a complementary metaloxide semiconductor as we discussed。

 so let's take a look at one case over here。If both of them are zero。😡。

Both Q1 and P2 are on and three wts get connected to the output in both paths。

 which is okay based on K cost laws， et ceter， you'll get three wts out here。😡。

And anyone and2 are off because they don't get enabled because input because the gates are voltages applied to the gates are zeros and zeros okay now if。

😡，A is0， and D is one。P1 is on， P2 is off， but 3volts still get connected through this path to the output and output doesn't get connected to 0 volts。

 which is good because you don't want output to get connected to both3  wts and 0volts that's not good then you don't know what the result would be so output is still one。

😡，If B is let's see B is0， then p2 is enabled on P1 is disabled。

 it's essentially the same type of situation except different transistors are enabled and disabled。

 so you still get a one in the output the only case。

You get a zero in the output is when both inputs are one。😡，If these inputs， A andmb are both1。

 P1 and P2 are both off because of the way PmostOS transistors operate。

 so output gets disconnected from output is not connected to 3 wts。

 but both of the NmostOS transistors are on based on how NMOS transors work。

 you get  zero wts and they act like a wire and the outputs will be0。😡，Makes sense。

 right So only when A and B are one， you get a zero on the output。😡，This is a Nant circuit。

You can think of it as。A and B inverted。So what is A and B， A and B is one。😡。

Only when both A and B are one。In all other cases it's zero。

 but you get an inverted function of that here， so it's AB inverted。

 so this is the notation that we're going to use A and B。

 you may have seen a different rotationation， but this is the notation that's used in logic circuits in general。

 so it's AB prime does that make sense or AB complement。😡，Okay。So this is this looks like this。

 A and B。Nand gate is like this， Nand gate is with an inverter。

And this is what the truth table looks like。And I'm showing you this truth table。

 we built this truth table actually in the previous slide， does that sound good？😊，No magic here。

 right， It's beautiful。So how do you build an end gate on top of this？😡。

This is an end gate that we want。 It's really the inverted version of what we built earlier。

And this is also the logical expression， Boolean expression， A and B。😡，Unfortunately。

 there's no easy way to build an end gate。Except by starting with a N gate and adding an inverter to it。

😡，So this is an N gate and you add an inverter to the output of the Nand gate and that's your real output at the end。

 and output y is really a function of and function of A and B over here。😡，Now。

You can be clever and you can say I can do better and yes you can。

 you can use fewer transistors for the end gate， but what you will come up with using the properties of POS and NmoOSs technology will not work。

😡，Because these are not。😡，Even though we treat them as perfect switches。

 they're actually not perfect switches。 P most transistor can pull the output up。

 and most transistor is terrible at pulling the output up。So putting the M transistor。

Connecting it to threevolts will not work。😡，If it worked。

You could design N gates with much fewer transistors and I'll let you think about that。Okay。

 so basically these are the gates that we have we have the CMmost knot gate over here。

 this is the gate level。😡，This is the truth table and this is the transistor level in the future。

 we're going to ignore the transistor level because we built the subtraction。This is the Nand gate。

Again， gate level， truthth table。And transistor level， and this is the end gate。

Gate level fruit table and transistor level。 So you can see that end gate is more expensive than N gate。

 right。😊，Yeah， tomorrow we will see Boolean logic you can build everything using just N gates actually。

😡，Let's see so this is the general CMmost gate structure。

 the general form used to construct any inverting logic gate， not Nanda nor。😡，Basically。

 you have a PmoOS pull up network。😡，And at the top， connect it to three wts。H will touch you。

You have the Nmost pull down network connected to the low voltage here and both of them are connected to share and output over here and inputs are supplied to both when we finish this and then we' done we'll be done the networks may consist of transfer in series are in parallel both of them when transfers in parallel are in parallel the network is on if one of the transfer is on when the transfer in series the network is on if all of the transfers are on。

😡，Okay， Pmo transferors are used for pull up， the others are used for pull down tomorrow we're going to start with this and we're going to build much more logic gates we're going to do a combination of logic。

😡，So I'll see you tomorrow。个。

![](img/cfb6fa359400b052df023df1c6899380_19.png)