# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p30 P30 Write your own Operating System A09： TCP + a little HTTP -BV1BDBEByEBY_p30-

Hello and welcome to the ninth part of the Appendix on the tutorial on Writ operating system。

So this is already the fourth video on the transmission control protocol。

 but so it's already worse than I had feared， but I'm confident that we will get it somehow running in this video。

So， yeah， let's just jump right into it。 I mean， we've talked about all that we need to know。

 It's just。That in the last video I couldn't go on。



![](img/7dbc400bd678ed3d1daabde601b2f13b_1.png)

嗯。Because I was just too much data， and I was just exhausted， so。So let's continue now。😔。

So there's just too much data here， right， so something must be wrong。

But the first thing I'm going to do now is I'm going to the driver of the network car。

And here I will shorten the output a bit。So。I will only print the bys starting at 34。

 because 34 Bs is。Yet， 12 plus。It's 14 plus 20。And yeah，14 exercise size of。

The ethernet frame header and 20 is the size of the。IPV4 had also。If I do this。

 it will only print the。TCP messages， only the TCP part of the message。



![](img/7dbc400bd678ed3d1daabde601b2f13b_3.png)

Okay， so。Now it should be a bit clearer what we are doing。😔。



![](img/7dbc400bd678ed3d1daabde601b2f13b_5.png)

So now we have a lot less data here。Okay， so the first messages are the ARP messages。

 they are ruined by this。 But okay， so that's。We have to live with that。Okay， so。

Now let's look into these messages。 we sent something， we sent another thing。

Three messages that we sent and one that we receive。O so。Let's look at these messages。

 We have two bys for the source port， destination port。 This is a 1，2，3，4 here and。Exodeadeimal。

And this is， yeah， just part 1024， which is the first free pod that we are using。

Beef Cafe is our initial sequence number。You know， the offset in that screen。

This would be the acknowledge number， but since the acknowledge bit is not set。

 this is just invalid so this is we can just ignore that。嗯。Okay， and then here's a 600，2。

 So this is really the interesting part。 This is。The header size， Yeah，6 is the header size。

And the0 here is。The reserve data and the 02 is really the Fl。

 and that's really what we are interested in。 now after that we have some windows size to check some and some options。

And the urgent point up。So here's the check some， here's the U point here。And here are the options。嗯。

But the thing we are really interested in is this bite here。So we sent a02。02 is synchronized。

 as you can see in the table。And we sent another synchronize on port。1025。Okay。

 so that's not what we want to we want to do。 so let's look into the kernel。Yeah。

 so here we do the TCP connect。And yeah， but there's all another TCP connect up here。

 and that's just wrong。😔。

![](img/7dbc400bd678ed3d1daabde601b2f13b_7.png)

I mean， net cut is。嗯。う。Yeah， net cut only opens one listening socket。 So when you connect to that。

 then it's， then this socket is gone， it's。Bound to something else and if you connect again。

 it will just go nowhere。So。

![](img/7dbc400bd678ed3d1daabde601b2f13b_9.png)

Okay， what do we have now， Here's our connect。😔，12 is sin and act。 you know the one。

The leading one is the acknowledge bit。And the two is the synchronized bit， so。So 12 is synac。

 and that's correct， that's what we expect to get。いや。So we send the in， we get us an a。

 and this 1 is another a。And。Here， we sent。We send some data。😔，Yeah， I mean。

 I'm sending this Ho TCP here。

![](img/7dbc400bd678ed3d1daabde601b2f13b_11.png)

And。

![](img/7dbc400bd678ed3d1daabde601b2f13b_13.png)

Okay， of course。I have limited the output of。

![](img/7dbc400bd678ed3d1daabde601b2f13b_15.png)

Also data to 64 byte。So yeah， this is a hello TCP， you know， H E LLO space。20th space。嗯。And then。

 yes。Then this eye just passes a 64 and the rest isn't printed。

But I'm wondering why it doesn't show this。😔。

![](img/7dbc400bd678ed3d1daabde601b2f13b_17.png)

So， let's see。Yeah。I mean， I am happy that the handshking actually already worked。But yeah。

 what's going on here？😔，Yeah， in my。Coat that I prepared。 I'm doing。あ。When I'm sending data。

From a socket。I'm giving it the。Push， and。Acknowledge bits。I mean。

The acknowledgement should not make any difference。

So the worst that could happen is you could just acknowledge something that you have received again and。

Not move and that would just move the pointer ahead by zero。Shouldn't have any effect。嗯。And push。

 yeah， push means don't buffers handle it immediately。 So that might。



![](img/7dbc400bd678ed3d1daabde601b2f13b_19.png)

Already make。The difference here。Okay， now here we have the message send and now we receive something。

😔，Pt， port。Sequence number， acknowledgeknowment number。😔，Message size， yeah。

 and this is so now now we get an acknowledge。Fit here。So yeah。Look at that。

 We've gotten the message from inside the virtual machine。 Isn't that something， So we。



![](img/7dbc400bd678ed3d1daabde601b2f13b_21.png)

Now we actually get TCP data out of the virtual machine and can communicate with machines outside of the virtual box virtual machine。

So that's already， yeah， that's already something。😔。



![](img/7dbc400bd678ed3d1daabde601b2f13b_23.png)

I'm happy about that， so。Let's see。 Now I'm closing the connection。So of this horse。 hello。

 this horse。This was the acknowledgement to the。To the hello。Now，11 means。Finalize and acknowledge。

So this means Netcar wants to close a connection， that's correct。Then we acknowledge that。Then。We。

Send our own。Finalize， and acknowledge。嗯。It's strange。

So here we send the acknowledge to the finalize。😔，Then， we send our。Our own。

 finalize and acknowledge。Like this。We should get another acknowledge， but。Yes。

 this is somehow strange。 We are also sending。This 0，4。D two。04，00。

 so this actually looks like another TCP header。I don't know why is Arizona isno send or receive。你别讨。

But 042 means it comes from the server。😔，And it's going to the client。

 So this is coming from Net cut， going to us。 I don't know why it didn't print the receive， but。

Might be an issue with。Mutual exclusion， probably。So。What do we have。0，4，0，0。

 acknowledge sequence number， Acment number。😔，Size， yeah， and then this is another acknowledge。 Yeah。

 that's， yeah， it's what we expect。 This is the final acknowledge。So。

So the connection has been properly closed at this point。Okay， let's see。 I run this again。

So we get the Ho TCP。😔，Now I'm sending something back。😔，Now， it's gone too fast。



![](img/7dbc400bd678ed3d1daabde601b2f13b_25.png)

I just remove some of these line feeds here。😔。

![](img/7dbc400bd678ed3d1daabde601b2f13b_27.png)

お。い。I mean， it didn't look like it was doing what we wanted to do。So I've paused a virtual machine。

 hey， hey， hey hey， look look at this， look at this。 There's a hello my O， yes。He。Look at that， so。

Here we send our message， we receive the acknowledge， here we receive this Hello my O。Okay， what。

 what is going on here， We send an acknowledge for this hello my O S， but why。Why doesn't this。

I mean。It's sending it to us again here。嗯。I don't know what's going on here。

 I think this might probably have something to do with the offset。😔。

Of the acknowledgement number and sequence number， I guess。So we get some data。 we acknowledge it。

But apparently， the acknowledgement has some error， I guess， because。Yeah， because。

Because Ne cut apparently doesn't accept our acknowledgeknowment。So we'll have to look into that。😔。

But I'm really happy right now that we have gotten this hello my O S here。

 So this is really a good thing。

![](img/7dbc400bd678ed3d1daabde601b2f13b_29.png)

Hey everyone， Yeah， if you remember the video about IPV4。

I said that I made a mistake with the length of the。Of the I message。 And I said that。You know。

 I made a cut there and。Interrupted the video， and I said that in a later video。

 I had gotten a lot of trouble because of this。Rather than made now， and yeah。

 this is the point where this trouble occurred。The thing is。

 if you remember the problem was that I was passing the wrong size of the IP message。

 you know I didn't pass the size of the IP message。

 but of the Ethernet train which might be larger okay so all the garbage behind the IP message was also passed to the next level。

And yeah， this is what happened here。 We added the length of the。

Of of the ethernet frame instead of the IP message to our acknowledgement number Okay and yeah。

 the remote machine doesn't do that it only adds the size of the IP message to its sequence number Okay。

 so our acknowledgement number and the remote sequence number went out of sync and yeah then everything fell apart Okay but。

Yeah if you followed the IPV4 video where I included the fix then this shouldn't have happened here to you in the first place。

 so let's get back to the video and listen to my rants about the ugly workaround that I made there it's really not pretty you know basically I counted the zero bytes behind behind the IP message and。

Subtracted them from the acknowledgeknowment again。 And that's that's really an ugly workaround。

 And it's not correct even， you know， because somebody might send you zeros and that's legal。

 So then we would go out of sync again， but。Yeah， whatever。 so let's go back to that。Finally。

 I found the problem so。😔。

![](img/7dbc400bd678ed3d1daabde601b2f13b_31.png)

Yeah， the problem that we had was。Yeah Necut sends us its buffer。

 And behind the data that you've entered， it fills buffer the buffer is filled with zeros。And。Yeah。

 what we had done here was。I added here。 the size。Of the full message。

 including these trailing zeros。And yeah。So instead， what I'm doing instead now is I'm。

Counting the zeros， Well， not counting the zeros。 I'm looking for the last。Point of this message。

 That is not 0。And that is what I。So what I add here now to the acknowledgement number。So。あ。Yeah。

 let's look what that does。So we get the Ho TCP again。And here we received hello my O。

And here we send the acknowledgeknowment。 And this time， the acknowledgement is okay， so。So。

 we don't receive。Another TCP message that complains about this answer。Okay， so。诶。Yeah。

 one more thing that I've noticed is here in。In the A case， we shouldn't return faults here。

In this case， we should break。Because， yeah， we set the state to close， but。

Removing the socket from the list of sockets is done down here。So。If we return already there。

 then the socket isn't removed from this list。Okayケ。So。That a set。Oh。

 I don't know if I have already shown you this， but I have also added such a little loop here in the scent on the socket。

 which waits for the socket to be established。😔，So， that's because。Here in the kernel。嗯。I connect。

 and immediately send the。Sent the message there。And yeah， if。

It could happen that the message is sent before we even get the Sun act and and we haven't sent the final act。

 so it would be not a good idea to be sending data already。

At least it would be violating the standard， and。Yeah， but on the other hand， I mean。This could。

Well become an infinite loop if yeah， in all kinds of situations， but。Okay， for this presentation。

 this should be。Enough。So。So the last thing we should be doing。😔，嗯。

Here we should also implement this reset。But this isn't。😔，that hard， so。😔，I mean， it's a。

Some its a bit of code， but。Yeah， let's just go into this。 So if we are resetting。

A socket that is that we already have。So we have a socket and we receive some illegal data on it。

 Then we just。You said socket。To send a reset。可没。In my implementation， I sent reset and egg。

 but whatever。😔，So the problematic case is when we don't have a socket yet。

Because we've received data。That is not going to any socket。 I think it would be okay in that case。

 to just ignore that。The package and just return faults here。嗯。But。Yeah。

 I think it would also make sense。To， to respond。To that。お。So then so we don't yet have a socket。

 which we can use to send the data over。 So we'll just make a temporary socket here。Let's see。😔。

So then we have to set these values for the socket。😔，We don't need a handr。😔，Okay。うち。Yes。

 the handler is set to 0， and the state to。😔，To closed by the。😔，As a constructor。😔。

So we don't have to set the state， we don't have to set the handl。😔，And the back end。Okay。

So we get a sequence number。😔，And turned that to our acknowledgement。😔，喜欢吗。

Maybe we just set our own sequence number to。😔，So acknowledgement number from。From the message， yeah。

 that I think that makes sense。😔，Yeah， and everything else should be done by。So， send method。O嗯。嗯。

Can we test this？😔，Yeah， maybe if I do something like。So upp here in the handton。😔。

You could do something like。So returning faults in the handler method meant we want to reset the connection。

 right。

![](img/7dbc400bd678ed3d1daabde601b2f13b_33.png)

So。

![](img/7dbc400bd678ed3d1daabde601b2f13b_35.png)

So now I tell it to quit。😔，And here， I sent this。Yeah， here's a reset message。And yeah。

 as you can see， the connection has been terminated so。So resetting seems to work。😔，Maybe we don't。😔。

1，2。嗯。Terinate this in ungracefully。 Let's see if we can。If we can quit gracefully。



![](img/7dbc400bd678ed3d1daabde601b2f13b_37.png)

好。

![](img/7dbc400bd678ed3d1daabde601b2f13b_39.png)

Okay， here we send。In an a， we get an a。We get to thing like ourselves as think。😔。

I think this is incoming。Andま。Here， we send them。Ak。Strange。We get a 19。算。😔，Ac a push。 And a f。What。

😮，Yeah， might have to do with the fact that。That we sent the。Ac from this return， I mean。I mean。

 we sent an egg here。After。The handler and the handler。嗯。So if the handler already sends a f。

 then normally you shouldn't be able to send data over that。Afterwards。😔，Yeah。

 but still somehow strange， but whatever。I think that is kind of okay。嗯。So。Maybe we'll。

Maybe I'll look。Let you know about a little fix to that， but I don't know。

 doesn't matter to me right now， something that I want to do now。Is。Yeah， here in the kernel。😔。

I want to implement something else。😔，嗯。Thank。So if we get the raw text。😔，Get slash H T T P。When。

 we send。The following response。😔，HTTP。Slash 1。1。Space。200。Space， O， back slash R， back slash N。So。

My O。B slash R， back slash n。Content type。Space text。Slash H T M L。B slash R， back slash N。

 back slash R back slash n。And now some。HTM added document。Yeah。やに。HtML head title。😔，Yeah。Of it。好这。嗯。

Next session session。Yeah。不。Yeah。O。Wait， I want to。Ha says listening。😔，Yeah。



![](img/7dbc400bd678ed3d1daabde601b2f13b_41.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_42.png)

。That。Okay， I have to count the length of this。😔，Yeah， about。200。I just say 200。



![](img/7dbc400bd678ed3d1daabde601b2f13b_44.png)

So。Pt forwarding。For TCP now。

![](img/7dbc400bd678ed3d1daabde601b2f13b_46.png)

Yeah。No， we're not reacting to it。😔。

![](img/7dbc400bd678ed3d1daabde601b2f13b_48.png)

Yeah。

![](img/7dbc400bd678ed3d1daabde601b2f13b_50.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_51.png)

So we get synchronized。 We send us in。Ark。And we get an a。

We get a hello and we send the acknowledgement so。😔，YeahI really don't see。😔。

Why this didn't work with。😔，With the browser。So， we do get。The are response that we want。😔。

In this case。NowSomething else is going wrong again， we get this a push fin again。😔，I don't count。



![](img/7dbc400bd678ed3d1daabde601b2f13b_53.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_54.png)

He。What do you know？So that's kind of cool， I think， so now we can really communicate through TCP IP。

And yeah， we've implemented， implemented an HTTP server， right， if you want to call it that。But yet。

 I mean， it does communicate through the HTTP protocol。嗯。And we can actually access this with。

With a web browser， so I think that's quite cool。So。Yeah， of course。

 you could now connect this H TTP server to a file system so that。

You would deliver the content of some file that。The browser requested， but。😔，Yeah。

 I think this really should be enough for the TCP and also for the。HTTP， I mean。

 I'm not going to show you completely HTTP， but。But yeah， it's， it's a little glimpse of H T TP。

 And yeah， it's， I think it's really cool that our operating system can now talk to a web browser and。

Deliver it some。Yeah， I mean， it's static data but it does deliver something。

 so I think that's quite cool。And yeah， this is all I want to do with TCP。So。



![](img/7dbc400bd678ed3d1daabde601b2f13b_56.png)

诶。Actually， that's all I wanted to do for the network stack。嗯。Not only TCP。

 but networking in general。So next time， I'm going to go a little bit into。Into file systems， Yeah。

 only the file allocation table F 32， but。It's better than nothing so here tune in next time when we will look at file systems。

Yeah， tune in don't forget to subscribe so that you don't miss the next video about file systems hit like if you like this video。

 I mean it's a bit of a mess。Protocol is still kind of messy and doing stuff that I don't really understand。

😔，I mean， this acknowledge push and f。😔，I don't know what。Well it's sending us that， but yeah。

 whatever。So。I have somewhat mixed feelings about it。

 I find it I do like the video for the fact that we can communicate through TCP and actually even H T TP。

 but。On the other hand， I do not like the fact that it still has some strange bugs and goes into strange loops at times。

 but okay。I think we will have to live with that so。Yeah。So much for today and see you next time。

 bye。