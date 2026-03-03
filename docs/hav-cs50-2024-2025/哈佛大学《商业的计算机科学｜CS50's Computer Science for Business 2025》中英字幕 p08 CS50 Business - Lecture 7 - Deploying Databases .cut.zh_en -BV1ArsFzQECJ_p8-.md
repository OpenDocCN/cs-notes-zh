# 哈佛大学《商业的计算机科学｜CS50's Computer Science for Business 2025》中英字幕 p08 CS50 Business - Lecture 7 - Deploying Databases .cut.zh_en -BV1ArsFzQECJ_p8-

Hello world。 My name is David Main， and this is the first of three live streams today。

 two of which are going to be focused on CS50B， CS50's computer science for business。

 one of which is going to be focused on CS502D， the new and improved version of CS50G The introduction now to 2D game development。

 Please forgive if we start and stop along the way。

 the first of these lectures will be focused on SQL and databases more broadly。

 Second of these lectures will be focused on cybersecurity。

 and the third of these will be focused which sounds like the most fun on angry birds。

 So more on that soon。 Please feel free to ask any ch questions via the chat of each other。

 I'm up here and won't necessarily be able to field them in real time。

 but we'll do my best to anticipate all such questions there and we will get started here in just a moment。

😊，Hello world， my name is David Main and today we'll talk about deploying databases。

 particularly when we have a lot of data that we want to store at scale Now what do we mean by data。

 really just information， it's often textual information。

 but it can be binary data as well that is files and such but databases then are just really collections of data somehow organized in a computer system now there's other terms of art in the space that are perhaps worth knowing about you might hear data warehouse。

 which is essentially a database of databases， really all of your data， somehow gathered together。

 you might hear about a data mark， which is actually a subset of your data。

 maybe just your marketing database or your financial database or the like。

 and then you might also hear terms like data lake which is essentially a hot mess of data which is where you might dump all of your textual data your PDFs。

 your files and so much more usually with the intent of going back and cleaning it up later but for now it just sort of sits there instead but today will focus primarily on organizing our data indeed in these data。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_1.png)

![](img/3741fde3a9a19aa400591a39252631a8_2.png)

![](img/3741fde3a9a19aa400591a39252631a8_3.png)

Bases， which practically speaking， is really just a piece of software running on a computer。

 People often conflate or equate a database with a physical server。

 but a database can just be one of many programs running on a server。

 but especially when you start to have lots and lots of data that server tends to serve up databases as a dedicated feature。

 So within a database， we might have different formats， we might have different formats。

 For instance， we might store most simply our data in which generally known as a flat file database。

 This might literally just be a text file inside of which is all of your data。

 Now that data might be structured in some sense。 for instance。

 you might essentially store it in rows and columns。 but if you have a flat file database。

 all you have at your disposal， typically is a text file。

 maybe something like a do csv file for comma separated values。

 whereby you very casually use commas to separate each of the pieces of data within rows and each row is implemented by a new line。

 a new line， a new line。 So you effectively have rows and column。



![](img/3741fde3a9a19aa400591a39252631a8_5.png)

![](img/3741fde3a9a19aa400591a39252631a8_6.png)

Even though depending on the length of the words and characters they're in。

 the columns might not line up perfectly visually but if you open that CSv file in the right program。

 it might actually be formatted quite nicely。 It doesn't have to be commas。

 it can be tab separated values or TsV sometimes people use pipes which are vertical bars characters on a keyboard that might work as well and generally you use those characters to separate one piece of data from another and it might actually be a binary file as well it may be a proprietary format of sorts。

 but it's at the end of the day just in individual file In fact。

 let's consider what a cv file might look like specifically for instance in the past we've played around with storing names and numbers akin to storing names and numbers in a phone book and in fact let me go over here to Vs code and inside of Vs code I've prepared in advance one such csv file called phonebook csv just that we can focus our attention entirely on the contents thereof I'm gonna go ahead and hide my activity bar as usual I'm going to go ahead and hide my Expr and then in my terminal window I'm gonna to go ahead。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_8.png)

![](img/3741fde3a9a19aa400591a39252631a8_9.png)

![](img/3741fde3a9a19aa400591a39252631a8_10.png)

![](img/3741fde3a9a19aa400591a39252631a8_11.png)

![](img/3741fde3a9a19aa400591a39252631a8_12.png)

Run code a phone book do CSV to open up this premade file。 Now， in this file。

 we see some familiar names and numbers。 Sorry， I can get rid of the。



![](img/3741fde3a9a19aa400591a39252631a8_14.png)

Header here， so let's rewind just slightly。

![](img/3741fde3a9a19aa400591a39252631a8_16.png)

All right， so。In fact， let's go over to VS code。 I don't remember quite where I did the transition。

 but I think。So let's go over here to VS code and as you okay。😡，Let's go over here to Biesco。In fact。

 let's go over here to VS code。 And as usual， I'm gonna to simplify the interface。

 and I'm going go ahead and hide my activity bar。 and I'm going go ahead and hide my explorer。

 And then down here in my terminal window， I'm going to go ahead and open up this file that I made in advance called phonebook cv。

 and in phonebook CSv willll see six lines of text and the seventh there is still blank。

 And you'll see in the top row， we have name， comma number。 And then below that。

 we have actual names， comma numbers。 Now those are the same names and numbers that we've seen before when we explored our data structures in the past。

 But in this particular case。 this is just a text file whereby the values therein are indeed separated by commas。

 Now， again， here you see because these words are of slightly different lengths。

 the commas don't line up perfectly。 But that's okay。

 because if we were to open up this file in say Microsoft Excel or Google sheets or Apple numbers those programs could determine where those comms are and then actually display the data to us in pretty rows and columns。

 But this is a Cv。

![](img/3741fde3a9a19aa400591a39252631a8_18.png)

In the sense that we have comma separated values， indeed， noteworthy though。

 is that that very first row is sort of a heading row。

 which indicates that the first column represents names and the second column represents values。😡。

And just so we have it in case we need it header row。Header row。Header row instead of heading row。

 if that's okay， to take that audio instead。Okay。G one second。

But the catch with these CSVs is that there's really no built- in functionality If we were to try to open this file programmatically with code。

 we could absolutely read the file top to bottom， left to right using something like Python and presumably a loop but we don't necessarily have built- in functionality if I want to just immediately look up for instance my name and number or John's name and number or anyone elses。

 we' would have to write code entirely that solves that problem but if we instead use not just flat file databases and CSVs for instance specifically。

 but instead we use a proper relational database， not only do we have the ability to store lots and lots of data。

 lots more data in fact， we also have typically built- in functionality via which we can query for data。

 save data and do so much more as well so a relational database at the end of the day is a collection of data that also provides us with functionality but that also supports relations across the data therein and we'll see along the way what we mean by that for instance。

😡，is a list of familiar now schools ha MIt and Oxford and the corresponding cities in which they are based just so happens that Harvard and mit are indeed here in the same city of cambridge this though is。

Okay， sorry。Re okay。Real database。Here， for instance， is a sample database， if you will。

 containing two columns， school and city， and indeed there's a。😡，Sorry， this is new material。Mm。

What's it。Let's consider a simple example here， for instance。

 as a data set containing schools and cities that we've seen before。 we have Harvard。

 MIt and Oxford at left and the corresponding cities at right。

 and indeed it's noteworthy that both Harvard and MIT are indeed in the same city of Cambridge。

 suppose though that we have a fourth school in the mix。

 the University of Cambridge in the UK which happens to be in another city called Cambridge。

 but not the same Cambridge。 Well unfortunately if we're storing our data simply in these rows and columns as such。

 there's a risk of。Sorry。2。Do we have the iPad off stage here？Not at the moment but。Hello world。

 My name is David Main， and today is all about deploying databases。

 particularly when we have lots of data that we want to store at scale。 Now， what do we mean by data。

 Well， really just information and that information might be textual in nature。

 It might be binary in nature that is to say files and such。 But at the end of the day。

 we want to store all of this data in what's generally called a database。

 which is a collection of data inside of a computer system。 Now。

 that database might be a specific piece of software， for instance。

 popular databases include Oracle and SQL server， MySql， Postgres and others。

 but people often conflate the server itself with the also Darn it。😡，Tighting it up。

 Let's do it again。Okay。I what the。Okay， here we go。I promise we'll get this right。Hello world。

 My name is David Main， and today is all about deploying databases。

 particularly when we have lots and lots of data that we want to store at scale now what do we mean by data well really just information and that information can be textual in nature or perhaps binary in nature that is to say files and such and at the end of the day we want to store all of this data in a so-called database。

 which is a collection of data in a computer system Now databases specifically tend to be actual products that you can download and install on a computer。

 for instance oracle and SQL server Mysql and Postgres。

 but there's different types of databases altogether and along the way today we'll explore exactly what forms those take but let's consider then for example。

 what some other terms might be that we encounter in this world of data more broadly you might hear of a data warehouse which is really a database of databases。

 all of your data somehow combined in one place a datamar which is actually just a subset thereof so this might just be your marketing database financial database or something else more narrowly defined and then you have data。

Wch are sort of hot messes of data whereby you might just dump all of your data and Pfs and files and Cv files and more。

 generally with the intent of coming back to it later。

 but it's not necessarily as organized as other format might take but today will focus indeed on databases which are organized collections of data and those collections themselves can take different forms。

 For instance， perhaps the simplest way of storing a lot of data is inside of a socalled flat file database。

 which literally means just storing your data in a file， maybe a text file。

 maybe a binary file Now that file might be structured， for instance。

 a very common format for flat file databases are cv files for comma separated values。

 whereby all of the textual data in your file is somehow organized effectively into rows and columns the rows are straightforward to implement in a so-called CV file because you just put one line of data per row per row per row just hitting enter at the end of each of those lines and then within each of those lines or rows。

 you can indicate。The presence of a column or more specifically in the individual cell by separating the data on that line with。

 for instance， commas。 Now there's alternatives to these。

 you might be familiar with TsV files tab separated values。

 sometimes people use vertical bars in order to delineate data within such a file're the choice of character is really up to you。

 but it does influence exactly what type of software or how the software reads that file subsequently Now。

 if we want to take a look at an example， let's do just that。

 we've seen in the past some sample data involving like names and numbers。 and in fact。

 I brought such as an example with me already。 let me go over here to VS code。 and as usual。

 just to simplify the interface， let me go ahead and hide my activity bar hide my file Exper and then down here in my terminal。

 Let's go ahead and open up a file that I made in advance called phonebook cv for again。

 comma separated values What do we see Well， the first line of this file is curiously a little bit different from all of the others。

 It's the so-called header row。

![](img/3741fde3a9a19aa400591a39252631a8_20.png)

![](img/3741fde3a9a19aa400591a39252631a8_21.png)

In the file and you'll see that it says name comma number and that effectively indicates that this file effectively has two columns worth of data。

 the first of which represents names， the second of which represents numbers phone numbers specifically the comma therefore indicates exactly where one column begins and ends therefore below that we have those names and numbers。

 Brian， David Doug， Eric and John followed by each of their numbers with commas they're in Now we got lucky in some sense in this particular data set in that none of the names in none of the numbers naturally have commas themselves。

 but suffice it to say that if any of your data in a cv file actually needed to contain actual commas grammatically that's fine。

 there's different ways of escaping the data， for instance。

 putting all of the data in one cell so to speak in for instance。

 double quotes it just requires that whatever software you're using to open or process these files knows to treat those quotes in such a way that they're not literal quotes but meant to keep。

gether， words or phrases that might otherwise have a comma that could confuse that whole process。

 but this data nicely enough is fairly simplistic。 and we have ultimately a whole bunch of names and numbers in this file but what we don't have is the ability right now to actually read this data very in a very user friendlyly way。

 we could certainly write some python code that reads this file top to bottom left to right using something like a loop in Python。

 But if I wanted to look up my number specifically or John's number specifically we would essentially have to read the entire file searching for searching for searching for my name or Johns at which point then we have the actual name Moreover。

 if we want to make changes to this file or we want to make additions or deletions。

 that's a fairly manual process whereby we have to open up the whole file go in there and make the changes。

 In other words， insofar as this is just a flat file a file alone。

 there's no inherent functionality offered to me to get more user。



![](img/3741fde3a9a19aa400591a39252631a8_23.png)

![](img/3741fde3a9a19aa400591a39252631a8_24.png)

Friendly functionality， I dare say we need to transition from a flat file database to something like a relational database where a relational database generally refers to software that not only stores your data for you。

 but also provides you with some core functionality Moreoverover。

 that software allows you to relate data within your set of data to each other in different ways。

 Let's consider， for instance， a simple example。 Here is a data that we've seen before three schools。

 Harvard， MIT and Oxford and the cities that respectively each of them is in it happens to be the case that both Harvard and MIT are in the exact same city of Cambridge。

 but otherwise Oxford is across the pond in Oxford UK but suppose we add another school and city to the mix。

 namely the University of Cambridge also in the UK in the city of Cambridge。

 Now this city of Cambridge is different from this city of Cambridge。 So now we have two problems。

 we have arguably an inefficiency insof far as for both Harvard and MIT we're storing Cambridge。

Whi seems best redundant to have to say the same word Cambridge in two places per our discussion in the past of just trying to avoid duplication even in though this case factually it's true there's also now a problem of disambiguation whereby this Cambridge is in the UK these are in the US but at first glance it's not obvious that those are actually different now we could chip away at some of these problems by just adding for instance Cambridge comma UK and Cambridge comma Massachusetts comm USA to be ever more precise。

 but that still doesn't eliminate the redundancy and it also doesn't fundamentally ensure long term that we're not going to run into the same problem again so let me propose that we take a data like this which might be stored very simplistically in a CSV file but begin to take steps toward storing it in a relational database instead for instance。

 let me propose that we explode this single table of data into two tables initially one for the schools。

😡，One for the names。 Then let me propose that we assign a unique identifier to each of those cities。

 for instance， a very simple number， like an integer， starting with the number one on up。

 These ideas could technically be anything。 but by convention。

 it's often the case that you just use simple integers starting at one moving up toward eventually infinity。

 Now this in and of itself hasn't really done much for us because I haven't yet related those cities to these schools。

 but suppose now I go over to this table of schools。 And in addition to their names。

 I had another column that's going to allow me to keep track of the city in which that school is。

 but no longer using its name using that city Id instead。

 So now I have an indication that both Harvard and MIt or in the same city。

 Aka number one Oxford is in the city aka number two。

 but Cambridge is in the city of number3 there by disambiguating between the two Cambridges。

 Now I can maybe just for thoroughness and for future。

proofing in case we encounter more problems like these add another column to this first table for school I。

 Now， those numbers can and in the real world are very often the same 1，2，3 on up toward infinity。

 but they're not used for the same purpose。 It's perfectly fine for multiple tables all to use very simple integers。

 even though those integers might indeed overlap context is going to matter。

 And indeed that is why in this table at left， which I might call my schools table。

 I have city I very explicitly stated so that it's not going to be misinterpreted as a school Id。

 So these 1，23，4s are different from these 1，23s， but there are both Ids in the sense that I'm now using them to uniquely identify my data And thus was born。

 the first of our relational tables inside of， if you will， a relational database。

 This is a database。 And so far， it's a collection of data and it's relational inof far as I have used these unique identifiers to relate some of my data。

Other data。The downside now is that this does not look particularly user friendly。

 I took the simplest and most convenient of file formats that of a CSv， for instance。

 that had all of the names and numbers right there in front of me。

 indeed we saw that a moment ago in tabular form and now I've created two tables with these arbitrary numbers that somehow create these associations。

 but I've just created work for myself because now I have to minimally sort of line up the numbers and figure out which school is in which city So wouldn't it be nice if the database itself provided me with a bit of functionality that allowed me to just as easily as before get at the answers I want when it comes to this data and the answer I might want is in what city is Harvard in what city is Oxford and so forth。

 Well， that too is what we typically get in a relational database which is some inherent functionality that we can leverage to solve problems like those So what does this mean Well。

 we're going to introduce ourselves now to another programming language this one called SQL。

For structured query language or SQL for short and SQL is typically the language used with relational databases via which to query data and also update your data and delete data and insert more data and do anything you might want with it it allows you then with code to automate the process of more generally reading and writing data。

 So what does this allow us to do。😡。

![](img/3741fde3a9a19aa400591a39252631a8_26.png)

![](img/3741fde3a9a19aa400591a39252631a8_27.png)

Well really four basic operations。 and there's this acronym that might help you remember it。 Cd。

 which a bit crudely stated， which has four letters in it。

 each of which represents one of the core features of， for instance。

 SQL C stands for create R stands for read U stands for update and D stands for delete So even though we're about to dive into really a whole new programming language that does has some similarities with languages like Python and even jascript at the end of the day。

 all it can do is these four fundamental operations。

 Now these themselves are not necessarily the commands or functions， if you will。

 that will run within the SQL database， but they're quite similar。 In fact。

 we'll see that in the world of SQL reading data that is accessing it and using the data in some form actually uses a command called select but create and update and delete are in fact。

 used to do any number of things。 insert also exist when we want to insert new data。

 And if we want to not only delete data but drop all of our data that is an。

Higher table thereof we can use a SQL command known as D as well。

 So even though we're about to take a tour of a brand new programming language。

 you'll find that SQL is incredibly powerful when it comes to manipulating data。

 reading and writing it， answering questions about data， doing data analysis。

 data science more generally and indeed SQL is especially powerful insofar as it's a different type of programming language than both Python and jascript whereas both of those languages where at least as we saw them very procedural in nature。

 if you wanted to use them to solve a problem you had to tell the computer step by step using Python or javascript lines of code。

 exactly what to do， exactly how to iterate， exactly what questions or Boolean expressions to ask SQL is known as a declarative language where it's closer to using English to just declare what question you have without worrying as much how to specify how to get from that question to the answer you needt worry。



![](img/3741fde3a9a19aa400591a39252631a8_29.png)

So much about loops， so much about variables， so much about conditions。

 you can instead say dare' say a little closer to English。

 exactly what data you would like to select， update， delete， or insert into your database。😡。



![](img/3741fde3a9a19aa400591a39252631a8_31.png)

So let's take a look， given that we have these commands in front of us。

 let's go ahead and explore how we might create one such table。😡，one sec。Okay。Here， for instance。

 is the first of the commands that we might execute when trying to create a SQL table in a relational database for the very first time。

 you would literally type out create table， then per the lowercase here。

 you would type the name for your table。 maybe it's phone book or something else。

 Then in parentheses， you would specify the name of a column that you want to store therein for instance。

 name or number， And then some specification of type， Is this a number。

 Is this a string of text or something else。 And then you can do that one or more times for additional columns as well。

 But how do you do this and where do you do this。 Well， you can use any number of database systems。

 Indeed， I mentioned oracle and SQL server， minusql Postgres and dozens dozens more。

 but we're going to use a fairly simple version of SQL for this particular class so that we can focus really on the ideas and not necessarily anything proprietary in nature。

 and we're going use a variant of SQL called SQL light And the command that will use to interact with this lightweight version of SQL is itself called SQL light 3。

 Now this isn't。

![](img/3741fde3a9a19aa400591a39252631a8_33.png)

That SQL light is a toy version of SQL。 In fact， it's very commonly used in web browsers and mobile applications alike。

 but it doesn't necessarily have as many features as some of those commercial and other open source tools might have that are particularly well suited for the largest sets of data Now we'll still use some fairly large datas today。

 but not necessarily in the millions and billion of rows that you might have out there in the real world。

 So how can I use SQLL 3， for instance， to create my first database and within it some table。 Well。

 let me propose that we first create a database as follows。 Let me go back to Vs code here。

 Let me go ahead and close phone book do cv， but in a moment， we'll use that within our own database。

 I'm going go ahead and increase the size of my terminal window here in order to see more on the screen。

 And I'm gonna type this command。 SQL light 3 space phonebook do db just by convention。

 I could call this file anything I want but do Db willll indicate to me and other people that it's a database and indeed I want the data theyre in to represent。



![](img/3741fde3a9a19aa400591a39252631a8_35.png)

That of a phone book。 Now， how can I actually get some preexisting data into this database。 Well。

 at the moment， there's nothing inside of it。 I've just created an empty database。

 but there's a few commands supported by SQL light 3 specifically。

 and Oracle and SQL server and my SQL and Postgres and others have comparable commands。

 I'm going go ahead and temporarily put my SQL light 3 program into Cv mode。

 I'm then going to import my existing phone book do cv file into a specific table。

 And then I go ahead and quit altogether， just prove that it's worked。 Allright， so let's do that。

 let me go back here to V S code。

![](img/3741fde3a9a19aa400591a39252631a8_37.png)

![](img/3741fde3a9a19aa400591a39252631a8_38.png)

![](img/3741fde3a9a19aa400591a39252631a8_39.png)

Let me go ahead now and at my SQL light prompt note my prompt has changed from the usual dollar sign to SQL light and an angle bracket to indicate that the SQL light 3 program is still running。

 I'm going go ahead and type mode CSv and nothing seems to happen。 But in general。

 that's a good thing。 if I see no errors。 I'm then going go ahead and import the file called phone book dot cv。

 which recall is in the same folder in which I ran this command a moment ago。

 and I could call this anything， but naturally I'm going to call the table into which I want to load all of this files contents quite simply phonebook。

 And now you'll note within SQL lights prompt， I'm using these dot commands to indicate that these are specific to SQL light 3。

 but before long， I'm going no longer have those dots in front of my commands because they're gonna to be SQL commands from the programming itself moving forward。

 So I'll hit enter there too， nothing seems to happen。

 So let's do dot quit to exit out and I'm back at my prompt at this point in time。 I now。😡。

A brand new database file called because I chose this name Phbook do Db and I can proceed now to reopen that for instance and show you what's inside so let me again run sQL light3 of phonebook do db and hit enter I'm back at my prompt and nothing seemingly has happened yet but if I run dot schema now this is going show me the so-called schema of my database the schema of a database is the design of its columns in particular the names thereof and the types thereof as well as potentially some additional constraints So here at my SQL lightpro if I do do schema what I'll see is a command that I didn't actually run but that was automatically run for me when I imported that phonebook do csv。

 This is not necessarily the typical way that you would create a database out of a cv file but it's one way though in the future when we know in advance what kind of data and how much of it we're going to have and it's not necessarily a file we're importing from the start we're going go ahead and design the schema for our future tables。



![](img/3741fde3a9a19aa400591a39252631a8_41.png)

![](img/3741fde3a9a19aa400591a39252631a8_42.png)

![](img/3741fde3a9a19aa400591a39252631a8_43.png)

And then load in data。 But in this case， I've used that dot import command specific to SQL light3 just to get things started more quickly。

 and you'll see here effectively the line of SQL code that the dot import command automatically triggered for me create table if not exist just in case I might have run this command before quote unquote phone book which is the name of the table I wanted to create a column called name the type of which is text and another column called number。

 the type of which is text as well and all of that as before is inside of those parentheses and then lastly I finished my thought here。

 it would seem with a semicolon， which in many programming languages SQL often among them is how you would terminate a thought much like a period after an English sentence Now I'm back at my prompt but there's no data apparent just yet all that we've seen is the schema so to speak of my database but not the data therein。

 So how do I get at those names and numbers within this new database Well here's the。



![](img/3741fde3a9a19aa400591a39252631a8_45.png)

Format of a select command via which you can select that is read or access data in one of these tables。

 The command syntax is to say select， then you can specify one or more columns that you want to select from a table and you can specify the name of that table Now。

 I've by convention here done this。 I've used all capital letters in uppercase for anything that's SQL specific。

 So there are keywords in SQL， much like we saw in Python and jascript among which here are select and from but the columns happen to be my choice of names。

 as is the name of the table。 So just for clarity， I've used lowercase there。

 that's not strictly necessary。 SQL light in in general SQL the language won't really care what you uppercase with respect to command but the column names。

 the table names， those should be considered case sensitive so that you or consistent with how you name them from the get go。

 Now， how can I go about selecting some actual data。



![](img/3741fde3a9a19aa400591a39252631a8_47.png)

![](img/3741fde3a9a19aa400591a39252631a8_48.png)

![](img/3741fde3a9a19aa400591a39252631a8_49.png)

Well， let's go ahead。Shi。啊。😊，I just want to check in。

So how can I go about selecting data from this first table Well let me go back to VS code here。

 let me zoom in a bit so the text is a bit bigger and now let me go ahead and clear my SQL my SQL light prompt so that I can focus entirely on what's new I'm going go ahead now and just per that canonical example type select and now I want to select the columns of interest which will be name common number and I want to select those two columns from the table called phone book and they'll finish my thought with the semicolon when I now hit enter you'll see using sort of ASI art if you will the tabular form of the data that was loaded from that CSv now into this SQL light database and here we have the column of names and the column of numbers but notice this perfectly correspond to what I select and if for some reason I don't care to see the numbers at this point in time。

 I can do something slightly different I can just say select name from phone book and indeed SQL will give me just that。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_51.png)

![](img/3741fde3a9a19aa400591a39252631a8_52.png)

While I can do select number from phonebook and similarly will the database oblige So already here I seem to have more expressive capabilities than with something like a flat file database in CSv whereby even though I could open that CSv either in VS code or Microsoft Excel。

 Google sheet's Apple numbers， I wouldn't necessarily have this precision with which I can select subsets of data I could see it with my human eyes and to be fair in those spreadsheet programs。

 we do have lots of functions but we'll see we have functions inside of a SQL database as well Now it turns out when you want to just select everything in a database table if only to wrap your mind on what's inside of that table。

 turns out there's a common convention， which is to use a wild card。

 which is something we've seen in the past， albeit in different context I can do select star from phonebook and no matter what the columns in the phonebook table are called this is going go ahead and give me everything as we saw before so it's not strictly necessary for me to enumerate each and every column especially if there's lots。



![](img/3741fde3a9a19aa400591a39252631a8_54.png)

Of them。 But indeed， SQL has supports a whole bunch of functions as well And particularly when your data is numeric。

 you can do things like average things together。 find lower。

 find maxa and minima So you can if it's textual in nature。

 you can force things to uppercase or lowercase。 You can check for distinct values that are unique。

 and you can even count the amount of data there in。 So how might we use some of these。 Well。

 let me go back to Vs code here。 again， I'll clear my terminal and propose that if your question is not what are the names herein and what are the numbers。

 But how many of them are there， we can do this in a number of ways。

 We can do select count the number of names from phonebook and then hit enter there and we get back 5 equivalently I could do select count number from phone book。

 And I should get back the same result。 In fact， when using this count function in SQL。

 It's quite common to be a little more succinct and say select count of star because you don't really care which。



![](img/3741fde3a9a19aa400591a39252631a8_56.png)

lumYou're counting because by definition of how SQL tables work。

 you're always going to have the same number of cells in every row。

 even if some of them might end up being blank。 So I suffices to say select countstar from phone book。

 Then a semicolon and enter。 and I'll get back indeed the same response。

 But suppose now I'd like to know what the distinct numbers are in this phone book。

 because we've seen before that some of the staff actually share a main number to do that。

 I could do initially select number from phonebook。

 but that again is going to return all of the rows irrespective of duplicates。

 And so I can apply one of these functions now and say select distinct number from phonebook。

 And as you might guess， I should only now see to the two unique numbers that are across that phone book。

 Now it's obviously easy for my humanize just count two unique numbers。

 But suppose this were a larger data。 and you were interested in how many distinct values there are。

 but not necessarily what those distinct。Use are well， you could combine these same ideas。

 And I could say select count of distinct number from phonebook semicolon enter。

 and I get back my answer of two。 So already， I seem to have more declarative abilities with this particular language where I can just select exactly what I want。

 Now it's not quite as user friendly is using natural language in English。

 that is your own natural human words， but there's a relatively simple set and finite set。

 certainly of keywords that you can use in SQL these than are just some of those。 Well。

 what more can we do with SQL。 Well， it turns out we can be even more expressive with keywords like these。

 I can group related data together。 I can search for something like a value。

 but not necessarily exactly some value。 I can limit the results to just the top 10 top 100 or some subset of the total number of rows。

 I can order the data。 that is sorted by a particular column in ascending or descending order。

 and then I can。😊。

![](img/3741fde3a9a19aa400591a39252631a8_58.png)

![](img/3741fde3a9a19aa400591a39252631a8_59.png)

Have a pred of sorts， whereby I can say only give me the row where the following Boolean expression is true。

 So within SQL， we have some of the same ideas that we saw in a language like Python and then jascript。

 But you'll find that by reading it left to right， It's more akin to just asking the computer system for what you want。

 So for instance， let's go back here to VS code， And let's select the number for John specifically。

 Now， if I were to do this in Python or even jascript。

 I would probably open the file read up from top to bottom left to right。

 constantly checking with a conditional and a Boolean expression is the current name John is the current name John is the current name John。

 And that's fine。 that would be a very procedural approach to the problem。 But in SQL。

 I can declare my intent as follows。 I can select the number from the phone book where the corresponding name equals quote unquote John using single quotes here in SQL by convention。



![](img/3741fde3a9a19aa400591a39252631a8_61.png)

![](img/3741fde3a9a19aa400591a39252631a8_62.png)

Hitting enter。 and I get back just the number I care about Now， conversely。

 if I want to see all of the names of staff who have the same number in mind while I can do select name from phone book where the number in question equals quote unquote plus 1。

6，1，7，4，9，5，1000 close semicolon and enter and now I get back Brian。

 David Doug and Eric who all share that specific number。 Now， of course。

 I can just eyeball this and see that four of us have the same number。

 but if I only care about the count， I could do this。 And now to save some keystrokes。

 I'm gonna do a technique much like my general command prompt whereby I can scroll back in time with the up arrow and move down back and forth to go through my history if I hit up just once。

 I get my whole command again， I can go ahead now and scroll here and say， you know what。

 don't just show me the name， show me the count of the names。

 So I'm gonna to insert that function call that we saw before of count。

 hit enter and now I get back quite simply the answer。

But what if I want to count and see at the same time the names and numbers of people。 But sorry。

 let's say that again。But what if I want to see at the same time the names and oh sorry。

But what if I want to see in this phone book the number of times that each number appears in total。

 So ideally 4 in one respectively， how can I do that， Well。

 you can express that notion in SQL as well。 Let me go ahead and select first a number。

 but also the count thereof using familiar syntax from that phone book， But this time。

 group those numbers together。😡。

![](img/3741fde3a9a19aa400591a39252631a8_64.png)

![](img/3741fde3a9a19aa400591a39252631a8_65.png)

As follows by saying group by number， you're telling SQL to essentially look through that column of numbers。

 group all of the like numbers together so that you can perform this aggregate function of count on those grouped by numbers。

 So if I hit enter now， we'll see that that first number which is common across several of us Indeed is shared by four names。

 but the last of those numbers who's just Johns only has a account there for of one。 So again。

 using syntax like this， we can pretty readily express the questions that we might want to ask about this data set or any other。

 Well， what more can we do with SQL Well， turns out if we want to not only select data that is read。

 we can also delete it for instance， if I decide that you know what I don't want to be in this phone book anymore。

 I can delete my own self， let me go back to VS code here。

 I'll clear my prompt and begin now with a new command delete from the phone book where how do I filter myself out。



![](img/3741fde3a9a19aa400591a39252631a8_67.png)

![](img/3741fde3a9a19aa400591a39252631a8_68.png)

Well， let's see。 I don't want to just delete from the phone book entirely because if in fact。

 I were to be a little sloppy and dares say hit a semicolon here。 don't hit enter。

 that would delete everything from the phone book。 Therefore。

 I want to use a more narrowly defined predicate a where clause that specifies that I only want to delete rows where some Boolean expression is true。

 And I think if I'm seeking to delete myself。 I really want to say where name equals quote unquote David。

 and then hit enter。 Nothing seems to have happened。 But as we begin。

 let's do select star from phone book。 and see what's now in the database。 And indeed， I am now gone。

 We see now Brian Doug and Eric with those same numbers， But John is there as well， but no David。

 All right， Well， suppose I quickly regret that。 how can we put myself back。 Well。

 it turns out in SQL， you cannot only select and delete， but also insert data therein。

 So here is the canonical format for how you might insert a new row or even rows into。



![](img/3741fde3a9a19aa400591a39252631a8_70.png)

To a table you literally say insert into and then the name of the table。 then in parentheses。

 you specify one or more columns into which you want to insert new data。

 Thereafter you say literally values。 and then in another set of parentheses。

 you literally specify one or more values that corresponds to that number of columns that will have the effect then of inserting into a new row。

 precisely the values you indicate。 So let's see how this might work。

 Let me go back to VS code now and let me insert into that phone book， the name of。



![](img/3741fde3a9a19aa400591a39252631a8_72.png)

David， as before， of course， you might realize now I'm forgetting to insert one other value。

 but that's fine。 It's up to me to insert if I so choose just a subset of data that seems to be successful。

 Let me scroll back in time to commands and reexeccutute select star from phonebook to now see the result。

 And indeed will now see that David is back。 albeit in a different order。

 but that's fine because I never seem to care about the order previously。

 but my phone number is null。 null， then is this special Sentinel value。

 which is distinct from the empty string。 That is the presence of a value that just happens to be blank。

 null means we never even put anything there， and it's a so-called Sentinel value that's useful because it indicates the deliberate or even accidental but glaring omission of data。

 It's not just that the user left something blank It's that your command。

 your sQL statement didn't insert anything at all。 So how can we resolve this。 Well， thankfully。

 there's the you in crud for。

![](img/3741fde3a9a19aa400591a39252631a8_74.png)

Update via which we can not only select and delete and insert， but also update our table。😡。

As follows， the syntax here is a little bit different。

 but it's to say update and then the name of the table then set followed by a whole bunch of key value pairs as in the past。

 the name of the column that you want to update and the value that you want to give it。

 And if you so choose a comma separated list of additional columns and values。 But in this case。

 I'll do just one， but I want to specify where this update should apply。

 If I were to omit the where clause， and just in my thought with the semicolon。

 this would update the entire table setting every columns value。

 every value in that column to the same value。 So how might I do this more carefully。 Well。

 let's go ahead and do update phone book set the number to quote unquote plus 1，6，1，7，4，9，5。

1000 where and only where the name is quote unquote David， if I had omitted that where clause here。



![](img/3741fde3a9a19aa400591a39252631a8_76.png)

What would happen Well， I don't think it would really affect Brian Doug or Eric。

 but it would affect John insof far as his number was different。

 but would no longer be if I didn't specify that this update should only apply where the name is indeed David。

 Now nothing seems to have happened， but indeed， that tends to be good。

 Let me scroll back in time and select star。 and now we see that I'm back in the phone book。 Now。

 if you don't like this ordering for some reason， or the whole point of this database is to show an alphabe about alphabetical list of your contact。

 Well， that too， we can address as before， let me go ahead and do select star from phone book。

 but let's order this by the name column。 Now you'll see that everyone's name is an alphabetical order as before and the number still correspond appropriately。

 if though you wanted to do this not in the default order。

 which happens to be ascending ASC for short， but descendending D E SC for short。

 you can do the same。 and now the order of the names is entirely flipped and you can apply。

That ordering to any column in some table。😡，Okay， let's take a couple minute break。So far， so good。



![](img/3741fde3a9a19aa400591a39252631a8_78.png)

Alright， let's transition now from our own tiny phone book to an actual real world database that comes to us from IMDB。

 the Internet movie database， which has a whole lot of information on actors and TV shows。

 movies and more within this database， you can imagine the need to store data in a fairly careful fashion because if you have thousands。

 maybe even millions of rows， you're gonna want to store things as efficiently as possible。

 So how might you go about storing for instance， the names of some TV stars in a database like this Well。

 we could， for instance， for a TV show like the office。

 put the name of the show in the very first column And then thereafter in each subsequent column。

 we could put the name of a star in the show So we have star star star， star and star。

 at least for those who receive top billing at the start of this particular series and then for any other show。

 we could add another row and another row in another row and then each of their main stars as well。

 But no matter what show might come to mind， you can imagine。😊。

InThe number of stars and it not necessarily being5。

 So some of those subsequent rows might have fewer columns or more columns。

 simply depending on the number of TV stars therein。 And that should rub you the wrong way。

 because if nothing else visually， the data is going to become very ragged whereby none of the edges。

 so to speak will line up and that in and of itself isn't so much a problem。

 but it does suggest a sort of sloppiness whereby your data is not all the same。

 So this tends not to be the best solution。 indeed， in general and relational databases。

 if you're in the habit of adding more and more columns， you're probably doing something wrong。

 unless the schema fundamentally for your data has very deliberately changed It's much more the common case to add more and more rows to a data in a relational table and so we should aspire to do something more like that。

 Now， we could， for instance， restructure things as follows into a two column table。

 therebyby assuaging my concern。 but now。We have sort of a new problem that we've seen before in other places whereby I've got lots of duplication。

 the office， the office， the office， the office， the office。

 which if nothing else is just wasting space now by storing literally the same name of a show multiple times。

 And as in the past， it might invite mistakes at some point because if I change the capitalization or spelling of some show's name I might not remember to make that change in all five places。

 So this is just asking for trouble So how might we do this a little bit better。

 let's propose that we do it is a relational table and introduce as before some of those unique identifiers。

 Let me propose， for instance， that we have one table here for the shows themselves in this case just one。

 but you could imagine having more and more rows for more and more shows in that table will'll have a title column for the title of the show。

 but will also start to have an I as well。 And rather than start it one， I've consciously chosen 38。

6，6，7，6， which happens to be the unique identifier in the actual。



![](img/3741fde3a9a19aa400591a39252631a8_80.png)

![](img/3741fde3a9a19aa400591a39252631a8_81.png)

Ne movie database for this version of the office。 Meanwhile， we'll call this new table shows。

 which makes perfect sense。 Meanwhile， let's have another table for instance。

 over here that has the names of all of those TV stars。

 but let's associate with each of them a unique identifier as well。 And again。

 rather than start it 1，2，3，4 and so forth， I'm using the actual identifiers from IMDB。 for instance。

 Steve Corrells is 13，6，7，9，7 arbitrary。 but consistently the case throughout their entire data set。

Now， unfortunately， at the moment， at a glance， there's nothing linking this data together。

 nothing relating one table to another， but even here I think we can solve this。

 not necessarily by adding a new column to these shows or now these people but in some cases you can even use a third table that somehow relates one to the other and in fact I'll propose here in the middle that we could have a third and final table。

 maybe called stars that creates that relation across these two tables。

 the first column of which I'll say is show ID which corresponds to the ID column in the show's table。

 the second column of which is person ID which corresponds to the ID column in the people table Now this is just one convention in different people。

 different companies might have different ways， but it's not uncommon to name your tables in the plural form of these words to then name the unique identifiers in most of the tables quite simply ID in all lowercase and then in an intermediate。

able like this， whose purpose in life is to relate one table to another to use the singular form of the table。

 followed by an underscore followed by ID but again。

 capitalization spelling conventions might differ， but this is just one way that I'll use uniformly as we explore this particular data set now unfortunately here too even though you might now see that oh the stars table links this particular show386676 with this particular person 136797 it's a lot more work certainly for me is a human we my humanize to now link these pieces of data together I can see of course that this ID here corresponds to this show here and this person ID here corresponds to this person here but it was a lot more convenient before when it was just all right together in the same table so on the one hand we've sort of addressed some of the problems we identified of redundancy perhaps ambiguity and the like but we've introduced new problems in that the data is like all over the place。



![](img/3741fde3a9a19aa400591a39252631a8_83.png)

This， too， is a problem that SQL can solve for us。 So let's consider this same data。 But in more。U。

 let me see。So let's consider this same data。 But how we might。 Let's consider this same。

Let's consider the same data。So let's consider the same data。

 but consider how we can get the answers we care about。

 so pictured here now are in the shows table and starss table， all of the IDs and column。😡，Dammon。

And that's。So let's use this same data now to consider how we can get at answers to questions we care about。

 So highlighted here now is the same Id in both the showss table and stars table。

 making clear that all of the persons in the latter， the stars table belong to that same show。

 Meanwhile， between the stars and people table， notice that there's indeed this correspondence between these Is pairwise。

 Wouldn't it be nice if we could represent more succinctly in SQL code。

 how we can join these values somehow back together， Well。

 let's take a step back and consider that not only is there more data like this。

 we can sort of take a bird's eye view of the design of or schema for this。Oh， man， I'm sorry。

I forgot where this was going。Let's consider。Okay， here we go again， sorry。Now， using the same data。

 let's consider。😡，啊。That was the problem。Now， just to be clear。

 let's consider exactly what data is in common across these three tables。

 So highlighted here is the same show ID in the shows's table as well as in stars indicating that all of the corresponding person Is are somehow associated with that show。

 Meanwhile， between the stars table and people table do we have the same Is pairwise in each of the same indicating that each of those people by way of the stars table is indeed associated with that show。

 Meanwhile， there could of course be more stars and more shows so we'll indicate as much with dot dot dot。

 but let's take a step back now and look at the entirety of our version of the IMDB database。

 which we indeed imported for you and for class into these relational tables here then is a diagram that represents the data we're about to explore you'll see some familiar titles here now like shows and people as well as stars but it turns out there's more tables in this database like writers and ratings and genres。

 Let's focus for now。

![](img/3741fde3a9a19aa400591a39252631a8_85.png)

on just two of these and consider how we might implement the simplest， if you will。

 of relations across just two of these tables before we then allow things to escalate into that relationship across three total tables so pictured here as shows is the table that has we'll soon see an ID a title a year and some episodes so this isn't quite as simple as our imagined version of IMDB which just had the stars and the names of the shows but here we have associated with each show a unique ID the title they'of and the year in which it debut in the total number of episodes Meanwhile。

 over here in another table are the corresponding ratings for that show which will map back to the shows's table by way of a show ID a rating on a scale on a numeric scale as well as the total number of human votes that contributed to that rating now strictly speaking。

 we could have put all of these ratings inside of the show。Table by just adding， for instance。

 a rating column and a votes column， but in this particular case。

 the two pieces of data came from two different sources。

 so it's not unreasonable to claim that this table will relate to this one specifically in a one to one relationship。

 That is every row on the left will correspond to one row on the right。

 and that's something we can ultimately enforce at the database level。😡。



![](img/3741fde3a9a19aa400591a39252631a8_87.png)

So what do we mean by this， Well， consider that the shows tables ID column。

 the unique identifier for each show， will naturally line up with the show ID column in the ratings table。

 So let's go ahead and take a look at just some of this data。

 Let me go back to VS code here and clear my SQL like prompt。

 Let me go ahead now and run select star from shows damn it。😡。



![](img/3741fde3a9a19aa400591a39252631a8_89.png)

![](img/3741fde3a9a19aa400591a39252631a8_90.png)

![](img/3741fde3a9a19aa400591a39252631a8_91.png)

Hep。Let's do that again。

![](img/3741fde3a9a19aa400591a39252631a8_93.png)

In fact， let's go back to V S code here， clear my SQL light prompt。

 and let's actually quit out of SQL light altogether。 Now， at this point， I'm going reopen。



![](img/3741fde3a9a19aa400591a39252631a8_95.png)

![](img/3741fde3a9a19aa400591a39252631a8_96.png)

Now， let's go back to VS code here and clear my SQL light prompt and quit out of SQLL 3 altogether。

 Now， instead of opening up phonebook do Db， which was the database we ourselves created using phonebook csv as an import。

 let's go ahead and open up a different database that I brought with us based on IMDB's own data。

 And to do that I'm gonna run SQLL 3 as before。 but this time specify shows do Db。

 which is a much larger database that's been made in advance。

 that brings me back to a SQLL prompt I'll go ahead and clear the same and now run select star from shows。

 but I don't think I want to see all of the shows at once because there's indeed going to be thousands。

 So let's go ahead and limit the result to just the top 10， the first 10。

 If I go ahead and hit enter we'll see here the first 10 shows in the actual internet movie database including its I It's title the year in which it debuted and the total number of episodes。

 Meanwhile， let's wrap our mind around the。Other table called ratings as follows。

 Select star from ratings limit 10。 And I dare say whenever opening a SQL database for the very first time。

 just selecting star from one or more tables is a useful if quick and dirty way to wrap your mind around the actual data therein and just limiting the results again just ensures that your screen is not going to overflow with more data than you care about is just gonna to give me a sense of the format of the data。

 And indeed， here we see three columns in this table show Id rating and votes。

So how can I now maybe see just how large each of these tables is， Well。

 I could certainly run the entire command and just wait and wait and wait for all the rows to come out。

 but let me instead clear my screen here and then do select count of star from shows and we'll see in this particular database。

 we have some 245200 shows。 Meanwhile， there's probably nearly as many ratings assuming that all of those shows have been rated。

 How though can I see how the actual tables themselves have been implemented。 Well， for that recall。

 we can run dot schema and dot schema is going to show me exactly how each of these tables has been defined。

 and let me scroll back to the top of this command and we'll see top to bottom these tables here。

 We have genres and people ratings and shows and down here stars as well。

 Let's focus on the few that we've talked about thus far。

 So at some point or other I or someone else ran the command create table shows Then in parentheses we specified a comma separated list。



![](img/3741fde3a9a19aa400591a39252631a8_98.png)

![](img/3741fde3a9a19aa400591a39252631a8_99.png)

Of all of the columns that we want to create and the corresponding types thereof。

 We'll see now that Id is no longer。We'll see now that Id is specifically integer and that lends itself to being a number like 1。

2，3 or much larger。 We'll see that title is text， but moreover， it's not null。 In fact。

 this is another feature of a proper database where whereby unlike in a CSv where you can put anything or nothing if you want in a database you can specify that users should not be able to insert or update values that contain null so that you ensure that every show in this table is in fact going to have a title。

 Thereafter we see that year is numeric， which seems to be another type altogether。

 and then episodes itself make sense is an integer。 Moreover。

 we then see something mentioning primary key， but we'll come back to that in just a bit。 Meanwhile。

 for people here not surprisingly we have I that's an integer name that is text and not null birth。

 which is presumably their birth year， which is numeric。 and then again。

 some mention of primary key of Id But lastly， let's focus here now on ratings which relate somehow to these shows。

We have here a show I， which is an integer that's not unique。 that's not null， but is unique。

 And this indeed ensures that we'll have a one to one relationship。 ultimately。

 The rating is a real number， which means a floating point value。

 something typically with a decimal point that similarly cannot be null。

 The number of votes is an integer that the too is not null。

 But notice here some mention of foreign key referencing show a foreign key called show Id referencing the shows tables I and we'll come back to all of these keys in just a bit。

 So now that we have that in front of us。 let's take a quick look at the actual data types available to us。

 We saw in Python that we had things like integers。

 as well as strings or stirs for short in SQL light specifically you have access to these primary types。

 Now in other databases like oracle and SQL server minusql and Postgres。

 you have an even longer list of available types that allow you to impose further constraints and formatting on your data SQL like though in soofar as it's a。



![](img/3741fde3a9a19aa400591a39252631a8_101.png)

L weight allows us these five choices here。 Now， integer speaks for itself。 Text is just text。

 Real is a floating point value。 Numeric is something that is like a number。

 typically a year a date or time or something else that generally falls into some standardized numeric format and blob or binary large object really just means a binary value of some sort。

 maybe even a file in the database， though files generally belong in the file system stored in a folder somewhere。

 So that's why we've seen not just text， but integer and other types in this file。

 we can see that there are other constraints we've imposed like keywords like not null。

 which ensures that the database won't even let you omit some value， and unique。

 which ensures that the database won't let you insert duplicate values。



![](img/3741fde3a9a19aa400591a39252631a8_103.png)

![](img/3741fde3a9a19aa400591a39252631a8_104.png)

![](img/3741fde3a9a19aa400591a39252631a8_105.png)

But let's now revisit these keywords that we saw in that schema for IMDB's database。

 namely primary key and foreign key。 we've been using the first of these and really the second without calling them by name thus far a primary key is a column in a table that uniquely identifies each of its rows。

 typically with some simple integral value like one to， three or something much larger than that。

 but a unique value that uniquely identifies every row in that table。

 a foreign key is the presence of a primary key in another table and it's these foreign keys that enable us to create these relations across tables。

 for instance， as before， when we had our showss table which had an I and then we had a stars table which related to that show ID in the first of those it was a primary key in the second of those it was a so-called foreign key。

 Similarlyly in the people table which had a ID uniquely identifying each person。



![](img/3741fde3a9a19aa400591a39252631a8_107.png)

![](img/3741fde3a9a19aa400591a39252631a8_108.png)

In the starss table， we had person ID， which in that context was a foreign key referencing the people tables primary key。

 So the use of these terms is just context dependent but they refer ultimately to these unique identifiers that not only uniquely identify data but allow us to cross-reence it in other places。

 and so in the schema here in VS code， we see the ability in the database itself in the database itself to specify that for instance。

 within the ratings table insofar as there is a show ID column that show ID is in fact a foreign key that references this other tables。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_110.png)

![](img/3741fde3a9a19aa400591a39252631a8_111.png)

![](img/3741fde3a9a19aa400591a39252631a8_112.png)

Primary key。 And we can see this elsewhere as well。

 If I scroll down to the bottom of the schema and reveal the create syntax for the stars table。

 we'll see that the stars table， as we saw pictorially has a show ID column and a person I column。

 both of which are naturally integers and not nu， But there's now two foreign keys in this table。

 namely show I references the shows tables， primary key I and the person I column references the people tables Id primary key as well。

 So rebose and not necessarily syntax that you might want to memorize。 And indeed。

 there software out there in the world that allows you to click some buttons and generate commands like these。

 which are not necessarily easy to remember。 but ultimately reading these things line by line does specify and make clear to exactly what our columns are and what each of the types therein is。

But there's another command in SQL that's even more powerful perhaps and allows us to somehow link back to the original material we care about。

 That is to say thus far in trying to impose these relationships across tables。

 we've created all of these new identifiers， namely these primary and corresponding foreign keys and to the human eye now。

 it's a lot more work to try to line up all of those values and figure out what data relates to what But in SQL。

 there's indeed an actual keyword called join that allows you to specify how you might take one table here。

 one table here and join them together so that you actually have fullfledged access to all of the data you care about as opposed to it being in multiple places。

 So how might we use this pictorially well here then our snippets of two tables namely we have our shows table here and our ratings table here and there's certainly more data in each of these tables。

 but for now we'll focus just on the office in the office recall， we have a unique idea。😡。



![](img/3741fde3a9a19aa400591a39252631a8_114.png)

386676 and it stands to reason then insofar as I claim there's a one to one relationship between the shows's table and the ratings table that there's gonna be a row hopefully in the ratings table corresponding to show ID 386676 Now for the purpose of this story I don't care what the rating is but suffice it to say it is there but these are these pieces of data are in two different places wouldn't it be nice if we just had one table with not only the show's title but also its rating。

 much like we would have if we used a darn spreadsheet or something like a CSv file Well。

 let me go ahead and propose that just for the sake of discussion。

 we flip around these columns just so that you can see things lining up more visually clearly although the computer certainly doesn't care in what order the columns are let me propose that we now highlight the values in common the primary key here and the corresponding foreign key here let me propose just for the sake of discussion that we nudge these two tables together to make clear that these are in fact the same。

So we might as well omit the duplicate one and demonstrate that we could somehow join together these two tables so as to get one new temporary table。

 if you will， containing title and Id and rating that we care about。 And， in fact。

 I probably don't even care about the Id itself， the primary key。

 That's useful for uniquely identifying the data， But as a human at the end of the day。

 the question I presumably asked is what is the office's rating。 So this is the end result。

 I care about， as we've painted this picture on screen， how can we actually do something similar。



![](img/3741fde3a9a19aa400591a39252631a8_116.png)

In code。Do I want to say that？Give me one second。Well， let me go back into V。 S code。

 clear my prompt here and let me propose to run the following command。 Select star from shows。

 join these shows。 sorry， I messed up。😊。

![](img/3741fde3a9a19aa400591a39252631a8_118.png)

![](img/3741fde3a9a19aa400591a39252631a8_119.png)

Let me go back to VS code， clear my prompt and execute the following。

 select star from shows join ratings so as to join those two tables specifically。

 but how do I want to join them I want to join them on the shows's table ID column lining up with the ratings tables show ID column like that Now I could go ahead and hit enter now and I would see the joining of those two tables on that those particular columns。

 but let's be more precise， let's specify that I only care about this for now where the shows ID happens to equal 38667。

6 semicollon and what I should see now on the screen is the composition of the joining of those two tables such that I have ID title year episodes from the first and show ID ratings and votes from the second for the office specifically Now if I don't care about all of those values。

😡，W I shouldn't be using the wildcard， so let me go back in my history。

 scroll to the start of my statement and select not star， but for instance just title and rating。

 my command's a bit long so it'll wrap onto two lines but I'm going to go ahead now and just hit enter and now I will see that the office specifically that office has a rating of 9。

0。😡。

![](img/3741fde3a9a19aa400591a39252631a8_121.png)

As an aside， there's multiple versions of the office， including the one in the UK。

 but the fact that I've specified this specific unique ID gives me the one that debuted in the US here in 2005。

 Now of course， this is only useful insofar as I know the unique identifier of the office being 386676。

 which is not going be the norm and certainly not something I would type into IMDB do co and their own user interface。

 but for now， it does demonstrate how we can using a SQL join query， combine these here two tables。

 If I wanted to do all of them， of course， I could rewind in time and just exclude that predicate altogether and executing this query would give me a big list of all of the shows and corresponding ratings from top to bottom。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_123.png)

All right， well， let's focus on another type of relation now altogether。

 besides the one to one relationship that we apparently have between shows and their ratings。

 it turns out that there's another type of relationship manifest in the same data set between shows and genres we have a one to many relationship instead and this stands to reason because a show could be both a comedy and a musical or a drama and thriller or any number of genres could be associated with some show。

 So what wouldn't really make intuitive sense to require a one to one relationship which would mandate that every show have just one genre。

 So one to many allows for just this one show can have many genres as well。

 Well how might this play out。 Well， let me propose that with one to many relationship we can see data like this here on the left。

 we have another excerpt from the show's table for catweasel and on the right。

 we have an excerpt from the genres table。 Meanwhile， notice that the。😊。



![](img/3741fde3a9a19aa400591a39252631a8_125.png)

![](img/3741fde3a9a19aa400591a39252631a8_126.png)

![](img/3741fde3a9a19aa400591a39252631a8_127.png)

D for catweasel here is 63881 and the show ID that we have excerpted here on the screen is exactly that again and again and again because catweasel apparently both is an adventure。

 a comedy and family show but how could we answer a question like well what genres does cat weasel belong to well here we can see at a glance what they are but how might we join the data together to get at this answer as well Well let me propose here？

That we take a look at the schema for genres by going back to VS code here and clearing my screen。

 Let me go ahead and do dot schema genres to see specifically how it was implemented create table genres was the tables name and then in parentheses we have a show ID which is an integer that's not null we have a genre column which is just text and not null and then a foreign key on that show ID column that references the show tables ID column Now as an aside this table isn't really as rigorously implemented as it could be because the mere fact that genre is text would seem to imply that we might have adventure adventure adventure in multiple places in duplicate So what we seem to have stopped short of with this particular version of IMDB is further normalizing the data and making sure that we also have unique identifiers for genres which we do not have in this case So we stop short of design this perhaps as well。

😡。

![](img/3741fde3a9a19aa400591a39252631a8_129.png)

As we might。 but it's now clear that there's still room for improvement。 But for now。

 let's take the design of this table for granted and let's poke around for the same data therein。

 So at my SQL like prompt to let me select genre from genres where the show I I care about is indeed 6。

3，881 semicolon。 and that gives me back just as we saw on the screen adventure， comedy and family。

 Meanwhile， though that's， of course， not the most user friendly command。

 just as it was not particularly user friendly to get the ratings for the office by having to know its unique show I So let's do better now and moving forward。

 it turns out that you can not only execute individual SQL commands， but you can nest them as well。

 So I could use one command to figure out what the unique I is for cat weasel。

 and then embed the result from that query into the actual question I care about。

 which is what are its genres So I might do this。Select genre from genres where the show ID I care about is not a number I know or remember。

 but I know it equals to the following。 Select ID from shows where the title I care about equals cat weasel close quote close parenthesis semicolon So now much like in grade school math。

 anything inside the parentheses will be executed by the database server first。

 then the answer will come back。 hopefully the number I care about， which is 63881。

 that will effectively be substituted here so that the show ID I search for in the genres table will be exactly that number。

 All right， let me go ahead now and hit enter crossing my fingers that this will work and indeed。

 I get back the same answer， but in this case， I as the human the programmer did not need to know or care what that unique ID is。

 Now imagine going to any website where your search。😡。



![](img/3741fde3a9a19aa400591a39252631a8_131.png)

![](img/3741fde3a9a19aa400591a39252631a8_132.png)

![](img/3741fde3a9a19aa400591a39252631a8_133.png)

For information， maybe imMDb。 co itself， no normal human is going to type in 63881 to find out information about catweasel。

 what they're probably going to type in is cat weasel so presumably if you think about a website like IMDB co what they're probably doing is a SQL query much more like this whereby in that text box in the web form。

 they're grabbing the user's input， presumably cat weasel in this case。

 and then constructing a SQL query like this in their own codeb on their server that effectively copy paste the user input here and maybe scrubs it so there's no danger and then ensures that they can get back no matter the ID what the corresponding genres are for catweasel。

😡，So here we have again， an example of a one to many relationship that allows us to get back the data we care about。

😡，Let me think for one second。I don't think we need this。

But there's another approach we could take for this one to many relationship that's more like the one to one relationship we explored earlier rather than use this nested query。

 I could alternatively use a join as well and in fact just as in programming more broadly there's often multiple ways to solve the same problem so let's see that in this particular case Let me propose that we treat these examples as follows on the left here is an excerpt from the show's table and on the right here is an excerpt from the genres table as well just as before in a way that the computer won't care about。

 let's just for discussion sake， flip these two columns around to make clear that catweasels I is indeed going to line up with these show IDs here we're to join these two tables together as we did before by pairing up the I column here as the primary key and show ID here as the foreign key you're actually going to necessarily need some duplication of data so that every row has。

Every column you care about so in fact， if you were to join these two tables together。

 the result set you would get back would actually look a bit like this Now we can eliminate some of this redundancy by getting rid of the duplicate foreign key but you'll see here that the title even if we get now rid of the primary key is duplicated again and again and this is not necessarily something we can avoid if we indeed want to join the two tables together we can avoid it by taking that different tact by actually using the nested query but let's just see this in action because it's perfectly valid and it's actually quite common to join two tables together even if you might get back temporarily some duplication if only because it makes it easier to get the title and genre and title and genre and title and genre iteratively all from the same result set So let me go back to Vs code here clear my prompt and let me propose that initially will select star from shows will join shows with genres specific。



![](img/3741fde3a9a19aa400591a39252631a8_135.png)

![](img/3741fde3a9a19aa400591a39252631a8_136.png)

On the show's tables Id equaling the genres tables show IDd。

 and now rather than end our thought and see every show in every genre associated with it。

 let's just narrow the scope not by limiting to some number of results。

 specifically specifically limiting ourselves to 6，3881 just because we know that it's cat weasel。

 let me hit enter and we'll indeed get back in each larger table with all of the columns because I use star and indeed we see that same duplication Now I can whittle that down if I only care about at the end of the day these genres for cat weasel and I can hit up in my history go back over here。

 replace the star with just genre and now we're back to an answer akin to the nested query as before。

 So again， this is only to demonstrate that we can in multiple ways solve the same problem but the question we cared about and the answer we wanted was initially what genres is cat weasel。



![](img/3741fde3a9a19aa400591a39252631a8_138.png)

And that we've now had in a couple of ways。

![](img/3741fde3a9a19aa400591a39252631a8_140.png)

Well， how about one more type of relation by revisiting our larger data set we've seen thus far one to one between shows and ratings we saw just a moment ago one to many between shows and genres Let's now come full circle when we looked at the TV stars and the shows that they're in by focusing lastly on a many to many relationship namely these three tables herein recall that shows is a table with ID title year in episodes recall that people has an ID name and birth year for that person noticeice though to be clear there's no mention of shows in the people table and there's no mention of people in the shows table for that we had that third intermediate table Now we'll call it a join table that has two columns in common show ID with the shows table and person ID with the people table and that third table is what relates one to the other shows to people and people to show。



![](img/3741fde3a9a19aa400591a39252631a8_142.png)

![](img/3741fde3a9a19aa400591a39252631a8_143.png)

But， of course， in the real world， it stands to reason that one person could be in multiple TV shows。

 and it stands to reason that one show has multiple people air go a many to many relationship。

 So when you have this type of relationship that there say is more involved than any of the others。

 How can we get at answers to questions we might care about whether it's me sitting behind a desk analyzing some data or me as a user sitting on IMDB do com just typing in queries。

 Well， let me go back to VS code here and clear my prompt。

 And let's go ahead and just poke around this data initially。

 Let me go ahead and select star from shows where the title of the show I care about is quote unquote the office。

 semicolon。 Well， we'll see that there are， in fact， several versions of the office over the years。

 but we'll focus for now on the US version here with Steve Correll and team。 Let me， in fact。

 clarify then that the office I care about not only has a title of the office。

 but it also and has a year of 2005。

![](img/3741fde3a9a19aa400591a39252631a8_145.png)

![](img/3741fde3a9a19aa400591a39252631a8_146.png)

Because 2005 is a numeric value。 I don't need the quotes。 It's not a string of text per se。

 And so this should now narrow the results to the same version of the office we've been talking about。

 Now， suppose that I wanted to get。All of the people who star in this show。 That is to say。

 how can I explore that many to many relationship。 Well。

 all of the people in this data exist in the people table。

 All of the shows in this data exist in the shows table。

 But the linkage between them recall is the stars table。

 So I kind of need to follow some breadcrumbs from one table to the next in order to get back the data I actually care about So I could do something like this。

 I could select the names from the people table where the idea of those people is in wait a minute。

 the stars table right， I can very easily select the title of shows here。

 But then I want to bridge this table people to the stars table。

 So I think I'm going about this ironically backwards。

 Let's actually figure out how we can get from one table to another by considering what we don't yet know。

 I want to。

![](img/3741fde3a9a19aa400591a39252631a8_148.png)

![](img/3741fde3a9a19aa400591a39252631a8_149.png)

Query about the office。 but let me propose that I don't remember what its unique I。

 that six digit number， but that's okay because I can at least figure out what the unique idea is for this particular office。

 which is going to be 3，8，6，6，7，6， but let's do it programmatically Select Id from shows where title equals quote unquote the office and year equals 2005。

 In other words， don't select star， Let's select only the value we care about。

 and we should indeed see that what comes。😡，Sorry。Damn it。Let me fix this。嗯。How do I bridge them？

It's going be 3，8，6，6，6。 So let me do select Id from shows where title equals quote unquote the office and the year equals 2005。

 In other words， nearly the same query， but let's narrow the scope of my interest to just the I in question。

 And sure enough， when I hit enter。 I get back only 3，8，6，6，7，6。

 So I seem to have a query via which given the title of the show I actually care about。

 I can get the unique Id thereof which I don't particularly care about。

 But that is necessary for bridging these tables。 Now， let's go ahead and move my cursor back up。

 so as to repeat this query， but let's encapsulate this in parentheses and make it a nested query。

 Then let's go ahead and further ask this question。

 select person Id from the stars table where the person Id。Is in this nested query。

 So let me go ahead and hit enter here。 And what we'll see now is that I am getting the person Id from the Star table。

 Nope， that's wrong。 damn it。😡，Sorry， I mistyped。Okay。Okay， let's back this up。Okay。

Suppose now that I want to get all of the people who starred in this particular office。

 How can I get from the shows table to the stars table to the people table ultimately， Well。

 let me propose that we select first， only the Id of the show that we care about so that I don't have to remember 3。

8，6，6，7，6。 Well， let me repeat the same query， But instead of selecting star。

 let's specifically select Id， which gives me just that。 Now， using this show Id。

 Can I get all of the person Is associated with it， Well， I can if I use the stars table。

 which links precisely those columns together， So let me do this。

 select all of the person Is from the stars table where the corresponding show Id doesn't equal because I might have multi okay。

 sorry。So how do I get？From the showest table in the print。Let me execute。

 select person IDd from the stars table where the show ID I care about equals 38，6，6，7，6。 but again。

 I don't wantna have to memorize or care about a number like that。

 So let me parenthetically copy and paste the previous query。 And for clarity。

 I'll go ahead and put this on a new line。 you'll see that SQL light 3 gives me a dot dot dot to indicate that I'm still in the middle of a statement。

 So let me parentthesize this fully and then say semicolon on the outside。

 So when I hit enter now what I get back rather cryptically are all of the person ids that line up with this show I in the stars table。

 But these two is not what I care about。 I care about the actual people and specifically their names。

 That's okay。 We've already gone from the shows table to the stars table by way of the show I lining up with the person I from the former to ladder how。

Now， can I go to the people table using these person I。 Well， I don't think that's that hard。

 I can nest those two queries together as follows。 Select the name of the all people whose Id。

Is not equal to， but in this whole set of person I。

 Now I could go through and start copying and pasting all of these person id。

 but I don't want to do that instead， let me parentthesize exactly that query as before select person I from stars where show ID equals and then in parentheses。

 let me put that in， select ID from shows where title equals the office and year equals 2005。

 let me close parenthesis close parenthesis semicolon and what you'll now see step by step is that on the outermost part of this statement。

 I'm selecting the name from the people table where the idea of that person is in the list of person I that comes from this second line here from the stars table。

 but the show ID that I look up in the stars table comes from this final query whereby I select the I of the show that I care about which at the end of the day is the office from 2005。

 And if I hit enter now if you've watched the show， you should now see。



![](img/3741fde3a9a19aa400591a39252631a8_151.png)

Some familiar names not just the leadcast， but even more of the TV stars from that same show from IMDB。

 So a bit of a mouthful and a bit of multiple steps to get there。

 but as you get better and better with SQL， much like you might get better and better with Python or jascript。

 these kinds of commands come to you much more readily and can you save these commands or cash them in some form so that you can answer these same questions again and again。

 not necessarily about this particular show， but even some others。 In fact。

 let's go ahead now and maybe lastly in this many to many relationship flip things around and ask for all of the shows that starred Steve Carell specifically flipping the many to many relationship in the other direction。

 Well， how might I do that。 Well at the end of the day， I'm probably gonna need Steve Corll's Id。

 I don't know what that is offhand。 So let's ask the database Select Id from people where the name of the person I care about is Steve Corll。

 I'm not gonna go ahead and now run this command。

![](img/3741fde3a9a19aa400591a39252631a8_153.png)

But that's just going to give me his I 1，3，6，7，9，7。

 but I don't really care about the specific number。

 So let me go back and parenthesize this query here。

 because what I really care about are all of the show Is that correspond to that person I in the stars table。

 So let me do that， select。😡，Person ID。Sir。So let me do that。

 Select show I from stars where the corresponding person ID equals specifically Steve Correll's name。

 then let me go ahead and execute that query and I get back now a whole list of show Is Well。

 let me go ahead now and do everything together， but ultimately select the title from shows which I ultimately care about So select all titles from shows where the I of the show is in the following query。

 select show ID from stars where person ID equals and then the very first query。

 select ID from people where name equals quote unquote Steve Correll， close Parn close Per semicolon。

 and what I should now see is not a whole list of opaque identifiers for each of those shows。

 but indeed all of the shows according to IMDB that Steve Correll has been in among them the office。

Yes。But that's not the only way we can do this。 And just to show you that there's other ways， too。

 I'll do this one a little more succinctly and right off the bat。

 But you can also use SQL joins to answer questions like this。 For instance， I could do this。

 If I know I ultimately want to join together。 people and shows by way of those stars。

 I could express myself as follows alternatively， select title from shows。

 joining the stars table on shows Id equaling stars do show Id。

 joining further on the people table on stars do person Id equaling people Id where the name I ultimately care about is。

😊，Steve Correll， semicolon。 So it's a different approach to the problem whereby I'm essentially joining all the three tables together。

 but then filtering them out by this predicate， where name equals Steve Correll。

 And that again gives me，Albeit more slowly， the shows that he's been in as well as some duplicates。

Sorry， thanking。Why are we getting duplicates？So I can run this command。 albeit more slowly。

 it would seem and get back the same results of all of the titles of shows in which Steve Corll starred。

 Now， there's a third and say final way that I could execute this using really an implicit join。

 So joining the two tables together without interestingly using the join keyword explicitly。

 And I can do that as follows。 Select title。Select title from shows and stars and people as a comma separated list of tables where the show's tableables ID equals the Stars tables show ID。

😡，And the people Id。Sorry， let me redo this query。Okay。Select title from。Again。

Select title from shows， stars and people as a commer。Wow。Select title from shows。

 stars and people as a comma separated list of table names where the show's IDs column equals the starss tables show ID column and the People tables ID column equals the starss tables person ID column and the name that I care about equals quote unquote。

😡，Steve Correll。 So notice that by way of this predicate。

 I'm implicitly joining the shows with the Stars table， the people with the Stars table。

 and then additionally filtering by Steve Corll's name in this case now， when I hit enter。

After a pause， indeed， a bit more slowly， I get that same result of the titles of all of Steve Carerell shows Now。

 of course， there's even more data in this database。

 we've looked at people in stars and shows we've looked at genres and and ratings but there's also this other table called writers and it turns out the writers's table has a relationship with shows and people quite like that of stars。

 in fact， the column names are the same show I in person ID but the table's name captures the relationship that of writers Now here too is maybe a missed opportunity to improve this data set further。

 because it would seem to indicate that we have the TV stars relationship captured here。

 the writers' relationship captured here， but what if there's other roles on the show set What if there are producers and cinematographers and yet other roles in the industry。

 it would seem that we need a separate table for each of those roles。

 each of which is structured and exactly。

![](img/3741fde3a9a19aa400591a39252631a8_155.png)

The same just has a different name， odds are， if we spent a bit more time。

 I bet we could factor out that commonality and avoid having stars and writers and even more tables and perhaps more generically have a roles table that somehow captures the association of people with shows。

😡，All right， well we saw a moment ago that not all queries perform the same and that indeed depends on some of the underlying implementation details of the database itself。

 particularly if we have not indexed are database tables that is to say there's yet another feature of relational databases whereby if you know that you're going to be performing certain queries and certain queries quite commonly。

 you might want to optimize the underlying representation of that data by creating indexes on your tables and what an index allows you to do a syntax like this in SQL lights。

 create index and then the name of an index on a specific table specifically on in parentheses。

 a comma separated list of one or more tables。 what these indexes do for you ultimately is create a data structure in memory。

 generally known as a B tree， which is not short for binary tree。

 It's a different type of tree altogether that looks a little something like this whereby your data somehow in memory let's。



![](img/3741fde3a9a19aa400591a39252631a8_157.png)

Over here。嗯啊。B bee trees， not to be confused with binary trees。

 bee trees are indeed a different type of tree， but they look a little something like this。

 whereby they're a very wide tree with lots of children。

 perhaps pulled as close to the root note as possible。

 the implication being that when searching some column for data。

 maybe a name like Steve Correll or a title like cat weasel。

 rather than have have the database resort to linear search from top to bottom。

 looking for every mention of Steve。

![](img/3741fde3a9a19aa400591a39252631a8_159.png)

Dren。I didn't want to standard of the screen because there's a background color issue here。

 which we'll just fix。

![](img/3741fde3a9a19aa400591a39252631a8_161.png)

When you create an index in this way， what the database essentially does for you is build up in its memory。

 a B treee data structure。 Now this is not short for binary tree。 A Bere is a bit different。

 It looks a little something like this， which is a fairly wide tree that might have many leaf nodes ultimately but those leaf nodes are as close to the root as is possible giving us ideally some kind of logarithmic running time。

 That is to say by building this data structure and memory related to columns that you know you're going to search on a lot。

 you can avoid having the database resort to something like linear search searching the entire column from top to bottom for a name like Steve Correll or a title like cat weasel。

 rather by storing that data somehow in the databases memory in this tree structure you can get to that data more quickly than something like linear search alone。

 In fact， let's see the effects。 let me go back to VS code here。

 and let me turn on a feature of SQL like called a timer。

 which will allow me to time how much time it takes。



![](img/3741fde3a9a19aa400591a39252631a8_163.png)

Each of my subsequent commands to execute。 Let me now do a query like this。

 Select star from shows where the title I care about is as before the office and any number of offices。

 notice now that I get back all of those results。 but in particular。

 I see just how much time it ultimately took in real time。 it took 0。038 seconds。

 which isn't all that long， but if you imagine a larger data set and you imagine a popular application like IMDB do com itself。

 you can imagine that even the 0。038 seconds， adding up， adding up over time。

 Now this has very real worldord implications for usability。 the longer a query takes。

 the longer your users are going have to wait and in turn。

 the more users you have the more servers you're going to need in order to support lots of users。

 each of those queries is taking a good amount of time。 So in other words。

 if we can shave even milliseconds off of this time。

 odds are that's gonna to save our users time and me money because I don't need as many。



![](img/3741fde3a9a19aa400591a39252631a8_165.png)

Svers to support that same number of users。 So what I could do， for instance。

 if I know that my users are frequently going to search on a column like title。

 I could go ahead and create an index in advance on precisely the same。 In fact。

 let me go ahead now and create index called anything I want。

 perhaps I'll call it title index to make clear what it's used for on the table call shows specifically on the title column Notice now。

 when I hit enter that query did take a moment。 almost half a second，0。357， but that's an operation。

 I'm only gonna have to execute once granted the database over time。

 if I continue to insert and update and delete data in this table。

 might need to make modifications to that index。 And for instance， the underlying B tree。

 but odds are， if I'm generally reading data。 selecting data from this database， as I would。

 if I have lots of users， odds are the reads are going be much more common than the rights。



![](img/3741fde3a9a19aa400591a39252631a8_167.png)

Cost of this creation of an index and maintenance thereof can be amortized surely over time。 Now。

 let's execute that first query yet again。 select star from shows where title equals quote unquote。

 the office。 Now， recall a moment ago， that query before I created the index took 0。038 seconds。

 which didn't sound like much。 But now that we have that index and the underlying data structure in memory。

voila， we're down to essentially 0 seconds。 We don't even have enough significant digits here on the screen to capture just how fast that new version was。

 We're at 0。000， which surely sounds fast。 So better response times for users less money for me fewer servers in our cluster。

 we're probably now in better shape simply by creating these indexes。 Now， I didn't necessarily。😊。



![](img/3741fde3a9a19aa400591a39252631a8_169.png)

I don't， sorry。Now， I don't necessarily want to do that for all of my columns in all of my tables because as with anything。

 there's ultimately going to be a tradeoff。 these trees and memories surely start to take up additional space and for tables that might be actually updated frequently。

 it might actually slow down my insertions， my updates my deletions。

 but certainly for the most common of queries like searching on a website or application。

 I probably can choose to optimize some of those columns in some of those tables now in fact I could go back perhaps and maybe engineer a few more indexes on the columns and tables。

 my previous query touched when looking for Steve Correll。

 which would in fact I dare say expedite just how long it takes to join some of that data together。😡。



![](img/3741fde3a9a19aa400591a39252631a8_171.png)

![](img/3741fde3a9a19aa400591a39252631a8_172.png)

Now， throughout this whole class， we've been focusing。 now， let me fix that。

Now we've been focusing entirely on SQL in the context of relational databases。

 but there are alternatives to SQL as a language， there are alternatives to。

Now we've been focusing entirely on SQL， but there are alternatives to SQL when it comes to storing data。

 in fact， aptly name， there's an approach called NoSQL， which stands for not SQL。

 or nowadays really not only SQL， which is fundamentally different approach to how you might store data。

 a relational database and in turn any database that uses SQL is based on rows and columns。

 which generally works well， but when you have more hierarchical data that you might want to store。

 it's annoying at best and challenging that's not what I want to say。😡。

Now up until now we've been focusing entirely on SQL。

 but they're all alternatives to SQL databases that allow us to store data in different ways。

 in fact， aptly named there's an approach calledNo SQL which might be said to stand for not SQL or really not only SQL。

 whereby you can store data in sorry I'm getting thrown off again。😡，Mmhmm。

Now up until now we've been focusing entirely on SQL。

 which again in the context of relational databases has me storing all of my data in rows and columns。

 which often works well， but sometimes breaks down。

 or at least makes it much more difficult to store data。

 especially if that data is hierarchical in nature Indeed an alternative approach to storing data might be using a technique Jon as noSQL instead for not SQL or really not only SQL。

 which stores rather than rows and columns what we might call document or objects instead。

 for instance， if you would prefer not to use rows and columns and indeed SQL itself but would instead just like to keep all of your related data together as from IMDB you could store some similar information in a document like this in a format that you might recognize as JSON JavaScriptscript object notation which in noSQL context is used as well and here you have ultimately the same data that we've been exploring。

 for instance in IMDB if this is an excerpt there from where。😡。

We have a unique I that by convention in this particular form is underscore ID as the key followed by colon。

 which indicates here comes a value， the value of which is in this case，386676。

 which of course is the unique I that we've seen for the office。 Meanwhile。

 if using a nosQL database and indeed this particular example thereof you might have another key called title。

 the value of which is not surprisingly the office。

 and then if you want to keep all of the related data together as opposed to putting it somewhere else over there and requiring a language like SQL to join everything back together。

 it is commonly done in the nosQL world to bundle everything up in one document or object such that another key here is stars。

 the value of which as indicated by square brackets is an array or list of additional objects。

 Indeed， these curly braces here indicate in object or dictionaries as we've seen in prior context where by each of these objects represents a person who has two keys and value。

An ID as well， like 1，3，6，7，97 for the name， Steve Correll and so forth。

 So the appeal of No SQL is often that you can just grab all of the data you care about right away。

 but you don't necessarily benefit from some of the same features we've seen thus far。

 some of the constraints that a SQL database can impose like uniqueness and guaranteeing that some foreign key references a primary key from one table to another。

 nor do you necessarily have features。Like the ability to add indexes to find very specific information quite as efficiently。

 And indeed， there might be redundancy， too， if you're storing some of these objects without references。

 but in the raw objects， but it's an alternative approach that's quite popular as well。

 but is distinct from SQL in that the data is no longer in rows and columns。

 but in a more hierarchical structure that can be nested instead。😡，But when it comes to databases。

 no matter what the format you use， there are some fundamental problems and risks that even today so many companies and programmers encounter。

 One of the first of those is what might be said to be race conditions which rear their head in all forms of computing。

 But in the context of databases， what can go wrong might be this。 If you have， for instance。

 very popular website like that for social media where users can click on an icon in order to like a post for instance。

 Well， for the server implementing that social media network。

 you might have some code that ultimately is using SQL code like this。

 whereby when someone clicks on the like button， the database， of course。

 needs to update its records to say that oh， we have one more like in our system。 Well。

 how might you figure out what that new count should be， Well。

 there might be an underlying query like select the current number of likes from the posts table representing the social media posts where the idea of the post in question for the sake of discussion is 13。

 assume now that that value is stored somewhere in memory。

And the second SQL query is now necessary on the server in order to update the current number of likes to the new number of likes that is plus1。

 So for instance， if the current number of likes was 50 at that moment in time。

 we of course want to update the post table setting the number of likes to 51 where the idea of the post to update is 13。

 That's fine and at a glance correct。😡，But what race conditions allude to is the fact that even well- intentiontention commands like these might lead to unexpected results。

 especially at scale if you've got not only a lot of data in your database。

 but a lot of users using your application or website。

 imagine that these two lines of code are being executed in parallel really on lots of different servers even in the simplest case where you have two servers to handle twice as many users。

 suppose that two users out there in the world， both click the like button on the same post at essentially the same time。

 and because that it takes a little bit of time for their request to go from their browser to your servers。

 imagine that on one server， this first command is executed and the answer comes back indeed as 50 but imagine before that one server has a chance maybe it's a bit slower to execute the second query。

 supposeose that the other users like hits your other server and it runs the same line of code and gets back the same answer 50 this。

Poin in time， both server' memory has in mind the number 50， in which case they'll both add 1 to 50。

 get 51， and both servers will thereafter proceed to execute update posts set likes equal to 51 where ID equals 13。

😡，Where is the bug， Well， because both of them inspected the value of likes in the database at essentially the same moment in time。

 But then it made a decision thereafter based on that value， you're going to end up storing indeed。

51 in the database instead of the correct answer， which should be 52。

So this race condition refers to really sort of two competing requests racing to finish。

 but getting interwoven temporally in terms of time accidentally and that is because fundamentally these two queries can be interrupted or at least interfreed with others because they're running in different places on different servers but ultimately accessing somehow the same database。

 you can think of this metaphorically in the real world。

 like I was taught years ago by one of my own professors who encourage us to consider a scenario in which you live with someone like a roommate and you have a refrigerator in which you like to store milk and one of you comes home one day opens the refrigerator and sees we're out of milk。

 so you close the fridge and you head out to the store to go by another jug of milk。 Meanwhile。

 your roommate comes home， who also likes milk， opens the fridge realizes oh we're out of milk closes the fridge and heads out the door。

 maybe in another direction to go get some milk。 Of course。

 this story ends with both of you coming home putting now not one but two jugs of milk in the fridge。

Wwhich was not the desired result and why did that happen because both of you made a decision based on the state of the world。

 the state of the refrigerator without somehow blocking the other from making a decision at the same time how might you have avoided that problem Well you could leave a note on the fridge saying like gone for milk or you could lock the fridge physically and funny enough that's essentially the solution to the same problem in databases whereby if there are two or more queries that you want to execute together so to speak atomically such that they both execute or neither of them execute。

 but there's no interruption， you can introduce what are known in the world of databases of locks or transactions whereby instead of executing just two lines of code you can first tell the database begin the following transaction then execute these commands and then commit my changes before someone else can then do the same and effectively these transactions prevent to。

😡，Different queries being interwoven together， as we saw might happen with the likes on a post or the milk in a fridge。

😡，And if something does go wrong with transactions。

 you typically get the feature of rolling back where at least one of the servers can say。

 I'm just going to show the user an error message and roll back without trying to change the database myself。

😡，But there's one other problem we should consider in the world of databases specifically SQL known as SQL injection attacks。

 it is quite common to use SQL and some relational database like SQL light or oracle or SQL server。

 MySQL or Postgres or something else to store all of the data for some website or application of course websites and applications often have text boxes of some sort that allow you。

 the user to type in queries and maybe search for some data or update or delete or insert some data into that database the problem begins though if the programmer who wrote the SQL queries。

 trusts that user input and assumes that they're not going to do something malicious like themselves run delete or themselves search for drop or other potentially dangerous command and it turns out in some cases if your code is poorly written be it in SQL and also Python or some other language。

 you can accidentally be tricked into users in。😡，jecting code into your system。 Now。

 what do I mean by this。 Well， consider， for instance。

 a login form that might look like this asking for the user's username and password。 for instance。

 email and password here。 though， that the programmer who implemented the authentication underlying this website didn't know about SQL injection attacks and is all too willing to trust user input。

 but suppose I in this story am a malicious adversary， And I suspect that as a programmer。

 you're in the habit of using single quotes， And I suspect that you're in the habit of using SQL databases。

 Well， a single quote is certainly something I can type on my own keyboard， for instance， curiously。

 not at the start of my name， but at the end， and it turns out that we've not seen this before。

 dash in SQL is how you begin a so-called comment， a note to self that does not is not meant to be executed。

 but essentially blocks out everything to the right and tells the database to just ignore it。

 So curiously， I've typed in my email address。 and。



![](img/3741fde3a9a19aa400591a39252631a8_174.png)

![](img/3741fde3a9a19aa400591a39252631a8_175.png)

E。 But I finished that thought with a single quote and a dash dash。 Well。

 let's see where things might go awry。 Suppose on the backend server is the code the programmer has written that somehow uses a SQL query like this。

 Select star from a table called users where the user name is whatever the user typed into the form and the password is whatever password the user typed into the form。

 Notice that I've preemptively put single quotes around the username and the password and much like in Python。

 even though this is meant to be pseudocode here， they currently braces just mean plug in the username there。

 plug in the password there， but quote them because their strings。

 they're not something like numbers。 Well， what can happen if a malicious mail in at Harvard do E。

Passes that input is this。 This SQL statement might become naively where username equals quote unquotemein@harvard doedduu close quote。

 which recall as the quote that I typed in dash dash， which tells the database。

 ignore everything else， that is don't even worry about what the user's password is。

 And if you assume that this query is ultimately being used to figure out if we do have a user with username maillin@harvard doeddu。

 and therefore should they be allowed to log in， suffice it to say this query。

 if you essentially trick the database into ignoring the entire password check could very well allow an adversary。

 whether it's me mailin athareddu or someone pretending to be me log into this server without even knowing the password thereby injecting SQL into the database。

 Now in this case， it's just as equivalent to none of that even being there。😡。

And so the user might get in Now， what's the solution。 It turns out there's a fairly simple solution。

 And it one stems from not trusting user input。 Indeed， when programming code。

 you should generally code defensively assume that users will make mistake or at worst will be malicious and you don't want to trust what they've typed in。

 But that's fine。 There exists plenty of libraries and in turn functions that allow you to format your SQL queries when writing code on a server to look more like this where you very deliberately use placeholders that often in many libraries are simply question marks and leave it to someone else's code。

 the library you're using to figure out how to insert the email address that someone's typed in into this placeholder how to insert the password that someone's typed in into this placeholder and let the library worry about quotes and escaping and generally sanitizing the user's input so to speak。

 there are welldefined ways to do it， there's sort of a checklist you might go through But if you are new at programming or just not necessarily versed in this。

You might miss one of those important details best to stand on the shoulders of others and very popular libraries。

 perhaps open source tools so that your code is much safer as a result but the lesson ultimately is do not trust users input Now on that downer of a note。

 let's emphasize that ultimately our goal has been to store data at scale moving from the simplest of files like text files like CVs to proper relational databases or heck even no SQL databases in the former though the paradigm is to store all of your data in rows and columns and thanks to features like indexes not to mention all of the commands that SQL supports。

 can you navigate that data by selecting and inserting and updating and deleting and whether using SQL light or indeed oracle SQL server minusql Postgres or any number of others you can scale your websites and applications well beyond the hundreds and thousands and hundreds of thousands of rows that we've seen here but to millions。

 if not billions as well with。

![](img/3741fde3a9a19aa400591a39252631a8_177.png)

Same。W。Okay。So I don't think I have any pickups， but I do need to fix the database tonight and rerecord laptop commands。

