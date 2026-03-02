# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P4：-04-CS50x 2024 - Lecture 3 - Algorithms.zh_en - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_0.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_1.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_2.png)

Alright， this is C S 50。 and this is week3。 and as promised。

 we thought wed take a bit of a break on new syntax this week and focus a lot more on algorithms and implementation thereof because over the past few weeks besides scratch we've now had C and you have a lot of like vocabulary now。

 even if it might not seem yet that you fully grasp all of the functionality of this particular language we practice it'll get easier and easier But today we'd focus instead on ideas and ultimately on this how to think algorithmically and so to take problems in the real world and try to quantize them in a way that you can map those puzzle pieces from week0 or all of this new syntax from weeks1 and2 to actually writing code to solve those problems to contextualize this though we thought we'd remind you of this here chart from week0 and recall that in week 0。

 we painted this picture where on the x axis on the horizontal was the size of the problem and the number of phone book pages increased as you went from left to right and then on the vertical axis or Y axis we had time to solve。

 So this was like how many seconds， how many page。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_4.png)

How many units of measure， whatever you're using， we might actually describe the solution there， too。

 And the first algorithm we had in week 0 for the phone book was like one page at a time。

 So we plotted it with this one to one slope， the second algorithm。

 we started doing two pages at a time， which did risk a bug I might have to double back one page。

 but it was still going for the most part， twice as fast。 So it was still a slope。

 but sort of a two to one slope instead of one to one。

 but the third and final algorithm recall was sort of fundamentally different。

 And it was this logarithmic curve。 so to speak， whereby it kept increasing increasing increasing。

 but very， very slowly。 So even if you like doubled the size of the phone book as by having Cambridge in Al here in Massachusetts merge。

 No big deal， it was just one more page turn， not another 500 or another thousand。

 So think back today on that particular idea of how we began to divide and conquer the problem。

 And that sort of gave us a fundamentally better advantage。

 So we thought we'd see if we can apply this lesson learned。As follows。

 if I were to take like attendance today， sort of here on stage， I could do with old school， like 1。

2，3，4，5，6，7，8 and so forth。 So one step at a time， I could also double the speed 2，4，6，8，1012。

1416 and so forth。 But I dare say we can learn a bit from week 0。

 And if you'll indulge me right in place， could everyone stand up and think of the number one。

 So right where you are， just stand up if you could。😊，Stand up and think of the number one。

 So at this point， hopefully everyone's literally thinking of the number one。

 And the second step of this algorithm， which I claim ultimately theoretically should be much faster than either my one person at a time or two people at a time。

 Step 2 is this。 pair off with someone standing and add their number to yours and remember the sum。

Person can be in front of behind， left or right of you。All right， most likely。

 most everyone in the room， if assuming you found someone is thinking of the number two now。

 unless you're like sort of an odd person out in the row and that's fine。 if you're still one。

 that's fine， but most of you are probably two。Next step is that one of you in those pairs should sit down。

Okay， so many of you tried to sit down as quickly as possible。 we noticed。 But so next step now。

 at this point， rather， most of you are thinking of the number two。

 a few of you were thinking of the number one。 And that's okay。 The next step。

 and notice we're about to induce a loop。 So the rest of this is on you。 If still standing。

 go back to step 2。If still standing， notice that this is a loop， so keep going， keep going。

 if still standing。U there。我发 about think。That's okay， but now keep going， keep going。

 keep paring off， so maybe you too。All right， a few more seconds。So step two still。All right。

 keep pairing if you're standing。嗯。All right。Alright， so theoretically。

 there's only one person standing left， but clearly， that's not the case。 That's fine。

 I will help with the the pairing because some of you are far away。 So let's see。

 what's your number here。Sorry。What's your number？E， okay， go ahead and sit down， how about in back。

 what's your number？😡，46， nice， okay， go ahead and sit down who else is standing over here。

 what's your number？You're 16。Okay， so go ahead and sit down and behind you。48 okay。

 go ahead and sit down， is anyone still standing yeah？32， nice， still stand over here。43， okay， nice。

 sit down， sit down and anyone else still standing here。22， go ahead and sit down。

 is anyone still standing and participating。Yeah我。Where， oh yeah。16， okay， go ahead and sit down。

 Anyone else still standing。Okay， so theoretically， everyone's paired off。

 you were the last person standing。 So when I hit enter here。

 having just greased the wheels to do all of the remaining edition myself。

 we should have the total count of people in the room and recognize that unlike my algorithm。

 which would have required pointing at each and every person or my second algorithm。

 which would mean pointing at every two people twice as fast。

 theoretically the algorithm you all just executed。

 I dare say should have been fundamentally faster why because no matter how many people in the room。

 maybe like if there are 1000 people in the room， there would then have been 500 just as there would be 500 pages in week0。

 then from 500， thered be 250125 why because on each step of the algorithm half of you。

 theoretically were sitting down sitting down sitting down dividing and conquering that problem So the total number of people in the room as of now。

 according to your count is 231 as a backup though Carter kindly did it the old fashioned way one person。

😡，And at a time and Carter， the actual number of people in the room is。Okay。

 so our first real worldl bug to be fair。 So theoretically， that should have worked。

 But clearly we lost some numbers along the way。 So a bug that we can fix today。

 But remember that really this is just similar in spirit to that algorithm we indeed did in week 0。

 it's the same as the phone book example， it went off the rails in this case。

 but it's the same idea ultimately dividing and conquering。

 and any time you have this having having having there's gonna be a logarithm involved there。

 even if you're a little rusty on your math， and that's fundamentally faster than just doing something n times or even n divided by two times where n is the number of people in the room or in week 0。

 the number of pages in the phone book。 So even when you're using your iPhone or Android device later today。

 like if you search for a contact contact using autocomplete。

 It is that socalled divide and conquer algorithm that's finding people in your address book。

 It's not starting top to bottom or bottom up， it's probably going roughly to the middle and then。😊。

The top half or the bottom half， repeating again and again。 So these ideas are everywhere。

 and hopefully you end up finding just the one person you're looking for。 or in your case。

 the one person last standing who should have theoretically had the count of everyone because if each of you started by representing one effectively handed off your number。

 handed off your number， handed off your number， it theoretically should have coalesced in that final person standing So let's consider the connection now between this idea and what we introduced last week。

 which was this idea a very simple data structures in your computer's memory like actually using this memory as though it's kind of a grid of bytes。

 each one of these squares recall represents one byte or8 Bs。

 and we can get get rid of the hardware and sort of abstracted away as just this grid of memory or this canvas and then we introduced arrays last week。

 and what was the key definition of an array。😡，How would you describe an array？What is it anyone？

What's an array， Yeah， in the middle。A collection。A collection。

 And I don't love data types only because in C， it tends to be the same type。

 So a collection of data。 I do like that。 But there's one other key characteristic。

 You want to be more precise。 It's not just a collection。Something about where it is。

Potentially strings， but strings are just an example of putting char， char， char char。

 It could certainly be integers or floating point values another characteristic。😡，It's what sorry？

It's not necessarily ordered， actually， we'll come back to that today， it could be in any order。

 and certainly a string isn't necessarily in sorted order， It's in whatever the word is。😡。

It's a list in concept， but there was something key about where we put things in memory， yeah。

Consecutive， the memory is consecutive， Aka contiguous。 An array ist important in C， because yes。

 it's a list of values。 Yes， it's a collection of values。

 but the real key distinction in an array in C is that it's contiguous。

 the bytes are back to back to back somewhere in the computers memory。

 at least for any given data type an int， afloat a bigger string。

 all of the characters are back to back to back in the computer's memory， not spread all out。

 even if you have space elsewhere。 So with that said。

 we can actually start to solve problems with that mindset。 And for instance。

 if I kind of pare this down to just an abstract array of size 12，3，4，5，6，7， for instance。

 suppose that there are these numbers inside of this array of memory。

 So here are7 integers or ins and C， I have in this case sorted them just to make the numbers pop out as obviously smallest to largest。

 But the catch with C is that if I were to ask you。

 or if you were to ask the computer through code to find you the number 50。Well， obviously。

 every human in this room just found it obviously right there because we kind of have this bird's eye view of the whole memory at once。

 but the computer ironically does not have that bird's eye view of its own memory it can only look at each location one at a time。

 So if you really were to do this like a computer， you would kind of have to like shield your eye and only look at one number at a time from left to right from right to left or in any order in order to find is the 50 actually there。

 you can't just take a step back and boom it pops out at you。

 So this is kind of analogous this array to being like a set of gym lockers or school lockers like this where the doors are actually closed by default。

 The numbers are in there。 but the doors are closed。

 which is to say the computer and we can actually look So we couldn't find yellow lockers。

 but we did find red lockers here。 And so I propose that you think of these lockers on the stage here of which there are seven as well as representing an array And just so we have some terminology Not that I've labeled these。

Bet 0， bracket 1， bracket 2，3，4，5 and 6。 and the bracket notation recalls the new syntax from last week that lets you index into go to a specific spot inside of an array and notice that even though there are seven lockers I only counted as high as 6。

 But again， that's just a side effect of our generally counting from 0。

 So 0 through 6 or 0 through n-1 because if there are n equals 7 lockers and -1 is 6。

 So that's the left bound and the right bound respectively。

 So suppose that we were to use these lockers as representing a problem like we want to find an actual number behind these doors。

 So this is actually a very common problem in the real world。

 And you and I take for granted every day that big companies like Google and Microsoft and others like do this for us constantly。

'm glad to mention AI doing something similar nowadays searching for information。

 and we'll focus on some basics first that will lead us to more sophisticated algorithms ultimately。

 But all we're gonna to talk about fundamentally。This same picture from week  zero and from week1 and from week2。

 where here is a problem to be solved。 So if for instance。

 the input to this problem is an array of numbers， an array of seven numbers。

 I can't see them all at once。 but I'm looking for something like the number 50 ultimately I want to get back out。

 I claim true or false like the number 50 is there or it is not。

 that's one way of thinking about the search problem， find me some piece of data if it's there。

 otherwise tell me that it's not true or false respectively。

 So the algorithm inside of this black box though， is where we're gonna actually have to do some thinking and actually figure out how best to find the number or the data we care about。

 and even though we'll use numbers to keep things simple today。

 you could certainly generalize this to web pages or contacts or any other type of information that are in some computer or database more generally So maybe to keep things interesting。

 could we get how about two volunteers wow， that was fast。 come on。

And how about one other volunteer I over here， okay， how about you， come on down？😡，Sure。

 round of applause for our volunteers。Okay。Welcome。Come on over。

 do you want to introduce yourself to the group？How much。Like a few seconds is Hi， I'm Sam。

 I'm not a CS concentration。So what are you。 Do you know yet， Applied math。 Okay， nice。

 nice to meet you。 We and。😊，Hi， I'm Louis， I'm from First year Matthews and I'm going to do Econ with stat youn Matthews too Okay I was in Matthews too。

 so Matthew South Oh my God， I was room 201。😊，5ifth floor one All right， So anyhow。

 So and so we have Louis and your name Sam Sam， Louis and Sam。

 So Louis and I are gonna to step off to the side for just a moment because Sam。

 we have a problem for you to solve behind you。 This feels a little bit like prices right。

 But behind you are the seven lockers。 And we'd like you to just find us the number 50。

 That's all the information you get。 But we'd like you to then explain how you go about finding it。😊。

Hers is just coming of in。Find us the number 50。And then tell us how you found it。

What was in there just so the audience knows？YeahYes， yes。It was $10， a very， very big $10 bill。

 fake money， okay。That was $100。$1。$5。 Okay， I'm not lucky。Oh。

I found it nice take it out and so people can believe， all right， it's wonderful。

 so you found the 50。And now if you could explain， I I'll take that。

 if you could explain what was your algorithm， What was the step by step approach you took。

I didn't really have one。 I thought I just started on one end。

 and I went down because it wasn't in order or anything。 So I just kept going until I found it。 Okay。

 so that's actually pretty fair。 And in fact， let's step forward here。

 Carter's going very secretly kind of shuffle the numbers in a particular new arrangement here。

 And so you really went from right to left。 And I dare say maybe going from left to right might be equivalent。

 but could could she have done better。Could she have done better because that took 1，2，3，4，5 steps。

 Could Sam have done better。Sure how？Okay， so if you got lucky。

 you could have found the number in one step， although luck isn't really an algorithm。

 It really isn't a step by step approach。 So I do another thought。Blet bills sort them and order。Oh。

 interesting。 So you could have taken out all of the dollar bills， sorted them， put them back in。

 And then you probably could have done something like the divide and conquer approach。

 No you weren't allowed to。 So that's fine。 But that would be a valid algorithm。

 Although it sounds very inefficient to do all this work。 just to find the number 50。

 because in doing that work， she would have found the 5 once。

 But that might actually be a reasonable solution。 if she plans to search again and again and again。

 not just for seven numbers， but maybe a lot of numbers。

 maybe you do want to incur some cost upfront and sort all the datas toes to find it faster。

 But let's do this a little more methodically， We'll step off to the side once more。

 And just by convention， if you want to go ahead and do we need this。Okay。Okay。

 let's go from left to right。 Yep， and go ahead and show everyone the numbers just to prove that there's no。

Funny business here，20。对。😊，Okay，500， nice。10 so it doesn't sound like it's sorted either this time。

Five nice。And。100 so close。I know now we're just messing with okay， and lastly。Very well done， Okay。

 so nicely done。Thank you。 So this is to say whether she goes from left to right or right to left。

 like this performance of that algorithm just going linearly from side to side really depends on where the number ends up being。

 And it kind of does boil down to luck。 And so that was kind of the best you could do because I dare say。

 had you gone linearly from right to left and go ahead to reset， had you gone from right to left。

 that time you would have gotten lucky。 So on average， it might just kind of work out。

 And so half the time it takes you maybe half as many steps half the number of lockers to find it on average because sometimes it's in the one end。

 sometimes it's in the other end， sometimes it's smack a in the middle。

 But we're gonna give you the option now， Louis， of knowing that it's sorted。

 So we're not gonna we're gonna take away the microphone from you。

 but stay on up here with us and you are now， given the assumption that the numbers are this time sorted from smallest to largest left to right。

 and you want to take more of a divide and conquer approach。Here， wait a minute。😀Ha。😊。

What might you do as your algorithm， Louis？Well， I think I know all the numbers， right， It's 1，5。

102050。 So Louis has some memory， as we'll say， Okay， but assuming if I didn't have memory。 Okay。

 assuming if you did't have memory， where would you start them， I would probably start in the middle。

 Okay， go ahead， go in the middle。 And what do you say。2020。 okay， what do you。

 what does that mean now for you？ So now that means， since I know there's some numbers bigger。

 I'll go to the right。 Good So you can sort of tear the problem in half so to speak O per week 0。

 skip all of the lockers on the left and now go where relative these3。 relative to the middle。 Okay。

 maybe don't know。 What's on the right hand side。 And so now it's 100。 Okay， nice。

 So50 must be between 20 and00。 So must be this one。Indeed。

 it all round of applause for Louis for getting this right this time。

We have some lovely parting gifts since we're using Monoppoly money， so it's not actual money。

 but this is the Cambridge editionition， Harvard Square in all for both of you， so welcome。

 thank you so much。Okay。So so Louis was actually getting particularly clever there when his first instinct was to just remember what were all the numbers and then sort of deduce where the 50 must obviously be。

 So that's on us。 like ideally， we would have completely change the dollar amount so that he couldn't use that information but it turns out Louis's instinct there to figure out where the number should be and jump right there indexex into that exact location iss actually a technique and it's a technique we'll talk about in future classes where you actually do take into account the information and go right where you want。

 It's an example of what we'll eventually call hashing， so to speak in a concept called hash tables。

 But for now， let's try to formalize the algorithms that both of these volunteers kind of intuitively came up with first and second and we slap some names on them。

 So the first and I've hinted at this is what we would call linear search anytime you search from left to right or from right to left It's generally called linear search why because you're kind of walking in a line no matter which direction you're going But now for today's purposes is let's see if we can。

😡，Can trulyly formalize what our volunteers' algorithms were by translating them。

 not necessarily to code yet， but pseudocode。 See if we can't map it to English like syntax that gets the ideas across。

 So I dare say the first algorithm， even though she went from right to left。

 then from left to right might look like this for each door， from left to right。😡。

She checked if 50 is behind the door as by looking at it。 If it were was behind the door。

 then she returned true。 Like， yes， this is the 50。 That didn't happen on the first iteration。

 though。 So she she moved on again and again， And now notice the indentation here is just as important as it was in week 0。

 Not that only at the very bottom of this algorithm， do I propose returning false。

 but it's not indented inside of the pseudocode Y， Well， because if I had changed it to be this。

 what would be the logical bug in this version of that algorithm， yeah。Exactly。

 if she had opened the first door， found it to be the wrong number。 if it says else。

 if it's not behind the door， then return false， that would erroneously conclude the 50s not there。

 even though it could certainly be among those other doors。

 So this first version of the code where the return false is sort of left indented。 So to speak。

 and the very last thing you do if you don't previously return true。

 that just make sure that we're handling all possible cases。

 But let's make this maybe a little more technical。

 This is how a computer scientist or a programmer would likely express this instead。

 instead of just drawing it in broad strokes， it's actually fine to kind of steal some of the syntax from languages like C and actually use some of the indices or indexes like 0。

1，2，3，4，5，6 to represent the pieces of data we care about。

 So this is a little more precise4 I like a variable I from the value 0 to n-1。

 So in the case of 7 doors， this is like saying for I starting at0 going up。😡，2，6 do the following。

 If the number 50 is behind the doors array。 So I'm using array syntax。

 even though this is technically still pseudocode。 if bracket if the I location of my door's array has the number 50 return true。

 Otherwise if you do that again and again and again in total times and you still don't find it you want to return false。

 So we introduce this is just an example of how you can start to borrow ideas from actual code to paint the picture even more precisely of what it is you want a colleague to do what it is you want your code to do ultimately by sort of borrowing these ideas from code and incorporating it into our pseudocode。

 But what about the second algorithm here。 the second algorithm whereby he took a divide and conquer approach starting in the middle and then going right and then going left。

 Well， turns out this is generally called binary search by implying to because you're either going with the left half or the right half。

And again， this is literally what we've been talking about since week  zero when I searched the phone book that too was binary search dividing dividing and dividing in half and half。

 so if we were to draw some pseudocode for this， I would propose that we could do something like this if 50 is behind the middle door。

 then we got lucky， just return true else if the 50 is less than the value at the middle door so if it's smaller than the middle door。

 I want to search to the left so I can say search left half else if 50 is greater than the middle door。

 I want to search to the right。😡，And I think that's almost everything， right。

 Is there a fourth possible case。What else could happen。Good。

 so taking into account that if there are no doors left or no doors to begin with。

 we better handle that case so that we don't induce one of those spinning beach balls so that the computer doesn't freeze or crash。

 There's really four possible scenarios in searching for information。

 it's either in the middle or to the left or to the right or it's just not there at all。

 And so I sort of slip that in at the end because technically。

 that's a question you should ask first， because if there's no doors， there's no work to be done。

 but logically， this is the juicy part。 the other three questions that you might ask yourself。

 So this then might be the pseudocode for binary search。 and we could make it more technical。

 And this is where it kind of escalates quickly syntactically。

 But I'm just using the same kind of syntax。 if doors in my pseudocode represents an array of doors。

 Well， then doors bracket middle is just a pseudocode like way of saying go to the middle door in that array。

 and then notice else if 50 is less than that middle value then search doors bracket0。

 So the leftmost one through doors， middle-1。 So you don't need to。

Time researching the middle door so I say middle-1 so that I scootch over slightly to the left so to speak else if 50 is greater than the value at the middle door。

 then you want to search one over to the right。 So middle plus1 among those doors through the last door。

 which is not in because we start counting it zero but N minus-1 and the rest of the algorithm is the same。

 This is just a little more precise。 and I dare say when writing a program in C or any language like honestly starting in pseudocode like this will generally make it much easier to write the actual code。

 So in fact， in this in future problem sets， do get into the habit。

 especially if you're struggling getting started， just write things out in English and maybe high levelvel English a little more like this。

 then as a version two， go in with your keyboard or paper pencil and make it a little more precise using some code like syntax And then I dare say in version 3。

 you can now translate this pretty much verbatim to see code the only headache is going to be。😡。

Rounding issues with integers， because if you divide an integer and you get a fraction。

 it's going to truncate So all that kind of headache。

 But you can work through that by just thinking through what's going to get truncated when you round down or up as a solution。

Any questions， though， on this pseudocode for either linear or binary search， as we've defined them。

Linear or binary search。NowAll right， well let's consider then a bit more formally a question that we'll come back to in the in future classes as well。

 what is the running time of these algorithms， What is that is to say the efficiency of these algorithms and how do we actually measure the efficiency of an algorithm is it with a stopwatch or with some other mechanism Well we propose that we think back to this picture here whereby this again was representative of both these phone book example from week0 and theoretically bug aside the attendance counting algorithm from earlier today。

 whereby this same green line theoretically represents how much time it should have taken us as a group to count ourselves why because if maybe another class comes in and doubles the size of the number of humans in this room no big deal that's just one more step or one more iteration of the loop because half of the people would anyway sit down so this green algorithm still represents the faster theoretical algorithm today and so recall that we describe these things more mathematically is N。

😡，So this was one page at a time。Or one person at a time。 This was two people or two pages at a time。

 So it's twice as fast。 So if n is the number of people or pages n divided by two is the total number of steps。

 And then this one got a little mathy， but logbased two of n and log based two of n just means what is the value when you take n。

 and divide it in two by two again and again and again and again until you're left with just one page or one person standing。

 But in the world of running times， it turns out that being this precise is not that intellectually interesting。

 And it sort of devolves into lower level math， it's just not necessary when having discussions about the efficiency of an algorithm or even code that you've written So generally a computer scientist when asked what's the running time of your algorithm or what's the efficiency of your algorithm or more generally how good or bad is your algorithm。

 they'll talk about it being on the order of some number of steps。

 This is a phrase you'll hear increasingly in computer science where you can kind wave your hand at it like the lower level details don't matter that much。

 all you care about。In broad strokes are certain numbers that will add up the most。 And in fact。

 when computer scientists talk about the efficiency of algorithms。

 they tend to throw away constant factors。 So literally numbers like two。

 that might be dividing here or a base here。 So， for instance。

 these two algorithms to a computer scientist would sort of be the same。 like yeah。

 it's technically twice as fast。 But look at the lines。 I mean， they're practically the same。

 And this one here， too， log base two sure。 but if you remember from math class。

 you can change the base of any logarithm from one number to another pretty easily。

 So let's just generalize it as log of N。 It doesn't really matter fundamentally。

 what the numbers actually are。 And honestly， if we zoom out slightly so that the y axis and X axis get even bigger。

 honestly， these first two algorithms really do start to resemble each other closer and closer。

 And I dare say in your mind's eye， imagine zooming further and further and further out like that red and the yellow line are pretty much。

Once n is large enough， going to be functionally the same like they're practically the same algorithm。

 but this one is still doing amazingly because it's a fundamentally different shape。

 So this is to say when a computer scientist talks about thinks about the efficiency of algorithms we just throw away the constant terms that when n gets really large just don't seem to matter as much they don't add up as much or fundamentally change the picture in a case like this。

 So what I'm describing here with this capital letter O has a technical term this is called big O notation and this is omnipresent and computer science and often rears it said even in programming specifically when talking about the design of some algorithm。

 and this is a little cheat sheet here on the screen now。

 very often algorithms that you write or you use will be decribable as being on the order of one of these running times So N is just representative of the number of things number of people number of pages。

 whatever it is you're actually doing in code So the mathematical form。😡，Inside of the parentheses。

 describe as a function of the size of that input， how fast or slow the algorithm is going to be。

 So this algorithm in the middle here， big O of n。 so to speak， means that it takes linear time。

 In other words。 So my first algorithm，1，2，3，4 or my first algorithm week 0，1，2，3，4。

 that was a linear search， the number of steps， it takes is on the order of n。

 because if there's n pages in the worst case like John Harvard's all the way at the end of the phone book。

 So it takes me n steps。 In this case， it's always going take me n steps to count you all because if I want to point at each and every one of you。

 that is always going to take me n steps。 So big O represents an upper bound on the number of steps that you might be counting。

 And so we often use it to consider the worst case。 in the worst case。

 John Harvard or whoever might be all the way at the end of the phone book。

 So that linear search is on the order of N。 But what about n squared。

 This means like n people doing n things。 So。Inst， and we won't do this today。

 but if we were to ask you again to stand up and shake everyone's hand in the room。

 not good for health nowadays， but it shake everyone's hand in the room。

 How many handshakes would there be。 Well， if there's n of you and you've got to shake everyone else's hand。

 that's technically n times n-1， let's throw away the -1， that's n times n or n squared handshakes。

 like that's a lot of handshakes。 And so the running time of shaking everyone's hand in the room to introduce yourself would be on the order of n squared at the other end of the spectrum。

 The faster end， big O of one doesn't mean that the algorithm takes literally one step。

 it could take two steps or three or even1000 steps。

 But what it means is it's a constant number of steps。

 So it doesn't matter how many people are in the room。

 this describes something taking just one step total or a constant number of steps total。

 So for instance earlier， when everyone stood up at the same time， that was constant time because。

We had twice as many people come into the room。 It's not going to take us twice as long to stand up if everyone stands up at the same time。

 that would be a constant time algorithm。 So this is linear， this is constant。

 if you want to get fancy， this is quadratic， this is logarithmic and this is n log N or there's other fancier terms we can give it as well。

 But for now， it's just a common list of running times that we might apply to certain algorithms。

 So linear search， I claim is in big O of N because it's going to take in the worstcase N steps。

 what about binary search。😡，How many steps does binary search take on the order of。

 according to this chart， yeah。Log n， yeah， because no matter what with binary search。

 you're dividing in half， half， half， but in the worst case， it might be in the last door you check。

 but you only took log n steps to get there， But it still might be the last one you check。

 So binary search indeed would be on the order of log N。 But sometimes you do get lucky。

 And we saw with our volunteers that sometimes you can get lucky and just find things quicker。

 So we don't always want to talk about things in terms of an upper bound。

 Like how many steps in the worst case might this algorithm take。

 Sometimes it's useful to know In the best case， how few steps might an algorithm take。 So for that。

 we have this capital Greek omega， which is another symbol in computer science And whereas big O represents upper bound。

Omega represents lower bound。 And it's the exact same idea。

 It's just a different symbol to represent a different idea， The opposite in this case。

 So here's a similar cheat sheet here。 But when you use the omega symbol。

 that just means that this algorithm might take as few as this many steps， for instance。

 in the very best case。 So by that logic， if I ask about linear search。

 our first demonstration with the lockers， Let's consider the best case。

 How many steps might it take to search in lockers using linear search in the best case。

 you get lucky。So I heard it。 Yeah， just one step。 So we could say that linear search is in omega of one。

 so to speak。 What about binary search， if you've got n lockers in the best case， though。

 how few steps might it take us again，1 because we might just get lucky in boom。

 It happens to be right there in the middle。 So you could say that both linear search and binary search are in mega of one。

 Now， by contrast， my counting my attendance algorithm， The first 1 I proposed 1，2，3，4，5，6，7。

 I claimed a moment ago that that's in big O of n because if there's N people in the room。

 I've got to point at everyone。 But equivalently， if there's n people in the room。

 and I have to point everyone， what's the fewest number of steps。

 it could take me to take attendance using this linear approach。So still N， right， unless I guess。

 which is not an algorithm。 like unless I guess I'm not gonna get the right answer。

 So I kind of have to point at everyone。 So in both the best case and the worst case。

 some algorithms still take n steps and for this， we have what we'll call theta notation。

 whereby if big O and mega happen to be the same， which is not always the case， but can be。

 then you can say that that algorithm is in theta of such and such。

 So my attendance taking algorithm。 The very first，1，2，3。

4 all the way on not to n would be in theta of n， because in both the best case and the worst case。

 It takes the same number of steps as per my big O。And omega analysis。 Now。

 there is a more formal mathematical definition for both of these。

 And if you take higher level computer science， you'll go more into the weeds of these ideas。

 But for now， big O， upper bound， Oomega， lower bound。Questions on the symbology。😡。

It'll be a tool in our toolkit。No okay， so with that said。

 let's see how we might translate this to actual code in something that makes sense now using C not so much new syntax。

 but applications of similar ideas from last time。 So for instance。

 let me actually go over to search do C and in search do C。

 I'm gonna to go ahead and implement the idea of linear search， very simply using integers initially。

 So to do this， let me go ahead and give myself the familiar Cs50 do H so that I can ask a human what number to search for。

 then let me go ahead and include standard I O do H so that I can use printf and the like。

 then I'm going to go ahead and do in main void without any command line arguments because I'm not gonna to need any for this particular demonstration。

 And someone asked about this a while back。 if I want to declare an array of values。

 but I know in advance what the values are， there is a special syntax I can use， which is this。

 if I want a whole bunch of numbers， but I want those numbers to be stored in an array。

 I can store them in using these curly braces and I'm going。

The same numbers as the monopoly denominations that we've been playing with and I'm just going to put them in sort of random order。

 but I'm going to deliberately put the 50 all the way at the end just so that I know that it's going to try all possible steps so big O of n ultimately now let's go ahead and ask the user for a value n and we'll use get int and just ask the user for a number to search for be it 50 or something else and then here's how I might implement in code now linear search translating effectively the pseudocode from last time for int I equals0 I is less than7 I plus plus and then inside of this loop I can ask a question if the I number in the numbers array so numbers bracket I equals equals the number n that I care about well this is where I could just declare return true we return false here I'm going to go ahead and just use a printf statement and I'm going to say found backslash n just a no visually that I found the number and else I might do something like this。

😡，If that's not the case， I'll go ahead and print out not found backslash n。😡，Alright。

 so let me zoom out for just a moment。 Here's all of my code。

 Any concerns with this implementation of what I claim is now linear search。

Any concerns with what I claim is linear search。 Yeah， when you the first old say not。Exactly。

 if I search the first number and it's not found， it's gonna to say not found。

 but it's gonna keep saying not found， not found， not found， which might be fine。

 but it's a little stupid。 I probably want to know if it's found or not。

 So I've made that same mistake that I called out earlier。

 like the else is not the alternative to not finding the number in that first location。

 It's the final decision to make when I have't actually found the value。

 So I think what I want to do is get rid of this else clause。 And then at the outside of this loop。

 I think I want to conclude printf not found。 But here， too， there's a new bug that's arisen。

There's a new bug， even though I fix the logical error you just described。

 what symptom are we still going to see。Yeah， now it's going to always print not found even when I have found it because even once I found it and I finish going through the array。

 it's still going to assume that I got to the bottom and therefore it's not found。

 So I need to somehow exit out of main prematurely if you will and recall that last week we also introduce the idea that main all this time does actually return a value in integer by default。

 it's secretly been0， any time a program exits it just return 0 and exit status of0。

 but we do now have control over that。 And so a convention in C would be that when you want your main function to end prematurely if so you can literally just return a value。

 and even though this feels a little backwards， this is just the way it is you return zero to indicate success and you return any other integer to indicate failure So by convention people go to one and then two and then three they don't think too hard about what numbers to use but in this case。

 I'm going go ahead and return one if I do get to the bottom of this file。

 So now if I open back up my term。😡，NoWdow， I run make search， No syntax errors。 dot slash search。

 I'm gonna be prompted for a number。 Let's go ahead and search for the number 50。

 And I should see found。 Meanwhile， if I run it again。

 dot slash search and I search for like the number 13， that should be not found。

 So I claim that this is now a correct implementation of linear search that's gone from left to right looking for a number that may or may not be there。

 Any questions on this version。😡，Of the code here。Yeah。And it says were training senior best。

Return0 indicates success when doing it from Maine in particular。And that's backwards。

 only in the sense that generally0 is false and one is true。 But the the。

 the logic here is that if something， if the program works correctly， that's0。

 But there's an infinite number of things that could go wrong。

 And that's why we need  one and 2 and 3 and 4 and all the way up。Other questions？It10， like。

Very beautiful。Yes。After that， and just like go away from。Correct。

 when you return 0 or return any value from main， wherever it is in your code。

 the program will effectively terminate right then in there。

 No additional code will get executed at the bottom of the function。 You'll effectively exit out。

 Just like in a normal function that isn't main。 when you return a value。

 it immediately exits that function。 It hands back the value， yeah。

So return one is just me being pedantic at this point because I'm frankly not going to really care what the exit status is of this program。

 but once I've introduced the idea of manually returning0 on this line 14 to indicate success。

 it stands to reason that I should also return a different value when I want to indicate failure。

 And so even though this does not functionally change the program， it will still work。

 it will still print the same things correctly， it's a lower level detail that programmers teaching assistant testing software might appreciate knowing what actually happened in the program underneath the hood。

😡，Alright， so what about strings， So it turns out with strings。

 we're gonna have to be think a little harder about how best to do this。

 So let me actually go ahead and do this。 Let me go ahead and get rid of much of this code。

 but transition to a different type of array。 This time and array of strings。

 And I'm gonna call the array strings itself plural just to make clear what's in it instead of numbers。

 I'm going use the square bracket notation， which just means I don't know what the moment how many elements it's gonna have。

 but the compiler can figure it out for me。 And then the spirit of monopoly。

 let's go ahead in our curly braces do something like this。

 Battleship is going be one of the strings， boot is going be another Cannon is going be a third iron is going be fourth thimble if you've ever played monopoly。

 know where these are coming from and top hat for instance。 So this gives me 12，3，4，5，6。

 I could write the number 6 here and the compiler would appreciate it。 but it doesn't matter。

 The compiler can figure it out on its own。 just based on the number of commas。

 And this also ensures that I don't write one number。To the left and then miscount on the right。

 So omitting it is probably in everyone's benefit。 Now let's do this。

 let's ask the user for a string S using get string instead of get int for some string to search for then let's go ahead and do the exact same thing for I int I equals 0 I is less than6 which is technically a magic number but let's focus on the searching algorithm for now I plus plus and then inside of this loop。

 let's do this if strings bracket I equals equals S then let's go ahead and print out just as before quote unquote found backslash n and proactively return0 this time and if we don't find it anywhere in the loop。

 let's go ahead and return one at the very bottom before which we will print not found backlash n So it's the exact same logic at the moment even though I've changed my ints to strings let me go ahead and open up my terminal window now do make search again。

😡， so far so good， let me now go ahead and do dot/lashse and let's go ahead and search for how about top hats so we should see found。

😡，All right， not found。 All right， well let's do dot slash search again， How about thimble。

 maybe it's because it's just two words， No thimble's not found either。 dot slash search。

 Let's search for the first one battlettleship。😡，Enter still not found。

 Let's search for something else like cat， not found。 What is going on。

Becauseuse I'm pretty sure the logic is exactly the same。 Well， it turns out in C， this line here。

 Currently line 11 is not how you compare strings。 If you want to compare strings in C。

 you don't do it like you did integers， you actually need another technique altogether。 And for that。

 we're going need to revisit one of our friends， which is string dot H。

 which is one of the header files for the string library that we introduced last week that has。

 in addition to functions like Stling， which gives you the length of a string。

 it also gives us as per the documentation here， Another function that will start to find useful here。

 succinctly named St comp for string compare and St compare。

 will actually tell us if two strings are the same or not。 It will indeed compare them。

 And if I use this now。Let me go back to my code here and see what I might do differently and if I go back into my code here and change this value。

 instead of using strings bracket I equals equals S。

 let's do stir compare and I read the documentation earlier so I know that it takes two arguments the first and the second string that you want to compare so strings bracket I and then S which is the string that the human typed in。

 but somewhat weirdly what I want to check for is that stir compare returns0。

 so if stir compare when given two strings is input strings bracket I and S returns an integer0。

 that actually means the strings are the same so let's try this let me do make search again。😡，H。

 what did I do wrong here？A whole bunch of errors popped out， what did I do wrong yeah？Yeah。

 so I didn't include the very header file we're talking about。 So again。

 it doesn't necessarily mean a logical error just means a stupid error in my part。

 I didn't actually include the header file。 So let me go back and actually do that up at the top。

 in addition to CSs50 do H and standard I O， let's also include string dot H let me clear my terminal and do make search again crossing my fingers that time it worked and now if I do dot search and search for top hat like before。

 now， thankfully， it is in fact， found if I do it once more and search for battleship Now it's in fact found。

 if I do it once more and search for cat， which should not be in there that is not in fact found。

 So now just intuitively， even if you've never done this before。

 why might it be valuable for this function called Stir comp to return0。😡，If the strings are equal。

 as opposed to a simple boolean， like true or false， which might have been your intuition。😡。

When you compare two strings， what are the possible。

Takeaways you might have from comparing two strings。It's not just that they're equal or not。Hello。

Okay， so maybe if the ASG values are the same， that might imply indeed literal equality。

 but something else。😡，我。How similar two springs are。Nice。

 like you and I in English certainly are very much in the habit of sorting information。

 whether it's in a dictionary in our contacts and a phone book in any such technology。

 And so it's often useful to be able to know， does this spring does this string equal another Sure but does this string come before another alphabetically or maybe after another alphabetically。

 So sometimes you want functions to give you back three answers。

 but equals equals alone can only give you true or false， Yes or no。

 and that might not be useful enough when you're trying to solve some problem involving strings。

 So it turns out stir compare actually compares the two strings for equality。

 but also for what's called playfully askcibetical order， So not alphabetical order per se。

 but askcibetical order， where it actually compares the integer values of the letters。

 So if you're comparing the letter A， it's gonna compare 65 against some other letters integer value askcibetical value。

 So we're not doing any form of sorting here。 So it's sort of immaterial。

 but as per the documentation， I do know。St compare returns zero if two strings are equal and a little teaser for next week。

 it turns out when I was only using equals equals to compare strings。

 bracket I and S I was not comparing the strings in the way that you might have thought。

 And if you have programs and Java or Python before equals equals is actually doing something different in those languages than it is actually doing in C。

 but more on that next week for now， just take on faith that stir compare is indeed how you compare two strings。

 So let's actually put this into play with some actual some additional code。

 let me propose that we implement a very simplistic phone book for instance。

 Let me go ahead and implement here。😡，How about in a new file instead of search do C。

 let's actually do phonebookc and in this phone book。

 I'm gonna to go ahead and include the same header file so CS50 do H so I can get input standardIo H so I can use printf string H so that I can use stir compare let me give myself a main function again without command line arguments for now and let me go ahead now and store a proper phone book which has some names and some actual numbers so let's store the names first so string names is going to be the name of my array and let's go ahead and store Carter's name how about my name and maybe John Harvard for phonebook throwback then let's go ahead and give me another array called numbers wherein I'll put our phone numbers so 6174951000 for Carter6174951000 for me technically directory assistance here and then for John will give them an actual one so it's actually gonna be 9494682750 you're welcome。

Text or call John when you want whoop And just for good measure。

 let's go ahead and put our country codes in here。 plus one。 even though at the end of the day。

 these are strings。 So indeed notice I'm not using an integer for these values。

 I kind of sort of should。 but here's where data types in C and programming more generally might sometimes mislead you。

 even though we call it obviously a phone number， it's probably best to represent it generally as strings。

 in fact， so that you can have the pluses， you can have the dashes so that it doesn't get too big and overflow in integer。

 maybe it's an international number for which there's even more digits。

 you on risk overflowing a value。 And in general， the rule of thumb in programming is even if in English。

 we call something a number。 if you wouldn't do math on it ever。

 you should probably be storing it as a string not as an integer。

 And it makes no logical sense to do math on phone numbers per se。

 So those are best instinctively left as strings。 And in this case。

 even more simply this ensures that we have pluses and dashes stored in。Of the string。 All right。

 so now that I have these two arrays。In parallel if you will。

 like I'm assuming that Carter's name is first， so his number is first， David's name is second。

 so his number is second， John's is third and thus third， so let's actually search this。

 let's ask the user for about a name front using get stringing。😡。

And this will be a name to search for in the phone book just like we did in week0。

 let's do for int I equals0 I less than3， again， the three is bad practice。

 I should probably store that in a constant， but let's keep the focus for today on the algorithm alone。

 I+ plus then in here let's do if how about names bracket I equals equals name typed in but wait a minute I'm screwing this up again。

😡，What should I be using here？Stir compare again。 So let's do stir compare names。

 bracket I comma name， which came from the user。 And if that return value is0。

 then let's go ahead and print out just like before， found backlash n。 but you know what。

 we can do something more interesting。 Let's actually print out the number。

 So I didn't just find something。 I found the name。

 So let's actually plug in that person's corresponding number。

 So now it's a more useful phone book or contact app where I'm gonna show the human not just found but found this specific number。

 Then I'm gonna go ahead before and return zero to indicate success。

 And if we get all the way down here， I'm gonna go ahead and say not found and not print out any number because I obviously haven't found one and return one by convention to indicate failure。

 So let me open my terminal window。 Let me do make phone book enter so far so good。

 dot slash phone book。 Let's search for Carter enter found his number， let's do it again。

 dotlash phone book。 David found it。 Let's do it one more time for John。Found it。

 And just for good measure， let's do one other here。 like Eli enter not found in this case。 Allright。

 so it seems to be working based on this example here。

 but now we've actually implemented the idea of like a proper phone book。

 but does any aspect of the design of this code， even if you've never programmed before CS50。

 does anything rub you wrong about how we're storing our data， the phone book itself。

 these names and numbers。😡，Does anything rub you the wrong way。 Yeah，m back。Yeah。

 really good observation。 I'm separating the names and the numbers。

 which indeed it looks a little bit weird。 And there's actually this technical term in the world of programming。

 which is code smell， where like like something smells a little off about this code in the sense that like this probably doesn't end well。

 right if I add a fourth name， a fourth number， a fifth name， a 50th name and number。

 like at some point， theyre probably gonna get out of sync。

 right So like there's something awry about this design that I shouldn't decouple the names from the number。

 So something kind of smells about this code， so to speak。

 And anytime you perceive that in your code。 it's probably an opportunity to go about improving it somehow。

 But to do that， we actually need another tool in the toolkit。 And that is， again。

 this term that I've used a couple times data structures。

 like arrays have been the first of our data structures。 and they're so simplistic。

 It just means storing things back to back to back， contiguously in memory。 But it turns out C。😊。

And a little bit of new syntax， but it's not a lot of new syntax today。

 A little bit of new syntax today will allow us to create our own data structures。

 our own types of variables， largely using syntax we've seen thus far。 So to do this。

 let me propose that in order to represent a person in a phone book， Well。

 let's not just implement them as a list of names and a list of numbers。

 wouldn't it be nice if C had a data type actually called person because if it did。

 then I could go about creating an array called using the pluralized form people containing my people in my phone book。

 and maybe a person has both a name and a number and therefore we can kind of keep everything together。

 So how can I do this Well， what is a person Well a person really in this story is a person has a name and a person has a number。

 So can create can we create a new data type that maybe has both of these together？ Well。

 we actually can by using one piece of new syntax today， which。

Just this here using oh it's called astruct。 we can create our own data structure that actually has some structure and it it's not just one thing like a string or an int。

 maybe it's two strings。 maybe it's two int。 maybe it's one of each。

 So a structure can be a variable that contains any number of other variable so to speak and type def is a crypto keyword that just means define the following type。

 invent the following data type for me。 and the syntax is a little weird， but you say type defstruct。

 curly brace inside of the curly braces you put all of the types of variables you want to associate with this new data type and then after the curly brace。

 you invent the name that you want to give it。 and this will create a new data type in C called person even though no one thought of this decades ago when C was created alongside of the ints and the floats and so forth。

So how can I actually use this Well it turns out that once you have this building block of creating your very own data structures。

 I can go back into my code and improve it as follows and direct response to your concern about it seeming not ideal that we're decoupling the names and the numbers Now it's going to look a little more complicated at first。

 but it will scale better over time。 So within my code here。

 I'm going to go ahead and essentially type out exactly that same data type So define a structure that has inside of it a string called name and a string called number and let's call this thing a person So these new lines copied and pasted from the slide a moment ago。

 just invent the data type called person So the only thing we need today is the syntax via which we can set a person's name and number like how can we access those values。

 So to do this， I'm going go ahead and erase the hardcoded array that I had before and I'm gonna give myself one array of type person。

😡，Called people with room for three people。 So this seems like a bit of a mouthful。

 but the new data type is called person。 the array name is called people， which in English is weird。

 I mean， it could also call it persons to make it a little more parallel。

 but we call them people generally， and I want three such people in my phone book Now how do I actually initialize those people Well previously I did something like this names bracket0 and then I did numbers bracket0。

 well it's a similar idea， I do people bracket0， but if I want to set this person's name the one new piece of syntax today as a period a literal dot operator that says go inside of this person and access their name field or their name attribute and set it equal to quote unquote Carterter then go into that same person but go into their number field and set that equal to plus 1。

617，4，9，51000 then and I'll just separate it with whitespace for readability go into people bracket。

😡，One， set their name into mine David， let's go into people bracket one number。

 set that equal to the same since we're both available through the directory， so 617。

4951000 and then lastly let's go ahead and do people bracket2 dot name equals quote unquote John and then people bracket 2 dot number equals quote unquote plus 19494682750 fix my dash semicolon and now I think I can mostly keep the rest of the code the same because if I'm searching for this person's name I think the only thing I want to change is this because I don't have a names array anymore so what should I change this highlighted phrase to in order to search the I person's name。

😡，What should this be yeah？People bracket I dash name， because this whole。

 the whole point of this loop is to iterate over each of these people one at a time。

 So people bracket I gives me the Ih person。 First is brief people 0， people1， people，2。

 But if on each iteration， I want to check that person's name and compare it against whatever the human typed in。

 now I can do exactly that。 but I have to change the output to be people bracket I dot。😡。

Number in this case。 So I've added a little bit of complexity and granted。

 this is not gonna be the way long term you create a phone book。

 odds are we're gonna get the phone book with a loop of some sort。 we're gonna use a constant。

 So I know how many people I have room for for demonstration sake。

 I'm just typing everything out manually。 But I think logically now we've achieved the same thing。

 So let me do make phone book for this new version。 No syntax errors， dotlash phone book。

 Let's search for Carter enter。 And there indeed， is this number。

 let's go ahead and search for David。 There's my number。 And lastly， let's search for John。

 his number。 And again， we'll search for someone we know is not there。 Eli and Eli is not found。

 So what we've done is try to solve this problem of introducing a brand new data type that allows us to represent this custom data that you and I just created。

 And that is by using thestruct keyword to cluster these things together。

 and the type de keyword to give it a brand new name that we might like。 Now， as an aside。

 when it comes to styling your code you'll actually see that style 50 in similar tools will。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_6.png)

Put the name of the data type on the same line is the closing curly brace。 just sort of a curiosity。

 That's fine。 Even though I wrote it the first way for consistency with scratch and our prior examples。

 this is the right way in styling it。 Any questions now on this data type。😊，Yeah。I两。答应。

The question is， can do you have to assign both the name and the number when creating a person or can you only get away with doing assigning one of them。

 you can， But that's gonna be one of those socalled garbage values， typically。

 And so there's just gonna be some bogus data there。

 And unless you are so careful as to never touch that field thereafter。

 you probably run the risk of some kind of bug， even a crash in your code。

 If you try to access that value later， even though you've never initialized it。 So， yes。

 it's possible， but no， do not do that。 Other questions。Oh。All right， well up until now。

 now that we have the ability to sort of represent more interesting structures up until now。

 we've sort of assumed that in order to get to binary search。

 we have a phone book that someone already sorted for us for our second demonstration with our volunteers we assume that someone Carter in that case had already sorted the information for us it was proposed by the audience that what if we sort the information first and then go find the number 50 that invited the question even early on。

 well how expensive is it to sort， how much time and money inefficiency do Google on Microsoft and other spend to keep their data and our data sorted。

 well let's consider what the problem really is， if this is how we represent any problem。

 the unsorted data that we might consume by typing things in randomly to a search engine or crawling the internet or just adding context in any old order to our phone is arguably unsorted。

 certainly not alphabetically sorted by default but we want to get it sorted and so somewhere in here in this black box we need a set of algorithms for actually sorting information as well for instance。

😡，If we have these integers here， unsorted 7，2，5，4，1，6，0，3， effectively random。

 the problem of sorting， of course， is to turn it into 0，1，2，3，4，5，6，7 instead。

 And there's a bunch of different ways to do this？ But before we do that。

 I think it's probably time for some brownies。 So let's go ahead and take a 10 minute break。

 And we'll see you in 10。 Alright， we are back。 And where we left off with this cliffhanger。

 We've got some unsorted numbers。 We want to make them sorted。 How do we do this。

 And at the risk of one too many volunteers， could we get 8 more volunteers。 wow， okay， overwhelming。

 Okay， how about 1，2，3，4。 How about all three of you， Okay，5，6。😊，7 and。Okay， hey， come on， all right。

 one from each section， all right， come on down。All right， let's come on down。Thank you。

 and if you all could grab a number here， so you'll be seven， stand on the left there if you could。

 all right， you'll be number two， stand to his left。😡，Okay， let's keep coming。Okay， yeah。Okay。

 here we go。There go。Okay， be 0 and 3。 Okay， so let's just make sure they match what we got there。

 Good so far。 Okay， so we have8 volunteers here， an array of volunteers， if you would。 This time。

 we've used 8 rather than 7。 We deliberately had 7 lockers just so that the divide by two math worked out。

 that was very deliberate that there was always a half， a middle， a middle， a middle。 In this case。

 it doesn't matter because we're gonna focus on sorting。 But first。

 how about some introductions from each group。😊，I'm Rebecca。

 I'm a first year in Pennypackcker and I'm thinking about studying environmental science and public policy。

😊，Nice。I'm Maria， I'm also in Pennty Packer， I'm the first year and I'm thinking of studying bioengineering Wo。

😊，My name is Karen Lee， I'm a freshman in Matthews， I'm playing on studying App mathematics。

 nice Matthews。My name is Emily， I'm a first year in Canada and I'm still deciding what to study there。

😊，My name is Tayya， I'm a first year from Toronto and I'm planning on studying Econ and CS。

My name is Teddy， I' am first year in Herbert and I'm planning on concentrating in computer science with linguistics。

来。My name is Lenny， I'm a first year in Matthews and I'm planning on concentrating in Gov and CS。

My name is E I。 I'm a first year in Holliis， and I plan on concentrating and sees E live。

 We keep looking for you today。 Okay， so if you guys could scooch a little bit this way。

 just to be a little more centered， notice that this array of volunteers is entirely unsorted。

 So we do thought we do three passes at this。 Could you all sort yourselves from smallest to largest。

 go。😊，Alright， that was very good。 So， yes， so sure， okay。😊，And let's see what was your algorithm？

I just kind of found the person that was like one lower one higher。

 So I like looked at him me had two。 So I knew I' to be on his left and then she had three。

 So I told her to come to my right and I knew he had five。 So nice。

 pretty clever and how about your algorithm same thing looked for the number that was lower and higher and the middle interesting because I think from the outside view。

 it all seemed very organic and things just kind of work themselves out， which is fine。

 but I dare say what you guys did was probably a little hard for me to translate into code So let me propose that we take two passes at this if you could reset yourselves to be in that order from left to right。

 which is just the exact same sequence just so that we're starting from the same point each time175 very good。

 so let me propose this。 we can approach sorting in a couple of different ways。

 but it needs to be methodical it needs to translate ideally to pseudocode and eventually code So as much as we can quantize things to be step by step I think the better this will scale overall especially when there's not eight people。

 but maybe there's。80 people or 800 because I dare say that if we had everyone in the room sort themselves if they were all handling a number like that probably wouldn't have worked out very well。

 it probably would have taken forever because there's just so much more data。

 So let's be a little more methodical。 So for instance。

 I don't have a bird's eye view of the numbers just as before because even though we don't have doors in front of our volunteers。

 they're effectively lockers too in the computer or the human in my case can only look at one door at a time。

 So if I want to find the smallest number and put it where it should go on the left。

 I can't just kind of take a step back and be like okay obviously there's the one I have to do it more methodically。

 So I'm going check here 7 at the moment， this is actually the smallest number I've seen。

 So I'm gonna make mental note of it2， I see now， I can forget about the7 because two is clearly smaller5。

 I don't need to remember it4， I don't need to remember it 1 that's clearly smaller。

 have I found my smallest number。Not even because there actually is a zero。

 so I should go through the whole list， but I will remember that my smallest element is now one。

6 is not smaller， Oh，0 is smaller， so I'll remember this， three is not smaller。

 and so now our volunteer for zero was what was your name。😡，Mary An， where should we put you clearly？

So there， But what's your name again。Eli's in the way。

 So we could have Mary Ellen and Mary Ella just go to the right of Eli。

 But that's kind of cheating right， because if this is an array， recall that they are contiguous。

 but there could be other stuff in memory to the left and to the right。 So that's not quite fair。

 We can't just have the luxury putting things wherever you want。 But Eli。

 you're not even in the right order anyway So why don't we just swap you to。

 So Maryla and Eli swap but now I've taken one bite out of this problem。

 I've coincidentally made it a little better by moving Eli closer to where he is。

 But you know what he was in a random location anyway。

 So I don't think I made the problem any worse fundamentally。 Now I can do this again。

 And I can shave a little bit of time off of it because I don't need to revisit Maryla because if she was the smaller and I've already selected her from the array。

 I can just move on and take one fewer bite this time around。 So 2 is the smallest number， not 5。

 not1 is the smallest number。 So I'm going remember that as with the mental variable，6，7，3。

1 is the small。So let me select number one， and we're going to have to evict U。

 which is making the problem slightly worse， but I think it'll average out。😡。

And now 0 and one are in the right place。 So now let me do this again， but faster。 So5， okay，4。

2 is the smallest，6，7，3， Okay，2， let's put you where you belong， evicting 5。

 Now I can skip all three of these volunteers。 Okay，4 is the smallest。 Nope， Nope， Nope 3。

 you're the smallest。 Let me evict 4。 Allright， And now let me move behind in front of these volunteers。

5，6，7，4。 Come on back。All right， and now let's select 6，7，5， okay， come on back。Oh no no cheating。

 you like， Okay， and then let's see 5，7，6， Okay，6， come on back。Okay， now you have to move。

 And now we've selected in turn， all of the numbers from left to right。

 And even though that did feel slower， I was doing it a little more verbally as I step through it。

 But I dare say we could translate that probably more to code。 Why。

 because there's a lot of like looping through it and probably a lot of conditionals。

 just asking the question， I this number smaller than this one or conversely greater than this other one。

 Allright， let's do this one more time。 if you guys could reset yourselves to this ordering。😊。

Alright， so we again， have 7，2，5，4，1，6，03。 Good。 So how about this。

 I liked the intuition that they originally had funny enough。

 whereby they just kind of organically look to the person to the left and the right and kind of fix the problem。

 So if they were out of order。 They just kind of swap locally adjacent to each other。

 So let's try this。 So7 and2， you're clearly out of order。 So let's swap just you to，7 and 5。

 you're out of order。 Let's swap you to 7 and 4， let's swap you to 7 and1， let's swap you to 7 and 6。

 let's swap you to，7 and 0， swap you to7 and 3 swap you to。 Okay that was a lot of swapping。

 but notice what happened。 I'm not done clearly。 It's not sorted yet。

 but I have improved the situation。 How who is now definitely in the right place。😊。

So seven or Eli has wonderfully bubbled all the way up to the top of the list so to speak。

 now I can actually skip him moving forward so that takes one bite out of the problem。

 let's do this again， two and five are okay， five and4， let's swap。😡，Look over there。😊，Thank you。

 five and one， let's swap。Five and six are good， six and zero， let's swap。Six and three， let's swap。

And we don't have to worry about Eli。 And now what's your name again， Har。

 we don't have to worry about him either as well。 So now I can go back to the beginning。

 And even though it feels like I'm going back and forth a lot。

 that's okay because the problem's still getting better and better。

 I'm taking a bite out of it each time，2 and4 are good，4 and one， Let's swap。😡。

4our and five are good five and0 swap， five and three， swap。

 and now these three are in the right place， let's do it again， two and one， here we go let's swap。

 two and4， okay，4 and zero swap。4 and three swap now these four okay， one and two， you're good。

 two and0， swap， two and three， you're good， you're good， okay， now one and zero， swap one and 2。

 and now zero and one。😡，A round of applause， if we could， for our volunteer。Right。

So if you want to put your numbers on the tray there， we have some lovely super Mario Oreos today。

 which maybe drives a lot of the volunteerism， but。😊，Here we go， thank you all so much。

And maybe Carter， if you can help with the reset。Alright， here we go。 This is， yes， oh， all said。

 Thank you very much。 Thank you。 Thank you guys。 So to recap。 Thank you， yes。😊，To recap。

 let's actually formalize a little more algorithmically what we did。

 and I deliberately kind of orchestrated things there to show two fundamentally different approaches。

 One where I kind of selected the element I wanted again and again on the basis of how small it was I looked for the smallest and the next smallest and so forth。

 The second time around I took a different approach but just fixing local problems。

 but I did it again and again and again until I fixed all of the minor problems and frankly。

 what they did organically at the beginning was probably closer to the second algorithm than the first。

 even though I'm not sure they would write down the same pseudocode for it the first algorithm we executed is actually called selection sort and I deliberately used that vernacular of selecting the smallest element again and again to evoke this name of the algorithm So for instance。

 when we had these numbers here initially unsorted。

 I kept looking again and again and again for the smallest element and I don't know a priori what the smallest number is until I go through the list at least。

Once then I can pluck out the zero。 I then go through the list a second time to pluck out the one。

 a third time to pluck out the two。 Now， this assumes that I don't have an infinite amount of memory because even though I kept repeating myself looking for the next smallest element。

 next smallest element， I propose that I only keep track of one number at a time。

 one variable in my mind， which was the smallest element I have seen thus far。 if I used more memory。

 I could probably remember from the first pass where the two is where the three is。

 but that's a different algorithm， it would take more space， more memory。

 I was confining myself to just one variable in my approach。

 So here might be the pseudocode for what we'd call selection sort。

 the very first algorithm that we all did together， not organically but more methodically as a group。

 I would propose that we use some syntax from C， when we talk about the loop and say4 I from0 to n-1。

 Now， why is that， Well if there were n people or80 through 7 or the index。

Or indices of those humans on stage from left to right。

 So what did I have myself do find the smallest number between numbers。

 bracket I and numbers bracket n-1。 So when the iteration when the loop starts 0。

 this is literally saying between numbers bracket 0 and numbers bracket n-1。

 So from the far left to the far right， find me the smallest number。

 then swap that number with numbers bracket I。 So that's why we evicted the person all the way over to the right or your left。

 the very first time。 and then the next person and the next person and so forth。

 So this is an algorithm that has us go back and forth back and forth。

 iteratively selecting the smallest element。 So if we generalize this now。

 not away from8 people to like n people， you can think of them as representing an array。

 aka doors like this where the leftmost one is 0， the rightmost one is n-1。

 second to last is n-2 and so forth。 if we don't know。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_8.png)

Care what end specifically is。 So how do how many total steps does selection sort perhaps take。

 And let's make this a little more real here。 Let me actually open up， for instance。

 a quick visualization here。 And on the screen here。

 you'll just see now an artist's rendition of an array of values whereby tall purple bars represent big integers and short purple bars represent small integers。

 So the idea of any sorting algorithm here as visualized is to get the small bars on the left and the big bars on the right。

 And this is a nice handy tool that lets you play around with different algorithms。

 So here is selection sort that I've just clicked in pink again and again。

 is the equivalent of me walking through the volunteers looking for the next smallest element。

 And as soon as I found them I swap them into their leftmost location evicting whoever there in order to gradually sort this list from left to right。

 And so as you can see here， it holds very briefly in pink。

 whatever the currently smallest element it is found is that's the analog。😊。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_10.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_11.png)

Of like me pointing to my head。Whereby it's constantly comparing， comparing， comparing。

 looking for the next smallest element。 Now， I'm kind of stalling because I'm running out of like intelligent words to say。

 But that is to say this algorithm feels kind of slow。 Like， it seems to be doing a lot of work。

 Where is the work。Coming in， like， what is it doing a lot of specifically。Yeah。Yeah。

 it keeps going back and forth and back and forth and even though it's shaving a little bit of time because it doesn't have to stupidly go all the way back to the beginning and I was saving myself a few steps like it's a lot ofcyclity again and again and again and put another way。

 it's a lot of comparisons again and again and some of those comparisons you're doing multiple times because I only remembered one element at a time in my head so I have to kind of remind myself on every past which is smallest which is smallest So this invites the question how fast or how slow or equivalently how efficient or inefficient is something like bubble selection sort well let's actually consider how we could analyze this as follows So if we have n numbers that we want to sort。

😡，How many comparisons do we do the first time？ Well， if there's n numbers。

 you can only make n-1 comparisons。 Why， because if we have eight people here and we started with whoever's all the way over here。

 we compare this person against 7 others。 N-1。 if n is 8。 So the first pass through the list。

 I made n-1 comparisons。 But that put the smallest number 0 in place。

 the second time I walked across our a volunteers。 I didn't need to walk in front of all8。

 I could shave off a little bit and do7 of them。 then 6， then 5， then4。

 So if I were to write this out roughly mathematically。 I could do this。

 N-1 plus n-2 plus n-3 plus dot dot dot all the way down to my very last comparison at the end of the list。

 Now， this is the kind of thing that typically in like high school。

 you'd look at the back of the math book or physics book that's got a little cheat sheet for all of the formulas that add up this series here。

 let me just stipulate adds up to this。 N times n-1 divided by2。

 So no matter what n is this formula captures that series。😊，That summation of all of those values。

 So that is how many steps I took again and again and again。

 when implementing selection sort for8 people。 So， of course， let's multiply this out。

 So this is like n squared minus n all divided by two。 Let's do it out a little bit more。

 That's n squared divided by2 minus n over 2。 And now we're back into the territory of running times。

 like how many steps， does this algorithm take how many comparisons are we making。 Now。

 n squared seems like the biggest term， it's the dominant term。 In other words， as n gets large。

 not 8 but 80 or 800 or 8000 or 8 million squaring that is going make a way bigger difference than just doing like n divided by two and subtracting that off。

 Similarlyly， just dividing even this quadratic formula by  two。 Like yes。

 it's gonna have it literally but that's kind of a drop in the bucket as n gets larger and larger and larger。

 It's still gonna be a crazy big number。 So computer scientists would typically wrap this in some big O notation and say。

 okay， okay， selection。Is on the order of n squared。 That's not a precise measurement。

 but it's on the order of n squared because it's making so many darn comparisons。

 not unlike everyone shaking everyone else's hand。 like I proposed verbally earlier。

 It's a lot of work to get that done。 So selection sort is on the order of n squared steps。

 And that's kind of a slow one。 That's what is at the top of my cheat sheet earlier when I proposed a ranking of some common running times。

 There's an infinite number of them。 But those are some of the common ones。

 So can we do actually better。 Well， if bubble sort then is in big O of n square， sorry， sorry。

 spoiler， if selection sort is in the order of n squared， could we maybe get lucky sometimes。😊。

Like with selection sort， what would the best case scenario be， Well。

 the best case would be like everyone is already sorted 0 through 7。 and we just get lucky。

 But does bubble sort。Does selection sort appreciate that？

Does selection sort take into account whether the list is already sorted， not necessarily。

 because if you look at the pseudocode even， there's no special conditional in here that says if it's already sorted。

 exit early， It's just gonna blindly do this This many times。

 And you can actually see pseudocode wise the n squared。

 notice that this line of pseudocode here is essentially telling me to do what do something n times from0 to n minus-1 or equivalently if you prefer the real world from one to n that's n times total。

 But what are you doing inside of this loop。 Well， every time you're inside of this loop。

 you're looking for the smallest element， looking for the smallest element and that might take you as many as n steps。

 So another way to think about the running time of this algorithm selection sort is this loop is telling you to do something n times this line is telling you do something n times as well。

 and that's roughly n times n or n squared。 It's not precise， but it's on the order of n squared。

 Unfortunately， if you're just blindly doing that much work。Always。

 even if you have any number of doors， this is going to end up being in omega of。N squared as well。

 because even in the best case where all of the numbers are already sorted。

 there is nothing about the algorithm called selection sort or even my implementation thereof that would have said。

 wait a minute， like I'm done and exit prematurely。 So selection sort is in big O of and mega of。

N squared as we've designed it。 And by coincidence， because those boundaries are the same。

 you can also say that it's in theta of n squared， no matter what you're gonna spend n squared steps or n squared comparison。

 But that second however that I keep teasing called bubble sort。

 And I deliberately use the word bubble in my description of what was happening because Eli。

 I think was our first volunteer who kind of bubbled his way up all the way to the end of the list。

 then number 6 did then5 then4 then three then2， then one all of the numbers kind of bubbled their way up being the bigger values to the right。

 So bubble sort just does something again and again by comparing adjacencies， comparing comparing。

 comparing and then it does it again。 And again and again， So let's analyze bubble sort。

 If for instance， this was the original ray that we tried sorting before， same exact numbers。

 I was doing things like flipping the7 and the two。 and then the7 and the5。 and then the7 and the4。

 But that would only fix maxim that would only fix minimally one number。

 I then had to repeat again and again。😊。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_13.png)

Again so that one too felt like it was taking some time。

 So here's one way of thinking about bubble So。 Bu sort pseudocode could say this。

 repeat the following n times。 And that's why I kept going through the list again and again。

 for I from 0 to n minus-2。😡，Now， this is a little weird。

 but we'll get back to this from I from 0 to n-2。 If the number at location I and the number at location I plus1 are out of order。

 swap them。And then just repeat， repeat， repeat。 But we've never seen n -2 in pseudocode before。

 Why is it n -2 and not the usual n -1。Yeah。takeate your number and pairs to next school。

 but if you're。Exactly， because we're taking a number and comparing it to the next one。

 So you better not go all the way to the end and expect there to be a next one at the end of the list。

 So if we use these same numbers here， even though they're in a different order。

 if this is location 0， and this is location n-1 always， If you think of I as being my left hand。

 It's pointing from 0 to 1 to 2 to 3 to 4 to 5 to 6 to 7， if you get to the end。

 you don't want to look at I plus 1 because that's pointing to no man's land over here。

 and you can't go beyond the boundaries of your array。 But n-2 would be the second to last element。

 as you know， and that makes sure that my left hand and right hand。

 stay within the boundaries of the array， if left hand represents I and right hand represents I plus1。

 So it's just to make sure we don't screw up and go too far past the boundary of the array。

 But as implemented here， this two does not take into account whether or not the array is already sorted And so and technically。

 we can actually do this n -1 times because the last one you get for free。 It ends up being in place。

 But even still， let's do。quick analysis here。 If we've got n doors in total from 0 on up to n-1 bubble sorts analysis looks a little bit like this。

 Do the following n-1 times n-1 times。 Well， how do we get from that。

 Let me back up to the pseudocode。 If this is the pseudocode， as I originally put it。

 I then may propose verbally a refinement。 You don't need to repeat yourself n times again and again。

 because again， the last one bubbles up。 But by process of elimination。 It's in the right place。

 So you can think of it as just n-1 times。How many times can you compare I and I plus1？ Well。

 you're iterating from 0 to n-2。 And this is where the math is gonna get weird。

 But that is n-1 steps also Y， because if you do it in the real world starting at one。

 this is saying from I from1 to n-1。 And then maybe it pops a little more。 obviously。

 this inner loop is repeating n -1 times。 So outer loop says do the following n -1 times inner loop says do this now n-1 times mathematically。

 then that's n-1 times n-1。 now we've got our old foil method。

 So n squared n n plus1 combined like terms gives us n squared-2 n plus1。

 But now let's think like a computer scientist。 when n gets really large。

 we definitely don't care about the plus1。 when n gets really large。

 We probably don't even care about the -2 n。 It will make a mathematical difference。

 but a drop in the bucket。 Once n gets to be in the millions or billions。

 So this would be on the order of what。Similarly。On the order of n squared as well。

 So algorithmically， and actually we'll use a different term now， asymptically。

 asymptotic notation is the fancy term to describe big O and omega and theta notation。

 asymptically bubble sort is quote unquote， the same as selection sort in terms of its upper bound。

 It's not 100% exactly the same。 If we get into the weeds of the math。

 they're obviously different formulas。 But when n gets really large and you plot the pictures on on a chart。

 they're going to look almost the same because they're going to be fundamentally the same shade。

So in our cheat sheet here， bubble sort now is in big O of n squared。

 but let me propose that we make an improvement。 Here's our pseudocode earlier。

 When might it make sense to abort bubble sort early。😡，Like。

 when could you logically conclude that I do not need to make another pass again and again。

And remember what I did from left to right over our volunteers， I was comparing， comparing。

 comparing， comparing and maybe swapping people who were out of order。So what could I do？

To short circuit this。Perfect， if I compare through the whole list left to right。

 and I make no swaps， it stands to reason that they're already ordered。 Otherwise。

 I would have swapped them。 And therefore I would be crazy to do that again and again and again。

 because if I didn't swap them the first time around。

 why would I swap them the second time around if no one's moving so I can terminate the algorithm early。

 So in pseudocode， I could say something like this。 if no swaps quit。

 And I could do that inside of the inner loop。 So once I make a pass through the people。 And I say。

 did I make any swaps。 if no， just quit because they're not gonna move any further if they didn't just move already。

 So bubble sort， then might arguably be an omega of what In the best case。

 how few steps could we get away with with bubble sort。It's not one， but it is N Y。

 because I minimally need to go through the whole list to decide， did I make any swaps and logically。

 and this will come up a lot in the analysis of algorithms。😡，Any question like， is this list sorted。

 cannot possibly take only one step if you've got n elements Y， because then you're just guessing。

 like if you don't at least take the time to look at every element。

 how in the world can you conclude logically that they're sorted or not。

 like you minimally have to meet us halfway and check every element。 So it's minimally in mega of n。

 Constantine wouldn't even give you time to look at the whole list if there's n elements。

 So that's the intuition there。 So we can't say anything about theta notation for bubble sort。

 Because it's different upper and lower bounds， But we seem to have done better asymptotically than。

Selection sort。 they're in the worst case， they're just as bad。 They're super slow。

 But in the best case， bubble sort with that tweak that conditional about swapping might actually be faster for us。

 And you'd want Google。 Microsoft。 your phone to use that kind of algorithm。

 Let me go back to the sorting demonstration earlier。 Let me re randomize the array。

 Small bars is small number， big bars is big number。 And let me click bubble sort this time。

 And you'll see again， the pink represents comparisons。

 But now the comparisons are always adjacent from left to right。

 So this is pretty much doing with more bars。 What I did with eight people here。 And you'll see that。

The biggest elements， Eli， being the first one of the humans， bubbled up all the way to the right。

 followed by the next， largest， next， largest， next largest。 But here again， you can visually see。

 And with the number of words I'm using to kind of stall here。

 you can hear that this is kind of slow because you're doing a lot of comparisons again。 And again。

 and again， and you're making improvements。 So you're taking bys out of the problem。

 But really only one B at a time。😊，So I kind of feel this is gonna be like holding in a sneeze if we don't finish this。

 So I feel like we should give you emotional closure with getting this to finish。😊。

Any questions in the meantime， because there's going to be no surprise， It's going to be sorted。

This is bubble sort。No， all right。 We're almost there。

 It's going faster because the list is effectively getting shorter and。Okay。

So that then was bubble sort。 But both of these， I claim now are actually pretty inefficient。

 They're pretty slow。 And my God， that was only eight humans on the stage。

 that was only like what 40 or 50 bars on the screen。

 What if we start talking about hundreds or thousands or millions of inputs like those algorithms are probably going to take crazy long because n squared gets really big。

 So can we do better than n squared。 Well， we can， But let me propose that we introduce a a new problem solving technique that we've actually been using already just not by name。

 in programming and in mathematics。 There's this idea of recursion and recursion is a description for a function that calls itself a function that calls itself is recursive。

 So what do we mean by this。 Well， we've actually seen this already。

 Here's the same pseudocode for binary search earlier。

 and binary search by imply to when either left or right or left or right having each time。😊。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_15.png)

So that was the division and conquering。 So this is the same pseudocode。

 But notice that in my pseudocode earlier， I literally used the keyword search inside of my definition of search。

 So this is sort of one of those like circular definitions。 like if this is a search algorithm。

 how am I getting away with using the word search in the definition of search。

 know it's kind of when you get reprimanded for using a word to define a vocabulary word。

 This is kind of like that。 because this algorithm is calling itself。

 this search function is calling itself。 Now， normally， if you were to have a function， call itself。

 call itself， call itself call itself， it would just do that infinitely。

 and presumably it would go on forever， or the program or computer would probably crash because out of memory or something like that more on that next week。

 But there's a key detail。 a key characteristic about this algorithm that makes sure that doing the same thing again and again is not crazy it's actually going to lead us to a solution。

 even though I'm using search here or search here， what's happening to the size of the problem。

For each of these lines。What's happening， yeah。It's being cut in half。

 So even though I'm doing the exact same thing algorithmically again and again。

 I'm doing it on a smaller， smaller， smaller input， fewer， fewer， fewer doors， fewer， fewer。

 fewer people。 And so even though I'm doing it again and again。

 So long as I have this so-called base case， as we'll call it that just make sure if there's no doors。

 You're done I can break out of what would otherwise be an infinite loop of sorts。

 All right so those two lines， we've already kind of seen And actually we saw this in week 0。

 So this is the pseudocode for the phone book example from week 0。

 and you might recall that we had these lines of code here。

 and this is very procedural or iterative where I literally told you go back to line 3。

 and we did that today， when we took attendance。 So to speak with that third algorithm。

 you went back to step 2 again and again， that's a very iterative loopbased approach。

 But you know what， I could be a little more clever here2 in week 0。

 we just didn't want to get too far ahead of ourselves。

 let me actually change these highlighted lines to be more succinctly search left half of book。

 search right half of book。Now tighten the code up。 So it's kind of a shorter algorithm。

 but it's the exact same idea。 But on week 0， I very methodically told you what I want you to do next。

 But here I'm sort of recognizing that wait a minute。

 I just spent the past six lines telling you how to search So go do more of that you have all of the logic you need So this too is recursive in the sense that if this is a search algorithm。

 the search algorithm is using a search algorithm inside of it。 But here too。

 the phone book was getting divided and divided and divided in half again and again。

 So recursion doesn't just describe mathematical formulas。

 it doesn't just describe pseudocode or code， even physical structures。

 So we deliberately brought back these bricks here today， which are reminiscent of course。

 for Mario and Super Mario brothers， that pyramid， especially if we get rid of the distractions of the ground and the mountains and so forth。

 is itself recursive as a structure Now why is that Well， here you can kind of play verbal games。

 if this is a pyramid of height4 and ask the question， well， what is that。APyramid of height4。

 I could kind of be difficult and say， well， it's just a pyramid of height3 plus one other row。

 All right， well， what's a pyramid of height 3， you could be difficult and say， well。

 it's just a pyramid of height 2 plus one more row。 What's a pyramid of height2。 Well。

 this plus one more row。 I might have skipped the step there。 What's a pyramid of height2。 Well。

 it's a pyramid of height1 plus one more row。 What's a pyramid of height 1。 Well。

 it's nothing plus one more row or at this point， you can just say it's a single brick。

 You can have a base case that just says like the buck stops here， stop asking me these questions。

 I can special case or hard code my answer to the very tiniest of problems So even those bricks then are sort the pyramid is recursively defined。

 And we can actually implement this even in code if we want in a couple of different ways to make this clear。

 So let me go back over to VS code here。 and let me propose that we do one old school iterative example with this code iteration dot C and iteration just means to loop again and again an iteration is a pass through。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_17.png)

and let me go ahead and whip this up as follows。 Let's include the CS50 library。

 So we have our get in function。 Let's include standard I O so that we have printf。

 Let's go ahead and create main。😊，With no command line arguments today。

 let's go ahead and create a variable of type ant set equal to the return value of get ant asking the user for the height of the pyramid。

 And then let me assume for the sake of discussion that there is a function now that will draw a pyramid of that height。

 Allright， now let's actually implement that function as a helper function so to speak。

 So if I have a function called draw， it's going clearly take an integer。

 and I'll call it maybe n as input。 and it doesn't need to return anything。

 So I'm gonna say that this is a void function， doesn't return a value。

 It just has a side effect of printing bricks on the screen。

 How can I go about doing a pyramid of height n。 Well， I'm gonna to do this one。

 which looks like this one at a time， then two then3 than4。 this is a little easier， for instance。

 then problem set1， which had the pyramid flipped around the other way。

 So this one's a little easier to do deliberately。 So if I go back to my code。

 I could say something like this for int I gets0， I is less than let's say n， which is the height。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_19.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_20.png)

I plus plus that's going to essentially iterate over every row of the pyramid top to bottom。

 This might feel similar， reminiscent to problems at one。 Then in in my inner loop。

 I'm going to do four int J gets0。 J is less than I plus1 J plus plus。

 and we'll see why this works in a moment。 and then let's go ahead and print out a single hash。

 No new line。 but at the very bottom of this row。 Let's print out just a new line to move the cursor down a line。

 Now I'm not done yet。 let me hide my terminal for a second。 I need the prototype。

 So I'm going copy this。 paste it up here with a semicolon。😡，And I think now the code is correct。

 Now， why is this correct， Because I'm my outer loop， I'm iterating n times starting at0。

 My inner loop realize I want to have at least one hash then2 then 3 than 4。

 So I can't start my number of hashes that's0。 And that's why I'm doing J all the way up to I plus1。

 so that when I is 0。 I'm actually still printing one hash。 And then two hashes and then 3。

 Otherwise I would start with 0， which is not my goal。

 Let me go in and do make iteration to compile this。 dot slash iteration。

 And let me go ahead and make my terminal bigger enter The height will be， for instance，4。

 And indeed， it's not quite to scale because these are a little more vertical than they are horizontal。

 but it' essentially looks like that pyramid。 And I can do this even larger。

 Let's do this again after clearing my screen， let's do like 10 of these。 and it gets bigger。

 Let's do like 50 of these。 And it gets even bigger， doesn't even fit on the screen。 But it works。

 And that's an iterative approach 100% correct。And similar to what you might have done already for something like week zero or week1。

 But it turns out if we leverage recursion， we can be a little more clever， in fact。

 let me go ahead and do this。 let me minimize my terminal window。

 Let me go back into my code here and let me propose to implement the exact same program recursively instead and let me go ahead and。

😡，Do this I'm going to leave main let's see exactly as is。

 and I'm going to go ahead and change my draw function to work as follows let me delete all of these loops because loops are sort of an indication of using iteration and I'm instead going to do this what is a pyramid of height4。

😡，I said it's a pyramid of height 3 plus one more row。

 so let's take that literally if a pyramid of height n needs to be drawn。

 let's first draw a pyramid of n minus1， and then how do I go about drawing one more row well this I can use a bit of iteration。

 but I don't need a double doubly nested loop anymore I can set I equal to0 I less than n I plus plus and this block of code is simply going to print one simple row of hashes again and again followed by a new line just to move the cursor down So notice this line here。

 and I'll add some comments， print pyramid of height n minus-1。😡，Print one more row。

 so I'm kind of taking a bite out of the problem by printing one row。

 but I'm deferring too weirdly myself to print the rest of the pyramid。

 Now I'm going to go ahead and try compiling this， make oh and this is no longer iteration So I'm actually going to do this code recursion do C。

 I'm going to paste that same code into this new version just so we have a different file without breaking the old one and now I'm going to do make recursion。

😡，All right， interesting。 So clang is yelling at me with this error。

 All paths through this function will call itself。 So Kang is actually smart enough to notice in my code that no matter what the draw function is going to call the draw function and the draw function is going to call the draw function。

 and the draw function is going to call the draw function。 Now to be fair。

 and the input to draw is getting smaller and smaller。

 But what's going to happen eventually to the input of draw， as I've written this code right now。😡。

Yeah， and back。Exactly， remember that integers are signed by default。

 They can be both positive or0 or negative。 And so here， if I just keep blindly subtracting one。

 it's gonna to do that seemingly forever until I technically underflow。

 but that's gonna be like 2 billion rows of pyramids later。

 So I think what I actually need to do is something like this。 I need to ask the question。

 if n equals0 or heck， just to be super safe。 let's say if n is less than or equal to0。

 just to make sure it never goes negative， let's just go ahead and return without doing anything。

 So I'm gonna comment this as like if nothing to draw， Well then don't blindly call draw again。

 So this is that so-called base case。 This is analogous to saying if John Harvard not in phone book or if no lockers or doors left then just exit or return in this case。

 So now I'll never call draw a negative number of times or zero number of times。

 I will only do it so long as n is positive。 So now if I make my terminal。😡，Make recursion again。

 does compile fine dotlash recursion。 Let's do the same input for。

 and I get the exact same number of bricks。 Let's go ahead and do it again with maybe 10。

 that seems to work。 let's do it again with 50。 that seems to work too。 And I can go a little crazy。

 I can do like 5000。 This is still gonna work。 It's just not gonna fit on my screen。

 but it is doing a valt attempt to print all of those out。 Now。

 it turns out that could get us in trouble if we start poking around in maybe not 5000 but 500000 or 5 million or beyond。

 But for now， we assume that this is just a slow process at that。 But if we go back to the goal。

 which was to print this thing here。 this too is a recursive structure that we're just now translating the ideas of recursive code too。

 And actually， if you've never discovered this， we would be remiss and not doing this for you。

 if I go into a browser here。 and suppose that I'm not using any AI fancy technology。

 I'm just go into Google com。 And I search for。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_22.png)

cursion because I'm curious to see what it means。 Google for years。

 has had this little Easter egg for computer scientists。It's not a typo。Get it。

 Ha ha kindnd of funny。 Yeah， okay， like， see recursion。 So if you click recursion that okay。

 now we're night mode for some reason， but okay， like。😊。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_24.png)

So it just does this endlessly。 Okay， so programmers with too much free time or too much control over Google's own servers to do that。

 So it turns out， yes， if you search for recursion on Google。

 this is a longstanding Easter egg in this case。 But the point of introducing recursion is that one。

 it's actually gonna be a very powerful problem solving technique because honestly， it one。

 we've seen in pseudocode already kind of tightens up the amount of code or the amount of lines that you need to write to convey an algorithm。

 And  two， it will actually allow us to solve problems in a fundamentally different way by using computers memory in an interesting way。

 And so toward that end， we wanted to introduce one final sort today。

 which we won't use humans to demonstrate， but just numbers instead。

 namely something called merge sort and merge sort is an algorithm for sorting n numbers that I claim is gonna be better than selection sort and bubble sort。

 It's got to be better because that n squared was killing us。

 We want to get something lower than n squared。 So merge sorts。

 pseudocode essentially looks like this。 And this is it merge sort says if you've got N。😊。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_26.png)

Numbers or an array of numbers。 sort the left half of them。 sort the right half of them。

 and then merge the sorted haveves。 And we'll see what this means in just a moment。

 But if there's only one number， just quit。 So this is my base case because this is recursive。

 because if this is a sorting algorithm called merge sort。

 I'm kind of cheating by using the verb sort in the sorting algorithm。

 But that just makes it recursive。 It doesn't make it wrong。

 So what do I mean by merging just to make this clear here among these numbers are two lists of size 4。

 And I'm gonna scooch them over to the left and the right。

 just to make clear that on the left is one half that is sorted 1，3，4。

6 from smallest to largest on the right is a second half that's also sorted 0，2，5，7。

 So for the sake of discussion， suppose that I'm partway through this algorithm called merge sort and I've sorted the left half already clearly I've sorted the right half already clearly now I need to merge the sorted haveves。

 What do we mean by that， Well， that means to essentially。

Conceptually point your left hand at the first at the left half。

 point your right hand at the right half and then decide which of these numbers should come first in order to merge or kind of stitch these two lists together in sorted order。

 Well， which is smaller， obviously zero So that last step merge sorted hs would have me take this number and put it in an extra empty array up here。

 Now I move my right hand to the next number in the right half。 and I compare the one in the two。

 Obviously one comes next。 So I put this now up here。 Now I compare the three in the two。

 Obviously the two comes next。 and so I put this up here，3 and5， obviously three。😡，4 and 5。

 obviously，4。Six and five， obviously five。And6 and 7， obviously 6。

 And I didn't leave quite enough room for7， perhaps and lastly 7。

 So that's all we mean by merging two lists together。 if they're already sorted。

 you just kind of stitch them together by plucking from one or the other。

 the next number that you actually want。 And that's it。

 And even though I picked up heart way through this algorithm。

 those three steps alone would seem to work so long as you can sort the left half and sort the right half。

 you can surely then merge the sorted halves。 Now I'll go ahead and do this digitally rather than use the physical numbers because clearly it's a little involved moving them up and down。

 But this rack here， this shelving essentially represents one array with maybe a second array here。

 And heck， if I really want a third and a fourth array。

 It turns out that with selection sort in bubble sort。

 we've really been tying our hands because I only allowed myself a constant amount of memory。

 just one variable in my head， for instance， with selection sort。

 that let me keep track of who was the smallest element。 And when we did bubble sort。

 the only number I kept in mind was I like I and I plus one。 I didn't allow myself。Additional memory。

 but it turns out in programming and N Cs， you can trade off one resource for another。

 So if you want to spend less time solving a problem， you've got to throw space at it。

 You've got to spend more space， spend more money in order to give yourself more space to reduce your time conversely if you're fine with things being slow in terms of time。

 then you can get away with very little space。 So it's kind of like this balance whereby you have to decide which is more important to you。

 which is more expensive for you or the like。 So let's go ahead then and consider exactly this algorithm as follows。

 So suppose that these are the numbers in question， So here is our array。 It's clearly unsorted。

 I'd like to sort this。 I could use selection sort。

 but selection sort was not great because it's big O of n squared and it's omega of n squared。

 So sort of damned if you do damned if you don't bubblebble sort was a little better。

 It was still big O of n squared。 but sometimes we could get lucky and shave some time off。

 So it was mega。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_28.png)

Only N。 Let's see if merge sort is fundamentally better and let's do so by trying to reduce the number of comparisons。

 No more looping back and forth and back and forth and back and forth endlessly。

 So here's how we can draw inspiration from the idea of recursion and divide and conquer as per week 0。

 Let's first think of these numbers as indeed in an array contiguously from left to right。

 Let's then go ahead and sort the left half。 because again。

 the pseudocode that you have to remember throughout this whole algorithm has just real three real steps。

 sort the left half。 sort the right half merge the sorted halfs。

 And then this is sort of a one off thing。 but it's important。 But this is the juicy part。 left half。

 sort right half merge the sorted half。 So if we go back to this array on the top shelf。

 Here's the original array。 Let's go ahead and sort the left half。

 And I'm gonna do so by sort of stealing some more memory。

 So I can sort of work on a second shelf with just these numbers。 So 6，3，4。

1 is now an array of size 4， essentially， how do I sort an array of size 4。 Well。

 I've got an algorithm for that。😊，Seelection sort。 But we decided that's slow。 bubble sort。

 that's slow。 Wait a minute。 I'm in the middle of defining merge sort。

 Let's recursively use the same algorithm by just sorting the left half of the left half。

 So if you've got an array of size 4， It's only three steps to solve it。 So left half。

 sort right half merge。 So let's do that。 Let's sort the left half。 Okay， wait a minute。

 How do you sort an array of size 2。 I've got an algorithm for that。 So the left half。

 sort the right half merge that you have。 Alright， let's sort the left half。😊，What now。

 So six is a list of size1。 What was that special base case then？😡，So if it's quit or just return。

 like I'm already done。 So this list of size1 is sort of weirdly already sorted。

 So I'm making progress。 Meanwhile， what's the next step after sorting this left half。

 sort the right half。😡，Done， this is already sorted， but here's the magic。

 what's the third step for these numbers？😡，Merge them。

 So this is like the left hand right hand thing。 Which one comes first， Obviously，3。 and then 6。

 And now we are making progress， because now the list of size 2 is sorted。 So what have I just done。

 I've just finished sorting the left half of the left half。 So after I've sorted the left half。

 what comes next if you rewind in time。Sort the right half of that left half。

 So now I take the right half and how do I sort this right half of size 2。 Well'。

 sort its left half done， sort its right half， done now， merge them together。 And obviously。

 the one comes first then the four。 Now， where are we。

 We're at the point in the story where we have a left left half sorted and a right left half sorted。

😡，So what comes next now narratively？😡，Merge the two together。 So left hand right hand， so one。😡，3，4。

6。 And where are we now in the story， We're sort of at the beginning because I've now sorted the left half。

 And you recall the demo I did physically。 This is how I had the left half was already sorted on the second shelf。

 But now that I've sorted the left half of the original array， What's the original second step。

Sort the right half。 So it's the same idea。 So I'm borrowing some extra memory here。

 And now I've got an array of size 4。 How do I sort an array of size 4， sort the left half。 Allright。

 how do I sort an array of size 2， sort the left half done， sort the right half done。

 Now what merged the two together。 And of course， it's two and 5。 Now， what do I do。

 I've sorted the left half of the right half。😊，So now I sort the right half of the right half。

 how do I sort a list of size2， well sort the left half done， sort the right half done。

 merge them together0 and7， where am I in the story。

 I've sorted the left half and the right half of the original right half。

 so I merge these two together，0 and then two and then five and then7。😡。

where are we we're at exactly the point in the story where we had the numbers originally on the second shelf。

 we had a list that' sorted on the left， a list that sorted on the right。

 and what I demoed physically was emerging those two together， so what happens now，0，1，2，3，4，5，6。

 seven。😡，And it seemed kind of magical and kind of weird。 in that I kind of cheated。

 And when I had these leaves， these leaf nodes。 So to speak these singletons， I was like sorted。

 I wasn't really doing anything， but it's that merging that seems to really be doing the magic of sorting things for us。

😊。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_30.png)

So that felt like a mouthful and recursion in general is the kind of thing that will like bend your brain a little bit。

 And if it went over your head like that's fine， it takes time and time and time and practice。

 but what there was not a lot of with this algorithm was again and again and again and again I was kind of only doing things once and then once I fixed a number I moved on to the next and that's sort of the essence of this algorithm here。

 if it helps you to see it in another visual way， let me go back to our previous visualization here。

 let me reranomize the array and click merge sort and this time notice that mergech sort is using more space。

 technically I was using one， two， three shelves but you can actually be slightly more intelligent about it and actually just go back and forth and back and forth between two shelves just to save a little space so you're still using twice as much space but you don't need four times as much space as the diagrams or as the shelves might imply。

 So here is merge sort。😡，And you'll notice that we're sort of working in haveve。

 sometimes big halves， sometimes smaller halves。 But you can see as the two halves are merged。

 things seem to happen very quickly。 And so notice that this is the same number of bars as before。

 But that was way faster。 I don't need to stall nearly as much as I have in the past。 So。

 so why is that。 Well， if we go back to the diagram in question。

 Here's the list thats here's the array that's already sorted。

 And if we consider now exactly how much work is done。 I'll stipulate already。 It's not n squared。

 n squared was slow。 and merge sort is actually much better than that。

 let's see how much better it is。 So here is the original list 6，3，4，1，5，2，7，0。

 And here are all of the remnants of that algorithm。 All of the states that we were in at some point。

 sort of leaving a whole bunch of breadcrumbs。😊。

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_32.png)

How many pieces of work did I do？ Well， like 1，2，3，4，5，6，7，8，9，10，1112，1314，1516，1718，192021 to a2。

23，24。 So I move things around like 24 times it seems。 And how do I actually reason about that。

 Well these are the numbers。 This is like my temporary workspace here。 and 24 is the literal number。

 But let's see if we can't do things a little more generically log base 2 of n recall is what refers to anything that we're doing in half dividing dividing dividing。

 And that's kind of what I was doing here， I took a list of size 8 divided into two of size 4。

 Then four of size 2， then 8 of size 1。 Well， how many times can you do this。

 if you start with8 numbers。 Well， that's log base 2 of8。 And if we do some fancy math。

 That's just log base2 of2 to the third， and remember the base and the number here can cancel out。

 So that's actually3。 So log base 2 of8 is 3， which means that's how many times you can divide a problem of size 8。

In half in half in half。 But every time we did that per this chart。

 I had to take the numbers and merge them together， merge them together， merge them together。

 And so on every row of this postmortem of the algorithm。 There are n steps， N steps， N steps。

 So laterally， there's n steps， because I had to merge all of those things back together。

 But what is the height of these yellow remnants。 Well， it's 3， which is log base 2 of 8， which is 3。

 So this is technically three times 8 Er go 24 steps。 But more generally， this is。

Log N height and end with。 so to speak。 So the total running time I claim is actually n log N。

 which it's okay。 if that doesn't quite gel immediately in your mind。

 especially if you're rusty on algorithms。 But and we can throw away the base because that's just a constant factor。

 And with a wave of our hand when we talk about big O notation。

 merge short I claim is in big O of n log N。 That is n times log N。Unfortunately。

 it is also in omega of n log n， which means that frankly， bubble sort might sometimes outperform it。

 at least when the inputs are already sorted or certainly relatively small。

 but that's probably okay because in general， data that we're sorting probably isn't very sorted。

 and honestly， we could even hack merge sort to just do one pass to check initially is the whole thing sorted and then maybe terminate early。

 so we can maybe massage the algorithm a little better to be a little smarter。

 but fundamentally merge sort is in theta of。😡，N log N is how you would say it。

 It's on the order of n times log n steps。 Now， in terms of that chart。

 it's strictly higher than linear， but it's strictly lower than quadratic and and n squared respectively。

 So it clearly seems to be faster。 So it's not as good as linear search。

 And it's definitely not as good as binary search， but it's way better than selection sort or bubble sort actually were。

 So with that said， we thought we'd conclude by showing you a final film that's just about a minute long that compares these actual algorithms。

 And shows them as follows。 you'll see on the top the middle and the bottom。

 three different algorithms。 on the top， you will see selection sort on the bottom。

 you will see bubble sort。 And in the middle， you will see and here an appreciation of what n log N is Aka A merge sort today。

 So if we could dim the lights dramatically。 This is n log n Vi V N squared。😊。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_34.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_35.png)

![](img/9f210938af1c9a3b9a31ef4bb439ac2a_36.png)

All right， that's it for CS50， we'll see you next time。



![](img/9f210938af1c9a3b9a31ef4bb439ac2a_38.png)