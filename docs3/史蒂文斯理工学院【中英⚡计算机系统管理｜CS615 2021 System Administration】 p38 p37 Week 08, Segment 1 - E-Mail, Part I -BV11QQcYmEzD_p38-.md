# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p38 p37 Week 08, Segment 1 - E-Mail, Part I -BV11QQcYmEzD_p38-

Hello and welcome back to CS615 System Administration。This is week 8， segment1。

 and after you spend some time talking about the domain name system will now diveve into another crucial service that every system administrator needs to understand as they inevitably end up using。

 maintaining and troubleshooting it email。Just like the DNS and other simple protocols like HTP。

 email utilizes a simple text based protocol STP， the appropriately named simple mail transfer protocol。

 and can trivially be observed and analyzed。But wait a second。

 didn't we get told that email is dead and that Slack has replaced all email communications and freed us from the yoke of constant interruptions and sending attachments back and forth and endlessly growing threads？

Well， about that， I have some bad news for you。 Email is not dead yet。 It remains a critical service。

He has some rough numbers pulled from various websites。 So consider them ballpark numbers at best。

 but they should give you an idea as to why it's important for you to actually understand how Emmama works。

There are currently estimated to be about 5。5 billion email accounts in news with the Gmail making up a good third of them。

That's right， there are still email accounts other than Gmail accounts。

 although of course Google runs many companies email。

 which is another example of where one company uses their direct competitor services。

 which is kind of wild to think about。And with these 5。5 billion accounts。

 there's a lot of emails that get sent and received every day。

 The current estimate is around 300 billion emails。Which breaks down to about 3。

4 million emails per second worldwide。Just think about all the traffic this generates and you can bet if this service goes down。

 your bus is going to notice you exist after all。Poor office workers receive an average of 1 hundred20 emails per day。

 which is just painful。Of course not every email you receive is when you actually read or have to read since somewhere between 30 and 70% of all emails are spam。

This range is so large because it actually is not easy to correctly classify spam。Sure。

 you know what spam is to you， but if you're an email service provider it actually is really difficult to correct the identify spam。

 and believe me， if you accidentally incorrectly classify a single non spam message of spam。

 your users are going to be upset。Now， of course， spam is a topic that could fill a few weeks' worth of materials all by itself。

 but we'll try to provide a bit of a summary of the problem space and some possible defense mechanisms in the next videos。

And， of course， email has been such a success story that it's been used， abused， if you will。

 for all sorts of other purposes。 as you all well know。

 people use it as a general file transfer protocol by sending attachments to themselves and others as a to do list and in our area as an learning and monitoring system。

Which of course， is a terrible idea because email really is not a reliable alerting mechanism at all。

 as we will see when we look at the details of the protocol。

We'll discuss better approaches to monitoring systems in the future video too。

 but let's go back down to the basics as we've done with other protocols。



![](img/fa9e6ee94746a05e4134734c10ca2bec_1.png)

So here's our naive view of how email works。 One person composes a message and hits send。

 and then the email will be delivered to the recipient's inbox， them just like that。

But of course we know that there's bound to be a bit more to the story。

 so let's go back and start over。We said the user is going to compose their message。

 which actually involvess the first component of the mail system。The mail user agent or MUA。

This is the program that you use to read your email to compose your emails there's a large number of possible Ms ranging from command line clients。

 terminal apps such as the Motroine programs common on many Uni systems。

 the mailed app program on your MacOS system， Outlook， Thnabird， etc， etc。Now， obviously， nowadays。

 many people use the browser as their male user agent as webmailil as the dominant form of email。

 which brings with it all sorts of major headaches and of course， nowadays， email， which used to be。

 well simple text， is by and large interpreted as HTML。

 which facilitates phishing the text via link obscuring official looking emails through the use of images or logos etc。

 and which also allows for all sorts of privacy invading tracking methodologies such as beacons and trackers。

 causing the MuUA to make a callback to the send server。

 allowing them to track just when and where you open the message and so on and so on。By and large。

 HTML and emails was a terrible idea， but I digress。So anyway。

 the user uses this MUA to read their email and when they do send it on its way。

It is not magically transported to the receiver， but rather it is handed off to the designated mail transfer agent or MTA。

This is what we generally refer to as the mail server and in the Uni world the most common pieces of software you may have heard about here are post fix。

 sent mail and Q mail， perhaps。The system we see here is the outgoing MTA。

 which takes the mail you handed it， looks at where it needs to go。

And then send it on its way to the receiving MT A。That system then may do a number of things。

 as we'll see later。 But if it eventually decides to accept and deliver the mail。

It may then hand it off to other mail processing systems。

 such as an engine to assess its feminess before it eventually is passed on to a so called mail delivery agent。

Which may sort the mail duplicated， forwarded， or otherwise process it in some way。

Procmail is a commonly used MDA and Uni systems， and it can be used system wide。

 or it can be invoked by each user locally。So now the email has been accepted and filtered and sit there in the user's inbox and if the user accesses a system directly。

 say they are logged in locally into the mail server and use a local MuUA such as Mo P。

 and they can now read the mail but oftentimes the mail server is not directly accessible to the user and they are more likely to use a separate service an access agent that allows remote access via a separate protocol such as Pop or IMap。

This is what you configure as your incoming mail server in your mail user agent。

 which then can pull the email down from the server。Now if you are using such a service。

 then it's quite likely that when sending enEma， you do not hand it directly to the outgoing MTA。

 but instead interact with the access agent here as well。

 which kind of completes our high level overview of the mail system。As you can tell。

 there are a number of moving parts here with plenty of opportunity for things to go wrong。

But for our immediate discussion， we will only focus on the work the MT is on doing。

Now this we're going to look at what happens between these two parties as this is where the simple mail transfer protocol is spoken。



![](img/fa9e6ee94746a05e4134734c10ca2bec_3.png)

So let's just go ahead and observe what happens when we send a simple mail。

Here we are again on our EC2 instance， and we start a packet capture for traffic to port 53 and 25。

Then we use the mail command。😮，To send an email from this system。

With a subject of SMMTP test to my personal address here。The mayor program is simple enough。

We just type our message in here and then end it with a period on the line by itself。

And that's all there is to it so we can stop our packet capture again。Now。

 before we look at the packets， let's first see what our mail server says about what it did with the message。

Since we are on the Uni system， we have a local mail transfer agent or MTA running postF in this case。

This allows for local delivery without involving any network traffic。

 but since we specified a remote address， we expect the server to hand it off to a remote system somewhere。

The mail server logs informational messages into the file， R log Mail log。

 so let's take a look at that file。Here we see that our PostF mail server picked up the message we composed from a user ID and assigns it a unique identifier。

 the string EV 4851 CEAD over here。It then also generates a unique message ID for this email to facilitate tracking of the message across systems。

So we have two identifiers here， the local string， EB 4851 CEA， and the message ID。

 which includes the string， thereby making it again easy for us to correlate and track messages across multiple systems。

We then see that this mail server tried to talk to the host Pans@netmeister。org on its IPV6 address。

But that system didn't like that our connecting server here doesn't seem to have a reverse DNS pointer record for its IPV6 address。

 so it denied its email。This MTA then tries again using IPV4。

 for which they exists a valid reverse PTR record， and the remote site then happily accepts the email informing us that it has cued the mail as identifier E843 D855 AB。

Having delivered the mail， our local MTA can then remove the message from its queue。So。

With these few lines， we can tell that our mail server itself consists of several components。

 and that it tries its best to ensure that we can track the message easily。

We also saw a first anti spam mechanism on the receiving end。

 that server appears to reject messages from systems that don't have a reverse DNS record。

We'll talk more about this and other defense mechanisms in one of our next videos。

 so for now let's take a look at what network traffic we captured。Up here in the first packets。

 we see that our server is looking up a DNS MX record for the domain netminister。org。

This is how we figure out what our mail server is， similar to how we saw earlier。

 how a name server determines what the authoritative name servers are for a given domain。That is。

 when we send an email to Fo@exle。com， then the sending m needs to perform an Mx lookup for example。

com to find out what mail server it should talk to。The result returned includes a host name。

 Pans@netmyist。org in this case， so unsurprisingly we then see a host here look up the A and Q records for that name。

With that information about the IP addresses in hand。

 we then see our server making a TCP connection to port 25 on the receiving server。TCP handshake。

 Sun， Soak egg。And then here we see the SMTP protocol packets where we identify ourselves and try to send a mail。

But then， get rejected。So our trusty mail server doesn't give up quite so easily and will then attempt again over IPV4。

Where it's successful and receives confirmation that the male has been cud。Okay。So far， so good。

Now let's take a look at what this looks like on the receiving end。

Here we are on the receiving mailil server。Remember the identifier。

 the mail server told her as sending MTA assigned to the mail when it accepted it。

We can check for that identifier in the receiving mail server log files。



![](img/fa9e6ee94746a05e4134734c10ca2bec_5.png)

And then here we see that we accepted this mail from our AWS EC2 instance with a message ID or as sending MTA had generated。

We then see our MT A， take this message and pipe it into a separate service。 spam assassin。

 which is an independent program that processes merely attempts to determine whether or not did spam。

Since this is a separate process， the mail server here considers this message to be delivered and remove it from its queue。

But then the spam assessment process after it has completed whatever it was doing。

Reinserts the message， which is why we are seeing a new identifier here。13D7 B85 A22。

But notice that the message still has our earlier message ID and is then accepted by the mail server for local delivery。

Whi it does by feeding it into the mail delivery agent， Pro mail。Now。

 Proc mail will process the mail based on the user's preferences。And according to its log。

As shown here。Was delivered。Based on a subject match into the mailbox slash T， slash SMTP test。

We can then use our preferred mail user agent mod to open this mailbox。And here we go。

 there's our mail。

![](img/fa9e6ee94746a05e4134734c10ca2bec_7.png)

If we view it， it looks just like we'd expect a real regular normal email just as we had sent it from her originating system。

 showing the from to and subject headers as we'd expect。Alright。

 so now we've seen an email across the entire mail system from composing the email using the mail command as our admittedly simple MUA to it。

 handing it to the local MTA Postfiix in this case。

 which found the responsible mail server and handed off the mail to it。

 even if only on the second try to it then processing the mail locally via spam assessment and Proc mail and using Mu to read the mail。



![](img/fa9e6ee94746a05e4134734c10ca2bec_9.png)

In the packet catch， we saw the DNS lookup and the TCP packet， and since those were all clear text。

 we saw the protocol in action。So we should be able to reennect the exact exchange manually。

 let's give that a try。So first we said we need to find out which mail server is responsible for the domain in question。

 so we start with an MX lookup。Once we have that， we need an IP address。

Then we can use the Tnet command again to connect to port 25 on that IP address。The server。

Greetets us with a 220 banner and we say Alo， followed by our host name。

The server replies with a list of SMTP options it supports， but at this point we don't really care。

 so we start sending our email by specifying the mail from command and providing our asenders' address。

The server seems to be okay with that。 So we then specify the recipient of the email。

Which also meets no objection。

![](img/fa9e6ee94746a05e4134734c10ca2bec_11.png)

Next， we tell the server， OK， watch out， here's the data upon which we can then provide the full email。

Now note that at this point， we are able to specify another from and2 header。

 the difference between these and the male from and recipient two fields we be discuss in the next video。



![](img/fa9e6ee94746a05e4134734c10ca2bec_13.png)

Next， we provide the subject header。

![](img/fa9e6ee94746a05e4134734c10ca2bec_15.png)

An empty line to signal the start of the male body。



![](img/fa9e6ee94746a05e4134734c10ca2bec_17.png)

And then we include our text message here。When we're done。

 we signal the end of the message via a single dot on a line by itself。



![](img/fa9e6ee94746a05e4134734c10ca2bec_19.png)

And we see that the mail server then accepts our message and cues it for delivery。

 providing us with the identifier shown here。

![](img/fa9e6ee94746a05e4134734c10ca2bec_21.png)

The connection to the server is kept open， so we could send another message here if we wanted to。

 but we O for now。 So we say good by。And there you have it， sending an email using Tnet。See。

 I told you that SMTP was a simple mail transfer protocol， didn't I。



![](img/fa9e6ee94746a05e4134734c10ca2bec_23.png)

All right， time for a break， let's summarize what we've observed so far。For starters。

 we noted that the default protocol and port is TCP25 and that we can easily observe all the data in clear text。

 which makes for rather convenient troubleshooting and debugging。

 but obviously isn't quite so great from the security and privacy perspective。

We saw that the service lookup uses the DNS for discovery of which mail server is responsible for the given domain。

 and then we observed that SMTP really is a very simple protocol following a trivial dialogue structure with the most basic steps being shown here。

The return codes and the SMTP protocol are once again simple numeric values that indicate what action the client should take next。

 which is rather similar to HTTP status codes as you will notice。Now， with this first look at as MTP。

 we are far from done covering the email topic。

![](img/fa9e6ee94746a05e4134734c10ca2bec_25.png)

So in our next video， we'll dig a bit deeper in particular into receiving end where we look at packet captures on the mail server as well as observe multiple relays。

Well also see what we can do about protecting the content of our message in transit by wrapping the mail communications in TlS。

We further dissect the an anatomy of an email message and look at the various headers that make up the message and what those headers tell us about the message and the mail system by which the message was delivered。

And， of course， we'll have to spend some time talking about how the male system can be and is abused。

As you've seen， we can connect to a mail server and just send an enema claiming to be from anybody really。

 so we have to think about how to add at least some layers of authentication or other assurances on top。

In the meantime， I recommend that you once again follow the commands and examples from this video and then perhaps take your investigation a step further by running through this practical exercise from this URL。

 You'll find much of the discussion here to make a bit more sense if you've manually observed the packets and messages yourself。

Until the next time， thanks for watching。😊，J。

![](img/fa9e6ee94746a05e4134734c10ca2bec_27.png)