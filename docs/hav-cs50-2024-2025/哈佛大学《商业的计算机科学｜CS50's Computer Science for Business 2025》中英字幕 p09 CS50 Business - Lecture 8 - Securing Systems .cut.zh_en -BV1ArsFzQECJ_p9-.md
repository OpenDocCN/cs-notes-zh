# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p09 CS50 Business - Lecture 8 - Securing Systems .cut.zh_en -BV1ArsFzQECJ_p9-

2。Hello world， this？Okay， hello world， there we go。Hello world。

 my name is David Main and today is all about securing systems Now what do we mean by security or cyber securitycur in particular Well generally it refers to keeping our system safe from harm from theft。

 from intrusion but I dare say it's helpful perhaps to think about a couple of primitives via which we can begin to secure our systems the first of which we might call authentication the process of proving who you are as by logging in with a username and password。

 but authentication alone is not necessarily sufficient for keeping a system secure because just because you can demonstrate who you are and have an account on a system doesn't mean you should be able to do anything in everything on that system。

 for instance， deleting files or accessing data that maybe you're not authorized to access。

 In fact another primitive to consider is just that authorization。

 some form of access control that specifies once you have authenticated and prove who you are what resources should you and should you not actually have access to now。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_1.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_2.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_3.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_4.png)

Of course in the real world， it's very much the case that you and I are authenticating all of the time。

 And how are we doing this。 Well， generally by way of using passwords。 And in fact， odds are。

 you have tens of hundreds of passwords nowadays not to mention usernames。

 but it turns out we humans are not very good at even choosing good passwords， in fact。

 it's commonly the case that passwords are discovered as by hackers getting into databases or somehow finding access to username and passwords and those passwords then leak out onto the public internet and people can download use them and abuse them。

 of course。 Well， fortunately， there's at least some security researchers out there。

 the good guys so to speak， they can also mind that data for lessons learned。

 And among the lessons we can learn is just how common certain passwords actually are。 and in fact。

 we can come up with the effective effectively a top 10 list of passwords we shouldn't use as a result。

 In fact， over recent years， such passwords as these have been discovered by security researchers to be among them。



![](img/fb8f024423da279c5a8671bafebdcc5d_6.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_7.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_8.png)

Most common， which is not in fact， a good thing。 For instance， among those 10 are 1，2，3，4，56。

 which certainly doesn't take much effort to come up with。

 but kind of suggests what the policy is on the systems that are allowing that password namely。

 they seem to require passwords of length at least6 Also common，1，2，3，4，56789。

 which is marginally more secure inof far as it suggests that those systems on which that password was found。

 at least has a larger length requirement for passwords， for instance，9。

 but also on the list or passwords like password literally which is taking nails a little too much on the head there。

 but password of course is just an English word， So probably not all that hard for someone to guess password1 suggests a bit more complexity because we've actually thrown a number into place。

 Qty of course is yet another option but for those unfamiliar， what does that signify。

 well if you happen to have a U English keyboard in front of you and look at the top several characters。

 you'll see that the keys on the keyboard spell。In fact， query0。 So a strange looking word。

 but nonetheless a word on the keyboard。 nonetheless。 Quey 1，2，3。 Now。

 this one's a little interesting。 Inofar as it suggests that systems on which this password's been found。

 at least require some alternation between lowercase and uppercase letters and maybe the use of some numbers as well。

 So marginally better than  queryity alone。1，1，1，1，11 isn't all that compelling。

 but slightly better is 1，2，3，1，2，3， So at least there is less repetition。

 but still a pattern in that one， I love you is both adorable and insecure。

 because even though it's three words， they're very commonly put together as used in someone's password and then another one。

 which you might think is actually pretty good capital P at symbol S W0， RD， Well， unfortunately。

 if you are thinking that you're pretty clever by substituting other characters that kind of look like letters of the English alphabet。

 like the at sign for a and the 0 for0 well。

![](img/fb8f024423da279c5a8671bafebdcc5d_10.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_11.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_12.png)

So do the adversaries out there， the bad guys on the Internet。

 the hackers that try to get into your systems know that people like you and me might use those heuristics。

 And so that's gonna be among the first things they themselves try when trying to get into your or someone's account。

 Indeed， what is the lesson learned really from the top 10 list here。 Well。

 suffice it to say that you do not want to be on this list。

 because if your password is among those here， any smart adversary when trying to get into some system is probably not going try some random passwords to get in。

 they're going download like I did， the top 10 list， the top 100 list。

 the top 1000 list and start with those passwords。 If only because probabilistically those passwords are gonna get them into some system sooner than any other passwords。

 they might actually guess。 Now， while you might see that there's some password policies manifest in here。

 The reality is that there's far too much predictability in all of these， we have the numbers here。

 which is not all that hard to generate certainly on a keyboard or even with a program that hacks into some system。

 We have English。s and English words appended with some numbers that you could certainly tack on very easily and in short。

 even something like this， I love you， which is three words mashed together。

 all three of those words are in the dictionary and any smart adversary for instance。

 after trying a so-called dictionary attack， downloading a really big dictionary of lots of English words。

 trying to brute force their way through all possible passwords is certainly going to eventually exhaust those words and then maybe start concatenating together joining together to English words and trying all possibilities。

3 English words trying all possibilities not to mention the fact that this is already on this here top 10 list。

 So there's some lessons learned even in these And so if you do have already passwords that are either on this list or all too reminiscent of passwords on this list。

 it's time to change for reasons that will now soon see So what are brute force attacks as the name sort of conjures up sort of from yester year。

 the idea of using like a big battering Ram to try to brute force here。



![](img/fb8f024423da279c5a8671bafebdcc5d_14.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_15.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_16.png)

through a castle door， just trying really the password might be。

 you could certainly try all possibilities。 if the passwords at least four digits long， for instance。

 you can try all possibility of four digits and you can work your way up from there。 In fact。

 let's consider then how secure a system would be if protected by only a four digit passcode and this is common nowadays on cell phones。

 for instance， you might minimally have a passcode that is at least four digits long now that might seem like a lot and that might seem certainly better than nothing and it probably is but just how secure is it。

 can we perhaps start to slap some numbers on the question of how secure is a system or phone in this case by considering the actual constraints on those codes。

 So for instance， if you are required to have a four digit passcode and those passcodes are entirely numeric 0 through 9 Well。

 there's 10 possibilities for the first digit times 10 possibilities for the second times 10 for the third times 10 for the fourth。

 which of course gives you 10000。

![](img/fb8f024423da279c5a8671bafebdcc5d_18.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_19.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_20.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_21.png)

So here we have already a sort of measure of just how secure the system is in the sense that an adversary in order to brute force their way into a phone protected by a four digit passcode is going have to try as many as 10000 possibilities。

 Now， on average， they might have to try half as many。 So maybe 5000 possibilities。

 They could get really lucky。 And your passcode is 0，0，0，0。

 which funny enough is not uncommon as the default passcode on certain systems。 But in general。

 they might need to try as many as 10000 possibilities。 Now for a human adversary。

 that might be pretty darnededious typing in 0，0，0，0。 it didn't work0，0，0，0，1 didn't work 0，0，0。

2 didn't work all the way up to 9，9，9，9。 that could indeed take quite a while。

 But if we have software at our disposal， even like a programming language like Python。

 we've seen it's not all that hard to write a loop， like a four loop or a while loop。



![](img/fb8f024423da279c5a8671bafebdcc5d_23.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_24.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_25.png)

That just tries all possibilities。 and heck， if I could somehow connect my laptop or any device to a phone that I have stolen and maybe automatically send all possible passcodes through that wire to the phone while I can probably do things quite quickly。

 But how quickly， let's see if we can't simulate this using our old friend Vs code。 In fact。

 if I switch over here to my programming environment as always。

 let me go ahead and hide my activity bar is unneeded。

 I'll go ahead and hide the explorer is uned so we can focus entirely on my terminal and on my code tabs。

 let's go ahead and create a new file called crack dot pi where crack itself is a term of art that means to try to figure out a password often via a brute force。

 So I can write this program in any number of ways。

 but I'm going to try to keep it short and sweet and really demonstrative of how relatively easy it is to write password cracking code like this at the top of my file。

 I'm gonna to say from string import digits。 We haven't seen。



![](img/fb8f024423da279c5a8671bafebdcc5d_27.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_28.png)

Something like this before。 But this is really just giving me access to the decimal digits 0 through 9。

 I could literally type them all out on my keyboard， but this is using a library， the string library。

 which has a list inside of it for all of those 10 digits。

 And this is just a nice way of getting all of them。

 which is gonna be convenient in a moment for reasons we'll soon see。

 Then I can import some other symbol here from it tools for iteration related tools。

 I'm going to import a function called product， which is essentially gonna allow me to very easily take the cross product of those 10 digits with each other again and again。

 And then quite simply， I'm going have a loop。😊，So I'm gonna to say for each passcode in the cross product of all of those digits repeated a total of four times and why am I using this syntax。

 Well， if you read the documentation for the product function in the inner toolsol library you'll see that you can pass in a list of values to take the cross product of the 10 digits as I described earlier and how many times you want to do that。

 why I want to repeat this process four times to effectively go for0 through 9 times itself times itself times itself to get me those 10000 possibilities in a nice for loop then just for the sake of discussion。

 let's just go ahead and print out each of those passcodes。

 but in practice I would probably take the phone that I've stolen， I'd grab a USB cable or the like。

 plug it into the phone plug it into the laptop， hit enter and automate this entire process But for our purposes。

 we'll just send all of the output to the screen All I'm gonna go ahead and hit enter now after running python of cracked and I'm sure this will take a while So I'll take my time walking over to the screen。



![](img/fb8f024423da279c5a8671bafebdcc5d_30.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_31.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_32.png)

Can see just how long it takes to try 10，000。

![](img/fb8f024423da279c5a8671bafebdcc5d_34.png)

Possibilities。 Well， that was quite fast。 And in fact。

 you don't see all 10000 on the screen because they flew past。 but I'm already down at 9，9，9，9。

 And indeed， if I scroll all the way back up， I'll see that we started at 0，0，0，0。

 So that was like what a second to go through 10000 possibilities doesn't seem as though that four digit passcode is keeping your system all that secure。

 Well， what if we try to do better。 And most phones allow you to upgrade from four digit passcodes to maybe four letter passcodes。

 So you can do something alphabetical using the English alphabet or some other。

 But let's suppose for the sake of discussion， it's four letters this time。

 how many possible combinations are there of four English letters。 Well。

 I would propose that there's 52 times 52 times 52 times 52。 Why， well。

 there's 26 letters in the English alphabet a through Z。

 but if we allow ourselves uppercase and lowercase， we can double that。

 So that's gonna give me 52 to the fourth power， which is how many Well。

 it's definitely more than 10。

![](img/fb8f024423da279c5a8671bafebdcc5d_36.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_37.png)

It's going to be 7311616。 Now that's quite a bit more in order of magnitude more。😡。

Can we modify my code， though， to try hacking into a phone that's using one of these 7 million passcodes。

 Well， let's see。 Let me go back into Vs code and make the slightest of changes。

 instead of importing digits。 I'm going go ahead and import all of the so-called ASI letters。

 The A through Z that we care about。 And that's an easy change up here。 ASI letters。

 And I know this exists by having read the documentation of the string library。

 which gives me this as a list of possibilities。 And then I'm just gonna change digits here to ASI letters so that we iterate over a through Z。

 both uppercase and lowercase a total of four times。 I'm gonna go ahead into my terminal window。

 clear the screen， I'll make it even bigger so we can hopefully see more at once。

 And I'm again going run Python of cracked do pi and stroll on over to the screen here。



![](img/fb8f024423da279c5a8671bafebdcc5d_39.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_40.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_41.png)

Now， thankfully this time it's not done yet。 in fact。

 it looks like it's going to take a decent amount of time。

 but as these passcodes scroll across the screen，s still going rather quickly。

 one column more so than the next than the next， but we see we're in the lowercase F's now We're now in the lowercase Gs and so forth。

 So this will continue some time， not only through the lowercase letters。

 but also the uppercase letters， but if I had to guess， I don't know。

 we're looking at a couple minutes here， maybe， and in fact， because my VS code is in the cloud。

 it's actually a little slower because all of these characters have to be sent over the Internet to my laptop here。

 I could run this even faster， if I ran the Python program on my own Mac or PC。

 but I don't think this is going to take terribly long。

 It's not quite as dramatic as you might see in the movies where you gradually see each of the numbers being filled in。

 which isn't really a thing but this will exhaustively eventually get to Zz Z Z So it's better。

 it's more relative terms and the reality is。

![](img/fb8f024423da279c5a8671bafebdcc5d_43.png)

That a system protected by a four letter passcode， which means as many as 7 million plus possibilities。

 is arguably more secure than a system protected by a four digit passcode which had only 10000 possibilities why well the attack is fundamentally still the same you can just brute force your way in and eventually given enough time you will get in but we have indeed raised the bar to the adversary in the sense that this is now going take them minimally more time with more time might come more risk because in the movie version of this。

 they would only have so many seconds or minutes before someone comes out and discovers that you're trying to hack into the phone。

 So of course you want the code to run as quickly as possible。

 And if you've got to go through more combinations。

 it's going to take you quite longer it might also equivalently take the adversary more resources more money for instance。

 if they want to speed up that process， now they need to invest in an even faster computer。

 faster laptop than mine in order to churn through more possibilities。

 So there's a tradeoff here though because what's。

![](img/fb8f024423da279c5a8671bafebdcc5d_45.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_46.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_47.png)

side now， arguably， it might be a little easier for you to remember a four digit passcode than a four letter passcode。

 if only because the letters just allow for so many more combinations indeed， but even this。

 I dare say four letters。😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_49.png)

Is not really going to keep the adversary out because if we flip back to B S code。

 we'll see that we're approaching the Z's。 And again， if we were to run this on another system。

 it might go even faster， but there's not all that many。

 There's only those 7 million And I think if only for the sake of closure here。

 let's hang in there until we actually hit the end of this list， Z Z Z Z， and we're now there。

 So it took a couple of minutes， it would seem。 Allright， well， can we do even better than this。

 can we make that process take even longer if we really want to decrease the probability that the adversary is going to get in。

 Well， what if we use four characters passcode。 So not just letters and not even just numbers。

 but four characters more generally， We're a character might be a letter of the English alphabet in this case。

 a digit like 0 through 9 or heck even some punctuation。 Well， if we do that。

 we have as many as 94 possibilities for each of these characters because we've got what 52 letters and we've got。



![](img/fb8f024423da279c5a8671bafebdcc5d_51.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_52.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_53.png)

10 digits。 And it turns out some 32 punctuation symbols that you might typically see on an English keyboard。

 So we have 94 times 94 times 94 times 94， which is definitely bigger than our last two values。

 This time we're gonna to have 78 million74896， which is another order of magnitude bigger。

 but here's the rub。 it's not all that harder for the adversary to wage and attack on this here system。

 Indeed， if I go back to Vs code and shrink my terminal window and then clear it going back into crackedtop pi。

 It's not all that hard to add in not just ask letters and digits but some punctuation2。

 So let me import that plus digits plus punctuation。

 And then I can combine all three of these lists into one bigger one。

 So as to try 94 possibilities four times。 Of course， I could go even bigger than that。

 Maybe we should graduate from four characters to8 character passcodes。

 This is going be similar math。 but this time it's 94 to the eighth power。



![](img/fb8f024423da279c5a8671bafebdcc5d_55.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_56.png)

Effectively。This is getting pretty darn big。 This now is going to be what we're in the millions。

 billion， trillions， quadrillions，6 quadrillion possibilities， which is a pretty darn big number。

 and we don't have enough time during the day to actually run this code Y， well。

 it's actually going to take quite a bit of time to wage this attack。 For instance。

 if we consider just for the sake of discussion。

![](img/fb8f024423da279c5a8671bafebdcc5d_58.png)

That maybe each of these operations takes one second。 So checking one passcode takes one second。

 Well， we can do a bit of math。 And if you' got to work your way through 6 quadrillion possibilities。

 I dare say at one passcode per second， you will spend 193 million years。

 brute forcing your way into this system。 So based on that back of the envelope calculation alone。

 it would seem that8 character passwords are already pretty darn good security， of course。

 unless your passcode is 0，0，0，0，00，0，0 or something else。

 similarly guessable or something else that's on one of those top 10 list or something else that's not in a dictionary that can be easily checked。

 but that's quite a bit more possibilities and probably makes your system more secure。

 So why is it that so many websites and applications are somewhat annoyingly making you and me come up with not only long。

 but seemingly random。Because you kind of want to be there in this sweet spot of those quadrillions of possibilities so that the odds are of the adversary reaching you are themselves quite small。

😡，Well， how can we defend against this attack nonetheless， because the tradeoff here， of course。

 when you have longer， more complicated passwords is that it's going to get harder for you and me to remember these things。

 and then you and I are going to resort to reusing the same password or using the same password but changing it ever so slightly for different systems。

 anytime you and I resort to a behavior like that a heuristic like that。

 we're making ourselves more vulnerable。 if only because think about it by transitivity。

 if you've got a password that looks like this on one system and the same password elsewhere。

 as soon as one system gets attacked， a smart adversary is going to try stuffing that same password into the other system to see if you are using the same there or maybe modifying it ever so slightly。

 So if the attack is so simple， it's like four lines of python code。

 how can we defend against this kind of attack。 Well we can indeed make our passcode requirements longer and longer and more complicated。

 but that just has a tradeoff with usability， just shifts the onus onto you and me to now remember these d things。

 So what if we at least。

![](img/fb8f024423da279c5a8671bafebdcc5d_60.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_61.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_62.png)

Some other defenses in place like this of rate limiting。 For instance。

 what if we indeed only let the adversary use one password per second。 Well。

 that's going take them quite a few million years to get through the list。

 odds are you and I will be dead before it's actually a problem。 So that's one way to view it。 Ally。

 it's probably unreasonable to think that if someone is trying a million plus passwords。

 odds are they are not you， this is， in fact， an adversary trying to get into your phone or device。

 After all， even if you've forgotten your password or if you're misremembering it。

 you're not going sit there trying something millions of times， probably not thousands。

 probably not even hundreds of times， maybe 10 times maybe 12 times。

 And at that point beyond it's probably less and less likely that you are you。

 and more and more likely that it's an adversary trying to get in by trying to batter the door down。

 So with rate limiting what you can do on an iPhone， an Android phone or the like。



![](img/fb8f024423da279c5a8671bafebdcc5d_64.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_65.png)

AsPerhaps you could have a built in defense such that if the user fails to input the correct passcode after 10 attempts。

 Well， you know what， let's pump the brakes。 Now let's lock the phone。

 give the user an explanatory message that says something like please try again later come back in one minute。

 Allright， maybe a minute later you or in this story。

 the adversary tries again another 10 times still doesn't get it。 Well。

 maybe this time we pump the brakes more and say， you know what， come back in five minutes。

 come back in 10 minutes。 come back in an hour among the funnier posts I've seen online actually when it comes to rate limiting is someone supposedly got a message on their phone that said。

 please try again in 16 years。 which is a little ridiculous。

 But that seems to be the case of maybe theyre not being in upper bound on just how many times the user is told to try again and how much delay is added each time。

 So with weight rate limiting。 We don't fundamentally change the threat or how the adversary can wage this attack。

 But we do effectively raise the bar so much higher that the a。



![](img/fb8f024423da279c5a8671bafebdcc5d_67.png)

just not going to stick around to continue waging that same attack if they can only do 10 passcodes at a time in between which they need to wait minutes or hours or heck years。

 Well， they're just going to lose interest in you probably as a target and move on to someone else。

 In fact， in the real world， it's often said that by locksmiths that you don't need to be the most secure house on the block。

 you just need to be more secure than your neighbor。 You don't need to have 100% security。

 having all of your doors locked with the best of dead bolts and the like。 rather。

 you just need to have better locks than your neighbor so that the adversary turns their attention to a lower barrier to entry。

 And so if we're raising the barrier to entry to the adversary。

 not only by choosing more complicated longer passcodes。

 but also significantly increasing the cost to them in time in resources in risk。

 odds are that might very well be sufficient， probabilistically to keeping the adversary out。

But if nonetheless， we're left with all of these passwords， a varying complexity。

 how do you possibly keep track of them if like I've claimed you shouldn't be reusing them。

 you shouldn't be using similar ones in an ideal world you would have a very long， unique password。

 seemingly random for every application and website you use。😡。

That's a lot to manage and of course behaviorally you and I might resort to fairly rational but unwise behaviors like。

 well， I'm gonna just write it on a postit note on my monitor， which is all too common。

 say in the workplace or home or maybe you have a little print out in your drawer of all of your passwords or something equivalent Well that's all fine and good and it might help you and decrease the barrier to entry to you but it really decreases the barrier entry to an adversary who might walk past that monitor and see the postit note or who might pull out the drawer and see all of the passwords there So better nowadays is to use what are called password managers software that you can download sometimes buy and install Also software that increasingly comes with today's operating systems and devices to do a lot of the management of your passwords for you and typically what a password manager is is a piece of software that someone's written that allows you to generate good passwords longong seemingly random more than that save those passwords in its memory ideally in a secure form so that no。



![](img/fb8f024423da279c5a8671bafebdcc5d_69.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_70.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_71.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_72.png)

You can just poke around your computer and find all of your passwords。

 and indeed these password managers themselves are typically protected by one main account password。

 a primary password that ideally is indeed long， complicated。

 seemingly random but that you have committed to memorizing In fact。

 the proposition by a password manager is stop memorizing and remembering all of these other account just remember this one account password for your password manager。

 And when you use it to log into the password manager。

 then you have access to all of your other usernames and passwords alike。 So on the one hand。

 there is a heightened risk here。 you're putting all of your eggs proverbally in the same basket such that if your。



![](img/fb8f024423da279c5a8671bafebdcc5d_74.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_75.png)

Password managers， password is compromised now all of your accounts are compromised。

 but the reality is if in practice you and I are using postit noteses or cheat sheets or reusing the same passwords or using bad passwords anyway odds are even though there's this new risk involved odds are it still a net positive because your overall practice would be more secure and again there's the relativity than your prior practices when it comes to your own systems and devices security so password managers on the whole are a very good thing to use if at least it's better than your current practices。

😡，Well， what else is a good practice Well， increasingly you're being required to do this by companies by websites and the like。

 something known as twofactor authentication， which requires that in order to authenticate to a system。

 you don't have bunch one but indeed two factors to prove who you are Now these factors are fundamentally different it would not suffice just to have two passwords instead of one but rather two fundamentally different types of factors。

 for instance， one of the factors is something you typically know So a password that you've long used but the other factor is something typically that you have for instance a phone in your pocket。

 a little key foob on your keycha or the like to which you receive a unique code usually a six or so digit code that you also have to type in in order to access that website or application。

 the code is constantly changing every minute or so but somehow stays in sync with the server that expects the code The implication of this is that yeah you still need your password and that could be compromised if somehow someone figures it out。



![](img/fb8f024423da279c5a8671bafebdcc5d_77.png)

Daase is hacked into that might leak out there， but now in order to get into your account。

 the adversary needs that second factor， not just knowing your password。

 but having something that's physically typically on you which narrows the threat from like literally anyone on the Internet in the world to just the people in the same room or building with you the same people in the Starbucks or airport wherever you might be which might still be a genuine threat but a far lesser threat because there's just so many fewer people surrounding you as potential adversaries Now here too there's some added frictions and as always this tradeoff this sounds like a really good thing when it comes to your security but what's the downside Well one it's like literally a second step in the process now you got to take out your phone find the key foob type it in what if you don't have signal what if your battery has died what if the phone is in the other room it does add genuinely some friction that might discourage you from using it and so here too is this constant struggle between like itT administrators and actually。



![](img/fb8f024423da279c5a8671bafebdcc5d_79.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_80.png)

Users between what makes good sense theoretically， but what makes good sense practically and striking that balance is all a matter of finding good corporate IT policy。

😡，Well， what else might we do， Well， these one time。What are？



![](img/fb8f024423da279c5a8671bafebdcc5d_82.png)

Now these codes that we're reading off of these devices and typing into our screens。

 well they're generally known as one-time passwords and one-time passwords are compelling。

 insofar as they're meant to be used once and only once。

 and then they change the upside of which is that even if someone's kind of looking over your shoulder when you read out and then type in that one-time passcode from your phone or other device。

 so long as you type it first， they can't use it subsequently because the server or device will effectively expire that passcode so that it can indeed be used once and only once。

😡，But what about some other threats now that arise from using all， I forgot my password Now。

 in the worst possible situation， that website or application will just email you your password to whatever email address they have on file for you。

 Now I say that's the worst possible scenario why because if they can just email your password that means they know what your password is because it came from their database。

 Now maybe that's not a big deal and they should know your password because you chose that password for that system。

 But again， you and I， as humans are not very good at picking these things in the first place and odds are that password statistically is the same password you use elsewhere or similar to a password you use elsewhere。

 or maybe even has some kind of personally identifying information that's useful to you but not really something you want that application or website to know And so no good comes from the website storing your password in a way that they can see it to and therefore send it to you So if you ever do receive a password reset email that contains your。



![](img/fb8f024423da279c5a8671bafebdcc5d_84.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_85.png)

password that you just happen to forget。 That is a bad sign。

 and you should probably steer clear of that particular service because it suggests that they are not adhering to best practices。

 So what are the best practices when it comes to storing these passwords server side， for instance。

 in the database that's maintaining the account for which you registered。 Well。

 we revisit the notion of hashing。 and remember that hashing was an operation that we explored in the context of hash tables and the implementation of things like dictionaries in the context of data structures more broadly。

 when we hashed value， we， for instance， looked at it， maybe a string。

 looked at the first letter of it。 and if it started with a。

 maybe we went to the first location in an array or our hash table。 if it started with Z。

 maybe we went to the last。 Well， you can come up with any number of hash functions。

 but the key design is that you take this seemingly infinite domain of inputs， strings。

 typically and then mapped them to a finite range of numeric values。

 indicating exactly where you should put them or string values。



![](img/fb8f024423da279c5a8671bafebdcc5d_87.png)

themselves are somehow unique。 and indeed， this is the context in which we'll see hashing when it comes to storing passwords for many years from the early days of computing。

 it was very common that somewhere on a server， there was just a simple text file that contained a whole bunch of username and password now ideally those passwords were not in the clear clear text so to speak ideally they would be hashed so that what you see in the file is not that Alice's password is Apple and Bob's password as banana you instead and see something seemingly nonsensical that doesn't quite read as the password itself。

 So in general， this is the process of hashing a password you've got the password itself。

 which might very well be Apple or banana you want to get out a hash value which in this case is not going to be as simplistic as a number from like 0 to 25 or1 to 26。

 it's going to be a string of text instead according to some algorithm and the hash function is the algorithm inside this proverbial black box that's going to turn this input into。

This output。 So， for instance， you might type in Apple in the case of our discussion of hash tables。

 and you might get back one。 You might put but。

![](img/fb8f024423da279c5a8671bafebdcc5d_89.png)

And you might get back one。 But in the case of passwords。

 you don't want these things mapping to just。Might get back one， but in the case of passwords。

 you don't want to just spit out a very easy to guess number， we want to indeed to be a string value。

 So Apple might instead hash to something that looks completely nonsensical like this。

 but that is the result of applying a welldefined hash function。

 a bit of code that converts this input into this output mean。

 in the past when we've hash on banana looking only at the second letter if we use a more sophisticated hash function now designed for passwords banana might look a little something like this completely different from the has value of Apple but seemingly nonsensical too。

 it's hard to imagine seeing that if you're an adversary who's hacked into some system and found this text file and imagining that it maps back to banana and indeed that's one of the goals of hashing in the world of passwords is that the hash functions should be one way so to speak。

 that is to say you could run the same input through the hash function again and again and it's always going to give you the same output deterministically。

 but it should be a one-way process such that if the address。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_91.png)

Or anyone has access to a hash value。 they should not be able to send it back into that algorithm and spit out the original password。

 The mathematics involved should ensure that that just isn't possible。😡，So with that said。

What problems might arise。 Well， here now is the bad version of this text file where we're actually storing the passwords。

 The better version would look quite like this。 But what if there are more users than just Alice and Bob。

 maybe there。Sorry。Reverse the process like the shoot。B it back in banana。Now in practice。

 as cryptic as those hash values are， they're even much shorter than you would see on an actual system nowadays。

 so you certainly wouldn't see that Alice's password is Apple and that Bob's password is banana instead you might indeed see some hash values like this。

 but this is really from yesteryear nowadays we might use even longer hash values that are statistically even harder to extract any information from or reverse engineer。

 So in practice， Alice and Bob might actually have a hash value that look something quite more like this and I challenge you to figure out that one came from Apple and the other banana given the a complexity alone of these hash values here。

 Now unfortunately， hash functions alone and storing password hashes in systems isn't necessarily a solution to all of our problems even if the hash functions are one way and there's no way to go from the hash value back to Apple or back to banana Well you could certainly in it。



![](img/fb8f024423da279c5a8671bafebdcc5d_93.png)

Avance。Calculate the hash values of like all English words， for instance。

 go work your way through a dictionary using a for loop and Python and figure out in advance the hash value for Apple for banana for cherry for any number of other words in that dictionary and then just keep them around。

 Store them in a spreadsheet， store them in a database such that you've precomputed all of those hash values thereafter。

 when you， the hacker encounter some system on which you've accessed the password file that contains not the actual passwords。

 but the hash values well， you could use what you've created otherwise known as a rainbow table。

 whereby you can look up the hash value you're seeing on the system。

 see if you've ever computed it before because if you have you just look in your little cheat sheetet there and figure out well what password or what word from the dictionary。

 did I hash to get that value and you can reverse the process sort of out of band。 In other words。

 given the hash value alone， you just cannot reverse the process but if you take the other approach。

 hash all possible dictionary。

![](img/fb8f024423da279c5a8671bafebdcc5d_95.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_96.png)

Wds and maybe combinations thereof。 you can come up with a cheat sheet， maybe a long cheat sheet。

 but if you've got enough memory in your system or database， that's okay。

 You can maintain that so-called rainbow table and use that to wage an indirect attack， if you will。

 on these hash values。 So that alone might not be sufficient defense unless the hash values you're creating are so long。

 and the passwords your users are using are so complicated that it's just not going to be worth the adversaryaries's time or expense or memory to precompute a massive number of millions。

 billions， even quadrillion possible passwords。 There's just not enough time in the day to do that or enough space in their own system。



![](img/fb8f024423da279c5a8671bafebdcc5d_98.png)

So that rainbow table quite simply akin to a spreadsheet。

 might just have the original password or word or words that they used as input and all of the corresponding hash values thereof。

 it's that relatively simple of an attack， so the only thing really protecting us at the end of the day is the size of these passwords and the size of the space in which these passwords live based on。

 for instance the complexity that your system requires。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_100.png)

Here though is another concern that we'll see if we have some more users in the mix So Alice's password is still Apple。

 Bob's password is still banana。 Carol's password， I claim is cherrry。

 but so is Charlie's password as well Now it's not going to be obvious from looking at the file assuming it's the hash values therein and for the sake of clarity will use the smaller hashs for now but you can imagine these being much longer。

 but the key detail here is that well Alice's hash values seemingly nonsensical Bob's is as well Carol's too at first glance is but wait a minute when you look through the list。

 you can infer that well I don't know what Carol and Charlie's password is。

 but their hash values are identical and this might leak information to me the adversary In other words。

 if maybe Carol and Charlie have something in common。

 maybe their brother and sister and had a childhood pet。

 maybe they both use the same word that they have in common as their password so I'm going to focus my attack there。

Or some other relationship that might exist between these two users。

 you're leaking information seemingly unnecessarily because you're telling the adversary you might as well start with some heuristics as opposed to resorting from the get go to just brute force。

 which might we take as we've seen quite a bit of time So how can we mitigate this concern whereby the same password will naturally yield the same hash value but that in and of itself would seem to leak information moreover。

 by transitivity， if somehow or other car's password is discovered while any smart adversary is going realize。

 well now I know what Charlie's password is as well with no additional effort other than comparing these hash values originally So here's how we might address this concern in part。

 if the password and question is cherrry and we're using that is input in the hash value by default is this hash value here。

 what if we instead sprinkle a little bit of salt in there so to speak。

 perturb the algorithm so to speak in a way that we're adding a little bit。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_102.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_103.png)

Of noise to it。 In other words， instead of passing as an input， both the password alone cherry。

 we would also pass in some other value， usually a couple of additional characters that might be as simple as Aa or A B or A or Zz or even a longer salt instead。

 but we choose that in advance， sort of sprinkle it into the algorithm so that the hash value in the end is perturbed such that if we pass in cherry as input and say a salt value of 50 arbitrarily。

 well， maybe the hash value ends up being this instead。 Now notice。

 and this is not leaking information per se。50 is the salt。

 and that's deliberately captured in the hash value because that's going to be useful when it comes time to check the user's password。

 And we'll see in a moment what that means。 But if instead for not just Carol but Charlie。

 we use the a different salt value， for instance， passing in not 50 but 49， notice that。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_105.png)

The resulting hash value will be completely different， not just the 50 changing to 49。

 but the rest of the hash value just changed as well。

 So so long as we have sufficiently many salts available to us enough range of values we can now allow users to have the same password even unbeknownst to us and so long as we use different salts for each user。

 the resulting hash value should look entirely different but what's the implication now for checking passwords and indeed how do we come full circle to now when I was trying to log into the first place at which point I forgot my password well typically in a welldesigned system。

 the way you are logged in is as follows if you type in your username and your password。

 those values are indeed sent from your computer or device to the server on their backend they've got some code there that receive that username and password and they don't just look up in their database or in their text file。

 that username and password， they first run your password。

As you typed it into the website through their well-defined hash function。

 and then they compare your username and that hash value to what they have in their database or in that text file。

 and if both match， they allow you to proceed。😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_107.png)

If though they see that if they are using salt values in this way。

 what they can do when checking passwords is try to add those salt values to your passcode。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_109.png)

Run it through the hash function and then compare those resulting hash values。

 including the outputted salt against the list of hash values in their database or text file。

 In other words， you use and reuse these salt values again and again to make sure that the text you're comparing will indeed output to be the same。

 It's not the raw passwords or clear passwords that are compared。

 It's ultimately these hash values themselves。 unless you discover one of these websites or applications that is in fact able to email you your password in which case they're not doing any of this most likely no hashing at all。

 they're probably justoring in the clear your password in the system。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_111.png)

Other defenses now that lend themselves to better security of our systems， while hashing。

Let me start actually let me take a minute break。Now whereas these hash functions are one way by design related in spirit but even more powerful is the art and science of cryptography which allows you to scramble information in such a way that you can also reverse that process you can not only encryptpt information from clear text into what well call cipher textex you can also decrypt that information from ciphertex back into plain text and this is useful for secure communications between two parties so what do I mean by this well suppose that you want to send a message to someone else but you want to be able to use an insecure medium you want to send this out over the postal service is a paperbased mail you want to send this out over the internet and someone might be eavesdropping wirelessly or on wires how nonetheless can you ensure that the recipient can receive the message and read it but no one else in between well what you can do is this you can take your original message aka plain text and you can choose in advance a secret key so to speak which is typically a number of some size。



![](img/fb8f024423da279c5a8671bafebdcc5d_113.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_114.png)

You can then pass that into a function known as a cipher， this here then is our algorithm。

 the output of which is going to be socalled cipher textex， which is text that is seemingly random。

 but with that same secret key can be reversed back into the plain text Indeed to decrypt that process of encryption you would pass in the cipher text that same key into the cipher and get back out the plain text so the first process is what you would do to send the message。

 the second process is what the recipient would do upon receiving the message that is to say decrypted This is generally known as secret key cryptography whereby the intent is to maintain a secret between two parties and keep that thing secret so that you can have communication back and forth by encrypting and decrypting your messages this is otherwise known as symmetric cryptography as well insofar as you're using really the same key in both directions to do that same process So for instance。

 how might this look。

![](img/fb8f024423da279c5a8671bafebdcc5d_116.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_117.png)

Well， if we're doing something quite simple， like we want to send someone the letter A securely and we choose a key of say one for the sake of discussion。

 well one in this case might be used by the cipher in the middle to just rotate the letter that was inputted by one place to give you the output so according to this algorithm A might become B。

 B might become C， D might become E and so forth and it might wrap around such that Z might become a。

😡，Oh sorry I should fix that。Otherwise， known as。Ssymmetric cryptography because the keys are the same。

 So for example， if you were to try to encrypt the message A that you want to send someone securely and you choose a key in advance。

 a secret key that is the number one you could pass them both into your cipher。

 which would output thereafter a value that's the result of somehow using both。 So for instance。

 if the key is one， a cipher might be simply to rotate the letters of the alpha by that many places。

 So if you input a and one， the output will be B。 if you input B and one， the output will be C。

 if you input C and one， the output will be D and dot dot dot。

 if you input z and one will wrap back around to a。 So this is a rotational cipher。

 otherwise known as a Casar cipher， and it's relatively simplistic。

 especially if we're using such small numbers， but you could imagine using perhaps fancier mathematics and not just rotating the letters but changing them somehow maybe leveraging their bitwise representation those zeros and ones in order to get back。

A result， aKA cipher text that you could eventually pass back through this same algorithm with the same key or effectively negative one and get back the original text as well。

😡，So the upside of this is the relative simplicity。

 So long as you and the receiver both know and have that secret key。

 you can do this all day long back and forth。 and only if someone in the middle intercepts this message and knows your secret key or figures out somehow what it is。

 can they too see your messages。 Now， of course in this scheme you probably don't want to use a key as simple as one。

 and heck maybe not even two or three or 13 or something else。

 you probably want to use a fancier cipher altogether。

 but the idea is going to be the same with symmetric key cryptography。

 you're still using an input and a key and the recipient is using in some form that same key。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_119.png)

All right， but what's the problem with that system because it sounds kind of straightforward and great。

 Well， how does the recipient know what key to use？ Well。

 you and they just have to agree in advance what the key is。 Well， wait a minute。

 how are you going to agree in advance what the key is if you need to discuss that securely and maybe the other party is halfway across the country。

 And so you can't really call them about it， you can't send them an email or text message why。

 well if those aren't going to be encrypted， you're just telling the whole world what that key is。

 But if you are proximal to them in person， you can just tell them the secret key。

 just tell them the whole message at that point， you don't need to establish this secure channel if they're right there。

 So there's sort of this chicken in the egg problem whereby to use symmetric cryptography。

 you need to establish a key in advance， but securely but you can only do so。

 if you already have a secure channel。 for instance， one on one in person， which is not realistic。

 for instance， in the real world， if I want to buy something from like Amazon com。

 I don't necessarily know。

![](img/fb8f024423da279c5a8671bafebdcc5d_121.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_122.png)

One personally at Amazon co so I certainly can't come up with in advance a secret key that we can use to keep my credit card information and my password secure。

 So how do I buy something from Amazon co Well， it seems that symmetric cryptography is not going to be the solution for us。

 but asymmetric cryptography does offer a solution and as the name implies the process of encrypting and decrypting in this world is going to be a little bit different and the world of asymmetric cryptography。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_124.png)

🤧。Sorry， this was not supposed to be there。In the world of asymmetric cryptography， other。

 wrong slide。😡，do you mind it was probably just a package to someone mind just running out there to check？

I heard someone call Yeah， let's take a moment。3，2。Now， asymmetric cryptography。

 otherwise known as public key cryptography， looks a little bit the same， but uses different keys。

 In fact， if you want to encrypt a message using public key cryptography。

 particularly to exchange a message with someone like Amazon do co with whom you have not established in advance a prior secret with which you could use symmetric key cryptography。

 what you can do is this you can generate in advance using a well documentcumented mathematical algorithm。

 a so-called public key and private key， a pair of two values。

 essentially really big numbers that have an inherent mathematical relationship with each other based on the algorithm you're using。

 For instance， one such algorithm is famously known as RSA and using your public key and private key。

 and in turn， the recipients public key and private key。

 can you both begin to communicate securely in particular。

 if you want to send a message to someone else。 for instance， Amazon do com。

 you can download their public key， which by definition。



![](img/fb8f024423da279c5a8671bafebdcc5d_126.png)

Is public。 It can be posted on their website。 It can be posted in the footer of every employee's emails。

 The public key indicates that indeed this is meant to be used by anyone out there。

 and you can use that public key passing in also your plain text to whatever algorithm you're using。

 RSA， for instance， an output a ciphertex。 But the interesting thing about public key cryryptography here is that now the recipient of that message。

 Amazon do com in this story。 theoretically should be the only one in the world who can decrypt that message。

 why， because Amazon hopefully is the only one in the world that has the corresponding private key。

 The other number that has some inherent mathematical relationship with the public key such that one encryptrypts and the other decrypts one reverses the effects of the other。

 So if you then as Amazon were to pass in your private key and that cipher textex you received you should be able to get back the plain text message from the original sender。



![](img/fb8f024423da279c5a8671bafebdcc5d_128.png)

And the same process can work in the other direction if Amazon then presumes to download your public key。

 they too can send a message in this way。 but in practice the way this typically works。

 at least in the context of browsers and something like Https nowadays where the SM and secure is that your browser will indeed establish a secure connection somehow with a website like Amazon co using public key cryptography but they'll use this public key cryptography which in practice it turns out tends to be a bit slower mathematically and therefore more timecon and more costly they'll use this to send not the actual message you care about like your credit card information or your password。

 but to exchange and somehow come up with an actual shared secret。

 some other third big seemingly random number that they can subsequently use using symmetric cryptography which is much more efficient and therefore less costly computationally in practice so you can use these both together but it's the public key cryptography。



![](img/fb8f024423da279c5a8671bafebdcc5d_130.png)

That helps address that chicken and the egg problem， and indeed this is the S in HTTPS。

 It's the combination of algorithms like these that actually enable those secure communications。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_132.png)

Now related to public key cryptography is in fact an alternative of all things to passwords increasingly you might be finding when you visit websites or other applications that you're not necessarily being prompted to create a password but rather to go password lists or to create as they typically called pass keys essentially pass keys or an application of public key cryptography to the process of authentication because it's clearly been a burden for us humans to come up with all of these usernames and passwords and to manage them and to make sure that we're adhering to best practices so you know what。

 why don't we write software that enables the computers to take care of a lot of that for us in particular in the world of pass keys。

 your computer your browser generates its own public key and private key and when you try to log into a server for the very first time that server instead of making you sign up for a password might instead send some kind of challenge to you like a numeric code。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_134.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_135.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_136.png)

The like from the server to browser， the browser or device more generally can take that challenge。

 use the device's own private key to essentially digitally sign that value then that value aka signature can be sent to and stored on the server。

 but notice that it's indeed a private key that's being used here to digitally sign the challenge not to encrypt it per se。

 The server then will keep around that signature and presumably associate it with your username instead of keeping around a password that both of you then have to remember but what your device does thereafter if it indeed supports these past keys is that it will subsequently use when you visit that website the next time the following operation the signature will be sent back to you saying here's the signature the user gave me prove to me that this signature is yours and the way that public keys can also be used in the world of digital。

Signatures is to verify mathematically that that in fact。

 is my signature and you can send back in effect， the original challenge。

 thereby proving mathematically to the server that I am indeed the only one in the world who could validate that signature for you because I am in fact the owner of that public key and private key and just as before your browser。

 your device keeps around privately， the private key but doesn't necessarily。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_138.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_139.png)

I think I mess this up， damn it。Sorry， let me double check this。Qu。😔。

Now related to cryptography is actually a solution to our earlier problem of passwords in the form of something that are now called pass keys。

 In other words， recall from our discussion of passwords that it's already a challenge to remember all of these things and come up with them in the first place and then to manage them thereafter will pass keys offer a solution whereby we can use more sophisticated the human largely out of the loop and get out of the business of generating and remembering an authenticating with passwords pass keys by contrast。

 rely on some form of public key cryptography whereby the first time you go to a website or application that supports pass keys。

 your device or your browser will generate its own public private key pair as before in the case of public key cryptography itself you'll send that public key to the service into which you're trying to log in and that service will send you a challenge like a big random number or string value that you then need to run through a piece of software on your device and it's all happens automatically。

😡，Softtware will take as input， that challenge from the server as well as your private key which you generated earlier that will output a so-called digital signature for you。

 which your device will then send to the server the server will then use your public key to validate that y that in fact is your signature why because there is an inherent mathematical relationship between your public key and private key which was created when you generated those both it stands to reason that only your private key can indeed sign with your particular signature and only your public key can validate that signature accordingly in other words thereafter when you try to log into that same server again you're not prompted for a password anymore rather your device is just sent another challenge and that challenge can then be fed in。



![](img/fb8f024423da279c5a8671bafebdcc5d_141.png)

A damn it， so close， let's start this over。Okay。Okay。老三。Have to go whenever hour。

Now we can actually use public key cryptography to address an earlier problem involving passwords with passwords of course we had this burden of generating them。

 managing them and then using them just to log in but we have now an alternative in the form of what are increasingly called pass keys which some website some services now support in the world of pass keys。

 you the human don't have to bother generating a password and then store it on the server and then use it thereafter which again is really putting the burden on you and me for our form of authentication with pass keys we essentially let software and our own devices do it as follows when you seek to register for a website or service for the very first time your device or your browser will generate a public and private key pair that as before have a mathematical relationship between each other such that one effectively reverses the process of the other。

 but we're going to use this public and private key pair in a different way we're going to send the public key to that server for which we want to sign up for an account and it's going to keep that around form。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_143.png)

It's then going to send me some kind of challenge， like a big random number or string value that I'm going use as input essentially to an encryption process as follows。

 I'm going to take that challenge and I'm going to take my private key and essentially encrypt the challenge with my private key technically refer to as digitally signing the challenge I'll then send the result my so-called digital signature up to the server the server upon receipt of my signature can use my public key apply it to the signature。

 essentially use it to decrypt that signature which should spit out ideally the original challenge and again。

 thanks to the mathematics underlying public key cryptography in this way the public key and private key have an inherent mathematical relationship that ensure probabilistically that those are the only two values that can perform these operations for me and so subsequently the next time the next time the next time that I visit that same website my device maybe with my blessing or approval can simply a way to challenge。



![](img/fb8f024423da279c5a8671bafebdcc5d_145.png)

From the server， use my private key as before digitally sign that challenge。

 send it up to the server and the server again using my same public key can confirm。

 yep mathematically this is the same user as registered for this mailin@harvard。

edduu account even though he is now passwordless using password keys instead of a traditional password and indeed if you sign up for services nowadays and see a passwordless option odds are underneath the hood。

 it's using a little bit of public key cryptography and some sophisticated mathematics to at least take you and me which have really been the source of most of our problems out of the loop and allowing the two computers to communicate。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_147.png)

On our behalf。So how else can we use encryption， this scrambling information to keep ourselves ever more secure Well。

 it's not always a feature offered， but increasingly do a lot of services offer what's called end to end encryption and the reason is this in the world of say the web using HTTPS which keeps the connection secure you might very well have a connection between you and that server by design and other users might have encrypted connections between themselves and that server。

 suppose the server is Gmail this means that I can send an email from my device to Gmail and it can be kept secure in between no one in between me and Gmail can actually see that their message and anyone who receives that message can log into Gmail have an encrypted connection there and similarly keep that message secure the catch though is that the man in the middle the machine in the middle that is Gmail and all of Google's employees theoretically could have access to that same email now。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_149.png)

Hopefully there's technological defenses and authorization flows and just corporate policies in place that largely prevent that。

 but I do not have a property called end to end encryption because that email is not secure between me and the final recipient it's sitting on a server between which you and the other person have a secure connection but that doesn't mean that the data is secure from prying eyes in that middle step indeed this is what really speaks to our privacy because you can have security but not necessarily privacy I can have a secure connection indeed to Google as can you but our emails might not necessarily stay private if that machine in the middle Gmail itself technically has access to all of our data therein so these are different properties that we might want to achieve but with end to end encryption we can guarantee this a bit better in fact various services nowadays like Whatsapp for instance and im messagesage and signal and other devices and services offer a stronger guarantee of privacy。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_151.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_152.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_153.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_154.png)

By way of end to end encryption and what this means is that even if your data is traveling through some thirdpart server like apples。

 the mathematics involved ensure that your device will encrypt the message in such a way that only the final recipient can decrypt it and even though that message in encrypted form is going through Apple servers or anyone else's the reality is that only the recipient can access it and ultimately read it now the machine in the middle might be able to see the cipher text。

 the encrypted form， but to them it might as well just be random zeros in ones because if they don't have access to the keys that you are both using as part of this end toend encryption。

 it's just going to look like random noise to them。😡。

And this notion of random noise comes into play in another scenario as well。

 Let's consider the security， not of our systems per se。 but now of our actual data on those systems。

 it's quite common， of course， to occasionally want to delete some files。

 maybe some document you wrote or some file you download sensor reason you occasionally might want to delete it。

 either because you don't want it anymore or just want to free up the space。 Unfortunately。

 historically deleting a file itself has not really been a secure operation。

 typically when a computer deletes a file， it effectively just forgets where it is。

 it loses track of what file name refers to what zeros and ones are inside of the device。

 And that's largely for historical efficiency reasons。

 It's a lot faster to just forget about the bits and then reuse them later then worry about changing them so that the actual data。

 the patterns of zeros and ones are no longer there。 For instance。

 consider this pattern of zeros and ones that might represent some large file on your system。

 Suppose that you decide to。

![](img/fb8f024423da279c5a8671bafebdcc5d_156.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_157.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_158.png)

Delete a file， for instance， these zeros in ones here。 Well。

 the computer can indeed just simply forget what those bits were previously used for a resume。

 an Excel file or anything else， and then gradually just let the computer reuse those zeros and ones and gradually overwrite them with new data so that is to say when you delete a file represented by these zeros in ones here then the computer effectively has more space like the zeros and ones don't go away like you don't delete the actual zeros in ones because then you'd constantly be losing space。

 but you can mark them for reuse by some other files。 the next file you download and in fact。

 maybe the next file you download only needs a subset of those bits。

 maybe just these here such that these zeros and ones here still in white are still remnants of your original data。

 the original file that you deleted but perhaps enough that you're gonna leak information In fact。

 if a researcher if law enforcement were to gain access to this device they could reconstruct here part of the file and maybe see some of the。

Numbers that were actually in that Excel spreadsheet of yours or something else。

 So really deleting a file doesn't mean that the data is gone forever。 It's really just forgotten。

 but often recoverable unless you really wipe or sanitize the device that storing the data and secure deletion therefore would mean actually doing a bit more work to ensure。

 at least with high probability that those zeros and ones cannot in fact be recovered in the same way。

 So if here again， as your original hard drive inside of your computer with all of its zeros and ones and you decide to delete some big file here。

 well， you should probably take an additional moment to change all of those bits to zero because now you've effectively securely deleted the file because I have no idea henceforth which of those zeros in ones were actually ones because everything now looks like a zero So secure deletion might do this or you could better yet just completely randomize it。

 So it's not all zeros。

![](img/fb8f024423da279c5a8671bafebdcc5d_160.png)

Comple random zeros in ones。 So for all intents and purposes， it is indeed now just noise。

 The funny thing， though， about this approach， which is very reasonable and which can be considered a good practice。

 depending on the hardware that you're using in the system you're using it with isn't necessarily the most efficient。

 especially with today's solid state drives and other devices which technically have a fairly finite life。

 such that the more you read from and write to them。

 the more rare and tear you're essentially putting on the electronics and eventually those zeros in ones might not be good anymore。

 And over time， the device might say you can't use those zeros and ones anymore。

 at which point some of your data might still be there。

 it just becomes inaccessible to you and you have less space to work with。

 So increasingly common is to turn on what's generally called full disk encryption。

 which is a use of encryption on your entire hard drive。

 like all of the files on your device the upside of which is。



![](img/fb8f024423da279c5a8671bafebdcc5d_162.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_163.png)

That all of the data on your computer， at least while you're logged out or the power is off is completely encrypted。

 That is scrambled with some secret key that's maybe in the form of your password or protected with your password。

 something that only you control So instead of the zeros and ones under your computer looking a little something like this。

 they will when full disk encrypted look completely random。

 And only once you log in with your appropriate password。

 does the computer decrypt those into the patterns of zeros and ones that are actually useful。

 the Excel files and other files that you might have on your hard drive。

 The upside of this is that if your device is ever stolen for instance。

 so long as it's not powered up and logged in the adversary。

 if they're trying to get at your data essentially is only going to see random zeros and ones unless they somehow gain access to or figure out your password。

 So you've effectively securely deleted all of your files， just by not telling the adversary。

 what your password actually is the flip side is if you have a password that's especially。



![](img/fb8f024423da279c5a8671bafebdcc5d_165.png)

Hard to guess， which is good， but you yourself forget it at some point and therefore can't log into your device。

 you've effectively wiped your hard drive as well， securely deleted everything because that password is the key to decrypting all of your data。

 but this is helpful in more innocuous forms when you might want to trade in or sell a device like a phone or a laptop whereby you want to be able to trust that the other user can't gain access to files that you might have once had on the hard drive。

 well， if you've been keeping it securely full disk encryptrypted this whole time。

 so as you've just so long as you just changed sorry。😡。

So long as you don't give them the password for all intent and purposes。

 you're just giving them a hard drive with random zeros and wantss。

 and you don't even necessarily have to worry about changing them all to zeros or completely random altogether and in fact。

 if you take an iPhone or an Android device and you wipe it so long as you're using a password in the first place。

 this is typically how it is wiped for trade in or for sale by just really sanitizing the secret key that was used to encrypt all of that information as opposed to all of the information itself。

 very painstakingly and often slowly changed to all zeros or randomness。

 which is ever more of a slow process on larger devices。

 laptops and desktops that have even more space on them。😡。



![](img/fb8f024423da279c5a8671bafebdcc5d_167.png)

But here too， we have yet another tradeoff whereby these same features can be used for evil as well in ransomware。

 for instance， is an application of these basic ideas for ill purposes。

 whereby if an adversary breaks into your system， they can actually use encryption to scramble all of your most important files not tell you the secret key unless you pay up some ransom and this has happened all too often in the real world where some company where some hospital where some system is infiltrated somehow。

 the systems themselves are left online， but all of the important data is indeed encrypted unless someone pays up using cash or Bitcoin or some equivalent and so these same things that keep us safe can also put us at risk and how you defend against this while not only adhering to best practices across the board as we've discussed already today。

 but also having backups of all of your most important data off site backups that aren't networked no less so that when the adversaries do encrypt things malicious。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_169.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_170.png)

![](img/fb8f024423da279c5a8671bafebdcc5d_171.png)

You don't back up the encrypted versions and then have nothing but just the encrypted form。😡。

So ultimately， as we've discussed here， there are so many ways to secure your systems。

 not absolutely but relatively， the goal ultimately is indeed to raise the bar to the adversary。

 to cost them more time， more resources， more risk so its to maintain a higher probability that your systems will indeed remain secure and your data and your activities。

😡，2。Today then was all about securing systems， but what can you yourself do actionably next。

 well one start using a password manager or pass keys。

 start using two factor authentication if you're not already。

 even if not for all of your accounts at least for the most important thereof and start seeking out and using where available and to end encryption so as to keep yourself not absolutely secure。

 which as I've claimed is just not realistic but so that you're relatively more secure than ideally most everyone out there this then was securing systems and this was computer science in business。

😡，2。Today then was all about securing systems and among the takeaways then for you professionally and personally。

 minimally are start using password managers or pass keys where available。

 Start using twofactor authentication if you're not already。 and if not for all of your accounts。

 at least the most important accounts of immediate need to you and lastly， where available。

 use and to end encryption to keep your communications is not only secure but private as well。

Ultimately， you're not going to be able to keep yourself， your systems， your data absolutely secure。

 but as we've discussed to be relatively more secure than most anyone else。

 at least positions you to be more private and more secure alike。

 This was computer science in business。😡，3，2。Today then was all about securing systems and what can you then do professionally personally。

 will at a minimum， start using。😡，Okay。Yeah， sorry， here we go。Good position。有。

Today then was all about securing systems。 So what can you do in the near term personally and professionally Well minimally one start using a password manager or pass keys where available start using two factor authentication if you're not already。

 if not for all of your accounts at least for the most important thereof and start using where available and to end encryption so as to keep your data not only secure but ideally private as well。

Ultimately none of us are going to be able to keep our systems absolutely secure。

 certainly in the face of the most resourced adversaries。

 but at least by raising that bar and making ourselves relatively more secure。

 ideally then everyone else we' want to be in a much better precision。😡，St back。Okay。

Today then was all about securing systems。 So what can we do in the near term to keep ourselves more secure well personally and or professionally minimally start using a password manager and or pass keys where're available。

 start using twofactor authentication， if not for all of your accounts。

 at least for the most important thereof and we're available to start using and seeking out endto- end encryption to keep your data not only secure but private as well at the end of the day。

 we're just not going to be able to keep our systems and data absolutely secure but we can at least aspire to keep them relatively more secure than most anyone else to include ultimately damn it。

 I'm so sorry。😡，I made the wrong transition last time。This is a bad habit。Tスタッ。

Today then was all about securing systems so what can we do personally。

 professionally in the near term we minimally start using a password manager or pass keys where were available。

 start using two factor authentication if not for all of your accounts at least for the most important thereof and seek out and use where available and to end encryption to keep your data not only secure but private as well。

 ultimately it's just not realistic for us to make our systems and our data absolutely secure。

 but we can aspire through these lessons learned in best practices to at least maintain ourselves more relatively secure than everyone else these were securing systems and this。

😡，Sorry。Last time。Okay。That's good。Okay。Today then was all about securing systems。

 What can we do then professionally and personally in the days ahead。

 Well minimally start using a password manager and our pass keys where available。

 Start using twofactor authentication， if not already， and if not on all of your accounts。

 at least on the most important thereof and seek out and use and to end encryption when you can。

 So as to keep your data not only secure but private as well。 ultimately。

 it's just not realistic to make our systems， our data absolutely secure。

 but we can at least aspire to make our systems and data relatively more secure than everyone else。

 This was securing systems。 And this was computer science in business。😡，Alright。All right。32。

Today then was all about securing systems so what can we do personally and professionally in the days ahead。

 well minimally start using a password manager and or pass keys where available。

 start using two-factor authentication， if not for all of your accounts at least for the most important thereof and seek out and use and to end encryption when you can so as to keep your data not only secure but private as wellUltimately we're not going to be able to keep our systems absolutely secure but through these lessons learned through these best practices。

 we can at least aspire to make our systems and data relatively more secure than everyone else This was computer science for business。

😡。

![](img/fb8f024423da279c5a8671bafebdcc5d_173.png)