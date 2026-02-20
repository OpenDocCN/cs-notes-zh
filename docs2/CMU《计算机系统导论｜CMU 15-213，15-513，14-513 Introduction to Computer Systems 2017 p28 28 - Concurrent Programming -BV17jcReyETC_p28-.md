# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p28 28 - Concurrent Programming -BV17jcReyETC_p28-

![](img/245fdbdecb5a98324d491cd7c87588ec_0.png)

なて。な个せ。

![](img/245fdbdecb5a98324d491cd7c87588ec_2.png)

That's actually super cool。や前ありこと。

![](img/245fdbdecb5a98324d491cd7c87588ec_4.png)

我想你发。

![](img/245fdbdecb5a98324d491cd7c87588ec_6.png)

Okay。So I hope you're making good progress on Maloc。I know for me。

 the first time I ever implemented a memory allocator， it was sort of an eye opener to thank that。

You can just write regular code and suddenly you're doing things that are。You thought some magical。

A mysterious part of the system was doing for you。 and you see that it's all。Not easy to do。

 but not conceptually straightforward。So today we're going to move on to what I think is one of the really interesting parts of this course。

Especially relevant in this era when we have。All these multi threaded processors that allow us to execute more full programs simultaneously and because。

So many。hichines are hooked up to real world devices that require some kind of asynchronous control that you can't predict when events will come in from a camera or a network。

or a mouse or some type of sensor， and so you have to as the processor has to just be ready to jump and handle any of these different events。

And one of the best ways to do that。And so that brings into the idea of concurrent programming。

 meaning having a computer that can do more than one thing at a time。

And this is actually a pretty tricky business， the many。

 many bugs out there in the real world have to do with concurrency errors。

And it's partly that there's a couple things behind it。

 one is that it's just really hard for we as humans to imagine all these different events that could occur and what order they might occur in and often you can anticipate you'll think well。

 I'm first going to read the camera and then I'm going to pick up this information and then do that。

 but instead the events happen in a different order and you're not really ready for that。

And it's even difficult to test out these things because it's hard to set up real world scenarios in which the event orderings vary over their full range of possibilities。

So this is an area where you just have to and there are tools that can help you。

 but at some level you just have to be much more careful about how you write your code。

 you can't just think I'm going to just throw some code down。Start running it。

 figure out where the bugs are， patch them up and then ship it。

 you really have to be much more meticulous in your design。

So there's some sort of terminology that there's some kind of interesting ways you can illustrate these。

 one is the idea of a race， so a race is basically anytime there's two different entities trying to use the same resource at the same time。

And if not handled properly， bad things can happen。So， but it's the idea of contention。

 there's two different events that can occur and they might occur and they're both contending for some resource。

In this case， a parking space。There's also a lot of these ideas。

 by the way you can illustrate with real world examples as we see the other is the idea of deadlock and the sort of traffic intersection gridlock is a perfect instance to that that you'll see that this intersection is blocked because。

Each。Let me see if I've got this， oh good。Each of these cars is in the middle of the intersection。

Is sort of preventing another car from getting through and there's you can see actually very clearly illustrated a circular dependency that one has a resource meaning this little piece of the intersection。

That this car needs。And so forth， that dependency， each one has a piece of the intersection that another car needs。

 and they can't go anywhere because they all have this sort of circular cycle of dependency。

And that's a classic deadlock situation。And so actually it's pretty interesting。

 you remember we harangu you that you can't use Paf in your signal hand wordss and we only were able to vaguely explain why。

But now that you have this idea of concurrency， actually， it's a perfect illustration of why。

And the reason is that。Within the printf code， and we'll get into this laterer in this。嗯。

Let's do next actually， I guess the idea of locks。 So lock is the way that you can。Sort of。

Grab a resource and say， I have exclusive control over this。

 No one else can get to it until I say so。 And so you acquire walk。

you can hold that as long as you want， you can do whatever you want then if now you have sort of exclusive use of whatever resource you're protecting with the lock and then when you're done you release it and that will allow somebody else to acquire meanwhile if 10 other programs are trying to acquire this lock。

 they'll just hang there and wait until that lock gets released and then they'll be a sort of free for all of which one gets the lock next but it's guaranteed that exactly one will get the lock the second time。

 you never have a case where two。Two programs can acquire a single walk。

So Pridf wraps locked around some parts of the code because it actually buried deep。

 deep inside in these obscure corners that have to do with time zone management。

It or not there's some shared resources， some shared global variables that if you had different。啊。

Instances invoking that could possibly mess each other up。

 and my understanding is it' sort of this library was created years ago。

When they weren't thinking about the need for sharing or concurrency。

 they put in this sort of unintentional shared resource。

 nobody's ever done the work to pull it out and make it truly safe。

We'll talk about how you can do that and so instead what they've done is just slap walks around the whole code so that when you call Prif or Sprintf or any of those related functions。

 it'll first acquire a lock。It'll then execute whatever this code is that has the shared resources and then it will release it。

And here's the problem with the interaction with signal handwis。

That imagine my main program is chugging along and it decides， oh， it's time for a printf。

And so it will acquire this lock。And start to do something。

 And imagine right after that lock gets acquired， a signal comes in。

And that signal calls this signal handware and because the signal handware has a printdf in it。

Pridf does， what Prif does， it tries to acquire a lock。

The problem is it can't get that lock because the lock belongs to the main program and this program can't release the lock until the signal handler exits and returns back to the main threat。

The main execution。And so it's a classic deadlock， although it doesn't involve four cars in an intersection。

 it's just。Executions。Even though they're actually all part of one process that are sort of waiting for each other。

The signal handler is waiting for the lock to be released by the main program。

 but the main program is waiting for the signal handler to return before it can release the lock。

And this is a relatively rare。Thing。And so 9。9% you'll see， and you might have done it。

You got ding style points if you did， you can throw a printf in a signal handler and it seems to work fine。



![](img/245fdbdecb5a98324d491cd7c87588ec_8.png)

Whoops。是。

![](img/245fdbdecb5a98324d491cd7c87588ec_10.png)

To do that。

![](img/245fdbdecb5a98324d491cd7c87588ec_12.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_13.png)

But just to be perverse， we sort of purposely wrote some code that would sort of slam as hard as it could on this particular feature and see what happens。

And so you'll see here's a classic case then that the。We're forking。

We're running through a little million times， and each time we're forking a child and the child exits immediately。

And of course， that will then cause the SG child signal to be delivered to the main program。

And then the main program has a PRf。And the parent has a sprintoff followed by Prif。And for reasons。

 I don't know。If you just make it solve a single printf， it doesn't seem to cause any problems。

 meaning I can't trigger this problem。And then you fire up this code and it will tugg along。And。

just whizz along but at some point it'll hang and in this instance it hung that somewhere close to 6000 and other times it' will hang。

 it'll be 50，000 in and you can see this is sort of the worst case scenario in terms of I'm just doing signal handle or signal handle or signal handr over and over again。

But it will hang it will I've never seen it again anywhere close to a million before it goes This code like all the code for a lectures is sitting in a class AFS director if you want to poke it yourself and try it。

 but I think you'll find it pretty reliably causes a dead walk so that's why that's the reason why you shouldn't put printf in a signal handle。

嗯。And。But it's an interesting interaction between the sort of model concurrency that's created by signals。

 which is a sort of bizarre。Thing where you。Min programs just executing Haway and then Kaboom。

 a signal gets delivered and a signal hand gets invoked， it's all part of a single process。

 this isn't multi threading。But it interacts with a feature that was added to printf。

To deal with multi thread， which is what most modern processors support。

Somebody some of the students made the observation actually， if every time you use printf。

If you block all signals， if you sort of wrap around printf。Just like we wrapped lock around it。

 if you block all signals。Before you call Pri。And then you restore the signal mask to what it was before。

 that actually will work。But you have to do it not just within the signal handlers。

 but every place in the code， because the problem isn't。Really， the signal handler the problem。

That's causing this。Really， in the first place is the main program。Make sense。

And then there's other sort of， so Delock is a classic and when it happens。

 obviously it's a really bad thing because the whole system or at least a good chunk of the system is unable to make any forward progress。

There's other ones that are more subtle， there's one that's often called starvation。

 and the idea is imagine we have a busy highway。With these long streams of cars going by。

And in this crosswalk， crossways， we have yellow cars and just by convention that they basically have a yield sign。

 so they have to wait until there's no traffic on the main highway。

And so they could wait forever if that green traffic just continues and the system isn't deadlocked。

 meaning progress is made， the green cars are going just fine。And it's not an instance of。

This of one car versus another， it's effectively the stream of green cars that's doing that。

 and you can get that you can imagine in a sort of process scheduling environment where there's two levels of priority。

And you could have the high priority things always winning out over the low priority。Back。

It used to be flying airlines。For a while， the pilots in the group。啊。

Flight attendants got to jump into the line in security ahead of regular people。

Which really was irritating。Because if you're waiting in line is you know。

 you don't want to wait any longer， so that's an instance that if there were an unbounded number of flight attendants。

 the rest of us could have been starved in the security line。So anyways。

 there's sort of these classic problems that arise， as I said。

 there's races that if you're not careful， you can sort of mess things up and we'll show examples of that not as。

as glamorous as crashing cars， but where your program is definitely not doing what you want。

 we saw a deadlock where the whole system freezes up or various forms of starvation are sometimes talking of fairness where due to some service can't be provided because something with higher priority keeps winning up。

And so this course is really just in this course it's just the beginning of a discussion about concurrency。

 there's other courses that spend a lot more time on it in particular if you take 214。

Spends a lot of time in concurrency and other courses on campus in various ways do a lot more in concurrent programming than we'll get into。

But it's a pretty important thing， it's sort of fundamental。So just as an example。

 you re in the network programming， you went through iterative。A server。

The iterative server does fine， meaning it， let's say client。

 make a connection and then run a session that involves sort of a cycle of sending messages back and forth。

Reading them。But there's a weakness in this server。

In that it really can only handle one client at a time， so for example。



![](img/245fdbdecb5a98324d491cd7c87588ec_15.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_16.png)

。I've got the server fired up on hammermerhead shark。And I can use it to echo things。Even misspelled。

And it works fine。But if any of you， if you guys have a laptop handy and want to jump to the。

Of course， the code for today， it's in Wed。In the。Do you know how to get to it。

The course AFS directory s Www s code s 23kPro。And if you type in this。Prompt echo client。

 you give the host is Hammerhead Shark and the port number is 15213。Give it a try， anyone trying it？

很文专业。But it'll be locked out because've got the I've got so access to the server the server the server as the weakness that' only able to do a single client at a time and as long as I'm。

Maintaining my connection to it， I'll dominate it， but now if I exit with a control D。Somebody else。

From Kaiser Pannceer。Was able to get in and is starting to do the echo， who's that？Okay。

And now a few can a control D。No one elses trying。Where is your sense of adventure。There you go。

Kisser Puner， it's back。Anyways， you get the idea that this isn't a very good server if you were Google and you had a million customers。

But you could only do one other time。

![](img/245fdbdecb5a98324d491cd7c87588ec_18.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_19.png)

So let's make sure we understand why it's really only able to do that。



![](img/245fdbdecb5a98324d491cd7c87588ec_21.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_22.png)

嗯。And so the way this， well diagram is-，- and this is a common way to show protocols involving concurrency networks and things like that is time is going down。

And each vertical bar represents one thread of execution， one process， think of it。

And so if you call the overall idea is that there's a server that's sitting there running in listen mode。

A clientient makes a connection request。And then the server accepts that。

And then the client is able to start echoing by writing。

To the server and reading back what it returns。And it can keep doing that right read as long as it wants。

 and then it causess the connection when I hit control D。

 it causess the connection and that was that。So meanwhile。

 if another client comes in like Kaiser Poer did and wants to make a connection。

 they can connect to it。And interestingly enough， and it's a little bit subtle。

 the call to Connect actually returns， even though there's no connection yet。A little weird。

 but that's the way it is， I'll explain it in the middle， but then when it starts to write。

 try to write， that call will hang up because there's nothing to write to。

 there's no actual connection yeah。And so it will basically get stuck there in that part of the code。

Untiltel this other connection is closed and the server is able to now accept another connection。

I'm pointing to the screen that you cant see。But anyways。

 it sort of sits there and just hangs for as long as that other connection exists。And。Like I said。

 the slightly subtle part is the client code makes it called a socket。

 which just sets up the data structures for a connection and makes a call to connect to a server。

 that actually returns， and then it's this call that blocks。

And it's a feature of a slightly subtle feature of。TCP。

 the network protocol that it will return from connect even though it doesn't have a connection。

Aly as a way to sort of。Speed up once the connection is formed， then more quickly moving on。

But whatever that particular feature isn't really important here。

 it's just a little thing you might notice。But the point is that the second client is boughted。

 it can't do anything as long as the first client is connected。And so that's a fl。

So this is clearly a case of a concurrency， we need a concurrent server。

 one that is able to manage multiple connections at a time。

 and we'll discuss in detail two different ways of doing this and sort of give you a little overview of a third way。

So the first way is to simply use the。The machinery you've already learned about processes and forks。

 and basically fork off a new process for every connection。And that's like I said。

 you can understand that exactly using just the ideas of work that you know already There's a second type called an event base that we won't talk in much detail it's covered in the book it's pretty interesting I'll just sketch through it and then there's a third which is really where we want to get to today which is threads and you've heard this term threads we keep mentioning threads over and over again finally today we're going to start talking about what threads really are。

So the simplest then this process one that basically the server。When it gets a connection request。

Will accept that connection， but rather than handling the echoing itself。

 it will fork off a child that then manages that particular connection。

And the echoing will go back and forth this way。And meanwhile。

 the server will be able to continue looping around and accepting new connections。

And so if a second client comes in again， it will fork a second child to manage that connection。

 so the main。ATh of control here of the server is only a loop to accept connections and to fork off essentially a handler that can deal with whatever that connection needs。

So doing this is there's a small few little subtleties in doing this correct that let's go through。

So this is the code that was presented last week of the iterative E server。

 the one that we just demo。And so again， this is the server， so the loop here is that it's。

Accepting a connection。And then it's managing that connection， the reading and writing。

 and then it's closing that connection。Well， we've got to move things around a little。

 but what we'll basically do is put the echo part。Into a child， so we'll call fork。And。

When the side that returns zero， of course， is the child。

 and that will be responsible for both the echoing and then once the connection is done to close that file descriptor。

And this actually makes use of a feature of。Of the accept。

That it lets you deal with different file descriptors， essentially different ways of connecting。

So the listen file descriptor is the file descriptor that's accepting new connection requests。

And when accept returns， it generates a new file descriptor that is the actual the specific connection that's been created for this particular client。

 and by having those different， then we're able to do this trick of now I can just run except on that same listen file descriptor。

And use， I'll generate a new connection file to scriptor for every time I return from accept。

There's a few subtleties about closing file descriptors， closing files。

 because remember when a fork occurs。Both the child and the parent have copies of the same file all the open file descriptors are duplicated between those two processes。

And so it's very important that the main program close the connection file toscriptor。Otherwise。

 if it doesn't， you think about what it's going to do is generate a bunch of orphan or unclosed files that will actually grow unbounded。

 which is not good。It a server。So if it doesn't actually actively close that file toscriptor。

Then remember， files only really get closed when the reference accountss get set to zero and that will never occur for any of the connections that are created until the program exits the server。

 but remember， server in principle should be designed that can run forever without abusing or overusing any resources。

So that one's pretty important。Similarly， the child has to close the listen file descriptor。

Just for the same reason， it's a little less critical because we've designed our children to only manage one client's worth of echoing。

 which presumably won't go on forever。So it's a little less fatal。

 but still you can imagine there's no inherent bound on how long the client stays active。

 and so that wouldn't be a good thing but it wouldn't be as bad as the other one。

 but in any case the right thing to do is to close the file toscriptors that aren't going to be used by this particular process。

So that's one of the tricky things again。As I mentioned in concurrent programming。

 you often have to be just。Srupulously careful and not rely on just running code and seeing if it crashes because it's really unless you ran this for a really long time。

 I mean， usually I think most processes can support  a thousand or more open files。

The likelihood of you encountering this intestine is fairly small。

And then just to really do this right， we should avoid zombie children as well。

And so we have to create a Sig child handler that's the type of views that we call weight pit and be able to reap all the children and again。

 this is an instance where this is pretty important because the server is。

Could run forever and And therefore， if it doesn't do this active reaping of its children。

 it can have an unbounded number of zombie children。 So again。Concepttuly， this is straightforward。

 but actually there's some subtle points in implementing this kind of code that you have to be careful about。

So just as a sort of picture， remember this important distinction between these two file descriptors。

I make a connection request the client does to the WIS and on the server side that client request comes in to the socket that corresponds the listen of FD that was created and passed to the accept。

靠。But then accept returns a second connection file descriptor for this process that then becomes sort of owned。

 so to speak by the child that I forked off， and then they sort of the server and the client then have a session where they can go back and forth reads and writes to。

To send messages back and forth。So the overall model then is I have this pink box represents the sort of main。

ASver that's just in this loop creating new connections over and over again。

 and that I'm each time I get a new client， I'm forking off a new process and letting that run。

So in this instance， this is a perfectly fine implementation。There's a few things， though。

 that make it not ideal。 One is there's a significant cost and overhead of fork and processes that。

If you did a lot of this and it wasn't just echo servers， but something more serious。

Both time and resources， but more serious way is。If you want to do any kind of interesting application。

 like more than echoing。It's very difficult to share information between processes。

There's no sort of common state to them as you know， part of their trick is that they。

At least conceptually duplicate and create sort of completely independent state。

And so if you wanted to like have a database that。Of customers you know that all these servers or manager or any kind of shared information。

It's not easy to implement using processes， you can do it。

 but it's not easy and it's not very pleasant。And then as I mentioned。

 there's these slightly subtle points about this sort of shared file descriptors。

But the biggest problem is it's really a pretty limited。Model of what you can do with this model。

So anyways， just some pros and cons。It's a very relatively simple sharing model。

There's some subtleties， but relatively speaking pretty easy。嗯。But as I mentioned。

 it's not very rich in terms of possibilities。So then there's a second apart and we're not going to really talk about it much。

 but those of you who do。Network programming will want to learn this。 There's this whole set of of。

library code that lets you manage what they call。嗯。Mage events on sockets。

 and there's a class of functions that are called select to do that。And。So roughly。

 and the idea is that this isn't actually concurrent programming at all。What it is is it's a way to。

The problem I have is if I were to just try to do this all on my own using file descriptors。

 and every time I made an exception a connection request，I could accept it。

 I could create a new connection file descriptor。 I could put it in an array。

 have as many connection file descriptors as I had clients。 that's fine。

 But then you're sitting there going。Okay， now what do I do， Should I listen and for a new request。

 Should I see if one of my clients has some messages that they want to be sending me， If so。

 Which one， How do I know， Well， the idea of I multipleing is。

Basically that you can create this array of of all the file descriptors that you're maintaining and then there's a you set of mask to say。

 I want to see if there's any traffic， any incoming。Information on any of these connections。

 any of these file descriptors。And if so， tell me which ones are there， and so you can go kachinnk。

Run this up。Function called select。And select will， if there's no incoming。

Input on any of these file descriptors。え我へ。But。If there's one or more， it will give back。

A mask saying which file descriptors have data that you can read And so this works for all file descriptors。

 the file descriptors corresponding to network sockets， which are network traffic。

 including the listening file descriptor and any client file descriptors you've created。

 but it will also be for terminal IO for。For reads that you're making of。Of regular files。

 So actually， there's quite a few possibilities。 And then your program can then just pick through this array。

And say， oh， okay， there's a new connection request。 Let me accept that， and I'll stash the。

Create a new connection file toscriptor somewhere in this array and you say oh。

 there's input from this client here， and so I'll read that and echo it back and oh there's input from these other two as well so it's just it actually is all purely sequential code。

And in some ways， easier to think about， but it just does this trick that is sort of integrated into the whole file management system in socket management that says。

 at any given time I can sort of query and ask which among this set of file descriptors has input available。

So it's a nice。Simple model and relatively easy to work with and debug。And so that's good。

It turns out that there's some weaknesses， you'll find， for example。

 if if one if I did this in this case and there's code in the book that does it。

 but it has this sort of a security weakness that if one of the。嗯。Clients。呃。

Pass is in a string that doesn't have a end of character。The server will hang up on that line。

Because it， it's an echo， it's not echoing character by character， it's doing line by line echoing。

And so it will just hang indefinitely。You knowNice clients don't do that， but in the world。

 as you know， there's many bad actors out there and so increasingly people write code that is not making any assumptions about the reasonableness of clients and so to actually then do you'd have to change the code and your echo client to do by one know basically character by character echoing or something like that。

To deal with it。 And this is a problem with servers that are implemented this way that。嗯。

They can be vulnerable if you don't sort of handle all the possible behaviors of clients。

And the other is， in this modern era， most processors have multiple cores。And this code is running。

 it's totally single threaded， and so it's not taking advantage of。

There's computing resources it could have。He big。Okay， let's jump into a quiz。反正个确。

This is a short one。自己。Okay， I think we're good here and I thank you guys。

Most we got the right answer。Yeah， we just saw a starvation remember the car is on the highway。

 and so the point is in starvation， something is making progress， but others are not。And then Malck。

This is very important that。Your fit algorithm and all your segregated lists are really mostly going to focus on external utilization。

And to get a good score in this， you also have to deal with internal fragmentation。啊， good。Okay。

 so now you've seen the lead up of。Let's talk about what I kept promising we talk about。

 which is threats。

![](img/245fdbdecb5a98324d491cd7c87588ec_24.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_25.png)

So this is an interesting way of thinking about it that we've sort of talked about。

When we talk about。嗯。Program so far， we sort of say there's this whole bunch of stuff that's in memory。

And that includes shared libraries， global data， the heAP。

 but we also say that the stack is sitting there in memory。

And so that's sort of the data associated with the program。And then there's the other part here。

 which is。Sort of what defines this particular process。

 there's all the registers including condition codes， stack pointers， program counter。

 and then all the various data structures that are maintained for you by the operating system kernel and as we saw before。

 those are kind of mapped into the same address space but up and regions of the address space that。

That you don't have access to。But what we're going to do now is sort of rearrange that picture a little bit。

Through the magic of PowerPoint。And say， let's think about the stack as really part of the runtime control for this program。

 because the stack is also the history of。Of outstanding function calls and all the data on this stack are pretty important that this sort of defines where within the program。

The execution is taking place and what to do as the procedures return。

And then we'll just sort of push all that， remember that all this kernel stuff is in virtual memory and in some ways it's just there being managed for you by the kernel and so you don't have to think about it too much。

And let's call that first part the threat， the in this case， a single thread。

 the combination of basically the registers plus the stack。And now with multi threading， the idea is。

 okay， if you have one thread， why not two， if you have two， why not three。

 Why not have a bunch of these threads。 And the key idea here is each thread has its own execution information。

But at sharing。The sort of more global information， it's sharing the code。Just like we saw with。

 but it's true sharing， it's not creating a replicas that then go off and diverge。

 it's actually keeping all these threads having access to the same global information。

 including the heAP and including the global variables。So the stacks are private。

But and we'll have copies of the registers， but they' so it lets us now run within a single- this is officially still considered a single process。

 but there can be multiple threads of control each relatively each doing their own thing。

And we saw with processes that there's this sort of hierarchy， a tree structure。

 the way forks and childs work， as parents， and so it forms this tree， threading。

 at least the model of threading that we use are sometimes referred to as peer threading。

Meaning all threads， even though there'll be a main thread and it will create new threads。嗯。

And those threads can create other threads， but at some level they're not one is no more sort of special than the other。

 There's no notion of this hierarchy and so forth。 So all these threads sort to have equal priority and access and privileges。

🤧嗯。And once again， we'll talk about this idea of concurrency。呃。

We'll just say if two threads sort of have overlapping executions。

 then they're considered concurrent。And well， actually now if we only had single core processors。

 then we'd have to just basically emulate this concurrency。

 meaning that we'd just jump from one thread to another。

Sort of make it appear that they're all being executed， even though at any given time only1 is。

But nowadays on a multicore processor， you have the possibility of truly running on separate cores within the same chip。

 these different threads， they'll each have their own registers， they'll be accessing the data。

It's all mapped into virtual memory。 It's all one system with its own set of。

OfPage tables and resources and things all managed by the colonel。But they all are。

So they're sharing that the sort of virtual address space， but they're each executing their own。

 and they'll have their own stacks and the stacks are actually still part of the virtual address space of this process。

 but they're just instead of having a single stack and one part of virtual memory。

 we'll have as many stacks as we need。And we know that stacks are bounded。

 We always ca how big a stack can grow so we can just allocate。

Think typically about five megabytes each for each of the runtime stacks we want to have。

So you see the distinction then between what we saw with processes via fork。Versus threats。

That in some ways they have some similarities， it creates multiple threads。Of control。

Sort of execution， logical flows。Running concurrently and the processor and operating system have to somehow manage。

The schedule of those。But they're different in that。The the sharing is true here。

 as opposed to sort of remember we saw with。Processes that we at least give the image that we're replicating。

 we're making independent copies of the whole address space。In general threads。

 the overhead of scheduling them and managing them is less than a process and you can see why when I create a new process I have to set up all the VM areastructs I have to sort of mark all these page tables entries as being。

呃。Set up with。So that they'll be replicated if I try to do multiple rights to them and all that stuff。

 whereas here， all that junk is taken care of all I have to do to create a new thread is set up a stack。

Little small amount of data structure and then I can start running it。

So the main way we make use of threads in every language。

 there's many different ways to do threading and some languages like Java， Python。

 so on and so forth， most modern languages have a built in threading capability。C doesn't。嗯。

In order to C++ and so instead there's this external library called P threadreads， Pstand for Posss。

 which is sort of a basically back when there were multiple variations on Uniix all being created by various different companies and organizations。

 they all gang together and say， hey guys， let's come up with a sort of universal set of。

Minimum standards called Poss， and we'll all guarantee we support at least that aspect of UniX。

So anyways， P threads and P threads is this giant library， 60 functions， inscrutable。Arguments。

 man pages， gore， all the usual stuff。But the basics of it are actually not so difficult。

So this will be just to give you the starting point， and like in a lot of places， any library。

 you start with Hello world， and it's like the ugliest code you can ever imagine because you're trying to do something very simple with a library that for which this is sort of has a lot of machinery that we won't really use。

But the basic idea of it， what I'm trying to do with this code is create a new thread。

Whose only job will be to print Hello world？And then exit。

So I'm actually going my main is going to spawn a thread。That thread's going to print hello world。

That thread will then terminate。And then the main program will figure out that the child is this。

Not child， this other thread is terminated and then it will exit。

And so basically I will create this P thread create is the function that sps a new thread。

And P thread joined。Is sort of the weight？The weight pit of the P thread world。

 it waits until a specified thread has exited， and then it continues on。

So there's a few things going on in P threadread， you pass the first argument is a pointer that then gets filled in by the library with the ID of the particular thread that was created and thread IDs or like process IDs。

Theyre unique numbers to identify。There's many arguments you can pass to a lot of these functions that you can just set to null if you don't really care。

 there's some special attributes you can assign the thing that's the most important the two things that are the most important is what you do is basically pass a pointer to a function。

 so it's a little like a signal handler。IThat you pass it。あ。

Except that we're not waiting until the signal happens here。

 we're just right away going to fire up this new thread， but this becomes the thread routine。And。

And then you can pass in up an argument。That then becomes the argument of this thread routine。

So in general， the thread routine band。Will be a。A program that is given a single void star as a pointer。

And that will be whatever was passed to it in the C。

And that void star then you can cast to whatever you want and extract out of it。

 you can pass a pointer to an array， can pass a pointer to a struct whatever you want。

 and then that can be sort of deciphered by the thread function so passing around void stars as you know the way and see is the way of sort of creating generic arguments it's not very。

Elegant， but it gets the job done。TheC's version of polymorphism， you might say。

And then the P threadd joined。When it。呃。Well we'll pick up。

 you'll see that the thread gets to return a void star and P threadread join then can get a copy of that if it chooses。

So the point here though， in this particular example is I called P thread that created a new thread。

嗯。And Pete thread create returns right away as soon as this new thread is created。

And then the main thread called P thread join。 and then it just would sit and wait until。

That particular thread terminated。And then the newly created thread calls Prif and returns。

 and then when it returns， it gets essentially reaped although it's not the right term for threads and the join will return。

So that's sort of the simple version of a P thread program。Okay， well。

 why don't we try something a little more classy than that？And this is the code。

And it's got some really interesting parts to it， interesting if you're a nerd， which I am。

 so that works。What I want to do is you remember that I want to。

I'm going to want to create a thread for every new client that contains enough information to it to be able to do an echo back and forth。

 which is actually if you think about it， all it really needs is the connection file descript。

Because remember， threads by definition， share all the file descriptors because that's part of the global data。

But here's the interesting thing and we'll see this that I'm going to call Malek。Here。

And you'll see there's no free in this code。 So somewhere we better look and say thered better be a free somewhere。

 and we'll check that out。 So I'm going to mallic a copy of an ins worth of storage。

 which might seem kind of silly， and I'm going to store in that place。

The connection file to scriptor。Returned by accept。

 and so you notice I call it con FDP for pointer instead of just con FD。So conFDP， its data type is。

Here， it's a pointer to an int， not just an int。Okay。

 and so and then that's the argument I'll pass to thread the thread routine。

 remember the thread gets a void star pointed to and I'll just pass this particular the pointer to this so basically I've created this little block of storage。

That ConFTP points to。In which the actual connection F， the file descriptor will be。

If you can read that， good for you。嗯。And then I'll pass that pointer then and the thread will have access to that little block of storage and we'll find out very soon why I did it that way and not some more straightforward way。

And here's the thread routine。So here you see it's able to then extract out of that block。

 it can dereference that pointer。Cass it to an instar D references it and gets out of it the connection file descriptor。

嗯。And。You can see down here it's going to use our standard echo and clothes on that to manage that client。

 but it's also going to do a few other things one is it calls a function called detach。

And there's two different thread types that are supported by P threads called joinable and detached。

So join aable is what I showed for Hello World。The the concept of it is that a thread will be created。

 and then somebody is going to wait until that thread is finished before proceeding。 It'll join。

A detached thread is more like one where there's something that will happen， I don't care。

 I don't even care when it finishes， it can run forever as far as I'm concerned。

 so just detach it and let it do its own thing and never bother me about it again。

So P thread supports either model。So I told it is a detached thread here。

And then here's the call it free。So you can think of this as sometimes referred to as a producer consumer model that。

Server allocated the amalek。The w four bytes worth of storage need to store this file descriptor。

Pasted a pointer to it to the thread。 The thread consumes it。And then says。

 don't need it anymore and can call free。Milk should always be balanced by free。

 Usually you put the free and the same kind of。Whoever created it should free it。

 but in this case it's a producer consumer。And lets let's see a little bit why we did what seems like this very awkward thing as far as passing an argument。

But first of all， you can see the overall model here is very similar to the process based one that now our server is just going to。

 every time it gets a new， it will just be in a loop accepting new connections。

And every time it gets one， it will will spawn a new thread。

 and that thread will be responsible for that client。 And then when they're done。

 that thread will just exit and nobody cares。 We will pay attention to it。

so it's a little like the process except we didn't do any weight， question。Totuch。

A detached thread is still a thread。 It' still， we don't use it here。

 but it's running in the same address space as the original， you know， a fork。It也。

Conceptually makes a copy of all the memory and now is the two the parent and the child make updates to global variables。

Those will be independent， but within a thread。If there's global variables。

 will that will all be the same， so it's the difference between a thread and a process。Yes。

started all。家你。Actually， it's an interesting question if any thread。

The main thread or any thread calls exit。Then the whole thing goes kong。And they're all done。

But if a thread returns or it calls P thread underscore exit。Only it will。

 Only that thread will terminate。So。呃。I believe that the main program， though， yes。

 if you return from Maine， it will return back up to a function that we'll call exit。

So it's the main program。Either calls exit or。Hs the end of it and does a return。

 then the whole thing's over。But if it runs。Forever， like a server would。

 then there's nothing going on。啊。No no， think of processes as like a pretty strong firewall around them。

There are ways you can create pipes between network connections essentially。

Various ways you can set up communication between processes， but it's not a normal thing。

But whereas within a process， the multiple threads by default。

Are able to talk interact with each other in all kinds of ways。跟。So yeah。

 it's the difference in processes sharing as hard is possible， but hard。With threads。

 sharing is so easy that you can have a lot of bugs because things tromp on each other in ways you don't want。

Which way do you want， it depends on the context。Good。😊，So like I said。

 there's this difference between。Joinable or detached threads， if you don't call detached。

 then you've got to join it or you'll have the equivalent of zombie children except their zombie threads。

But if you detach them， then。Then the creating thread。

 the main thread doesn't have to worry about them ever that once they exit or once they return or call P thread underscore exit。

The system will essentially reap them。Okay， so now let's talk about why I went through that。Sort of。

Riggamer all about mallaching in one place and freeing in another and passing a pointer and blah。

 blah， blah。嗯。Why to do that Well， let's imagine we did the more obvious thing。

Which is we just have a local variable called the conFD。And we pass a pointer to that。To the threat。

And then the thread can happilyp away， it's a perfectly good pointer。

 it can dereference that pointer and extract the connection file descriptor out of it。

But if you think about it， what that means is this local variable。Will be on the thread。

 on the stack， excuse me， of the main threat。And we'll talk about this next time。

 There's actually one of the weird things about threads is it's perfectly legal to have。

References between threads， between the stacks of different threads， it's possible and it happens。

 so that's not inherently a bad thing。The problem is。That。Let's just assume that this connection FD。

Is it the same location in the main stack throughout the life of this while loop？

The problem is if I then create a second thread。Then I've set up a race condition。嗯。Because。

I'm hoping that the first thread will read out of this pointer。

The connection file descriptor that it's supposed to use before。

My call to accept returns and overwrites that same local variable with a new connection file descriptionscript。

Makes sense。So the problem is that really this， you think of it。

 this memory location within the main stack is a shared resource and Ive created a race condition。

That I'm trying to assign a value to it， have it get read by a newly created thread。

Then possibly assign another value to have that read by a second thread and happen。

 and it's purely a question of which one wins if this child fires up really quickly and sucks it out that I'm fine。

 but if for some reason，The operating system decided to respond to this except。

More quickly than the child can get created。Then I could possibly。Overrider。So just to demo it。

 you'd have to work pretty hard to create that particular race in this code。

But just to show you it the same idea。Is some sort of very simplified code that does basically the same thing。

What it does is it creates 100 threads。passings。The same pointer to each one of them。

Because it's a pointer to this local variable I in its own stack。

And so I'm doing the exact same thing， except I'm doing this without any network stuff going on。

 I'm just going to fire up 100 threads。In a row， as fast as I can。But if you see it。

 I'm really passing the same thing to each of these。

 I'm passing a pointer to some place in the stack， and it's the same pointer every time。

 but I'm assigning different values to the variable that's stored in that stack position。

And then meanwhile， the thread will extract。嗯。This integer I。

And it will save it in some place that I can basically build up a collection of all the different values of I that were passed to one of the 10 different threads。

So if there were no races。Then each thread I'd get value0 through 99 for the 100 different threads。

But what can happen if this goes too quickly？Then I can have， basically multiple threads。

 will'll see the same version of I going on。So this code again is on the web page。

 and so what you'd get then， this is sort of like a histogrammar for each possible value of I。All 99。

 how many instances of those get get observed by one of the threats。 And so if there are no race。嗯。

It be exactly one。Even running on a single core laptop。

 which you might have trouble finding one nowadays， so this I did a while ago。

You see that the race still occurs。 There's a couple times when basically the。

Gets around this group twice before the threads have a chance to respond。

 and so there's a few cases where I'm seeing that like no one gets value zero。

 but two of them get value1 and so forth。If you run it on a multiC server。Excuse me。

 it gets even worse。That you can see that in this example。

 there are actually 12 different threads that got Val 90 out of this routine。Yes。

 are you to avoid the？So that's an interesting question， so let's think about that。

So what's it about mal that makes this so special？Here you see that。So this is the same idea。

 I'm going back to the original code， not in this example。That I'm mallocing an int。

And then I'm storing my。My file descriptor in that。Met location and passing a pointer to it。

So and Mount， by the way， is thread safefe， so it has locks built into it so that multiple threads can cause。

So it's gold。And so you can think of it， each of these calls to Mal is creating a new and unique。

Place in the heatap。For this。 And so each of the time I call this。

 I'm actually passing different pointers here， right？

And so I'm basically creating these isolated spaces for all these different ones。

And then within the thread， it can say， okay， I've got it。and call free。

 and that storage can be reclaimed now and potentially go back and get reallocated again。

 but only after I'm absolutely certain I'm done using it， right？

So I'm being very careful it's sort of like this hand shaking， I'm saying， okay， here it is。

 I got it。So it's setting up that kind of execution model where， like I say。

 a producer consumer model where it's very carefully managing these and making sure it doesn't have the race that makes sense。

So that's just a little， you know， usually we discourage people from mallocing int's worth of storage。

 but this is a case where it's the right thing to do。More typically too。

 what you're passing is a set of arguments。And so usually what you'll do is you'll define that。

It's some type ofstruct。And you fill it up。You'll mal space for that struct。

 you'll pass it to the thread creation。 The thread routine will then。

Cast that to whatever struck pointer type it is， and then extract the various arguments so that's a more typical model of how you use this。

 yes。You couldn't just free outside。Well， you mean the main routine free？Yeah， see。

 but then there's the race right here。If I tried to free like here。

How can I be sure that but I've basically consumed。

 that's why you want to think it as producer consumer right that only after the consumer is sure it's done。

 then it can basically say， okay， all set。And you know， you're not really communicating。

 you're basically just making calls to Mel and free to do this， but that's the idea of it。Good。😊。

Yeah， these are very important to Roy understand， so these are good questions。Okay。

 so we now have a pretty good idea of what threads look like。

 we'll go in more next time and the time after that and look at how you really do synchronization。

 this example is pretty limited。But we can see already that there's some very specific things we need to do。

So one is， as I mentioned， threading。Sort of sharing is the default and it's hard not to share and that can actually get awkward。

 there's no way you can look at threaded code， some global variable and threaded code and know basically do I have to protect this with some kind of lock to be careful or not it can be very awkward。

And it's also difficult we'll see to actually test this code and run it because the thread scheduler you'll find that the Linux thread schedule is not too clever or it tends to be very repetitive。

 like it'll always give the child priority over the。Original or something like that。

 You can run program a thousand times， and it seems to just。Give you the right result。 But it's。

 it's because it didn't really try out all the possible event order。 So you saw that example with。

Where I could induce this sort of races， but I had to write code that would really bang as hard as it could at that particular feature to make that happen if I'd written a more normal like echo server without using the malic。

 I probably could have gotten away with it， except maybe one out of a million times all of a sudden it would have a problem and one out of a millions。

 really not good enough in this world。So we'll talk more about some of those issues next。Okay。

 so I guess the main point you can see where we're heading for is process based concurrency is pretty limited and not that useful。

Event based， as I said， is is actually。嗯。It says it's bad， actually from a programming point of view。

It's actually a pretty easy model， like we'll find GDP is not your friend with threads。

All of a sudden， you're going to start using Pds again。Because I mean， there are support in GDP。

 but it's really， you know， basically when you say break here， it's going to say， well。

 which thread do you want me to break， right， so it's pretty awkward there。Whereas this event based。

 which I like if you take the networking class， you'll get into this。It's all within a single loop。

 and basically it's like a little scheduler built into the code that you have much more control over。

So anyways， that'll get us for today。

![](img/245fdbdecb5a98324d491cd7c87588ec_27.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_28.png)

![](img/245fdbdecb5a98324d491cd7c87588ec_29.png)

我们去。