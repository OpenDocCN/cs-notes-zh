# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P5：CS50 Fall 2025 - Lecture 4 - Memory .cut.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

Alright， this is CS S 50， and this is week 4， the week in which we take off the proverbial training wheels that have been the CS 50 library and reveal to you all the more what's going on underneath the hood of a computer in terms of its memory。

 we'll also talk about files and how you can actually persist information for a long time。

 whether it's a file you've downloaded or today that you've created yourself， But first。

 I just wanted to share some artwork that two of your classmates。

 Avery and Marie kindly made before class， which is a picture made out of postit notes， some green。

 some purple， which collectively from where you are， looks like what。😊，Yeah， so indeed。

 it's a cat that they made using only zeros in ones or green and purple pieces。 And， in fact。

 even though this is fairly low resolution in that。

 it only has a few pixels this way and a few pixels this way。

 It's actually representative of how computers do actually store。😊，Images underneath the hood。

 So let's actually start there。 In fact， if we've had this bowl of stress balls for some time here on the lectern。

 And if we take a beautiful photo of it， they look a little something like this。 Of course。

 this too is a finite resolution。 And by resolution。

 I just mean how many dots go horizontally and how many dots go vertically multiply those two together and you get some number of bytes。

 maybe in kilobytes， megabytes or heck。 if it's a massive image， you could be even bigger than that。

 But it is， in fact， finite。 And if we zoom in on this image， you start to see a little more detail。

 But at the same time， if you keep zooming in， you start to see， indeed。

 that there's only finite detail。 And when we go really zoomed in。

 you start to see actual dots or pixels as they're called。 In fact， any screen。

 any image you look at if you look close enough by pulling your phone up to your eyes or walking really close to a TV。

 you may very well see the same thing， because any image on a screen like this is represented by hundreds。

 thousands， millions of tiny little dots called pixels。

 And each of those pixels has a color that gives it collect。😊。

The appearance of stress balls in this case or cats in this case。 So， in fact。

 among the things we're going to do this week in the problems is actually have you write code via which you can manipulate your own images。

 not only to understand what's going on underneath the hood。

 But to apply some of today's most familiar filters， so to speak。 In fact。

 if we go all the way down here， you'll see that this image， of course， is multiple colors。

 weve got some white and some red and shades in between。

 but let's keep things simple for a moment and propose that instead of looking at these dots。

 we look at these zeros and ones。 And let me propose that in a picture like this。

 any0 will be interpreted as black， any one will be interpreted as white accordingly。

 if you can see it。What is this a picture of？O， smiley face is， in fact。

 right because if you kind of focus only on the zeros and try to ignore those ones。

 as I can do here for you， you'll see that embedded in that image was， in fact， this smiley face。

 Now， this would be a sort of1 bit image。 you either have a0 or1 representing each of the colors in modern times。

 we would actually use 16 B per color，24 B for color， maybe even more。

 And that's how we can get every color of the rainbow instead of just something black and white。

 But in effect， what's happening here。 is that if you did have a file on your Mac or PC or phone Storing this pattern of zeros and ones。

 And you opened it up in some kind of image program or like the photos app。

 it would be depicted to you visually as this， simply a grid X and Y where some of the dots are white。

 some of the docs dots are black。😊，Alright， so with that said， how， what kinds of。

Representations might be involved here。 Well we can actually rewind to week 0。

 recall that we talk briefly about RGB， which just means red， green and blue。

 which is one of the most common ways to represent colors inside of a computer。

 And if any of you have ever dabbled with Photoshop or similar editing programs or if maybe in high school earlier。

 you made your own web pages。 odds are you're actually familiar with a syntax we're gonna see a lot of today。

 This doesn't add anything intellectually new it's just an introduction to a common convention for how else we can represent numbers。

 So this is screenshot of Photoshops， color picker。

 Photoshopping a popular program for editing photos and files。

 And you'll see here that my selected color looks to the human eye as black。

 And I've highlighted here how I got that。 I chose black by typing in 0，0，0，0，0，0。 which also。

 if you look up here means that I want 0 red，0， green and 0 blue。

 And yet we somehow translated it to  six zeros instead of just three。 Well。

 if we take a look at another color like white instead。😊。

Claimed that you can represent white in Photoshop and today in code with F F F F FF or equivalently255 red。

255 green，255 blue。 And here， if you think back to week0s。

 maybe a hint at where we're going with this。 if you're using an 8 bit number。

 which mean then you can count from 0 on up to 255。 So recall that 255 is like the biggest number。

 you can represent with just 8 bit。 And yet， somehow。

 there's gonna to be a relationship between the 2，55s and these fs that we see down here。

 Let's just run through a few more。 If we wanted to represent something like red。

 we're gonna use F F 0，0，0，0。 If we want to represent green。 We're gonna use 0，0， F F 0，0。

 And lastly to represent blue， we're going use 0，0，0，0 FF。 So what's going on here。

 And why do we have just this different convention。 Well， turns out in the context of images。

 And also memory in general， it's just human convention or programmer convention to use this alternate representation of numbers。

The so- calledled decimal system， but another one that's not all that far off from what we've been doing over the past few weeks。

 So here again was the binary system。 You've got just two digits in your vocabulary，0 and1。

 Here's the familiar decimal system where you've got 10 instead，0 through 9。

 suppose we wanted a few more digits。 Well， we're sort of out of Arabic numerals here。

 But I could toss into the mix like A B D E and F either in lowercase or uppercase。 And in fact。

 that's what computer scientists do when they want to have more than just 10 digits available to them。

 But as many as 16 digits available。 And in fact， when you want to use this many digits。

 you call it hexa decimal， implying that you've got 16 digits， Aka base 16。

 Now this there's an infinite number of base systems， we could do base 3， base 4， base 15。

 base 17 on up。 But this is just one of the relatively few conventions that are popular in computing。

 And let's just teas at a apart because we're gonna see these kinds of numbers a lot。 Well。

 thankfully， like in week 0， it's the same old number system。😊。

Whi you're familiar with the columns and the placeholders。

 it's just the bases in those columns mean a little something different。

 So instead of using powers of  two or powers of 10， we're gonna to today use powers of 16。

 So 16 to the0 of course， is 1，16 to the first power is 16。 So we have the one's column。

 the 16s column and so forth。 Meanwhile， if we wanted to therefore start counting in hexadeadecimal。

 This two digit number in hexadecimal is， of course。

 the number you and I know in decimmal as 0 because it's still just 16 times 0 plus 1 times 0。

 This in hexadeadecimal is how you would represent1 but you would say 0。

1 or 01 instead of just1 to make clear there's two digits。 This would be 0，20304，0，5，6，7，8。

9 Now things get a little interesting。 in the decimal world。

 we're about to carry the1 and give ourselves  two digits 1 and 0。 But in hexadecimal。

 you can keep going。 So the next number in hexadeadecial is going be 0 A 0。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_1.png)

0， C，0， D，0， E，0， F， and now things get interesting again。 what probably comes after 0 F。

 even if you've never seen hex before。So 1，0， you still still carry the one as before。

 This goes back to 0。 And why is this now appropriate。 Well， how many digits did we just。

 how many numbers did we just count through， Well， we started at 0，0， We went up through 0 F。

 And that's a total of 16 combination。 So the highest we counted。 Let me rewind。 This number here。

 of course， is going be one times F。But what is F， Well， let's rewind further， In fact。

 let's have our little cheat sheet here。 If we want to have these digits at our disposal。

 I dare say that 0，1，2，3，4，5，6，7，8，9，10，111213，1415。 So F is just gonna represent the number 15。

 So if we now fast forward back to where we were just counting from 0 on up through 0。

 a through 0 f we land here， This， of course， is 16 times 0，1 times f， which is one times 15。

 So this is how in hexadeadeimmal， you would represent the number 15。

 This in hexadeimal is how you would represent the number 16。 instead 15 to 16。 This is not 10。

 That's how you would pronounce it in decimmal。 This is 1，0 in hexadecimal。

 because 16 times 1 plus 1 times 0 gives us， of course，16。 Now we could do this toward infinity。

 but we won't1，2，1，3， dot dot dot all the way up to F。 So quick mental math，16 times F。

 that is to say。16 times 15 plus 1 times 15 is any guesses。It is， in fact，255。

 You don't even have to do the math because if you just think about where we were going with this。

 Indeed， we saw pairs of Fs in the Photoshop screenshots。

 because this is how a computer would represent the number you and I know in decimal is 255。

 by just using two f。 Now， why， like why are we jumping through these hoops and doing some additional mental math Well。

 it's just convenient for the following reason here again is the math we've been doing 16 times F plus1 times F aka 16 times 15 plus 1 times 15。

 which gives us 2，40 as some of you did in your heads a moment ago， plus 15 gives us indeed 255。

 But indeed， why is this useful。 Well， just aesthetically。

 let me separate these two digits a little bit。 And then consider for the moment。

 how you represent 15 Aka F in binary。 So how do you represent 15 in binary。

 Well I've got the one's place， the two's place， the fours place and the8s place。

 And I am doing this in my head。 But I think that just gives me1，1，1。

1 because we've got one times 8 plus 1 times。sorry。

8 times 1 plus 4 times 1 plus 2 times 1 plus 1 times 1 gives me， I hope， indeed，15。 So 1，1，1。

1 in binary equals。sorry， equals 15，1，1，1，1 in binary give equals 15。 But if you now。

 I messed this up， sorry。Let me rewind and say this a little more intelligently。

So why do we care about hexadecimal。 Well， it turns out that it's just convenient to use two hexadeadecimal digits to represent numbers because a single hexadecimal digit can be used to represent4 Bs at once。

 For instance， let me go ahead and explode this by putting a little bit of space between the two digits here。

 And let's consider how you would represent F。 Well， if F is 15。

 and you want to represent 15 in binary， I think that's just going be 1，1，1，1。 Now why is that， Well。

1 in the8s place plus  one in the forest place plus1 in the twos place plus1 in the ones place indeed gives me 15。

 So using a single f， I can count up as we've seen already as high as 15。 But of course。

 I've claimed in the past that it's super common to use 8 Bs at a time or one by to represent any value because that's just a very useful common unit of measure。

 And so in hexadeadecimal。 if you want to represent 41s， you can say F。

 if you want to represent another four1s， you can just say F which。

To say that F and f together is just like the same as81s together。

 which is how we finally get to the total number of 255 because this is the ones place。

 the two's place， the fours place， the816，32，64，128。

 But if you group these into clusters of 4 Bs alone。

 you can represent all of the possibilities from 0 through 15， just using 0 through F。

 So with one hex digit， you can represent 4 bit。 which is a long way of saying is it's just convenient for that reason。

 which is why the world tends to use hex when talking about colors。 and as we'll see memory as well。

 So， in fact， let's consider what is meant by memory and what's going on inside of the computer。

 when we've been storing values thus far。 Well， here's that canvas of memory。

 I propose last time I propose last time and before。

 that we can sort of number these bytes arbitrarily but reasonably this is by 0，1，2，3，4，5，6。

7 dot dot dot。 and maybe this is byte 15。 That's fine。 nothing wrong with that。

 But in the real world， any。

![](img/272dfdb65ad4ae9b6c395f4647e726f9_3.png)

Grammar would actually think of these locations instead， not in decimal notation。

 but in hexadeimmal notation， just because it's convenient for the reasons discussed。

 So we would actually number these from 0 on up through 9 and then keep going with A， B， C， D， E， F。

And so forth。So what does that mean for the other digits。 Well， this would be 10。 This would be 1，1。

 This would be 1，2 dot dot dot here now is 19， but here's 1 a，1 B，1 c，1 d，1 E1 f， and so forth。

 just using hexadeadecimal notation， But there's arguably some ambiguity here。 For instance。

 if you just at a glance where to look at this board and see this address10。

 is that by 10 or is that by 16。 It's just not obvious because if you don't know what base system you're working in。

 which you could infer by looking at the rest of it。

 it could potentially be ambiguous So in the world of hexadeadecimal。

 super common to literally prefix any number you ever write in hexadecimal notation， using0 x。

 the0 doesn't mean anything per se or the x， it just means what follows the0 x is a number in hexadeadecimal notation。

 which makes unambiguous the fact that this is O x10。

 which if you do the math and deccimal again ends up being 16， not of course， the number 10。

 In short， today you're about to see。A of0 xs and a lot of two digit or four digit or8 digit numbers in hexademal notation。

 General， we don't care what the numbers translate to。 You don't need to do a lot of math。

 but it's gonna be commonplace to see syntax like this。 Allright， back to sort of normal time。

 So here is a line of code int n equals 50 where in me want to declare a variable called n in store a number like 50 in it。

 Let's actually go ahead and do this simple now is it probably is in a file called how about a dot C。

 We're going play around with computer addresses。 And it addresses do C。

 I'm going do something super simple at first。 whereby I'm going include standard I O dot H。

 Then I'm going go ahead and int main void no command line arguments here。

 And then I'm going declare this variable N said it equal to the arbitrary but familiar value of 50。

 And then just so that this program does something mildly useful。

 Let's go ahead and print out with percent I and a backlash N。 that value of N。 So nothing new here。

 I'm just literally going through the motions。

![](img/272dfdb65ad4ae9b6c395f4647e726f9_5.png)

Declaring a variable and printing its value。 So let's do that。

 make addresses enter dot slash addresses。 And hopefully I'll indeed see the number 50。

 So not all that much going on in the code。 but let's consider what's going on in the computer's memory。

 This line of code and the one after it is giving the results of that program。

 But where is that N ending up。 Well， here's my grid of memory。

 And let's just suppose for the sake of discussion that the 50 ends up down here。

 Maybe there's other things going on in my program。

 So this part of my computer's memory is already in use。

 So it's reasonable that it could end up in this location here。

 But what is important is that how many bytes am I using for N。 apparentlypparently。😊，4。

 and that's because we've said integers tend to be 4 by， a 32 B。 So this is at least to scale。

 even though I'm just imagining where it ends up in memory。 So that's where the 50 actually ends up。

 So when I actually call printf and pass in N clearly the computer is going to that location in memory and actually printing out that value。

 but that value is indeed at a specific memory address。

 It's not going be quite as simple as O x0 or O x1 or a small number， typically。

 it' maybe is gonna to be something arbitrary like O x 1，2，3， where I'm just making this up。

 it's an easily pronounceable number in hexadecimal notation。 Allright。

 So what can I use that information for。 Well， thus far， this hasn't been useful to us。

 but certainly programs we've been writing have actually been making use of this。

 but with a bit more syntax， I can actually start to see things like this， not just on the screen。

 But in code， In fact， let me propose that we introduce to new operators in C。😊。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_7.png)

Two new pieces of syntax， one is a single ampersand and one is a single asterisk and we'll see that the asterisk has a few different uses。

 but the ampersand has a very simple straightforward one。

 which is to just get the address of a variable in memory。

 So if you've got a variable like n if you prefix it with ampersand n you can actually ask the computer at what address is this variable store。

 you can find out if it's indeed O x1，2，3 or something else altogether。 So in fact。

 let me go ahead and do this by going back to my address do C program and let's see if we can print out not the value。

 which is obviously going be 50。 but let's actually print out the address thereof。

 So up here in my code I'm going to change the n online line 6 to be ampersand N instead and I'm going to go ahead and make one other change because yes。

 N lives at an address and yes that address is technically a number but it's conventional not to use percent I to display that number but rather。

Another piece of syntax， which is just a new format code， which you don't often need。

 This is more demonstrative than useful， I would say。

 but percent P is going to be what we use when we want to print out an address of something in the computers memory So back to the code one more change。

 I'm going change my percent I to percent P instead So at this moment we should see a version of the program that's not going to display 50 anymore。

 but something like Ox 12，3 but probably a bigger number than that because my computer has way more memory than that address suggests。

 So let's again make addresses let's run dot slash addresses and indeed this variable at that moment in time。

 apparently lives somewhere in the computer's memory at address Ox7D3 c34 Ecc all of those are hexadecimal digits。

 it would be painful to do the mental math to figure out what the numeric address is but we're seeing it indeed in this common hexadecimal notation。

 which is not going to be often useful for us as humans but the computer is and has been using。

This information for some time。 So， in fact， what we're about to introduce is admittedly one of the more complicated concepts in computing and in C in particular。

 namely a topic called pointers。 And I will say today more so than ever。

 might feel like a bit of a fire hose。 In fact， all these years later。

 I still remember the day in which I finally understood this topic。

 which was not the day of the lecture in which I was introduced。

 but it was in like the backright corner of the Elliott House dining hall。

 I was sitting down during office hours with my teaching fellow。

 and he finally helped that light bulb go off over my head。

 So if some of this feels a little arcane today， it just comes with time and with practice like everything else。

 So what is a pointer， a pointer is going to be a variable that can store in a address。 Now， yes。

 that address is technically just a number like an integer。

 but we distinguish between integers that we care about like 50 and things we might do math on。

 And a pointer which in this case is just going to be the address of a variable the address of a value in memory。

 So what does this mean。😊，Well， we can start to do things like this。

 I can declare my variable n as before and set it equal to the value 50。

 but I can actually get the address of n and put that address in another variable and that variable we now call a pointer So P is going to be the name of this variable。

 it's going to store the address of n， which we can get using the ampers sand。

 but there's one more piece of syntax which I promised before。

 this asterisk here and the asterisk here means that this variable P stores the address of an integer not an actual integer per se。

 it's weird looking syntax。 it kind of looks like multiplication， but it isn't。

 it's just the developers of C decades ago decided to use an asterisk。

 even though it's admittedly non-obvious what it's doing。

 but in this context when you see an asterisk right after a data type like int it just means that the variable in question is not going to be an int per se。

 but an address of an integer。Okay， so let's put this to the test using a line of this code in my own file here。

 Let me propose that we do this。 Let me go back to V。 S code here。

Let me introduce this additional variable。 int star P， as it's typically pronounced。

 set that equal to ampersand N。 and then do the exact same thing as before。

 Let's not print out ampersand N。 But let's actually print out the value of P itself because P is now equivalent to ampersand N。

 So let me go back to V S code。 Let me do make addresses again。And。

 I did something wrong and stupid here。 This was not meant to be the moral of the story。

What did I do wrong， yeah。Yeah， I just missed the semicolonlon so still making those mistakes here。

 All right， normally me clear my screen again and do make addresses enter dot slash addresses。

 And now I should indeed see the address of n。 I just so happened to temporarily store this time inside of a variable called P。

 Now， just so you've seen it。 it turns out that when using this syntax of using a star to declare a socalled pointer and ampersand over here to get the address of something。

 you might see an online references in such different formattings of this。

 This is the canonical way to declare a pointer int space， then the star， then without a space。

 the name of the variable。 However， it will work。 and you will sometimes see that the star is over here or the star is in the middle。

 But again， we would recommend stylistically that it just go here。 admittedly。

 I think it would been clean clearer if the star were over here。

 making clear that it's related more to the int than it is to the variable name。

 but this is simply the convention。 So this means hey， computer give me a variable called P。😊。

That's going to store the address of an integer。 And the am person saying is just saying， hey。

 computer， tell me the address of N。 and it's the compiler and computer itself that decided where to put that variable in memory。

😡，Questions。Would you get an error if you didn't put the asterisk， You would。 And let's take a look。

 So let me go ahead and clear my terminal。 Let's go ahead and delete the star there。Oh。

 let me go ahead and clear my terminal。 Let me go ahead and delete the star before the variable P。

 Now， let me go ahead and do make addresses again。 And indeed。

 I'm getting an error incompatible pointer to integer conversion initializing in dot dot dot。

 And even though that's a lot of big words， it kind of says what it means。

 you're trying to go from a pointer on the right to an integer on the left。

 which is just not appropriate here。 Yes， at the end of the day， they're all numbers。

 but it's more properly， a pointer or an address on the right。

 but a little old int now incorrectly on the left。 So the fix there is just to indeed put it back。

Other questions on this new syntax， yeah。Indeed， to recap the question。

 can you use the address of operator to find the address of other data types like strings。

 Absolutely， And we'll do that with a couple of examples today as well。

 We're just using ins to keep it super simple I。 Other questions on these addresses and pointers。

Correct， correct。 Even if it's not an anton question。

 we'll come back to other data types in a little bit。 You're still gonna to use the star。

 That is the same syntax for everything。And， yes。交的。Oh， yes。

 Can you tell the computer you want to store a variable in this address。

 That's where we're going in just a bit。 Indeed， now that we have the ability to find out the address of something in memory stands to reason that we can go to that address ourselves and maybe poke around and actually put values there。

 And in fact， thats that's among our goals for today。 So let's consider how we might get there。

 So here now is my canvas of memory。 And let me propose that the number 50 happened to get stored in the variable n down there at bottom right。

 just because and that's probably O X 1，23 or in reality， a much larger address。

 but it's easier and quicker for us to just pretend it's at 0x 1，2，3。

 what is actually happening in code when I declare P and put a value there。 Well。

 recall a moment ago， I declared P to be a pointer to an integer that is the address of an integer。

 So what's happening in memory is this。 if n is down here and happens to be an address O X 1，2，3。

 when I actually assign P to。😊，Apersand N， that just literally takes that address of N and puts it inside of P。

 Now P as an aside happens to be pretty big。 It turns out by convention on most systems。

 a pointer that is a variable that stores in address is actually gonna be 8 B large。

 It's gonna be 64 B。 Why is that our computers have so much darn memory nowadays and the gigab that you need to be able to count higher than 4 billion as an aside。

 if you only used 32 B for your pointers you could only count recall as high as 4 billion。

4 billion is 4 gig equivalently that would mean your computers could not have 8 gig of memory。

16 GB of memory。 your servers couldn't have tens of gig of memory we use 64 B or 8 nowadays for pointers。

 because our computers have that much more memory。 Allright。

 So what is P storing literally just in address like this。

 So when we wrote this code just a moment ago， what the computer did and has been doing for the past several weeks is literally just finding the location of n in memory。

And plopping that value inside of P， which itself is taking up a bit of memory。

 but by convention more memory，8 bytes in this case。😡，The thing is。

 who really cares about this level of detail， typicallyy， as programmers。

 it's useful to understand what's going on， But rarely are we going to care precisely about where things are in memory。

 Today is really about just kind of looking at what's going on underneath the hood。 So， in fact。

 we can abstract away most of my computer's memory I would propose because at the moment。

 all we care about is P existing and N existing。 So who really cares what else is going on。

 And frankly， generally， I am not gonna care that N is at address O X 1，2，3。

 just that it is at an address that happens to be O X 1，2，3。

 And so the way a programmer or computer scientist when talking about design on like a whiteboard or frankly。

 in sections and office hours on a whiteboard we rarely care what the actual addresses are。

 So we generally abstract the specific address away and literally represent pointers with arrows on the screen or on the whiteboard or the like。

 This just means that P is a variable that points to。The number 50 in memory。Okay。

 questions on this mental model for what a pointer is。

 It's a pointer in like very much the literal sense。Okay， so if you're on board with that。

 let me propose that we consider now what these things look like maybe more physically。 In fact。

 we've got a couple of mailboxes here to make clear with the little metaphor that here is a physical representation of our variable say P labeled as such inside of this is presumably gonna be the address of some actual value。

 That value at the end of the story is gonna be the value of n。

 which recall for consistency as address O X 1，2，3。

 So what happens when you actually try to locate a value in memory is analogous to sort of looking up something inside of these mailbox。

 which if you think of your computer's memory as hundreds or thousands of little mailbox。

 maybe more apartment style， where you've just got rows and columns of mailbox as opposed to individual ones for single family homes。

 Each of those mailboxes can contain the address of some value in memory。 And so what's real。

Happening is that if this is P not drawn to scale because they only make mailboxes so large inside of P is gonna be an address like O X 1。

2，3。 And just to be dramatic。 since there's a big football game this weekend。

 here is a Harvard foam finger metaphorically， like this pointer is like pointing at that value over there。

 And in fact， we're gonna see， as you asked a moment ago。 Can we actually go to an address in memory。

 We don't yet have the syntax for that。 But we're about to， Yes， you can。 And， in fact。

 if I follow what I'm pointing at， open up this location in memory。😊，voila。

 there is the 50 in question。 So any time we're talking about values or we're talking about the addresses thereof。

 you can think of it analogously as being like physical mailboxes。

 one of which might contain a useful number like 50。

 one of which might contain the address of that value。

 And we now have the syntax we'll see to actually go from one to the other。 In fact。

 let's do this in the context of our old friends string。

 which I claim a couple of weeks back is one of our training wheels。

 like every programmer and computer scientists in the world knows that strings or a thing they just don't exist by that name in C。

 because that's indeed one of the little white lies we've told for a few weeks just to make life easier。

 But today， I think we no longer need that same support。

 So let me propose that we do something like this in my next program， Let's move away from integers。

 as was proposed。 and let's use something like a string instead。

 And let's just store our old friend H exclamation point。 Well， let me go back to V S code here。😊。

And in this version of my program， let me propose that we'll actually。Oh，m sorry。

Sttrike two for me today。Apologies。And。Let's see。So how do we actually convert this metaphor into actual code。

 So let me actually go back into VS code here， which in the most recent version of my program。

 what I was doing was getting the address of n and starting in in P。

 And then I was literally printing out P itself。 And that's when we saw the big hex Smal number。

 That is generally not useful， but it's maybe interesting to see that one time。

 Let me instead though， introduce another use of that star or asterisk operator that allows us。

 as was asked a moment ago to actually go to that address。 So in this version of my program。

 I'm going to keep n equal to 50。 I'm going keep P equal to the address of N。

 But what I'm now going to do is show you how syntactically， I can print out not P。But， N。

But by using P following the proverbial foam finger metaphor by printing out percent I back slash n and printing out n instead。

 Now， obviously， I could cheat and just say n and print out n like in version 1。

 But that doesn't really demonstrate anything interesting here。 However。

 if I only have P at this point in the story。 It turns out you can use the star for another purpose。

 if you simply prefix your variable name with a star。

 That is the socalled now de referenceence operator。 which means go to the address in P。

 So if I now open up my terminal here， do make addresses for this version。

 Then do dot slash addresses in enter， I now get back the number 50。

 So what's really happening in line 5， as has been true for several weeks now， we have。

A variable called N being initialized to the number 50。 Then on my next line 6。

 I'm declaring P is an address of some value and the integer specifically and putting the address of N in there exactly。

 And then on line 7， I'm actually saying， print out an integer percent I we've done for weeks。

 But what integer。 go to the address in P and print out what you find there。

 So that's equivalent again to the the foam finger， which is over there。

 pointing at the address I actually want to point， print out instead。Okay， so。Usefulness。 Well。

 I think we can get there by taking a look at one of our little white lies that we've been telling。

 In fact， let's turn our attention to strings， which up until now have been a sequence of characters in the computer's memory。

 A string is a thing in programming more generally。 But in C。

 it technically doesn't exist by this name， but you can still use strings in C。

 but just not by calling them S T R I N G as the actual data type。

 But let's let's start with our familiar code here。 Let me go into addresses dot C。

 Let me add our trading wheels in for now and include C 50 dot H。

 because in this version of my addresses program。 What I want to do is declare a string S。

 And I'm going set it equal to high exclamation point。😊，Then as we did in week1。

 let's go ahead and print out with percent S backslash n。 that value of S。 So nothing new。

 nothing interesting here。 So let me just do it quickly and do make addresses。

 then dot slash addresses。 and we see high on the string。

 So that has all been something we've been taking for granted。

 but let's consider what is going on underneath the hood of even that program。

 So the string we've declared in memory exists somewhere in the computer's canvas of memory。

 So string S equals high might end up somewhere down here。

 And I'm gonna stop drawing all of the boxes when not necessary。

 But here we have H exclamation point。 And as we discussed two weeks ago， the null character and U。

 which just means the string stops here。 So as a quick refresher。

 even though the word is three characters， it takes up how many bytes4 always。

 because you need that null terminator。 Allright， So maybe that string could be accessed then by its name S。

 and we've seen this before， S bracket 0 is the first character S bracket 12。

 And then if you want to poke around， you can go into S bracket 3， but you'll。😊。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_9.png)

See quote unquote no on the screen or the compiler will sort the computer will sort of remind you that you don't really want to look there at that point。

 So three characters accessible via this array syntax。

 But we know now that everything in the computer's memory is addressable。

 and maybe that H just so happened to end up at O X 1，2，3， And the I ends up at O X 1，2，4，1，2，5，1，2。

6， respectively， doesn't matter what these numbers are。

 But because strings or sequences of characters back to back to back in memory。

 it must be the case that these addresses are themselves contiguous back to back to back without gaps inside of them。

 That's how a string has always been stored in memory。 It's just an array of characters。 All right。

 So with that said， what really is S。 we thought of s in every program we use strings and before as just a string like that is the sequence of characters or really it's the name of an array。

 But that's a bit of a white lie， because what S really is is going to be of more。😊。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_11.png)

ific value。Take a guess。 what is actually going to be the value in S。Yeah， the address of。

 if I may that array。 So we've got like sort of four possible answers here。 A，B，C and D。

 Multi choice， Which of those numbers probably makes sense to store in the variable called S。

In order to get to this string。What is S's value？0 x 1，2，3 is correct。

 So we don't talk about this in like week 1 because like it's already hard to like remember semicoons in week1。

 like God forbid start thinking about like what these specific addresses are。 S is a string。 Yes。

 but technically S is and has been since week 1， a pointer。

 the address of an array of characters in memory。 the address specifically of the first character in memory。

 which is sufficient why because of this null terminating convention that we talked about weeks ago。

 that tells the computer where the string ends the pointer tells the computer where the string begins。

 And that's how you get using just numbers， zeros and ones inside of a computer to store something as interesting as an actual string。

 So in fact， let's let's take a closer look at this。 In fact， let me go into the S code again。

 and just for the sake of discussion。 let me declare S as before。

 But instead of printing out the whole string at once。 Let's go。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_13.png)

Go ahead and do this。 printntf quote unquote， percent P backslash N。

And then let's print out S itself initially to see whether it's actually O x 1，2。

3 or presumably a much bigger number。 Then after that， let's print out another pointer。

 another address rather percent p back slash and comma。

 And now I'd like to print out the address of the first character of S。

 But let's let's not get ahead of ourselves， Let me go ahead and make address again。

 dot slash address is okay， there now in this high program is the address at which the string itself is stored。

 O x 5， a 7，1，4，3，02，7，0，0，4 bigger than O x 1，2，3。 Well， let's now poke around。

 What if I were to do this。 What if I want to print out the address of How about the first character in that string。

 Well， at the moment， recall that S bracket 0 is literally the first character， That is a char。

 So with what syntax could I get the address of the first character。Well。

 we haven't learned all that much。 that's new today。 It's just a single ampersand。

 that will get me the address of that character。 If I do this for the next character。

 I can see one after another。 And in fact， this is gonna have four characters in total。

 including the null character。 So let me copy paste， which is generally frowned upon。

 but not for a lecture demo because we're just trying to do this quickly。

 let's print out the address of S itself。 And then more specifically。

 the address of S's first character， the address of S's second character。

 third and the address of that null terminator。😊，Alright， let's go back into make addresses。

 Let me go ahead and clear my terminal and do dot slash addresses and。We see， oh we see one， too few。

 Let me scroll up。 We see if I zoom in in my terminal here， the following。S itself contains O， X 5，6。

1，9，9，9， B， D0，0，0，4， and the address of the first character in S A K。

 A S bracket 0 is exactly the same thing。 The next character， the I in high is one B away。

 The exclamation point is one more by away。 and the null termminator is one more B away。 So again。

 bigger numbers。 But the point is， these are indeed。

 just the actual addresses of all of these characters in memory。😊，All right。

 let me pause for any questions here。Good question。

 Why do I need the ampersand before the specific characters in S， but not S itself。

 Think what S actually is。 I'm claiming for the moment that S itself is the address of that whole string。

Which just so happens by design to be equivalent to the address of the first character。

 because that is the convention humans came up with decades ago to represent a string。 Now。

 you might think that you need the address of every character in the string。 But no。

 that's why humans decades ago decided to just terminate every string in memory with the backslash 0 or null terminator。

 because if you give me the beginning of the string in the end， I can obviously with a loop。

 find everything else in between。Other questions。what we're doing here with strings。All right。 Well。

 what is then this actual thing in memory？ Well， it turns out that S is yes， a string。

 as we've been describing it。Come on，It turns out that yes， S is a string。

 as we've been describing it all this time。 but technically。

 I think we're ready to reveal what little white lie we've been telling， or if you will。

 what abstraction S actually is in the C 50 library。The type， you know， as string since week 1。

 all this time has simply been a synonym for。Char star S。This is where。

Maybe so what does this really mean， Well， we saw instar P earlier here， we're seeing char star S。

 but what does that really mean。 Well， S is the name of the variable。 And yes， it's a string。

 But what is it really， S is the address of a char。

 And so in week1 of the course in the actual CS 50 library。

 we've told this little white live by just creating a synonym in the library that makes char star。

 So to speak the exact same thing as string T R I N G just so that we don't have to think about this level of detail。

 let alone xsimal notation and addresses and pointers and dereencing in all of this complexity in the first weeks of the course。

 it's simply abstracts away what the cha what a string actually is。 And in fact。

 we've seen this technique before in a more complicated way。 In fact。

 if you recall a couple lectures last week， we actually claim that you could create a phone book。

 for instance， using persons and persons have names and numbers。

 And we created our own type by saying type de。 And that type was a whole structure。

 which is the complexity part a structure containing a name。In a number。

 and we gave that data type ultimately the keyword person。

 So we've already invented in class our own make believe data types to create things that didn't come with C itself like a person。

 Well， thestruct is very specific to what we were trying to do with the phone book。

 But typey Def is more generally useful because it literally allows you to define your own type。

 So it turns out all this time in the C50 library。 We have had a line of code that starts with Ty de followed by。

That would have been better transition。 So， for instance。

 if we wanted to create an synonym for int because we never remember what it is and call it integer instead。

 you could simply say type def int integer semicolon。

 and that would create in your programming environment。

 a data type called integer that is literally equivalent to int。 Now， this is not all that useful。

 So instead in the C50 library， we do use type def to tell the computer that cha star should instead be spelled as string。

Semicolon。 And that just means that string ever after is the same thing as saying char star。

 So all of this time since week1， I could have been doing exactly that if I wanted。 And in fact。

 if I go back to Vs code here。 let's simplify this quite a bit and go back to the very first version of the program wherein I use percent S and just print it out S is value itself。

 The string high。 Well， this， of course， is going work as always， as follows。

 it's just going to print out high on the screen， But now if I get rid of the CS50 library and try to recompile this。

 notice， we'll get an error that I think I've seen before。Here we have。

 if I scroll up to the very first line， use of undeclared identifier string。 did I mean standard in。

 and no， I don't。 And no， I didn't a couple weeks ago when I accidentally did that。

 But it the compiler does not know about the keyword string at the moment。 that's fine。

 Even if I don't have the C 50 library installed on this computer。

 I can just get rid of the word string， which is a concept。

 but not a keyword in C and just rename it to char star。 And now in my terminal window。

 I can do make addresses again， thoughtslash addresses and vo we're back in business with no C 50 training wheels whatsoever。

 because printf knows given a char star， go to that address， print， print， print。

 print until you get to the null terminator and then stop printing。

 There's a loop in there that does exactly that。Questions。

On char star or what a string actually now is。Yeah， in front。Like how does it note？Good question。

 how does printf know to keep going until it gets to the null the format code。

 because I've been using percent S， which means print a string instead of percent C。

 which means print a single character， printf C is that percent S and it was like， oh。

 I should use a loop to print out all of the characters until the null terminator。

 if I instead passed in just percent C， it would stop after a single character。Emics。Other questions。

Good question。 Why don't I dereference S in order to print it out。

 So let me try that for just a moment here。 Why do I not have to now or any week prior do star S here。

 because after all， if S is the string， I want to go to the string and print it out。 Well。

 the first answer is that printf is doing this for you。

 because it's being handed the address and it is going to the address for you。

 So that star is somewhere in printf's implementation。 But this is also incorrect conceptually。

 because yes， S is the string， but more technically today。

 S is the address of the first character in the string。

 So I really want to provide printf in this case with the address， not the specific character。

 because I want to treat it as a string， not a single character indeed。

 So I could use the percent S if I change to percent I can use star S if I change to percent C to print out the single character。

Allright， so let's play around just syntactically for just a moment here。 in V S code。

 let me propose that we still use cha star S here and then just demonstrate exactly what's going on。

 So I'll do exactly what was just s。 So I'll use percent C。

 And then I'm going go ahead and print out for now our old week two syntax treating S as an array。

 So S bracket0 S bracket1 and S bracket2。 And I'm using some copy paste just for time's sake。 This。

 of course， is not gonna do anything all that interesting， but it is gonna demonstrate that indeed。

 we have H exclamation point back to back to back in memory。

 And if I really want I could print it all on one line by getting rid of of course， those new lines。

 But what more can I do with this syntax。 Well， I could take literally the fact that S is the address of the first character in memory。

 So instead of using this array notation， which we introduced in week 2。

 I could technically go to the address of S。 why Well。

 S is the address of the first character of the string。 star S means go to that。Addres andvoila。

 you're at the first character by definition of what S is。

 so I could print out the first character using star S instead of S brackets0。😡，How could I do this？

 Well， here's where we can actually take advantage of the fact that。

Pointers and addresses more generally， are， in fact。Numbers。

 and you can actually do arithmetic on pointers themselves。 In other words。

 there is a concept known as pointer arithmetic， which means given an address， you can add to it。

 subtract to it， Heck you could even multiply or divide。

 even though that would probably be weird in most cases。

 we could certainly add numbers to an address。 So， for instance。

 if I want to print out the second character of S。 That's kind of equivalent to going to S。

But then moving over one character。 So maybe I should do a little bit of pointer arithmetic and do S plus one in parentheses just so that like in math class。

 we do order operations correctly。 And then down here， I could go to S again。 But wait a minute。

 I want to go to S plus two characters away or two Bs away。 So now I can do make addresses down here。

 And I did mess up new mistake。 unintentional。不。Yep， I forgot my parenthesis on the very end here。

 So that was just user error。 make addresses again。 dot slash addresses。

 And now I indeed see H I exclamation point one more time using pointer arithmetic instead of our familiar array notation。

 So what is that array notation。 Its what we would generally call syntactic sugar。

 which is a very weird way of saying， like it's just nicer syntax。

 Like no one wants to write code that looks like this。

 It's sort of bends the mind a little bit to read and parse all of this visually。

 just S bracket 0 is much more straightforward。 But what it's really doing is this。

 And the computer is essentially converting that bracket notation for us into this more esoteric but correct version instead。

😊，Alright， what else can I do， Well， just for fun for some definition of fun。

 Let's go ahead and print out three different strings and recall that a string is a sequence of characters that starts at some address。

 So let's first print out the sequence of characters that starts at S。

 Let's next print out the sequence of characters that starts at S plus 1。

 And let's lastly print out the string that starts at S plus 2。

 Just playing around with the definition of what these pointers are。 Let me do make addresses。😊，And。

Not my day。What do I forget。Semicolon， so if it happens to you， happens to me too， make addresses。

 dot slash addresses。 And now this one's gonna be a little curious。 but I see hi。

 I and just exclamation point。 Y， because I'm treating a string literally as what it is a sequence of characters。

 but I'm giving printf， the address of the first character initially， then of the second character。

 then of the third， But all three of those statements work。

 because all three of them happen to be terminated by the same null character。

 even though I and the exclamation point alone， was not really my intention。

 that doesn't stop me from being able to do it。 nonetheless。Alright， well， let's do one other。

 maybe application of this idea。 Let me propose that we take a look at。

Let me propose that we take a look at our computer's memory here。

 And let's suppose that we want to start comparing values， because in week1， we did a lot of that。

 And even in week 0， we did a lot of that with if and El if and else and so forth。

 So let's make this a little more real。 and also reveal why last week。

 we had to solve unexpected problem using another string function， namely St comp S T RCP。 So here。

 for instance， our two arbitrary variables in memory。 I and J And I gave them both the value of 50。

 And maybe they indeed end up there。 Each of them taking up 4 B。😊。

Last time recall that we weren't able to compare two values in memory just by using the equal equal operator unless those values last time were actually integers。

 In fact， let's do that。 Let me go back into V S code here。 close out addresses。

 and let's code up maybe another version of my compare program from last from the past。

 This time I am going to use the C 50 library just to keep things simple initially。

 I'm going include both it and the standard I O library here。

 I'm gonna give myself main with no command line arguments。 And then in main。

 I'm gonna declare exactly what we just saw on the screen。

 a variable I set to 50 a variable J sets of 50。 And then we're gonna do our old familiar syntax from week 1。

 If I equals equals J。 then let's go ahead and print out something like same backlash N else。

 let's go ahead and print out quote unquote different Backlash N。

 So super simple program that simply compares two variables that yes are obviously going to be the same。

 But let's do this。 So let's。😊，Do make compare dot s compare。 They're in fact the same。 Okay。

 so that actually works as intended。 But why didn't it work last time when we tried comparing strings。

 the solution to which was actually to introduce St comp。 Well。

 let's go back to V S code and resurrect that buggy example initially。 In fact。

 let me go into V S code here。 And instead of using say integers， let's go ahead and do this。

 and I'll rename them just by convention。 So my first string will be quote unquote。

 let's do my first string will be whatever get string gives me。 So we'll prompt the user for S。

 my next string will be called T by convention。 And I'm going ask the user for that。 then down here。

 instead of using I and J， which are common for integers， I'm just going use S and T。

 which are common for strings and just ask literally the same question as we have in the past。

 Alright， let me go ahead and do make compare。And。Thank you。 I'm an idiot。 Wow， we're strike 6 today。

 Allright， what's the error， Well， I'll show you the error message。

 What did I unintentionally do wrong here。Yeah， I'm getting a string。

 but I'm trying to store it into an in。 So this is just frowned upon。

 So let me go ahead and change that to what I should have typed the first time。

 Give me a string S and a string T。 Now， if I do make compare， we're back in business。 Alright。

 let me do dot slash compare。 And I'm gonna go ahead and type in， for instance。

 let's say hi exclamation point。 and high exclamation point， both for S and T。

 which are obviously clearly。😊，Different。Now we've tripped over this before and recall that the solution was indeed to introduce a function called St comp。

 And I explained it at a high level。 Well， that's because you're not just comparing two values。

 You gotta compare character after character after character。 And that's what indeed St comp does。

 So let's go ahead and do that。 Let me go back into this file。

 Let's go ahead and include the string library at the top here。

 And instead of doing S equals equals T， let's do if the string comparison of S and T happens to equal equals 0。

 which per the documentation for the function means they're equal instead of one before or one after the。

😊，Other， no， I did not get it wrong this time。 I caught it， yep。Is that right， No， I fixed it。

 That's all。 But I， yeah， anyhow。Yes， so how do we actually go ahead and compare the strings this time。

 Well， let me go ahead and do make compare dot slash compare and now type in exactly the same thing。

 H exclamation point， H exclamation point。 And now they're in fact the same。

 And just to demonstrate that this isn't just some flu。 I can type in high， for instance。

 and by and those are in fact， different。 So clearly， St comp is doing something useful。

 But what is it actually doing。 Well， first of all。

 let's make clear that what was a string last week is technically a char star this week。

 So I can remove that training wheel。 I'm still gonna include the C50 library。

 because as we'll see by the end of class today， get string and get in and all of those get functions from C 50 are actually still useful because it's a pain in the neck in C still to get user input without using functions like those。

 But I'm gonna get rid of the data type that we thought was called string。

 This will still work exactly as before if I do make compare dot slash compare and type in high and high。

 We're indeed seeing that they are now the same。 So what's actually going on。😊。

side of the computer's memory with strings。 Well， I would offer that S probably ends up like over here in memory。

 And then maybe it actually has its characters down here。 So notice the duality。 S， as of now。

 is an address， which means it takes up 8 B or 64 B。 But the actual characters。

 It turns out end up somewhere else in the computer's memory。

 And this is what's different about an int。 The int I and the in J both ended up exactly where the variables were named。

 But with strings， the variable itself contains not the string。

 but the address of the first character in that string。

 which I claim could end up anywhere else in the computer's memory。

 So those addresses might be O X 1，2，3，1，2，4，1，2，5， and 1，2，6， for instance。 Meanwhile。

 S is going contain literally the address of that first character。😊，When I create T in memory now。

 it ends up maybe over there， taking up 8 B of its own down here ends up the second thing that I typed in。

 not at the same address， but at0 x，4，5，6，4，5，7，4，5，8，4，5，9。 Now。

 if the computer were really smart and generous。 It could probably notice， wait a minute。

 You type that thing in already。 let me just point you at the other memory。

 But that's not how it works。 When you call get string。

 you get your own chunk of memory for whatever the human typed in。 even if by coincidence。

 it's exactly the same。 So Ts characters are ending up here， S is characters are ending up here。

 what value should go in T。😊，Exactly，0 x 4，5，6， because that's the first address of the first character in T。

 So we put O x 4，5，6 there。 So at this point in the story。

 we have two strings in memory and two pointers there too。 And so， in fact。

 if we kind of abstract that away， it's kind of equivalent to S pointing at the chunk of memory on the left and T pointing at the chunk of memory on the right。

 So why was string comparison actually necessary。 Well， in this case。

 we wanted to make sure that the stir comp function was handed the address of S and the address of T So that the stir comp function written by someone else decades ago。

 actually has its own four loop or while loop that essentially starts at the beginning of each string and compares them character by character by character by character。

 That's what it's designed to do by contrast， when I was using equal equals a few minutes ago。

 And also last week incorrectly to compare strings what was getting compare。😊，Well。

 if you literally compare S equals equals T， that's like saying does O x 1，2，3 equal equal O x 4，5，6。

 And that's obviously not true because those are literally two different addresses。

 So the answer I was getting last weekend today was correct。 Those addresses are different。

 but conceptually， of course， I actually intended for the program to compare the actual characters in the string not the simply the addresses thereof。

 So how do we go about fixing something like that。 Well。

 using stir comp ensures that we can actually go ahead and compare them character by character。

 and I don't need to create my own for loop or while loop。 the stir comp function does that for me。

 And we can see this to if I go back to V S code here。 get those two strings。 And just for kicks。

 go ahead and print them both out using printf of percent P backlash N then let's go ahead and print out with percent P again backlash and for each of them passing in those。

😊，ablesS and T respectively， what I should see that even if I type the exact same thing。

 we're going to see two different addresses when I make this version of the program。

 Here's my first high。 Here's my second， and the two addresses are it's subtle。Very much different。

 The first one ends in B 0。 The second one ends in F 0， both of which are hexadeadecimal values。

Question。On any of that， thus far。Any， Oh， yeah， question in front。呀。我在。

What about pointers in general。Really good question。 When you create a pointer in memory or really。

 when you allocate a string or an integer in memory， how does the computer decide where to put it。

 it uses different chunks of memory for different purposes。 And， in fact。

 one of the topics we'll look at after break today is exactly that how a computer decides where to lay things out。

 It's often very intentional。 and it is often auto incremented。

 So theyll go back to back to back when possible， But over time， things will start to get messier。

 especially in larger programs where you're adding and subtracting values for memory all the time。

 So more to come。 Other questions on what we have done here。😊，Alright， before we break。

 let's do one other example that elucidates perhaps what can go wrong without understanding some of these underlying building blocks。

 whereby let's go ahead and create a program this time that aspires to copy2 strings。

 which seems pretty reasonable at a glance because it's certainly easy to copy two integers。

 You just set one equal to the other。 But that's not going be the case It turns out with copying a string。

 So let me open up how about copy dot C， a new program。

 And I'm gonna to include a few libraries at the top。

 We'll use Cs 50 dot H so that we can still use get string conveniently。

 We're going include C type dot H for reasons we'll soon C。 But we saw that a few weeks back。

 We'll include standard I O as always。 and lastly， we'll include string dot H。

 inside of my main function， which won't take any command line arguments。

 Let's go ahead as before and declare a string equal to get string and just prompt the user for a variable S。

 Then let's go ahead and try to copy。S into a new variable T。

 just like I would copy any two variables using the assignment operator。 Then let's treat the copy。

 otherwise known as T now as an array， which we're allowed to do per week 2。

 So let's say the first character in T， we actually want to set equal to the uppercase version of that same character。

 So this line 12 at the moment is literally on the right hand side saying use the two upper function from the C type library。

 which we used a couple weeks back， pass in the first character of the copy T。

 and then update the actual first character of T。 So let's capitalize T。 but not S。 Now。

 at the very bottom of this program。 Let's go ahead and print out the value of S at this point in time。

 And then let's print out the value of T at this point in time。 and。😊。

If you have an in growing instinct for this， when I make this program called copy。Man percent S。

 When I go ahead and make this program called copy and do dot slash copy。

 Let's type in high exclamation point。 no， let's do it lowercase first。

 Let's do high in lowercase enter and will see curiously that S and T both got capitalized。

 even though the only character I touched was T brackets 0。 I didn't touch S after making this copy。

 Now， to be clear what's going on， why don't we remove one of these training wheels。

 So string really doesn't technically exist。 It's always been a char star。

 And this string is also a char star。 So what's really going on。 Well， more clearly now。

 S is the address of the string。😊，That the human typed in。 But T is a copy of what literally。

The address of the thing the human typed in， which is going to be one and the same。 So， in fact。

 pictorially， you can think about it this way。 If here is my canvas of memory and the user is prompted for S and the user types in high in lowercase as I did and it happens to end up down there。

 What gets stored in S is gonna be the address of that memory。

 which for the sake of discussion is maybe O X 1，2，3。 So O X 1，2，3 is what is stored in S。

 when I then on my second line of code create T， I get another 8 by of memory or 64 B to store a pointer char star Aka a string。

 But what is put in S what is put in T literally S O X1，2，3。 So abstractly。

 it's essentially equivalent to S and T both pointing to the same chunk of memory。

 So when I do T bracket 0， and go to the0 or first character of T。

 that happens to be the exact same chunk of memory that S is pointing to。

 And so when that lowercase H becomes a capital H， it's as though both S and T。😊。

Have changed and recall， too， if you're enjoying this syntax。 If I go back to V S code here。

 I did use a ray notation， but I equivalently could have said， go to the address in T。

 go to the address of that first character， which functionally is exactly the same。

 We're just not using the syntactic sugar now of the square brackets。

 That is why high is actually being capitalized for seemingly both versions。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_15.png)

Of it， the original and the copy。 So how do we go about fixing this。 Well。

 we need a couple of new solutions， namely two new functions here。

 malloc is going to be a function that allocates memory。 So memory allocation。 Aka A malloc。

 and then free， which is going to be the opposite， which is when you're done with new memory。

 you can hand it back to the computer and say use this for something else。

 So using these two functions alone， I dare say we can solve now this problem in memory by making an actual conceptual copy of the string by copying H I exclamation point in the null character elsewhere in memory so that we can actually manipulate the copy thereof。

 So how do I do this， Well， let me go back to B S code here。😊。

And let me go ahead and initially propose that we do this。

 Let me propose that we get rid of much of what we did earlier。

 except we'll keep around the declaration of S。 But now， if I want to create a copy of S。

 it turns out I'm gonna need to ask the computer for as much memory as S itself takes up。

 So H I exclamation point takes up how many bytes in memory。😊，4 is correct。

 because you need the null character。 So how do we figure this out。 You can do this。

 Let me give myself another string called T。 but we don't need that white lie anymore。

 Another char star called T and set it equal to not S。 which we knew was going to go wrong。

 said it equal to the return value of this new function。 Maloc。

 which is going return the address of a chunk of memory for me。 How many bys do I want。 Well。

 technically， I just want four B。 So I could do malloc of4。

 And that will literally ask the operating system running in the cloud and V S code for four B of memory somewhere in that black and yellow grid。

 I keep drawing on the screen。 I don't know where it's gonna be。

 But I don't care because malloc's return value will be the address of the first byte thereof Now。

 it's a little dumb to hard code for， not knowing what the human gonna type in。 but that's okay。

 we can do this more dynamically and use our old friend Sterling ask the computer。

 What is the length of S。And then。Add one， because we know that we need to additionally have an extra by。

 even though the length of high in the real world is 3， but we know underneath the hood。

 we actually need that fourth by。 hence the plus1。 Now， to use malloc。

 I actually need to add another library here。 standard lib for standard library dot H。

 And that's gonna give me access to the prototype 4 and in turn， the malloc function。 Now。

 with this chunk of memory， it's up to me to copy the string。

 So how do I go about copying a string from S into T。 Well， I can do this in a bunch of ways。

 But let me propose that we do it like this for into I equals 0。

 I is less than the string length of S， whatever that is I plus plus and then inside of this fairly mundane loop。

 Let's just set this I。😊，Value of T equal to the Ih value of S and copy literally， very mechanically。

 every character from S into T。Then down here， let's go ahead and capitalize just the first character of T by using two upper as before。

 with or without the syntactic sugar。 And then at the very bottom of this program。

 let's print out the value of S itself just for good measure to make sure we didn't screw it up this time and let's print out the value of T just so we see that I。

 in fact， have capitalized T and only T。But I'm not quite done yet。

There's a design flaw here and a mistake， but it's subtle。

Does anyone want to pluck off one or the other？Check 50 and design 50。 You're not gonna like this。

 yeah。Yes， because Stlang always returns the sort of real world length of the string H I exclamation point3。

 This would seem to accidentally forget to copy the null character。

 So I can fix this in a few different ways， I could， for instance。

 at the bottom of my loop actually do something like T bracket4 equals single quotes back slash0 and manually terminate it myself because I know it's got to end with the null character。

 This would be frowned upon to。 I shouldn't be hard codingd the4。 This is all too sloppy。

 So don't do this， What I could instead do is say go up to and through the length of S。

 because if the length of S is3。 But I use less than or equal to。 that thing's gonna iterate。

 of course， four times because I'm starting at0， as always。 So that， I think fixes that problem。

 But now the design flaw， which is subtle， but we've seen it before， yeah。😊，Exactly。

 it's just dumb of me to be asking the computer。 What's the length of S， What's the length of S。

 What's the length of S And every iteration。 So this is why we introduce this trick where you can set another integer variable like n equal to that string length。

 And then after the semicolon， just keep comparing I against N。

 which means you're not calling functions wastefully as before。 Alright。

 if I didn't mess up anything else， let me go into my terminal， let me do， that I mess something up。

😊，I still yes， I did mess something up。 I should have put this back as well。 Thank you。 Alright。

 so let's go ahead and do make copy， enter dot slash copy。

 And now I'm gonna go ahead and type in hi in all lowercase and hit enter。

 and you'll see now that S is unchanged。 It's printed out again in lowercase。 But T is， in fact。

 capitalized here。 Now， why is this。 Well， in this case。

 what's happened is that I've got s in memory， But this time when I allocate T。

 I then use malloc to get a whole chunk of memory here。

 that initially just contains who knows what garbage values as we called them before。

 I'll just leave them as blank here。 But it happens to be for the sake of discussion at O x 4，5，6，7。

8 and 9， when then I actually set t equal to the return value of malloc。

 it's as though t is just pointing to this chunk of memory。 Then in my own loop。

 when I go from0 on up through N， that just means to copy the H， then the I。

 then the exclamation point。 And because of the equal sign， also print copy。😊。

The k null character instead。So this is getting a little tedious， though， admittedly。

 like this is a lot of work just to copy a couple of strings。

 Could we be doing this a little bit better， So we actually can。

 because of the libraries we're including， turns out there's functions for copying strings that come with C。

 So in fact， if I go back to V S code here。 I don't actually need any of this for loop here。

 So long as I have actually allocated enough memory for this string， which I do think I've had。

 I can actually use literally a function called stir copy S CP PY for short and pass in the destination and the source in that order almost feels a little backwards。

 But that's the way it's done to copy S is bytes into T。 It's easy to mess them up。

 but don't mess them up per the documentation。 the destination comes first。

 And then the source string instead。 So if I do this now， let's do make copy we're good to go。

 if I do dot slash copy now and type in high in all lowercase。

 we still have preserve that good property。 But let me propose that things can go wrong。And in fact。

 this is about to make the program look way more complicated than it feels ideal。

 but I've been a little lazy here。 There's a bunch of things that can go wrong for which it's worth knowing about the return values of these here functions。

 So all of this time。 It has been possible for certain functions we've been using get string among them to return confusingly This null value。

 N U L L， again， humans decades ago decided that one would be called N U L。

 other humans have decided this new thing would be called N U L L， N U L。

 pronouncednounce null is just the null terminator， backslash 0， It is a single by of 8 bits。

 all of which are zeros， that's been true for a few weeks now。

 N U L L happens to be a special memory address， literally O X 0。

 at which nothing is supposed to ever live。 So whenever I described the top left corner is this is address 0。

 This is one。 This is two。 humans years ago decided， you know what， let's just waste by location 0。

And never put anything there so that we have a special value to ensure that we can signal when something has gone wrong。

 So humans just decided， don't use memory address O x 0 specifically And a few bytes after it。

 So what does this mean， Well， in my code all this time。 And since week 1， frankly。

 things could have gone wrong。 So in V S code here， I'm using get string and I'm using malloc。

 and I'm using stir copy and all of these print statements here。

 But I'm not actually adding as many error checks as I should。

 So it turns out if you read the actual documentation for get string， which in fairness。

 we never told you about until now， in cases of error， get string can return null。

 Why would it ever have an error， if the human types in such a large paragraph of text。

 maybe that there's no room in the computer's memory for everything they've typed in Well。

 you don't want to just get back part of the text and not know that something went wrong。

 Get string is designed to return a special Sentinel value。 N you L L in all caps。

 that just means I can't oblige。 I can't return you a correct value。Here's an error instead。

 So what I should always have been doing since week1， but we consciously don't。

 because it adds just too much overhead is check。 if S equals equals null。

 then we should abort the program altogether。 And for instance， like return one。

 as we've done before to just signify error。 like we cannot proceed because get string did not work。

 That is true of malloc 2， technically， we should say。

 if the address in T also equals null that is Ox0。 we should also return one because something went wrong。

So let's do this one more time。 Turns out that even to upper is taking for granted the fact that the human typed in anything at all。

 What if the human just types enter， Well， that's a valid string。 It's the so-called empty string。

 quote unquote， but what is the length of nothing。It's gonna be0。

 and that's problematic because if you try to go to T at the first location， what is actually there。

 Well， that's actually the null character， which is not something you should even try to capitalize。

 It would seem So what we should really do here to is check only if the Sterling of S is greater than0。

 should you even bother upper casing that first character。 I mean， one at best。

 it makes no sense because if there's no string， there's nothing uppercase at worst。

 I could break something by touching memory that I should not。And if I may。

 there's another issue now online line 15， I'm asking me computer for memory。

 and it's gonna hand me those four bys。 But technically， I'm never giving them back。

 And so even though this program is so short that it's gonna quit pretty soon and it's not a big deal。

 the computer will automatically reclaim that memory in long running programs like servers or things that are running for a long time。

 if you use Maoc and ask for memory， but never give it back to the computer never free it so to speak。

 your computer might get slower and slower and slower and slower。

 essentially because it's running out of memory， not physically。

 but the computer thinks it's using all of its memory， even if it's not actively in use。

 you as the human know best。 And so at the end of this program， when I am completely done with T。

 you should similarly call free of tea passing in the address that you allocate it previously。

 so that the operating system gets that memory back。 If you don't do that。

 it's what's called a memory leak。 if you've ever used a Mac program。

 a Windows program iPhone or Android program， that how is's just getting slower and slower。😊。

And slower and slower， that is often a symptom of a human having messed up and not freeing memory that they don't actually need。

Anymore。Questions on null or any of these kinds of checks。Now。All right， Well， as a teaser。

 in just a bit， we're going to reveal when and why things can go terribly wrong by way of a little bit of clayation from our friends at Stanford。

 But it feels like we' were long past a good snack break。

 So why don't we go ahead and have some oranges and some fruit snacks。 And we'll see you in 10。😊。

Alright， we are back。 So with memory。 a lot of things can go wrong。 And in fact。

 a question came up during the break about whether or not I should have also called free on S。

 which was the string that I actually got back from getstr， The short answer is no。

 this has been a deliberate choice over the past several weeks。

 whereby the implementation by C S50 of get string automatically freeze memory that it has given to you once it is no longer needed。

 So that's a bit of magic underneath the hood， once those once you no longer use that， though。

 that feature goes away。 But because I actually use malloc to get my memory for T。

 I did have to free that specific memory。 So the rule of thumb quite simply is if you malloced it。

 you must free it。 if we get string malloced it， you do not have to free it to yourself。

 But of course， things can go wrong。 And thankfully。

 there are tools which we can find memory related errors。

 And one thing we're gonna show you briefly is another tool called Valgrin。

 which is a nice compliment to something like debug 50 and print F and the duck for actually chasing down specifically in this case。

😊，Memory related error。 So in fact， let me go over to V S code and open up a program I wrote in advance because it's just not all that useful。

 but it is demonstrative of some things that can go wrong。 And in memory do C。

 we have this code here。 We include standard I O do H and we include standard lib do H。

 the latter of which recall is necessary now， when you want to use malloc and in turn free and inside of this main function I'm doing a few things。

 I am first allocating three integers in kind of an interesting way。

 because it turns out that malloc takes as its argument the number of bytes that you want to get。

 Now I know on most systems and integer is indeed 4 by。 So if I want space for three integers。

 I could just do three times 4 is 12 and put 12 inside the parentheses here。

 but that's generally frowned upon because it would make my code less portable to other systems where might not be4 bys。

 So turns out you can use this operator size of and actually ask the computer how big is a data type like an int on this specific system and for chars。

Always get back one for ins， you'll usually get back4 and same goes for other data types as well。

 But this is the more dynamic way to ask that question。

 if you want to get three integers worth of memory。

 what I'm then going to do is assign on the lefthand side。

 the return value of malloc to this variable x just because and x itself is a pointer2 in integer more specifically to this chunk of memory。

 which is a sequence of three integers。 This is very arbitrary。

 and this is only meant to demonstrate things you can do incorrectly ultimately。

 but this is how I would dynamically get space for three integers from malloc and store the address thereof in x。

 So it stands to reason that I could put my first value at x bracket 1 equals 72。

 my second value equaling 73 and my third value equaling 33。 Now。

 if some of this is rubbing you wrong these are x there's riddled with mistakes already。

 some of which are old to us What's the first thing I've done wrong。

 even if you have no idea what's going on with line 8 about。9，1011。What I do wrong。Yeah。Yeah。

 my indexing is wrong。 Like we've known for weeks now that with arrays or with array syntax。

 you always start counting it 0， then 1， then 2， not 1，2，3。 So that's an issue。

 And this is a new detail。 But given that I've used Maloc On line 8。

 what other mistake have I done in this version of the program。What's missing？Free。

 so I didn't actually call free。 So this program has a memory leak。

 It's asking for memory and never handing it back。 Now， that's pretty good。 You know。

 if few of us were able to just kind eyeball the code and debug it。

 but that's not gonna be true for all people， all programs。

 certainly when the programs get larger and more complicated。

 So a program like Valgri purpose in life is to help you spot these kinds of errors。 So。

 for instance， when I run make memory to compile this program。

 and then do dot slash memory at a glance， like it actually seems perfectly fine。

 if only because I'm not seeing any errors， even when I compile it or when I run it。

 But I do claim that there's at least two that we've seen here。

 it's just we're not getting so unlucky that the programs actually crashing as a result。

 So this is more late and harder to detect bug。 But what I'm gonna do now is this。

 I'm gonna open up my terminal window in full screen。 I'm going then do vgri space dotlash memory。

 So is to run the Valgri memory checker on this program。 So similar to debug 50。

 but the name now is Val。 This isn't a C。😊，This is a common program that programmers use When I hit enter。

 the output's gonna be atrocious。 frankly， it's more way more complicated than it needs to be。

 They put this number here， which means something specific。

 but it's just stupid that it's on every line of output。 So it's overwhelming at a glance。

 But once you've trained your eyes to look for useful information。

 There's a couple of useful insights here。 So one， invalid right of size 4。

 That apparently is somehow related to line 11。 So let's go there。

 Let me minimize my terminal window， Look at line 11 of memory dot C and just see which line that was。

 Okay， In right of size 4。 Well， writing means like changing a value。

 reading means accessing a value。 So there're sort of opposite In right of size 4。 Well。

 here's why it's generally useful to know generally how big an in is like 4。

 you're trying to write 4 bys incorrectly。 So why is line 11 invalid。😊，Just to be clear。

Because the index is off。 like I'm touching memory that I should not。

 If I ask the computer for space for three integers， each of which is 4 Bs。

 that should give me location 0，1 and 2， not location 3。

 So you still have to know little something about programming to be able to make good use of that information In right of size 4。

 But once you've sort trained your mind in your eye to catch it like now I mean I have to go in and fix that problem。

 But what else is wrong based on Valgri's output here。 So this is kind of worry， some leak summary。

 definitely lost 12 B in one blocks。 I don't really know what one blocks means for now。

 but 12 B should be familiar because if you generally remember that an in is 4 B and you ask for three of them。

 Oh there's my 12。 So somehow I'm losing 12 B of memory not in the literal sense。

 but it means by the time the program finishes， you have not returned or freed。

 all of the memory that you asked for。 So this line here is your hint that you've done something wrong with respect。

To 12 by in total。 And sometimes you'll see slightly different output here。 For instance。

 we see mention up here，12 by in one blocks are definitely lost in loss record 1 of1， very verbose。

 but the juicy part is on line 8 is the source of that error specifically。 So there， too。

 It's a little bit of a breadcrumb leading me to the solution for fixing this。 So if I go up here。

 I look at line 8。 Okay， there's only so much that I could have done wrong on line 8。

 If I've malllocked the memory on line 8， sounds like I do need to free it later on。

 So let's fix both of these problems。 The first one is just the indexing issue。 Change the 1，2。

3 to 0，1，2。 Let's then change fix the second problem by just freeing X at the very end。

 And just for good measure。This was not caught by valagin because it doesn't always happen。

 but there's one other。Scennaario that could go wrong， and it relates to line 8。

What should I be doing？I am doing an array， but recall that we can use array syntax on chunks of memory。

 So technically， what line8 is doing is this。 it is allocating 12 by of memory from the computer just because just to demonstrate how malloc works。

 and it's storing the address of that first byte in a variable called X。😡。

The bracket notation is just the syntactic sugar that allows me to change values at X's address。

 I could alternatively just use pointers and say， go to x and put 72 there。

 go to x plus 1 and put 73 there， go to x plus2， and put 33 there。Using pointer arithmetic。

 but those are identical。 And no generally， you know。

 most people would just use square bracket notation because it's just a little cleaner and easier to read and write。

Okay， but back to this question， there's still a subtle bug here based on our example。

 just before break， what should you be doing anytime you call malloc and get string and a few other functions for that matter。

Did I hear the answer？Checking for。Checking for null， right， because iflock has an error。

 there's not enough memory for whatever reason， you should not be proceeding to touch that memory because it might be the null address。

 That is 0 x0。 So what you should really be checking as well if X equals equals null。

 There's no more work to be done here。 let's just return one down here And only if we get all the way to the bottom be maybe return 0 to signify explicitly that is in fact successful operation。

 Allright with that said， let's go back down here remake memory No error messages from the compiler dot memory that too seems okay。

 but it was fine the first time。 Let's now run vgr。

 Let me maximize my window run vgr dotlash memory crossing my fingers as always。

 And now this is actually pretty good。 It's much shorter output。

 even though it's just a scary at a glance。 But most this is fluffy and not revealing Heap summary in you said exit 0 and0。

 So look like all he blocks ref freed。 no leaks are possible。 Heap is a word will come。to。

 but this means there's nothing wrong。 In fact， zero errors， which is a good thing。 So in short。

 Valgriin is among the most arcane programs we're gonna to use。

 It output was really designed for those more comfortable， if you will。

 but there's still juicy insights there。 If you just look for things that lead you to like this file on this line number odds are that will lead you to the most subtle of bugs。

 In fact， another type of bug is when we do indeed touch memory we shouldn't。

 So let me zoom out on that clear my terminal。 And let me open up another program or maybe write this one real fast incorrectly。

 So let me create a program called garbage do C， to demonstrate what we've generally called garbage values。

 that is values that are still in memory， but I didn't put them there myself necessarily。

 I'm gonna include standard I O do H。 I'm gonna include standard lib do H。

 And then I'm gonna go ahead and actually no need for standard Lib this time。

 Let's do int main void and inside of main。 Let's give myself an array of like way too many exam scores or whatnot。

 We used to do just。😊，F，But let's say there's 1024。

 Then let's go ahead and do4 int for int I equals 0。 I less than 1，24。 I plus plus。 And in here。

 let's go ahead and print out whoops， let's go ahead and print out using printf each of those scores。

 Of course， I have clearly forgotten to do something in this program， which is what。

I haven't actually put in any scores there for real。 Like I've asked the computer。

 Give me an array for1 hundred201024 integers， but I've not used get in or even manually typed in any of my quiz scores。

 which we did in the past。 That's because I'm intentionally trying to show us garbage inside of the computer's memory。

 What this loop is gonna do on  now is literally print out the first in。

 the second in the third in all024" but all of them should be garbage values because I myself haven't put anything in those dresses yet。

 So let's go ahead and make garbage。 Let's go ahead and maximize my terminal window just to see more on the screen。

 do dotlash garbage It's gonna be super fast output because the computers way faster than 1024 values alone。

 there is a lot of garbage output。 So when we talk about garbage values in the abstract。

 like here's just some random  zeros a 25 a 32000 a negative number and so forth。

 that's because that's essentially remnants from the computer's memory stuff that might have happened previously。

 not necessarily by me in this moment， which is to say you just shouldn touch that memory at all。

Whatsoever。 So now we're seeing garbage values for the actual first time。

 Let's consider another example of a program that doesn't contain that does。

Contain potentially memory errors。 And let's look at this too。

 So this is not really a useful program。 It's meant to be demonstrative of some of these concepts。

 So here we have a program takes no command line arguments up here。

 we've got a line that pair of lines that declares two pointers。

 but doesn't yet initialize them to any variables。 And that's fine。

 you don't have to have an equal sign with any variable。

 You just eventually should assign it some value。 But this just tells the computer。

 give me a variable X that's gonna store the address of an int。

 Give me another variable Y that's gonna store the address of another int。 Okay， What happens next。

 Well， on this line of code in this simple example。

 We're allocating enough space for a single integer just because it's a stupid exercise。

 there's no reason to do this other than to demonstrate how Maloc works for the moment。

 Maloc returns the address of that chunk of memory， So that's what goes in X。

 So X is now pointing at somewhere in memory 4 bys of space that it can certainly put a value at How do we do that。

 Well， if you do star X and use the direct。😊，That means go to that chunk of memory and put the number 42 there。

 That's totally valid。This says， go to the address in Y and put the unlucky number 13 there。😡。

Unlucky quite literally because what is Y pointing to at this moment？It's just the garbage address。

 Why， because if you don't initialize why who knows what it's gonna be pointing to， Maybe it's 0。

 maybe it's 25， maybe it's 32000， a negative number， just like we saw in the previous example。

 you have no idea what values are going to be an X and Y。 unless you yourself put those values there。

 So this is highlighted in red because bad things are going to happen if you try to dereence an invalid or a bogus pointer。

 even worse than just touching variables that might not have values。

 if you dereference an address and try going to some random place。

 the computer is generally not going to like that。 And in fact。

 our friends at Stanford wonderfully brought this particular scenario to life。

 whereby even though this example is a bit contrived just to fit it all on the screen at once。

 it is going to be the case， that bad things happen if we don't check for these values and actually assign valid values in the form of。

 as we'll see now， some clayation。 So here I give you binky。

EWhich is a bit of clayation from our friend， Nick Parlante at Stanford if we could dim the lights unnecessarily dramatically。

Hey， Viki， wake up， it's time for pointer fun， What's that？Learn about pointers。Oh， gooddy。Well。

 to get started， I guess we're going to need a couple pointers。Okay。

 this code allocates two pointers， which can point to integers。Okay， well， I see the two pointers。

 but they don't seem to be pointing to anything。 That's right。 Initially。

 pointers don't point to anything。 The things they point to are called pointees and setting them up a separate step。

 Oh， right， right。 I knew that。 Thepointees are separate。 so how do you allocate appointee。Well。

 this code allocates a new integer pointee， and this part sets X to point to it。Hey。

 that looks better。 So make it do something。Okay， I'll dereence the pointer X to store the number 42 into its point E For this trick。

 I'll need my magic wand of dereencing。Your magic wand of dereferencing。 that that's great。

This is what the code looks like。 I'll just set up the number， and。Heay， look， there it goes。

So doing a D reference on X follows the arrow to access its point E。 In this case。

 to store 42 in there。 Hey， try using it to store the number 13 through the other pointer， why。Okay。

 I'll just go over here to Y and get the number 13 set up and then take the wand of de referencing and just。

 oh， oh， hey， that didn't work。 Say， Binki， I don't think de referencing Y is a good idea Ca you know。

 setting up the pointee is a separate step。 And I don't think we ever did it。 good point。Yeah， we。

 we allocated the pointer Y， but we never set it to point to a point E。Very observant。 Ey。

 you're looking good there， Binki， Can you fix it so that y points to the same pointee as X。 Sure。

 I'll use my magic wand of pointer assignment。 Is that going be a problem like before。 No。

 this doesn't touch the pointees。 It just changes as one pointer to point to the same thing as another。

😊，Oh， I see。 Now， Y points to the same place as X。So， so wait， now why is fixed， It has ap pointee。

 So you can try the wand of de referencing again to send the 13 over。啊。Okay， here goes。Ay。

 look at that。 Now， dereencing works on why。 And because the pointers are sharing that 1 point E。

 they both see the 13。 Yeah， sharing whatever。 So are we going to switch places now， Oh， look。

 we're out of time， but。Can only imagine how long that took Nick。

 But the key detail was that bad things happened to Bki when we did this line of code dereferencing an invalid pointer that had no true value assigned。

 It was just some garbage value。 Now， what's the solution。 Well， as Nick proposed。

 just don't do that。 And instead， at least do something sensible like assign X equal to Y。

 not to make a copy of anything per se。 But to literally point x at the same location in memory。

 to point Y， the same location in memory is X， then a line like this is perfectly valid。

 You can go to that address， which happens to be the same as the 42。

 And that's why in the claimation form， we saw that the 42 became a 13 instead。 So again。

 at the end of the day， this is only demonstrative of these basic building blocks that we now have at our disposal。

 but also how easy it is to do things incorrectly。 So this is one of those with great power comes great responsibility。

 C is one of the languages that is incredibly high performing。

 It's so close to the hardware that you have so much control over the memory and operation。😊。

That you can write really good， really fast code， and that's why even all these decades later。

 it's among the most omnipresent programming languages in the world。 at the same time。

 you can really screw things up in so many of today's software that are hacked in some way or crash for some reason is often because humans have just missed some simple mistake like this that happens to relate to memory so more modern languages that will soon see like Python and if high school you study Java。

 you don't have this much control over the computer's memory。

 there's many more defenses put in place to protect you and me from ourselves so to speak。

 but you pay the price by some of those languages tend to be less slower and less performant yeah。喂。

What is the difference here that we're now playing with memory。

 This will become clear this weekend next。 And in fact。

 some of the examples on which we'll end today will motivate needing to have finer grain control over what's going on inside of the computer。

 when you want to deal with files。 for instance， you're gonna need to know a little something about memory addresses and where things are。

 when you want to build structures in memory beyond the complexity of an array。 In fact， next week。

 we're gonna start building like two dimensional structures in the computer's memory to represent the equivalent of like a family tree。

 for instance， or trees more generally that can store data in a more efficient way。 up until now。

 all we have is arrays and with arrays， you can achieve something like binary search。

 But we're gonna see there are things you can't do with arrays， especially if speed is important。

I say last week about this I'。It's like 13。s like a signing a。Correct， so last week。

 if you had just said int X equals 13 or int y equals 42 or what not totally fine。 And again。

 this program sole purpose in life is to demonstrate how you can make mistakes in and of itself is not useful here。

 but it's representative of how we're gonna start using this syntax not only in this week's problem sets。

 but next week as well。😡，Alright， so with that claim made that we can do a lot of damage。

 let's consider how pointers and knowledge of memory addresses can actually solve some useful problems。

 Can we get one volunteer to come on up and help pour a drink， Come on up。 Alright， what is your。😊。

Name。Come on？If you want to say a quick hello to the group， I'm Olivia。 Okay。

 and and little something about yourself。 Oh， I live in Canada。 Okay， welcome。

 well come on over here， Olivia。 and we have two glasses。 Well really three glasses。

 So we have these fancy Ray bands that have cameras built in。

 whereby we can sort of capture your point of view。 If you're comfortable。 will'll put these on。

 There's no lenses in them。 The white light will mean we're recording。 Hopefully a memorable moment。

😊，Except that this battery is dead。 So we're going to go to the backup glasses Stay here。

 So when these are on， whatever you look at， we'll have a view of。

Which adds nothing to the demo per se， but a nice memento。 nonetheless， All right， but this version。

This battery2 is dead。 All right， We don't have a backup for the backup。

 so we're going to pretend that this part never happens。Olivia。

 we have two glasses here for you and I'm going to go ahead and pour some colored liquid into boat。

 so we've got some blue liquid here into this glass。All right， so we'll fill this up here。

And then in this one， we're going to go ahead and pour this orange liquid。

And at this point in the story， I'm going to exclaim， oh， no。

 I accidentally put the wrong liquid in the wrong glass。 So I got this backward。

 So what I'd like you to do is swap the values in these glasses so that the blue goes into that glass and the the orange goes into this glass。

😊，Without mixing it without mixing it。 So you're hesitating why。 Well。

 it would be hard to do unless you can talking to the mic。 Oh。

 it would be like hard to do without mixing the two because like。

 you don't have anywhere to put other one。 Of course， So in the real world。

 this is not really solvable。 unless， for instance， we have a temporary variable， if you will。

 like an empty glass in which to do this。 So here is your third variable。

 if you want to go ahead now and get the blue into that one and the orange into that one。Yeah。

No pressure。Alright， so we're putting one value into the temporary variable。

We're putting the other value。😡，Into the original value。Okay， and now you're probably gonna take。Yep。

 I'm guessing the temporary value put it into the original variable。And that was very well done。

 if I maybe we can give Olivia a round of applause for just that。 Thank you。

Little parting gift for you here too。Goal here really being to create a memorable moment of like， oh。

 remember the time Olivia tried to swap two values。 She needed a temporary variable is the takeaway。

 So why is that one code， If we wanted to do the same principle。

 we're gonna need somewhere temporary to put one of those values before we can make this happen。

 The catch is though， that if we don't do this intelligently it's just not going work in C。

 unless we take advantage of some of these new capabilities。 So in fact。

 I'm going go over to B S code here。 And I'm going open up a program called swap C that I wrote in advance whose purpose in life is simply to swap two variables values。

 So I've got standard I O do H at the top So I can use printf I've got the prototype for a swap function。

 which is might as well be Olivia in this case that's going take two inputs A and B or glasses and swap the values ultimately is its purpose inside of main though I'm going do this。

 I'm going set two variables X and y equal to1 and 2 respectively I'm then just as point of clarification going print out the value of x such and such Y is such and such。

 then I'm going call。Sp function， Aka， Olivia to swap the values。 X and Y。

 Then I'm gonna print out X is this。 And Y is this。

 So that hopefully I'll see that they've indeed been swapped at the bottom of this file。

 we have the actual swap function， And as you might expect， it takes two inputs， A and B。

 both of which are integers。 I could have called them anything I want。

 The first thing this function does， is it grabs an empty glass called temp puts a or the blue liquid into it。

 Then we put into a， the value of B。 So we sort of lost the value of a at this point。

 except that we did make a copy of it into temp。 And then lastly， we put into B。

 the temporary variable。 And at the end， the temp variable is empty。

 although technically it still has a copy of the value。

 But it's no longer useful because the job is done。 And a has become B and B has become a。

 So I dare say this is like the literal translation of what Olivia just did。

 And I like the logic of it。 However， when I actually run this program。 Something goes awry。

 So let me go ahead and do make swap。😊，Dot slash swap， and I'll maximize my window。

 I should see hopefully that x is 1。 Y is 2， and then x is 2， and y is1。But no， like。

 even though I literally translated into code what Olivia did， this didn't actually seem to work。

And why is that？ Well， it turns out that this version of the program is not right， In fact。

 because of issues of scope。 And we've talked about scope before。

 generally in the context of like where a variable lives。

 We've said that a variable only exists in like the most recent curly braces that you opened up for it。

 And that was true。 It's just sort of a colloquial way of describing what scope is。

 But scope comes into play here because it turns out that a and B insofar as they are the arguments or parameters for the swap function。

 they have a different scope than X and Y。 And that still follows the same definition。

 They're inside of different curly braces than X and Y are。

 So it seems that I may very well be swapping A and B。 but I'm not having any impact on X and Y。

 So why is that， Well， in C， all this time， anytime you pass in arguments to a function。

 You are passing in those arguments by value。 so to speak。

 You're literally passing in copies of the variables to the function you are calling。

 So what does this mean。 Well more concretely， if like this is a photograph。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_17.png)

Of a chunk of memory inside of the computer。 And we sort of zoom in， as we've done before。

 and we abstract away all of the bytes from top to bottom。

 What's really happening inside of the computer's memory is that we're using some of it for X and Y。

 and some other memory for A and B。 But how is that， in fact， happening。 Well。

 it turns out to a question that came up before the break。

 memory in a computer is actually assigned in a somewhat deliberate fashion。 And generally。

 if we think of this rectangle is representing my computer's whole chunk of memory， generally。

 what happens when you run a program with dot slash something or on a Mac or PC by double clicking or on a phone by single tapping。

 what happens is all of the zeros and ones that were compiled by the company or person who made that program are loaded into the top of the computer's memory。

 so to speak。 This is just an artist rendition， there's no notion of top or bottom per se。

 But it's loaded into this chunk of memory at the very edge of the computer's memory。

 Aka machine code， the zeros and ones that compose the actual program， that's where they go。

 So they're copied from the hard drive or the SSD， whatever you know it as the persistent storage。😊。

And it's put there in the computer's Ram or random access memory。

 which is the faster memory where programs and files live while you are using them。 Meanwhile。

 if your program or the program you're using has any global variables global in the sense that they're defined outside of main and not inside of main or inside of other functions。

 They end up right below that machine code by convention just so they're accessible everywhere。

 Meanwhile， there's this big chunk of memory below that called the heap。

 The heap is the chunk of memory that malloc uses to allocate memory for you。

 So the first time you call malloc， it's going to give you probably this chunk of memory。

 the second time this chunk， the third time this chunk and this chunk and so forth。

 back to back to back in memory， But malloc is going to manage all of that for you。

 you don't have to worry about where it's coming from。

 but it's coming more generally from this big heap area。

But it turns out that the way computers are designed is that the heap， of course。

 sort of grows and therefore downward， again， even though there's no notion of up down inside of the computer。

 but it grows in this direction。 But it'd be nice to make use of this other area of memory。

 and that's what's called the stack。 And the stack is the area of memory that's used。

 anytime you create local variables or call functions。 So again， malloc uses memory from up here。

 and functions and variables use memory down here。 just because this is what humans in a room decided years ago is how the computer's memory would be used。

 therefore， the stack grows sort of vertically much like stacking trays in a cafeteria or the dining hall。

 they go from bottom to top in this model。 All right， Well， let's consider for the moment。

 just how the stack is used because we're using a main function in this program we're using a swap function in this program。

 So I claim that those functions are going to use memory down here。 Well， how are they going use it。

 and how is this， in fact， bad for our current goal。 Well， when you call the main function，😊。

Uses this chunk of memory here， specifically if main has any arguments。

 like command line arguments or if main has any local variables， they end up down here in memory。

 Meanwhile， when main call swap， swap gets the next available chunk of memory above it。

 so to speak in memory and any of its arguments or local variables end up there。

 So when main when swap is done executing。 it's as though that memory disappears。

 even though the zeros and ones are still there。 but the computer can now reuse that same chunk of memory later。

 air go garbage values。 when functions are being called going up and down conceptually。

 that's why you're getting remnants of previous values in the computer's memory。

 But let's focus on main for a moment in main in this program recall that I declare two variables X and y X getting the value1。

 Y getting the value2 per these two lines of code。 then I call the swap function。

 So swap is going to get its own chunk of memory more technically called a frame of memory。

 and inside of that frame， it has two arguments A and B， and a local variable called temp。

 So I'll draw them as such。😊，When you actually call swap passing in X and y。

 X and y are passed in by value， that is to say copy。 So a becomes a copy of x。

 and B becomes a copy of y。 So when this line of code or rather this prototype for swap just makes clear that it takes two arguments。

 A and B， both of which are integers in that same order。 So x come a y lines up with a comm a B。

 So what happens then inside of the swap function if a is a copy of X and B is a copy of y。 Well。

 at the moment， it's equal to1 and two respectively。

 but consider this first line of code int temp gets a。

 So temp takes on the value of a next line of code A gets B。 So a gets the value of B， sorry。

 which just happened。 Meanwhile， B gets the value of temp， So B gets the value of temp。

 Now temp still has a copy of1， So it's not quite analogous to the liquid because that glass is clearly now empty。

 but it does。remnants of what it once did。 But the key here is that A and B have successfully been swapped。

 If I were to print out A and B， I would see that they've been swapped。

 But what has obviously not been swapped in this story， no one has touched X or Y。

 Because when swap returns， especially if I don't even print out anything in swap， X and Y are un。

 So A and B， the copies were swapped。 but not the original values。

 And that's the essence of the problem here with this represent this simple example of swapping values。

 because I was passing by value。 But as of today， we now have a solution to this problem because previously to today。

 if I ask you to write a function that swaps two values， you could not physically do it in code。

 because you had no way of expressing the solution to this problem。

 But now we have the ability to pass by reference that is used pointers and address more generally to tell the function how to go to an address and do something there。

 How to go to another address and do something there。 How do I express this syntactically。

 It's going look a little scary at first glance， But it's just an。Of today's new building blocks。

 this bad version of the program where A and B are both integers just needs to change to be addresses of integers。

 So give the function a sort of treasure map that leads it to the actual X and Y by saying that a is now not going to be an int per se。

 but the address of an int。 B is going to be the address of an int。 A now to use those values。

 you can say the following int temp gets whatever is at location A。

Go to location A and put whatevers at location B。 Go to location B and put in the temp value。

 And here is a perfect example of where this use and overuse of the star or asterisk operator is just like cognitively confusing。

 frankly， because we use star for multiplication， we use it for declaring a pointer。

 we use it for dereferencing a pointer。 Ily， humans years ago would have come up with another symbol on the US English keyboard to represent these different ideas。

 But this is where we're at。 we're using the star for different things in different context。

 So this just tells the computer that a is gonna to be a pointer， an address of an int。

 This tells the computer that B is gonna to be the address of an int。 This star。

 when there's no data type to the left of it means go to that address。

 as does every other example thereof。 So what's happening this time。

 if we actually look at the diagram again。 X and y are still one and2 respectively。

 swap gets called It gets now the values of the address of x and the address of y。 So pictorially。

 we might draw that as following。A is pointing to X。 B is pointing to2。 I mean， technically。

 it's like O X 1，2，3 and O X 1，2， whatever。 But who cares。

 We're just gonna abstract it away now with actual arrows or pointers。 The beauty of this now。

 then is if we look at the swap function， int temp gets star A。 That means started A and go there。

 sort of shoots and ladder style familiar with the game and you find the value 1。

 So you put the value 1 inside of temp， which is why it's there Now。 Meanwhile。

 this next line of code。 go to a's address， go to B's address and copy the ladder to the former。

 So this means go to a， This means go to B， where you find the two。 So put the two。

Where a is pointing。 Lastly， go to B and put temp there。 So that's easy。 Go to B and point temp。

 which is why we now have the one。 And the beauty of this now is that when swap is done executing this memory。

 this frame sort of goes away conceptually， even though the zeros and ones are still there。

 but it's done being used， but we have now mutated the actual values of X and Y by giving them a proverbial treasure map of the addresses of x and Y。

 not copies of the values themselves。😊。

![](img/272dfdb65ad4ae9b6c395f4647e726f9_19.png)

So hopefully， this is the beginning of an answer to like， why is this stuff useful。

 You can now solve a whole new class of problem and even more next week， other questions。

They' want to need the syntax， pictures or the like。This is good use of pointers now instead of bad。

 Allright， so with that new capability， let us consider here。😊，How things can still go wrong。

 And why indeed， with this power comes that responsibility， Well。

 if you consider now the bad version of the code is fixable via this good version of the code。

 we've still left a big glaring problem in the diagram itself。

 designing something that grows this way， Again something that grows this way。

 like this is not gonna end well。 Why， because the more you call mallc。

 the more memory that gets used here。 The more functions you call the more memory that gets used here。

 And at some point， like they will collide because the computer only has a finite amount of memory。

 So how do you avoid this situation。 like you kind of don't like you honestly just make sure that you minimize how much memory you're using by calling malloc only as much as you need to and not calling for a million bytes of memory just because you might need them。

 you only allocate what memory you need And you try not to call functions again and again and again and again and again and again without them finally returning。

 So if you ever did something recursive a couple weeks ago。

 where you accidentally maybe call the function that never had a base case。

 never divide and conquered and actually shrunk the problem， you could。😊。

Overflow the stack or equivalently heap by just using too many frames of memory。

 So it's just a mistake in the programmer for the programme themselves。

 So if you've ever heard these phrases now， which some of you might have heap overflow or stack overflow。

 There's a very popular website called stack overflow。

 And this is the etymology thereof like stack overflow refers to this representative big problem with computer's memory。

 if you're not mindful of how you're using the computer's memory。 And this is just the way it is。

 if you've got finite amount of anything， that resource can eventually run out at which point program will crash or something else might very well go wrong。

 In fact， this is a general， more specific examples of what are called buffer overflows。

 a buffer overflow It generally just a chunk of memory like an array that actually just gets overflow with too many values like using allocating a small array and trying to put too many numbers there in There's problems that and in fact。

 you can see this very simply， if we take off those last of our training wheels。😊，So， for instance。

 these are the functions in the C50 library， get in， get string and so forth。

 They're harder to take off these training。 It's harder to take off these training wheels because C does not fundamentally make it that easy to manage memory yourself。

 So， for instance， let's focus for just a moment on get in。

 I'm gonna go over to V S code here in just a second。

 And let's go ahead and create our very simple program called get dot C。

 whose purpose in life is to just get an integer， much like C50's own function。 So in get dot C。

I'm going to propose that we write a program that does a little something。Like this。Include C。

 S 50 dot H， include standard I O dot H。 and then inside of main。

 let's go ahead and declare an int N。Set it equal to get int。

 we'll just ask the user for the value of n。 Then let's go ahead and print out ns value verbaate and back by just doing quote unquote comma n。

 So this is not a very interesting program because it's literally hard coding rather This program is simply using the get in function or in order to get in and stored in n。

 So let's run it， make get do slash get type in a number like 50 seems to work。 And yes。

 I think this program is correct， even though it is using the C 50 training wheel of get in。

 let's stop using get int， though。 It turns out that you don't have to use get int。

 if you instead use a function called scanf， which scans formatted input。

 which just means read something from the keyboard into memory。

 This is essentially what get string and getin using。

 although that too is a bit of an oversimplification。

 but let's use it here now is an opportunity to get rid of the training wheel of the C 50 library altogether。

 and down here， let's do this instead。😊，Using get in， let's declare a variable N。

 but not give it a value yet。 Let's now print out just a little prompt just to tell the human what we want。

 We want them to type in a value for N。 And now let's use this new function called scanf and say scan from the user's keyboard in integer represented by percent I or old friend and format code and please put the integer that the human types in。

In the variable N。This is slightly buggy， though， because if I want a function like scana to be able to change the value of a variable。

 just like the swap function， I can't just pass in n。 I need to pass in the address of N here。

 In fact， let's take a moment now to go into the swap function， which we knew to be buggy before。

 and actually updated to match what we saw on the slides。

 I claim that the problem is that we're passing in originally。

 x and y is one and2 into the swap function， but therefore we're passing in copies。

 But what if we change the swap function to take in D。

 the address of an int and the address of an int。 let me change my prototype accordingly because that must be changed。

 then when I change this function to take in those pointers。

 I need to change my code to dereence them。 But there's one last thing I need do。

 I'm still on this line of swap passing in X and y， which is literally the values X and Y。

 If I want to pass in the address of x and the address of Y， what other operator。Why now need。

The ampersand X and the ampersand Y to pass in sort of the treasure map。

 the pointer to those two variables locations。 So if I open up my terminal window now。

 do make swap on this version do swap cross my fingers。 Now。

 this new and improved version of swap as claimed does actually swap the values。

 the key being swap now has access not to X and y per se， but to the address of X and Y。

 So if we now close out swap and go back to get， here is the same principle applied to scanf。

 if scanf exists and it comes with C its purpose in life is to scan an integer from the keyboard and put it somewhere you want。

 you can't just give it the variable name because it's gonna get a copy of whatever garbage value is in there。

 you have to say， put this answer in the address at the address of N itself。So lastly， after this。

 let me go ahead and print out n colon and then present I again as a format code。

 backslash n comma N。 This line is just my prompt because I just want the human to know what they're being asked for。

 This line is printing out N colon and then the actual value。

 So the only interesting part here is that I'm declaring a variable called n。

 but I'm not giving it a value myself， But I'm using scanf instead of get int to scan。

 so to speak an integer from the keyboard and put it at the address of n。

 so that scanf has access to that value。So if I now do make get without any C 50 library dot slash get。

 let's type in the number 50。 I indeed see the number spit back at me。 And just to be clear。

 Prif uses these format codes a percent I and so forth。 Scf uses essentially the same format code。

 So that's why I'm using percent I in both places。 both functions per documentation are designed to do just that。

 So this is great。 We've gotten rid of get int。 catches that getting rid of get string is much。

 much harder。 why， well let's try another example。 let's go ahead and try to get a string from the user instead of just an in。

 So we'll call it string S。 but wait a minute。 C 50 library is not included。

 So we need to use the actual thing that this is。 So char star S means give me a variable that's gonna store a string。

 Let's go ahead and print out that prompt just to prompt the user for S。 just for clarity。

 Now let's use scanf and scan a string with percent S。 and put it at location S。

 Then let's go ahead and print out just a reminder that the value of。😊，S is now that passing in S。

 Now， there's something a little bit different here。

 Notice that I've deliberately not used an ampers sand before this S Y。

Even though I did before the end， yeah。这块了。Yeah， so I want to pass in the address of the string。

 which is， if I may like already S。 like S is by definition， the address of some string。

 that is what a char star is。 or rather， it's the address of a character。

 but we know already that if you lead it to the first character。

 whatever function can find the end of it thanks to the null character。

 except that that's not gonna be wholly true here。 But I don't want to do ampersand here because if S is an address doing ampersand S would be the address of an address。

 which is actually a thing called a pointer to a pointer， but none of that today。

 But it's gonna be correct as written here。 And was an integer。 So I needed the address of it。

 S is already a pointer by definition， it's a char star， So I don't use the ampersandant here。

 But the problem is this。 If I now do make get dot slash get and let's type in a word like about high。

Okay， it did work。 Let me try something even bigger。 Like， hi， let's just hold this down a lot。

 Let's do how about this。A really long strength。Let's type in a really long string。Like， hi。

And it's always a gamble to see if I've done this long enough， but。Okay。It didn't break。 Okay。

 you'd like to think that this is correct。 But let's go ahead and do this。 Valgrind of get。

Dot slash get enter。 Let me maximize my screen。 Oh and let me go ahead and type in a value for S While Valg is running。

 I'm gonna type in high exclamation point。 And now。

 let's actually scroll down to the scroll to the top of this。

 A lot of error seems to have happened here。 Use of uninitialized value of size 8。

 use of uninitialized value of size 8。 Like a lot of stuff is going wrong here。

 apparently on it looks like maybe line 4， which is quite early in the program。 And in fact， well。

 actually， that's not it line。Multiple lines of code here we're having issues with。 But why， Well。

 let's focus on the code here alone for a moment。 Line 5 is giving me what。A variable called S。

 That's the address of a char。 But what is S right now， Like what value is in there。

It's a garbage value because there's no equal sign involved。 I'm just saying， give me space。 Like。

 give me 8 B，64 B to store the address of a character。

 But if I don't use the equal sign and actually put anything there， It is， in fact。

 just some garbage value。 The printf is uninteresting。 It's just printing out S colon。

 scan if though， is saying go to this address and store the characters that the human typed in。

 But that means like following the wiggly line that we drew on the screen before。

 because we have no idea where S is pointing， It might be there， there there there。

 you're putting the string at a bogus location in memory。 You haven't actually allocated memory。

 So when you then try to print it， you're just trusting that you're going to memory again。

 that you control。 So what is the solution here， Well。

 there's a few different ways we could solve this。 we could do something like this actually allocate space for like four Bs so that the human can safely type in So the human can safely type in high exclamation point with room for the null character。

 We could change S to actually be an array of size 4。

Because we can treat arrays as though there are addresses and addresses as though there are arrays。

 It turns out that syntactic sugar really goes in both directions。

 This too would solve that problem or better still we wouldn't use scanf at all because how do I know how many characters the human gonna type in like this was a question too that came up during break。

 Well hi will fit in four Bs with the nu character by will not So maybe I need five what if they type in a longer word 6 maybe the longer word 7。

 Well， maybe100 or maybe 1000 or 10000 or 100000 or a million like at some point。

 you've got to draw a line in the sand and say you can't type in something longer than this。

 And you see this in applications all the time like on the web。

 you can only type in so many characters sometimes into forms。

 And that's for various reasons among them is this getstr， though。

 we'll handle almost an infinite number of characters because the way we implemented getstr is to take baby steps through the input。

 When you type in a word on the keyboard or even a paragraph on the keyboard。

 we get strings implementers called malloc essentially。And again and again and again。

 just asking for one more bitete if we need it， One more bite if we need it。

 One more byte so that you don't have to worry about doing that。 The problem is。

 if you were to write code yourself without the C 50 library or someone else's equivalent library。

 you have to decide like how many bys do you want to allow and you have to trust that the human is not going to mess around and type in more values than you actually expect。

 So what's happening with all of these examples thus far is that if you think of your memory as kind of a minefield of garbage values wasn't a problem when we declared N to have a value of 50 because we told。

Scanf to go to that address and put the number 50 there。 And it fits。

 That's fine because an int is always four Bs in this case。

 Who knows how many times the human is gonna hit the keyboard when typing in a string could be  three or four or a million or anything else。

 So when we declare S here to be a pointer， It takes up 8 Bs per the Oscar to the Oscars the gruch here。

 whereby that's8 garbage values that collectively represent that address at the moment。

 because we've not assigned it to any other value。 So if we tried to tell Scf。

 go to this address and store high or anything else there。

 Like who knows where it's gonna end up in memory hence the sggly line again。

 and the program will quite often crash。 I didn't get it because I didn't type in long enough of a string。

 but it would eventually if I tried hard enough crash because you're touching memory that you yourself did not allocate as an array via malloc or some other mechanism。

 So what is the solution，  honestly， like don't use C for user input like this unless。

Prepare to implement that complexity yourself， use the C50 library or some other library。 This。

 too is why in two weeks， we're gonna switch to Python because Python makes life so much easier when it comes to basic things like getting user input。

 as do many other modern languages。 But those languages just have code that other humans have written to solve these problems for you。

 So these problems exist。 But they'll be abstracted away for you。Alright。

 let's tie this now together with where we began， which was to ultimately that we want to have。

The ability now to actually access files。 and we introduce now a topic called file Io Io for input and output。

 a file is just a bunch of bytes that are stored on disk where disk might mean in a hard drive。

 the thing that spins around with a platter with lots of zeros and ones on it or an SSD is solid state drive。

 which is no moving parts nowadays and generally where our data is stored long。

 whereas Ram random access memory，'all the yellow pictures we've been drawing is volatile that is to say when you lose power。

 the battery dies， you lose everything in Ram on a hard drive or solid state drive。

 that's persistent storage or non-volatile storage， which means when the power goes out。

 thankfully you don't lose all of your documents and essays and so forth。

 whether it's on your Mac PC or somewhere in the cloud。

 but we haven't yet seen any code via which you yourselves can create files。

 like literally every program we've written even the phone book example last time。

 when I typed in names and numbers， they got deleted as soon as the program quit and ended。

 So with file IO， though we have the ability now to start creating saving editing， deleting files。

 much like you。from the file menu of Google Docs， Microsoft Word or the like here are just some of the functions that come with the programming language C that allow you to open files。

 Aka F open close files， Aka A F closed print to a file scan from a file。

 read a file write to a file， lots of different function。

 some of which will explore this coming week。 But why don't we first use them to solve a problem here in V S code。

 So let me go ahead and close get do C， Let's go ahead and open up a new program called phone book do C。

 but implement a persistent version of it ultimately。

 that doesn't just get deleted from memory when the program quits。

 Let's go ahead and only because it will make life easier。

 Let's include the C 50 library still for this。 Let's include standard I O do H for this。

 and let's include string do H for this。 Then inside of main， No command line arguments。

 Let's go ahead and。😊，Open a file called phonebook dot C SV。 CV stands for comma separated values。

 Many of you have probably used them in the real world。

 They're like very lightweight spreadsheets where things are effectively stored in rows and columns where the columns are represented by just commas between values。

 And we'll see this in just a moment。 How do you open a new file called phone book do C SV。 Well。

 I'm gonna do file star file equals F open phone book do CV。

 And then I'm gonna do quote unquote W for right。 So what's going on here。 F open is opening a file。

 whether or not exist yet called phone book do C SV。

 And it's opening it in such a way that I will be allowed to write to it。

 Hence the quote unquote W per the documentation。 It means I can write to this file and not just read it。

😊，The return value is going to be stored in a variable called file， a lowercase by convention。

 but that file is technically astruct called file in all caps。 It's a little weird。

 It's among the few things that is fully capitalize and see。

 it doesn't mean it's a constant or anything like that。

 It's just how someone implemented it years ago。 This is giving me a pointer two。

 essentially the contents of that file。 It's a bit of a white lie。

 Secondly giving you a pointer to a chunk of memory that represents that file。

 but for all intents and purposes， it's a pointer to the file for now。 Now。

 let's go ahead and ask the user for a name and number to add to this phone book。

 let's do char star name equals get string quote unquote name to prompt the human for that char star number。

 let's prompt them for that。 And do with this。 And I could be using the string data type。

 But I'm trying to at least remove what training wheels we don't technically need anymore。

 And now that we've got a name and number in variables， let's print them to the file。 That is。

 let's save them to the file。 instead of printf。 We're gonna use F print F。

We're going to specify what file we want to print to in case we have multiple ones open what。

Do I want to print a string followed by a string， followed by a new line， Ergo。

 comma separated values，1 after the other per line。

 Then I'm gonna pass in the values name and number respectively。And now， I'm gonna to go ahead and。

Do F close to close that file so that it's effectively saved。 Alright。

 so let me go ahead and demonstrate first that phonebook dot CSV does not really exist。

 It's empty initially。 And let me scooch it over to the right hand side here so that， oh。

 let's do this。Let me go ahead and sc it over to the right here so we can see both at the same time。

 I'm now gonna do make phone book enter so far so good。 dot slash phone book。

 And let me go ahead and type in， for instance， let's see my name，6，1，74，9，5。

1000 and watch the top right of your screen as the program F writes to it and F closes the contents。

 All good。 Allright， let's run it again because maybe like the ios app or the Android app。

 I'm adding new friends to my phone book here。 So I'm gonna dot slash phone book。

 And I'm gonna go ahead and oh。😊，Top right just got turned blank。 Well， let's try this。 Kelly，6，1，7。

4，9，5，1000。 enter。 Okay， she's back。 Let me run it again。 Dot slash phone book gone。Well。

 what's going on here？It's not persisting， at least as long as I would like。

It seems to be the case that like writing to a file means literally rewrite the file。

 So if you use W， you're going to write to the file， but literally starting at the first byte。

 if you want to be smart about it and append to the file。 per the documentation for F open。

 you instead use quote unquote A for a pen instead of quote unquote W for right。

 this is a convention in other languages too。 let's start this over。

 let me go ahead and recompile this program， make phone book。 Now let me do dot phone。

 I'll type in my name again first 617，95100 enter so far so good。 do phone book。 So far so good。

 Kelly 6，1，7，49，5，1000 enter and now we're on our way。 In fact， I can close this file。

 I can close this file， I can then open up phone book do cv。 and indeed， it has persisted。

 And in fact， if I downloaded this file onto my Mac or my PC。

 I can then write click it or double click on it and probably open it in Microsoft Excel or Apple numbers。

 I can import it into Google sheets or any number of other spreadsheet tools because。

Now I am persisting and writing files of my own。Questions on any of the techniques。

We just tried out here。If we really want to be nitpicky， like technically。

 I should fix one bug or missed opportunity。 if I open up phone book do C。

 I'm gonna propose that as with any use of pointers and addresses more generally， here too。

 something could be wrong。 Like， maybe I'm just out of space。

 And so F open can't physically open the file for me。 So here too。

 I should check if file equals equals null， Okay， fine， return 1。

 and then maybe at the very bottom here I return 0 to make clear， No， no。

 if I get this far all is well。 So in short， any time， you are dealing now with pointers。

 you should be checking the return values to see if all， in fact， went well。 Yeah。Yes。

 everything we are using is part of standard I O dot H。

 which is wonderfully useful now because it has not just print F， but F print F and so forth as well。

😊，Good question， yeah。Yes， so we have how our pointers used in this code。

 The short answer is you have to use pointers because this is how C designed files to work。

 So we couldn't really introduce you all to files， file I O in week1 or two or three because we we'd have to introduce like this stupid little character to you and you'd be like。

 what does this mean it's not multiplication， because the way file I O works is that when you open a file。

 you are essentially handed the address of that file in memory。 that's an oversimplification。

 you're technically handed the address of a data structure in memory。

 that references the file actually on disk。 But for all intents and purposes， as I said。

 this gives you a pointer to the contents of the file。 And if you want to write to the file。

 you need to then do use f printf in this case， tell it what file to write to So you can go there and then store something like this string with these values plugged in。

 So in short， in C without pointers， you just can't do file I O。

 unless it's abstracted away for you by some library。Good question， other questions on file。I owe。

Al right， well， let me do one other example here that's a little reminiscent of things we see all the time on our phones and laptops and desktops like these progress bars for like video players。

 And you're all probably generally familiar with the term like buffering。

 if only because YouTube and other apps when they are slow or you have a slow internet connection。

 They might say buffering dot dot dot。 Well， what does that mean。 Well。

 a buffer is just a chunk of memory more specifically。

 it's often an array that is only a finite size that stores bys of stuff。

 in the context of a video player， for instance， this red line here。

 which represents that way that much through the video。

 it's an array that stores like the next few bytes of a video。 And ideally。

 if you have a fast enough connection when you hit play。

 those bytes keep getting downloaded and added to the buffer。

 And hopefully you don't finish watching the bytes that have been downloaded before more bytes have been downloaded。

 So a buffer is just a chunk of memory or more specifically an array in a language like C。 Well。

 just to demonstrate how else you can do things with file I O。

 Let me propose that we write a simple little program that is our own implementation of the Cp program。

 the copy program。😊，That we've used a few times already that allows you in your terminal window to copy one file to another。

 likening it to this idea of a progress bar where byte by byte， you want to do something。

 namely in this case， copy it， not watch it instead。

 So let me go in V S code and code up a program called Cp do C。 And in this program。

 I'm gonna go ahead and include standard I O do H at the top。

 I'm going then give myself a main function that this time does take finally。

 a command line argument via in Arg C。 and our old friend string Arg V。

 which today we can now reveal to be also just a char star。 In fact。

 this is how we can now technically write the declaration for main because string no longer exist without the C50 library per se。

 So that's really what's been going on this whole time。 Now， let me go ahead and do this。

 I want to be able to write a program that takes two command line arguments。 actually。

 the name of the file to copy and the name of the new。File to create from it。

 So let's go ahead and create a file using the same syntax as before called SRC for short source。

 as is a convention。 And let's open a file using。The file name， Arg V bracket1。 So the first word。

 the human types。 And let's go ahead and open it in read mode。

 because I want to read the source and write to the destination。 My next file。

 file star DSST destination for short will be F open of R V 2 comma unquote right Now。

 why 1 and 2 and not0 and1 in0 is the name of the program。

 which is not interesting one in2 will contain the next two words that the human types。 Now。

 let me propose I want to copy this file from source to destination byte by byte similar in spirit to a buffer like this where you're just grabbing from the Internet 1 byte of the video at a time。

 So as to watch it in this case， I want to copy it。 So how can I do this。 Well。

 we don't have a data type per se for representing a by 8 B。 However。

 a common convention is to actually use our new friend type de and simply declare byte to be something significant or something specific。

 So let me declare a type。Called byte。 And what is a by going to be。 Well， ideally。

 is just a char because a char we know is1 B or 8 B。

 but recall that chas can be treated as integers and integers， of course。

 can be positive and negative。 So even though this is a little esoteric， technically。

 I wanted to define a byte to be what we'll call an unsigned char。

 which is probably a keyword you haven't yet seen。 but it just tells the compiler that this char that is this sequence of 8 bits cannot be interpreted as a negative number。

 because I am not doing anything with math。 These are just raw bys or 8 B。 So now down here。

 I can give myself a byte， and I'll call it B for short。 And now I'm gonna write a loop。

 similar in spirit to what YouTube and other players are probably doing。

 which is iterates over a file， Bte byte byte making in our case， a copy thereof。

 So while I am reading from this file， into this byte the size of one by  one at a time。

Into this destination。Go ahead and check。That I've read at least one。

 So while the return value of a new function called Fri is not equal to 0， go ahead and。Oop， sorry。

 source。Go ahead and call F right another new function going to that address of the byte。

 grabbing the size of it， which happens to be one， but I'll use size of for consistency。

 grab one such byte and write it to destination。 This is a huge mouthful admittedly。

 the last thing of which I need to do is close the destination。 so as to save it。

 close the original file， the source， But this huge mouthful。

 which you'll get more familiar with the next problem set is essentially saying on line 12。

 while I can read one byte at a time， right on line 14， that byte to the file。

 Iple essentially this idea of the red progress bar going by to by to by， reading one byte at a time。

 reading from one file， the source writing to the other the destination And here too。

 to your question earlier， like why why pointers This is the way file I always done。

 you have to be able to express， go to this address。 go to this file。

 if you want to get data from it or to it。 and a minor refinement to。Technically。

 when you open in files， if you know theyre binary files that is zeros and ones and not ask your Uniode text files。

 you can technically tell F open， write and read in binary mode。

 So there's no mistaking the bits for something other than raw data an image or otherwise。 Allright。

 so if I go ahead now and do make C P。 It's so far compiles。 Let's try this out。

 So here again is phone book do CSv。ops here that's phone book dot C here again is phone book do CSv with two of us。

 David and Kelly， let's try to make a copy of this file as follows dot slash Cp。

 So this is my version of the copy program。 not the one that comes with the system。

 Let's copy phone book dot cv into copy dot cV enter。Let's open up now the copy of the CSP。 whoops。

 da， wrong program。 Let's open now the copy of。The CSV enter。 andvoila， thank God。

 like it actually worked。 I have made a byte 4 Bte copy of the file using syntax that was not available to us until today。



![](img/272dfdb65ad4ae9b6c395f4647e726f9_21.png)

So who cares And what's the motivation。 Well， it's a lot more fun to treat not just text files and these tiny little examples。

 but to actually play with realword examples。 And in the next problem set among the things you'll do is experiment with BM files。

 bit mapped files， which essentially just means a grid of pixels top to bottom， left to right。

 much like our cat that our volunteers at the classes start created for us with a bitm file。

 you'll store in files， literal sequences of pixels or dots。

 each of which is going to be represented with a specific color， a red value。

 a green value and a blue value And among the things youll be able to do given such beautiful photos as this is the weaks bridge done by the Charles River。

 is actually make your own Instagram like filters to apply to photos like this。

 understanding now as you do or soon will understand to be able to iterate over the file。

 top to bottom left to right over each of the bites therein and somehow mutate the bys to look a little bit different。

 So if this is the original photo， you might be able to make it all gray scale， by changing the R's。

 the G's and the be's to smaller values， somehow that are simpler values。😊。

That are just black and white and gray tones。 You might take that same photo as input and give it more of a CPepia tone。

 like an old school photograph instead。 You might actually reflect it。

 like actually put these bytes over here and these bytes over here so as to create the inverse of the image by reflecting it over the vertical axis here。

 or you might even blur the image like this。 This is kind of a common feature in a lot of photo editing programs to either blur or de blur。

 Well you can sort of do a little bit of math and make every pixel a little fuzzier by kind of clouding with the human is actually seeing or feeling more comfortable。

 You can actually write code now that you know how to manipulate files and addresses thereof and actually do edge detection and find the salient characteristics of something like the bridge to distinguish it from the sky and actually find filter like edges like these。

 So those are just some of the problems that you're gonna solve over the coming weeks' problems that manipulating ultimately files like these as well as Jpegs And the last thing we thought we'd end on is a sort of computer science joke。

 which for better for worse， you're now getting more and more。😊，Able to interpret。

 so I'll leave you dramatically with this here， famous joke。Oh。That's more laughterer than usual。

 All right， that's it for week 4。 We will see you next time。

