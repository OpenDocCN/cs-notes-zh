# CMU《并行计算机架构与编程｜CMU 15-418 Parallel Computer Architecture and Programming sp18》 - P20：Lecture 20 - 3-2-18 - Carnegie Mellon University.zh_en - GPT中英字幕课程资源 - BV18b421J7cA

All right， so I want to run through a couple of things today。

It's gonna be a little bit of a busy day just because there's a bunch stuff that we want to cover。

 I'm gonna run through MPI really quickly。 Turns out MPI is pretty straightforward。 There's。

 there's not a lot of reason doing extensive on that。

 And then I want to back up and run through some more optimization examples。嗯。So let's do it。嗯。

So MPI is message passing interface。 So MPI was designed。As an interface sort of。

 for supercomput to allow problem solving by communication。

 It's very different than a shared memory model， right。In shared memory。

 you assume that the processors can communicate through shared memory。

 whether it has uniform access or non uniform access。

If we're dealing with different computers or situations where the p nuumma memory is really expensive to get from one side to another。

 It's something that we don't neglect。 We oftentimes communicate by message pass。We pass a message。

 We do a large amount of work。 We hand results back。

And so NI is basically a standard interface for doing exactly that。嗯。

And so I'm gonna skip through a bunch of the stuff we've already talked through in this tutorial and just note the obvious。

 right， message passing。Is an asynchronous type of thing， right。

 The sender sends a message to the receiver。 The receiver cues that message。Right。Now。

 we have a choice about what happens next。Option A is as the sender。

 we wait for the receiver to receive that message， to process it。

 to generate some type of reaction to it and to send us a reply。Option2 is we send it and forget it。

We send that message。 We go back， doing do the other types of things we're doing。

 and we periodically check for a reply if we care。Right。

You can mail someone a letter and stand by the mailbox。Each day。Right， waiting。

For it to show up versus reply to show up。 or right。You can send them a letter。

 and then every morning， go check your mail。And do whatever you want to do during the rest of the day。

 makes sense。And so MPI works both ways。 You have blocking sends and receivers where you block。

 waiting for the recipient to get it or block waiting until someone sends you something。

And non blocklocking versions。Will you send it？And then you go about what you were doing。

 allowing you to overlap computation and messaging。MPI itself。Is an interface。It's not a library。

Okay， the MPI interface is a specification is implemented by a whole bunch of different libraries on different systems。

So我。Yeah， mean so I guess that's what it。 It specifies basically what the communication is like。

 It doesn't specify how you implement that。MPI is commonly used in C And C plus plus。 In some cases。

 it's actually used a lot in Fortran。 I think Fortran is slowly dying， but I do mean slowly。嗯。

A minimal but sort of useless MPI program initializes the MP libraries and closes things down。

Don't expect a significant performance gain from this particular implication。However。

 what I can promise you about it。😡，Is it will give you as much instant gratification as the first time you ran Hello world。

You'll say， yes， MPI works。And now what？Okay。Arr handling， basically。

 if you're doing it in C or fortran or something like that。

 it's going to return error codes like C and Fortran commonly do。 if you're working in C plus plus。

 you're gonna to get exceptions。嗯。There is no standardized environment for running MPI programs。

 right， just the same as there's no standardized environment for running C programs or C plus plus programs。

 right？ That's not a function of an interface or a library or anything like that。

That's a function of the， the runtime environment。There are recommendations that if you're running an MPI program。

 the command be called MPI exec。And then you say MP I exec in the name of the program that way that invokes the runtime that can deal with all the threads and all the in initialize the communication。

 that type of stuff。 But that's just a recommendation。Not all MPI systems have to work that way。嗯。

2 really important things in MP or MP comm size in MPI comm rank。

So a communicator is basically a group of。Of MP parts。That are that are together。

 size tells you how many you in that group。And rank tells you your number with Ne group。Okay。

So that's just sort of like a P I D， except to the fact that it's an I D within a group。

Groups can overlap。So here's a slightly better version of the low world。 At least we learn something。

嗯。We learned how many are inside the default group， and we learn how rank。Initially， when， you know。

 when you， when you initialize MP， you're part of that MP comp world。Okay。

 unless you join a different communicator， that's where you are。

 That's just the default communicator。Okay。嗯。You know。

 we know the classic problems with senders and receivers， Right， I mean， a sender wants to send data。

 A receiver may not be ready。 A receivers waiting for some for something。

 The sender may not have sent it yet。嗯。There are bursts when senders send a lot of data and receivers aren't quite ready for it yet。

There are times when receivers are sort of bored， and senders aren't ready to send data yet。

Buffering comes in between to allow us to hold on to those bursts。

 to train them when the receiver is ready。Blocking communication。You know。

So non block communication sort of allows that to happen where you spend something and go after business。

But if you're actually doing synchronous communication， Would you send something in wait。

 You're actually waiting for that to be written processed。That。

 like any other type of synchronization， right， serializes things that otherwise could be parallel。

And when you sortize things that otherwise could be parallel， you're getting less parallelism， right。

So performance is going to suffer significantly for that。Processes are collected into groups。

 Each message sent to the context must be received in the same context。

 A group in a context together form this thing called a communicator。

A process identified by its rank in the communicator。

 there's a default communicator whose group contains all initial processes called MPI Com World。Okay。

Because， yeah。So basically， what， what there is is there's the membership in the group。

And then there's the ability to communicate within the group。Nominally。

 those are two separate things。But a communicator captures both the context and the ability to communicate。

Does that make sense。Okay， so because MPI is designed to work in a heterogeneous environment。

 it has its own data types。Okay， MPI in， MPI double precision and so on。 by using the MPI data types。

 We're in a situation where A， we can work freely across different types of systems。 B。

 we know exactly how big things are。Right， a classic problem in C is that if you say int。

 people wonder how big an int。Right。This sort of resolves this by standardizing all the data types。

 the representations and the sizes。Okay， MPI tags were once used fairly heavily。

 Some people call MP tags message types。With the idea that when you're sending messages。

 you can tag them with what type of messages they are。

 And then the receiver can make a decision about what to do with them based upon what type of message it is。

It allows sort of an internal organization of。Of message types。嗯。Tags， I mean， you can still use。

 you， you can still use them。 They still function for that purpose。

 I wouldn't say they're particularly heavily heavily used。嗯。Okay。The basic MPI send is an MP send。

 An MP send is blocked。嗯嗯。The start of the buffer， how many things are in the buffer， the data type。

The data type also comes with it how big the data type is， right。

 If we know exactly what data type it is， we know how big it is。

 If we know how big it is and how many we have， we know the size of our buffer。So we have the start。

 we have the size。Destination is where it's going to。 The tag， like I said。

 is you can use that as a message type or just set that to 0。

And then the communicator is the channel on which you're sending it， which group you want to reach。

Okay， so that's a destination via that communicator。Receive does what you'd expected to do。 Start。

 count data type， where it's coming from。 the tag of one was sent， the communicator。

 and then a status that may contain some further information about that。Receive is also blocking。

 If there's not data that's already in queued， Re will wait for it。

And we'll talk a little more about that status in a minute， by the way。嗯。You know。

 blocking communication makes the programming model really， really simple， right， You send something。

 you wait for it to be acknowledged。 Now， you know the state of the universe and you proceed。

The problem with it， like I said， is that you're stizing something that otherwise could be parallel。

 you have something that could be making progress。Frozen， right， waiting for somebody else to act。嗯。

Non blocklocking receive and send。Relax that model。 So if you do a non block send。

 what happens is you send it， It gets queued and you go about your business。Okay。

Non blocking receive。 You ask for something。 You either get it or it's not there yet。

But you don't block。And this allows us basically to pull， okay。

Check to see if things are there and then go about and do some other work and check to see if things were there and go back and do some other work。

 So it allows us to overlap the computation in this wait time。

MPI weight and MPI tests are the two weights that we deal with non blocklocking things。

If we have a non blocking weight or a non blocking send and now we want to wait for it because we've done everything that we can do。

 we can call weight。And now we'll block for it。If we want to see whether or not it's de yet。

 we can call test。😡，Okay。And again， notice that status field， we can get more information。

The return from test is going to tell us whether or not it's ready。😡，That return follows the C。

 you know， the C And C plus plus convention where 0 means it's ready and nonze means it's not。

Even though in the MPI spec， they use the phrasing true and false。So don't be confused by that。

 It does follow the， It does follow the convention of the environment that you're coding in。

NPI status。Is going to be just some other information about it。 The source， the tag， if it's there。

 account that shows progress canceled if it's been canceled and error if there's an error。

So if we test and we get back status， that can tell us， for example， if it's broken。

MPI probe is like an MPI receive， but it just gets the status。It's like a peak。嗯。

We talked about why there are data types because it lets us be portable， right。

 Lets us know how big things are。 We talked about tags and what they're used for。嗯。Ys。嗯。You know。

 in the end， MPI is really simple， right mean。3，4，5。

 These six basic functions probably cover 90% of which we'll use。

If you add that the two non blocking things in probe， probably 9 functions。

That's really all there is to MP。 The trick with MPI is not how to use the libraries。

The trick is how to structure， how to solve the problem， right。

So message passing is a great way of problem solving， because it allows for sort of。

 you'll see this a little more。 It allows for sort of soft synchronization。😊，Right。

It allows a process to do a bunch of work。 And when it's done， send a message。

 And so you synchronize on this communication rather than synchronizing on data。

 You're not sharing memory。 So you're not piling up trying to get to the same thing。

You get something， you work on it， you turn on it， you send off your results。Okay。

 there's nothing else you need to be listening to in class。 Come on。Okay。Any questions about that？

Alright， so that should 30 seconds or close to a tutorial about， about that。 Oh。

 I guess I should have sorry， I should have covered broadcast and reduced。So broadcast。

Sends messages to more than one recipient， just like you'd expect to do。And reduced does what you。

 what you expect to do。 There are certain operations， you know， that， that can be applied。

And you can collect results basically。嗯。So here you can see hes。

Here you can see a broadcast operation。 And you can see it's just going to everybody in the current communicator。

 which in this case， is the default communicator。And here， you can see。An MP reduce。

 that's reducing the results。By summ。Yeah。S of like the number。Processes that you're sending it。

 Yeah， how does the broadcast scale with the number process you're it， That's a really good question。

 And the cool thing about MP I is it doesn't have to answer it because it's just an interface。😊。

So it said nothing at all about the mechanism by which that communication happens。

So the underlying implementation is gonna control what that communication is a series of uncast messages or is a broadcast along a shared bus。

So if you deal with supercomputer， depending upon the architecture of the of the actual communication that may have different costs。

 it may be that there's a relatively low cost， relatively low in quotes to arbitrate across a common bus and send one message to multiple processors。

It may be that such a thing does not exist， and you actually need to address that message to each of the processors in turn。

Does that make sense。Does it make sense why M I doesn't not only does not have to。

 but cannot answer that question。Imentations for different。Yeah， that's exactly right。

 The hardware is going to have different mechanisms。

 and those are going to be exploited by the software layer。

And so depending upon what's available in the hardware。

 the software is going to be able to answer that question differently。Okay。嗯。Okay。Let's see。

 And so this works just like any other reduce。 And in this case， it's reducing pi。By summary。对呀。

So is it safe to assume that？every single person that group every single member of that communicator gets it。

 yes。Do they support that？Of like。For。Grabs it。Now you're asking me a question where the best answer I can give you on that is not that I know of。

So I have never used a worker poolol configuration that now。I have。Yeah， I have used Q。

 I have used a queue in in， in that situation where I broadcast work to a queue。

 and then I took work off the queue。But， I don't know that。

I don't know of a built in mechanism for that。 Now that might just mean I don't know of it。

 So send me an email， and I will give you a definitive answer。

And I will look it up and give you a definitive answer， but not that I've used。

Total number of significant MPI programs I've written in my lifetime， probably 10。I mean。

 it all honest。 So I've used it。 I've used it enough to be comfortable with it。

 If I would run into that， I would go Google it， and I will Google it for you。Okay。Deadlocks。

 anytime you use blocking communication， be careful of deadlocks， They sneak up in unfortunate ways。

 This is a sneakky way that a deadlock。嗯。We're sending on process 0。

 We're sending to process 1 and then trying to receive from process 1。On process one。

 we're sending a process zero and then trying to receive from process zero。

The problem with this is that when buffers become full， things block。Right。

So the ability to send a message depends upon the receiver having the ability to read it。

So what can happen here。Okay。嗯。So if there's insufficient storage on process one for。For， you know。

 for， to receive this message， that send is gonna block。Right。

 process  one is not going to be able to receive it。Process one， on the other hand。

 is trying to send to process0， but process0 can't receive that because process one is trying to send。

Process  zero can't get to the receive to start processing that message。

And so we're sort of deadlocked here。Right， and it's not obvious that we're deadlock when you first look at this。

 because you look at this and say， okay， it's going send this message， and it's going wait。

 The other one' is going to send the message and then wait。

There is some subtlety that can sneak up on you。The best solution to this type of thing is probably non blocking I O。

Of course， non blocking I O complicates the programming model a lot。 And so if you can avoid that。

 sometimes you can reorder things so that you can avoid the potential for that。In this case。

 the reorder of the receive and send make sure that we're not gonna get in a situation where the two sends can't push the data because buffers are full。

Because that first receive was going to drain a buffer。Makes sense。Okay。

AndI think that's sort of all I actually want to say about MP is I want to get on to the other code examples。

 I just want to give you a 30 second introduction to it。

Mostly to convince you that it's not frightening， scary or terrifying and that when you have to use it。

 it'll be easy。Now， what I'd like you guys to do。Is to come over to this directory。Oops。

 you can't see that。Come over to this directory。And open up on your desktops。

 these two files and your choice of editors。Okay， and open them up from the recitation week 7 area。

 I've gone ahead and fix the numbering issue。 So this is now。

 this is week 7 instead of week 6 because， well， it is。That've resynchronized。

Resitation weeks with class weeks。And you can just C， D there。

 There's nothing magical about the path， right， You can just C D to the usual class path， A F， A F。

 S C， S academic class 15，4，18， S 1，8。And then from there， you can just find your way into public。

 and then you'll see the recitations there， and then you'll see recitation week 7 code。Alright。

Sounds like we're there。 I'm going to get there。Can you guys see that what looks that。

The first thing I'm opening up here is matrix at age。All right。So this is sort of a， A。

 a classic and important problem。 So we had this a sparse matrix。Meaning we have some。

 some big n by N matrix， but relatively few of the values are nonze。

So we're going to use a dense representation of that matrix。 And then we have a vector。

 and we want to apply the two。So if we take a look at what's going on in this code。

We see a lot of things that you would sort of expect。For example。

 we see a representation of a vector right here， and the representation of a vector right has an array。

And that's our vector。And it has a length， which is the number of elements in that array。Right。

 shocking。If we come down to the sparse matrix part， we're assuming for the moment。

 this matrix is square。So the number of rows is equal to the number of columns。Okay， and see。

 you see the number of rows here。Now。You see the value in the S value。😡，And so basically。

 what we're going to do os。Seectctor representation。Here we go。mAnd so now if you look at this。

 you see the number of rows and rows， which is going be the same as the number of columns because we're square。

Okay， now you see count of the number of nonze elements。

Remember that since we're dealing with a sparse matrix。 as's part of the definition of this problem。

 we're gonna have relatively few non zero elements。

 So we're gonna use this dense sort of press representation。 And basically。

 what we're gonna do is we're gonna have a vector of just the values。Boom， boom， boom， boom， boom。

 boom， boom， boom， boom， boom， boom that densely has the values。

And then what we're going to do is have vectors that tell us their position。

So if you look at this code。You see the number of rows， which is also the number of columns and N Z。

 the number of non zero elements。 this vector of values。

Which are simply the values in Rome major order with none of the zeros。Okay。

And then we see the column index for each entry。And then we see the row start。So basically。

 for each value， we know which row it is on and which column within that row is on。

And that tells us where it is in the actual two dimensional matrix。Does that make sense？

It's just a list of points， basically， within two dimensional space。Value， row column， value。

 row column， value， row column， where these points are listed in row major order。Now。

 as you might imagine， what this does is this makes if our matrix is truly sparse。

 while it shrinks it down to a much denser representation。And that's great。

That allows us to solve much bigger problems， And if it solves memory issues。

 it can also allow things to perform much better。Having said that。

 dealing with a sparse representation， obviously is going to take a little more work。

 and so it's going to add overhead。😡，Right。And that's basically what I think is worth seeing inside inside matrix H。

 So let's turn to matrix dot C。But。This is not the version we should be looking at。Mhmm。Alright。

 hang on， let me find the code I want us to look at。Oh。Give me one second。

 we don't have the right version of the code in here， but we'll fix that。There we go。Maybe not。



![](img/501820741086772e6576238c9e84fdca_1.png)

![](img/501820741086772e6576238c9e84fdca_2.png)

Alright， I think we're now。I think we're not good。If reopen that， you should be happy。

And so go to this thing here labeled。 If you search for beyond， you know， itll be。

 it'll be there at line。17， it'll be labeled standard sequential version。

I don't want to spend too much time on the standard sequential version。 but if we look at it。

We see that it does sort of exactly what you'd expect it to do。Okay。

And if you look at it and in particular， look at what's going on。In。These three lines。

It tells us a lot about what's going on in this inner loop。Okay。So focusing on those three lines。

What I would like to know is how many loads are there and how many floating point operations are there。

What time。What you。嗯。啊。我7。Do an LS。Okay， see every more。You would know us。EnV mold thats you can pig。

那个。So we're in MV Mo dot CPK。Okay。So I'd like to know how many loads there are in those three lines。

What values are we loading。What values are we loading。Yeah。C and。サイ。久緒にね。Okay。

 now what about associate with the floating point operation。

What better associate with floating point。We focus in on the floating point operations。M v， X v。

Right and vow。We agree。How many floating point operations do we have。Okay， if you said two。

 what are they。The multiply in the ad。 If you said one， why did you say one。O together。

 It could also be because the multiply and ad are  fued， right， There' is the multily and ad，Okay。

 so we take a look at this。 And we assume for a moment that we have two thesefuse multiply ad units。

2。Okay。That were're operating on a3 gigHz system。Okay， how many gigaplos can this inner loop see。

So focus for a moment on the fact that it's 3 GHz。Alright。

 And I think I probably also should have told you that it's three cycles of latency for each of these operations。

That was a necessary variable。So if it's 3 GHz and three cycles of latency。What does that tell us？

Yeah。T were getting half， yeah。系关。Okay， so if it's three cycles of latency。

For our dispatches every three cycles。And we're at three gigaplops。Then were。

 and thenre we're three gigahertz。 We're on one， if we look at one of those right we're one gigapflop。

 right。Because we can dispatch every three cycles。And we're3， and we're3 GHz。Makes sense。

3 GHz every third cycle， we can put one in so we can get。Basically one gig of5。Right。

Since we have two of these， we can get two gig。Three gigitcycles per second。Every third cycle。

 each one of these can do an operation。 We can put another operation in。 We have two of these。

 so we can do two every three cycles。Okay。So in terms of our gigaplops， we're two gigaplops， right。

Now， if we talk about memory latency， what's that going look like。

If I tell you that we have two loaders and each can load each cycle。Are we gonna be。

 are we gonna be memory limited， or we gonna be floating point operation limited。

Can I load the data values in as fast as I can process them in this case。What do you think。Well。

 I have3。 I can， I can， I can turn， I can produce in this three gigaplas， right。

That's my total output of this system。And then if I look at this code here， right。

 I'm ultimately going to end up with， with three cycles per element in terms of these。

 this to use multiplying ad。And so the question is， can I feed that。

That's going to require three loads。So the answer is， yes， I can， right。Oh， those take what。Yeah。

 those take less than three cycles。 So in this case， I can。Now。

If we come down to the next version here， we're unload where we we have the code that's unrolled。

Okay， and so we did is we now， we now， you know， did a standard unrolling。嗯。And you guys can sort of。

Browse through that。One thing to note is that G， the GCC，-0 3 is used， it's able to optimize out。

These that are these loops of I。 So we're not really focused on those。And again。

 we want to focus basically on these three lines。And these three lines。

We're producing the actual ad and multiply。Okay。嗯。Allright。Now when we do this。We turn out to be。

 out to be。 We turn out to be limited by the load units。We bring ourselves up to 4 gigphps。

We have two loads per three cycles。2 ads and two multiplies。And now we turn out to be memory limited。

Now。I'm gonna skip all the way down。To line 146。um。Actually， we correct that to line 2，93。right for。

And I'm sorry。Alright， try real。There we go。All right， now I'm on line 146。

If you take a look at line 146。We've added in a pragma here。For OMP parallel。

Someone tell me what that's gonna to do。Yeah。Processor high level。 I mean， just take。

 take the sky hi and what that's gonna do。Cut up the loop into chunks。Be一 charge。Okay。

 so it's asking's it's asking Open MP to automatically parallelze this by chopping this up into partitions and feeding them to processors。

Okay， so how many chunks is it is it gonna chop this into。Generally speaking。Wild gas。Number。

 of course。It going chop this up into number of cores into number of core chunks and parallelze them。

Fair enough。Nothing dramatically complicated there。So if we， if we have a core， we'd expect you know。

 a speed up of at best what。Number of core times， which given a cores is going to be。8。Okay。

 as it turns out， we see a speed up of 5。5 times。The world isn't perfect， right。

 So for putting in one magic line of code， that's not bad。For actually making use of our parallel。

 our resources， that's not so good。So it's all a matter of perspective。Right。

It certainly has the bang for the buck， but it doesn't have much bang。

So let's charge down to this next chunk of code right beneath it， where it says OMP dynamic。

And now look where it is four scheduled dynamic。And somebody tell me what that line of code means。

 give somebody real else a chance。Consider assigning。the same amount of work。Do take things。Okay。

 so if we， if we schedule a dynamic， is this going break it into more pieces or fewer pieces。

 the same number of pieces as a schedule。It's kind to break kids。good。Can't actually have elements。

Yeah， exactly right。 It's gonna chop it into into a whole bunch of small pieces。

 And the reason it's gonnan it into a whole bunch of small pieces is exactly， as you said。

 to make them sable。 If we chopped it in the same number of pieces， right。

 we're gonna put one piece in each process or there's nothing to dynamically schedule。Right。

 so we're gonna chop it into a bunch of small pieces。That way we give each quarter piece。

 and then when it's done， we give it another piece。Now， if we have a situation。

 we have a variable work density。Is that a good thing to do or a bad thing to do。Good thing， why。

Don't know。て。Just going out。Yeah， so like， if some are gonna end up with more work and something less。

 we can keep feeding the beast。 The ones that finish early， we can give more work to。 Okay， now。

 if we don't have a variable work density。You know， and each thing is going to take about as long。

Is it to our benefit to the schedule dynamic。No， why not？请谈。Chunks that are all need。Yeah。

 there's overhead and chopping it off and scheduling it and waiting for things to be done。

 handing out another piece。 There's overhead associated with each dispatch。 If we do this。

 we're doing a whole bunch more dispatches。 Plus， we're doing the work associated with these dispatches at runtime rather than statically when this code is emit。

Now， in this case， do you think this is going to help us at all。So you said no， not really。

 Any want to say yes， absolutely， more dynamic， more better。I like dynamic。Okay。

 somebody in the back。 Tell me why this is not going to help us very much。我 that。😊。

Not doing the tables。Okay， I will reason I didn't do the tables is that I have to tie my shoelace。

So here I will climb our shoelas。And then。I we'll get some break back。You shouldn't have smiled that。

You were just。Hi， I'm Greg。 Rachel Hey， Rachel。So we're talking about dynamic and。诶。就 suggestion。

know this is going to be a bad。And maybe it as a suggestion somewhere。

 I'm not sure that it's going to be a good case。So which side of that do you follow？一用的O。

So we talked early。The work is sort of evenly distributed。The， the， you know， it's the。

 the work density is， is about the same。 Then dynamic scheduling involves all this overhead to schedule dynamically。

 and it's all。runun time， not a compile time。 And so it slows down。 But if the same。

 like what looks like the same amount of work， the same space， you know， sometimes of。

Then the key portion。So which piece do you think we were in with a matrix？Its the。Yeah， I mean。

 we're just multiplying here， right？And it multiplies and multiplies and multiply。And in this case。

 we've even gone to the point where we have a dense representation。

Because we have a dense representative。That means we're not going to any large sections that have all zeros。

 right？Maybe if this was the sparse thing and we had you chunks of the matrix in its zeros and you get a chunk of matrix that was all zeros。

 you shrug it off and do nothing。And now we have a very important。Right。

 but in this case we're not in that situation， right。

 we have just a whole bunch of work that's about the same。😡，And so， obviously。

 this is not going to generate a huge improvement。 I mean。

 maybe sometimes a hair and maybe most of the time， not at all。No great surprise there。All right。

I want to skip down to where。Now， I want to come back。To somewhere around line 94。Thats。

So like one of。I mean， like， so could， could it be the case that there's just this down on its luck。

 Sorry thread that you know， keeps losing out arbitration for the memory， you know， I mean。

 like maybe。In that case， we should give it a quarter or buy the cup of coffee， I guess。

 But is that gonna to happen often enough that it's going to。

It's going to justify the over branded dynamic scheduling。Okay。

 so now we're dripping over here to the thing that says pregnant do parallel reduction on value。

 which like I said， is line 94 and 95。All right， now what we're paying attention to here is。

OMP parallel。 And then this bit4 reduction plus colon value。So this is our standard， like you know。

You know， map operation， right， So we're adding here。 So basically。

 what's going on is the end of one of these things。

 Then we're going to do a common reduce using the framework。

And we're going to reduce value by adding that。So at the end， where each of these computes a value。

 then this is going to collect those values in some。😡，Does that make sense。Okay。嗯。

This is not going to have a startling impact upon performance。All right。Now I want to turn to you。

Somewhere around line 2，13。Alright， so now， do you guys remember at the beginning of the。

 of the semester， when we， we took advantage of vector lane and vectorized our code。Sheer do。

 you remember it， anybody else remember it？Yep， so here we're basically doing the same thing。

 but we're using Gcc extensions to do it instead of a special compiler。

And what we have here is this vector T is declaring basically a vector variable。

Which is going to be used for our vectorized math。😡，Okay。And so， we see an operation。

Sort of like this， where we see we have a vector T star X V and a vector T star M V。

 And now you can see that we're operating upon those two vector types。That's a vectorized multiply。

Make sense， just like we had at the beginning of the semester。Different mechanism to get there。

 We're using GC extensions。 But that's exactly what this is。嗯。I guess what I could say about this。

Is that。My intuition on this was this was worth a shot。When I was reading through the code and。

 Randy is actually the one that wrote all this code。 When I was reading for this code。

 I actually thought this was gonna get a huge。I don't know what's causing that。

I actually thought this was going to get a huge。😡，Improvement in performance。

And then looked saw his notes and basically said his notes said not so much。And then I ran it。

And then。The performance I got was not so much better。And the question is， why？😡，Well。

 what generally limits performance if we're able to successfully vectorize operations。Yeah。Well。

 so if we're dealing with GPUs divergence could be an issue。

 But when we're dealing with sort of vectorizing floating point operations that are all packed in an array。

 And we're basically saying here， do this， right。あち。It's the instructions stream。So， okay。

 so maybe the instruction stream isn't particularly coherent。 But here we actually have the array。

 I mean， you see the array， you see the vector， you see。

 you're actually putting a floating point number into each lane。 So we know we're gonna be able to。

 to do that。Go ahead。So like one thing could be that we're hitting an ater limit。😡，But we're not。

I mean what generally limits us when we we start start to get past our problems。

 parallellyzing the computation and actually manage to get a really high level of parallelism。

What's that？We don't have enough in the lanes。 Let's say that we're， you know。

 if we get to the point， we don't have enough lanes。 The good news is。

 if we saturate all lanes on all cores， the good news is our floating point operation should be high。

 but they're probably not。😊，And the reason they're probably not high is what？😡，Yeah。

Like memory turns out to be the problem， right， like any any time we really think we've gotten past a hurdle and we've managed to go wide。

 right， memory somehow is going to bite us。RightAnd so take a minute and take a look at this code。

 talk to the person next to you if you'd like， and tell me why memory biteless。😡，这是。

Wheress coming from。我や。I。Re。Okay， talk to me。So I。Yes。So it's the same place member。That's correct。

ID X， No， I think you I don't think we' were very concerned about I D X。Yeah， so I X not what about。

他实的。All right， who's got a theory？Any else have a theory？The is in the back， excellent。

 So one thing to tell you is when you give a group of students something to work on and you listen to the room。

 initially， the volume comes up。And then the volume levels off， and then it crashes down。

And then it goes up again。Oh， did I。 And then when it comes up again， like。

 no one's talking about anything to do with the assignment。I saw hand up。 That made me really。因为。

Okay， everybody point to the person with their hand up in the back。Okay。Oh， you're over there， right。

See your friends to get all the。第事。I'm great。A you know。Grant right， so yeah。

 so we're not pre transposing， right， And like when reading the columns need to like。I about you。

Okay， so you read。60块钱。Alright。It's the。In such a way that it。It doesn't line up towards the cash。

Every fourth vector。Or whatever。冇で。系 a one time。Okay， maybe there's a cash line issue。

 and there probably is because there always is。What do you think。

 Why do you guys think we're not just knocking this dead， yeah。I had one thought I realized me。

I was thinking， oh， yes， we're learning two whole vectors worth。Well。Does't suppose。Yeah。

That's like 16 hole。Then I thought there。Right next to each other in that array。

That doesn't seem so bad。Yeah， I think I mean， think we're getting closer， yeah。第次 comp排的是。Okay。

 why do you think we're gonna hit the memory bandwidth with it。It's like they have basically one。

 two， three。Okay， what are the memory operations that you're looking at。だけど。Yeah， I mean。

 at the end of the day， right， we have these memory operations and our memory throughput is limited。

And so， you know， if you think back to our first example。

RightWe didn't have a huge amount of free bandwidth of that time。And now we're vectorizing。

 trying to do eight times as much work。Right， without having to go back and do that math。

 we're gonna be memory limited， which is really funny because。😊，In theory， there's， you know。

 should be able to support like 384 gigaplops of， you know， across all， across8 cores。

 I think there' are 6 giglops each。But then in reality， when you go to do that。

 you have to feed that beast， right？And we can't sustain that type of memory throughput。第千言。

It is a bandwidth issue， not a latency issue。I mean， bandwidth issues become latency issues。

 but the latency is secondary to the bandwidth。Right we'll eventually be able to do it， but。

It's slowing us down。Okay。So now let's open another version of the thing in there。

 If we back up one level， there is M V mole extra。And let's just open the version in there。

 M V mold do CPP。And if you could jump down to about line 200 in that code。Notice。

That we have the pound pragma O MP parallel above that。 So these variables declared here。

Private to a threat。They're all perth read， private variables。 They're not。Okay。

 and you soon see the comment in the code that says private to thread。And you can see， above that。

The O MPP parallel， right， things above that are going be shared。

 Things below that are going be private to a threat。Now， if we scan down。

We're going to see eventually， a pound pragma O MPP barrier。Remember。

 that's where we let the threads catch up。So there's a parallel phase with that parallel coming down to that barrier。

That barrier we synchronize， right， And then we can become parallel again， after that point。

So we basically can see there's a phase 1 and a phase 2 where phase 1 is punctuated by that synchronization。

Makes sense。Stop and wait right there。So let's ask ourselves， well， what's going on in phase 1。Well。

 if we look in phase 1。We see our three favorite lines right there in phase 1， right。

Where we basically do our famous multiplying ad on the date。

The thing to note is that each of these is now entirely independent because they're operating on thread local variables。

Which asks the question， how is it that we can turn around and aggregate these results？

Because normally aggregating the results would turn out to be an expensive thing， Right？

 So now each thread has a result。 and we're gonna have to walk through these what sequentially or something in order to deal with that。

But if we take a look at what goes on in phase 2， it's sort of cool。😊，Okay。So we have our barrier。

We have a statically schedule。For a loop。And now what's going to happen is。

We're gonna to use the threads to sum across all local threads。

So each thread was originally working on a partition of data and generated a set of results。

Now we're turning those threads around vertically， and they're aggregating the results across threads。

Okay。And so here you see that each thread is then working。In a petition。

Aggregating the results vertically within that petition。This way。Right。And so this is a really。

 really nice approach， because then in the initial phase， there was no overhead to synchronization。

 We took the problem。 We broke it up， and we gave each thread a chunk of it。

 and each thread computed a set of solutions within its partition。😊，In the next phase of the problem。

 we have the same threads， right。I mean， that's the way OpenM works。

We basically turn them around sideways and then have them walk across those partitions。

 summing across all threads。And that's what's going on here。Okay。

So it lets us have the parallelization without having the cost of synchronization。Now。

 I will say that when I ran this， I actually didn't get the speed up again that I expected。And so I。

 I was playing with this code last night。And。And I emailed Randy， and I asked him， I said， hey。

 you know， here gives us the speed up I got like。Is that what I should be seeing because I was a little surprised。

 I only saw a very modest gain when I ran it。

![](img/501820741086772e6576238c9e84fdca_4.png)

And I expected we'd see a lot more because the parallelization。 Now， what's probably happening is。

 from my quick look at it since I emailed Randy and asked them is I think we're just running to the same memory limits。

So the pattern is really nice and pretty。At the end of the day， I think we're still。

 we're still competing from memory。Any questions about that。Alright， And where are we with time，2，49。

 I think we'll call it there。 Have a great weekend， everybody。😊。

And we are hard at work gra your exams。 And so we'll have those back for you shortly。 Actually。

 before you guys leave actually， before， before you leave， Actually， let take five minutes。

 What's your feedback about the exam。Honest feedback， Any who wants to throw thoughts out there。Okay。

 so， so， so I appreciate the feedback of the exam was too hard。 But actually。

 if you could dive down and give me more detailed feedback， that would be gra。

 as hard as a word that I， I can't use to fix things。 Go ahead we have like practice exams that。😊。

So practice exams that are harder。 Okay， I' saw the hand in the back， yeah。There's one question。

苦しいのね。你过し。The cube question was really language。O， we' pay。

How many people had trouble with the language on the cube question， raise your hand？Oh my god。Okay。

 so， so， so the good news is I will raise that issue with the course staff and we'll talk about that as we deal with grading。

 because if that turns out to be an issue， then don't panic。😊。

We could adjust for that and how we wait the question and how we grade the question and whatnot。

 So don't panic on that， yeah。我这个。Cling。一しでさい。あそ人にはそう。Okay。I gotcha， yeah。Yeah。

 also the ISPC question I think was a。Just also。What。I think it was like。

How many people felt the ISBC question was unclear， raiseise your hand。Okay， I mean。

 that's still too many。 That's a little less overwhelming， but that's still too many。Go ahead。

Not everything on the exam was also。Shown up in the practice exam， like especially the。

Scaling with like。Yeah， so and Randy and I were talking about the practice exam。

 but we decided is that the course needs homework。And the reason is。

 like the practice exam was one sample， and it was a good sample， but it was just one sample。

 And it was a very small sample of a very large material space。And so at some level。

 it was reflective， but at some level， it also wasn't。Yeah。SoHow的。So I don't know if I should。外 true。

Thank summer。So basically the way that's going to be grade because I'm the one who's grading that particular one is that each each of those multiple choice questions is really like four questions。

 and each box gets graded， basically corrected and correct for some fraction of the points。

So if it's a two point question， there are four boxes， each particular one is worth four points。Okay。

 so we should do that in the paper。 Yeah， there was no way to like。The timing of the exam because。

You didn't give us like an actual。Just gave us questions。So there is no way to like。

TimeTo get your cadence right。Okay， yeah。So， yeah， what happened to the quizzes。

 So I think what happened to the quizzes is that the lab set is new and there's been a huge amount of effort developing the labs。

And I think in redeveloping the labs， the quizzes just went by the wayside。

Because there are two types of quizzes。There are quizzes that are a waste of time。

 and there are quizzes that are really reflective of what the exams will be。And。

What we need to have is home。 we， we can't really give a lightweight quiz that's not heavy impact on you。

 that's reflective of the exam right in class， because like we can give a really simple question。

 and that's not reflective of the exam。 So we sort of decided we needed。

 and we sort of came to this realization like， hey。

 we could develop a whole bunch of fake quizzes or we can do the development of the projects。

 The development of the projects 1。Now， what're realizing is we really have to make the investment in。

In homework， where you can actually do questions that are the same depth as the exam。

And so I think coming back coming back from springprint break。

 we're going to start to look at how to achieve that and try to get you guys more reheared and better prepared going into the final。

Other feedback yes， ma'am。I heard。I'm not sure。得到老是。So I don't know。

 I don't know where you heard that。I forgetOkay， I hope it wasn't for me。Otherwise。

 I saw some motors in this area。mean you're not penalized for providing feedback， right。

 take this to heart and try to write a final exam that meets our purposes and makes you guys happy。

 That's the goal， right。All right， if you've got other feedback， drop an email to the course staff。😡。

Yeah。房子。で种。The problem with the solution to the project is the moment the solution out there for the rest of time。

 we will be seeing that same solution again。And it's like54 whenever I used to using my accident start your。

来在其他。So what we might do， like when the course matures。We might be able to do that Right now。

 the problem is these labs were developed the day before yesterday。 Like。

 I saw the lab at lab the rats lab the same day you did because it wasn't there the night before。

So we had a good solution， right， but we didn't necessarily have like the best solution。

 And we need to balance things。 So if we put an exemp our solution out there。

 even if we don't put it in writing。Everybody is going to go see。 Everybody's going to hear about it。

 They're going to learn about culturally， right， because it's gonna be in the air。

 and every solution is gonna be that way。 And no one's going to think through it。

If we get experience and see how solution， how students solve the problem。

 then we can say like students have approached it this way or this way or that way or there's other way and not put like one target in front of people。

Okay， so again like。We want to we want to get to be able to have a conversation about solution space without putting one like hold one1 carrot in front of everybody where they run toward it。

Because otherwise， we'll never explore like neither we nor the students will explore the solution space of the assignment。

Okay， so maybe as we grade it， we can try to keep track of how people solved it and have that conversation after the fact。

So maybe it's not， It's not gonna to be having the conversation ahead of time。

 but maybe we can reflect on it afterward。带出去。So once we grade the midterm exam and we know where we are。

 then we'll be in a position to think about if we should make an adjustment and how。But let's take。

 let me grade that， grade the exam。 and let the course staff talk about how it is that we got to where we are before we start to think about that。

 But what I now know is there's a question that we need to look at really carefully。Right。

 to understand that people may have been interpreting it differently。

 So that was really good feedback。 And maybe we can make some corrections as we grade。

