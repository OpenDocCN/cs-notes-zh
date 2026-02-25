# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p66 -66-#140 __ 67 Real Time Protocol (RTP) __ Session Initiation Protocol (SIP) -BV1UMtueiEaA_p66-

![](img/3d4e329c09f7bc5c6e1de422650dda4d_0.png)

![](img/3d4e329c09f7bc5c6e1de422650dda4d_1.png)

Good morning， everyone。 Today， we are going to start with the multimedia networking One more topic that is known as your protocols for realtime convert applications。

 So we are going to see RTP today and in the next class we are going to see the S So moving towards a slide。

 first of all， you have to understand what do you mean by RTP that is nothing but that is known as your real time protocol Okay so realtime protocol。

 what actually it is it does and how we are going to find out like on what basis we can have this realtime transport protocols and all So you know that it is an internet protocol because as the name specifies you it does a protocol。

 So definitely it is an internet protocol and also it will specify you some of the way of programs where we are going to manage the realtime transmission of multimedia data values that is nothing but your。

😊，or video data values and also you can transmit all these data values over any kind of your network services。

 it can be your Unicast， it can be your multicast， it can be your broadcast Okay。

 so you can transfer this kind of audio or video multimedia datas over any of the network services。

And one more thing also， I have already told you about Ie TF。 Okay。

 I hope you have remembered that IE TF what is a full form of that internet engineering task force。

 So what it will do， it will just request for some of the comments。 Okay， what is that RF。

 Can you see my slide， I have mentioned over here， RF 3，5，5，0， What is a full form of RF。

 that is nothing but request request for comments。 Okay， request for comments。

 So here if you want to request any of the comments， you have to use the code as 3，5，5，0。😊。

And also why RTP is used for this RFC， you can say that this RTP is designed only for these IETF audio video transports okay it is useful only for this audio video transport which also like supports for your video conferencing if you want to have with multiple destinations or multiple peoples that kind of things it is going to provide you the applications okay that's the reason this is also known as your internet telephony and remember one more thing that here this RTP it will be giving you the real time delivery of multimedia data that you have to remember it sorry it does not keep the realtime delivery of multimedia data because if it gives a realtime delivery multimedia data then it has to be encapsulated with your DCCP but as the RTP packet has been encapsulated with your UTP segments that's the reason。

😊，The real time delivery of data packets， you cannot guess。Fine。

 so that is the reason it is very dependent on your network characteristics。

 whatever the networks we are utilizing， it can be Unicast， it can be multicast， it can be anything。

 Okay and also it it used to manage all the data whenever it will reach from your sources to destination side。

 then it has to manage all the variety of data with the best effort or you can say best effort of data values because always we used to read that the data is whatever we are transforming。

 they will have one kind of your packet structure， which will carry the audio and video data or you can say multimedia data。

 So when this kind of packet structures has been organized and they have when they are moving from one place to another place that time what will happen is it has to like it has to transmit in such a way or it has to encapsulate all the header files in such a way that it to reach over them。

 So our focus。😊，Always be to find out the best effort or best performance out of that Okay and also one more thing here。

 I want to highlight that you can see here like RTP packet provides payload type identifications What is that payload type you know everywhere TCP UDP。

 we have the structure of them right TCP structure segment is their UDP structure segment is similarly in your RTP segment what happens is it will have the payload type okay it will identify the payload and also it will have the packet sequence numberings okay so which is packet number like sequence which which number it moves from one place to another place all these things has been organized and also there they have given the time stamping the time stamping is nothing but。

They will have within the time period to reach from your source to destination side Okay and also this RTP what what it will do actually you know that it runs from your all the end system end system in the sense it will run in your source and destination side and also you know that this one will as it runs in between the end systems。

 then definitely it will combine the data transport。 Okay。

 what is that that will be with a protocol fine it will be it is like what it will do it will just have or it will just monitor that in between your end systems。

 all the data delivery happening or not and also as we are using uncast and multicast network So it has to monitor over your large multicast it has to monitor on your large multicast that。

Large multicastard， the packets has been delivered properly or not okay so monitoring system like it happens in between your center side and in your receiver side to detect to detect if there is any packet loss happened or not or is suppose if any packet loss happen then it has to compensate for any kind of your deleteter that is a reason both the protocols。

 whatever is working in between your transport layer or network layer on network layer。

 they have to find out that if there is any kind of your any kind of your packet loss。

 then it has to be compensated with your deleteitter So in this way we are achieving the interoperability which is nothing but your like video conferencing or Y applicationss or over these rP has to run and all these things has to run together So that is a main work of your RTP。

 which may come。For your eight marks of question。 So it's not over。 Well move to the next one here。

 you can see。 I already told you this RP runs over your UDP and also it provides the interface of your transport layer and the network layer。

 So now here what we are going to do is we will have the RP libraries which will provide the transport layer interface。

 Okay and this transport layer interface extends from your UDP and if it is extends from your UDP。

 we should have the port numbers， the IP address C this is the like RP。 Okay。

 so how this one is working out in our sorry this is ouri layer how it is working。

 So this is our transport layer。 So in our transport layer。

 the RP library will be present with the UDP and also it has to carry your port numbers IP address payload identifications packet sequence numbering and all the time time stamping I have already。

Made you to understand what is the meaning of each so。

Here they are going to have the informations in your rTP header。 okay。

 the informations will be in your rTP header， which is already encapsulated with your UDP and also with all variety of your port numbers and I addresses。

 So what will happen the receiver what he will do he has to reconstruct all the data values and also he has to describe how you are going to have the coding and encoding process if all the data or bit streams has been passed through or if it has been packetized。

 okay so as for the rule here， the UTP will run or it will use this datagram protocol will use this rTP library and then it will transfer all the packet from one place to another place。

 So now let's take it one example suppose if I want to send 64 KBB of PCM， which is。

Ecodd voice over your RTP。 How I'm going to say that I have to use my application layer because it deals with that。

 So this year， the application will collect all the encoded chunks。 Okay， first， what it will do。

 it will encode all the data chunks。 So in I told you that it takes 20 milliseconds of time for each data chunk。

 So for every 20 milliseconds of data chunk。 It has to go for 1，60 by of data， right。

 for each 20 milliseconds time period，1，60 by of data has to be placed inside your chunk。

 So what other things we are transferring now， the audio chunk plus your RTP header value。

Program where the RTP packet has to be encapsulated with your UTP segment。

 So the two things we are going to transfer。 The first one will be your audio chunk。

 whatever the values are there， then the next one will be your rTP plus UTP segment here what will happen this RTP header what it will do it will just indicate you that which kind of your audio type of your audio encoding is present inside your each of the packet so that what will happen。

 it can change your encoding during the conference time whenever it is passing。

 it can change it So it will contain all varieties of your sequence number and your timet that has to be remembered and also you know that I have already explained you the sequence number sequence number means what whenever you want to use to find out to detect the lost packet that time you have to go through your sequence number because acknowledgement will receive with your sequence number。

Okay， then what about your here we have used a timet payload identification。

 What is a payload identification what it will do in the payload identification it has to describe the specific media encoding so that anything can be changed if it has been adopted with any various variation of your bandwidth or frame indications okay or if you want to start go for the starting of the like frame so end to end collections and on it is going to have and along with that it will also have your source identification source IP address。

Pt address。 So all the like the synchronization process， this timet， everything。 So what will happen。

 These are known as your RTP components。 Okay， if you will put all。

 So everything is known as your RP components。 So through this RP components。

 we have to move the packets or you can say that the multimedia data from source to destinations inside。

 So now how we are going to include the quality of service that is known as your Q O inside your RTP。

 So what will happen here， we know that this quality of service is nothing but it is a kind of your feedback。

 which we have to include whenever there will be a number of packet lost or how the round trip time has been organized or you can say that how the jter delay is there。

 Okay so the source has to adjust all these variety of data rates accordingly。

 So that thing what will。we have to calculate our QS。 that is quality of service。

 It's providing the best effort or not。 So that time we have to use our like you can say like if we have to use the mechanism where we can have the timely data delivery if we are not having the timely data delivery。

 then we cannot guarantee on our quality of service because if there is no data delivery。

 then the feedback definitely it won't be good So that is the reason we have to find out always what will be the data delivery with the time stamp and if it is not there。

 then there will be a no guarantee of your Qs and also this RTP encapsulation which encapsulated with your UDP values it will be always inside the end system So if you have any intermediate routers then it won't provide the best effort because there will be a special effort。

😊，Whi when the RTP packets will arrive to your destination side so that will be your timely manner things。

 Okay， so it will en all the synchronization process in the intermediatemedia and it will try to separate all these transmitted audio and video streams So that is a reason it won't provide that much of like a special effort towards your rTP packets。

 So here you can see your rTP header。 okay so what is your rTP header。

 this is a structure of your rTP header already we have discussed。

 we will have one payload identification time， which will carry the seven bits of data。 Okay。

 and if any sender changes any encoding during a call then the sender has to inform these things to your receiver side。

 So we have some of the payload identification named like 0，3，7，26，31 and 33。 So if you have0。

 then you can understand that it is a PC。😊，connectivity and with the 64 KBps data values。

 if it is a3， then it is a GCM connectivity and 13 KBps。 So similarly。

 we have given some of the payload types So it will indicate that which type of encoding is currently being used if the send wants to change this call during the call anything encoding values。

 then the send has to inform to the receiver so that the transmission will be successful。

 Now the next one is your sequence number already you know the sequence number。

 what is the meaning of sequence number， whenever we will send any packets。

 each packet has to be acknowledged which some of the sequence number So if any packet will get lost or something happens and we will come to know that okay that sequence number has not been received in the send some packet lost is there。

 So it will helpful for theP packets to send from your one site to another site and also we can restore the packet。

😊，Sequence， and it carries 16 Bs of data。Similarly， timest is there。 And what is your timest。

 This timest is nothing， but it carries your 32 bit long database。 Okay。

 and it it will helpful for you to sample all the data RP data packets so that whenever we will send for audio whenever we will send or we will just read any time period。

 So within that sampling period， the data or the audio has to reach inside your receiver end。

 and also if there will be like if any application generates any kind of your chunks。 Okay。

 then what will happen， it can encode 160 samples。 Okay， then that time。

 the timet will increase to 160 for each RP packet whenever the source will be activated。

 fine so depends on your chunk value， your timest will get increase and if suppose the times this kind of timest has to continue。

😊，It will continue in a constant rate。 okay if the source is inactive because it has to finish this 160 encoded samples。

 So that is the job profile of your timet。 So next one is what is that synchronization source I that also carries your 32 bits of data what it will do it will just identify you that the source of RTP stream and also each stream in your RTP session。

 How distinctly it is like your like synchronization suicide。

 So it is going to identify all the source of your RTP stream。

 So then the next one will be a misceaneous fields which carry some of the data values or error data fields。

 or if anything is that it's going to carry over there。 So this is a structure of your RTP header。

 So now you can see here the RTSP or RTP programming assignment how we are going to do the rTSP or RTP programs。

 So how we are going。😊，To do the first thing is the server has to encapulate encapsulate with your stored video frames。

 So if it has been encapsulated with the stored video frames。

 then it can be transferred like your RTP packets。 and if we have any video frame。

 then we have to add the RTP header into that。 and then we have to create the UDP segments。

 and then we have to send these UDP segments towards your UDP sockets and and then what will happen whenever any packet things we are going to send。

 it has to carry the sequence number and the time stamps。 Okay then only all these things。

 the client side will provide then we have to write the client side program。

 and we have to issue any of the commands if you want to play or pause that commands we are going to give then the server side of your RTSP is going to provide you all these data things。

 So these are the way to write the program。In your client side and in your server side。So now。

 what do you mean by real time control protocol， There is one more like a concept is there。

 which is known as your real time control protocol。 So what will happen in these is。😊。

Suppose you have any conjunction with your RRTP。 Okay， so that time what you are going to do。

Like if you have any participant in your RTP sessions。

 which you want to send the RP control to all the packets And also that time how you are going to do。

 So that is a major role will be played here and also here what will happen this kind of your packet。

 it will send to your all of the variety of your participants。 Okay。

 so the major role of this one will be， it will have one packet structure。 Okay。

 which has to be defined under your RF 3550， whatever I already told you。

 So then what will what it will do， it will have one control information about all these RP sessions。

 So it will have the authority to send to deliver the packets or multimedia data but it will not transport any media data by itself。

 Okay， so the primary focus of your RCP will be。LikeOn your quality of service。

 how quality of service you are going to provide when there will be media distributions。 Okay。

 so you have to periodically， you have to check all the transmission transmitted packets and round trip delay time and the packet delay variations all these things you have to check it out over your streaming multimedia sessions。

 Okay then then only it can carry or control all your quality of service parameters because if you can deliver the packets properly。

 then there will be a loss of packets and where the feedback will be like it will be not under the control。

 So to increase your performance and to increase your like bandwidth and everything you should have the feedback on quality of service properly。

 So that is nothing but about your realtime control protocol whenever you are going to send the packets。

 you have to send a number of packets， how many number of packets lost how many number of packets。

How many number of packets has been received and what will be your deleteit So all these things has to be carried out inside your RTC。

 So if you if I told you already we have to send all these things on on your like multicast or uncast or broadcast network services。

 So here the RRTC provides your multicast。 So here you can see the center is there。

 this is a network service and decide side it is a receiver。

 So what will happen here each in your each RTP session a single multicast address has to be there。😊。

And also all RP and rP packets， they have to belong with your multicast address。

 Okay multicast in the sense， you can send the packet from your like from sources to many destinations multidestins So that is known as your like a multicast address Unicast in the sense only particular one server and one receiver will be one client will be there okay so that is a difference between your Unicast and multicast address so here you are going to send all the rTP and rCP packets on your multicast address。

 so it can have one sender， but there will be a multiple address where the data can be sent okay so here another thing also will be there it will have the different different port numbers。

 distinct port numbers and it is going to distinguish the packets and the rCP will help to rTP to distinguish the port numbers and to send over your RP traffic。

😊，So whenever we are sending the packets over your ric traffic， we will have to just measure that。

 it will be a limit traffic so that the number of conference participants will get increase。 Okay。

 so it is each participant will reduce your ricip traffic and it will have it will increase the conference participants so here you can see the diagram Rp and ripP is moving now。

 So from here also rP and rP packets will move to the networks。

 so there will be a RP packet types there will be a receiver report packets。

 there will be a send report packet， there will be source description packets。

 So whenever we will have the receiver report packet that the fraction of your packets will get lost and the last sequence number will be achieved and also we will have some inter arrivalval jter or you can say that delay jter find that will be occurred inside your receiver report packets What will happen inside your send report。

😊，Se the report packets there will be stream of your rTP packets。

 which will have the current time and the number of packet sense and the number of byte cents。

 Okay and inside your source description packet there will be your email address when the send and centers name will be associated with your rTP stream and then they have to map with your SSRC and then they have to send with the user host name So it provides the like the mapping in between your SSRC and also with the host name So this is a packet types inside your rTCP so now what is happening inside your rTCP the stream synchronization So how we are going to do the synchronization inside your rTCP。

 So here what will happen is。Suppose if you want to send the multimedia data streams within a RP session or if you want to have the video conferencing。

 then each send has to generate 11 rP stream or video okay or you can say11 stream of your audio。

 So there will be given the timests within that RP sessions。

 and these RP packets will tied to the video and audio sampling clocks。

 Okay so whenever will say indeed they will not be tied with a wall clock time that you have to remember。

 we have to give the sampling clock time period over there。

 So whenever it will go through your RPCP send， then the report packet will contain the like recently generated all the packet。

 which is already initiated or associated with your rP stream So that's the reason it will have the timest of RP packets。

 Okay then the receiver will use this association of synchronization play out。

Of your audio and video and the audio and video can play in the receiver end properly。

 So this is known as your rTP synchronation method， which used over your rTP stream of data packets。

 So this is about your rCP synchronization method。 Now what is how if we are sending the data packets in such a way。

 Then how we are going to have the rP bandwidth and scaling。

 So here the rTCP will attempt all the limits of your traffic。

 like to 5 percentage of session of bandwidth and。 then what will happen like some example。

 suppose one send is there sending video or two mps of data。

 So that time the rTCP has to attempt within the limit period and it has the traffic will be0 kps。

 So it will give you 75 percentage of rate to receivers and the remaining 25 percentage to your your send。

So 75 Kbpss has to be given to your receiver side。And then all the receivers will gain the get the artisticP traffic。

 Okay， at 75 Kbps right， that has to be there。 So 75 kbps has to be equally distributed among your R receivers then all the sender will get the artistic traffic with 25 kBps because I told youa 75% will go for your receiver。

 So 75% has gone for your receiver another 25 kbps whatever will be there it will go for your sender size。

 So if it will go like this， then only atip can attempt the limit of your traffic of5 percent of your session bandwidth。

 then what will happen。 then the participant has to determine that artisticip packet transmission period。

 and then the packet size， the average packet size， which has been already given over your sessions。

 then it has to divide by your allocated rate then here only allocated rate So then only what will happen then we can calculate。

😊，bandwidthand， which is occurring inside your RTCP。 So that was all about your RTP。

 Now we have moved towards your SI that is known as your session initiation protocol So what do you mean by session initation protocol so it is quite simple and we have to because this is also can come for your eight marks of question so and we all know that this SI is nothing but it is a signaling protocol okay it will give you the signals and where it will give it will give over the web okay and it will like define all the message in between it has to maintain all the messages in between the center to receiver side。

😊，Right， so first it has to set up the call， then it needs some of the like if Ill give you one example。

 So telephone calls you can see right So in telephone calls， what will happen。

 first it has to set up the call then it has to find out all the details of two telephone talking who are they then the call has to set up and the phone enters into a data transfer phase right So whenever the call will be there by using this protocols and all in the then it will move the voice packets between your two phone call right So in this world the voice is not using we are using we are have gone for the video conferencing that is known as your voice So now this S is a call set up protocol which will operate on your application layer okay and also it will be very flexible protocol because it will go into the depth and it will just find out the modulations and everything it will be a very。

😊，Clean and clear because it will use the general proposed way to set all the realtime multimedia sessions。

 Okay in between the send and receivers。 suppose if I want to give one simple example also whenever the SI will set up this telephoneic call that time video and audio will have the multicast meetings。

 Okay because it is a single server and multiple clients。

 So it will have the multicast meetings and then it will send the instant message right so here what we are learning that SI is a term where we can have the telephone calls but video conferencing is a term where we have used on the multicast network services So the people can be identified by their names or email address because video conferencing through video conferencing you have gone through your name or email address right you have login into that。

So it is quite different from your S so it will just reach with your callers those who wants to like join with the call and not with the IP device says So that is a simple term of your S So how S services are there so we will have the mechanism only I told you first we have to set up the call then for caller to let know that who wants to establish the call then the caller and call can agree on media types like encoding then end the call okay whenever it will go on then they have to determine the current IP address because it has to map with yourneonic identifiers it ident address of your IP address so they have to determine the current IP address and how they are going for the call management they have to add the media files multimedia files during the call then they can change this by using the code code in the sense coder and encoder streams。

Then they have to invite others， and then they can transfer the call or they can have the whole call。

 So these are some of these S services， which has been provided by your S。

 So you can see here the example。 now Alice is there having one I address。

 Bob is there having one I address So I'm inviting Bob of which address this is my IP address。

 So this is my IP4 address I have given this is my address。

 which I'm given and this is my multimedia or your profile right So for the port number I have just sent it。

 So it will have inside my bo's terminal rings So now 200 we know that 200 means okay the connection is like established right it will indicate his port number and IP address and then it will prefer the like encoding part then it will send to the particular port number then the SI messages can send over your acknowledgement if it is having the TCP or UDP。

😊，s goinging to send over。 Then what will happen。 We can send our audio or multimedia audio or video files about that through each the。

It will create the S port number and it will transfer the Orion video in between the client and server。

 or in between the Alice and Bob。 So in this way， we have to set up the call to know that how the I addressr working out。

 So this is an example of your S So if you want to setting up a call like how youre going to do。

 So if you want what I told you code right So code or and encoded negotiations。

 supposeupp Bob doesn't want to have this encodecoding part。

 So what he can reply instead of replying with the 200 okay it can say that it's not6 not。

 So it means that he is not interested to have the establishment with the Aliies。

 then it can accept the reply and list the encode things and all。

 then Alice can send the new invite message those who are advertising that like we want to have the establishment because there will be a n number of clients who want to have like。

Transmission of packets so they can have the different encoder process。

 And through which they are going to join。 And suppose one more case， it can be alike。

 it can reject the call in between。 So the bo can reject the call by replying busy gone payments required or something like that。

 So that time， the media has to send this kind of like reject message over your AP stream or you can utilize some of the protocols。

 So these are at some way of transferring the call from one place to another place Here you can see another example of S。

 here we have written this one。Whatever in the diagrammatic way we have seen。

 the same thing we have written by using a SD TP message sentax。 So what is a message first。

The inviting will be towards this mail I where SI message with the ver name 2。0。

 then via what we are sending SI vername UDP this is a send address Okay So then from whom it is coming from this is the mail I to this is the mail I call I is this one content type will be application。

 then content length will be 885。 then you are sending here IP4 IP address I have used the vera for and then I have this address to where Im send address。

 then here you can see the audio message。 Okay so this is like and also this SDP means session description protocols okay or it is the application protocol So it will have a unique call I and through which the bos I has been intermediatemediated and the Alice wants to send the message by using this S T。

Message syntax， So it is very easy to remember。 it is not difficult to remember just you once if you will go through this。

 you can it will be easy for you to remember。So now how we are going for the name translation or user locations。

 supposeuppose one caller wants to call the call。 So how the caller name or email address。

 how they will find out。 So first， they have to generate the caller names and email address。

 then it has to generate the I address with the current host name。 Okay。

 if you want to go for the DSCP protocol you can attach that。

 Also will have the different IP devices like your PC smartphone and any of the card devices。

 What will be the result of this。 the result can be based on your time of day。

 it can be your it can be your home place anything。

 So the caller don't want where you are like in at home or office or anywhere because it does the location doesn't matter。

 Okay， only the name is name matters。 So the status of call can be sent by a voice mail that if you are already talking with someone or something like that。

 So that it will give you the Pps sound and it can give you the message like。You are busy。

 so that in the location doesn't matter。 Only the name and the message matters a lot。

So now how we are going to have the SI registergistrar。

 So here we will have the SI server that is known as your registrar when the bo wants to send any of the S client。

 then client sends the S register message to your Bob's registrars server。

 So how the register message will be looked like you can see the registrar。

 this is a domain name with a ver name you are sending through S message wasname UTP。

 this is the address from and2 then it expires within this 3600 time period This a timest。

 So in this way the registrar can send a message over your S server。

 And if you have the S proxy how you are going to work out that is again one more S server。

 but it will be like a temporary S server。 So here suppose Ali sends any invite message to her proxy server then it will contain the address S I。

What will happen， the proxy will be responsible for routing all this S message to the code and also it will have the multiple proxies。

 So whenever the bo sends any kind of your response back to your same set of your S proxies that time it will return the S response to the all because it will contain the bos address then it can have an with your local DNA server with your TCP setup So in this way the S proxy will have one S server we with multiple addresses and all and they are going to contain all the they will be responsible for routing all the S messages okay。

😊，So here you can see the S P example。 Okay， so here this person calls to this person。

 So first what we are going to do， the first item will be this is the IP address where the Jim sends invite message to here S I proxy。

 Okay， next， what we are going to do。 We have to send this proxy message we have to forward it to your poly S I registrar。

 It is a server。 Then here what will happen。 the poly。

Server will return a real direct message that yes that it should try to connect with this S because you can see this Ucom。

 whatever has written here it has been this is a registerstrar。

 So next what will happen He will send directly the request to this you come register server。

 So whenever you are sending anything the server name has to be mentioned sent over here here it is has written that two S proxy So we have sent here。

 then two Po register we have sent here Porear told that don't send to me send to this newcom S register then we have sent here then youcom register forwarding the invite to your running with your S client because normally you want to send a data packet from here to here。

 So in this way we have send the packet from media or audio files from your send site to your receiver site。

 then it will send you the acknowledge back which has gone through this the response and it has been raised over your send site so you have to draw。

😊，This kind of diagram， whenever the question being asked with an example。

 So here the data flows will be in between your send to receiver site。

 Okay so if you want to go for the comparison stage with your point3 to3 then here H3 point H。

323 is another signaling protocol for your real time interactive multimedia okay it will be complete and it will be integrated with many of the protocols where it will have some video conferencing signals registration process admission control transport or code so it will have a single S components which will be associated with your RTP and also it will not mandated okay it can be combined with other protocols also so it will be away from your I to U telephony it will just comes from your IETF which already we have described already discussed before it will。

Have the concept of your h TP and also like it can use the KISS principle that is keep it simple stupid principle so it uses all this variety of your protocols to find to have the comparison in between your SI which is very important so you have to remember all these things and with this your rTP and SI SI concept gets over I hope you people understood this the question can come in any way so there will be eight marks of question on the same topic so please go through the slide one second to have a clear idea Thank you。



![](img/3d4e329c09f7bc5c6e1de422650dda4d_3.png)