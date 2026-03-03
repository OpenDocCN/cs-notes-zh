# 哈佛大学《CS50X 计算机科学导论｜introduction to computer science 2025》中英字幕（deepseek - P6：-06-CS50x 2025 - Lecture 4 - Memory.zh_en - GPT中英字幕课程资源 - BV1hFrxYPEfa

![](img/8c4f64e556c9e456e704dee6118981ae_0.png)

![](img/8c4f64e556c9e456e704dee6118981ae_1.png)

🎼Yeah。All right， this is C S 15。 and this is week 4 on memory。

 wherein we reveal topic that's actually fairly distinct to CS S 150 nowadays as an introductory course known as pointers。

 Indeed， Today is the day you can tell your friends that you learn something about pointers and in turn。

 how computers work underneath the hood。 I will say that this is the kind of topic。

 This is the kind of lecture where probably won't all sink in the first time around。

 think back to that fire hose that we showed in week 0。 In fact， all these years later。

 I still remember where I was on campus when finally， today's topics finally clicked for me。

 it was an office hours and Elliot House dining hall in the backright hand corner。

 which is only to say as you approach this week's material。

 This week's problem set4 take comfort in knowing that it is challenging。

 It's meant to be challenging。 But as we sort of ratchet things up and up and up over the past few weeks。

 we will start to plateau in just about a week and then it sort of smooth sailing there on out。

 even though it might not feel that way initially this week。 But this week。

 we'll focus all the more indeed underneath the hood。 like how information is represented。😊。

Like this is a photograph of the bowl of stress balls that we have most every week。

 But recall that any time you have an image like this， it， of course。

 is composed of pixels and those pixels or dots， each have some bits or bytes associated with them that prescribe what color those dots should be。

 But there's only a finite amount of information in there。 So if we sort of enhance enhance enhance。

 like you don't actually see the5，0 more and more clearly， you only see it larger。 And in fact。

 this size， you can actually see the dithering。 so to speak。

 which is sort of this cloudiness that looms over the image。

 and you can kind of see the outlines of the actual pixels。

 All of those hard vertical and horizontal edges are the pixels， the dots that compose that image。

 So this is actually an example in fact， on this last slide here。

 can you see them even most clearly on the screen as we go and go and go。

 So how do you go about implementing them are representing something like an image。 Well。

 there's bunches of different file formats out there for images like there's gif， there's Jpegs。

 there's。😊，Kings and there's others as well。 But the simplest of them。

 like a bit mapap image is literally just a map of bits horizontally and vertically conceptually。 So。

 for instance， here is a grid of bits， zeros and ones。 And suppose， for instance。

 that maybe O represent0 represents black and one represents white。

 Can anyone with their human eyes see what this is a picture of， even though it's just zeros in ones。

Can you see it， yeah？So it is actually a smiley face because if the zeros are black and the ones are white。

 This is what's actually late in that image。 It's hard to see at this size， of course。

 But if we were to shrink that down and actually use square pixels black and white。

 it would probably pop out all the more clearly。 Of course。

 it's not that useful to store things with single pixels because you can only represent two states like0 in one like black and white。

 And so here might be that same image actually zoomed in such you can see all of those individual pixels。

 But when it comes to color， we of course need more than a single zero or a single one to represent each of those pixels。

 we probably need like 24， maybe three bys worth for some red。

 some green and some blue and recall that that's， in fact。

 one of the ideas we we talked about in week0， how do you go about representing images for instance。

 So more generally， this is actually kind of an art nowadays。

 if only for fun to actually use small dots and compose things on the screen and wonderfully。

 just before we began today。 of your classmates bravely volunteered And in fact。

 let me invite them to come up and introduce。😊，Themelves before we reveal what they have made on this canvas here using post it notes。

 square paper as their pixels。😡，Hello， my name is Seina。 I'm a freshman in Wiigglesworth。

 I'm thinking of studying robotics， and possibly in secondary and A F E S。 welcomelcome Hi。

 I'm Jeffrey。 I'm a freshman in Fair Hall， and I'm thinking about concentrating in econ and C S。

 welcome and allow me hang onto the microphone。 if you would。

 I'm going to go ahead and reveal what they kindly did on very， very short notice before class began。

 And here is what they came up with。 a grid of pixels Two colors here。😊。

What is it that you tell what it is， Sha we say well we make we can nicely honest。

 What is it they made。Because they're a little insecure about their pixel art。Saturday ladder？Again。

A fllamingo。Is it a flamingo， no？No， they said a palm tree on an island。 Oh。

 it's a palm tree on an island。 All right， maybe a round of applause for palm tree on an island。

 if we could。 Thank you。😊，Here So suffice it to say when you do have just， thanks very much。

 If you have just a single color to use black or white。 you're using one bit art。

 it's actually kind of hard to paint a picture。 But if you do have actually more colors at your disposal And an even bigger grid。

 can you do more interesting things。 And so， in fact。

 we invited some past students to do exactly this， we shared a Google spreadsheet whereby we use the cells instead of his long default rectangles。

 we just turn them all artificially into squares。 So that you can use sort of the paint bucket tool and just paint different pixels onto the screen。

 And among the pieces of art that some of your predecessors came up with where this here。

 a scene from Mario using a grid of multicolored pixels， this one here of scratch。

 the cat This one here in honor of the Harvard Yale football game coming up in a few weeks time。

 This one here using a bit of the same。 And in fact。

 if you'd like to play along at home just for fun， if you got a C50 dot Ly slash art。

 you can make a copy in your own Google account of that blank spreadsheet。😊。

And just play around if you'd like to experiment as well。

 But this is really meant to motivate one of today's topics。

 which is indeed how we can start to manipulate data at a lower level。

 including images and other things and images of course， can be among other ways。

 be represented with RGB some amount of red some amount of green some amount of blue Before we dive into that。

 though， let me augment our vocabulary a bit today by adding another base to our systems。

 So we have binary， of course， which is base two， we have decimal， of course， which is base 10 Today。

 we're going introduce one more， which is useful in today's concepts， as well as others。

 as we'll see down the line， known as hexa decimal where you actually have 16 digits at your disposal。

 And if any of you are artistically inclined or you might have dabbled in web development。

 you might actually be familiar with hexa decimmal notation itself already here， for instance。

 as a screenshot from Photoshop whereby if you use the so-called color picker to manually choose a color that you want to paint onto the screen you see。

😊，A lot of information over here。 but salient to today's conversation is this here where there's a hash sign。

 and then typically 6 or sometimes 3 digits in this case，0，0，0，0，0。

0 means that the color I'm going to get here is actually black。 So it's sort of no red， no green。

 no blue， hence the zeros means you're gonna get black。 Meanwhile。

 if I play around with the same color picker。 And I instead do F F， F， F， F F。

 either all caps or in lower case， I actually get a color that we're gonna see today is going be white。

 which is like a lot of red， a lot of green， a lot of blue all the frequencies of light cominging together to give us what we know as white light。

 But now we can kind of play with this， because it's no coincidence that these are indeed 6 digits of sorts。

 even though the letters of an alphabet and not numbers yet per se。 For instance， F F 0，0，0。

0 would seem to mean a lot of red and no green， no blue。 And indeed， that's why we get red。

 According to Photoshop itself。0，0， F。😊，00 gives no red。 a lot of green， no blue。 And， of course。

 that's the color Photoshop would give us。 And lastly，0，0，0，0， FF gives us indeed blue。

 because that's no red， no green， but a lot of blue。

 So the zeros would seem to make intuitive sense here。 And if you have no red， no green， No blue。

 But what's with the F。 like F， of course， in English are letters of an alphabet， not numbers， Well。

 it turns out that photoshop， and people in the world of images and people in the world of computer memory tend to use a different system altogether。

 they don't use binary， and no one really in practice uses binary except the computers we use because you can't do or see much with zeros and ones alone。

 we humans in the real world use the decimal system again，0 through 9。

 which is just very conventional。 But in the context of computers and specifically memory and files and images。

 we tend to use hexadeciimmal， which gives us another six digits in our vocabulary。

 And I'm deliberately calling them digits， even though they appear to be letters， but this is just a。

😊，We just we need we want  six more symbols。 So we have 0，1，2，3，4，5，6，7，8，9。 I don't want to say 10。

 and I don't want to write 10 because that would be two symbols on the screen。

 So the world years ago， decided， All right， when we want to represent 10 with a single digit。

 Let's call it a， and then B for 11， and then C and then D and then E and then F where F happens to be 15。

 So this is what's known as hexadeimmal notation。 And it's really the last of the notations or systems that will use。

 you can use uppercase or lowercase。 the software you use kind of decides what conventions to use。

 but they mean one and the same。 So hexadeadeimmal Hex implying 16 in this case otherwise known as base 16。

 All right， So just a bit of jargon out of the way。 How does it actually work mathematically。

 Like the exact same way as in week 0。 The math is a little different。

 It's not going to come to intuitively in the same way。 But the system is the same。

 If you've got two digit values here。 Like here are some placeholders。

 The columns represent the 16th to the  zeroth place。😊，16th to the one place。 that math is easy。

 This is the ones place。 This is the 16s place。 Instead of in our human decimal world， ones，1s。

100s or in the binary world，1，2，4，8， same idea， just different powers for each of the columns。

 Allright， so this number 0，0 represents the number you and I know as 0 in hexadeimal，0。

1 represents the number you and I know is1。 And it goes from there pretty straightforwardly，0，5，0，6。

0，7，0，8，0，9 translates 2 exactly what we know in decimal。

 like the number 9 because it's1 times 9 plus 16 times 0 gets a little more interesting when you're using two digits。

 but you're using hexadeadeimmal because now if I want to count as high as 10 in decimal。

 I would represent then in hexadeimal as 0， a0， B is 11，0， C，0， D 0， E0。

 f and there's our f and f all stipulate just represents the number we know as 15。

 So 1 times f gives us 15 plus。😊，times 0。 All right， dot dot dot。

 we're not gonna to do the whole range of numbers here。

 but I don't want to call this 10 in hexadecimal， just like in binary， even though you might see 1，0。

 you don't say 10， you would say 1，0， same in hexadeadecimal。 So this is 1，0。

 But if I translate this pair of digits to decimal， what does this represent。

So this is 16 because I've got 16 times 1 plus 1 times 0。 and on up and on up and on up。

 we can sort of do this for quite a while。 It gets interesting only once we get to the end using hexadecimal。

 as I've defined it， What's the highest we can count with two digits then。😊，In hexademal。

FF would be the highest because F seems to be the largest digits。

 So this is actually 16 times 15 plus 1 times 15 actually gives me 255。

 So that is as high as I can count in hexadecimal from 0，0 to F F， otherwise known as 0 to 255。

 And if you don't believe me， quick little math will give us that again。

16 times 15 plus 1 times 15 as well。 Allright， so how is this useful doing out this math。 Well。

 we have the following con。 Oh， actually， why is this useful。

 So it's very common to use  two digits of hex， maybe possibly more。 why， Well。

 it turns out that to represent the numbers 0 through 15， let me spread these apart now。

 just to be deliberate about it，0 through 15， How many bits do you need。😊，Well 0。

 you can use any number of bits。 How about 15。 Like how many bits， Sorry。

 How many bits do you need to count to 15。So it turns out it's four， right because in binary。

 that would be what the8s place plus the four's place plus the two's place plus the one。

 which I think gives me indeed 15。 So why is hexadecimal useful Well。

 it turns out that you can represent a single hex digit whether it's0 or F using four bits no matter what。

 And so why do we tend to use two hexadecimal digits。 Well。

 it's just useful to be able to describe a single byte otherwise known as8 Bs using two digits instead of8。

 So in binary， we'd have to use8 in hexadeadecimal， we can just use2 And it's just useful visually。

 Hexadecimal is useful as a result。 Allright， so when are we gonna see this and why are we going to see hexadeadeimmal。

 Well， here's like a grid of for the computer's memory。

 just abstract it away as by by by byte in rows and columns。 Well。

 here is how we might number those bytes as I've stipulated for several weeks now。

 we can call this byte0， this byte1 by two dot dot dot all the way to byte 15。 but by。



![](img/8c4f64e556c9e456e704dee6118981ae_3.png)

We don't use decimal， and we definitely don't use binary。 Instead。

 a computer scientist would think of the addresses the locations of the count of bytes in memory as still starting from 0。

1，2，3 on up， But as soon as you get to 8，9， A， B， C， D， E F。 Again， just a convention。

 there's nothing really intellectually interesting here other than we're using a different base system instead。

 Here's how the others might play out。 and it gets a little confusing because this 1，0 is not 10。

 if it's in hexadecimal。 but clearly， there's some potential ambiguities here。

 Like it's pretty obvious now that if you see an A through F。 it's probably hexadecimal。

 But if you see 10 or 11 or 12。 it's maybe not it might not be 10 or 11 or12。

 those might be hexadecimal。 even though 1， A，1， B is So this is an ambiguity。

 And so what we're also going to see today， that the way humans have mitigated this potential ambiguity is when you write things in hexadeadecimal by convention。

 you put a 0， X before them，0。Typically， a lowercase X that does not mean anything mathematically。

 It's not an extra0 per se。 It just means to the human reading this here comes a hexadeadecimal number。

 And now there is no ambiguity。 So we're gonna see a lot of this today。 General。

 we won't care about the numbers。 But that is what we're going to be looking at is hexadeadecimal。

 So any questions on hexademal， which again， is just another way of representing numbers。

Any questions on hexadecimal？Okay， so let's see this in practice and start to tease apart what's going on underneath the hood of our computer all of this time when we actually start to use variables and more。

 So here's a single line of code， Give me an integer called N and initialize it to the value of 50。

 So fairly straightforward。 So let's actually do something with this kind of code。

 Let me go into V S code here。 Let me go ahead and create a program called let's call it addresses do C。

 because I want to look at the locations in memory。 the address of things in memory。

 and let me stipulate， as we've said in the past。 just as mailboxes in the real world。

 houses and buildings in the real world have unique addresses like we were at 45 Quincy Street。

 Cambridge， Massachusetts，021，3，8 USA Similarlyly， does your computers memory。

 have addresses but they're super simple numbers like 0，1，2 dot dot dot all the way on up。

 So I've created a program now called addresses dot C。

 let's just play around with some familiar code， Let me include standard I O do H Let me。😊。

Int main void。 So no command line arguments for this。

 Let me declare that variable n said it equal to 50。 And let's just print out n。

 So this is like week1 stuff， super simple and and presumably familiar by now。

 whereby I want to print out using the percent I placeholder the value there of n。 Allright。

 hopefully， if no syntax errors。 I can do make addresses enter so far so good dot slash addresses enter And I see as expected the number 50。

 But what's actually going on inside of the computer's memory in this case。 Well。

 we can actually see that over here。 Let's look at this grid of memory here for today's purposes is。

 I don't necessarily know where in the computer's memory at this point， the n is going to end up。

 So let's just arbitrarily say the computer finds room for the int in the bottom right hand corner of my screen。

 the size of it is deliberate because recall that integers tend to be how many bys on most systems nowadays。

4 bys by convention， Aka 32 B if you multiply by 8。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_5.png)

![](img/8c4f64e556c9e456e704dee6118981ae_6.png)

So who knows N might very well end up in the bottom right hand corner of my screen here with the number 50 stored there。

 Now， it's not literally the number 50。 There is literally 320s and ones in the computer's memory that are turned on and off to represent the pattern that gives me the decimal number 50。

 So again， that sort of week 1 style stuff。 But we're thinking about now the computer's memory。

 In fact， even though we refer to it as n in my code， it's got to live somewhere。

 And the address at which it might live for the sake of discussion is maybe something notationally written in hexadeciimmal like O X 1。

2，3， completely arbitrary in practice， it's probably a bigger number than that。

 But for the sake of discussion， let's assume that that 50。

 the variable N just so happened to get placed by the computer at location O X 1，2，3。

 Can we see that in code。 we haven't yet， thus far。 But if I propose here。

 maybe going back into V S code in a moment， maybe we can actually。

Use some slightly new syntax and poke around the contents of the computer's memory。

 But before we do that， we do need a few new building blocks。 And there's not much new syntax today。

 but we're going to go pretty darn far in terms of capabilities with just a few new symbols。

 It turns out that in C。If you use the ampersand operator， just one of them， not two。

 two means and logically， just like two vertical barsmen。 or if you use just one of them。

 as we are going to today， that is going to be the so-called address of operator。

 So you can write ampersand and the name of a variable and the compiler essentially will tell you where that variable is in the computer's memory。

 we're technically when the program is running， you will be told where it is。

 The star operator or a single asterisk is not multiply in this context。

 It's going to be the dereence operator， which is going be a trick via which we can have an address and go there sort of following a breadcrumb following X marks the spot on a map and going to that location and memory and just see what's there。

 Is it an in。 Is it a cha I it a string or something else。

 So these sort of reverse the effects of each other。 This tells you the address of something。

 This tells you how to get to something。 So the address of operator and the dereence operator。

 So to speak。But we need one other building block。 And this one's gonna be useful in the context of printf。

 Re that printf has all those format codes like percent S for string， percent I for integer。

 percent F for float turns out there's another one percent P。

 which is going to allow us to print what are called pointers， which are really for now。

 synonymous with addresses in memory。 So using just those new building blocks。

 Let me propose that we do the following leveraging this notion of a pointer。

 I'm gonna change my code in just a moment。 So still have the same single line here in n equals 50。

 But then let's create a second variable called P just for convenience。

 But let's declare it as a pointer。 A pointer is simply a variable that stores the address of something。

 So it's a variable that stores the address of something like O X1，2，3 or some such value。

 How do you use it syntactically。 It's a little weird。

 especially since we've used star and the ampersand in other ways already。 But you say that I want。😊。

Vable called P。 The type of this variable is going to be a pointer。 so to speak。

 How do you express that。 Well， I want it to be the address of an integer， So you say int。

 But you make clear that it's the address the address of an integer。

 not an actual integer per se by putting a star here of all the things we have。 And we'll see And C。

 I will can see this is sort of the most confusing way to do this。 Ideally。

 there would just be a variable called pointer and you just write it and you get a variable that's a pointer。

 But in the way， in the case of C， you actually specify that this variable P will indeed be an address。

That points to an integer。 So just have to kind of let that ingrain in yourself。

 This one's a little easier。 Ampersand。 And how would you express that in English based on my previous definition。

The address of N Ampersand N just means get the address of N。

 And because code recall is generally read and executed right to left in this case。

 this says wherever n is， get the address of it like O x 1，2，3。 and assign it to the variable P。

 What is the variable P。 It is a pointer。 so to speak。 That is the address of an integer。

 So it's a little it is arcane。 It's a little weird。

 But this is kind of as low level as we can get with C with just telling the computer exactly what we want to do。

 So let's see this。 let me go back to V S code here。 And quite simply after clearing my terminal。

 let me go ahead and print out using percent P。 the following address of n。

 And then we'll enhance this code to actually actually no， let's do this exactly as I did。

 Let's go back into V S code here。 Let's declare int star P equals ampersand P。

 and then print out not I itself not n itself。 But print out using percent P。 the value of P itself。

😊，So what is this going to do for me， it should print out the address of N。Alright。

 so in my terminal window， make addresses， enter。I messed up because I did something stupid。

 I forgot the semicolon， as you might have one or more times the past few weeks。 Let's do this again。

 Let's make addresses， enter damnm it。I screwed up a second time。I want the address of N。

 not the address of P。 Allright， so I'm doing well。

 So so much for remembering this concept from the dining hall of Elliot House。 Allright。

 so make addresses enter。 Oh my God， thank you。 Allright， So now it works。

 hopefully dotlash addresses。 It's not gonna be as simple in the actual computer is O X 1，2，3。

 It's probably gonna be a bigger number。 And indeed， it's a much bigger number。

 but there is an address of some sort might be different run on a different system。

 But it turns out that the variable N is stored at location。 O X 7 F F E F 3 C2，9，2，5 C。

 which is just a really big number that if we did all of the math on paper pencil or computer would be a really big decimal number。

 Why the server has lots of gigs of memory， billions of by。 So of course。

 it's probably going to be a big number like that。 Now， I don't strictly have to create P。 In fact。

 let me do what my instinct had me doing a moment ago。 let me delete P。

 and simply just print out directly。 What is the address of N。 Let me go ahead and。😊。

Recompile the code， make addresses， do slash addresses。

 And I actually do get a different address this time。 why。

 because I've run the program again and things got organized in memory a little bit differently。

 So these numbers are not going to remain invariant， unchanged。 But every time you run the program。

 things might deliberately or for other reasons， get moved around。

 But all I have done is ask the computer explicitly。 what is the address of N。

 And that's what I'm seeing。😊，All right， so just to recap then what these lines of code are doing。

 previously， when I had both N and P， this ladder line is just asking。

 what's the address of N storing the address thereof in this variable P。

 But there's some disagreement in the world as to how you should write this syntactically。

 And just so you've seen it in case you see a video or a tutorial or book that disagrees。

 This is really the conventional way to write the star。 That means， hey， computer。

 this is a pointer to an integer。 The address of an integer。 You could also write it this way。

 And some people do this。 I do think it's a little this can get you into trouble in certain cases。

 Some people do this with spaces on either side， which even looks more like multiplication。

 but it's not。 all three will work， but the recommended the conventional way is indeed to do this。

 even though I do concede it looks a little weird， but it'll get more and more comfortable over time。

😊，Al right， so if you're with me that what we've just done amounts to just figuring out where in the computer's memory a variable actually lives。

 I think we can poke around further to see even more of what's going on。 In fact。

 let me go ahead and propose this。 Let me propose here。😊，That way。Go back to V S code here。

 clear my terminal window。 and let's go back to the version before where I explicitly did have P。

 So int star P。Equals ampersand N。 And then again， printf quote unquote。

 And what I had before was percent P backslash n comma P。 So this printed again。

 the exact same thing， The address of N。 But what if I actually want to print out N itself。

Just like I did in week 0。 Well， in week 0， Oh sorry， just like I did in week 1。 in week 1。

 I could have just done， as I did a few minutes ago。

 this and this would print out in the old school way， the value of n。 And just as a quick check。

 make addresses， dot slash addresses。 and there's my 50 as expected。

 But now that I have these two other operator， whereby I have both ampersand and star。

 I can kind of poke around with them play around with them in ways that should hopefully with some practice makes sense。

 So for instance， I could do this again。 int star P equals the address of n。 Well。

 I could print out n literally， as I'm doing now， or I could use the location of n called P and go there with the second of these two operators。

 the dereence operator。 The de reference operator， the single star means go to this address。

 And so now when I go back to V S code。 and I do make addresses， dot slash addresses enter。

 I still get 50。 I'm。😊，Jumping through hoops proverbly here。 because is this sort of the stupid。

 longer， more complicated way to print out the value of 50。

 But it just speaks to the relative power that I have by just figuring out what the address is and then going there。

 But the confusing part， I do think about this for me And for most folks learning this is the following the designers of C decades ago made。

 I would say the unfortunate decision to use the star in two different ways and three different ways in total。

 one multiplication we saw that in week1 since， But notice that there's two different uses of this star operator here。

 it literally means go there， dereference the address that is follow the breadcrumbs and go there。

 But when you declare the pointer， when you create the pointer， you also use a star。

 But you also use the type。 So what's confusing， at least to me is that we're using the star in two different ways。

 both of which are related to addresses， both of which are related to pointers。

 but when you create a variable or declare a variable for the first time， you specify not only star。

 but the type of the pointer。Just like any other variable declaration。

 But when you use the pointer subsequently， you do not mention the data type again。

 The compiler is smart enough to remember。 Okay， got it。 You wanted a pointer to an integer。

 The compiler will remember that for you。 you do not need to remind it。 So admittedly confusing。

 But on line 6， we are declaring the pointer and assigning it a value and on line 7。

 we are dereferencing the pointer。 So one sort of one creates the pointer。

 One goes to that there address。So in terms of what's going on inside of the computer's memory。

 let me propose that if we revisit the same grid and we propose that 50 ended up down here。

 the value N is actually technically at O x1，2，3。 What exactly is P the second variable。 Well。

 I could draw it as follows in my memory。 Maybe by chance， it ends up here。

 sort of higher up on my slide。 But this is the variable called P and the value of P is simply literally the addresses of N。

 Why is p so big。 Well， it turns out on most systems nowadays。

 pointers that is addresses are 64 B or 8 B。 So they just use a lot of bit。 Why， Well。

 you and I have gig again of memory nowadays。 And if you're counting up to the billions of by。

 you actually need more than 4 B or 32 B because recall from week 0。

 even the highest you can count with 4 B or 32 B is 4 billion。

 But some of you probably have max or PCcs that have 5 GB，6 GB，8 GB or more。😊，Memory nowadays。

 that means we need 64 B to count that high so we can actually label every memory location in order to access these spots。

 So what is P， It's just a variable whose value happens to be an address， What is N。 Well。

 it simply happens to be an integer at that address。What questions do you have on this， yeah。

Are you able to use more than one point or remain main absolutely， just like variables。

 you can create as many as you want， including arrays thereof。

How do you differentiate them by way of their name， So I'm using P because it sounds like pointer。

 but I could call it Q or R or S or T or use an actual English word to describe my variable。

 I'm just using P for short。😡，Just like any variable， yeah。That's the points are have。

A good question。 Does the pointer have an address itself， Short answer。 Yes。

 because anything in your computer's memory has an address and odds are。

 it really has8 addresses associated with it。 So maybe we refer to it by the first one or something like that。

 There actually exists， but we won't do this today。 Pointers to pointers。

 which answers that question。 But here， I'm leaving it abstracted away and just calling it P。

 But it absolutely has an address。Other questions， yeah。You may have already said this。P in the code。

 Do we do。A good question。 When you're referencing P in your code， do dereence it， Do you use star P。

 short answer， Yes， if you want to go to that location。 And that is usually。

 as we'll see this weekend and next week， how pointers are useful。

 You want to go to that location and do something there， It is rarely。

 if ever helpful to literally print or see the actual address， because who really cares。

 especially if it changes every time I run my code， we we as programmers don't care where things are。

 but that we can get to those locations。Good question， yeah。How is the。Sorry， not physical。

 not yet actual physical memory。Yes， without going down this rabbit hole today。

 we're talking really about virtual memory。 This maps underneath the hood。

 using virtual memory to physical memory。 But for all purposes。

 we're talking about one and the same today， old computers， simpler computers， simpler times。

 so how can we now， sort of think about this。 Well。

 that is literally what's going on in the computer's memory。 But as I just said。

 rarely do we actually care that it's specifically at O X 12，3。 and in fact。

 the name pointer kind of conjures up a nice metaphor here。

 Let's sort of ignore all of the bytes of memory that we're not even using or talking about anyway。

 And who really cares about O X1，23， Let's just abstract that away as we've done in the past with literally an arrow when drawing or talking about these things。

 and just think of P as being a variable that literally points to another location in memory。

 So indeed， whenever a computer scientist is talking about or arguing about or designing something that involves memory。

 They're not going get into the weeds of doing O X anything。

 They're just going to use arrows to draw things on paper or digitally。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_8.png)

And in fact， next week， when these sort of all comes to a head when it comes to memory。

 we're gonna build things in computers memory known as data structures。

 Fcier structures than simply a。 we're gonna to do one dimensional structures。

 two dimensional structures， and we're going to use pointers as sort of a thread with needle to connect this location with this one with this one then this one and start to create twodial objects。

 if you will， inside of our Mac， our PCcs， our phones memory as well。 So to make this super clear。

 we actually do have a nice metaphor。 Maybe if you really wouldn't mind coming up。

 I keep saying that you can think of addresses in memory as being akin to physical addresses in the real world。

 like mailbox for， say this building again，45 Quincy Street and Cambridge， Massachusetts。😊。

And here then is a mailbox that has the name P。 So this is appropriate because if a pointer is a variable that stores an address。

 this here mailbox called P would seem to be， I'll say storing an address。 Meanwhile。

 Ulia has a separate mailbox here， that's actually called N。 So it's like a variable in memory。

 we're kind of cheating because technically the pointer would be twice as big as this mailbox。

 but Home Depot only has so many different sizes。 So they look the same physically。 But N。

 according to the story lives at address O X 1，2，3。 So if I am the computer。

 And I am executing code that looks like star P go to the address stored in P。

 that's akin to like a person opening up a mailbox looking inside。

 seeing that what's in there is not an actual value you care about per se。

 but it's kind of like a treasure map X marks the spot。 if we sort of abuse the metaphor。

 which just means if I want to go to the address in P。

 that means I look in computers memory and just to be dramatic， we can do this too。

 We've got a little big。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_10.png)

![](img/8c4f64e556c9e456e704dee6118981ae_11.png)

![](img/8c4f64e556c9e456e704dee6118981ae_12.png)

Pm fingering， This is like the computer pointing at the actual location， O X 1，2，3。 Andvoila。

 there is the number 50 that we care about。 And for those following along at home。

 maybe avert your eyes here in Sanders， we can similarly do this with the Yale foam finger as well。

 to dereference that as well。 And the crowd went wild for those of you watching from New Haven today with applause。

 So thank you to the Julialia， though， for this particular demo。😊，Yes， yes， we will。

We will enhance the applause in the final version of the video。

 So let's now revisit admittedly a bit of a white lie that we've been telling for a few weeks now。

 And I kind of tripped over this in week 1， but then sort of wave my hand and solved it real quickly by introducing the C S 50 library。

 But I'm going propose that we revisit what a string actually is。 Now， we use strings in weeks1。

 we then began in week2 to talk about strings。 Thank you as just being an array of character。

 So that was the first reveal。 But even then we kept using the word string。

 But it turns out that strings do not exist in C as a data type。

 Strings are not a C S 50 thing per se。 But there is literally no keyword in C called S T R I and G string。

 It's a concept that exists in C。 So nothing is that we've said over the past few weeks has anything to do with C S 50 per se。

 Almost every programming language you'll encounter in the real world support strings in some way。

 But my claim today is。😊，That the keyword string is actually made up for us for convenience over the past few weeks。

 Now， why is that？ Well， up until now， we have been creating strings in code with lines like this Str S equals unquote high in all cap semicolon。

 What that would do according to week2's discussion of memory is it would give us4 Bs in memory for H I exclamation point in a fourth byte to be clear for the null character。

 N U， the backslash 0， which is just 80 bys。 And we were therefore we're able to manipulate that string as though it were an array。

 So S bracket 0 is the first character。 S bracket 3 is the very last character specifically that null character。

 Well， really， we can start to think about strings a little differently still today。 In fact。

 let me go back over to V S code here， clear my terminal window。

 And let's stop playing around with integers like number 50。 And instead， let's do this。

 let's give myself a string S equals quote unquote， high exclamation point。😊。

And then let's go ahead and print it out just like in week1 with percent S backlash N comma S。

 Let me go ahead and increase the size of my terminal window。 do make addresses。

 And here is the very same mistake。 We glossed over in week1 error use of undeclared identifier string。

 did you mean standard in。 Now， maybe that does sound familiar。 But it's kind of a red herring。

 This has nothing to do with standard in per se。 string is undeclared because it doesn't exist in C by default。

 And in fact， it thinks maybe this is a typo standard n is a thing that exists in programming languages。

 But string I said in C does not But this fix for me， recall in week 1 was to very quickly say。

 we'll come back to that。 And at the top of my code。

 I went in and added one more include C S 50 do H。 And somehow if I clear my terminal。

 rerun make addresses。 that solved everything。 And string was brought into existence。

 But how exactly was that the case。 we'll see today， what's actually going on。

Underneath that hood as well。 So what have I just done with this code。

 I've simply printed out the string S， but notice， I claim what's really going on if I visit。

The actual memory in the computer is， yeah， it's an array。

 But if an array is just a chunk of contiguous memory。

 Certainly we could figure out what the bytes are。 The addresses are of each of those characters。

 H I exclamation point and the null character。 And again。

 for the sake of simple discussion supposeuppose the H is at O X 1，2。

3 stands to reason that I is going to be at O X 1，2，4。😊，Exlamation points at O X 1，2，5。

 and the null characters at O X 1，2，6。 The specific numbers don't matter。

 But what does matter is that they are 1 B apart。 And that is literally what I've meant all these weeks when I say contiguous。

 back to back to back， They're literally one B apart。 So once we know this。

 can we sort of leverage this to play around with and see strings perhaps in a somewhat different light。

 Well， let me go ahead and do this。 Let me go back to V S code here after clearing my terminal。

 Let's leave string S as is。 But let's print out a few different things。

 Let's actually print out what is inside of S。😊，Perscent P back slash N is how I can display an address。

 A K， A pointer。 And let's print out the value of S。

 Let me go down to my terminal and do make addresses， enter dot slash addresses。

 And what I see now is a seemingly random， but a much bigger hexadeadeimmal address。

 So it seems that S is not a string per se， because I literally just told the computer to print it out with printf。

 albeit using percent P instead of percent S。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_14.png)

But percent P just means show me the address of a variable。

 And it seems that S's technical value is O x 5，9， F B 1，6，9，9， D，0，0，4。 Now。

 that is the longer version of what I just proposed for discussion sake is O X 1，2，3。 Well。

 let's be a little more pedantic here。 Let me go ahead and print a couple of more things。

 Let me print out another address using percent P。

![](img/8c4f64e556c9e456e704dee6118981ae_16.png)

But let me print out the address of the first character in S using my array notation。

 And then let me do some quick copy paste just to see a few more of these。

 Let me print out location 1， location 2 and location 3。

 So we're really kind of making use of this arcane looking syntax day， lots of percent p。

 but that just means show me address address address address and so forth。

 S bracket 0 is from week 2， just show me using array notation。 The first character。

 The second character the third and the fourth。 And Ampers is new today。

 just means show me the address of that character， not the actual character。

 So if I go back down to my terminal window。 make address again。

 I'm gonna see five values in total now， Z slash address gives me this。 let me zoom in。

 And what's noteworthy is that the very first one is identical to the second one。

 which seems to imply that S that has the same address is the first character of S。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_18.png)

That sort of makes logical sense， because what else would it be， if not the first one。

 And so what we're seeing here now is a hint that whereas percent P is printing out literally the value inside of S。

 What was percent S doing all this time。 It was thanks to printf's implementation decades ago。

 going to that address and printing character， character， character。

 character and stopping only once printf finds what。



![](img/8c4f64e556c9e456e704dee6118981ae_20.png)

The backslash0， the null byte。 So some person years ago literally implemented printf。

 They literally are using S as an address going to that address somewhere with a star operator in their code。

 and then using a four loop or a while loop iterating over character character character in character from that address onward until it sees the so-called null character。

 All of this sort of been happening for us automatically， But that's really all that's going on。

 If I go back into the visualization of my computer's memory。

 here's that same simplification using smaller numbers， O X 1，2，3，1，2，4， and so forth。

 And what is S then when it's declared in memory。 Well， it's a pointer， which means it takes up 8 by。

 So I am doing this to scale。 But what is S really doing。

 it's storing the address of the first byte of the actual characters。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_22.png)

It's storing nothing else。 S is not storing the last byte。 It's not storing the length。

 It's not storing anything other than the first byte's address， but that's okay。 Why。

 Because how does the computer functions like printf know where the strings end just to be super clear。

😡，The backslash 0。 That's why we're wasting an extra byte all these weeks because someone needs to know or tell everyone else where strings actually end。

 Those of you who do have some prior programming experience in Java or in Python or other languages。

 You can and generally just ask a string。 Like what is its length。 You can call it a length function。

 You can do do length or similar。 Those of youve done this before。

 That's because in higher level languages like Java in Python。

 there is more memory being used than just the address of the variable alone。

 someone somewhere is keeping track of the length of that chunk of memory。 But C is much lower level。

 It's much more efficient。 It's much more complicated in that it leaves it to someone else。

 something else to keep track of where strings actually end。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_24.png)

But like， that's it。 And， in fact， all I brought these just to be sort of unduly dramatic。

 Like all these weeks， we've had these sort of training wheels on， right。

 like where we've had these simplifications of C S 50 dot H and strings existing。 And now。

We're taking the training wheels off because like this is literally all that's been going on since week1。

 I'm not sure that added anything。 This is all that's been going on since week1， But again。

 that's sort of the design of the course is to help you understand first at a high levels。

 you can just get things working and start playing around。

 Now we're taking a peak underneath the hood to see what really has been going on all of this time。

 And indeed， who cares what addresses these things live at。

 And so the way you would typically think about or draw this on a piece of paper is literally just with an arrow。

 S is pointing at a chunk of contiguous memory that is null terminated， so to speak。

 So where did string actually come from。 Well， here's how I've been declaring strings today and prior string S equals quote unquote high string being supposedly the type of my variable。

 Well， it turns out that a string we have seen is really just an address。

 But it's the address of what just to be super clear。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_26.png)

A string is really the address of。It's first character。 So it's first character。 So it's first char。

 So I think the implication of this now is that if we get rid of those training wheels and we get rid of even the C50 library。

 we can actually start calling strings char stars。 and this is what real geeks call strings like oh。

 a char star in C is known to mean you're just talking about a string。

 but you're doing it a sort of a lower level actual vernacular， which implies that the address is。

 in fact， that of its first char。 The last address of the address of its last char is implicit in that null character that we've been using all of this time。

 So we've actually seen this kind of before， In fact， just recently。

 we introduced the notion of persons， And I said， well。

 if we wanted to invent our own data type and a person for instance， would have a name and a number。

 we introduced syntax like this， which was kind of a mouthful。

 but the only interesting part is what's inside of the data structure in this case。

 person was the name we gave to the data type， This whole struct is what we wanted a person。😊，To be。

 and the way we brought a person into existence in C was we defined a type using the type def keyword in C。

 That's actually gonna be the trick to what we've been doing in Cs50 for the past few weeks。

 We're using type de to define our own type。 we want to create an alias， for instance。

 from one thing to another。 So just to keep things simple at first。

 supposeose that I'm really confusedfuse by int， like it's an integer I get， but why int， why int。

 suppose I want to create a synonym called integer for int。

 I could literally say type def int integer semicolant， And this will bring into existence。

 a data type called integer， which doesn't really solve a problem other than helping you remember that ins is really just short for integer。

 but the syntax can be as simple as that。 it doesn't need to be multiple lines with structures and person attributes like that。

 So accordingly， how can I define a data type for a string， I can say type de char star。

 which is admittedly more。Mind bending。 but I want to think of it instead as a string。

 So inside of C 50 dot H since week1 has been literally this line of code， a bunch of other lines。

 too， but this one liner， because you're including at a top your code brings into existence。

 the keyword string。 but it's just like doing an automatic find and replace between string and char star。

That's all that's actually happening really underneath the hood。Okay。

What questions do you have on what a string。Actually is， in this case。It's all what's inside of C。

 S 50 dot H。Yeah。嗯哼。😊，2。A really good question here。 Am I violating my own。Convention。I am not here。

 I do。 I runshin。 Do you know if this would work without the space here。We'll find out he's checking。

 So this is a different context。 I'm not actually declaring a variable here called string。

 I am declaring a type called string。 It's possible。 It's a allowed。 I don't know。 offhand。

 So good question。Yeah。Other questions， yeah， I'm back。Really good question。

 When is it more useful you use char star instead of string， Honestly， after you exit C S 50。

 you should not use string anymore。 And in fact， among the things we're gonna do next week is take the last of these training wheels off and take away the C50 library so that you actually use only native C code per se so that there are no more training wheels physically or virtually otherwise。

 So in the real world， if you ever write C， you would just use char star。

 We use string only because I dare say， introducing char star in these memory addresses and like mailbox is all in the first week of C。

 It's just too much when all we want to get working is like hello world or Mario or the like other questions。

 yeah。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_28.png)

Really good question。 In my V S code here， when I use the ampersand。

I used it in front of each of the characters，0 through3， but I didn't use it here。 A subtlety。

 but the reason I didn't use it here is because S we now know is already a pointer。

 It is a char star。 So if it's already an address and percent P expects an address。

 there's no reason to do ampersand S。 It is already the address of a string。 specifically。

 I can now take away the C50 library from my own code， let me clear my terminal， go back up here。

 take the C50 library away， which was a bad thing earlier。 But if I now call this char star S。

 this declaration here， makes more explicit that S is the address of a char。

 So percent P expects an address。 you can literally slot in S right there。 but S bracket 0。

 S bracket 1 S bracket2， those are actually chars inside of an array。

 So if you want the address of those characters， you do need to use the ampersand。

In answer to the question that came up over here， if I were to incorrectly use an ampersand here。

 that would be getting the address of the pointer， not the address of the stream。

 but we're not here to talk about that today。😡，Other questions， yeah， and back。

Where does percent S come from， So that percent S is supported by C and specifically printf。

 So strings exist as a concept in C。 The word string does not exist， but when you use printf now。

 as I can hear as another demonstration。 I can do printf。

 I don't change this now to percent C because I don't want to print a character。

 I still want to print a whole string conceptually， and I can pass and here S just as before。

 So printf has always understood percent S。 That's not a CS50 thing。

 The only thing that was a CS50 training wheel was the word string。

 which we can now take away safely， you just have to start writing cha star instead。😡。

Other questions and back。For。Be writing。A good question。 So in your own code。

 should you now start doing type def char star string， semicoons so that you can still use string。

 like， no， I mean， if you are， if after today or if after a few days from today。

 you sort of understand what's really going on and you're comfortable with it。

 There's no reason to like keep putting the training wheels back on yourself in perpetuity。

 The simpler approach would be just be keep using C 50's library for some amount of time。 And that。

 too， is fine。 Even come final projects。 It's fine to still use these training wheels。

 the goal of today and next week and beyond， it's really to make sure you understand how you can write code successfully。

 even without those same training wheels on。Alright。

 so let's poke around just a little bit more with these capabilities。 In the S code here。

 let me propose that we can dabble a little further， as by doing something like this。 if I go into。😊。

Let's say addresses dot C one final time。 I'm still gonna create s as quote unquote high in all caps。

 But now just to be clear， let's print out this string manually。

 just as we could have back in week 1 except now there is no string。 There's only char stars。

 I'm gonna do percent C back slash N quote unquote comma S bracket0。

 And then just for the sake of discussion。 let me just copy paste this twice So as to print out these two characters。

 Again， I'm just playing around in the real world。 I should really use a for loop or something like that。

 But I just want to manually poke around with this new syntax。 So let me make addresses again。

 dot slash addresses。 And I should see H exclamation point1 per line。 So that's just week one stuff。

 But now let me propose that there's this other feature of C。

 we can avail ourselves are known lastly as pointer arithmetic。 So if。😊。

Every chunk of memory has an address， and that address is just a number， whether it's an hexadeimmal。

 decimmal， binary， whatever。 They're just numbers。 I can actually do math on addresses。

 And if I can start in one location， I can go 1 by away，2 B away，3 B away。

 just by adding one or two or three。 It stands to reason。 So what's the implication of this。 Well。

 it turns out that I don't need to use square bracket notation anymore， if I don't want to。

 we introduced it in week 2， it is a feature of C， and it is a very。

 very common and useful convention。 And probably the convention to keep using。 But strictly speaking。

 we don't need to use square brackets anymore to print out individual elements of an array。

 For instance， I could。😊，Change this first line to not be s bracket0。

 but I can just say go to the first character of s because if s is a string。

 otherwise now known as a char star and char star just means the address of a cha。 Well。

 if I want to print out the actual cha。 I can use star S to go to that address and where I will find X marks and spot。

 a cha in the computers memory。 But here's where the arithmetic comes in。 Let me do another line。

 print f percent C back slash n comma， go to S plus1。

 So I can literally do a bit of math on my pointer to go one location to the right。

 I can do this once more printf percent C backslash n comma percent S percent sorry。

 star S plus2 to go to location to the right。 And I'm doing this only because I know H exclamation point gives me three location。

😊，In total。 But if I now do again， make addresses dot slash addresses。 I get the exact same behavior。

 And， in fact， the square brackets we introduced in week2， which again。

 come with C is just syntactic sugar。 so to speak， which is a term of art in computing。

 which just is a more user friendlyend way of expressing this weirder syntax。

 The square brackets by the compiler are essentially converted into pointer arithmetic for me。

 so that I don't have to write code that admittedly on the screen looks more cryptic than it would with just the simpler。

 more user friendlyly square brackets。 But all that those square brackets are doing underneath the hood is effectively pointer arithmetic for you。

😊，So if I want to play around one final way with all of this same code。

 I can even do things that probably aren't the best idea。

 but do speak to the power of this syntax in this language C。 For instance。

 if I want to print out the actual string S。 we know I can do this already。

 Pre S and print out S itself because S is a string otherwise known as a char star。

 So make addresses just gives me high exclamation point。

 But what if I only want to print out part of the string。

 I could start part way in the middle of this thing。 What if I do this。

 print F percent S back slash n， S plus1， So no star， I don't want to print out a char。

 I want to print out a whole string。 What is a string， a string is an address of the first character。

Of the string， still no terminated。 So when I compile this code printing out and actually let me get rid of the previous line。

 when I compile this code with make addresses and I run dot slash addresses。

 what should I see on the screen now， If I'm not printing starting at S。

 I'm printing starting at S plus 1。Yeah， I think you're saying I like I exclamation point Y because if these strings start at O x 1。

2，3 and go O x1，2，4 O x 1，2，5， O x1，26。 And I'm starting at O x1，23 plus 1。

 that means start it the second character。 And I think， yep， I now see I exclamation point。

 If I change it to two， I now see after doing make addresses。

 I think I should just see very excitedly an exclamation point， and that's it。

 I probably don't want to go even further than this。

 because then who knows what's gonna to happen if I start printing beyond the boundaries of the actual string。

 And that， in fact， is gonna be one of the tradeoffs here。

 Even though now with these simple operators like star and Ampersand。

 we can now manipulate and understand memory at this lower level， we can actually do a lot of damage。

 And among the things we'll talk about today2 after the break is recall that the crowdstr fiasco a few months back where like systems around the world broke down。

 including airlines and the like， that stupid， stupid issue was the result。

Such a simple problem that after today's break， you two will understand。 But in the meantime。

 in happier news， let's have some little bites of blueberry muffins in the transep。 See you in 10。

 No， No， don't appla。 We're not on。 See you in 10。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_30.png)

![](img/8c4f64e556c9e456e704dee6118981ae_31.png)

All right， we are back and one araum。 So this was the line of code I proposed in Cs 50 do H is's not quite the line of code in C50 do H because as was asked styyllistically the quote unquote right way to write this would indeed be without the space after the star。

 So even though string is not being declared as a variable here。

 but rather as a type stylistically and I just ask style 50 for the correct answer。

 it would indeed omit the space。 So this is what I should have said earlier and we'll fix that in the online version thereof。

 But for now， let's actually transition to taking a look again at the computer's memory and revisit some problems that we looked at indirectly over the past couple of weeks and better understand why things worked and now work the way they do。

 So let me go over to VS code here and have've written in advance relatively simple program。

 I'm still using C50 do H and standard Io do H for this example。

 I'm calling get in twice to get two variables I and J。 So two numbers from the user and'm。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_33.png)

![](img/8c4f64e556c9e456e704dee6118981ae_34.png)

![](img/8c4f64e556c9e456e704dee6118981ae_35.png)

![](img/8c4f64e556c9e456e704dee6118981ae_36.png)

Checking for equality using equals equals。 So if I equals equals J， I'm going to print same。

 Otherwise， I'm going to print different。 So fairly straightforward， and it should just work。 Indeed。

 if I open up my terminal window and I do。

![](img/8c4f64e556c9e456e704dee6118981ae_38.png)

Let'sops， sorry。 If I open up my terminal window， do make compare because this files compare dot C。

 I can then do dot slash compare and type in two numbers like 50 and 50。 and they're indeed the same。

 or I can do it again，50 and 51 and they're in fact different。

 And I'll stipulate that pretty sure this code is in fact， correct。

 But what if we make a change of sorts and actually compare not integers， but strings。

 What's going on。 Well， let's first consider what is happening with integers。

 So here's my computer's memory。 and I've zoomed out a bit so we can fit more on the screen at once。

 And here might be where I and J end up in the computer's memory when running this program。

 I hear J here， both of them 4 B because both I and J are integers。

 It stands to reason then when I compare I and J， we are literally comparing 50 against 50 in that first scenario。

 And indeed， it's technically 32 B and 32 B， but they're exactly the same if they're both storing and representing the value 50。

 Allright， So fairly straightforward。😊，But what about strings， In fact。

 we deliberately introduced stir comp or for string comparison because when I last tried to compare two strings。

 it didn't actually work as intended when using equals equals。 So in fact。

 let me go back to my code here and close my terminal window and just make a couple of changes here。

 same idea but different data types。 So let's do string S equals get string and will prompt the user for string S now instead of I then maybe a string T just to keep the variable name short for the sake of discussion and prompt the user for T here。

 then let me go ahead and say if S equals equals T。

 go ahead as before and print out same backslash n otherwise go ahead。

In my else clause and print out， quote， unquote。Oops， quote unquote， different。 Allright。

 so same logic， but different data types using strings for the type and get string for the function。

 Let me open my terminal window again。 make compare no syntactic errors。

 but let me go ahead and do dot slash compare and type in something like how about high and hi both in all caps。

But they appear to be different。 I can try again， maybe my name， David and David， also different。

 even though it seems to be the same。 So what's going on。 Well。

 you might already have an intuition in someone last time when we looked at a program like this did have an intuition。

 But what if we make it more explicit now， What if I change my strings to literally char stars。

 which doesn't affect the functionality， but takes off one of those training wheels。

 I'm not gonna get rid of C50 do H altogether， because as we'll see， I still want to use get string。

 Otherwise， it's a pain in the neck and C to get user input。 but will come back to that。 But S now。

 iss not only a string， it's more precisely the address of a character technically。

 the first character of a string。 So what then is being compared on line 9 that's yielding this different answer。

😊，Why are high and why are David different， even if typed identically。



![](img/8c4f64e556c9e456e704dee6118981ae_40.png)

Yeah， it's two different addresses。 What's really going on If we take a look at the computer's memory now dealing with strings is the following。

 Here's that grid of memory。 Maybe S ends up here。 and maybe the actual array of characters ends up here because notice when we're using strings technically we're storing the address and we're storing the actual characters And that's all been happening magically in one step for us。

 one line of code。 but technically there's different chunks of memory involved。

 and it might be at O x1，2，3，x 1，24 Ox1，25 and O x1，2，6。

 all of that happens automatically with that one line of code when I create and initialize S。

 Meanwhile， S is going to therefore store the address of that first character。

 hence the whole idea of a char star。 But what is t。 Well。

 maybe t ends up over here somewhere in memory， maybe the other high that I typed in later the David that I typed in ends up at maybe Ox 4。

5，6， x45，7， x 4，58x 4，5，9 again， who cares what the addresses are， but they are back to back to back。

 which is important。😊，But suffice it to say then what ends up in T is the address of that second string that I actually typed in。

 And for all intents and purposes， that's like S pointing to this chunk of memory。

 T pointing to this chunk of memory。 So when I use literally equals equals to compare the two strings。

 That is compare the two char stars。 That is compare the two addresses clearly they're in different places。

 It's like asking the computer are O X1，2，3 and O x 4，5，6， the same。 Well， of course not。

 those are literally two different numbers in an hesmal or anything else。

 So we needed a solution for this。 And that is why we introduced St comp。

 the function that actually addressed this properly。 If I go back then to Vs code here。

 And instead of using equals equals。 I give myself access to our old friend now。

 the string dot H header file in that library is the definition the declaration of stir comp So I can do stir comp passing in。

😊。

![](img/8c4f64e556c9e456e704dee6118981ae_42.png)

Varis S comma T and recall what is the return value I care about。

 what is stir comp return if two strings are equal。 So return0。

 Otherwise it's a positive or negative number， which helps with alphabetization。

 but that's not what we want here， I want to make sure that the return value of stir comp equals equals0。

 And what does that do for me。 Well， if I open up my terminal again， make compare dot slash compare。

 and again， type in high exclamation point， enter and high exclamation point， enter now they're。

 in fact， the same。 but if I type something different like high and by those， of course。

 are different not on the basis of their addresses， but on the basis of their actual characters。

 And in fact， that's what's really happening。 the way stir comp is implemented by someone else years ago。

 is that they have some code， some kind of loop probably that first dereferences S and T respectively goes there。

 And then in some kind of loop。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_44.png)

![](img/8c4f64e556c9e456e704dee6118981ae_45.png)

Iterates over these two strings in memory， checking whether the individual chas equals equals each other。

 stopping once it hits backslash 0 in either string。

 And if they happen to look the exact same character by character， then it returns 0。

 It's a little fancier than that because it uses some less than or greater than to figure out if one comes before the other asbetically。



![](img/8c4f64e556c9e456e704dee6118981ae_47.png)

But it is doing the walking across this string。 So the person that implemented stirir comp uses a for loop。

 a while loop， whatever to do all that legwork for us。Questions on St comp or what we've just。

Revealed yeah。Good question。 Is it subtracting the ASciI values of the characters， not necessarily。

 It's probably comparing them with less than or greater than literally。

 because if you're comparing A And B， that would be like comparing 65 and 66 if capitalized。

 So you don't need to subtract anything per se。 You can just compare the magnitude of those values。

Yeah。😊，A good question。 Do we use two locations in memory for both the pointer S and the actual array of characters。

 Short answer。 Yes， and how that is happening is as follows。

 If I go back to VS code and highlight the lines of code that we just wrote。 for instance， line 7。

 the left hand side of the expression here creates those 8 bys in memory called S that will eventually store an a address of the first character of some string。

 The get string function written by CSs50 handles the process of allocating the array for H exclamation point and the back slash0 and puts it somewhere。

 I depicted it down here on the screen。 So getstr allocates one chunk and your code here allocates the other chunk。

 There are other ways to do this。 And in fact， once we completely take away the CS50 library。

 you have to allocate not only the left side， but also the memory for the right side of this expression。

 so to speak。 and we can do that in different ways。 And we'll come back to that soon。😊，Alright。

 so if we now know and appreciate that these two addresses are indeed different S N T。

 it turns out we can kind of play around with create some new problems， but also solve them as well。

 So how might I go about， for instance， let's see。😊，Seeing what we just did。

 if I go back into VS code here， let me just do something simple and no longer compare these。

 but just to make the point using our percent P format code now。

 I can actually print out the actual values of S and P。 if I want to S and T。

 if I want to convince myself of all this。 So I can print out sorry with percent P with the value of S with percent P the value of T。

 and in this case， even if I type the same thing， watch again what happens。

 make compare dots compare， I'll type in high， I'll type in high， and I should now see two addresses。

 but per the depiction on the screen， they do end up in different locations。

 They're similar locations。 these numbers are actually pretty similar but notice they differ down here A B and an F puts them a few bytes apart So they're actually next to each other in memory。

 but they're not， in fact， at the same location。 So that's what's happening underneath the hood。

 And just to be super clear。 it is rare if ever that you as a programmer will ever bother using percent P to print out an address。

Generally， we do not care where things are just using it for the sake of demonstration to make clear that we could go there。

 if we so want。 Allright， well， what if we want to make maybe manipulate these strings and actually change them in some ways。

 Let me do this。 Let me clear my terminal。 Close compareare dot C。

 open up a new file called copy dot C， whereby I might ultimately need to make copies of strings in memory。

 And let me go ahead and do this。 Let me include C 50 dot H。 So I can still use get string。

 Let me include how about standard I O dot H， as we often do Let me include string dot H。As we。

 as we now do in main void for my main function。 And then in here， let's do the same thing as before。

 Str S equals get string and prompt the user for that string。

 Then let's go ahead and copy the string as follows。 string T equals S。

 Then let's go ahead and capitalize the first letter of this string。 And it might be a little hazy。

 But we introduced the library a couple weeks back called C type do H。

 which has a bunch of functions related to types in C。 one of whose functions recall is two upper。

 which just uppercase is a character。 So what I'm gonna do here is I'm going change the first character of T。

 but not s to equal whatever the return value of two upper is passing in the first character of T。

 So I'm just changing the first character of T to be the uppercase version thereof。

 Now I'm gonna go ahead and print out the value of S is percent S back slash n。

 and'm gonna plug in S。 And then I'm going to do the exact same thing for T。

 So I can see both the before。😊，And the after version of my capitalized change。

 Let me open my terminal。 Let me do make copy。And I screwed up because I should be including not a C file。

 but a header file。 So C type dot H at the top。 unintended mistake。 make copy again。 that worked。

 dot slash copy。 And now this time， let me deliberately type it in all lowercase。

 H I exclamation point， because the whole point of T is to be uppercase。 If I hit enter now。

 I see a curiosity， both S and T were somehow capitalized for some reason。

 even though I only changed on line 12。😊，The first character of T。 Why might that be。

Why might that be， Let me offer a bit of a hint。 What if again。

 we take off some of these training wheels， S is just a char star as of today。

 T is just a char star of after today。 So what's happening such that I'm seeing the change effect both S and T。

 yeah。Yeah， I'm really copying literally S and T， which means both of those variables contain the same address。

 So even though I'm following T's address that leads me to the same location that S is pointing to。

 So I'm essentially changing the one and only one copy of high exclamation point。 In fact。

 we can see that as follows， if I open up my computer's memory。

 let me propose that S ends up over here， maybe high and lowercase ends up down here。

 maybe at those same addresses as before Ox12，3， therefore， S contains Ox12，3。 Meanwhile。

 T is a separate variable that I declared with almost identical technicalical code。

 but I then set it equal to S， which is like literally copying the value in S into T。

 if we now get rid of all these unnecessary addresses and just use abstraction。

 it's as though S and T are pointing at the same place。

 So it doesn't matter whether you follow S or you follow T。

 when you dereference either as is implied by the square bracket notation means go there。

 you're just changing the one and only copy of H。 And so whether you print。



![](img/8c4f64e556c9e456e704dee6118981ae_49.png)

Or T， you print out the capitalized version thereof。 So what's the solution here， Well。

 we actually need to be a little more clever when it comes to making actual copies up until now。

 super simple to copy integers。 Chars floats， longs doubles。

 all of those primitive data types super simple because code like that online 10 would just work。

 But whenever you're talking about something fancier， like a string， which isn't one location。

 It's sort of a sequence of locations， someone's got to do the hard work of allocating another chunk of memory copying the characters from old into new and somehow keeping track of all of that。

 Now， we'll do this ourselves in just a moment， but thankfully。

 there's gonna to be a library that can make our lives easier instead。

 So let me go ahead and do this。 Let me propose that。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_51.png)

We in V S code， improve this code as follows。 Instead of just blindly copying S and calling it T。

 I'm gonna actually use a new function called malloc。 We haven't needed this before。

 It's among the remaining tools in our toolkit and see。 But malloc stands for memory allocation。

 and it's a function that's super simply， lets you pass in as input a number。

 How many bytes of memory do you want and it will hand you back a chunk of memory。Specifically。

 it will hand you back the address of that chunk of memory。Specifically。

 the address of the first byte of that chunk of memory。 free is the opposite。

 once you're done with this memory， you can call free and give it back to the computer so that you don't eventually run out of memory。

 You can give things back when you're done。 So how can I now leverage this in my own code。

 will let me propose that I implement a copy a little more cleverly here。

 Let me go back to V S code here。 And instead of using。😊，Eals T。

 Let me instead say T initially should store the address of a new chunk of memory that's big enough to store the characters of S。

 The way I do that would be malloc。 And how many do I need。

 H I exclamation point in the null character。 I couldn't just get away with saying4。😊。

Me give me four bys of memory and store the address of the first byte in T。

 That is what line 10 is now doing。 Now， that's kind of a stupid approach。

 Like I shouldn't hardcode the number 4 because who knows what the human is gonna type in。

 But we have other friends here。 we can say figure out what the length of S is add one more byte for the null character and ask malloc for that many bys。

 because now， no matter how big or small S is， we're gonna ask for the appropriate number of bys。

 What is stored in T at this point in the story is the address of that chunk of memory。

 specifically the address of the first by in that memory。 Now。

 there's no null terminator or anything。 Everything in there at the moment is sort of garbage value。

 so to speak， until I put something there。 So what I'm gonna do now is this after I allocate that chunk of memory。

 I'm gonna use a four loop。 just like the authors of stir comp had。

 but for a different purpose for int I equals 0， N equals the string。😊，leength of S semicolon。

 And we've seen that technique before。 So we don't waste time calling Sterling again and again and again。

 I is less than n。 And then I plus plus， and inside of my loop。

 I'm going to copy into location I of T， whatever is at location I of S。

 effectively copying from left to right， all of the characters of S into T。😊，At the very end of this。

 I could do something。But I think there's I could do something to manually add a null character to the end of my new string T。

 But I don't think I have to do that。 The one time this makes sense is perhaps now。

 I'm gonna actually iterate from I less than or equal to N。

 because I actually want to copy the null character as well。

 So if the string is H I exclamation point new line。

 I actually do want to go from 0 to 1 to 2 to 3 and then stop。 normally， I would go from 0 to1 to 2。

 but I want to include this sort of secret null character there。

 So I think this for loop will capture that for me。 I'm not gonna change any of the rest of code。

 So all I have done that's different now is explicitly allocate a new chunk of memory 4 T and copy everything in S into T。

 But to use malloc， I need a new library。 I'm gonna go up here and include standard lib dot H。

 And again， you learn to practice what's in what library or you can go to manual C5 and。😊。

It up to figure out where in which header file something is。

 And I'm also going to include the same header files as before。

 So the only change is to add standard live。 Let me open my terminal window， make a copy。

Dot slash copy。 And now let me type in H exclamation point in all lowercase。

 And I should see in a moment the output of both S and T。

 But hopefully only one of them is capitalized T And indeed， I've done it somehow。

 So what actually just happen。 Well， if we actually go over to a visualization thereof here is my computer's memory when S exists if though I'm gonna allocate new memory with malloc。

 that's like calling malloc getting some chunk of memory， maybe it ends up here。

 maybe it ends up somewhere else。 I'm just keeping in the same place for discussion。

 and the first address happens to be O x 4，5，6。 Well， what gets stored in T。

 the return value of malloc and malllock returns。 The first the address of the first bite of memory。

 So what ends up in T is effectively O x 45，6， But who cares。

 will' just draw it abstractly as an arrow。 What does my four loop then do。 Well。

 it iterates over S and T in lockstep such that the H gets copied the I gets copied the exclamation point。

😊。

![](img/8c4f64e556c9e456e704dee6118981ae_53.png)

Getied And because I use less than or equal to， we also copy the secret null character as well。

 Then I use two upper on t bracket 0。 Here's T， here's t bracket 0。

 And so I think only the H and T is now capitalized。 It's not a particularly interesting exercise。

 but it does demonstrate really， with this few steps is possible how we can solve this problem of actually copying strings in memory by allocating enough space for them in that actual memory。

 But there is a caveat。 A lot of things， unfortunately。

 this week onward can go wrong when it comes to memory。 like your computer could be out。

 Maybe you have an older computer。 Maybe you have a really fancy program that has so many variables。

 so many arrays that eventually you run out of memory。 It's possible that malloc can fail。

 something can go wrong。 And Maloc will not， in fact。

 return to you the address of the first bite of memory available because if none's available。

 It's got to return something else。 So in cases of error， what malloc really return to you is。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_55.png)

![](img/8c4f64e556c9e456e704dee6118981ae_56.png)

Like I have no valid bytes for you。 And 0 itself is a number。 So that's a little confusing。

 And this doesn't really help with confusion。What malloc returns if an error happens is null with 2 Ls。

 This was stupid design decision decades ago to call the character 0 N U L。

 and the pointer 0 N U L L， But this is where we're at。

 So N U L L is the address 0 and it almost always signify something went wrong。

 We just need a special symbol to signify something went wrong when returning a value from malloc。

 So how can I use this， unfortunately， now， just like in some of the problem sets thus far。

 when you've started to add error checking to when things can potentially go wrong。

 your code gets a little more verbose。 But what I'm gonna do here。

 if I go back to V S code is the following， what can go wrong， Well， if。



![](img/8c4f64e556c9e456e704dee6118981ae_58.png)

T ends up equaling null。 That is if it has a bogus return value in it。

 that is not a valid memory address。 then there's not much I really can do。

 except like return1 just to signify error。 I could print out an error to the screen。

 I could inform the user somehow。 But if malloc returns null。

 I had better not proceed to try copying things from left to right into it because there is no memory there。

 That chunk of memory on the screen at bottom right does not exist if malloc fails。 Of course。

 So you don't want to go there and start blindly touching memory。

 let alone capitalizing memory that's there。 So I have to start adding in some of these error checks in this case。

 And in fact， even this is a little naive。 It's probably not safe to even assume that the user typed in any string at all。

 Maybe the human just to be difficult or making a mistake and just hit enter。

 So the length of the string is0。 You probably shouldn't try capitalizing0 either。

 And so what we should probably do down here2 to be super safe is only if the stir length of T。

Is at least greater than 0 then go ahead and capitalize it。 Otherwise。

 do not touch that memory either。 In other words， starting this week and next week。

 and even when we get to Python， you should start acquiring an instinct to code defensively。

 things can go wrong and your code and someone else's code。

 And if you do not handle those situations with ifs or else if or the like， your computer will crash。

 the thing will freeze or the like， And again， to tease the crowdstrike example。

 if you screw up and you don't check the boundaries of something， the length of something。

 who knows what can happen， because if you touch memory that does not belong to the typical behavior again is to crash to freeze to do some undefined behavior like that。

 Now， I will say this is getting really annoying。 I mean。

 I've written what like 30 some odd lines of code just to copy to strings that's a little unfortunate when this is probably a pretty common thing to do in the real world。

 So it turns out there are library functions like this too。 And in fact。

 I can get rid of a lot of my code here for copying， and I can actually。😊，Call a function。

 stir copy ST CP PY for sure， and pass in the destination， Pass in the source semicolon。

 and that will do all of the four looper， the while looper。

 However that person implemented it of copying one into the other。 The ordering is a little weird。

 It is indeed the destination comma source。 but that saves me the trouble of doing all of that。

Code myself。Questions then on what we've done here， the key details really being malloc。😡。

And one omitted detail， which we'll come back to yeah。你说的す。A really good question。

 Let me summarize if you allocate two variables that are happen to be next to each other in memory。

 but maybe you type in， excuse me， a very long string for one of them。

 Can one overflow into the other one， short answer， yes。

 And we're gonna talk about that briefly today。 The code I've written is not vulnerable to that at the moment。

 And in fact， among the things that getstr has been doing for us since week1。

 is it actually sort of crawls over the user's input。

 literally taking like baby steps to make sure that we only allocate more memory。

 more memory memory memory for every keystroke that you type in。 So theoretically。

 there should be no way to crash getstr unless you type in more bys than the system has even memory for it。

 But even that， we should be able to detect because we are somewhat inefficiently but very conservatively trying to avoid the situation you describe。

 But it is too common in life is again， with crowdstrike。

 you'll see that humans will make mistakes when it comes to the length of memory or rays that we have。

 Now I alluded to there being one mistake or omission here。

 that I somehow not practice what I preach。😊，A moment ago about Maloc and its cousin。

I never freed my own memory。 So technically， this program has what we would call a memory leak whereby I am asking for memory on line 11 via malloc。

 but I'm never giving it back to the operating system。 Now。

 this is a bit of an overstatement because technically， when the program quits。

 it should automatically give everything back。 But a lot of programs in the world keep running again and again and again。

 really forever。 like a clock program or a web server or an email server and the like。

 And if that code that you or someone else is written。

 asks for memory asks for memory and never hands it back freezes， crashes eventually。

 because the computer will somehow run out of memory。

 So it's an easy fix at the very bottom of this program once and only once I am done using T in the first place。

 I can simply free T and see itself or really the functions that we're using keeps track of how many bytes you asked for。

 you do not need to when freeing it， it will free that by onward that you requested。😊。

So free sort of does the opposite of then Maoc。 All right， unfortunately。

 we have so much power at our disposal now， lots of things can go wrong， But thankfully。

 there are tools that help you find these mistakes。 So that when if and when your program crashes。

 you don't have to just kind stare at the screen or ask a TF for another human for help。

 You can actually use software tools that other people wrote that detect these common errors。

 And one of these programs that you're now gonna have access to besides printf， besides debug 50。

 besides the rubber duck is a program called Valgrind。

 which is a command line program that whose output is a little scary looking。

 but it will allow you to look at your program for memory related errors。

 So let me go ahead and propose this， I'm gonna open up a program that I wrote in advance here。

 called memory do C。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_60.png)

And quite simply in V， S code， it looks as follows。 I have including standard I O。

 I'm including standard Lib so that I can use Maoc。 And this program does nothing useful。

 It just demonstrates as simply as I can a bug On line 6。

 I'm allocating a variable called X that's going be a pointer to an integer。

 And I'm allocating space for three integers。 So we haven't seen this before。

 but it just kind of does what it says， Give me memory for three of these things。

 What are these things。 Well， whatever the size of an int is， I know it's for， usually。

 So I could just write four times 3， but I'm gonna generalize it size of is an operator and see that lets you figure out what is the size of this type of variable。

 It's usually for， but on older computers， eventually on newer computers， it might not be for。

 So I'm not gonna write 4。 I'm gonna say size of int。

 So this whole line 6 gives me enough memory for an array of three integers。

 and it stores the address of the first byte in a variable called X。😊，So what's x 1 gonna be 72。

 What's x 2 gonna be，73， What's x 3 gonna be 33， Even in these four lines of code， there's two bugs。

Can you spot any of them yeah？我在。Yes， so I did not0 index my array。

 So that' sort of week 2 type mistake。 This should be X bracket 0， X bracket 1， X bracket 2。

 And there's a second more subtle mistake。But yeah。I don't have what。I don't have room。 Oh。

 I don't have room for the zero， but that's okay because I'm dealing with integers only。

 I'm not strictly trying to treat this like a string， but good eye。

 but only relevant to if I'm dealing with strings or cha stars。It's subtle。

 but we also talked about it like three minutes ago。Yeah， I didn't free the memory。

 So I called malloc， but I didn't eventually call free at the end of my function。

 So at least two mistakes。 it would seem。 Now you can reason through this。

 and there's only four lines of code。 So eventually you'd probably figure it out with some time and practice。

 but could a program help me spot these mistakes。 Well， debug 50 is not relevant here per se。

 And your program crashes。 debug 50 can probably tell you on what line it crashed。

 but not necessarily why what we need is a memory related program called Valgrind and to do this to use it。

 I'm going to do the following。 I'm going run make memory， And if I do dot slash memory at a glance。

 nothing seems to go wrong。 It didn't even crash， but it's still incorrect。

 And especially if I have these kinds of bugs in larger software。

 It's definitely going to crash eventually。 So let me do this instead。

 let me run this program called Valgri on dot slash memory。

 So just like you run debug 50 on dot s something。 you run vgri on dot slash memory。

 let me increase the size of my terminal window because there's gonna to be a lot of ugly output here for a moment and hit enter。

😊。

![](img/8c4f64e556c9e456e704dee6118981ae_62.png)

And you'll see a whole bunch of cryptic output in a lot of numbers。

 which largely aren't useful for us。 till we get to the error messages。 So I ran the command up here。

 I saw all this crazy output， but what's germane。 Well， here I have invalid right of size 4。

 It's a little technical。 But that just means I'm changing something that involves4 bys。 Well。

 what does that mean， Well， apparently， my mistake is in memory dot C line 9。

 And it's elaborating with some cryptic addresses， which again， I don't really care about。

 But I do care about this， after a block of size 12 is allocated。 So there's 12。

 like evidence that there's indeed an array of three ins， which total 12 B。 So that's consistent。

 But what's going on， it's at line 9。 Well， how did I somehow touch4 bys that I shouldn't。 Well。

 if I go back to my code by shrinking my terminal window。 Look at line 9。 It did not like。

 as you observed the last element of the array， Because I one index， instead of 0 index。 O。

 I think my fix is。😊，Be to change this to 0，1 and 2。 So 0，1 and 2。

 But let's go back to the errors because there was another one on the screen。 If I ignore anything。

 I don't really understand。 in this summary， here's something。

12 B in one blocks are definitely lost in lost record 1 of1， more verbose than ideally it would be。

 But that problem seems to relate to memory dot C line 6。

 So I'll admit vgar's output is sort of a big， complicated mess。

 But there are little hints of diagnostically useful information。

 like invalid right of size 4 and the line number of the file。

12 bys in one blocks are definitely lost in memory dot C and line number。

 So those are the kinds of things you want to look for。 even if at a glance。

 it is and will look confusing。 So let me go back to now line 6。 And oh， line 6。

 even though it's not obvious， what's wrong with this line。 If I'm somehow losing 12 B。 Well。

 it must be a memory leak。 So let me just have the intuition to go in and say， oh， eventually。

 I have to free X because X is pointing at that chunk of memory。

 Let me now clear my terminal window down here。 make memory again。Dot slash memory。

 and it doesn't seem to crash still， but it is more correct， even though at a glance。

 it seems fine either way。 Let me do now vgrind of dot slash memory。

 Let me increase the size of my terminal window， clear the screen and hit enter。

 And now there's slightly less output。 But what I really like is the sound of all heap blocks were freed。

 Whatever that means， no leaks are possible。 And even though there's still a lot of output there。

 I don't see anything glaring anymore。 So Valgrind， too， this week and next week。

 will be your friend。 And all it's doing is helping check for memory related mistakes in your code。😊。

Questions， then on Valgri。Yeah， in front。Can you set a condition before you free the memory。

 you could， in this case， logically， there's no reason to。

 because this program is so relatively simple that I do want to free it no matter what。

 but you can absolutely have conditionals in there which you might in more complicated programs。😡。

Allright， well let's play around slightly more with with these garbage values to which I alluded earlier。

 Let me actually close this。 Let me code up a file called garbage do C。

 just so we can make the point that there can be these so-called garbage values in a computer's memory that are really remnants of something else that has been at that location and memory before。

 and I can actually do this pretty easily。 Let me in garbage do C include standard I O dot H。

 Let me go ahead and do whoop standard I O do H。 Let me go ahead and do int main void inside of my main function。

 Let me just give myself an array of like a lot of scores to come back to like week2 when we introduced arrays。

 supposeupp I very sadly， have 1024 scores to keep track of the course of college。

 I now my iterate over those as follows for int I equals 0。 I is less than 1。

24 I plus plus and inside my four loop。 let's just blindly print out those values percent i backlash N scores bracket。

😊，I the problem， though， is that I have neither hardcoded those actual scores into this program like we did in week2。

 nor have I prompted the user for the scores with get int or anything else。

 So who knows what I'm going to be printing 1024 times。 Well， let me open my terminal。

 let me do make garbage。 pun intended， let me increase the size of my terminal window dot s garbage。

 and I should see 1024 values eventually will be my scores， but who knows what they are now， enter。

 it's a mix of some really good and some really bad scores it would seem some zeros。

 some small numbers， some big numbers， my God， some negative numbers， which isnt good for scores。

 but they're all over the place。 And if I scroll up， I could count them。

 there's indeed going be 1024 of them， but they're garbage values。

 and that I can't make head or tails of what they actually are。 As an aside。

 this has nothing to do with C， but the operating system Linux that we're using here does have commands that you can run if you are getting overwhelmed by output。

 So for instance， if I run garbage。Again， if there's you know there's gonna be more output than you can see at once and you don't want have to bother scrolling back through time。

 you can actually do what's called piping it to a program called less。

 which is the name suggests will show you less of the output at a time。 one screen at a time。

 So if I hit enter now， I only see the first screen until I hit space space space space and so forth。

 And it will paginate the output for me and I can just hit Q when I'm done with that。

 So it doesn't change my code doesn't change my program just a handy command line trick if you're ever overwhelmed by the amount of output there。

 But these garbage values can really get us into trouble。 And in fact。

 let me propose to consider another program that's a little arbitrary。

 But it's going to use some of today's building block。 So here's a main function。

 And at the top couple of lines here。 I'm doing this。

 I'm creating a variable called X that's gonna store the address of an in。

 I'm creating a variable Y that's gonna store the address of an in。 So far， so good。

 I haven't assigned them any values yet。 but that end。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_64.png)

Self is not problematic， I can always assign them values later， like any variable。

I'm now going to allocate enough bytes for the size of an int。

 You and I know it's probably going to be four， but I'm doing it dynamically asking for the size of an integer。

 And I'm storing the address of the first byte in X。

 But notice what I'm not doing is storing anything yet in Y。 The next line of code here。

 I'm sort of using the Sentinel value 42 and storing that at the location in X。

 So the dereference operator says whatever address you got from mallc。

 go there and put the number 42 there。This next line says go to the address in Y and put the number 13 there。

 but I've highlighted in red this time Y。😡，This line will probably crash。Why， intuitively？

🎼We haven't given y a value。 I didn't copy S's value。 I didn't mall anything for y。

 It contains a garbage value。 Maybe it's0 like we saw on the screen。 it's a really big number。

 Maybe it's a big negative number。 Who knows。 but that's like saying go there and like put this number 13 in some random。

 unlucky location。 And again， programs probably going to crash， freeze or something else。

 The other lines here are okay。 eventually， I get around to copying X into Y。

 giving it a valid value and then going to Y value and assigning it the number 13。

 So that one line of code was the problematic one ultimately。 So what's nice about this code。

 is that it actually happens to the line up perfectly with a fun video that our friends at Stanford University put together。

 That's about two minutes long。 And it introduces a character that's wellknown in computer science spaces as binky。

 So a professor Nick Parlante of Stanford spent some time doing some clayation to bring exactly that code and exactly that problem to life。

 if we could dim dramatically the lights。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_66.png)

![](img/8c4f64e556c9e456e704dee6118981ae_67.png)

Hey， Benki， wake up。 It's time for pointer fun。 What's that。Learn about pointers。Oh， goody。Well。

 to get started， I guess we're going to need a couple pointers。Okay。

 this code allocates two pointers which can point to integers。Okay， well， I see the two pointers。

 but they don't seem to be pointing to anything。 That's right。 Initially。

 pointers don't point to anything。 The things they point to are called pointees and setting them up a separate step。

 Oh， right， right。 I knew that。 The pointpointees are separate。 so how do you allocate apointee。Okay。

 well， this code allocates a new integer point T， and this part sets X to point to it。Hey。

 that looks better。 So make it do something。Okay， I'll dereence the pointer X to store the number 42 into its point E for this trick。

 I'll need my magic wand of dereencing。 your magic wand of dereencing。 that's great。😊。

This is what the code looks like。 I'll just set up the number， and。Ny， look， there it goes。

So doing a de reference on X follows the arrow to access its point E。 In this case。

 to store 42 in there。 Hey， try using it to store the number 13 through the other pointer。 Why， O。

 I'll just go over here to Y and get the number 13 set up and then take the wand of D referencing and just W。

 Oh， hey， that didn't work。Say， Binki， I don't think dereencing Y is a good idea because， you know。

 setting up the pointee is a separate step。 And I don't think we ever did it。Good point Yeah。

 we allocated the pointer Y， but we never set it to point to a point D。Very observance。 Ey。

 you're looking good there， Binki， Can you fix it so that y points to the same pointee as X。 Sure。

 I'll use my magic wand of pointer assignment。 Is that going be a problem like before。 No。

 this doesn't touch the pointees。 It just changes one pointer to point to the same thing as another。

😊，Oh， I see。 Now， Y points to the same place as X。So wait， now y is fixed， it has a pointee。

 so you can try the wand of dereencing again to send the 13 over。Okay， here goes。A， look at that。

 Now， dereencing works on why。 And because the pointers are sharing that 1 point E。

 they both see the 13。 Yeah， sharing whatever。 So are we going to switch places now， Oh， look。

 we're out of time， but。Alright， so Bicky's purpose in life is really to make clear that bad things can indeed happen when you touch memory that you shouldn't。

 including things that we now know as garbage values。 But there's even other problems。

 but also solutions that we now have access to thanks to our newfound understanding of memory and inter turn pointers。

 So it's been very common over the past few weeks， especially last week to have to swap values。

 like when we were doing bubble sort or selection sort。

 we kept having our human volunteers swap locations and in the computer's memory or in our pseudocode。

 we had to have two variables or two values swap locations as well for this。

 we thought we'd motivate folks we can offer you either little Mario mushroom or question mark。

 if wed get one more volunteer today to act a little something out with me here。

 Don't all raise your hands at once。 How about I saw the Harvard shirt that shirt， yes。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_69.png)

Yeah no， you yet come on down。 Yes， the one who wanted to keep using string as a type de before。

 maybe a round of applause to break the awkwardness here。

For the other volunteer you had you hand up catch my eye next time， too。 But for now。

 we just need one of you and come on up。All right， you want to introduce yourself to the world。Hi。

 my name is Gabe。 Gabe。 Okay， and a little something about yourself。 I live in there。 I'm a freshman。

 nice， alright， well， good to meet you。 Come on over here where we have two glasses of water。

 One is pink。1 is blue， and each of these effectively represents like a variable that contains some value。

 either pink or blue。 Could you go ahead and swap the two values of these glasses。😊，Okay。

 that's technically just like moving the variables around in memory。

 but I'd really like you get to get the pink water in the blue glass and the blue water in the pink glass instead。

 So let me undo that。you're hesitating why because if I pour the blue in the pink。

 then they're gonna blend together。 Yeah， and you're gonna sort of overrite the value with the other。

 And so we're gonna lose information in that case。 Okay， okay， so this was a bit of a setup。

 So let me get you a third glass or a temporary variable， if you will。

 And if you want to verbalize how you would solve the problem now with this third variable。 Okay。

 so I'm gonna pour the blue into the new variable。 And then。😊，Pour the pink into my old blue cup。

 nice。And then pour the blue back into the old pink cup。 Very nice。

 I think that that warrants a round of applause， if we could。😊，Okay， so like really that。Okay。

Which would you like， Oh Al right。 So thank you to Gabe。 So。

 this was all to make the point that swapping is not that hard。

 And we all have kind of an intuitive notion of how to do it， but we do need。

 it seems like a temporary variable。 And that actually maps pretty cleanly on the C code。

 So how might we do this in practice。 Well， if we want to implement a actual function in C that does swapping for instance。

 I might do。😊，If we want to actually do something in C that involves swapping。

 I might do something like this。 avoidvo function because I don't need to return a value。

 I just need to do some work。 Fun called swap。 It's gonna take in two values in a and in B。

 And the goal in life here is to swap A and B。 It's actually pretty straightforward。

 I could actually do lines of code like this， calling a and B the two inputs like the pink and blue glasses temp or TM for short for the temporary variable。

 And just as Gabe did， I can store in the temporary variable one color of liquid or the value of a。

 I can then change a to be that of B。 And then I can copy the value from the temporary variable to B。

 And at which point I don't care about temp anymore。 This code is correct。

 It would swap those values just as Gabe did with the glasses of water。

 But it's only going to work inside of the scope of swap。

 And this is the catch recall it when we introduced the notion of scope earlier a few weeks back。

 we said that variables really only exist in the context of the curly braces in which they were defined。

 or in this case， as part of the arguments passed into the function。 So this success。😊，Ss A and B。

 But if main or any other function is using swap， it's actually not going to have any useful effect on the original values of A And B。

 In fact， let me go over to VS code here， where while Gabe was doing that。

 I whip up this program in advance。 and it looks like a lot。 but it does something relatively simple。

 I've got main， which declares two variables。 X and Y values of one and 2。

 I'm then just printing out X is this， Y is that， I'm then calling a swap function。

 And then I'm just printing the same thing。 X is this， Y is that。 the whole point being。

 hopefully it'll say the opposite the second time。 What is the swap function。

 exactly what I just proposed earlier， which is exactly what Gabe just did correctly with the glasses。

 But as you might see where we're going with this。 If I go into my terminal window and say make swap dot slash swap enter。

😊。

![](img/8c4f64e556c9e456e704dee6118981ae_71.png)

It doesn't actually seem to affect the values of X and Y。 It does affect the values of A And B。

 And I can see this。 if I use our old friend debug 50。

 let me go ahead and set a break point inside of swap。 Let me run debug 50 on dot slash swap enter。

 And just to demonstrate what's going on here。 let me step through a few of these lines of code as follows。

 So notice one at top left， T has some bogus value initially， it's a garbage value。

 It's like putting some random color inside of the glass。

 but I kept it empty because in the real world， we need space for the colored liquid。

 But A is one and B is2。 Y， because we passed in X and y respectively。 If I now step over line 17。

Notice that temp changes to 1。 If I step over line 18， A changes to 2。 If I step over line 19。

 B changes to 1。 So A and B per Gabes algorithm were swapped correctly。

 But if I continue running this program all the way to the end， ultimately。

 I got because of the second printf that X is still one and y is still two。

 So A and B were changed clearly per the debugger， but X and y were not。 So why is that。 Well。

 it turns out that the answer to that too relates to memory and code like this。

 at least if encapsulated in a function， is not correct。

 precisely for the matter of scope because we're changing the values of variables that are local to the swap function。

 but has no effect on main that's actually using this function。

 And the reason for that is a term of art， when you pass arguments to function。

 you're generally passing things by value。 You are passing in copies of those values。

 So when you pass an X and y， you're really。In a copy of X and a copy of Y that you can do anything you want to。

 And we're calling them A And B in the context of swap。

 But that has no effect on the original versions of X and Y。 What's really going on， though。

 can be thought of again in terms of the computer's memory。 So here's a chip of memory。

 Let's kind of zoom in abstractly on the sort of grid as we keep describing this。

 And consider that we can use this memory in bunches of different ways。

 But the world has standardized how we use computers memories when running programs。

 And we tend to use this part of memory at the top。

 So to speak in certain ways and this type of memory at the bottom in other ways。

 And if we understand what those ways are， we can actually infer deductively why this function is not working as intended。

 So it turns out let's even get rid of the individual bytes because we don't really care about numbers for now。

 It turns out that when you double click a program on your Mac PC or tap an icon on your phone or run dot slash something on your code space。

 the computer automatically loads the program's machine code， the zeros and ones that someone。😊。

Compiled or maybe you compiled into the top of your computer's memory。 so to speak。

 It's not literally the top because who knows how the thing is oriented。

 but just for the sake of discussion up here。 What else gets loaded into the computer's memory。

 if your program has any global variables to find outside of main by convention。

 they go below the machine code that was loaded into memory。

 What else if you end up using malloc in your code， that memory comes from this location here。

 which we didn't do until today， But actually it turns out that get string has been using malloc all this time since week1。

 because that's how we're getting an arbitrary amount of memory for everything you might type in at the keyboard。

 the heap， though， so to speak grows downward。 So the more and the more and the more and the more you call malloc。

 the more stuff that gets filled up top to bottom in the socalled heap。

 But there's one last region of memory generally called the stack much like a stack of trays in the cafeteria or dining hall that sort of works its way up as you continue putting stacks trays。

 tray and tray on top of each other。😊，The stack， so to speak。

 grows upward and the heap and the stack are used differently。 The heap is indeed used for malloc。

 but the stack is used anytime you call a function。 Anytime you have local variables。

 they use memory down here。 So in particular， for the code I just wrote a moment ago where I had a main function and a swap function。

 the stack gets used to implement this kind of logic as follows。 I first unbeknownst to me。

 my computer does this for me， I get a chunk of memory at the bottom of my computer's memory space that contains any command line arguments。

 if we had int Arg C and char and string R V like a couple of weeks back。

 or if I have any local variables like X and Y。 if I then call a function like swap swap gets its own chunk of memory。

 It own frame of memory above main in the computer's memory。

 So it's like putting down a main tray from the dining hall and then a swap tray on top of it from the dining hall。

 Each of them contains their own local variables， X and Y here， A And B here。😊。

And you can kind of see where this is going already。 If X and Y live here。

 But we're changing A and B here， Well， obviously we're not changing X and Y down here。 Well。

 let's be a little more specific in the main function， when I have two local variables like X and y。

 It's like having space for them in the computer's memory。 And initially。

 I had values  one and two respectively。 When I then called the swap function。

 that had two local variables of its own， technically arguments passed in which because I'm passing by value gets copies of X and y called A and B。

 but the values are gonna be the same initially， one and2 respectively。

 But then in the three lines of code that represent what Gabe did with the the glasses of water does is we have a temporary variable。

 a third， still in the same frame of memory。 And I signed with this code here。

 let me step out of the way。 this first line of code stored the value of a in temp like this。

 the next line of code stored the value of B in a like this at which point， unfortunately。

 theyre identical， but no big D。😊，Because like Abe， we kept the temporary variable around。

 and then we can store the value of temp inside of B。 Now， as an aside with respect to the debugger。

 we pulled up earlier， as well as a couple of weeks back。

 when you've looked at the top left of the debugger window。

 and you can see your local variables what you're seeing in the debugger is either these variables。

 if you've set a break point in main or these variables， if you've set a break point in swap。

 the debugger is just showing you what variables are in scope。

 what is scope really mean it's a slice of memory at that moment in time effectively。

 And we've been simplifying it verbally by saying what's between the curly braces。

 But that's the simpler way of describing really this。 Now we don't care about temp， eventually。

 what we do care about is having swapped these values。 But unfortunately， as soon as swap returns。

 Well， mains X and Y are literally left unchanged because we only passed in copies thereof。

 So the fundamental problem seems to be that the swap function is logically correct。

But it has not been given access to the。Lo of X and Y in memory。

 What swap really needs is a treasure map， so to speak， that leads it to the actual location of X。

 the actual location of y， so that using like the star operator。

 it can go there and go there and swap the actual values inside of main's frame of memory。

 So what we really want to do is what a computer scientist would call pass by reference or pass by a address would be the same thing in this case。

 whereby what I want to do is not this code per se， which is logically correct。

 but doesn't fundamentally change the calls variables。 X and Y。 Watch the delta here。

 This is correct。 And it looks crazy scary at glance， because there's all this new syntax。

 But it's really just the same syntax from the start of today， used a few different places。

 What I'm saying now in this correct version of swap， is that a is not gonna be an int per se。

 It's the address of an int。 and B is gonna to be the address of another int。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_73.png)

This is my sort of treasure map whereby A and B are going to contain the addresses of X and Y。

 What am I going to do， Well， temp is still just an int。 It's still just an empty glass。

 but if I want to store the value at a in temp， I have to go to a and store it in temp。

 I have to go to B and go to a and put the ladder in the former， the former in the ladder。

 I the first in the second， then I go and get the value of temp and put it at the address in B。

 So exactly same logic， exactly what gavebe did just way more syntactically involved， but again。

 it's just using pointer declarations up here and pointer dereferencing down here to go to those locations in memory。

 And in fact， if I make this change in my own code here， let me go back to V S code。

 and let me hide my terminal， let me make these changes。 So pass in the address of an int。

 the address of an int， dereference a， dereference B。



![](img/8c4f64e556c9e456e704dee6118981ae_75.png)

Reference A and D reference B。 It's almost done， but I do have to change one more line of code。

 And based on what we've discussed thus far， how does line 11 need to change。

I no longer want to pass an X and Y。The address of x and the address of y。

 which involves the syntax ampersand X。And ampersand Y。 So again。

 syntically way scarier than it once was。 But it's just these simple building blocks。

 Get me the address of X and then go to that address as with the star operator。

 So let me open my terminal window again。 Let me do make swap， enter。 It's airing now。

 But why I've made a subtle mistake。 It doesn't like the effect that I've passed in the address。

 But wait a minute。 Let me scroll up。 What else needs to change。The prototype here。

 So this also needs to be matching the actual implementation。 So sort of newbie mistake。

 But I think now， if I do make swap again does compile dot slash swap， I should see X is 1， Y is 2。

 and then hopefully indeed， the opposite。 So this version of swap correctly swaps the value。

 because now I have a correct understanding of what is going on inside the computers memory。

 And indeed， if we look at this code now in the context of the stack frames。

 let's see what now happens。 So here is again， the same setup。 main has variables。

 X and y equaling one and 2。 swap gets called。 But what are A and B。

 They're no longer the values of X and Y。 But the addresses of X and Y。

 I don't care what those addresses are。 So I'm going to abstract it away with some simple arrows。

 But these are sort of like the treasure map。 I keep referring to the breadcrumbs。 However。

 metaphorically， you want to think of it， A and B now lead to X and Y。

 So you're passing things in by reference， so to speed。



![](img/8c4f64e556c9e456e704dee6118981ae_77.png)

![](img/8c4f64e556c9e456e704dee6118981ae_78.png)

![](img/8c4f64e556c9e456e704dee6118981ae_79.png)

![](img/8c4f64e556c9e456e704dee6118981ae_80.png)

And therefore， swap can manipulate those values。 Now， as an aside。

 pass by reference is really the same idea as pass by value。

 but the values you're passing in are the addresses instead of the actual value。

 So it's sort of just context dependent as to how you think about that。

 But passing by reference means really you're passing in by address。 Allright， So with that said。

 step by step， What's happening， I'm going to a， which is going to contain the value1。

 and I'm going to store that in temp。 So what I should see in temp still is one。

 Now I'm going to go to B。 And what I should see at B is 2。 and I'm going to put it at star A。

 which is the same thing as2 here。 Then lastly， I'm going to grab temp， which is one。

 and I'm going to put it at B， which is like following that arrow and changing that to one。

 And this then pictorially， is why my new version of the code。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_82.png)

![](img/8c4f64e556c9e456e704dee6118981ae_83.png)

Indeed， works as expected and better still when swap is all done and that frame of memory is taken away。

 It sort of it's still physically there， but we don't care about it anymore。

 So we might as well think of it as just disappearing。 The change has， in fact。

 permanently affected Ma's version of X and Y。Questions， then。On this trickery。Yeah。Sorry。

 a little letter。A good question。 When a function returns， does it stack disappear。

 typicallyyp know you still have remnants of all of those values that were once there。

 unless the compiler of the computer has sort of scrubbing that memory。

 which is not typically done for performance reasons， And so there could be remnants of past things。

 So as an aside， your mind is actually going in an interesting adversarial way place。

 because suppose there was some function that you're calling， that involves passwords， for instance。

 and the user types in their password and their password is stored at that location and memory。

 even if there that function returns， if the code is not implemented with any kind of rigor in place。

 you could somehow maybe if you have malicious access to the code access that memory location。

 where there's the garbage value， but that garbage value is useful because it's someone's actually password。

 actual password。 and in fact， that's a threat that has indeed happened from time to time。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_85.png)

So here then to recap the bad code， but logically correct， just doesn't get the job done。

 The green code， of course， does get the job done for exactly those same logical reasons。

 but there's another problem we've now created。 even as we understand how the stack's working。

 And I claim that the heap is where malloc takes memory from。

 having like two arrows pointing it does not seem like a very good design because if you keep using he by calling malloc a lot。

 you're going to eventually overflow the stack or if you call lots and lots and lots and lots of functions as you might with recursion or some other technique。

 you might overflow the stack like a big stack of trays eventually toppling over and touching things that it shouldn't either。

 Unfortunately， there's no real solution because you only have a finite amount of memory。

 So it doesn't really matter things go this way or this way。

 eventually you're going to either run into other chunks of memory or run out of memory altogether。

 So strictly speaking， this isn't such a bad thing unless you let things get out of control and you don't keep track of how much memory you're using or defensively make sure you're freeing。



![](img/8c4f64e556c9e456e704dee6118981ae_87.png)

As much as you can。 And there are terms of art out there like heap overflow。

 which means if you call malloc too many times you might somehow overflow some other area of memory with the heap。

 Some of you might know a popular website called stack overflow。 Well。

 what is the etymology of that website Sta overflow is when you call so many darn functions that they overflow each other and maybe hit the heap or overflow each other in some way。

 you're overflowing the memory region known as the stack。

 These are generally examples of what are called buffer overflows where buffer just means a chunk of memory that you're using for some purpose And so a buffer can certainly overflow another。

 especially if you're treating it as a chunk of memory this big。

 but you start poking around past the end of it。 It's like allocating an array for four characters but trying to print the fifth or the sixth or the hundredth or the thousandth。

 if you've not asked for it， you're overflowing the buffer you've been given。

 So an array is just a buffer and YouTube and Netflix。

 they all have buffers into the colloquial sense and that they might pre downloadload a few seconds or minutes。

Video storing it in a chunk of memory， like an array， or maybe somewhere on the heap。

 But the point is a buffer is a finite size， and you can potentially overflow it by going past the boundary of it past the end。

 or maybe even past the beginning。 And thus was the issue with the real world a few months back with crowd strike。

 So this is very popular security related software， Ironically。

 that a lot of the world has installed on their servers to keep themselves safe for those unfamiliar。

 unfortunately， this very software crashed some months back taking down very important systems with it。

 including Delta airlines as sight and so many other companies。

 And this cost the world millions of dollars probably in lost labor and effort because systems went down。

 Sales were lost。 Human time was incurred。 And it boiled down in retrospect to the stupidest of bugs。

 if I might say， if you read through their very long Pf。

 They postmortem that describes what exactly went wrong， which took a few weeks。

 I believe to come out。 There was this paragraph here， which actually sounds like a lot of big words。

 sensors that received the new version of。

![](img/8c4f64e556c9e456e704dee6118981ae_89.png)

Channel files 2，91， carrying the problematic content were exposed to a latent out of bounds read issue and the content interpreter。

 Like the real interesting part is the last sentence。

 The content interpreter expected only 20 values。 Therefore。

 the attempt to access the 21st value produced in outof bounds memory read beyond the end of the input data array and resulted in a system crash。

 So literally， even though you're only in a class like this for like a couple of months time now。

 they had an array of size 20， and they wrote code， they tried to access the 21st element。

 They touched memory they shouldn't have the software froze or crash。 therefore。

 the systems that froze or crashed and cost the world millions of dollars in downtime and other side effects because of one off by one error。

 So it's a very possible danger to trip over And among the downsides of languages like C is that they make it very easy to do this。

 There is nothing in C stopping you from doing this and a few other languages allow this。Well。

Other languages like Python and Java generally prevent you and me from doing this Why。

 because humans for years were writing so much darn buggy code that we realized， wow。

 we should probably build into the programming language defenses against this stuff。

 So with the right language in the right know how， you can avoid these problems altogether。

 But in this particular case， they had code that similarly was not sufficiently tested。

 They didn't have a check 50 to tell them a priori whether or not the code was correct。

 And so they ship this to computers around the world as an aside too。

 this is one of the dangers of automatic updates。 if you have this on your phone or your Mac or。

 let alone your corporate servers。 if you update automatically your systems。

 but the update itself is buggy， you can therefore take down your whole system personally or professionally。

 there's a lot of real world implications to that business decision they made。

 it seems to update so unilatally unilaterally as well。 So beware。 But these things happen very。

 really in the real world。 Okay so let's take things down back to sort of like C 50 land here。

 Here was the functions。Tining wheels that we've been using since week 1。

 And let's just consider for a moment how one of the most powerful of these does Let's consider for just a moment how one of the simplest of these actually works。

 namely get int。 So it turns out and C it's not that hard to get an in or a char or a float relatively simple。

 at least in a safe way。 Strs are the scary one， Because who knows how many characters the user is gonna type in and you would seem to have to decide in advance。

 Do I want room for one character4 characters，10，1000。 What if I get the number wrong。

 And they type in a really long paragraph ins and chas and floats are easy because there are4 by or1 B or4 Bs。

 you sort of know in advance。 So let me propose that we implement a simple problem。

 a simple program that really kind of implement the idea of gett int。 So first。

 let me open my terminal and clear it， Let me open a new file called get dot C。

 because I'm gonna implement my own functions for getting input。

 I'm gonna go ahead initially and actually still use C 50 dot H And I'm gonna use standard I O do。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_91.png)

And then in main， I'm going go ahead and very simply， as in week1， do this。

 Int n equals get int and just prompt the user for n。 So nothing interesting there。

 And then quite simply I'm gonna print out using percent I'm gonna print out using percent I。

 the value of n passing in N。 So again， week1 stuff。

 no memory no explicit use of memory or pointers here yet。

 make a get dot s get type in 50 program for now seems to work。

 But suppose I take away truly the training wheels。

 not just for the keyword string but for the get int function as well。

 And I take away this header file， which means get int no longer works。

 How could I implement this instead。 Well， without C50's training wheels。

 You can still solve this problem。 You can declare an int called n and don't give it a value initially because you want it from the user。

 I can then prompt the user with like a printf n colon space with no new line because I just want to a blinking prompt for the user。

 which get in does for you automatically。Otherwise。

 and I can use a function called scanf to sort of scan the user's input for some format string。

 So for some type of formatted text， maybe it's an int， a float， a string or something else。

 So scanf is sort of like the opposite of printf printf print something scanf read something from the user themselveslf。

 Allright， So how can I use this。 I can call scanf， I can say。

 what do I want to scan from the keyboard， so to speak。

 and I want to scan in an integer from whatever the human types， Where do I want to put that integer。

 Well， I can't just say put it in n。 because you can't change I want end to persist。

 I want to tell it to go to the address of n and put it there wherever there actually is in memory。

 So again， just like with swap。 if I want another function to be able to change my variable。

 can't just hand it the variable， I have to hand it the address of my variable。

 And scanf is designed to expect that。 Now is my last line。

 I can print out N colon I backlash n and now print the value of N。😊。

So it's a bit of more of a mouthful。 I've got like 2，3 lines instead of my one with get int。

 But I think it'll work。 Let me do make get do get and type in 50。 for instance。

 enter and it does seem to work。 And effectively， this is what get int is doing。

 get in is a little smarter because， for instance， if you don't type an int and you type in cat or dog or bird or something else like weird things will happen。

 So we make sure that if you don't type in something that's actually an int。

 we prompt the user again and again and again， using our own loop。

 So we sort of handle that error checking for you。 But if I want to do this with a string。

 how might I go about doing this。 Well， let me go back into my program here after clearing my terminal。

 And let me just kind of do the same thing but with strings。 I could say string S。

 But we know strings don't really exist as a data type。 So I'm gonna more explicitly。

 say char star S like that's effectively a string or placeholder there。

 let me print out a prompt for that string， just say S colon just because I want the user to。

Ppe in a string for me。 And now I'm gonna to use scanf again。 What do I want to read from the user。

 Well I want to read a string。 And so just like printf。

 I use percent S to scan a string from the human keyboard。 And now after that。

 I need a place to put it。 Well， I think I want to put it in my string S。

 I don't need an a percent here because S is already a cha starts。

 It's already the address of a string， if you will。 But now if I go and print this。

 I'm gonna say S percent S back slash N just as before。 So it's the exact same logic。

 but this line of code is now dangerous。 And this is why we give you get string。

 And this is why more of the world should use libraries instead of doing this。

 why is this line of code on line 7 dangerous。Or undefined what it will do。Yeah， a little letter。

It doesn't know where my string is gonna end or more specifically。

 It doesn't know how much memory is available for that string。 At the moment。

 the only memory I've allocated implicitly is 8 B for the pointer called S。

 So I'm ready to jot down in memory where I want to put this string。

 but I never initialize S to anything previously， when I wanted to initialize S to something。

 I could， for instance， malloc some space。 or I could even do something like I could specify that。

 let's get out of the pointer business today。 And let's actually just say that S is an array of like 1000 characters。

 And that would mean I have 1000 places where I can put that chunk of memory。

 So turns out there's an implicit relationship between pointers as we've seen today and arrays whereby you can treat one as as the other。

 But for now， let me stick with this model of making clear that I did not call malloc。

 And so S contains a garbage value， which is like saying whatever the user types like over like there somewhere random。

 It's a garbage value and that's probably going cause the computer to crash。😊，Not always。

 And I don't know what to expect today， but let's try this。 make get dot slash get enter。

 Let's type in high exclamation point。 I got lucky。 It still worked。 Let's do something random。

 like just type a lot of characters that will hopefully overflow the buffer that doesn't even exist En got lucky。

 But if I do this again and again， I know ideally， that would have made an educational point。

 But again and again and again， eventually it will probably crash on me。 It's certainly incorrect。

 And I bet we could figure this out with Valgri if we start poking around with that tool as well。

 So what's the solution here， what's really the issue。 Well， if we consider where we started。

 if here's my memory。 Let me actually put a lot of Oscar the gruches here to make clear that like before you use memory。

 it's effectively garbage values。 Like who knows what is there。 So in my first program。

 when I created variable N， I actually used 32 of those bits or four of those bytes to put a legitimate pattern of zeros and ones to represent the number 50。

 So that part was good。 But when it got to the string version， I allocated。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_93.png)

Space for the pointer，8 byte， as I said earlier， but I never initialize S to anything to malloc to like an array。

 like literally nothing。 So S is value is literally this sequence of garbage value。

 So who knows what it is pointing to， there is certainly no memory allocated elsewhere。

 like in the heap for whatever the human actually types in。 So this value is effectively garbage。

 and this is the best I could do with squiggly lines。 like who knows where it's pointing。

 Certainly nowhere where valid。 And so in this case， I got lucky， it did not crash。

 but the more run the code， the bigger the input it is odds are this will， in fact。

 crash ultimately on me。 So how can I avoid this。 Well， if I go back into Vs code。

 I could just allocate space myself and say equals malloc of4。

 but there's still gonna be a danger there。 even if at the bottom。

 I do free S because I only have allocated space for4 Bs。 if the user types in 5 or 50 or 500。

 who knows what's gonna happen， I'm going overflow my buffer of size 4。



![](img/8c4f64e556c9e456e704dee6118981ae_95.png)

I could do this another way。 I don't have to use malloc。 I can use week2 stuff。 I can again。

 as before， just say S maybe not 1000 but 4。 that gives me an array。

 which is a chunk of memory of size 4。 But what happens if I overflow that buffer。

 like bad things will happen。 And so this is why we still use and would encourage you to keep using get string because it avoids overstepping the boundaries of any buffer。

 Like we literally， as I acted out before， take these baby steps in code。

 And every time you type a character， essentially， we call malloc again and again and again。

 and it's a little inefficient， but we call malloc is many times as we need to grow enough space in the heap for whatever the human types in。

 whether it's one character  for，4000 or more。 It's just really annoying to write out。 And in fact。

 the code is open source。 but it's a decent amount of logic just to do something relatively simple。

 languagens like Java and especially Python make life so much easier with input and output。

 and we'll get to that in a few weeks time。😊，Any questions then on。Scanf。

 and really why we've been using these training wheels， yeah。

I only heard part of that is would it be valid to use malik and just allocate a really big number。

 So that just kind of like kicks the can down the road。 But I bet whatever number you come up with。

 I could。 if I copy paste enough or just type type type a lot。

 I could overflow that buffer still by just typing in longer input and worse。

 you're now wasting memory because you only have a finite amount of memory。

 if one program is using all of this memory just in case some crazy user types in way too much。

 I mean， most of the time you might be slowing down the computer or at least wasting memory as well。

 So Getstr does that too， we only allocate what memory you need， ultimately。

 even though we end up allocating and freeing a lot of memory along the way。Really good question。

Alright， so let's transition then to a final topic that's going set you up really for problem set4 in which case you'll be exploring something specifically known as file I O or file input and output。

 And we've deferred playing with actual files where you can save files and open files until now。

 because you actually do need pointer syntax and C to do that with files in Python world's gonna be easier in a few weeks's time when you don't even need that complexity。

 But for now， we'll explore sort of the idea of file input and output as follows。

 There are a bunch of functions that come with see related to files。

 And here's just in short list thereof， But you can kind of infer from the names what these do in code because there are operations you're familiar with in the real world。

 like opening a file， Aka F open closing a file， A F close printing to a file。

 Aka F print F and a bunch of others as well。 So any function that starts with F probably means that it operates somehow on files。

 whether it's。

![](img/8c4f64e556c9e456e704dee6118981ae_97.png)

![](img/8c4f64e556c9e456e704dee6118981ae_98.png)

Text files or binary files with zeros and ones。 These files。 these functions tend to be involved。

 We'll see with this how we can now like create some of our own files。

 So let me go ahead and do this。 let me go back to B S code And let's make in the spirit of week0 my own actual phone book in C。

 like let's write some code that allows me to save in a file。

 someone's name and number so that it actually persists over time。

 And I'm gonna go ahead and call this phonebook do C。 And in this file。

 I'm going include just to make life easier still for today because we've seen that scanf is not really your friend will use get string again to include C50 do H standard I O do and also string do H。

 which might be useful into main void again and inside of main， Let's do this。

 Let's firstop let's first open a file called phonebook do cv。

 most of you are probably familiar with Cv files。 They're like lightweight Excel they're like spreadsheet files that can be open in Excel。

 Google sheet。😊，Or Apple numbers of the like。 It just means comma separated values or C SV。

 So I can make a very simple file like this myself。 But the syntax is going to be a little new。

 It turns out weirdly And C， there's a data type called file in all capital letters for really no good reason。

 I'm going then declare a pointer called file in all lowercase。 but I could call it anything I want。

 And I'm going to set it equal to the return value of calling F open for file open。

 And I'm going to specify that I want to open a file called phone book do CS SV。😊，In。

 let's say right mode， quote， unquote W。 And I know this from the documentation for the function that W means right。

 And that's why I'm passing it in is the second argument。 Now， let's go ahead and do this。

 I could do string， but we know strings aren't really a thing。

 So char star name equals get string and prompt the human for their name。

Then let's do cha star number and prompt the human for their number。

 And then I want to save the human name and number in this file。

 Like I'm adding friends to my contacts。 Let's go ahead and do， not printf。

 but F print F passing in file as the first argument。

 which is unlike printf printf obviously just goes to the string string by default。

 But F printf needs to know what file you want to print to。

 I want to print out a string that looks like a string comma， another string and then new line。

 So just like printf， lets you format what you're printing F printf lets you format what you're saving as string。

 comma string and then a new line。 The last things I'm gonna to pass in are the values for those placeholders store the name and store the number。

 semicolon。 And then lastly， let's go ahead and close the file。 So it's not that many lines of code。

But this is code enough to like prompt the user for a new name， a new number。 save。

 I could run it again。 new name， new number， save。 And just to make this clear。

 let me go ahead and do this。 Let me open up phone book。Dot C SV， which doesn't yet exist。

 Let me kind of split the screen here， which if you haven't discovered。

 you can do by just dragging the tabs up and around。 so I can see both at once。

 Let me do make phone book， enter， dot slash phone book， enter。

 And I'll do how about John Harvard enter。 And now let's see， plus 1，9，4，9。 what's his number。2。

Line Rnction， do you remember？Has anyone texted this number yet？You have it saved？

This is not important， but I'd like to be consistent。Yeah。😊，Thank you。 And the 2，7，5。

0s spelllls C 50。 So enter。 And now notice what happened to top right in my CV file。

 I added a name to the phone book。 Now， let me run the program again， because there is a bug。

 I'll put in my name now。 and I'll just I'll just do。 Let's see plus 1，6，1，7，4，9，5。

 I think we use 1000 last time enter But notice John Harvard disappeared。

 And that's because I chose to write to this file， But there's another mode in which I can write data。

 I can actually use a for a pen， which is probably smarter。

 Let me run my program a third time and put John Harvard back。 So John Harvard enter plus 1，9，4，9。4。

6，8，2，7，5，0。 Oh， yes， thank you。 Someone caught my mistake before I did。😊，I compile it again。 Okay。

 control C。 make phone book。 enter。 Now， let's rerun dot slash phone book。 All right， here we go。

 John Harvard will put him back plus 1，9，4，94，6，8，2，7，5，0， enter。 Okay， that's in there。

 let's run it one more time for myself。 David Main plus 1 plus 16，1，7，4，9，5，1000 enter。

 And now it's indeed a pending to the file。 So if you've ever used Excel or Apple numbers or Google sheets。

 And you're adding rows to the file， or you're literally clicking like new contact on your Android phone or your iPhone。

 effectively， what's happening is Apple or Google wrote code like this。

 to add add more and more data to some file。 It might not be as simplistic as a CV file where you're separating the values with commas and just putting it in raw text。

 it might be some binary file with raw 0s and ones， but it's the exact same idea。 And in fact。

 if I go ahead and。😊，Try to。Improve this code。 I should note this。

 too in the spirit of error checking。 Let me add one additional line before we add one other example to the mix。

 It turns out that just like malloc， things can go wrong when you try to open files。

 Maybe it doesn't exist， Maybe there is a typo， maybe you are in fact， out of memory。 So here too。

 and for problem set4 onward， you should get into the habit of checking return values。

 Don't just assume that you've got a valid return value。

 check instead per the documentation of this function。 If file equals equals null。

 bad things just happen。 Something went wrong。 And I should probably just get out of here and return one or some other value instead。

 So again， the lesson today is any time pointers are involved for malloc F open and other functions as well。

 do not trust that they are valid until you have checked whether they are null or not。Alright。

 one final flourish here to implement the notion of copying a file as well。

 We we introduced we you might have seen the Cp command before for copy files from one to the other。

 How might we implement that ourselves。 even though it's been around for some decades now。

 Let me go ahead and open another file here called copy do C， or actually we'll call it。

 we did copy earlier。 we Yes， let's go ahead and create a new file called Cp dot C to implement our own version of the copy command in this file。

 let me go ahead and include standard I O dot H。 And let me go ahead and include another file。

 standard int dot H， because it's something you'll see in problem set for。

 And I'm gonna go ahead and in int main。 I'm going to use command line arguments now。

 int A C string Rrg V as an array。 But weop。😊，But we know strings don't exist。 So technically。

 main can henceforth be written as char star Rrg V。 still an array thereof。

 So we're just getting rid of the word string。 And here's how I could open one file and copy it into another。

 recall that copy works like this。 C P source destination。

 So it's the opposite of the stir copy function confusingly。

 But C P copies the source file to the destination So you can change the name or give it any name you want。

 So how might I use this knowledge。 Let me create a pointer called source SRC for short。

 and open a file called well what should the file be called。

 Let's expect the user to pass in in Rrg V1， whatever the file name is per the usage at the command line。

 Then let's open it up in read mode specifically， Then let's go ahead and have a destination pointer called DSST for short。

 that equals the return value of opening the second file that the human type the name of at the prompt and we'll open that in right mode。

I'm gonna to do a pen mode because I want to literally copy everything。

 I want to add to an existing file。 And then what do I want to do。

 I'm gonna propose that we do this byte by byte。 And there's many different ways to do this。

 But among our list of functions from earlier are functions like F read for reading from a file。

 F write for writing to a file， as well as print which prints to a file。

 But if I actually am dealing with binary data， I might actually want to do this。

 I might want to declare a variable of type byte， which by convention。

 especially in the Windows world is capitalized as byte， give me one variable of type byte。

 and let me do this while I read from the file， passing into that byte， a byte from the file。

 So give this function， the address of that byte， so we can go put 8 B in it。

 then let's read in the size of a byte， which I could just write as one。

 but I'm gonna keep it dynamic。 I'm gonna read one such byte at a time。

 And I'm gonna read from the source file。 And I'm gonna keep doing this so long as the return values not 0。

 This is a mouthful。😊，me just stipulate for today's purposes that line 11 just starts a while loop that iterates over the file called source by by by by by by by from left to right。

 top to bottom。 so to speak。 And how do I save each of those bytes to the destination file while I can do F right passing in the address of that by so it can go to the location。

 the size of it。 So it knows how big it is how many there are， which is still one。

 but send it to the destination instead。 And then at the end of this code。

 Let me hide my terminal for a moment。 Let me go ahead and close， for instance， the destination file。

 And let me go ahead and close the source file。 And ultimately， I think this is enough。 So again。

 iterate over all the bys in the file，1 by，1 by，1 by at a time and write them by by by by by。

 and minor tweak technically because I want to do this literally， There's no text involved。

 There's no uncode， I just want this to be a raw copy of by technically。

 I can specify read the file in binary and write the file and binary。 Don't try to do any kind of。😊。

Interpretation of characters treated as raw， zeros and ones。

 And just so you've seen it technically in C， there is no such thing as a data type called Bte。

 This is again a thing in the Windows world， and we will give it to you in problem set 4。

 but I can actually create a type using type def。 I'm going it be equal to something called U 8 U in 8 T。

Where that just means unsigned 8 bit integer。 but more on that some other time or never perhaps。

 But for now， that just gives me a by of 8 B in a manner consistent with what Windows computers do。

 And if I didn't mess this up。 Let me open my terminal window。

 Make C P for make the copy program dot C P。 I want to run dot C P。

 So it's my version of the copy command， not the built in system1。

 let me go ahead and copy a file like what was the file we started with addresses dot C。

 And how about we'll call this how about we call this backup dot C。And if I open up addresses C here。

 we'll see the file with which we began class earlier。 if I open up backup C。

 we'll see exactly the same file。 if I hold them side by side， these happen to be text。

 but they could have just been raw zeros and ones， I've indeed implemented the C command correctly in this way。

 Now how though does this loop work。 let me go back into Cp do C recall that I had this loop here。

 let me close these other files， there was this loop that somehow just new to advance to the next byte in the file。

 even though there's no plus one， there's no four loop explicitly。

 it's just kind of reading and reading and reading until if we return0。 Well。

 the reason for that is that these file reading and writing functions behave a bit like a YouTube video or a Netflix video whereby once you start reading from them like watching them。

 the sort of cursor advances from left to right。 So as soon as you read a byte。

 the file itself keeps track of where you are in the file， kind of like an old school cassette tape。

 once you start playing it physically， the device is moving。 So it knows。

Where to read the next bytes from and where to write the next bytes to。

 And this is all gonna be germane as we introduce ultimately。

 a specific file format this week in problem set4， known as a bitmap file or BM for short。

 in the world of bitmap files， you'll see that you can represent images like this。

 But these images are really just gonna to be a grid of pixels top to bottom left to right。

 And among the goals for this week is to implement some Instagramlike filters via which you can actually manipulate these images。

 So for instance， among the filters you'll implement is first one that converts any image。

 even a photo you yourself took into black and white by throwing away color information somehow and just retaining some form of grayscale。

 you'll implement。 and it's a bit hard to see on the screen， but a CPepia tone。

 sort of an old school photograph photographic style。

 you might be able to inver or flip the image on its access here。

 So I've just reverse the sides of the bridge same photo just flipped around in the computer's memory by moving like these bytes over here and these bytes over here。

 or if you really are feeling more comfortable。😊。

![](img/8c4f64e556c9e456e704dee6118981ae_100.png)

You can do edge detection。 And write， no， I said that wrong。 Or if you're feeling really， No， wait。

 everyone has to do this。Sorry， let' let's stick the landing。 We had like one minute left。

 So if what you'll also be challenged to do is blur the image too。

 whereby you're gonna make it look fuzzier by sort of combining pixel value so that it's not quite as crisp as it originally was。

 And if you're feeling really comfortable， you can even do edge detection。

 whereby you can figure out where the outlines of physical objects are on the screen by writing more sophisticated code optionally to render images such as this here。

 So ultimately， this whole week is going to be about file input and output recovering images that might have been deleted or corrupted as well。

 But we thought we'd end on a final pointer note。 This is another one of these comics that now computer scientists should be able to understand the humor of。

😊，Hopefully。Okay， lots of laughter。 All right， that's it for CSs50。 We will see you next time。😊。



![](img/8c4f64e556c9e456e704dee6118981ae_102.png)