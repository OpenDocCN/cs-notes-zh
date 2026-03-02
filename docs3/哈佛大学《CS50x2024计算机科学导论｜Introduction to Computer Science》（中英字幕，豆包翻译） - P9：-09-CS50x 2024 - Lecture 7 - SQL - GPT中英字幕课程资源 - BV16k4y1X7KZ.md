# 哈佛大学《CS50x2024计算机科学导论｜Introduction to Computer Science》（中英字幕，豆包翻译） - P9：-09-CS50x 2024 - Lecture 7 - SQL - GPT中英字幕课程资源 - BV16k4y1X7KZ

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_0.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_1.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_2.png)

All right this is CS 50 and this is week 7 on the day before all Hallello Eve today we will introduce yet another language。

 the goal of which is not to introduce another language for languages sake but to really begin to emphasize that when it comes to the world of software programming engineering more generally like there's often different tools for different jobs and if you were to try to use C to solve all of our future problems like would actually be painful is you've already seen how much how much more pleasant it is to solve certain problems with Python but today quite quickly we'll realize that even Python is actually not the most pleasant way to solve a lot of problems。

 especially when it comes to data data at scale and in fact as we transition in the final weeks of CS50 to the world of web programming and if you so choose with your final project mobile programming。

 you'll actually need more tools in your toolkit than C and Python alone in fact today we'll introduce a databasecentric language called SQL or SQL next week we'll explore markup languages like HTML。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_4.png)

And CSS， a bit of jascript as well。 And then we'll synthesize all of this together and to the end of the class as some of you might for your final projects as well。

 But before we do that and talk about data， let's actually start to gather some data。

 So if you could visit this URL here on your phone or laptop or if easier。

 here's a barcode version thereof you can point your camera at this barcode here and it's gonna pull up a relatively short Google form that's just going to ask you a couple of questions so that we can collect some actual live data and actually play around with it initially in Python So if you go to that URL there。

 you'll see a Google form And if you haven't been able to scan it quite forget that's fine just kind look over the shoulder of the person next to you but you or they will see a little something like this So among the questions will be which is your favorite language on the list only thus far as scratch C and Python and below that you'll see another question asking about your favorite problem across the problem sets。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_6.png)

Thus far， each of them is radio buttons， which means you'll be able to select one button for each of those questions。

 and ultimately what's gonna be nice is that if you've never used Google Forms before as an administrator。

 all of that data is actually going to end up being not only in Google Forms but also if you so choose in Google spreadsheets。

 which is an example of course of a spreadsheet software similar in spirit to Apple numbers on Max or Microsoft Excel on different platforms and Google Sheets is going to get allowed us to store all of that data in rows and columns And so since Google made both of these products。

 they integrated one with the other。 So in fact， if I on my laptop here in another window open this up。

 let me flip over， here's the live spreadsheet and we'll see that the very first person who buzzed in really liked Python as did a lot of other people thereafter but hello world was your favorite in Python which is great。

 there's a couple of votes for scratch here if we scroll down there's one holdout for C who really liked credits in this case here and if we scroll down further。

 it looks like Python。In scratch or in there， a few more Cs and so on and so forth。

 So suppose that we want to actually now analyze this data。 Now。

 any of you have used Excel or numbers or Google spreadsheets know that it comes with builtin functions and formulas and we can do all of that。

 But suppose there was a huge amount of data。 or suppose that this data was not coming in via Google sheets。

 your own web application or your own mobile application。

 And it's just ending up in some kind of spreadsheet。 Well。

 wouldn't it be nice if we could actually analyze that kind of data with code。 And in fact， you can。

 And the simplest way to store a bunch of data isn't with anything fancy， In fact。

 but just like a literal text file， something ending in do txt or maybe more commonly do csv。

 In fact， what we'd call a flat file database is literally just code for text file containing all of your data。

 But your data typically has delimiters that separate some values from others。 In fact。

 the most common approach there say is to use indeed comma separated values or cv files。

 And what that means is that in simple。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_8.png)

one， just asking maybe Uniicode， you sort of mimic the idea of rows and columns by using new line characters like backlash N to represent row after row after row。

 that's pretty straightforward to just move the cursor to the next line。

 And because text files aren't graphical。 So there's no notion of like vertical bars that you can put between what you and I think of as columns。

 you literally just use a comma or some other such symbol to separate one value from another。

 So in fact， let me go ahead and do this。 even if you've never done this before。

 turns out in Google sheet and also Excel and numbers， you can export your data。

 not in some proprietary Apple or Microsoft or Google format。

 But in kind of a globally portable format known as dov。 So let me go up to file。

 I will go to download and notice I can export this in a bunch of different formats。

 But the1 I care about for today is going to be dotv on my Mac。

 that's going put it into my download folders。 And what I'm going go ahead here and do in just a moment。

 is let me go ahead and open up VS code。 So in short。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_10.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_11.png)

Downloaded this file。 It gave Google gave it a long default file name。

 I've renamed it's a favorite cv。 Let me go ahead and actually open it now in Vs code here。

 And this now is the exact same data。 If you're still submitting the form。

 I'm afraid you make the cutoff。 So we're not gonna see more data ending up in this file because I've literally downloaded a copy of it。

 but indeed， if I scroll through this， we'll see that it's got some 399 lines of data or technically 398。

 because the very first one is what we call like a header row。

 which just describes what each of these columns means。 Now。

 notice that even though the Google sheets interface actually put all of this data in proper graphical rows and columns。

 you can still see the rows because they're just separate lines。

 and you can kind of see the columns by focusing on like the comma here， the comma here。

 the comma here， and then also the comma here， the comma here， the comma here and so forth。 Now。

 a quick subtlety。 Hello world is sort of a twoword problem name and itself has a comma in it。

 what's to stop me from。Confusing the comma in Ho world from the commas that Google apparently inserted into this file。

😡，Yeah， so automatically， you all did not type this。 we did not type it into the form。

 but Google is smart enough as is Apple and Microsoft。

 when they export Cvs to somehow escape seemingly dangerous characters or characters that could just break things。

 And in this case， a convention in the CV world It just to quote any strings that themselves have comma so that any program you're writing that reads this file doesn't get confused。

 So the only thing that came in automatically from Google is just this timestamp here based on the time of day in our own local time zone that was added automatically。

 So we have three and not just two columns。 So with that said， we have three columns。

 timestamp language and problem， the latter two of which came from all of you。

 let's actually write some code that analyzes this data。

 Let's figure out what the most popular something or other is here。 So I'll close the CSV file。

 let me go ahead and use what seems to be folks favorite language thus far and write a file called favorites do pi for instance。

 and I'm gonna use Python to open that CV file， analyze crunch。

Some numbers and output some statistics， if you will。 So the easiest way to manipulate CV files。

 as you might have gleaned is not to just open the file yourself。 look for commas。

 allocate memory or anything like that in C。 in Python， you can literally just import Cv。

 which is a Python module that gives you Cv related functionality。 in Python。

 there's a bunch of ways to open files。 one way to open a file is like this in Python。

 you can say file equals open similar to F open and C。

 you can specify the name of the file you want to open like favorites do cv。

 And you can explicitly say you want to open the file for reading quote unquote R just like F open。

 strictly speaking in Python read is implied。 So if you omit the second argument， it will still work。

 But for parity with F open， I'll do the same here。 Then you can maybe do something with file。

 And then at the end， you can close the file like this。 So in Python。

 there really is a mapping between F open and F close， but in。😊。

The functions are called open and close for short。 but a more common way。

 a more pythonic way so to speak I。e。 the way people tend to do it in Python is actually to use a keyword that didn't exist in C where you instead say with and you say with open this file name as a specific file name and then indent it inside of that now you can do whatever you want with the file and the implication of using with even though it's not obvious from the keyword itself is that the file will be automatically closed for you later So this is just a minor Python convenience so that you don't have to remember to close the file unless something go wrong。

 it will just close automatically as soon as you're outside of this with block。

 So how do I go about reading a CSV the simplest way is to actually give yourself a variable called maybe reader like if I want to read the CV I'll call my variable reader set that equal to the return value of a function that comes with Python CSV module called reader in lowercase and you just pass in the file name So the first line there on line3 opens the file。

And gives me access to the bytes therein Line 4 now actually uses this library that comes with Python to just go read it for me。

 figure out where the commas are so that it can hand me line after line the data in the file Now the first piece of data in the file。

 though was what what's the first very first row。😡。

So it was that header row with timestamp language problem。

 I actually want to skip that because that's not data。

 That's what we might call metadata that's describing my actual data。

 So one way to deal with this I can literally just say next reader。

 and next even though the semantics here are a little weird。

 it just means no no give me the next line from that reader instead of the first by default。

 And now inside of this with block， I can do something like this for each row in that reader。

 let's do something super simple initially， let's just print out row bracket1 So row bracket1。

 So what's going on here。 Well， the CSv reader in Python is going to return to inside of this loop。

 one row after another。 each of those rows， though has how many columns3 the timestamp。

 the language and the problem And just like in see our lists in Python or0 index。 So 0，1，2。

 So if I'm printing out row bracket1， that's the second or middle column。 So what's this gonna print。

😡，Row after row。Each of the languages that you all replied with。

 So that's all this isn't doing any kind of analytics yet。

 I'm just kind of going through the motions to at least print out some data of interest。

 So let me run this Python， a favorite stop enter。 and it happens super fast。

 but if I scroll back in my terminal window there is all of that raw data。

 So this is to say once you know the function names once you know the keywords。

 It's actually pretty simple in Python to just get up and running with a file and start looking at the data therein。

 but it turns out that it's a little suboptimal to use the reader alone。

 It turns out there's better ways to do this。 and let me make this clear as follows。

 I don't strictly need a variable， but let me actually declare a variable called favorite set it equal to row bracket1。

 and then print out that favorite value。 This is not doing anything new。

 it's just declaring an additional variable， but I want to highlight the fact that I'm just kind of trusting that row bracket1 is the problem or is the language I care about is language is language but suppose one of you。

😡，I go into the Google spreadsheet and like you know anyone might with a spreadsheet。

 you might start moving things around and you might swap some of the columns left and right。

 you might delete one of the columns， add something else。 In short。

 spreadsheets are arguably fragile and that it's pretty easy in the Gui the graphical user interface to change them around And so my code in Python accordingly is arguably kind of fragile because I'm just hoping that row bracket1 is always the data that I care about So what would be marginally better let's actually use that header row instead and more common arguably in Python is not to use a simple reader but instead what we would call a dictionary reader I'm going change this to dit reader capital D capital are and that's it for the change to line for on line 5 I'm gonna get rid of the next line because I don't want to skip the header now what dit reader does which reader does not is it automatically analyzes that first line in the file figures out what are all of your columns called and thereafter when you iterate over this reader。

😡，Each of your rows now is It's no longer a list of size of size 3， bracket 0， bracket1， bracket 2。

 each row that you get back in this loop on line 5 is now wonderfully a dictionary instead。

 the keys of which are from the header field， timestamp language problem。

 the values of which are whatever each of you typed in again and again。 So how do I change the code。

 I no longer have these numeric indices because row is no longer a list， It's a dictionary。

 So if I literally want the language that you typed in。

 I can use row bracket unquote language treating row is a diict not as a list anymore。

 Now this is again more robust because if you move the columns around on me。

 code is still going work at least so long as you don't rename the columns at the very top。

 So that's still one assumption I'm making。 All right， well， beyond them。

 What could I actually do here。 Well， just to be clear， I don't strictly speaking。

 need this variable。 So no need to highlight this again。 So let me。

Simplify the code a little bit and get rid of this variable and instead just print out the language in that row as a quick check。

 let me rerun Python of favorites dot pi and it seems to still work even though there's a lot of output we're not gonna to check all 399 lines but it looks like it printed out all of those popular languages Well。

 what more can we actually do Well let's actually now start to crunch some numbers and figure out how many people like scratch。

 how many people like C， how many people like Python like let's start to analyze this So maybe the most pedantic way to do this in Python would be to kind of just create some variables and do all of the counting myself。

 So let me actually go ahead and do this。 let me delete this code for now and after opening the reader。

 let me create a variable called scratch and set it equal to0。

 a variable called C set it equal to zero a variable called Python set it equal to0 just so that I have three counters similar to what we did in week zero week1。

 anytime we count it anything。 honestly this looks a little stupid and it's not wrong。😡，In fact。

 this is how you would do it in Python but Python also has some clever syntax if you want to be really cool。

 you could do scratch comma C comma Python equals 0，0。

0 and do all three at once if you like that So it tightens up the code a little bit even though the effect is ultimately the same Now let's go ahead and iterate over this file row by row by row and if we see scratch increment the scratch counter if we see C increment the C counter if we see Python increment the Python counter instead so how do I do this well I could do something like four each row in the reader just like before。

 let me go ahead and get that favorite variable。😡，And set it equal to the language in that dictionary that just came back as part of this iteration and now I can do something like this。

 If favorite equals equals scratch， then with my indentation。

 I can do scratch plus equals1 L if favorite equals equals C。

 I can go ahead and increment C plus equals one L， and I don't think I want else just to be safe。

 even though we only saw three options， I think just to be super safe L if favorite equals equals python。

 then let's go ahead and increment Python。 The one thing we can't do that we could do and C is the plus plus trick So plus equals is as close as we can get。

 So what have I done inside of this loop， I've just incremented each of those counters by one。

 if I see scratch or C or Python again and again。 All right outside of the loop and outside of the width block because once I'm done reading all of the rows。

 I might as well let the width clauses close the file automatically， let's just go ahead and。

Print out some values。 So I'm going to go ahead and print out scratch colon and then inside of there。

 let's print out whatever the value of that variable is。

 Let's then go ahead and print out C colon and then whatever the value of the C variable is。

 And then lastly， let's print out Python colon and whatever the value is。

 And now I made a three typos here。 This is not going to print the values What do I need to do。😡。

Sorry。Yeah， I'm missing the F in front of each of these strings so that I actually get formatted and that is to say the variables get interpolated inside of the curly braces like we saw last week。

 Allright， so honestly， that's kind of a decent amount of code。

 like 18 or so lines of code just to count the number of responses。 But let's see if I got it right。

 Let me open my terminal and run Python a favorites do pi。

 And now I see by an overwhelming amount folks like Python followed by C followed by scratch in that order。

 But that was a decent amount of code have to write And it turns out there's actually better ways of doing this。

 more pythonic ways， more programmatic ways of doing this。

 And if we think back to one of our universal data structures think back to how we preach last week and the week before the value of these dictionaries more generally like the CSv modules clearly a fan of them。

 because that's what di reader is giving us dictionary after dictionary after dictionary。

 And this was the general idea of a dictionary。 It associates keys with values。

 much like you might in a two column table on a chalkboard。😊。

Or the like Well this is kind of what I need right Like if I want to keep track of how many people said scratch and C and Python。

 you know， if I had a piece of chalk， I could just kind of write scratch and C and python is three keys and then with my chalk and maybe an eraser。

 Keep track of the values。 they all started zero， then I add one add two add3 or maybe on a chalkboard I actually use hash marks。

 but like a dictionary is like kind of the perfect data structure for just associating something like scratch C Python with something else。

 Keys with values respectively。 So this is gonna look a little weirder。

 but it's going to be pretty conventional to do something like this instead。

 let me go back into Vs code I'll close my terminal window and let me go ahead and actually delete a lot of this because I can simplify this further Let me go ahead and now give myself maybe a variable just generically called counts and set that equal to an empty dictionary and you can actually do this in a couple of ways。

 you can literally write out。😊，With nothing in parentheses。

 which will give you an empty dictionary like the picture on the board。

 but a little more conventional is to just use tea keystrokes and use two curly braces with nothing inside。

 that gives me an empty dictionary like this picture here。

 Now my loop is gonna be the same I'm going do for each row in the reader I'm gonna go ahead and grab the favorite language for this person。

 So favorite equals row quote unquote language。 But now I'm going do something a little different。

 There's two scenarios here。 Either I have seen this language before and I want to increment it by one or if I've never seen this language before because like the loop just started。

 what should I initialize the count for this language too。So one。

 because I've only seen it once exactly。 So now let me go ahead and do exactly that。

 If this current favorite that I am seeing in the row is already in the counts dictionary and in Python。

 this is literally how you ask that question if favorite in counts that will check。

 is there a key with this name， Sc C or python。 If so。

 go into that location in the counts dictionary index into it at the favorite location because favorite is a string。

 It's either quote unquote Sc C or python and just increment it by one like this else as you noted。

 if it's not there implicitly then counts bracket favorite should probably be set equal not to0 because we're literally are seeing it in the current row。

 let's initialize it to one。 And thereafter， if we see it again。

 it's gonna be plus equals1 plus equals1 plus equals1。

 So now outside of that loop outside of the width block， let me do this for each favorite。😊。

In those counts and this too in Python is a trick， if you want to iterate over all of the keys in a dictionary。

 that is if you want to iterate over the lefthand column of all of these keys。

 you literally can say for something in that dictionary， so for favorite in counts。

 this is giving me a variable called favorite and updating it automatically top to bottom in that dictionary。

 let's go ahead and print out in F string that's going to say whatever the name of that language is。

 colon and whatever the value of that language is in their dictionary。😡，So again， logically。

 the only thing that's new is this。 I'm now using one dictionary instead of three variables to keep track of three things like updating this chalkboard with three different things。

 Sc C Python and the last thing I'm doing which is a little different is once I have that dictionary whether there's three languages or maybe tomorrow they'll be fourth because we're going introduce SQL today。

 Well， this will iterate over all of those keys and print out the values All right。

 so if I didn't do anything wrong if I do Python of favorites do pi and hit enter， there we have it。

 and it happens to be in a different order this time。 that's because we saw Python first。

 we then saw scratch and eventually we saw C， but if we wanted to sort these differently。

 we actually could with some different code But in short， what if we done。

 we've created this kind of structure in memory with three keys。

 Python C and scratch because each time we encounter such a language from you all we either set our counter to one or increment it by one instead。

😡，Any questions on this code or this general idea of using dictionaries as kind of like a little cheat sheet for doing some work。

 some math in this way， super common。Paradm。Al right， well， let me tweak this a little bit。

 right now in my output， we're seeing Python scratch and C。 maybe for the sake of discussion。

 suppose we want to sort this by key。 We can actually do that。 Let me close my terminal temporarily。

 and it turns out in Python， there's a bunch of ways to do this。

 But the simplest way to sort a dictionary by key is literally to use a function called sorted that comes with Python that just does it for you。

 And even if you pass it a dictionary。 It will sort that dictionary by the lefthand column so you can iterate it over alphabetically instead。

 So if I go back now to VS code。 if I open my terminal window and I rerun Python on favorite stop high now that I've added the sorted call。

 we should now see just because it sorted alphabetically instead。😡，Now， that's not that useful。

 especially if we had lots of languages。 you probably don't care about it being alphabetized as much as you care about it being ranked。

 by which is the most popular， which is the least popular。 And for that。

 there's a bunch of ways to do this in Python， And I think the simplest way to sort by value。

 the right hand column instead of the lefthand column is probably to make this change instead。

 Let me close my terminal temporarily， Let me still use the sorted function， which by default。

 sorts by key， but let's change it to be as follows。

 Let's change it to sort by a function called counts do get， which is a little weird。

 but this comes back to yes， last week's brief discussion of object oriented programming or O。

 remember in Python that almost everything is like an object of some sort。 An int is an object。

 in dictionary is an object。 a string is an object。

 which is to say that not only do these things have values like quote unquote hello world or 50。

 these variables， these objects can also have functions。ilt intoto them Aka methods。

 So it turns out that because counts is a dictionary because I made it so that counts dictionary like any dictionary in Python comes with a function called get。

 And if you just tell the sorted function to use that built in method。 it will actually。

 for every key。 get its value， Get its value， get its value and sort effectively by the right hand column and of the left。

 Now we'll see down the line， perhaps more sophisticated ways of using this。 But for now。

 this just overrides the default behavior and sorts the dictionary not by key， but by value instead。

 All right， so now watch this。 if I run Python。 a favorite stop pi once more。 previously。

 it was in the order in which the languages appeared first in the Cv file。

 then it was sorted alphabetically。 now it should be sorted by value。 And indeed。

 scratches the least with 40， C is the next with some of the8 Python is the biggest with2 under 80。

 That's not much of a top 10 or a top3 list。 let's actually reverse it。 and the easiest way。

Python to do that is to pass a third argument into sorted and you would know this by just reading the documentation。

 you can literally say reverse equals true capital T。

 And now if I rerun this one last time Python of favorite stop I I'll see the same values but with the whole thing reversed in order long story short。

 even though this might feel like a slog like adding this and looking up this so much easier than like in C where you would have had to like figure how does bubble sort work。

 let me implement bubble sort selection sort， any of those sorting algorithms or use some other library in Python。

 you just get a lot more for free so to speak it's just built in once you get comfy with the documentation And to be clear。

 this is an argument as is this， as is this but in Python we have not only positional arguments which are based on what position they are in left to right。

 just like C， you also have these named parameters whereby they have explicit names that you can use yourself to make clear that you're using this one but not this other one。

More parameters in Python can be optional than N C。😡，All right。

 Any questions about that technique yet。 And if you're feeling like this is starting to take the fun out of Python。

 like， that's actually kind of the point of doing this like the hard way。All right。

 well let's do it one other way that's marginally better。 It turns out in Python。

 there really is this reach ecosystem of libraries。

 the code that comes with the language itself or even third parties and coming with the language is another module called the collections module or package here whereby if I use from collections I can import something called counter capital C。

 and it turns out if this felt a little bit painful to create a dictionary yourself initialize it maybe to zero or one like this turns out you have the same problem that people before you have had and so there's another way to do this。

 you can create a variable called counts set it equal to counter capital C open per enclosed print and this is a different type of object。

 it's a different type of object in Python that has counting capabilities built in。

 and so if I actually want to use this counter instead I can do this for each row in the reader let's go ahead and grab the favorite language from that row just like before and without doing any of that。

😡，Headache of like if， L if or any of this， you can literally just index into that counter using favorite。

 quote unquote， scratch or C or Python。And increment it by one。

 what the counter class is going do for you。 So to speak。

 another example of object oriented programming and counts is now an object thereof what this whole feature of counter is gonna do for you is it's gonna automatically initialize everything to0。

 even if you've never seen it before。 And then you can just blindly start incrementing。 So in short。

 there's just more pleasant ways。 Sometimes to do something in Python as well。 Allright。

 how about lastly， let's make things maybe oh， actually， let's do this。

 we can even simplify the sorting here。 Let me actually take this one step further。

 instead of manually figuring out how to sort this。 I'm gonna do this for each。😊，Favorite。

And the count thereof in the counts variables， most common functions return value go ahead and print out this as well。

 So in short， again， a bit new syntax， but what's going on here。

 well it turns out that this counts class and sorry this counter class and in turn this counts variable comes with a function built in that you would only know from the documentation。

 it's literally called most underscore common and what it returns to you when you call it is a pair of key value。

 key value。 And so this two is a trick in python that we did not have in C。

 if you want to iterate over something but grab two variables at a time on each iteration like this。

 you separate them by commas and can get favorite count favorite count。

 favorite count So if I run this now Python of favorite stop pi this two just works。

 and it's getting a little simpler， a little tighter than before then if we had actually done it all manually。

😡，Lastly， here's a code that's the shortest version thereof we down to like 1415 lines。

 if I wanted to change this to analyze the most popular problem thus far in the class。😡。

How do I go about changing the code to print out top to bottom the most popular problem or problems？

😡，What line should change， yeah。So yeah， line 10， because I've written this in kind of a general purpose way in using dictionaries with keys。

 it suffices to change language to quote unquote problem because that was the third column from the CSv。

 And so now if you're curious， let's actually make my terminal window a bit bigger Python of favorite stop I enter tragically we peeked early with hello world is the most popular problem thus far followed by filter。

 then scratch peaked even earlier， Mario DNA and so forth than a bunch of others thereafter。

 So based on this sample size， here's the ranking of the problems thus far So we got it hello world problems in the weeks to come Allright so now that we've done that in that way。

 let's just make this program slightly interactive and see how we can really take a fundamentally different approach。

 I'm going go into VS code。 I'm gonna keep everything the same except that at the bottom。

 I'm gonna get rid of this loop because I don't want to more print out everything want。😊。

Look up specific counts。 like how popular was this problem。 How popular was this other problem。

 And what I'm gonna go ahead and do is to create a variable called favorite。

 set it equal to I could use get string in the CSF library， but we saw last week。

 there's no need to for strings。 certainly， let me just use the input function that comes with Python and prompt the human for their favorite problem。

 And then let me go ahead and print out for instance。

 an F string containing whatever their favorite is Col and whatever the count count is thereof of that favorite close。

 So let me open my terminal window， let me run Python of favorite stop pi enter And if I type in hello comma world looks like 65 people indeed like that one。

 If I run Python a favorite stop pi again， I type in scratch。 Now we see that one。

 if I type in anything else， I'm gonna get its specific value。

 So this is to say not only can we write Python code to kind of analyze some data。

 pretty tightly versus the manual code we wrote out earlier。

You can also make these programs interactive as well and this is gonna be a super common paradigm right if you go into the world of like consulting analytics。

 data science more generally like among your roles is going to be like to analyze data to ask questions of data get back the answer。

 be asked questions of data， get back the answer honestly life gets pretty tedious even though you've only been programming in Python perhaps for like one week week and a half now。

 when you have to write code to solve all of the world's problems and there's this sort of in programming that programmers tend to avoid writing code as much as they can because ideally you would solve problems with the right tool for the job minimizing the number of lines of code you actually write So how do we actually get to that point well。

 instead of just dealing with CSV files pure text turns out there's an entire world of proper databases not file databases where you store everything in text files but like a database program like a piece of software running on a computer running on a server that's always listening for you。

 it's got a lot of memory it's got a lot。Space and in turn a lot of data。

 and it supports a database specific language that makes it much easier。

 much faster to ask questions of the very same data。

 It's a relational database in the sense too that it's not even necessarily one spreadsheet like one set of rows and columns。

 you can have two sheets，3 sheets，30 sheets across which there might very well be relationships or relations。

 So SQL or SQL is a database specific language stands for structured query language that's a declarative language whereby you're not going to be in the habit with SQL typically of writing loops and conditionals and this kind of thing。

 you're instead going to describe the data that you want to get back。

 You're going to describe the question that you want the answer to。

 and we'll do this using a relatively small grammar。

 That is to say there's not that many keywords in SQL。 It's a pretty small language。

 but it's going to allow us to eliminate dozens of lines of Python code。

 perhaps SQL follows this crud paradigm。 So C R UD。Whi simply means that in a relational database。

 you can really only do four things。 you can create data。

 read data that is like look at it or analyze it somehow， update the data or delete the data。

 So crud for short。 and that really speaks to just how relatively simple the world is even though we'll just scratch the surface of some of its capabilities today and you'll explore more over time。

 specifically in SQL。 there's gonna to be other keywords that map to those four ideas technically you don't just create data in the world of SQL。

 you can also insert data like inserting more rows into a sheet。

 and it's not the word read that people use people say to select data， but they mean to read data。

 which is sort of the opposite of writing or creating data。

 but the U and the D are the same except that there's also a keyword in SQL known as drop which lets you very destructly。

 very dangerously like delete entire database tables as well。

 So how do we do this And what's the connection to our favorites data thus far。

 Well here is the syntax and this language called SQL via which you can。Create a table。

 So the jargon is a little different， but the ideas are exactly the same from the world of spreadsheets。

 What you call a sheet in a spreadsheet。 The database world calls a table。

 It's a table of rows and columns。 But it's the exact same idea。

 You're gonna have discretion over what to call the table， just like you can call a spreadsheets。

 something else。 And you can also specify the types of data that you want to store in your rows and columns。

 And it's gonna to go a little more deeply than just formatting it like in Excel and numbers in Google spreadsheets。

 you can actually control maybe how big the data could be depending on the database you're actually using in Cs 50。

 We're going to use a light version of SQL。 literally a language called an implementation of SQL called SQL light。

 which has really all of the core functionality that you would see in the real world and with larger。

 more scalable systems， but it's going to allow us to focus on a lot of the building blocks and SQL lights is actually really popular on Max PCcs and phones nowadays。

 a lot of the data that games and other applications on your phone might store。😊。

Actually have a file， a binary file with zeros and ones that's in the SQL light format。

 So if you do a mobile app， for instance， for your final project。

 you'll have an opportunity to play with something like this。 Well。

 how do you actually run SQL light 3。 It's just a command built into your code space。

 So this is a program you could install on your own Mac your own PC or the like。

 We'll do everything as we've done before in the cloud and actually use your code space。 And by that。

 I mean， we can just start to play with this data now using SQL instead of Python。 So let me do this。

 let me open up my terminal window here。 and let me go ahead and maximize my terminal window。

 just because we'll focus now on the files here。 recall that I have a file called favorites do cv and that CSv files just text。

 but let me load it into a proper database。 So I can actually use this other language called SQL on it to do this。

 I'm going run SQL light 3， which just means the third version of it。

 And I'm gonna create a new database called favorites do Db。 That's just a convention。 but。😊。

Here comes a database that I'm going to create。 Notice I'm not using the tabbed code editor。

 I'm not using the code command because the code command is generally for text files。

 SQL L 3 is gonna create a binary files， zeros and ones ultimately， when I run that。

 It's going ask me to verify。 Yes， I'm going hit why and then enter。

 And now I'm at the SQL light prompt， which is not the dollar sign。

 It literally says SQL light with an angled bracket。 Now。

 one time only I want to go ahead and load favorites dot Cv into this database。

 So I can actually play around with it using Python but this new language called SQL。

 And the way I'm gonna do this is as follows。 I'm going do dot mode CV enter and that just puts SQL light into Cv mode it has different modes for different file formats。

 I'm going do dot import。 And then I'm gonna specify the file that I want to import。

 which is favorites do Cv。 And then this one's up to me。 What is the name of the table。

 I want to create and table again is essentially synonymous with sheet。

 So I'm gonna call everything the same。 I'm gonna call my。😊，Table favorites as well。

 So what this command is essentially going to do is all of those lines of Python code that open the file。

 read it row by row and do something with it。 This is just built into SQLL。

 It's gonna to load the hold darn Csv into this new favorites do Db file。 And then that's it for now。

 I'm gonna go ahead and literally type dot quit to get out of sQL light。

 I'm back at my dollar sign prompt If I type Ls。 I have not only favorites do csv。

 I also have favorites dot Db now as well。 a brand new file。

 And in that file now is an optimized version of the csv file in that Db file now is a version of the data that's going to lend itself to crud operations。

 creating reading， update and deleting using this new language called SQL。 All right。

 so how do I get into this。 Well， let me clear my terminal window and sort of pretend that I'm doing this now the next day。

 I've already created the database that's a onetime operation once you've got the data。

 Now I'm gonna go ahead and again run SQL light 3。😊，Favorites do db just to open the file again。

 but it's already now all of the data is in there， just as a teaser。😡，Let me go ahead and do this。

 dot schema is a SQL like command that just shows me the schema of this database table。

 and we'll see more about this in a little bit。 But for now。

 this is showing me essentially the SQL command that was automatically run when I imported this database the first time around。

 And for now， just notice that it mentions timestamp。 It mentions language。

 it mention problem very loosely， it calls each of those text。

 So we're not trying very hard to distinguish one type of data from another。 It's all text。

 but notice create table， if not exists favorites。 This is essentially the create table syntax that I alluded to earlier via which you can create a table in a SQL like database。

 But more on that in just a bit here now， is how we can actually get at the data in that database。

 It turns out that we can select one or more columns from a database table using syntax。Like this。

 literallyter the keyword select， then the name of one or more columns that are in that database。

 and then from the specific table that you care about and notice that in capital letters here are all of the SQL specific keyword。

 select and from in particular and in lowercase by convention here are the placeholders for the columns that you or I have created and the tables that you or I have created。

 So if I go back to SQL light here。 let me just clear with control L。

 which will just freshen up the screen here so we can focus on what's new。

 if I want to select everything from the table called favorites。

 Here's what I can do select star from favorites， semicolon and do forgive me semicolons are back for SQL in this case。

 But select star from favorites， uses a syntax， you might not be familiar with star here has nothing to do with pointers。

 Star is a wild card。 It means give me everything no matter what it's called from this particular table when I hit enter what we're going to see is the entire contents of the。

Favorite table that's the result of having imported that CV into this database。 So when I hit enter。

 there is all of that data。 and it's SQL light just to be friendly。

 It's using what we might call ASI art， like just very simple text like hyphens and vertical bars and pluses on the corner to make it look pretty and make it look like it is a proper table。

 But what you're really seeing is the contents of favorites do Db specifically in that table。

 specifically if I only care about languages。 let me try something more specific than star。

 Select language from favorites semicolon。 This is gonna give me just a single column now of all of the favorites that you selected for language specifically。

 This is a little overwhelming to see all 399 or so pieces of data。

 So let me actually trunccate it a little bit。 Let me do select language from favorites limit 10。

 So we're about to see that there's little tricks you can use to sort of tweak the behavior of the language in order to get back more or less data。

 In fact。😊，Turns out there's a bunch of keywords like these built into SQL。

 much like Google spreadsheets。 Apple numbers， Microsoft Excel。

 and certainly Python is a lot of functionality that you just sort of get for free with the language。

 if you want to calculate an average， count the number of things in a file。

 Get the unique or distinct values。 force everything to lowercase， force everything to uppercase。

 get the maximum value， minimum value， much like spreadsheets。 if you're familiar with that world。

 you get all of that functionality in SQL but also more。 So for instance。

 if I go back to my terminal window here。 let me go ahead and select the total number of favorites in this table。

 The total number of rows that you all inputted。 So I could do select star from favorites semicolon。

 And then I could literally like start counting these like 1，2，3 there's clearly a better way。

 And indeed on our list of functions was a count function。

 And so the way I can use that in SQL is like this， select count of star。

 So pass star in is an argument to the count function。 You don't care what columns your count。😊。

Just count them all from favorites semicolon。 And now you're actually gonna get back like a little baby table that has just one row。

 one column inside of which one cell of which has the total actual count。

 And it's 398 because 399 recall included the actual header row from the file。 All right。

 so suppose you want to actually note that this is the exact same thing is counting a specific column because every column has every row has the same number of columns 3。

 we could just say select the count of languages or select the count of problems。

 all of those are gonna give me back the same answer。 It is therefore conventional and SQL。

 If you're just trying to count the number of rows don't even worry about what they're called just do count star to get back everything more simply。

 All， but what if we want to get back the distinct languages。

 And we didn't know a priori that this came from a Google form with three radio buttons。 Well。

 we could do something like this。 We could select the distinct。

Languages from the favorites table enter， and that gives me Python Sc C because distinct is one of the other functions that comes with SQL。

 This is obviously very easily countable with my human eyes。

 But if I wanted to do this more dynamically， I could change this to be count the distinct languages。

 and just like in C just like in Python just like in scratch。

 I can nest these functions and pass the output of one into the input of another。 if I hit enter now。

 I now get three in this case here。😡，Okay， let me pause to see if there's any questions or confusion just yet yeah。

It does sQL light。SQL light 3 is a program， and it's an implementation of the SQL light language。

 which itself is a lightweight version of what the world known as SQL。

 which is a very convoluted way of saying there's lots of humans in the world。

 Not everyone agrees what SQL should be。 Microsoft might disagree with Oracle might disagree with other companies as well。

 So there's a common subset of SQL in the world。 that almost everyone knows and learns and uses。

 but there are also some vendor specific features。 SQL light tries to distill things really into the essence。

 And so that's what you increasingly see on Android on ios on Mac and PCs as well。

 So we use it because it's relatively canonical。 Good question。😊，Alright。

 so let's do a few other things by introducing a few other keywords without trying all of these right now。

 here in this list is a bunch of new keywords that are going to give us even finer control。

 And we saw limit already。 And that sort of just limits the output。

 But you can also have what are called prediccateates。

 like you can you literally use the keyword where to start filtering the data without using an if and an L if and an L if and an L if and so forth。

 You can just in one line express something conditionally， you can order the data。

 And you can even group similar data together。 So what do I mean by this。

 Let me go back to V S code here。😊，And let me play around with a few different queries。

 Let me select maybe the count of rows from favorites， which previously was going to be 398。

 if I just get back all of the rows， but suppose I only want to know how many of you like C。

 I can then say something like where the language in each row equals quote unquote C and the convention here is to use single quotes though SQL light is tolerant of other formats as well。

 if I hit enter here， I'll see indeed， as we saw with Python。

 the 78 number that honestly took what 13，1415 lines of code。

 now I've distilled that kind of query into a single line of SQL code instead by using this built-in functionality。

 Supp I really want to get specific and how many of you really liked hello world in C as your favorite。

 Well， I could change this query and just like your dollar sign prompt your shell。

 you can go up and down in your history and SQL light to save keystrokes， you can use Boolean。😡。

Logic and I can say language equal C and maybe problem equals quote unquote hello world。

 And the number of you that like that problem was 7。 So really， really early on。

 like hello world in C。 Now notice a couple of key differences。 One。

 I'm using and and not ampersand Ampersand like in C。 I'm using single equal signs。

 So SQL behaves like scratch does， which is not like Python or C why different people have implemented different languages differently equals equals equality in the world of SQL for comparing things left and right。

 All right， things are now going to get a little more interesting。

 but the whole goal of all of that Python code was to sort of analyze the ranking of languages and popularity thereof。

 turns out in SQL， once you have the vocabulary。 it's pretty easy to do something like that。

 I'm going do this。 I'm going select all of the languages in the table。😊。

But I'm also going to select the count thereof。And then I'm going to do that from the favorites table。

 but I'm going group by language because I claimed a moment ago that group by is another one of our key phrases in SQL that's going let us group data and what this effectively means is that if you've got this table with a lot of duplicate languages again and again and again。

 you can group by that column and essentially smooush all of the python rows together。

 all of the scratch rows together， all of the C rows together。

 but figure out how many of those rows just got smooushed together effectively doing all of that dictionary legwork or the counter legwork that I did in 1315 lines of Python code so if I had enter here this now is the motivation for what we're now starting to do I have distilled into a single line of code in a language called SQL what indeed took me more than a dozen lines of Python code just to get back an answer and I can do the same thing with problem I can just change language here。

 for instance， to problem instead。😡，But per this list， I can not only group things， I can order them。

 So if you actually want to get like a top 10 or a top three list。 well。

 let's just change this query slightly before the semicolon， let me order by the count of those rows。

 semicolon。 And now what I get is from smallest to largest 40，7828 280 if you want to flip that。

 that's fine。 by default， order by uses ascending order abbreviated ASc if you want to do descendending order。

 DC， you can do that as well。 And now we have a top three list from largest to smallest。 Now。

 honestly， this is a bit of a mouthful to use count star over here， count star over here。

 there's a niceity in SQL 2 where you can create little aliases of sorts。

 So if I use the same query again。😡，Let me scroll over to the left。

 I can actually use the keyword as here and I can rename this weird looking column countstar to anything I want like I can rename it to n and then at the end of this query I can order by n essentially creating a synonym if you will for one versus the other so if I hit enter now same exact thing but my little baby table that came back not a technical term has two columns one of which is more simply called n now instead of count star just makes it minorly more convenient in your actual SQL code to reference things that might actually be a little annoying to type Lastly suppose we want to get like a top one list and we just want the most popular language honestly I can just do limit one enter that gives me just this tiny little table。

 a temporary table really with one row and honestly if I don't even care about what the language is I can omit that entirely just see how many people really like the most popular language280 in this case。

 but of course it's more interesting。😡，To see what it actually is。 So in short。

 just by turning these knobs like syntactically， it's relatively easy to start getting at more and more data and more answers there。

 too。Questions。On this thus far。Any questions No， okay， well suppose that this week， for instance。

 one of our new problems is going to be called 50 Vi。

 and it's going to allow you to explore the world of SQL in the context of a place called 50 will。

 suppose that that suddenly becomes your favorite problem。 Well。

 how can we go about adding more data to a database。

 Well we've seen create table for creating the table。

 we've seen select for selecting data therefrom turns out there's also an insert into command that you can use to insert new data into a table。

 Now I did this sort of in bulk by just importing that whole CSv file and SQL light 3 did it all for me automatically。

 but in the real world， if not if you don't have a captive audience。

 every one of whom is submitting the form at the same time。

 but maybe it's an application that's running 247。 you're gonna get more in more data over time。

 just like Google itself。 So if you write code like this， you can insert one row at a time。

 one row at a time and actually change the data in your table。 So just as a check。

 let me do select star from favor。It's enter just to see all of the data。

 And the last data we got was at 1，41 PM and 21 seconds。

 Suppose now I've decided I want to insert one new row。 I can do this， insert。😡，Into favorites。

 And then I have to specify what columns do I want to insert into。

 I'm going insert a new language column and a new problem column timestamp I could。

 I don't really want to look up the time。 So I'm going to leave that one blank。

 and I'm going to put in values as follows for this。 SQL for the language。

 which wasn't even an option on the form earlier and 50 Vi for the name of the problem。 semicolon。

 So there's a bit of dichotomy here in the first set of parentheses。

 you specify a comma separated list of the columns that you want to put data into in the second set of parentheses。

 you actually specify the values that you want to put into those columns。

 So when I hit enter nothing seems to happen， which in general is a good thing at my terminal。

 but if I now rerun select star from favorites， we will seevoila， a brand new row。

 we don't know what time or date it was inputed at。 In fact， we see an old friend No。

 which indicates the absence of a value。 but we do indeed see that SQL in 50ville is actually。

Now in there。 so in the world of SQL， null has nothing to do with pointers or addresses the world of SQLs just using the same word to represent the same idea that there's no data here。

 but it has nothing to do with like actual memory addresses in this case。

 But suppose that you don't want to do that like no， no no。

 let's just delete that 50 bill hasn't even been released yet nor in fact we've even finish talking about SQL。

 how do we delete data from a database table Well there's a delete from commands。

 Let me go back to Vs code here。 let me go ahead and clear my terminal just to keep things clean。

 let me go ahead and delete from favorites and let me not hit enter here after a semico and this is one of the most destructive things you can do as a database administrator if you Google around there are horror stories of interns in the real world executing commands like this that there are companies。

 this will delete everything from favorites。 So if you ever do this remember we told you not to today But if we add a where clause here only delete rows where。

The timestamp column is null。 This is more reasonable。 And frankly。

 any companies you work for should also have backups of their database。

 so we shouldn't even be reading about these horror stories， but such as the real world。

 So this is going to delete any row from the favorites table where timestamp capital T because that's how Google did it is null。

 I go ahead and hit enter nothing seems to happen， But if I do select star from favorite semicolon that now row is again gone。

 So you can use these prediccateates， these where conditions coupled with select。

 coupled with delete and other operations as well。 What if I actually want to make a change。

 So if you want to update existing data like this。 Well， we could do this。 I could update this table。

 I could set one column equal to this value where some condition is true。 So how might this work。

 Well， let me boldly claim that a lot of you are really going like 50ville in the world of SQL。

 So all of these favorites are sort of pass now， So let's do this。

Let me go ahead and update the favorites table， setting the language column equal to SQL quote unquote。

 and with a comma， let me go ahead and also update the problem column to be equal to quote unquote50 Vi。

 I'm not gonna have any kind of where here， which means like this is just gonna do its thing on all of the on all of the rows。

 So if I had enter。 nothing seems to have happened。 But if I now do select star from favorites。

 everyone's favorite is literally that problem。 So this too is destructive。

 Like unlike the real digital world。 There's no like control Z or undo that。

 like you better have made a backup of your database。 otherwise， that's not a good thing。

 in this case， I do have the CSV file。 So I could just delete my favorites do D file。

 I could reimport the data。 So I haven't really lost anything of importance。

 but you could in the case of the real world and any data you're actually working on。

 So just to make the point， let me go ahead and delete from favorite semicolon enter。

 let me reselect， there's no data there anymore。In fact， if I do select count star from favorites。

 we'll see as much that the answer is， in fact，0 because everything has now been deleted。😡。

Any questions then on that code there？No， all right。 So if not too scared yet。

 let's go ahead and take our 10 minute break。 Now。 Halloween candy is served。

 and we'll be back in 10。All right， so we are back and before we dive back into SQL and some real world data。

 it turns out unbeknowst to me we've had a Halloween costume contest。

 so it's now time to announce the winners of this year's CS50 costume contest if our two winners would like to come on up。

😡，Who I'm told during break， dressed up as me。Come on over， would you like to introduce yourselves？

Hi everyone， I'm David。 I am living in Matthews as a first year。

 I'm planning on studying Gov and computer science。😊，Hi everyone， I'm David。

 I'm a second year in math， and I'm planning on just studying computer science。 Well Thank you have。

😊，Oreios for you。Thank you both so much。 Did anyone else stress like this， We have two more Oreos。

 if you'd like。😊，Intentionally。Oh that's pretty good， Okay， yes， we have one more winner。

 come on down。Thank you。This is intentional oh okay。Hello， my name is David。 I'm from Canada。

 and I'm my first year。 I'm not sure what I'm going to study。 Okay， Wel as well。 Thank you。

 All right。😊，So up until now we've played around with the data that you all gave us。

 which was based very simply on like your favorite language and your favorite problems。

 but it turns out there's a lot of like real world data in indeed the real world。

 some of which is quite voluminous and indeed there can be not just dozens or hundreds。

 but thousands， hundreds of thousands， even millions of rows in the biggest of databases and so what we thought we do in the latter part of today is really actually get our hands dirty with a realworld data set from the Internet movie database otherwise known as IMDB and in fact if you go to IMDB co you'll be able to answer via their web interface。

 some of the very questions will do today using SQL alone。

 but what you'll find ultimately is that what websites like imMDB co or their mobile app versions thereof are probably doing is yes giving you a nice pretty graphical interface to type queries。

 but underneath the hood， they are passing your input into SQL queries or similar queries that they've formed most of they're just way。

😡，For placeholders like the keywords that you're actually searching for。

 So let's go ahead and experiment， maybe with just some real worldl data initially before we consider how to actually store it at scale。

 So let me open up just for the sake of discussion an actual empty spreadsheet just so I have some Rose and columns to play with。

 and let me propose that we want to model TV shows from the real world。

 how could we go about doing this Well maybe I could start in this first column a so to speak。

 and I could create a title column and then maybe a column for the star of that show and a very popular show of course is the office So I might put this into this second cell in that first column and under star。

 I could put someone like Steve Carll。 but of course he wasn'tt the only star of the show There are others as well。

 And so if I want to put in someone like Ra Wilson。

 maybe I need a second star column So Ra Wilson but even as early as the first season there was also another star and the credits John Kinski So he was a star Jenna Fisher。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_13.png)

Was get top creditted in the first season。 So Jenna Fisher and then BJ Novak。

 Harvard alum was also in the first seasons of opening credits as well。 So we've got all 1，2，3，4。

5 of these folks planet miss Velony one's name， but here's the beginnings of a real world data set and we could imagine doing this for like everyone's favorite shows adding more and more rows。

 but let's consider as we often do not just the correctness of this implementation。

 but the design like it's pretty straightforward like it's very readable。

 So I think it's good in that sense， but if you start to nitpick what's poorly designed even in the world of spreadsheets about what I've done here assuming that the next row is another show。

 The next row is another show and so forth。What's bad about this， yeah？Yeah。

 so eachrow is gonna have a different number of columns。

 And even I couldn't make up my mind from the get go。 like do I have just one star column or two。

 or maybe now I'm up to five for even bigger shows And later in the office when more people got top billing。

 we're gonna need more than five columns for stars。 So that's fine。

 Like we can clearly scroll to the right and just keep adding more columns。

 but there should be something about that design that like Rusia the wrong way。

 Like something feels a little off if some rows have this many columns。

 others have this many the data would be very jagged along the right hand side。

 it would be very sparse， which would be another way to describe it， there's probably a better way。

 So maybe I should kind of flip the data around and maybe a better approach here would be to just have one column for stars。

 So let me actually let me do this。 Let me just move like Ray Wilson over here and John Kinski over here and Jenna Fisher over here and BJ Novak over here as well。

 I'll get rid of all of these superfluous identically named columns。 And now this is sort of better。

Because now I can have any number of stars in the vertical。

 although it's a little weird to leave this blank， so maybe I should kind of copy paste here。

 so in some sense this is better in that now I only have one title column。

 one star column and I can just keep adding row， row， row， row for each show in its stars。

 but what's now poorly designed about this。😡，Yeah。Yeah I'm repeating the title and in general。

 copy paste， repeating yourself and code has generally been a bad thing。

 It's generally gotten us in trouble if I make a change or maybe a typographical error somewhere。

 maybe it propagates elsewhere。 and if nothing else， it's just a lot of wasted space。

 Like if this is actually going be stored in a database in a CV file。

 Why are you duplicating the same string again and again and again for large TV shows。

 that's just wasteful， It just doesn't seem wise。 So how can we eliminate that redundancy。 Well。

 unfortunately， in the world of spreadsheets， things kind of now escalate quickly to be just kind of annoying。

 but let me do it nonetheless with just a small bit of data， let me propose that we do this instead。

 let me create not one sheet， but maybe multiple sheets and assume that there's some kind of relationship or relation across these sheets。

 So just to be pedantic， let me call this sheet， not the default sheet one。

 but let's call this shows And in this sheet， I'm going have a title column for every show And I think I'm gonna be proactive here。

 I'm gonna start giving every show a unique。D number， much like Harvard affiliates have Harvard Ids。

 Yale affiliates have Yale Id numbers and so forth。

 Let's go ahead and give each show its own unique identifier。 for reasons we'll soon see。

 So for the office， let me just for consistency with the actual Internet movie database。

 I'm gonna give it a unique number of 3，8，6，6，7，6。 The specifics don't really matter。

 but that happens to be what people in the real world actually do。 but that's it for TV shows。

 even though I could imagine there being many more in this sheet。

 let me create another sheet now here， and I'll call it people in the people sheet。

 let me keep track of all of those TV stars。 So one will be one column will be named another will be also called Id here。

 but it's gonna be a person I， not a show Id。 And here we have， for instance， Steve Krell。

 We have Ray Wilson。 We have John Kinski。 We have Jenna Fisher。 And we have BJ Novak。

 And this is gonna be a little tedious， but just to be consistent with。😊。

turnsur out that according to IMDB， Steve Kele's unique number in the world is 13，6，7，9，7 Ras is 1，9。

3，3，9，8，8 Johns is 102，4，6，7，7 Jennas as 2，7，8，9，7，9。 and lastly BJ Nox is 1，1，4，5，9，8，3。

 so now we have the same people， but they each have a unique I number。 Lastly。

 let's associate those shows with those people in a way that avoids the two problems we identified earlier。

 which was having a variable number of columns in one case。 versus redundancy in the second case。

 let's really tighten things up。 So nothing is in duplicate that doesn't actually need to be。

 So I'm gonna create a third。Sheet here。 and I'll call it stars like the TV stars for these shows。

 And what I'm gonna do is have only two columns， a show Id and a person Id。

 I could write these in different ways， but it's conventional in the database world to use snake case so to speak where everything is everything is lowercase with underscores instead of spaces。

 and for show I， well， we're only mocking up one show for now， but I'm going go ahead and say 3，8，6。

6，7，6， which is the office I claimed And now I'm going go ahead and have all of those person Is。

 And this time it's okay to copy paste if only to save time。

 So I'm going grab all of these five stars Is paste them there。

 And I am going to indulge by duplicating the show Id even though we didn't like that earlier。

 Now this indeed is kind of escalated quickly because none of these sheets are very useful to look at to the human eye because none of them has like the complete picture we have shows in one people in another。

 and then like this cryptic mapping of numbers in the third But I propose that this is sort of the。😊。

Right way to implement data if your goal is to have a canonical source of truth for every show in every person。

 that is to say you only say the show's name once in one place。

 you only show you only write the TV starss names once in one place and you associate them you relate one with the other by way of this third sheet here So if you've not seen it already notice that if the office has this unique I 3。

8，6，6，7，6 Not in the stars table， that same value appears multiple times but what this third sheet is doing is associating that same show I with one2。

3，45 different people。 Now I can see that it's similar in spirit to what we already indicted as bad design a moment ago。

 the office， the office， the office， the office， but think about our world of C in the world of C and really computers in general。

 data takes up finite amount of space typically like an integer is 4 bys 32 Bs。 So even though yes。

 I'm duplicating this value。It's just the same four bys，4 bys，4 bys，4 bys， it's not T H， E， space， O。

 F，F， I， C， E， null character。 It's not the same 11 bytes again and again。

 It's just a number and numbers tend to be much more efficient。

 that computers can crunch numbers much more quickly。

 Duplicating numbers is in general allowed or smiled upon duplicating strings will get you into trouble。

😡，So with that said， is this a useful spreadsheet now。

 like would you want to be handed this in your job and ask questions like， hey。

 who stars in the office， like you can answer it， but you have to look up one sheet， then another。

 then a third， or you need to use like v lookup or special functions in Excel or Google sheetets。

 I mean， you're just creating a lot of work for yourself。 but academically， if you will。

 systematically this has a lot of merit， because we've avoided all duplication。

 We've sort of normalized the data， so to speak by factoring out any duplications。

 So where are we going with this。 Well， it turns out that we' play now with some actual data from the real world from the actual Internet movie database。

 And in a moment it's gonna look a little something like this。

 This is an artists rendition of five different sorry， six different tables So not one。

 but six different tables that we created using freely available Internet movie database data。

 they kindly provide not Cvs， but T Svs tab separated values which are essentially the same thing。

 but you look for tab characters。😊，Instead of commas， in order to convert them。

 as we did into our own format， SQL lights in this case。

 But we'll see that there is a file that we've made available from today。

 which you can download off the course's website called shows do Db and it contains all of this same information。

 And in that shows Db file there are indeed these six tables but let's focus on just two of them initially like IMDB。

 the Internet movie database is all about rating TV shows and tracking that kind of information So let's actually take a look at some of these ratings and figure out how we can actually answer actual questions。

 So let me go over to VS code and let me run SQL light of shows do Db。

 which is a file that already exists there's no cv， no tsv。

 we did all of this for you already When I hit enter， I get my SQL light prompt。

 And the first thing I like to do whenever I'm playing with a SQL database for the first time。

 maybe I got it from a class or my boss or the like is just to wrap my mind around what's inside of the database because you're not typically gonna be provided with pictures like this You're just to be given a file。

 So let me just select。😊。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_15.png)

Some data， let me select star from the shows's table。 I don't really want to see all of it。

 So let me just limit it to the first 10 shows in the table。

 And here we can infer each what the show's table looks like。

 Every show has an I a title the year in which it debut apparently and the number of episodes as of last night when we exported the data。

 So that seems to reflect this picture。 and this is technically an entity relationship diagram。

 a standard way of depicting things。 and you'll see that in our picture shows indeed have an I column title column year column and episodes column Well。

 what about these ratings。 Well， according to the picture that has a show I。

 a rating and a votes column。 So let's go back to VS code here。

 and let's do select star from ratings limit 10， just to wrap our mind around some of the data。

 And there we have a show I in the left。 we have rating in the middle。

 which seems to be like a floating point value and then votes， which seems to be an integer。

 So we have some different types of data here。 But there's a lot of data。 in fact， if。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_17.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_18.png)

Do this now， select star from shows。 Let's not select all of the data。

 Let's do select count stars from shows。 And in this database。

 there are 214000 shows in this database。 So we're well past the 398 rows that we've been talking about thus far。

 So it turns out per this diagram， there's actually a standard relationship between these two tables。

 shows and ratings respectively。 and it's what we would call a one to one relationship whereby every show in this design has one rating。

 And this is indicated， technically， if you look at what the arrowheads look like on these diagrams。

 this indicates that it's a one to one relationship， which means every show has one rating。

 which means every row in the shows table has a corresponding row in the ratings table Str speaking。

 they could be in the same table。 you could just kind of join them together and make one wider table。

 but IMDB keeps the data separate。 So we too kept them separate and two separate tables here。

 So what does this actually mean in practice。 Well， let's actually。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_20.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_21.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_22.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_23.png)

Take a look in VS code at the schema for these tables。

 let me clear my screen and let me do dot schema， but specifically look at the schema or the design of the shows's table so you can do dot schema shows and any command in SQLL with a dot is SQL light specific in the real world if you're using other products like Oracle or Postgres or MyosQL or others they have different commands。

 but anything else that we've been typing， especially the capitalized keywords is indeed standard SQL If I hit enter here。

 here is what the showss table apparently looks like。😡，In other words。

 here is the create table command that we， the staff ran in order to create this table for you。

 and then we imported a bunch of data into it。 Every show has an ID has a title， has a year。

 has a number of episodes， but there's more detail here apparently the I is an integer。

 The title is text and it is not null cannot be null the year is numeric whatever that means and the episodes is an integer when that is now familiar and then primary key So there's some other stuff going on there which will come back to but let me also do dot schema ratings enter and we'll see a couple of other data types here。

 there's show ID， which is still an integer， but not null rating。

 which is a real number Aka float but it too cannot be null， and then some number of votes。

 which is an integer， cannot be null， and then there's mention a foreign key So unlike our data set for the favorites a bit ago。

 which we just did automatically an imported this database by us and by IMDB has been more thoughtfully designed where there's actually some relationships across。

Multiple tables rather than previously just one Now in the world of SQL。

 we have indeed different data types。 for instance we have these five primarily one cutely named blob。

 which is actually binary large object which generally means like a file or some piece of data that's zeros and ones though generally it's best to store files on file systems like in folders on disk so to speak not in your database there's integers we've seen there's numeric。

 which numeric is more like dates and times， things that are numbers。

 but not necessarily integers or floating point values there's reels which do have decimal points in them。

 and then there's just text in other SQL databases in the real world in your future jobs or your future classes that you might use SQL again in there are even more database types in other databases。

 oracle， minusql Postgres and so forth， but these are sort of representative of them。

 they just get more precise in other systems。 but there's also some keywords that we've seen already that you can specify when designing a database that this column。

😡，Not be null。 If you want to make sure that no one can insert or update data。

 unbeknownst to you that is null， you can impose that when creating the table and unlike Excel and Google spreadsheets and Nepple numbers。

 which will generally let the human type in or not type in anything they want with a database you have more protections over the integrity of your data。

 Moreover， you can specify that a columns values must be unique。 if you want to avoid duplicates。

 like you don't want the same person to be able to register twice for your website thereby making sure they have one unique email address。

 your database can help with that too， you don't have to rely on like Python to check if it already exists。

 But there's this other feature of relational databases。

 that is databases that have multiple tables across which there are relationships。

 And that's these keywords we saw briefly a moment ago。 primary key and foreign key。

 And we started to scratch this surface here。 It turns out what I was doing was actually best practice in the world of relational databases。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_25.png)

I gave or really IMDB gave every show in the world a unique I。 and that unique I in this case 38，6，6。

7，6 is a numeric value， an integer that uniquely identifies that TV show。 In other words。

 this is the primary key for this table。 technically a sheet。

 and I'm using that just because it's easier to type in than my black and white window。

 This Id column is the primary key for shows as I was mocking up earlier。

 What is the primary key in the people sheet here It is also Id。 It's a different I。

 but it's by convention often called the same thing。

 but this people column called Id is its primary key。 and you could perhaps see where this is going。

 Those same numbers， also happen to appear in this third table。 but in that context。

 they're sort of foreign keys。 like they didn't come from this star sheet。

 but they are in this star sheet。 So they're sort of relatively foreign it。 So foreign。😊。

Ks is simply the presence of primary keys in some other table in some other data set。

 And so it's just a description of relativity。 But the foreign key is the column that uniquely identifies your data foreign keys is just the appearance of those same numbers elsewhere。

 So what does this mean if we go back to Vs code here。

 you'll see that when we created this table using IMDB's real data。

 we specified that in our show's table， which is bigger than the1 I mocked up with Google sheets there has not only an Id in a title。

 it again， also has year in which the show debut and the total number of episodes because that's juicy data that comes from IMDB beyond what I mock up a moment ago。

 in the ratings table。 Meanwhile， there's a show Id， which is also an integer just like this Id。

 but is the name implies this show Id column is actually going to be a foreign key that references the shows tables Id column。

 So this is the relational in relational databases。 these are two tables that have a relationship。😊。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_27.png)

And that relationship is that show ID is sort of referring to this actual ID here。

 and it allows us essentially conceptually to link these two tables together。😡。

So what does this actually mean， Well， let me go ahead and do this， Let me go back to BS code here。

 I'll clear my terminal and let's play around with some of this data。

 So let's go ahead and do this just to experiment， select star from ratings where let's get all of like the good shows where just like rotten tomatoes will do the cut off it like 6。

0 out of 10 So where rating is greater than you're equal to 6。

0 and just so I don't overwhelm my screen let me just limit this to the first 10 results。

 In other words， this is sQL syntax for selecting all of the ratings that are at least 6。

0 or higher from that table enter and we see just the first 10 of them not the top 10 because we've not sorted or grouped or anything like that but the first 10 in the table So what is interesting here is that we've seen just sampling of the data if you will。

 but this isn't all that interesting here。 let me actually distill this just to the show I because in other words。

 I want to know 10 good shows to watch So let me just select show I so same。Result， but less data。

 it's just that first column thereof Now this is gonna be a little annoying。

 But if I want to find out the names of these shows。

 think about the picture from once we came all of the show's names are in the showss table。

 but all of the show's ratings are in the ratings table。

 So even if I do select star from ratings I'm never gonna know what show I'm looking at what the heck of show I 626。

1，4 Well I could do this I could select star from shows where the I of the show equals 62，6，1。

4 semicolon enter so I could watch this show from 1981。 let me do another one。

 select star from shows where Id equals63881。 So I'm just grabbing the second Id from here。

 Okay so Cat weasel， a kids show from 1970 All right so I'll watch that。 So now let's do another one。

 I'll just copy this。 Like suffice it to say this is not the best way to look up。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_29.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_30.png)

Where I'm literally like copying and pasting values from one query into the next。

 But this is where SQL gets a bit powerful。 I can have nested queries。

 I can put one inside of the other。 So let me instead do this。

 Let me clear the screen and let me instead do this， select。😊。

Star from shows where the idea of the show is in the following list of IDs。

 select and actually I'll do this on a separate line select show ID from ratings where the rating value is greater than or equal to 6。

0 semicolon So I've separated this onto two lines， the dot dot dot is just a continuation character which means same query。

 multiple lines， but the parentheses are deliberate just like grade school math。

 I want what's in parentheses to happen first and so what the database will do is we select as before。

 all of the show Is from the ratings table where the rating value is at least 6。

0 out of 10 and that's gonna return to me effectively a list， some kind of collection of show Is。

 which previously I was copying and pasting now the database will do the legwork for me。

 it will now select everything from the show's table where the ID of the show is in that list。

Of values。 And it's actually gonna be more than 10， unless I go in there and say， limit 10。

 which I can do。 So let me go ahead and hit enter now。 And now I see more useful information。

 not just the ratings information， which in a vacuum tells me nothing about what to watch。

 Now I see the show Id， the title， the year and the episodes。But notably， what is。

 and if I want to distill this into just the title。

 let me actually go back here and instead do select just the title from shows where the Id is in this whole list。

 and I'll reexec it by just copying and pasting the same。 The only difference now is instead of star。

 I'm selecting title Here's now how like the data analyst at IMDB might be selecting 10 shows that are really good to watch According to ratings。

 But what， of course， is missing from the output， whether I do star or just title。

 Like what's missing， yeah。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_32.png)

Like the actual rating， like I know these are at least 6。0， but like which is 7。0， which is 10。0。

 It'd be nice to actually combine the data in some way。 So we can actually do that， too。

 because it turns out that when you have two tables in the world of SQL or even more。

 you can actually join them together。 You can join them together。

 literally using a keyword called join。 And you can do this as follows。

 Let me kind of propose with a sample data set， these two tables and dot dot dot just means we don't really care about the specifics。

 we just care about the structure。 So on the left here is a simplified version of my shows table that has a show Id and a show title。

 but I've omitted year in episodes as just intellectually distracting from the basic structure here。

 But they're there in the real table。 on the right hand side here。

 we have the ratings table with just two of its columns。 The show I and the rating。

 but I've omitted the votes because it doesn't really add anything to the discussion。

 But let me propose this。 Not that these two tables and these two rows therein。😊。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_34.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_35.png)

Definitely have commonalities like they both have the same Id in the left table。 It's 3，8，6，6，7，6。

 Aka， the primary key of that row。 but it's also appearing in duplicate in the right hand table。3，8。

6，6，7，6。 And in that context， it's a foreign key。 The point though， is that they're the same。

 So wouldn't it be nice if I could sort of treat one table here， one table here。

 And if my fingertips represent these identical values， kind of like glue them together。

 So I get one wider table with all of the information together to satisfy your concern that we don't even know what the ratings are of those shows。

 Well， let me go ahead and do this。 just for artist rendition。 Let me flip title1 Id。

 which has no functional effect。 It's just gonna put the numbers closer together on the screen。

 let me then literally highlight the fact that these two numbers are identical。

 and let me propose that we do the equivalent of this。

 we somehow join these two tables on that common value， strictly speaking。

 I don't need both values because theyre duplicates。 So I don't care if one of them goes away。

 But what I'd really like to do is select indeed。😊。

A temporary table that is the joined version of that original data。 And frankly。

 I don't really care as the user what the idea is heck。

 All I care about is what show to watch and what its rating is， Give me the title and the rating。

 All of these numbers are again metadata， things that the computer cares about。

 but we humans probably do not。😡，So how can we implement that idea of taking one dataset that has a relationship with this data and somehow combine it together well let me go back to VS code here。

 let me clear my screen and this is gonna be a bit cryptic at first。

 but it's very step by step let me do this select star from shows but not from shows alone let me join it with the ratings table so let me select everything from shows joined with ratings but I need to tell the database well what do I want to join things on like what are my fingertips specifically I want them to join on those common integers so I can literally say on and then I can specify one table on the left shows do ID on the left should equal the ratings tables show ID column on the right。

😡，Again， if I'm joining shows with ratings， it's called ID in one， it's called show ID in the other。

 but it's the exact same thing。 In fact， if I rewind this is where we came from two tables with the same value So with this query here if I go ahead and now specify not just that。

 but let me further say where rating is greater than or equal to 6。0 and heck。

 let's limit it to 10 just fits on the screen So it's more of a mouthful。

 but when I hit enter now we have a wider table that indeed contains everything star from having joined these two tables left and right。

 Now again， I don't really care about much of this data like year and episodes and definitely not the Is so let me actually hit up let me go to the beginning of the query and let me just select the title of the show and the rating of the show。

 the query is getting a little long and it's wrapping but it's the same query but except for star except instead of star I've done title comma rating now when I hit enter like this is the list。

😡，have been nice to see the first time around show me 10 shows with a rating of 6。0 or higher。

 But remind me what the rating actually is。 So maybe I can prioritize the sevens， the8s。

 the9s and even the tens， if any。😊，Any questions about this technique of joining two tables。

This sort of solves the problem that we created in the world of this sheet。

 where I was just kind of playing around where I sort of moved all the data into its separate locations。

 which is not at all pleasant to use， but with SQL with join。

 you can still get any of the data you want yeah。调解。Correct， so yes。

 I should have called that out more explicitly。 in my query here， I was using dot notation。

 which we've seen in Python。 we've seen in C。 it means something similar in spirit here。

 but it has nothing to do with structure objects。 in this case it has to do with tables and columns So shows dot I just makes clear that I want the I column from the shows table to line up with the show I column from the ratings table。

 strictly speaking， I don't need to do that because in this case， there's no ambiguity。

 one table has a column called I。 the other table has a column called show I。

 So certainly the database can just figure this out for me。

 but for best practice and explicit sake of being explicit using the dot notation and table names can help。

 especially if there's some common language across them。 All right， Well。

 let's go back to the bigger data set here。 these are all six tables in IMDB。

 We focused for just a moment there on like shows and ratings alone。 But what about genres。

 So genres like comedy and documentary and drama and so forth。 turns out。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_37.png)

This actually implements a different type of relationship。 previously。

 we saw a one to one relationship， but it turns out that IMDB supports what's called a one to many relationship when it comes to genres。

 Why well shows like the office， I do think are generally considered comedy and that's it。

 But there's certainly other TV shows that might have multiple genres associated with them。

 Maybe it's comedy and a bit of romance thrown in like ro comms and so forth。

 So you could imagine some shows having two or three or more genres。

 and so one to many means that one show can have many genres。

 one to one would mean like one show can have one rating as we've seen。

 So why don't we go ahead and focus maybe on how about a query like this。

 Let me go back to Vs code here， clear my screen and let's just look at some of those genres So star from genres and then I'll limit it to 10。

 And again， I do this just to wrap my mind around a new data set。 I could look at the schema。

 but that tends to be more cryptics。 I just want to look at the raw data。 it looks like here。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_39.png)

There are a bunch of genres， comedy， adventure comedy， So two comedies， which is interesting。 Oh。

 interesting family action scifi family。 So the values here duplicated。

 which it turns out is not the best design of IMDB。

 We literally just imported the data as they implement it。 But notice that show ID 6，2，6，1。

4 is a comedy。 but so is show 6，3，8，8，1。 And so is show 6，5，2，70。

 So it turns out that in the real world。 Sometimes data is somewhat messy。

 There's duplication of comedy comedy comedy， but such is the way IMDB's data is。

 But what's more interesting to me for now is notice this。😊，This show Id in three rows is the same。

 So there's some show out there that's considered by the world to be an adventure。

 a comedy and a family show。 So let's see what that is。 Let me just highlight and copy that value 6。

3，881。 and do this。 select star from shows where the idea of the show equals that value。

 And it turns out we saw it briefly before。 it's a show from the 1970s called Cat weasel。

 which falls into all three of those categories。 So by using a one to many relationship sort of depicted by this picture here。

 you can implement that same idea without having that jagged edge when we looked at the spreadsheet earlier in an earlier version of this。

 we had star， star star， star， which we could do again。 genre， genre， genre genre。

 But now we instead have two separate tables where this many to many relationship is implemented across。

 So let's actually play around with it。 Let me go back to the Scode here。

 And let's actually take a look at the schema for genres。 And we'll see that it's pretty small。😊。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_41.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_42.png)

As the picture suggests it's called genres。 Every row has a show I， which is an integer。

 cannot be null。 It has a genre， which is text， cannot be null。

 and that show I is a foreign key in this table that references an I column in the show table。

 So very similar in spirit and so it really is just kind of on the honor system that we're only putting one row for each show in ratings but zero or more shows in the genres table for shows as well。

 So what can we do once we want to tinker with genres。

 Well let me do this How about we select the show I from the genres table where the genre is comedy。

 Like I'm in the mood for some comedy， Let's see all of the available comedies except this is limited to 10。

 Here are the show Is for 10 comedies according to the Internet movie database。 Well。

 that's not very interesting。 I care about the title So we can do that select title from shows where the I of the show is not equal to。

 but rather in the following subquery， if you will。

Elect show ID from genres where genre equals quote unquote comedy limit 10 just to keep things simple so same queries before。

 but now I'm using it it as a nested query to select the actual titles whose IDs match those there enter and there are those titles for 10 comedies。

 maybe a couple of which we've seen cat weasel we've seen before。

 but what if we want to now let's see。😡，Maybe we want to get all of the let's flip it around。

 Cat weasel keeps coming up， why don't we figure out with a query what all of its genres are。

 so cat weasel let's see so let's do let's see select star。😡。

From genres limit 10 because I know it's in the top the first 10。 This was 6，3，8。

81 with cat weasel's Id。 So let's do this。 So select genre from genres where the show I equals that value。

 Okay so there's the same query as we did before。 Can we make this dynamic。

 Well we can too what if I instead more dynamically do select genre from genres where the show Id and not in if I'm looking for specific show now I can actually do equals and in my subqueer I could do this select I from shows where the title of the show equals quote unquote cat weasel semicolon enter So again。

 even though I'm typing these very quickly， I'm really just composing like similar smaller ideas that we've seen before into larger and larger queries to just get at more of this data。

 So what's really going on underneath the hood。 Well you can kind of think of it like this。

 If we've got this relationship between shows and genres here's an excerpt from shows and I didn't bother showing the。

Thousands of other shows。 Here's an excerpt from genres on the right。 What is that queer。

 What are we essentially trying to do， Well， let me flip this around here。

 Let me highlight the fact that this is the same。 This is the same。 This is the same。

 So wouldn't it be if I could kind get these all together。 Well， if I join these tables。

 we're actually gonna notice an interesting artifact。 if I them as we did before with ratings。

 I'm going kind of need to fill in the gap there， because this is not a table like tables by definition。

 always have the same number of rows and columns like you can't have gaps in them like this。

 So the simplest thing to do is just to fill that in this way。

 But if I were to try to combine two tables that have this one to many relationship。

 You're actually going to get duplication。 It's not duplication in the original tables。

 but in the temporary tables， otherwise known as a result set that's coming back to us。

 So what do I mean by this。 Well， if we actually implement this same ideas before where we try to join these two tables。

😊，propose that we do it with this syntax， let me do select star from showss join genres。

 which is just like we did with ratings， but now let's join it on shows。id。😡。

Equals genres do show I D。 But let's just do this for catweasel， where Id equals 6，3，8，8。

1 semicolon with the ratings， it worked perfectly because it was a one to one relationship。

 So the rows just got wider， if you will， But now because it's a one to many relationship when you execute these queries。

 you are going to get back duplicate data， but this is okay。

 It's considered okay because this is sort of ephemeral。

 These results sets these temporary tables exist just for us to look at the data。

 just for us to crunch the numbers somehow， it's not actually stored in duplicate in the database itself。

If I wanted to tighten this further though， let me actually get rid of the star and let me just do title genre and indeed we can now see。

 okay Cat weasel three times has three different categories。

 but generally we don't even care about that， so I can even whittle this query down to just selecting genre and that too will just give me the result。

 effectively hiding the duplication， but when you join data with a one to many relationship。

 you're temporarily going to get duplicates， which is actually useful because it's very easy then to get at the show's title。

 no matter where you are in some loop。😡，Al right， well， what more can we do here， Well。

 let me propose that we revisit the main database here with six tables and let's look at perhaps the juiciest and the one that's really what most people use IMDB for is to look up like shows and people theyin。

 let's focus on these three tables and we can infer from this diagram that there's now for the first time。

 three tables involved in a relationship。 There's people there are shows。

 but I' propose this intermediary stars table。 much like I temporarily in Google sheets gave us a third sheet to kind of link the two together。

 This stars table we're about to see purpose in life is to join two other tables together。

 And in fact， it's only going to have two column show Id and person I。

 So what this is going to do for us is implement this idea。 many to many relationship。

 Why because any TV show can obviously have many people in it but one person can presumably star in many different shows like Steve Correll has been in multiple shows not just the office So when you have a many to many relationship。

 you actually do need this third table。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_44.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_45.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_46.png)

To sort of bridge the two any number of times， but it's going to make our life a little more unpleasant to get the data we want because it's going to add some additional steps。

 if you will。 So let me do this。😡。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_48.png)

Suppose that I want to get everything I know about the office。

 Well let's start with a single query here in DS code。

 select star from shows where title equals quote unquote the office， and I should see oh interesting。

 several attempts at creating a TV show called the Office over the years。

 you can perhaps infer the year in which the most popular of them began。😡，2005。

 so I presume this is the one we all know and have watched， at least in the US， which is this one，3。

8，6，6，7，6， which matches the I that I very carefully used earlier。

 So let me actually be a little more deliberate where the title equals the office and the year equals 2005 that query now gets us the office that we all know in the US and perhaps love but now let's actually do something like get all of the people who starred in it。

 at least according to IMDB whoever had top billing So how can I do this。 Well。

 unfortunately in the showss table， there are no people and there's no stars even。

 but I could do a nested query like this。 Why don't I select the person Id from the stars table where。

😡，Whoops where？The I， the where。Sorry。Where show ID equals， and then in parentheses。

 let me do that same query as before， and for time's sake， I'll just copy paste。😡。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_50.png)

So that we get back the one and only office in that subquery。

 So what I'm gonna to do is sort of take an intermediate step， a baby step， if you will。 Right now。

 I have found in the showss table， the office I care about。 But if I want to get to the people table。

 I have to kind of take a step through the stars table， this intermediate table。

 just to get anywhere close to the names of those people。 So what can I get from the stars table。

 Well， why don't I at least select all of the person Is in that table that are somehow associated with the same show I So in V S code what I'm doing is this。

 select person Id from that intermediate stars table where the show I in question is whatever the show I for the office。

 I could literally type 3，8，6，6，7，6， but I'm trying to do this more dynamically。

 So I've used a nested query instead。 All right， this is correct。 whoops ironically， where show I D。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_52.png)

Oh， select。 I， Oh， thank you。 Oh， who said that。 Okay， I Batman。 I owe Batman Orreos after class。

 Thank you， Batman。😊，That's de facto yes， other good prize for that costume。 Okay。

 so let me fix this。 My apologies。 So let's go ahead and select person Id from stars where show Id equals。

 And then this is where I messed up before。 I did select star from shows。

 But I can't look for a show I equaling an entire row of information。

 I instead need to do select Id from shows where the show's title equals quote unquote the office and the year of that show is 2005。

 And just to call this out much like in C， I'm quoting strings。

 but I'm not quoting numbers that's not necessary for something like 2005。

 And just to be super clear too， I have generally adopted a style already today of capitalizing any SQL keywords like select like from like where and so forth。

 And then using lowercase for everything else。 strictly speaking， that's not necessary stylically。

 we would encourage you to be in the habit of using uppercase for your SQL keywords because they just pop more on the screen。

😊，Makes things more readable， but strictly speaking。

 SQL itself does not care about that capitalization of keywords。 All right。

 now let me cross my fingers。 and now I get back this list of person I。 And again。

 my goal is to figure out who is in the office that debuted in 2005。

 This is not that interesting because I don't know who any of these people are。

 But here's where we can do one additional step and nest a nested query。

 So let me actually select the names from the people table where the idea of those people is in and then on a new line just to make it pretty where the I equals this query。

 which I'll paste here， and then that equals and another line and indent further。 this query here。

 So just to save time， I'm copying and pasting the previous query but I'm wrapping it with one outermost query now that's saying select names from people where the idea of those people is in this result set where the idea of those shows is in this result set。

 So the parent。make clear ideally what's happening in what order from inside out En。

 And there we have it， at least according to IMDB for the latest season。

 like this is the top build stars that are in this here database。 Allright。

 so how can we do something else。 Well， let me just do it in the other direction。

 Supp we want to see all of Steve Correll shows， not just the office。

 select title from shows where the Id of the show is in and then here I'm going do select show Id from stars where person Id equals。

 And then here indenting for clarity， I'm gonna select Steve Corll's Id by saying select Id from people where the name of that person is quote unquote Steve Carell。

 And so in this way， I'm sort of。😊，As I'm writing the SQL query sort of back in reverse。

 I'm asking first what I care about。 But before I can even answer that。

 I have to answer this nested query。 What is Steve Kll's Id。

 Once I have that what are all the show Is that that person Id has been in。

 and then please tell me what the title of all of those shows is。

 Let me go ahead and cross my fingers。 and voila some of these you might have heard of some of you might not have。

 But if you were to go on IMDB do com and search for Steve Corll。

 you would presumably see this here list of shows that he's been in in some particular order。

 just to show you two other syntaxes， but let me not emphasize this because it will look complicated。

 there are other ways to solve this same problem。 If you prefer the approach of joining。

 we can actually join not just two， but three tables together。 But question first。

Now just stretching first so two final ways to execute the same idea but the first of them that I just did is arguably relatively simpler。

 you could do this I could select the title from the shows table by joining it on the stars table on the showss ID column equaling the starss tables show ID column and then I can further join it on the people table on starss。

 personson ID equaling people A this is a mouthful and even I am kind of crossing my fingers that I didn't screw up when transcribing it from my print out here but what I'm effectively doing is joining one to three tables altogether by telling the database how to join the showss table with the starss table and the people table。

 specifically the way to bridge that picture per the diagram is to specify that shows ID should be lined up with starss。

 show。😡，Id and stars do person I D should be lined up with people I D。 And that's it。

 That essentially allows us to connect these three tables with their common fields。

 If I hit enter now， I'm going get back somewhat slowly， actually。😊。

A really long list with some duplication of all of those particular shows。 Oh， actually。

 all shows in the database because I didn't practice what I'm preaching。

 I wanted to search for just Steve Correll。 What you're seeing is the entirety of the tens of thousands of TV shows。

 Control C is your friend。 Let me go ahead and reload SQL light。 and let me type that again。

 let me type that once more。 sorry， select title from shows join stars on shows do Id equals stars show Id join people on stars person Id equals people Id where this was the part I left out name equals Steve Correll。

 And if I didn't screw up by typing so fast。 enter。

 Now we get a little more slowly than before those same shows that Steve Corre starred in。

 So this is just to say there's another way of doing this。 But maybe a third way。

 which is a little simpler than that。 explicitly joining them in that way。

 you can alternatively still do this。😊，Select title from shows， stars and people。

 You just literally enumerate with commas What three tables you want to join somehow。

 And then you can instead of using join， you can just use where clauses to kind of make sure they line up properly。

 You can say where shows do I equals stars do show I and people Id equals stars do person Id and name equals quote unquote Steve Corll。

 And I realize this is hard to keep track of everything now all these darn different ways to do this。

 this is just to say that there's different approaches to solving the same problem and for different people。

 you might think about things a little more differently than someone else。 if I hit enter here。

 this too it's a little slower than the nested selects it seems。

 but it does in fact give us that same answer。😡。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_54.png)

And just for thoroughness， if I go back to our diagram， besides the tables we've seen。

 there's actually another writers's table in there as well。 If you're curious to see what writers is。

 let's just glance at that real fast。 In VS code， let me do do schema writers。

 and it's actually almost the same as stars， except this case in writers。

 we are associating a show with a person Id， both of which in this context are foreign keys that indeed reference back shows and people Id。

 which again， if I do this schema stars， which we didn't see before， is structurally the same。

 So the relationship is essentially embodied in this case by IMDB and in turn by us by way of the table's name。

 TV stars or writers thereof。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_56.png)

All right， I know that's a lot， any questions？😡，Before we take a higher level step back， yeah。find。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_58.png)

A good question。 Does SQL provide any way to figure out the mapping between tables without looking at the database。

 short answer， no， like this is the。 Well， that's not quite fair。

 depending on the database you're using， you might be able to click a button， for instance。

 and get a nice pretty picture like this that shows the relationships。 Indeed。

 we use software to generate this。 We didn't do this diagram， for instance， by hand。

 SQL light itself does not provide you with that in SQL light， the best you can do is run dot schema。

 And if you don't specify a table name， you'll get everything from the table describe once you get comfortable with SQL though。

 the idea that you can read the text and sort of infer what the structure is。 But yes。

 their graphical programs can generate prettier pictures like this。

 But it depends on the software you're using。 Yeah。😊。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_60.png)

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_61.png)

SQL is not case sensitive with respect to its keywords。

 but table names and other things that you chose。 you've got to be consistent with how you capitalize them。

 I've done everything in lowercase， but that tends to be one convention。

 Other people might use camel case where you alternate caps。Appropriately all right。

 so let's take a higher level look at this and also consider some of the actual real world problems that tragically are still with us in some form today。

 Notice that some of the queries we executed a bit ago， were're actually relatively slow。

 whereas I hit enter and got a lot of my results like that。

 those last two queries where I was joining all of those tables looking for Steve Carral's shows。

 We're actually relatively slow。 And let's try to take a simpler case。 Let me do this in SQL light。

 you can actually time your queries by running dot timer and then turning it on。

 This is just gonna keep track now of how many seconds or milliseconds any of your queries take if you're curious to figure out what's faster。

 what's slow。 Let me do something relatively simple like this。

 select star from shows where the title of the show equals quote unquote the office semicolon that was pretty darn fast。

 and it took 0。044 seconds in reality。 If you care further。

 you can break this time down into user time like spent in my account versus system time。

 which means spent in the operating system essentially， but we'll focus on the real clock wall clock。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_63.png)

Time of0。0。😡，44 seconds， Pre darn fast， but we can actually do better because it turns out in the world of SQL。

 you can create what are called indexes， which is a fancy way of saying a data structure that makes it faster to perform queries like select and even other queries as well in a index。

 you can use syntax like this， create index， the name of the index on a specific table on the specific columns。

 And what I mean by this is if you know that your application like imMDB do com or their mobile app is going search on certain columns frequently。

 you can prepare the database in advance to build up some fancy data structures in memory。

 so it can get back answers even faster than that。 So case in point。

 let me go back to Vs code here and let me create an index called whatever title index for instance on the shows table specifically on the title column So that's simply the syntax for telling the database in advance index this column because I'm gonna to do a lot of searching on it。

 So I want the queries to be fast enter It took a moment。😊，Took almost half a second， but the index。

 I only have to build once， even though technically you have to maintain it over time。

 if you're doing updates， deletelets and inserts。 But now let me do the same queries before。

 select star from shows where title equals quote unquote the office previously， that query took 0。

044 seconds when I hit enter now boom。 I mean， it takes no time at all or less time then it's even keeping track of in terms of significant digits Now that might not seem like a big deal to us humans and are human eyes。

 but if you've got hundreds， thousands， millions of users as maybe the real IMDB co has you just saved yourself a fortune in servers and complexity wide because the same server can clearly now handle way more people per unit of time per second because each query takes less than less time。

 I mean， we're all too familiar here and it Yale Shi with certain university applications that are just so darn slow when you click a button and the stupid thing spins and makes you wait and wait a lot of the time that can be explained by like poor database design or。

ases that might not have been indexed properly。 So when you're searching for some course。

 for instance， in the course catalog， it's taking forever because underneath the hood。

 it's essentially doing linear search over everything。 But by contrast， in a relational database。

 when you create an index in advance， because you have a hunch that maybe users are going to search on that column like show titles。

Essentially， you're building up in memory。 what's called a bee tree， which is not a binary tree。

 It's still a tree though， if you think back to week five。

 but it's a very short factory instead where every node might have two or three or 30 children which essentially pulls the height of the tree way up which is to say that when you search for some value in a B tree。

 it's invariably going to be in the leaves， So the shorter the tree is the fewer steps it takes to find the value you care about。

 So when you run create table， that kind of data structure is being magically created for you by the database So it's not a simple linear search through the entire column top to bottom。

 So with that said we can see this really with more complicated queries and let me go back to V S code here let me propose to run that same slow query before even though it's fine if you're not comfortable with the syntax it was relatively slow though to watch。

 So let's do select title from shows stars and people where。tid equals starss。show ID and people。

id equals starss。😡，Person ID。😡，And name equals Steve Corll。

 So this was the last of those queries that just searches for all of Steve Kell's TV shows without using joins explicitly。

 but by just enumerating all three tables in question and then using where to cleverly connect the dots。

 so to speak。 but my timer is still on。 So notice now when I hit enter， it doesn't just feel slow。

 it actually took 2。763 seconds， like that's slow， that's expensive。

 That's gonna to annoy your users that's gonna annoy your students if the database is sort of thinking and thinking and thinking and taking that much time。

 But let's note this。 that same query I just executed， touched a bunch of columns。

 And it turns out that whenever you declare a primary key in a database， at least in SQL light。

 you get an index for free。 like primary keys are automatically index。

 So searching for a number in that column super fast， not linear search。

 it's something logarithmic most likely or ideally closer to something like constant time even。

Here though， I'm touching not just shows I， but I'm also filtering on stars show I。 So a foreign key。

 foreign keys are not indexed by default。 I'm looking at people Id。 that's a primary key。

 that's indexed， but stars person I， not indexed by default is a foreign key。 Lastly。

 I'm filtering by name in in the people table names are not index by default。

 So I'm touching three separate columns， two foreign keys。

 one name field that have no fancy tree structure built for them。 but I can do that。

 Let me go down to my terminal here let me create one index called say person index。

 though I could call it anything I want on the stars table on the person I column So that indexes that foreign key took 1。

7 seconds， but I only have to do it once create index show index on the stars table show Id So another foreign keys getting its own index。

 took 1。4 seconds， but it's a one time thing。😡，And lastly， let's index all of those actors names。

 create index called name index on the people table on the name column enter that took 1。0 seconds。

 but at one time operation So it essentially I built up like three of these trees in memory now specifically for these columns so now recall previously that that slow query。

 if I scroll back up that took what was it 2。7 seconds， I think 2。7 seconds previously。

 but if I now run the same thing select title from shows stars people where shows I equals stars show ID and people I equals stars person ID and name equals Steve。

 so close Corll， same queries before， previously took 2。7 seconds。

 which was the most annoying of them yet now when I hit enter boom0。0。0，1 seconds。

 which is the difference again between bunches of linear searches and in this case。

 searching a fancier week fivet B tree in this case。 So indexes matter。

 So what's then maybe the trade off here。 Like why not index every column in every table because this is feeling great like we're speeding things up like factors of like 1000 practically What's the trade off。

😊，Lots and lots of memory or space。 Yeah， so you're just trading off space for time。

 which we said a couple of weeks ago is an acceptable tradeoff depending on what resources you have。

 but it's probably an overcorrection to index everything。

 especially since it will slightly slow down， inserts updates and delete because you have to maintain this tree structure so it doesn't devolve back into like a linked list or something linear but in fact。

 selective about it is perhaps the best strategy。 Allright。

 so that we can now solve some other problems more generally， let me just connect two dots。

 even though we focus today on SQL， specifically for databases。

 you can actually combine one language with another and solve different problems。 And so in fact。

 let me do this， let me revisit our favorite pi from earlier。 but let me actually now use。

The favorites database as follows。 Let me go into V S code here。

 Let me remove favorites do Db because if you recall it made everyone's count previously was became 50ville。

 So let me remove that file。 Let me run SQL light 3 on favorites do Db again Let me create the file anew Let me set the mode to CSv again。

 let me import that file called favorites do cv into an identical table as before called favorites and then quit。

 So Ive just reset things to my backup， if you will， from the CSv file。

 So I again have a favorites do Db。 Let me now minimize my terminal window here and re favorites do pi。

 and let me just go ahead and get rid of that version entirely and focus this time on not talking to a Cv file opening in iterating over the rows。

 We can actually use Python to execute SQL queries and kind of get the best of both worlds。

 So let me do this here。 Let me from。😊，The CSs 50 Python library import our own SQL functionality。

 and this is a training wheel we still provide for SQL because it's just much easier than using the industry standard libraries for SQL。

 It just is painful for simple tasks。 So now let me create a variable called Db for database。

 I'm gonna set it equal to the SQL function that C50 row。 And this is gonna look weird。

 But the way you open a Db file in Python， whether it's with Cs50's library or someone else's you say SQL light colon slashlash slash favorites do Db。

 So weird syntax， but it's commonplace，3 slashes not to like a URL is usually Now let's use a variable called favorite and set it equal to the return value of input by asking the human for their favorite TV show。

 And now previously we opened up the Csv file， iterated over it looking for the show they typed in show they typed in or rather。

😊，I'm sorry， not the show the problem or the problem that we typed in。 Let me instead do this。

 Let me set use a Db variables execute function， which comes with the CS50 library and let me execute this sQL query select count star as n from favorite where problem equals question mark。

 and the question marks a little weird， but think of it for now like Cs percent S comma favorite I'm going plug in whatever the human typed in into that query where the question mark is So no percent S I'm using a question mark in this world of SQL。

 This is gonna give me back a temporary table and I'm gonna store that temporary table and a variable called rows because a temporary table is essentially0 or more rows。

 So I'm gonna name my variable rows。 And then if I want to get back the first and only row。

 I can literally do like row equals rows bracket0 just to be pedantic just to get literally the first row in that temporary table or result set。

 And now if I want to print back the。In column therein， I can do print。Row， quote unquote N。

 So let me take a step back and do this。 Let me go into SQL light 3， a favorite Db。

 and let me literally type something like this。 here， I'm in SQL L 3 at the bottom。

 And the problem I'm searching for， for instance， is scratch semicolon。

 notice that is how in SQL in the command line of SQL light 3。

 I can get back the answer I want But what if I want to make a python program that queries the database for that value and then print something out in two weeks time。

 What if I want to do that to make a web application like IMDB do com or a mobile app that writes code to generate a user interface。

 but that pulls the data from a database， You're not gonna have your human users using SQL light 3。

 you're gonna generate the output for them。 So let me close my terminal window here rather。

 let me close out of SQL light 3， let me now run Python of favorite pi enter。

 I'm prompted for my favorite using the input function。

 I type in scratch and hit enter and there's my 34。 So this is an。😊。

ably common practice to use one language for what it's best at like SQL is best at reading data from databases。

 Python is maybe best in this case for like creating a user interface wherere eventually making a web application。

 but it's certainly fine to use one inside of the other。

 the documentation for this library if and when you get curious is that this URL here。

 along with a lot of C 50s own documentation。 but there are some problems， nonetheless。

 we might encounter in this world， and we thought we'd end on these challenges。

 It turns out that in the world of SQL， even though we haven't touched upon this yet。

 you're generally working not with like hundreds of people in their favorite languages and problems。

 not even thousands of movies， but like millions of things in the database like Instagram posts or Tiktok videos or the like。

 those are huge databases with millions of rows。 The problem with SQL。

 and really databases in general， is if you have like thousands。

 millions of things happening at once， things can get out of order。 And like your math can be wrong。

 you can lose track of how many like something has。 And so， for instance， as of last night。

This remains the most popular Instagram post who dates in the world。

 It was clicked on by so many people。 And you might think that's pretty straightforward to keep track of click。

 click， click， but not when there's millions of devices in the world and thousands of servers probably at meta running Instagrams backend So how do you actually keep track of all of these likes。

 Well， maybe Me is using code like this to implement the counter for likes on Instagram。

 Maybe they are using lines of code similar to what we just wrote Db dot execute select the current number of likes from the posts table where the idea of the post equals whatever the one is that the user clicked on。

 So the post a moment ago， presumably has a unique I。

 a primary key and that number just gets plugged in here when meta wants to figure out allright。

 someone just clicked on this post， Let's figure out what the current number of likes。

 So we can add one to it and update the database。 So this query here gives us a temporary table containing。

😊，Current number of likes before you or someone else clicked。

 Maybe then we just declare a variable called likes to get at the first rows likes column。

 So this is just Python syntax similar to what I did just to get the actual number you care about like 34 or whatever million it is here。

 But then suppose there's a second database query and a third line of code that updates the posts table setting the likes equal to this value where the idea of the post is this value。

 So these question marks are similar again spirit to print Fs percent S their placeholders for things that are going be plugged in after the commas。

 So if I want to update the number of likes to be whatever the current number is plus one。

 I put it there is a second argument。 and then I plug in the idea of that post。 The problem， though。

 with large systems like the metas， the Google is the Microsoft and others of the world is that they are executing code like this on multiple servers。

 thousandshou of servers that might be executing slightly out of order， one might be faster。

 one might be slower which。It to say。Even though these three lines of code represent what should happen when I click on that post and you click on that post and you click on that post。

 the lines of code chronologically might get shuffled a little bit。

 Like maybe this line of code gets executed for me and then it gets executed for you。

 and then you and then the server moves on to the next line of code。 So it's sort of multitasking。

 handling lots of users at once。 The problem with this is that you run into a race condition of sorts。

 where the servers are sort of racing to handle one user。

 but other users requests are happening at the same time。

 So the analogy that I was years ago in an operating systems class actually pertains to something like a refrigerator here。

 So we have a mini refrigerator here。 suppose you've got one in your dorm or your house room and you come home one day and you really like milk。

 So you open the fridge and you look inside and there's we're out of milk。 So you close the fridge。

 you walk out to like CBS or somewhere else and go to get more milk。 Meanwhile。

 though your roommate comes home， who in this story， also like milk and so。

Decide that I'm out of milk in the fridge。 So they maybe head out。

 Maybe they follow a different path to go get more milk as well。 some number of minutes pass。

 You both come home later on like darn it now we have like twice as much milk as we need。

 We don't really like it that much and some of it's gonna go sour now。 So it's wasted。

 like we made a mistake。 We should not have bought twice as much milk。 Now， stupid story。

 But the point is that both the view made decisions based on the state of a variable。

 But the problem was that variable was in the process of being updated when someone else looked at it。

 the first person in the story was on their way to the store。

 So the variable was about to be incremented in terms of quantity of milk。

 But the other person didn't know that yet。 So they too tried to increment it。 And in that case。

 we ended up with too much milk。 But suppose what might happen here is similar in spirit。

 supposeose that that post at some point in time had just 1 million likes。

 And suppose this line of code got executed for me for you and for you after all three of us clicked on it。

 Well。Vue of our likes variable in meta servers might be 1 million，1 million and 1 million。

 They therefore update 1 million to be 1 million plus1。

 And so what they update the database to be is 1 million1， but they do it three times 1 million1。

1 million1，1 million1， but they've lost two of those likes。

 because they might have inspected the variable while some other server。

 some other users like was being processed。 So long story short。

 when you have lots of data on lots of servers， all of which is happening very quickly。

 you run into these so-called race conditions and code like this can be dangerous。

 even though it might not look incorrect at a glance。 thankfully in the world of SQL。

 though you won't generally have to do this certainly for problem sets say there are solutions to this。

 but too many engineers in the world don't know this。

 don't remember this or don't appreciate this reality。

 there are keywords in certain databases that let you instead begin a transaction。

 which means essentially that these three lines of code should either。

All happen together or not at all。 They should be atomic。

 That is to say they should all happen without interruption or they just shouldn't happen at all。

 And that ensures that you can that the math does not go wrong because my like will get counted and then you're like and then you're like as opposed to them being intermingled and lost track of accordingly。

 So in Python using the CS50 library you could wrap these three lines of code by saying begin transaction to the database commit the transaction to the database and that relatively simple solution avoids this problem of race conditions。

 But this too is a topic。 if you Google invari， you'll see that this is a problem that has hit various servers and apps over time。

 But there's one other problem that the world is still not very good at。

 and that's known as a SQL injection attack。 And it turns out that even with what we've been doing even code like this here。

 is all too easily vulnerable to being hacked， if you will。 that is misused in some way and。😡。

You practice what I'm preaching， which is using placeholders like this。

 It turns out that it's very dangerous to take user input in generally。

 like most of your users might be nice， good people。

 but there's always going to be someone who's malicious or curious or just execute something you don't expect and things can go wrong。

 So in the world of SQL， Here's what can happen。 For instance。

 here's the login screen for Yale accounts。 Here's the comparable screen for Harvard accounts。

 And all of us in their habit of using one of these screens or something similar or another。

 You're often asked for like a username or email address and a password。 But suppose that。



![](img/4ca7f7443412272fdbcd7f1f8ee6173e_65.png)

Harvard or Yale or Google or Microsoft or wherever are taking user input from forms like this。

 be it on the web or on a mobile app。 And they're just plugging your input into a SQL query that they wrote in advance that just is waiting for your username or password to be plugged in so they can ask a complete query of the database。

 It turns out that if I'm a bit malicious or curious。

 I could maybe type in some funky syntax to fields like this that I know have special meaning to certain databases。

 And it turns out in the world of SQL SQL light in particular。

 single quotes are clearly important because I've been using them all day long for strings。

 And I didn't mention this yet， but the comment character in SQL light is。

 If you want the rest of a line to be ignored， you just say。

 So it's noth it's not like in Python and C respectively， it's or two hyphens。

 So suppose that I'm a hacker or curious students。 And I want to see if like Harvard knows what it's doing when it comes to SQL injection attacks。

 I could literally type in maybe my username with a single。😊，And then dash dash。 Well。

 why would I do this？ Well suppose for the sake of discussion that some developer at Harvard or any website really has written a line of code like this to get the to check if the username and password just typed in match what's in the database。

 So how might I do this。 And if so， let the user log in show them their account or whatever。

 So here's the line of code in question select star from users where username equals question mark and password equals question mark。

 This is correct。 This is green because it's good it is not vulnerable to attack because I'm using these placeholders here。

 which even though we've implemented in the C50 library， most SQL libraries support the same syntax。

 but it can vary by system。 This is safe。 What is not safe is to use some of the stuff you learned last week。

 where you can just use F strings or format your own strings and interpolate values with curly braces。

 For instance， suppose you took me at my word last week that you can do this in Python。

 this code here， unfortunately in yellow。

![](img/4ca7f7443412272fdbcd7f1f8ee6173e_67.png)

Is not safe。 Here's a format string in Python。 Here's the beginning of a SQL query。

 Here's a placeholder for the user's username。 Here's a placeholder for the user's password。

 and I've proactively correctly put single quotes around them。

 The problem is if you just blindly plug users input into premade queries like this。

 they can finish your thought for you in ways you don't expect if you trust the users。 For instance。

 if I plug in for my user name。 mail in athard single Notice what happens。

 Here's the single quote from the query。 Here's what I typed in。 but wait a minute。

 It looks like this single quote that I typed in。 finishes the thought that the developer started the dash means heck。

 ignore the rest of that。 and indeed I've left it gray out because what effectively happens is that only executed is what's in yellow here at the moment。

 why because everything after that close quote， which finishes the developer thought is just ignore。

 So that mean this。Literally an example of how you can hack into a database by injecting SQL like dash。

 is an example of SQL silly as it is。 It's a comment that tells the database to ignore the password。

 So what does this mean， Well， of course you're gonna get row back now because if you're only searching for someone by username。

 It doesn't matter what their password is what they typed in you've essentially blacked out that part and you're not even checking the password the effect then would be that you could log in as me or Carter or anyone else just by knowing their usernames if the Harvard developer wrote code in this way And even though I'm pretty sure Harvard Key does not suffer from this。

 so many darn websites have in the past。 And if you Google SQL injection attack。

 search by and Google， for instance， like the past month or the past year。

 you will tragically likely see results because humans continue to make this mistake。

 The solution though， ultimately is actually just used placeholders just use the library that escapes potentially dangerous input。

 And this looks a little weird。 But in C， we saw that。Escape character was a backslash。

 and that may backslash N or backslash something else be treated specially weirdly in SQL。

 it tends to be just another single quote。 So if you do quote quote that actually means I mean a literal quote。

 it's not like the empty string or nothing in between it。 So it looks weird， but long story short。

 if you use a library like CS50s or anything in the real world that handles escaping of user input。

 The whole query you can think of as being now good and green again。

 because it doesn't matter what the human types in any scary characters will be properly escaped by the database。

 So it'll depend on the library you're using， but it almost always is the syntax using question marks or some similar placeholder。

Allright， so with that said， you are now inducted into the hall of people who know now a little something about databases。

 We've only just scratched the surface of using the language。

 but it's now something we'll use to build up more and more interesting applications。

 especially for final projects when we soon transition to web programming or mobile app development if you go that route。

 but you'll soon be able to speak a language literally and figuratively that those before you have acquired as well。

 So you are now qualified to understand this sort of internet joke this is someone who if I zoom in was trying to get out of paying some camerabased tolls by tricking the state through the city into to deleting or dropping their whole database drop means delete the whole thing。

 not just the rows therein so maybe not that funny。

 but this is now the note will end on similar to other XKcD comics we've introduced you to like every C person out there has seen knows this comment。

 So if you ever refer to with a wink if you ever refer to little boby tables with a wink if it's a computer sign。

On the other end， they'll know whom you mean。Okay， there we go。Alright， tough crowd。 Allright。

 Batman， come on down for your cookies and we'll see you next time。

