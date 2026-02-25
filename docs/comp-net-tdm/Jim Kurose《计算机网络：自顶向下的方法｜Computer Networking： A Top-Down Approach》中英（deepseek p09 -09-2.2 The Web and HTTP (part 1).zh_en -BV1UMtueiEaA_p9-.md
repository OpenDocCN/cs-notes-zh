# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p09 -09-2.2 The Web and HTTP (part 1).zh_en -BV1UMtueiEaA_p9-

In this first section on HTTP we're going to start off with just a very quick overview of the web and HTTP。

 then we're going to dive down into the two types of HTTP connections persistent and non-persistent connections and look at the major messages used by HTTP。

 the request message and the response message and then finally we'll wrap up this first section by taking a look at what are known as cookies。

 a ways for state to persist at a server between one client connection and another client connection Now this is just the first of two parts that we're going to cover on HTTP but we've got a lot to cover here so let's get started。

Well let's begin our discussion of the web and HTTP with just a very quick review to set the stage。

 remember that a web page consists of a base HTML file， as well as a set of referenced objects。

 and each of these objects can be stored on different web servers。 An object can be an HTML file。

 JpeG image， a Java Appt audio file or many other things。

 and the web page itself as well as the reference objects are each addressable by it's known as a URL。

 There's a host name associated with it， and then on that host， there's a path name piece to it。



![](img/8831f3fa8e5644f7f03e7cf961930a14_1.png)

Well， let's get started with our study of HTTP and the very first thing to know is that HTTP adopts the client server model that we just studied in Section 2。

1。A client might be a web browser like Firefox or Safari or Edge。

 or it might actually be embedded in a device and you might not even see it。

 a server might be a traditional web server that only serves web pages or a more general purposepo server like Gaia。

cs。ums。edu， which provides a number of services。

![](img/8831f3fa8e5644f7f03e7cf961930a14_3.png)

In this animation here we see on the top a PC running the Firefox browser making an HTTP request to a server and getting a response back。

 the bottom we see an iPhone running a Safari browser also making an HTTP request and getting an HTTP response back both of those browsers are speaking the HTTP protocol with the Apache web server。



![](img/8831f3fa8e5644f7f03e7cf961930a14_5.png)

HTTP uses the transport services provided by the TCP protocol and here's how an HTP transaction works the HTTP client。

 your web browser for example， opens a TCP connection to a web server using port 80 will learn about port numbers in just a second one or more messages HTTP messages are then exchange between the client and the server and then the TCP connection is closed。

HTTP is a stateless protocol， this means that the server maintains no internal state about the ongoing request。

 there's a single request for an object and a single reply， that's it。

There's no worrying about something like well， this transaction has five steps where're now in step three and if I fail。

 I'm going to need to roll back my state to what it was before this five step transaction started。

 none of that with HTTP， it's stateless and you might ask why， well。

 because of its simplicity as we'll see， protocols that maintain state will need to deal with cleanup problems when a multistep transaction fails returning to the initial state and resolving incon state。



![](img/8831f3fa8e5644f7f03e7cf961930a14_7.png)

There are two types of HTTP connections， what are called persistent connections and non- persistentent connections。

 and it's important to remember these HTTP connections between a browser and a server are different than the TCP connection which is provided at the transport layer underneath。



![](img/8831f3fa8e5644f7f03e7cf961930a14_9.png)

In non persistentistent HTTP， a TCP connection is opened at most one object is then sent over the TCP connection and the TCP connection is closed。

Downloading multiple objects is going to require multiple TCP connections to be established。

 and we'll see that it takes a round trip time first to open the TCP connection and then another RTT to make the request and receive the response。

In persistent HTTP， a TCP connection is again open to the server。

 but this time multiple objects can be transferred serially over the single TCP connection between the client and the server。

Once those multiple objects have been requested in returned， the TCP connection can be closed。

 persistent HTTP corresponds to HTTP version 1。1， which is probably the most common form of HTTPN use today。

Here's an example of non-persistent HttP in operation。

 Let's assume that the user in step 1A here enters a URL www。sschool。

edduu and as for a webage that contains text as well as references to 10 JpeEG image in that base HM file so in step 1A we see the client initiating the tCp connection to the http server at port 80 at www。

sschool。edduu in step 1b the httP server at the host which has been waiting for a TCP connection at port 80 accepts this ttp connection and notifies the client and notice in steps 1a and 1b。

 no httP requests have actually flowed yet this happens in step 2 in step 2。

 the HttP client sends the HttP request message into the TtP connection that's just been established this http message indicates that the client wants to receive。

This base HTML file in step 3， the servers now receive this HTP request message and forms the response message that contains the requested object and sends this message back to the HTP client after sending the response message and step 4。

 the HTP server closes the TtP connection， and step 5， the HtP client。

 receives the response message containing the HTML file， displays the HTML file。

 parses it finds the 10 reference JPEG objects， and in step 6 now is going to have to repeat the preceding five steps for each of the reference JPEG objects。

Now we can take a look at the response time for nonpersistent H TTP。

 We can define the response time as the amount of time from when a user first enters a URL into a browser until that base H file is received and displayed。

 So let's define the R TT， the roundtri time as the amount of time needed for a very small packet to travel from the client to the server and back。

And so we can see that the non-persistent HTTP response time per object has the following components well。

 one RTT is needed to initiate the TCP connection and another RTT。

 a second RTT is needed for the HTTP request to be transmitted and received and for the first bytes of the HTTP response to be returned。

 and then finally there's the amount of time needed for the server to actually transmit the file into its internet connection。



![](img/8831f3fa8e5644f7f03e7cf961930a14_11.png)

![](img/8831f3fa8e5644f7f03e7cf961930a14_12.png)

And so overall， the non persistent HTTP response time is2 RTT plus whatever amount of time is needed to transmit the file。



![](img/8831f3fa8e5644f7f03e7cf961930a14_14.png)

So we've seen that two RRTTs are needed to fetch a web object Now multiple objects can often be retrieved in parallel。

 but still two Rtts is well two Rtts。 and you know we really want to get our information as fast as possible so it's possible using a simple technique to actually cut this latency from two Rtts to one RtT and that's to use a technique known as persistent connection。

 and this is the way that most web servers are now operating in persistent HTTP HtP1。

1 the server leaves the connection open after sending the response。

 subsequent HTTP messages between the same client and server can then be sent over this open connection without having to wait that RtT to establish a new TCP connection when a client has a new request sends it as soon as it encounters a referenced object。



![](img/8831f3fa8e5644f7f03e7cf961930a14_16.png)

And so we can see here how persistent HTTP cuts the response time in half to one RTT。

Now that we've looked at the two styles of HTTP connections。

 we can dive down into the details of the HTTP messages themselves and remember way back in section 1。

1， we said that a protocol defines the format and the order of messages sent and received among network entities and the actions taken when these messages are sent and received。

 let's take a look at the HTTP protocol and let's take a look at its messages。

There are two types of HTTP messages， request messages and response messages。

 let's take a look at a request message first。A request message starts with a single request line with that line beginning with a method name。

 for example， get as shown here， a URL。 In this case， the name of the H file being requested。

 the version of H TP in this case 1。1 and a new line。 that is a carriage return line fee。

 The single request line is then followed by a number of header lines that provide additional information。

 For example， the name of the host where the request is being made。

 the type of browser making a request in this case， Firefox。

 the types of objects that can be accepted and preferred language in this case， US English。

 and the fact that this connection should be kept alive。 The request message ends with an empty line。

 So as you can see， very human readable。

![](img/8831f3fa8e5644f7f03e7cf961930a14_18.png)

Here's the general format for an HTTP request message we see the request line followed by header lines。

 the HTTP protocol specification， RF 7320 85 pages long and has all the details about the methods。

 header field names and values fortunately for us， networking students we don't need to know all of those details。

 but if we were implementing an HTTP client or server。

 we'd have to know every detail when we looked at the get message in the previous slide there was no entity body that's needed by some request messages like post which we'll see in a second that need to send additional information not in the header fields to the server。

Here are the four types of H TTP request messages。 We've seen the get method already。

 The post method is used to upload completed form data to the server。

 and the put method can be used to upload a new object to the server with a given URL possibly replacing an existing object。

 And last， the head method， asks for a response that's identical to that of a get request。

 but without the response body。This could be used， for example。

 to determine the size of an object that would be retrieved。

 but without actually retrieving that object。

![](img/8831f3fa8e5644f7f03e7cf961930a14_20.png)

Now let's quickly take a look at the HTTP response message。

 the response message begins with the status line and the first thing on the status line is the version number of the HTTP protocol being used in this example here 1。

1。Following the version number are there two most important pieces of information in the response message。

 a status code and a short message in this case the status code shown is 200。

 which means that everything went OK and a short status phrase， in this case， the word OK。

Following the status line， there are response header lines。

 as in the case of the request message that provide additional information。 For example， shown here。

 you can see that the date and time， the response was sent。

 The type of server is also shown in this case， an Apache server version  2。4。6。

 The last modified field shows the time when the document was last modified。

 the content length field shows how long the document is and the content type field indicates the type of object that's being returned。

 In this case， an HTML document， and finally， the body of the object being returned。 In this case。

 the H document itself。

![](img/8831f3fa8e5644f7f03e7cf961930a14_22.png)

And here are just a few of the HtTP response status codes and phrases。

 We've already seen the 200 okay indicating that a request has succeeded。

 You've probably seen a 404 not found when a requested document was not found on the server。

 All of the response status codes and phrases are contained in the RF document。

 So take a look there if you're really interested in learning about all of the status codes and response phrases。

 So that wraps up our discussion of HtTP messages。 It's pretty simple as promised。

 and there's only two types of messages。 And as also promised it's pretty human digestible。

 We could look at those HtTP messages and pretty much understand them。

 Let's wrap up our initial study of HtTP by coming back to this question of statelessness。

 we said that H TTP is a stateless protocol。 As it turns out。

 it's possible for a web server to actually maintain some user state to remember。

What a user's done in the past and how that might influence what a user wants to do in a current session by using a technique known as cookies。

 Let's take a look。Websites will use cookies to maintain information about a user。

 more specifically a user's browser in between transactions。

 and there are four components to using cookies First a server at some point is going to send a cookie to a client the cookie is just a number and is contained in a cookie headerline of an HTTP response message being sent to a client。

Then later， when the client next makes a request to that server。

 it'll send along that cookie value to the server in a cookie header line。

Now the server is going to remember all of the requests that's received and the responses it's sent associated with that cookie value。

 so it'll have a history of the interactions with that user。

 Let's take a look at an example Let's take a look at an example。In this example。

 a client on the left here is going to make a couple of HTTP requests to an Amazon server。

 for example， on the right， which has a backend database where it's going to store cookie related information。

 the client also has cookie information from other websites it's visited in this case。

 a cookie from eBay， for example， but it doesn't have a cookie from Amazon yet。

The client makes a request as usual to the Amazon Web server initially without a cookie line。

 when the Amazon Web server gets the H TTP request。Creates a cookie。

 stores the cookie and the transaction information in its database。

 and sends an HTTP response to the client， including a cookie value。Now。

 here in the second request by the client， the client includes its cookie value to Amazon。

 allowing the Amazon server to take a cookie specific action。

 perhaps taking the first H T TP request now into account。 For example。

 maybe the first transaction was a request to look at one item of merchandise。

 and the second H T T P request wanted to look at a second item of merchandise。 with cookies。

 the second reply could be crafted to offer the client a deal on buying both of those items of merchandise together。

 even though the second request only wanted to look at one particular piece of merchandise。

 The client comes back a week later and again provides cookie。

 The server can again take a cookiespec action。 For example， it could say， hey。

 I missed you during the past week。 You sure you don't want to buy those items that you looked at during the past week。

So in this example， we can see how cookies can be used to store state about a user at a website in between HTTP interactions。

Given that cookies can be used to store user state over multiple transaction。

 they've got lots of uses remembering that you've authenticated yourself to a site before。

 for remembering the contents of your shopping cart。

 or for making recommendations based on past behavior。

You may have also read about the many privacy concerns about cookies cookies can allow websites to learn a lot about you There are what are called thirdparty cookies that can be put into your browser and allow websites to establish a common identity across multiple website and you may have also heard about the EU's general data protection regulation GDPR under GDPR cookies that aren't strictly necessary for the operation of a website can only be activated after you've given your explicit consent for their use and for the collection of personal data。

You may have noticed recently that at a lot of sites before you're able to use that site。

 you have to agree to a certain cookie policy。

![](img/8831f3fa8e5644f7f03e7cf961930a14_24.png)

Well that wraps up the first part of our study of the web and HTTP and we've learned a lot already after a quick introduction。

 we dove down into the different types of HTTP connections。

 we studied the request and the response messages and we also took a look at cookies a way to remember some state on the server side between user interactions with that server so coming up next in the second part we're going to take another deeper dive into some additional aspects of improving HTTP performance。

 we're going to look at web caches， we're going to look at the conditional get request and then finally we're going to look at HTTP version 2。

 the most recent version of HTTP and take a quick peek at HTTP version 3 which is coming within the next year or so。



![](img/8831f3fa8e5644f7f03e7cf961930a14_26.png)