# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P11：-11-.Lecture 11_ Q&A (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

哎。I guess we should do an intro to this as well。 So this is a just sort of a free form Q& A lecture where you as in the two people sitting here。

 but also everyone at home who did not come here in person get to ask questions and we have a bunch of questions to people asked in advance。

 but you can also ask additional questions during for the two of you who are here。

 you can do it either by raising your hand or you can submit it on the forum and be anonymous It's up to you regardless though what we're gonna to do is just go through some of the questions have been asked。

 try to give some as helpful answers as we can， although they are unprepared on our side， and yeah。

 that's the plan。 I guess we go from popular to least popular。😊，Far away。All right。

 so for our first question， any recommendations on learning operating system related topics like processes。

 virtual memory interrupts， memory management， etc？

So I think this is an interesting question because these are really low level concepts that often do not matter unless you have to deal with this in some capacity right so one instance where this matters if you're writing really low level code like you're implementing a kernel or something like that where you want to just hack on the Linux kernel It's rare otherwise that you need to work with especially like virtual memory and interrupts and stuff yourself。

 processes， I think are more general concept that we've talked a little bit about in this class as well and tools like Htop and PG and kill and signals and that sort of stuff。

 in terms of learning it maybe one of the best ways is to try to。

Take either an introductory class on the topic。 So for example， MIT has a class called 6828。

 which is where you essentially build and develop your own operating system based on some code that you're given and all of those labs are publicly available and all the resources for the class are publicly available And so that is a good way to really learn them by doing them yourself there are also various tutorials online that basically guide you through how do you write a kernel from scratch not necessarily a very sort of elaborate one not when you would want to run any real software on but just to teach you the basics。

 And so that would be another thing to look up is like how do I write a kernel in and then your language of choice you will probably not find one that lets you do it in Python but in like C++ rust there are a bunch of topics like this。

One other note on operating systems， so like John mentioned， MIT has a 68 to8 class。

 but if you're looking for a more high levelvel overview。

 not necessarily programming or own operating system， but just learning about the concepts。

 another good resource is a book called Modern Operaing Systems by Andy Tananbaum。

There's also actually a book called the FreeBSD Operaing System， which is really good。

 it doesn't go through Linux， but it goes through freeBSD。

 and the BSD kernel is arguably better organized than the Linux 1 and better documented。

 and so it might be a gentler introduction to some of those topics than trying to understand Linux。

Do you want to check it as it answered， yes， nice answered。For our next question。

What are some of the tools you'd prioritize learning first？

MaybeWe can all go through and give our own anonymous this。Tools to paradise learning first。

 I think learning your editor well just serves you in all capacities right like being efficient at editing files is just like a majority of what you're going to spend your time doing and in general just using your keyboard more in your mouse less it means that you get to spend more of your time doing useful things and less of your time moving I think that would be my top priority。

Jings works。So I would say that what tools to prioritize will depend on what exactly you're doing。

 The thing kind of the core idea is like you should try to find the types of task that you are doing repetitively and say like here if youre instead of like if you're doing some sort of like machine learning workload and you find yourself using you the notebooks like the one we percentage yesterday a lot。

 then kind of again like using a mouse for that might not be the best idea and you want to familiarize with the keyboard circuits and pretty much with anything you will end up figuring out thatre like some repetitive task and you're running a computer and just trying to figure out there's probably a better way to this be a terminal an editor and it might be really interesting to use how to learn to use some of the topics that we have covered but if they're not extremely useful in everyday in everyday basis then it might be not worth prior。

大son them。Out of the topics covered in this class， in my opinion。

 two of the most useful things are version control and text editors and I think they're a little bit different from each other in the sense that text editors I think are really useful to learn well。

 but it was probably the case that before you started using Vim and all its fancy keyboard shortcuts。

 you had some other text editor you were using before and you could edit text just fine maybe a little bit inefficiently whereas I think version control is another really useful skill and that's one where if you don't really know the tool properly。

 it can actually lead to some problems like loss of data or just inability to collaborate properly with people So I think version control is one of the first things that's worth learning well Yeah I agree with that I think learning a tool like Git is just going save you so muchharache down the line it also to add on to that it really helps you collaborate with others and need to touched a little bit on Gitthub in the last lecture and like just learning to use that tool well in order to work on larger software projects that other people are working on is an invaluable skill。

For our next question， when do I use Python versus a batchsh script versus some other language？

This is tough because I think this comes down to what Jose was saying earlier too。

 that it really depends on what you're trying to do for me， I think for bash scripts in particular。

 bash scripts or for automating running a bunch of commands you don't want to write any other like business logic in bash like it is just for I want to run these commands in this order。

 maybe with arguments， but like even that it's unclear that you want a bash script。

 once you start taking arguments， similarly like once you start doing any kind of like text processing or configuration。

 all of that reach for a language that is a more serious programming language than bas bash is really for sort of short one off scripts or ones that have a very welldeed use case on the terminal in the shell probably。

😊，For a slightly more concrete guideline， you might say write a bash script if it's less than 100 lines of code or so。

 but once it gets beyond that point， bash is kind of unwieldy and it's probably worth switching to a more serious programming language like Python。

And to to that， I will say that I found myself writing sometimes scripts in Python because if I had already solved some sub problem that covers part of the problem in Python。

 I find it much easier to compose the previous solution that I found out in Python and just tried to reduce Baco that I don't find as reucable as Python and in the same way。

 it's kind of nicer a lot of people have written something like Python libraries So like Ruby libraries that do a lot of these things whereas in Ba it's kind of hard to have like code reviewsuse。

And in fact， rule。And in fact， I think to add to that。

 usually if you find a library in some language that helps with the task you're trying to do use that language for the job and in Bsh there are no libraries。

 there are only the programs on your computer so you probably don't want to use it unless like there's a program you can just invoke I do think another thing worth remembering about bash is bash is really hard to get right。

 it's very easy to get it right for the particular use case you're trying to solve right now。

 but like。Things like what if one of the file names has a space in it is has caused so many bugs and so many problems in bash scripts。

 And if you use a real programming language， then those problems just go away。

Checked it for our next question， what is the difference between sourcing a script and executing that script？

OSo this actually we got in office hours a while back as well。

 which is aren't they the same like aren't they both just running the Bsh script and it is true both of these will end up executing the lines of code that are in the script the ways in which they differ is that sourcing a script is telling your current bash script your current bash session to execute that program whereas the other one is start up a new instance of bash and run the program there instead and this matters for things like imagine that script Auto age tries to change directories。

If you are running the script as in the second im error dot/script。sh。

 then the new process is going to change directories。

 but by the time that script exits and returns to your shell。

 your shell still remains in the same place。However， if you do CD in a script and you source it。

 your current instance of bash is the one that ends up running it。

 and so it ends up CDding where you are。This is also why， if you define functions， for example。

 that you may want to execute in your shell session， you need to source the script， not run it。

 because if you run it， that function will be defined in the instance of bash in the bash process that gets launched。

 But it will not be defined in your current shell。 I think those are two of the biggest differences between the two。

弄好么嘟嘟。Next question， what are the places where various packages and tools are stored and how does referencing them work。

 what even is/lash bin or/lashlibB？So as we cover in the first lecture leaf there is like this path environment variable which is kind of like a semicolon separated string of all the places where your cell is going to look for binaries and if you just do something like echo dollar our path you're going to get this list and all these places are going to be consulted in order it's going to go through all of them and in fact it is already we covered which so if you run which and specific command the cell is actually going to tell you where it's fine in this。

Beyond that there are like some conventions where like a lot of programs will install their binaries and their like user bin。

 or at least they will like include simlink user bins so you can find them。

 There's also user local bin there are special directories， for example。

 user as bin is only for the pseudo user and some of these conventions are slightly different between different diss。

 So I know like some dis， for example， install the user libraries and their OPT， for example。In the。

course much。to say。Yeah， I think one thing just to talk a little bit more about bin and then Anish maybe you can do the other folders so when it comes to B。

 the convention there are conventions and the conventions are usually slash bin are for essential system utilities。

 user bin are for user programs and user local bin are for user compiled programs sort of so things that you installed that you intend the user to run are in user bin things that a user has compiled themselves and stuck on your system probably goes in user local bin but again this varies a lot from machine to machine and Dis to distro on arch Linux for example。

 B is just asse to user bin they are the same and as Jose mentioned there's also SB which is for like programs that are intended to only be on this route that also varies from Dis to distro。

 whether you even have that directory and on many systems like user local bin might not even be in your path or might not even exist on your system。

On BSD， on the other hand， user local bin is often used a lot more heavily。Yeah。

 and so what we were talking about so far， these are all ways that files and folders are organized on Linux。

 things or Linux or BSD， things vary little bit between that and Mac OS or other platforms。

 I think for the specific locations if you need to know exactly what it's used for you can look it up but some general patterns to keep in mind are anything with bin in it has binaries。

 executable programs in it， anything with lib in it has libraries in it so things that programs can link against and then some other things that are useful to know are there's a slash ETC on many systems which has configuration files in it and then there's slash home which underneath that directory contains each user's home directory so like on a Linux box my username or if it's a niche will correspond to home directory slash home slash in niche。

Yeah， I guess there are a couple of others like s temp is usually a temporary directory that gets erased when you reboot not always。

 but sometimes usually check on your system there's slash var which often holds like files that change over time so these are usually going to be things like log files for package managers they' are going to be things like log files files that keep track of process Is then there's s dev which host devices usually so these are special files that correspond to devices on your system we talked about slash cis。

Anish mentioned E TC slash O OP T is a common one for just like third party software that。Basically。

 it's usually for companies ported their software to Linux。

 but they don't actually understand what running software on Linux is like。

 and so they just have a directory with all their stuff in it。 and when those get installed。

 they usually get installed into s OPT。嗯。I think those are the ones off the top of my head。Yeah。

And we will list these in our lecture notes， which we'll produce after this lecture。Next question。

 should I app get install a Python whatever package or Pip install that package？

So this is a good question， I think at a higher level this question is asking should I use my systems package manager to install things or should I use some other package manager。

 like in this case， one that's more specific to a particular language and the answer here is also of it depends。

 sometimes it's nice to manage things using the system package manager so everything can be installed and upgraded in a single place。

 but I think oftentimes whatever is available in the system repositories the things you can get via a tool like Appgit or something similar might be slightly out of date compared to the more language specific repository So for example a lot of the Python packages I use I really want the most up- to-date version and so I use PIP to install them。

并。To extend on that it is sometimes the case that like the system packages might require some other dependencies that you might not like realize about and it also might be the case that like for some systems and enough at least for like Alpin Linux。

 they don't have wheels for like a lot of the python packages so it will just take longer to compile them。

 it will take more space because they have to compile them from scratchs whereasas in like if you just go to Pip has binaries for a lot of different platforms and that will probably work。

You also should be aware that Pa might not do kind of exact thing in different computers。

 So for example， if you are in a kind of laptop or like a desktop that is running like X86 or X 86。

64， you probably have binaries， but like if you're running something like rospberry Pi or some other kind of embedded device this are running on a different kind of hardware architecture and you might not have binaries。

think that's also kind of good to take into account。 In that case。

 it might be worthwhile to use the the system packages just because they will take much longer。

 they will be much shorter to get them than just to kind of compile from scratch the entire Python installation。

 Apart from that， I don't think I can think of any exceptions where I will actually use the system packages。

 instead of the Python provided ones。Maybe virtual end but multiple versions。

Like worth talking about。嗯。So one other thing to keep in mind is that sometimes you will have more than one program on your computer and you might be developing more than one program on your computer and for some reason。

 not all programs are always built with the latest version of things sometimes they lag a little bit behind and when you install something system wide you can only depends on your exact system。

 but often you just have one version what Plets you do especially combined with something like Python's virtual end and similar concepts exist for other languages where you can sort of say I want to NPM does the same thing as well with its node modules。

 for example， where I'm going compile the dependencies of this package in sort of a subdirecty of its own and all of the versions that it require are going be built in there and you can do this separately for separate project so that they have different dependencies or the same dependencies but different versions these still。

Have kept separate。 And that is one thing that's hard to achieve with system packages。Next question。

 what's the easiest and best profiling tools to use to improve performance of my code？

This is a topic we could talk about for a very long time。

 The easiest and best is to print stuff using time。

Like I'm not joking like very often the easiest thing is like in your code you at the top。

 you figure out what the current time is and then you do sort of a binary search over your program of at a print statement。

 the prints how much time has elapsed since the start of your program and then you do that until you find the segment of code that took the longest and then you go into that function and then you do the same thing again and you keep doing this until you find roughly where the time was spent It's not foolproof。

 but it is really easy and it gives you good information quickly If you do need more advanced information Valgri has a tool called cache grind call grind cache grind。

😊，One of the two。 and this tool lets you run your program and measure how long everything takes and all of the call stacks like which function called which function。

 and what you end up with is a really neat annotation of your entire program source with the heat of every line。

 Basically how much time was spent there。 it does slow down your program by like an order of magnitude or more and it doesn't really support threads。

 But it is really useful if you can use it。 if you can't。

 then tools like perf or similar tools for other languages that do usually some kind of sampling profiling like we talked about in the profile or lecture can give you pretty useful data quickly。

 but there。😊，It's a lot of data around this， but they're a little bit biased in what kind of things they usually highlight as a problem。

 And it can sometimes be hard to extract。Meaningful information about what should I change in response to them。

 whereas the sort of print approach very quickly gives you like this section of code is bad or slow。

I think would be my answer。 Flame graphs are great。

They're a good way to visualize some of this information。Yeah。

 I just have one thing to add oftentimes。Programming languages have language specific tools for profiling。

 So just figure out what's the right tool to use for your language。

 Like if you're doing JavaScript in the web browser。

 the web browser has a really nice tool for doing profiling。 you should just use that。

 Or if you're using go， for example， go has a builtin profiler is really good。

 You should just use that。Thing to just all last thing to that is sometimes you might find that the like doing this binary search over time that youre kind of。

Finding where the time is going， but this time is sometimes happening because you're waiting on the network or you're waiting for some file。

 And in that case， you want to make sure that like the time that is kind of like if I want to write like1 GBat file or like read one gig file and put it into memory you want to check that the actual time that is there is the minimum amount of time you actually have to wait if it's 10 times longer。

 you should try to use some other tools that we cover in the thebugging and profiling section to see why you are not utilizing all your resources because。

Because that。No， no， finish your thought。 I just， I realize because that that might be a lot of what's happening。

 I think， like， for example， in in my research， like machine learning workloads a lot of the time is loading data。

 and you have to make sure that like the time it takes to load data is actually the minimum amount of time。

 you want to have that happening。😊，And to build on that。

 there are actually specialized tools for doing things like analyzing wait times。

 very often when you're waiting for something。 What's really happening is you're issuing a system call and that system called takes some amount of time to respond。

 like you do a really large write， a really large read or you do many of them。

 And one thing that can be really handy here is to try to get information out of the kernel about where your program is spending its time。

 And so there's a it's not new， but there's a relatively newly available thing called BPF or EBPF。

 which is essentially kernel tracing。 And you can do some really cool things with it。

 And that includes tracing user programs。 It can be a little bit awkward to get started with。

 There's a tool called BPF trace that I would recommend you look into if if you need to do like this kind of low level performance debugging。

 But it is really good for this kind of stuff。 You can get things like histograms over how much time was spent in particular system calls。

 It it's a great tool。😊，What browser plugins do you use？O。

 I try to use as few as I can get away with using。Becauseuse I don't like things being in my browser。

 but there are a couple of ones that are sort of staples。 The first one is U block origin。

 So U blocklock origin is one of many ad blockers， but it's a little bit more than an ad blocker it is what do they call it like network filtering tool so it lets you do more things than just block ads。

 It also lets you like block connections to certain domains。

 block connections for certain types of resources。 so I have mine set up in what they call the advanced mode where basically you can disable basically all network requests but it's not just network requests It' also like I have disabled all inline scripts on every page and all thirdpart images and resources and then you can sort of create a white list for every page so it gives you really low level tools around how to how to improve the security of yourrousing but you can also set it in not the advanced。

odeAnd then it does much of the same as a regular ad blocker would do。

 although in a fairly efficient way。 if you're looking at an ad blocker。

 it's probably the one to use and it works on every browser。That would be my topic， I think。

Th probably the one that use like the most like actively is one called Stylus the less you modify like the CSs like the style sheets that like web pages have and it's pre neat because like sometimes you're like looking at a website and you want to hide some part of the website you don't care about like maybe not maybe like some sidebar you're not finding useful thing is at the end of the day these things are displaying in your browser and you have control of what code is executing and similar to what John was saying like you can customizes to know end and what I have for a lot of web pages like oh hide this part or also trying to make like dark mode for them like you can change pretty much the color for every single website and it was actually pre neat is that there's like a repository of people that have contributed this style sheet for like the website So if someone probably has like one for Github like they want dark GiHub and someone has already already contribute one that makes。

m more pleasing to browse apart from that one that I is not really fancy。

 but I have found it incredibly helpful is' one that just takes a screen stop an entire website and it will kind of scroll for you and make kind of like compound image of the entire website and that's really great for when trying to print a website is just terrible because they have built far interesting。

😊，OhNow you mentioned building into Firefox。 Another one that I really like about Firefox is the multi account containers。

 Oh which kind of lets you like by default， a lot of kind of web browsers like for example。

 Chrome have this kind of notion of there's the session that you have where you have all your cookies and there are kind of old around the different websites in the sense that like you keep opening new tabs and unless you go into incognito。

 you kind have the same profile and that profile is the same for all websites theres like this it's like it's an extension it's built submits。

😊，It's it would complicated。 Okay， so I think like you actually have to say you want to install it or enable it。

 And again， like the name is multian containers and this lets you tell Firefox to have like kind of separate isolated sessions。

 So for example， you want to say， oh， I kind of have a separate sessions for whenever I visit Google or whenever I visit Amazon。

😊，And that can be pretty neat because then you can like at a browser level。

 it's ensuring that no like information sharing is happening between the two of them。

 and it's much more convenient than having to open a and the window where it's going to clean all the time this stuff。

One thing you mention is Stylus versus stylish Oh yeah one I forgot about that。

 One important thing is the browser extension for si loading CSS styles it is called stylus and that's different from the kind of other one that was called Styllist because that one got bought at some point but some city company that started using it not only to have that functionality。

 but also to read your entire browser history and send that back to their server so they couldn data it so then people just build this kind of open source alternative that is called stylus and that's the one we recommend said that I think the repository for Sts is the same for it two open them but I will have to double check that。

Do you have any browser plugins Yes， so I also have some recommendations for browser plugins。

 I also use UBlock origin， and I also use stylus。But one other one that I'd recommend is integration with a password manager。

 so this is a topic that we have in the lecture notes for the security lecture but we didn't really get to talk about in detail。

 but basically password managers do a really good job at increasing your security when working with online accounts and having browser integration with your password manager can save you a lot of time like you can open up a website and it can autofill your login information for you so't need go and copy and paste it back and forth between a separate program if it's not integrated with your web browser and it can also this integration can save you from certain attacks that would otherwise be possible if you were doing this manual copy pasting for example phishing attacks so you find a website that looks very similar to Facebook and then you go to login with your Facebook login credentials and you go to your password manager and copy paste the correct credentials into this funny website and now all of a sudden it has your password but if you have browser integration then the extension can automatically check like am I on f E co or some other domain that maybe looks similar and it will not enter the login information if it's the wrong domain so browser extension for password managing is good。

No， I agree。Next question， what are other useful data wrangling tools？嗯。

So in yesterday's lecture I mentioned curl， so curl is a fantastic tool for just making web requests and dumping them into your terminal。

 you can also use it for things like uploading files， which is really handy。

In the exercises of that lecture， we also talk about JQ and PP。

 which are command line tools that let you basically write queries over Jason and HTML documents respectively。

 that can be really handy。Other data wrangling tools， a pearl。

 the pearl programming language is often referred to as a right only programming language because it's impossible to read。

 even if you wrote it， but it is fantastic at doing just like straight up text processing。

 like nothing beats it there so。😊，Maybe worth learning some very rudimentary pearl just to write some of those scripts。

 like it's easier often than writing some like hacked up combination of Greep and Akinai。

 and it will be much faster to just hack something up than writing it up in Python， for example， but。

Apart from that， other data wrangling。No， not off the top of my head， really。Colllumum D T。

If you pipe any kind of like white space separated input into column dash T。

 it will align all the white space of the columns so that you get nicely aligned columns。Yeah。

 that's an head and tail。 But we've talked about those。

Think a couple of additions to that that I find myself using commonly one is。

Bim like Bm can be pretty useful for like doing data wrangling in itself。

 sometimes you might find that the operation that you're trying to do is hard to like put down in terms of like piping different prayers。

 But if you can just open the file and just record like a couple of quick beam macros to do what you wanted to do it might be like much。

 much easier。 and the one and then the other one， if you're dealing with tabular data and you want to do more complex operations like sorting by one column then grouping and then computing some sort of sta。

 I think a lot of that workload I ended up just using python and pandas because it's kind of build for that。

 And one of the pre neat features that I find myself also using is that it will spark to many different formats。

 So of this intermediate state has its own kind of。Paandnda's data frame object。

 but it can kind of export to HTML later a lot of different like table format。

 So like if your end product is some sort of summary table， then pandas。

 I think is a fantastic choice for that。😊，I would second the Vm and also Python。

 I think those are two of my most used data wrangling tools for the VIm1。

 Last year we had a demo and this year is's in the lecture notes， but we didn't cover it in class。

 we had a demo of turning an Xm file into a JSson version of that same data using only Vm macros。

 And I think that's actually like the way I would do it in practice I don't want to go find a tool that does this conversion it was actually simple enough to encode as a Vm macro that I just did it that way。

 and then also Python， especially in an interactive tool like a Jupyter notebook is a really great way of doing data wrangling。

 a third tool I'd mention， which I don't remember if we covered in the data wrangling lecture or elsewhere。

 is a tool called Pandoc which can do transformations between different text document formats So you can convert from plain text to HTML or HTML to markdown or late text to HTML or many other formats it supports a large list of input formats and a large list of formats。

I think there's one last one which I mentioned briefly in in the lecture data wrangling。

 which is the R programming language。 it's an awful。 I think it's an awful language to program in。

 and I would never use it in the middle of a data wrangling pipeline。 but at the end。

 in order to like produce pretty plots and statistics。

 R is great because R is built for doing statistics and plotting。

s there's a library for R called G G plot， which is just amazing G plot2。

 I guess technically is it's great it's great。 It produces very nice visualizations。

 and it lets you do it does to very easily do things like if you have a data set that has like multiple facets。

 like it's not just X and y。 it's like X， Y， Z and some other variable and then you want to plot like the throughput。

😊，Grouped by all of those parameters at the same time in producer visualization are very easily lets you do this。

 And I haven't seen anywhere else that lets you do that as easily。Next question。

 what's the difference between Docker and a virtual machine？啊。What's the easiest way to explain this。

 So Docker starts something called containers。 And Docker is not the only program that starts containers。

 There are many others， and usually they rely on some feature of the underlying kernel。

 In the case of Docker， they use something called L XC。

 which are Linux containers and the basic premise there is if you want to start what looks like a virtual machine that is running roughly the same operating system as you are already running on your computer。

 Then you don't really need to run。Another instance of the kernel， really， that other。

Virtual machine can share a kernel。 you can just use the kernels built in isolation mechanisms to spin up a program that thinks it's running on its own hardware。

 But in reality， it's sharing the kernel。 And so this means that containers can often run with much lower overhead than a full virtual machine will do。

 but you should keep in mind that it also has somewhat weaker isolation because you are sharing a kernel between the two。

 if you spin up a virtual machine， the only thing that's shared is sort of the hardware and to some extent。

 the hypervisor， Where with a Docker container， you're sharing the full kernel and that。

Is a different threat model that you might have to keep in mind。One other small note there。

 as John pointed out， to use containers， something like Docker。

 you need the underlying operating system to be roughly the same as whatever the program that's running on top of the container expects。

 and so if you're using Mac OS for example， the way you use Docker is you run Linux inside a virtual machine and then you can run Docker on top of Linux so maybe if you're going for containers in order to get better performance。

 you're trading isolation for performance， if you're running on Mac OS that may not work out exactly as expected。

And one last note is that there is a slight difference of like docker and containers。

 I think one of the main gutes that you have to be familiar with is that like containers are more similar to virtual machines in the sense of like they will persist all the storage that you have where Docker by default won't have that like Docker is kind of supposed to be running some the many D like I want to just run some software and I get the image and it runs and if you want to have any kind of persistent storage that links to the whole system you have to kind manually specify that whereas like a virtual machine is using some like virtual disk that is being provided。

Next question， what are the advantages of each operating system and how can we choose between them。

 for example， choosing the best Linux distribution for our purposes。I will say that for many。

 many tasks， the specific Linux distribution that you're running is not that important。

 The thing is it's just kind of knowing there there are different types of groups of distributions So for example。

 there are like some distributions that have really frequent updates but they will break more easily。

 So for example， like a Linux have like rolling updates the way of post updates where like things might break。

 but they are fine with things being that way where maybe where you have some really important and web server that is hosting all your kind of business analytics。

 you want that thing to have like a much more steady way of updates。 So that's for example。

 why you will see distributions like De and being much more conservative about what they post or even for example。

 when to makes a difference between kind of like the longter releases that they only update every two years and the more kind of like periodic releases of like when there is like two a year。

That they may so kind of knowing that the difference apart from that。

 some distributions have like different ways of providing the binaries to you and the way they kind of have their repositories。

 So I think like a lot of redha Linux don't want non-fr drivers in their official repositories where I think like U is fine with some of them。

Apart from that I think like just a lot of what is called to most Linuxs is kind of sharing between them and there's a lot of learning in the common ground so you don't have to worry about the specifics。

Keeping with the theme of this class being somewhat opinionated。

 I'm going to go ahead and say that if you're using Linux， especially for the first time。

 choose something like Uuntu or Debian。 So Uuntu is a Debian based distribution。

 but maybe's a little bit more friendly。 Deian is a little bit more minimalist。

 I use Deian on all my server， for example， and I use Deian desktop on my desktop computers that run Linux。

 If you're going for。Maybe trying to learn more things and you want a distribution that trades stability for having more up to date software。

 maybe at the expense of you having to fix a broken distribution every once in a while。

 then maybe you can consider something like arch Linux， but think those de in into。😀Ha。😊。

Or Slackware， Oh man。 I'd say that if you're installing Linux and just like want to get work done。

 Debbie's a great choice。Yeah， I think our agree that the other observation is like you couldnt solve BSD BSD has gotten it's come a long way from where it was there's still a bunch of software you can't really get for BSD but it gives you a very well documented experience and one thing that's different about BSD compared to Linux is that in BSD when you install BSD you get a full operating system mostly so many of the programs are maintained by the same team that maintains the kernel and everything is sort of upgradedited together which is a little different than how things work in the Linux world。

 it does mean that things often move a little bit slower I would not use it for things like gaming either because driver support is but it is an interesting environment to look at。

And and then for things like Macs and Windows， I think。I。If you are a programmer。

 I don't know why you are using Windows unless you are building things for Windows。嗯。

Or you like want to be able to do gaming and stuff， but in that case。Like maybe try dual booting。

 even though that's a pain too， Macs is a good sort of middle point between the two where you get a system that is like relatively nicely polished for you。

But you still have access to some of the lower level bits， at least to a certain extent。

 It's also really easy to doboot Macos and Windows。

 It is not quite the case with like Macos and Linux or Linux and Windows。All right。

 for the rest of the questions， so these are all zero output questions。

 and maybe we can go through them quickly in the last five or so minutes of class。

So the next one is Vm versus Eaxm。Easy answer， but a more serious answer is。

Like I think all three of us use VIM as our primary editor。

 I use EMX for some research specific stuff which requires EMX。But at a higher level。

 both editors have interesting ideas behind them。 And if you have the time。

 it's worth exploring both to see which fits you better and also。

Like you can use Emax and run it in a Vm emulation mode。

 like actually know a good number of people who do that so they get access to some of the cool emax functionality and some of the cool philosophy behind that like Emax is programmable through a list which is kind of cool。

 much better than Vim script but people like ViIms modal editing so there's an Emax plugin called E mode which gives you vimmodal editing within Emax so it's not necessarily a binary choice you can kind of combine both tools if you want to and it's worth exploring both if you have the time。

😊，Next question， any tips or tricks for machine learning application？Our resident machine learning。

I think the like knowing how a lot of these tools， mainly like they wrgling in a lot of the shelters is kind of really important because。

It seems a lot of what you're doing as a machine learning researcher is trying different things。

 But think one core aspect of doing that and like a lot of scientific work is being able to have like reproducible results and logging them in a sensible way。

 So for example， instead of trying to come up with really hack solutions of how you name your folders to make a sense of the experiments。

 maybe just worth having， for example， what I do is have like a JO file that describes the entire experiment and all the parameters are within。

 and then I can really quickly using the tools that we have cover query for all the experiments that have some specific purpose。

 So like some use some data set， things like that。 apart from that。

 the other side of this is if you are running of things for training machine learning applications and you are not already using some sort of cluster that your university or your companies providing and you're just kind of manually SS with a lot of。

Lughs like do because that's kind of the easy way。 It's kind of worth of automating a lot of that job because it might not seem like it。

 but kind of manually doing a lot of these operations takes away a lot of your time and also kind of your kind of mental energy for running these things。

Any more V tips？I have one so in the VIm lecture we tried not to link you to too many different VIm plugins because we didn't want that lecture to be overwhelming。

 but I think it's actually worth exploring Vm plugins because there are lots and lots of really cool ones out there you can one resource you can use is the different instructors do files like a lot of us I think I use like two dozen Vm plugins and I find a lot of them quite helpful and I use them every day and we all use slightly different subos of them so go look at what we use or look at some of the other resources we've linked to and you might find some stuff useful。

Think to add to that is， I think we。Went into a lot of detail the electrocur if Im wrong is getting familiar with the leader key。

 and which is kind of a special key。 a lot of programs with like plugins that we link to。

 And for a lot of the common operations， Bm has sort ways of doing it。

 But you can just figure out like quicker versions of doing that。 So for example。

 I know that you can do like semicolon W Q to exit and like save an exit or that you can do like capital set set。

 But I just actually just do leader which for me space and then W。

 And I have done that for a lot of a lot of of common operations that I keep doing all the time because just like saving one keytrooke for extremely common operations is just having like thousands a month。

Yeah， just to expand a little bit on what the leader key is So in VIm you can bind some keys I can do like control J does something like holding one key and then pressing another。

 I can bind that to something or I can bind a single keystroke to something what the leader key lets you do is bind so you can assign any key to be the leader key and then you can assign leader followed by some other key to some action for example like Jose's leader key is space and you can combine space and then releasing space followed by some other key to an arbitrary vim command。

And so it just gives you yet another way of binding like a whole set of key combinations。

 leader key plus kind of any key on the keyboard to some functionality。

I think I forget whether we covered macros in the VIm lecture but like Vm macros are worth learning。

 they're not that complicated， but knowing that they're there and knowing how to use them is going save you so much time the other one is something called marks So in VIm you can press M and then any letter on your keyboard to make a mark in that file and then you can press apostrophe in the same letter to jump back to the same place and this is really useful if you're like moving back and forth between two different parts of your code for example。

 you can mark one as a and one is B and you can then jump between them with tick A and tick B there's also control O which jumps to the previous place you were in the file no matter what caused you to move So for example。

 if I am in some line and then I jump to B and then I jump to a control O will take me back to B and then back to the place I originally was this can also be handy for things like if you're doing a search then。

The place that you started the search is a part of that stack so I can do a search。

 I can then like step through the results and like change them and then control O all the way back up to the search。

 Control O also lets you move across files。 So if I go from one file to somewhere else in a different file to somewhere else in the first file control O will move me back through that stack。

 And then there's control I to move forward in that stack。

 And so it's not as though you pop it and it goes away forever。

The command colon earlier is really handy。 So colon earlier gives you an earlier version of the same file。

 and it it does this based on time， not based on actions。 So for example。

 if you press a bunch of like undo and redo and make some changes and stuff earlier。

 will'll take a literally earlier as in time version of your file and restore it to your buffer。

 this can sometimes be good。 if you like undid and then rewrote something。

 And then realize you actually wanted the version that was there before you started undoing earlier。

 let's you do this。 And there's a plugin called。😊，Undo tree or something like that。

 number of there are several of these that let you actually explore the full tree of undo history。

 The vim keeps because it doesn't just keep a linear history。

 It actually keeps a full tree and letting you explore that might in some cases。

 save you from having to retype stuff you typed in the past or stuff you just forgot exactly what you have there that used to work and no longer works。

 And then's one final one I want to mention， which is we mentioned how in vim you have verbs and nouns So you have verbs like delete or yank And then you have nouns like next of this character or percent to swap brackets and that sort of stuff。

 The search command is a noun。😊，So you can do things like D slash， and then a string。

 And it will delete up to the next match of that pattern。 This is extremely useful。

 and I use it all the time。😊，うううん。One another need addition on the undo stuff that I find incredibly valuable in an everyday basis is that like one of the like builtin functionalities of Bm is that you can specify and undo directory and if you have a specified and undo directory by default beam like if you don't have this enabled whenever you enter a file like your undo history is it' like clean there's nothing in there。

 And as you make changes and then undo them you can create this history but as soon as you exit the file that's lost but as as you exit soon as you exit Bm that's lost however if you have like an undo there beamm is gonna persist all those changes into this directory So no matter how many of times you enter and leave that history is persisted and it's incredibly helpful because even like it can be very helpful for some files that you modify often because then you can keep the flow but its also sometimes's really helpful you modify your bus C and something broke like。

Five days later。 and then you beam again like， what actually did I change if you don't have。

 say like birth control， then you can just check the end and like oh， that's actually what happened。

 And last coming is also really what familiar yourself with ras。

 And what different special races beam uses。 So， for example。

 if you want to copy paste that's gone into a specific racer。 And if you want to， for example。

 use the o copy like the OSkboard， you should be copying or chunky like copying and pasting from a different racer。

 And there's a lot of them and yeah think that you should explore。

 there's a lot of things to know about ras。😊，The next question is asking about two factor authentication。

 and I'll just give a very quick answer to this one in the interest of time。

 So it's worth using two factor offth for anything security sensitive。

 So I use it for my Gitthub account and for my email and stuff like that。

 And there's a bunch of different types of two factor off from SMSbased two factor off where you get special like a number text it to you when you try to log and you have to type that number to other tools like universal two factor。

 This is like those UB keys that you plug into your computer and you have to tap it every time you log in So not all yeah John is holding a UB key。

Not all two factor off is created equal and you really want to be using something like U2F rather than SMMSbased2 factor off or something based on one- time passcodes that you have to type in。

 we don't have time to get into the details of why some methods are better than others。

 but at a high level use U2F and the internet has plenty of explanations for why other methods are not a great idea。

Last question， any comments on differences between web browsers？Yes。😊。

Differences between web browsers。 There are fewer and fewer differences between web browsers these days。

 At this point， almost all web browsers are。Chrome。

Either because you're using Chrome or because you're using a browser that's using the same browser engine as Chrome。

 it's a little bit sad， one might say。I think these days。

 whether you Chrome is a great browser for security reasons。

 if you want to have something that's more customizable or you don't want to be tied to Google。

 then use Firefox， don't use Safari。It's a worst version of Chrome。

 the new internet Explorer edge is pretty decent and also uses the same browserer engine as Chrome and is probably fine。

 although avoid it if you can because it has some like legacy modes you don't want to deal with。Yeah。

 I think that' there's a cool new browser called F that you can't use for anything useful yet。

 but they're actually writing their own browser engine and that's really neat。

 Firefox also has this project called Serervo which is they're re implementing their browser engine and rust in order to write it to be like super concurrent and what they've done is they've started to take modules from that version and port them over to Gecko or integrate them with gecko which is the main browser engine for Firefox just to get those speedups there as well and that's a neat thing you can be watching out for。

That is all the question。 Hey， we did it， ice。I guess thanks for taking the missing semester class and let's do it again next year。

哎い。😊。