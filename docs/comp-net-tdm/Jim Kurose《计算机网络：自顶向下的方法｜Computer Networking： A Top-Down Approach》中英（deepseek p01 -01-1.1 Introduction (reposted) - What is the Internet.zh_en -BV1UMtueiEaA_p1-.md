# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p01 -01-1.1 Introduction (reposted) - What is the Internet.zh_en -BV1UMtueiEaA_p1-

Well welcome， this is where it all begins， section1， chapter one。And in this first video。

 I'd like to do basically three things。 First， I'd like to give you a broad brush overview of what we're going to be covering in this introductory material。

 and hopefully you've already seen the video about the course as a whole。 Secondly。

 we're then going to just dive right in。 We're going to ask ourselves two questions。

 What is the Internet and what is a protocol。Well let's jump right in and let's get started and let's first talk about what's the goal of looking at this introductory material and really there are two goals here first is to give you a broad brush view of computer networking so that you can see the big picture and secondly we'll be introducing a lot of vocabulary now I can absolutely promise you everything we're going to be covering here in this introductory overview is something you're going to see in a lot more detail so you can just sit back here。

 relax， look for the big picture view will come back to this material again so sit back。

 relax and enjoy this introduction。Here's what we're going to cover in this introduction and overview。

 which corresponds to Chapt 1 in our textbook。 We'll start with where we are here with an introduction and asking ourselves two questions。

 What is the Internet and what is the protocol。 and that'll get us started。

 Then we're going to dive down into more detail。 We're going to start at the network edge。

 We're going to look at the hosts at the access network and the physical media that make up the Internet in more detail。

 We're then going to dive down into what we might call the network core。

 We'll talk about two technologies used to build networks， circuit switching。

 which is what the telephone network is traditionally used。 and packet switching。

 which is the technological basis for the Internet。 We'll talk about packets。

 routers and switches within a packet switch network and we'll talk about network structure in particular。

 We'll see what we mean when we say that the Internet is really a network of networks。

 We'll also talk about network performance and see how packets can be lost or delayed。

While being forwarded from source to destination， and we'll talk about throughput as a performance metric。

 the rate at which bits can be forwarded from source to destination。

 We'll spend some time talking about protocol layers。

 which is a way to decompose and structure our discussion of an incredibly complex system like the Internet into more manageably sized pieces of our discussion。

 and we'll talk about the service model provided by a network。

 We'll spend just a bit of time overing network security and the history of computer networks。

 which actually started a long time before the Internet came into being。

 So that's where we're headed。So let's next ask ourselves a seemingly simple question。

 what is the internet after all， and of course the answer to that depends very strongly of course。

 on who you ask， and I thought I'd start off with just a clip from a BBC comedy that I just finished binge watching that addresses this question。

What is it？This Jen。It's the internet。that's right， This is the Internet。The whole Internet。よ。

I offer a loan of it so that you could use it in your speech。It's so small。

That's one of the surprising things about it。Hang on。

 it doesn't have any wires or anything It's wireless。Oh， yes， everything's wireless nowadays。

 isn't it。🎼And of course， if you ask kids， you can always get some amazing answers as well。

 It's sort of like a robot in your house that does lots of things and everything for enough for no money or anything。

And then there are some people who sometimes mistake the internet。

 which is really an engineered artifact like a roadway or a telephone network for the people who use the internet。

 as in this recent headline here from the Washington Post as if the Internet is some thinking entity。

But we're engineers， and so let's take an engineering view。 and here we can take two viewpoints。

 Our first take here is going to be very much a nuts and bolts approach。

 If you're going to tell me about something， tell me about the pieces。

 What are the components of the internet。Let's begin at the edge of the network and work our way in At the edge of the network are the devices that Internet users like us use to connect to the Internet。

 There are literally billions of devices connected to the Internet。 While often call these devices。

 hosts or in systems， and there are tons of different types of devices that can be connected to the Internet。

 Of course， there are computers， our own personal computers， computers and data centers。

 as well as smartphones connected to the Internet。We've got internet connected gaming and media streaming devices in our home。

 we've got digital personal assistance， security cameras， energy monitors。

 appliances like refrigerators， washers， dryers， picture frames。

 and even your mattress can be connected to the internet。

There are personal health and fitness devices and human augmentation devices like ARVR glasses Ves are also connected to the internet。

 For example， your car well not mine and maybe not yours， this is a Tesla， there are trucks。

 scooters and bikes connected to the internet and one of my favorite devices of all time and actually the oldest of everything that you see here is a toaster that's connected to the internet and it downloads the weather forecast and burns that forecast into your toast。

 this was actually a masters project in the early 200s at a university in the UK and there are many。

 many more types of devices and really for anything that's digital。

 there's probably some value in connecting it to the internet and for other formerly。

 say analog devices like bikes and scooters giving them a digital footprint and internet connectivity enables new types of use。

Moving deeper into the network， we find the devices that make the network actually a network。

 what we'll call packet switches that forward packets。

 chunks of data between each other and between hosts and end devices willll see that there are two types of packet switches routers and switches and well learn a lot about these and then there are the numerous communication links that interconnect the routers。

 switches， hosts and end systems， and finally these links routers， switches。

 hosts and end devices are all assembled into networks。

 each of which is owned and operated by some entity。 For example， here on the UMass campus。

 we operate our own campus network， and this UMass network is different from the internet to backbone network that connects a networks on other campuses and it's really the existence of these multiple networks that gives rise to the saying that the Internet is a network of networks。

And as we'll also see again and again throughout this course。

 the sending and the receiving of information among routers， switches， hosts。

 and end devices is going to be controlled by protocols。

Everything that happens inside a network is governed by protocols。

 protocolcols are everywhere in a network。 Yes， this is a course about principles and practice of networking。

 it's also a course about protocols。Because protocols describe a standard way of doing things。

 there needs to be a body that defines these standards for the internet。

 the Internet standards and internet protocols， that defining body is known as the Internet Engineing Task Force or IETF。

 and their standards are known as RFCs requests for Commons。Well。

 that's a very nuts and bolts approach to what the internet is。

 and the second way we can answer this question is really by taking a more services point of view and to think of the internet as a platform upon which all of these wonderful applications can be implemented。

As a service platform， the internet provides an interface that applications can use to send and receive information to each other。

 and that in a nutshell is really what the internet's all about from a service perspective。

 The delivery of information from one point in the network to another Now all those internet applications residing at the endpoints can be incredibly complex and sophisticated。

 imagine that by talking into your control for your TV。

 a streaming movie starts appearing on your screen。

 can you imagine all that goes on in the applications to make that happen。

But that application level complexity sits on top of a basic service infrastructure to simply deliver packets from one location to another。

 all that computing happens in the applications is that part of the internet well， yes。

 in some ways as we'll see， but we'll be focusing more on the information delivery aspects of the internet than on the structure of those sophisticated distributed applications but we'll cover a bit of this latter topic as well when we cover the application layer。

Well I'd like to wrap up here by coming back to this notion of protocols and I'd said the internet is all about protocols so what is an internet protocol and really one of the easiest ways to think about internet protocols is to first think about human protocols you know I think humans execute protocols all the time here's an example of a protocol it's what I call the what time is it protocol I' do the time？

cuscusSo what's the protocol here， The human protocol for asking the time one person says， oh。

 excuse me， do you have the time and the second person then looks at their watch and responds with the time we see here there's a request and there's a reply Now you might think what are other human protocols Well。

 here's a good one that I always like to use when I've got students live and in class and it's called the question asking protocol So the professor says are there any questions。

 you know， professors love to get questions right and if you're a student。

 your part of the protocol then is either well， look down at your notes because you don't want to ask a question or look up at the ceiling or if you've got a question you raise your hand and then the professor says。

 oh okay great I've got a question I love questions。

 Student asks the question and then the reply comes back there you've got a multistep。

Question and answer human protocol。 So why don't you pause me for a second and just think about what other human protocols can you think of。

Well， hopefully you've thought of a couple of good human protocols。

 so for the protocols that you just thought of and the protocols that we talked about before。

 the question answer protocol and the what time is it protocol。

 what are the common things that we see in these protocols well。

 there are specific messages that are sent in the case of humans things that are said and there are specific actions taken when the other party receives those messages？

And computer network protocols are completely analogous to these human protocols。

 except that it's networked components， applications， host router switches。

 and links that are exchanging messages and taking these actions as dictated by a network protocol。

Let me give you an example in the human what time is it protocol， There are two distinct phases。

 There's the greeting phase。 where you talk with me， and then there's the request phase。

 What time is it and the response。 And as we'll see shortly。

 that's exactly analogous to protocols used on the web。

 There's a connection request phase followed by a request response phase。

And so with this as background， we can already come up with a pretty serviceable definition for network protocol that we see here。

 protocols define the format and the order of messages sent and received among network entities。

 as well as the actions taken on message transmission and receipt。

Okay well that wraps up our introduction to the introduction and what did we learn here well we actually address two technical things we talked about the question of what is the internet。

 remember we started at the edge and we worked our way in and we also talked about the notion of what is the protocol Now in the next section we're going to start taking a look more at this nuts and bolts type of approach to answering this question。

 what is the internet， we're going to start at the edge with the devices we talked about a little bit earlier and then work our way in。



![](img/ac526d8f21395d1a42292dbf14ef7d05_1.png)

![](img/ac526d8f21395d1a42292dbf14ef7d05_2.png)