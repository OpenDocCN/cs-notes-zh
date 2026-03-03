# 哈佛大学《CS50X 计算机科学导论｜introduction to computer science 2025》中英字幕（deepseek - P10：-10-CS50x 2025 - Lecture 7 - SQL.zh_en - GPT中英字幕课程资源 - BV1hFrxYPEfa

![](img/6a0bc78e77555613a960f4c7c09b7797_0.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_1.png)

Allright， this is CS 50 and this is our week on SQL or SQL for structured query language。

 which is a programming language specifically for talking to databases Now over the course of this lecture。

 what we're going to do is solve some problems in new and different ways by transitioning from that other language Python which it turns out is very multipurpose and indeed this is thematic with Python that you can do so many things with it but it turns out there's certain things you might want to do in computing that maybe aren't ideal for a language like Python let alone a language like C and so you might want a more specialized language that makes it easier for you to get real work done and indeed this has been true over the past several weeks we started with scratch we transitioned to C we then transitioned to Python and there's actually a lot of overlap in those languages in what you can do they're not perfectly complementary I can't imagine doing some of the things we did in scratch using C but what we will see today no pun intended is that using a domainspec language something specific to data。



![](img/6a0bc78e77555613a960f4c7c09b7797_3.png)

Bas in this case， you can actually save a lot of time and express yourself a lot more readily with a lot fewer lines of code than something like Python allows。

 but before we do that， I dare say it would be ideal if we have some data that we can play with so we have data to put into a database and let me propose that we go ahead and collect some live data here So if you'd like to go to this URL here that's on your screen if you're on a laptop or desktop or if you simply have your phone in front of you feel free to scan this code here which will lead you to a Google form via which we're gonna collect some information from everyone here I'll go ahead and in just a moment transition to just a screenshot of what everyone here is seeing because if you're watching this onde thereafter the form probably won't still be open because we can't take data from the future into account today but what we'll have here is a Google form via which we're gonna to collect some information from everyone here in the room virtually and this form asks two questions it asks what's your favorite language the options for now。

Scratch C and Python and it also asks what's your favorite problem from recent problem set so go ahead and take a moment and fill out that form and in just a moment we'll see that these responses are being gradually collected not in the context of the Google form per se but in a more useful format for today's purposes that of a Google spreadsheet In fact let me switch over to my other laptop here where I have full screened all of the responses as they are coming in you'll see that all of them are timestamped for a particular day and time on which we actually recorded this year session and you'll see two columns one for people's preferred language and one for people's preferred problem you'll see that a few folks sort of jumped the gun a few hours even before class began but that's great all the more enthusiastic but as I scroll down here you'll see there's a lot a lot of data coming in a couple of hundred responses already and so let's go ahead and use this data now to actually manipulate it to search it to sort it and actually ask questions。



![](img/6a0bc78e77555613a960f4c7c09b7797_5.png)

About this here data and in order to do this what I think we're going to do is first talk about what are called flat file databases。

 a flat file database is kind of the simplest type of database in the world whereby you just use a text file a file in which you can store maybe some rows and columns but that's actually not really possible in text files alone because of course in text files you literally just have text so you can put any characters you want on the screen。

 you can maybe have different lines of or different rows of text but we probably ideal need some way of delineating the data that's inside of that file and one of the most common ways to do this is by a file called CSv comma separated values which is a file format via which we can store really a simplistic database in purely an ASI or really a unIode file and what this means is that all of your data in a CSv file is stored row by row by row or technically line by line by line so each entry has a line of its own but。

Not of columns， you can do this in a number of ways。

 but the simplest way as in the CSV format is to just put a comma in between the values that you are actually collecting。

 and then so long as you're using software like a spreadsheet or maybe Python code or something else altogether you can tell that software to interpret those comms as really delineating where columns at one column ends and the next column actually begin So it's a nice lightweight format using a very familiar tool like a text editor to actually store some data that we might care about and in fact。

 what's nice about collecting data via forms nowadays whether it's with Google Form or whether it's with Office 365 or the like is that you can actually export all of the data ultimately in exactly this format CSv So in fact。

 let me go back over to my actual browser here and you'll see that we indeed have some more data。

 some more rows that have come in over time here And if I go up to the very top of the screen and drop down the menu here you'll see that under the。

menuUnder the download submenu， I can actually download this dataset in a bunch of different formats。

 Microsoft Excel with which many of you are probably familiar PDF。

 although that really won't lend itself to manipulating it very easily with code H if I want to make a web page out of it but you'll notice at the bottom there's actually a couple of options one of which we've talked about already namely CSV for comma separated values there is an alternative called tab separated values。

 which also is a convention to whereby to delineate columns you simply hit the tab key to kind shift the data over but I dare say CSv is probably a little more common if only because a lot of text editing programs nowadays automatically convert tabs to spaces indeed c50 dev and VS code as configured does exactly that So CSv is a little more robust。

 So I'm going to go ahead and click on comma separated values that's going drop a file into my download folder on my here computer I'm going go over to VS code now Min my window for just a moment and then open。



![](img/6a0bc78e77555613a960f4c7c09b7797_7.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_8.png)

up my file Exper， which initially has nothing in it for today I'm going to go into my Mac OS downloads folder and simply drag this file over to the Expr to essentially upload the file to my account。

 I'm going to go ahead now and hide my Exper maximize my window again and hide my terminal window and you'll see exactly that same data here but clearly in textual format now the file is by default called favorites form responses one csv but let me actually simplify that just to make my life easier let me open up my terminal window and the command recall for renaming a file can be Mv for move and I'm going to rename that file favorites dash form responses csv to simply to more simply favorites csv now let's go ahead and open up that same exact file but under a different name now and we'll see these rows and columns but it's not quite as pretty as Excel or Google sheets or Apple numbers would be we have to look a little harder for each of the comms and indeed in each of these columns in each of the。

😡，liness of text rather we have commas delineating one piece of data from another。

 but the very first row in this file is a little different。

 The first row is actually the headers of the columns that we saw visually in Google sheets a little bit ago and so that's actually indicative that's actually pretty common in CSV files whereby the first row and only the first row is somehow special and most software will interpret that first row is being special as really describing the data or the attributes or the records within each of those columns that follow line by line Now there is one curiosity here notice that the first line really the second line after the header file has three values。

 the timestamp at which the form was submitted comma the language that that person found to be their favorite comma and the problem set that that person found to be their favorite but notice here line three in the file there's actually three commas instead of two even though there's still just three value。

Why do we have the quotes around the name of this problem set， Hello world。

 whereas scratch did not have a value， Titamin did not have a value。

 Mario did not have a value because we named that problem set hellello comma world。

 we need to make sure that the value is essentially escaped somehow as with double quotes in this case here to make clear to any software that's processing this data be it again。

 Google Sheets or Microsoft Excel or Apple numbers or my own Python code ultimately that there is something special going on in that string and that comma should not be confused with the other commas which actually have meaning to delineate those columns So what can I actually go about doing with this file Well let's actually go ahead and start answering some questions about the data here I realized that not everyone got their response in from time because I downloaded the file just a couple of minutes ago。

 but I think this is enough data for us to play with so let me reopen my terminal window here and clear my terminal and why don't we go ahead and write a program。

😡，In Python for now， that simply iterates over this data toward an end of doing something interesting with it ultimately。

 let me go ahead and run create a program called favorite dot pi， And in this file。

 let's go ahead and do this。 First， I'm going go ahead and import a package called Cv。

 It turns out in Python， there's built in support for cv files。

 which is going to save me a huge amount of time because I'm not gonna have to figure out how to open a file and iterate over every line and break on all of the commas and somehow load it into memory。

 The CSv module is going to do a lot of this form me。

 So I'm going go ahead and say with open quote unquote favorites do cv comma quotequ R。

 And this is going to allow me to open a file called favorites do cv， which is the shorter name。

 I gave that same file a moment ago。 unquote R means open it in read mode。

 And I'm going give this a variable name of file just so that I know how to refer to this file once it's open in memory。

 Then if I want to read。😊，file line by line。 It turns out thanks to this python package called CV。

 I can do this pretty easily。 For instance， I'm going to create a variable called reader。

 I'm going to set that equal to the return value of CSv dot reader。 So inside of the CSV package。

 There is a function called reader that is going to give me exactly that conceptually some kind of object in the computer's memory that knows how to read CSv files。

 I have to tell it what file to read。 So I'm going to pass in that same variable that I just got back from opening the cv file itself。

 Now for the moment I want to go ahead and iterate over all of these row。

 So for each row in that reader。 and this is wonderfully useful python syntax for just iterating line by line over this so-called reader。

 Let's just go ahead and do something simple like print out the second column we see in that file。

 So recall that these columns are going to be zero indexed as our python lists。

 So zero would be the timestamp。 and I don't really care about that。😊。

1 is going to be the favorite language， and two is going to be the favorite problem among our problem sets。

 Let me go down now into my terminal window。 Run Python of favorite a pi cross my fingers as always。

 And bah， I seem to get out very quickly on the screen。

 a list of all of the languages in that column。😊，But if I scroll back to where I just ran that command。

 let's go up and up and up and up all the way to that output， which is a ways away now。

 though I can clearly see visually a theme here among the most popular language in the group today。

 let me keep scrolling back， keep scrolling back and oops。😡。

There it is my command that I ran earlier。 There's one anomaly here。

 The options on that form were scratch C and Python。

 and yet it would seem based on my output here that someone's favorite languages language but that's a bit of a red herring because recall that in favorite cv that first row was important。

 That first row had timest capital T because that's how Google does it language in lowercase because that's how I name the form and problem in lowercase as well。

 So I seem to be getting a piece of my metadata so to speak the column name and not only the languages in question。

 So how can I fix this。 Well， there's a bunch of ways to do this。

 but the simplest way is actually to use a function in Python that just says next reader which essentially mean skip the first line of this file。

 just next and move on to the second row instead。 If I now run this command again。

 let me do Python a favorite pi And just so I don't have to scroll through hundreds of lines of output recall this cleverness in the Linux operating system whereby I can pipe the output of one。

😡，Command into the input of another command， like the command less。 And as the name implies。

 this is gonna to show me less output from top to bottom， let me go ahead and hit enter。 And indeed。

 we see that the very first line of output here is Python now and not language。

 So a minor bug fix if you will， but it at least now gets the job done。 So at this point。

 we have a program in python， it's only a few lines long。

 that seems to know how to open a cv file read it line by line by line。

 and I have the syntax in python to access particular columns。

 bracket 0 for timestamp bracket1 for language bracket2 for problem。

 even though here I'm clearly only playing around with the column number one。 Well。

 what more what might I want to do。 Well， let let me take a baby step toward making this program more interesting。

 let me clear my terminal window for just a moment。 let me go into my for loop here。

 And instead of just all in one breath printing out row bracket1。

 let me actually create a variable just for the sake of discussion called favorite。

 So at the current favorite language and just set that。

Explicitly equal to row bracket1 and then print that out as favorite。

 So I haven't fundamentally changed anything about this program。 In fact。

 I've kind of introduced a seemingly unnecessary variable。

 but I just want to be pedantic here about how we can make this program even more user or programmer friendly to me。

 So this is still going to work。 let me go ahead and run again Python a favorite Pi and pipe the output of that command into the input of less。

 and I again see the exact same input。 but the reason I did this is because I want to improve this program now it turns out that my program is written is a little vulnerable to changes in the CSv file。

 like if you've used Google sheetets or Microsoft Excel。

 you probably know that you can click on those programs and drag to move the column to the left or to the right if you kind of want to reorder your data and the problem with that is that if I or if a colleague of mine gives me a CSv file whose columns are now in a slightly different order that's going create a problem for my code。

 which is currently assuming。😡，That the favorite language is always in bracket zero so the second column。

 the middle column among those three， but it'd be nice in general to make your code a little more robust against changes to the input so that things just don't break unbeknownst to you so I'm actually going to introduce a different feature of the CSv package whereby instead of using a reader I'm going to actually use something called a dictionary reader or dit reader which is going to give me back essentially not a sequence of lists one per row indexed by numbers012 but it's actually this dit reader going to give me back a dictionary or dit for each row so that instead of using numeric indices like01 and2 I can actually use strings as keys to get at the data that I actually want specifically I can use the names of the columns as defined in that first row of the file so let me go ahead now and make a。

😡，A of other changes we no longer need to ignore the first row of the file so I'm going to get rid of this call to next because the dictionary reader is going to assume that the very first line of the CSV file has the header names that I care about and it's going to consume that row for me automatically before iterating over everything thereafter and the reason I introduce this favorite variable a moment ago is because I want it to be super explicit here that instead now of indexing into the current row as though it's a list with numeric indices。

 I instead am going to index into this row using strings as my keys using the syntax for indexing into a dictionary instead of a list and for that I can simply do this language quote unqu so row now to be clear is no longer a list in Python it's actually a dictionary but I can still use the same square bracket notation to index into this dictionary but this time using the proper name of the column。

😡，Now if I go ahead and clear my terminal， rerun the same command piping up through less so we can just see the first food linesvoila it's still working as intended but if I now were to go back to Google sheets or Microsoft Excel and fus with the graphical user interface and move those columns around download a new CSv wherein there's still comma separated values but they're sort of in a different order this code now will still work and I or a colleague very difficulty with great difficulty changes the names of the column headers their at which point things are still gonna break but at least now this is more robust against minor mistakes like reordering Let's tighten this up again I didn't strictly need that favorite variable。

 so let me go ahead and actually get rid of that and just more succinctly now print out row bracket quote unquote row bracket I'm confusing the two row quote unquote language to print out this row's favorite language so fairly straightforward there but now let's actually solve。

😡，More interesting problem because at the end of the day。

 all this program is doing is iterating over CSv printing out all of the favorite languages。

 That's not really a step forward because I could already see in Google sheetets itself。

 all of the answers that I actually cared about， just visually with my own eyes。

 but it'd be nice now to maybe crunch some numbers and it'd be interesting to know among the people that submitted this form in time before I downloaded it to my code space。

 how many people do prefer scratch， how many people do prefer Python。

 how many people do prefer C Well， it looked at a glance that Python was definitely visually the biggest contender。

 but let's quantify that now。 So let me go ahead and make this program a little more interesting。

 whereby'm still going to import the Cv package up here。

 I'm still going to open the file down here and I'm still going to use my dictionary reader But this time instead of just blindly iterating over the file and printing things out let's actually create a few variable。

 So one let me create a variable called scratch and set it equal to zero let me create a variable called C and set it。

😊，0 and a variable called Python and set it equal to0 so that I have three variables by which I can count。

 how many people like scratch。 how many people like C， how many people like Python。 Now。

 this is a little bulky visually。 So stylistically。

 there's actually a slightly more elegant way to initialize multiple variables at once that I'm gonna to vail myself up here just to make the point that I can Sc comma see commaython equals0 comma0 comma 0。

 and there's other ways still to achieve the same goal。

 but this is just a little tighter instead of wasting three lines。

 I'm using one line to do exactly the same thing This has nothing to do with Cvs。

 it's just a coincidence that I'm using commass on this line 5 to separate my variables and these values。

 but it's a python trick。 if you want to initialize multiple values at once to a value like0。

 Now let's bring back that four loop。 So for each row in that dictionary reader row by row by row。

 let's go ahead and grab the current rows favorite language as we did earlier。

 and now let's use some conditional。😊，To check what that favorite is。

 So if that favorite equals equals quote unquote Sc well。

 then let's go ahead an increment our scratch variable by one else if the favorite value equals equals C then let's go ahead and increment or C variable by one just as with scratch else if the favorite equals equals Python。

 then let's go ahead and increment are python variable by one instead Now technically and logically。

 I could have just used an elses at the bottom of this conditional。

 but just in case someone slipped in a fourth language that I don't want to talk about yet into the file or maybe the form change。

 but my code doesn't know about it， I don't want to mistake some random other value for Python So I'm just going to ignore logically any rows that don't equal scratch or C or python in this case Now at the bottom of this program outside of that loop and outside of the file itself having been opened。

 which because of the width。😡，Will be automatically closed now let's just print out these three values。

 So let's print out using say a format string just so it looks a bit pretty on the screen that the total value for scratch is going to be whatever is inside that scratch variable let's print out on the screen another format string that says whatever the value of the C variable is that's how many people love C And then lastly。

 let's print out another format string with Python as its prefix and print out through interpolation there of the variable Python。

 how many people really like Python So if I didn't make any mistakes here。

 I think I can reopen my terminal window now， run Python of favorite stop pi I'm pretty sure that the most popular language just based on a glance earlier is going be Python but let's see if we can quantify it by hitting enter and indeed it looks like 11 of you like scratch59 of you like C but 243 of you prefer Python。

 So glad to see that it's only getting better and better it would seem here over the week so。😊。

How did we go about doing this， Well， very mechanically right I wrote a decent amount of code here。

 some 17 or so lines just to iterate over that file， create some variables， increment them as needed。

 And this is totally fine， It's not an unreasonably long program but I do think it's getting a little wordy。

 if you will。 It seems like we're spending an awful lot of time sort of building this up when it would be nice if we could maybe simplifyimplified this code a little bit because this is kind of a common paradigm。

 You get some data set as input， Someone， maybe it's your teacher， maybe it's your boss。

 maybe it's your own curiosity or asking questions about that data。 You'd like to provide answers。

 Well， how can we go about improving this kind of code and doing something a little differently Well。

 let me propose that we revisit this idea of dictionaries themselves。

 They've already been useful in the context of this dictionary reader because we can get handed back more user- friendly dictionary objects instead of rows。

 each of which represents a row of our data and recall that a dictionary really is just this。

 It's a set of key value pay。And it's sort of the Swiss Army knife， if you will。

 of programming because it's actually very powerful to just be able to associate one thing。

 a key with another thing a value。 So in fact， instead of having， for instance。

 three separate variables just to keep track of all of those counts。

 know why don't I draw some inspiration from the world of dictionaries and maybe use one dictionary to keep track of all three of those languages。

 And this has been the thematic way back in C recall。

 that we initially would often create one two or more variables。 and then we realize no， no， no。

 there must be a better way。 and there was in week two。

 we introduced arrays which allowed us to have one variable containing multiple similar values。

 And now with Python， because we have these fullfledged dictionary objects。

 that's just to allow us to associate arbitrary keys with arbitrary values。

 we can use that a little more readily and keep our code a little cleaner two。

 So back here in VS code， let me go ahead and propose that instead of having all three of these variables here。

 and in fact。😊，All of these conditionals here， let's get rid of most of that code in the loop and instead let's just create a new variable。

 for instance， called counts that's going to be an empty dictionary and recall that two curly braces open and close together with nothing inside in Python gives me an empty dictionary sort of a table that's ready to go looks a little something like this but with nothing in it initially but it's now one and only one variable All right now let's go ahead and iterate for each row in that reader just as before let's go ahead and grab the current rows favorite by using the dictionary we just got back from the reader indexing into it via the column name language and now instead of having those three conditionals using three different variables。

 let's be a little more elegant let's just say that we should go into the counts dictionary index into it at whatever this name of the language is and increment that by one In other words use the current language。

😡，Scratch or C or Python as a key into the counts dictionary and whatever its value already is。

 increment it by one。 Now this is close， but actually a little buggy。

 It turns out if you just blindly index into a dictionary using a key like scratch or C or Python but that key isn't yet there。

 that's actually a so-called key error， you can't just blindly use a key that doesn't yet exist and try to increment it because what are you incrementing。

 There's no data actually there。 There's no row in this table to go increment the value thereof So I do need to be a little more careful here。

 let me instead do this conditionally So if the current favorite language is already in the dictionary called counts then okay go ahead an index into the counts dictionary using that favorite as your key and increment that value by one else if it is logically the case that that favorite。

😡，Wage is not yet in the dictionary。 That is to say there is no key for it yet in this dictionary。

 no big deal。 let's index into that dictionary， but assign it a value of one。

 So if it's already there， well then presumably we've seen it before so we want to increment the total value。

 but if it's not yet there we just want to assign it of value。

 So in both cases we're indexing into the dictionary。

 but we have to make sure that we're only incrementing an existing value if it's there。

 but we're initializing the value to one for this current rows favorite language if we've not seen the same language before。

 now at the very bottom of this program， let me go ahead and get rid of all three of these print testss and just do something a little simpler。

 let's go ahead and iterate over every favorite key in that counts dictionary and again。

 this is sort of pythonic syntax whereby you don't have to worry about what's the key what the value it is if you just iterate over a dictionary using syntax like this。

 the favorite variable that I'm creating。😡，This here four loop is going to be initialized to one by one each and every key in that dictionary。

 presumably three in total， given the data we have so inside of that loop。

 let me go ahead and print out a format string containing the name of the language using curly braces to plug in that value and then let's go ahead and output with another set of curly braces。

 whatever the value is of that key by indexing into that dictionary inside of curly braces and then closing the quote on the outside。

 which should give me language count， language count。

 language count by iterating over that dictionary Allright crossing my fingers is always let me reopen my terminal。

 let me rerun Python of favorite stop pi and voila we get the same counts Now I will note there's slightly differently ordered。

 I think earlier we saw scratch and then see and then python but in this case we're actually seeing python and then C。

😡，Then scratch， and this is subtle， but does anyone have an instinct for why this is the case。

 Why did my ordering suddenly change？😡，Now that I'm using a dictionary， instead of three。

Explicit print calls。It's ordered by default based on the order in which we inserted those keys and so the answer actually lies in favorite csv itself。

 if we go back to that file here you'll see that someone's favorite language as of the second row in this file was Python though curiously their favorite problem was scratch so I'm not quite sure how to reconcile those two but their favorite language Python the next person's favorite language was also Python the third person's language was C and then if we go down and down and down I think we'll eventually see scratch and so dictionaries nowadays are ordered in the sense that if you insert one key before another and then you iterate over that dictionary later you're actually gonna to say the same ordering thereof whereas I previously in my code had full control over all three print statements so it seems to be an opportunity for us to perhaps sort these via key or maybe even value。

 In fact one is a little easier than the other and let me go back into my favorite stop pi here and propose that we do that Let's first。

😡，by the counts themselves。 So this is actually a relatively easy change down here in my for loop。

 instead of just blindly iterating over the dictionary from first key to last key。

 let's actually sort those counts first by using Pythons sorted function。

 And then in my terminal window here， let me run Python of favorite stop pi again， En。

 And now you'll see that I've actually sorted them by the keys themselves C and then Python than scratch。

 So it's not the same order in which I printed them， now it seems to be doing it alphabetically。

 but I do seem to have some control over how I'm printing this your file。 All right。

 But what if I actually want to be a little more clever and print these things out in order of their values。

 not their keys。 So I don't really care about alphabetization， the end of the day。

 I really want to know what's the most popular。 What's the least popular。

 How can I go about doing this。 Well， in my same code here。

 Let me hide my terminal window for a moment。 and let me add a bit more syntax to the sorted function in Python。

 It turns out if you want to do this。Can actually specify what key to use to sort the dictionary。

 And I'm going to use the clever trick here whereby I write key equals counts do get。

 and that's going to tell the sorted function that I actually want you to get the value from the counts dictionary and use that as your sorting key。

 So don't use the actual key in the dictionary as per our slide here instead use as your key whatever the value is of the counts dictionary itself。

 So sort by count。 Let's go now and open my terminal window again， let me rerun favorite pi。

 And I'm going to leave the previous run on the screen。 so we can see now that this one so close。

 So it's clearly not alphabetically sorted anymore。

 So that's good because I want I didn't care about alphabetization but it seems to be sorted how from smallest to largest。

 So from least favorite to most favorite。 So that's kind of backwards。

 but not to worry if you consult the。cumentation for Python sorted function。 you'll see actually。

 that there's another argument we can provide distort sorted。

 Let me clear my terminal here and close it for a moment。 and let me say that you know what。

 whatever you do with sorting， go ahead ultimately and reverse it。 So set reverse equal to true。

 Clearly the default value must be implicitly false。

 But if I reverse that order by getting each count now， if I run Python or python。

 Now if I run Python， a favorite stop pi enter。 Now， finally， all these minutes later。

 I have a proper analysis of everyone's favorite language ordered from most favorite to least favorite The code itself not terribly long。

 still 14 or so lines， but it's kind of a decent amount of effort just to get to this point。

 I had to write a decent amount of code at a decent amount of complexity just to get a simple answer and you can imagine that you glance at the Google form or your boss glances over your shoulder and ask what's everyone's most popular what's everyone's favorite language。

 it'd be nice to be able to answer that super quickly。Ironically， just like Google can。

 just like Microsoft Excel can， just like Apple numbersumb can because typically you can sort of highlight the data and then in the bottom right corner nowadays you can see a quick summary maybe of the max value。

 the min value， the sum， the average or you could use functions built into a spreadsheet。

 it almost seems like I have to make more work for myself in code。

 at least with Python to answer those same kinds of questions。

 but not to worry that's why we're introducing ultimately a new language today。

 SQL via which we can actually get back that speed。

 that flexibility that you already get in graphical interfaces like spreadsheets。

 but you can also use that technique programmatically in code as well。

 but before we dive in let me pause and see if there's any questions。😡。

On what we've just done here in Python。

![](img/6a0bc78e77555613a960f4c7c09b7797_10.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_11.png)

A really good question and we'll come full circle to the answer to that actually toward the end of today's lecture because we will reintroduce Python at some point。

 because it turns out as you learn more and more languages and you tackle more and more sophisticated programming projects it's actually very common very compelling to mix programming languages sometimes and so you can actually use SQL inside of Python。

 in fact any number of other languages， because yes。

 sometimes you'll find it easier to bring back a more multipurpose language like Python to get some job done。

 but you still want the flexibility than the ease of use of querying for your actual data。😡。

The equal signs here。 So in my code on the screen right now。

 I'm using equal a single equal sign quite a bit。 And that's for the assignment operator in Python。

 whereby you assign over value from the right of the expression to the left。

 I don't have any equals equals in this here code because recall that equals equals in C as well as in Python is for comparing two values for equality left and right。

 So I previously in my conditional version did use equals equals to actually compare the favorite value against quote unquote scratch quote unquote C quote unquote Python。

 but here now I'm only using a single equal sign for assignment a good question。 All right。

 so let's transition now to a proper database for this here data and in fact。

 we'll focus today on what are generally called relational databases which is a piece of software that allows you to store data thus a database but in such a way that you can relate some of your data to other data。

 In other words， instead of just throwing in all of this data messily。😡，To like a folder。

 much like on your Mac， your PC or even your phone。

 you can actually store it a little more methodically。

 a little more algorithmically if you will by baking into the database。

 some kinds of relationships among pieces of data and we'll see in a moment what we mean by that In fact the language we'll talk about ultimately today SQL or SQL for sure really stands for structured query language which is a programming language specifically designed for databases so once we've got a lot of data in a database SQL makes it easier to get it back out and in fact among our goals now for the coming time together is going to be to see can we take that 14 line program in Python and whittle it down maybe to one line of code and a different language namely SQL here So what is SQL allows to do even though it's a new programming language where we're going spend today on it really as well as a problem set that we'll use it again later in the course to to solve bigger and better problems as well but it really only supports four key pieces of functionality that are sort of crudely referred to。

😡，In the industry is crud CRUD is a helpful mnemonic for keeping track of what you can do with SQL and in particular the C stands for create。

 you can create data in a database The R stands for read。

 you can read or access data from the database you for update which means you can update or change data in the database and D for delete you can of course delete data from the database so even though we're about to see a new programming language the end of the day it really only does these four things Now technically in a little confusingly it literally does three of those four things using the exact same terminology create update and delete but it turns out CRd is more general concept in databases more generally in SQL specifically the command we're going to see and use for reading data getting data from a database is technically called select and if I may it turns out there's a couple more ways to create and delete data you can also insert data which starts with I so it doesn't really fall into our nice acronym there you can also drop data or really drop whole。

Seets of data or tables of data using D for drop as well。

 So this is to say there's still only four fundamental operations。

 but the verbiage that we use throughout the language might vary from command to command。

 So what can we actually do with SQL。 Well first， we need a database to start playing with and the data and databases are stored in what we're gonna call tables and tables have rows and columns。

 which wonderfully is exactly the same mental model that we have in the world of spreadsheets。

 whether you saw them today in Cs50 for the first time or have been using spreadsheets for years。

 whether it's Googles or Microsoft or apples or anything else。 Spsheets， of course。

 also store data in rows and columns And if you have multiple sets of data inside the same file in the world of spreadsheets。

 recall that you can create multiple sheets。 Now in the world of relational databases that are used for web applications。

 mobile applications， business applications more generally you can have an analog of exactly that same idea in the world of relational databases。

 we call sets of data tables。Have rows and columns。

 which is really the analog of sheets in the world of spreadsheets and the command via which you can create such a table is not quite as simple as going to like the file menu and adding a new sheet or clicking a little plus icon somewhere this is a programming language SQL so if you want to create a table you're literally going to express code like this by typing it at a command prompt and hitting enter but where are you going to actually run that well it turns out that in the context of CSs50。

 dev and our own vS code environment and really a standard practice in industry as well would be to use a command line program to access a database specifically we're going to use a database called SQL light which is the name implies is sort of a lightweight version of SQL That doesn't mean it's a toy language or a toy database in fact SQL light databases are used in web applications。

 mobile applications and all of the CS50 applications we're going to build here and what's nice about SQL light is that it stores all of your data in a file on your hard drive。

File in the cloud。 It's not a special piece of software per se that needs to be installed and run 247365 so that you can constantly have access to the data That is the case with databases like MySql or Postgres or Oracle or Microsoft access or SQL server there's so many SQL databases out there that are syntactically mostly the same but certain databases have slightly different dialects so to speak they've sort of evolved slightly differently over time but we'll focus on SQLL。

 which really is not only light， but has a lot of the core features of any SQL database out there So in fact in the real world if you start to use some other SQL database。

 you should be quite fine ultimately having this foundation in SQLL itself。

 Now how do you use SQL light on say a Mac or PC or in VS code in the cloud as with CSs50 you just need to install the software which we've done automatically in advance for you and you can run a command line program called SQLL3 where the three just represents the third version of this here program So SQL。

3 is going to be a command line program via which we can create a database and also execute command inside of that their database。

 The typical syntax for creating a new database with the SQLL 3 command is literally SQLL 3 space and the name of the database that you want to create。

 So in fact， let me go over to Bs code here and let me go ahead and type SQL light 3 and then let's call this favorite do Db So there's different file extensions in the database world。

 But do Db is pretty common in the world of SQL light for storing your actual database。

 When I go ahead now and hit enter。 it's going to ask me here in C50 you sure you want to create this file。

 and that's just as a quick reminder that it doesn't exist yet。 but that's indeed my intent。

 So why for yes， and now I'm at a SQL light prompt。

 So notice it's no longer a dollar sign which is my terminal Windows default prompt。

 Now I'm inside of a program that's running continually until I quit out of it and that prompt is SQL light and then an angled bracket or greater than。

😊，Just to indicate that I'm not in my terminal per se， my shell。

 but rather in this here program Now I could type some fairly arcane commands and import that whole CSv file into this dot Db file。

 but it turns out that SQL light3 comes with some handy commands to just automatically import a CSV file for you and what I'm going to do is this I'm going to type first dot mode and I'm going to put SQL light into CSv mode long story short SQL light can import different types of text files like CSvs Tsvs tab separated values in other formats as well。

 but I know in advance that I want to import a CSv file so I'm going to tell SQL light to go into CSv mode the fact that I started this command with a dot is just specific to SQL light itself it has nothing to do with SQL per se and the commands were about to C but anything that starts with a dot at the SQL light command just means you were configuring the SQL light program itself Now let's go ahead and import with dot import。

😡，Favorites do csv into a table called favoriteites。 So to be clear。

 I already have a file called favorites do csv。 I've just created a new file called favorites do Db and I want to store inside of that Db file。

 the database， a table called favorites。 So this is like having a sheet called favorites inside of a file called favorites do Xls X in the world of Microsoft Excel。

 I'm just naming everything accordingly。 I'm going go ahead and hit enter It blinked for a moment。

 but didn't take very long。 And now let me go ahead and just do dot quit enter and do quit gets me back to the dollar sign prompt as usual。

 But now if I type Ls not only while I see favorites do csv favorites do pi。

 but also now favorites do Db， the database that I've just created and into which I've imported all of this data。

 Well let me go ahead now and clear my terminal and rerun sQL light3 on。

Favorites do Db enter that brings me back into the prompt。 and let me now start to poke around。

 like what is it I just did by importing that CSv file into this database。 Well。

 I can see as much by typing dot schema。 the schema of a database is the design of the database。

 What table or tables are in there。 So if I do dot schema enter。

 I'll see now some fairly arcane syntax， but this was all automatically done for me when I use the dot import command。

 A what that import command did for me was execute an actual SQL command called create table。

 if not exists， quote unquote favorites。 and then import into that table， apparently three columns。

 a timest column， a language column and a problem column。

 And those are all encased in parentheses here。 they are all quoted as you see。

 and they're separated by commas。 Again， these are now SQL these are SQL commas not in the file itself。

 But what type of data did I import。import command is pretty naive and if it just sees data。

 it's just going to assume it's text text text。 so even if it looks like numbers。

 it might still assume that it's just text text text。

 but we're gonna to get back to that in the world of SQL。

 there's actually going to be proper data types we can do So long story short。

 What was the point of this Well I didn't want to first start our introduction to SQL by typing out this cryptic looking command and then manually import all of that data the do import command just automatically gets me going with a SQL light database containing all of the same data as a CSv and frankly you could imagine doing this in the real world if for work or some future assignment you've got a CSv file that's part of the assignment or task you can very quickly import it into your very own SQL light database and instantly start executing the following types of SQL commands on it to answer questions about that data So let's do exactly that let me clear my terminal but stay inside of SQL light let me increase the size of my terminal just because we're gonna to start to see a lot of textual output and let me propose that we introduce the first of those crud commands。

V which we can start to read data from a database， recall that the first command。😡。

Recall that the command for reading data from a database is this select so it kind of has the right semantics when you want to select data from a database read data from a database you literally write select and then you specify one or more columns that you want to select data from and you specify from what table you want those columns to come from So what you see here on the screen is sort of the canonical simplest form of the select statement in SQL so let's put this to the task let me go back to VS code here where I have my full screen terminal window and let's select everything from this favorite table let me go ahead and type literally select star where star in this case is a wild card representing every column that happens to be in the table from what table well the favorites table semicollon so you do need to unfortunately end your SQL thoughts with semicollonons just like in C but unlike in Python Now this is a quick and dirty command so to speak that it's really just gonna dump out all of the。

😡，Onto the screen for me。 But when you're opening a database for the very first time。

 it's kind of a nice， simple way to get started。 if you just want to wrap your mind around what is it I just opened。

 kind of like glancing at a file on the screen。 So I'm gonna go ahead and hit enter and very quickly you see a sort of ASI art version of that tabular data。

 So the commas have been interpreted in advance as being delineating different columns。

 that's why visually we see on the screen the sort of vertical columns or pipes and that's just SQL lights being user friendlyend for me。

 In fact if I go up to the very top of this output here。

 you'll see that immediately below my command， I see three columns name timestamp language problem。

 So that CSv has been somehow loaded into memory in this three column format Now suppose I don't really care about timestamp。

 and for now I don't even care about problems what more can I do let me clear my screen and let me select a specific column So select only the language column from the favorites。

 And if I now hit semi。In an enter now I get back essentially a single column tableable。

 a subset of that there table。 and in fact， that's what I'm doing with each of these commands。

 I'm sort of creating temporarily in memory， a virtual table that just contains the data that I care about and I'm not doing anything useful with it yet I'm just dumping it to the screen but I am essentially selecting these temporary tables with these various commands。

 Now this isn't all that much progress just looking at the very data that I've always had access to。

😡，But besides just selecting the data turns out that SQL like Python like C like scratch comes with a whole bunch of functions built in。

 A lot of these are mathematical or statistical or analytical in nature and indeed SQL is very commonly used in the world of data science and analyzing data consulting in the like because it lets you very readily as you'll see answer questions about data and for instance you might want to compute averages or AVG for sure you might want to count the number of rows in some data sets。

 you might want to get unique or distinct values from a data set。

 you might want to force everything to lowercase or uppercase you might want to get the max value the min value and that should evoke recollections of the exercise we just did we're trying to find the most popular language in that their data So for instance let me go back to VS code here and let's try a couple of these out in my SQL life prompt why don't I go ahead and just see how many people submitted this form before I downloaded it into my codes。

😡，So I can do， of course， select star from favorites semicolon。

 and I could just manually visually count all of the rows like there's got to be a better way when there's hundreds of them。

 and indeed there is per this list of some of SQLs functions。

 I can use the count function to answer just this。 Now I don't really care what I count。

 I really just want to count all of the rows。 And so the best way to do that is to actually say canonically select count star using the star and parentheses because count as a function。

 So I'm passing in arguments and star again is a wildcard that represents all of the columns and that's fine because I just want to count the total number of rows ultimately。

 So from favorites semicolon。 and what I'll now get back is not all of the darn data in the table。

 but rather a single temporary table that contains just one value of interest。

313 form submissions came in before I closed it and downloaded that file。 Now I made the form。

 So I know what the candidates for favorite languages are。😊。

There's other things I can do with this data too， for instance。

 if I want to get the unique values of everyone's favorite language。

 well I can use distinct as a keyword here too。 This one I actually don't need parentheses for。

 turns out but I'm going to do it here as follows select all distinct languages from the favorite table and this is going to now whittle down that long column of all of the languages that everyone selected into just a list of three。

 because of course there's a lot of duplicate pythons。 there's a lot of duplicate Cs。

 there's a few duplicate scratches， distinct just means I only care about the distinct values of language Now what if you want to count how many unique languages there are we can compose these ideas in the same kind of way as in Python and C I can do select the count of all of the distinct languages from the favorite table So again。

 I'm first filtering it down to the distinct languages then I'm counting those rows from the favorite table and as you might expect。

I get back three as my answer。 So sort of little tiny bitesized questions I'm asking。

 but all very quick。 and all just with a single line of code。

 So even though I have the power now of programming。

 I can still answer questions like my familiar spreadsheet tools long have。

 But it gets a little more interesting than this。 It turns out there's yet other features。

 besides these here functions。 And there's some other keywords we can use。

 And we'll just start to scratch the surface of these to give you representative use cases of these。

 but it turns out that you can group data。 you can look for data that's like a certain value。

 not exactly equal to， you can limit how much data comes back if you're getting overwhelmed with the number of rows。

 you can order or sort the data， and you can also use essentially conditionals filters。

 otherwise known as predicates to get back just subsets of data instead。 So， for instance。

 let me go back to Vs code once more。 And let me play around with a few of these new keywords。

 And let me propose this。 suppose I care about how many of you really like C。 Well。

 I could just select。😊，All of the data as before and sort of counted up manually。

 But that seems unnecessary。 Let me do this。 Let me go ahead and select the number of people who from favorites。

Where the language they gave us an answer to their form was equal to quote unquote C and you'll notice this the first time I'm using literal quotes in sQL light when you want to quote a string value。

 a textual value， a literal you use single quotes and I realize all of these languages have their own conventions but in SQL light。

 you would use single quotes around values like C。 So what is this asking this is saying select the count of all of the rows from favorites where the language in that row happens to equal quote unquote C So this should give me the same number as earlier in code and indeed there is that same count 59。

 but how did I get it， notice that I was able to answer this in one line of sQL code as opposed to 14 or so lines of Python code All right。

 what else might I do， supposeose I want to be a little more specific。

 and I really want to know how many people like not only C but hello world they sort of peaked early in terms of their excitement and。

😡，like hello world and then none of the problem sense。 So how can we express that。 Well。

 let's go ahead and select the count of all of the rows from the favorites table where their favorite language is quote unquote C and the problem that they love is quote unquote hellello comma world that was one of our very first problem sets in C And so now I'm using this conjunction of checking for the language value and the problem value。

 similar to Python， the keyword is indeed and unlike C where it was ampersand Ampersand。

 but this is now giving me some Boolean logic if I go ahead and enter， we'll see that eight of you。

 okay I'm not sure how I feel about that eight of you really liked not only C but hello world was your favorite problem in question but we can get back that answer to with just one line of code we don't have to write a whole Python program we don't have to debug it。

 we can just express ourselves if in a new way using this here language known as。As sequL。

What though， have I been doing very carefully stylistically。

 you'll notice that I keep capitalizing select and count and from and where and and and then using lowercase as appropriate for everything else。

 This is a stylistic convention。 we've talked about style， of course。

 in the context of C and Python quite a bit in general in SQL。

 we would encourage you stylistically in CS50 and really in the real world use use uppercase keywords like select and count and from and so forth for anything that's built into SQL itself and then use the proper capitalization for any tables you yourself have created for any values that you're searching from why well。

 frankly， it just tends to be a little more readable when you can distinguish what is SQL code and what is actual table names and values thererein。

 but this isn't a universal thing， even different databases and different programmers might have their own conventions。

😡，So let me pause here and see thus far， are there any questions？

On our use of SQL with any of these keywords here or our prior ones。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_13.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_14.png)

What is the difference between select and insert， select is just for getting data or reading data。

 insertt is going to be for adding new data， we haven't gotten there yet， but we will shortly。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_16.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_17.png)

So distinct gives you back unique values Group I we'll get to in a moment。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_19.png)

But distinct we've seen gives you unique values。😡。

![](img/6a0bc78e77555613a960f4c7c09b7797_21.png)

Oh， can you chain the commands together， you can separate the commands with semicollonons just as in Linux。

 but generally I would say people do them one at a time。

 we'll see in a moment how you can nest queries though as well。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_23.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_24.png)

A good question Does it matter if you use single quotes or double quotes。

 the right way to do it in SQL light is indeed with single quotes。 That is the convention。 However。

 SQL light has been around for a while and is very tolerant of different conventions So it will often work to use different quotes like double quotes as well it even supports backts in some cases but what we'll try to show you here is sort of the right way to do things in general and in fact you'll notice that I'm actually not using quotes around everything strictly speaking。

 it's conventional and SQL light to use double quotes around keywords like favorites and language and problem because those are symbols that I myself created in my database and in my database table however。

 when there is not a corresponding SQL command that is identically named it's not strictly necessary to quote values So this is to say I could to be really proper do select countstar from favorites where language equals quote unquote C and。

😡，Problem equals quote unquote hellello world， and again notice I've used single quotes for my string literals for the values I'm searching for。

 but I've used double quotes around all of the symbols from my table name and my column names。

 this is the right way to do this here， but I would say in the real world it's so much more convenient to omit quotation marks when you don't strictly need them。

 so that's the habit that I will generally be in as well。😡，All right， if I may。

 let me propose that besides these commands， we introduce a few other pieces of functionality and then improve on our database as well so let me propose that suppose that I care about not just the hello worlds problem。

 but there was a follow on problem recall and see where it was hello it's me whereby you could actually type in and see your own name printed So if I want to check for either of those how can I express that logically well it's very similar to Python and pretty similar to C select the count of the rows from the favorites table whereas before language equals quote unquote C and but now I want to check for two possible favorite programs so let me use some parentheses logically just like you might use in Python or C where the problem equals quote unquote hello comma world or and I'm capitalizing it to make clear that it's a SQL keyword the problem equals quote unquote hello it's me close close parenthesis semicolon。

😡，Before I hit En， let me see if anyone can spot。The potential bug in this code。

 I think I've just created a problem for myself by advocating for one style。Or another。

The problem is that we seem to have for my hello， it's me problem。

 There's actually three single quotes involved， one of which I'm using as an apostrophe for it。

 and this is gonna to be problematic because just like in Python。

 just like in C the language the computer is not going really understand where the string begins and ends if there's this ambiguity Now in C and also to some extent in Python the way we generally solve confusion like this is we would escape the value using backslash in SQL。

 it turns out that you don't just put a backslash in front of the apostrophe in this case。

 to avoid that problem， weirdly and admittedly confusingly。

 the convention is to actually use two apostrophe。 So this does not create one string on the left and one string on the right。

 having two single quotes in a row means you only want one of them logically to be there。

 So thissuages that concern there。 So if I now go to the end of my command and hit enter this time it worked because now it turns out that eight of you like hello world。

 I'm infer。😡，That none of you liked hello it's me any better because the count is still8。

 but at least now if we get more data over time and I update the CSv and in turn my database。

 I would be checking for both the language of C and either the problem hello world or hello it's me but really the goal here has been to experiment with some of the slightly different syntax that we need to express some of these here problems but you know what what if I wanted to express this even more succinctly and I really just care about any of the hello problems themselves be it hello world or hello it's me let me propose to use one other keyword that's on our new list here namely like where you want to search for not necessarily something that's exactly the same but like a value so to speak so let me go back to BS code here and let me do as before select count star from favorite where language equals quote unquote C and and here's the new part。

 the problem is not equal to but rather like the following value。😡。

Hello comma something Now how do I express something Well here there's another piece of syntax that we need to introduce we've seen the asterisk or the star being used with count and in other context for selecting any number of selecting all of the columns available but when you use the like keyword if you want a wildcard。

 you actually use a little weirdly a percent sign instead So if I now do hello comma space percent in this context of using the like keyword SQL will now search for all of the problems that start with H ELLO comma space and then zero or more other characters after that and because I'm being a little clever here I know that both of the problems I care about are start with hello comma something this should be equivalent to the previous command。

 but I don't need to have a special list of all of the values I'm looking for。

 this will get everything that starts with hello comma space and indeed I still get back my eight rows as before。

😡，All right， how now might we use some of these other commands too Well。

 it turns out that with group by， we can actually group similar values together So how might this be useful Well consider this sample table here。

 It doesn't have nearly as many rows， but I propose that suppose I collected a small number of form submissions that just had maybe these six submissions one person like C three people like Python and two people like SQL Well we haven't yet seen syntax via which we could replicate that earlier Python program whereby I really want to be able to get a quick analysis of how many people like C。

 how many people like Python， how many people like SQL Obviously I can just skim the list visually here because it's sure but if there's hundreds of submissions let alone thousands or millions it would be nice to be able to answer that question without having to write a dozen or more lines of Python code for relatively simple and pretty common question So how might I do this。

 Well， let me go back to Vs code and let me introduce that group by。😡，Syntax。

 let me go ahead and select the language column and the count for that language from the favorites table。

 But how do I want to do this counting， Well， let's go ahead and group those rows by the language value So the only thing that's new here now is group by language and what this is gonna do for me is the following if I go back to this here visualization Not that the possible values or C Python and SQL。

 but there's several of Python and SQL So how might I go about analyzing this Well。

 really notice there's one values for C， There's these three values for Python and there's these two values for SQL wouldn't it be nice and kind of your mind's eye you could take this table and kind of squish it vertically grouping all of these similar values together combine all of the C values。

 all of the python values and all of the SQL values as we've now left scratch behind Well how can I do that What I really want is to get back and answer like this。

 I do want the count。Of something， but I want to group that counting by the specific value for language I don't want to count up all of the rows as I keep doing。

 I want to group my counts by the value in the language column so how might I express this with exactly this code if I want to get back a two column temporary table language in the left column the count thereof in the right column but I want to squish this together in my mind's eye and combine all of the similar languages together and then count those I do at the end of this query group by language and if I hit enter now I get back that same analysis as earlier that we implement it in Python but using a single line now of SQL code。

😡，How might I improve on this further， Well'll notice here that currently what I've just selected is indeed the。

Is indeed the counts really in the order seen here。 C and then Python then scratch。

 which seems to be alphabetized in this particular case， but it would be nice， frankly。

 if I could actually sort this by count not so much because I have a lot of data here。

 But if you had lots of different values in a much taller table， it might not be as obvious。

 which is the biggest， So it would be nice to just do the sorting ourselves。 So how might I do this。

 Well， let me go ahead and do a similar query， and just as in Linux in your terminal window in SQL light。

 you can actually hit the up arrow and go back through your recent command。

 So I'll start to do that now to save myself some identical keystrokes。

 let me go ahead and instead of just ending my thought with a semicolon。

 let me actually say order by the count of those rows， semicolon。 if I hit enter now。

 you'll see the exact same data， but it is indeed sorted by the count column。 Unfortunately。

 just like with my earlier Python program， I accidentally sorted it backwards。

 It's from smallest to largest。😡，defaultfault， in fact。

 what's implicitly happening here is that I'm ordering it by count in ascending order。 ASC for short。

 whereby ASC indicates ascending order。 So from smallest to largest。

 but if what I want to do is actually do this in descending order。

 I can actually do D EC for descending hit enter here。

 and now I actually do get a sorting version of this from largest to smallest instead。

 Now this temporary table I have here is a little weird because one columns called language。

 the other columns called count star turns out there's another trick we can use in the context of SQL。

 if we actually want to rename these columns that we're getting back from our queries and we can alias these things in the following way。

 Let me go ahead and now do this select language。😡，Coma count star。

 But if I want to give this countstar column an alias a nickname n is our goto value for numbers。

 for instance， in programming。 So let me rename this from countstar to just n for number and then let's do this as before from favorites Let's group by language and let's order by and now this might make a little more sense。

 let's order by n in descending order semicolon and now I get really back the same result。

 but I indeed see language as the column name it left and for the column name it right。

 and that's just a little more explicable。 and in fact this will be useful in code if you want to give aliases to the headers you're getting back so that in Python or some other language you don't have to keep typing countstar countstar。

 you can use nicknames or these synonyms instead And just to show you one other query one other keyword that flashed before our eyes earlier。

 there's also this limit keyword which isn't super useful with this relatively small data set。

 But if you've got hundreds， thousandshou， millions of rows， you might want to。😡。

Limit the results to be just the top 10 or the top one because you might not care about all of the other data Well I can do that here in SQL light as well。

 let me go ahead and clear my screen， let me hit up so as to open up the previous command and let me add to the end of this statement limit one if what I really care about this whole time is what is everyone's most popular language enter now I get back just that answer and there we have it the most popular language with a total of 243 favorites is indeed Python to be fair our queries have gotten a little longer a little longer。

 but by just using these building blocks and those we've seen prior。

 we can express in really single lines of code what previously took us half a dozen or a dozen or more lines of code and say Python。

😡，Let me pause here now and see if there are any questions。Yes， a really good question。

 unfortunately yes， and I think as you're getting started with SQL for the very first time。

 like that's gonna be one of the mistakes you and I commonly make by just getting things out of order。

 so I've been very careful with my cheat sheet to do things in the correct order。

 but even I forget sometimes and have to look it up or ask CS50's duck or the like。



![](img/6a0bc78e77555613a960f4c7c09b7797_26.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_27.png)

A really good question。 short answer， No， because the way the Google form was designed was to only store values in the CSv if those options were selected。

 if no one liked a certain problem or even a certain language， we would have no evidence thereof。

 We would have to go back to the original form and maybe maybe create a new table that contains all of the original authoritative answers。

 but that have nothing to do with what people selected。 So indeed， as you'll see in Python。

 you might want to even validate data， there's probably some hackish ways where a malicious user could get submit data into the form that wasn't actually on the form unless Google 2 is doing validation。

 So that's a compelling use case for exactly that same solution。



![](img/6a0bc78e77555613a960f4c7c09b7797_29.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_30.png)

A really good question so I'm following the same paradigm in mathematics whereby if you are doing like multiplication followed by addition and you want the addition to happen first between two values you have to parenthesize that in math similarly here what I cared about logically was that the language was C and the problem was hello this or hello that and so I expressed with parentheses。

 the fact that I only cared about one of those ladder being true。

 but I definitely wanted language to be true and so parentthesizing in that way ensures that the operators are handled and the priority I intend。

😡。

![](img/6a0bc78e77555613a960f4c7c09b7797_32.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_33.png)

So in the case of the form I created， there were only specific values allowed hello comma world and hello comma。

 it's me Na were not supported in the list of options I gave to the user。

 so I don't think this is a concern in my analysis of that data because I know from the get- go what those values are even that said if I were to use that like expression hellello comma space percent sign if there were a third if there was a fourth if there were a fifth option in that form that started with hello comma something。

 we would also take those into account so that might be a little too overly generous and indeed not the best design Well before we move away from this favorite data set。

 allow me to propose that we look at just a few other features before graduating to a real world much larger data as well So in addition to to create a table which we automated earlier and in addition to selecting data as we just did hands on you can indeed insert data into a table as well。

😡，relet in the case of our Google form， because you all used a Google form to insert that data。

 But before long， I bet we're gonna be writing software wink win whereby we're going to programmatically encode code。

 need to insert more and more and more data based on what someone might be types into a form of our own The canonical syntax for insertion is indeed this whereby I can insert into the table name and then in parentheses。

 I specify one or more columns for which I have values Then I literally say values and then in another set of parentheses。

 I specify one or more values that I want to insert respectively into those columns from left to right。

 So the syntax here's a bit more verbose， but let's go ahead and try this out。

 Let me go ahead in my VS code and go and type insert into the favorite table。

 How about just the language column and the problem column。 I don't really care about the timetamp。

 I don't want to figure out what time it is now and write it in the right format。

 So I'm only going to insert2。😡，Values， not three， specifically language and problem The values I want to insert are going to be quote unquote sQL because I'm a big fan of SQL all of a sudden and the value for problem is going to be 50ville。

 a problem that awaits you as well。 then I'll hit semicol and enter and nothing seems to happen but if I quickly do select star from favorites。

 which again is nice quick and dirty command for just seeing all of the data in a table look at the bottom of the table。

 I actually do see a new value namely sQL and 50ville。 Now curiously there is a value for timestamp。

 but it's a special value。 and we've seen this value by name before in C that of null。

 So in the world of C recall that Nll with 2 Ls represented a0 pointer。

 an invalid pointer or just an initialized value that has no valid address。 in SQL。

 this has nothing to do with pointers per se but we still use null in all caps and UL to represent explicitly the absence of a value。

This is actually a really nice feature of SQL。 imagine the world of Google sheetets， Apple numbers。

 Microsoft Excel humans make a mess of their data all the time。 For instance。

 if you don't have a value in a cell。 one of those rectangular boxes in a spreadsheet Does that mean it's deliberately blank Does it mean you don't know the value。

 Does it mean you're missing it and you're gonna come back later。

 So what do we humans do well in English we might have a convention like writing Nlash a for not available。

 maybe lowercase， maybe uppercase， but that's a complete hack。

 because what if you want the cell to actually contain for whatever reason。

 inlash a it's ambiguous So maybe you color it in a different color like maybe black it out in the spreadsheet just to indicate no。

 no， no， there's nothing here。 but a color is not an explicit value for a cell。

 So in the world of spreadsheets。 It's actually harder to express the deliberate absence of data than it is here in SQL。

 So when you have a null value， that means I or someone has made a conscious choice。

Not put a value there。 It is not the same as quote unquote nothing。 the so-called empty string。

 It's not a blank value。 It is the conscious， deliberate absence of a value instead。

 So that there is a plus Now， suppose I want to actually get rid of something now。

 turns out there's other features Indeed of SQL， we shouldn't explore。

 not just the insertion of data， but the deletion of data as well。

 Now this one is pretty simple delete from table where some condition is true。

 but anytime as in the real world， you can make really bad decisions and make really big mistakes by deleting data that you did not intend。

 So for instance， let me go back to VS code here。 and let me propose that I want to get rid of this SQL value because it wasn't in the original form。

 I'm really just playing around here。 I can start my query with delete from favorites。 And please。

 please， please， especially if working as an intern or fulltime engineer and industry。

 do not ever end this thought with semicolon。 unless you know what you're doing。

If I were to hit enter on my keyboard now， this is how you would delete everything from the favorites table。

 This has happened before there are news articles about employees doing really bad things because they deleted data they shouldn't have So let me just let me just delete my semicolon and finish this thought as per this slide where I'm saying you should really use a where condition we used where before for select where we only wanted to get a subset of data presumably when deleting stuff I probably only want to delete a subset of my data maybe one row or a few hopefully not ever all so let me specifically delete from favorites where the timestamp column capital T because that's how Google does it is null and this too is a little weird and instead of saying equals null the right way in SQL is to say is null or conversely is not null to express that you literally are checking for that absence of a value So this I'm more okay with because。

That all but one of my rows has timestamps。 So if I hit enter now， nothing seems to happen。

 but if I do select star from favorite semicolon and enter。

 notice the bottom of my output no longer has that SQL or 50ville value。

 Now I will say there's other things too。 we can do with our data set， not just insert。

 not just delete， but also update existing values。 and this syntax a little wordier。

 but it does what it says。 If you want to update a table and set one column equals to some value where some condition is true。

 You can express that with code like this。 You can actually set multiple values at once by separating column equals value comma column equals value。

 comma column equals value and so forth。 But for now。

 I'm going go ahead and set two things to known values。

 Sose that I'm really getting excited about SQL。 I really hear good things about this 50ville problem。

 Let's kind of change this data and decree that everyone's favorite language as of today。

 or this coming week is going to be SQL。Favorite problem is going to be 50ville。

 so I can do this albeit destructively。😡，Update favorites。

 set everyone's language equal to SQL and everyone's problem equal to quote unquote50 Vi semicolon。

 I haven't executed this yet。 But what this means is that it's going to iterate over the table top to bottom。

 And because there is nowhere clause， I am going to change every cell to equal SQL and 50 Vi respectively in the language and problem column。

 So this too， probably not something you should do in the real world。

 certainly not when working for a real worldor company with a real worldord database unless you want to blow away all of your data and replace it with SQL and 50 Vi。

 but let's do that。 enter。😡，Nothing seems to have gone wrong。

 Let me do another select star from favorites， and I really hope no one has questions about the previous version of the data set because now everyone loves SQL and 50 Vi。

 and unlike most computer software， I cannot just hit control or command Z to undo what you have to do now is exit out of SQLL。

 hope you made a backup of your database earlier， which I didn't and then restore somehow from backup。

 so beware the power of these commands that you now have at your disposal。😡，All right。

 so that was a lot。 and unfortunately we're out of data now， the hundreds of rows that we've had。

 but that was never a lot of data to begin with。 So in fact。

 let's go ahead here and take a few minutes break。 And when we come back。

 we're gonna graduate from hundreds of rows to millions of rows of data Indeed we're going introduce you to a real worldord data known as IMDB。

 the Internet movie database， which has lots and lots of information about movie stars， TV stars。

 movies and TV shows and so much more， and we're going to use some of that publicly available data to explore SQL all the more。

 but also the design of our databases， but let's come back in 10 minutes and we'll pick up there with millions of rows。

 suddenly。All right， we are back and we now dive into the Internet movie database or IMDB for short。

 which again has a lot of real worldor movie stars， TV stars， TV shows， movies， writers。

 directors and so much more and all of that data turns out is downloadable in TSv format tab separated values and so among the things we've done before class today is we actually wrote a program of our own。

 turns out it was in Python， but it could have been in any language to automate the process of importing those Tsv files into our very own movies and TV shows databases for todays we're gonna focus on TV shows in the world which many of you are likely familiar So we thought we'd go about showing you how we might design a database for TV shows。

 So let me begin with just some quick and dirty spreadsheets in fact。

 if I go back over to my browser here I've got a Google spreadsheet open wherein I'm storing the title of one of my favorite TV shows。

 the office and then I have a lot of TV stars who featured in that show， Steve Correll。

 Ra Wilson and so forth。

![](img/6a0bc78e77555613a960f4c7c09b7797_35.png)

But even in the world of spreadsheets， I would argue that this way of associating TV stars with the TV shows they were in is maybe not the best design。

 Why well here I have just five of the TV stars from the office but there were certainly many others in that ensemble show but so where does this design in do I add another star column。

 another star column another star column and the like。

 that doesn't seem like the best design because then when I add a second TV show to this same design then I'm going have a different number of stars for that show and a different number of stars for the next show and so forth。

 So this doesn't feel like the best design to use columns to store each and every TV star in a TV show。

 Well let me propose that we look at a second version of this that I whipped up in advance whereby maybe we stick to just two columns I like this better because from the get- go I've got two and only two columns and this thing isn't going to grow wider and wider with more and more TV stars。

 but I also don't think I love this design。 Why Well because in the。

First column I've got the title of the show the Office。

 but I've got it again and again and again and again。

 one such row for every TV star in the second column here， So this feels more compact sure。

 but there's a lot of duplication now I'm literally repeating the office。

 the office again and again and again。So the right way to do this。

 not necessarily in the world of spreadsheets， but as we'll soon see in the world of relational databases is as follows。

 In fact， it's just convenient visually for us to use a spreadsheet just temporarily to mock up this idea but I dare I dare say the right way to solve this as we'll soon see in relational databases is not even with a single sheet。

 but rather to start using our database tables or in this case temporarily sheets to represent real worldor entities or relationships therein In particular。

 notice at the bottom of my Google sheet here， I have a shows tab a people tab and a stars tab In other words。

 in the world of TV shows， there are of course the shows themselves that's a real worldord entity。

 each and every show， but there's also lots of people in that industry， the actors， the writers。

 the directors and so forth。 So people is another realword entity。

 but then there are the people specifically who star in those shows and that's more of a relationship。

 So we've got entity entity。And relationship。 So notice here in my shows tab I have the beginnings of a sheet for just all of the TV shows in the world there we have in the second column。

 the office， which is the one we keep talking about。 And just for the sake of discussion。

 let me propose that it will be advantageous to us and good design to assign every TV show in the world a unique I doesn't really matter what it is。

 but some unique number that no other TV show is using is probably helpful。 So for the office。

 for instance， I'm going to arbitrarily but deliberately will soon see use 38，6，6，7。

6 as its unique I Meanwhile， if I click on the people tab now。

 here are the real world people that is to say people are an entity unto themselves and here we have again。

 Steve Carrell Ra Wilson and so forth， each of whom has their own unique I which is again an integer and it could be the same numbers as before。

 but in the context of people， these ideas must be unique in the context of shows。

 these ideas must be unique。 So there is。😊，necessarily a relationship yet。

 but if I go to the third and final sheet here， the star sheet notice somewhat cryptically I have no TV shows。

 I have no people but I do have the unique identifiers for both。

 and the way I propose to maintain relationships between shows and people is by somehow linking their unique identifiers together。

 So if I want to associate Steve Correll and rain Wilson and other people with the office。

 I include their I， their I and so forth， but in the lefthand column。 I associate those person Is。

 so to speak with the corresponding show I Now I do concede that there's still some duplication here。

 I keep seeing 386，67，6386676， which is obviously the I for the office。

 So there's still some duplication here。 but the duplication does not extend to these longer strings of text。

 the office but。These smaller integers and that I'm going be okay with in the world of relational databases。

 we shall see it's very common and generally good design to use simple integers。

 but unique as your identifiers for data It's okay if you have duplication therefore those integers because what it's 32 bits。

 maybe 64 bit It's not a variable number of characters as would be the name of a TV show like the office or TV show with an even longer name we can gain efficiency by just using simple integers but unfortunately this spreadsheet I do can see it's no longer nearly as useful to look at as the previous versions。

 because if I want to see shows I have to go here if I want to see people I have to go here if I want to figure out who stars in what show I have to go here but these numbers mean nothing to me the human but that's why we're transitioning now away from these spreadsheets again to a proper relational database because with SQL this programming language。

 we can somehow join these disparate data sets together and get back。

The answers to the questions we want to visualize exactly the data we want。

 but underneath the hood so to speak all of the good design will be intact using integers to relate one piece of data to another so indeed in the world of IMDB we're about to see even more data than this in fact what we'll see now is this so-cal schema and recall from earlier that the schema for a database is the design of that database and it turns out there's fairly standard ways of drawing databases and database tables therein in the relationships between those tables but we'll focus step by step on subsets of this data here but the picture you see on the screen here really represents a showsdb database containing lots of information on TV shows from IMDB that's apparently going to have six tables and among those tables at top left are the people table and then we have at bottom left the stars table in the middle we have the shows table below that we have a writer's table and then above that and top right we have。

the genres table， which will give a genre to each of these shows and the ratings for each of those shows。

 And indeed that's among the reasons IMDB is popular is that it offers up ratings or people's evaluations of these various films。

 But let's indeed focus on just the subset of this for a moment Let's focus on the world of TV shows at left and at right the ratings thereof Now technically these two tables could be combined into one。

 but insofar as ratings are such a prime feature of imMDb and themselves are sort of a real worldord entity。

 the ratings for shows。 IMDB chose to store ratings in a separate table or technically tsv file。

 So we've opted to do the same for consistency with the original data But let me go ahead now and open up vs code again whereby I still have my files from earlier but we're done with those favorites tsv favorite and favorites do db but during break I also copied into my code space a big database called shows db which is like 50 mebys of data from IMDB itself。



![](img/6a0bc78e77555613a960f4c7c09b7797_37.png)

As seen in top left of my explorer， let me go ahead and close the file Expr。 though for now。

 let me increase the size of my terminal window as before。

 And let's go ahead and open up this new shows dot Db file。 I'm again。

 going to use SQL light 3 shows do Db enter and rather than create this file。

 which I did the very first time with favorites do Db。 This1 I showed you already exists。

 So I'm simply opening it by running SQL light and then the file name。

 Let's just go ahead and start wrapping our mind around some of this data。

 Let me go ahead and do something like select star from show semicolon again。

 my sort of go to default command just when I want to get a sense of what is it I have in front of me。

 En。😊，And it's taking a while now。 All of our favorites thus far kind of flew across the screen。

 but we are looking at decades worth of TV shows now flying across the screen here。

 So I would wager that we've got not even hundreds， but thousands， tens of thousands。

 hundreds of thousands of TV shows。 This is a very large database。

 And so we're now going really be applying the principles of good design to make sure that when we execute queries when we design databases。

 we're indeed doing it well， because you can imagine for real worldord websites like IMDB。

 you can't really afford to make poor design decisions because realwor users are using that site。

 they want to get quick results， you want to minimize the number of servers。

 you have the amount of money you're spending so good design decisions aren't going to just translate into good problem set scores now。

 but actual time and cost savings in the real world。 In fact。

 that was a lot of rows flying across the screen。 Let me clear my terminal for a second。

 let me just do a quick select count of star from shows semicolon。 and indeed， we'll see there's two。

😊，234000 TV shows in the database as we have saved it here。

 If I want to see just the first 10 of those shows， there's other syntax I can write too。

 let me go up in my history and if I don't want to see240000 rows all at once。 Well。

 I can limit myself to the first show or maybe more useful the first 10。

 Just so it fits on the screen And indeed we have a bunch of shows from the 1970s1 from 1981 and if I limited it to even more rows。

 we'd see more and more films。 but what is it I'm looking at Well it looks like in the show's table I indeed have an I for the show。

 I have a title for the show， I also seem to have the year in which the show debuted on TV for the first time and as of now the total number of episodes that are associated with that show So it's a helpful way to just look at a subset of the data just to see what kinds of data is there even though it's nonexhausive。

 How about the ratings。 Let me go ahead and do the same thing select star from ratings limit 10 whereby I just want to wrap my mind around this table。

😊。

![](img/6a0bc78e77555613a960f4c7c09b7797_39.png)

okay I can infer here that in one column is the show ID。

 which I'm guessing corresponds to the ID in the showss table that we just looked at。

 There's a rating column which seems to be out of 10 I'm guessing from 0。0 to 10。

0 for an average and then the number of votes by realworl humans on the internet that contributed to that average rating so just to the glance I can kind of infer what this data looks like in the absence of any additional detail Now what you'll see here implicitly is an example of what we would call a one to one relationship it turns out that with relationshipsal databases。

 you can indeed have these relationships across tables and they can be different types of relationships one to one means that every show has one rating according to the design of IMDB's database and I can kind of infer that as follows if I have in my show's table up here an ID column that I'm inferring and I could confirm from IMDB's documentation uniquely。

Identifies each of these shows when I then see in another table。

 a column that by convention is called show ID。 the implication is that that's not a unique identifier for this tables rows but it's a reference to if you will another tables unique Is So this is just one convention and there's many in the real world but in the original table where the data is defined like TV shows the unique identifier is typically called ID。

 but when that same identifier is used elsewhere in another tables for cross-referencing purposes。

 it is typically written as table name underscore ID。

 but you change the pluralization to be singular So show ID means that it probably comes from a table called show in the ID column So I'm just inferring but frankly again per the documentation I bet I could confirm as much and if indeed we do go back to the visualization of this database and take me away。

 you'll see that the arrows drawn。😡，Between shows and ratings actually implies this kind of relationship whereby every show has a one to one relationship with its one rating in the other table。

 Now， how can we go about wrapping our minds a little more formally about what's in this here database。

 Well， let me clear my screen。 and let me use that schema command。

 But let me use it slightly differently previously for my favorites do Db。

 it just showed me the schema for the design of my favorites database。

 that was super simple because that was all automatically generated from that dot import command。

 This database again， I claim we created ourselves using IMDb's own data。

 So what we did in advance of today is this if I want to look at the schema or the design specifically of my show's table。

 It looks like this。 And we've tried to form at this line by line to be a little more readable than the automatically generated one for favorites。

 So at some point we， the staff ran a command called create table and we created a table called shows inside of parentheses。

 We then specified what are the。😊。

![](img/6a0bc78e77555613a960f4c7c09b7797_41.png)

Columns for that table。 The first one， we decided to name ID and we decreed that it's actually gonna be an integer。

 a number from， say one on up。 The next column is gonna to be a title column。

 it's gonna to be text because of course the office and other such TV shows have text as their name。

 And in particular， we want to make sure that no TV shows's title is null after all， if it's null。

 that means we don't have it。 why is it in our database。 So that's just kind of a business decision。

 I do not want blank data， null data in my database because what would it even mean for a TV show to have no name。

 That's not really useful data at all。 Then we have a year field， which yes is an integer。

 but it turns out for things like years， It turns out that it's SQL light。

 you can specify more generally that it's a numeric value。 So it's like a number。

 but it's a special type of number like a year。 it's not just a boring old integer episodes though。

 is just going to be an integer because we just want to count 0，12 on up。

 there's nothing really special about that And then the last thing here after the final comma is a little。

Different but we'll come back to this whereby the primary key for this table is ID。

 And for now that just means that the unique identifier for this here table is going to be the aforementioned ID column or're just telling the database what to expect Meanwhile。

 if I do dot schema ratings， which is that second table very similar in spirit。

 but notice this I've created a table in advance called ratings and inside those parentheses。

 there are these columns a show ID column which like the I column earlier is indeed an integer。

 but be careful here it is not null it would also make no sense if we've got this orphaned rating that has no relationship to a show。

 So we do not want show ID to ever be null that rating has， of course a real number as its value。

 So a real is similar to a float in C or in Python whereby it has a decimal point and that's apt for something like an average and it too is not just real。

 but also not null and then the number of votes that contributed to that average is an integer because there's some number of humans。

😡，Who voted that too should not be null but the interesting part here and here is the relation in relational database notice that this last line of code here specifies when creating the ratings table that theres a relationship between this table and another specifically show ID in this table somehow references the ID column in the show table and you'll notice sort of some keywords here。

 primary key is what I said defines the uniqueness of the column foreign key is what imposes the relationship between this table and that so henceforth what we mean by primary key is a unique identifier for a tables rows it is guaranteed to be unique row by row by row a foreign key meanwhile is just the appearance of a primary key in some other table for the purpose of relating that other table to the original table so it's foreign in the sense that。

😡，It's the same number but it's in a foreign land it's in a different table that's somehow referring back to the original table so these is just jargon but at the end of the day what's kind of nice here。

 these are just numbers and we've tossed on a bunch of terminology here in jargon but really we're just talking about reusing numbers so that we know just like my visualization with the Google spreadsheet earlier that there's a connection somehow between these two Now what about all of these data types well here's a quick summary within the world of SQL light these are really the data types you have available to you and it's not that many there is our integers for simple numbers counting up or down there's numeric which are numbers but things like dates and years and times so things that are composed of numbers but are a little different semantically there's real which are floating point values with decimal points there's text which is just text and then we haven't seen it yet but there's blobs which is wonderfully named and it stands for a binary large object it's like when you want to just store raw zeros and ones for some reason in the database so that's not an especially common case at least for our purposes V subB these。

But there's these other keywords we should keep in mind。

 some of which we've already seen like null and not null。

 which allows you to specify when creating a table what kinds of values can or cannot be there。

 And this is how a relational database differs from something like a spreadsheet generally speaking in a spreadsheet。

 There is nothing stopping you from typing or deleting any values whatsoever from any of the rows and columns。

 In fact， it's pretty easy for you or a colleague to break a spreadsheet in that way。

 but one of the features you get from a real worldorl database like SQL light and that the database software itself can prevent you or other people。

 colleagues， users from removing or adding data to your database that should not be there。

 you can specify that this column this cell in our database table cannot be null or it can be null and you can specify that it must be unique or it doesn't have to be unique。

 the database gives you those features for you。 and indeed these things called primary and foreign keys are the key to。

No pun intended relating one table's data to another table's data。

 So let's go ahead and start playing around with some of this real world data here。

 Let me go back to VS code and let's poke around。If I now do select star from ratings。

 let's go ahead and look at like some of the most popular TV shows over the years。

 Now if I just hit semico in and enter now， that's gonna give me all the ratings and that's not that useful。

 but let me do this。 let me add a where clause which we saw earlier and say where the rating is greater than or equal to maybe 6。

0 So it's better than5 So it's at least six or higher I don't really want to see hundreds or thousands of results。

 but let me go ahead and just limit this to like the first 10。

 It's not necessarily the top 10 because I'm not ordering the data。

 but for the sake of discussion I want to see 10 shows that seem to be pretty good based on their rating Allright not that useful because what the heck are these shows。

 these are all unique numbers， I don't see the offices number in here but I do see 10 show ids that I haven't yet seen Well this isn't all that useful yet。

 but let me whittle this list down instead of selecting everything let me reexecute that same query but select just the show I from ratings。

So same kind of query， but a subset of the answer that I get back。

 I just have now a temporary table containing all of those show Is。 Well， why is this useful？ Well。

 what I don't want to do is this。 if I want to know what 10 TV shows should I start watching。

 This would be incredibly tedious。 Select star from shows。 where the shows's Id equals。

 and I'll copy paste this6，26，1，4 semicolon enter。 Okay。

 so that's the first TV show that debuted in 1981 that has a pretty good rating of 6。0 or higher。

 What's the next one。 Well， let me start with that same query。

 but go back up here and copy the second I semicolon。 All right， Cat weasel。 So from 1970。

 that seems to be pretty popular， let me do it again， let me delete that I grab a third I here。

 copy paste it。 En UFO from 1970。 I mean， this is gonna take me forever。

 just to come up with my list of 10 TV shows that I should watch based on their rating。

 So there must be a better way。😊，Copy pastse is rarely if ever the solution to our problems in CS50 let alone programming more generally。

 can I automate this process somehow， but in a way that shows me useful information because I as the user。

 I really don't care about the primary keys， the foreign keys， any of those integers who cares。

 they exist solely for the purpose of uniquely identifying data in a database but I am a human and I prefer to think about TV shows by way of their titles。

 so how can I do this？😡，Well， let me go back to that earlier query whereby I got all of the show Is that are rated at least 6。

0 or a higher done。 And now let me use this as kind of a building block to answer another question as follows。

 Let me do this。 select star from shows where the I of the shows is in this earlier query。

 So here I'm gonna copy paste。 but just to save myself some keystrokes and make clear that I'm indeed using the same query is earlier。

 I'm going copy everything from earlier， paste it here without the semicolon。

 And I'm gonna move the limit 10 to the outside because what I care about is limiting the number of TV shows not the show Is per se。

 So it's almost the same。 but just like in math class， because of the parentheses。

 this is going to be executed first by the database。

 That's going give me back a list of Is where the ratings are greater than or equal to 6。0。

 And then I'm going use that list of Is。To ask the database a second question。

 the outermost question here Give me everything you know about the shows whose I is in that list of results。

 So I'm using one query inside of another。 this is known as a nested query。

 And we do this all the time and see in Python when you pass the output of one function into the input of another。

 that's all we are doing here。 So when I now hit enter。 what I should see is thank you。

 actually 10 shows titles not to mention their ids and their year and their episodes。

 and indeed notice the title notice the Is at left。 Those are the Is that we selected earlier。

 but thankfully I can see the titles now as well。 And if I don't care to see any of that other information like you in episodes。

 that's fine， let me just hit up again。 And instead of selecting star。

 let me just select what I care about all I care about is the top 10 TV shows that I should watch here and now I have just the titles as well。

 So again， even though the queries are getting a little longer。

 and I could be a little more tidy and I could move。😡，Things to the next line and so forth。

 And I'll do that as an example， but it's just composing ideas from earlier into larger and larger queries by solving smaller problems first。

 And let me do this Now。 Let me actually type this out a little more clearly without wrapping if in SQL light。

😡，Oops， let me do this。Let me go ahead。And make this multiple lines。

 So if I were to start this query as follows， select title from shows where ID in。

 but I know what I'm gonna type is actually going wrap onto multiple lines。 That's okay。

 I can hit enter here。 Not my prompt changes to an ellipsis dot dot dot。

 and then the greater than sign。 This is SQL light waiting for more of my query。

 So I'm going go ahead and copy pastte it from earlier。 And then I still haven't hit semicolon。

 I'm hitting enter just to put it onto another line， but now I want to limit it to 10。

 and now semicolon。 So I mention this because it's actually very easy to accidentally get into a weird place with SQL light。

 because if you have an open parenthesis or an open quotation mark。

 you might get the dot dot dot prompt， which just means you haven't finished your thought at least as far as SQL light is concerned。

 So you can finish your thought with the semicolon。 the parenthesis。 The quote mark， hit enter。

 And now you have a three line command， which might just be a little more readable for you。

 but still executable。 Wors case。 if you get into a weird place control C is your friend to interrupt the process somehow。

😡，To actually quit out of that query itself。All right， but there's a way now to do this。

Differently And I used this terminology earlier， wouldn't it be nice if even though we have a shows table and a ratings table and all these other tables。

 could we somehow join them back together when we want to to see more data at once。 And indeed。

 if we consider in SQL， one other keyword we can do exactly that an operative word in SQL is that of literally joining two or more tables together。

 So what do I mean by this。 Well， let's do this visually first。

 So here we have a visualization of a TV show at left and the rating thereof at right。

 And for today's purposes， I don't really care what the actual rating is or the votes were or so forth。

 So I've showed just a subset of the data herein。 But these are two separate tables。

 shows at left and ratings at right。 But notice， even though this is a tiny example。

 notice that they do have a column in common。Notice that the ID value at left is the same as the show ID at right。

 Wouldn't it be nice if I could kind of take these tables then and kind of line up those identical values and concatenate them together by kind of joining them where those Is are the same and in fact。

 just for the sake of visualization， let me propose to do this。😡。

All I did was flip the title and ID column， not because this is technically useful， but visually。

 it puts the two Is up against each other。 In fact， let me squeeze the tables closer together。

 noting that 3，8，6，6，7，6 is indeed the unique identifier and it's the same in both the shows table and the ratings table。

 So sure let's kind of shift things over。 And heck。

 I don't really need both of these values here at the same time。

 So I bet I could somehow literally join these two columns together in code。 In fact。

 let me go back to VS code and let me introduce one other technique here。

 Select star from shows join ratings。 How do I want to join those two tables left and right。

 Well please join them on the shows tables I column equaling the ratings tables show I column。😡。

And just for good measure， where the rating is greater than or equal to 6。0 and limit 10。

 So the last part there is not that useful。 It's just borrowing some of the ideas from earlier。

 What is useful here is I'm not just selecting from one table now。

 I am selecting from two tables being joined together。

 But I have to tell the database how do you want to join those together。

 Like how should those two tables be lined up。 Well。

 I want the show I column in one to line up with the show sorry。

 I want the I column in one to line up with the show I column in the other。

 So you have full control over what values are being lined up And if I hit enter。

 I will see everything together here。 the I column， the title column， the year。

 the episodes and also the duplicate show I column rating columns and Vo columns。

 which is pretty much what we just saw But my own visualization， I was keeping it simple dot dot dot。

 I don't care about most of those columns but this is what we have done with this join keyword we have created in memory a temporary table that has all。

😊，Of that data I care about。 and in fact， a bit more。 Now， at the end of the day。

 what I really only care about if I go back to my visualization here is I really only care about getting access to say the title and the rating itself。

 So if I want to whittle down this list down even further， that's actually not that hard。

 let me go back to Vs code And as always， instead of just selecting star。

 let's select what I actually care about like title comma rating。 And if that's all you want。

 so long as it's clear to the database that okay titles from over here and ratings from over here。

 so long as the column names are not duplicative， I can just refer to them by their short names enter。

 now I get back 10 TV shows that I do want to watch because all of these have ratings as you can see with your eyes that are greater than or equal to 6。

0 and there are the titles。

![](img/6a0bc78e77555613a960f4c7c09b7797_43.png)

Thereof。 So let's return now to the schema for the entire database focusing not just on the show's table and the ratings table。

 but a few others as well。 in particular， why don't we focus this time on the genres table。

 which describes whether a show is a comedy or a drama or something else along those lines。

 So let me go back to VS code here。 And let me go ahead and wrap my mind around this new table。

 So select star from genres and then let's just limit 10。

 I don't really care about everything that's in this table just want to get a quick sense of it it's actually a pretty simple table per the diagram from a moment ago whereby the genres table has two columns。

 a show I and a genre and the show I presumably refers to the I column in the show's table and genre appears to be a text field that describes the genre for that particular TV show。

 What's worth noting about the genres table is that this is not really practicing what we preached earlier because indeed I see comedy comedy comedy。

 I see it three times I see scifi twice So theres is redund。



![](img/6a0bc78e77555613a960f4c7c09b7797_45.png)

sing this table so feels like a missed opportunity to fully normalize these tables by removing those duplicates and having a whole separate table。

 much like we have a whole separate table for shows and for people themselves but more on that perhaps another time For now。

 let's go ahead and just focus on one of these TV shows that we saw earlier that of cat weasel。

 one of those earlier UK shows Let me go ahead and do select star from shows let's do select star from shows where the I of the show is this one here notice that what's curious about this show here。

63881 is that it's a comedy an adventure a comedy and a family show altogether。

 Now I happen to know what this one is， but as before let me go ahead and select by its I where I equals 63881 semicolon and indeed there's the cat weasel show that I've promised us。

 So it seems that cat weasel per the genres table actually has many genres associated with。



![](img/6a0bc78e77555613a960f4c7c09b7797_47.png)

And this is worth noting because indeed， besides one to one relationships across tables。

 you can also have one to many relationships whereby in this case。

 one show can have many genres associated with it。 So to see this， let me go back to VS code here。

 Let me clear my screen and do dot schema for genres Just to make sense of what's in there。

 And as expected， show I is an integer that can't be null that is apparently indeed a foreign key that references shows tables I column So quite like the ratings table。

 but the genre in here is indeed a textual value for which there might be duplicates。

 but it can never be null。 Allright， let's go ahead and now and see if we can't select programmatically the genres for this TV show called catweasel。

 Let me go ahead and first select the genre。

![](img/6a0bc78e77555613a960f4c7c09b7797_49.png)

From the genres table where the show I equals that same value。 Okay。

 there's that list of three values that I inferred by just looking at the top 10 list earlier。

 But indeed， this show 6，38，81 aka cat weasel has three genres Adv， comedy and family。

 So how can I go about selecting now the genres plural for this show。 Well， frankly。

 I and no one in the world should really have to know what the unique identifier is for cat weasel。

 After all， if you were to go to IMDB do co， it would be a bit crazy to have to type in the numeric identifier for a TV show。

 just to search for it。 So let's make this more like a keyword search。 let me instead say。

 select the I from the show's table where the title of the show equals quote unquote cat weasel。

 In other words， I know from earlier using select alone， I can get that unique I of cat weasel。

 and I know from earlier that I can compose more sophisticated queries by nesting one select inside。

😊，Another so let me do this。 I'm gonna copy this just so I don't have to type it all out again and let me go ahead now and select the genre column from the genres table where the show ID in question happens to equal the results of this query and now notice a subtlety previously when I nested a query。

 I actually use the preposition in because I was getting back a whole bunch of show I and I wanted to get back the title of any show whose I was in that list of IDs in this case。

 Cat weasel by definition only has one unique identifier 63881。

 so instead of saying in I'm more precisely saying equals I want to select the genre for the show that literally equals this value and SQL will accommodate that so you use in when you want to search across multiple values and use equals when you know there's just to be one If I hit enter there we have it。

I now have a query that much like my first query searches for all of the genres for the show。

 but it doesn't aranely search by a show ID。 It instead searches by the name of the show itself。

 which I'd argue is much more useful Now we can visualize what might have just happened here our simplified versions of these two tables we have the shows's table at left and the genres table at right and just for the sake of discussion。

 let me flip around the two columns just so we can see that these two things do line up even though this is not a technical thing let me kind of highlight the fact that 63881 a deed appears everywhere among these ID。

 so let's kind of nudge things closer together and let's go ahead now and ideally line up all of these common values but notice here that it's not a one to one。

 this is kind of a one to three relationship more generally known as a one to many So really when we line these columns up what's actually happening when we line these tables up what's really happening is something like this select star。

😡，From shows let's join them together on the genres with the genres table on shows do I equaling genres show ID where I equals 63881 So what have I just done here well if my goal is to sort of join this stuff together these tables together as we did earlier not using ratings but genres。

 but we want to accommodate for a one to many relationship the queries essentially the same select everything from the showss table by joining it with the genres table how to join it we'll join it on the shows do ID column and the genres show ID column so that's what I mean by kind of lining them up just right so that those numbers overlap but for the sake of discussion I only care about one TV show for today I don't I could do this for all of them but let's focus on just one and what I hit enter now notice what happens is I get per the star operator all of the columns from both of the tables including I title year and episode but also show ID and genre now the data。

base itself it's not bothering to flip things around and show me side by side like I did with my slides。

 but the idea is exactly the same when I try to join these two tables in this way。

 what's effectively happening is the database is noticing okay I've got a value at left 63881 and I got the same value at right again and again and again So effectively what's happening is the left hand tables rows are duplicated verbatim just so that when we get back a table it has the same dimensions rows and columns height in with sort of work out to the same that does mean there's a lot more duplicative data that's coming back but if you want to be able to see everything about catweasel for each and every of its genres this in this case is what the join query would be doing we get back yes duplicate data but it's fundamentally joining things in precisely the same way Now at the end of the day I probably only care about really the title and the genre so I can tighten this up if I go back to VS code here and I select only title comma。

From shows joined with genres on shows do I equals genres show I， where the I is 6，3，8，8，1。

 I'm just gonna get back a much smaller table exactly like the  one I depicted a moment ago。

 and heck， if that's even too much。 like I don't need to know the name of the show。

 if I'm already searching for it。 Well， let me hit up。 Let me go to the beginning of my query。

 And let's just get rid of title and genre。 and just select the genre。

 And now I have a list in this temporary table of all of the genres for this particular show。



![](img/6a0bc78e77555613a960f4c7c09b7797_51.png)

If we bounce back， meanwhile， to the chart itself。To the schema itself。

 there's even more tables than these。 And in fact， we won't spend time going through each and every one of them。

 but I think it's probably worth showing one of them that really represents a third and final type of relationship that you might have in this or any database of your own as well。

 a many to many relationship。 And indeed， that's the right semantics for something like TV shows and TV stars because presumably one show has many TV stars and one movie TV star is presumably if they're successful。

 going to be in many TV shows。 And so you sometimes want to have not to one to one。

 not a one to many， but a many to many relationship。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_53.png)

And to do that， it does not suffice to have just two tables like shows and ratings or shows and genres。

 you might need a third table。 and this is where we began after the break by visualizing thing in that spreadsheet temporarily when we have a shows we have a people table and maybe we have a stars table that somehow relates the first to the second So how can we go about building that let me propose that we explore the data set as follows let me go back to VS code and let's just start to poke around with the office again。

 one of my own favorite shows and let's do select star from shows where the title of the show equals quote unquote the office。

 let's just see what we know about the TV show， the office Now some of you might know the office in the US with which I'm very familiar is not the only version of the office in fact。

 the origin for it was actually a UK version several years prior。

 but I think the one that I'm most familiar with the US is probably this one that started in 2005 if only because it had 188 episodes because it ran。

For like nine years， nine seasons so that's probably the one I'm thinking about with Steve Correll。

 Rain Wilson and others。 So if I want to narrow my search results to that。

 let me start with the same query but say where the title is the office and the year equals 2005 because for today's purposes。

 just want to focus on one of these here offices Now suppose I wanted to ask a question like who starred in the office Now that question is very reasonable and honestly。

 if you go to IMDB do co and search for the office you'd probably expect to see a list of all of the TV stars in that show。

 the cast members。😡，But this data seems to be split across a shows's table。

 a people table and a stars table。 So how do I get back a simple common question。

 given what I'm proposing is very good database design。 Well。

 let me propose that we take baby steps here or small bytes out of this problem as always。

 Let's first select how about the I only from the show's table where the title of the show is the office and the year of that show is 2005。

 I don't care about all of the columns。 I only care about the I。 And I could make mental note of 38。

6，6，7，6， and then copy pastse that， But again， that's not the right way to do things。

 I should not be hard coding the Is literally when the user is going care about the titles。

 not these Is。 But suppose I want to now get everything I know about that show as it relates to people。

 Well， let me go back to the schema for these three tables。

 Notice that we have the show's table here， which has an I a title。



![](img/6a0bc78e77555613a960f4c7c09b7797_55.png)

A a number of episodes。 The people table has an ID， a name of a person and their birth year。

 but this stars table is what we might call a join table whereby its purpose in life is to implement this relationship between one and the other and that table clearly has a show I and a person I and this is where I'm now thinking in my current query I am getting the show I that I care about What I really want to know is who stard in this show。

 So I need a bunch of person I。 Well， this is the table the stars table that associates show I with person I。

 So maybe I can kind of bootstpped things and use this one show I that I just found found all of the corresponding person Is and see where that gets us。

 So let me go back to BS code and let me do this select all of the person Is from the stars table where the show I itself from that table is equal to and now I need this query from earlier。

 So let me go ahead and do this。

![](img/6a0bc78e77555613a960f4c7c09b7797_57.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_58.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_59.png)

Maybe on a second line， select I from shows where title equals the office and year equals 2005 close parenthesis。

 semicolon， In other words， I've got a nested query again per my parentheses。

 I want the unique I for the office then I want to use that show I to find all of the related person Is enter and I get back a whole bunch of person I。

 But who are these people。 One of them is probably Steve Correll wantss probably rain Wilson and so forth。

 but this is not useful information。 So let's take this home one step further。

 Let's select the name from the people table， where the I of that person is in the following query。

 Well， how do I get back all of those people Is， Well。

 person Is Let me go ahead and do select person I from stars where the show I equals。

 And now let me do another nested query。 Select I from shows where。

Title equals as before the office and year equals 2005， Close parenthesis。

 closed parentheesis semicolon。 So this must feel like a lot if you're seeing SQL for the first time。

 but realize that I'm just taking a third and final baby step。

 The first query I ever executed during this process was the last one on the screen here。

 Give me the I of the office that I know and love from 2005。

 The second line of code on the screen is the second command that I wrote before。

 whereby I want to select all of the person Is from the stars table that are associated with that show I。

 but that just gave me a list of person I， none of which I recognized visually。

 So the third and final step， which on the screen is the very top line here。

 select the name from the people table where the I of that person is in that list of person Is that I didn't recognize earlier。

 So if I didn't make any typos and I hit enter。 I should see thankfully， Creed Bret and Steve Carll。

 Jennifer Fer， Kate Flannery and so forth。😊，Some of the top stars from that their version of the office。

 So a big query to execute， but composed of smaller and hopefully seemingly simpler queries as well。

 All right， let's try one other query， not just searching for all of the stars of the TV show。

 the office。 Let's just search now conversely for all of the TV shows that Steve Corll was actually in。

 So one way I could do this is very similar in spirit。

 let me go ahead and select the title from the show's table where the I of the show is in the following list。

 select the show Id from the starss table where the person Id equals And now I need Steve Corll's own I。

 So much like I search for the office's I， let me search for Steve Corll's I as follows。

 Select I from the people table where the name of the person is quote unquote， Steve Corll。

 close parenthesis close parenthesis semicolon。 So same idea but I'm sort of searching the tables in the opposite or。

😊，To get back all of Steve Corrells shows instead of all of the office's TV stars。 Let me hit enter。

 and I get back all of the shows， according to IMDB that Steve Correll has been in。

 But theres turns out there's another way to do these kinds of queries when you do have one to three tables involved。

 you don't have to rely on subqueries alone。 If you prefer the idea of kind of joining the tables not just two but three of them you can do that as well。

 Let me do it as follows select title from shows joined with the stars table on shows do Id equaling stars show I joined once more。

 So we're sort of combining all three tables at once in your mind's eye The people table on stars person I equals people Id where name equals Steve Corll。

 Now this is a different approach where I'm explicitly joining one2 and three tables based on those common primary and foreign keys。

 but。😊，Using the join syntax this time to get back all of。All of。Steve Correll's TV shows。

 And that was actually a little slower because it turns out there's some final opportunities we're about to dive into。

 to optimize this database for faster queries。 But let me show you one last way， too。

 If that felt a little verbose， we can also search for all of Steve Corll's shows as follows。

 Select title。😊，From shows， stars and people， in other words you can tighten up a join query and specify all at once the three tables in this case that I want to select things from。

 and I don't even need to explicitly use the join keyword。

 I can do it implicitly by saying where showsDt ID equals stars。 show ID。😡。

And people ID equals starss。person ID。And name equals Steve Corll。 In other words。

 this is just a third way to express the exact same idea。

 Give me all of the titles from all of the shows that Steve Corll has been in。

 joining them really implicitly by specifying which of the columns in one table must equal the columns in other tables enter。

😡，And again， with some suspense， get back now。The same list of shows。



![](img/6a0bc78e77555613a960f4c7c09b7797_61.png)

Before we move on， let me summarize here that we have not only the tables we've looked at。

 but even one other as well， namely the writers table and if we're curious as to what that is。

 we can actually poke around too if I go back to my SQL like terminal and I do dot schema writers you'll actually see that the writers table is quite similar to the stars table because recall that the stars table associated people with shows so does the writers' table associate people with shows as well but as per this one we have a show ID and person ID but the table name itself writers connotes that the relationship therein is indeed that of writers as an aside there's probably a better way to implement even that idea because what about directors and producers and other people on a set well more on perhaps that design opportunity another time for now I think it's timely where we try to chip away at the time of these queries and perhaps others So it turns out besides just deciding when making your own relational database whether it's within an。

😡。

![](img/6a0bc78e77555613a960f4c7c09b7797_63.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_64.png)

![](img/6a0bc78e77555613a960f4c7c09b7797_65.png)

Automated import command or manually， as we the staff did in advance for the IMDB data that we downloaded in files from the internet。

 we can structure our data in the computer's memory in a way that draws inspiration from week5 of CS 50 and week3 of CS 50 where and we focused on data structures and algorithms respectively in the world of databases you the database designer can choose in advance to create indexes so to speak on your own databases so that you can speed up certain queries。

 In fact， let me go ahead and show you in my vs code environment with the same database how long it takes to execute a representative command I'm gonna go ahead and do timer do timer on which is a sQL like command that's just going count how many seconds or milliseconds it takes to run each and every one of my commands just so I can see it without having to like look at my watch and time it manually I'm gonna now do something simple like select star from shows where the title of the show equals quote unquote。

😊，The office。 So I'm just curious to know how many seconds or milliseconds does this year command take enter。

 and it's pretty fast In real time， it took definitely less than one second in real time。

 it took  point043 seconds。 So that's actually pretty darn fast。

 But I bet I can speed it up even faster。 Let me propose to do this。

 let me build my own index inside of the databases memory using syntax like this。

 create index and then the name of the index on the name of a table these column specifically In other words。

 if I'm the designer of this database。 And I know that my users are gonna be searching on the names the titles of TV shows quite a bit。

 I can in advance， tell the database to build a fancy treelike structure in its memory or ra So as to speed up searches for values therein。

 So how do I do this。 Well， let me go back to vS code， and let me simply do create index。

 I can call it anything I want， but I'll just be clear with title。😊，Underscore index。

 So I know what I'm indexing。 What table do I want to create this index on， Well， the shows's table。

 specifically the title column therein。 So here Ive specified， create an index。

 So a fancy tree like structure and memory on the show' tables title column enter。

So that itself took a decent amount of time， almost half a second。

 but that's a command I'm only going to run once。 So it's an upfront cost。

 but hereafter I can amortize that cost over many more selects。 let me go back up into my history。

 this was the exact same query we executed a moment ago， which previously took 0。043 seconds。

 but this time after creating the index。😡，0。001 seconds。 And you might have thought earlier，0。

43 was already pretty darn fast。 I mean，0。001 is an order of magnitude faster。

 What's the implication of this well， one the human users of your website or application are going to get answers much more quickly and maybe more importantly in the real world if I can handle like40 if this query is like 140th the speed of the previous query。

 I can buy 40 times fewer servers to handle my users because presumably a database server in the real world can only handle so many users at once。

 So if you speed up your query by a fact of 40， you can get away with that many fewer servers and that much less money as a result。

 So building this index in memory can be super efficient with the result in time。

 Now what's the tradeoff well， as in every discussion of efficiency thus far in design。

 there's gonna be a tradeoff。 And when you build one of these trees in memory typically known as a B tree。

 which is not a binary。😡，TreIt's literally a B tree。

 It's essentially a tree that's very short or as short as possible。

 So it's not a binary tree in that each node has only two children。

 It might have three or more children as well。 and the idea of having lots of children in this tree is that it kind of pulls the height of the tree up so it might be very wide but it's very short。

 So the amount of time it takes to get from the root node at the top to any leaf node at the bottom tends to be fairly minimalist。

 and you don't have to do any of this。 there's no pointers， there's no C code。 you。

 the developer don't have to do any of this when you create an index。

 what's happening underneath the hood is that kind of structure is being created for you instead。

 and we can really see this maybe with one of our same queries from earlier。

 let me go ahead and propose that in VS code。 I bring back one of our slower queries from before。

 Even if you're not 100% comfortable with the syntax。

 just take on faith that it's the same fairly slow query I executed a bit ago。

 select the title from the show's table， the stars。

And the people table where the showss tables ID equals starss。show ID and people ID equals starss。

 personson ID。😡，And the name equals Steve Carell。 I'm going to go ahead and hit enter。

 And because I've turned the timer on， we will now know mathematically how long this earlier query takes thinking。

 thinking， thinking。Alright， and here we have 3。483 seconds。 like that's annoyingly long。

 if you will。 Like that's gonna be annoying website waiting and waiting for the response to come back。

 And it's certainly going to cost other people time because I've got multiple users on the website。

 they too might be wanting to execute queries as well。

 just to show how impactful these indexes can be。 Let me go ahead and revisit a query from earlier and show that we can speed up even our more sophisticated queries as well。

 recall that when we're searching for all of Steve Corll shows earlier， we did this。

 select title from shows where the I of the show is in the following subquery。

 Select show Id from the stars table where the person I equals this subquery。

 select I from people where name equals Steve Correll， close parenthesis。

 close parenthesis semicolon。 I have my timer on now though So we'll see how long this one actually takes enter。

 and it's not too slow but  point215 seconds in real time。 Okay can we do better。😊。

Notice in this query， we searched on a couple of columns 1。

 I searched for Steve Correll on the name column in the people table and I also searched for the person ID column in the stars table In other words。

 when I was asking SQL to filter my results by those two wear clauses。

 person ID in name it was probably doing a lot of work and you can think back now to week3 of CS50 and even week0 of CS50 when we first implemented linear search searching the phone book page at a time or searching the lockers one at a time linear search was slow but these SQL tables are really just really tall lists of values So if you want to search for a person ID or you want to search for a name if you do not have a fancy data structure in memory already like one of these so-called B trees that an index gives you what is the database gonna do it's gonna literally search over every person ID and every name looking for the values you care about。

 So can we help the database out if I know。I'm frequently going to search on person Is and names。

 Let's create two indexes。 So let me go back to my SQL like prompt and create one index called say name index on the people tables name column because I want to search for names like Steve Correll semicoon En It's thinking thinking that took over a second。

 but it's a one time operation。 Let's create one more index called say person index on the stars tables person Id That too is gonna to take a moment。

 moment， moment，2 seconds， but it's a one time operation。 Now。

 let's rerun my earlier query remembering that previously， it took 0。215 seconds。

 And that earlier query was as before， select title from shows where the I of the show is in the following subquery。

 Select show I from stars。😊，Where person Id equals the following sub sub queryry。

 Select Id from people where name equals quote unquote。Steve Correll， close close parenthesis。

 close parentheesis， semicolon， previously again， this query took 0。215 seconds。

 but gave me all the results I cared about。 Now when I hit enter， it's instant0。001 seconds。

 So hundreds of times faster， than the previous query just by building up these indexes in memory So at the end of the day。

 what's helpful about these indexes is the massive improvement potentially in speed。

 But if we looked at how much space this database is taking up on the system。

 it's probably gonna be more space because we have to store these B trees somewhere in memory or on the servers hard drive。

 And it turns out because we've created these indexes if I go about inserting， updating。

 deleting data over time， I'm actually going slow down those operations just a little bit not by a huge amount。

 but presumably the database has got to keep this tree balanced as we've discussed in the past too so that if we insert or update or delete things。

 we make sure that the tree itself is still efficiently stored in memory。

Even though we might get massive savings with our select queries。

 we might increase the time required for some of our other operations。

 but odds are if you are a very read heavy site or application like IMDB itself probably is。

 where many more people are using the data than are changing the data。

 odds are that's going to be a net positive。😡，All right， with that said， enough about design。

 let's focus lastly on how we might use these databases and some of the problems we might run into。

 Now it turns out it's actually very common in the real world to use multiple programming languages together thus far today。

 I've been focusing really just on SQL in isolation and on Python in isolation but sometimes it turns out it would be very compelling to write a Python program that maybe takes user input but still harnesses the power in the capabilities of SQL by using SQL inside of Python and so we can actually do this by using C50's own library。

 which in addition to get ins and other such functions that we implemented for you in both C and Python in the Python library。

 we also have support for SQL databases and these aren't so much training wheels as they are just very user friendly features on top of proper SQL databases。

 that is to say it turns out that when you use a third-party library to query a SQL database。

 there's lots of functions that you might have to pick up in this language or that。C50's library。

 we do simplify it a little bit but without hiding any of the underlying functionality from you。

 And so in fact， at this URL here， if curious， you can see the documentation ultimately for CS50's own library。

 but within this library do we have functionality like that allowing us to execute SQL inside of Python。

 So let's do that let's go back to Vs code and open up favorites pi but start from scratch here and instead of importing the Cv package。

 let me go ahead and import something from CS50's zone library as follows from C50 import Sql in all caps。

 This is gonna give me access to SQL specific functionality in CS50's own library let me then create a variable called DB for short。

 but I could call it anything I want set that equal to the return value of that SQL function from CS50's library and then specify what SQL light file I want to open the syntax for this is a little weird。

 But inside of quotes what I do is pass in a string here that says follows SQL light colon favorites Db。

😊，Kd of looks like you URL， but there's a third slash in there。 follows a similar format overall。

 though。 that will take care of now opening that dot Db file in Python code instead of having to manually run SQL light 3 as I have in the past。

 Now， let's go ahead and ask the human for their favorite language， for instance。

 by creating a variable called favorite， set it equal to the return value of the input function in Python。

 which is like get string and just prompts the user for their favorite。

 Let me now call Db dot execute， which is a function or method that's inside now of that database variable。

 because of how the C 50 library open that file and execute a line of SQL from within my own Python code in particular。

 let me select how many people like a particular language based on the Cv。

 which is now in our dot Db file。 select count star。😊。

As N from favorites where language equals question mark close quote And in this case here。

 not to throw too many wild card characters at us today。

 but in the context of C50s library and in the context of a lot of SQL libraries in the real world。

 a single question mark without any quotes around it is also meant to be a placeholder for a value like the string that the human typed in。

 We don't want to use F strings， we don't want to use the curly braces。

 In this case for reasons we'll come back to。 but the question mark is a placeholder that much like percent S in printf from C we'll get plugged in with the actual favorite that the human typed in。

 Allright， Now， I want to do something with the return value of this function。

 And it turns out when you use a select statement inside of this execute function。

 what you're going to get back is a list of0 or more rows。 So if you match a row。

 you get back in a list of one row。 if you match two。😊，rows， you get back a Python list of two rows。

 If you match nothing， you get back a list with nothing in it of length0 in that case。 Now。

 if I only really care about one answer， like the first row that comes back， well。

 let's do exactly that row equals rows bracket0。 So I'm just for the sake of discussion now。

 assuming that I'm gonna get back at least one and frankly， just one row。

 So let's just grab it with row equals rows bracket0 because rows is a list but row is now a single row。

 And now what this function Dbx U does per its own documentation is it returns to you， yes。

 a list of rows， but much like the dit reader in the context of CSV files。

 each of the elements in that list of rows is itself going be a dictionary。

 And the keys for each of those dictionaries is gonna be the name of the columns from the SQL table just like the dit reader is grabbing the column names from the CSv itself。

 So lastly， let's go ahead and print out the popularity of that there language print。

Row quote unquote n， because I want to index into that one dictionary and get back the value of n。

 which to be clear was the alias that I gave to count star。

 Just so I don't have to keep typing countstar count star I can more simply and more succinctly call it n for number。

 So let me go ahead and open up my terminal window again， run Python of favorites dot pi enter。

 and my favorite say I'm I'm gonna buck the trend here。

 and I'm gonna to say that C was my favorite enter。

 What is this crazy error message that I just induced deliberately for the sake of discussion。

 So in this case here， it's underlining my entire query here under D do execute。

 And then I'm being told more specifically that there's more placeholders than values。

 So maybe a teachable moment indeed， I spend all that time talking about the placeholder value earlier。

 But what I fail to point out is how you place a value there。

 So it turns out that the Db execute method takes minimally one argument。

 The query you want to execute。😡，But ideally， one or more additional arguments for the values you want to plug into those placeholders。

 So what language am I searching for， well， whatever value is in my favorite variable which contains the string that the human just typed in a moment ago So if I now open up my terminal window and pretend that never happened by clearing my screen let me now run Python of favorites do pi again really crossing my fingers。

 that was the problem didn't do that last time enter。 I'm asked for my favorite。

 I'll type in C again enter and there is thankfully that 59 So granted it's still a decent number of lines of code。

 but notice what's not in here。 there's no more loop， there's no more dictionary reader。

 there's no more conditionals。 I have used SQL instead to just declare what question I want an answer to and I get it back in the form of some Python variables rows being a list and containing one or more dictionaries in this case。

 So hopefully that sort of demonstrates how we might combine these two languages。😡。

Indeed in the problem sets to come， we're gonna do quite a bit of this。

 but in our final moments together feels worth dwelling on some of the bad things that can happen in the world of SequL。

 much like we saw bad things in the world of sea and really any programming language as well So it turns out that in the world of sequL and really programming in general。

 you can be vulnerable to something called race conditions and the story that was once told to me was this if you're in college。

 for instance， and have one roommates and between the two of you。

 you've got one of those little refrigerators in your dormitory。

 And both of you really like something like milk and so you're determined to make sure you always have milk in the fridge Well how might you go about solving this problem if one day you come home and you realize you're out of milk。

 you open the refrigerator， you see nothing in there。

 you close the refrigerator and then you go off to the store ideally picking up a gallon of this here milk All right Well mean。

 suppose in the story that your roommate comes home opens the fridge similarly loves milk and realizes oh we're out of milk and so closes the fridge goes out and tries shopping for another jug of milk Well what happens unfortunately。

If both of you have inspected the straight of your refrigerator and made a decision based on the value therein well at some point。

 both of you are going to get home， you're going end up with two jugs of milk。

 which is way too much milk because you don't really like milk that much but that therefore is a problem So how could we have solved this here problem questionable whether these problems were compelling for this example in retrospect but more for us later The problem at hand was that both of you in the story。

 made a decision based on the value of some variable but you didn't signal to the other person that you're in the process of updating the value of that variable better would have been in this story for the first of you to lock the refrigerator physically or at least put a note on the refrigerator saying something like gone for milk to prevent the variable from being updated in duplicate if you will at the same moment of time Now asian is contrived as that story is it turns out it's representative of something that can happen quite a bit in the real world consider any popular social media application nowadays or particularly。

popular post this photo here is as of this morning。

 still the most popular post ever on Instagram based on the number of likes that it got upwards of millions but this is actually a hard problem for a company like Me in any of these social media platforms to keep track of because presumably when something goes viral online and lots of people are clicking like like like like there's a lot of potential changes to a database somewhere all at once because so many people are trying to like that post at a time and just for the sake of discussion。

 let me hypothesize that meta， the company behind Instagram maybe is using hex CSs50's library for this。

 but more specifically using Python and SQL together。

 but it's really the SQL that's germane for our discussion here。

 let me step out of the way here and note that in these lines of code。

 I'm supposing that first a company like Me is executing a SQL statement like this select the number of likes from the posts table where the idea of the post。

Question mark where question mark represents whatever the unique identifier is for this here post so that's how Facebook that's how metata is trying to figure out how many likes does the post currently get Why are they trying to do that Well if we go back to the code here they're then getting from the first row they get back from the likes column the current number of likes for that post why because the goal is to increment it simply by one so the third and final line of code here says update the post table set the likes value to this placeholder where the ID equals this placeholder and as before have unlike before I have not one but two placeholders here plugging in likes plus one so the value of the variable that we just inspected and then the ID of the post So where is the problem here Well a company like meta and any of these social media platforms has so many server so many users probably so many databases that odds are these inputs are going to be coming in it once and much like our refrigerator example odds are。

Meta is smart about this， they might potentially figure out on line one what the current number of likes is on line3 actually update that to be the number plus one but what if some other users like came into the database while these three lines of code were executing you can imagine if things are happening so quickly maybe the first line of code gets executed for me and then the first line of code get executed for you and the queries in the system essentially get interwoven somehow such that now even though two people might have clicked on like。

 they might have happened so quickly together that just as the first one is in the process of updating current number plus one。

 the other one is in the process of updating current number plus one when really the math should have been current number plus two and they both end up writing the same value instead of one that is ultimately two likes higher than it once was In other words if you have code being executed that can somehow get interrupted by other code being executed on another server maybe with the same data。

😡，ase， something called a race condition can happen much like both of us inspecting the state of the milk in the refrigerator while someone else was in the process of updating it as well。

 So it turns out with a wave of the hand。 there are features and solutions in the word of SQL to prevent this。

 and they are called transaction。 a transaction allows you to say to the database execute all of these queries or none of them。

 but it has to be all or nothing。 it is not acceptable for part of them to get executed。

 but not the others。 you can effectively therefore lock someone out of the database So it's a little fancier than that。

 but it's similar in spirit to putting a lock on the fridge or a note on the fridge to signal。

 do not make any changes to this database until my queries are entirely done rather than only partially done So here then in green is the right way to do something like this for at least meta。

 you first begin a transaction。 then you do whatever database logic you want ideally not much because you want to keep it quick and simple。

 but then at the end of your code， you commit。😡，All of those changes。

 So this is sort of like making change， making change， making change。

 but only saving the results to the database at the very end。 So it's either saved or it's not saved。

 you don't get interrupted part way through。😡。

![](img/6a0bc78e77555613a960f4c7c09b7797_67.png)

Now besides these race conditions there's another problem in the world of databases that can strike you as well known as SQL injection attacks。

 and this is actually germane to what people have been calling prompt injection attacks nowadays in the world of AI where people are trying to trick AI into misbehaving in certain ways by injecting inputs into them that they weren't expected same idea with SQL injection attacks and in fact these came long before prompt injection attacks historically with a SQL injection attack imagine taking user input via anything via something like favorite Pi or maybe something webbase so for instance。

 when Yale students log into their website， they log in here using their net ID and password when Harvard students do the same they log in using something called Harvard key in both cases there are form fields in the application or website prompting for user input but here's the catch what Harvard in this case is expecting me and anyone to do is log in with their email address and their password but what if I maliciously and very cleverly use some funky character。

😡，or punctuation in my email address that are not valid email characters。

 but they are valid SQL characters and we haven't talked much about these but single quotes are certainly valid syntax and SQL we've seen those it turns out that dash dash to hyphens are also popular as well but unlike Python and unlike C which use other symbols and SQL denotes the start of a comment so in SQL if you do dash dash anything the anything will be ignored thereafter so notice what I've done here is I've written my email address mailland atharard。

 udu single quote now let's see why this is germane so here let me hypothesize I'll take myself out of the picture is how Harvard might be implementing login to this database they have a query in their python code that says select star from users where username equals this placeholder and password equals this other placeholder and for the sake of discussion assume that username and password somehow in Python。



![](img/6a0bc78e77555613a960f4c7c09b7797_69.png)

came from those two text boxes， the username and the password field and then what Harvard does is check if I get any number of rows back that means that I found a row with that username in that password therefore let's proceed to log the user into the website or application All right all fairly reasonable but what could go wrong well here is in green the query we want to execute but let's plug in those potential values from my own form if I were to type in mailland atharvard。

 you do single quote notice what happens here and if I'm using not the placeholders but literally format strings F strings in Python So the point here will be use the placeholders use the question marks because what far too many people in the real world do is they don't use a library like CS50s they don't use something that solves this here problem here is an F string or format string and Python that formats the same string select star from users where username equals quote unquote something and password equals quote unquote something。

😡，This is why we don't use format strings for SQL because this demonstrates a SQL injection attack notice that whoever wrote this code at Harvard presumably put single quotes around the username placeholder and single quotes around the password placeholder but what if I a malicious student use a single quote or an apostrophe in my own email address what happens here well let's plug in mailin@harv。

edduu single quote now it's a little subtle but notice the fact that I added a single quote at the end of mailin@harvard。

edduu kind of closes the first quote that the Harvard programmer wrote and then I typed in dash dash but recall that dash dash means an ignore everything to the right so it doesn't matter that there's another quote it doesn't matter that there's an and that doesn't matter that there's a mention of a password I have essentially tricked the database into a treating the dash dash and everything after it as an iorable comment so logically what happens really？

😡，And I'm going gray out everything after the dash dash the database is only being asked to select star from users where the username equals mailin@harvard。

eddu everything else is ignored the same conditional comes thereafter if I get back any rows。

 log this user in and so the implication here is effectively that if you were to log into Harvard's system as mailin at Harvard。

eddu single quote you could presumably log in as me without even knowing my password because you've essentially tricked the database into ignoring everything after that username so this is a sL injection attack in the sense that you the user have injected code SQL code into my application by just typing in user input and so the takeaway here is that trusting user input bad like you should never trust user input because it could be misstyped or misspelled at best but it could be malicious input at worst you should always assume the worst unfortunately of your here。

😡，Use and somehow defend against this。 So what is the solution， The right solution here notice。

 and it's very subtle would be to escape the single quote that I typed in。

 And we saw this earlier when I had to escape the apostrophe and hello comm it's me I could encode code。

 make sure that no matter what the human types in I change any single quotes to two single quotes to escape them accordingly。

 but that's gonna to be annoying and hard to remember all the time。

 So really the right solution is to do indeed what I started out preachaching。

 which is use placeholders like question marks， which comes with CS50s library。 But again。

 this is not a CS50 thing， it is representative of how many， if not most SQL libraries out there。

 let you execute SQL code inside of another language like Python Now a little more playfully。

 this is a sort of meme that's gone around in the Internet here。

 Here's a someone's car with a crazy long license plate。

 but with a mention of drop a database table which as you might imagine drop being。😡。



![](img/6a0bc78e77555613a960f4c7c09b7797_71.png)

The keywords we mentioned earlier is sort of how you go about not just deleting data but dropping all of the data in a table and if we zoom in here。

 presumably what some hacker here is trying to do is trick some of those cameras that are on streets in various countries that try to read your license plate and if someone wrote code to read license plates that trust the user input and doesn't just allow for dash dash but allows for drop database table。

 you can do really bad damage to databases by tricking them into to executing delete or drop or any number of other commands as well and in fact。

 the final note that we thought we'd end on is this here。

 which sort of inaugurates you welcomes you into the world of educated computer citizens by name of someone called little Bobbbby tables。

 let me take myself away for just a moment and let everyone read here this。😡，XKCD。But henceforth。

 after today， if you mention little Bobby tables to most any programmer in the world with a bit of a smile。

 they should know who and what you are talking about， an allusion indeed to sQL injection attacks。

 So with all of this power， indeed， as always comes great responsibility。

 that then was sQL and willll see you next time。😊。

![](img/6a0bc78e77555613a960f4c7c09b7797_73.png)