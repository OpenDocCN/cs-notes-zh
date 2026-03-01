# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p40 40_02_03_哲学家就餐问题.zh_en -BV11y411z7Dn_p40-

![](img/db7788edcc0dd60cc133c4399aefd048_0.png)

Okay。Here we have a dining philosopher problem。 What's interesting about this problem is that you need to figure out a way for a bunch of people sitting at a table。

 In this case， philosophers to all figure out a way to share a certain amount of forks and what's interesting about this particular issue is that it can expose certain problems like deadlocks。

 for example， and one of the things that you can do to prevent this is to use the correct forms of concurrency。

 So in this case， the muttex is going to provide exclusive fork access。 So these are eating forks。

 the arc allows sharing forks between philosophers。

 So the simulation is going to print the start time。

 the eating direction and the total time for all the philosophers and also the total time approximately equals the philosophers divided by the forks。

 So that's the number that can eat concurrently。 So when you're doing a form of simulation on concurrency。

It's always really important to benchmark it to make sure that what you think is happening is happening。

 So if you introduce a bunch of threads and nothing speeds up， then there could be a problem。

 So in this case， we're going to use these techniques。

 which is a mutex to represent exclusive fork access。

 We're also going to wrap it in an arc to share muttexes between threads。

 We're also going to use a numbered philosopher and acquire a lower fork first。 then finally。

 we're going to do all the timing for the simulation。 So again。

Really critical to print out the time speed up。 There is a diminishing return that's going to happen with concurrency。

 And this is called Ammdsla， where。The more there is something that's going to wait。

 the there's diminishing returns with the concurrency。

 So you need to double check that it's even worth it to， to actually make something multi threaded。

 So in this situation here， we're going to use the standard library。

 This is Arc Mutex thread duration， we're going to implement a fork。 So in this case。

 this is the thing that the philosophers are going to use。

 And then we're going to implement a philosopher。And then right here we have the philosopher。

We make it an instance of it， and then we have an eat method here where in this case。

 it shows the logic behind the fact that they need to pick up the forks in a way that really prevents deadlocks。

 but we do have some debugging information， which also is really helpful when you're first you know going through and building out concurrent code is to have。

The really the printing or the logging statements， logging is even better so that you know exactly what's happening。

 In fact， if you had a log dot debug， you could debug it while you're developing it and then not show those messages when it's in production。

 but then if there's an issue and you need to do some more development。

 you would toggle on the debug method。So here we have the main method and this main method is going to show that we only have four forks at the table and this is going to print out the information about it。

 and then we're going to apply mutex around this so that it's going to prevent issues with shared access to a fork which would cause massive problems like a deadlock。

And here we see all the philosophers， there's a vector right here that is a section that includes everybody that we want to have at the table。

And then here we're going to put this into our collection。 Finally。

 we're going to spawn threads here so that everybody can start eating together。 And then finally。

 we're going to go ahead and print everything together。

 So really the key takeaway here is that the muttex is what is helpful so that we can have everybody try to eat。

 But there's some logic around who can get the fork at a given time。 So let's go ahead and run this。

 And if we go to go into dining philosopher here we type in cargo run。

We can see the simulation so this is again critical when you're doing multithted programming is to go ahead and build out the instrumentation for what exactly is happening because the philosophers for example。

 need to be able to pick up both fork right so we're debugging that and we also have the ability to print out the messages when they're done when they started and at the very end again you should benchmark it and say well how many philosophers were there well we have approximately we can see actually from Rus that it'll tell us。

Exactly the list of philosophers here。 And then we look at the time。

 and we should have a level of efficiency because of the fact that we're able to use multi threaded programming to you know。

 speed up the work。 So in a nutshell， this is a great way to play around with。😊。

Some of the classic problems in concurrency by using the rust language。

 Ru has a lot of safety techniques as well that will prevent you from compiling code with known errors。

 it's not going to prevent every error， but this is a great idea for maybe a future level of concurrency that you could use in a real world project。



![](img/db7788edcc0dd60cc133c4399aefd048_2.png)