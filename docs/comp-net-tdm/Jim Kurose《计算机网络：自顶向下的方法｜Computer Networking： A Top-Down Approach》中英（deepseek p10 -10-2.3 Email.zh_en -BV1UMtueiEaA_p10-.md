# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p10 -10-2.3 Email.zh_en -BV1UMtueiEaA_p10-

。

![](img/c7505e0a533c39e54420c4f3f491c84c_1.png)

In this section， we're going to take a look at an application that's been around for a long time since 1972 email matter of fact。

 it's been around so long it's part of culture already。

 part of your parents culture since the movie you've got mail came out in 1998 and my breath catches in my chest until I hear three little words。

Now I'll admit this is not going to be the most exciting of all the applications that we take a look at。

 but it's a good example of the client server model that we saw with HTTP。

 it's relatively simple so we're going to want to take a look we're going to focus on two things here we're going to look at the infrastructure for email as an application。

 the user agent， the mail client what you use as a user when you use email we'll look at email servers and we'll look at message and message cues as well secondly we'll take a look at the SMTP protocol。

 the simple mail transfer protocol that lies at the heart of email as an application so let's take a look。

Well as a distributed application， email has three components， first there's the user agent。

 the mail client， if you will， that you use as a user。

 then there are the email servers equivalent to the HTTP servers and finally there's the SMTP protocol simple mail transfer protocol for moving messages around to and from servers。



![](img/c7505e0a533c39e54420c4f3f491c84c_3.png)

Well， the first of these three major components is the user agent。

 otherwise known as a mail reader or a mail client， and that's what you use to compose。

 edit and to read email。 so you do that every day。 The messages that are read are created by your client are actually stored on the server。

An email server has two sets of messages for each user。

 it's got a mailbox that contains the incoming and the previously received messages for that user and it's got a queue of messages that it's waiting to send to the destination SMTP server。

And the final piece of the email infrastructure is the SMTP protocol itself。

 this is used to push a message either from the user agent or from a mail server to another mail server。

It operates in a client's server paradigm where the client is now the sender of the email。

 whether it's the user agent or the sending mail server。

 and the server side in a client' server sense is the receiving mail server。



![](img/c7505e0a533c39e54420c4f3f491c84c_5.png)

![](img/c7505e0a533c39e54420c4f3f491c84c_6.png)

Well， let's walk through an example of the various steps involved when Alice over here on the left wants to send an email message to Bob over here on the right where Bob's going to read it。

 Now Alice and Bob both have their own email clients that is to say their user agents in their own email servers where they have accounts So let's start over here on the lefthand side。

 Alice first uses her mail client， her user agent to compose an email message she's composing the email message eventually she hits send when she hits send Alice's email client contacts Alice's email server and pushes that is to say transfers and a client server model transfers the message that Alice is written to the mail server using the SMTP simple mail transfer protocol we're gonna to take a look at that protocol in just a second。

 Okay so now the message is sitting on Alice's server the next step Alice's server is going to contact Bob server got a server。

Contacting a server， and the first step that Alice's Ser is going to do is to open up a TCP connection。



![](img/c7505e0a533c39e54420c4f3f491c84c_8.png)

In step 4， Alice's SMTP server， acting as a client sends Alice's message over the TCP connection to Bob's email SMMTP server。

 Bobs Ser then places the message in Bob's mailbox and then at some point in the future asynchronously。

 Bob's going to invoke his user agent and read Alice's message from his email server。



![](img/c7505e0a533c39e54420c4f3f491c84c_10.png)

![](img/c7505e0a533c39e54420c4f3f491c84c_11.png)

R C 5321 defines the SMTP protocol。 SMTP operates on top of TCP using TCP to reliably transfer email messages from client to server。

 port 25 is the standard server port number associated with SMTP。

 So the client always knows the port number on which to contact the SMTP server。 As we saw earlier。

 mail messages are directly transferred from the sending server。

 which acts like a client in this case， to the receiving server to the destination server。

Following the TCP setup， there are then three phases to message transfer。

 there's an SMT handshking protocol that's shown over here on the right that involves the exchange of three messages。

 a 220 message that's initiated by the server to the client over the TCP connection the client then saysHo and the server then saysHo back Then there's the SMT transfer of messages and finally the SMTP connections closed。

 and then the TCP connection can be closed and we'll see shortly that the command response interaction like HTTP consists of ASI text again very human readable and a status code and a phrase as a response。



![](img/c7505e0a533c39e54420c4f3f491c84c_13.png)

Here's a sample SMTP interaction between Alice's email server acting as a client at CRreps。

frR with bo'ssmtpserv at hamburger。edu， and what happens first following the establishment of the TCP connection is Bobs server to hamburger。

edu sends a 220 message with its host name， Alice's SMmtP server responds with the word hello and its host name and then Bobs server responds back with a message that says hello to Alice's host name pleased to meet you that's really the phrase that's returned with the 250 code。

In the first few lines so far， the SMTP servers performed a handshake with each other in lines 4 through 13 here。

 you can see the SMTP protocol identifying who the message is from， who the recipient is。

 the phrase data which tells the server that the message itself is about to begin and then the message itself terminated by a line that only contains a period following that the client says I quit I'm all done。

 and the server responds back with a 221 message and at this point the email message has been transferred and the SMTP connection has been closed。



![](img/c7505e0a533c39e54420c4f3f491c84c_15.png)

Well， before diving into the details of email message formats。

 let's make a few high-level observations about the SMTP protocol itself and let's start by comparing it to HtTP。

 We saw that HtTP is a poll protocol that is the HTTP client is pulling data generally from the HTTP server whereas SMTP is more of a push protocol。

 it's pushing a message from the client to the server and again that client could actually be a user agent。

 a mail client or it could be a mail server pushing a message from that mail server to another mail server We also noted that SMTP messages are human readable。

 they're encoded in ASI format， we can look at them understand what they do and they have status codes not the same status codes but a similar idea to what we saw in HtTP and in fact。

 HtTP you can see drew some of its inspiration from SMTP。And then finally。

 SMTP has multiple objects that could be encoded into one message and in HTTP， as we saw。

 there's just one object in each request。

![](img/c7505e0a533c39e54420c4f3f491c84c_17.png)

SMTP uses persistent connections， meaning that multiple email messages can be transferred over a single SMMTP connection。

 and we've seen already that SMMTP requires messages to be in seven bit ASI human readable form and that the message itself is terminated by a line with only a period on it。



![](img/c7505e0a533c39e54420c4f3f491c84c_19.png)

So what does a mail message format actually look like， What's the protocol for that， Well。

 I'm going to spare you the pain。 And if you're really interested。

 I'm just going to point you to RF 2822 that defines the syntax for the email message in much the same way that HTML defines the syntax for what web documents look like in a nutshell an email message is going to contain a header portion which will have a two line。

 a from line and a subject line And these lines within the body of the email are actually quite different from the SMTP mail from and receipt two commands。

 I know it's a little bit confusing。 the headers then followed by a blank line and then the body of the message encoded in7 bit ASI。

 And again， for the details， take a look at RFC 2822。



![](img/c7505e0a533c39e54420c4f3f491c84c_21.png)

While all of our discussion so far is focused on pushing a mail message towards the destination SMTP server now suppose an email message is actually at the destination server。

 how is that message retrieved？Well， of course there's a protocol for that。

 the Internet message access protocol IAP is probably the most widely used email access protocol。

 it's defined in RFC 3501 and you can check that out for the details there are lots of other protocols for accessing email as well one can also use HTTP to retrieve an email message from a web server that's also configured to return email messages。



![](img/c7505e0a533c39e54420c4f3f491c84c_23.png)

In this section we took a quick look at one of the oldest networked applications around email we looked at the email infrastructure。

 mail servers， mail clients， message cues， things like that and we also took a look at the SMTP protocol the simple mail transfer protocol which gave us another good example of a client server type of protocol similar in some ways to HTTP but also different Well coming up next we're going to take a look at the DNS protocol。

 the domain name system protocol as we'll see it's very different from SMTP and HTTP doesn't involve users like you and me and it's a critical piece of core Internet infrastructure。



![](img/c7505e0a533c39e54420c4f3f491c84c_25.png)