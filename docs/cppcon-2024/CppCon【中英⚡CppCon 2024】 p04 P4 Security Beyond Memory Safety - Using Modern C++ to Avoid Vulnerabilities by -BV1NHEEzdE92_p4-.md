# CppCon【中英⚡CppCon 2024】 p04 P4 Security Beyond Memory Safety - Using Modern C++ to Avoid Vulnerabilities by -BV1NHEEzdE92_p4-

Something really valuable about actually attending and being here in person is having the opportunity to。



![](img/3026c275adbf788da8d8c2461251cc37_1.png)

Actually， we ask the speakers while they're there， go up to the microphone。

 ask a question that you have or meet them after the talk。

 chat them out in the hall there's just a lot of。Opportunities if， you know。

 something isn't really clear to you to kind of just get in there and get a much clearer answer if you need。



![](img/3026c275adbf788da8d8c2461251cc37_3.png)

![](img/3026c275adbf788da8d8c2461251cc37_4.png)

This is my first time attending CPPCon in person， and I hope you are equally excited as I am to talk about security beyond memory safety。



![](img/3026c275adbf788da8d8c2461251cc37_6.png)

![](img/3026c275adbf788da8d8c2461251cc37_7.png)

Now I will first talk a bit about my perspective on memory safety because it will be slightly different than what you've heard for example。

 in Herb's keynote before， then I will introduce myself and talk actually a little bit about security as a whole because for the rest of this presentation we actually want to come up with secure design So what actually means secure design we need a way to actually discuss argue whether something is secured and after we've established this baseline we can finally talk about how we can use modern C++ to avoid vulnerabilities by design。

😊，So let's start by talking a bit about memory safety。

 There's basically no discussion about C++ at the moment that doesn't talk at least a little bit about memory safety。

 right。😊，And if you Google for C++， and especially the experiences that people have。

Especially new join us to the language。 you get descriptions kind to working with C+ plus。

 like 50 shades of shooting yourself in the foot with a rega。😊。

And while this may be due to inexperience， but how did you join us get experienceience first right。

 maybe a lot of outdated tutorials and so on， a large part of it is attributed to memory safety or the lack there of I would say。

 right， because it's very hard to get into the language if you are only used to very high level high abstraction languages that take care of everything for you。

😊，Yeah， if， if you have never even written any programming language before。

But it's not just the new join us。 It's also the people that have been there for quite a long time。

 right You may have seen this press release by the White House from February this year。

 future software should be memory safe。😊，Because those are kind of the users are the people that get the products built in C++ right and they are also caring about memory safety because well。

 lots of bugs are attribute to that， but more important is the sentence below。😊。

Address the root cause of many of the worst cyber attacks。

 And this is what I'm interested in much more。 So let's look at what attacks are out there。 right。

 This is the common weakness inumeration， top 25。 I don't want you to read the list at all。

 I want you to focus on the title。 because it says stubborn weaknesses。

 And they define stubborn weaknesses here as 15 weaknesses that have been present in every top 25 vulnerability list of the past five years。

😊，And then they analyze this list and they say out of these 15，5 are attributed to memory and safety。

So one third， right， And that's a substantial amount， I would say。

 And this is not just of academic structure， anything。 If we just look。

 there was a nice article here， there's a zero click Windows， T CPP， I， R CE that impacts Os， okay。😊。

There was an integer underflow in the IPV 6 stack of windows that caused a buffer overflow and enabled arbitrary code execution。

 So an a attacker could just send a few IPV6 packets to your machine and take full control。😊。

Due to memory and safety， And this is super recent。August 14。Okay， so。Let's just use rust。

 and everything is fine， right。Now， kind of， the problem is we cannot just use rusts。

 even if we wanted to use Rus now for everything。If you're working in embedded。

 the compilers are not there for other platforms。If you have a code base that is huge millions of lines。

 you are not going to convert this to us。 the cost is just way too high。

 and then there's training people and so on。 so a lot of arguments I'm not going to dive too deep into this。

 But if we look now inside of C++ we also know that there is a lot of effort spent and not just recently right we have the C++ core guidelines and we have them for a very long time。

 they are focused on safety。We have been with C plus+ 11 stuff like SmartPoer and so on。

 We got the standard ranges that help us make less mistakes， avoid these issues。

 and now our honest behavior with C++ 26， which is going to be a great improvement here。😊。

And even around the C++ ecosystem with like CPP front， carbon， circle comps on。

 we have a lot of activities that want to address memory safety。😊。

So for the rest of this presentation， let's approach this burning topic of memory safety。

As if it was solved， or as if we at least don't have to care about。

 there are smart people working on this， and they will hopefully find a solution。

But the solution is not there yet。😊，And we will still need to think about how we can work with the code that is written now that has been written in the past and that will be written in the future to actually come to security beyond memory safety。

Because even if we would now fix all of the memory safety issues。

 our software would still not be secure。You can take this from the numbers。

 one third of the issues were memory safety related， but there is much。

 much more just to illustrate there was this famous GPAC in 2015。

 where hackers were able to remotely take over several Jeep vehicles and completely engage or completely disable the brakes。

 for example， remotely without any interaction and it resulted in Christling to recall 1。

4 million vehicles， imagine the cost。😊，And they are some other nice stories like this year how I hacked my car blog post by Green Luigi1。

 They wanted to install custom firmware on their infotain system of the Hyundai。

 did some reverse engineering found out that the updates are signed。 So well。

 they don't have the private key。 They cannot sign。 right So they reverse engineered further。

 found the public key for the verification。 Googled the public key And the first match was an open SS L tutorial。

 So the key was taken literally copy paste out of a tutorial where， of course。

 the private key was also written。 and all leads to doom， right， So。😊。

A really nice example and this is exactly what motivates me so hi I'm Max Sofman I'm from Germany and unlike I guess many of you I have not studied computer science at all。

 I have studied cyberse from the beginning at one of the leading places to do so the Hu University Boham and even that my PhD there association with the Maxplan Institute and I'm still affiliated as an external lecturer there teaching the next generations about security outside of that I'm working as a security manager at IA that's a subsidiary of Bosch where we are writing software for the automotive industry and I'm the security manager for all of our onboard core security products。

😊，So I'm handling everything from setting up processes， doing security reviews of designs。

 architectures and code， but also handling vulnerabilities and so on。Just as a disclaimer。

 I'm not sent here by my employer， so the views I express are my own， not necessarily the ones by Es。

Okay， let's talk a bit about security now， because if I would do a poll。

 I would guess and ask you about like what is the relation between bucks and vulnerabilities。

 I guess the picture that we could paint is something like this。

 at least this is what I've seen a lot。And it's horribly wrong。Because。Let's look at a simple。

 real picture that shows you that vulnerabilities are actually like overlapping。

 but not a subset of bugs。So this is a real picture from the University of Belaffa in Germany。

 And you can see this system is back free。 Yeah The barrier is raising。

 lowering exactly as specified。 you cannot make it raise without an I D card。 Everything is fine。

 but it's clearly vulnerable right And the reason is that， well， they are not overlapping。

 they are overlapping， but they are not one integrated into the into the other because bucks are about a violation of the intended behavior。

😊，A violation of the specification and the specification describes what we intend。



![](img/3026c275adbf788da8d8c2461251cc37_9.png)

But security is not about what is intended， it's about what is possible。

 And we can clearly see the mismatch here。 And well。

 the university saw that too and patched the vulnerability by putting these stone pillars on there。

 But well， it took them apparently quite some time。So how did they even get into the situation first。

 that they had this insecure barrier installation and we don't know， right。

 but one way we could say is that they had an incorrect attacker model。

Because arguing about security is mostly meaningless without a proper one。Look at this。

 like raise of hands。 is the secure。Is this insecure？Got you。 You cannot raise your hand。

 You don't know against whom。😡，If this is a gate they shall keep out animals。I guess this is secure。

 even with a zip tie。