# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P5：-05-CS50x 2024 - Lecture 4 - Memory - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/8f310f169bb1b17e412b37f8847977db_0.png)

🎼Yeah。

![](img/8f310f169bb1b17e412b37f8847977db_2.png)

![](img/8f310f169bb1b17e412b37f8847977db_3.png)

![](img/8f310f169bb1b17e412b37f8847977db_4.png)

Allright， so this is C S 50 and this is week4 and this is actually one of the weeks that really makes Cs 50 Cs 50。

 And so far as we'll take an even lower level look at how computers work and in turn what it is you're doing when you write code toward an end of really giving you a complete mental model of like what's going on inside so that when you run to solve some problem when you want to fix solve some problem when you want to write some code。

 you actually know what those building blocks inside of the computer itself actually are。

 We'll ultimately to take off some of the training wheels that we've had on for the past few weeks。

 particularly in C and we'll also introduce more familiar media type。

 So files like images are sort of everywhere and we'll introduce you to exactly what's going on when you just look at photograph or a gif or a p or any kind of image on your screen like this one here and it'll become clear that unlike Hollywood TV shows in movies if you try to enhance a picture like this to sort of look closer and closer and closer in the movies。

 typically trying to figure out who the bad guy is， for instance。

 like eventually you run out of information。😊，Because there's only a finite number of bits or bytes that compose these files。

 So anytime you've seen computers that you just hit a button in boom， it's enhanced。

 and all of a sudden the suspect is clear。 That's a lot more Hollywood than it is computer science。

 But with that said later in the term， we will talk about artificial intelligence。

 And even though there might not be that information there through statistical reasoning and modeling and predictions can computers increasingly actually create information where perhaps there was none just based on what's most likely to be there。

 So more on that before long too。 But you'll see that all of these thoughts on the screen。

 all of these pixels， so to speak， or just a grid up down left， right to compose these pictures。

 And we're fortunate to have three volunteers on stage who kindly just before lecture began。

 created their own pixel artwork so to speak， on this here， easel。

 if you guys would like to spin this around， let's see。😊，What it is you've been working on。😡。

And if you'd like to introduce yourselves as our three artists today first， Yes， I'm Talia。

 I'm a junior at the college studying economics with possible computer science secondary。😊，Hi。

 my name is Boet， I'm from atBU welcome。I'm Marcelo Caesar， Se computer science student。

 been working as a software engineer since age 16。 Nice， well welcome to you all。

 and if you would like to give us a description of what it is that you built out of pixels here。

So we built a firework。Okay， nice， and it's very blocky because what we've given them is post it notes。

 each of which represents one of these pixels or dots。 Now typically it might be black or white。

 but the post it notes we have here are pink or blue。

 So each of these represents a dot on the screen。 and I gather you did one other that actually conveys maybe a bit more information if you want to reveal version 2。

😡，And thus， we have yet more pixel are。 So maybe a round of applause for what our volunteers were able to do using pixels alone。

 Thank you。 We have as always， limited supply of delicious Super Mario Brothers orreos for each of you。

 Thank you so much for coming up。 But thank you。 But the point here really is that there's only so much you can do when you just have dots on the screen。

 Now， of course， the image that we saw a moment ago of these stress balls is much higher quality。

 It's much higher fidelity or more specifically much higher resolution。

 and resolution just refers to how many dots or pixels are on the screen And the smaller they are。

 And the more you cram in on the screen， the clearer and clear the images are。

 But at the end of the day， even this here P art represents what's going on on your phone。

 your laptop， your desktop， your TV nowadays， because all it is is this grid of pixels。 Now。

 before we can actually write code that actually manipulates these kinds of images we need to understand and we need to have some new syntax for navigating files。

 not just text， but files stored somewhere on the。😊。



![](img/8f310f169bb1b17e412b37f8847977db_6.png)

![](img/8f310f169bb1b17e412b37f8847977db_7.png)

Computer somewhere on the server。 But let's consider how we might store even information like this。

 but we'll make it simpler。 Here is a grid of zeros and onesClearly。

 But I would argue that each of these might as well represent a pixel an individual dot。

 And if that dot is a0， it's representing the color black。 If that dot is a one。

 it's representing the color white。Given that， can anyone see what this grid is a picture of。

 even though it's using zeros and ones and not post it notes。Like this here。Yeah， and back。

It's a smiley face。 How do you see that Well in a moment， it's gonna to be super obvious。

 But if I actually get rid of the ones leaving just the zeros there。

 you have the zeros that were there just a moment ago。

 So what this translates to typically on a screen is not a pattern of zeros in ones literally on the screen。

 but a pattern of dots。 So again， white might be one and black might be one might be white zero might be black but we pictured it course on our screens as this actual grid。

 but that's really all we need inside of a file to store something like an image。

 we just need a pattern of zeros and ones。 But of course having more colors would be more interesting。

 And if you actually have a larger grid， you can do even more with pixel arts and in fact。

 for fun at the beginning of the semester， we have a staff training with all of the teaching fellows course assistant teaching assistant and we gave them all this Google spreadsheet and we sort resized all of the rows and columns to just be squares。

 instead of the default rectangles And then we encourage them to sort of create something out of this。

 and in fact， just a few。here are some of this year's creations creating essentially images using Google spreadsheets by treating each of the cells as just a dot on the screen。

 So here we have a team who in a few minutes made a super Mariio world， a bigger canvas， of course。

 than this year El here。 we have a pixelixbased version of scratch here。

 we had an homage to the Harvard Yale football competition And then here we had a character of some sort。

 So this is what the team here did。 And actually if you'd like to play along at home at the risk of distracting you the entirety of lecture。

 If you go to this URL here， It'll actually give you a copy of that same blank spreadsheet。

 But let's talk about representing not just zeros and one in black and white but actual colors。

 And so recall from week 0。 when we talked about how to represent information colors among them。

 we introduced RGB， which stands for red Green blue。

 And it's just this kind of convention of using some amount of red。

 some amount of green and some amount of blue mixed together to give you the actual color that you want。

 Well， it turns out in the world of computers。 There's a。😊。



![](img/8f310f169bb1b17e412b37f8847977db_9.png)

![](img/8f310f169bb1b17e412b37f8847977db_10.png)

way for describing those amounts of red， green and blue。 At the end of the day， it's of course。

 just bits。 and equivalently， it's just numbers like 72，73。

33 was the arbitrary example we use in week 0 for the color yellow。

 But there actually tends to be a different notation by convention for representing colors that we actually see today。

 too， as we explore the world of memory。 So here's a screenshot of Photoshop。

 If you've never used it before， this is like the color picker that you can pull up just to pick any number of millions of colors by clicking and dragging or typing in numbers。

 But notice down here。 we've picked at the moment， the color black by moving the slide or all the way down here to the bottom left hand corner。

 And what this user interface is telling us is that there's0， red，0， green，0。

 blue and a conventional way of writing this on a screen would be literally a hash symbol and then3 pairs of digits。

0，0 for red 0，0 for green，0，0 for blue。 if by contrast， you were to pick the color。

 say white in Photoshop。 It gets a little weird。Now it's a lot of red， a lot of green， a lot of blue。

 as you might expect， cranking all of those values up。

 But the way you write it conventionally is not using decimal， but using letters of the alphabet。

 it would seem here。 So F F for red， F F for green， F F for blue。 More on that in a moment。

 When it comes to representing red， here's a lot of red 2，55，0， green，0， blue。

 And so the pattern is now F F 0，0，0，0。 Before I reveal what green is， what probably should it be。

What pattern， yeah。Close， not 0，0，0，0， FF， but。😡，0，0， F F 0。

0 because it seems to be following this pattern indeed from left to right of red， green blue。

 So 0 red 255 green，0 blue and thus 00， f 0，0。 And then lastly， if we do solid blue， it's 0 red。

0 green， a lot of blue and thus0，0，0，0 F。 So somehow or other F is apparently representing is apparently representing the number 255。

 And we'll see why in just a moment。 But recall that in the world of computers。

 they just speak 0s in ones。 And we've seen that already in sort of black and white form。 We。

 of course， in the real world tend to use decimal instead of binary。

 So we have 10 digits at our disposal0 through 9。 But it turns out that in the world of graphics and colors turns out in the world of computer memory。

 it tends to be convenient not to use binary per se， not to use decimal per se。

 but to use something called hexaadecimal。 where as soon as you need more than 10 digits total。

 you start stealing from the English alphabet。 So the next few numbers or digits rather or。A，B，C， D。

 E F。 And there's other systems that use even more letters of the alphabet。

 but this is probably the last we'll discuss in any detail。 So in this case。

 we have a total of 10 plus 1，2，3，4，5，6 So 16 total aka hexadeimmal or what we might call base 16 in the capitalization actually doesn't matter。

 it's conventional to use uppercase or lower case。 So long as you're generally consistent。

 So hexa implying 16 decimal。 So hexadeimmal notation here or otherwise known as base 16 for mathematical reasons that go back to our discussion in week 0。

 So here's some of that same reasoning from week 0。

 how might we go about representing using two digits in hexaadeimmal。

 different numbers that you and I know is decimmal。 Well。

 if we consider this as being the 16 to the zeros place 16 to the one's place。

 And if we do out that math， of course， that gives us the ones place and the 16s place。

 So we've only changed the base， not the story from week 0。 So if we were to start representing。



![](img/8f310f169bb1b17e412b37f8847977db_12.png)

actual values in hexadeadecimal。 here are two zeros。 So that's one times 0 plus 16 times 0。

 which of course， gives us the number you and I know is 0。

 So in hexadecimal and in binary and in decimmal， it's the same way to represent the number you and I know as 0。

 But here now is the number one in hexadecimal。 Here's the number 2。 Here's the number 3，4，5，6，7，8，9。

 So it's identical up until this point to our world of decimmal。

 But how do I count up to what you and I would call 10 in decimal。

 According to what we're seeing here thus far。Yeah。

 so now it goes up to A because a would apparently represent what you and I know is 10。

 B represents 11。 C represents 12，13，14，15。 How though， do I count up to 16， yeah。Exactly。

 so not 10 quote unquote， but one0 because the one in the second column here to the left actually represents the 16s place。

 So it's 16 times 1 gives you 16 plus 1 times 0， gives you 0， So 16 in total。

 So this now is the way the number you and I would think of as 1718192021 dot dot dot。

 And if we go all the way up as high up as we can count well what's the largest digit apparently in hexadecimal。

 the smallest is clearly 0。 and the biggest I said was F。 So once you get to FF。

 the math gets a little annoying。 But this is now 16 times 15 plus 1 times 15 And what that gives us actually is the number you and I know as 255。

 So we saw it in Photoshop， we've seen now in hexadecimal。

 this is not math that you would ever do frequently but indeed it's the exact same system as week 0 just with a different base。

 But why all this additional complexity。 Why are we jumping through these hoops introducing yet another one to give us。

Some pattern like this of FF。 Well， it turns out that hexadecimal is just convenient。 Why， Well。

 if you have 16 digits in your alphabet，0 through F， how many bits。

 How many zeros and ones do you need to represent 16 different values。😡。

It's four right because you've got four bits that's two possibilities for the first times  two times 2 times2。

 so that's 16 possibilities，2 to the fourth power and if you've got four bits represented by a single digit it's just convenient in practice for computer scientists and programmers。

 So F might indeed represent 1111 but that's not a full byte which is8 bits and no one counts in units of four in computing it's always in units of like 8 or 16 or 32 or 64 or the like So it turns out though because hexsmal lends itself to represent four bits at a time。

 well if you just use two of them， you can represent 8 bits at a time in 8 Bs is a byte which is a common unit of measure and this is why even Photoshop uses this convention as you color programs as does web development more generally of using two hexsmal digits just to represent single bytes because the one on the left represents the first bits。

 the first four bits， the one on the right represents the second four bits。 So it's not a big。😡。



![](img/8f310f169bb1b17e412b37f8847977db_14.png)

Deal per se。 It's just convenient， even though this might feel like a lot all at once。

 Any questions then on。Heexa Desimal。Yeah， in the middle。No。Okay， no questions on Hex atsmal。

All right， so with this system in mind， let's go about considering where else we might see this in the computing world。

 and I would propose that we consider as we've done in the past our computer is really just this grid of memory。

 for instance， where each of these squares represents a single byte and I proposed a couple of times already that when we talk about a computer's memory。

 we can think of them as each of these squares as having an individual location。

 like I spitballed back in the day that maybe this is the first byte， the second byte。

 the third byte， maybe this is the billionth byte so we can number all of the bytes inside of a computer。

 Well， it turns out as we'll see today in code， computers typically use numbers indeed to represent all of the bytes in their memory and they typically use hexadeimmal notation for such by convention。

 So what do I mean by that technically if we were to start numbering these and count it 0 as most programmers would this is byte 0。

1，2，3 dot dot dot this is byte 15。 But if I wanted to keep going it would be then 1617。

But that's not the true in hexadeadecimal。 So instead in hexadeadecimal。 Once you hit the 9。

 you'd actually use a through F just as I proposed。 Meanwhile， if you kept going thereafter。

 you would have10， but as you noted， this is not 10。 This is  this is 16 here。171819。

 And so here's where things get a little weird。 I'm saying 16。

 I'm saying 17 and you're obviously seeing what any reasonable person would read as 10 and 11。

 So there's this dichotomy。 And so we need some convention for making clear to the reader these are hexadeadecimal numbers。

 not decimal。 Otherwise it's completely ambiguous。 And the convention there。

 which you might have seen in the real world。 even though it's a bit weird is just a prefix hexadeadecimal numbers with 0 x。

 It's not doing anything mathematically， it's not multiplication or anything like that。

 Just 0 x means here comes a hexadeadecimal number hereafter。 just distinguish it from decimmal。

 And you can see that even though we don't have enough room for 255 B。 you start。

See patterns that we haven't even talked about yet。

 because we're just using those two columns as the one's place， the 16th place and so forth。

 Capital or uppercase is fine。Allright， so with that said。

 let's actually do things more technically interesting。

 like looking back at some code that we've already seen and seeing what we can actually glean from this newfound representation of memory location。

 So I'm gonna go over to VS code here where I've opened my terminal window but no code file yet。

 and I'm gonna go ahead and create a file called addresses do c because I want to start playing around now with the addresses of information in my computer And to do this。

 let me do something super simple first。 let me include standard Io do H。 let me do an in main void。

 no command line arguments。 And then in here， let me do exactly the line of code we just saw declare an int called N set it equal to a default value of 50。

 and just so that the program does something noteworthy。

 let's have it actually print out percent I backlash n and plug in that value of N。

 So this is like week one stuff just creating a variable and printing out its value just to make sure that we're on the same page。

 So let me do make addresses in my terminal window。😊，And when I do dot slash addresses。 No surprise。

 I should indeed see the number 50。 But let's consider what that actually does inside of the computer now by flipping over。

 for instance， to the same line of code and translating it into this same grid。

 So here's a grid of memory。 And I don't necessarily know where in the computer's memory it's gonna end up。

 So I'm picking spots arbitrarily。 But I know that an int typically is 4 bys on most systems。

 And so I've used 1，2，3，4 squares。 and the first four that I assume are available down here。

 and I'm calling this n， and I'm putting the value 50 in it。 So literally。

 when you write that line of code int n equals 50 semicolon。

 the computer is doing something like this underneath the hood might be over here might be over there。

 but I've drawn it simply down there。 But that means that that 50。 And that variable n in particular。

 live somewhere in the computer's memory。 And where might it live。 Well， I don't really know。

 And frankly， I'm not gonna care ultimately after today， but let me。

po that if all of these bytes are numbered from 0 on down， maybe this is a address O x 1，2。

3 for the sake of discussion。 So it's a hexadecimal number 1，2，3。 It's not 123。 It's 1，2，3。

 but in hexadecimal just because it's a little easy to say。

 But that variable N clearly must live at some address。 So can we maybe see this。 Well。

 it turns out that in C， there is a bit more syntax we can introduce today that actually gives you access to the locations of variables inside of the computer's memory。

 The first of these is literally an ampersand。 And you might pronounce that the address of operator using a single ampersand you can actually ask the computer at what address is this variable and then the asterisk here might be known as the dereference operator。

 which allows you to take an address and go to it kind of like following a map X marks the spot。

 the star will take you to that location in memory so you can see what's actually there。

 So what do I mean。well let me go back over to BS code here and let me go ahead and change my program to be ever so slightly different as follows I'm going to still declare n just as before to have the value of 50。

 but instead of printing out an integer per se， I'm going to print out an address and it turns out the format code for that using printf is percent P。

😡，And if I want to print out now the address of N， recall that I have these new two new capabilities。

 the first of which is germane， the ampersand will get me the address of n。

 So let me go back now of Vs code and let me make a change whereby I'm gonna change the percent I to percent p。

 which is gonna show me an address as opposed to an integer per se。

 but I need to tell print what address to show So I don't want to print out n because that's literally the number 50 I want to print out the address of n like where is it in memory。

 So here I prefix it with an ampersand。 And now if I go back into my terminal window。

 make a address is again dot slash addresses。 I'm not gonna get as lucky as seeing Ox 1，2。

3 probably because I got even more memory than that in this computer but when I hit enter。

 I do indeed see O X something And if I zoom in here enhance， if you will。

 it happens to be at this moment in time on this server Ox7 FFCc 3 a7 F FB。

 So it's a big address that's。Really big number。 if we actually did all of the math。

 but who really cares。 It's just the fact that it exists somewhere is the only point for now。

 So this percent P symbol that we're passing into printf as a format code is leveraging the fact that C supports what are known as pointers。

 So a pointer is really just an address。 the address of some variable that you can even store in another variable called itself a pointer。

 So what do I mean by this。 Well， if a pointer is an address。

 we can start to tinker with the same idea as follows。 Let me actually go back to VS code once more。

😡，And play around with syntax like this。 So let me still declare a variable called n and set it equal to 50。

 But let's actually create an actual pointer， a variable whose purpose in life is not to store a boring number like 50。

 but the address of some value。 And so the syntax for that is admittedly weird。

 if you want P to be a pointer， a variable that stores an address。

 you literally say int star for reasons we'll sort of see And this is different from the star I mentioned earlier for reasons we'll also see soon。

 but int star P means hey compiler give me a variable called P inside of which I can store the address of an integer。

 What address do you want to put in there。 Well now I can borrow that same syntax from a moment ago I can use ampersand n。

 which is gonna say， hey compiler give me or hey computer， give me the address of n itself。

 previously I didn't bother with the variable。 I just sent the address of n right into printf directly。

 but I can now play with it as follows。 Let me go back to V S code here。 I'll clear my term。

window and let's just play around with two variables。 So int star P。 So it's an asterisk。

 but most people would say star equals the address of n。 And now I can tweak line 7 ever so slightly。

 instead of printing out in duplicate ampersand N。 I can literally just pass in P for pointer。

 So I've not done anything really that interesting other than add a variable。

 but just to show you the syntax via which you can create a variable。

 whose purpose in life is to store one of these addresses。

 So let me go ahead and now and do make addresses once more。😡，Thought slash addresses。

 and we should see indeed pretty much the same idea。

 the address at which end happens to be now that I've recompiled and actually run my code。😡。

But it gets a little more interesting than that。 I can do one more thing when it comes to my computer's memory in VS code here。

 let me clear my terminal again。😡，And let me see if I can perhaps kind of reverse this process。 if P。

 if N is 50， and P is storing the address of N， wouldn't it be interesting if I could somehow express go to the address of N and tell me what is there。

 So to do that， I'm just kind of undoing all of the intellectual work I'm doing here。

 But if I want to print out an integer at some location。

 I can go back to percent I just print an integer as always。

 But P now is storing the address of someplace。 It is the treasure map。 so to speak。

 So if I want to go where Xmarks the spot。 the syntax for that I claimed a moment ago is star P。

 So star P means go to that address， Don't print the address。

 go to that address and show me what's inside of the computer's memory there。

 So now if I go into my terminal and do make addresses and do dot slash addresses。

 what should I see on the screen when I hit enter。50， so I indeed see now 50。

 Now here's where it's an unfortunate choice of syntax from the authors of C decades ago。 Clearly。

 I'm using star in two different locations。 and suffice it to say it doesn't represent multiplication in either of them。

 It's being used to represent addresses somehow when on line 6， I specify a data type like int。

 And then I have a star and then the name of a variable。

 that is the syntax for declaring a pointer for declaring a variable that will store an address。

 What address， Well， ampers and n， whatever that is O X something。

 When you do a star and then the name of a pointer without specifying a type。

 this just means go there。 So the star clearly is related to memory is clearly related to。

 it's unfortunate that it's the same symbol。 It would have been nice if they pick maybe a different symbol for a punctuation。

 but they mean slightly different things in that context。

 On line 6 were declaring the pointer declaring a variable called P that's going to point to。

Integers location。 But when I say star P， that means go to that actual location。

 So just try to keep that in mind， even though it's ever so slightly subtly different。

 So what's going on then inside of the computer's actual memory。 Well。

 let's consider that in pictorial form again。 So even though I've written the pointer in this way int than a space than star P equals Amperserson and semicolon。

 that is the conventional way， that's how you'll see it on most websites most textbooks。

 technically speaking， I will admit that it might actually be easier to understand if you actually move the asterisk a little to the left。

 because this makes visually， I think even more clear that int star is the type of the variable P as opposed to the star being somehow attached to the variable name itself。

 However， you might also see it written with a space on either side。

 which I don't think really helps anyone。 But the point is that white space does not matter in this context。

 and the conventional way is to do it by prefixing the variable name with the star。

 and this avoids getting into trouble when you declare multiple。At a time。

 But if it helps you to think about it， you can think of it as int star as being the type。

 It's not just an int per se。 So with that said， let's consider now the canvas of computers memory inside of which we're storing n in now P。

 So previously， I propose that N is maybe yeah， maybe it's shown in the bottom right hand corner of the screen。

 So N is storing the number 50 here。 But technically n live somewhere。 and for simplicity。

 I'm gonna to claim it's at Ox 1，23 rather than the bigger actual address we just saw。

 But what about P Well P itself is another variable that I declared separately。

 So it's got to live somewhere in the computer's memory。 And it turns out by convention。

 pointers take up more space。 they typically use 8 bys nowadays rather than just4。

 Why is that if you've got 8 bys， you can count even higher， you can have even more addresses。

 you can have more memory in your Mac， your PC and phone。 That's a good thing。

 So pointers tend to be 8 bys， which is why I've used 8 squares on the screen here。 But what。



![](img/8f310f169bb1b17e412b37f8847977db_16.png)

![](img/8f310f169bb1b17e412b37f8847977db_17.png)

Actually， P storing。 Well， it's just storing a number。 Yes， it's technical an integer。

 but that integer is itself being should be thought of as the address of some other value。

 So N is down here at O X1，2，3。 P is up here at Who knows what address doesn't matter for the sake of discussion。

 but its value。 What it's storing with its pattern of 64 Bs is apparently O X1，2，3。

So how does this help us Well， if you think about this a little more abstractly who cares about what else is going on in the computer's memory。

 it actually tends to be helpful to think about this pictorially as being a little something like this at the end of the day you and I even when we start writing code in C that uses pointers generally you and I are never going to care about the actual addresses。

 even though I showed you OX7， something that's not generally useful information。

 it suffices to know that it exists somewhere and let the computer figure out how to get there and so very often when talking about pointers and addresses more generally。

 people actually abstract them away so to speak， so instead of literally writing on the screen or the whiteboard when discussing this OX123 what the actual address。

 who cares what it is， it suffices that it's a a value that leads me to the other value that I care about。

 sort of the treasure map as I described it earlier。😡。

So let's now connect this maybe a little more metaphorically。 So Carter。

 maybe here you might have noticed that we've had for a while now these two mail boxeses on the screen on the stage。

 So this white one here is labeled P to represent our pointer variable。

 Carters is labeled N representing our actual integer。

 and what's really kind of going on here is that if I were to access the value inside of P。

 much like we saw it up here。 that's like opening this up and figuring out what the actual value is Now this itself is a little arcane O x1。

23。 And so if we actually do this a little more metaphorically。

 we can maybe do this and actually point R way。😡。

![](img/8f310f169bb1b17e412b37f8847977db_19.png)

![](img/8f310f169bb1b17e412b37f8847977db_20.png)

If you don't mind。So here we have。A big pointer。Oh， forgive me。 I guess we'll use this one here。

 Okay， so we have this big pointer that's essentially pointing at the location and memory that we care about be it O X1。

2，3 or something else。 And then if we dereence this， that is used the star notation。 star P。

 that's like asking Carter to go to that location。 Open up the mailbox andvoila。

 what value do you have there。 Wallila， maybe a big round of applause for Carter for having。😊。

Practice this。Beforehand with me。哎。That was mostly just an excuse to use the phone fingers today。

 But with that said， that's hopefully a helpful metaphor， honestly， because these pointers。

 these addresses actually tend to be among the more arcane topics and see that even if things are kind of clicking right now。

 as soon as you start writing code involving addresses。

 it's easy to sort of get lost in some of the details。 But metaphorically。

 these mailboxers are meant to represent really what's going on。

 mailboxes and the physical human world have addresses。

 I can go to that address open it up and then I can go to another address by following that treasure map。

 if you will， or pictorially here the arrow that's pointing from one location to another。

 So even though it's very weird syntax with ampersands and asterisks and the like。

 it's just addresses in memory much like mailboxes in the real world。 So with that said。

 let's maybe begin to take off certain training wheels by revisiting what strings are as we've been using them thus far。

 So here's a line of code and see that we've been using since week1 really。

 where I declare a string variable called S。😊。

![](img/8f310f169bb1b17e412b37f8847977db_22.png)

![](img/8f310f169bb1b17e412b37f8847977db_23.png)

![](img/8f310f169bb1b17e412b37f8847977db_24.png)

Sa it equal to quote， unquote， high。 Now， technically high is three letters or two letters in a punctuation symbol。

 But how many bys is is that string taking up。Is it  one， two， three or was it？I'm seeing it here。

 it's4 or y。😡，Yeah， there's always a null character that even though you don't see it on the screen。

 that is what terminates every string we claimed a while back。

 So if I were to draw this maybe high ends up in the computer's memory down here。

 bottom righthand corner， but it is indeed4 bys， not just three， because secretly。

 there's always been that null character， even though we as programmers don't often have to type it explicitly ourselves。

 That's with a double quotes do for us， it terminates the string with that null character。

 Now recall from week two， when we talked about arrays。

 we started playing around with strings as really just being as of characters。

 So we call them a string， but we could treat them as as of cha， so to speak。

 So if the string was called s S bracket 0 would give us the first cha。

 S bracket 1 the second S bracket 2 the third。 And if you're really curious。

 S bracket 3 would give you the last hidden null character。

 which we saw on the screen as just a zero。 when we printed it out while tinkering with some actual code。

 But technically today， logically， it would seem that it's also true that H exclamation。



![](img/8f310f169bb1b17e412b37f8847977db_26.png)

In the null character must clearly live at some address。 They much clearly live in their own mailbox。

 so to speak。 So maybe for the sake of discussion， this H today is at O x 1，2，3。

 but recall that arrays are characterized by contiguousness from left to right。 So if H is at O x1，2。

3， it must be the case that I is at O x 1，2，4， I is at 1，2，5 and the null character is at Ox 1，2。

6 because those are one B apart。 And I deliberately shows numbers here whether it's decimal or hexadeimal。

 It doesn't matter。 These differ by just one B themselves。

 So that's what implies that they're indeed adjacent or contiguous in memory。

 But what is S then when I declared S to be a string。

What is it that's been going in S all of this time if clearly S is actually this thing here。😡。

Well strings have kind of been a white lie for a few weeks because S itself technically is a pointer。

 S is the address of this string。 So the string is somewhere in memory。

 but S itself is a separate variable that gives you a clue as to how to find all of those characters in memory。

 So if you had to guess just intuitively now， if this is the string actually in memory。

 That is this is the array of chas in memory， what would logically make sense to put as the value of S。

😡，A pointer， specifically。嗯。A pointer to H。 And how would I express that， What's the actual value。

 O X。1，2，3 might very well suffice as the value here of S。 Now， why might that be。 Well。

 that essentially gives you enough information to find the beginning of the string high in this case。

 Now you might think， well， wait a minute， how does it know about the second character in the third character。

 But now if you kind of rewind in time wait a minute。

 maybe now the null character actually makes even more sense from week2， why。

 because if S is technically storing the location of the beginning of the string。

 Someone's got to keep track of where the string ends presumably。

 And that's effectively the string itself， because humans decided decades ago。

 let's just null terminate every string with a special character，0， all0 bits，8，0 bit specifically。

 But that's enough information。 The sort of treasure map leads you to the beginning of the string。

 And then you can use a four loop， a while loop， whatever to walk through the string。

 And that's what printf does。 And you just stop as soon as you see that null character。

So this then is what a string actually is。 S is and has always been since week1， a pointer。

 so to speak that actually refers to the start of that array of characters。 and frankly， again。

 who cares about the Ox 1，2，3 specifics， we can abstract that away and actually just treat S as literally an arrow that points to the beginning of that string because it will be rare that we actually care about where this thing physically is。

😡。

![](img/8f310f169bb1b17e412b37f8847977db_28.png)

In the computer's memory。Now， before we see this in code， any questions on this revelation， yeah。Yes。

 have pointers gotten larger as computer's memory has increased over the decades。 to try an answer。

 Yes， like back in my day， we were limited to like 2 GB of memory total。 Well， why too， Well。

 if you had 32 B memory or if you use 32 B to represent addresses 4 B， as was conventional。

 you can count recall as high as 4 billion values。 but generally。

 numbers are both negative and positive。 So that haves it。 So the reason decades ago， computers。

 PCcs Max could have no more than 2 GB of memory was because literally the integers being used。

 the pointers being used were only 4 B that is 32 B sorry，4 B that is 32 B long。

 And so you literally you could buy more memory， you could buy a third gig or 4 gig。

 but you literally had no way mathematically to express all of those bigger locations。

 So it was effectively useless in that case。 in more modern times， computers 10 now to use 64 B。

 which allows you to count crazy high。 And that's more than enough to address bigger chunks of memory。



![](img/8f310f169bb1b17e412b37f8847977db_30.png)

Really good question， others。On memory thus far。All right。

 well let's translate this a bit of code by going back over to V S code here and let me propose now that we revisit maybe a simpler string example as opposed to these integers。

 So let me go ahead and throw away all of this integer related code let me go ahead and for the moment。

 include C50 H。 so that we have access to string and other things as in week1。

 and let me do a string S equals code unquote high in all caps and let me do a simple safety check S backlash n S just to make sure everything worked as it did in week1。

 So make addresses dot slash addresses， and I should indeed see high on the string。 Well。

 let's now kind of tinker with what's going on underneath the hood。

 And now things can get a little more memory specific。

 So I'm still going to declare S as a string up here。 But you know what。

 instead of printing out the string itself。 let me actually treat S as the pointer， I claim it is。

 I claim a string is just an address。 So I have this new syntax today percent P to print out pointers to print。

Addres let's see what S actually is。 Let me do make addresses again。 dot slash addresses。

 And there it is。 It's not as simple as O x123， but it is at location。 O x 5，5 C 7 C 6，7，0，8，7，8，0，0。

4 All right， who really cares specifically， But if we poke around a bit more things might make a bit more sense。

 Let's do this。 Let's also print out the address using percent P of how about the very first character of S。

 So the very first character of S is known as S bracket 0。

 we did that in week 2 treating a string as an array。 But how do I get the address of a character。

 Well I have our new symbol today， Ampersand。 So even though this looks like a mouthful Ampersand S square bracket。

0 square bracket， it's just two ideas combined S bracket 0 gives you the first character in the string S and adding an ampersand at the beginning says tell me what that address is。

 So if I recompile this code make addresses。😊，Slash addresses。Even if you don't remember the value。

 O X， whatever， What are we going to see on the screen。At a higher level。

Perhaps the same exact thing。 Why， Well， S is just an address。 But what does that mean， Well。

 it's just the address of its first character。 And we saw that per our picture a moment ago。

 So can I see the contiguousness of this。 Well I'm gonna resort to some copy paste just for times sake。

 even though this is going look a little silly， And I could certainly use a loop instead。

 but let me print out the second location， the third location and heck。

 even the fourth location what's the fourth location of that null character。

 if I now do make addresses again and dot slash addresses and zoom in。

 I don't really care about what these are specifically。

 but notice the first two are indeed the same because the first represents S。

 the first represents the first character of S， which now I reveal exactly the same idea。

 and the next ones are literally just one bite away ending in 5，6 and 7 respectively。 So again。

 the numbers in themselves are not useful actionable information。

 but it does let us actually see what's going on under。The hood so just to rewind for a moment。

 let me actually go back to the original version where I'm printing out the string itself using percent S。

 let me remake addresses to make sure that okay it still prints out back it still prints out high but what has been going on now all this time well let me go back to our simple line of code that we've been using since week one which gave us a string called S setting it equal to the value of high let me propose now that strings were indeed this white lie and if I can unnecessarily dramatically say here we take like the training wheels off and reveal that all this time。

😡，String。String。Is probably actually what， technically。Yeah。A char star， that was amazing。

 thank you for that。So。It's a char star， which admittedly at first glance。

 just makes a simple idea look unnecessarily complicated。 and that's why in weeks one。

 we indeed introduced these training wheels whereby we CS50 invented the data type called string just to kind of hide this lower level detail。

 if you will string for us as an abstraction Now that is to say string is not a CS50 specific word like every programmer in the world knows what a string is。

 it is a sequence of characters， it is an array of characters but in C technically decades ago when it was invented。

 they didn't think they didn't decide to create an actual data type called string because especially if they were among those more comfortable char star is equivalent and it achieves the exact same thing。

 even though at a glance， we didn't want to start week1 with that lower level detail Que here in front。

😡，Sure， can I clarify how the star makes it a string。

 So we've up until now been just calling it a string so that S is a string and that's a sufficient mental model。

 but technically what is a string， I claimed pictorially with my grid of memory that a string is really just an address。

 It's really just the address of its first character I then try to demonstrate as much encode code by using percent P and showing you literally S is a value like OX something and literally its first character is that that same address OX something So here when I claim that string has never really existed except within the confines of CSs 50。

 technically the data type of a string is best expressed as char star Y while a string clearly can't just be a cha because a char by definition is a single character。

 a string we already know is a sequence of characters but how can you represent a sequence of characters。

 you can call it a char star which is a different data type that we're introducing today for the first time and the star just means that S。

is not a cha。 The star means that S is the address of a char。 And by convention。

 it's the address of the first char in a string。So with that said， if I go back to my actual V。

 S code over here， I can change literally。Char string to char star S。

 I can get rid of the CS50 library， our so-called training wheels。

 which has been the goal for the past few weeks to put them on initially and then take them off quite quickly so now this is the same program and percent S is still the same S is still the same everything else is still the same all I've done is change quote unquote string to quote unquote char star which obs the need for the CS50 library and if I now do make addresses and dot slash addresses high behaves exactly as it would so this is now raw native C code without any training wheels without any CS50 scaffolding that just uses these basic building blocks and primitives Other questions on this。

😡，Correct， why don't we use the， the ampersand symbol for this。 And though we did earlier。

 So in this case， there's no reason for an ampersand because the ampersand tells tells you what the address of a variable is。

 I'll concede that it probably would be a little more consistent。For us to do this。

 which is maybe where your mind is going。 Now， never mind the fact that that looks even worse。

 I think syntactically。 it's a reasonable it's a reasonable instinct。 but it turns out that， too。

 is what the double quotes are doing for you。 the C compiler called clang is smart enough to realize that when it sees double quotes around a sequence of characters。

 it wants to put the address of that first cha in the variable for you。

 But when we had a variable like n， which we created， you have to distinguish n from its address。

 So that's why we prefixed N with an amperscent。 But the double quotes take care of it for you。

 Other questions。On these here， addresses。No all right well， beyond that。

 let me propose that we tinker with one other idea to see how we actually invented this thing called a string。

 Well， I claim that string is just char star。 you've actually seen this technique before。

 know it was just a week ago that we tinkered with structures。

 custom data types to represent a person and recall that we had a structure of a name and a number representing a person。

 but more importantly， we had this keyword type def。

 which defines your own type to be whatever you want。

 Now we used it a little more powerfully last time to actually represent a whole structure of a person having a name and having a number。

 but at the end of the day， we really just invented our own data type that we called obviously person。

 but and that represented indeed this structure。 but type de was really the enabling element there。

 And so it turns out with type de， you can create any number of data types of your own。 for instance。

 if you just really can't get the hang of calling an integer an int。

 you can create your own data type called integer that itself is a synonym for。



![](img/8f310f169bb1b17e412b37f8847977db_32.png)

Because the way type F works， even though this ones even simpler than the struct is you can kind of read it from right to left。

 This means give me a data type called integer that is actually an int。

 And that's the same thing that happened a moment ago Give me a data type called person that is actually this whole structure。

 but an integer is even simpler。 Now， most people wouldn't do this。

 This really doesn't create any intellectual enhancement of like the data types。

 but you could do it if you really want it more commonly。

 And you'll see this in code in the future would be not just a typeef， something like an integer。

 but it turns out curiously， C has no data type for a byte。

 Like there's no built in obvious way to represent 8 bits and store whatever you want in them。

 However， you can use what's called a U in underscore T， which is a data type that comes with C。

 And frankly， those more comfortable might simply use this data type once you sort of commit to memory that it exists。

 But honestly， for most of us， it's a lot more convenient to think of a byte as being its own data type when you want to write code that manipulates。

or two or more byte。 Would't it be nice to have a data type called byte。

 So it turns out that you can represent a byte， which is a bit using an unsigned integer with8 bits。

 And this is just a data type that's declared in some other C header file but long storyory short。

 you'll see and use this before long。 But it's just a synonym to make things a little more user friendlyly like person like string like byte。

 So what is in the C 50 do H header file， among other things literally this line of code。

 This is the single line of code that we deploy in week1 onward that teaches Kang to think of the word string as being synonymous with char star so that you all never have to type or know or think about char star until wonderfully today in week4。

 a couple of weeks later instead。 So that's all we've been doing。

 That is the technical implementation of the training wheels。

 It's just using a custom data type in this way。

![](img/8f310f169bb1b17e412b37f8847977db_34.png)

So how about one other maybe pair of examples here with our addresses such that we can tinker a little bit further。

 It turns out that once everything in the world is addressable using these pointers like using numeric addresses to represent where things are in memory。

 you can actually do something called pointer arithmetic and here too， we。

 the programmers generally don't care what the specific values are， but we care that they do exist。

 And if they do exist， we can maybe do some arithmetic on them and like add one to go to the next byte。

 add two to go to the next next byte， add3 to go the next next next byte and so forth。

 So pointer arithmetic literally refer to doing math on address。

 So how do we translate this into something actionable， let me actually go back to Vs code here。

 and let me propose that we do something like the following I'm going throw away my first printf here and I'm instead going print out this string character by character just like we did in week two。

 Let me go ahead and call print。Pass in percent C for a single char， backslash n， comma。

 and now I want to print out the first character in S using array notation。

 what do I type to print the first character in S？😡，Yes。Yep， oh here。 S bracket 0。

 So S bracket0 gives me the first character in S。 And let me copy paste just for demonstrations sake here inside of my same curly braces and print out the second cha and the third。

 And I don't care about the null character。 I just want to print the string itself for now。

 So even though this is jumping through way more hoops than just using percent S and print the whole thing at once。

 It's again， just demonstrating how we can at a lower level， manipulate these string。

 So let me do make addresses。 dot slash addresses。 And yet again。

 we see somewhat stupidly one per line H I exclamation point。 I can， of course。

 fix that by getting rid of this I can get rid of this。 And I can leave the last backlash n。

 So let's just make it a look a little prettier， make addresses dot slash addresses enter and I can print it out all on one vme。

 But now using pointer notation。 turns out we can do one other thing。

 which admittedly for now is gonna to feel like unnecessary complexity。

 But it's actually a really helpful tool to add to our toolkit。 so to speak。

 whereby I could instead do this。😊，To print out the first character in S， yes。

 I can treat it as an array and get the zeroth index。 However， what is S。

 S is just the address of a string， What does that mean。

 S is the address of the first char in the string。 So if I do star S， what's that gonna print。😡。

Presumably H， right because if the first character in S is H。

 then star S will go to that address and show me what's actually there。

 And let me go ahead and do this again。 Let me kind of copy paste twice。

 and then tweak this a little bit。 I want to go to the next by over。 Well I could do S bracket1。

 Allright， But I could instead go to S plus one。 And I could instead go to S plus2 there by doing what we're calling pointer arithmetic math on addresses。

 And now if I go ahead and rerun， make addresses dot slash addressesila。

 there isops I forgot my back slash n。 Let's fix that just to be ti dot dot slash addressesila。

 there is our high。 Now this is not how a normal person would print out a string。

 but it does go to show you that there's not really been any magic like these characters are just where we predicted they would be。

 And now that you have this star notation， the dereference operator which means go。😊。

There you have the ability to access individual values。

 you even have the ability to ask where those things are by using ampersands as well。

 but it turns out that the reason that we introduce the array syntax first is that the array syntax is what the world would call syntactic sugar for exactly this when you say S bracket zero the compiler is essentially doing star S and saving you the trouble when you do S bracket1 the compiler is essentially saving you the trouble of doing star in parentheses S plus one and same for the third char as well So all this time pointers have been there underneath the hood。

 they are what allow us to go to very specific memory locations。

 they are going to be what allow us soon to start manipulating files。

 whether it's photographs of stress balls or csi style content but for now I think we should take our10 minute break where whopi pis will now be served in the trans so you intend。



![](img/8f310f169bb1b17e412b37f8847977db_36.png)

All right， so we are back and we've clearly drawn too much attention to the stress ball today because now we're all out of these and will be pies but more next week in the meantime。

 though， we thought we'd now use some of these new building blocks。

 this idea of being able to manipulate underlying addresses to revisit a couple of problems that we kind of swept under the rug previously by avoiding these problems altogether。

 So by that I mean this let me go over to Vs code and let me create another example called compare c whoses purpose in life in a moment is's gonna be to compare values in kind of a very weak one way2 So let me go ahead and include cs50 do H let me go ahead and include standard I o do H let me do in main void no command line arguments and in here。

 let me just get two integers using get int as follows So get int and we'll ask for I let's go ahead and get int and ask for J just so that we have two things to compare and then I'm gonna do something super simple So if I equals equals J then let's print out as we。

😊。

![](img/8f310f169bb1b17e412b37f8847977db_38.png)

Did in the past same backslash N else。 if they're not the same， let's， of course， print out。

 for instance， different。 So super simple program that we use the first time around really just to demonstrate conditionals。

 But now we'll use it to tease apart some subtleties。

 So let me go ahead and compile this with make compare。😡。

Dot slash compare and we'll compare like one and one for I andJ respectively。

 Those are of course the same。 Let's compare one and2。 those are of course different。

 So long story short， this program seems to work and we won't dwell much further on it。

 but let's consider for a moment what's going on inside of the computer's memory when that code is executed so here's my canvas of memory maybe I ends up over here。

 maybe j ends up over here， each of them I've drawn as four squares because integers are typically four bytes or 32 Bs so I has the value 50 here。

 I has the value 50 so I accidentally typed1 and one but assume that I typed 50 in both cases。

 they both live at these two separate locations。 All right so that's all fine and good and when we compare them of course 50 and 50 or1 and one are in fact the exact same。

 but what if we actually compare different types of values。

 let me go back into Vs code here and instead of integers let's still using the CS50 live。



![](img/8f310f169bb1b17e412b37f8847977db_40.png)

![](img/8f310f169bb1b17e412b37f8847977db_41.png)

Maybe use some strings instead。 So let me go ahead and change my I and J to maybe S and T respectively。

 So string S equals get string。 and I'll ask for S unquote and then string T equals get string and then I'll ask for T unquote and then down here。

 I'll compare S equals equals T。 So here's the code almost the same logically。

 I'm just getting different data types instead。 still using the CSF library。

 So let's do make compare again， dot slash compare。

 And let's type in something like high exclamation point， high exclamation point。

 and that's interesting。 Allright， let's maybe try it again。 So maybe lowercase high， high， no。

 those are different， let's do it one more time。 like high by okay， so it half works。

 So it seems to be saying different， no matter what Well， my might that be。 Well。

 let me first just peel back a layer。 We already know that strings。Don't technically exist。

 they're really char star and string here is char star。

 so does this reveal perhaps implicitly why S&T are being thought to be different even though I literally typed I twice。

😡，Yeah， on line 9 here， I'm really just comparing the addresses that are in S and T。

 And that's why I change it to cha star just not to change anything。

 but to make it even clear that S and T are in fact， addresses， They're not strings per se。

 they're the address of the first character in those strings。

 And even though they happen to be the same words that I typed in。

 it would seem to imply that they're ending up in different places。

 So here's another canvas of memory for this program。 And here， for instance。

 might be S with enough room for8 bys up here， as a pointer here maybe is where high ended up for this particular story。

 Well， what's actually going in S。 Well， if H is at O x1，2，3， I is at O x1，2，4 and so forth。

 What's going in S is Ox1，2，3。 But when I use get when I use get string a second time and type in high exclamation point。

 even the exact same way uppercase or lowercase， T is ending up presumably somewhere else in memory。

 So it's maybe using these 8 bytes over here。 the same letters coincidentally by。



![](img/8f310f169bb1b17e412b37f8847977db_43.png)

Of how getstr works are ending up in the computer's memory。

 maybe down there bottom right hand corner， those are presumably different addresses， O456457458459。

 so what's going to go in T is its value。😡，O X 4，5，6， according to this example。

 And so when you literally compare S equals equals T， No， theyre not the same。 They are， in fact。

 different。 even if what they're pointing at happens to be the same。

 So the computers taking us literally， if you compare S and T respectively。

 it's going to compare what their values actually are And their values are the addresses of the first letter of this string and the first letter of this string。

 respectively。 And if those addresses differ， which they clearly do。

 they're going to be deemed different。 Now， you might wonder， well。

 this just seems stupidly inefficient， why put the same string in two different places， well。

 maybe the string needs to be changed later on， and we might want to have two different versions thereof。

 And frankly， the first time you call get string， it does its thing。

 the second time you call get string， it does its own thing。

 it doesn't necessarily know how many times it's been called in the past。

 And so maybe there's no communication between those calls。

 And so surely it's gonna to do the simple thing and just create more memory。

 create more memory for each of those strings duplicate。Though they may seem to be。

 So what does this imply， Well， you might recall that we avoided this problem altogether just a week ago by using what solution on line 9。

 I did not compare two strings using equals equals last time。😡。



![](img/8f310f169bb1b17e412b37f8847977db_45.png)

Exactly， we used the stir compare function， which is in string dot H very deliberately at the time because I didn't want to trip over this mistake at the time until we were sort of ready and had the vocabulary to discuss it。

 but I did not do S equals equals T， even though logically that's what you're trying to do compare for equality。

 But if you know now what a string is， it's an array of characters starting at some address。

 you really need someone something to do the heavy lifting of comparing every one of those chars from left to right。

 we did it ourselves last time by just implementing it in code or two weeks ago。

 but stir compare does it for us So stir compare S comma T actually weirdly returns three possible values。

0， if they're the same a positive number if one comes before the other or a negative number if the opposite is true。

 So St comp remember can be used for alphabetizing things or ASI batizing things based on those ASI values。

 So this version， if I open my terminal window now and do make compare。

Dot s compare and type in high and high now in fact they're the same because Stir comps doing the work of comparing them cha by cha and if I do high and by those are now in fact different so we avoided the problem last time for this very reason that simply using equals equals would not have worked yes。

😡，Oh good question。 So when using St compareare， the documentation says that it will return0 or a positive number or a negative number。

 It doesn't tell you a specific number。 So the magnitude of the integer that comes back actually has no meaning。

 it might very well be10 in negative one， but there's no guarantee。

 And so you can check for equality equals equals or you should check for greater than or less than but not specific to a certain number。

 So it just gives you relative ordering， it doesn't give you any more detail than that。

 All right so if we were to now take this lesson a step further just to hammer home this point whereby these strings S and T must clearly live at different addresses。

 let's actually try to see this in code。 So let me go back to V S code here。

 let me go ahead and just remove all of the conditional code。

 And instead do something old school like print out percent S backlash n and print out S。

 then let's go ahead and print out percent S again but print out T just to see the two strings as。

Duplicative。So here I go make compare dot slash compare high exclamation point。

 high exclamation point。 And， of course， they're actually the same。

 But if I actually want to see where S and T are， I can change the percent S to what。😊。

Prescent P percent P here。 And I don't need to use an ampers and before the S or the T because they are already addresses。

 That was today's big reveal。 And it turns out that printf is smart enough when you use percent S。

 and you give it an address or of S or the address in T to just go there for you。

 So printf is been doing all of that for us with percent S。

 but percent P is actually going print out those raw addresses。

 So let me make compare dot compare high once high twice and here now we should see the addresses at which high lives。

 and it's not gonna be as simplistic as O x 1，2，3 and x 4，5，6。

 but if I go back to my terminal and hit enter indeed。

 I get two different headecimal values that makes clear that if I were to naively compare them with equals equals they are always going to be different。

 even if I typed in the same words。 So there's implications now of this。

 especially if we want to start changing things in memory。 So for instance。

 let me create a new program called。

![](img/8f310f169bb1b17e412b37f8847977db_47.png)

![](img/8f310f169bb1b17e412b37f8847977db_48.png)

And in here we'll start somewhat similarly with CS50 do H we'll start with standard standard Io do H and preemptively I'm gonna to go ahead and include string H as well I'm going to declare main as not taking any command line arguments and this time I'm just gonna get one string S with get string and I'll prompt the user for S and now let me go ahead and naively say this let me give myself a new string called T and just set it equal to S。

 My instinct being this is how I've copied integers before this is how I've copied floating point values before。

 this shortly is how I copy strings using the assignment operator as usual let me now for the sake of discussion proposed that I want to capitalize the first letter in T but not the first letter in S so logically based on week two syntax I'm going go into the T string go to location0 and set it equal to two upper of t bracket0 so recall we introduce。

Upper is just a handy function for capitalizing things。 There's too lower。

 and there's a bunch of others as well。 I didn't include the header file yet， though。

 So I'm going to go back and include anyone remember where these are。Yes， C type dot H。

 And it's fine to look that up in the manual if you ever need it。

 So here I am a little naively capitalizing the first letter in T。 technically speaking。

 I should check what the length of t is first because if there's no characters there。

 If it has zero charged。 There's nothing the uppercase。

 But for now I'm going keep it simple and just blindly do that there。

 Now let me go ahead and print out with percent S。 the value of S。

 now let me go ahead and print out with percent S， the value of T。

 and I should see one lowercase S and one capitalized T。 All right， here we go。

 make copy dot slash copy， and I'm going deliberately type it in lowercase， high exclamation point。

 and we should see now。Hh， they're both capitalized， it would seem。Intuitively， why might that be。

Exactly， the addresses are the same。 So if I do use the assignment operator and just do S equals t equals s semicolon。

 it's going to take me literally and copy the address in S over to T so that effectively they're pointing it the same thing。

 So if we draw another picture here for instance， here maybe is S and here maybe is the lowercase high that I first type in down here in memory maybe that's at Ox1。

23 again and therefore that's what's in S。 when I then create the variable T by declaring it to be a string as well。

 that gives me another variable here called T but I'm just setting it equal to S。

 I'm not calling getstr again in this version of copy that was then compare in copy。

 I'm just literally copying S into T so that literally just changes the value to Ox123 also and if we abstract away all of these addresses that's essentially like S and T both pointing to the same place。

 So if I use S bracket 0 or t bracket 0， they are1 and the same。I use T bracket0 to use uppercase。

 It's changing that lowercase H to capital H。 but again， both strings。

 both pointers are pointing at the same value。 And again。

 this should be even clearer as of today if I go back into VS code and indeed take these training wheels off and treat string is what it is char star。

 which indicates that both S and T are just addresses which makes even clearer syntactically that this is probably the picture that's going on underneath the hood。

 Now just to make the code a little more robust， let me at least be a little careful here。

 if the string length of T is greater than0 then and only then should I really blindly index into the string and go to location 0。

 that doesn't really solve the fundamental problem。

 but it at least avoid a situation where maybe the user just hits enter gives me no characters and I try to blindly uppercase something that's not there。

 but there's still a bug there's still a bug。 So how do I actually solve。

Well it turns out we need two other functions that we haven't had occasion to use。

 but these are perhaps the most powerful and they're going to allow us to solve even grander problems next week when we discuss all the more things called data structures but for now let's very simply solve this idea of copying a string Let me go back into VS code here and let me give myself one more header file that's called standard lib for standard library So include standard lib H in which both of these functions。

 malloc and free are declared for me and now in my code。

 I'm going to behave a little bit differently here。

 clearly I got into trouble by just blindly copying the addresses。

 what I really want to do when I copy strings presumably and then uppercase one of them is I want to create a duplicate string a second array that is identical but is elsewhere in memory So the way to do this might be as follows instead of just setting T equal to S I should really call this brand new function called malloc which stands for。

Memory allocate， and it takes a single argument， which is just the number of bytes。

 you would like the operating system to allocate for you。 So whether you're using this on Windows。

 Mac O or Linux in our case， this is a way I can literally ask the operating system。

 Please find for me some number of bytes in the computer's memory that I can now use for my own purposes。

 So Maoc here。 I technically need at least three Bs。

 but that's not gonna be enough because I need a fourth for the null character。

 So I could put four here， but that's stupid。 I shouldn't just hard code a number like this we've seen。

 So I could probably do stirlang of S。To dynamically figure out how many bytes I want for the copy。

 but that too is not enough， because string length returns the human readable length。

 So H I exclamation point。 So I think I want a plus one in there too。

 So that just means get the length of whatever the human typed in。

 Add one for the null character to make sure that we're not under counting Now， what can I then do。

 Unfortunately， I need to do a bit of work here。 So let me actually go ahead now and do something like this for int I equals0。

 I is less than the string length of S I plus plus And then inside of this loop。

 I could copy into the I location of T， whatever is in the I location of S。

 Now this is a little buggy1， this is inefficient to keep asking this question。

 We talk about this in the context of design。 I should probably improve this by giving myself like a variable like n set that equal to the string length。

 and then do I is less than n again， and again， just so I'm not stupidly calling string length for。

Different times or three different times。 But this， too， is slightly buggy。

 and this one's very subtle。 This does not。Fully copy S into T。 Does anyone see the very subtle bug。



![](img/8f310f169bb1b17e412b37f8847977db_50.png)

That I've introduced， sorry。Yeah， I'm forgetting the backslash0。

 so even though I'm copying H exclamation point or whatever the human typed in I need to go one step further deliberately to make sure I also copy the backslash0 or at least manually put it in myself so I could solve this by either doing this up to n through n I is less than or equal to n or I could plus one here。

 that two would be fine or if I really want I could do this like t bracket the t bracket 3 equals quote unquote backlash0。

 but again I shouldn't get in the habit of hard coding things I could do string length of S and that would give me the last location in S which would also work but that two is stupid I might as well or just unnecessarily complex let's just do this change one symbol and boom now we're copying all three and the fourth character as well All right so with this said。

 let's go ahead now and make sure that t is indeed of length at least grade。😡。



![](img/8f310f169bb1b17e412b37f8847977db_52.png)

![](img/8f310f169bb1b17e412b37f8847977db_53.png)

than 0。Then let's go ahead and capitalize T as before and print out the results。

 So let me go ahead and open my terminal window， make copy， dot slash copy。

 And I'm going to deliberately type high in lowercase。 And now we should see disparate S and T。

S is now still lowercase， and T is now capitalized。 But why is that exactly， Well。

 let me actually go into save my computer's memory again and propose that if what I had before was this situation where S is pointing at this chunk of memory and T was accidentally pointing that same chunk of memory。

 What we really want to do is have T point at a new chunk of memory。

 And malloc is what gives us this chunk of memory， And then using that for loop。 can I copy the H。

 the I， the exclamation point and even the backslash 0。 So now this is a little subtle。

 But malloc is what gives me access to this new chunk of memory。 Maloc takes one argument。

 the number of bytes that you want。 It's a find for you。😊。



![](img/8f310f169bb1b17e412b37f8847977db_55.png)

![](img/8f310f169bb1b17e412b37f8847977db_56.png)

Take a guess what， what value is malloc returning。Conceptually， it's returning a chunk of memory。

 but that's like kind of hand wavy。What might Malck actually be returning？Perfect。

 Maloc is returning the address of that chunk of memory。 not the last address。 The first address。

 And here's a difference with strings。 This chunk of memory is not magically terminated with null for you。

 Like I had to do that with my for loop Maloc， and in turn your operating system does keep track of how big these chunks of memory are。

 So even though it's only returning the address of the first byte of that memory。

 the operating system is gonna know that it used up four bys here 4 bytes here。

 and it will keep track of that so that it doesn't give you an overlapping address in the future because that would be bad。

 your data would get corrupted。 but you similarly have to remember or figure out how many bytes are available thereafter。

 it's up to you to manage it as by putting a null character there yourself。

 So if I go back to my code now， let me actually harden this code just a little bit more as follows。

 whereby I can do this a little better， if I go back to VS code here。

 it turns out if something goes wrong and I'm out of memory。

Maybe I've got an old computer or maybe I'm typing something way bigger than three characters in like 3 billion characters and the computer might genuinely run out of memory。

 I actually should be in the habit of doing this if T equals equals a special symbol called null with two Ls。

 and I promise this would eventually exist， I should just return one now or return two。

 return negative one， return any value other than zero and just abort the program early。

 that means if Maloc returns null， there's not enough memory available and it turns out all this time。

 I'm going to do one other crazy thing， even though we've not expected you to do this thus far。

 technically when using getstring getstr， if you read the documentation， the manual。

 it too can return null because if you type in a crazy long string and the computer can't fit it in its memory。

 getstr needs to signal that' to you somehow and the documentation actually says that if get string returns null。

 then you too should not trust what's in it。 you should just exit the program。mediaIn this case。

 but there's one other improvement we can make here。

 and even though this is making the code seem way longer than it is。

 most of this I've just added is just error checking。

 just mindless error checking to make sure that I don't treat S as being valid or T as being valid when it isn't。

 turns out this is stupid。 I don't need to reinvent this wheel。 Certainly for decades。

 people have been copying strings even in C。 So it turns out there's another fun function called stir copy wonderfully enough that takes the destination as its first argument。

 the source as its second argument and that will for me copy S into T respectively。

 So that does the equivalent of that for loop， including the backslash0。😡，However。

 there's one other function recall that was on our cheat sheet a moment ago。

 whereby Maoc is accompanied by one other function called free。

 So free is the opposite of malloc when you're done with your computer's memory you're supposed to give it back to Windows to Mac OS to Linux so it can reuse it for something else。

 And frankly if you've ever been using your computer for like hours on end days on end and maybe it's getting slower and slower。

 maybe it's photoshop， maybe it's a really big document， generally really big files。

 consume lots and lots of memory if the humans who wrote that software be it Photoshop or something else。

 wrote buggy code and kept using malloc malloc malloc Maloc asking for more and more memory。

 but they never call the opposite function free， your computer might actually run out of memory and typically the symptom is that it gets so darn slow it becomes annoying to use and frankly the mouse starts moving very slowly maybe the thing freezes all together。

 the computer crashes， bad things happen when you run out of memory。

 So in my case here if I go back to VS code， it's actually on me in this language called。



![](img/8f310f169bb1b17e412b37f8847977db_58.png)

![](img/8f310f169bb1b17e412b37f8847977db_59.png)

To actually manage the memory myself so that when I have called malloc thereafter I had better free that same memory now I don't want to free it right away。

 I want to free it when I'm done with it， so frankly the very last thing I'm going to do in my program here is called free on T because T is what I malloced up here so at the very bottom of my program。

 I should free T。 and then just to be super nitpicky。

 let me return zero just to signify success at this point。😡。

Now there's a slight asymmetry which is a little inconsistent here even though getstring I'm going to imply is still allocating memory for me。

 it actually does use malloc， getstring and CS if these other functions are special。

 they manage memory for you， so you do not and should not free memory that getstr returns to you。

 we handle all of that for you， but that's a training wheel that's going to be taken off as of this week anyway。

 so it's kind of moot so not to worry， but I'm only freeing memory that I malloced。😡，All right。

 no then means。The what is null。 It is just an address。 And it's literally the address 0。

 So there's this theme。 like N U L recall was the terminating symbol。

 which just means the string ends here。 N U L L， which is not greatly named。

 but it's what humans went with years ago。 just means that this is the address 0 and what your computer does。

 is even though I've been playfully saying that oh。

 in the top left is address 0 and then one and then 2 and then3， the address 0 is hands off。

 Like it's kind of a wasted by that your computer should never use because the computer uses 0 as a special sentinel value。

 null to signify error。 So we're spending one by at a billions nowadays。

 just to make sure that there's a special symbol that's coming back that can indicate when something has gone raw。

 All right， That was a mouthful。😊，Any questions？On this copying of strings， this mallocing。

Or this freeing。OhAll right， so let me give you a tool with which to make some of this stuff easier so that when you make mistakes or have bugs。

 as you invariably will， you can chase them down without having to raise your hand without having to ask the duck。

 you actually have more technical tools with which to diagnose the problem yourself。

 And there's this new tool that will introduce today called Valgrind and Valgrin's purpose in life is to check your usage of memory for you admittedly it's an older program it's pretty arcane in terms of its interface and there's just gonna to be a mess of output on the screen。

 but there's gonna to be certain patterns of mistakes that you'll notice。

 and I'll demonstrate a couple of them now so you can see where in how you might go wrong。

 So I'm going go over to Vs code here。 I'm going to create a program called memory do C that is deliberately buggy but it's not gonna to be obviously buggy at first。

 So by that I mean this let me do include standard I O do H。

 Let me also include proactively standard lib do H so I can use malloc Let me declare main with no command line arguments and let me do something very。

😡，Simple， instead of just declaring an int called X。

 let me be a little crazy and manually allocate this memory myself。

 So in X just gives me an integer and it has since week 1。 But now that I have malloc。

 I can kind of take control over this process。 So let me declare not an int。

 but an int star called X。 So give me the address of an integer and let me store there the return value of malloc by asking malloc for。

 let's say，4 bys。😊，So I know that ints are  four bytes。 if I want four Btes， I just tell malloc。

 give me  four Bs。 Now， frankly， this is a little stupid。

 I shouldn't just assume that the int is always gonna be  four bys on everyone's computer。

 So there's this function you can start using called size of or this operator technically where you can say size of int。

 And even if you're on an older computer， for instance， really old at this point。

 size of int will return the correct value。 no matter what。

 you don't have to assume that it's in fact4。 But you know what。

 I actually like more than this number of ints。 let me actually treat x as an array of integers。

 So I could actually if I want an array of integer。 I could do this， give me three integers But no。

 no， let me not do week two syntax， let me do this myself as follows。

 let me treat this as three times the size of an int。 So that's technically gonna give me 12 Btes。

 but this makes x effectively an array。 and this is kind of deliberate now because if an array is just contiguous memory and malloc returns to a chunk of contiguous memory。

 you can treat what comes back from malloc as an array indeed。

That's what we're doing as strings we're treating chunks of memory as as of chars so let me do something arbitrary here let me go to x bracket1 and set it equal to 72 X bracket2 set it equal to 73 X bracket 3 set it equal to 33 and we did this a couple of weeks ago that's high but in ASI code let me go ahead and make memory and it seems to work fine。

 let me do dot slash memory and no problem like there's no error messages from the compiler。

 there's no runtime errors when I actually run the code but does anyone see any of the bugs thus far。

😡，What did I do wrong， Let me let me look a little bit back yeah。

It doesn't seem to know when the array ends or more specifically。

 I'm not respecting when the array ends because I'm sort of stupidly starting at one then two then three。

 But technically， if I asked for three of these things， I should have done bracket 0， bracket 1。

 bracket 2。 And there's a second more subtle bug that you would only know from today， yeah。😡，Okay。

 I don't necessarily know when one integer ends and the next one begins。

 That's actually not a problem because on a given system， integers are always the same size。

 So the computer can be smart enough to go from here，4 bys this way，4 bys this way，4 bys this way。

 That's okay。 Strings are problematic， because who knows how big the sentence was that the human typed in。

 But there's a more subtle bug。 What have I not done。😡，I didn't call free。

 so I didn't practice what I just preach anytime I now like I call free。 But again。

 per my terminal window， neither of these bugs seem obvious。

 you might submit this code or deploy it to your software and be none the wiser。

 but a tool like Valgrin can actually help you find these things。

 So let me increase the size of my terminal window。 let me run this command Valalgrind on my program。

 So dot slash memory is how I ran it a moment ago。 just like debug 50。

 you type before the name of your program。 Valgrind， you type before the name of your program。

 and the output's gonna look crazy。 But。😡，This is useful。 Why So notice at the very top of this。

 we're just seeing what version of vgin we're using and what command we ran。

 But this starts to get juicy。 And I'll highlight this here。 In right of size 4。 In right。

 So writing means changing information， like setting a value or signing it a value。

 and this is useful here。 the problem is in memory do C at line 9。 So colon 9 means line 9。

 All right， so let me go back to my code。 look at line 9 and oh， interesting。

 So invalid right of size 4。 So it's cryptic。 but size 4， I know is the size of an integer。

 So I'm probably doing something stupid on line 9 involving changing an integer and sure enough。

 even though it's not super obvious x bracket Oh， obviously， this doesn't exist。

 So I have to change the problem。1 in two were okay， even though it's logically the wrong thing。 Now。

 I think this will get rid of this error。 So let me actually clear my terminal window and make it bigger again。

 let me。Recompile my code because I made a change， let me rerun vgrind of dot slash memory。😡。

And now that mirror went away。 there's a mess of output here， but that error went away。

 but this is interesting here Now，12 by in one blocks are definitely lost in lost record  one of1。

 So unnecessarily verbose。 But the hint here is that I somehow lost some bys。

 otherwise known as a memory leak。 So earlier， when I described an imaginary bad programmer who kept calling Ma。

 Mallock Mal and never freeing。 That's what's called a memory leak where you're sort of losing track of your memory and never freeing it again。

 So I've definitely lost 12 B in one block。 whatever a block is in this case。

 This is a little less obvious。 It's up to us to notice that， okay， wait a minute。

 memory do C line 6 is somehow germane， let me go back to oh， this is where I called malloc。

 And Valgarin doesn't necessarily know when I should free the memory， that's up to me。

 But I should probably free it at the end of my function， when I'm definitely done with it。

 because once you free your memory， you should not touch that variable again。 unless you。

Actually change what its value is。 So now， as I've done this。 And this program to be clear。

 does nothing useful。 Like this is just an intellectual exercise， not anything productive。

 Let me do make memory one last time。 dot slash， let's do vgri dot slash memory and let me grow my terminal window again and hit enter。

😊，And even though it's still kind of output， it's still kind of cryptic。

 at least it says no leaks are possible。 So now this is my own sort of teaching assistant telling me before I submit the code or before I deploy it to production in real software。

 that at least there seem to be no memory related errors。 So Valgrin is not for logical bugs。

 It's not for syntax errors。 It's for memory related bugs as of today。Questions on any。Of that。

No okay so what else can go wrong， We mentioned these in the past。

 It turns out that garbage values are a thing and recall that if you declare a variable。

 but don't give it a value with an equal sign and you just blindly start using it like printing it out or doing math on it。

 you might be manipulating a garbage value which is some number that's essentially remnants of your computer having been on for a while because if you're using this canvas and reusing it again and again。

 surely there's gonna be patterns of zeros in ones there that you didn't put there yourself。

 at least in the moment， they might be remnants of the past so garbage values are values of variables that you did not proactively set yourself as intended So we can actually see this。

 let me actually go ahead and whip up a really quick program here after shrinking my terminal window let me close memory do C let me go ahead and open garbage do C and in here I'll do include about standard Io H let's include standardlib do H actually。

😡，We don't even need standardlib。th。Let's go ahead and include standard Io do H and then int main void。

 and then inside of the curly braces， let's give me like a really big array of scores。

 like 1024 scores like if it's a really busy semester and then let me go ahead and just blindly iterate from I equals0 on up to I as less than 10。

24 and I'm not going to bother with constants， I'm just going to play around with these numbers for a moment。

😡，呃。

![](img/8f310f169bb1b17e412b37f8847977db_61.png)

And oh， thank you。Oh， cookies for you。 Okay， these are okay， here we go。 Okay， come on。

 thank you very much。 fars there。😊。

![](img/8f310f169bb1b17e412b37f8847977db_63.png)

Okay。Okay now everyone's really paying attention。 Allright so in my loop here。

 I'm just gonna to do something stupid like print out all of the values in the scores array using percent I。

 even though I did not put anything in this array。 So on line 5。

 I'm obviously declaring an array of size 1024 for that many ints。

 but I'm never actually putting values in there myself or with getin or any other function。

 So there's garbage values there。 There's presumably 1024 garbage values there。

 and we can now actually see them， let me make my terminal window bigger。

 let me make garbage no pun intended dot slash garbage and there's gonna be way more than even fit on the screen。

 but who cares， we just need to see a few， there are some of the garbage values in the array So make super clear that when you create variables of your own。

 you do not give them values of your own who knows what may be there。

 In some cases it gets automatically initialized for you to all zeros。

 but that is not always the case。 And in general， distrust。

variable unless you yourself have put a value there。

 So how now might we leverage this to to now might we think about potential problems。 Well。

 consider this code here， which this program2 is more for discussion than actual utility where at the top of it。

 I declare a variable called x and a variable called Y both of type pointer。

 So x and y are supposed to be the addresses of two integers。 malloc。

 the size of an int and store it in x。 So I'm giving myself space for x。

 even though obviously I could have done this weeks ago by just not using the star and just say give me an in X。

 Now I'm doing it like the low level way。 mallocing the X for myself。 I'm then saying go to X。

 go to that address in memory and put the number 42 there。

 I'm then saying go to Y and put the unlucky number 13 there。



![](img/8f310f169bb1b17e412b37f8847977db_65.png)

But what's worrisome about this line here after this line， this line， this line。Something's bad。

 I think。Yeah， I never allocated memory for y。 so specifically， I never assigned y a value。

 which means it's a garbage value， which is still a number。 Maybe it's 0。 maybe it's a big number。

 maybe it's a negative number。 And if if it's a positive number， it could be an actual address。

 like somewhere in the computer's memory。 But star Y means go there。

 Who knows what memory I'm touching。 That's how computers crash。

 if you touch memory that you're not supposed to。 So let me pretend that I didn't at least do this。

 And let me just forge ahead and set y equal to X。 So there's the same。

 And I think what that would mean is now if I do star Y and go to the address。

 that's the same thing is going to this address in X。

 And I think this will have the effect of changing the 42 to 13。 So this code is correct。

 so long as I don't blindly dereference Y by using star Y notation。 So this gets a little abstract。

 even though this is just an exercise here。 And our friend Nick Parlante。

 a professor at Stanford wonderfully put together a little clayation that's fun to take a look at。😊。

Whereby if I go ahead and open up this file will be introduced to someone who's a little famous in the world of computing named Binki。

 if we could dim the lights and take a look at what bad things can happen if you don't manage your memory properly。



![](img/8f310f169bb1b17e412b37f8847977db_67.png)

Hey Benki， wake up， it's time for pointer fun。What's up？Learn about pointers。Oh， goody。Well。

 to get started， I guess we're going to need a couple pointers。 Okay。

 this code allocates two pointers， which can point to integers。Okay， well， I see the two pointers。

 but they don't seem to be pointing to anything。 That's right。 Initially。

 pointers don't point to anything。 The things they point to are called pointees and setting them up a separate step。

 Oh， right， right。 I knew that。 Thepointees are separate。 So how do you allocate appointee。Okay。

 well， this code allocates a new integer pointee， and this part sets x to point to it。Hey。

 that looks better。 So make it do something。 Okay， I'll dereence the pointer X to store the number 42 into its point E for this trick。

 I'll need my magic wand of dereencing your magic wand of dereencing。 that's great。😊。

This is what the code looks like。 I'll just set up the number， and。Hey， look， there it goes。

So doing a dere on X follows the arrow to access its point E。 In this case， to store 42 in there。

 Hey， try using it to store the number 13 through the other pointer。 Why， O。

 I'll just go over here to Y and get the number 13 set up and then take the wand of de referencing and just。

 oh， oh， hey， that didn't work， say， Viinki， I don't think de referencing Y is a good idea Ca。

 you know， setting up the pointee is a separate step。 And I don't think we ever did it。 good point。

Yeah， we allocated the pointer Y， but we never set it to point to a point E。Very observant。 Ey。

 you're looking good there， Binki， Can you fix it so that y points to the same pointee as X。 Sure。

 I'll use my magic wand of pointer assignment。 Is that going be a problem like before。 No。

 this doesn't touch the pointees。 It just changes one pointer to point to the same thing as another。

😊，Oh， I see。 Now， Y points to the same place as X。So， so wait， now why is fixed， It has a pointee。

 So you can try the wand of de referencing again to send the 13 over。Okay， here goes。Ay。

 look at that。 Now， dereencing works on why。 And because the pointers are sharing that 1 point E。

 they both see the 13。 Yeah， sharing whatever。 So are we going to switch places now， Oh， look。

 we're out of time， but。All right， so our thanks to Nick。

 I can only imagine how many hours he spent making that happen。

 but hopefully gives you more of a visual as to what's happening when we're dereferencing these addresses and going to them and assigning values And when as per biggie's explosion there what happens when you dereference values you shouldn't So related there too。

 let me do this。 Let me go over to VS code and open up now a program I wrote in advance called swap c。

 and the purpose of this program is just to swap the value of two variables。

 So let me walk over to the code here and point out that in mainine I've got two variables X and Y。

 no pointers， no magic there， just x and y are1 and2 respectively。

 I've got a couple of printfs here saying X is percent I Y is percent I passing an X and y just so we can see that X and y are indeed1 and2。

 I'm then calling a function called swap which presumably should swap the two values。

 and then I'm just printing the exact same thing again my hoping that it's first going say12 then it's gonna say21 thus achieve。

😊，The idea of swapping here。 And here' swap， swap takes in two integers， A and B。

 though it could have called them whatever I want。 it temporarily puts a in temp。

 it then changes a to B。 it then changes B to temp。 And then that's it。 It's a void function。

 So it doesn't return anything。 but it does all of the mathematical work in here。 So this is curious。

 though， because when it runs， if let me open up my terminal window here， make swap dot slash swap。

 I should see one，2， and then to one but no， even though I do think this is logically correct。

 And actually we we're almost out of stock。 but we do have another box of cookies search can we get one volunteer to come on up here。

 maybe okay， how about you Yes， in the pink come on up A round applause， though， really。

 it's about the cookies now， I know。Okay。And what is your name？

My name is Caleb and I'm a first year concentrating computer science。

 All right welcome please have a stem behind the desk here so we have two no you can stand that's fine we have two glasses of water colored blue and orange respectively and I would like you to swap the values of these two variables so that the orange liquid goes in the blue glass and the blue liquid goes in the orange glass。

😊，Seems like a bad idea。Why is that？Because I can't get one out to put the other one in。

Because there's no third glass okay， correct。We do have what we generally call a temporary variable here。

 So here， let me give you a variable called Temp。 And if I give you this。

 how does that change things？ Well now I can take one Okay， very carefully。Nice， I'm trying。Okay。

 here we go。And now， you can put。B into A， if you will。Nice。And now， temp goes back into。That one。

All right， that was very well done， maybe a round of applause。Thank you。So。

This was just a cookie-based way of making clear that the code on the screen seems to work。

 If I scroll back down to the swap function， it seems to do exactly what you just did there whereby the temporary glass is where we put a。

 then we changed a to contain B， then we changed B to contain what was originally in a but is now in the temporary glass and now we're done。

 So it did achieve the stated goal。 And yet when I ran this code a moment ago。

 it was one to and then one to again， So why might that actually be Well here we can go back to some of today's fundamentals to consider what it is that's going wrong And in this case。

 it's actually related to a concept we introduced some time ago。

 whereby there seems to be an issue of scope， whereby sometimes when you're manipulating variables inside of curly braces thus defining their scope。

 it has no effect on values elsewhere。 The variables might not even exist elsewhere as we saw in the past。

😡，I mean by this。 Well with scope， it turns out with matters of scope。

 it turns out that in this case， the way I've implemented the swap function。

 I'm doing something a programmer would call passing by value。

 I'm literally passing in X and y by their values1 and2。

 another way of putting this is passing by copy So when I pass X and Y into the swap function。

 it turns out swap is actually getting copies thereof。 Now what do I mean by this。

 let's go back again to this picture of memory representative of what's in your Mac。

 your PC or your phone。 And if we zoom in on this chip。

 And we treat it more abstractly as this canvas， get rid of the actual hardware and consider what's going on inside of the computer。

 It turns out that there are conventions of how computers use this memory。

 and it's worth having a general sense of what goes where So generally speaking if this is a big rectangular region of memory。

 even though this is just an artist's depiction thereof it turns out that the top of your memory。

 so to speak is where machine code goes the zeros and ones that you compiled。



![](img/8f310f169bb1b17e412b37f8847977db_69.png)

edInto here。 So when you do dot s something or on a Mac or PC， when you double click or on a phone。

 when you single tap that loads your program's machine code。

 the app's machine code to the top of your computer's memory， strictly speaking。

 it doesn't have to be the top。 But for our sake， it's in this region here。

 That's how the computer can access all of those zeros and ones quickly。 below that， so to speak。

 or we're global variables go。 We haven't had many occasions to use these。

 But if you define a variable outside of main and outside of every other function and see it's what's called a global variable。

 So those get tucked specially up at the top。 So that they're accessible everywhere else in your program。

 Then there's something called the heap more on that in a moment， and it grows downward。

 So you have a lot of memory available to you here in the heap and you can keep getting more and more and more available to you。

 But at the bottom of this memory， is's what's called the stack。

 and the stack actually grows curiously in the other direction up and up and up。

 And it turns out when you use malloc and ask the computer for memory。

 it comes from this heap region specifically。😊，When you use functions with variables and arguments。

 you're using stack memory。 Now， the viewer will notice that this does not seem like a good thing if they're about to collide eventually。

 and bad things can and will happen when one overflows the other。 But more on that too in a moment。

 But let's focus for the moment on a stack。 when we do something like this swap function。

 So for instance， when we had code like this， which was bad It did not allow us to permanently change the values of X and Y Y。

 no pun intended here on the stack is where the very first function goes in your computer's memory。

 So main， if you have any variables， they go at the bottom of the computer's memory once you've loaded that program。

 So what do I mean by that。 Well， if you think back to the code a moment ago。

 it was things like X and y and so forth。 When main calls swap， swap goes above it on the stack。

 so to speak， And each of these rectangles， the technical term is frame。 So this is a stack frame。

 this is a stack frame。 and if swap called another function， another frame。Go on the stack this way。

 And then as soon as swap returns， though， that memory essentially goes away。

 or the computer forgets about it， even though the bits are obviously still there。

 you still have the hardware， but it's forgotten and main remains until main finishes and exits your program。

 But let's consider what's going inside of these stack frames。 So here's main at the bottom。

 And it had two variables。 X and Y。 Those variables were one and2 respectively。Main called swap。

 which had two arguments， A and B， also integers， which are effectively local variables also even though you're declaring them in the signature。

 the prototype of the function。 So when swap is called swap is using its frame of memory as follows room for a。

 room for B room for temp， not necessarily to scale。

 I just wanted everything to be a pretty rectangle。 What's going where。 Well。

 because functions in C pass values by pass by value that is copy a is a copy of x and B is a copy of y。

 but their separate byte。 this is a different memory location than this。

 this is a different memory location than this。 So we're just copying the patterns a bit from one to the other。

 This is passing by value， Aka passing by copy。 So what then happens just like our demonstration。

 we used temp cleverly whereby with this code here， we copy the value of a into temp。

 So that puts the number one here too， we then changed a to equal。B，So that's what happened here。

 We then changed B to equal temp。 So that changed the value there。 But then swap return。

 you went back to your seat， leaving A and B swapped。 Yes， but what was not swapped was。😡，X and Y。

 like you did all of this work correctly。 but in the wrong scope， you operated on copies thereof。

 So this swap function， while logically correct， will never solve this problem correctly as written。

 because we've been passing by value。 So today， we introduce a technique whereby you can pass by reference instead pass by pointer instead。

 because instead of just passing in copies， what if we actually tell swap where X is and where y is。

 not what it is and what it is， but where each is， then swap can sort of follow the proverbial treasure map。

 go to those locations and change them permanently。 So this was the bad code in red。

 And this is gonna to escalate quickly visually。 but it's just an application of today's ideas。

This is the correct solution now。 So let me do before in red is bad。 green after is correct。

 Why the way you specify pass by reference or pointer instead is you change swap。

 to take not two integers per se， but two addresses of integers。

 And the syntax for that today is just to add the star。 So int star and in star。 Meanwhile。

 the code down here has to change。 Temp does not have to change。 Temp is still just a variable。

That's ready for some value。But the A and the B and the B need to be rewritten as follows。

 So star A means go to the address A and get its value and put it in temp。

 just like you reached for one of the glasses and pour it in。

 star B means go to the value in B and grab it and then go to the value at a and change it to B that at B。

 And then lastly， this is not now sweat。 This is now colored liquid。

 This last line is go to the address B and put temp there instead。

 So the picture now is fundamentally different。 main looks the same still。

 But when swap is called effectively， and we won't bother with O X 1，2，3 or 4，5，6。

 let's just do it with arrows pointing at things。 A is a pointer to X B is a pointer to Y。

 So what do those lines of code tell us to do go to a。

 So that means this kind of like the old shoots and ladders game if you ever played。

 like follow the arrow。 And that leads you to the number one and store。In temp。

 So that one was straightforward。 go to the value in B。

 So follow the arrow that gives us two and put it at the location in a。

 which means put the two there。 The very last line of code now means get temp。

 which is obviously there and go to the address B and change it to one。

 So now even though we've not changed a and B at all per se。

 we've used them as little breadcrumbs to lead us to the right location in the computer's memory。

 So when swap returns this time， even though it's a void function， it has made a difference。

 and it's had this effect of swapping the actual original values of X and Y。

 The code admittedly is cryptic looking， it's not the most user friendlyly syntax。

 but this ability now to go to locations in memory and change what is actually there is what we've been given today with this new syntax of the star operator and occasionally as needed。



![](img/8f310f169bb1b17e412b37f8847977db_71.png)

The Ampersand one as well。Questions on this technique。

 which is admittedly like the most sophisticated of the examples thus far and will probably take time to get used to。

 yeah。

![](img/8f310f169bb1b17e412b37f8847977db_73.png)

I say that again， will this work here。Good question。

 Will this work if you're swapping the values of two strings instead of two ins， Yes。

 if you go to the address that the string represents and change maybe with a loop all of the characters one at a time。

 so it's going to be more complicated than this in green because you're going to have to change all of the individual characters probably reusing a temporary char instead of a temporary integer。

 but you could yeah。😡，Since integers have a fixed number of bits is can you ever run into a situation where you run out of memory。

 absolutely like your phone， your laptop， your desktop can only do so much。

 can only count so high because of these physical limitations。

 And hopefully its just you never reach that limit。

 But we'll talk in a couple of weeks time when we transition to web programming and databases and the metas。

 the Microsoft， the Googles of the world that have crazy large amounts of data。

 like the number of bits we use in those contexts is actually going matter for exactly that reason。

 if business booming。 and you've got lots and lots of data， lots and lots of users。

 you need to be able to count higher。 just so that you've seen the code actually in operation。

 here is， of course， my swap function down below。 And if I go ahead and change its prototype to take in pointers to A and B and similarly change the prototype up here。

 And if I go in and change a here to be star A to de referenceence it。 star B to de reference it。

 star A to de reference it and star B to D reference it。

 I claim now that this version of the code should now work。 In fact。

 let me go ahead and do make swap。

![](img/8f310f169bb1b17e412b37f8847977db_75.png)

![](img/8f310f169bb1b17e412b37f8847977db_76.png)

It didn't compile。 So why might that be。 Well， let me scroll up to see what the message is。

 incompatible integer to pointer conversion passing into parameter of type in star that's a lot to absorb。

 But clearly， the issue is with how I'm calling swap。

 So why is this will notice that now that my swap function expects as arguments pointers to integers。

 I can't just blindly pass in X and y which are integers。

 instead I do need to use our friend the new ampersand operator to pass in the address of X and the address of y。

 So now if I reopen my terminal window run makes swap and do dot slash swap now I see12 and then to1。

 So the code changes in this way and maybe this example more so than others makes clear y the star operator lets us go somewhere。

 but the ampersand effectively does the opposite and figures out what the address of something now is。

 All right， so what about these other locations in memory， Well， it turns out that indeed。

 the stack as we've described it grows up and up and up and。



![](img/8f310f169bb1b17e412b37f8847977db_78.png)

The stack here in this sense， is kind of like the stack of trays in the cafeteria or any of the dining halls。

 like there's one tray， another tray， another tray， another tray。

 But then you start removing them from top down。 So there's an ordering to them that will actually revisit next week。

 But this is not a good design in general， like you shouldn't be doing things like two trains on the tracks like barreling together toward each other in this way。

 But honestly， it's kind of the only way， because if you've only got a finite amount of memory。 Okay。

 sure， you could have them both grow in the same direction。

 but they're still going hit some impasse eventually， you're still going run out of space。

 So the way computers were designed years ago， is they use memory in this way。

 even though bad things can happen if you use too much stack space or too much heat space。

 So what do I mean by that。 Our example a moment ago。

 just had us call main and then swap and that was it。 So it's like two frames， No big deal。

 But if you call many functions again and again and again。

 if you do something recursively where you call yourself。 You're gonna pile。

 pile pile stack frames potentially， So you could start to hit the so-called he area。 Meanwhile。

 if you call malloc too many times。You might be growing down， down， down。

 down down and then overrun some of the stack memory as well。

 So bad things can happen when you overrun either of these。

 And those of you maybe with prior programming experience might have heard at least one of these terms heap overflow or more popularly stack overflow。

 super popular website for questions and answers about programming。

 the etymology thereof is exactly this idea of overflowing the stack and touching memory that you should not。

 whether it's memory down here or even worse memory over here as by something called heap overflow and these are specific examples what we'll start calling buffer overflows。

 buffer is just a chunk of memory and buffer overflows means overflowing using too much of that memory。

 and buffers are everywhere。 In fact， if you've used YouTube recently and maybe it's just kind of paused and spinning and spinning and spinning。

 maybe you're on a really bad connection like there's no more bytes in your buffer。

 there's no more video footage in the buffer because maybe you have such a bad connection。

 But if Google were to make mistakes。

![](img/8f310f169bb1b17e412b37f8847977db_80.png)

And try to download too many bytes at a time， they too could overflow a buffer。

 And if YouTube or similar apps have ever crashed， it could be because they're trying to use more memory than they actually should be。

 So these things are sort of everywhere Now as for these training wheels。

 we sort of took away the mystery of what a string is But what about all of these other functions we've been taking for granted now for a few weeks。

 you can and should still use them to solve some problems because frankly。

 C does not make it easy to get user input safely like period full stop like it is very nontrivial to get user input without running the risk of overflowing a buffer。

 why， well you're the programmer， how do you possibly know in advance how big of a string a human might type in tomorrow or the next week of the next day。

 you could try to be safe and allocate a million bytes all at once。

 but what if they type in a million in one characters you use copypae so much that they similarly overflow So getting user input is a hard problem。

Lets introducetroduce you to what the alternative would be and give an appreciation for what libraries like CS50s and others like it are actually doing for you。

 Let me go ahead and create our own version of get int and get string without using the CS50 library but using a standard C function called Scf and to do that let me go over to VS code let me create a new file called for instance。

 get dot C and then in get doc let's make a very simple program first that just gets an integer but again without using the CS50 library so let me go ahead and include the standard Io library let me go ahead and declare main as int main void and then inside of main let me go ahead and declare an integer end so that we have some place to put the integer that we' getting in from the user then let me go ahead and just prompt the user for a value for n so N colon space for instance because again I'm not using get int so I can't just call it to present the user with a prompt so I'm going to use printf to create my own prompt and now let me use this function scanf as follows。

I'm going call scanf and then I'm going to pass a scanf similar in spirit to printf a format code like percent I effectively telling scanf that what I want it to scan so to speak from the user's keyboard is in fact a single integer Now I'm going to close quotes and I don't need a new line because I'm not trying to print anything I'm trying to get something from the user using scanf but I do need to tell scanf where to put this integer Now if I want to put this integer in the variable n。

 It's not quite as simple as just passing n in because recall how variables are past this variable n is going to be passed by value。

 effectively a copy is going go to into scanf and so scanf's not going to have the ability to change that value but if you think back to how we swap two values and pass two values into that swap function in C well if we pass those two values in by their addresses So passing by reference so to speak。

 then the function swap in that case scan。😡，F in this case can actually go to that address and change the value。

 So to summarize， I'm gonna pass the scanf one argument。

 which is a format code and a second argument， which is the address of an integer into which to put the user's value After that I'm just going to go ahead and print out what's happened。

 So I'm going go ahead and print out the value of n followed by a colon followed by an actual placeholder percent I backlash n and I'm going to pass in now to printf the value n So to be clear I'm still passing n into printf just like we've been doing since week1。

 but I'm passing the scanf the address of n so that scanf can actually go to that address and change the value of n。

 So I think this is actually going to work， even though I've not used get in or any of the c50 library。

 let me go into my terminal run make get seems to compile let me do dotlash get and let me type in a value like 50 for n and indeed I should see spit back out me that the value I got was 50 So it turns out that getting an integer from users is relatively straightforward just use。

Scanf。 but， of course， to use scanf， you need to know a little something about pointers or addresses more generally。

 that was not knowledge we had in week1。 And so we do indeed use those training wheels of the C 50 library for the past few weeks so that we can get integers more easily And it turns out if the user types more than symbol integer or doesn't even type in integer。

 Scf isn't necessarily going behave as user friendly as get in might。

 So in the C50 library we do a more error handling for you as well。

 But let's consider now an implementation not of getting an integer but getting a string instead let me my terminal window and let me go ahead and erase all of this code。

 and instead focus this time on getting a string。 Well。

 we know we can't use string anymore at least if we're not using the C50 library but not a problem because know that strings are now char stars。

 So if I want to get a string from the user like getting I think a char stars。

 So let me call this string S by default。 let me go ahead therefore and declare a variable S that's going。

My string let me go ahead next as before and prompt the user for the value of that variable just by prompting them with printf。

 so nothing fancy there。 and let me try again using scanf to scan this time of string from the user's keyboard I'm going type scanf I'm going do percent S instead of percent I because I indeed want to scan a string in this case。

 and then I'm going go ahead and pass in just S And here at first glance seems to be an inconsistency because previously I did ampersand n but that's because in was an integer not the address thereof but in the world of strings as we now know a string is just the address of its first byte。

 And so if we declare S to be a char star aka string Well S is already in a address So I can just pass in S in this case to scanf without actually using an ampersand after that let's go ahead and print out the results。

 So let's just use printf。 let's print out a prefix like S colon again percent S as my placeholder and now backslash n because I'm。

on the screen。 and then let's go ahead and pass in S as always to printf。 So S is just a string。

 So just pass it into printf like that。 Well， let me go ahead now and I'm going to go ahead and compile this in old fashion way because we actually protect you from doing something like this。

 but I'm going go ahead and ignore the warnings you would otherwise see with make and I'm going go ahead and compile this with clang directly So clang O get because that's the name of the program I want to output but I'm going specify capital W no uninitized which is simply another command line argument that's going tellang not ton us about variables that are not initialized because case in point on line5 as some of you might have noticed I didn't initialize S to anything even null but that's okay because I want to forge head blindly just to make a point as to what's going on here and in fact。

 let's go ahead and compile this code as follows it does seem to compile even though make would have warned us that somethings awry。

 me go ahead now and run。Dot/lash get and this time not type in 50。

 but let me type in something like our familiar high exclamation point and hit En。😡。

I immediately get a segmentation fault， which means something has gone wrong related to memory。

 a segment of memory has been touched that I shouldn't have。 Well， why， in fact， is this。 Well。

 let's consider what it is we've been doing。 If this here is my computer's memory。

 And in the first case， I was just trying to get an integer。

 that was actually pretty straightforward。 because even if this memory is filled with a whole bunch of garbage values as personified here by Oscar the grouch。

 when I declared n to be an integer before， I just needed on this machine 4 Bs。

 which is the typical size for an int and I put the number 50 there。

 So it doesn't matter that there were these garbage values。

 I just went to those four bys after declaring a variable called n and overwrote those bits with some pattern of bits representing the number 50。

 But strings we now know we sort of fundamentally different。 If I go back to that same memory space。

 and I declare S to be a pointer， that is a char star。 Well。

 recall that pointers are generally8 Bs on modern systems。

 And so that's like taking eight of these bytes from memory and calling it。S， but the catch is。

 if I haven't initialized S to actually be a valid location as via calling malloc。

 there are still garbage values there。 That is to say patterns of bits that maybe been there always。

 but from some previous function that got called or some other lines of code if this program were actually bigger。

 So it's just some garbage value is filling that variable S。

 The problem though is that in my code now， when I call scanf and I tell scanf to scan a string from the user and to put it at that location S。

 Well， what is that location S， it's literally a garbage value。

 It's the equivalent of a foam finger pointing there there there。

 we just don't know because it's not a valid address And so I get that segmentation fault here in my terminal window because I've not initialized S to be some known value。

 I get a segmentation fault because effectively I've accidentally touched memory that I should not in fact。

 have done so。😡。

![](img/8f310f169bb1b17e412b37f8847977db_82.png)

![](img/8f310f169bb1b17e412b37f8847977db_83.png)

![](img/8f310f169bb1b17e412b37f8847977db_84.png)

So how do we fix this。 Well， clearly， I need S to point at some valid chunk of memory。

 And I could do that using malloc。 But frankly， in this case。

 I could do it even more simply by just declaring S to be like an array of characters as we might have in week2 So let me go ahead and clear my terminal window here。

 Let me go into get dot C and let's simply change what S is instead of a char star。

 which we know is what a string technically is， we can still implement strings as as of characters that's certainly still true。

 So let me go ahead and do that declare S to be an array of say four characters。 And in this case。

 I should have enough room for the H the I， the exclamation point and even that null character。

 the trailing backlash0 So now let me go ahead and build this make gets and because I'm not not initializing something this time I can use make as usual without getting yelled because I'm not yet doing anything wrong。

 Now let me go ahead and do dot slash get enter And in this case。

 it's ready to receive my H exclamation point enter。actually seems well why， because in this case。

 I actually had enough space for S because if I go back to my memory here because I've now redeclared as an actual array of four characters。

 that's like asking the operating system， for instance。

 for these four chas here and certainly I can fit H exclamation point and the null character into those four bytes。

 So there's not a problem。 but there might be a problem if the I or the user more generally types in too many characters。

 So let me go ahead and run dot slash get again。 let me type H exclamation point。

 but just to get a little aggressive。 let me kind of highlight that and paste it again again。

 again and again， and really type very excitedly a pretty long string that is surely longer than four bys。

 Well， unfortunately， I've only asked the operating system for an array of four bytes。

 So what's gonna happen with all of those extra highs， highs highs。

 they're just going to by default remain contiguous from left to right。

 top to bottom in the computer's memory。 but they're going to end up some of those characters。

At locations， I didn't ask the operating system for in this array。 So if I go back to V S code here。

 I've typed in a very long string， certainly longer than 4 B in total。

 let me hit enter and darn it there is another segmentation faults。 So in short。

 we you are going to see these segmentation faults any time you touch segments of memory so to speak。

 that do not belong to you that you didn't allocate space for as via an array or even via mall。

 And this is gonna to be a fundamental problem with getting strings。

 because I don't know in advance how long the string is going to be that the humans going type in。

 maybe it's for， maybe it's fewer characters， Maybe it's even more。 So what's the alternative。 Well。

 I could go in here， maybe and allocate， I don't know， like 4000 characters for S。

 But what if you type in and even longer string that's 401 characters or more I might still have these memory related errors。

 these segmentation faults。 So one of the reasons then， too。

 that we provide you with the C50 library and in turn， functions like get string is that get string。

Very， very conservatively walks through these users' input， by by bite by byte。

 one character at a time。 and what the CS50 library is doing underneath the hood is as soon as it realizes。

 oh the user gave us another byte， another byte we in the CS50 library are constantly allocating and reallocating more and more memory using malloc for you and effectively managing the memory required for that string So even though Scf exists。

 it's dangerous to use with strings and even with integers。

 it turns out it lacks some of the error handling that the CS50 library has thus far provided。

 how do we actually go about solving this， the way getstr actually works and the CS50 library is it kind of tiptoes it it gets one character from you and then checks if there's another one coming then it allocates more space for a second if there's still a third it allocates more space。

 more space， more space So essentially what Getstring does is it uses malloc again and again and again and it kind of lays the tracks down as you're typing in the keystrokes and hitting enter。

😡。

![](img/8f310f169bb1b17e412b37f8847977db_86.png)

![](img/8f310f169bb1b17e412b37f8847977db_87.png)

That we never assume how many characters you're gonna to type in。

 we dynamically allocate just enough bytes for you plus one extra for the null character and this is sort of a hoop that's just not fun to jump through when at the end of the day all you want to do is get input from the user so even with the training wheels officially off it's going to be annoying to get strings from users and see but it is easy with ins with floats with other data types and frankly we soon in two weeks pivot to Python which takes care of all of these problems for us and manages our memory but for now we have one final to do beyond Scf which is file IO which is a fancy way of saying input and output because now that we know a little bit of XxsMmal now that we know a little bit about pointers we actually have some more functions available to us that will let us actually manipulate files on a computer's hard drive like image files or text files or anything else we might want among the most common functions that are related to files are these here。

😡，Open is going to be a function that lets you open a file doing in what you might otherwise do by going to file open in a graphical program。

 F closed does the opposite。 It's the way you encode sort of click on an X and close a file。

 Nothing's going happen visually， but it's how you give access to a program to the contents of a file。

 F print F it allows you to print not to the screen， but to a file。 F scanf lets you read data。

 not from the keyboard， but from a file。 F read and F right or similarly used to read and write data from a file。

 but generally binary data like images or something that's not asking your uncode text。

 F is a function that lets you kind move around in a file left to right。

 kind of like fast forwarding or remindwinding through Netflix or similar when you want to jump to a different location in a video or in this case。

 a file。 And there's bunches of others as well。 So to give you a sense of what you can do when it comes to manipulating files。

 Let's write just a couple of final programs。 for instance。

 that let us manipulate some of this code for us。 In fact， let me go ahead and open up here in。

Yes code。A new file called say phonebook。 C。 and in phonebook。 C。

 we're going implement now a version of the phone book like we did in the past。

 but in this case we don't actually have a forgetful program that prompts the user with getstring for a couple of names and numbers and then just forgets about them all together。

 This version of the phone book is actually going to go ahead and save them persistently to a file for us。

 and for this， let me go ahead and open up just on my other screen here。😡。

But without flipping over just yet， let me go ahead and open up， give me just one moment。

So we have this ready to go。 Let me go ahead and create the file。 this program as follows。

 I'm gonna to cheat and save time by using the C50 library because I do not want to get into the nuances of getting strings character by character。

 which itself will escalate too quickly。 But let me go ahead and include the C50 library。

 the standard I O library and lastly， the string library for this particular case。

 in my main function now， I'm going to go ahead and open up a file called maybe phonebook do cv。

 if you've ever used a Cv file。 It's like a lightweight spreadsheet that you can open an Apple numbers。

 Google spreadsheets， Microsoft Excel， but Cv means that we're gonna separate all of the values by comma。

 So anywhere we want a new column， we actually use a comma as we'll soon see So how do I actually do this。

 I can open a file called phonebook do cv by literally using F open phone book do cv and I have to tell F open how I want to open it。

 do I want to open it for reading with R。 do I want to open it for writing with W。😊。

Or do I want to open it with a pending A And for something like a phone book。

 if I run this program again and again， I'm gonna actually do aend so that new contacts get added to the file and we don't overwrite it with W。

 Now， what is F open return。 It technically returns a pointer to a file。

 But this one's a little weird。 It's all capitalized。

 but it is a thing and see file in all cap star file is going be a pointer to that file in memory。

 So think of F open is opening the file and returning the address thereof in the computer's memory。

 All right， what do I want to next do， I want to go ahead and get two strings from the user like maybe someone's name。

Using get string again to keep things simple for now。 let me then go ahead and get another one。

 How about their number， using get string again， prompting for number。

 And I don't strictly need these training wheels。 So even though it doesn't really make a difference。

 I'm gonna at least change that to cha star。 even though I do want to keep using get string conveniently。

 And now I want to save this person's name and number to that Cv file。

 So I'm going to use not print f。 but F print F printing to that file variable。

 which is open in the computer's memory。 Now I'm going to go ahead and print out two strings。

 S comma S， then I want to go ahead and print out the name for the first placeholder and the number for the second placeholder。

 And for good measure， I want to move the cursor to the next line in the file。

 So I am going include a backlash N。 Then I'm going go ahead and F close that same file with F close。

 And that's it。 No more printing to the user。 But I claim that I'm gonna to be changing the file again and again and again。

 So let me try this。😊，Pwn book。Okay， dot slash phone book enter。

 And let's type in like David and how about plus 1，6，1，7，4，9，5，1000。Enter， okay， hopefully it works。

 Let's do it again。 dot slash phone book。 Carter will give him the same number as last time，4，9，5。

1000。And let's do how much just those two。 So let me go ahead now and reveal that we do have a file in here called phonebook dot CSV。

 So that does exist let me go ahead and do this。 Let me open up my file browser over here。

 I've got a lot of files I've created， here's phone book dot CV。 And if I click on it。

 there is the file that I just created separated by commas。 But even more interestingly。

 let me actually right click or control， click on this， download it to my max downloads folder。

 let me go into my downloads folder just for fun， And I've installed an advanced Microsoft Excel。

 If I go into my downloads folder and open up phonebook dot CSV。 We're going to see。😊。



![](img/8f310f169bb1b17e412b37f8847977db_89.png)

Oh， Apple numbers， not Excel， opening up， view my spreadsheets。 Allright numbers is kind of stupid。

 So there we go。

![](img/8f310f169bb1b17e412b37f8847977db_91.png)

![](img/8f310f169bb1b17e412b37f8847977db_92.png)

No， it just this isn't a Mac versus PC thing。 So now we have a phone book do CSV rendered in this format here。

 numbers presumes that the top row should be gray and not white as well。

 So it looks the formatting looks a bit off Anyhow， clearly。

 you could open this same file in a spreadsheet program like Microsoft Office or Apple numbers or of course。

 something like Google spreadsheets。 But let me do one other thing when it comes to copying files now。

 whereby besides making a phone book， whereby I clearly have the ability now to save strings in files and actually just for good measure。

 let me hammer home the point that any time we're dealing with pointers now。

 something could go wrong。 And if you read the documentation for F open。

 we should also check that file could be null。 maybe the file not found or something's not working on the server。

 And so just to be safe， we should return one there。

 So even not just Maoc not just get string any time a function returns a pointer。

 you should check if it's null because if it is per the documentation。😊。



![](img/8f310f169bb1b17e412b37f8847977db_94.png)

Almost always means something has gone wrong， so you should get out lest you trust the return value therein。

😡，So let me go ahead and do one other program here。 Let me create my own copy program。

 So up until now we've used commands like Rm and LS and C for copy。

 I can actually create my own version of Linux's copy program perhaps as follows let me actually go into Cp do C in this case let me include some familiar files standard Io do H let me include how about one other standard int do H for reasons we'll see now because in standard in do H is that you int8 type that I mentioned earlier。

 which is just means give me give me an8 bit value that's unsigned which means no negative numbers like it's just raw data it's not an integer in the positive or negative sense and let me just nickname that to byte just to make clear that I want to manipulate files byte at a time Let me now declare for the first time today a version of main that takes in an arg C takes in argc and takes in。

😡，Arg V， which is for command line arguments， technically though I'm not using the CS50 library in this version。

 So even that can now be changed and this is the canonical way and C to declare main when you want to get command line arguments using cha star instead of string So now I'm going to do two things。

 I want to open remember how copy works。 you specify two files the file you want to copy and the new name that you want to give to the copy。

 So it would be like Cp space old name， space new name at the command line。

 So accordingly I'm going to do this。 I'm going create one file and memory called source or SRC for sure。

 and I'm going set that equal to whatever is in Av1 in read mode， but just to be super specific。

 I'm going to use read binary mode。 I don't want to be copying text files。 I want binary data。

 zeros and ones like images So I'm going tell F open to expect binary data。

 I'm then going go ahead and create a second variable called destination DSST for sure。

 and I'm going open up whatever is in Argv2 the second file name at the command line。

But I don't want to write read this file。 Im want to write to it in binary using zeros and ones。 Now。

 let me do the copying one byte at a time。 It's a little inefficient。

 I should really do bunches of bytes at a time for speed。

 but let me just give myself one byte in a variable called B。 So byte is not a thing in C。

 It's literally a synonym I created just for the sake of discussion because we'll do this in the future as well。

 Now， let me go ahead and do this。 How do you copy a file from old to new。 Well。

 I think it would suffice to use a loop and just start at the beginning of the file loop all the way to the end of the file And within the loop。

 copy one byte from old to new。 So how do I do that I used F printf last time to write text This time I'm going to use a different function as follows while there are bytes to read from the file。

 and this one's gonna to be a mouthful。 So let me just type it out and then I'll explain it。

While that line is true， go ahead and write。😡，This line which is similarly a mouthful。

 so I'll type it first。And then explain what it does。Then I'm gonna to close destination。 Whoops。

 then I'm going to close source。 And I claim if I haven't messed anything up。

 this will now copy files for me。 How， so this is indeed a mouthful。

 but there's in function called Ereed， whose purpose in life is to read one or more bytes for you。

 How does it work， Well， just like。Swap just like scanf。

 you have to tell it where to load those bytes in memory。

 So if I want to put them in the byte called B， I can't just say B because that's pass by value。

 I need to pass by reference。 So I say the address of B is where I want you to put one by from the file at a time。

 How big as a byte technically I could just say one because we all know how big a byte is。

 but I'm just going be super proper and generalize this as size of B。

 So it just figures it out for me， just in case we ever do more than one byte at a time。

 how many bytes do I want to copy at a time，1， just to keep it simple。

 And where do I want to read those bytes from the source file。 F read， if you read the documentation。

 just tells you how many bys were successfully read logically it should either be one was read or0 were red based on what I'm asking it to do。

 I'm asking it to read one at a time。 So it's either going to succeed or fail。

 So I want to do this for as long as it succeeds because it's gonna to succeed until it gets to the end of the file。

 and then there's no more bytes to read at which point it will return。ro。

So now I do the opposite with Fite and it's almost the same line。 Where do I want to write that byte。

 Well， first， I tell Fite where to find the byte， go there and get the byte that was copied。

 It's this size， which is gonna be one。 but I did it generally one by at a time。

 please and write it to the destination file。 So if I now open up my terminal window。

 let me first make Cp to create my own copy program。 Let me actually open an image I came with today。

 Here's a happy cat from the internet。 and that's gonna be my original image。

 let me now go ahead and run this dot slash Cp。 I have to run dot slash because I want my version of Cp。

 not the one that comes with Linux。 So dot slash Cp cat dot jpeg and let's call it maybe my backup cat just in case I ever mess up the original enter See to work okay when I run now code of backup dot jpeg to open the copy there is that same happy cat So it's very lowlevel manipulation。

But it all results from mine now having the power to express myself in terms of locations and memory using pointers。

 understanding that strings and now files are really just abstractions on top of these lower level details。

 And from all of that is gonna to come some pretty powerful functionality。 In fact。

 among the things that you can now do as you'll soon see as manipulate at least simple files known as bitmap file。

 So BM is bitmap file， And it essentially implements images exactly as we began today as just a map of bits。

 a grid X Y coordinates of grids， each of which represents a pixel coordinate。

 a bitmap is a type of file with a BM file extension on a computer that stores images just like that。

 And now that you have the ability to not only think about images in this way。

 but write code that manipulates images， you can do powerful things all Instagram and Tiktk and Snapchat like filters nowadays。

 So， for instance， here is an image of the bridge。 the week's bridge across the river， here is。



![](img/8f310f169bb1b17e412b37f8847977db_96.png)

Black and white filter that we've applied by writing some C code， as you soon will。

 to change it from colorful to black and white。 Here's the original that you might see every day Here。

 mean， is a reflection thereof。 if you've ever flipped an image around on the X axis this can actually rotate the image even though this is the other side of the bridge over there。

 Meanwhile， heres a blurred version if it looks a little blurry like that's deliberate because we've essentially smudged all of the values by looking at every pixel looking up down left and right and blurring the effect to give it this effect here。

 Here is what's called edge detection whereby if you're feeling more comfortable。

 you can write code that at looks at these individual pixels。

 tries to figure out where the edges are just like a fancy computer might and then colorize it in this way as well and you'll be able to do all of that because images like these are just grids with coordinates with lots and lots of pixels。

 So what started quite simply now is going to be something you now have complete control over now that we've taken off these training wheels and it's cultural within computer science to understand ge humor like this And so the last。

Thing well do today。Is give you this joke to end on， which for better for worse。

 should now make sense。And those chuckles will suffice。This was CS50。

