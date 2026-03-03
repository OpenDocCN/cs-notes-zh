# 哈佛大学《计算机科学导论｜CS50 introduction to computer science 2025 Fall》 - P8：CS50 Fall 2025 - Lecture 7 - SQL.zh_en - GPT中英字幕课程资源 - BV1S8sFzFEt7

Allright， this is CS S 50。 and this is already week 7。

 wherein we introduce another programming language。

 this time known as structured query language or SQL or SQL for short。

 Now SQL as we'll see is a different sort of programming language that allows us to solve like a lot of the same kinds of problems that we've been dabbling with over the past several weeks。

 but arguably in a lot of context， it allows us to solve those problems more easily。

 indeed among the goals for today are to demonstrate that sometimes there's multiple tools that you can use to solve the same problem。

 whether it's C or Python or today's SQL， but we'll also see that SQL allows us a different sort of approach to solving problems whereas C very much so in Python to a large extent or very much procedural programming languages。

 whereby you have to write these procedures functions step by step that tell the computer what to do including loops and conditionals in all of that SQL is said to be a declarative programming language。

 which is a different sort of paradigm， whereby when you want to solve some problem。

 you essentially declare what problem。😊，You want to solve or you declare what question you have and it's up to the programming language to figure out using loops and conditionals in all of those lower level building blocks。

 how to get you the answer。 So ultimately today is all about teaching you yet another language。

 mostly so that you can learn again to teach yourself new languages and to appreciate that once you exit a class like CS50 and out there in the real world really isn't all that big a deal to pick up new programming languages。

 especially when in advance， you've seen different programming paradigms like procedural like object oriented like today declarative as well。

 but today ultimately it's also about data and so to get us started。

 we thought we'd collect some real worldorld data by asking all of you a couple of questions。

 So if on your laptop or phone， you would like to pull up this URL here。😡。

It will also exist in just a moment in Q R code form。

 So if you'd like to go to that URL there or simply scan this here Q R code with your phone。

 that's gonna lead you to a Google form for those unfamiliar。

 Google has lots of tools among which are is a tool via which you can ask people questions via forms。

 Microsoft has something similar as well。 And at that URL。

 what you'll soon see is a form that looks a little something like this among whose questions are which is your favorite language。

 at least among those we've studied thus far。 So go ahead and anonymously answered the questions you see on this form。

😊。

![](img/8b4f340d248e78d45f88a7de8bf3991a_1.png)

You'll see which is your favorite language and also which is your favorite problem in problem sets thus far。

 And meanwhile， as you might know， if you've used Google Forms yourself to collect data。

 we can move from questions here to actual responses and as people start to buzz in we'll see that the data here is starting to update in real time and Google gives us these nice graphical user interfaces or gos via which we can analyze the data and so far Python is easily the winner with 70% plus of you preferring it 11% of you wishing we were still in scratch and 18% of you in C and you'll see the responses are coming in here。

 but for our purposes today， what's more interesting than the actual answers to these questions is how we can get at the raw data。

 So among the things you can do in Google sheetets is quite literally click view in sheets which in Google Form is click on view in sheets and what this is going to allow me to do is access the underlying raw data now because Google has forms and spreadsheets。

 they sort of tied these two products together but what's especially nice about Google。



![](img/8b4f340d248e78d45f88a7de8bf3991a_3.png)

ets is that I can also download the raw data as a file。 I can download as an Excel file， a text file。

 Pdf。 But for today， we're gonna download it in a very common format known as Cv for comma separated values。

 And indeed if I go to the file menu download comma separated values。

 This is perhaps the most straightforward easiest way to get raw data out of any kind of tabular data like this to load it into code that we are about to write。

 So if you haven't buzzed in already， that's fine。 But at this point in time。

 now that I' click the button， I now have a cv file in my Mac downloads folder。

 which if I go ahead and open up here。 I can see that indeed I've got this longnamed file favorite form responses one cv。

 I'm gonna shorten that file name to just favorite do cv。

 And what I'm gonna go ahead and do is open up Vs code。 And in my file Exp。

 I'm gonna literally just drag and drop favorites cv from my Mac。

 that's gonna have the effect of uploading the file as it was at that moment in time so that we can now begin to write some code。

😊。

![](img/8b4f340d248e78d45f88a7de8bf3991a_5.png)

![](img/8b4f340d248e78d45f88a7de8bf3991a_6.png)

Using this file。 and VS code is automatically gone ahead and opened it up for me。

 And what you're looking at here is what we're gonna to start to call a flat file database。

 It's a very lightweight database in the sense that it stores a lot of data。

 and it's a flat file in the sense that it's literally just a text file。 And by convention。

 the way the data is stored in this file， is indeed by separating values with comms。

 There are other conventions as well。 But Tv is probably the de facto standard。

 but Tv is a thing for tab separated values， Pv， which is pipe separated values where you might have a vertical bar。

 essentially， these file formats try to use a character that might not appear in the actual data。

 So as to separate your rows and columns。 So indeed， if I switch back to Vs code here。

 and we take a look at the data。 you'll see that from Google sheets。

 I've been given three columns timestamp， which was automatically generated for me。

 The language as well as the problem。 And what I see here is that we had a few respondents buzz in a little early。

 very excited for today's data。 But here's the rest of them from like 1，30 PMm Eastern onward。

 and you'll seeparating separated by comms。😊，Are effectively three columns of data。

 So everything before the first column represents a timestamp。

 Everything between the first and second comma represents the choice of language that you all buzzed in with。

 and then everything after the second comma represents the problem。

 Now it's kind of jagged edges that doesn't line up in nice rows and columns because some answers are longer。

 some answers are shorter， but the comms are sufficient to tell the code we write where one column ends and the next one begins。

 So how do we go about writing code like this， if we now like to ask some questions about the data。

 like what is the most popular language， what is the most popular problem or conversely the least of each of those。

 Well， we could just look at the raw we could look at the original data in Google forms。

 and that's where we got the pie chart， but how is Google figuring out what the most popular answers are and what pie charts it wants to depict。

 Well， they probably wrote some code not unlike what we're about to do。

 Although we'll start with just a command line environment as always。 So within VS code。

 I'm going go ahead。And do this。 I'm gonna go ahead and open up a program called favorites dot pi。

 And let's write a program whose purpose in life is to open the CSv file。

 read it top to bottom left to right and then crunch some numbers。

 figure out what the most popular answers R to those questions。

 So I'm going go ahead and import a package that comes with Python。

 a library called the CSv library and nicely enough。

 this is just code that someone else wrote years ago that figures out how to read data from a file separating it via comma so that you and I don't have to write all of that ourselves。

 and I'm going to use this Pythonic convention with open quote unquote favorites do csv as file。

 though if I want to be super explicit that I intend only to read this file which is the default。

 I'm going go ahead and explicitly say quote unquote R just like we did in C when using F open to open a file and read mode。

 And now I'm going to do this。 I'm going to go ahead and say reader equals csv do reader file。

 So this is a Python convention whereby the CSv library comes with a function called Read。

That takes as its sole argument here， a file that has already been opened。

 and what that reader will do is figure out where all of the commas are so that I can iterate over this reader in a loop and get back row after row after row without me having to write all of the code to figure out where those comms are。

 So what I'm gonna do in this loop here in this block of code is for each row in that reader。

 let's go ahead and just print out maybe the second column， which was the language column。

 So I'm gonna to go ahead and say print row bracket1 because what we'll see is that this reader。

 which again comes with Python hands me a list a list a list for each of the rows where in bracket0 would represent the first column。

 bracket1 would represent the second bracket2 would represent the third because everything is zero indexed in Python。

 Allright， so let's see what the effect is here。 Let me maximize my terminal window。

 run Python of favorite do pi cross my finger。that I got this right and voila。

 there is every language that was selected by you all in the form from top to bottom by default chronologically。

 but there's a bit of a bug， I dare say let me scroll up and up and up in this output。😡。

Through all of these answers。Until I get to the very top where I ran the program myself。

 which is here， Python of favorite stop pi， there's a minor bug here。😡，What's the bug in the output？

Yeah， it accidentally includes the header， which is a bug in the sense that I really just wanted to see the languages。

 But the code is doing what I told it to， which is just print out every row。

 So there's a few ways we could ignore this。 Let me go ahead and minimize my terminal window and let me go ahead and say。

 one， you know what， after we create this reader， let's just skip to the next。

Let's just skip to the next row and ignore it effectively and then begin iterating over everything thereafter。

 and so what happens now is if I remaximize my window rerun Python of favorite do pi enter and now scroll up again to the beginning of this incarnation of the program you'll see that the very first thing I see after my program was run was indeed Python Python Python Python and so forth。

 no more quote unquote language so how is that well this is a feature we haven't quite seen before or talked about in much detail。

 but this reader is stateful in some sense and this was actually true of all of the file Io we didn't see whereby when you were using Fread or some other function to read data from the file something was remembering where it was in the file so that you didn't get the same bytes again and again and again it was more like a cassette tape。

 an oldscho casette tape if you will or a scrubber along the bar。

On the bottom of like any streaming video， whereby when you just read some data。

 it grabs the next chunk， the next chunk， the next chunk the next chunk。

 and something inside of the computer's memory remembers where it is。

 So this says skip to the next row。 And thus when you do four row in reader， you get everything。

 but the first row because the reader is stateful。 It remembers where it is in memory。 Allright。

 Well， thus far， this isn't all that useful because all I'm doing is just printing out the data。

 But let's take a step toward making this program a little more useful in particular。

 let's just be a little more pedantic。 and specify that what I'm really doing here inside of this loop is figuring out what the current rows favorite is。

 So I'm gonna create a variable called favorite and set that equal to row bracket1。

 And then even though this doesn't change the functionality， I'm gonna print that favorite。

 just because semantically stylistically， it's nice to know what row bracket1 is as by defining a variable that tells me or anyone else who reads this code in the future。

 what it's actually doing。 Allright， But readers are。😊，Only so useful。 And in fact。

 if I were to open up this CV file， maybe in Microsoft Excel or Apple numbers or Google sheetets again。

 you could imagine someone kind of moving the data by just dragging one of the columns to the left or the right such that now it's no longer timestamp language problem。

 Maybe it's timestamp problem language or maybe timest is all the way over to the right。

 you could imagine therefore that the indices we're using 01 and 2 could be a little fragile。

 because if someone changes the data on me now， my code is just going break because I am blindly assuming that the second column aka bracket 1 is going to be the language column。

 but that might not be the case。 but there's an alternative to this and you might recall having seen this before。

 I'm going go into favorite stop and tweak my code a little bit。

 not just to use a reader but a dictionary reader。 So I'm going change this to diict reader instead of just reader and then the upside of using a dictionary reader is that every time I go through this loop reading row by row by row。

 each row that I'm。Handed by this reader is not going to be a list anymore that's numerically indexed with zeros and ones and twos。

 Each row is going to be， as you might guess， a。A dictionary。

 which is a collection of key value pairs， which means now we can use words as our indices instead of just numbers。

 which is to say if I switch from reader， which gives me lists to dit reader。

 which gives me dictionaries， I can change this line 10 now and say。

 I specifically want the language column wherever it is all the way to the left or the middle or the right。

 So in general， using a dictionary reader is probably just going to be more robust because it's resilient against changes in that actual numeric ordering。

 let me pause here to see first， if there's any questions on this exercise。

 whose purpose in life is just to demonstrate how we can download the CV data。

 then iterate over it line by line without actually analyzing it yet。😊，No okay。

 so let's ask maybe the most natural question which is like how many people prefer Python。

 How many people prefer C or scratch in turn。 In other words， how can we recreate in our own code。

 what Google forms is doing for us graphically with those pie charts。 Well。

 I think what we could do is write some code logically that essentially relies on this mental model。

 What I have here is an opportunity to use a bunch of key value pairs。

 because if I want to know how many instances of Python there are and C and scratch， Well。

 those might as well be three keys， the values of which are hopefully gonna to be three numbers that represent the count of the popularity of each of those languages。

 So in memory， I essentially want to construct something that looks like this and would。

 if we were doing this on a chalkboard， but recall that this mental model maps perfectly to the notion of a Python dictionary because a dictionary in Python is indeed key value pairs。

 and we've seen it already because that's how the dictionary reader works。

 But we could certainly use our own dictionaries to solve this same problem ourselves。

So the goal at hand is to count the number of people who said Python and C and scratch respectively。

 So how to do this。 Well， I think what I could do is actually let me delete this line because we are using a dictionary reader。

 we no longer need to skip the first row。 It is automatically consumed by the dictionary reader for us So this now would be the better version of the dictionary reader let's go ahead and do this。

 let me declare some variables first that will store for me the total number of people who said Python scratch and C respectively。

 So I could say scratch equals 0 C equals 0ython equals0 and I could just set three variables equal to 0。

0 and0。 if you haven't seen it before， there are some pythonic tricks you can do here if you've got three variables that you want to initialize all at once because it's that simple。

 you could alternatively do scratch comma C comma Pth equals 0 comma 0 comma 0 This too would have the intended effect and it looks a little better because it's all a simple one liner but what do I want to do now Well down here。

LetGo ahead and do a simple conditional before we enhance this by using an actual dictionary。

 Let me go ahead and say if the current favorite in that reader equals equals scratch。 Well。

 let's go ahead and increment。 the scratch variable by doing plus equals  one。

 as we saw last time else if the favorite in the current row equals equals unquote C。 Well。

 let's go ahead and then increment the C variable by one else if the favorite equals equals Python。

 then let's go ahead and increment plus equalsython by one instead。

 I could technically get away with saying else here。 but I'm consciously this time。

 not trying to over optimizeimize this。 because if someone changes the form maybe next semester and whatnot And we're asking about a fourth language。

 I wouldn't want my code to assume that anything that isn't scratch or C must be Python when there could be some future fourth language。

 So this is a little more robust。 And in this case。

 we'll just ignore anything that isn't scratch or C or Python。😊，Allright， at the end of this。

 let's go ahead and not just print out the favorite， but outside of the for loop。

 let's go ahead and print out， for instance， the scratch count is this then let's go ahead and print out the C count is this and then let's print out the Python count is this。

 but of course there's a subtle bug here yeah。So I didn't format these things。 It's F strings。

 So I need the little F over here to the left of each of these strings。 Allright。

 so let me go ahead and maximize my terminal window。

 run Python of this version of favorite stop high。 And hopefully what we'll see is not every row again and again and again。

 but three lines of output， giving me the total counts instead。Alright。

 this seems to line up with the rough percentages that we saw coming in earlier on Google Forms。

19 of you like Python， followed by 58 of you and C and 24 of you preferring Po scratch instead。

 Alright， But why does this perhaps rub you the wrong way。

 I already alluded to the fact that we're going get rid of this。

But why is this not the best design just using three variables like this， yeah。アイ？标速。Yeah， exactly。

 if we were to add a bunch more languages， a fourth one， a fifth one， a sixth one， a 10th one。

 a 20th one， like having that many variables is just certainly gonna to look unwieldy。

 and it's just not gonna it shouldn't rub you the right way。 at that point。

 we should really be graduating to some proper data structure。

 whether it was an array and see or better still in Python an actual dictionary。

 So let's do that instead， let me go ahead and in a newer version of this file。

 let's get rid of these individual variables and let's just have a generic variable called counts。

 for instance， and set it equal to an empty dictionary And just using two curly braces will give me an empty dictionary。

 or if you want to be more pedantic， you can actually call the diict function。

 which will return to you in empty dictionary， I'd argue。

 though that most people would probably just use the double curly braces like this to indicate that here comes a dictionary for me。

 Now， how do I use this。 while I don't need to update three separate variables。

 I think I could just do something like this。 I could say once I've determined what the current row favorite value is for language。

😊，I could say counts bracket favorite。 So use the current string as an index into the dictionary。

 So it's going to be quote unquote， scratch or C or Python。 and then just increment that by one。

 And then down here， we don't have these variables anymore。 So I'm going to go ahead instead say。

How about this， We'll use a loop for each favorite in those counts。

 Let's go ahead and print out how about the favorite value and the counts thereof without any F string for now。

Okay， so the only thing that's different is I'm using a dictionary here。

 which is essentially the code version of this two column chart。

 whose keys are going to be the favorite strings scratch or see or Python。

 The values of which are going to be the actual counts。 And I'm just doing some simple math by plus。

 plus saying or incrementing the count each time I see a certain language。 Unfortunately。

 this code is not quite going to work。 Let me go ahead and run Python of favorite stop pi and。😊。

Dang it， there's a key error。😡，Let me minimize the terminal window so we can see both at once。

 Why is there a key error， Apparently on line 11， wherein I'm indexing into the counts。Allray。

 dictionary。What's going on， yeah。Yeah， it's a little subtle。

 But if this is like the very first time through the file， there is no key Python。

 There is no key C or scratch， because no one has put them there。

 And yet recall that plus equal means you're going to that location in the dictionary and just blindly incrementing it。

 but what is it， Well， it's effectively a garbage value。

 but it's not even that because there's no actual key there。

 So we need to do a little bit of logic here。 And we can solve this in a couple of ways。 Well。

 I could say something very pedantically like this， I could just say， well。

 if this favorite is in the counts dictionary。 This is the pythonic way to ask that question。

 is this key in this dictionary。 If so， well， then it's safe to go ahead and increment it just as I've done before。

 But if it's not what I think I want to do is set counts favorite equal to。1， instead。

 because either I want to increment the current count by one or this is the first time logic light I've seen this favorite。

 So I want to set it equal to1 instead， we could do this a different way logically。

 just like we couldnt C， solve problems differently。 I could instead say something like this。

 I could get rid of all this code， and just say if favorite not in count。

 then I could say count bracket favorite equals0。 So just always initialize it to 0 if it's not there。

 now I can safely blindly update the count by one， because now I know no matter what once I get to line 13。

 that count is actually there。 Allright， so let's see with this version of the code。

 let's go ahead and clear my terminal window， rerun Python of favorite do pi cross my fingers and there we go。

 Python and scratch and C interestingly， the order switched around this time。😡。

Based on the order in which I was inserting things into the dictionary。

 but we'll see how we can exercise a bit more control over that。

 But let me propose that that key error recall， we discussed briefly last week that whenever you have these kinds of trace backs that refer to certain exceptions like exceptionally bad situations that can happen。

 you can also change your code to just try to do something and then try to catch the exception instead So on alternative way to do what we initially did would be this instead of just blindly saying go into the counts dictionary index into it at the favorite key and increment it by one what we could do is try to do that。

 please except if there is a key error in which case。

 you know what go ahead and just initialize that value to one instead So in there's like four different ways already to solve the same problem。

 whichever way you prefer is quite reasonable， this is just another way and arguably another pythonic way to do things by trying to do something but anticipating that something in fact。

 can go。ron。A while ago we？Correct， a while ago。 I removed next Read because that was only necessary for CV dot reader because that was just reading every row again and again。

 But when you use a CV dictionary reader， that automatically consumes the first row。

 because that's how the dictionary reader knows what the columns will be called。

 And so you don't have to skip over it Instead， a nice enhancement。 Other questions。On what？

We' have just done。Here。Al right， so let me propose that like writing this amount of code is kind of annoying just to ask a relatively simple question。

 like what's the most popular language in this file， right it's nice。

 It's sort of a step backwards from Google spreadsheets and Apple numbers and Microsoft Excel where you could really just like highlight the column。

 and it would just tell you the answer usually in the bottom righthand corner or you could use function in one of those spreadsheet tools to ask the same question。

 So it's starting to feel like with almost 20 lines of code like maybe there's a better way。

 And I dare say there is rather than use a flat file database。

 Let's graduate already to what the world calls a relational database and a relational database is simply data in which you define relations among your data。

 which isn't so much relevant now， except that that timestamp is associated with that language is associated with that favorite problem as well。

 But we'll see that datas can be much more much larger and more complicated。

 And it might be valuable if we can actually express relation。😊，Across multiple pieces of data。

 In particular， let's introduce already a programming language called structured query language or SQl for short。

 A A SqL。 and SQL essentially only has four fundamental operation。

 So even though we're transitioning into a new language， by the end of today。

 we're going transition out of the new language because there's only so much you can do Now。

 as with any language， it's going to take time in practice to sort of get the hang of it。

 but take comfort in knowing that SQL really just supports four fundamental operations。

 And the acronym that the world uses is indeed crud， which stands for create read， update and delete。

 that is to say when using a relational database， you can create data， read data。

 update the data or delete data。 And that's pretty comprehensive as to what's possible。 Now。

 what is an actual database。 Well， generally speaking。

 a database is just a piece of software that's running on a computer somewhere inside of which is stored a whole lot of data。

 And that database therefore provides you with access to that data at any time。

 whether it's on your local macro PC。😊，somewhere in the cloud or to a whole cluster of web servers。

 which we'll talk about in the weeks to come as we transition from command line tools to the web Now。

 technically in SQL， the commands you actually use to implement this idea of creating data。

 reading data， updating and deleting data is almost the same。

 but for whatever reason the world chose the command select which is equivalent to reading data so we will'll soon see that there's a command in SQL that lets us select data。

 which is equivalent to this idea of reading it， whereas the other three options refer， of course。

 to writing data that is changing data technically speaking。

 we'll be able to insert data into a database will soon see and we'll also be able to drop data altogether。

 not just delete individual rows， but whole tables so to speak of rows instead。😡。

So what does this all mean Well， let's go ahead and do say an example of using SQL to ask some relatively simple questions and begin to develop some muscle memory for using this new language。

 if I were to manually load a bunch of data into a proper database for SQL。

 I would actually use code like this。 I would literally type create table that Id come up with the name of the table。

 aka sheet and then I would specify every column that I want to put in that table。

 and here's where the vernacular changes。 So whereas in the world of spreadsheets， you have sheets。

 tabs that contain rows and columns in the world of databases。 you have tables。

 which are just rows and columns， it's different terminology。

 but it refers to conceptually the same thing in CS50。

 we're going to use a specific version of SQL known as SQL light。

 which is like a lightweight version of SQL that's actually very commonly used in web applications in mobile applications。

 but it doesn't have all of the bells and whistles or all of the scalability that your oracle。

 SQL servers， Microsoft access。Pogres， mySQL， those are just product names。

 open source and commercial like， which you've ever heard of， just represent bigger。

 faster versions of SQL databases， but will indeed use the lightweight version of it known as SQL light and the command we're going to start to run is quite literally SQL light 3。

 which is version3 of the same command， which we've preinstalled into your code spaces for you。

 So let's go ahead and do this。 Let me go ahead and run a command called SQLL3。

 which is going to let me create my very first SQL light database。

 and I'm going to import into that database， the CSv file that we downloaded from Google forms。

 In other words， I'm going to load that same data into a different program and actual database so that I can use a completely different programming language to ask questions about it instead of writing as we just did some Python code。

 So let me go back into VS code here。 let me close my CSV file and my Python file。

 Let me reopen my terminal window and let me go ahead and run。😊，SQL light3 space。

 and then the name I want to give to this database， which， for instance。

 will be favorites dot Db for database by convention enter I'm going to be prompted to make sure I want to create this new file why for yes。

 enter and now I'm inside of the database running a command at a prompt thats now says SQL light and then an angle bracket。

 I'm not going to be using any dot SQL files for now。

 although you can actually write SQL code in separate text files。

 I'm actually going use the databases interactive interpreter to just run all of the commands I want interactively by just typing them out semicolon enter type it out semicolon enter back and forth。

 but you can save all of these commands as you'll see in problem set7 in files as well Now how do I go about actually importing that CSv file into this lightweight database Well for this I'm going to execute three commands。

 and any command in SQL light that starts with a dot is specific to SQL light。

 this lightweight version of SQL Anything that doesn't start with a dot is generalizable。

And we'll work on most any SQL database anywhere in the world， no matter the product you're using。

So I'm gonna go ahead and in my SQL light terminal。

 I'm gonna change my mode to CSv mode just to tell the database that I want to load some Cv data。

 I'm gonna then literally import that data from a file called favorites do cv。

 which is the file we downloaded earlier and then uploaded to my code space。

 And now I have to specify the name of a table， So I'm gonna call this table aka sheet favorites just to keep everything consistent。

 and that's it in the absence of an error message， everything probably worked fine。

 I'm going do quit that quits out of SQL light， but what you'll now see if I type Ls is that not only do I have favorites do cv。

 which I uploaded favorites do pi， which we wrote a few minutes ago。

 but I also now have favorites do db， which is a database version of that same file。

 Now I can't actually see what's inside of it because if I go ahead and run code of favorites Db I'm going see this file is not displayed in the text editor。

 because it is either binary or uses an unsupported text encoding。 This is to be expected。😊。

Because this database is stored essentially in the form of zeros and ones that the SQLL 3 program knows how to read。

 but is not something that VS code can just show me everything they're in。

 And generally storing data in binary is going to be more efficient than storing things purely textually because we're going to be able to use various data structures and algorithms that we've been talking about for weeks more easily on that binary data。

 Allright， so let's go ahead now and see what this import command did。 I'm going to again。

 maximize my terminal window。 I'm going to go ahead and run SQL light 3 again。

 passing in favorites do Db enter。 This time it already exists。

 So it just opened it without prompting me。 And now I'm going to go ahead and type another SQL light specific command called dot schema。

 The schema of a database is just the design of the database。 What does it look like。

 What are the rows and columns and tables thererein。 So if I type dot schema。

 What I'm going to see is this SQL command， create table， if not exist。😊，Qu unquote favorites。

 which is the name of the table。 Then in parentheses， they are going to be apparently three columns。

 one of which is called timestamp， the next of which is called language。

 the third of which is called problem。 And each of those columns is gonna be raw text。

 Now we'll soon see that it doesn't have to just be text。 But when I use the dot import command。

 this is the default table， that SQL light created for me soon。

 we'll see that I can exercise more control， especially over the types of data that I'm putting in this database。

 But what's really nice about the dot import command is it could not be easier to convert a CV file to a SQL light database so that now。

 as we're about to see， we can use SQL on it。 instead of Python or any other language instead。Okay。

 so how do we go about getting data from this database？ Well。

 the first of our commands that we'll explore is that one called select to select data means to read data from the database。

 And in this sense， it's going to be a declarative language because I'm just going to declare what data I want to select from the database。

 and I'm not going to worry about opening the file anymore or iterating over it with a for loop or a while loop or defining variables of the like。

 I'm just going to select syntactically what I want。 So let me go back to SQL light here。

 let me clear my terminal just to get rid of the past commands。 and let's do the first of these。

 select star from favorites。 and I regret to say the semicolon is back for the SQL code we're now writing enter。

 and we will see a sort of ASI art version now， So even better than the raw CSv file of all of the data that was inputted into this table。

 So select star from favorites is apparently selecting everything So the star in this context is。

AWil card of sorts that represents all of the columns in the table。

 The table itself is called favorites， so I'm selecting all of the columns from the table called favorites。

 and here you have it with sort of simple ASI art， first column， second column。

 third column chronologically listed because that's exactly how it was loaded into the database。😡。

Alright， so if star is wildcard， what more can we do。 Well。

 if you don't care about all of the columns， you can actually be a little more specific。

 So I could say instead select just the language column from the favorites table， semicolonlon enter。

 And now I have just a single column of data that shows me one cell for every submission but not the timestamp or the favorite problem that that person put in。

 or if I want to declare that I want a couple of columns， so I can say select language and problem。

 but I don't care about the timestamp from favorites as such， and now you get two columns instead。

 So in short， rather than write the dozen or so lines of code that we earlier did with Python to open the file and then iterate over it with a reader。

 we just select what data we want from this here database。

 But even more powerfully SQL comes with a whole bunch of functions built in quite like the spreadsheet software that you and I are already familiar with in the real world like Excel and numbers and Google sheetets。

SQL light comes with an average function， a count function， distinct lower min Max min uppercase。

 and so forth。 There's a whole list of them。 We'll play around with just a couple of these。

 If we want to transform some of this data， let me go back into V S code。

 clear my SQL light terminal。 And suppose I just want to get the total number of rows in the favorites table。

 Like how many people at the moment in time， I downloaded the file。

 even if not everyone had quite buzzed in yet。 did I end up with in that file， Well。

 I could say select the count of all of the rows from the favorites table。 semicolon。

 And now I'll get back a single cell， which gives me 272 submissions had come in the moment I downloaded that file。

 Supp I want to see just to confirm that no one submitted bogus data。

 which languages were actually among those typed in Well。

 I can select only the distinct languages that were typed in from the favorites table and now I get a unique list of languages that everyone buzzed in with irrespective of how many times。

😊，If I want to maybe get how many distinct languages there are， if it's not as obvious as three here。

 I could select the count of distinct languages from the favorites table。

 and that would just tell me the answer 3 is the total number of languages that are distinct in that submission。

 So again， it's easy to just eyeball this， but very quickly with single statements that are sort of English like left to right is enabling me to select the answers I want to some of these problems。

 Well， what more can SQL do。 Well， here is a bunch of other keywords that we can add to our SQL commands that allow us to control further what kind of data we're going get back。

 We're going be able to group data by similar values We're going to check for not not just string of equality。

 but for fuzzy matching， checking if something is close to a string that we're looking for。

 We can limit the total number of rows coming back。

 we can order or sort the data by a certain column and we can actually have predicate。 So to speak。

 using a aware， which is similar in spirit to an if condition。

But a little more succinctly written instead。 So for instance， let me go back to VS code here。

 Let me clear my terminal again and let me go ahead and select how many of you answered C is your favorite language without selecting all of the counts again。

 Let's just hit the nail on the head。 So let's select the count of rows from the favorite table where the language selected equals quote unquote C semicolon。

 And I get back a simple answer 58 of you buzzed in with the answer C。

 how many of you liked both C and very specifically the problem called hello world。

 if you sort of that was the extent of your sort of the passion for code。

 let's go ahead and select the count of star from favorites where the language you typed in equals quote unquote C and the problem you typed in equals quote unote hellello comma world semicolon。

 And it looks like five of you said your favorite language was C and your favorite program was hello world。

😊，Great， allright， so it's getting a little more interesting。

 What about the other version of hellello world where we called it。 hellello， it's me。 Well。

 that one's interesting because I think it's gonna break my convention of using single quotes。

 which would be convention here in SQL。 whenever you're using a raw string。

 single quotes here would be the norm。 But let's type this out。

 So select count of star from favorites where language equals quote unquote C and the problem this time equals quote unquote hello。

 it's me。 So at a glance， this is probably gonna to confuse sQL light 3。

 because does that middle apostrophe belong to the first one or the second one， this is ambiguous。

 And this is weird in C， we would solve this problem by putting a backslash in front of it and socalled escape character。

 different languages have different conventions。 This one's a little weird。 But in sQL light。

 what you instead do is doubly single quote So putting two single quotes is the convention for escaping a single quote。

 just because。😊，You gotta remember or Google these kinds of things in the real world if you forget。

 enter now I get back that。 So it was not the case that any of you liked both C and that problem specifically。

 Well what if we want to be a little more inclusive of either hello problem Well I could do this in this way just like in my codespaces terminal I can go up and down to go back through my history same thing in SQL lights so I can go back two commands to get up here and let me go ahead and write something longer where the problem is hello world or the problem equals quote unquote hello it's double apostrophe me single apostrophe semicol and parenthesis So it's wrapped onto two lines here。

 So it's a little messy， but I'm just logically saying where you buzzed in with C as your language and a problem of hello world or a problem of hello it's me enter it should be the same answer as before。

 because none of you liked hello it's me， but I chose this syntax because I can actually make this。

A little cleaner。 I can go and delete this whole parenthetical and just say where language you will see。

 And the problem is like， quote unquote hello comma percent sign， single quote semicolon。

 So this is a little weird too。 It's just how SQL does this instead。 But whereas previously。

 I was using an equal sign to check for literal string equality。

 like literally those problem names like allows me to use wildcard。

 And it's not a wild card quite like the previous use of the asterisk that we saw when you are using a wild card in a string in sQL。

 you say percent sign to represent0 or more characters there。

 So hello comma space percent is going to hopefully match this or the other problem that started with hello comma。

 So let me go ahead now。😊，And hit enter， the answer is still going to be the same， but indeed。

 it's demonstrative that that is how you could express yourself a little more generally if you wanted a pattern match like that。

Questions now on any of these techniques， yeah。

![](img/8b4f340d248e78d45f88a7de8bf3991a_8.png)

good question。 does it have to be capitalized when doing string equality， yes， but not with like。

 like will tolerate case insensitivity， So uppercase or lowercase。But like select。Oh， I see。

 good question。 So the capitalization。 So styyllistically in SQL。

 I would argue and this is a stylistic convention in SQL。

 certainly for CS 50 and also for a lot of companies and communities in the world， to uppercase。

 your SQL keywords just to make them stand out from words that you and I chose as like the name of the table or the name of the columns therein。

 this is just a convention， I would propose like always to be consistent。

 but for CS 50 and for style 50s sake I would propose that you indeed capitalize like this。

 And frankly， it just makes it easier to read to my eye because the SQL stuff jumps out and then the lowercase stuff is specific to your data。

😊，A good question。Alright， how about another set of keywords that we saw on the screen earlier。

 namely grouping by。 Well， suppose we have a data set like this whereby，ops。

 we suppose we have a data set like this， whereby。How' does this go。Happy Halloween。

Whereby here's just an excerpt from that table。 So as languages go， say one of you like C。

 two of you like or three of you like Python。 And then now that we're introducing SQL。

 let's imagine that two of you now like SQL even better。 So that's the extent of the data。

 Wouldn't it be nice to be able to figure out how many of you like C or Python or SQL。 Well。

 I could write some python code open the file， iterate over it using variables using a dictionary and those 20 or so lines of code。

 we wrote earlier to answer this question， wouldn't it be nice to just ask the SQL language to figure out how many of you like C。

 How many of you like Python， How many of you like SQL。

 we can do this by grouping these cells by common values。

 let's group all the python rows together and all of the SQL rows together。

 And even though there's just one all of the C rows as well。 So how can we do this。 Well。

 let me go back to Vs code here and clear my terminal， and let's do this。

 Let's select every language。 But it's respective count as well。From the favorites table。

 But before you do any of that， group everything by language。

 So this one takes a little more practice in getting used to。

 but this is simply saying select all of the is saying look at the languages essentially group all of the common languages together and then figure out what count that gives you for all of the grouped rows。

 If I hit enter here， we'll get an answer just like the Python code that took me 20 lines of code to write earlier。

 What's really happening though in the database is something a little bit like this。 notice。

 of course， that there's only one version of C， there's then three versions of Python and there's two examples of SQL。

 and the table I'm essentially building is to group all of those by identical values and then spit out the total counts here。

 Now on the screen It's just  one3 and 2 in the data with some 200 plus responses。

 we have much larger answers including scratch instead of SQL right here。

 But this now sort of speaks to just how much more convenient。

 it is to if you want to ask a question like that， especially for the data is more than。😊。

Couple hundred rows。 If your boss， for instance， in the real world has a CV data set and wants you to analyze the data。

 Well， you can literally download it， import it into SQL light， run one command and boom。

 like you've got this analysis done。 if the extent of it is just to group the data and figure out what kinds of counts you have in the data。

 All right， what else can we do。 Well， we can play around with this a bit more。

 let me go back here into V S code and propose that we could order those results more then in just the default way。

 So let's go ahead and select the language and the count from the favorites table yet again。

 let's group by language yet again But this time， let's order by the counts column in descending order。

 So it's a bit more of a mouthful and it takes some practice to memorize all of the syntax。

 But when I hit enter now， I get back the same answers。 But Python is at the very top of the list。

 Now， count star isn't necessarily all that self explanatory。 And indeed。

 it's a little annoying that I have to write out。😊，St here at top right as well as in the beginning。

 So it turns out SQL also supports aliases。 So if you want to change the temporary name of the column to be something else like n for number。

 well， then I can actually define an alias with the keyword as order by n at the end of this statement and then hit enter and get back the same results too And so if it's not sort of implicitly clear already each of these SQL select commands is essentially giving me back a temporary table。

 This is not being saved anywhere。 like now it's gone from the computer's memory once I've actually gotten my answer。

 but it's essentially returning a subset of the tables that do exist in the computer's memory because that's what the import command did for me。

 it loaded the whole data set into memory。 And now I have these temporary tables that are just containing the answers to questions I care about。

 And if you only care about the top one language。 Well， there's a limit keyword to。

 I can literally just say limit one at the end of that exact same statement enter。

 and now I've got a single answer。To my question， a single row saying Python was the most popular with 190 people selecting that。

All right， for now， I think that's enough on select， there's a few more keywords。

 but it really is just a matter of composing these building blocks， questions。

 though on these capabilities。Fundamentally。All right。 Well how about maybe inserting data instead。

 So here might be the canonical way to insert a row into a table in SQL。

 You literally say insert into then the name of the table， then in parentheses。

 the one or more columns for which you have data。 and then literally the word values。

 And then in another set of parentheses， a comma separated list of the one or more values that you want to insert into those their columns。

 So， for instance， let me go back into V S code here。 And of course。

 at the time we circulated this form a few minutes ago， we had not yet assigned problem set 7。

 but in problem set 7 is a problem called 50 Vi， which let's propose might very well be someone's favorite in a week。

 So let's go ahead and insert that row now preemptively。 let's insert into the favorite table。

Two columns， language and problem。 Why， well， I don't really care to figure out what the timestamp is in the format thereof。

 So I'm just going to omit the timestamp altogether。

 but the values I'm going to insert for this new row be are going to be quotequote sL commaqu 50 vi close close parenthesis。

 semicolon， enter。😡，Nothing bad seems to have happened。

 Let me go ahead and select star from favorites just to see what my dataset looks like now。

 And indeed， at the bottom of the file or the bottom of the table， indeed， there is that new row。

 But what's sort of noteworthy is that this isn't just blank。 there's our old friend null。

 which is not a null pointer。 It's the same word literally N U L L。

 And it refers explicitly to the absence of data。 And this is actually a nice feature because if any of you have ever used like Google spreadsheets。

 Apple numbers， Microsoft Excel and thought about or looked at cells that are blank。

 Like what does it mean if a spreadsheets cell is blank。

 Does it mean like there's literally no data there。

 Does it mean that you just don't have the data there， It's missing in some form。 Well。

 how do you address that， Well， maybe you put like nlash a in English for like not available or something like that。

 but that's kind of hackish。 And if you use N， that might mean that no one can actually type N is their answer。

 And so what's nice about SQL and database languages more generally。

 is that null signifies the conscious omission of data， It's not just a missing value。

It's consciously not there。 It's not just the empty strain， quote unquote for instance。

 So we might see different examples of that。 but what's nice now is that I can distinguish null from other values。

 And in fact， if that is not a good idea to have any data in my data set that is null for whatever reason。

 like it just looks like bogus data would nice to know who inserted that when no problem。

 we can also delete data from a table in SQL， and I can delete from the name of the table where some condition is true。

 So， for instance， if I want to delete that， I can do this in a couple of ways。

 but perhaps the simplest is to delete from。Favorites where timestamp is null。 semicolon。

 So is2 is another SQL keyword here。 And that will go ahead and delete only those rows where the timestamp is null。

 enter。 Let's do the same select command is before， enter， And voila， that row is now gone。 Be very。

 very， very careful would delete statements。 If I had foolishly done this。

 want to guess what the results would be。😊，It would delete everything。

 And like you can go go around and see actual articles of like interns at companies who had way too much access to a company database executing something like delete from favorites because they forgot the predicate。

 They hit enter too soon and boom all of the data is now gone。

 So these are very destructive commands。 And just like in the real world。

 if you don't have backups or versions of the same tables。 The data can indeed be lost forever。

 So don't do that always have your where and make sure your where is correct。 Allright。

 so well let's go ahead， maybe and suppose let's claim that maybe 50ville is gonna be a really popular problem among students so much so that it becomes overnight。

 Everyone's favorite problem。 Well， we can update the table as is here is the general syntax for updating rows in a table。

 You literally update the name of the table。 The word set and then a bunch of key value pairs。

 The column that you want to update setting it equal to the value that you want to update it to where some condition is true。

 So what does this mean concretely。😊，Well， let's say that we want to change everyone's favorite to SQL and 50 Vi。

 I could do this， update favorites， set， language equal to SQL。😡，Coma problem equal to 50 Vi。

Close quote， semicolon。 And this is where， again， it can be dangerous。 But in this case。

 I'm going to go ahead and hit enter without any predicate to filter this。

Nothing bad seems to happen。 but if I now do select star from favorite semicolon。

 all of you would seem to like 50ville。 and there is no going back to the previous version of the table unless I quit out of this and I import the whole CSv again maybe after deleting the data entirely。

 All right， so how do I get rid of all of the data。 Well。

 if you want to delete from favorites for real now， enter select star from favorites。

 we can confirm that that was a bad idea。 there's literally no data in the database anymore。

 but we can certainly restore from our actual CSv。 So in short， we've got select。 we've got insert。

 we've got update， we've got delete， we've seen create albeit automatically generate by SQL light 3。

 maybe we'll see drop and we can see drop now。 So recall that if I do dot schema。

 I can see all of the tables in this here database。 if I do drop table favorite semicolon。

 and now again， do dot schema now there is nothing in this database at all。 So that's an even worse。

Command to run unless you know and intend what you're doing。Questions then on these crud operations。

 creating reading， updating and deleteleting Yeah， here first。啊。

Why do you not do quotation marks around null。 So null is a special symbol。

 And if you put quotation marks around it， you would literally be looking for the value N， U L。

 L that maybe was the name of a language or the name of a problem or something literally in the CSV。

 We are looking for the absence of that data altogether， yeah。

Really good question because it's so easy to destroy data like this。

 Or people actively backing up their data。 short answer。 Yes， absolutelyly。

 like all of CS50s Web apps and the like are automatically backed up on some schedule。

 Even then we have to decide what that schedule is。 And if it's daily， for instance， nightly。

 we could lose up to like 23 hours，59 minutes of data in some case。

 maybe companies would therefore version their data more tightly， like every five minutes。

 every minute， although that's gonna consume a lot more space。

 but there already is this theme of trade off， certainly in computing。

 you can also implement forms of access control。 So SQL light is lightweight。

 it has no notion of username or passwords。 if you have access to the data， you can touch everything。

 But in the real world with commercial and open source software like Oracle and SQL server and Postgress and Myql。

 you actually have username and passwords and specific permissions。 So you can give users， interns。

 the ability to select data， but not update or delete or insert data or any combination thereof。

 So there are defenses。 Other questions on these here。 Crud。😊，Commands。Alright， well。

 let's transition to something a little more real world。

 Let me propose to open up how about another spreadsheet here just so that we can tinker around。

 So I'm gonna go ahead and open up a spreadsheet that I made in advance here。

 Give me just one moment。

![](img/8b4f340d248e78d45f88a7de8bf3991a_10.png)

![](img/8b4f340d248e78d45f88a7de8bf3991a_11.png)

Actually， sorry， let me get one more here。mm。

![](img/8b4f340d248e78d45f88a7de8bf3991a_13.png)

Parddon。Let's open this version three。Okay。

![](img/8b4f340d248e78d45f88a7de8bf3991a_15.png)

Okay， let's go ahead and play with some real world data。 So many of you might be familiar with IMDB。

 the Internet movie database， which is a great repository of data for movies and also TV shows and actors and the like。

 And within IMDB's website， you can actually download T SV files tab separated values of files that contain a lot of the data from that website。

 So we went ahead and did this， we then converted that T SV data into a whole bunch of SQL tables so that we can begin to play with it in the context of TV shows。

 However， let's start first with a question about how you could go about modeling data for TV shows themselves。

 So， for instance， in advance， I also created a few different spreadsheets that just allowed me to play with how I might model data。

 realwor data at that。 So the office is very popular TV show。

 the US version here is the US version here start Steve Carerell and others。

 So if I think about how IMDB or maybe just even little old me with a spreadsheet might keep track of who starred in what TV show。

😊，I might just use a Google sheet like this。 And in the first column。

 have a title column where this is the title of the show like the office。

 And then if it stars one person， I would put Steve Correll in the next column。

 But if there was a second star， I might put Ray Wilson or John or Jenna or BJ Novak here。

 column by column by column。 And I could just keep adding show after show after show after show one row per show And then however many stars that are in there。

 What might you not like about the design of this data， though， or what might start to look odd。😊，た？

Yeah， it's a little weird that we have star， star， star， star， star。

 just this repetition has tended to be bad， anytime we're copying and pasting should rub you the wrong way。

 other observations about it too。Yeah。Yeah， at the moment， I've got 1，2，3，4，5 stars。

 And there's certainly TV shows with fewer TV stars and more。 And so， okay， I can add more columns。

 I can just keep saying star star star。 but then it's gonna be a very ragged data set。

 very sparse data where there's gonna be a lot of blank cells for shows that have small casts。

 But then a lot of columns for shows that have large cast it just feels like this should be rubbing you the wrong way。

 It just feels like it's gonna get messy， especially as the number of stars let alone shows gets larger。

 Allright， well， another version of this data that I put together is this instead。

 so I didn't like the fact that I was gonna have an arbitrary number of columns based on the specific show in question。

 So here I scaled back。 and I just have a single column for title as before。

 But now a single column for star。 And I decided that if a TV show has multiple stars。 Well。

 I just put each of the stars names。 and then to the left of them specify the show that they're in。😊。

Seems to be a little better in that I've solved some of the redundancy problem。

 But I've kind of just kind of like covered up the hole in a leaky hose。

 And now another leak sprung up here， which is to say there's still a bad design。 What's bad here。

Yeah。Yeah， now I've got the office， the office， the office， the office。

 the office and that too feels like I'm wasting space。 If I manually type this in。

 odds are eventually I'm to screw up and one of these is gonna be misspelled。

 which is gonna break some things somehow So this two doesn't feel quite ideal So the third and final version I whipped up to model this data which is going to lead us to a similar design and an actual database looks a little more arcane。

 but is the right way， at least academically to do things and we'll see technologically too this is going to be a big gain。

 So here I now have a spreadsheet with three separate sheets。 One is called shows。

 which is selected at the moment。 another is called people， which is not selected yet。

 and the third of which is called stars。 What am I doing here will notice that in the show sheet I've still got the title column but I've decided to give the office a unique I much like a Harvard student has a unique I number much like an employee and a company probably has a unique employee I similarly have I given the office a unique identifier that happens to be the same as it is in IMD。

Meanwhile， for all of the people that exist in the world of TV shows， for instance， these five folks。

 I have their names as well as unique Is for them。 and those integers are unique to the people and no connection per se to the show Is just yet。

 But the third and final sheet I've whipped up is going be a sort of cross referencing sheet that allows me to associate shows with people。

 And at a glance， this looks the most arcane of the three because it's just numbers。

 it's just integers， but if you recall from a moment ago that the office's unique I was 386，67，6。

 that's how we associated that show with this person which happens to be Steve Corll and so forth。

 Now at a glance， not very useful to me the human unless I do some fancy spreadsheet stuff like v lookups of familiar the like。

 but this is a stepping stone to how proper databases do actually store data。

 What I have done here is normalize the data by eliminating all redundancies except for maximally。😊。

Some redundant integers。 And why is that。 Well， integers。

 at least we know from our days in C are gonna to be a finite length， It's gonna be 32 bit。

 maybe 64 bit， but it's always going be the same number of bits。

 And that's nice because anytime you have a fixed number of bits。

 it lends itself to storing things nicely in an array or doing binary search because everything is a predictable distance apart as opposed to strings like Steve Corll or John Kszyinsky or the names might vary in length。

 these Is for this title of the show。 And these ideass for the persons are not going to vary in length because they're all just integers。

 But of course， this spreadsheet now， much less useful because if I want to figure out who is in the office。

 Well， first， I have to figure out what show this is。 Then I have to figure out what person this is。

 and this is。 and this is， but that's where SQL is again。

 going to swoop in and allow us to solve this problem。 And indeed。

 SQL is one of the most common ways that web applications today。

 mobile applications today store any amount of data at scale。

 They are most likely not using simple CB files， they are using SQL light or myql or。😊。

res or oracle or other commercial and open source incarnations of SQL databases。

 and odds are IMDB might be using the same as well。 Alright， so let's go ahead and do this。

 I have created in advance， a file called shows do DB that contains hundreds of thousands of rows from TV shows and TV stars and other data from IMDB itself。

 And in a moment， we'll see a database that if drone is a picture looks a little something like this。

 There is going to be a people table， there is going be a shows table。

 theres going be a stars table that somehow links the two。

 There's also going be a writers table and a ratings table and a genres table。 So overnight。

 this sort of escalated quickly from just favorites。

 which was a single table to now a real worldord data that has six tables。

 But here is the relational in relational databases。 as these arrows are meant to imply right now。

 there are relationships across these several tables。 case in point。

 here is people here and we'll see in a moment that。😊，ersonIn the IMDB world has an I D number。

 a name and a year of birth。 a show in the IMDB world has a unique I， a title。

 the year at debut and a total number of episode。 But there's no mention of people and shows。

 There's no mention of shows in people。 But per the arrows。

 there's going to be this third table here stars that somehow links show Is with person Is。

 And this is where relational databases get really powerful because you can solve all of those redundancy concerns。

 and actually enable yourself to select data much more quickly instead。

 But let's focus on something simple first。 Let's focus just on the shows table。

 which pictorially might look a little something like this。 So in just a moment。

 I'm going go ahead and re V S code。 And I'm going open up instead of favorites do Db。

 I'm gonna go ahead and open up a file called shows do DB， which again， I arrived with in advance。

 So if I open up my terminal window here。 open up shows whos not with code。😊。



![](img/8b4f340d248e78d45f88a7de8bf3991a_17.png)

If I go ahead and open up with SQL light 3 shows dot Db and hit enter， I'm back at a SQL prompt。

 Let me go ahead and type dot schema shows just to show you what command created this here table。

 And it got a little more interesting already。 Notice that the table is called shows。 and it's got 1。

2，3，4 columns， the Id for each show， a title for each show。

 the year of debut for each show and the number of episodes。

 There's also clearly some mention of types and some other keywords that we haven't yet talked about。

 But let's focus now first on just what the data is。

 the best way to wrap your mind around a new data。 If someone hands you a SQL database or you've imported a Cv into a SQL database It's just select some data。

 So select star from shows， semicolon。😊，That's a lot of data flying across the screen。

 It's not very easy to see because some of the show names are apparently crazy long。

 And so it's rapping， but it's still going and going and going。

 I'm gonna hit control C to interrupt it。 Control C as with our terminals in generals， your friend。

 let's run that same command， but just limited to the first 10 shows。

 So they are the first 10 shows in the IMDB database of TV shows。

 So we've got 10 rows in this data going back to it looks like the 1970s is roughly where their data starts。

 Allright， so here's the data we have in here。 Well， how much is there。 Well。

 let's go ahead and check。 So select count star from shows semicolon。 And now we're talking。

 there's 25087 shows in this database。 And if I do the same for people select count star from people semicolon looks like there are 704315 TV stars associated with this your data。

 So here too， the data is much more interesting and much more representative of real world。😊。

Data how about the ratings。 IM DB， if unfamiliar， is also a place where you can go to check the ratings from users as to whether something is good show a good show。

 a bad show or anything in between。 So let's do dot schema ratings and I'll see that yeah。

 there's this table called ratings that as we saw briefly on the screen There's a show Id and then a rating and then the total number of votes that contributed there too。

 And again， some data types and other syntax that we'll get to before long。

 but let me go ahead and just do select star from ratings limit 10 just to get a sense of what the data is that's now what the data looks like in that table。

 So to a human at a glance， not that useful， because you don't know what those show ids are。

 But in a moment， we're gonna to see how we can reconstitute this data by linking these tables together by way of those Is and actually get answers to questions。

 So among other things。 a SQL database or a relational database more generally supports one to one relationships。

 whereby a row in one table can map to a one row。😊，Another table。

 So this is in contrast to one to many， for instance。

 So one to one means one row over here somehow relates to one row over here。 again。

 the relational in relational database。 How might we go about seeing this。 Well， first。

 here's a tour of the data types that SQL light supports。 whereas in C。

 we had a somewhat similar list and in Python that list one away at least with regard to explicit types in SQL。

 we're back to when creating our tables， explicitly stating what the types of those columns are。

 So you have integers， you have numeric， which is more of a catch all for things like times and dates and other useful real worldl data。

 you have real numbers， which are like floats with decimal points， you have text。

 which we've seen already。 And then you have blobs， which is a great name。

 which stands for binary large objects， you can actually store raw zeros and ones like files in the database generally that's frowned upon to store files。

 But there's certain times where you do want to store binary data and not pure text。

 that's it for SQL light。 There are only these five types。

Other commercial and open source SQL databases like Oracle and Mysql and Postgres and the same names I keep rattling off。

 you have even more data types than these。 So that's among the additional features you get by using other databases as well。

 There's a few keywords， though that are worth noting in SQL。

 you can specifically say when creating a table that this column cannot be null。

 if you don't want timestamp， for instance， to ever allow for null values。

 you can literally specify when creating that table， this column cannot be null。

 And if I try to insert data into that table， with a null value as by not providing a timestamp。

 the insertion will fail。 And so here's where things are different from just writing Python code or certainly using a spreadsheet。

 you can actually have built in defenses so that you and no one else messes up your data by inserting bogus or blank data accidentally。

 you can further say that things must be unique。 So every element。

 every cell in a column must be unique to ensure that you can accidentally put two things with the same I。

To Harvard Is to employee Is that are duplicates。 you can avoid that altogether。

 but more importantly， relational databases support these two concepts。

 primary keys and foreign keys， and this is where the magic really starts to happen。

 a primary key is the unique identifier for a table。

 It is the column of values that uniquely identify every row。

 So it's probably going to be the show I， the person I， the Harvard I， the employee I。

 any time you have a value， often numeric， often integral that uniquely identifies rows。

 you simply call that a primary key。 when that same I appears in another table for crossreencing purposes。

 you refer to it instead as a foreign key because that same key is over there in another table thus foreign。

 but they refer to one in the same things。 in the context of the table in which it's defined it's primary if it appears in some other table。

 it is now considered foreign。 All right， so how can we make use。Of this。 Well。

 let me go ahead and propose that we execute a few SQL commands as follows。

 If I wanted to start asking questions about ratings。 I could do something like this。

 Select star from ratings where the rating is maybe a good show。 So let's call it 6。0 or higher。

 but let's just limit this to the top 10 shows that meet that threshold enter。

 So here I now have a temporary table that gives me three columns from the ratings table， show Id。

 which is for the moment， useless identifier because I don't know what show it corresponds to。

 but the rating value in the number of votes that contributed there too。 Well。

 how might I actually get to the shows that are actually highly rated at 6。0 or higher。 Well。

 I don't need to select star。 If all I care about is these top 10。

 I can whittle this same command down to just selecting the ratings。 And now sorry， sorry。

 not the ratings。 I can whiow this table down to just selecting the show Is。

 So this is the answer to the question。 What are the top 10。TV shows whose ratings are 6。0 or higher。

 Well， from the table， these are the first 10 that come back。 How do I now select？

The shows that correspond to these values。 Here's where things can be done a few different ways。

 I could select everything I know from the show's table where the idea of the show is in the following set。

 I'm going do a parenthesis。 and then just for readability。

 I'm gonna hit enter the dot dot dot and angle bracket just means I'm continuing my thought。

 It's not executing the command yet。 What is the query I now want to run what it's gonna to be a nested query。

 I can now do the same thing as before， select the show Id from the ratings table。

 where the rating is really good， greater than or equal to 6。0。

 But let's then limit the total number of queries to just 10。 So here。

 just like in sort of grade school math， we have parentheses。

 So the first thing that's going be executing is the thing inside parentheses。

 So this is gonna get me every show Id from the ratings table that has a really good rating of 6。

0 or higher。 That's gonna return to me a column of values。

 I'm then gonna say select star from the shows table。😊。

The idea of the show is in that list of values， but only show me 10 of those is what I'm asking here。

 So what I should now see is much more useful data， namely the 10 shows that are highly rated enter。

 And indeed， I get back these 10 shows， all of whose ratings are indeed quite a bit higher。

 If I want to only care about the title。 That too I can do。 So let's do this again。

 instead of selecting star。 Let's select title from shows where the Id of the show is in the following parenthetical。

 Select show Id from ratings where the rating is greater than or equal to 6。0。

 close my parenthesis limit to 10， enter。😊，And I see the exact same thing。

 but just the nail being hit on the head。 Just give me the titles of those top several shows。

Of course， I might want to might be able to do this differently。 In other words。

 Here's the top 10 titles。 Well， what are the ratings。

 Like that's why you go to IMDB or rotten tomatoes of the like。 You want to see the actual ratings。

 not the titles or the ratings， Well， it turns out we're gonna need another technique to do that。

 namely an ability to join two tables。 And in fact， just as a teaser for this。

 if we want to start playing around with some real data。 here might be， for instance。

 excerpts from two tables。 Here's the show's table at left。

 Here's the ratings table at right or a subset thereof。

 if I want to figure out what the rating is for a given show。

 wouldn't it be nice if I could somehow like line these two tables up together。

 such that just like the tips of my finger， I line up this value with its corresponding value over here。

 cross reference of sorts。 Well， just for the sake of discussion。

 let me just kind of visually flip this around though that does nothing technically underneath the hood。

 Let me just scooch them together now after highlighting the common values， demonstrate that， well。

 wouldn't it be nice to take the shows table and join it with the ratings table。😊。

in such a way that those Is all line up and we're going to have the ability to do just this。

 This is a lot already。 And this isn't the sort of cliffhaner I' wanted to end on because who cares about joints。

 But it's gonna be cool。 But let's take our 10 minute Halloween candy break and come back in 10 for the next。

😊，All right， we' are back。So recall where we left off was essentially here。 We had these two tables。

 The showss table at left and the ratings table at right。 And the motivation here was like。

 how do we actually associate shows with their respective ratings。 because the ratings， of course。

 are not in the show's table as an aside， they could be。 And in fact。

 because this is meant to demonstrate a one to one relationship whereby every show has one rating。

 we could have just put the rating in the number of votes into the show' table。 But we chose not to。

 because IMDB actually stores their ratings as a separate TSV file。

 And so what we tried to do for parody with that is only import into a ratings table。

 The very TSV file that we had downloaded from them。 But that too would be a solution there too。

 So at this point in the story， we've got the shows table here。

 We've got the ratings table over here。 We've noticed that there are commonalities。

 There are show Is that appear in both tables and in fact， to use some of the new vernacular。

 This is the primary key。 The Id column here。 This is that same value。

 but in this context it's known as a foreign key。😊，Because it's in some other table。

 but that's gonna to be how we link these two things together。

 So how do we select for not just the office， but maybe every TV show it's respective rating Well。

 let's go back to VS code and at my SQL light prompt。

 let me go ahead and do this select star from the shows's table but let's go ahead and join the show's table with the ratings table How do I want to join these two tables together will do so on the shows tables I column being equal to the ratings tables show ID column and then go ahead and filter the results in the following way where the rating we care about should still be greater than or equal to 6。

0 and let's only limit this to the top 10 results So it's a bit more of a mouthful but what I'm doing is selecting everything from the result of joining shows and ratings on this column with this column and the rest of the predicate is as before So join is going do。

Literally that join these two tables as I have prescribed when I go ahead here and hit enter now that I have my semicolon。

 I get back a complete table containing everything from the shows table。

 Everything from the ratings table with those unique identifiers lined up Indeed。

 if you look at the primary key over here。 the I column6，2，6，1。

4 do do dot over here you have show I which came from the ratings table 6，2，6。

14 dot dot do So we've taken two tables and really joined them together。

 but we're only seeing a subset because I limited it to 10 such rows。 Now， of course。

 most of this data doesn't seem very interesting if my whole goal is just to tell me what the ratings are for these shows。

 Well， let's go ahead and encode achieve this sort of result。

 let's literally join these tables together。 let's get rid of the redundancy altogether and then really let's whittle it down to just a title column and a rating column。

 So how do we do that Well， in， I'm going to go ahead and select more specifically the title of every show and the rating of every show from the shows table。

 but。😊。

![](img/8b4f340d248e78d45f88a7de8bf3991a_19.png)

joinin it with the ratings table on shows I equaling ratings show ID。 And as before。

 I'm going to limit it to where rating is greater than or equal to 6。

0 and 10 such results enter and now I have a nice， simple。

 temporary table that in one column has the titles of these shows and in the right hand side has the ratings of the shows。

 even though those two data sets we're completely separate in two separate tables。 Indeed。

 if we think back to where this data came from。 what we've been focusing on is the showss table。

 And we've joined it with the ratings table， here's the primary key for shows。

 here's the foreign key for ratings。 and by convention notice。That we've adopted a certain。

 a certain approach。 Anything that's called Id here implies that it's a primary key。

 Anything that's something underscore Id implies that it's a foreign key。

 and the convention we adopted， which is actually quite common。

 is if the table is called shows plural。 We call the foreign key show singular underscore Id。

Different companies， different communities will have different practices。

 but we've been consistent across all of these tables with our underscore and lowercase conventions。

 yeah。Really good question。 How do all these ideas generate and relate to each other properly。 Well。

 in our case， I have no idea the Internet movie database people came up with these unique identifiers somehow。

 and we simply them into our data in practice what they probably did。 And what you will do。

 for instance， in future problem sets when generating data is you just assign an arbitrary integer starting at one。

 then 2， then 3， then 4， then5。 And you just let it auto increment all the way up。

 And you let the database ensure that you never have duplicate values。 Yeah。😊，Just。Dot do and。

I that's only to like make it look better， right there's no。Correct。

 the dot dot dot in angled bracket that you keep seeing is just the continuation prompt。

 which means I have prematurely hit enter deliberately because I want to move everything onto the next line So it doesn't wrap ugly onto multiple lines。

 It is not sQL syntax。 It's specific to sQL light 3， and it's just a continuation of the thought。

 That's all good， good observation。Yeah。Good question。 When you limit something to 10， for instance。

 Which ones do you get， you just get literally the first 10 rows from the table。

 And so it will typically be ordered if you don't use the order by keywords in the same order from which it came from those tables。

 And so you're just seeing arbitrarily the first 10 that match that predicate。

 which is rating greater than or equal to6。 We have not ordered it by rating。

 So I'm not getting like the 10。0 shows necessarily。

 I'm just getting the first 10 shows that are greater than 6。

 And the point for that is just I want to fit on the screen。

Rather than see hundreds of thousands of answers。Okay。

 so you might recall now that there were certainly other tables besides these。

 So let's see in the broader scheme， not just shows and ratings， but let's focus on genres。

 if only because genres is interesting， because there's no longer a one to one relationship。 because。

 of course， why would a show have multiple ratings， It sort of has its own rating。

 but a show could certainly belong to multiple genres。

 You could imagine a show being a comedy and a drama or a musical and a comedy or any other number of combinations of one or more genres。

 And so the way we've chosen to implement that here， too， is with a separate table called genres。

 which is not perfect。 There's gonna to be some redundancies here is that we have not yet eliminated。

 but it does indicate that we can go ahead and have multiple such values。

Associated with each and every show。 So how do we get there。 Let's focus just on this。

 Let's go back in just a moment to V S code。 and let's take a look at the schema for now genres in genres。

 we have the following a table called genres， which has two columns， a show I。

 which is an integer that cannot be null and a genre， which is text， which is also not be null。

 And now for the first time， let's actually use some of the vernacular we've introduced here we have an example explicitly in SQL that specifies when creating this table that it the show I column shall be a foreign key that references the show's tables Id column and admittedly。

 I think the syntax for creating tables is a bit of a mouthful。

 even I often have to read to look it up to remember the order of everything。

 But here we have the columns listed first and then these key constraints。

 foreign key referencing this primary key over here。 And in fact。

 let's rewind to look at the shows's table now to see from from once we came。 So if I do dot schema。

😊。

![](img/8b4f340d248e78d45f88a7de8bf3991a_21.png)

Shows， which we've done before， but waved our hand at it then we'll indeed see that shows has a primary key called IDd。

 which is an integer。 How do I know that because the very last thing in the parentheses says that the I column in this table is a primary key。

 Then we see that the title is text can't be null。 The year is numeric。

 which again I described as sort of a catch all for other realwor numeric types that aren't purely integers or real numbers per se episodes is an integer。

 both of those apparently can be null because maybe IMDb just doesn't have that data for some older shows。

 but primary key is indeed specified here。 And just for thoroughness。

 let me distinguish now genres from ratings if I do dot schema ratings again which we waved our hand at earlier。

 very similar in spirit to genres in that there's an I column that somehow references。

 the showss table and then some other column here genre in this case we had ratings and votes。

 which were reals and integers respectively， but notice this one additional constraint here。

Deliberately specified that show ID in the ratings table must be unique。

 that is to say you cannot have the same show ID more than once in the ratings table why because I indeed wanted a one to one relationship and it would not be one to one if there were multiple show IDs that correspond to one ID in the show's table itself。

😡，But genres， we're going to allow that it can be duplicates。

 And so we don't have mention of unique there。 Al right， so where does this get us。 Well。

 let me go back into my terminal here after clearing all of that。

 And let's go ahead and just see the data to wrap our mind around it a little more real。

 So select star from genres limit 10 just to see the first 10。 All right。

 so it looks like there's some comedies， Advs， comedies， family action scifi and so forth。 Well。

 let's go ahead and look up just one shows information， In fact。

 I saw this this I before about let's just look up this show。 What is this adventure show6，3，8，81。

 So select star from shows where Id equals 63，8，81 semicolon。 Okay。

 so this is the show called cat weasel from 1970， which had 26 episodes in total。

 And that was indeed， it's unique identifier。 So that's all fine and good。

 if I want to see something about that specific show， But as before。

 how do I associate cat weasel in this case with all of。😊，Gs， well。

 instead of it being a one to one relationship necessarily。

 maybe cat weasel is not just an adventure。 Maybe it's also a comedy and a family show。 And indeed。

 if I go back to the results just now， you'll see that 6，8，1，1，1。 indeed lines up with adventure。

 comedy and family and then the Id changes to be about some other show。

 So how do I select these three answers to the question。 What genre is cat weasel。 Well， for this。

 we need to talk about one to many relationships and how we can get those back。 Well。

 let's go ahead and do this now in my terminal。 Let me go ahead and say。😊。

The following select genre from the genres table where the show I equals just that 6，3，8，8，1。

 which I'm now starting to memorize adventure comedy and family。

 So that's the answer to the question。 but this certainly isn't the best way to do this where you have to like look up the unique I for the show you care about then copy past it or memorize and type it out into this query just to get the genres。

 it would be nice to just ask all of this in one breath。 Well we can do this。

 even though it's a bit more of abose， I'm going to instead this time。

 say select genre from genres where the show I I care about equals and now I'm just gonna hit enter。

 so as to move this nested query inside of parentheses。 and I'm going to say， well。

 I don't know off the top of my head what the unique I is for cat weasel。 but I can ask the database。

 select the I from the show's table where the title of the show equals cat weasel and this now obviouss the need for me to memorize or copy paste that unique I I'll hit enter and close。

😊，My parenthesis， I'm going to go ahead then and say semicolon enter and now I get back the exact same answers。

 but without having to know or care about these numeric values， and that's kind of the point here。

 even though the database itself， the actual IMDB website needs to use these unique identifiers to store everything in the database we humans generally speaking should not know or care what these identifiers are。

 they're just meant to implement this notion of relationships， these crossreferences。

 and so here we see an example where you can ask the question you care about without worrying about any of the underlying numbers or even seeing them as a result。

😡，Allright， Well， what's really， how else might we go about doing this。 Well。

 let me propose that we join these two tables and ask the question in a slightly different way。

 So here's an excerpt from the showss table。 Here's an excerpt from the genres table。

 And clearly we could do something like we did before for ratings where we could line these two up and kind of join them together。

 just for the sake of discussion。 Let me flip these columns around。

 though that has no technical significance。 And now we can clearly see 63，881 appears there。

 and here， the difference， though， because now this is a one to many relationship is that it's not quite as simple is just joining the rows together。

 I need to kind of join it here and here and here。 and the database can do this for you。

 albeit at some cost in redundancy。 So what I'm going to observe is that these Is are all the same primary key in this context。

 foreign key in this context。 Well， I'm going to start to join them together here。

 but it's not possible to return a temporary table that's just outright missing data。

 you have to get the same number of rows and columns everywhere and。😊。

So what the database is going do if I do join these two tables together and they are participating in a one to many relationship with each other。

 it's going to duplicate the data that's necessary to sort of make every row look the same Downside is。

 it might indeed be taking up some additional space unless the database is smart and somehow using pointers or something like that underneath the hood to avoid the redundancy。

 but for my purposes， this is actually quite nice because if I iterate over these rows。

 as I could in Python as we'll eventually see， it's just nice to have all the data you care about in each and every row。

 even though it's clearly redundant。 But the data is not being stored redundantly in the data。

 it's just temporarily being presented to me with this here redundancy。

 So what do I really want to have happen。 Well， I really care about actually joining these two tables together。

 and ultimately just getting back the title and the genre respectively。

 So let me go ahead and my VS code here and do select title。😊，And genre from the shows table。

 But let's join it this time on the genres table on shows do I equaling genres do show I。

 So that's quite the same as with ratings where the I equals just for times sake，6，3，8，8，1。

 which I know is catweasel， but I could certainly use a nested query if I wanted to do this as before。

 enter and I get back catweasels3 genres。 And if I were to loop over this data in some kind of like Python code。

 I would have access to the title and genre with each iteration。

 which I claim is useful but if I don't care about that and I just really want to select the genres。

 I can do this with joins 2， let me just select the genre from shows joining it on genres on shows do I equaling genres show Id where the I is catweasel 63881。

 and now I get back just that answer。 So in short， what if we just seen one you can join。

wo tables together and whittle down the temporary table to just the data you care about or if you prefer。

 and if I scroll back up in my history here， you could take a fundamentally different approach。

 but still get the same answer of simply using a nested query I would say as you learn SQL for the first time。

 I think it's quite often easier to just do multiple nested queries because you sort of work your way from the inside out。

 taking sort of baby steps to the problem If the problem and question is give me all of the genres for a specific TV show Well。

 first I need to know because I know how the data is laid out in the database。

 I need to know the unique idea of the show I care about fine that's pretty straightforward and hence this inner query once you have that you can parentthesize it and on the outside now you can select the question to which you really want the answer。

 which is what is the genre that lines up with that show I one or more times So in short nested queries probably easier and certainly when learning for the first time but quite powerful are these join queries where。

This achieves the exact same result， especially if I were to generalize away the 63881 and do a nested query here。

 sometimes you want join， sometimes nestedqueries suffice。😡，Oh my goodness。

 How does SQL do all of these searches， What's its time complexity。

 We'll talk about that toward at the end of today In the most naive implementation。

 SQL is essentially just doing linear search from the top of the table all the way to the bottom。

 However， we as the programmers are going to have the ability to optimize those queries so that the database can actually do something closer to binary search and in general。

 will be able to achieve much better performance as a result。



![](img/8b4f340d248e78d45f88a7de8bf3991a_23.png)

A really good question。 All right， let's go back to the big。F chart of this data set。

 We've looked now at shows and ratings。 We've looked at shows and genres。

 Let's now focus on the juiciest part。 like the part that associates shows with people。

 That is who stars in what thinking back now to what I was mocking up in the Google sheet at the very start whereby I wanted to somehow be able to associate the office with Steve Correll and John Ksinski and Jennifer Fisher and so forth。

 the right way。 And the right way I claim is going to be like this。 Here's my people table。

 which has a primary key of I and then the name of each person in their birth year if known。

 then we have the shows table， which we keep talking about， which again has a primary key。

 a title and year and episodes thereof。 And then the stars table is somewhat new now。

 because now when it comes to people starring in TV shows。

 we have a third and final type of relationship， a many to many relationship Why because it's certainly the case that one person can be in multiple shows And it's certainly the case that some shows have multiple people hence many to many。

 So this is the third and final relationship where just to recap。😊。



![](img/8b4f340d248e78d45f88a7de8bf3991a_25.png)

ings was one to one。 genres was one to many。 And now stars is going to be many to many。 Allright。

 let's dive in。 So these queries will be a bit more verbose。 But again。

 they're going to follow this principle of sort of taking baby stepsps to the answer we care about。

 Let me go back into VS code here。 And suppose I want to find out everything about the office that we know。

 So select star from shows where title equals quote unquote， the office semicolon。 Well。

 that's interesting。 There's a whole bunch of offices。 There was the UK version。

 There's a few other variants。 But the one we're probably talking about with these stars is the one that started in 2005 with 188 episodes。

 That's the US version， In fact。 So let me be a little more precise。

 Let me select everything I know from the stars from the shows table where the title equals office and year equals 2005。

 So we don't confuse our answers with the other versions of the office。 Now。

 how do I go about selecting all of the people who starred in that version of the office。 Well。

 I already have an answer to the question of。😊，What is the idea of that version of the office Because it's right there in front of me。

 And in fact， I can narrow my query more precisely。

 Let's just select the Id from the show's table where the title is the office and the year is 2005，3。

8，6，6，7，6。 Now， I could lazily just copy paste that or memorize it。

 but we're gonna do this query more dynamically。 I want to next， though。

 figure out who is in that show， So if I have a show Id， I want to figure out who's in it。

 But how do I get to the people and the names of those people。

 I have to logically go through this cross referencing of the stars table。

 So here's where this query is gonna be a bit meatier than the past ones。

 and that we need to do a bit more work than before。 Al right， well， what's the work I need to do。

 Let me go ahead now。And do the following。 Select all of the person Is that are associated with this show ID。

 So how do I do that， Select person I from the stars table where the show I equals。

 and I could lazily copy paste this， but let's avoid that where the show I equals let me now in parentheses do this。

 select Id from shows where title equals quote unquote the office。😡，And year equals 2005。

 and then close my parenthesis semicolon。 So what am I doing， I'm taking a second baby step。

 if you will， The innermost query inside the parentheses is just again。

 dynamically figuring out the unique I of the office I care about The outer query is now figuring out all of the person Is associated with that show as per the stars table and the stars table has only two columns show Id and person Id。

 That's how the linkage is done just with those integers。

 enter I now have a column of person Is that are starring in that version of the office。

 So how do I take this one final step。 If I really want to care about their names and not their random person Is。

 Well， I could go ahead and select the name from the people table where that person's Id is in the following set。

 So when I'm dealing with a single value， I just use equals for equality。

 But when I'm dealing with a whole result set， a whole column of answers， I use the preposition in。😊。

In SQL instead， So where the person's ID is in the following dataset set。 Well。

 let's do the same queries before， select all the person Is from the stars table where the show I I care about equals because there's only one show I care about。

 I'm going further parentthesize this select ID from shows where title equals unquote the office and year equals 2005 enter。

 I'll close my parenthesis enter， I'll close my parenthesis semicolon and now from the outside in。

 I've taken three baby steps。 the innermost one just gets me the show I。

 the second one in the middle gets me all of the related person I and the last one is really the final flourish。

 get me all of the names of these people based on those Is enter。

And now we see all of the stars in this show beyond even the subset that we've been playing with visually on the screen。

Okay， that's a lot。 Let me pause here and see if there's any questions， yeah。

This outermost query is what gives me the names， but that query needs to know the ID of the person whose name you want。

 so the middle query actually gets all of those person IDs， but to get those person IDs。

 I need to know the show ID， so the innermost query。

 this one gets me the show ID of the office itself。😡，Alright， so at the risk of overwhelming。

 here are other ways you can solve the same problem。

 But I do claim that the nested selects is probably conceptually and pragmatically the easiest way。

 But let's also solve this problem by doing a few joins just so you've seen it。

 So if I care about all of let's flip it around now。

 let's select all of the TV shows titles that Steve Corll has been in beside the office。 Well。

 how might I do this。 Well， first， let me select everything I know about actually before we do a join。

 Let's let's flip the question around first。 How about all of the shows that Steve Correll has starred in besides the office。

 So let me select everything I know from the people table where the name of the person equals quote unquote Steve Correll semicolon。

 All right， there seems to be only one Steve Corll in IMDB born in 1962。 That's all nice and good。

 What I really care about is his Id。 So I'm gonna narrow this down to selecting just his Id Now I could memorize or copy paste 1。

3，6，7，9，7。 but don't need to do that， let's just use this as part of a nested 。

Let's now select all of the show Is from the stars table that are somehow related to Steve Correll's person Id。

 So where person Id equals and I could copy paste this， but that's generally frowned upon。

 So let's not do that。 Let's just set it equal to a nested query。

 where I do the same thing as before。 Select Id from people where name equals Steve Correll。

 then close my parentheesis semicolon。 Allright， he's been in a lot of TV shows。

 but this is not useful because I have no idea what all of these integers are。 So the final flourish。

 Select the title from the show's table where the I of the shows I care about is somehow in this parenthetical list。

 Well， what's that parenthetical list， Well select the show Id from stars where the person Id equals Steve Corlls。

 What is his Id， Well， I didn't memorize it。 So I'm gonna select Id from people where the name of the person I care about is Steve Correll。

😊，Quote unquote close this parenthesis， close this parenthesis semico and enter。

 And now I see all of Steve Corll shows。 And even though we're doing this in a black and white command line environment。

 think about what the actual IMDB is doing with both of these queries。

 If you go to IMDB do com and search for Steve Correll。

 even though there's gonna to be a lot of colors and pretty pictures and whatnot。

 you'll probably get in some form a list of all of Steve Correll shows。

 Or if you search for the office， you'll get a list in some form of all of the stars they're in。

 I could claim then that if IMDB do com is using SQL， which it very likely is。

 but not necessarily they are executing queries just like we did。

 And when you type into the search box， something like the office or Steve Correll。

 they're essentially just copy pasting your user input into a prefabed SQL query that they wrote in advance so as to get you the answers that you actually care about。

 So this is how a lot of today's websites and a mobile apps are actually working。

 the programmer comes up with sort of the template for the。😊，Quries you might ask。

 and then you supply the actual data you're searching for。All right， how about now as promised。

 a couple of other ways to implement these many to many relationships based queries？😡。

But by using joins， if I know I need to involve the shows table。

 the people table and the stars table， I can actually do this all in one breath without any nested queries。

 Select for me the title from the shows table。 But let's join that on the stars table on shows dot I D equaling stars dot show I D。

😊，啊。But let's additionally join the shows' table on the following。

 Let's join it on people on stars do person Id equaling people dot I D。 In other words， if you know。

 conceptually that you've got these three tables。 you want to somehow combine them without using nested selects。

 Just figure out how to line them all up。 So again， I'm selecting from the shows table。

 But I'm joining it with the stars table by lining up the shows tables primary key with the stars tables。

 foreign key。 And I'm lining it up with the people table by lining up the stars tables foreign key with the people tables primary key。

 I'm just kind of logically connecting all of the things I know to be related。 And lastly。

 let's just say where the name I care about equals quote unquote， Steve。😊，Krell， semicolon。

It's a little slower for now。 And this speaks to the question that was asked earlier。

 How is the database doing this， Well， slowly， Apparently by default， unless we optimize it。

 I got back essentially the same results， although there is some duplication as a result which alludes to the filling in of blanks that I alluded to earlier。

 But let me show you one other technique too。 But again， I would encourage you。

 certain for problem set 7 to focus on nested queries when you can because theyre a little conceptually simpler。

 if I care about the titles of those shows， I could select title from the showss table and the stars table and the people table all at once in one breath。

 But I want to do so where the showss tables primary key equals the stars tables。😊。

Foreign key and the people tables primary key equals the stars tables。 foreign key。

 and the name I care about is Steve Corll。 In other words。

 this is just a third way to express the exact same idea by doing implicit joins by selecting data clearly from all three tables as per this comma separated list of table names。

 but telling the database with your predicate， the wear clause how you want to line all of those tables up。

 if I hit enter here cross my fingers， I should get back。The same results as well。

 albeit with duplication， which I didn't see in the nested queries。Okay， that， too was a mouthful。

 Let me pause here。For questions。Yeah。Correct， in order to do this。

 you as the programmer must know the internal structure of the database。

 which is quite often the case， whether you created the database yourself or you work with a colleague who designed the schema for the database。

 That said， I think your questions hinting at sort of the challenge。

 like I really need to know the underlying implementation details。

 When really all I care about is the answers to my questions in code quite oftenly nowadays。

 there are object relational mappings whereby you can use Oms for sure。

 whereby you can use libraries that they understand the underlying database schema。

 you as the programmer do not need to， because it figures out how to do all of the joins for you。

 So for C 50， we're introducing everyone to the bottom up， understanding of how these joins work。

 but that， too can be easily automated because of those schemas yeah。Good question。

 Is indentation in SQL important technically no， but like with any of the languages we've talked about thus far。

 it is good for the humans and certainly good for the students in a context like this。

 Python of the languages we looked at is the most rigorous whereby indentation very much matters。

 And the consistency thereof SQL。 I'm just trying to pretty print things to make it easy to gr visually。

All right， so those last two queries were arguably kind of slow。 whereas with my nested queries。

 I actually got lucky and just boom， I got the answer quite quickly。

 Those joins seemed to be a step backwards and then it was taking more time to get back the same data that I actually cared about but that's something we can actually chip away at。

 It turns out that one of the other values of a relational database Vi be something like a spreadsheet is that you can actually tell the database in advance how to optimize for certain queries。

 This is not the case for spreadsheets。 if you have a lot of data in Google spreadsheets or Microsoft Excel or Apple numbers。

 tens of thousands of rows， hundreds of thousands of rows， millions of rows。

 your computer is going slow to a crawl and at some point those software packages are just going say sorry file is too big and they're certainly not going be terribly fast at searching the data。

 but with a SQL database and relational database is more generally you are as much the architect of it as you are the user of it in this case。

 And so you can tell the database in advance。 if you want to optimize for certain queries like select statements So for instance。

 let me go back。ToVS code here。 And just for the sake of discussion。

 let's time how long it takes to find all of the shows whose name is the office。

 I'm going to use a SQL like command called timer。 and I'm gonna to set it to on。

 And this is just now going to tell me for every command I run how long it took。

 I'm going now select everything from the show's table where the title of the show equals quote unquote the office close semicollon enter And that query took。

 let's say in realter 0。042 seconds。 That's crazy fast。 Like it's less than a second。 I mean。

 it's truly a split seconds。 So no big deal。 But it's a fairly simple query。

 but I bet we could optimize even this。 Now why would you want to optimize even queries that are already pretty fast。

 Well， if they're very commonly being executed。 And I dare say someone going to IMDB do com and searching for the office or any TV show like that's the common case。

 people are looking for TV shows， movies， actors and so forth。

 Itd be nice to use as little amount of time to answer those questions as possible。 why1。

 it makes for happier customers and users because you're getting them the answer faster。😊，2。

 it saves you money because presumably， if you've spent 1000 for a server and that server has certain amount of Ram。

 a certain speed CPU or brain， It can only do so many searches per unit of time per second per minute or the like。

 So wouldn't it be nice if all of those searches is faster using less time。

 So you can handle not 1000 users at once， but 2000 users or 5000 users all with the same hardware。

 So there's certainly upsides there。 Well， how can I go about optimizing a query。

 Well I can create my own index， Another use of the create keyword in SQL。

 where I can tell the database。To optimize for searches on a specific table and specific columns therein。

 I say create index， and then I come up with a name for the index。

 whatever I want on the name of the table that I want to index。 And then in parentheses。

 the columns that I want to optimize for。 So what is this meal in real terms。 Well。

 let's go back to V S code here。 and let me create an index called， for instance， title index。

 So the name doesn't matter on the shows's table using the title column。 In other words。

 tell the database， please expedite searches on the shows tables title column。 After all。

 that's what I just searched on enter。😊，Now that took a moment， almost half a second。

 but that's table that's an index that only has to be created once。

 If I do a lot of updates and deletes， it might actually take a little bit of time over over the course of using the database to maintain that index。

 but for now， that's a one time operation creating the index。 but watch what happens now。

 if I scroll up in my history and go to the exact same query as before， which previously took 0。

042 seconds， which yes as fast， but not nearly as fast as the new version。😡。



![](img/8b4f340d248e78d45f88a7de8bf3991a_27.png)

Which is 0。001 seconds instead， orders of magnitude faster。

 so I can handle 42 times as many users on the same database。 so to speak。

 then I could have previously， just by building this index。 So what actually is an index。 Well。

 we come full circle to discussions in like week five of the class。

 So an index and a database is very often created using what's called a Be tree。

 This is not binary tree。 Be tree is its own distinct structure， that's very similar in spirit。

 and that it's fairly shallow， because most of the nodes have children。

 but it doesn't necessarily have two children。 It might have more children。 And in fact。

 the more children the nodes have that's sort of higher up。

 you can pull all of the leaf nodes and the shorter。 you can make the height of the tree。

 So this is just a generic representation of a Be tree。

 But what this implies is that when I am now searching for titles like the office。

 the database doesn't have to do the default behavior。

 which is started at the top and use linear search all the way to the bottom。

 If it has proactively built up an index and memory。To my command。

 it now has a treelike structure storing those titles that allows it to find in some logarithmic time。

 whether it's log base 2 or some other base， the same data much more quickly。

 and that's how we went from 0。042 to 0。001 second instead in this case here。😡。

Questions then on these here， indexes。No， all right。 Well。

 let's propose that we can combine some of today's ideas。

 It turns out that now we're getting to the point of the course where you're not just choosing between this language and another。

 You're generally using a suite of languages to solve problems。 And indeed。

 in the coming weeks of the class when we transition to webbased applications。

 you're going to use a bit of Python， You're going use a bit of SQL。

 You're going use a bit of javascript and two other languages called Hl and C。

 you might be using like five different languages at a time just to build one application。

 Y because some of them are better for the job than others。

 And indeed that's the ecosystem in which real worldor software development is done。 Well。

 to make this bridge， we have a version of the C 50 library， recall for Python。

 which has functions like getstr， even though it's not that useful because it's just like the input function。

 but get in and get float， but also in the Cs 50 library for Python。

 we have a module that specifically makes it easier to use SQL from Python code。 After all。

 wouldn't it be nice if I could get the best of both worlds and implement like an interactive。😊。

Program in Python， but that uses SQL to actually get back data。

 Or I can build a website that allows people to search for TV shows or TV stars and actually get that data from a database。

 But use Python to generate the web pages themselves。

 Well we have some documentation for this library here。

 But I'm gonna go ahead and use it in real time to show you how much more easily you can solve certain problems by using each tool for what it's good at。

 So let's go back to V S code here。 Let me exit out of SQL light and get back to my normal terminal And let me go ahead and let's say minimize。

😊，My terminal here。Actually， let's go ahead and open up favorites do pi。

 which is where we left off before and recall that in the last version of favorite do pi。

 we had simply used a dictionary to go about keeping track of how many of you said Python or C or scratch。

 And when I last ran this program with Python of favorite do pi。 The answer looked like this。

 Now notice that it's not sorted alphabetically otherwise C would be first and it's also not sorted numerically otherwise C would be second。

 So it would be nice in Python to maybe exercise some control over this。

 but I stopped short of doing that before because it gets very annoying quickly And by this I mean the following let me go back into VS code here and into favorite do pi And if I wanted to sort by the counts here I could do this I could change my loop from iterating for favorite in counts to favorite in sorted counts。

 So this is actually not too bad thus far I can actually sort dictionaries pretty readily。

 So now if I run this and let me make my terminal a little bit taller so we can see both。😊。

If I run the program now， you'll see that it's sorted alphabetically by key。 So apparently。

 when you use the sorted function in Python and pass it a dictionary。

 you can still iterate over all of the key value pairs in that dictionary。

 But it's been sorted now by key。 So that's nice。 if that's to be my goal。

 But maybe that's not really my goal。 And here's how alternatively， I could sort by value， the 1，90。

 the 58 and the 24。 I can still use the sorted function。

 But I need to tell Python to use a key a sorting key of the counts dictionaries gets function。

 And then if I run it again。I now see it sorted by value。 but Dararn it。

 it's now sorted in the opposite order。 I see scratch at 24， then 58 then 1，90。

 If I want to reverse it。 Well， then I have to go up here and add another named parameter reverse equals true。

 I can run it another time。 And now I get the result I care about。 Long story short。

 This is just very annoying to have to use that amount of code to actually answer relatively simple questions。

 And this is why we did transition for much of today to a declarative language like SQL。

 that just let me select what I care about in that data。 So if I again。

 I go back into my database version with SQL light 3 of favorites do DB。

 I'll maximize my terminal window。 What did we do before。 Well we can select from the database。😊。

Select let's say see， favorite comma count star from favorite group by favorite semicolon， whoops。Oh。

 al right。Sliide。Oh， sorry。What do we do， We do select language comma count star from favorites group by favorite。

 damn it。 What happened。 Oh we deleted it。 See this is why you don't use the delete or drop command。

 So we'm not gonna demonstrate this again。 But recall before break that when we at selected this information。

 we use the group by command actually group by the language in question。

 And we got back all the count。 But then we were very easily able to reorder things by actually just using order by and then doing something in ascending order。

 or for instance， descendending order instead。 Well。

 now let's actually combine these worlds of Python and sQL together to write first a program that does just that。

 But to do this， we're gonna need to restore that database。 So let's go ahead and do this。

 Let's remove favorites do DB， which is just a file in my account。

 let's go ahead and run SQL light 3 of favorites do DB to create a new version thereof let's now go ahead and change my mode as we did earlier in class to CV。

 lets。😊，Now do import of favorites dot CS SV into a table called favorites。

 And now let's do dot quit。 And when I do L S， okay， now it's back favorites dot Db。

 in addition to today's other files。 Now， let me go ahead and run SQL light 3。Of favorites dot D B。

 And just as a sanity check， select star from favorite semicolon。

 There's all of the data back minus the addition and subtraction that we ourselves made earlier manually。

 And let's go ahead and in SQL， go ahead and do select language comma count star from favorites。😊。

And group by language。But let's order by count star in descending order。

 And that's one of the last commands we ran with this file。

 And there is the answer in a single line of code instead of some 17 lines of code plus or minus some whitespace here。

 Can we merge now these two ideas。 Well， let's see how to do this。

 Let's go back into favorite do pi here and make a new and improved version of it that actually uses SQL。

 and now dictionary， no4 loop， no try accept or any of this。 instead。

 let's go ahead in from Cs 50's own library， import a SQL function。

 which will give me access to this functionality。 let's create a variable called Db by convention。

 But I could call it anything I want and set it equal to Cs 50 SQL function。

 and pass to Cs50 SQL function。 The path to the database file I want to open。 This is a little weird。

 But the syntax here is SQL light without the three colon slash slash slash favorites。😊，Dot D B。

 This syntax， otherwise known as U R I is going to allow us to use the SQL light protocol in order to open up favorites do Db。

 which is the very file I was just experimenting with manually in my terminal Here now is how I can execute a SQL query in Python using C50s library。

 Now， as an aside， even though this is indeed meant to be a training wheel。

 Cs 50s library is just easier to use than a lot of the real worldorld libraries that makes this possible。

 So because we spend so relatively little time on this。

 we're still using this training wheel for this。 Give me a variable called rows。

 because I want to get back all of the rows from this table that contain those languages。

 and do DB dot execute。 The only function that's useful in the C50 library for SQL。

 is this execute function， which allows me to write literally a line of SQL like select language count star from favorites group by language order by count。

😊，Star descending order。 just to make my life easier。

 I'm gonna add that alias trick that we saw before。 So as n to change the count to the variable N。

 And then here I can just do order by n instead。 It's a little long。

 but notice that now I'm using SQL as a string that I'm passing as an argument to this D B execute function。

 So at the very end of this， I've got to close my quote close my parenthesis。

 So as to use one language in effect inside of another。 Now。

 assuming I do get back a temporary tables， rows with that line of code on line 5。

 let's do this for each row in rows， go ahead and do the following。 Cre a variable。

Called language and set it equal to row， quote unquote language。

 Then create another variable called n， for instance， and set it equal to row， quote unquote n。

 And then let's just go ahead and print out language and n respectively。

 So what does C 50's library do。 It returns by design， a list of rows。

 Each of those rows is a dictionary of key value pairs。 So when I do four row and rows。

 this is just iterating over a list of values。 And we've done that over the past couple of weeks。

 inside of this loop。 I'm just creating temporarily two variables language and n to show you that each row is indeed a dictionary。

 which means I can index into it using strings like quote unquote language and quote unquote N because those are the columns that I selected using this query up above。

 strictlyly speaking， I don't even need these variables。

 I can just get rid of that and a little more succinctly just pass in row bracket language and then row bracket。

😊，And instead。 So let me go down to my terminal window here， exit out of SQL light。

 run Python of favorite stop pi in this form， enter。 and I get back。 It would seem。😊。

The same exact answer， 190， 58 and 24 in this case。Questions now on this comm mingling。Of languages。

All right， How about one final thing。 Once we have the ability to like use Python now we can。

 in fact， make things interactive。 So for instance， let me close my terminal temporarily。

 let me go ahead and now ask for some user input。 So after opening the database， let's do this。

 let's ask the human using Python's input function or equivalently Cs get string function for their favorite TV show and store it in that same variable。

 Then let's do a SQL query that selects that data rows equals Db dot execute select and let's see how many people select this favorite problem rather。

 not TV show， how about favorite problem from our favorite data， So select count star。

 as n from the favorite database where the problem in question equals well now I need to put the user's input。

 I don't know what that is yet because they haven't typed it in yet。

 So what I'm gonna go ahead and do is a placeholder and say favorite close quote and make this whole thing in F string。

 Then I'm going go down here。I don't need to iterate because ideally I'm just getting back a single answer。

 how many people chose this problem as their favorite。

 So I'm going to say that the row I care about is simply the first row。

 So rows is a list So rows bracket0 is the first and only row in that list and then let's go ahead and print out row quote unquote n Let's see the result here and then。

See what happens。 Let me put some single quotes here and single quotes here。 Let me open my terminal。

 Let me do Python， a favorite stop I， And I'll say hello， comma world enter。

 And as before at the start of class 42 of you like that。 However， this is not， not。

 not how you should ever write SQL code in Python。What could go wrong with this code？

Nothing went wrong a moment ago， but what could go wrong。Yeah。The user input， how so。True。

 I don't know what those are yet， but we're about to go there What even more simplistically could go wrong by plugging in the user's input here。

Yeah。Exactly， if I inputted the other problem we played with hello comma， it's me。

 where it was I T apostrophe S that if interpolated right here。

 is clearly gonna confuse the single quotes such that who knows what's gonna come back Now。

 in the best case， the code does not work。 And I'll get some kind of error in on the screen。

 which is not great for the user because the program's not gonna be useful。

 there's no user friendly error message， but in the worst case。

 the user could do something incredibly malicious， if you are simply blind blindly trusting user input and plugging their input into a SQL query that you yourselfconstruct。

 Why what if the user type something crazy like the word delete or drop or update or any of those destructive commands that we saw earlier。

 and somehow tricks your code into executing maybe the select。

 but then eventually an additional query like a delete。

 maybe they type in a semicolon and then delete or a semicolon and then drop or something like that。

 This is the biggest threat。Taking user input and trusting it in the context of databases。

 and it's called as one of your classmates knows already what's known as a SQL injection attack。

 a sQL injection attack is the ability for an adversary or an unknowing user to somehow inject code into your database。

 a SQL injection attack then might look something like this in the real world here， for instance。

 is like the login screen to Github do co they do actually use SQL among other languages underneath the hood。

 I believe not necessarily for this， but suppose they did。 And when logging into Github do co。

 you're prompted for your username or email address and then of course your password。 Well。

 what if I know a little something about SQL。 and suppose for the sake of discussion。

 Github is using SQL light， which they're not using because it's not meant for massive large massive datasets like this but suppose they are And just to be malicious。

 I type in my username name， mailland@haror Uu。 But then I use a single quote and then dash dash。

Well， the single quote is there me being an adversary in the story because maybe I can confuse their code by closing their quote sooner than they intended。

 And we haven't talked about this yet。 But it turns out that dash dash in SQL is the comment character。

 So it's like hash in Python or slashlash and C this in SQL means ignore everything to the right that alone can be used fairly maliciously as follows here。

 for instance， could be the code that Github is using underneath the hood whereby they might have some Python code and heck。

 maybe they're using the C50 library that executes this premade query。

 Select star from the user's table where the username equals this question mark and the password equals this question mark passing in username and password。

 for instance， But if they are trusting the username and password I typed in and just plugging it right there they could be vulnerable to indeed a sQL injection attack。

 For instance， this code will soon see is actually the right way to do it。

 But suppose they were doing it with F strings like。😊，Started to in my version of favorite stop pie。

 same thing。 select star from users where username equals this username and password equals this password and the little F here means here's a format string。

 What could go wrong。 Well， let me actually paste in the mailin at Harvard E single text here。

 notice that this single and this single are meant to surround the username and same thing for the password there。

 But watch what happens when I type in my data。 mailin at E single quote。

 So this would seem to finish the thought prematurely。 And then it says。

 And so that just means ignore everything else。 And so the effect here is essentially to gray out all of that stuff because it's effectively been commented out。

 So what github ends up doing accidentally in this case is selecting star from users where username is mailland irrespective of what has password actually is。

 And if you assume that down here they've got some conditional logic like well。

 if we get back some rows， that means that mailin is in fact of registered user go ahead and log him in。

 we don't know。😊，What the code looks like。 So it's dot dot dot you've just enabled anyone on the Internet to log in as me or anyone else just by suffixing their input with a single quote and。

 And that's the least of our concerns。 If we additionally went in there and maybe instead of we put a semicolon and then delete from users or drop users。

 we could cause massive havoc on their database， this happens all the time even now in the current year you can Google around and see examples of companies that have not used proper sanitization of user input and it's not just the intern。

 it's like random people on the Internet are accessing or destroying their data maliciously So what is the solution to a problem like this。

 Well， one， do not use format strings in Python to simply plug in user input。

 but the more important lesson is never trust users input either they're going to do something accidentally or they're going to do something maliciously and you do not want that to happen。

 So the solution then is to use a library almost always use a library。 This is not。😊，Wheel。

 you should reinvent yourself And by library， I mean something like this。

 If you instead use a library like Cs 50s and you don't just use F strings。

 You'll see in a moment you use question marks。 what will happen is this。

 when the user goes and types in mailin single。 That's fine。 Let them put weird。

 scary characters like single quotes in their input。

 The library will take charge of escaping user input。

 So anything dangerous in their input will be changed from one single quote to2。

 because we saw earlier today that that's how you escape a character。

 And that means that now what you have is， in effect。

 My username is apparently mail in harbordu apostrophe dash dash。 and that's my username。 Well。

 that's obviously not a real email address， It's not a real username。

 this is just going to return false。 No rows are actually going come back。

 And the way to do this now when our favorites example Anaously is in V S code here。

To actually go up into this execute line， don't use an F string。

 change the value of problem to be a placeholder instead and then pass into this execute function。

 one or more arguments that will be substituted in for that question mark。

 And this is not a C50 thing。 This is a industry convention whereby you quite often use literally a question mark。

 And that means that whatever this variables value is。

 will get plugged into that question mark for you。 But the single quotes will be added。

 any dangerous characters will be escaped for you。 And at that point you can trust that the user can type in anything they want your code is not going to break。

 you can see hints of this actually in the real world。

 if you've ever gone to a website and they tell you like， oh， you can't like for passwords。

 for instance， like all of us probably intuitively know that you should have pretty long hard to guess。

 passwords with letters and numbers and punctuation symbols。

 sometimes websites very stupidly prohibit you from using certain。Punctuation symbols。

 which should drive you nuts because there's no computational reason that you have to put the onus on the user to sanitize their own input。

 but quite likely those websites have kind of learned part of this lesson and they know some characters can be dangerous and SQL like semicolons or single quotes or the like and they just don't want you to ever type those in。

 even though there are solutions to this problem use a library that someone else smarter than you with more history of writing code than you has used that's open source so that many people have seen it and banged on it over the years so that this problem is not something you're vulnerable to。

😡，Questions then on what these here SQL injection attacks。Are all about yeah。这加了应该。Good point。

 So by also telling people what characters they shouldn't use。

 You're leaking information because a smart adversary might know， oh。

 if they don't want using that symbol， they're probably using this language or this technology。 Yes。

 no good comes from telling the world more information than they need to know。

 So that's another good paranoia to have How about one other issue before we come full circle to the SQL injection attacks。

 There's another challenge with relational databases than with SQL itself， namely race conditions。

 This isn't so much a problem when I'm writing a little program here on my own computer。

But when you're running SQL code on a database in the real world in the cloud where you have many different servers talking to that database and many different users talking to those web servers。

 as is gonna be the case at Me and Google and Microsoft and any number of popular companies nowadays。

 And even some of C50 zone apps uses centralized SQL databases where if multiple people are trying to do the same thing on them at the same time。

 their homework run check 50， we too are vulnerable to what are called race condition。

 So what is a race condition。 Well， the way I learned this back in the day when taking a course on databases and operating systems more generally was to think of a scenario like this。

 maybe in your dorm， you and your roommates have a little dorm fridge and you're in the habit of really liking to drink milk as the story was told to us。

 And so maybe one of you comes home from class one day and gets your room look in the fridge。

 there's no milk in there and so you decide to walk across the street to CS or some other store to get milk。

 Meanwhile， your roommates comes home from their class and opens the fridge and like we're out of milk。

 let me go to the store too。 and for the sake of。😊。

They go to a different store altogether so that you don't run into each other and the problem solves itself。

 So now both of you are on your way to a store to get milk。 time passes。 You both come home。

 One of you puts a ju of milk in the fridge。 The other one gets home is like， damn it。

 Like we already got milk。 I can't fit this milk in the fridge or now it's too much milk。

 We don't really like milk This much。 iss gonna go bad。 Like very bad outcome here。

 Having too much milk is the moral of the story。 But what's the stupid story。 What's the。

What's the real takeaway， Why did we find ourselves in a situation where we ended up with too milk。

 too much milk。We didn't know what the other person was doing。 And to really geek out on this。

 we inspected the state of a variable that was in the process of being updated by someone else。

 And this is a thing in computing as far back as scratch。 recall with scratch。

 you could have multiple scripts running at the same time for a single sprite because scratch in effect is multithreaded。

 you can have a single sprite doing multiple things in parallel by having those multiple scripts Similarlyly here。

 your room is sort of multi-threaded because you have two independent beings so you can both go to the store。

 solve the same problem in parallel， The problem though。

 is that if one is not aware that the other is doing that work already。

 you might make poor decisions。 So in the real world。

 what should the first roommate have done after inspecting the state of the refrigerator and realizing。

 oh， we're out of milk。Okay， call the other roommate or maybe more simply like put a note on the door or like maybe dramatically lock the refrigerator somehow。

 And in fact， that's a term of art in databases is to actually use a database lock so that if you are in the process of updating the value in the database。

 Lock it so that no one else can inspect the value of that database and potentially make a poor decision。

 So when might this actually happen in the real world， rather than the contrived milk example。

 So there are a lot of social media post nowadays that are quite popular to this day as of today。

 still the most popular Instagram post for instance。 And imagine when this was first posted。

 hundreds， thousandshou， hundreds of thousands of people might have all been clicking the heart icon essentially at the same time。

 Now， meta the company behind Instagram， presumably has lots and lots of different servers。

 But let's suppose for the sake of discussion。 They have a single database， which is not true。

 But the danger is still there， even with multiple databases。

All of these different web servers are talking to the same database and suppose those those servers are using Python code。

 and hey， the CS50 library that might look a little something like this in order to decide how to update the total number of likes for an Instagram post。

 The first line of code running on meta servers might say this。 get these rows as follows。

 Exute a query like， select the current number of likes from the posts table where the idea of the post is whatever it is。

1，2，3，4，5，6， whatever， notice no SQL injection attacks possible here because I'm using the placeholder。

 not an F string。Then the next line of code running on metaservver， maybe just stores in a variable。

 just to make the code more readable。 The first rows likes column。 So it's again。

 it's the CS50 library in the story。 rows is a list of dictionaries。

 So this is the first such element in the list。 and this is the likes column in the column we just selected the temporary table。

 Lastly， what do we want to do。 Well， we want to plus plus essentially that total。

 So we update the post table setting the number of likes equal to this question mark where the Id equals this question mark。

 and we didn't see this already， but the C50 library supports indeed multiple arguments after the SQL string。

 I'm gonna update the number of likes to be likes plus one plugging in the same I of that post。😊。

So in short， take on faith that it's quite common that in order to achieve one small goal。

 like updating the number of likes stands for reason you might need to do two database queries or three lines of code。

 Now， if these lines of code are executing on multiple web servers。

 you could certainly imagine that if people are hitting the like button。

 pretty much at the same time， maybe one server is going execute this first line of code and it's going to get its answer。

 Maybe there's 100 likes at this point in the story。 And then just by chance， on another server。

 this line of code is also executed， but it too gets the same answer。 There's currently 100 likes。

 Meanwhile， the first server in the story continues to do its execution of code。

 such that it updates the number of likes from 100 to 1001。

 But because the other server was essentially running the same code in parallel。

 it's going make the same mathematical decision and update the number of posts。

 the number of likes from 100 to 10001。 But at this point in the story。

 the number of likes should obviously be 100。2， so we've lost data。

 And that's one of the dangers of a race condition is that you'll end up with an inaccurate result。

 And for a company like Meta， they don't want to go losing data like likes like this。

 like that actually drives engagement and so forth。 And so like that's genuinely a technical。

 if not a business problem as well。 So it's analogous sort of the milk problem。

 but actually at scale。 So what's the solution。 There's a bunch of different ways， but conceptually。

 we just want to lock the database when this logic is being executed。

 It such that when one server is updating the number of likes。

 no one else should be allowed to update the like count at the same time。

 Now that's a little crazy for someone as big as meta because you're really just serializing all of these likes and slowing things down。

 So there's more fine grain control nowadays， namely called transaction where you can essentially lock not the whole table and then certainly not the whole database。

 but just the row in question， for instance， And so you would use commands in SQL。

 like begin transaction。 And then execute the lines of code that you want。

 And then when you're ready to commit it。 that is save it。 You use。😊，Commit command。

 But if something goes wrong or you get interrupted， you can actually roll back the whole thing。

 And what this kind of code does in effect by using more verbose C 50 and Python code like this is you can ensure that those three lines of code inside or technically the two database queries inside were either both be executed or not at all。

 They will not be interrupted。 And that's the fundamental solution to this problem。

 analogous to putting a lock on the fridge or by leaving a note or calling your roommate。

 preventing them from making the same decision themselves。



![](img/8b4f340d248e78d45f88a7de8bf3991a_29.png)

Questions then on these race conditions， the solutions again。

 even though this won't be germane for CS 50， simply using techniques like locks and what we called transactions。

NoAll right， then a final moment to end on。 we would not be a computer science course if we didn't introduce you to a few pieces of C Canon here is a sort of meme that's circulated for years when it comes to like optical character recognition O CR of like toll booths trying to detect your license plate automatically。

 This is someone trying to have a funny old time tricking the city into deleting their database altogether。

 because if you're just scanning this off of someone's license plate or front of the car and just blindly plugging it in without sanitizing their input escaping their input with something like a good library。

 you might very well drop the entire database as an aside， something did something similar to。

 where I think they made their license plate null and ULL。

 which just confused the heck out of the system too。

 because the programmers didn't understand why null was all over the place when lights were being run and whatnot。

 And lastly， a very famed character in the world of XKCD as computer science circles goes is this。

 So we'll end as we've done before on an awkward silence as you process this here canonical C S joke。

Now， you too know who little Bobby tableables is。 All right， that's it for week 7。

 We'll see you next time。