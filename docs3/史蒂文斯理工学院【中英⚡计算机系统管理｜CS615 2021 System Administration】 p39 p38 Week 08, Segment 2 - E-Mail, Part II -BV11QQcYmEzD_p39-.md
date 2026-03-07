# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p39 p38 Week 08, Segment 2 - E-Mail, Part II -BV11QQcYmEzD_p39-

Hello and welcome back to CS615 System Administration。This is week 8 segment 2。

 and we'll continue our discussion of the mail system and how emails are delivered。In our last video。

 we had looked at the simple mail transfer protocol and observed how it delivers the mail from a client to a mail server。

We had TCPDm to observe the packets and saw how the protocol lets us send a mail using， for example。

 the Tnett command by connecting directly to the given MTA。In this video。

 we'll now take a look at the receiving it to see what happens when a server accepts the mail。

 as well as talk about ways to protect the email information and transit from being intercepted or observed by an adversary。

So let's take a look。Here we have three windows。Up here in the top one。

Are running a TCP dump and a receiving mail server。

Looking for packets from our EWS instance as well as DNS Loups。Here in the middle。

Will tail the mail logs。On the mail server。Let's just clear up any current messages so we can start fresh。

Then down here， we will now send our email just like we did before。

We compose our content knowing full well that everything we type here is being sent in the clear to the remote side。

And there we go。As soon as we finish our mail， do we see the connection made， the packet flow。

 and the mail server log activity。

![](img/92098231fa3412ded7d4382c777416cc_1.png)

So let's go up there now and look at what the mail service sees。

Let's scroll back up all the way to the beginning。Okay， here we go。

We first see an IPV6 reverse lookup as you will recall from the last video。

 our mail server will first try to send the email using IPV6。

 but since our IPV6 address does not have a valid PTR record looking up here， the mail is rejected。

Next， we see additional DNS lookup being performed based on what our client attempts to deliver。

 We'll see those repeated further down。 So let's skip over these here。All right， so here。

We see the IPV4 connection from our AWS instance， and then not surprisingly。

 we see the reverse PTR lookup of that IP address。We then see our 220 halo message。

And receive the Alo from the client。As soon as we get the mail from message。

 we are then going to look up the MX record for the domain that this message purports to be from。

After that， we see another DNS lookup in a domain named Spmhouse。org。

We'll get back to that later when we talk more about spam and abuse detection。Over here。

 we see that OS server accepted the mail and lets the client know upon which the client disconnects。

But our work here isn't done， as you may recall from our last video。

 we know that this mail server hands the mail off to spam the assassin。

Which performs a number of DNS lookups。That we see here。Again， we'll discuss those in our next video。

 but do take note of the frequent use of the DNS for all these。If we look at the mail logs now。

 we see the same messages as we'd expect and as we had seen the last time。

The IPV6 connection that we rejected。The IPV4 connection that we do accept and let deliver mail。Then。

 hand off to Spmmus assassinin。And the final delivery into Procmail。All right， so far。

 there's nothing unusual here。 The various lookups on the server may seem surprising。

 but I promise we'll get back to those in the next video。But now let's run through this once more。

 this time manually。Note that here。When we send our ALO message。

 the server provides us with a list of additional features that supports。

 and one of those is Star TLS。Which provides a form of opportunistic transport encryption by allowing the client to upgrade this planex connection to an encrypted connection by well starting to use TlS。

Anyway， so why don't we give this a try？Okay， cool。 Looks like the server is ready now。 But damn。

 I forgot how to speak to your less。I don't think I'll manage a TlS handshck manually over tell it。

 so a good thing the server awards here。But okay， how do we begin to start TlS connection then？😊。

Let's use our trustee Open SSL S clientient command。Which supports the star TlS option。Here we go。

Nice， now we're connected with a TLS connection between the server and client here。And now。

 when we say Alo， know that the server no longer offers star Tls。Because， well。

 we already are speaking Tls。So now when we send our various SMTP commands here。

You'll notice that in the upper window our packet capture no longer as able to display the contents of the packets。

 only letting us know that the traffic is of type SMMP。So now。

 knowing that our connection is encrypted in transit， we can send confidential messages。

 resting assured it cannot be read by anybody capturing the packets in between our systems。

Let's scroll back up here to take a look at what the Open SSL command tells us。As you can tell。

 this all looks very similar to a common TLs connection to say。

 an HTTP server with the usual certificate chain， server certificate。

And the negotiated session key and all that jazz。Eventually showing us that our client was even able to verify the certificate the server presented。



![](img/92098231fa3412ded7d4382c777416cc_3.png)

So what we saw here then was the communications between the sending and receiving MTAs。

The client or sender begins the connection and sends an elo command to which the server replies with a list of options。

The sender， select starttiers。The server replies。The two perform a TlS handshake。

 and then the remaining communications between the two are encrypted and transit， excellent。

But so why did we call start Tls opportunistic encryption？

And what are some problems with this approach？To understand that。

 let's consider what things look like when we have an adversary in the middle In the scenario。

 we envision an attacker able to intercept our packages between the client and the server so that when the client sends the Alo。

 it will replay that to the server。But when the server replies with the options it supports。

Then the man in the mill can take those options and relay them to the client。 But in addition。

 the attacker is then able to strip out the star Tl S option。

 thereby giving the client the impression that this server cannot speak Tl S。

Thus causing it to speak plain SMTP and thus allowing the attacker to continue to observe the traffic in the clear。

So this is clearly not desirable。🤢，But S MTP does not provide for any means to start out immediately speaking Tl S。

 and the mail server may have to talk to hundreds or thousands of remote systems。

 How is it going to know when a receiving mail server supports Tl S。



![](img/92098231fa3412ded7d4382c777416cc_5.png)

Wouldn't it be useful if there was a way to look up whether a given domain wants to use TLS for all its MTAs？

Well， what do we do when we want to look up something， Why we asked the DN S。

So here we are performing a text lookup against the domain in question with a special prefix underscore MTA STS。

Which stands for MTA strict Transport Security。If your domain has such an entry。

 it is expected to specify the current version of your policy。

As well as an identifier for this policy version， as you see here。But now what。

If you've determined that a domain has an MT STS policy。

 then you can retrieve it by looking for the file，S。

text under the well known path of the server named MTS under that domain。

Such a policy that might look like this。At least， you can specify your Mx servers covered by this policy for how long the client should cash the policy。

As well as in what mode the client should operate。RFC 8461。

 which specifies MTA SDS to find the different modes。

 allowing mail server operators to carefully roll out this policy via a testing mode that then allows the remote client to simply send a report to the server operator if it finds any violations。

In enforce mode as shown here， we are telling the world that this MTA expects to always use star TLS。

 so if you're a client and you connect to the service and somehow it doesn't offer you start TlS。

 then you should abboardt because you know something's fishy。Alright， so let's pretty sweet。

 we can now know whether we should be talking TlS or not。

But we still have another issue which just kind of at the root of the x509 PKI we use for TLS。

 how do we know that we can trust the certificate we are presented？Normally。

 we verify against a rude trust bundle。 But let's suppose that for whatever reason we can or don't want to do that。

 or perhaps it's considered that the evil man in the middle was able to issue a certificate for the target domain that would validate by our trust bundle。

 but isn't， in fact the all un we want。We can simulate the case of an invalid c by removing our trust bundle altogether。

So， then。Our connection using Star Tls。

![](img/92098231fa3412ded7d4382c777416cc_7.png)

Will， tell us that this serves no good。Now note that here we are still able to talk as MP。

 That is the failure to validate does not prevent us from sending mail To do that。

 we'd have to make a decision to abort。But anyway， so now without a trust bundle。

 how would we know whether the certificate presented by the server is authentic？Well。

 what do we do when we want to look up some information。We asked the DNS again。

If we make a DNS lookup for a TLSA record using this special name。

 encoding the port and protocol that we're interested in， Ie TCP port 25 for SMDP。

We might get back a record like this。This type of record。Is part of the so called Danin standard。

 which is defined in RF 6698 and stands for a DNS based authentication of named entities。

Using this standard， we can assert the authenticity of say a TlS certificate without the use of a PKI。

 That is the TlS record here includes the Sha 256th check sum of the public key of the certificate and because we used DNSSec。

As shown here by the authenticated data bit in the dig output。

 we know that this information is accurate。

![](img/92098231fa3412ded7d4382c777416cc_9.png)

So now， with this information。We can add these flags to the Esclline command here。



![](img/92098231fa3412ded7d4382c777416cc_11.png)

Passed the TlSA record。And then。Our connection again becomes fully validated and authenticated。

If we scroll back up here， we see that the open SSL command tells us the validation happened using Danne。

Al right。 so once again， I hope I was able to spark your interest in a topic that is obviously much more complex than what we can cover here in this video。

 but as quickly recap what we did discuss from our last video。

 we remember that SMTP is a clearex protocol so that in order to protect communications and transit。

 we can use star Tls， which allows the client to begin opportunistic encryption with the server if the server offers it。

😊，This is pretty neat， but as we know， TLS also allows us to get authenticity guarantees since we can validate the certificate and thus establish that the server we're talking to is indeed the one we think we're talking to。

But since Darts is merely an option offered by an MTA。

 we also saw that Neversari in the middle could simply strip it out。

 and we wouldn't be none the wiser。One mechanism to protect against that threat is MTAs strict transport security in which we use the DNS to look up information about our mail server。

 Polo Web server using HTPS， and then can determine whether we are supposed to talk to your less with a mail server in question。

We also discussed another thread， however， that of an attacker posing as our mail server and presenting an invalid certificate and us looking for a mechanism to validate the certificate without relying on the X 509 PKI。

To address that， we saw the use of the DanE protocol。

 which once again utilize information from the DNS to validate the remote certificate。

Now with all these mechanisms， we have the good level of assurances that the system we're talking to is the one we want to talk to。

 but this still poses one final dilemma， what to do if we are running into a problem。

Should any of these possible failures then prevent us from sending mail， if we do not feel close yet。

 then all these assurances are really not worth much。 But on the other hand。

 experience has shown that it's easy to make mistakes。

 and having a wrongly deployed certificate lead to mail not being delivered can be a high cost。

For this reason， you'll find only few services on the internet configured for enforced MP STS。

 for example， Google recently within the last year or two， I think， did enable this。

 but most of the other email providers are still operating in testing mode where they collect failure reports only。

Unfortunately， not many services on the internet utilize Danne， which of course。

 is a result of DNS segment being widely deployed， as we had discussed in the previous video。

As so often， I'm afraid I can't provide easy solutions， but I hope that with this video。

 you learn a bit about how to protect meals in transit。

We're slowly to discuss the remaining issues we had hinted at earlier。

 We've established ways for the email client to assert the authenticity of the server。

 but we have not at all addressed the problem that any information sent by the client can be completely made up。

So in our next video， let's dig into how we can protect against having our poor mail server get abused to spam our users。

Until then， thanks for watching， cheer。

![](img/92098231fa3412ded7d4382c777416cc_13.png)