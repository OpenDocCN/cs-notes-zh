# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p03 CS50 Business - Lecture 2 - Designing Data Structures .cut.zh_en -BV1ArsFzQECJ_p3-

Hello world。 My name is David Main， and today we'll be designing data structures。

 Last time recall we focused entirely on algorithms and we did this for searching。

 for sorting and really problem solving more generally。

 but we sort took for granted that the computer could store all of the things we were searching for or sorting somewhere in memory Now let's focus today though on how we can actually store those things in memory and maybe if we're just a little bit clever we can actually facilitate more efficient algorithms by storing data in interesting ways underneath the hood of our computer Indeed underneath that hood is memory RA random access memory that might look a little something like this might be look smaller。

 might look bigger depending on the device but this is the type of memory that programs are loaded into when you double click on them or tap on them once。

 It's where files are stored temporarily while you're working on them or editing them。

 It's ultimately where your computer is storing information so that it can be fed into the computer's brain。

 the so-called CPU or central processing。UnitSo Ram is used constantly within your device。

 But how you store data is sort of less obvious。 So let's actually zoom in。

 so to speak on this memory and see what might be inside。 So for instance。

 any one of these black chips might contain some number of bytes or even megabytes or nowadays。

 even gigabytes。 So in fact， let's go ahead and zoom in on this。

 And you'll see that it's just sort of a rectangular black chip inside of which somehow or other are stored lots and lots of bytes and in turn。

 therefore， lots and lots of bits， zeros and ones。 Well， if there's lots and lots of bytes。

 and indeed lots and lots of bits。 it stands to reason that we could start to number them and say maybe this is the first byte。

 this is the second byte， this is the third byte and dot dot dot。

 maybe this is like the1 billionth byte not to scale。

 that is to say we can assign numbers or let's say addresses to each of these bytes just so that we can refer to them later。

 And what's interesting about your computer's memory even though it's not really laid out in rows and columns like this。

 This is just。Artist rendition， if you will， of what's inside of that black chip。

 It turns out that you can kind of think of all of those locations inside of your computer's memory akin to like real worldor postal addresses。

 For instance， at 45 Quincy Street is Memorial Hall inside of which is Sanders Theater at Harvard University。

 which is just one of the many buildings on campus。 But that address 45 Quincy Street。

 uniquely identifies the building so that if you wanted to send a letter to that from anywhere in the world。

 you could write that on the outside of an envelope and somehow or other。

 it would reach that building。 Similarlyly， and frankly， more simply。

 if you were to write the number one on the equivalent of that envelope and send it to your computer。

 it might end up at this location one in memory or this location 1 billion in memory。

 So long story short， if we've got a whole bunch of bys in memory， each of which represents 8 Bs。

 we could certainly just arbitrarily， but consistently number them。

 so that each of those bites has an address According， what we essentially have at our disposal here。

 if you will，Sort of a canvas， a digital canvas that we can use to store anything and everything that we might want to do compute on inside of our computer。

 Now， what might that mean， Well， let's go ahead and suppose that we want to store just 8 B or 1 B。

 Well， we could put that data here。 Now， if we want to store bigger values recall and count higher than。

 say 255， which we claimed in the very first lecture was as high as you could count with 8 B if you start counting it 0。

 because there's 256 total possible permutations of those 8 B。 Well。

 if you want to count higher than that， you might need4 bys， or maybe even 8 B to count really。

 really large。 So in other words， we don't have to use these as individual bytes。

 We could use them as clusters of bys so as to use 8，1624，3248 I didn't mean to say that dim。

Let me fix that。嗯。How best to do this？So let's go ahead。

 I'm trying to remember how I got to the screen。Can you help me？Hello， world。 My name is David Main。

 and today is gonna be all about designing data structures。 Now。

 recall that last time we focused entirely on algorithms， searching for things， sorting for thing。

 Da。 Sorry， let's just do that once more。😊，I promise I will not get stuck in this rut。Okay。Hello。

 world。 My name is David Main。 And today is entirely about designing data structures。 Now。

 last time recall， we focused entirely on algorithms， searching for things。

 sorting things and generally solving problems。 But we sort of took for granted that we could store all of those things somehow in the computer's memory。

 but we didn't really consider how we might do that。 In fact， today。

 what we're going to do is exactly that， take a look underneath the hood， so to speak of a computer。

 consider how it actually stores data and how you and I can more cleverly store data of interest to us so as to facilitate those algorithms performing even better than they might。

 if we used a more simple layout inside。 Now， let me propose that inside of your computer or really your electronic device of most any sort。

 is a chip that looks like this。 This is a stick of memory or Ram random excess memory。

 and this might store millions of bytes， even billions of bytes。

 megabytes or gigabytes respectively today。 In fact。

 if we focus on just one of these black chips here， you could imagine。😊，Let's say zooming in on this。

 And let's take a look virtually inside。 In fact， inside of this chip is all of these bites。

 And in fact， if there's a whole bunch of bys stands to reason that we could sort of arbitrarily number them。

 maybe this here at top left is the first byte。 This is the second bite， the third byte。

 And if it's gigab of memory， this might be the billionth B， give or take not drawn to scale。

 In other words， you can think of the bys that can be stored inside of your computer's memory。

 akin to postal addresses， if you will， simpler versions thereof。 For instance。

 we might visit 45 Quincy Street， Cambridge， Massachusetts 0，2，1，3，8 USA。

 and that would lead us very specifically to memorial Hall。

 the building in which Sanders Theater at Harvard University lives。 Now。

 if we were to send an envelope somehow or other， it would get to that very unique and specific address。

 And similarly， digitally， if we wanted to store a bite at a very specific location in memory。

 we could send it to by1 or two or。😊。

![](img/662bcf12ea2e68802be56a49693956ea_1.png)

1 billion and to be fair， computers typically start counting at0 as we've seen。

 So it might really be byte 0 and one and2。 but we don't have to use just individual bytes because recall that one byte is 8 Bs。

 And the highest you can count with 8 B was 255， assuming positive numbers in0 alone。

 And that's because with 8 B， you can represent 256 total possibilities。

 but if you start counting at 0， you can only go as high as 255。

 So we might want to use more than one by。 for instance。

 we might want to use four bytes or even 8 bys to count even higher just store bigger amounts of data。

 And that's what's nice about this model for memory。

 We can sort of treat this grid of memory is a canvas， if you will。

 kind of sort of similar in spirit So what an image is with rows and columns of pixels。

 And that's not with this technically is because indeed， inside of this chip。

 there's no notion of rows and columns。 This is just an artist rendition of。Of the bytes therein。

 But it is nice in the sense that it's this canvas that we can use to just paint a picture of all of the data that we want to store inside of that computer。

 But at the end of the day， all we're doing is putting specific bytes at specific addresses。

 And so with that very simple paradigm in mind， we can begin to stitch together。

 if you will the most interesting of data structures。

 That is to say a data structure is a way of structuring your data inside of the computer's memory。

 Now， let's go ahead and abstract away the physical hardware。

 focus just on this virtual artist rendition thereof。 And in。

 let's zoom in because we're not gonna to need today all of those bytes therein。

 And let's consider much more simply。 if this is some of our computers memory。 And maybe this again。

 is by0，1，2 or something like that。 let's consider how we might start storing some data there in。

 What kind of data， Well， it could be numbers， It could be letters， It could be words。

 it could be phone numbers， It could be any sort of data we want。 But we'll keep it simple。

 as we've done in the past initially。😊。

![](img/662bcf12ea2e68802be56a49693956ea_3.png)

By storing， for instance， just numbers。 Well， how might we go about storing numbers。

 Well I dare say the simplest way is to use what's called an array。

 the simplest of our data structures， if you will today。

 in array is a block of back to back memory in which you can store your data Now。

 what do I mean by that。 Well here is a grid of just three bys of memory， if you will。

 because my intent with this story is to store three values， at least initially， So for instance。

 if I want to store， let's say for the sake of discussion， the numbers 1，2 and3。

 I can use three of those bytes inside of the computer's memory using what we're gonna call an array to store them back to back to back。

 That is to say this is in contrast to putting like the one over here， the two over there。

 the three over there。 What's nice about an array is by design。

 The values are stored back to back to back。 so that you know that the second value is one by away from the first。

 And you know that the third value is two bys away from the first though。

We don't have to limit ourselves to individual bytes。

 These could be increments of 4 or 8 or even larger than that。 But for now。

 we just have what we'll call an array of three values。 Now， suppose that for whatever purpose。

 we want to store a fourth value inside of the computer's memory。

 Maybe these numbers are not quite as trivial as 1，2，3。

 Maybe each of these represents a phone number or a name or some other value that you want to store inside of the computer's memory and it stands a reason that eventually you might want to add a fourth one。

 Now， it's pretty obvious that according to this story， if we're using an array。

 that fourth value should go right there。 But the catch is that I think we've oversimplified the picture right now。

 because a moment ago， recall that these value certainly lived in the context of lots and lots of other bytes in the computer's memory。

 indeed millions of them， billions of them。 So I think we might need to take a step back and consider that these three values do not live in a vacuum inside of the computer。

 There might be data all around them。

![](img/662bcf12ea2e68802be56a49693956ea_5.png)

![](img/662bcf12ea2e68802be56a49693956ea_6.png)

![](img/662bcf12ea2e68802be56a49693956ea_7.png)

![](img/662bcf12ea2e68802be56a49693956ea_8.png)

And in fact， even though we might want to instinctively put the number four there might not be possible because computers are of course。

 doing many things at once nowadays on your phone， on your laptop， on your desktop。

 you're probably running at any given time， multiple programs， maybe ones in the foreground。

 the others are in the background， but you're still running multiple programs and within a given program。

 You're probably storing multiple values， not just a single number， but two or three。

 you might have strings of text。 For instance， we began today with a hello world exclamation and here in fact。

 might be inside of a computer program。 the words hello world。

 because maybe someone type that into the keyboard。

 maybe that's the script for today's lecture stands for reason that inside of the computer's memory at any given time。

 there might be numbers and letters and colors and videos and any number of other things and we don't necessarily know that there's going to be there available space where we want to put that fourth value because after。



![](img/662bcf12ea2e68802be56a49693956ea_10.png)

If previous。L in the story。 I simply asked the computer for space for three numbers。

 It gave me space  for1，2，3 numbers。 And if in this same story。

 I asked the computer in whatever program I'm running for room for a sequence of characters that is text。

 Well， it knew I had already been given1，2，3 values here。

 Why not put H E L O comma world right after that， that seems to be a very clean design。

 Unfortunately， it didn't anticipate my necessarily needing a fourth value。 I mean， heck。

 I should have just asked for four values if I wanted four values， Now。

 I've sort of painted myself into the proverbial corner here。 Now， if the computer had been smart。

 so to speak， maybe it would have left room for a fourth value。 But what if I wanted five values。

 it might not have anticipated that， What if I wanted six values 7， So at some point。

 the computers probably going to do the simplest thing。

 which is just plop the next values right where there space available。

 So certainly reasonable that this scenario might happen。 Now。

 why is Oscar the gruch all over the screen？ Well， for today。



![](img/662bcf12ea2e68802be56a49693956ea_12.png)

Purpos， we're going to stipulate that any time I don't know or care what the value is in a location in memory。

 we're just going to represent it as a socalled garbage value。

 Maybe it's remnants of the program having used that memory before or the memory now having been clear or reset to all zeros or something like that。

 So for this story， I don't really care what those values are where Oscar is depicted。

 I just know that they're socalled garbage values。 but I'm proposing that the one in the story。

 the program does care about the numbers1，23 and the phrase hello world。

 because those are clearly visible in memory long story short。

 where can I go and put this fourth value。 Well， the value of these Oscar the gruches or garbage values is that technically I can use any of them because if they're just garbage。

 I can repurpose the zeros and ones that are there change the patterns that they're representing in store if I want the number one。

 the number two， the number three and best yet the number four。

 So I've clearly got a lot of available spots into which I could put one2。34， but where to do that。

 Well， if here are four arbitrary Oscar the gruches in a row。

 which means it lends themselves to repurposing these four bytes as an array。

 What I could do is copy the one to that first location。 The two to the second。

 the three to the third。 And now I can go ahead and put the fourth value。

 That was the whole point of this story into that fourth location。 Now。

 I don't need this array and duplicate。 So I can technically just throw away。



![](img/662bcf12ea2e68802be56a49693956ea_14.png)

Whats。Now， I don't need that fourth。 Now， let's say I got to fix the color here。

Now I don't need that original array anymore， so I can go ahead and just give that memory back to the operating system。

 so to speak and allow it to be reused eventually for other purposes entirely。😡。



![](img/662bcf12ea2e68802be56a49693956ea_16.png)

So that then is an array， A block of contiguous memory that is values back to back to back。

 But that's a key defining characteristic。 no matter how many values you want to store an array。

 you must keep them together according to that definition， which means if you want to grow the array。

 And there is not space available for that additional value。

 You're going have to relocate the array altogether。 Now。

 I arguably got lucky because there was plenty of garbage values around me so I could repurpose most any of those in order to store the four values。

 but that's not necessarily always going to be the case and problematically too。

 even though I told that story fairly quickly， just copy the one to the one， the one。

 the two to the two to the three to three and then add the four。 Well， that took work。

 It took like three steps plus the fourth step to add the four。

 That was a good amount of work just to add one value。 I had to copy the entire array。

 So could I maybe do better than that。 Well， it turns out you can using this very same canvas of computer memory if。

😊。

![](img/662bcf12ea2e68802be56a49693956ea_18.png)

![](img/662bcf12ea2e68802be56a49693956ea_19.png)

![](img/662bcf12ea2e68802be56a49693956ea_20.png)

Think a little harder about how to treat all of those individual bytes。 And in fact。

 the second data structure we'll talk about now is a so-called linked list。

 which is an alternative to an array。 but as is too commonly the case in computer science and technology more generally。

 There's going be tradeoffs。 We're going have some advantages here。

 but potentially some disadvantages as well。 So let's rewind to that canvas of memory。

 which is just a whole bunch of bytes that we can treat however we want。

 And let me propose again that I'd like to store the value 1 initially。 But for now。

 I'm also going to reveal that indeed， each of these locations in memory have addresses1，2，3，0，1，2。

 however you want to label them 45 Quincy Street in the real world。

 But let me propose using some standard terminology that this value 1 is that location， Oh。

 I don't know。 Ox 1，2，3。 Now， the Ox is a little weird。

 but that just indicates that I'm using what's called hexedadecimal notation， which is basics。



![](img/662bcf12ea2e68802be56a49693956ea_22.png)

Which is different from base 10， Aka decimal and different from base2， Aka binary。

 And it's not necessary， but this is conventional when talking about computers memory。

 it turns out that computer scientists and programmers tend to think about addresses and look at addresses in hexadimmal notation。

 but I still chose a simple value。 This is at location 1，2，3。 This is not the value，1，2，3 per se。

 This is location 1，2，3， at which the number  one currently lives。



![](img/662bcf12ea2e68802be56a49693956ea_24.png)

So suppose I now want to store the number two in this list of numbers。 Well。

 I could just put it here and put the next number there。 but again， per our previous story。

 let's suppose that there's something in the way， the memory immediately to the right of that number one is maybe already in use by something else。

 but that's okay。 because if I don't hold myself to the constraints of an array that values must be back to back to back。

 I could kind of just use this really as a broad canvas and put the number 2 wherever I want。

 For instance， if the first available space in the computer's memory is way over here。

 which is not contiguous with the number one， It's not back to back with it， that's okay。

 because I can just observe that that second value happens to be for the sake of discussion at location Ox 45。

6。 again， I made it up。 So it's an easy to pronounce number but Ox 4，5。

6 might be where the two now lives in memory。😡。

![](img/662bcf12ea2e68802be56a49693956ea_26.png)

![](img/662bcf12ea2e68802be56a49693956ea_27.png)

However， unlike an array， it is not the case that the second value is one by away from the first value。

 In fact， according to this picture， it would seem to be 1，2，3，4，5，6，7，8，9，10 bys away。

 which is kind of arbitrary and not necessarily predictable。

 just so happened that that two we had room for it right there。 In fact， let's continue the tail。

 suppose that the next available spot for the number 3 is over here at location 0 x 7，8，9。 And again。

 the picture is not to scale because there's more than 10 bys between these addresses。0 x 7，8，9。

 is where we might put the three， but there too。 it's not necessarily obvious where the three is relative to the two or relative to the one。

 If that just happens to be the first available spot。But what can I do now， Well。

 if this is just a canvas of memory in which I can store bitetes and bitetes， in turn。

 can be thought of as numbers， just patterns of bits that represent decimal numbers or whatever。

 Maybe I could use a few more of these bites to kind of stitch together these values in memory。

 Or if you prefer metaphorically， maybe to leave some breadcrumbs that lead from one value to the next to the next。

 or I kind of like the mental model if you're remember in olden times。

 you might stitch popcorn together using a thread around a Christmas tree at the holidays。 Well。

 this， too， might be a way metaphorically where we could kind of stitch these numbers together。😊。

By using their location。 So let me propose this。 let me get rid of some of the distracting bys that we're just not using in this story。

 But let me propose that for each of these three values。

 we use one additional byte for what we're gonna call metadata just to keep track of where the next value is。

 So again， nothing has changed yet。 The one is at a location， O x1，2，3。 The two is at location。

 O x 4，5，6， and the three is at location O x 7，9。 What if I， if you prefer yet another metaphor。

 create a sort of map for myself， a treasure map that leads from one value to the next。 Well。

 if I instead treat each of these numbers as taking up not one byte， but two。

 let me use the second byte。As a pointer， if you will， to the next location in memory。

 So the first byte will contain the actual number I care about the data like one。

 but the second byte now will contain the address of the next value I care about。

 which is going to be Ox 4，56。 And if you think about this now as a sort of treasure map， Ox4。

56 means the next value is at that location here。 Well。

 how do I get from this second location to the third。

 let me use the second byte for the second value to store the number0 x 7，8，9 and Ox 7，8，9。

 if I follow that pointer or address， if you will， it's going to lead me to the third value 3。

 which is again at location Ox 78，9。 And I'm deliberately using a term of R here， pointer。

 which is indeed how programmers would refer to these values inof far as they're sort of pointing from one location to another as depicted here by my hand。

 Now， as for the second by here。Technically， I don't really need a second byte because there's no fourth value yet。

 but to keep this data structure standardized， such that each of these chunks of memory are the same functionally。

 I should at least allocate that second byte， even for this number 3， even if I don't plan to use it。

 Now， even though I'm not going to use it， there's still one by or 8 Bs here。

 what should those 8 bits be permed as well， by convention， we're just going to make them all 0s。

 which will represent with the value O x 0， which just means 0，00，0，0，0，0，0。

 a sort of sentinel value such that if the computer ever sees a 0 byte。

 otherwise known as a null byte， it's sort of a terminus in that path。 That's it。

 there's no more values in this here list。 So this is a little cryptic to look at。 And frankly。

 no programmer， no computer scientists is really going care too much about what the specific addresses are。

 After all， the theme in computing。

![](img/662bcf12ea2e68802be56a49693956ea_29.png)

Generally that of abstraction， whereby we shouldn't have to care forever about these low level details。

 like the specific addresses at which these values live。 So， in fact。

 it's conventional to abstract this away。

![](img/662bcf12ea2e68802be56a49693956ea_31.png)

啊。So it's。So it's conventional to abstract those specific addresses away and simply indicate on say the whiteboard on which you're designing this data structure that this so-called linked list does have an address that is the address of the very first byte which I'll claim is again Ox1。

2，3 but at the end of the day all we rarely care about is that we've constructed a list of three values。

 irrespective of the specific and uninteresting addresses at which those three values live So we're going to draw it indeed with arrows pointing from one value to another in order to indicate visually in this case。

 that this is indeed visually pictorially a linked list of three values。

 each of which we're going to conventionally call a node so this node contains two bytes。

 one piece of data that I care about， and if you will one piece of metadata。

 which is information that really helps you maintain the data you care about in this case that metadata is the address of the next node in memory but。

😡。

![](img/662bcf12ea2e68802be56a49693956ea_33.png)

![](img/662bcf12ea2e68802be56a49693956ea_34.png)

Were going to make sure we remember where all of these values in memory are by storing one special pointer that is the address of the very beginning of the list。

 Now， it turns out that suffices。 I don't have to remember forever。

 the address of the second byte or the third byte， because I can always figure that out from these nodes in memory。

 And that is to say， if you give me the address of the very first byte in memory。

 and let me rewind before we had the arrows。 O x 1，2，3 will lead me to this node。 O x 4，5。

6 will lead me to this node。 O X 7，8，9 will lead me to this node and O x 0。

 Aka null will indicate that this is the end now of the list。



![](img/662bcf12ea2e68802be56a49693956ea_36.png)

So what's the upside here。 Well， among the advantages now of these linked lists is that we're no longer bound by the simple but nonetheless constraint of arrays whereby your values must be by definition back to back in memory。

 and that was limiting insof far as there might not be available space right next to the array and memory。

 which if nothing else is going to create a whole bunch of work for me。

 because as with our simple example earlier， I had a copy the one。

 the two in the three to a whole new location in memory just to add that fourth value。 Now。

 in the world of linked lists， I dare say if you wanted to insert the number four， well。

 you could plop it over here over here over here over here。

 it doesn't really matter because you could sort of pictorially draw another arrow from the three to that new value or more specifically。

 you could change that null byte0 x0， to be simply the address of that fourth additional value wherever it is in memory。



![](img/662bcf12ea2e68802be56a49693956ea_38.png)

![](img/662bcf12ea2e68802be56a49693956ea_39.png)

So linked lists offer this sort of dynamism where you can grow them and heck。

 you could even shrink them without having to impact all of the existing values as by copying them from one place to another。

 In other words， it would seem to just give us the ability to grow and shrink this data structure without wasting time really ever copying values around。

😡。

![](img/662bcf12ea2e68802be56a49693956ea_41.png)

But there might very well be a downside。 And in fact， that， again。

 is thematic in computing such that any time you sort of get a win。

 you're going to have to take a loss somewhere else。

 There's going to be a tradeoff that often involves time or space。 and indeed。

 we saw that with our discussion already of algorithms。 So let's consider， for instance。

 what the efficiency is of or the cost is of inserting a new value into a linked list as designed here。

 And let's consider our little cheat sheet of common running times for algorithms。

 This is not exhaustive， but it's representative of some very common running times as we've seen big O of n squared n log n and log n and1 in the last of those represented constant time。

 which is ideally the fastest， whereas O of n squared could take us quite a few steps。 Well。

 here is the beginning of a linked list。 And it's initially empty because it's not pointing at or storing the address of any actual nodes of value。

 So we're beginning at the beginning。How now might we insert the first value。 Well。

 if the first value is one， maybe there's some available space over there。

 and so we can draw an arrow from this variable， if you will。

 this placeholder for the beginning of the list that leads to that location and memory So I don't know where it is it's like X something So I would technically store that address in this box but that just means pictorially that it's pointing to this location and memory All right。

 what if I insert another value into this length list， how might I do it， Well。

 I dare say the simplest way to insert a new value into this list is to just kind of squeeze it into the beginning。

 and so I could put two there。 I could then put a third value right over there。

 and notice the one has not moved the two has not moved， I've just added the three wherever I can。

 And even though it might take a few steps， And if we were to type this out in pseudocode or actual code。

 it would take indeed a few steps to maintain these arrows and these address but the advantage here is that the one's not moving the two's not moving in heck if I add a fourth value。

 the three is not going。To move either。But notice what has happened。

 If I care about maintaining these elements in sorted order， say an increasing order 1，2，3。

 I've accidentally built this linked list in reverse order。 Now。

 obviously our humanize can easily see that。 well， you could just traverse the list in the opposite order。

 But that's not good enough， because how do you get to this last element of the list。 Well。

 you have to start at the beginning and follow the arrow， follow the arrow， follow the arrow。

 and that's going to take a bunch of steps just to get to the beginning。 And because these arrows。

 as we've described them only point in one direction。 so to speak。

 That is to say we're only maintaining the address of the next node， not the previous node。

 I'm going to have to go back and forth through this list again and again to find the first elements I inserted then the next element and the next element That's a lot a lot of steps。

 However， it's pretty darn efficient to do the insertion itself。

 not the subsequent searching or traversing of the list， but it's。Prety darn efficient Why。

 because all I have to do to insert a new node is find some space for it。

 point it at the existing list and then point this box at the new node。

 And that's gonna take what three steps give or take total， but that's constant time。

 which is generally good， because it doesn't matter how many nodes are already in the list。

 I can with just three steps， put another one in， put another one in， put another one in downside。

 of course， is that they're ending up in some random。 And in this case， reverse order。

 because I'm not inserting them deliberately in sorted order。 So among our little cheat sheet here。

 what might the running time of this implementation of inserting B。 Well。

 it's going to be constant time。 And that doesn't mean literally one step that would be super fast。

 but it doesn mean representatively a constant number of steps。

 And I'm spitballing that it might take some three steps in total。



![](img/662bcf12ea2e68802be56a49693956ea_43.png)

![](img/662bcf12ea2e68802be56a49693956ea_44.png)

![](img/662bcf12ea2e68802be56a49693956ea_45.png)

Alright， so that's not necessarily the best way to do this because indeed。

 we have this side effect that we're accidentally putting things in reverse order。

 even though we're sort of making a mess of things pretty darn fast， how else could we do this， Well。

 I could instead start with an empty list， And I could begin to add the number one。

 S I want to then insert the number two。 and suppose to keep it simple still。



![](img/662bcf12ea2e68802be56a49693956ea_47.png)

But different from the last algorithm， What if I insert the next node at the end of the list and the next node at the end of that list。

 that might by chance， give me sorted order 1，2，3， but had I inserted different numbers in a different order。

 I might be appending them。 so to speak to this linked list such that they still end up in sort of a messy order。

 So let me propose that we actually consider now that the running time of that algorithm。

 always inserting it at the end of the list is actually going be worse than the first approach because to find the end of the list。

 I have to traverse the list， Traverse the list， traverse the list every time I insert a new node。

 Now， to be fair， if your mind is going here， I could use some additional memory to just keep around the address of the most recently added node effectively keeping a pointer to the end of the list to ob the need for going through the list again and again。

 And that's totally fine。 but it's a little different algorithm。

 So I'm going keep it simple now just to compare and contrast these simplistic。



![](img/662bcf12ea2e68802be56a49693956ea_49.png)

![](img/662bcf12ea2e68802be56a49693956ea_50.png)

Imentations of inserting where we insert at the end。

 otherwise known as preending or we insert the sorry if we insert at the beginning。

 otherwise known as preending or we insert at the end known as appending。

 and the first running time we claimed was big O of one Con time。

 the second algorithm app is gonna to be linear time big O of n because if you've got n elements in the list。

 it's going take you that many steps to find the end assuming you don't use some additional memory to remember it in perpetuity。

 Well， let's take one other approach whereby we consciously insert elements in sorted order。

 And now depending on the elements， I want to insert it might end up at the beginning of the list。

 the middle of the list or the end of the list based on the value in question So suppose I insert the number two first。

 but I want to maintain sorted order。 And then I want to insert， say the number one。

 Well it doesn't matter where the one goes in memory。

 but it does matter that the arrows point in the appropriate direction。 So here I sort of got luck。



![](img/662bcf12ea2e68802be56a49693956ea_52.png)

![](img/662bcf12ea2e68802be56a49693956ea_53.png)

And that one is smaller than two。 So it really belongs at the beginning of the list。

 And we saw earlier that prepending to a list is pretty fast。

 constant time 1 to three steps to update all of the arrows in question。 Well， I got lucky here。

 But what if I next want to insert， say the number4 Well。

 that goes in terms of its values all the way at the end。

 So that's going now be big O of n and steps to find the end of the list。

 And then if I then certain the three， that's going to get a little trickier because I have to now find the right location for it。

 which again means traversing the list， looking for a value that's less than the three and greater than the three。

 and then putting it there。 And there's other scenarios too because if it's already the largest element it's going to end up the end。

 if it's already the smallest element， it's going to end up at the beginning。

 But we already saw those scenarios。 So in this case。

 the three ends up if you will in the middle of the list。

 So inserting here too would seem to take again linear time。

 And so here's already a disadvantage of the linked list。 at least。



![](img/662bcf12ea2e68802be56a49693956ea_55.png)

We've described the insertion algorithm whereby it's taking linear time end steps to add new values to the list。

 whereas in the array scenario， it turns out it's conventional that you just kind of plop it at the next location because by nature of arrays。

 you do keep track of the size of an array and therefore where the end of the array is。

 And so you have really what's called random access to arrays that's actually the origins of the term Ram random access memory means that you can jump right to the location where you want to plop the value with linked lists。

 we've created a bit more work for ourselves because we have the value。

 the upside of being able to find memory wherever it exists but we then need to stitch everything together and find all of those locations potentially again and again。

 and deletion in fact， is no better。 for instance， if here is the list of four values and we want to delete any one of those value specifically we you're gonna have to find it first。

 So really deleteleting is sort of equivalent to searching for value because you have to search for it before you can delete it And once you've deleted it。

 you have to then update these arrows， which is a bunch of。



![](img/662bcf12ea2e68802be56a49693956ea_57.png)

Steps 2。 So that， too， I would claim， is going to be linear time as well。 Meanwhile， searching。

 of course， gives us the same problem， because even if you don't plan to delete anything。

 you've got to find a value by definition of searching for it， so。Can we do better than this。

 It would seem that we've gained dynamism by introducing linked lists because we can grow and even shrink them much more easily than arrays insofar as we don't have to copy the original array to the new array location。

 which itself might be expensive， but we're still wasting time in other ways。

 by having to traverse the list。 So it's almost kind of a wash Moreover。

 with a linked list if you think about it。 with a。😊。



![](img/662bcf12ea2e68802be56a49693956ea_59.png)

Yeah。Moreover，'m sorry。Moreover， with a linked list， let's go back to the diagram。

 If you wanted to search for some value， you can't use so-called binary search whereby you go to the middle and then the middle of the middle and the middle of then a why。

 Well， even though you and I have this sort of bird's eye view of this picture and can kind of ballparked that the middle is like roughly over there。

 you don't know how to get to the middle unless you start at the beginning of the list count all of the elements therein。

 then do it again and go to the halfway point。 and then the halfway point of the halfway point and so forth。

 Now， again， you can use some additional memory to sort of remember that in perpetuity。

 But that's a lot of memory if it's a really big list。

 So it doesn't feel like we've made progress when it comes to the efficiency。



![](img/662bcf12ea2e68802be56a49693956ea_61.png)

![](img/662bcf12ea2e68802be56a49693956ea_62.png)

Of storing values in memory。 we've just given ourselves some flexibility when it comes to finding space for more and more values。

 So can we search more effectively and gain back the speed of binary search whereby I was able to divide and conquer the problem in half and half and half and half。

 Well， I think we can， if we take yet another approach to our computer's memory and treat that canvas as though we can build trees on it。

 Now， what do I mean by this。 Well， let me propose that we explore yet another data structure。

 namely a binary search tree， which is kind of like a family tree。

 But instead of having members of your family drawn in the computer's memory。

 you just have the values we're talking about in this case， but in a particular order。

 So for instance， let me propose that we're storing initially seven values。 And for simplicity。

 let's propose that these seven values are currently in an array。😊。



![](img/662bcf12ea2e68802be56a49693956ea_64.png)

![](img/662bcf12ea2e68802be56a49693956ea_65.png)

![](img/662bcf12ea2e68802be56a49693956ea_66.png)

It would look quite like this。 And it's an array by definition。

 because all of the values are back to back to back。

 recall that when you have these values back to back to back。

 you can very easily jump to the middle element， because if you know the index or address of the first element and you know the length of the array or the index or address of the last element。

 you can literally subtract one from the other divide by two round appropriately and boom。

 you can find the middle element， Similarlyly， you can find the middle of the middle。

 just by doing a bit of arithmetic as well。 So this is to say when we talk about random access where you can jump right to a location。

 It doesn't mean random in the sense that you can go to any location that you don't intend to。

 it means that you can jump in constant time to any specific address in memory， thus Ram。

 random access memory and arrays really thrive in that environment。

 you don't have to start at the beginning to find the n。

 you can do a little bit of arithmetic to find the end or even the middle because。



![](img/662bcf12ea2e68802be56a49693956ea_68.png)

![](img/662bcf12ea2e68802be56a49693956ea_69.png)

You know that every value is adjacent to the next。So can we gain that efficiency by。

 but but still give ourselves the dynamism of linked lists where we can grow and shrink them by just using any available memory without having to move things constantly around。

 Well， let me propose that we think about this array。Maybe not in in one dimension， but maybe two。

 So in fact， let me color code the middle element first。

 Let me color code the middle of the middles and then the remaining elements here。

 the middles of the middles of the middles， if you will。

 And let me propose that at least in your mind's eye。

 we redraw these seven values in two dimensions adding some verticality。

 So the numbers have only moved up or down， they've maintained the same order from left to right。

 and let me propose that now each of these numbers is just yet another node。

 a chunk of memory that you're using to store some data and maybe metadata。

 But this time for metadata， let's not just store the address of the next value。

 let's use two pieces of metadata， two bytes， if you will， two pointers， if you will， two arrows。

 if you will。 to keep track for every element which element is smaller than it and which element is larger than it。

 And that's the key definition of a so-called binary search tree。



![](img/662bcf12ea2e68802be56a49693956ea_71.png)

![](img/662bcf12ea2e68802be56a49693956ea_72.png)

That for any node you look at， its left child， so to speak。

 borrowing the family tree metaphor is going to be less than it。

And its right child is going to be greater than it。 And that's true of the subtes。 For instance。

 relative to the number four， not only is the left child smaller， but the left subtree is smaller。

 Every element to the left of four will be smaller， even the three。

 every number to the right of the four is going to be larger than the four， including the five。

 So that's the definition of a binary search tree， you maintain that particular order。

 Now even though I haven't drawn it to scale， you can think of indeed。

 each of these note as taking up three bys， one for the data you care about the actual number like four。

 one for the address of the point or two， the left child and one for the address of the point or two。

 the right child。 So each of these boxes and two arrows， collectively represent three by。 And again。

 this is what I mean by using your computer's memory as a canvas。 the end of the day。

 All we have are zeros and。😊。

![](img/662bcf12ea2e68802be56a49693956ea_74.png)

OneAnd in turn， bytes， units of8。 So I can use those， really， however I want。

 And I am choosing now to use those in groups of three bys in order to create effectively this diagram。

 Now， this diagram is not going to be out literally in this way。

 top to bottom left to right inside of the computer's memory， these things could be anywhere。

 But that's what the arrows are for。 they're going to point at the locations in question。 Now。

 what's the value of designing this tree， this binary search tree in this way。

 I think I have magically gained back the ability to do binary search。 Why Well。

 so long as this binary search tree is ultimately defined by its root。 The topmost elements。

 and that is how you access all of the other elements。

 Watch how many steps it takes me to find any number。 supposeuppose I'm searching for the number one。

 Well， obviously， with our birds eye view， you can see it。 but the computer can't。

 if the computer starts searching。

![](img/662bcf12ea2e68802be56a49693956ea_76.png)

For the number one at the root of this binary search tree， it's going to see the number4。

 but it can use a conditional recall。 can in turn， a boolean expression to ask itself。

 is the number I'm looking for less than or greater than or heck equal to the number I'm looking at。

 Well， one is obviously less than4。 So the computer can search down this way and ask the same question again recursively。

 if you will。 I the number I'm looking for one less than greater than or equal to this value。

 Of course， the number one is less than And so we go down this way。

 Notice we have not looked at this element or this element or this element or this element。 In fact。

 we've sort of divided and conquered this problem by chopping the tree， if you will。

 in half and half in half， that is to say when I go left here。

 it's kind of like if destructively snpping the tree there and not caring about anything in that direction。

 Similarlyly， when I go this way， it's sort of like snipping the tree here。



![](img/662bcf12ea2e68802be56a49693956ea_78.png)

Caring about anything in that direction。 And we've sort of seen this metaphor before。 And it too。

 was fairly destructive when I toured the phone book in half in half in half。

 I didn't care about half of the book to the left or half of the book to the right again and again。

 here， too， it's sort of the same thing。 Of course， it's not destructive。

 These elements and memory aren't going anywhere。 But we are saving time by not looking at half of the tree。

 half of the subte， half of the half of the subtree and so forth。 So what do we gain from this。

 what it would seem that the running time now of this algorithm is now log of n。

 technically logbased to of n because I'm effectively dividing the problem again and again and again in half by traversing it in that way。

 Now， what's the tradeoff of half done this， because that seems like a win。

 I now have the ability again to do binary search， which was one of the fastest algorithms we've thus seen I no longer。



![](img/662bcf12ea2e68802be56a49693956ea_80.png)

![](img/662bcf12ea2e68802be56a49693956ea_81.png)

![](img/662bcf12ea2e68802be56a49693956ea_82.png)

Suffer from the slowness of having to follow all of those arrows just to find the middle or the end elements and so forth。

 So that seems to be a win。 But what's the downside。 Well， it would seem that。



![](img/662bcf12ea2e68802be56a49693956ea_84.png)

There is a trade off。 I'm saving time。But I'm losing space， if you will， indeed。

 this tree takes up even more memory than the data structures we've seen thus far。

 Arrays were super efficient。 All we started was the data， the values 1，2，3。

 and even 4 that we cared about back to back to back， there was no metadata， There were no pointers。

 there were no additional bites just to maintain that data structure linked list， though。

 like literally overnight doubled the amount of space we needed。

 because we needed as much space for the data， the values we cared about 1，2，3，4。

 But we also needed metadata， bys to store O X 1，2，3，0 X 4，5，6，0 x 7，8，9。

 So that was twice as much space。 Some or other， You've let me spend three times as much space with this data structure。

 Y， because for every value， like 4， we now have two pieces of metadata。

 the left child and the right child or technically， the addresses thereof or pointers there too。 Now。

 technically， there's a little bit of savings at the bottom here。 insofar as the leaf nodes。

 the grandchildren， if you will， don't。Actually have any great grandchildren themselves or children themselves。

 but per my comments earlier for conformance， we really want every node to be structured in the same way。

 even if we're not using those two children， pointers， left and right。

 So technically even these nodes are taking up three bytes in this story。

 It's just that two of those three bys or null O x0。

 which indicates again that there really is no arrow there。

 It's not pointed to anything at least as of now， maybe there will be because if we insert like the number 0 into this might actually belong as the left child of this here number one。

So it takes up more space to use this binary search tree than it did a linked list and then it did in array。

 What other downsides might there be。 Well， I've showed you this binary tree already built。

 but how did it get built up in precisely this way。

 let's consider building this tree step by step and see if there's a bit of danger there too。

 For instance， if we clear the board。 and begin again with inserting just a single number like two this time。

 that might go at the root of the tree， It has no children。

 So it's a fairly simple binary search tree， It doesn't look like much of a tree。

 but it still meets the definition because it's greater than any of its left children。

 which is not applicable。 And it's less than any of its right children， which is also not applicable。

 So it doesn't violate any of the terms。 suppose we then insert the number one。 Well， ideally。

 it would go over here， because that's less than the two。 And I think we're still good。

 still doesn't look like a tree， but it also doesn't violate the definition thereof。

 If I then insert the number3， It's going to go numerically over here is the right child because it's。

thanhan the number two。 So it would seem fairly straightforward when building a binary search tree that it all sort of works out perfectly。

 but that's not necessarily going to be the case。 I chose this order 2，1，3， deliberately。

 to show that sometimes we can get lucky and lay out the memory exactly as we want the first time around。

 But consider a more perverse case， if you will， a worst case scenario in which the insertion order happens to be inserting the number one。

So far， so good， then the number two。So far， so good， but then then number three。

I don't like where this is going。 Now， technically。

 this is a binary search tree because one is greater than anything to the left。

 even though that's not applicable， one is less than everything to the right two is less than everything to the right of it and greater than nothing over here。

 So it technically meets the definition of a binary search tree， but as you can kind of see。

 especially if we continue to insert4 and5， So ironically in this case。

 inserting numbers in increasing order is actually a bad thing because this binary search tree is going to devolve。

 if you will， into what kind of looks like a linked list， you know。

 it's not drawn in a way that fits on the screen left to right。

 but that was just an artist rendition thereof， it's going to just get long and stringy。

 which is really just going to be a linked list from smallest to largest even though I might be drawing it in this way。

 Now that's fine like that's still a connected data structure， you can still。😡。



![](img/662bcf12ea2e68802be56a49693956ea_86.png)

Search for values， but you can't search for them very efficiently， because it's so long and stringy。

 But there's a correction here， right， Like even with three values。

 I could make this look more like a tree if I balance it by kind of pivoting everything like this。

 So the two should eventually become the new route。 One should become its left child。

 The three should remain its right child。 And then I think off to a better start。 In other words。

 if my algorithm for inserting nodes is a little more intelligent。

 and as soon as I notice that the thing is devolving until like a long and stringy linked list， fine。

 do some kind of pivot to correct that， so that the problem doesn't get too bad too quickly。

 And that's fine。 And in fact， there are other data structures that we won't talk about in this particular class that do exactly that。

 They have additional steps， additional code， if you will。

 that tell the computer how to maintain a balanced binary search tree。

 which this at the moment is not。 But to do so is gonna take a few more steps。

 But it turns out that's not terribly。😊。

![](img/662bcf12ea2e68802be56a49693956ea_88.png)

![](img/662bcf12ea2e68802be56a49693956ea_89.png)

![](img/662bcf12ea2e68802be56a49693956ea_90.png)

StepsAnd we're still going to be able to retain ultimately the logarithmic running time of searching and deleting in and inserting into a binary search tree。

 even if we maintain balance， just so happens that the algorithm for doing so is a little more involved。

 this， of course， is just a pretty simple picture to pivot this over to the left。

 So whereas a binary search tree could devolve into linear time big O of n not if we are smart about it and we maintain a balance to that tree。

 as by changing what the root is as soon as we see that the situation is devolving So as to maintain more of an actual tree like structure。

 So funny enough， it seems as though this is how we could be in our phones。

 be it ios or Android storing our contacts。 we could be storing them in a binary search tree。

 better yet a balanced binary search tree， the nodes of which ultimately store things like John。😊。



![](img/662bcf12ea2e68802be56a49693956ea_92.png)

![](img/662bcf12ea2e68802be56a49693956ea_93.png)

![](img/662bcf12ea2e68802be56a49693956ea_94.png)

![](img/662bcf12ea2e68802be56a49693956ea_95.png)

![](img/662bcf12ea2e68802be56a49693956ea_96.png)

![](img/662bcf12ea2e68802be56a49693956ea_97.png)

Harvard's phone number and maybe email address and other information。

 It doesn't have to just be simple numbers like 1，2，3，4。 We can actually store， of course。

 strings of text and more information as well。 but we can therefore store all of our contact in a way that allows me very efficiently to insert someone else to delete someone。

 if I don't want them in my phone anymore without having to use a simplistic array which recall might result in ios or Android having to constantly copy all of your contacts from one big chunk of memory to another just to add one more person。

 but when you use the autocomplete feature inside of your contacts app。

 you ideally want to be able to find someone quite quickly as via a binary search and not something slow or like linear search And so with binary search trees alone。

 I think we're pretty on our way to getting the best of both worlds， dynamism。

 dynamic insertion and deletion that doesn't require linear time necessarily。 In fact。

 it looks like we could achieve such logarithmic time and searching can be done in。



![](img/662bcf12ea2e68802be56a49693956ea_99.png)

![](img/662bcf12ea2e68802be56a49693956ea_100.png)

Logarithmic time that is to say big O of log n。😡，So we're back in business。

 even though there's still a tradeoff。 What was that tradeoff， Well， any time we're saving time。

 we're probably spending something else。 And indeed， even though we're saving time。

 we're using more space。 And maybe that's fine。 And frankly， nowadays。

 space is getting less and less expensive。 The memory you can have inside of your phone in your laptop。

 your desktop is getting less and less expensive。 So maybe that's a reasonable tradeoff。 Then again。

 there's other tradeoffs。 And this doesn't really apply to us as the users of these devices。

 But the programmers at Apple and Google and beyond probably had to write more complicated code。

 more sophisticated code， fancier algorithms to implement the binary search tree than a simple array。

 and even maybe a simple link list。 So human time， developer time。

 development cost might be yet another resource that we want to factor in when it comes to making decisions。

 for instance， at Apple and Google， which algorithm should we do， it might be faster for the user。

 But if it's gonna to take the programmers， lots lots of time to do it。 And therefore cost maybe。



![](img/662bcf12ea2e68802be56a49693956ea_102.png)

It's not the right call。 then again， if you're fortunate to have millions of users having one team member or a small team work on a better feature for longer。

 you can amortize that cost， of course， over the many， many， many uses of the algorithm itself。😡。

All right， See like we're in a pretty good place。 Are we done。Well， not necessarily。

 Lo n time is pretty darn good。 Loarithmic time。 but the best thing we've seen on our little cheat sheet is that socalled constant time。

 Big O of one。 Can we get closer to constant time， because that's kind of the holy grail of an algorithm。

 if no matter how much data is inside the computer's memory。

 you can still find something like that one step， or maybe two steps or three steps。

 But some number of steps that has no dependent on the number of values already in the data structure。

 So you know what， let's get a little crazy here。 And let's see if we can maybe borrow some ideas from arrays and link lists and kind of mash them together。

 kind of like we did with binary search trees， But let's build something even fancier inside of the computer's memory。

 namely a hash table。😊。

![](img/662bcf12ea2e68802be56a49693956ea_104.png)

So a hash table is a data structure that if we do this well。

 is going to get us closer to constant time。Well， what could we do， Well。

 let me propose that I'm going to start with an array。

 I'm going to draw it vertically just so it fits nicely on the screen。

 but that's just an artist rendition thereof。 It's equivalent to an array that goes left right because again。

 that chip and memory has no notion of up down left right， This is just how we are addressing things。

 But notice if you count these up， I've deliberately chosen an array of size 26。 Why Well。

 for this story， let's move away from storing simple numbers like 1，2，3，4。

 and let's actually store people like John Harvard。

 that is contacts in your address book which might include a name and in turn a number or an email address or whatever other pieces of data you keep in your phone。



![](img/662bcf12ea2e68802be56a49693956ea_106.png)

![](img/662bcf12ea2e68802be56a49693956ea_107.png)

So why 26， Well， maybe I could store everyone whose name starts with a here。

 Everyone whose name starts with Z down here。 and then all of the letters in the English alphabet in between。

 And you can do this for any human language。 Now， that's all fine and good， at least initially。

 for instance， if I draw some inspiration from maybe the world of Nintendo。

 we can store the names of Nintendo characters in the computer's memory as follows。

 Each of these locations can， of course， have an address associated with it or an index index 0 or location 0。

 index 25。 what happened to 26。 Well， again， anytime you start counting it 0。

 you only go as high as n-1， if n is 26。 therefore。

 the large the lowest elements on the board here is gonna to be 25。 Allright。

 now you can conceptually think of each of these elements in the array as representing a through Z accordingly。

 So in this case， a is not in fact 65 B is not in fact 66 because。

I'm not using ASI or more generally Unicode here。 I'm really just treating the first box。

 the zero box as a placeholder for a and the 26th box location 25， as a placeholder for the Z names。

 Allright， let's go ahead now and start inserting some names。 It's a Mario here in the middle。 Well。

 that's gonna go at the M location roughly here， what's that0，1，2，3，4，5，6，7，8，9，101112。

 it's the 13th letter M。 but because we start counting at 0， it's at location 12。 So all is good now。

 what's nice about this data structure。 Well， if I subsequently start searching for Mario in my phone and type in M。

 the phone knows immediately go to location 12 why。

 because if it looks at just the first letter of Mario。

 it's pretty easy to figure out that the letter M is the 12 letter of the alphabe because you could write code to do that And you can jump randomly But specifically to that location。

 You don't have to start at the top。

![](img/662bcf12ea2e68802be56a49693956ea_109.png)

![](img/662bcf12ea2e68802be56a49693956ea_110.png)

![](img/662bcf12ea2e68802be56a49693956ea_111.png)

![](img/662bcf12ea2e68802be56a49693956ea_112.png)

Looking for Mario， you know that Mario， first name starting with M is going be at location 12。

 no matter who is above or below him。 Allright， suppose we insert some other friends into our phone。

 maybe Louis。Now I got to do that again， let me fix that and I'll go back to this position。

Color was wrong。好下。Okay。Let's insert another friend in the phone now。 How about Luigi。

 Luigi goes at location 11， which is one before Mario， because L comes right before M。

 So far so good。 Maybe next we insert Peach， Peach goes down here at the location that corresponds to the first letter of her name。

 P。 Now， if we continue with this， we're in pretty good shape， we can store Daisy。

 and we can store Waro and Zel Don Yoshi and all of these other friends of ours in our phone。

 And if I subsequently want to search for any of these characters。

 the algorithm I've implemented can simply look at the first letter of that name and jump immediately to that location。



![](img/662bcf12ea2e68802be56a49693956ea_114.png)

![](img/662bcf12ea2e68802be56a49693956ea_115.png)

There's your constant time because I have a fixed length array， size 26。

 and I've associated in my algorithm here， numbers with each of those locations，0 through 25。

 And because I can certainly look at the first letter。Of a string of text， someone's name。

 And I can see that letter。 and I can convert it to a number。 For instance， here's where the 65。

 the 66 actually does come in handy。 When I see a name that starts with B。

 While I know B starts with I know B is that has the depth。



![](img/662bcf12ea2e68802be56a49693956ea_117.png)

![](img/662bcf12ea2e68802be56a49693956ea_118.png)

If I insert someone whose name starts with B like Bdo here。

 I know that B in Uniicode is the value 66， but I also know it's the second value in my array。

 so I can essentially subtract 65 from the Uniicode value of the first letter of someone's name to immediately get the right location。

 So here's where it's so wonderfully useful that letters have been standardized as having corresponding decimal values in both Uniode and previously ASI because you can do some very simple arithmetic in so calledled constant time to convert those unicode values to the corresponding values from 0 to 25 here。

 So， in fact， to insert each and every one of these Nintendo friends takes me constant time。

 Maybe not one step。

![](img/662bcf12ea2e68802be56a49693956ea_120.png)

It's probably like two or three because arrays indeed give me this random access based on there。

Athmetic indices 0 through 25。 So this is great。 and this is a hash table。

 A hash table is essentially an array that you use to index into to store values that specific locations。

 but it's not all hash table does because what if I've got more friends than these and I have to store a second name that starts with L。

 and a third name that starts with L。 Well， where does link go， Well。

 I don't want to put link for instance， where Luigi was because then I'd have to delete Luigi just to add link or anyone else whose name starts with L。

 which doesn't seem particularly compelling And so what I'm done here pictorially is I've proposed that okay。

 okay， link in really anyone whose name starts with L belongs at this location 11 let me store that person than not exactly at that location necessarily。

 but in a linked list at that location。 So as implemented here。

 a hash table can be thought of as an array。😊。

![](img/662bcf12ea2e68802be56a49693956ea_122.png)

![](img/662bcf12ea2e68802be56a49693956ea_123.png)

![](img/662bcf12ea2e68802be56a49693956ea_124.png)

Of linked lists and those linked lists exist for the sole purpose of managing collisions。

 A collision in a hash table is when two values both hash to， so to speak the same location。

 L is going go to 111111。 and unless you're willing to just plop that person somewhere else。

 seemingly randomly in memory or you're willing to delete whoever is there to add that person you want to probably just start linking them together somehow。

 So on the one hand， this is a wonderful solution， because it means I can store as many as three or more names that start with L。

 the downside is this is devolving again， now my hash table is sort of devolving into a linked list based on this design。

 because what about in the most perverse case， I only have friends whose names start with L。

 My hash table is gonna have 26 locations， only one of which I'm using location 11 and it's just gonna be one massive linked list there of all of my friends。

😊。

![](img/662bcf12ea2e68802be56a49693956ea_126.png)

![](img/662bcf12ea2e68802be56a49693956ea_127.png)

Whose names start with L。 Not the best design。 Now， in this case， that hasn't happened yet。

 but even in the world of Nintendo， there might be a lot of these so-called collisions that I can solve by using these chains。

 these length list。 But again， my data structure is moving away now from a running time akin to constant time。

 big O of1 starting to approach big O of n。 And in fact。

 if we often consider the worst case scenario especially when n gets large in the worst case。

 I only know people whose name starts with L or any letter of the alphabet。

 this is going to devolve entirely into a linked list。 So technically。

 if we analyze the running time of this hash tables implementation。

 it's technically going to be big O of N。 Now， in practice。

 and let'sveer a little away from theory here， in practice。

 am I really going to be friends with only people whose names start with L， like most likely not。

 I'm probably going to have friends whose names also start with M and P。



![](img/662bcf12ea2e68802be56a49693956ea_129.png)

![](img/662bcf12ea2e68802be56a49693956ea_130.png)

And B in many letters of the alphabet， maybe not all。

 I don't have that many friends whose names start with in English Q or X。

 which tend to statistically be less common。 But on the whole。

 if you assume a uniform distribution of friends to add some statistics to friendship。

 then you might technically have something closer to。



![](img/662bcf12ea2e68802be56a49693956ea_132.png)

Oh。Sorry， I didn't want to say that。And let me cut this stuff。

Now if we assume a uniform distribution of friends， so to speak。

 to add some statistics to the world of friends， well it's not going to be quite as bad as that in fact。

 we might really have big o of n divided by K where K is some constant like 26 So ideally if we have a uniform distribution of friends over the English alphabet based on the first letter of their names。

 each of my linked lists or chains should be maximally n divided by K where n is the total number of people in my phone where N K is in fact 26。

 but again recall that when we discussed this asymptotic notation。

 big O and omega we only really cared about the highest order terms。

 not the denominator or constants in this case， so really now I'm sort of nitpicking big O of n divided by K is really still just big o of n because if you've got lots and lots of values n doesn't matter if you divided by 26。

 there's still going to be a lot of values in each of these linked lists and therefore they might still be slow。

😡，We're drifting again。 it seems from our constant time。 So the source of this problem， though。

 this performance impact seems to be the fact that we're getting these collisions。

 I've got multiple people whose name starts with L and a bunch of other letters of the alphabet。

 So how can we reduce that probability， because if I don't have those collisions。

 I'm not going have these linked list and therefore I'm not going have this performance slowdown。

 So what if I do something like this。 instead of having a linked list， sorry。

 instead of having an array of size 26。 What if I use a bigger array And look at not just the first letter of someone's name。

 but maybe the second and the third， I bet it's less likely that I'm gonna have two friends whose name start with the first three letters of their name。

 not impossible， but statistically much less likely。

 So we could put these same three friends whose name start with L in this way in the array and this array is not going to fit on the screen because it's gonna have thousands of boxes now。

 but you can imagine this box represents。

![](img/662bcf12ea2e68802be56a49693956ea_134.png)

![](img/662bcf12ea2e68802be56a49693956ea_135.png)

L A， A， L， A B， L， A C， L A D， all the way down to maybe L U J here after L U I。 Now。

 what's the advantage of this。 Well， if I take the time to look not just at the first。

 but the first three letters of each of my friends names。

 Then I can come up with a location in this array that probably doesn't have any collisions。

 And indeed， these three friends now have their own spots。 Well， what's the tradeoff， Well。

 here the trade off is pretty obvious to save time and reduce collisions， I'm using a lot more space。

 Now I'm using 26 times 26 times 26， in order to have enough boxes to fit a representative for each of those patterns of Allf。

 I messed that up， sorry。

![](img/662bcf12ea2e68802be56a49693956ea_137.png)

![](img/662bcf12ea2e68802be56a49693956ea_138.png)

嗯。26 times 26 times 26， which is gonna give me many more boxes now。

 even though I haven't drawn nearly all of them on the screen。

 I'm sort of waving my hand with some dot dot dots here instead。

 So if you're willing to spend that much more memory， great。

 But notice the other tradeoff that's implicit here， I don't have any friends。

 apparently whose names start with L A A and L AB and L。

 And I can think of other weird combinations of three letters that just are not going to represent human names。

 at least in English， So I'm wasting a huge amount of space now。

 whereas I wasn't really wasting nearly as much space。 when I only had 26 positions。

 So on the one hand， you can do it on the other hand， there's a tradeoff。 And at the end of the day。

 it's a design decision。 It depends on what is more important or perhaps equivalently。

 what is less costly for you to implement。

![](img/662bcf12ea2e68802be56a49693956ea_140.png)

Allright， but that does give us the sort of holy grail of big O of one， but not quite。

 there is still a chance that there might be two friends or more friends whose names do， in fact。

 start with the same first three letters。 So maybe hash tables aren't quite where we want to end this tail。

 In fact， let me show you one other data structure that maybe really literally gives us constant time access。

 But we'll see what price we pay。 And this is compelling because of the same picture。

 recall that when we analyze the running time of， say。

 those three algorithms with which we tore a phone book in half。

 the first two algorithms where these straight lines。

 because there was a one to one or one to two relationship between the number of steps and the number of pages in that their phone book。

 My third algorithm now that we know now。My third algorithm， which we now know is binary search。

 was log base2 of N。 And indeed， that was a very different shape。

 What we're really trying to get to is an algorithm whose running time is constant， represented by K。

 whereby no matter how big the problem is。 The solution there， too takes the same amount of time。

 K steps or K might be 1 might be 10 might even be 1000。

 but it is independent of n the size of the problem。 And indeed。

 if we reintroduce our big O notation， we can think of this same chart now as really representing two linear algorithms。

 even though the slope is different， these are really the same algorithm fundamentally Big O of n。

 as we'll say， this algorithm doesn't really matter what the base is。

 we're going to call a big O of log n。 But this third algorithm now here is something now。

 but this sorry， I didn't want to say that。Hm。Now， this third algorithm here would be said to be log of n or big。

 Im sorry。This third algorithm here is big O of log n doesn't really matter what the base is here。

 but this algorithm that we're seeking now， the constant time algorithm might be said to be in big O of one。

 whatever the constant factor is1 to，3 steps，100 steps，1000 steps。 constant number of steps。

 Can we get to that point。 Well， let me propose that we try to get there。 note un intended。

 I guess kind of intended with tries， short for retrieval even though retrieval isn't pronounced retririeval。

 a try is another type of tree， but that's not a binary search tree。

 And here you see yet another mashup of ideas that we've discussed today。

 a try shall be a tree made up of as。 So it seems we have an evolution of data structure here where people just started mashing together different ideas。

 and we get these sort of amalgams of first principles。 This one， a try begins with a root node。

 That root node， I'm not going to draw quite as abstractly as a single box。

 I'm going to draw it as 20。6ix boxes， just to convey more clearly that inside of this node is technically an array of size 26 and that arrays locations suffice it to say。

 are going to represent the letters in the English alphabet and we're going to use those locations to implicitly store whether or not someone's name and in turn。

 phone number or email address or anything else is in this data structure。 So， for instance。

 if we if we alphabetically label each of those boxes just for the sake of discussion。

And now highlight T。 supposeose that we want to insert the first name into this data structure。

 So I've gone to my phone。 I've said add new friend。 I type in the letter T for their name。

 I type in the letter O for their name， I type in the letter A for their name。

 and then I type in the letter D for their name， because why my first friend in my phone here in the world of the Nintendo at least is going to be the character known as toad。

 Now I've drawn this picture a little differently at the very end。

 such that when I traverse these nodes and in turn these arrays。

 I'm just kind of indicating with a green box here that the box stops here。

 That is to say if you can reach this point， and there's no arrows continuing further。

 T0 A is a name in this data structure。 Suppose I want to insert another name into this data structure。

 Oh oh， supposeose that other friend's name is tot。 Well， that's fine。

 if the next friend's name is a super string， so to speak， a longer version of that same prefix。T， O。

 A， D， E， T， T， E， we just have to indicate as with the green box here pictorially that another name ends here。

 So what are these green boxes， will it just be additional bit or maybe an additional byte。

 We're just using more of that canvas to sort of put a check mark conceptually that means there is the name that stops here in memory。

 doesn't really matter， though for today's purpose is how we implement that underneath the hood。

 So in other words， notice that we are implicitly storing the names toad and toed simply by having one array for each letter in those names with arrows from the positions that correspond to those letters leading to the array that represents the next letter in that person's name。

 So what are these arrows， Well those are just pointers or addresses。

 which is to say if this array has size 26， all of these values initially are blank that is null O x0。

 if you will， but for the location。T， what we're gonna do is change that initially blank value or null value to be the address of this array down here。

 And once we've typed in the letter O on my phone， I'm going to then update this initially blank value to point at another array。

 another array。 And now that I'm done saving toad's name in my phone。

 another byte is going to be used to indicate that， okay， even if there's an arrow there。

 a name does stop here。 So the mere presence of non zero values。

 the mere presence of addresses that lead you to another node in this data structure indicate implicitly now。

 that the name T Oad is in this data structure and similarly tot is in this data structure。 Now。

 they don't all have to be super strings or substrs of each other。

 if I have a third friend Tom in this world。 Well， T O M can similarly be represented in this data structure and notice here。

 we're reusing some of those same array。 So on the one hand， there's a bit of efficiency。Here。

 but on the other hand， even at a glance with just three friends in my phone。

 you can see an inefficiency， too。What's that inefficiency， Well。

 especially if all of my friends names start with T。

 I'm wasting 25 locations in memory because I have no friends who start with A。

 B or Z or anything in between。 So it's a little wasteful to be using these arrays。 And frankly。

 even if I just to insert a few more friends into this try data structure， which， again。

 is a tree of arrays， it's gonna to get very bulky with relatively few pointers therein。

 and a lot of null values， a lot of empty locations in these。😊，Arays。 Now。

 what's the implication of that。 Well， on the one hand， we are clearly wasting a lot of space。

 So I am not loving that， but what's the implication， time wise of all of this， Well。

 the running time of a try implemented in this way is said to be Conant time big O of 1 Now。

 why is that we notice， And in your mind's， I imagine there being not 3 names in this tree， but 30。

300，303 million， it's going to take a massive amount of space， Yes。

 there's going to be a lot of arrays on the screen with a lot of empty value still。

 but how many steps does it take you to find toad in this data structure。

 even if there are 30 or 300 or 3 million other names，1，2，3，4。

 how many steps is it going to take to find tot 1，2，3，4，5，6。



![](img/662bcf12ea2e68802be56a49693956ea_142.png)

![](img/662bcf12ea2e68802be56a49693956ea_143.png)

7，8， no matter how many other names and in turn arrays and nodes are in this data structure。

 how many steps define Tom T O M 3 steps。 And that is independent of the total number of names in the data structure。

 And that's a powerful idea。 You can store as much data in this data structure as you want。

 and can be really， really large， but it will always take a constant number of steps to find any individual name。

 And if realistically， we assume that there's some upper bound on the length of a human name。

 I don't know if it's 1，2，3，4，5，6，7，8 for todt， maybe it's 10 letters， maybe it's 20。

 there's some really long names out there if you Google， maybe it's 200 or something like that。

 but it is finite。 I know of no one in the world， or in the Nintendo world whose name is infinitely long。

 it certainly stands to reason that that is a constant K。

 And even though I'm quibbling here a little bit。 in so far。



![](img/662bcf12ea2e68802be56a49693956ea_145.png)

As the maximum length of someone's name is constant， there's an upper bound on it。

Searching for inserting into deleting from a try is said to be constant time。 That is big O of one。

 We found our holy grail， and it's not going to devolve into a linked list with really long chains。

 because there's no notion of collisions anymore， we've handled that。

 even in the case of toad and toadt， as by having additional markers that keep track implicitly of where a name ends。

😡。

![](img/662bcf12ea2e68802be56a49693956ea_147.png)

Now do you want to use a try？Frankly， this is kind of a head fake。 Probably not。

 They really do tend to use and therefore waste quite a bit of space。 And so in practice。

 it tends to be better to use typically a hash table in some form。 Now， yes， yes， yes。

 there tend to be collisions and hash tables， but I chose the most simplistic of hash functions。

 the decision making process that determines given a domain of inputs， a through Z。

 what the range of output should be0 through 25， if I choose a fancier hash function。

 maybe looking at the first three letters or maybe only the first two or something more sophisticated than that。

 I bet I can statistically reduce the probability of collisions。

 even if there's occasionally some collisions， but there's not going to be a lot of collisions。

 And indeed， in general， that tends to be appealing when you're designing a data structure that at least in the average case。

 the common case it performs very well。 And yes， even though there might be some perverse case is sometimes that are really slow because darn it。

A bunch of collisions there that might very well be okay if those are indeed the exception to the rule and not the rule itself。

😡，So。That said。Let's abstract on top of some of this。

 It turns out that what we focused on thus far are indeed data structures。

 ways to stitch together information in your computer's memory by treating it as that sort of canvas in addressable canvas。

 And we looked at arrays， we looked at linked lists。

 We looked at trees specifically binary search trees。 we then looked at hash tables and now tries。

 But it turns out in the world of computing。 There's also what we'll call abstract data types。

 which are sort of data structures， but they're not necessarily specific data structures。

 that is there more ideas， concepts， features that can be implemented with different data structures。

 So data structures tend to be among your implementation details。

 And I meant it when I said you might be working in a whiteboard drawing a picture。

 with a colleague trying to decide how do we want to lay out this product in memory。 Now。

 as an aside， when you're using programming languages that are popular and industry。

 odds are you just let the programming language figure out how to store things in memory for you。



![](img/662bcf12ea2e68802be56a49693956ea_149.png)

![](img/662bcf12ea2e68802be56a49693956ea_150.png)

But nonetheless， part of the brainstorming process very often does involve deciding well。

 what data structures should we be using in some form under the hood。

 But at some point you want to abstract on top of those low level implementation details。

 and you want to consider， well， what functionality do we really care about。

 What is the business problem we're trying to solve in code and in turn with algorithms and data structures and offer a few examples thereof。

 a dictionary is a very common thing to implement in code and by dictionary。

 I might mean literally words and definitions， be it in English or any other language。

 But it might also more generally just be something associated with something else。 Indeed。

 dictionaries or sort of the Swiss army knives of abstract data types in that they let you associate anything with anything else。



![](img/662bcf12ea2e68802be56a49693956ea_152.png)

For instance， if you were to draw this two column table like this and you just wanted to store。

 for instance， name， number， name， number， name， number。 you could do exactly that。Dim it。诶。Tocom。

 for instance， if you wanted to store words and definitions， you could do so in these two columns。

 You could put the words here as a list on the left and the corresponding definitions in the column at right。

 You could also store more generally keys and values where the key is the thing on the left。

 The value is the thing on the right。 So it might be word in a definition。

 But it might also be a name and a number as in a phone book， because if you think about it。

 a phone book， be it physical or in your phone is kind of like a dictionary。

 But instead of words and definitions， it's indeed names and numbers names and emails or whatever nowadays instead。

 So we could store data like this， really on a blackboard left to right， top to bottom。

 But how could we implement that encode code while a dictionary is just a collection of key value pairs。

 How can you implement a dictionary though in memory。

 This is where we have to break the abstraction barrier and really get into the weeds of like what's underneath the hood of the computer。

 Well I could store。

![](img/662bcf12ea2e68802be56a49693956ea_154.png)

![](img/662bcf12ea2e68802be56a49693956ea_155.png)

![](img/662bcf12ea2e68802be56a49693956ea_156.png)

Keys and values be they words and definitions or names and numbers using an array。

 Like I could just have a really big array from left to right。

 storing all of my friends names and numbers alphabetically or all of the words and definitions in a dictionary alphabetically。

 Maybe that's okay， too， because it's not that often that you add new words to a dictionary。

 although I guess the big dictionary manufacturers do do that like once a year。

 So maybe that's not the best design to use an array。 Okay， so let's use a linked list。

 this would allow the dictionary every year to grow and this would allow me in my phone to add or even remove new names and numbers on some periodic basis。

 So a link list is better， but wait a minute， linked list were giving me linear time。

 not logarithmic。 So maybe I want to use a binary search tree， which I could。

 but that too is giving me logarithm。 Can we want to use a hash table or try。 So long story short。

 even to implement the simplest of ideas， a dictionary with words and definitions or a phone book equivalently。



![](img/662bcf12ea2e68802be56a49693956ea_158.png)

With names and numbers， I can use any of today's data structures。

 and heck if we really noodled on this， I bet we could come up with yet other data structures still So an abstract data type really just offers you functionality without prescribing how it's implemented under the hood and a dictionary allows you to look up via keys corresponding values。

 Well， what else are there in the world。 Well， there's cues， which take different forms in it。

 there are printer cues whereby if a bunch of people are trying to send something to the printer at the same time。

 ideally， those jobs get queued so that the first person's job comes out first。

 the second person's job comes out second， in the real world， if you're lining up at a store。

 maybe to buy some new product ideally， the stories maintaining a queue whereby the first person in line gets to buy the product first。

 and then the second person in the third， So there's an order and not chaos there and there's fairness。

 if you will。 And so a queue if you really think about it is what you would technically call a fiIO data type first in。



![](img/662bcf12ea2e68802be56a49693956ea_160.png)

![](img/662bcf12ea2e68802be56a49693956ea_161.png)

First out， that is to say PIO is a desirable property for a Q。

 If only for fairness is sake because I'm gonna be really annoyed。

 if I go to the store and I'm there first， but they sort of call on the person way at the end of the line or Q。

 that's not really a desirable feature of a Q， I want PIO instead。 if I'm first in。

 I want to be first out。 So in the world of Qs2， there are typically operations。

 and we can use the terms of art here to Nq means to add something to a Q Dq means to remove something from the Q。

 But the way you Nq is important。 when you N queue something， it goes at the end of the Q。

 And when you D queue something， you remove it from the front of the Q there by maintaining that fiIO property。

 Now， how can you implement a Q and a computer's memory。 Well， honestly。

 I probably could just use an array and plop the first person or value here and then here and then here and then here and I just need to make sure that with my corresponding Dq algorithm。

 I remove this value first。 then this one， then this one。



![](img/662bcf12ea2e68802be56a49693956ea_163.png)

![](img/662bcf12ea2e68802be56a49693956ea_164.png)

![](img/662bcf12ea2e68802be56a49693956ea_165.png)

Maintaining first in， first out order。 Now， with an array， I'm going to have a fixed size queue。

 which might be the case， even in the real world。 Like maybe only so many people can get into a club at the same at a given time。

 So there's a fixed length queue。 And that doesn't work。嗯。



![](img/662bcf12ea2e68802be56a49693956ea_167.png)

Now， I could use an array to implement Nqueuing and dequeuing。

 but that is gonna cap the total number of people or numbers or names that can be in the data structure at once。

 So maybe I don't want to use an array。 Why I could use a linked list that's gonna give me a lot more dynamism。

 but it's not gonna make it easy to search for things。

 but maybe I don't really need to search Indeed that typically is not among the functions that are provided by a queue。

 So it really kind of depends what properties I want。 Arrays might work。 Link list might work。

 Don't think I need anything fancier than that， But there's other types of data structures in the world。

 What if I instead want。Ooh， I lost the slide， sorry。Now， there's other data types in the world。

 In fact， stacks is another common paradigm where a stack is typically a data type that allows you to store things in actually。

 sorry， let me fix this。Now， there's other data types in the world， namely stacks。Nope。

 do they again。Now， there's an alternative to a queue that might be desirable in some cases。

 namely a stack。 for instance， if you're in the habit of stacking your clothes at home where you take something out of the washing machine or dryer and you put。

 let's say。Let me just think。Now there's other data types， in fact。

 stacks are perhaps an alluring alternative to queuees with a different sort of property， in fact。

 if you want to mean sorry。😡，Messed up my transition。Stacks。Now， an alternative to cues are stacks。

 which you might see in a cafeteria， For instance， anytime there's a stack of trays。

 it's not a first in， first out kind of property because that would mean well。

 if they stack the trays from the bottom up just by nature of how gravity works。

 first in would be the bottom one and first out would mean like somehow pulling out the bottom stack。

😡，I messed up。One last time。Getting tired。Now， an alternative to cues are stacks which offer a different sort of property。

 and you see stacks in the real world， maybe in a cafeteria where there might be a stack of trays whereby you typically take from the top。

 but that would not be a queue。 Why well， a queue gives you fiIfo which is first in first out and the first tray in。

 presumably by way of gravity and how it works would be at the bottom So first out would mean sort of taking somehow the bottommost tray from the stack of trays。

 that's not than a queue similarly in the kitchen。 if you've got a stack of plates on the shelf。

 you're probably not in the habit of taking first in first out。

 that is the bottommost plate that you put in first。

 So cues don't really make sense for those purposes。

 those are really better described as stacks both literally and figuratively because stacks in the way weve described them offer a different property。

 Lifo last in first out。 And indeed， if you wash a whole bunch of plates， stack them， stack them。

 stack them on top of each other， the last one。

![](img/662bcf12ea2e68802be56a49693956ea_169.png)

![](img/662bcf12ea2e68802be56a49693956ea_170.png)

![](img/662bcf12ea2e68802be56a49693956ea_171.png)

In is probably going be the first one out by nature of having pulled it from the top。

 same with all those trays。 The last one in on the top is probably going be the first one out。 Now。

 that's a desirable physical property。 And there's a necessary physical property。

 in a lot of cases in the real world， Maybe not a desirable property in the computing world。 In fact。

 your printer would be a little obnoxious if it maintained a stack instead of a queue of jobs。

 because it would mean whoever sent their job to the printer most recently would get their print out first。

 And that just doesn't really feel like an equitable outcome there。 But there are there are。



![](img/662bcf12ea2e68802be56a49693956ea_173.png)

啊。But there are use cases for stacks， including in computing。

 but at a lower level that we'll perhaps see before long， but in terms of some terms of art。

 for stacks， push is the term of art that describes adding something to the stack。

 even though you're probably not in the habit of pushing your plates or your trays down。

 popping by contrast is the process of removing something from the stack。

 which is generally at least physically going to be from the top Now， to make these more clear。

 will turn to a friend of our Shannon Devval who kindly painted the picture of stacks and cues coming to life in ways that will hopefully remind you that as esoteric as many of today's topics might have been in reality。

 they are really representative of some real worldord realities。

 be it that stack of trays or plates be it the line in which you're waiting， In fact。

 I would propose to you that as you emerge from this week's lecture。

 focusing on the real world around you， keep an eye out for data structures or at least data types。

 and you'll see。

![](img/662bcf12ea2e68802be56a49693956ea_175.png)

Even if you're not a computer person， a lot of the ideas we're exploring and trying to distill into these first principles are in fact。

 more familiar than you might think， but first， let's take a look at Jack and his stacks and cues。😡。



![](img/662bcf12ea2e68802be56a49693956ea_177.png)

🎼Once upon a time there was a guy named Jack。 when it came to making friends。

 Jack did not have the knack。 So Jack went to talk to the most popular guy he knew He went up to Lou and asked。

 what do I do， Lou saw that his friend was really distressed。 Well， Lou began。

 Just look how you're dressed。 Don't you have any clothes with a different look。 Yes， said Jack。

 I sure do。 come to my house and I'll showed them to you， So they went off the Jacks。

 and Jack showed Lou the box where he kept all his shirts and his pants at his socks。 Lou said。

 I see you have all your clothes in a pile。 Why don't you wear some others once in a while。

 Jack said， well， what I remove clothes and socks， I washed them and put them away in the box。

 Then comes the next morning and up I hop。 I go to the box and get my clothes off the top。

 Lou quickly realized the problem with Jack， He kept clothes， Cds and books in a stack。

 When he reached for something to read or to wear。 He chose the top book or underwear。

 Then when he was done。 He would put it right。😊。

![](img/662bcf12ea2e68802be56a49693956ea_179.png)

![](img/662bcf12ea2e68802be56a49693956ea_180.png)

![](img/662bcf12ea2e68802be56a49693956ea_181.png)

![](img/662bcf12ea2e68802be56a49693956ea_182.png)

![](img/662bcf12ea2e68802be56a49693956ea_183.png)

![](img/662bcf12ea2e68802be56a49693956ea_184.png)

🎼Back back it would go on top of the stack。 I know a solution， said a triumphant Lou。

 You need to learn to start using a cue。 Lou took Jack's clothes and hung them in a closet。

 And when he had emptied the box。 He just asked it。 Then he said now， Jack， at the end of the day。

 put your clothes in a left when you put them away。 Then to morrow morning when you see the sunshine。

 get you clothes from the right from the end of the line。 Don't you see， said Lou。

 it will be so nice， you'll wear everything once before you wear something twice。

 And with everything in cus in his closet and shelf， Jack started to feel quite sure of himself。

 Oh thanks to Lou and his wonderful cue。😊。

![](img/662bcf12ea2e68802be56a49693956ea_186.png)

![](img/662bcf12ea2e68802be56a49693956ea_187.png)

![](img/662bcf12ea2e68802be56a49693956ea_188.png)

![](img/662bcf12ea2e68802be56a49693956ea_189.png)

![](img/662bcf12ea2e68802be56a49693956ea_190.png)

![](img/662bcf12ea2e68802be56a49693956ea_191.png)

![](img/662bcf12ea2e68802be56a49693956ea_192.png)

All right， that's it for today， we'll see you next time。And now to make this more clear。

 let's conclude with a look at Jack and Lou and their stack and Q。😡，And now to make this more。Yep。

And now to make this more clear， let's conclude with a look at Jack and Lou and their stack and Q。😡。

