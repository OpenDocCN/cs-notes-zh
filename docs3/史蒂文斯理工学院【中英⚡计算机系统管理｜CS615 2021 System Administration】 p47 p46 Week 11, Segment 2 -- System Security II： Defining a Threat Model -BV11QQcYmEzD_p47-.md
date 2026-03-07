# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p47 p46 Week 11, Segment 2 -- System Security II： Defining a Threat Model -BV11QQcYmEzD_p47-

Hello and welcome back to CS615 System Administration。 This is week 11 segment 2。

 and we continue our discussion of system security。In our last video。

 we talked about the concept of risk assessment。 and we concluded that rather than try to make a system secure。

 we should instead be a bit more realistic and perform a proper risk assessment。

 whereby we seek to identify specific risks that we can then try to minimize。

But we noted that in order to be able to do that， we'd need a threat model。 So let's talk about that。

 In this video， we'll define what a threat model is， how we can formalize this model。

 and most importantly， that it's imperative to keep the attacker' motives and capabilities in mind。

Much of the content here in this video is derived from an introductory conference talk I gave a few years ago。

 so you can also refer to the blog post right up included in the links for additional context。But O。

 so let's get started。 Similarlyly to how we perform a risk assessment for a proper threat model。

 we also need to begin by identifying just what exactly it is we're protecting。

 As we mentioned the last time， the different assets we have will likely to lead us to identify different types of threats and vulnerabilities。

But we didn't really discuss， just。Who it is that might attempt to exploit the given vulnerability。

 And that really can make an important difference in determining your mitigation strategy。

It's important to keep in mind that your attackers are actually human beings with very specific goals。

 You are not attacked willyly， but generally， with very specific intentions and desired outcomes。

That is， different attackers have different motivations， and perhaps more importantly。

 different attackers have different capabilities to execute types of attacks。

We'll get back to this in a few minutes， but hopefully it's obvious that an individual。

 frustrated teenager has a different objective and ability to harm your assets than a nation state attacker with a literal army of highly trained experts in the military industrial complex at their service。

And perhaps this also gives you an idea that there are some things you simply cant defend against and that it's not useful to waste resources against something that you can't do anything about。



![](img/0e4efbb0c507e86cb1b154076e21746e_1.png)

In this context， I always like to refer to this wonderful article published a few years ago in the Eusni's Loin magazine by James Mcickens。

 which summarizes the concept of a threat model rather succinctly。

If your concern is that a scorned lover breaks into your email， change your password。

 If your concern is that criminals are trying to take over your account。

 don't click a link sent to you via email that then asks you to log into a site without using your password manager or multifactor authentication。

But if you are facing a capable and motivated intelligence agency。

 chanceances are you aren't going to be able to defend yourself。Well， now， that， of course。

 is a bit niilistic。 And while this is true for most people for system administrators and people working in the information security industry。

 we actually are interested in defending against such adversaries as well。

 So it'd be nice if we had something a little bit more formal to define our threat model process。

 an approach we can follow beyond passwords and magical amuls。😊。

So let's try to break this down a bit。First of all。

 we begin by identifying the possible threats we know about。 then， and that's right。

 Were back to drawing Venn diagrams。 We're looking at what kinds of threads we actually care about。

 For example， we may not really care about the physical value of the hardware in question。That is。

 if an opportunistic robber manages to scurry off with serviceing questions。

 we don't really care about the monetary loss of the hardware。

 It's the data we're primarily concerned about， say。Next。

 there are some threats that we can defend against。 This is the tricky part。

 We have to be honest with ourselves and decide consciously what our defensive capabilities are。

For example， when outsourcing hardware management to Amazon EC2。

 we understand that it is possible that a capable adversary may legally force Amazon to install a back door and the hypervissor that our VMs are running on。

 but we implicitly accept this threat as something we cannot defend against given our current capabilities and infrastructure requirements。

Accepting certain threats as outside the realm of what we can defend against does not mean we simply throw our hands in the air and give up。

 But rather that we are being realistic and decide not to waste time and money on efforts that would ultimately be futile。

So from these circles， we built an intersection of threads。 we then decide to defend against。 Ne。

 there is a subset of all the threats we know and an intersection of threats we care about and can defend against。

That means that there will be some threats that we know about。

 but don't care about or some threads we don't know about， but wouldn't care about if we did。

In those cases， that's not a problem since we have consciously placed those to be outside of our threat model。

The threats that we know and care about， but decided not to do anything about are then what is commonly termed the accepted risk。

 You understand that there is risk， but you are willing to take it。

Sometimes this decision is forced on you simply because you cannot defend against this threat。

 as in the example I gave a minute ago regarding hardware compromise of EC2 VMs。So by and large。

 the objective of your threatened exercise is to increase this intersection wherever possible。

And you should be careful not to waste time and effort on threats you can't defend against anyway。

 especially if you don't even care about a given threat。

Although sometimes you may deploy defenses just because you can。 But the biggest issue， of course。

 is that there are some things you don't know about。

 And it's particularly hard when there are threats that you could defend against。

 had you only known about them。For this reason， it's so vital that as system administrators。

 we continuously keep up to date with the developments in the industry and the information security space。

But all this is still very abstract。 So let's take a look at a more formal model that can help you identify the different threads。

 One of these models is stride， which map specific threads by category to a givenon system property。

Spooothing， for example， a threat against the authenticity property。Tempering against integrity。

 repudiation against non repudiation。Information disclosure against confidentiality。

 denial of service against availability and elevation of privilege against authorization。

For each property， you can then begin to enumerate vulnerabilities。



![](img/0e4efbb0c507e86cb1b154076e21746e_3.png)

Which might look like this。As you can see here， you might break down your data model into the different properties and identify where threats against the confidentiality property might manifest。

Each of these areas then can be broken down further to identify much more specific threats。

Which can be done with increasing detail as needed on each layer。

Until you have mapped out a nice graph of all the things that might go wrong。Cool。

 so list allows us to zoom in and out of different system components without being bargged down and trying to secure all the things。

But in this part， we are merely enumerating threats。 How do we figure out what to focus on then。

For this， we can use the dread methodology。 Yep， in fora geeks like acronyms What a shock。

Dread allows you to assign to each thread numeric value determined by asking these questions here。

 we assign a numeric value to each of the attacks， damage。Reproducibility。Exploitability。

Affected users。And discoverability。Some people then also like to add another factor。

 How hard is it to detect the given compromise。You can then assign values to each vulnerability based on these factors。

And the value of the asset。For example， pick a number between1 and 10 to assign to each average the Dt plus D score and multiply it by that value。

 The resulting score should give you an idea on which areas you should focus on。



![](img/0e4efbb0c507e86cb1b154076e21746e_5.png)

Here's an example Dr+ D spreadsheet。I have a link to the Google sheet in the slide so you can check it out or copy it to play around with yourself。

You see that we have here a definition of the assets in the integrity and confidentiality category。

 where we are identifying different trust boundaries and then assign them a numeric importance。

This can then help us prioritize our defenses。We also iterate over the list of possible threat actors。

Which help us clarify just what different objectives our adversaries might have and what methods they might commonly use。

Each threat actor。Has a number of additional attributes。

That help us clarify what they might be capable of。And how they might actually act。Now。

 with all this defiant。We then use Dr plus D over here on the left to itemize the individual threads。

 then assign them numeric values for each of the damage reproducibility， exploitability， and so on。

Averaging these numbers and multiplying by the acid importance then yields a final numeric score。



![](img/0e4efbb0c507e86cb1b154076e21746e_7.png)

Which tells us。That our most critical area to focus on here would be defenses against S Q L injections。

 library vulnerabilities and account compromise。And， of course。

 no discussion of proper threat model would be complete without a reference to this X KC Dcom。

I think it's great because it shows so succinctly that there are certain threats you can't well protect against。

Strong cryptography only works against cryptographic attacks。

 sufficientufficly motivated adversaries will find the weakest part of the system。 Fr。

 the human component and attack that。By the way， the human component is not only easily attacked with actual physical violence。

 but offering large sums of money can easily get you a compromised account。

 which of these methods employed depend again on the attacker in question。

It's another example of how attackers will go for the lowest hanging fruit。

 Atters will continue to employ the cheapest， most effective attack until it ceases to be that。

Nobody is going to burn a $1 million O day if they can compromise your infrastructure with a few simple PHP or SQL code injections。



![](img/0e4efbb0c507e86cb1b154076e21746e_9.png)

That is， your attackers also have a cost benefit calculation they themselves follow。

 They also have something to lose， and they will act rationally within their moral economic frames。

Atters will continue to pursue a given angle， an attack vector for as long as the value they derive from it is larger than the cost to them。

The more time and effort they have to spend on an exploit。

 the less likely they are to continue to use it。One way to shift us in your favor。

 then is to raise the cost of the attack。 make it harder for them to get to the system。

Multifactor authentication， for example， significantly raised the cost of attack。

But there's another thing you can do。 And that's something we all too often forget。

 We can reduce the value of the asset。Anonymize your user data。

 Delete your users's private data after certain periods of time。

 Expre authentication tokens or key materials， reduceuce the lifetime of Yas keys。

 All of this is super effective。

![](img/0e4efbb0c507e86cb1b154076e21746e_11.png)

So to summarize our threat model process。Identify assets and assign values。 No。

 these values can be largely arbitrary， but you should be consistent within the organization and threat more or less to the scale。

 In my example， I picked numbers from 0 to 10。 You could use a larger scale if you need more granularity。

 for example。You strive to identify threats and dread plus D to derive a threat score。

If you're consistent in your use of these numbers， you then get a neat little list of things sort of by priority。

 what to focus on in your defenses。Now， the most difficult part of threat modeling is retaining your focus。

 As we've seen in our examples， you can zoom in and out。On the various components。

 and while you frequently outline your threat model and abstract terms。

 you may need to go into specifics as you translate it into the specific recommendations。

When you try to perform these assessments， it's good to keep in mind that you can't offend against all threats all of the time。

 prioritize and pick your battles。Remember that attackers will always go for the lowest hanging fruit and don't try to shoot for perfect security everywhere。

 but stop the bleeding first。 Fo on what matters。Raising the cost of attack。

 not eliminating the entire threat is frequently sufficient because your adversaries are people， too。

They will make rational decisions as they pursue their goals， understand their goals and objectives。

 and you can better focus your defenses。Okay， I think this about wraps up our quick intro to the concept of threat modeling。

With that now in our tool build， we'll take a look at a few core principles and information security in our next video。

 We will discuss the zero trust model and look at how cryptography can help us raise the cost of the attack until the next time。

 Thanks for watching， Gith。

![](img/0e4efbb0c507e86cb1b154076e21746e_13.png)