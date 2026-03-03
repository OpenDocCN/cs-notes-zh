# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P50：21_字符集编码原理.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/6c88768e0d8e6b6d9d582bbdce12b27a_0.png)

![](img/6c88768e0d8e6b6d9d582bbdce12b27a_1.png)

So now we're going to talk a bit about character sets and we talked about text strings。

 but character sets are important to understand。 I'll admit that I'm old。

And when I started we are the character sets didn't even have lower case， that's how old I am okay。

 so some of you watching may be that old， but I think most of you got into technology sometime after we had uppercase in lowercase。

So the basic why in the old days we had only uppercase on a controlled data。

 CDC 6500 computer had to do with memory space and the memory of the computers back then was very costly and so the fact that we could use six bits per character instead of these8 bits per character。

 which is what ASCI is was a tremendous saving because every single bit of memory had to be hand bait main and so。

But。Upper and lowercase is really much much better for humans。

 keeps us all from shouting all the time， but back then upper uppercase so there is several standards for upper and lower case back then as we were moving from uppercase only to upper lower case。

 there was Eodic， which was the IBM mainframe standard and then ASCI。

 which was the standard for the rest of us and ASCI was a much better standard in the Esodic because it was in everything's in order。

 you can see ABC So if you look at this ASCI chart。

You can see there's a numeric equivalent for every character so we got the characters。

 some of these are nonprinting in this first column nonprinting then we have like exclamation point and some stuff we got so the zero character is encoded inside the computers the number 48 and these are hexadecimal or octal or binary these are the zeros actual zeros and ones inside the computer this is an eight bit format so there's eight zeros and ones and so that's a byte we call that a bytes so if you got megabytes and then you have some more characters and upper lower uppercase。

 some more characters and then lowercase and some more characters and it stops at 127。So for example。

 if you're thinking well why is it that the exponentiation operator raising to a power in Python is star star right well that's because we had that character and it was on keyboards for a very long time and so we tend to use these ASI characters as the only special characters that have great meaning because you know it's just a lot of the programming languages we use are 20 and 30 years old and so they really kind of stuck with this character set for the essential things。

And if you look at like the less than and greater thans and all these character there's there's nothing in here。

 for example， that's greater than or equal， which is， you know if we were doing this in math。

 we would say greater than or equal， but that's why greater than or equal is greater than followed by equal sign because that character greater than or equal character。

 one character is not here and even though now they've got those somewhere we tend not to use them because we're sort of always afraid that we're going to run into a keyboard or character set representation that doesn't have that particular character and like a superscript squared like a little two that's tall。

 I mean it's two that's short I mean two that's small and moved up some character sets have those so you can say you know x squared and it's little two up there。

You know， and and so we don't do that。 So ASI was our， our standard for a long time。

 It's a great standard widely used， and we still use it basically， but。And so in the old days。

Each character is a number stored in 8 bits of memory Actually you can go up to 256 and we'll talk about that in 85s bits of memory we call it a byte and there's a function in in Postgres in many other languages that can map between a character and it's a according number so we've got you know what is the asking number for H capital H it's 72。

 what's the asking number for lowercase E， it's a 101 L is a 108 and and then what is the character that's associated with 72 L that's H and what's the character associated with 42。

It's an asterisk。 So that's a good quiz question right there。

 What is the character associated with 42。Asster because 42 is very important。

 And so you can predict these numbers if you have a nice ASI chart by。

Doing to find lowercase uppercase H is like right here， and then there's the 72。

 so you go from you know H to 72， you go from lowercase E。E to10 E to 101 and L。

And then if you're gonna go what's the 72 well you go down to 72 and you look over what's 42。

 let's go find 42 here's 42 like what character is associated with 42 and that's an asterisk and so you can just figure that out like one of the things we generally assume when ASI is that like a is less than B numerically and that what we use for sorting and things like that you'll also notice that uppercase is lower leig you know from a sorting perspective than upper lowercase and we do in old days we would even like subtract the current letter I'm looking at minus lower uppercase A to get its position within the alphabet so you'd subtract like 68 minus 65 and you get three to get to the D well plus one and then you get the fourth character in the alphabet So we used to do with these functions we have done you know character I mean mathematics with characters but that's not all that common these days you probably better off doing it。

Greater than unless that。Now。I mentioned that inside of 8 bits we can store up to characters 0 through 255 and so what happened is we started with under 127 for most of those printing characters and nonprinting characters。

 but then they started adding things to beyond 127 and so we have like Latin 1 which is very US and Europeancented which it has various like Umlauds and swas and various things like that and they added them and they picked numbers and then Windows came out and they have this character set calls Windows 2 1252 and then they had variations of these things sort of started getting to the point where that all the ASI would be the same。

 but then the second half would be different and it would be important for you to know the code set。

It's like， so okay， this is Cyyrilllic， this is Spanish， this is whatever。

 And so and so these became important in the problem。

The problem happened is you would get a file and there was nothing in the file that would tell you which character set it was。

 and so if you misinterpreted it， you would just get messed up characters。

And so there was all these overlapping character sets because of this 128 extra 120 characters which was completely different and because they were not self-documenting。

 know you'd send a file from Spain to the US and you didn't get it right or whatever。

 so they would create standards for what the second half of those numbers were up to 256 and they thought that was good enough and the answer is no that's not good enough and it's a mess。

So again， as the world moved towards more and more computers are not just Europe and America。

 we had to solve this problem。And so I'll be honest。I， if you ask me back in the 80s or '90s。

 probably probably late '80s。You know how to solve this。

 I would not have come up with this Uniicode idea。 I think it's darn， clever， very clever。

And so the idea is is that instead of like code sets where you got like， here's a file it's Cyyrelic。

 here's a file and it's Turkish and here's a file and it's Latin  one。

 and you got to just tell people what it is and then you have to tell your software which and you have to install all these character sets on your computer and then you got to know them and you got to code switch between them as you're looking at files。

Make one big character set，32 bit numbers are 2 billion。

They actually limited it to 21 Bs to allow a nice compatibility with another character set called UTF 16。

 And so there are character sets and then characters within those character sets。

 But now what we've done is created one big character sets。 So if you want like Chinese。

 there's several different Chinese traditional Chinese simplified。

 there each a character set and then they get their own set of numbers and they kind when a new character sets shows up。

 And a lot of these character sets are both modern character sets and even historical character sets。

 There's enough space in UniIcode to have historical character sets。

 And so what happens is if you look at this and say， okay， What is 72。 Well， that's an H。 What's 231。

 So this CHR is actually looking up the Unicode。 And so there I think that's a sia there。

 And then what's 2013， well， that's the character for China And there's a much larger range and every character has。

Its own specific。 So the 220013 that's in a range of characters that is like the China characters。

 And so if you look near there， there'll be other Chinese characters。

 And so there's here's your slot， here's your slot， Here's your slot。 Oh。

 you got a new character set。 we'll get you another one at the end and so there's 150 character set and 137000 characters。

 but this whole unicode is something that evolves over time。

 So that's why there's a version to UniIode right 12。1 it changes pretty rapidly。

 but then they don't break the old ones。 And so they just find a place to put every character。

And again。It's awesome。 It's just awesome。Except。Here here's the Uni code code charts so you can see go look around。

 it's just just impressive， it's just really impressive how they have mapped all these diverse things into one character set。

But here's the problem。 We can't afford to make every character on disk on a network connection in a database be 32 Bs long thats way that would basically quadruple instantly the amount of space that we do for text and a lot of what we put in these things is text we put in numbers which are automatically very short Tex is by far the greatest thing we put in databases or send across the internet。

And so we needed a compression scheme， and you can go to that Wikipedia page UTF8 and you can watch。

The research I think it's kind of fascinating how they came up with ideas and so there's like so the idea is is that you go in 0 through 127 you leave that Bi ASCI and you make it so that that's one byte so the most common format is ASCI and then you got these code pages that go to the 256。

And then they have extensions， so the idea is is every character is from somewhere between one and four bytes。

And， and and。I'm not an expert at this， but basically what they did was they could have used 32 bits right。

 but they actually created signal characters， these 111。

 they reserved some of the bits as signals in a way to make it So they could say you know what this second character the second character looks a certain way。

 And so we can kind of assume that the only thing if it's UTF 8。

 It's one in0 in the first character first two Bs and then everything else has got to be something else and what that allowed them to do was it allowed them to have a reasonable conversion or not perfect but reasonable detection of like Latin。

 the old Latin1 Cyyrilllic and those other ones。 So you could look at a file and say。

 you know what I don't think this is UniIode。 Now didn't tell you what it was but you could say it's probably not Uniicode mostly because of these second byte these prefixes were not every single prefix。

So basically you can ask how long so there's a concept of characters。Octs。

 which that's the fancy way saying bytes and then bit length。Okay。

 and so we can look at this little tiny four character Chinese。

 I think this stands for learning management， it's four characters because that's four Chinese characters and in Uniode a Chinese character takes the same width。

Is from a character perspective now。Oct link， this is how it's actually stored in the database。

 so that actually is a 12 bytes。to store for characters so these must be around three byte characters。

 these particular ones that I chose are three byte characters。

 so there are four characters that turn into 12 bytes and bit length is basically going to be always this number times 8 so it's 96 bits and then ASki tells us what the actual Unicode number is because。

This just tells you that's that's only for a single character。

 What's the Unicode number for that particular character。 Okay。

 so that that's the difference between asking， but care length， bit length and oct length。

 And this could be a column， et cetera， et cetera， et cetera。

 So it's any string that's sort of once it's kind of inside Postgress。

 it's going to be thought of it's going to be UTFA。 And so so you can see that。

This would be four times square the 16， if it were like using all 32 bits。

 so we're even saving on character sets like Chinese。So again， they're using some of these patterns。

 so they look at these patterns and if they don't see these patterns in these later bytes。

 they're like。I don't think this is Unicode and so they use this as a signal so that they say， look。

 you're， I mean， this not UTF 8， and so they can at least detect by looking kind of algorithmically。

 you can say， hey， can you tell me if this file is UTF 8 or not。

 and so because they made the UTF 8 format more strict than you can put anything in these four bytes。

Then they actually can detect like invalid Unicode。 and sometimes you'll get it， right。

 sometimes you'll be reading a file and downloading something off the internet that claims to be UTF 8 and your software will say no。

 it's not UTF8 because it violated one of these rules。Now。

The key to UTF 8 was it started in the early 2000s like any technology that in effect wants to replace a previous technology transition is a really important thing。

 And so the nice thing about UTF8 is ASI is the same as UTF 8 up to 127 ASI is the same as UTF8 and so an ASI file is UTF8 file So a lot of things I did because I'm from the United States。

 I'm like， yeah， it's UTF 8。 I was only using those characters anyways right and so it made it really easy。

To do it now in databases and on file systems， you actually had to explicitly sometimes convert back in the old days。

 but now we don't， we just make UTF thing eight things in the database and files and send them across the network。

And so by 2004， it was 60% of the web pages were already UTF8 and then you look at the ASCI there that's by 2012。

 the ASCI is like about 15% so frankly ASI and UTFA are the same ASCI is a perfect subset of UTF8 so you can see that there's not much there's Western Europe character sets that be kind of those Cyrellic ones and there was some Japanese character sets and like everything else so you see them even in 2012 and so at this point 94% of the pages in the world are just plain old UTF8 and that's really cool and so it took you know 20 years but these days we just assume UTF8。

嗯。If you look in Postgres， you will see that you can have a database with lots of different character sets。

 Now these， you should think of these as legacy。You should not say oh。

 I'm in Japan so I'm going to use Japanese， you might find yourself in a legacy situation。

 you do not want to do this for new stuff okay these are the old kind of formats and you want to come up with a scheme that transulates these perhaps into UTF8 so basically and if you look at other databases like myQL it has like a jillion UTF8s in it。



![](img/6c88768e0d8e6b6d9d582bbdce12b27a_3.png)

What you really want is just to be UTF8 and then convert your data on the way in if you're kind of stuck with some legacy data to get your legacy data converted into UTF 8 and as of 2019 and later you just use UTF8 going forward。

So now I want to just do a quick review of how we deal with these character sets in Python。

 and it has to do with external data being used internally in Python。



![](img/6c88768e0d8e6b6d9d582bbdce12b27a_5.png)