# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P64：8_模块4 2 1 第3版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/d3f298def50912bcf5f714c83cb61c25_0.png)

Module 4， threads and go， topic 2。1 mutual exclusion。So we've been talking about channels。

G Teams is sending data back and forth through channels。Now sharing variables。

Between go routines can cause problems okay， and I'll show you an example of this。

But two go routines writing to a shared variable to the same shared variable can interfere with each other。

So so you know one will try to write one number， the other will try to write the other number and we'll get into an inconsistent state and I'll give you a more concrete example of that in a few slides。

A program， a thread program is said to be concurrency safe。If it can be executed。

Be invoked concurrently with other go routines without interfering improperly with the other go routines。

 So then you say， oh， this is concurrtency safe because I know that when this runs。

 it won't mess with the variables of the other go routines and alter them in some some way that will ruin the other go routines。

 So by this， I mean， note that one go routine can mess up the execution of another go routine right。

 So say this one go routine is using a variable X， the other go routine writes to that variable X while while the first go routine is using it。

 maybe maybe the second go routine didn't intend for that variable to be written by by this first go routine。

 And so the first one go routine can interfere with other go routines。😊。

A goine function said to be concurrency safe if you know that that won't happen。

 that they won't interfere in these unsafe ways。So let me just give you some example of what do I mean by bad sharing。

 how can that happen， and how can they interfere with each other， so it's be a little more concrete。

Okay， here's an example of variable sharing going on okay。Now， all this is going to do。

Is all it really does is it increments a variable I。 Okay， so there's this variable I。

 we're going to start it off at 0。And I'm going to make two threads in my main。

 I'm going to make two threads， which just increment I And I each one is going to increment at once。

 So by the time they're done， I should equal 2。 So I should start off a0。

 You run these two threads to increment I。 And then at the end， I should equal 2。

So just to look at the structure of the code， there are two functions。

 the main and the ink function for increment at the very top I'm just declaring this global variable I Also I'm declaring my weight group。

 remember I make a weight group so that the main doesn't complete before the go routines before the subgo routines have a chance to execute so I make the weight group。

Now my increment function， all it does is i equals I plus1。

 and then it calls a WG done to know that you don't have to wait for it anymore， it is now done。Now。

 then。My main function， I you know X Wwg dot add， I call the add method and I add two because I'm going wait on two go routines right because I'm gonna have two go routines that I'm gonna to create the do increment thing right。

 So I add two。 Then I I invoke the two go routines。 So go ink， go ink。 both of them。

 She just increment this I。And then I do a weight WG weight。

 waiting for both of these guys to finish。 and then at the end I just print I。

So what I expect is that I should print two right because I starts off at zero。

 I initialize to0 at the top， it should be two when it's done。But this doesn't always happen。

So let's explain sort of why this doesn't happen。It happens because of all it sometimes doesn't happen because of all the possible interleavings now at first glance。

It would seem like there's no real problem here because， you know there are different interleavings。

 but the interleavings all look reasonable。 they look like they don't cause a problem at a glance so。

What I'm showing here is this table。 the two tables， two different interchleavings。

 Each one of these tables has task  one on the left Test2 on the right， test2 in the middle。

 and then on the right is the value of I。 I just want to keep track of the value of I as we go through the code。

 Now notice I'm not showing all task1 and test2。 I'm not showing the done calls because the ordering of the done calls doesn't really matter for this。

 But I'm showing you that there are two different orderings for the i equals I plus1。

 So in the first in the top one， the top little chart， T 1 executes I equals I plus one first。

 then test 2 executes it second。 in the bottom， test1 executes second。 Test2 executes first。

 But either one of those two orders， the value of I ends up correct。

 So if you look at the top ordering。 Look at I， right。😊，It's zero at first。

 after the first increment， it becomes one， after the second increment， it becomes two。

And same thing on the bottom， even though the test2 does this increment first。

 it doesn't really matter because I is incremented twice still， so it goes from0 to 1，1 to2。

 so it looks like either one of these interleavings is just fine right that it shouldn't change the value of I but that is deceiving。

So really there are a lot more interleavings than we're seeing here。

The reason is because of the level at which this concurrency， this interleaving actually happens。

So concurrency is at the machine code level， not the source code level。

 so the what I mean by this is that the interleaving is not interleaving of go instructions。

 go source code instructions， what's actually getting interleaved are the underlying machine code instructions。

 right。So remember， the go source code is compiled to machine code on whatever platform you're on。

 And so these machine instructions， which are sort of smaller instructions。

 Those are what are actually getting intolead。 So what that means is for each one of these go source code instructions。

 there can be。Many a sequence of machine code instructions that correspond to the go source code instruction and so the interleaving can basically partition can chop up。

 interrupt right in the middle of a go source code instruction。

 it can start interleaving right in the middle of it。😊，So let's be more concrete。

 Let's take I equals I plus one。 The instruction that we're basically looking at right now。

 Now that might be typically that would map to it could map to three machine code instructions。

 First， a read I where you read the value of I from memory， because that most of these machines。

 there register based So you can't when you do the increment operation。

 you can't just increment directly in memory。 I mean， there are processes that do that。

 but most of the time， you read first read the data from memory into a register。

 Then you do the arithmetic manipulation。 and then you write the result back to memory。

 So those are three steps I'm showing here。 read I。

 it goes to memory to wherever the value of I is brings it into some register。

 That increment just takes the contents of that register as one。

 then write takes the contents of that register and writes it back to memory。

 wherever I is supposed to go。😊。

![](img/d3f298def50912bcf5f714c83cb61c25_2.png)

So that Iiggoi plus1， it looks like one instruction， it's one go instruction。

 but it's really a sequence of these three machine code instructions。Now。

This is important to keep in mind because the interleaving actually happens at that level。

So and that's what gets confusing because see normally。

 programmers aren't thinking about the machine code when they're writing their code or if they were。

 then they'd be writing machine code directly， write assembly code straight。 Now generally。

 if you're writing go code， you're thinking source code level， go instructions。

 You're not thinking about the sub the way that the go instructions are subdivided into machine code instructions not unless you are a hard code hardcore coder。

 you usually don't think about that right So this is where people can get tripped up。

 So let's show the interleavings， the different possible interleavings again。 except this time。

 instead of just looking at the two interleavings you know task one does the increment first or it does it second。

 those are the two。 Now we're gonna take these three instructions。

 these three machine instructions that interleave those and show how it can go wrong。😊，Okay。

 so here is an example。Where it goes wrong。 So this time you got task one left， actually。

 Ive the left very left column。 I've just numbered the line so I can refer to them。

But you got test one and test two and then on the right you got the value of I Now task one。

 if you look at just a test ones column and first it's going to do a read in step one。

 then step three is going to do the increment， then step4 does the right。And test2。

 it has the same order on in step two is going to do a read， then step6， it does an increment， step7。

 it doesnt right。Fine the ordering is you know in each one of these tasks。

 the ordering stays the same， but the relative interleaving can be different。

 And so notice the interleaving that we've picked。 and I've highlighted the read instructions。

 read I， read I。Task one does a Read eye in step one， and test two does a read eye in step two。

So what happens is both of them have read the same value of I。

 so note that the value of I at the beginning is zero。

 so test1 and test two have both read values zero for I。

Now then test1 goes ahead in step 3 and step 4， It increments that0 to a1。

 and then it writes it back to the location of memory where I goes。

 So it writes a1 into the location of memory where I goes。 And you can see that I is equal to1。

 But remember that task2。 The read that it did in step 2， Its still read a 0。

 So by the time test 2 does its increment in step 6。 It's incrementing what it read was a 0。

 which was a0， right， It's not incrementing the actual value of I in memory， which is now a1。

 right Remember T1 wrote a1 back to memory in step 4。 But that's not what was read by task 2。

 because of this interleaving test 2 read the old value of I 0。 So So test 2 in step 6。

 It increments as 0 to a1， And then it writes a1 in for I。

 Now there was already a one in there for I and writes another one in there for I。

 but the end of the sequence， I has a value 1 instead of2 so。😊，Think about this for a little while。

 but the idea， the general problem is that when these two these two and these two go routines are sharing this this I variable。

 right， they're both writing to it。The interleaving is happening at a finer granularity at the machine code level and that adds complications that people don't think about sometimes okay so it's important to be aware of these。

Thank you。😊，Module 4， threads and go topic 2。2 Mutex。

So how do we do sharing of data correctly between go routine routines。

 don't let two go routine routines write to a shared variable at the same time。

 just as a rule of thumb。Don't let that happen because you can get these into leavings that caused the problem that we just saw。

So you need to restrict the possible interleavings of these gold teams。

 say there are two gold teamss， gold Team 1 and 2， which are both writing to this variable I to this shared variable。

 shared data。Then you have to restrict their into leavings in such a way that you make sure that they can't both write to it at the same time。

So access to the shared variables cannot be interleaved you know you have to somehow as a programmer ensure that they can't both do that at the same time so how do you do that that is called mutual exclusion you need to have code segments you as a programmer have to declare code segments and these different go routines which cannot execute concurrently。

So that they cannot be interleaved。Because and so this action of say writing to shared variable so say that these two go routines both write to I right I equals I plus1 Is I plus1。

 you got to make sure that this go routines segment where it writes to I can is mutual mutually exclusive with the writing to I for this other go routine so you have to declare these segments of code that are mutually mutually exclusive with one another。

😊，And you have to do that as a programmer， so there are constructs， of course。

 built into into Gol to do that。So what we're going to use is in the sync package again。

 theres this mutex object。Mutex ensures mutual exclusion， okay。

 there are several methods associated with Mutex， but let me just describe it conceptually first。😊。



![](img/d3f298def50912bcf5f714c83cb61c25_4.png)

It uses what's called generally called a binary semapho Okay。

 so semapho is you know like the flag on your mailbox right if you have one of those outdoor mailboxes。

 So if the flag is up， that means the shared variable is in use right that means that theres somebody is using the shared variable so like specifically the shared variable if we're trying to protect this variable I right there are two go routines that are writing to I。

😊，Only one can do it at a time， so the flag should be up when one go routine is writing to eye。

And then the flag being down means the shared variable is available。

 So when this one go routine is done right to I， then the flag goes back down。

And then the other go routine knows， oh， now I see the flag is down。

 I can write to I if I want to Okay so each one of these go routines has to adhere to this protocol。

 meaning there's this semopho， this flag and this binary these are up or downs0 one， right。

If the flag is up， then you are not allowed to use the shared variable。😡。

Because that means somebody else， some other go routine is using it。 If the flag is down。

 then you are allowed to use the shared variable， but you have to put the flag up first。

 so you have to put the flag up and then use a shared variable and when you're done using a shared variable。

 you have to put the flag back down so everybody else。

 all the other go routines know they can use a shared variable So it is this protocol that you have to that the programmer has to write into their code and adhere to in order for this scheme to work。

 but this is the idea。😡，Thank you。Module 4 threads and go， topic 2。3 Mu text methods。

So we talked about these semaphos inside the Mutex。 you put the flag up。

 put the flag down to declare， put it up to declare you are using a go routines using the the the data。

 the shared data。 It's writing to it， and then put the flag down when you're done writing to it。

So these are implemented in a set of methods lock and unlock so lock。

 when you call lock that basically puts the flag up and when you call unlocklock。

 it puts flag down So you call lock our go team should call lock before it's about to use the shared data。



![](img/d3f298def50912bcf5f714c83cb61c25_6.png)

And what will happen is if no one has the lock， meaning no go routines are using the shared data。

 then that first lock that call to lock will proceed， it'll put the flag up。

 meaning set some binary value from 0 to 1。Internally， and then it will continue， right。

 so it will not block。 the lock will the code will execute in that mutually exclusive region。

 and it'll access to shared variable。Now， if while that's going on， say another go routine。

Comes along and calls lock。 Now， remember at this point when the second go routine comes along。

 calls lock， the flag is already up， right， So when that happens， lock will。

 then this lock will block。 It won't allow the second go routine to continue and access the shared data。

 So it stops the second one。 So who whichever go routine gets into that region calls lock first。

 it gets the lock and the other guy， whoever the other one is， it has to wait。

 And notice that we're talking about two go routines。 This could be any number of go routines。

 You can have 10 go routines all trying to share the same。😊，Same I， same eye variable。

 something like that。 They all like one of them gets in there first calls lock first。

 Then there could be9 other ones that try to call lock while the first ones in there and all9 will block。

So， so that's basically what lock does。 Now， unlock is the matching thing。

 So unlock is a thing is the function that gets called when your when the go routine is actually done using the shared data and it's effectively putting that flag down。

 So when this one go routine。😊，It's done using the shared data。

 It's got to call unlock if it doesn't that as an error because it'll cause it deadlock。

 It calls unlock。 And then what'll happen is one of the one of the go routines that are waiting。

 that are blocked on their lock will be able to continue So if there were like9 go routines that are that called lock and are now blocked as soon as unlock is called。

 the first one that called lock in the waiting list， it will actually itllll be allowed to continue。

 It'll stop blocking。 Itll be allowed to continue。 Itll access the shared variable And in this way。

 as long as you put a lock at the beginning。 as long as every go routine puts calls lock at the beginning of its mutually exclusive region and calls unlock at the end。

Then it ensures that each one of these that only one of these go routines can be inside this region。

 this mutually exclusive region， which in our case is basically where the shared variable is being written to。

So。So this mechanism is sort of generalizable to lots different lots of different goal routines。

 even though we're only talking about two right now。And here's a little example of it。

 how we would modify this incrementing problem。 So this incrementing problem that we had。

 I'm fixing it now I go to this increment function and now basically I've done a couple of things I've added。

 if you look at the second line， I've created a Muex， so called it MUT。😊。

And then the the increment function is still the I equals I plus one。 But before that。

 it calls M U T dot lock。 and after that， it calls M Ut dot unlock。

 So now that region in between the lock and the unlock。

 that is mutual mutually exclusive with any other lock unlock region。 So remember with them。

This example， these go routines I had two go routines would call that would basically execute increment。

 and so both of them have a lock and an unlock， since they're both executing the same function。

 increment function， they both have a lock and unlock before and after their regions。

 So those regions are exclusive。 So only one of those go to go routines can be executing I equals I plus1 at a time。

 because once one of them gets in there and calls lock。

 The other one is blocks blocked on that lock until the first one finishes calls unlock。

 then the second one can go through。😊，So that's sort of a simple example of how you would do mutual exclusion。

Thank you。