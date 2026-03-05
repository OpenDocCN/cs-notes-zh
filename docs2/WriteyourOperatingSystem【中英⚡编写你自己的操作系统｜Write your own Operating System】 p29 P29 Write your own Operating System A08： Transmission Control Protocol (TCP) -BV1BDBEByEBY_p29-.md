# WriteyourOperatingSystem【中英⚡编写你自己的操作系统｜Write your own Operating System】 p29 P29 Write your own Operating System A08： Transmission Control Protocol (TCP) -BV1BDBEByEBY_p29-

Hello， welcome to the8 appendix to the。Hello and welcome to the AI Appendix to the tutorial on Writing your own operating system。

Now， in the last two videos， we implemented the transmission control protocol。Yeah。

 at least something that's kind of compatible with that。Not a complete TCP。😔，Implementation。Yeah。

 but we didn't implement the receive method yet， so we could send data。

And we could send a the request to a connection。We could send the date as a information that we want to disconnect。

嗯。But we still need to be able to。To process the return data that we get， so。

Last video we sent a synchronize。Message to a server we received。The acknowledgeknowment of that。

But we didn't send the corresponding acknowledge to that。 And that's why why the server kept。

Re asking us for。The acknowledgecknowment。嗯。And we also haven't implemented anything for this finalized and for termination of。

Of the connection。

![](img/89a8340e49453b1571211dc28a08e296_1.png)

Yeah。So we'll just jump right into that。So what do we have？We get data from IPV4。Now， if。

This should be different， actually， because。So the TCP header that we use has four extra bytes for options。

 which are not necessarily there。 so I will make。嗯。I will do this like this。

The size needs to be at least 20 because that's the smallest size。

 the smallest legal size of TCP header。Then。あせなけ。I put。Yeah， this pointer over the。

What was the data that we receive？😔，Okay。Yes， this basically works way like in UDP so。

We iterate our sockets， and look for a socket。Which is responsible for this message。Okay， let's see。

 I think this isn't exactly a good idea to handle this at this position。😔，谢谢。Re。

So we will make a big switch here。😔，And distinguish the cases that we will only look at those three bits。

 synchronize， acknowledge， and finalize。Okay， so。If we find。😔，A state， a socket that is listening。

On the part that he is looking for。So this will just be done in the case of a sin。And this only if。嗯。

If we actually have a socket， you know， so。So if we find a listening one and。So， if。

If the sender wants to synchronize。😔，And this is a listening socket。 Then we set the socket。

To this value。To the one that we found here，So the other one wants to synchronize and we are listening okay。

If we have a socket。😔，そ。Yeah。Only if the socket is actually so we go into the switch only if we have found a socket okay。

And if we have found a socket。😔，嗯。That is。Yeah， we， we now look at these three。Fex。

And if only the synchronize are set。ItMean the other guy wants to connect to us。

 but we only allow that。嗯。If we are actually listening。Yeah。Yeah。So I would。那个不会 here。

And this will be。False usually but set to true if we want to terminate the connection。

 so if someone tries to connect to us without us being listening。嗯。Then we terminate the connection。

And if we are listening， we go to soon received。Yeah。And we set the。

Acknowledgement number to the sequence number that we get from。Ass a message。Yeah。

But that is in big Indian， so we have to switch the Indians again。😔，And we have to set this plus one。

😔，I can tell you this was really something that made me go crazy with this plus one。

 which I didn't have there for some time。ItTook me quite a while to figure out that it has to be there。

So we set the sequence number again to this fixed number， which isn't a good idea but。😔。

Because of security reasons， but I will use it for now。😔，the socket is already and。😔，In our list。😔。

Then， we send。😔，S an act。And after that， we have to。Increase our own sequence number。Yeah。Okay。

 so if we are a server。We are listening。 We get as soon， we send us an a， okay。

That's what we are doing here。没。Yeah。嬉しい？よし。Yeah。So much coat。If we get a an act。😔，Yeah。

So we should only get a syn act if we have sent a S before。😔，And otherwise。

 we terminate the connection again。Yeah。谢。So then we set the connection to established。😔，嗯。Oh， yes。

Then we have to do the same thing we have to set。😔，And the acknowledgeknowment number。

Two is a sequence number。Plus one。Increase our own。Sequence number。Okay。

And then we send the acknowledgement。That exists， okay？So。We have synchronized。

 we have synchronized knowledge。😔，嗯。Then there are two cases that are just illegal。

You cannot synchronize and finalize in the same message。Yeah。So in my implementation。

 I did the finalization a bit Hackish。😔，嗯。

![](img/89a8340e49453b1571211dc28a08e296_3.png)

So， because。Because as I've set the acknowledge and。Finalize could be in differentfferent。

It could be indifferent。😔，Messages。I implemented it。So， that。

Fin and f act are basically treated in the same way。And in both cases， I mean， if I get a f。

 I should send a fin and an egg。And if。I'm on this side， and I receive a thin or thin egg。

That was an asenddon act。So， but， but it's okay to。To include the f also in this message， so。

That's why I did it so that in both cases。嗯。I go to some common state of， yeah。

 I'm currently closing and sending F plus act both。



![](img/89a8340e49453b1571211dc28a08e296_5.png)

Yeah。Yeah。Yeah。So in this case。😔，Yeah。Yeah。あ。Yeah， if。If I'm currently established。

 then I wouldn't get a thin egg in the first place。Unless the other one wants to disconnect。

So that means I am going to F weight1。😔，No， I don't go to Fin weight one。

 Fin weight1 is where I go when I disconnect myself。嗯。In this case， I go to close weight。Yeah。

So when I was established， I get a film。Then I sent an acknowledgement。は。And。Fin after that。Yeah。

So if we are in close weight。😔，That means we had gotten a fin have sent。嗯。Acknowledge。

And our own thing。So。Now， we should get just the acknowledge。Yeah， this。

 this should actually only be an acknowledge， but。But whatever。

 So we will also talk about that case in the。In the case。In the acknowledged case。O。嗯啊。He。因为。

So we had cotton and we have sent a thinin act。😔，And now we receive the last a which could also contain a thin act。

Could also contain a fin。So we set this to closed。😔，嗯。Yeah。Yeah。Yeah。So this is a final state。

In this case， we said removed to true。😔，Actually， know thats nonsense。😔。

So if at the end of the handling， the socket is closed， then we will remove it from the。

From our list。And we retrieve that by setting it closed here。😔，Thank。And it's。If we get a F a。Well。

 we are already in。Let's that。If we are in Swe1。😔，We sent a f。 We receive a thin a。

 that means we have the thin and the X。 So then we should go to time weight。

 but we don't actually do the time weight for because it would take too long to implement that now。

 so then I would。😔，有。Yeah。So this means the other guy wants to disconnect。

We acknowledge that and then we get his acknowledgement and just set the state to closed。Otherwise。

 if we have sent a f， then we receive possibly a f act or a single f。But that's。嗯。These are both in。

嗯。Both in this case here， so。Yeah。Yeah。嗯。So we have sent a fin， we have received a F act。

So we just have to send a final a。And removing it from the lister done later。😔，い。嗯。Okay。

 so then we only have two cases left the acknowledge if we get an acknowledgement。And if we。

 if there isn't any of these bits set。 So， so it's not a。Message that controls the。

Behavior of certain。Of the socket。So this is really。The case where we。嗯。

Where we really handle the data， so we pass it to the handler。Okay， so we received an act。😔。

So if we were in S received。😔，That means we were listening before。

 We had gotten a sin sent a sin act。 And now we have gotten the final act。 So that means。

We now go to the established。From a state。If we were in thin weight1。😔，Then we go to Fin weight 2。😔。

可。So that means we get the thin and。A in different messages。And if we were in close weight。😔。

This is strange。There seems to be some mistake。😔，I mean， when we send。😔，The data we already increase。

こ熬。We already increased the sequence number by the size， but actually。

The sequence number should be set to。As the acknowledgecknowment number in the。Acknowledge case。

But whatever so。So if we are close weight。You receive a fin send you。😔，Okay。You receive a f。

 send it back。Then we send another thing。😔，And receive another a。 So actually， close weight should。

Shouldn't actually exist。Because we sent both these messages at once anyway。So because of that。

 I will just。Remove the state。よし。う。Okay， so now we go to the case where we actually handle the data that we get。

 so we pass it to the handler。Yeah。So we compare the sequence number of the message that we get to our own acknowledgement number。

 if they aren't。系啊。Identical， that means the packets have arrived in a different order and。嗯。Yeah。

 we cannot handle this yet so。😔，うんうん。Yeah。And I will。Have this handr。😔，Return a above。😔。

And the bulling that we get from it。Will tell us if we are supposed to。嗯。

If we are supposed to reset the connection after that， so the。

The protocol that or the handlers that we talked to might say can now say， hey， kill this connection。

 okay？In this case， it would say true。Which means keeps the connection alive。So after that。

 if we don't reset if we don't。Reset， then。Then we acknowledge the data that we've got。没。Yes。Yeah。

 but we don't add the。Total size， we add the payload size。Which is size。No。

We have to look at the header size that is written in the header。😔，Yeah。So， we acknowledge the。

The length of the payload that we've got。😔，Yeah。は。So we pass the data to the handler if it says we should keep the connection alive。

😔，We acknowledge Sir。Data that we've received。い。Okay。Okay， before we start handling this stuff。😔，No。

We will check the message for the reset flag first。And in that case。😔，い。If the socket is not zero。

Yeah。Yeah。不。So we will only go into this handling here。😔，Yeah。So if we get a reset， we set the。

Soocket to close directly。 Then we don't get into this switch。Into these switch switch cases， and。

Instead， we will just remove the socket from our list。Yeah。Okay。So what systems in TCP sometimes do。

😔，This。They sent you data together with an acknowledgement message。嗯。

I'm really wondering about my code here at this point， because。😔，Oh妈。So， if。Yes。

 the question is what kind of an egg is set， so。If we， if it's a synac。😔，I mean。

 when can we get an act？As a response to a cac。In that case， we don't go any further。😔，Then。

 we return false。I don't get what where my code works like this here。😔。

So what I've written in my code is。So for the piggybacking， this is called piggybacking you send。

Your data and with your data you also send。And acknowledge to a previous message， so。嗯。But。

But why do I have， I mean， what I have here is。If the message flags。😔，Is just an acknowledge。

And nothing else。Then I break out of this。 so I don't go into the default case。

 but that doesn't make sense I mean。😔，I think it should be。😔，If it's not equal to act。

 because if act is the only bit that is set there。Then there might be some data piggybacking。

I don't know， so I think it should be like this。😔，But the point is that I don't always break at this point。

 So if I get an egg， which is。嗯。嗯。So then usually if I only have one。😔，X then。

Then I give this also to the handla。😔，Okay， then we also need some code for the reset。嗯。

I was just is terrible。😔，Because the reset might not have。

IMight not have a corresponding socket attached to it。😔，All we can do actually， is with return true。

Returning the。嗯。The data blocks that we have received ourselves。

But then we have to do all this stuff with。With a pseudoo header again， so。哎。I don't know。

So in the kernel， I'm going to make a copy of the UDP handler。Oh。他。よし。嗯。Yeah。Yeah。O。嬉しう。



![](img/89a8340e49453b1571211dc28a08e296_7.png)

So I'm opening a server again。

![](img/89a8340e49453b1571211dc28a08e296_9.png)

谢谢。

![](img/89a8340e49453b1571211dc28a08e296_11.png)

嗯。や。I'm not getting the。The result here。I mean， the connect seems to work。😔。



![](img/89a8340e49453b1571211dc28a08e296_13.png)

![](img/89a8340e49453b1571211dc28a08e296_14.png)

Yeah。Yeah， I don't know。So I'm clearly。😔，To exhausted to continue with this right now。So。



![](img/89a8340e49453b1571211dc28a08e296_16.png)

So， but yeah。I will。Make another video apparently looking into this where this didn't work right now。

 but。Yeah， as I've said， I'm just too exhausted right now， so。So just tune in next time。😔，Yeah。

 this kind of frustrates me now， but。So don't like this video， okay。

But still subscribe so that you don't miss the next video when you。

When we will see what the problem was and。Yeah， so we'll see you next time， right？



![](img/89a8340e49453b1571211dc28a08e296_18.png)