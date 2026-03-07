# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p40 p39 Week 08, Segment 3 - E-Mail, Part III -BV11QQcYmEzD_p40-

Hello and welcome back to CS 615 System Administration。 This is week 8 segment 3。

 and we're still talking about email。In our last video。

 we had seen the use of Tl S to wrap Plat STP in a transport layer encryption。

 which is nice and well and provide some security， but unfortunately。

 does not solve all the problems one might have with email。In this video。

 we'll take a closer look at the elephant in the room， spam。

As mentioned in our first video on the topic， Spm makes up for up to 70% or more of all emails sent。

So let's take a look at why it's so easy to send unsolicited email in bulk and what defense mechanisms we have against it。

So here in the bottom window， we have our email client mut and up here in the top。

 we are once again sending a simple email from our E to instance。After we submit the mail。

 we know that the sending MA will connect to our receiving MA and hand the mail。

 which will then processed locally and eventually delivered it into our inbox。There it is。



![](img/b3f815105816088595f8cc704563b57b_1.png)

When we look at it， we see the various fields from to subject and the contents of the male。Now。

 let's compare to sending the same email manually using Open SSL S client again， also like before。

We specify the mail from。And recipient two fields。And then add our text here。

Then we wait for the mail to be delivered。But when it shows up in our inbox。

It originates from the spamd user。When we look at the contents of the mail。

 it looks rather different。Specifically， it tells us that our spam detection software by running on the mail server here has determined that this email is well。

 spam。As you scroll through the text here， you see that the spam assessment tool appears to have several heuristics to determine the probability of an email being spam。

 including missing headers。Since these various properties add up to a score above the currently configured threshold。

 the system marked the messages spam instead of just dropping it into an inbox。

So let's see if perhaps we can outwit the spam detection system here。Let's try again。

We once more specify the same mail from and recipient two fields。

But then when it's time to provide the data， we also fill in some additional headers。A from hiter。

 it looks more normal。A shoe header。The subject header。

As well as the other headers that the spam detection system had complained about being absent。

So now we enter this email to the mail server。It shows up in our inbox。As we'd expect。

 not mark the spam。There， that looks much more normal。Here is the date header。

 We had specified the from to。And subject。But where is the message I D header。To view that。

 we have to ask our male client to show us all the headers。

 Most email clients only display a small subset of headers that the user may be interested in and hides the others。

So now when we look at all the headers， we notice quite a few more details hidden in our email。



![](img/b3f815105816088595f8cc704563b57b_3.png)

Let's get rid of the second window up here for the time being。

So now we see up here at the top from header， some information that I was spamces added here。

We had claimed that no， this message does not look like spam。

 as well as some headers telling us how he received the message。

Even including the T L S cpher and strength used。Down here， we have another from header。

 but that's different from the from header we have way at the top。

 And the male client only showed us the second one。

So we see that an email is a bit more than just what we've come across so far。In particular。

 an email consists of a few mandatory headers。 Without these headers， the email cannot be delivered。

This includes the from header， also known as the SMTP mail From header up here。

 as well as a recipient obviously and the date header。In addition。

 the email may have any number of optional headers。

 They're truly optional in that the mail protocol doesn't require them， but as we've seen。

 their absence may lead other systems to classify the mail spam because well from emails sent by actual friendly cooperating email systems tend to include them。

These headers include the cosmetic from header， which we notice can be different from the SMMTP male from header。



![](img/b3f815105816088595f8cc704563b57b_5.png)

The two header， which can also be different from the SMTP recipient2 header， the subject。

 and so on and so on。As we've seen a little bit， some of these option headers can be used to relay a lot of useful information about the email to the receiving system。

Now， of course， we also have the content of the message。

 which we generally consider to be plain text， or unfortunately， HTML nowadays。

But the content is really independent of the simple mail transfer protocol and may even contain attachments and multipart messages all defined in another standard。

But for the time being， let's keep our focus on the email headers and how our spam detection system reacts to them or uses them。

So let's go back to our E two instance and try something else。

Let's specify a random mail from address here。And then。

Let's try to send an email to my Steven's address。Now， this mail server immediately says not so fast。

 my friend， I'm not responsible for Steven St Eduu。

 So I won't let you send mail to that domain from me。So perhaps let's try another mail server。

We all know that Yahoo runs a mail service that anybody can sign up for。

 And surely Yahoo can send an email to Stevens， right。So let's give that a try。Again。

 same mail from address。And same recipient。But nope。

 Yahoo doesn't allow relaying email for domain that is not responsible for either。

This is known as not relaying email。Back in the early days of the Internet。

 there were only so many mail servers and any mail server was happy to accept mail for any other mail server and handed it off to them to relay the mail。

😊，But then， of course， meant that you could abuse the other mail server and send mail through it to other systems。

 So with time， mail server said， you know what， I only allow people to hand me emails that are for my users。

 which is what you're seeing here in action。 Then advise your email server is not responsible for the Steven St Iu domains and rejects our attempts to send an email to that address。

Now， there are still a few so called open relays on the Internet to day。

 but they are oftentimes abused by spammers to deliver the mailre for them without being detected and thus end up on various Internet block lists。

But， anyway。So if we want to send an email to our Stevens address。

 we have to talk to the mail server responsible for that domain。

Which we can look up via the Mx D S record。So let's give that server a try。Hey， look。

 that one's not shutting us down right away。Let's create an email and see what that looks like when it shows up in our inbox。

The mail will， in fact， be delivered to a local inbox in a window below。

 because I have my Stevens account set up such that all mail from there as automatically forwarded to my private address。

Okay， so our mail server has accepted the mail and。Wait for it。Down here。It comes it。Okay。

 so that looks fairly normal。So we've shown that in order to send email to a specific domain。

 you pretty much have to talk with the responsible mail server and that open relays are not by and large used any longer。

 which shall address one part of the spam problem。 but obviously we still have some work left。



![](img/b3f815105816088595f8cc704563b57b_7.png)

Let's look again at this email we had opened a minute ago。

We have a from address as some user at this easy C two instance。

But specify the different user down here。 So maybe if theres no relation between these two。



![](img/b3f815105816088595f8cc704563b57b_9.png)

Can we just send an email pretending to be somebody else， Let's give it a try。Let's again。

 talk to our mail server here， and。Let's pretend we're sending an email from。 No， I don'n know。

 Let's say Barack Obama， who wants to invite me。So we specify all the headers。日本の？Type or a message。

And send it off。And here， it shows up。And sure enough， it looks like it came from my good friend。

 Barack。Let's look at the headers。And yet， this email definitely came from Barack Obama。

 No two ways around。 That is there。So， in other words。SMTP provides no authenticity guarantees。

If you can send me an email， you can pretend that you are whoever you want to be， really。

The SMTP mail from can be said to anything。And doesn't even have to be in alignment with the from header that you are showing。

 but sometimes spamers use when the mail server tries to only accept SP mail from headers in saying its own domain。

But that seems like a huge problem， right？ How do we fix this， I mean。

 the mail server can restrict what mail it accepts， which makes sense。

 and it knows what domain is responsible for。 But just how is it supposed to know whether the system connecting to it is responsible for the email that it claims to be sending from。



![](img/b3f815105816088595f8cc704563b57b_11.png)

But wait a second。 if we are connecting from an I address。

 maybe there's a way to determine whether that address should be allowed to send mail on behalf of a given domain。

Let's give this another try， using a different example。

Let's try to send a mail through Yahoo service， again。This time， pretending to be from Bill Gates。

 why not？All right。 We already knew that Yahoo doesn't allow relaying mail。

 So let's instead have Billgate sent this mail to my Yahoo account。There， of course。

 Yahoo accepts mail that goes to Yahoo dot com makes sense。So here comes our approved email。

Since obviously， all these people want to communicate with me per email。But what's this？

 Yaho tells me it won't accept my mail。The website that references here will give you more detail on why it rejected our on mail。

But let's see how it figured out that it shouldn't allow as random easy see two instances sent me on behalf of Microsoft dot com。

And what we do， I want to look up some information。Why to the DNS？Here。

 let's make a DNS query for a text record in the Microsoft do com domain that matches SPF。

Look at that。SPF。Stands for S policy framework。 and there's a way for you as the domain owner to specify what systems are allowed to send email to behalf。

Would this Seia an effect this。Include the results of these other Dous lookups。

 but then deny anybody else。So let's look at one of these。Underco SPF A。

micsoft do co expands to these net blocks， specifying that any SMTP connection from these IP is allowed to send email for the Microsoft。

 com domain， but nothing else， which is by Yahoo knew not to let us send mail on Microsoft's behalf。

What does this look like for my own domain？This entry here says that any I addresses for Nemistar。

 org， as well as the Mx record for this domain are allowed to send mail， but nobody else。

Let's compare to what Google uses for Gmail。Okay， redirect。Looks like that also uses some net blocks。

And now back to our original victim， Po Barack Obama。



![](img/b3f815105816088595f8cc704563b57b_13.png)

Looks like Obama dot org uses a sales force and send grid to send email。

 But note that the last word there is not minus all， but tilder all。

 which indicates a so called soft failure。W the Microsoft example had a so called heart failure。

So our mail server up here can actually reject the email right away when it checks the mail from address。

Even before accepting any more data。Well now note that the SPF heart and soft fail modes do not necessarily imply that the mail is to be rejected by the mail server。

 It merely indicated to the mail server that it should consider。

And if we then look at the headers from our email that we sent pretending to be Mr。 Obama。



![](img/b3f815105816088595f8cc704563b57b_15.png)

We note that the headers include this information。 Obaama。

org discourages the use of this random E C2 IP P address as a permitted sender。

And the system processing that may may then decide what to do with this information。

A common example might be to place the mail into a quarantine inbox or to otherwise label it as possible spam。

Now， in the case of the heart S PF failure， we have seen both the Yahoo and my mail server。

 not even accepting the mail。 But if we had tried to send thepoof Microsoft mail through the Stevens mail server。

 it would have been delivered， but then gotten a note in the headers like this。SPF failed。

 Microsoft dot com does not permit this random easy to address to send email on its behalf。But wait。

 so Steven's email server sent the SPF failed email so that the email server seems to act differently from the others we've seen。

As I mentioned before， if I send email to my Stephen St E U address。

 it gets automatically forwarded to my private mail server。There。So， now。Let's take a look。

At the full headers here。Okay， that's a lot。Let's see what might be of interest in this context。



![](img/b3f815105816088595f8cc704563b57b_17.png)

Over here， weve seen authentication results， etcter， and。Wow。

 a whole bunch of Microsoft exchange data here。Let's change our display to show us only the headers we care about right now。

First， let's take a look at the path the email took。



![](img/b3f815105816088595f8cc704563b57b_19.png)

We know it was forwarded from Stevens to a mail server。 But what did that look like exactly。

We see several received hers， which provide us with the exact path the email took。

It starts out being sent by a local user accepted by the local MA on our EC C 2 instance。Which then？

Talk to this M X server responsible for Stevensedu。

 which appears to be an outlook do co hostted domain。

Which then talks to this other mail server in the Office 365 domain me。Internally。

 using Tl S and IBV6。Which then connects to。Another internal system。Before then。Being delivered。

To my mail server。Which then feeds it into spammicatin， as we've seen before。

So this email did go places in between being sent and being delivered into my inbox。But。

If we look at this path， how would we know that the email that entered the system is indeed the one that was delivered in the end。

That is， how do I know that the party invitation for my good friend Barack over here is actually authentic。

It could have been the case。 and， in fact， it was Michelle。

 who wanted none of Barak's nonsense this weekend， but Barack hacked into the intermediate mail service and changed the mail。

Now， we already know that the origin I P may not have been trustworthy for the Obama org domain。

 which is why SPF told us to be careful， but also note that we have an additional header。

 authentication results that tells us something else。



![](img/b3f815105816088595f8cc704563b57b_21.png)

It says message， not science， meaning a few things。It implies that messages can be signed。

 that this message was not signed and that we have to learn about one more system， De him。



![](img/b3f815105816088595f8cc704563b57b_23.png)

Deakcom stands for domain keys identifieddentified mail。

 Another way to detect emails moving by providing the digital signature across parts of the message。

It was developed by combining two parallel efforts by Yahoo and Cisco。Then standardized in RF 4871。

 and now RF 6376。And it adds yet another header， the deakim signature header。

 which we'll see an action in just a second。And if youre wondering what else we might need if we want to verify such a signature。

 And if you then guessed， oh， I don't know， but I be it involves the DN S。 Well， you'd be right。

 We get even more DN S text racks。Look， I told you that we depend heavily on the DN S。

 even though nobody uses DN Sec and the DN S really cannot be trusted。 Welcome to the Internet。



![](img/b3f815105816088595f8cc704563b57b_25.png)

But let's look at Deamman action to understand just how exactly it's supposed to help us。

Let's send an email from our own mail server to my Steven's address。

My mail server is configured for use with Decapm， so we'll sign the message and send it。

It will then bounce around the Stevens or rather Out Office 365 mail service。

As we've just seen before being delivered back to this mail server。There it is。Let's take a look。

Here are our headers。We see the deamm header， but let's quickly weed out the ones we don't care about and have much display the dechem signature and authentication results headers in the default display。



![](img/b3f815105816088595f8cc704563b57b_27.png)

There， so here we see multiple deccom signatures and multiple authentication results since our email traversed multiple mail servers。



![](img/b3f815105816088595f8cc704563b57b_29.png)

Let's start at the bottom。Here we see the signature made by our outgoing mail server with authentication results showing both the pass of the SPF check。

 as well as the dem signature was verified。Likewise。

We see that the Stevens mail server over at Microsoft also signed the mail and then forwarded it back to us。

But。😔，Wait， it says down here， signature was verified。

How did the remote server know how to verify the signature。



![](img/b3f815105816088595f8cc704563b57b_31.png)

And what exactly does this blob of a signature actually signify。

So the deam signature includes information about which domain it is responsible for。

 that might not work in this case。The so called selector which allows for using multiple key pairs。

 In our example， the mail server uses a selector of 2021。



![](img/b3f815105816088595f8cc704563b57b_33.png)

And then includes a hash of the body of the email， thereby guaranteeing that the body cannot be modified and I know that it was indeed Barak's invitation to his party and not Michels not mixxing the party。

But Deam also extends to the headers。 since， as we've seen in this video。

 they play a rather important role here。 So we are informed which headers the signature covers to subject date and from in this case。

And of course， it then includes the actual signature of the data。But okay。

 so now how do we verify the signature？Dont we need to know which public key to use to verify the signature with well。

That's where the DNS comes into play again。In order to determine the right key。

 we can look in the DNS for the correct public key for the given selector。

We combine that with a string underscore domain key and the domain in question。

And we get back the public key that can verify the signature in the header。Pretty neathu。But hey。

 what's this down here in the deki header。 It says something else。Dmar pass。

 Now what on earth is Dmar， I thought we were done here。Well， not so fast。 I'm afraid。

We've seen that we can use SPF and Dcam to provide some assurances。

 but we still don't quite know what to do when we find a mismatch。As a receiving mail server。

 we have to be quite careful about what mail we reject since a false rejected email as something that people can get pretty upset about。

 much more upset than about a falsey accepted spam message。

So how do we get the sending domain to tell us what we should do when we encounter bogus SPF or Deum information？

Well for that， we have Dmar to main based message authentication， reporting and conformance。As noted。

 it combines the use of SF and Dkim， but also checks that the SMTP mail from the from header are in alignment。

 as well as what to do when there are mismatches。It further defines how to report such problems into whom。

 And， of course， it uses the DN S。 A pet you are coming that India。So， now。Let's see that in action。

 too。

![](img/b3f815105816088595f8cc704563b57b_35.png)

For example， we can look up what Yahoo's Dmarc policy is in the DNS。

This entry here tells the world that if you encounter an email that doesn't match Decom and SPF。

 then you should reject that mail。So now let's see what happens when we talk to one of Gmail's M X servers and pretend to send an email from a Yahoo address。

We know that Google should now perform an SPF check at a minimum。

Let's construct the bogus email to some random Gmail account。Because of Yao's demar policy。

 this email should get rejected。

![](img/b3f815105816088595f8cc704563b57b_37.png)

And it is。And note it is explicitly the demar policy that triggered this rejection。



![](img/b3f815105816088595f8cc704563b57b_39.png)

And see what other company demar policies look like。Google， for example。



![](img/b3f815105816088595f8cc704563b57b_41.png)

Is a bit perllnient， rather than instructing Ma service to reject Miss Mated Ma that says， go ahead。

 accept them。 But please mark them as bogus and put them into a quarantine inbox。



![](img/b3f815105816088595f8cc704563b57b_43.png)

While Facebook， for example， a strict Le Yahoo here。



![](img/b3f815105816088595f8cc704563b57b_45.png)

So how did Dmar help us here？We saw that SF can tell you who is authorized to send mail。

 but you could conceivably use an authorized I P， but then set the from address later to something else。

 which users wouldn't notice。 Dmark can enforce alignment here。

We know that Deakcom can sign parts of the message。

 but we didn't have a good mechanism to tell the receiving mail server what we do when it encounters a mismatch。

 Demart provides this mechanism。But Dmar can also allow some final control。

 It's not reject or accept， but you can also quarantine， for example。And finally。

 if you'd like to know what the different problems are。

 the mail service was observed for your domains。

![](img/b3f815105816088595f8cc704563b57b_47.png)

You can ask them to send you an aggregate report。Which allows you to then fine tune your enter spendm mechanisms accordingly。

All right， let's take a break here。 We've covered a lot。

In our effort to understand how spam protection mechanisms work。

 we've seen that we need to pay attention to the STP headers， some of which are mandatory。

 some of which are optional。And some of the optional ones aren't even quite so optional。

Weve also seen that each hop along the path and email takes may add additional headers。

 which provides us with a pretty detailed view with a lot of metadata。Now。

 since email is such a simple protocol and has no authentication restrictions built in。

 it's easy enough to spo messages。So we need a range of spam protections for starters。

We don't allow just about anybody to send Ema through our mail server any longer。

 only to domains that we are in charge of。We can perform dynamic lookups in public blocklists via DNS lookups to ascertain the IP reputation of the sender and then decide whether we want to talk to them。

We saw that no earlier videos。We can use the sender policy framework to define who is allowed to send email on our behalf。

 and we can use Dem to assign parts of the email to assure the recipients of its authenticity and integrity。

And we can inform receiving mail service how they should handle mismatches via the Dmar mechanism。

Now， all of this is probably a fair bit more complex than you initially assumed when we started talking about the simple mail transfer protocol。

 but there also isn't the full story just yet。Think， for example。

 about what happens when mailing lists handle and redistribute emails and what the impact of that ondcom signature is。

 We won't be able to discuss the solutions to this issue in this video。

 but perhaps you consider this another jumping off point to extend your research。Finally， though。

 it's important to consider the implications of running a large scale email service。

 as we've discussed here。

![](img/b3f815105816088595f8cc704563b57b_49.png)

You need to have solid spam protections in place， many of which overlap but aren't quite identical with fishing protections。

 We'll discuss those a bit later in the semester。Now， if you are sending a lot of email。

 you need to understand the impact of all those lookups we're performing， for example。

 as well as all the traffic we're logging for each connection。 As we've seen in an earlier video。

 there's quite a few messages logged for every individual message。

 So now multiply that by a few million。We've also talked about spam a lot here。

 but spas were subjective。What unsolicited bulk email to you may be an important business newsletter or a customer campaign for me。

How do you send lots and lots of email without being marked as a spammer。

 The mechanisms we discussed here can also help you in this regard。Now， in the end。

 you may decide that getting all this right isn't easy。

And perhaps you should outsource this to another company。You've seen that Stevens， for example。

 has made the decision by having Microsoft handle or your email。

 just like Cloudfl handles most of the H DP traffic for Stevens。 But as always。

 this has a lot of implications。Not the least of which are privacy implications。

 because now all your emails are floating around the Internet across systems owned by a third party。

The list of difficult aspects and implications of managing emails at scale goes up。

 and I hope have been able to give you an impression of the depth of this topic。As always。

 we can cover all nuances and oftentimes only hinted some of the larger topics。

The best way for you to understand the material， though。

 remains playing around with the commands and examples from these videos yourself。

Try to find out how the different popular email services handle sending and receiving email。

 Look at the headers of the mail you receive。 Try to spoof some mail and see what spam protections are in effect。

 Im sure you'll find out some interesting angles and have a bit of fun in the process。And with that。

 thanks for watching。Jes。

![](img/b3f815105816088595f8cc704563b57b_51.png)