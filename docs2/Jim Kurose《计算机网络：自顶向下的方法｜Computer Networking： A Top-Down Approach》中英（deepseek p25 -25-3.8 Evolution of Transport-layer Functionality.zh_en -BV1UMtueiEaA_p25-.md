# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p25 -25-3.8 Evolution of Transport-layer Functionality.zh_en -BV1UMtueiEaA_p25-

。Well， we're all done with the technical topics of the transport layer。

 so let's now do a little bit of crystal ballgazing and look into what the future of the evolution of transport layer functionality might look like。

The TCP and UDP protocols have been in place with a bit of changes for TCP for more than 40 years now。

 and so they've proven by 40 years of use that they provide a pretty simple。

 but maybe more importantly and arguably sufficient set of services to accommodate an amazing range of applications from the earliest internet applications like email。

 FTP and TNe to applications that didn't even exist when TCP and UDP were standardized， the web。

 streaming， voiceover IP， gaming， and more。Well， over the past 20 years。

 there have been a number of flavors of TCP developed for specific scenarios and some of them deployed in practice。

 but as you can see here in this table， these are sometimes fairly specialized environments。

 and it remains true that the TCP flavors that we studied earlier in this section really remain the dominant deployments。

Well， if you remember our discussions when we first introduce the transport layer。

 you'll perhaps recall some of the services the transport layer doesn't provide。

 support for real-time services or security in particular， and these are incredibly important。

 but they've been primarily added at the application layer。

 that's been in the form of application layer protocols and distributed application layer infrastructure such as content distribution networks and data centers and with application layer service providers connecting close to their customers Edge network。

We learned in chapter 2 that pretty much since its inception HTTP has been running over TCP， however。

 there's change offoot with a new version of HTTP that's HTTP3 building a lot of transport layer capabilities at the application layer and then running over UDP Let's wrap up here by taking a look at this。

Quick， which stands for Quick UDP Internet Connections。

 is an application layer protocol that's meant to sit underneath HTTP and run over UDP as we see here。

It's already seeing widespread deployment on many Google servers in Chrome and in the mobile YouTube app。

 it's also in the process of being standardized in the IETF。From a technical point of view。

 there's really not much for us to learn here because Quick adopts the approaches that we've learned about already in TCP for reliability。

 congestion control， and connection management。And actually。

 if you look at the quick draft specification， it says。

 quoteRead familiar with TCP's Los detection and congestion control， hey。

 that's us we'll find algorithms here that parallel wellknown TCP ones Well。

 since we've carefully studied TCP's reliable data transfer and congestion control protocols as well as flow control we'd be really right at home with Quick so we don't really need to say anything more about these particular techniques。

 but we should say a word about Quick connection establishment and how quick multiplexes。

 multiple application streams over a single quick connection like TCP quick as a connection oriented protocol between two endpoints。

 and so a connection setup a handhaking protocol is used to set up sender and receiver state for reliability。

 congestion control and security。What's currently done in HTTP is that a client first sets up a TCP connection。

 we've seen that takes a full RTT and then sets up a second connection on top of the TCP connection to do transport layer security and that takes another RTT。

 so overall two RTTs are needed before data can begin to flow。At the application layer and using UDP。

 Quick performs a handshake in just one RTT and sets up reliability， congestion control。

 and security state all in one handshake as shown here。

Quick also introduces the notion of multiple application level streams that are multipleed over a single quick connection and here's how we can think about streams in the case of HTTP3。

 you can think of end streams being set up one for say each of the N objects that need to be retrieved from a web server in traditional HTTP shown on the left here。

 multiple objects would be retrieved serially one after another from the web server the advantage of having multiple streams is that multiple web objects can be retrieved concurrently as shown on the right here。

Each of these individual streams has its own reliability and security。

 but they're all congestion controlled by a common congestion control protocol。

 which looks like DCCP， as you can see here。In this animation， an object's first retrieved。

 but there's an error on the retrieval of the second object。

 and so in the case of the original HTTP protocol， the retrieval of the third object is going to have to wait until the second object is requested correctly in the case of Quick。

 the retrieval of the third object can happen concurrently while the second object's error recovery is happening。

 as shown here on the right。When a unit of work is blocked， for example。

 the transfer of the second object here and that blocking stalls all of the work backed up behind it。

 that's called head of the line blocking。Well that wraps up our crystal ball gazing into the future evolution of transport layer functionality。

 and we're really all done now with the transport layer。

 so let's wrap up by summarizing and then taking a look at where we're heading next。



![](img/26cd0c5ac81fd1f74be9322788e0b1ca_1.png)

![](img/26cd0c5ac81fd1f74be9322788e0b1ca_2.png)