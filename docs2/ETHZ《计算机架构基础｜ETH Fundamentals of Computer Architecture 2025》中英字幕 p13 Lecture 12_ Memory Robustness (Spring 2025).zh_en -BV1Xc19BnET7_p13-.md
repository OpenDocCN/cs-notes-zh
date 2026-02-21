# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p13 Lecture 12_ Memory Robustness (Spring 2025).zh_en -BV1Xc19BnET7_p13-

![](img/4281349ccf53b3eafe6978d710441345_0.png)

So。对不起。没。资量是3个。ますね。呃，但你这边去没锁。你咯第个发疗又佢。是。み合わせたますよ。Oh。Yeah。Okay。🎼Thanks。

 can start the live stream too I think its the right one。🎼Yeah。

🎼Could be though if it's the previous one， that's also looking and you start it。我这。然后。是。对对。

I think we can get started。Today we're going to talk about memory robustness is's going to be also quite research oriented。

 but it's also very fundamental。Um， we're going to talk about issues like bit flips in memory that we started last time to motivate part of memory centric computing。

 but we're going to go into more details。If。Let's see it's going to be an intense lecture there are a lot of works in this area that are quite exciting I think and there's more to discover。

 which is the interesting part。😊，Okay， let's see。Zoom playing tricks。This is not connected。

 I think her。I'm not sure Okay， maybe maybe because of Zoom， Okay， yeah yeah yeah， I see， Okay， okay。

 I figured out thanks， this's another title for this talk。Okay。

 so this is the work that started a lot of it actually I'm going to talk about this one a lot。

 this is our IA 2014 paper it was rejected once that's one thats why it's not a 2013 paper this could have been published in 2013。

And they got rejected and then it got published at riskca 2014 spurred a lot of work on top of this。

 but I'm going to give you a story so I'm not going to talk about that directly how many people know where this bridge is yes what does mean Oh reject it very good yeah basically when you do scientific work you usually try to publish it and you send it to a conference。

😊，And the conference decides whether they want to take the paper or not take the paper based on some review process not necessarily limited time slots。

 they may consider this paper not so interesting for example。

 yeah peer yeah basically you sent it for peer review and when you send it for peer review that means you get some reviews and their reviews may not be positive for publication initially when we submit it in micro in 2013 we got not so positive reviews I'm happy to share them but we don't have time they're in the backup slides if you're interested in seeing the use they're in the backup slides。

But viewers do not necessarily make the right decision in my opinion that's why you got to believe in the work and do it and do it in the right way and then viewers make the right decision in my opinion for the next conference and I think they were p to have made the right decision in my opinion because there are many。

 many， many， many papers that replicated this work many times over and many papers that built on this work also its an example there are many。

 many examples of this this is my personal one of my personal examples but other people have a lot of examples also yeah so basically take their U process with a grain of salt also because they don't necessarily do the right thing as well right doing the right thing is very important but people have not figured out how to do the right thing in general in the world okay anyway without going into more let's say。

😊，Philosophy， do you guys know where this bridge is？Yes， Washington that Washington State。

 the exactly， the commonarrowrows bridge， yes。But that's the wrong answer。

Because this bridge doesn't exist anymore， basically this is what happened to this bridge。

 a bit flip， in my opinion， a reliability problem， that's the right answer basically in the sense that it used to be there Tacoma Earth bridge。

😊，And I think it's a reliable problem you can read a lot of audits in bridge building。

 civil engineering， etc， but basically these are this is an infrastructure that is very valuable for humans today we're building the computing infrastructure if we get bitflips in our computing infrastructure。

 the consequences will be much worse than this in my opinion and in many cases。

 okay another example these folks are building some city and they're sitting on this road they're very happy right now。

 but if a bitflip happens on that road they're not going to be very happy。😊。

So basically I think of security about preventing unforeseen consequences， it's a very。

 very general statement about security in general， you can think about this maybe safety also robustness in general。

 but we would like to be able to prevent unforeseen consequences by designing our systems to be robust it's very difficult problem it's not an easy problem to enable this。

Okay， I like this picture also we have self driving cars today that are making decisions for us before in 1990s Mr。

 Bean didn't have self driving car so he's driving his own car in a self drivingriving mode。

 let's say and he is the AI engine that is taking the decisions over here。

 but if a bit fliplip happens over here， he may not be very happy either right？😊，This is fun。

 of course， but you can imagine the real implications as we discussed last time we talk about Rohammer to motivate intelligent memory control。

 we're gonna do more of that， but you know Rohammer。

 so I'll go through some of these relatively quickly essentially a Ro hammer is the fact that you can predictably induce bitfs in the EM chips and all recent EM chips are fundamentally vulnerable and the paper that I showed you showed that initially and it's really what's really fascinating is it's also the first example of how a simple hardware failure mechanism can create a widespread system security vulnerable In fact。

 this paper was's taken by a lot of security folks and shown that oh you can actually do all of these different cool attacks by exploiting these bitfs I'm going talk about some of them and you see that people are writing interesting articles that sound like forget software now hackers are exploiting physics and this is a nice accurate statement actually because it's really about physics's what's going on is really about physics I will not go into a lot of device level works but I will mention some of the device level works also so I showed you this paper before this is a paper that we wrote before the Ro hammer paper actually。

😊，vi paper at IMW conference essentially we argued that there are going to be a lot of problems with memory going into the future。

 we were not the first ones to argue that but we provide our perspective and say we said that basically we need to solve the issues that we're going to have with memory going into the future meaning to take a much more system level perspective meaning design intelligence controls essentially。

And I'm going to present another paper next week actually in the same conference。

 another invited paper discussing what the status is 12 years afterwards。

 if you're interested in also a short paper to look at。😊，Okay， so what are its old issues。

 so main memory technology today is DM dynamic random access memory it was in met in 1960s by Bob Denard and the idea is very simple you have a capacitor that stores the charge and the charge level one or zero is indicate essentially whether a capacitor is charge or discharge indicates whether you have one or zero and they have an access transistor that's enabled to share the charge of the capacitor with a bit line and the sense amplification circuitry so that you can sense whether you have charge stored here or you don't have charge stored here。

some noise margins of course for this circuitry to work this is just a single bit and this is very dense because you can make the capacitor very all of these very very dense as I'll show you in the next couple of pictures basically this is a charge based memory and for this to work the capacitor must be large enough for reliable sensing and the access transistor must be large enough for low reage and high retention time and all of these structures need to work very well also so there's a lot of let's say art and science and engineering that goes into making this work today because we're at node levels of 10 nanometers or so。

😊，And this is a report in 2009 from international technology robotm of semiconductors at the time。

 and they basically said scaling the circuit feature size。

 the minimum feature size below 35 nanometer is challenging and they were absolutely right。

 it's actually quite challenging to scale things， but people have scaled down， but it came at a cost。

So why do we want to scale the circuit smaller and outside essentially we want to pack more bits in a given millimeter square so that we can have higher capacity memory。

 scaling is also good for our energy， although that's debatable today， et。Okay。

This is another view of the chip actually if you do if you put it under microscope you see cells that look like this it's like the mesh type of structure hexagonal this another view if you're interested you can see more videos etc cetera。

 so you can see that the capacitor are actually etched into the substrate in a vertical man。



![](img/4281349ccf53b3eafe6978d710441345_2.png)

It's like a skyscraper where some people like to use these analogies。

 so people actually to do a lot of tricks to design DM today， which is actually very interesting。



![](img/4281349ccf53b3eafe6978d710441345_4.png)

Except the difficulty is as the cell size becomes smaller it becomes less reliable right charge is reduced retention time is reduced as a result you're more likely to lose charge quickly and also you're more likely to have noise effects that are disturbing you and we're going to talk about some of the noise effects today does that make sense okay？



![](img/4281349ccf53b3eafe6978d710441345_6.png)

![](img/4281349ccf53b3eafe6978d710441345_7.png)

Okay so we did some studies， I think I mentioned this in I don't remember if I mentioned this one in the last lecture。

 but essentially we did studies with Facebook， for example the large scale。

 we analyzed the memory errors that they see DMs that they see in all of their data centers。

 it's actually a lot of memory it's amazing this 2015 we did this work in 2013 or so they have much more much much。

 much much much much， much much more memory today because a machine learning they actually increase that memory size。

 I don't know what that is， but the numbers they didn't allow us to publish in 20415 today they will not allow anyone to publish those numbers it's a bit crazy but basically the takeaway we analyze all of the errors that that were documented that were recorded automatically in their memory systems across all of their data centers and we show that there is a correlation between the density of the DM chip that's employed in the server and the error rate that you get in the server so as memory chip becomes denser you get more failures and some of these failures get reflected in the application etc sometimes you need to go on。

Replace things， yes， are there also metrics available for。Say8 more even 6 gigab yes。

 and newer papers。Yeah but this is 10 years ago at that time those chips were not there today we have8 gigabits this is actually gigabits but this is a single DM chip so there are certainly newer papers that actually look at this。

😊，And the trend is similar basically， as you reduce the cell size as you make the chips more dense。

 you get more errors。But we'll talk about some of the other things people are also trying to mitigate some of those errors。

 adding ind earthquake ands， et。Okay so if you're interested。

 that's the paper from 2015 okay so we also were building a lot of infrastructure to understand some of these technology scaling issues because basically the chips become denser with technology scaling and technology scaling clearly is good for capacity but not good for reliability and we wanted to understand what are the other issues that may come up this is the first infrastructure that we built you can see that it's kind of makeshift and over time we improve the infrastructure you've seen these pictures last time before this is actually where a lot of the Ro hammer experiments were done that's at CMU and this is the open source infrastructure of TC you can read papers Ubender here I worked a lot on these different topics he's in the back he could actually do this lecture also he has done that before multiple times and this is some of things that he has worked on for example and this is for time so you can see a lot of these pictures so why did we build this infrastructure actually reason we built this infrastructure was to really understand data retention because we believe at the time in 2011 or so that retention retaining chart。

In cells actually going to be much more problematic going into the future because cells are becoming smaller。

 the number of electrons you can keep in that cell is going to reduce and reduce and reduce and this's going to become big issue it is actually a big issue。

But there are other issues also， it turns out so we had this cool idea in my opinion to exploit heterogeneous retention time so if you look at because of process variation the EM cells actually have a lot of variation in terms of how long they can retain data。

😊，At the time we were refreshing the every 64 milliseconds based on the standard but we asked the question。

 do you have to do that and you don't have to do that and it' is not actually a new idea also what we propose a implementable memory controller based solution to actually implement with low cost the idea is basically refresh cells with different retention times at different rates it turns out this not this is easier said than it's actually a very tough problem because it turns out these are dependent on location these are dependent on the value pattern here these are depend on time so you cannot just do this easily unless you add error correcting codes etc so if we wrote papers on this topic this is one paper that was an IA 2012 where we said oh if you actually are able to do this you can get a lot of benefits you can reduce the refresh rate significantly here。

You don't refresh everything every 64 milliseconds， you refresh some every one second， for example。

 it could be one second， but yeah it's possible basically as long as you characterize it so we built this infrastructure to characterize。

😊，The different DM sets and this is actually the paper we wrote with the first paper we wrote using our infrastructure to understand the data retention behavior and we said that basically the previous paper we wrote is very difficult to implement in real life it's a good idea。

 but it's very very difficult to implement in real life unless you do something about it。

And we basically said I'm not going to go into the details。

 but there are issues like variable retention time data pattern depends that are difficult to handle actually I don't have another paper over here。

 but we also wrote a paper in DSN in 2015。😊，To solve this problem in a reliable and robust manner and it turns out that's going to be awarded the test of time award at theN because it's actually a solution。

 it's actually a very good solution to that problem it's called avatar a variable retention time and refresh and we use air collecting codes and memory scrubbing to understand which cells for which cells you can actually reduce the refresh rate significant。

W is fascinating okay okay so we actually at the same time we were building infrastructure to test flash chips so this is actually very interesting we have some work in this area which we're not going to talk about right now but we'll have one lecture I think on flash memorym next week great so you'll get to learn about flash memory as well which is essentially all of the storage all of the interesting really interesting storage that we have today I believe flash memory is really an enabler of devices like this if we didn't have flash memory we couldn't really store huge amounts of data in devices like this at low cost but basically we were building an FPG based infrastructure to test by flash memory as well and we actually look at error patterns in flash memorym this a paper from 2012 and another paper from 2013 Intel invite us to write paper in their technology journal at the time to understand flash memory errors etc and it's a more updated paper invited to the proceedings of the a that actually summarize a lot of research that happens over the course of maybe eight nine years or so to our research as well as others research so if you're interested in learning。

More about flash memory， this is still a very good to reference on the topic。

 even though technology has evolved a little bit over time。

Okay so why am I telling you this story because it turns out if you actually are looking at different types of memory with different infrastructures you can ask different questions。

 so in flash memory for example we saw in these works that there's some disturbance errors there's some retentioner data retention flash memory is also charge based memory and you lose charge from the floating gates at the time but there's also red disturbistance so whenever you access one cell in flash memory you disturb some other cells and we ask this question basically can you have that sort of problem in theM as well。

And we were quite sure that you could have that sort of problem。

 but we weren't sure whether you could actually have that sort of problem in normal operating modes in the。

 so we use our infrastructure to look at at what operational conditions you actually would get this sort of redisturbance flipping bits。

Okay， so you've seen this picture before basically the idea of row hammer is or redisturbance is in DM。

 you activate one row， which brings the data into the sensorifier， which is not shown here and then。

And then you can read the database after you activate the so you apply high voltage to that word line and then you actually close that robe or precharge the bank which applies low voltage to the word line and this is a very valid pair as long as you obey the timing parameters and if you keep doing that repeatedly which a valid operation activate precharge activate precharge high voltage low voltage low voltage and if you do it enough times before the cells get refreshed it turns out physically adjacent cells some physically adjacent cells that are vulnerable lose their charge complete basically they little by little lose their charge and eventually their charge gets depleted so you can read them correct。

Hopefully that makes sense， sir。So we call this the hammerd we called the victim Ro。

 we've actually seen this last week before also， so I' go through this relatively quickly and we showed in the first paper that I mentioned earlier that more than 80% of the chips that we tested from three major DM manufacturers。

 they' are only three major DM manufacturers in the world that occupy more than 96% of the market today I think maybe even more today actually with HPM etc。

 because HPM is difficult to produce。I should also say that there's a very Western centric view of the world because we don't know enough about the Dm manufacturers and the let's say Eastern world that Western world tries to shun away which is a very dangerous thing to do in the world yeah but again basically these are three major manufacturers and more than 80% of the chips are vulnerable。

And this is we showed that this is a scaling problem， we basically tested a lot of modules。

 I think 129， and we showed that this problem didn't appear before 2010 when the cells were large。

 we couldn't basically induce a bit flips， at least with the patterns that we tried。

And we induced pit flips in chips that were manufactured in 2010 and all of the chips that were manufactured between 2012 and 2013 were wellnut。

It's interesting and we said basically because the cells are chips are becoming denser。

 cells are becoming smaller， you get more vulnerable and this is going to become chips are going to become more and more vulnerable that's why we predict basically going into the future why is this happening I've already told a lot of the space when you access one cell you disturb another cell do it electrically interference between the cells and the wire is used for accessing cells for there are multiple device level mechanisms that I will not go into there are a lot of device level papers in fact we have a paper at VTSA will flash at you that have appeared last month that talks about some of the device level studies etc if you're interested you can go and look at that for example。

 but when you activate apply high voltage to a row an adjacent role get slightly activate this well this is one mechanism and vulnerable cells in that slightly activate will lose a bit of charge and if row hammer happens enough times charge in such cells get traineded that's one way of thinking about it but there are multiple other things that happen at the device level。

The fascinating thing is there's some device level problem over here or circuit level problem。

 whatever you want to call it's really actually both circuit and device level problem and now your algorithm and problem and user gets affected。

😊，So it has immediate implications because you can induce these bitfs under normal operating conditions。

In a real view answer。Using a user level program。Okay， that should not be happening clearly right。

You should not be this should not be these bit should not be happening under normal operating conditions essentially if you extend the operating condition and if you operate out of let's say specification yes you may get them but we showed that the key a major contribution of this work is to show that you can get these under normal operating conditions so we show that using our FPG infrastructure and then we basically said well can we do this with a user program on a real CPU based system and that's what we did essentially using an XcD6 based system using real D modules using real user load programs which we open source which Google later built on I'm going to talk about Google's work also soon。

With only these six instructions， you can select addresses X and Y。

 such that they map to the same sub， and basically what this program does is it makes sure that X and Y are not cached。

And X and Y are not in the robot referralls as。And you basically keep doing this。

 let me see if I can do this with it's easier here。

Okay so you do hammering and if the chip is vulnerable you get bit flipps we also said in the paper that if you actually have X and y if you sandwich which one row between them you get a lot more bitlipps this is called double sided hammer and we characterized that a little bit in the paper。

 but we should have characterized it more proudly。They have double side hammer is much more effective essentially a lot of our characterization in the papers about single sided hammering which is a little bit less effective but with more patterns like doubleside hammer you get disturbance from both ropes that you're activating and there's one row sandwiched okay so this is actually a result from running this program on real systems at the time and essentially you get significant number of errors and there are reasons why AMD has lower errors etc but essentially you get errors that's the point and there's nothing special about Intel and AMD as long as you're building good enough memory controller you get these errors and everybody gets these errors IBM apple etc whatever we didn't go and basically kind of make a big deal of it saying that oh you get apples these days I think people write security papers saying that oh we always get especially with Apple we get these errors and Apple we could have them that also anyway okay go ahead so of course like this issue persist in DM but then the memory。

very good question basically memory controllers are built by the processoror manufacturers。

It was true 10 years ago， it was true right now。And essentially， it's on the pro。

So Intel builds it AMD builds it and video builds it so every processor manufacturer builds a memory controller we're going to get back to that later on actually this is a problem actually in the in the IMW paper next week i'm going to present saying that this is a problem we need to be more careful about how we distribute tasks between the memory control and。

😊，Does that make sense okay thats a very good question that was not necessarily the case like in 1990s when there was a separate memory controller chip there used to be a CPU chip memory chip and that memory controller chip but because of large scale integration cable is Moore's law memory controller got sucked into the CPU chip it didn't get sucked into the memory chip because memory chip is not good at logic。

😊，If you remember less than， yeah。Okay。But Intel used to build those memory controller chips also。

 but there were also other companies building those memory controller chips at the time。

Now Intel could be purchasing IP from some other company， but in the end。

 they're the ones who're really building the memory controllers。Okay。

Okay so this is the paper and clearly if you do this with a user level program we said that you could do a lot of bad things with this user level program with some effort security engineering you could actually take over a system we said for example we could get hijack control of a system you could actually crash the system so those bigs are obvious to us to actually to make bad things and we argued that this should be prevented I'm going talk about solutions later but okay the first people who actually picked up on our work as right after it was published was memory testing software people the mem test Passmark software for example it's actually from their website directly they cite our paper saying that according to the research basically there's a problem we introduced so why am I only getting errors during test 13 hammer tests they introduced the hammer test which is somewhat similar to what we wrote。

But it's not very comprehensive actually， even then they received a whole lot of emails and inquiries from people saying that why am I getting errors over here so they had to add this FAQ and they had to say that the errors detected doing test 13 are almost most certainly real errors。

 maybe there are real errors。😊，There's it， and you can read about this， which is interesting。

So testing is important as you can see okay so we also said in the paper that this is not good and we should basically this is I'm going to read the first sentence over here memory isolations the property of a reliable and secure computing system and access to one memory address should not have unintended side effects on data stored in other addresses and we said that somebody can write a security exploit and later Google folks Google projects to your folks read our paper they basically did essentially what we kind of said they use these bit flips to gain kernel privilege using a user level program they actually had two security attacks I'm going to talk about that but there has been a lot of work to use Ro hammer to take over a system which is what the Google folks did read data they do not have access to I'm going to probably flash one of the papers it's called rable for example。

 break out of virtual machine sandboxes Google folks also did that actually which is a less interesting attack but then taking over system but if you can do it this is also good Cor important data for example you could corrupt some important weights or parameters and machine learning。

Get very bad accuracy still secret data like cryptographic keys machine learning all parameters so you can actually in the end cause a lot of trouble right in fact there's actually a lot of theoretical papers in the 1990s that are written on cryptography and they basically say if someone can target bit flips and induce bit flips on cryptographic data like keys etc ceter then all of these security protocols are broken。

😊，These are theoretical and later a lot of those theory people went into practice。

 let's say with Ro hammer Ro hammer enabled them to actually really show that these security protocols are broke。

😊，Okay that's very interesting I think today we're actually talking about post quantumum cryptography et with Rohammer I'm not sure how that will turn out okay anyway so this is a copy and paste from the Google's blog post Mark Seaborn and Thomas Dllian they basically said they learned about the problem from our paper they replicated the problem on a selection of laptops and found a subset of them exhibited the problem and they basically built two working privilege eation exploits one of them takes over the Google native lines which is essentially going taking over the virtual machine sandbox the other is more interesting essentially it uses Rohammer and use bitlips to gain kernel privileges on Linux。

😊，G run is an unprileged user level process。And basically the idea is you had the virtual memory lectures two lectures go。

 so now hopefully you understand this very well， but essentially the process。

 the user level process is written to induce speech flips and page table entries。😊。

And it flips the right bits in the page table entries such that it can get right access to its own page table。

And if a user level process gets right access to its own page table then it can do whatever it wants right because you know the layout so that's the idea over here I'll go through this attack a little bit but if you're interested to have a black hat talk as well and Thomas Doian actually he was not working about on these topics he actually has some talks online and he always says that Ro hammermer is an eye opener for him essentially showing how bad the robust pros and hardware work okay let me go through this throughout really quickly I already gave you the key idea basically clearly page table and piece this is slides from Google it's Mark Seaborn slides。

😊，Essentially， a pagetable entry is controlled access and if a book fliplip happens in a physical page number。

 you can get access to a different physical page。😊。

And the idea is to do that over here and to be able to do that they developed an attack called Patable spray such that they could maximize the probability of the attack so basically all of these row hammer attacks are prost you don't have any guarantees that。

You will get access， but if you're lucky， hopefully you'll get access and if you try enough times you will get access。

So basically these are the exceed6 64 page table and there a version of this you have seen two lectures go。

 so if you actually try to flip the readrites permission bit from let's say read to write，😊，Uh。

 you get very little chance right to flip that bit because it only one bit out of 64 bits。

But if you try to flip the physical page number， it's 20 bits on a 4 yearabyte system。

 you get a lot higher chance。So that's the idea over here the question is how do you flip that basically you have the virtual address space and you have the physical memory and what they do is they map a file with rewrite permissions。

 this is the files' virtual address space and this is the file's physical mapping。😊。

And this is basically how you map the file if it's into physical memory。

 there are some page table entries， the red ones are page table entries。

And basically you keep doing it repeatedly if you keep mapping the same file multiple times and then virtual add space here。

 but then physically you point to the same place as you can see。

 you have a lot of page table entriess over here。And then you can feel the physical memory with page table entries this way。

😊，So each of them points to pages in the same physical file mapping as discussed。

 there's only one physical file mapping over here now if a bit in the right place in the PT flips。

 the corresponding virtual lattice points to a wrong physical page with readrite axis。

Because you open the file with right permission。😡，And if you kind of flip one of the page table entries that are over here。

 now you can get access to some other page。😡，Because you change the pointer right and you have right access。

That's the beauty of this attack right page table screen chances are this wrong page contains a page table itself an attacker now can read write page tables that's the idea。

😊，And they can do anything based。Okay， does that sound good？

I will not go through their exploit strategy， but basically I explained everything so the key over here is to find out that you actually have a right spot in the PT you actually cause bit flips in the right spot so basically there's some process that happens earlier like search for locations prone to flipping like some sort of profiling of the memory like we read did actually in a lot of our works。

😊，Okay， which is very interesting， there's a lot of work that actually improved on this later on and later people start drawing pictures that look like this that's the Rohammer and one of the famous hackers on the internet saidRohammer is like rakings in apartment by repeatedly slamming a neighbor's door until the vibrations opened the door you were after。

😊。

![](img/4281349ccf53b3eafe6978d710441345_9.png)

Theses like a real a kind ofs it's nice actually， it's a nice description。

Okay I will not go through all of the security applications but there's a lot of interesting work as I said this is just a selection of the work these are folks from Tgras that basically showed that using Ro hammer through JavaScript they could gain understrict access to systems of website visitors remotely this is work from Kaazza for example here which shows that they could gain access to a mobile phone deterministically by exploiting the regular memory allocation patterns in Android operating system they could fool the operating system to allocate a page table and take to a location that they profile to be rawham vulnerable in a deterministic way because the memory allocator in the operating system follows in deteristic policy and they could actually take over your system they had an app for this also if you're interested you can maybe you can download it an Android system I don't know。



![](img/4281349ccf53b3eafe6978d710441345_11.png)

![](img/4281349ccf53b3eafe6978d710441345_12.png)

You can actually excite these attacks with GPUs because GPUs actually can generate a lot of requests。

 as you have seen with the GPU lecture， you could do these attacks through remote direct memory access engines。

On a different server also so you could do it over the network essentially and this is another paper that talks about how to do it over the network。

This is the paper that shows that even if you cannot take over another system。

 you could actually read memory that you don't have privileges for reading。

 it could be some private memory and the idea is you make confidentiality basically as opposed to let's say breaking integrity and the idea basically you exploit the data dependence of Roham bitlips over here which we will get to because Roham bitlips turn out to be data dependence so you can actually infer what data you have in an occasion that you don't have access to by flipping bits around it。

Okay， and then。These folks show that along with other folks。

 you could induce these bit flips and neural networks in a let's say targeted manner。

 and that could lead to very low accuracy in the inference， neural network inferenceprints。

There is more work in this area that I don't have time so these folks show that you could do it on FPGs and you could actually recover private keys that should not be recoverable again。

 but it's cryptography for example it's one example and Google has some work on this actually Google and Microsoft both all of the attacks as well which is very interesting I will talk about this later on this is another attack by Google more recent attack from 2021 we'll talk about that because this also shows that you could actually do row hammer across multiple rows we'll get to that。

😊，And there may be other attacks like this right if your computer is not working。

 maybe this is a solution right or maybe this' is another attack。😊。

Again interesting pictures Okay we have a lot of papers on this i'm not going to cover all of them。

 but if you're interested this actually a paper that was invited to the topics in hardware and better security in 2019。

😊，And even at that time we thought this problem will be solved。

 but we were working on actually showing that is not solved yet。

 but still it covers a lot of work more recently we've written papers with Atbar and Gi that talk about that and our Isca paper even though it was rejected the first time it was invited to the 50 years of IsA retrospective if you're interested you can read it actually the refresh papers the radarer and experimental refresh papers were also invited to 50 years of IsA so people thought that they were actually important to be published at a major let's say selection of works from I。

Okay， so there's also works from Google showing that Samsung proposed a bad solution this is actually a very interesting area。

 these are public works。😊，This set the DMs workshop which is going to happen again in June so again you can read this Samsung had this let let's say very hard to read paper and then Google said that it's not a good idea and more works also show that the DDR5 is also vulnerable this actually a difficult problem right now this is from Ky's group also they basically show that one out of 10 tested devices DDR5 devices vulnerable。

😊，I believe there needs to be more work to show that the DDR5 is also vulnerable。

 I believe they're vulnerable at the circuit level at device level without mitigations they're definitely vulnerable。

 no question about that if you turn off the mitigations the question is can you actually flip bits and let's say a takeover a system etc with all mitigations in place。

That's actually a good problem to show， especially in the security community。

Okay and this is Gi ice thesis if you're interested in a lot of these Gi ice thesis is one of the latest thesis on the topic he defended last year and he will receive the major dissertation award from the DSN community dependable systems and networks community for this thesis and also from the computer architecture community you'll get an honorable mentioned so his thesis recognized by two at least two major communities but two morals all right testing and。

Hardware oriented security and trust so may be one of the few people with four communities recognizing its seasons in a very。

 very major way， it's very difficult to do that I think。😊，Okay。

 so this is that's another interesting part of these studies I think it's really across disciplines with it been computer science right it involves security clearly it involves safety。

 it involves testing it involves computer architecture。

 even though computer architects initially told us that。

Computer architecture has nothing to do with this， but now the area they're writing papers about it。

 it involves dependability， robustness， so it really spans across the stack。😊，Devices also。

 although we don't do work in devices， that's not our expertise。

 but there are other people who work in device level and they actually publish very。

 very interesting papers at the device level。Okay， so any questions now i'm going to go into a bit more detail。

 Yes， in the beginning you mentioned a very specific set of assembly commands in order to introduce。

Roowham， is this more diverse because otherwise you could just block this yes。

Yeah that's a very good comment basically for example C flash instruction is privileged right now。

 so you cannot use C flash， but there are other ways of actually doing this and other works have' shown that。

You could come up with very different ways of inducing these patterns so you need to block a really large fraction of things and people's creativity always overcomes what you block in general。

 but that's not the only way of doing it in fact i'll probably flash another paper where we did we did with Microsoft that shows many。

 many different ways many many different types of instructions to do this。😊。

But security folks are actually very good at coming up with new waste。Very good， so you can actually。

 for example， flush a cache line without requiring a flush instruction by building eviction sets。

 you can actually evict any data you want from a cache as long as you can build a good understanding of the cache。

 which many people can today actually。😊，Okay， so we did a lot of work to understand Rohammer in this paper。

 we had a lot of characterization and results。Thanks to our infrastructure that enabled us to discover it as well as understand。

 of course we tested 129 modules， that's a lot of modules。

These are old modules at the time i'm going to give you a quick conclusions and then we're going to look at some new works also and I'm going to tell you a story also because there's an interesting story I think of how this was handled in industry and maybe we'll talk about the academic story as well so basically one of the questions is what is the adjacency of the aggressor and victim roles from the perspective of the memory controller and we found out that most of them are adjacent from the perspective of the memory controller the distance between the row addresses one minus one as you see but there are some cases where they are not adjacent and we basically said that this is because。

😊，There's some mapping that goes that happens after the memory controller inside the DM chip row addresses are rempped to other addresses for various reasons one of them is actually because you may get a fault you may get a hard fault in one of the rows and you remap the row somewhere else right so basically from the memory controller's perspective。

There are some non-adjacent drove addresses that lead to thes。

 but physically we believe that the adjacency， physical adjacency is really important in the end。

 and they have some results supporting that， not in this the question is basically the reason this is interesting is can the memory controllers solve this problem？

If the memory controller doesn't know exactly which rows are going to be flipped。

How does it prevent this problem it could take a very let's say conservative approach and refresh the entire bank for example。

 but that's expensive Okay， it's good to keep this in mind so it's hard to solve this problem without knowing the addresses that are going to be affected when you have。

Okay， this is access interval basically the idea here is how。

This is essentially two axises to the same rope or different ropes， essentially TRC。

 this is not allowed below 55 or below 52。5 nanoiseconds was not allowed at the time and if you actually reduce the access rate to DM meaning you slow down the excesses I said you don't access rows as frequently。

 you can reduce the bitlipse as you can see right。And you can make this a parameter and say， oh。

 I'm not going to access DM or at least the same row。诶。

More than more often than n nanoseconds if you want to get rid of bit flips you need to make that value very large that n needs to be 500 nanoseconds according to our testing these are real results showing the errors you get in the worst chips that we've tested from three major manufacturers and this is clearly a bad idea in the end if you have less frequent accesss you get fewer errors but this is bad for performance also right。

Although gear eye the solution that does this in a very selective way we're going to talk about that is called block hammer for example。

 this is a refreshing interval， another lever you can play with is refreshing interval and this is the easiest lever to play with that's why everybody played with it after our paper basically the idea is if you can reduce the refreshing interval meaning increase the refresh rate。

😊，The likelihood that you're going to be able to。Perform enough activations to induce a bit flip reduces。

😡，And this is these results from real chips support that。Essentially。As refresh rate increases。

 you get fewer errors， but if you want to get rid of every single error that we saw in our test patterns。

 you need to increase the refresh rate to be 7x。That's a lot。

Refresh is bad to begin with as we discussed earlier。

 we were trying to eliminate refreshes the reason we built our infrastructure was to eliminate refreshes as much as possible right because refreshes are bad for energy bad for performance。

 bad for quality of service， bad for predictability and if you want to increase now if we need to increase refreshes to actually solve the own hammer problem that's a bad idea and our access patterns were not the worst so the number if you want to get rid of every single bit battery you need to increase even more。

But basically， this is one way of solving the all hammer， increasing the refresh rate， okay？😊，Okay。

 so data pattern， as I mentioned， some data patterns lead to many more errors because it turns out there's more coupling that happens across the capacitors and the word liness because of the data stored in the capacitors。

This is very interesting and there's more work in this area and there are actually security works that take advantage of these data patterns to induce more errors and make the attacks more successful if you use let's say not so redistbance vulnerable patterns you may not get errors in your chip so you need to be careful as a security engineer also or attacker in the paper we showed other stuff one of the important ones errors are repeatable。

 meaning if you get an error if you are able to induce a ro hammer or bit flip。

In a row or in a cell you will be able to induce it again again again again again and this makes us secure vulnerable because now someone can figure out which bits are vulnerable and they can actually attack those bits we showed that basically a simple air quaing codes don't solve the problem essentially get many errors for cache line this is very interesting because industry was arguing that air collecting codes solve the problem I remember very well I gave a presentation and ISC in 2015 was in Frankfurt I talked about row hammer memorycentric computing etc ce and then a major memory manufacturer as vice president gave the next talk and he had the opportunity to actually respond to my talk and he basically said we have a solution to raw hammer。

And he said ECC。And everybody knows that it's not a good solution to Roham today， because they also。

 it's not just our papers， but it's also security papers that show that even when you have ECC。

 you can actually take over a system。😊，This is a。哎呀。

Okay and we talk about doubleside row hammer essentially a lot of these are studied all of these are studied in this paper but later paper is actually studied more row hammer is getting much worse we're going to cover that after we cover some more stories this is the work that I mentioned with with Microsoft that showed like different access pattern different instructions and basically we try to answer the question can we guarantee that a chip is not vulnerable to raw hammer and this is a very difficult testing problem and I think it's very difficult to guarantee that it's still a good question task ask if you can find methods to actually guarantee with your testing methods that a chip is vulnerable or not vulnerable to raw hammer it's good but。

😊，As you're going to see it's going to get much much worse。

 so GI and autobar actually had a lot of studies that show that the vulnerability is much more nuanced than it is because it is varies spatially as well temporal。

😊，Right yet。Okay， we may get into that so GiI was a first author of this work that showed that Ro hammers actually behaves interestingly with different types of parameters I'm going to talk about that with another of GiI's works on voltage。

😊，This is one of Tbe's work on ATM chips， AM chips are also vulnerable basically any DM chip is vulnerable because fundamentally the DM organization is the same sell the same。

HBM is more interesting today clearly because it's the machine learning infrastructure right today and whenever you write papers like this。

 people become even more interested。Although all of these memories are everywhere。Okay。

 this is another gearIs work which maybe talk about and this is the more recent work that we actually briefly talked about last time。

 variable redistance that makes a lot of these solutions much more difficult to let's say implement。

😊，🎼Okay so about those solutions。🎼待て。Maybe we should take a 10 minute break。Let's take a  ten break。

I don't think we're going to finish everything， so I'll take a 10 minute break today。

 but we'll be back and we'll talk about solutions。嗯。嗯。嗯。Oh。嗯。嗯。Yeah。你个啲方都瞓到。

If you take my notes go just it thes as。Can I ask a question about the Google attack on the kernels or like the page table rather？

So I was wondering。I'm not entirely sure because I've visited the lecture like two years ago but the page table in physical memory it's not it's all in the same like memory reaching right it's tell anywhere it depends yes because that also gets mapped through virtual memory so if you were to map the entire page table to like the same purchase address space。

 it would probably also not be too smart from a security yes yes but otherwise you could technically protect like high highly sensitive areas by mapping empty pages next that solution has been proposed except it's very intensive in terms of capacity requires people have proposed yes if the page table is everywhere of course。

 to get very resource yes there also other solutions that people have proposed like encrypting the page tables。

 those are more。PossiblyDoable but then there's later when associated with those and print over it technically still doesn't solve like the issue of Ro hammer potentially that's true damaging the kernel exactly you can damage。

 but maybe you cannot take over yes， yeah thank you very much。😊，这个作来。系喺都明 that咁。我履。ます。😊。

It's not the weekcast but' like for sure。I'd like to meet for sure that's very tight。

I on my mind for sure and maybe a'll do a lot more then I I know so。😊，Well。

I can actually also ask an administrative question。

About administrative about La four okay so right now we're still in lap3 and I think the ending is next week So I've heard like the two lectures ago there was a short talk about that we were going to do a lab four I assume the La four then starts in last week of the semester I think so。

 but Muhammamed is probably the better personal therere the better people to answer those questions so yeah recall we were talking about recall were talking about four yeah planning week of the semester so were have。

😊，So yeah， but me we may make it probably kind of also。 so we also it might be also。现在可给这个还品。嗯，不。

是 sketchで所应该是。submitYeah， Larry one month or so you can whole so we you guys I think that important kind of completes course so that's why we want to。

Do you make easy for to be just。工系放过。And online meetings know。

 some courses have like open hours you can just comment questions relevant questions。

For exam actually you're going also have discussion or sessions that because we have session but we can actually use。

 but can so the that there are some we like to make sure that are not guys more than weeks because then theyre not be any other we no because the exam is。

To mean actually we can also real real we there are also。

 but there are some I think for the we areing。Friday。さす。如果必是自。です。你我紧。そそ。やこもなの。

And it sucks that I'll it almost out find。い。这明有可。男性でのじゃ男性性まあいつい。你这个是。たんです本てなよかったごまめたのさ。

Maybe price been put up in that。やってまい先生。Is everything good Yes， Okay， okay， let's get started。

So let's see。I have about 300 slides I'm not sure covered sorry there's a lot of interesting stuff in this。

 but you get the gist of it you don't need to understand the details of every single paper as you can see。

 but every single paper builds up very， very interesting things I think。😊。

So let's talk about d hammer solutions， this is where we argued that you need to actually provide two types of solutions when is immediate because you find this vulnerability。

 all of the DM chips are vulnerable and all memory in the world is main memory in the world is DM right？

😊，Maybe not and over time they'll become more vulnerable。

 clear there are limited possibilities because we believe that the memory controllers were not designed to handle these well。

😊，Increasing the refresh rate is one possibility for example we talked about that in our paper but we'd say that its it's a bad idea。

 so in the future we should probably look at better solutions to protect future D tips we should come up with better solutions like programmable memory controllers for example so in our Ica paper we talked about seven solutions in total and our best solution at the time was probabilistic adjacent ro activation I'm going to talk about that and it was employed in the field after that but I don't think it's a good solution at this point at least the way we know how the vulnerability has evolved one of the solutions was actually adding activationctuation counters per row we dismissed to saying that' is too expensive that's what's happening in industry today。

So it's the kind of the， let's say。😊，I don't want call the dumbest solution that you could come up with。

 but it's one of the first solutions that you would come up with if you're given a problem like this。

 Okay， let me add an activation counter per row。 There are a lot of issues， actually。

 even with that solution， there are a lot of issues as we will discuss。

 but I don't think it's the best solution， but at least that says a solution that industry is following as we discussed last time。

 but we're going discuss a little bit more。 Now let me talk about some solution approaches。

 So you could build better D chips or air collect codes。 I don't think these are good ideas。

 Airqu codes are very good at。Preventing bit flips that are random。

 but they're extremely expensive when you want to prevent bit flips that are not random So in this case。

 you know exactly the error mechanism it's very expensive to protect everything with air correcting codes。

 especially if you get a lot of bit flips in a code word。

Increasing the refresh rate we discussed it again not good for various reasons。

 Phy isolation somebody discussed this earlier during the break actually isolate agor rows and victim rows secure the critical data from other data。

 it becomes expensive basically and people have shown that this is not easy to do so it's vulnerable actually So two solutions that are actually very me see if I have another slide I don't have another slide but there's actually another solution which is remapping whenever you have some vulnerable you remap the role somewhere else it is also very expensive it's not in slides for some reason but will' add them later on that's also very expensive but people have explored that I think the two very let's say promising solutions are reactactive to refresh。

 meaning figure out whether an aggressor row is that being activated or a victim row is being let's say hammered for some reason next to it and refresh the victim rows somehow that's one approach we're going talk about that just the victim road not the entire memory increasing the refresh rate to refresh memory there's also a proactive。

😊，Language is basically figure out which rows are hammered and reduce the access rate to those basically slow them down。

 don't hammer them essentially。I think these solutions are actually solutions and maybe there's a combination of multiple solutions including ECC a small level of ECC that could be useful now the difficulty is people are still developing solutions the difficulty is this complex cost power performance complexity tradeoff space in the end all of these solutions and there are a lot of solutions that are proposed and I think there needs to be more creative solution going into the future also there's no perfect single perfect solutions in the end。

😊，And also security can be part of this also， so maybe you allow some bit flips， right？

As long as they're not exploitable I don't like that idea it's not a good idea。

 but some solutions actually are not secure enough essentially whenever you come up with the solution it's important to prove the security or the solution okay what did industry do basically industry did what they could do meaning they increase the memory refresh rates this is Apple their security patch I like Apple because they actually talk about ciar paper as you can see and they basically said listen this is a bad issue a mallish application can induce memory corruption test privileges this issue was mitigate by increasing memory refreshments they didn't say by how much like 2 x or so2 x is not good enough to get rid of all of its。

😊，And many other companies released similar patches and this is the easiest thing that you can do in your memory controller right memory controllers have enough programmability to increase the memory refresh rates across the board and the entire memory but this is also a bad idea for various reasons as we discussed right for performance energy so our solution required changes to the memory controller the idea is very simple。

😊，🎼Basically， memory control after closing a row activates or refreshes selectively。

 the neighbors of a row with very low probability。That's the idea and if you do this probabilically with a large enough but low probability are you can be quite secure it's a probabilistic mechanism so it's reliability guarantee is probabilistic in memory actually you would like to get a guarantee that's around 10 to the minus15 or so at least in flash memory as you may see later on so we get close to it with p equals 0。

05005 if you're actually more paranoid you can increase the probability right you could configure this solution。

Okay， so that's the item and it turns out this is low power low performance overhead。

 the slowdown is very low across the workload we tested for the row hammer thresholds that we have seen at the time。

 so the row hammer threshold that we have seen at the time the number of activations you needed to use a bit was on the order of 100。

000 or so today where at a very different regime so this solution doesn't scale very well as we but there is a benefit to the solution other if it is it's basically there is no cost you just need any stateless。

😊，You don't need to keep track of anything you just need to flip a coin and you can do that actually with the random number generation that you do in D as we have discussed and it could be zero cost。

 almost almost zero cost， low complexity， so it's very cheap compared to the perole activation counter solution that's being implemented today。

😊，So I like this idea a lot still and we showed that basically you could do this in a DM chip。

 you could do this in a memory controller and if you do an DM chip you need to have enough slack and timing and refresh parameters and with our infrastructure we showed it with other works that there's a lot of slack in the timing parameters for example。

 there refresh latency some of it is just wasted it's just specified but actually it doesn't need to be that long so you could actually sneak in row hammer preventive refreshes in that refresh latency that's specified by the DM standard if you want to implement the memory controller there's some danger here in the sense that the memory controller analysis needs to know which rows are physically adjacent so it goes back that picture that I showed you memory controller may not know which rows are physically adjacent so we said that there needs to be this is one of the reasons why you say you need to have system memory codesign the memory controller needs to be provided more information about the ERM chips essentially and configured accordingly。



![](img/4281349ccf53b3eafe6978d710441345_14.png)

And this was implemented by Intel in their memory controllers so you could actually choose。

 this is a snapshot of bios from one of the Intel machines。

 you could actually choose your Ro hammer solution。

 either you pick hardware Ro hammer protection or2 X refresh。😊，I don't know why it's so limited。

 but if you go to hardware Ro hammer protection， there' is an activation probability that you choose and you can choose your activation probability。

😊，Every two activations probably is very expensive you do refresh every two activations not so good right every 512 which is similar to what we suggested actually is maybe okay okay so that's the paper there are more solutions that I'm not going to talk about over here but basically our takeaway was just like we argued even earlier than the Ro hammer paper you need intelligence choice for solving these issues。

😊。

![](img/4281349ccf53b3eafe6978d710441345_16.png)

And we were doing similar work with our flash infrastructure。

 if you look at flash memory you have actually intelligent controllers you will see flash memory next week a little bit and you will see how difficult it is to really make it work there are a lot of issues and you have to have an intelligent memory controller to actually set the voltages right so that you can read the data correctly in flash memory and again if you want to foreshadow things you can read some papers and take a look at it。

😊，Okay， I'm going to give you a little bit more story after this。

 but basically the reason I think it's really important to there are two major directions in my opinion to。

Solve this sort of issues and we're going to generalize this the bit flips later on。

 essentially we don't know enough。😡，To be able to prevent these issues we need to know elements bit right so if you want to prevent。

 for example， if you want to configure the probability， if you want to configure the refresh rate。

 if you want to even add ECC how much Ecc are you going to add。

 you need to know under what conditions these bit flipps are triggered right？😊，And we tested a lot。

 but there are other things that we don't know enough yet， like aging， for example。

 if you ageD intern chips five years。Under different conditions what happens to allhamut's restaurants right i'm actually quite interested in this if it's in space what happens right if are trying to go to space do you go there with Dm good luck。

😊，Maybe maybe you go there with no memory environmental conditions it looked at some of these basically there are a lot of things that happen that affect these bitflips like memory access patterns。

 memory control and system design decisions etc and then I think theres a solving parts this is all a lot of characterization basically that's why infrastructure building for characterization understanding is really important modeling also but modeling is also difficult at the device level some of these things are very difficult to model So is important we need actually more flexible than efficient solutions like how do we make it configurable programable patchable so that if we discover that we didn't do the right thing because somehow some environmental conditions have condition under which the system is operating leads the worst row hammer you just need to configure things to be better right or maybe you discover some other issue as we will discuss later on and to patch things patch the solutions etc。

😊，I think qua architecting system and memory is important still to avoid performance and denial service problems because some of the solutions。

Can cause denial denial of service。For example， if one process is attacking memory and you prevent raw hammer assuming even with para solution。

 probil to getvaation， but then you deny service to some other process right because you're slowing down the memory access rate because you keep refreshing memory right？

So essentially， even if you're perfectly secure， you may start causing denial of service or performance degradation and this is a problem with peer solution a decent activation solution。

 no。Prov activation counter solution that's being employed in industry today。Okay。

 so what happened essentially？It's an interesting story I'll go through some of this relatively quickly。

 but Intel implemented para， which was a step in the right direction， in my opinion。

 they wanted to make the memory controller more intelligent etc。

 but at some point D manufacturer said we solved the problem。😊，DDR4。

 we don't have this problem anymore。And magically， everyone believed them。I don't know why。

 but everyone believed it， even Intel basically stopped their solution。😊。

They basically disabled their memory driller solution。Of course， as a researcher。

 you don't believe that sort of claim， especially with what we know it's very hard to believe claim how did you solve it？

😊，They basically said they added in the MTRR which we will talk about which is partly based on the principles of para etc I mean they cannot get a little vulnerability unless they move to another device type etc ce or some sort of substrate that's difficult so they had to have some sort of architectural solution internally and we will talk about that。

But we also at the same time basically we questioned it and we showed that that's not true that claim is false completely we also did a lot of circuit tool or testing work to show that this is actually a very difficult problem solve much more difficult than we actually demonstrated in our 2014 paper。

So we wrote two papers， one of them is this one revisiting Roham this is Jeremy's part of Jeremy's PhD thesis it was published in thisca 2020 and basically here this is the takeaway we tested a lot of chips this is more chips than we tested before different types of chips including LPDDR DDR for DDR3 and basically we show that newer DM sit are much more vulnerable to raw hammer you get more bit flips that happened earlier earlier meaning with fewer hammers there are new chips like LPDDR who was weak as cells fail after only 4800 hammers don't talk about 10000 we' were talking about 4800 double sided so double it so 9600 still pretty small compared to 100000。

And you get newer technologies leads to bitlips in more rows and farther away from the victim row。

 we basically said that there is this last rate use effect where you can actually get bitlips in farther away rows and later Google paper Health double actually showed that in more detail。

And basically most this is the characterization， we also added did some simulations studies is to check if this trend continues and the rawhe threshold keeps reducing。

 none of the mitigation mechanisms that are proposed is going to be effective。😊。

Meaning they goal going to be either not work or performance will be term so these are I will go through these around really quickly because I've given you the key results and there's a lot to cover。

 but these are the chips that we tested we built even more infrastructure for this actually and you can see a lot of chips are tested from a lot of generations I'll give you one result this result shows that as you go from older DDR for generations to newer DDR four generations regardless of the manufacturer that you have the hammer count at which you experience bit flips reduces the first bit flip reduces you can see that this curve is earlier and this is the lower hammer lower hammer count and also you get more bit fliplips at a given hammer count。

Basically， newer generations are much more vulnerable， as you can see。

Okay I already said this early and this is a simulation study where we studied a lot of the mechanisms that are proposed in literature including our own mechanism basically we showed that and this is actually data that's obtained this is hammer count on the X axis and going from left to right hammer counters reducing meaning chips are becoming more vulnerable to raw hammer and you can see that these are the tested data DDR3 EDR to new EDR for old DDR for new LPDR for old LPDR for new so we're marching towards this site。

😊，And you can see the performance impact of the solutions。

 increasing the refresh rate leads to a drop in performance by almost 80%， even with DDR3。

 as you can see， if you want to print all the bitfs， para， which we thought was a good solution。

 it becomes much worse at very low hammer counts， meaning if you get a bit flip。

 let's say after 100 hammers，100 activations， you lose 80% of your system performance with PE。

 that sounds terrible， right？And we're marching towards that， we'll see numbers closer to 100 soon。

 even lower actually。So this is it's a fascinating graph I think later works populate this part as you will see yes so para is determined no no that's a probabilistic solution that's exactly yes to flip once it's being hammered once right so less hammers is just more vulnerable but what is that produce no no you change basicallyly the idea is to prevent all the bits you configure para。

😊，To make sure you don't get any bit exactly， you increase the probability exactly exactly that's why performance decrease even the ideal mechanism actually decrease yeah。

😊，Okay， so there's a basically significant opportunity to come up with new Ro hammer solutions and after this a lot of people started even more row hammer solutions there were works。

 but more works happened。😊，So basically a key takeaway of memory is really a technology scaling problem and finding a solution to it is difficult and it will become more so and this is still true。

😊，Find기 good。Okay， so this is an example over here。

 this is either reported HC first or row hammer threshold high a number of hammers for the first bitf values。

 ideally you're infinite。And if it's one， that's terrible right with the one activation。

 you'll get a bit fluid。😊，So we're marching from left to right over here。

 this is HM also with older technology， that's part of whats work。

Okay so as I said we also questioned whether the claim of D manufacturers is true and together with Kave's group we published this work at ITP security and privacyva concurrenly with ICO paper that I mentioned earlier and the idea here was to as this question is or the solution is good it or can we bypass them and basically we were able to bypass that TR is essentially memory manufacturers added this target draw refresh which is a very vague mechanism that's added to the standard it's not a mechanism actually it's really a way of solving a problem they basically said you could send target refresh commands from the memory controller and this would refresh something is that a correct characterization maybe it's a little bit better than that but basically this is a way of actually solving the problem。

え。But they didn't disclose what they did in turn， so clear there needs to be a mechanism for。😡。

Detecting， for example， when to refresh something right it's clearly a refresh based solution。

 but what do you refresh and when do you refresh was not disclosed by the manufacturer。

They basically were doing security by obscurity and claiming that okay based on this we solve the problem so we basically hypothesize that internally there had to be a mechanism that keeps track of some of the rows and that needs to keep track of some sort of way of which rows are frequently activated either probabilistically or deterministically and then decide what rows to refresh fish and that's what we did basically I mean basically said maybe there's a table internally this happened of course with some testing of the DM with IPJB infrastructure if you didn't have an FPJB is infrastructure we wouldn't be able to come up with this attack or show this easily at all actually maybe at all so basically we said that if you hammer many rows not just two rows or one row if you hammer many rows。

Maybe you will。Overflow。The internal tables that are there to detect aggresss， for example。

 if the DM manufacturer puts a table over there to keep track of four frequently activated rows with some way of detecting frequent activations that's also a difficult problem by a frequent item count。

 but let's assume that they did it， if I actually hammer five rows very frequently。

 they will not be able to detect one of them。So I have overflowed that tape and that's essentially what we did。

To be able to do that we need to the reverse engineer the DM chips and the memory controllers again with our FPG these infrastructure and we actually provide an automatic tool that can effectively create many side row hammer attacks so these are on many side attacks so this is double sided only these red rows and then they could have three side of the as you can see the red ones are the hammer rows。

😊，You can see that this is foresightd red ones are the hammer rows again if the manufacturer is only keeping track of two rows then we could bypass of course there are some other considerations and these are from real chips again we were able to induce big flips for example。

 after we hammer five rows in this particular module after we hammer seven rows in this particular module nine rows in this particular module。

😊，And bit flips are not like deteristally increasing or decreasing because there's some internal mitigation that we didn't complete the reverse engineer later work we're going to complete the reverse engineer almost complete and this is a table from this paper that's showing that we were able to induce bit flips in all of the chips we tested but we were able to induce bit flips in enough chips that。

We thought this was important to publish and write because the claim was。

There is no bit fliplips right now there are bit flips except you need to work a little bit harder and in some case。

 for example， the best pattern that we found was 19 sitesd 19 rows being hammered。😊。

It's interesting okay this is very interesting and we were able to show that you could take over you you could launch different type of attacks on mobile phones。

 different mobile phones again if you try harder you can get all of them to be checkmarked meaning you could actually induce withs and all of them and we were able to replicate different attacks on different modules like page table attacks that we discussed R attack that we didn't discuss but it's essentially getting the encryption keys etc and you could do it relatively quickly in many cases right so these are real attacks on systems that are claimed to have completely row hammer free chips this is actually row hammer free is what manufacturers set。

Okay， so this is the conclusion of key results and he basically said that this is not exhaustive these results scratching the surface。

 there's a lot more room for uncovering more vulnerable chips essentially。😊，找个。

So basically the takeaway was Ro hammer is still an open problem。😊。

Despite the claims and security biosecurity is likely not a good solution， I still believe this。

 but we're still doing security biosecurity and current solutions because we don't know exactly how the internal solutions today work a little bit more we know。

 but still I know。😊，But the bar is a bit higher because it's harder to induce bit flips now because there's a lot more going on inside the the chips。

Okay， so these two works actually cause a lot of churn in Gek， which is the standards body in DM。

 a lot of people said okay。What's going on you said these chips were not vulnerable now they're vulnerable。

 but there are two studies that are showing fundamental issues so people got together and they wrote。

😊，Not so great white papers， they reference our papers。

 but I think some of the solutions are actually very。

 very weak if you want to look at it's interesting。

 but I don't think these are let's say solutions themselves these are more like。😊，Oh。

 how do we brainstorm about solving the problem type of papers？Will you agree， Greg？

Yeah but they do actually reference these words say it again guidelines yeah I'm not sure if there are good enough guidelines either okay but more recently as I said。

 there was a more let's say concerted effort but this took about three to four years as you can see to have a more let's say better framework for a solution around cor activation counterors which we talk about last time I'll go through that a little bit more but you got the basic idea and this was standardized in April 2024 and as far as we know all the arm chipps are going to implement some version of this but we don't know exactly how it will work。

😊，Okay， so we did more work on uncovering this target jewelry refresh almost completely I will not talk about this in detail this is actually fascinating you can uncover a whole lot of almost everything if you spend enough time you can figure out exactly how the solution works this is Haan's work part of his thesis。

And the ideas， I'll give you the basic idea， but I will not talk about the detailed results。

 the ideas very very interesting， I think。😊，What you can do is you can profile the retention time of rows。

And you know that this row is supposed to retain data for the small right。

 and then you can launch a row hammer attack。And。You figure out whether that row would retain that data if the row。

Did retain its data that means that somebody refreshed that data so you reduce your refresh rate you get rid of the refresh rate you get rid of refresh or do something that's enough but launch your ro hammer attack and the Ro hammer attack is supposed to take longer than the time the row is supposed to retain its data so the row is actually not supposed to retain the data that you wrote over there。

But internally， there's some mechanism that refresh through。

So if you can actually figure out that there there's an internal mechanism that refresh around and they're retained its data you can figure out that there's something going on internally you know the retention time they're always supposed to lose this data but they didn't lose this data so somebody must have refreshed it that's the idea then the question is who refresh it and how often did they refresh it you can actually figure that out with the methodology okay so we figured out a lot of things based on the based on this methodology and you can see for example some of the aor detection mechanisms are counter based some of them are sampling based so there's some probabilistic mechanisms that happen some of them are mixed。

😊，You can see some of them are doing per bank detection。

 some of them are not doing per bank detection etc cetera。

 some of them are refreshing four neighbors as opposed to two neighbors。

 so there's some which makes sense also because Ro hammer affects not just the immediate physical neighbor but also maybe a little bit farther physical neighbor as well。

In the end， what this work showed is that。You can bypass essentially all the modules that we tested and almost all of the roles in a DMM experience at least one row hammer to flip using our mechanism。

 and ECC is completely in effectff。So this is another work that shows that ECC is completely ineffective。

 you can opt to summon row hamrrh flips8 by data word clearly I mean ECC is effective if it's very strong right but very strong ECC is expensive。

😊，Okay， so there's more results here。How much time do we have any questions？Okay， 25 minutes。

 there's still time， you can still ask questions。So this is fascinating。

 but later we looked into more roll hammer characteristics it a paper that YaI was the first author on。

 we looked at temperature， however would that affects roll hammer。

 aggressor of active time and physical location of a cell。Again。

 I will not go into details over here， but it's fascinating to study temperature so there's no easy relationship between temperature and all hammer vulnerable TBs different cells behave differently and there's a bonded range of temperature where a cell happens to be more vulnerable to raw hammer I don't think we quite understand this yet do we get。

😊，n off yeah he doesn't understand fully okay there's maybe more needs to be done over here it's very different from retention time for example data retention time has an exponential relationship with temperature meaning retention time reduces exponentially with as temperature increases。

😊，Whereas Rohamer you don't have any such relationship okay basically this is this the second observation led to Rpress which we have discussed briefly。

 we will discuss a little bit more if you actually keep the aggressor of active a little bit longer。

 then the minimum interval specified inside the DM data sheets， you can induce more bitfis。😊。

That's the idea over here and if you actually row press later extended the study to be much wider longer time intervals and certain physical regions are molecule so why is this interesting basically it' interesting for developing better defenses。

Because if at some temperature level or at some physical region or at some active time。

 you're much more vulnerable you need to change your mechanism right to take that into account。

 otherwise your defenses may not work。It is also good for an attacker perspective because if an attacker knows more information up like this。

 they could do a better attack so it's always if you know more information you're a better attacker as well a better defend。

😊，Okay， this is one example over here if if you keep the objective active a little bit longer。

 you reduce the hammer count to induce a bit flip by 36% and if your configuration of the defense assume some hammer count。

That's not taking into account the 36% the an attacker can do sp foots basically。

Okay there's more over here， for example， if theres this paper shows that more than 90% or around 90% of the cells are much less vulnerable through a hammer and a small fraction of cells are much more vulnerable so why not design protection mechanisms that take this into account you're more aggressive in the protection over here and you're less aggressive in the protection over here you can reduce the area overhead or the performance overhead of the defenses this way。

Okay， and Gary are giving a talk on this topic as you can see。😊。

Okay there's more row hammer analysis which I will not talk about i'm going skip this one these are very interesting studies to do because we need to fundamental we understand the problem like how does this change with voltage for example so gear I updated the infrastructure to be able to do that there's a summary interesting I will not talk about that we asked the question does this happen in HM chips I mean we knew that it happened in AM chips but to what extent etc so you can read more about that in these papers。

The I wrote papers on the spatial variation of Ro hammermer。

 there's a lot of interesting data over here。Which I'm not talking about。

But you can talk to him if you want so let me talk a little bit more about let me switch to the attacks and solution side and then we're going to probably get back to characterization so there are other other people also doing things I mean infrastructure wise not many people did study using real theM chips using FPGs more recently there are actually papers coming up because we open sourced our infrastructure and more people are actually doing work in this area but people are also working at the system level and developing more attacks Google actually built a simple infrastructure and they basically showed that。

😊，You could induce bit flips with an aggressor row that's far away from the victim rope。

 so this is classic robe hammer， you have an aggressor row。

 you keep activating that robe and you have a victim over here。In this health double attack。

 they called it， you activate aggressor of A many times。

And then you activate aggressor Rob a few times。And this caused big flips and victimcy。

So the aggressor or B activations can be I don' know 100， let's say。

Now there are two interesting issues over here one is if you didn't know this maybe configure your row hammer defenses such that you only take into account aggressor a activations so you set your row hammer defense to kick in after maybe 10。

000 activations right whereas the real number should be0 over here right because you activated this 10。

000 but then what about this one right like got activate only 100 okay there's another issue。

This one， if you keep activating this and your defense kicks in at some point。

 now your defense becomes an attack。Because what your defense would do is it would refresh these aggressors。

And that refreshes an activation， print？😊，Now， your defense becomes an attack on the victim。

whichch is very dangerous as you can see so that's why this is very interesting I think and you can read the paper for more detail they wrote a paper they first published a blog post but then wrote a paper at using security after some time。

😊，Okay， so Microsoft was also doing work in this area quite a bit and these folks actually I'm not go this in detail。

 but they basically showed that you could induce these bit fliplips using coherence mechanisms in existing CPUs if you want to know you can read the paper for more detail and basically even non- malicious code can actually induce these bitflips like in commodity workloads because of coherence mechanisms。

 it's actually interesting because there was work in 2012 or so at Intel that show that there are some workloads there are some benign workloads that induce bitflips in real systems real DM chip and they were actually also related to coherence。

Okay， so they kind of rediscovered something that was never documented let's say properly in my opinion so we spent a lot of time at Intel in 2012 so had a lot of interesting things Okay。

 so gear I don't love this block camera solution I'll go through this relatively quickly because this is an out of the box solution relatively a lot of solutions were basically let's detect the agory rows and refresh adjacent one the solution doesn't say that basically the solution tries to do something different and it also tries to remain compatible with command answer so if you want to actually detect。

😊，If you want to refresh adjacent roles， you cannot implement that solution in the memory controller perfect because memory controller doesn't know which rows are adjacent feature。

But memoryr knows which rows are being activated， so in this work the idea is to use area efficient balloon filters to detect which rows are being activated a lot and you selectively throttle accesses to rows that are activated too much dangerously。

 let's say。😊，Basically stop the accesses to that row until you think it's safe so there needs to be some security proof and yeahI provides that proof a and if you actually do this。

 you can also inform the system software about something that keeps activating rows electric and this is the advantage of this work is it's compatible with commodity DM chip you don't need to know the remapping or mapping of rows inside the DM there's no need for proprietary info or modifications to DM chip you could implement it perfectly in the memory controller the key is basically designing this to work well yes isn't that isn't that it's dangerous for example if you have like memory mapping output operations that tends to access a certain memory region along。

A lot yeah。Very high frequency device that communicates over a memory map region that's good that's a good question。

 but then you probably wouldn't be accessing the arm right because they're a memory map to some device and you would be going to that device yes。

I don't think there's any reason to access D in a case like that。

 it's just you use the memory mapping as a way of identifying the device。

But that's a very good question， it's good to think about these corner cases am I accessing memory in some way。

 I don't think in that case it's a problem。😊，Okay， so this。

This is an example of a more intelligent memory controller as you can see it's a little bit more intelligent。

 it's a little bit more expensive also and it's less scalable as GiI also showed but you can also download the source code。

 a of almost all of these works out there source code downloadable even our original row hammer work we uploaded that six line assembly program if you remember and Google built on that program to actually built their row hammer attack。

😊，Okay so essentially this is an example of intelligent memory controller so these are the solution approaches I will not go through in detail again there's more to be developed here and I'm going to flash a lot of pictures but' what's happening in industry as I said last time essentially SK Heinx published this paper finally in 2023 this is the first let's say paper written by DM manufacturer that's acknowledging the problem。

 row hammer that citing papers and also saying that we try to solve this problem introducing per row hammer tracking which is essentially similar to PRAC per row activation counters and it's essentially a D controller implemented inside the DM chip to hopefully avoid bitfs although if you read this this comprehensiveive scheme lease to reduce probability of failure due to raw hammer attacks by 93。

1%。😊，Meaning there's still 7% or 6。9% even with this cryptic thing there's not much information you cannot understand this what's exactly done。

 but at least the high level idea is every row is an activation counter and with some information this activation counter gets incremented at some point if this is greater than some threshold you refresh some adjacent rows。

😊，Exactly what is refreshed and when it's refreshed is not described。But。Step in the right direction。

 hopefully maybe not the best solution， but at least an intelligent control is happening over here the problem one of the issues is this this is done with the standard Dm interface so if you're not able to refresh the rows while the accesses are coming in。

😊，You may still get bitfs。Basically the memory controller is sending requests as well and the DM chip is internally doing something and if the number of refreshes that you need to do while the memory controller is sending requests is a lot。

 then you may not be able to do the right thing and refresh your abstract because at some point basically if there's too much that you need to refresh over here you need to tell the DM chip stop。

I need to do something in turn right and today there is a way to do that with DM it's called an alert signal。

 which is a very interesting signal it's not used a lot alert means basically I have some error。😊。

And in the end， the PRX solution relies on this alert。

 but we have a better interface solution that I will briefly describe so okay。

 this is Samsung's paper that Google showed was broken。You can still read it if you're interested。😊。

This is a paper from Microsoft that talks about these per activation counters。

 which had a lot of influence， Microsoft actually pushed the solution a lot。😊。

And eventually it got let's say standardized in genetic the question is are these good we wrote papers at the UC last year and also more recently at HPpC again here I mentored the student who wrote these papers right here like here I can present this talk but basically this showed that。

These are these solutions work， they can be configured to be secure and safe。

 but under conditions where when the raw hammer threshold is low。

 you will get very high performance overheads。😡，Even with not so low performance thresholds。

 you get some performance overhead because these solutions change the D timing parameters。

 so we propose some solutions to actually reduce the overheads etcter again if you're interested you can be。

Okay， the question is are we are Ro hammerphy， have you guys gotten rid of bitlips？

And I believe that' the answer is no。We didn't talk about row press but I will't talk about that very quickly。

 we talked about that very briefly last time， this is something that we wrote to ISca in 2023 and the idea is to find mechanisms or phenomena that doesn't require high row activation cut。

😊，So this is a row press paper if you're interested you can take a look at it。

 but the basic idea is it's different from the row hammer vner it's a different redisturbance phenomenon and using user little program you can induce bit flips when you cannot induce with row hammer in some chips and there are some solutions that are provided so what's the idea if you keep the D open for a long time this cause bit flips and adjacent rows they do not require many row activations in fact you can reduce the activation count by one to two or of magnitude。

In fact， which is really， this is fascinating， only one activationctua is enough in some cases。

 you activate the row， keep it open for 30 milliseconds。

 which is not allowed in the existing standard， but it's important for a fundamental understanding of the device from my perspective。

 you keep it open for 30 milliseconds and you get a bit foot。😊。

That means that this fundamental operation of keepingarrowactive， the ro buffer。

 the sensor sound fire is connected to the cells。Les to some disturbance to physically adjacent growths with just one activationctua。

Okay， good to think about。And this was not documented in any device level studies。

 so Ro hammermer was actually studied at the device level。A little bit， but here。

We basically showed this phenomenon and later device level people tried to explain why this is happening。

It's actually very interesting that's why I see the lab that we built as a lab for discovery it's more of a science type of lab to figure out what's going on and then later people can explain the situation right。

😊，Okay， so okay， I think。I have already said this right but if you configure your defense but then you figure out some other phenomenon leads to a low activation count and you cannot configure it so this is the difference between row hammer and row press row hammer you keep activating at the maximum possible rate row press one example you keep the row open for long this is a allowed 70。

8 microseconds joys actually can keep the row open 70。

8 microseconds and can reduce the activation count by an or magnitude let's say。Okay。

 so we studied this with our infrastructure， we studied many manufacturers。

 and initially in our papers we used to don't tell enough tell the names of the manufacturers。

 but now we tell the names of the manufacturers。I think it's good for reapplication of studies。

I already said the amplification of the end vulnerability。

 but it's also at a different underlying error mechanism than whoever so this is the major result essentially if you look at these three manufacturers。

 Samsung Heix and micron。😊，This is row hammermer， you basically activate a row every  you keep an row open for only 36 nanocond before reactivating it。

And as you increase that interval， you reduce the activation minimum activation count to induce a bitlip significantly as you can see right by one to two or of magnitude so 7。

8 microseconds is allowed 70。2 microseconds is also allowed if you do refresh scheduling in the end so this is the allowable range。

 30 milliseconds is not a allowable range but it's important to study and you can see that you get bitlips in these chips with a single hammer count。

So that's very interesting。Okay， so basically， where are we according to Ro press？

You can get bit flips。With 380 activations or 335 activations with HM。

 of study is the world press phenomenon on HM。This is very low number。

 so there are some workloads that actually activate a row。😊，Maybe close to a thousand times in。

In normal operation mode basically you don't it's not a malicious workload it's a benign workload。

 so how do you solve this problem？😡，This becomes worse actually， as you see over here。

 if you actually increase zero on time。😊，This is still allowable 70。2 microseconds。

 you get a bitlip after 5051。😊，Hamers， 51 acts。It's the question is of course， this is benign。

 it may not be exploitable easily， but if this benign workload actually induces bitflips。

 it's actually doing this a lot， then either you get bitfps or you have a secure solution that solves this problem。

 but the secure solution at that。😊，Actation count is going to be very expensive in terms of because it it'll keep kicking in very quickly and then it will generate these refreshes or throttle the rows and as a result you will your performance will tank yes what key reason is actually there to even allow such long row roll on time is there a certain reason why yes is necessary to the that's a good question basically I mean solution will like to is going to limit that row on type today it's allowed for keeping if you so if you keep the row open longer。

😊，What you can do is you can exploit the robot for locality， that's the main reason。

Because there may be more accesses coming in and they could easily come within 70 microconds， right？

Miseconds is questionable， but microseconds they could easily come okay， so that's the reason。

 but if you limit that a little bit， then you can solve this problem more easily。😊。

And existing memory controls actually keep it open as we will see。

You have the question also yes what physical property changes if the capacitor is also basically the transistor over the capacitor is to involved so why does the capacitor basically influence the other role in on state but not in off state？

Oh okay， basically theres no leakage that happens right if in the off state you don't have any leakage but in the on state because different pros share the substrate underlying substrate I didn't go into the vest of mes and I have some slides at the end。

 they share the substrate in the on state there is electrons leak。😊，Very good questions， okay。

Okay I think I've said a lot of these but basically this gets worse as temperature increases it's also it affects a different set of cells than row hammer it's also interesting that behaves differently as access band and temperature change compared to row hammer so we basically declare that this is a different phenomenon than row hammer even though it's related and later device level works actually prove that with their simulations so we also showed that you could actually keep a row open in an Intel system using some memory by accessing different cache blockss in the so this again a user level program that keeps accessing different cache blockss in the same row and the memory control keeps the row open。

😊，For example， we keep accessing 32 Ca blockss 48 cache blockss， 64 cash blockss。

 and essentially we get bit flips with raw prints whereas we don't get bit flips with raw hammer for example。

 so you need to keep the all open long enough to get bit flips and these are real results later works from other people have replicated these results I might mention them。

😊，So row press is also a real phenomenon it's a bit harder to use than row hammermer clearly on a real system。

 but it's possible to do okay so how do you mitigate this basically as you can kind of alluded to you can limit the maximum row open time but you don't want to limit it too much if you limit too much then you're not exploiting robotbo for locality so we basically said find a sweet spot。

😊，Hopefully not seven microseconds。Keep it lower， you make a trade off， you exploit lesser of local。

 but you also reduce the you're not as vulnerable if you actually use a much unlimited。

 let's say you' open tie and you configure the rohan miigation to account for the low press induced reduction in AC。

😊，That's the idea right you could do that so basically you could adapt all of the row hammer mitigations that are proposed to row press。

 but it comes at a cost。You start。Essentially， you start preventing bit flips or taking preventive actions to prevent bitfps at a much lower activation company。

Okay， and these are the results we showed that basically if you have R press and if you want to mitigate it。

 your performance overhead increases。We have different mechanisms。

Okay and this is a paper that was published， it' got the distinguished artifactact Award from micro so the artifact is nice。

 you can build on it if you're interested and also it was selected as a topic so you can take a look at it if you're interested。

😊，So there's more to come， I think。Let's see I think we are getting close to the end， okay。

 five minutes， five minutes and 1 hundred slides， let's see。We're going to try hammer。Okay。

 so I've already said this I'm not going to talk about this so if you're interested you can read more papers so this is row hammering combining role hammer and roll press which is interesting there's more studies this is another work you I did you I did a lot of work for a thesis。

😊，So he deservely got those awards so we always argued for a better communication between Dm and controller also I think one of the interface that's broken today is the interface between memory and the controller as we've discussed multiple times so this work selfm Dm which was published at micro last year after six rejections because people either thought this was not interesting or this was。

😊，To revolutionary， which is kind of interesting right different viewers think differently right what did they say revolutionary or。

😊，They think it's almost too early to publish this Okay， yeah， right。

 well they said something else also and it's close to evolutionary， right？😊。

Okay anyway so the basic idea is very simple it's actually a very small change to the interface the idea is to enable autonomous maintenance in DM because there are some things that DM chip can do without requiring the memory controller like doing refresh for example or doing raw hammer mitigation if you actually it has some intelligence inside it can do a much better refresh mitigation refresh retention time mitigation row hammer mitigation memory scrubbing error correction etc The problem today is memory controller very tightly controls DM and DM cannot initiate anything by itself。

😊，So it cannot say oh I'm going to do a Roheim mitigation， it can。

 but it's limited as we discussed with peer anchor so our idea was to say we make one single change to the Dm interface。

And enable a lot of optimizations in the DEM chip。Without requiring the memory controller to change or without requiring the memory interface to change。

 we argue that this would。Be good for multiple reasons because you could actually implement these mechanisms nicely and easily over here this also decouples the innovations that happen in the year'm shift from the interface now your interface doesn't need to change but a memory manufacturer can implement some innovation over here so nobody needs to wait for 10 years。

 20 years etc to change the interface because interface change is a huge problem in this area or you don't need change the memory joy so that's the idea basically。

😊，So the idea is again， what's the interface change， the interface change is very simple。

 the D chip can say no to the memory controller。😊，In a fine way。

 if the memory controller says activate this row， memory controller the an says no， I'm busy。

That's it that's the only interface change， I don't know what's revolutionary about this。

 but it's apparently it's revolutionary I mean there are implications of course right where does the memory control now reside right you you asked that question earlier now part of the memory control resides over here。

😊，And some people don't want to give up the control。

Okay even though the system will become better so basically memory controller orchestras accesses theM chip does what it is good at performs maintenance so I think it's a very principle to approach to partition that work nicely between memory control and DM chips and we showed that you could actually implement a lot of the refresh solutions that are proposed in literature a lot of Ro hammer solutions proposed in literature memory scrubbing solutions proposed in literature and get good results and I let you read the paper this was part of Haan's work but Aak presented because this got rejected six times。

😊，In the end。The fact that's Sa， yes yes， it got accepted in micro 2024。😊。

I think we start submitting in 2022 right。And nothing has really changed in the work like evaluation writing changed a little bit。

 but the basic idea doesn't change。😀呵呵。😊，And when it was this issue at microcro。

 somebody came up and said， this is a great idea， this is a principal solution to this problem。😊。

Yeah， so great ideas get rejected basically， that's the that's one of the takeaway over here。😊。

🎼I believe thiss actually a nice idea and we need to do more of this this is so okay another way of thinking about this is okay I will stop here after that。

 but now what we're doing is if you think about the memory controller memory controller controlling everything in the arms is a very procentric approach processor sincere we're very procentric what we're saying is make the。

😊，Meary control a little bit more memorycentric。That's the idea。

 I think it's a move toward more memorycentic directions in fact in the paper we say that if you have actually have this sort of interface。

 you could also implement processing in memory operations more easily etc， in the ERM chip。😊。

Again I'll leave you with that I didn't cover all of my slides。

 but that's okay no problem if you're interested you can look at the remaining ones。😊。

Or maybe we'll start with part of this next week。Okay， well I'll see you guys next week。



![](img/4281349ccf53b3eafe6978d710441345_18.png)