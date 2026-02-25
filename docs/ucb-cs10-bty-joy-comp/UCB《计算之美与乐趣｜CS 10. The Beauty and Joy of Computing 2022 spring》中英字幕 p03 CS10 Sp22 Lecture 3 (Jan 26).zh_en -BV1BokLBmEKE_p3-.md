# UCB《计算之美与乐趣｜CS 10. The Beauty and Joy of Computing 2022 spring》中英字幕 p03 CS10 Sp22 Lecture 3 (Jan 26).zh_en -BV1BokLBmEKE_p3-

He everyone， welcome。Started in just a moment。 I believe these slides are now linked on the website。

 I'll drop them。In chat as well。But they should be for right now they're on the top of the website。

 they'll make it into the calendar linked normally sort of later today。

Slides are not actually showing up yet。That is weird。Oh， that's my be。All right。Now。啊。Yeah。Al readyy。

No。All right。Lecture slides or that's Identt mode， I hope doesn't matter， but we can grab。

I can grab our presentation mode slides。😔，There we go。And share you。From。All right， cool。

 so let's get started with everything for today。

![](img/05684e20f1b11779a69c1452d754564e_1.png)

Again， sort of like normal if。You have a question please feel free to drop it in the chat or raise your hand and I will yeah sort of do that and if there's anything urgent or you would like to unmute yourself to ask a question feel free to do so so main thing to know announcement wise so。

We starting to get the into rhythm of how things are going， but next week。

 campus said we will be all in person。So what that means is if we can set up the live Zoom link for lecture。

 it might happen to be sort of sulcasted on Zoom， but please don't rely on attending lecture via Zoom next week。

The way that this will at least work is that。Because we have the classroom set up to do automatic recording。

So there will be recordings of all lectures。Those will continue to be posted later in the day or early next day for the lecture recordings。

Labs， it should say lectures labs and discussions will be in person。

 although discussions don't happen at the end of the week， but yeah next week。

We will hopefully be seeing each other in person。Lectures are hearrsstfield annex it's sort of on the south Eastish side of campus labs are all in 200 Sa Taja die Hall which is on the northeast corner it's a really nice lab it is one of the few computer science labs thank you for the note about transcripts。

It is Taarge eyehu is one of the few computer science classrooms that has natural light。Which is a。嗯。

Yeah， it's just a nice lab to to spend some time in so you can。😊，呃。

You can go there hopefully that lab has key cardt access so hopefully everyone has automatically been added to the key cardt access list for lab。

 but if you need some access just knock on the door and someone should let you in。

And this week we'll be doing lab a reading quizzes in the second lab of the week， so if。

Normally they'll be in the first lab， but for this week getting started， it'll be second lab。

 one reading this week a video， a short question， reading quizzes really should be designed to take you you no more than 10 minutes。

They are。嗯。Yeah， just your ID reading quizz excuse for lab access。And yeah。

 they should ideally take you no more than 10 minutes or so。

 but you know they'll be open for a little while， but the idea is just that they they're a quick check。

 they're mostly to reward you for points for doing the readings。

Stuff like that can you do them asynchronously yes please post a private note on Ed and we will get a list of asynchronous re quizzes set up right now we're going to make time for doing them in lab but if you can't make a lab time we're making arrangements for those cases in two weeks we'll have our quest the quest is sort of like a mini midterm again somewhere between a quiz and a test。

It'll be 7 pm on Tuesday， the date that's on the calendar I didn't want to write a different date when I was just joting the slides down。

 but the date on the calendar is correct it'll be 7 p。

m we will have room and location details in a week or so。

once campuses all confirm that and there will be a way to take the quest online using remote proctoring so that will be an option as well the the quest is。

Closed。嗯。You sort of closed book， but you have access to handwritten cheat sheets and later this week or early actually early next week after we meet with our staff meeting we'll give you sort of the details on all of that。

 but you really shouldn't have to worry about you know cheat sheets too much for。

For the question and things like that it's probably going to be like somewhere between 10 and 15 questions it will only take an hour and we have a bank of past exams on the website self checks are linked so。

With that today we're going to focus on number representation and why numbers are a useful abstraction and talking about how they are an abstraction。

 but before we get to that I wanted to spend a few minutes on the last topic from Monday's lecture。

Which actually leads into this idea of numbers data types。诶。

No updates on on the wait list yet I mean wait list don't close until the end of week four。

 so there's still a lot of opportunity for for people to move around。Um。Yeah。

So domains ranges and data types so oops in。In SNAP。

 we've been talking about and using the blocks that SNAP provides us。And a really important concept。

That you'll be using and that we'll be talking about is the domain and range so in math class again we're going to talk and rely on some terms for math class but the point is not to think about things in a purely mathematical context but essentially what we're talking about are the inputs and outputs of our functions or blocks and again here if we say function we're talking broadly if we say pure function we mean just a peer function but we can think of a domain and range as not just what are the you know what is the particular input to this block but what is the acceptable set of inputs so in a square root block。

We can generally say， for example， that the input that it accepts are non negative numbers。啊。In math。

 you'll learn that you can of course do the square root of negative one， you get imaginary numbers。

 yada， yada ya。In the case of what we're programming， what you're doing most of the time none。

If the square root should be non negative numbers， you know。

 this is one of those cases where the exact input。Whether it's not negative or just numbers it's clearly numbers at least right you can't ask for the square root of the text hellello CS 10 that would be a little bit weird but what you can do is ask for。

The length of something like the text Hello CS10， which would just return the number of letters in the text Hello CS10。

We have a lot of blocks like greater than less than equal to these blocks can take in text they can take in numbers and they return whether or not one thing comes before another thing how this works with text we're not going to get into but it's pretty standard there's some cool things that you can do with text and actually a little bit of how we talk about how numbers are represented we'll get into that。

And we have these Boolean predicate blocks and an or。

And one of the nice things about S that is helpful is。

Any any block that is hexagonal shaped is meant to deal with boolean values so the and block accepts two type two inputs both of those should be values that are true or false S will be pretty forgiving if you put the value let's say hello and goodbye into this block S won't give you an error but the results might not necessarily be what you would expect so each block has a range of data that that it likes to accept that's called the domain。

And of course， each of these corresponding outputs have a set of logical outputs that make sense。

The square root block， of course， gives us back a number。

The length of block gives us back a number and in particular we can say the length is a non negative number right I cannot。

Give you a set of text which has a length of negative five there's just no way to input sort of less than nothing for example you can't have a length of less than nothing if we sort of think about you know anything physical right it could either be zero or something so we could we could further specify non negative number but if you just said。

If you just said integers or numbers that would be acceptable for for the range now these additional two blocks are hexagonal shaped and what's really nice about snap is the shape and to an extent to the color。

Of a block， communicate the purpose and point of a block so whoops these hexagonal blocks。

Always return boolean values true or false， so is one greater than two？

Is the text hello less than a fan the text goodbye？Maybe that one won't make sense right now。

 but those things we can always say the only acceptable results of that calculation are true and false。

When it comes to the and and the ore block。FewTrue and false or true and true。

 these blocks will tell us if both things are true， if one thing is true。

 if they're both false and so on， or if only one of them is false。

So and and or will always only return bullyan values true and false how and and or work willll get into later and there'll definitely be a bunch of exercises in in labs so conceptually what we can say is everything has。

OfSome kind of a type。So we have what we typically might call real numbers。

 so we could say these are numbers， which are any numbers that aren't imaginary numbers。

Pi is a real number， negative five is a real number， one over 100 is a real number。

In snap for the most part we're just going to focus on the idea of numbers。

 but if we can be more specific it is sometimes helpful we have natural numbers also referred to as counting numbers。

 we have letters， which we typically mean a single character at a time。So that's ABC D EF。

 notably this often does include our numbers， so zero can be a letter。In a lot of cases。

 we have words， which are made up， of course， of a series of letters put together。

Whether or not a word or a sequence of letters is a real logical word in your language。

 typically not something our functions care about but。We have we have words。

We have sentences so a bunch of words put together usually by spaces。

 a sentence you can also think of as just a bigger word and of course we have our boolean values and our boolean values are always just the values true or false and they get their entirely own data type because it is useful to think about how to separate those out in a lot of cases from other things so when in lab you work with the if block or the else block or the repeat until block。

Separating out a boolean value will become a useful thing。So。In Sn。诶。Hopefully over time。

The the aspect of data types will become something that is is intuitive you can try and memorize these data types。

But。It's not particularly I wouldn't try and focus on just straight up memorizing them。

 but you might want to take notes to write them down that's cool。

 but over time hopefully the shapes and colors should end up conveying meaning。So。In Sap。

 what we've seen right now is primarily we've worked with things that have letters and numbers。

And each slot and snap usually conveys some kind of meaning。

 so these rounded input slots only accept numbers as their input。

These wider slots typically mean that text should go in there， but when we get to variables。

 you could drop in a variable or the output of another block。

Text can really be just about any kind of input in a lot of cases。

Next week we're going to get to lists， so lists are a special data type that we haven't talked about yet。

 but it's these sort of three little rectangles stacked together to convey that a list is multiple pieces of data in one thing。

And of course SNap has an input slot which sort of means any valid type。

 so anything could be in theory less than any other thing。

 but logically that means numbers and letter so just because something says or snap a let a block whoops except any input type doesn't always mean that it is logically any any input type and yeah zero can be treated as a letter or a number depending on the context so。

That。That really just depends on how you're using the data。

And we'll get to an example of that in a bit。So。One thing to note， when we build our own blocks。

We we get to choose when when we have inputs what they look like and so in。

It should still be the first lab next week。But the actually that might have been now。

Now the ordering got off， so let's see maybe remember anyway， this is what lab number is this。呃。

Work with report Okay yeah so so yeah this will be next week's lab there there should be additional references and on the labs website but。

啊。In S you have a lot of options for building your own blocks and specifying the input type。

 so in lab you'll learn how to communicate within a block。

That this cube function from from Monday's lecture that it should be a number and if you don't do this。

 your functions will work perfectly correctly， but if you do say that cube only accepts numbers that conveys to someone。

Reading this block and using it perhaps that that that cube function makes numbers and when I say it conveys to someone。

 the most important someone， perhaps that you can make your code readable to is your future self there are many things that you' will do in the moment。

That seem intuitive or obvious that in one hour or six hours or in two weeks。

 you'll look back and be like， what was I thinking during that time period？And so。

That's a little bit on the types of data。In SNAP we sort of briefly introduce these。

 but it's worth mentioning that predicates are a special kind of block and we're going to go through through predicates pretty quickly predicates are reporter blocks that specifically return a boolean value and again this is a case where S will let you do things which are sort of against the rules。

But anytime you see this hexagonal shape， you should immediately think this thing returns one of two values。

 a true value or a false value。And that's the point of of what a predicate block does in the second lab so starting later today or excuse starting tomorrow for this week next week we'll have Wednesday labs we're going to get into using conditional statements so a conditional statement will。

Let us say if some piece of code is true。Then execute the thing inside that block。

 so we'll see how to sort of nest blocks with inside one another。And if something is false。

 then then nothing happens in the case of the basic if block so conditionals are blocks。

 they also we could say are you know they're a special type of block that accepts this predicate as an input there is or there are blocks and snap that are multiple types of conditionals so a wrong hung keyboard key so we did this on on Monday's quiz。

嗯。Which of these is not a function， hopefully everyone had a chance to answer the first question after Monday。

In which of these is not a pure function。哎。And the answer to this one was a pick random is not a pure function。

 because if I say pick random one to 10， I can ask that function。

A bunch of different times and then we'll get a bunch of different results。

 so things that involve inherent randomness are not are not a pure function because for the same inputs。

 they can return different kinds of outputs。Again， in SnAP we have three kinds of blocks， commands。

 which we sequence together in a set of steps。Do this do this do that we have reporter blocks which return a an output to。

Just really to anywhere else in your program whatever was asking for that that output and we have predicate blocks which are a special kind of reporter block that specifically return true or false so you'll get to use all of those in lab this week。

So。😊，Again， don't focus too much on terms， but if we say procedure， that's just a sequence of steps。

If we say function， we are typically talking this should say a peer function。

 but we're typically talking about something that has inputs returns and output and if given the same inputs it'll return the same output again so I'm going to leave it through that I'm going to talk specifically。

About numbers today。And fair warning， some of the steps here are a little bit dense in terms of thinking about how numbers can be represented。

But。What's going on today is really useful to understand and to sort of drive home the fact that。

When we have data， data can be represented in many forms and what the meaning of that data is is really dependent upon a program that is interpreting that data or put another way。

 the user who is using that data。If I tell you the number 10。Without any context。

 the sequence of digits 10。We call that the number 10 in English we know that it is one more than9 one less than 11 but we don't know 10 of what and in particular we assume that that is the number between9 and 11 that is perhaps not always the case for the sequence of digits one and zero so today we're going to talk about how we represent numbers and why we have。

Multiple。Multiple different types of number representation。

Something that I think we're all familiar with， but perhaps not thought about this way。

Is if we take the example of 7091。How do we know that this thing is 7091？Well。It turns out that。

Probably at some point long ago， you talked about each position in a math class。

 you have the one's position， the tens position， the 100ths position， the thousands position。

 and then you could go to the tens of thousands， the hundreds of thousands， the millions。

 and so on positions of numbers。And the way that we can represent these is if we say I have 7091 in base 10。

The thousandss position is noted by the power， the 10 to the power of three。

The 100s position is notated by 10 to the power of  two， the 10's position 10 to the power of one。

And the ones position 10 to the power of zero since anything to the power of zero is one so what we're really saying is this is the value one times one so one plus the value 9 times 10 so one plus 9091。

Plus zero。Plus thevalue 7 times 1000， so we have 7，000 plus 0 plus 90 plus1， 7，091。

And note how many times in here we re use this idea of base 10。

 so we have a little superscript on this number。To denote specifically， but it's base 10。呃。

And elsewhere in here we refer to base 10， so this is how we represent a number to interpret its entire sequence of value。

It turns out that we're entirely used to using。Base 10 but there are many different number systems that are that could be used it turns out that the decimal number system is super useful it's very natural to use it has a lot of nice properties。

Yet 10 is is a nice number to work with it's easy to count with on your fingers right most of us have 10 fingers that we can use to count。

But it's not the only option， so we're going to talk about three other options and we'll see where they get used so the first thing we'll introduce you would have expected to be binary but it's not the ocal number system it's base eight and I think this is actually a little easier to conceptualize when we see how things work。

So one thing to note the base 10 system has 10 possible digits， zero through nine。

 the base eight system also has eight possible digits now zero through seven so zero is always our first digit in these number systems representing nothing we're going to stick to using our Arabic numerals zero through seven zero through nine zero through one in the case of binary you can guess that if we talk about trinary that might be zero through two。

 but really the fact is these can be any symbols representing that quantity。

 so what's the pattern here。In base eight， we have zero through seven or our first eight digits and up until the value7 our base 10 and our base 8 numbers look pretty similar but how do we represent eight in base in base eight well eight is the quantity zero so zero times one plus the quantity one times eight or one times eight to the power of one？

In base eight， we note， we have no eight numeral or no numeral nine because we don't we only have eight options for。

For how we represent something。Let's say we have the number 15 in base eight。

How do we understand what value this would be in base 10 as we're going through this if you're feeling good I highly encourage you to sort of do the mental math to think you know ahead we're not going to expect you to to do the mental math like during a lecture on a quiz you'll totally have an opportunity right it out but if you're getting to the point if you're getting the point you know I always encourage you to sort of just try and think a couple steps ahead so how do we conceptualize the the number 15 you can always choose yourself because we're adding digits whether you want to go left to right or right to left。

I personally think it's a little bit easier to start off going right to left， so smallest to biggest。

But。You could go largest to smallest so 15 base eight， how do we conceptualize this。

 this is five times eight， so the value five again。Plus one。Times8， so five and8 is 13 in base 10 so。

15 base8 is the same value as 13 base 10 it's worth noting that these are not two different numbers this is the same value written two different ways。

 so 15 base8 is exactly equal to 13 base 10 it is not a different number it's just a different representation on the same number。

So what about this value 7071， base eight， how do we do that？Well， we have eight。Plus seven times8。

 so that's 56。Plus zero times8 squared so。We have 56。

And one would be 57 and seven times8 cube would be  seven times 512。

Which gives us 36417 times 512 not something at that point that you probably want to do in your head if you do this in your head and you got close to 3500 that's pretty awesome。

Numb like this， if we ever give them to on a test， we will give you reasonable examples such that you don't have to know that8 cubed happens to be 512。

You were not supposed to be able to figure this one out that quickly or。Mentally。

 I would say that 7000 base8 is pretty unreasonable knowing that8 cubed is 512 is really。

Only logical if you happen to remember， that was one of the examples from from Monday's lecture was that we we actually cubed to twice and got 512 so that's。

That's something where if I gave you this number， you could write it out。

 but it would probably take a couple minutes。This is。

A question for the lecture self check so i'm not going to have you do it on gradecope right now。

 but take。Let's say。Take about 30 seconds。And don't write your answer yet。Um。

I think this is more fun than a poll personally。Take about 30 seconds and try and figure out what is the value 34 in base8 converted to base 10 and when I say go type A B c D or E in the chat so take about 30 seconds think about the value 34 in base8。

 what is the value of that in。In in base 10。All right， how we do on time。Hit enter right now。

 hit A through E in the chat。Awesome lots of lots of Ds on the exams no calculators but you like it will be set up such that you won't need a calculator I will not whoops do not mean to scroll that fast I will make sure that you don't need。

A calculator or I will not give you a number like 7071 on the exams yeah in this case 28 D is absolutely right。

We have four。So one's position still the same。Plus three times8 three times8 is 24 plus4 we get 28 D is the correct answer so nice。

I personally find this more fun than just popping up a poll in front of everyone。So。😊。

What's pretty cool now we've spent time talking about base eight now we get to talk about binary base two。

😡，And in binary。It is exactly the same as before we're now just replacing where we had a 10 in our math with the or an eight in our math with the value two so this handy table on the right will show us sort of how things compare and again one thing that I encourage you is look for the patterns so。

The values zero and1 are always the same in binary we don't have a value two that would be trinary if we had three values。

 so to represent the value two we have zero times1 plus1 times two to the power of one so plus1 times two。

So that's how we represent two， how do we go from two to three in binary we？Add one。

How do you go from three to four in binary well， we add one and if you were to write out the math。

 we carry the digits over。😡，So we have one00 and you can see they。

If you just sort of imagine this being a table where every time you add one。

And binary you often have to add numbers you add in once you get to a new power of two。

 it'll add in an additional digit。That is how。How we start to conceptualize。

How how to think about number systems so a new form of notation there will be a lot of sort of different kinds of notation。

 but this one is pretty common oftentimes you will see。

The values written out using some kind of written notation there's not one for octal usually。

 but if you see the prefix0 b that means this number or this string of numbers is represented in binary and this is really useful because it turns out。

Subscripts are kind of annoying to type in a lot of places。

 so having a non subscript way of telling you that this is a base two number is useful so。

What is the value 110 in base 10？Well， you could。You could just look at the chart on the right。

 but we have zero times one plus one times two so you've got two plus one times two squared which is four so four plus two plus zero gives us six so if you wanted to look just right on the chart it would be this number six right here。

 but what's really awesome right is the same patterns extend all the way up。To any number。To any。

 we could already think about how this might extend to any base representation。

You could if you want to design your own base1 million system。

 although recognizing that there are a million symbols that you would have to keep track your head to understand what the number means。

Would probably not be very easy to use， but theoretically you can do it。So。Again。

 we can take a value like the number 10 and go backwards to base eight and into binary so。whoops。So。

10 in base 10。Is a representation of the value if we're thinking about base eight？

We could subtract off。Usually when we go from binary where we have more digits。

To a system like base eight to base two。I don't know why the animation didn show up here we'll start with the largest digits so let's figure out how many powers of eight do we need well we need eight to the one right because we have a number bigger bigger than eight so eight to the one is eight if we subtract off eight to the one from two。

Then we are left with two left over， so if we go backwards 10 in base8 is one times8 plus two times one。

Can you convert base 10 to face eight yeah can I write that out yeah so let's see。How why。

Why did this？Not show up。All right， so。10 based 10 is so this is equal to。What。One。All right。

The way that I like to think about this is。10。Divided by eight。Is one。So there we have one。

Times eight。And I see this is a problem with using things that have superscripts so one times eight to the one。

诶。And then we have two。10。Technically， the way to think about this is 10 mod8。

Which would be the remainder。Is gives us two left over and this is。Let's see two。Times 8 to the。Zero。

Which is just two so now we have one， two because those would be in our。

Our I guess we would call this our eighth position。

 this would still be in our in our one's position would be how we how we map those together doing going from decimal whoops。

Going from decimal to base8 and decimal to binary is a little more involved。

 but essentially what we're doing is we're taking a number， we're dividing it down。

We will usually be converting from a binary。Or base8 number or now a base 16 number。呃。呃。To base TA。

So we go from essentially。One way to think about this is to take the number of steps。

And reverse them。So what？What we'll do now is talk about。

 I'll try and clean those up after so that there is。An example there。

I do want to talk about is base 16 because base 16 is。In many ways。A。A much more useful。Base system。

Baase 16 gets used in。A lot of different cases so base 16 now you might have thought。

 as I said 16 well we don't have 16 digits。诶。That that we can use。Which is totally true。

But we do have the alphabet that we're used to writing。

 so our base 16 digits are 0 through nine that's 10 of them and the letters ABC， D。

 E and F are the values 11， 12， 13， 14， 15 and 16 so。Now we have 16 digits， and yes。

 in this case we called the letter F a digit， which represent the values  zero to 15。

So commonly when we write out base 16 numbers， we'll write out Ox is a notation for for base 16 this is something。

That。Predates all of us。But base 16 numbers are a useful useful thing。

 they will show up elsewhere if you continue to take computer science。

 and that's because it turns out that if you've noticed reading a binary number like 12 already has a lot of digits。

Reading a bay 16 number will be much much more compact and for humans16 is probably sort of a reasonable limit of something that can be conveyed and understood without。

without too much complexity， there are systems that go beyond this。

 but people don't really use them to actually communicate anything useful so。Base 16。

 what is the value a5 and base 10？So again， starting small the biggest。

 we have five times 16 to the zero so that's。5 times one is five and we have to figure out now what is the value of a well a is the next thing after nine so a is the value 10 times 16 to the power of one so 10 times 16。

Is 160。Plus five times one would be 165， so a5。Gives us the value 165 I one thing to notice here right is with two digits in base 16 we can represent numbers that were starting to take many more digits in in base 10 so the more sort of。

The more options that you have in your base system。The more compact your numbers will be。

 whether that's good or not really sort of just depends on the context， but a5。

Represents the decimal number。165。All。I am not going to spend time going through all of these today。

Yeah， so would it be 165 in base eight？I don't believe so， but that。嗯。喂。Five。

 six times eight would be 48。And 64， no， so in8 would be a different would be a。呃。A different。

A different number we'll work on。I'll do the conversion at the end of lecture for that。

 but it will be。Yeah， I want to check the math on that before I say something wrong out loud。

Converting to base eight in your head is not。啊。Is not something that is always super useful。嗯。😊。

So one question that we might ask are which are the following orderings of numbers in the right order。

 so if we order things from least to greatest。How。呃。How do we do this？

One thing to note is we have the number 11 in here， so if we just say 11， that's 11 in base 10。

How do we order those and one thing to do is when we look at a problem like this is to standardize。

The the values so C ABC， so that would be 12 and then we convert our last。诶。

Our last number to binary and i'm going to leave this cool so I think a couple of people have got but i'm going to skip ahead such that you can think about that after lecture and the answer will be on the self check so both of these questions today you could put them in the self check and they'll be there for practice after the fact so。

呃。Yeah， with the last few minutes。We have we'll do some more practice on base conversion。Before。

Let's see。嗯。Yeah， I actually want to do things a little bit out of order。

And come back to base conversion a little bit because I think just conceptualizing numbers first will actually be a better way of doing this so。

We've been talking about numbers and how we come on， Google for you and how we represent them。

And what we've seen is that。You know。There's a lot of different ways to represent numbers。

 it could be kind of a pain to translate them and we'll come back to translating in just a couple minutes。

 but we're so used to thinking in B 10 that thinking in other systems can be really challenging。U。

Base two has so many digits， whoops。That it can be impossible to read and get a sense of what that number might be。

So this value in base two， which John I want to bother reading can be written out as 4DA in base 16。

Base 16 to base two is a really cool mapping because。Each。When we convert between powers of two， so8。

 16 and two， we can actually take every four bits of a base two number and map that to one letter of a base 16 number。

 we'll come back to that， but hexadeadeimals useful because when we need to talk about binary numbers。

 it ends up being a more compact representation。Why why do we use binary？Well。

 it turns out that as a system of encoding information。2。

Bineary is nice because you can only communicate one thing at a time。

 you can only ever communicate on。Or off true or false， yes or no， right？

It can be one of those two things， but it's only ever， you know， A or B at the same time。And so。

What's pretty neat is that using a sequence of yes or no options you can invent all kinds of signaling systems。

 so the ancient Greeks had a system of communicating using torches whether they were on or off this wasn't actually a binary encoding right they weren't trying to just communicate a sequence of numbers but the positions of torches could communicate a bunch of different options and you might be able to answer now is if they have let's see one to。

Three， four， five torches， they could communicate up to 32 different possible combinations of things with five torches。

So that is。One kind of interesting thing is you could you could have。Now with just five torches。

 you could have a way of representing up to 32 different things because the largest value here we could think of as two to the power of a five so that's one sort of useful thing now。

One thing that。嗯。You know， one thing that again is useful in this case is in a system like this。

 it's more easy or it's easier to communicate。On。On or off。

It turns out that in electrical systems where your computers are actually connected to a power system。

 have things stored in them on or off is something else that is easy， easy to manage so in computers。

 these are just a couple of terms， I wouldn't recommend memorizing them。

 but they are things that will come up。So a bit is a single binary digit， it is one。

Bit of information is just the value zero or one yes or no， a group of four bits is called a nibble。

 a term that。Almost no one uses， but is occasionally useful for trivia。

 but that is a group of four bits together。And a group of eight bits is called a byte。

 so this is a useful thing， so if you've wondered what a megabyte is。

Mega is the prefix for 10 to the sixth， so a megabyte is roughly 1 million bytes。The exact sort of。

Definitions of 1 million。Versus two to the power of 20。

 if you have seen sort of other computer numbers can get complicated。

 but you can say that a megabyte 10 to the6 is roughly a million bytes。

 a kilobyte if you know the scientific prefix kilo， 10 to the three， so 1000 a kilobyte is 1。

000 bytes or 8，000 bits。So we're going to leave it there well actually i'll do one slide with the last second and then we'll come back to converting on Monday and spend a little bit more time on that。

 but I think what is fun to understand about numbers and the way that we represent them is that。

When they're all just a series of bits， they can represent just about anything we want them to so normally if we have a series of numbers。

Yeah we can just treat them as a number i'm not sure I understand thanks Siri we can treat them as a number that says how much something is worth if you've used Photoshop or any other image editing program or graphics program or you've tinkered around with colors on a website。

You may be familiar with things like RGb which represent。

Each color has a series of three hexadecimal values。And if you're really curious。

 we can translate each letter into a specific numeric code where the value 65 represents capital A and it kind of goes up from there and you could design a system for just about anything so this is not a real system but you could decide right that that something with the value0 is sad something with the value1 is happy and so on basically if we think about emoji。

 there a system which uses many larger numbers to represent pictures that have their own system of representation so what we'll leave you with today and then we'll come back to conversion on Monday is pick a random value in this case for E6F21。



![](img/05684e20f1b11779a69c1452d754564e_3.png)

This same value of bits is the letters capital N， lowercase O， and exclamation mark。

Interpretted as a color。It's a very weird shade of brain。If you convert it to decimal。

It's a fairly large number。And if you interpret it as a decimal valued number。

 so a real number that the computer can store decimal numbers， it is a very tiny number in fact。

 and how that math works we are not at all going to talk about but the point that I leave you with is that if we give you a sequence of data it is up to you to decide or up to the programmer to decide what the meaning of that data is and how to interpret it so that was a lot about numbers will pick it back up on Monday finishing off how to convert numbers in a couple more steps and that is where we'll leave things for today。



![](img/05684e20f1b11779a69c1452d754564e_5.png)

Thank you， thanks。

![](img/05684e20f1b11779a69c1452d754564e_7.png)

But self check questions are linked on the first slide and should now also be linked。On the website。

And then let me make sure。That。嗯。All right， yeah。Thanks everyone， we will see you on Monday。

