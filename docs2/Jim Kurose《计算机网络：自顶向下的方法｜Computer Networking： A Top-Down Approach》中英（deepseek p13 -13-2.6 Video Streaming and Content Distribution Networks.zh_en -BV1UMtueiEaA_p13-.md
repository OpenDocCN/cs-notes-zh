# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p13 -13-2.6 Video Streaming and Content Distribution Networks.zh_en -BV1UMtueiEaA_p13-

In this section we're going to move away just a little bit from our focus on application level protocols and focus on application level distributed infrastructure for implementing a service。

 the service that we're going to want to take a look at is video streaming It's an application we all know and love and probably use a lot there's some amazing examples of very sophisticated distributed infrastructure to implement video streaming services so there's a lot to learn we're going to start off by looking at video as an application and then as we've seen the internet can introduce variable delays between a sender and a receiver so we'll take a look at client side techniques buffering and adaptive play out to mitigate the effects of variable internet delays then we're going to take a look at something called dash dynamic adaptive streaming over HTTP and we'll see how dash can be used to accommodate changes in available capacity available bandwidth between a source and a destination。

We'll look at an example of dashash and use， looking at CDN's content distribution networks and Netflix as an application。

 so there's a lot to see， a lot to learn here， so let's get going。

Streaming video traffic is a major consumer of Internet bandwidth by some estimates。

80% of residential ISP traffic is streaming video traffic。 Now， when we think about streaming video。

 A couple of challenges are going to be apparent。 As always， there's the issue of scale。

 We're going to want to be able to reach tens or hundreds of millions of users。

 The second challenge is that of heterogeneity。 Some users are going to be mobile。

 Some are going to be fixed， Some are going to be on high speed broadband connections。

 other are going to be in bandwidth poor connections。

 How are we going to cope with that kind of heterogeneity。 And as we'll see。

 the answer is a very sophisticated application level distributed infrastructure。😊。

Let's start our discussion a streaming video by looking at the structure of video itself。

 A video's just a sequence of encoded images， sometimes called frames taken at， say 24。

30 frames per second。 And each image is a matrix of pixels。

 Those pixels are usually encoded to reduce the size of the images。

 and therefore reduce the size of the video by exploiting image redundancy。

 Theres spatial coding that exploits redundancy within an image。 For example， in this image here。

 rather than storing n repeated purple sky pixel values。 we could store the single pixel value。

 purple and the number of repeated instances。 That's two values to encode that part of the image rather than n。

 That's coding within a frame。 We can also code between frames。

 If the image doesn't change much between frames or changes just a bit。

 we can then just send the changes between frames， for example， rather than the entire new frame。😊。

And there are two broad classes of video encoding methods。

 Con bit rate video and variable bit rate video。 And as the name suggests in constant bit rate video。

 the video recording rate over time is going to be fixed constantant。

 And with variable bit rate codinging， the encoding rates going to change over time as the amount of spatial and temporal correlation changes over time。

 We see here a number of encoding standards whose encoding rates range from Mpeg 1 at 1。

5 M B per second to M peg 4， which is what were recording these videos in， for example。

 that can run up to 10 M per second and higher。😊，Now。

 when we think about the technical challenges associating with streaming stored video。

 there's going to be two sources of complexity here。

 The first has to do with the fact that the amount of available bandwidth between client and server is going to be changing over time。

 there could be congestion in the home network and the access network， the core network。

 the network within the video server complex or within the video server system itself。

 So the amount of available bandwidth is going to vary over time and we're going to need to be able to adapt to that。

 Secondly， we've seen that the delays between a source and a destination in the internet between a client and a server are also going to change over time。

 It's not like there's a circuit with a fixed delay from source to destination guaranteed bandwidth between source and destination。

 a packet switch network， we're going to see variable delays。

 and so we're going to be able to adapt to that at the client as well。

Let's start by taking the big picture view and take a look at the three steps involved in streaming stored video。

 First， the video is being recorded。 Secondly， the video is being sent by the server。 And finally。

 third， the video is being played out at the client。

 and we'll do this in the context of this diagram here。 on the X axis， we have time going forward。

 And on the Y axis， we have the cumulative amount of data that's been recorded that's been sent or that's been played。

 as we'll see。😊，In this first black staircase curve here， we show video being recorded。

 Let's assume for simplicity that it's a constant bit rate video。

 We see more and more video being recorded over time with the cumulative amount of data going up at a constant rate。

 sayy with each jump representing a new frames worth of recorded data。

 This video is then stored and then eventually transmitted by a server here。 In this example。

 the video is being transmitted the same rate at which it was recorded。

 It's an Mpeg video recorded at 5 M per second than it's being sent at 5 M per second。

 But it could be sent faster or even slower。 But let's assume for simplicity that's being just sent out at the recorded rate。

 After some network delay shown here， the video playout begins at the receiver。

 again at the same rate at which it was recorded。 And now we see why this is called streaming video。

 If we look at this point in time here， we can see that the client is playing out frame 2。

 while the server sending frame 10。😊，Rather than downloading the entire video before playing it out。

 the client begins play out while the server is still sending。 That's the say。

 streaming later frames in the video。 And you might want to think about the advantages of streaming video。

 rather than downloading the video in its entirety first and then playing it up with streaming the client can begin play out earlier。

 And if the client doesn't watch the whole video。 We're not wasting a lot of bandwidth transmitting portions of the video that aren't viewed。

Now over on the client side， we're going to have to deal with a constraint known as the continuous play out constraint。

 And this means that the timing of play out at the client side is going to have to match the timing from when the video was first recorded。

 So you're sitting at the client。 You're playing out the video。 Everyone's engaged。

 It's time to play out a piece of video。 That piece of video better have arrived from the server to the client in order to be played out。

 If not， we're going to see that spinning dial that you see here that we've all seen at one time or another。

 The source of the challenge here is the variable delay between the video server and the client。

 And to mitigate that delay。 we're going to use buffering to absorb some of those changes in delay。😊。

There are other challenges as well， Like how to deal with client side operations like fast forward and rewind。

 And if packets are lost， they'll be retransmit if we're streaming over TC P。

 resulting in additional delay。 So a fundamental challenge we'll need to address。

 I that of variable network delays。 Let's see how this is done。

Let's again return to this figure and again， assume constant bit rate video being transmitted by the server at a constant rate as shown in the red staircase curve here that we've seen before。

 The difference between this diagram and the previous diagram is that the network delay for each video frame is now going to be variable。

 Remember， in the previous diagram with a fixed network delay， the black staircase curve had nice。

 even staircase steps， because network delay was assumed to be constant fixed here。

 the steps are no longer nice and even。 Sometimes there's a longer horizontal step。

 like here and here， when the network delay of a frame significantly longer than that of a previous frame。

 And sometimes the horizontal delays are quite short， like here and here。

 when the network delay of a frame is significantly shorter than that of a previous frame。

Because of the variable network delay， frames are no longer received with a timing that matches the timing needed for playout。

To accommodate this so called jitter in network delay。

 a client's going to use a buffer to smooth out delay。 as shown in the blue playout curve here。

 a client will now also wait before beginning play out。 But once playout begins。 However。

 the client's going to play out video with a timing shown in blue here。

 that matches the original timing is shown in red here and in black in our earlier figure。

 how long should the client wait， well， that's the million dollar tricky question。

 If the initial client play out delay is too short and frame delays are highly variable。

 a frame may not arrive in time for its play out。 That's called starvation and gives rise to that spinning wheel that we're used to when videos freeze and if the initial client play out delays too long。

 Well， then the user has to wait longer before video play out begins and users hate to wait。

Having taken a look at client side buffering and playout。

 let's now turn our attention to the challenge of varying amounts of bandwidth availability between client and server buffering's great for absorbing variable delay。

 but what happens when the amount of available bandwidth that exists between the client and the server just isn't enough to support the rate at which video is being transmitted from client to server in this case we're going to need another solution and that's where dash dynamic adaptive streaming over HTTP in this case comes in。

And so here's how dash works。 And let's start at the server side。

 The video that's going to be streamed is divided into chunks。

 Each chunk is then encoded at different encoding rates。

 at different levels of quality and stored in separate files。

 La files are going to be associated with chunks of video that are encoded at higher quality。

 And so it's going to take longer， a longer， higher amount of bandwidth in order to be able to download those。

 These different chunks， each representing different encodings are going to be stored at different nodes within a content distribution network。

 And finally， there's going to be a manifest file。 The manifest file is going to tell the client to pick up this chunk at this particular level of encoding。

 Here are the server nodes。 The CN nodes that you can go to。😊，On the client side。

 the client's going to do the following。 It's going to periodically estimate the amount of server to client bandwidth that's available and ask itself。

 can this path support even more traffic， Can I request the next chunk at a higher fidelity When the client needs a chunk it's going to consult the manifest and request video  one chunk at a time。

 choosing the maximum coding rate that it's estimated to be sustainable given the currently available bandwidth。

 It can choose different coding rates at different points in time。

 depending on the amount of available bandwidth at that time。

 and it can choose which server to request a chunk from。So we see that in dash， the intelligence。

 the control is really at the client's side。 The client's given information。

 the manifest file that lists its options。 The client then monitors performance to determine the encoding rate and the C D N node from which it'll make its next request。

 That puts a lot of intelligence at the client。So let's step back and ask ourselves a fundamental question。

 How do we want to structure an application that's going to be able to stream videos to potentially thousands or hundreds of thousands of simultaneous clients and to be chosen from a catalog that could have millions of videos in it。

 What are the options for doing this。 Well， we might start off by thinking about well， a mega server。

 One massive server that's got all of the videos and it's going to handle all the requests coming in from all of the clients。

 So what are the problems with that。 Well， hopefully it's obvious to you。

 It's a single point of failure。 Obviously， there's going to be a potential for congestion there in the network and also in the video server itself。

 And then finally， there are going to be long delays between the video server location and some points on the planet。

In short， this solution just doesn't scale。The second option。

 the approach that's adopted in practice is to build a large distributed infrastructure to store and serve copies of video chunks at different geographically distributed sites。

 This is an example of an application layer content distribution network， a C DN。

 The servers in this network are loaded with content to serve and either a manifest file or a C DN DN S server will point a client to the content that the clients requested。

There are two approaches that are taken in practice in the interdeep approach to CN。

 the CdN servers are pushed deep into many access networks at the Internet's edge。 In 2015。

 a CdN company known as Okamai hadquartered in Cambridge had a quarter of a million CN servers deployed in more than 120 companies。

 And I'll add that in 2018， one of our faculty members here at Umass Ramme Siderraman was part of the team that received an ACM Scom networking systems award for building Okaai's content delivery network。

 The second approach is known as the B home approach。 And in this approach。

 a smaller number of larger server clusters are located in Ps。

 points of presence that we learned about earlier when we were studying Section 1。5。Now。

 let's walk through an example of streaming a video via C N。 Here's a network setting。

 We see Netflix central here， and we see copies of content， say。

 including copies of madmin distributed around its CN nodes。 and here's me sitting at home。

 and I want to watch a particular episode of madmin。

 So my Netflix client app sends a request to Netflix Central saying， hey。

 Jim wants to watch this episode。 Netflix central then returns a manifest file listing the video chunks and their locations。

 as we saw earlier， My Netflix client app might then begin retrieving a video here from this nearby CN server performing buffering and client play out。

 as we saw earlier。 And if that path happens to get congested。

 my Netflix client might choose to get the next chunk from this server here。😊，Now。

 if you think about Netflix， it's not an ISP。 It's about content， not about the network。

 but it uses the networks provided by ISps to deliver content over the ISPs network at the application layer。

 For this reason， a service like Netflix is sometimes called an over the top or O T T service since it's an application level service writing on top of the I infrastructure。

 And you might recall in our very first class when we asked ourselves the question。

 what is the Internet， we answered that question in two ways we gave a nuts and bolts answered。

 describing the pieces of the Internet。 But we also answered that question by saying that the Internet was a service infrastructure on which amazing applications are being built。

 And that's precisely the point of view taken here with Ot T services。😊。

Well I hope you found this section interesting。 We stepped away here just a little bit from an emphasis maybe on looking at protocols to look at application structure itself。

 particularly the case of a large scale distributed application level infrastructure for streaming stored video we started off by looking at the characteristics of streaming video then we looked at buffering techniques and playout strategies at the client then we looked at chunking and that's where we encountered dynamic adaptive streaming over HTTP dash then we wrapped up by taking a look at content distribution networks very quickly there。

 and the example of streaming stored video over a content distribution network。



![](img/d0bfb5b85c2bc1fb19c8ce0ce8ed21b8_1.png)

![](img/d0bfb5b85c2bc1fb19c8ce0ce8ed21b8_2.png)