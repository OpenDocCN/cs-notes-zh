# P142：p141 9-8 Dan Boneh Interview -- Security - 加加zero - BV1qotgeXE8D

 Great， so here I have Dan Buenay， some of you I hope know， fellow faculty。

 effects senior in the department， who researches cryptography and security。 So Dan。

 how did you get into cryptography and security in computer systems？ Well， first of all。

 I was your background。 Oh， thanks Phil。 First of all， it's a pleasure to do this。

 I'm happy to help with us。 Let's see， I fell in love with crypto at a very， very young age。

 I think it's one of these things where， for God knows why， but my dad， for some reason。

 taught me the RSA algorithm when I was like nine years old。

 And I just got completely fascinated by these big numbers and all of a sudden， they had these codes。

 And then I went in and kind of encrypted a message to my friend with RSA and。

 he thought I was completely nuts。 But that kind of stuck with me。

 And then as I got to college and I learned more about crypto， I just realized it's。

 such a fantastic field。 It's an area where you get to use really deep math。

 Literally 20th century math is like as advanced as the mathematics is to use in。

 computer science gets。 And at the same time， we get to use it for real world applications。

 So people really do care about the results。 In fact， when you communicate with Google these days。

 the key exchange that you're doing is using what's called elliptic curve， D。P。 Helman。

 That is using extremely advanced mathematics。 As I said， 20th century mathematics。 And it's amazing。

 This is like people use this all day long every day without even realizing that they're， doing it。

 So for me， it's just a lot of fun to kind of work in an area that involves both deep。

 math and yet has real world applications。 I should say more broadly。 I mean， I do。

 there are two parts to my work。 I work on cryptography as one half。

 And then I also do a lot of work on computer security more broadly。 For me。

 the problem of security is a small part of computer security。

 The problem of security software is much， much larger than just cryptography。

 And I should tell you that computer security in general is also a fantastic。

 fantastic area to work in。 As a career path， it's a terrific career。

 Can I amend this job security and security？ Yeah。 If I go to sleep now and you wake me up in 100 years。

 the first thing I'll ask is， you know， is computer security still a problem？ Gary， it's you。

 Computer security will only be worse than it is today because we will be depending on。

 computers and networks so much more than we do today。 Well， so students， the class have covered。

 actually， network address translators with， it， you know， NATS， so they're wireless routers。

 You've done some work on kind of the security of these wireless NATS today and some of the， issues。

 You just want to say a little bit about some of the crazy holes that you found out。 Yeah， sure。

 sure。 I've done a lot of work on security， for example， of embedded devices。

 So when you build an embedded device， these days， so what is an embedded device？

 So I'm talking about things like security cameras， photo frames， you know， these are。

 frames that you put on grandma's desk and you can upload pictures to it so she can see， grandkids。

 Photo frames， wireless， you know， printers， routers， all of these embedded devices that。

 need to be configured somehow。 These days， they're configured through our web interface。

 So when companies do this， they have to kind of build a small web application that sits。

 in the embedded device。 Well traditionally， when you build a web application， you would use。

 you know， rails or， jangle or， you know， a lamp stack in general。

 But a lamp stack doesn't fit on a tiny little security camera， right？

 There's no SQL server running there。 So what they end up doing is they end up building their own web application and their。

 you know， their own infrastructure basically for making configuration possible。 And as you。

 well hopefully you will take one of our security classes， which I'll apply， in the next few days。

 Yeah， in T255。 That's how it does in just a minute。

 But you'll learn from those that in fact building a secure web application is non-trivial。

 But after you take quite an effort to secure web applications， even from basic attacks。

 things like cross-site scripting， things like， you know， request forgeries and so on。

 And so we looked， you know， we had like， we bought like 20 of these embedded devices。

 And we started looking one by one at the different application web applications and data on devices。

 And it turns out they basically all had various sorts of vulnerabilities all。 Again。

 it was basically a hardware company。 And this is somebody hacks on a picture frame。

 Why should I care？ Ah， okay。 So you should really care about that。 Okay。

 Because if you're an enterprise and now one of your employees put a picture frame on their。

 desk in their office， that picture frame is going to be connected to your corporate network。

 So I'm glad I'm not an enterprise。 There you go。 Okay。 So I don't care。

 You can pretty much guess the rest。 Great。 Yeah。 And Stanford's computer systems are hacked all the time。

 They're hacked all the time。 So I'm not concerned about any more vulnerabilities。 Yeah。 Yeah。

 I'm not the kind of person you cater to。 I see。 I see。 Okay。 Well， and yeah。

 it's basically these devices are used as stepping stones into larger attacks。

 So if you have a security camera at home， that security camera or you know， even think。

 of the nests like a thermal staff that is controlled remotely， those devices， if they're。

 not properly secured， the nests we haven't looked at。 So I don't know if it's。

 I don't know if the security status is what I am。 But those devices could be used as a stepping stone into a larger attack on your home network。

 on your corporate machine， in the arm。 Exactly。 Exactly。 And by the way。

 all the attacks work today is basically is using stepping stones。 Yeah。

 So they break into one machine from that machine。 They start to do a lateral transfer traversal to try and find other machines that can be。

 broken into from the other machine that they've not taken control。

 They try to get to the administrative accounts。 And so on。

 they move slowly from one machine to another until they get the crown jewels。

 like the database or the after directory。 And then they just dump all the data from there and away they go。

 Well， so this past weekend， there's the CS faculty retreat and you gave a talk kind of。

 about some of the revelations from the stoat， from the Snowden's leaks， et cetera。

 And one of the things you talked about is how there might be some suggestions that certain。

 crypto systems might be weaker than we thought。 So that going into detail is kind of going forward given what we've learned from Snowden。

 If I want to design a secure system， then what other some extra steps I should take。

 or there's some things that you thought might be okay but aren't now and want to go forward。

 and do something slightly differently or？ Yeah。 There are basically two advice bits to keep in mind。

 Well， first， there's a zero advice bits which you will learn which will drill into you once。

 you take the crypto class， CSB55， which is you never design your own crypto and not only。

 should you not design your own crypto， you should not even implement your own crypto because。

 I guarantee you if you implement your own crypto， it's going to be vulnerable to a tiny， attack。

 It's probably going to have bad randomness and it's going to be vulnerable to other side。

 channel attacks and so on。 So you should use kind of existing innovate。

 I wouldn't quite say it that way。 I would say use kind of existing standards and existing open source well-bedded implementations。

 So that's a zero through。 The first rule that I would say that's a result of other revelations from the summer is make。

 sure that whatever you build is agile in the sense that it's crypto agile in the sense that。

 if we discover at some point that there's a vulnerability in a particular algorithm， it's。

 not going to take you six months to then go ahead and on under fire， go ahead and build。

 a new algorithm into your system， QA tested and then deploy it。

 That's a long process which when you do under fire is a bad idea from a security point of， view。

 The idea is to kind of make your system agile to begin with， crypto agile to begin with so。

 that the system will support multiple algorithms back deployment time。

 And then if one algorithm turns out to be insecure then all you have to do is just flip。

 a configuration switch and the system just moves to the other algorithm and everything， works fine。

 Now in the client server model that actually is more difficult because you have to change。

 both the clients and the servers but we've got to start somewhere。

 So for example if you build a web server make sure that the web server can support multiple。

 algorithms。 It's not baked in， the algorithm being used is not baked in somehow hardwired into the web。

 server。 When you build a very common example is a software upgrade mechanism。

 So when you shift software upgrades to your clients those software updates need to be。

 signed so that not anyone can ship an update on your behalf。

 Well you can't imagine how many companies when they build software update mechanisms。

 they just hardwired RSA。 That's the signature mechanism。

 And my point is try to make it so that even a software update mechanism something that has。

 been on is that actually is agile in the sense that there's an easy way to update the algorithm。

 on the fly so that just a matter of simple configuration and boom you move to signatures。

 using a different algorithm。 So that's the first piece of advice behind agile。

 The second piece of advice is in particular when you build an SSL based server today many。

 websites use what's called the RSA mechanism which is the browser chooses a random pre-master。

 secrets， encrypts the pre-master secret using the server's public RSA key and sends the results。

 over to the server the server decrypts and recovers the pre-master secret。

 Yeah this is what I thought when we covered TLS works and it's basic exchange。 Fantastic。

 So this is what I would call the basic RSA key exchange and the problem with that mechanism。

 is it doesn't provide let's call forward secrecy。 So what do I mean by that？

 Well imagine that today someone recorded the interaction between you and the web server。

 so they recorded the RSA encryption of the pre-master secret。

 Now a year from now somehow they were able to break into the web server and recover the。

 RSA secret key。 What that key would allow them to do then is go back to what they recorded a year before。

 decrypt the encrypted pre-master secret and now they can really remember the entire thing。

 Game over。 Exactly。 So the basic RSA mechanism doesn't have what's called forward secrecy。

 There is another key exchange mechanism in SSL it's called it is it's called well it's。

 a mechanism that supports forward secrecy and that's a mechanism that's based on DC， Hellman。

 So there are multiple names for it it's called a femoral DC Hellman in open SSL the name for。

 it is VHE or ECVHE we'll get to the differences between those in a second。

 And the idea there is that the key exchange actually uses the DC Hellman protocol instead。

 of using RSA。 Right。 So what happens is each side the browser says to the server it's part of the DC Hellman。

 exchange。 The server says to the browser it's part of the DC Hellman exchange and the servers RSA。

 key it's only purpose。 It's just to authenticate the servers DHE Hellman message。

 It's just for signing。 So the yeah exactly the server RSA key is used for signing not for encryption。

 So even if the server RSA key is stolen a year from now it doesn't matter because。

 And so in so for secrecy means that even if somebody in the future cracks something that。

 it might might still secure going forward in time。

 If the session was secure today it will secure you'll be secure a year from now even if you。

 lose your secret keys。 So for what secrecy is a pretty important concept it's a good thing to do well you know especially。

 protects you from using stolen and such。 It also limits the amount of time in which a particular key is used because your session。

 really now depends only on that particular DC Hellman exchange。

 Unlike the RSA key where the server has to get a new certificate。

 It's a once it's a whole process it's a whole year。

 But the point is if someone breaks the RSA key somehow not by stealing the private key but。

 somehow by a brute force attack。 If they break your RSA key then would recover all sessions with DC Hellman they would have。

 to break every single individual DC Hellman exchange to recover the session which is a。

 lot more work。 So it's clear going forward that you mean network applications the internet are increasingly。

 important that more and more applications are just on the internet now interconnected。

 and correspondingly security is increasingly important。

 So in terms of classes going forward what are the classes that students could take to。

 learn more about this because in ten years not knowing something about security is going。

 to make you dead in the water。 That's the next question。

 So the security classes are kind of vital to undergraduate education and computer science。

 We get many complaints from industry about universities not us but other universities。

 graduating students who know nothing about security and the result as a result the code。

 they write causes a lot of problems down the road。

 So the classes that we offer are one CS155 I would argue that needs to be a required class。

 So the point of CS155 is A to teach you a lot of defensive programming but more importantly。

 it's to get you into the security mindset and the way we do that is we teach you a lot， of attacks。

 So the only way to learn how to defend against attacks is to know how to do the attacks yourself。

 So we teach you how to break things but more importantly we then draw lessons and teach。

 you how to defend against those attacks and kind of get into the security mindset。

 Whenever you write code think about how that code can be exploited and what would go wrong。

 if the code is exploited。 So the security mindset general principles for writing secure code things like defense。

 and depth， lease privilege and so on。 These are things that we just go on and on and give many examples of those issues in CS155。

 So that's offered in the spring。 It's co-taught by myself and John Mitchell。

 Another class that's worth taking is the crypto class if you're more interested in learning。

 how a cryptography works。 And I can tell you the interesting thing is that there are many companies who actually。

 use crypto but they have very little crypto expertise and so by kind of taking that class。

 you'll know what needs to be known about crypto in order to use it properly and whatever。

 job you go to you would actually become the go-to person at that company to deal with。

 any crypto like issue。 So it's a valuable knowledge to have。

 I'm convincing you I should go back to school。 I haven't taken one for that。 Well yeah， but you do。

 It's a fun class。 Great。 Awesome。 Well， any other last comments you think or thoughts about what's going on in security。

 and computer systems or we could be talking about this for hours？ Of course it's a fun thing。 Yeah。

 I don't know。 Do you want to have a how long do you want to make this？ Well。

 why don't I want to be nice to these students and they can in fact find out in， Sounds good。

 It sounds good。 5 or 2。25。 So thanks a lot Dan。