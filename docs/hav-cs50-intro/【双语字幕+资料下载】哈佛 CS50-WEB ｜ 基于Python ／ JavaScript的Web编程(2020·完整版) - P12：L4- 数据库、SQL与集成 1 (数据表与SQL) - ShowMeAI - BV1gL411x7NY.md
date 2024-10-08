# 【双语字幕+资料下载】哈佛 CS50-WEB ｜ 基于Python ／ JavaScript的Web编程(2020·完整版) - P12：L4- 数据库、SQL与集成 1 (数据表与SQL) - ShowMeAI - BV1gL411x7NY

![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_0.png)

[Music]。

![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_2.png)

all right welcome back everyone to web，programming with Python and JavaScript。

so last time we took a look at a，brand-new web framework written in。

Python called Django and what Django，allowed us to do was to build dynamic。

web applications applications where we，now had the ability to not just display。

the same HTML and CSS to the user every，single time but to dynamically generate。

HTML in order to allow users to interact，with a page that was a little bit more。

dynamic doing things like rendering，things on the page only if a certain。

condition was true we're looping over a，list of values and displaying one HTML。

element for each of those possible，values but where Django gets especially。

powerful and where web applications，certainly get much more interesting is。

as we start to delve into the world of，data and trying to have web applications。

that store data inside of a database and，to do that we're gonna introduce a。

couple of topics today in particular，we're gonna introduce the idea of sequel。

models and migrations sequel is a，database language that we can use to。

interact with databases and Django is，going to be allow us to have an。

abstraction layer on top of sequel to，interact not by writing direct sequel。

queries but by interacting with Python，classes and objects that are we're going。

to refer to as models and migrations are，going to be a technique that are going。

to allow us to update our database in，response to changes that we make to our。

underlying models so before we get into，things that are more Django specific。

let's begin with the discussion of，sequel more generally and more broadly。

just a discussion of data and the types，of data that we're going to want to。

store and now there are a number of ways，that we could try to store data inside。

of a computer system but oftentimes in，databases in particular in a type of。

database known as a relational database，we're going to store data inside of a。

table where each table is going to have，rows and columns and so for the take of。

today we're going to imagine starting to，construct a database and a web。

application than an airline might use，for example for keeping track of various。

different flights on that airline and，keeping track of which passengers are on。

those flights and so what we have here，is a sample table for example of how you。

might represent a whole bunch of flight，related data here I have three columns。

for three pieces of information that I，might want to keep track of for any。

particular flight for any given flight I，might want to know that flights origin。

what city is weaving from its，destination，what city it's arriving at。

and its duration some value in minutes，of how long it's going to take the。

flight to get from the origin to the，Nesta nation so each of those columns。

represents one field that I might want，to keep track of about my data and each。

row meanwhile is going to represent an，individual flight so here for example is。

one row representing one flight from New，York to London and that flight just so。

happens to take 415 minutes，and so what sequel is going to allow us。

to do is it is going to be a database，language that is designed to interact。

with relational database management，systems databases that organize data。

into tables where every table has rows，and columns and it turns out there are a。

number of different database management，systems that implement parts of the。

sequel standard of this type of language，some of the more popular are MySQL。

PostgreSQL and sequel Lite but there are，definitely others as well and each of。

these has various different features and，different use cases where some might be。

more appropriate MySQL and PostgreSQL，otherwise known as just Postgres are。

more heavier database management system，so to speak they're generally running on。

servers elsewhere where a lot of big，companies will use servers like this in。

order to store data and represent their，data in a sort of a separate database。

where the idea of that is that you might，want your web application running on one。

server but you might want your database，running as an entirely separate process。

such that they can behave independently，you can debug and test them。

independently and one if not if one goes，down the other doesn't go down as well。

sequel Lite is a bit of a simpler，lighter weight implementation of the。

sequel standard and what sequel Lite is，going to do is rather than be an entire。

server that is going to be listening for，requests and making responses a sequel。

Lite is just going to store all of its，data as a single file so we're gonna。

store sequel data inside of a sequel，Lite file and that's gonna make it a。

little bit easier for us as we're just，getting started to begin to write。

queries and add things to our database，and retrieve things from our database。

but know that many of the same types of，sequel syntax that will see with sequel。

Lite which is Django's default can also，be applied to other languages as well。

and other database management systems，too so as we begin to store data inside。

of a sequel database ultimately each of，those pieces of data has a type in the。

same way that in Python we have types，for various different types of data we。

have integers and we have strings and we，have lists and tuples and so forth。

equal to has types that represent，various different categories of。

information that you might want to store，inside of a database and each database。

management system has its own different，set of types sequel Lite for example has。

a fairly short list of basic types that，it supports it supports text for just。

like strings of text for example，something like a city name for instance。

might be sort is text we have support，for integers which is just 0 1 2 3 4。

plus the negative numbers negative 1，negative 2 negative 3 and so forth we。

have support for real numbers where real，numbers don't have to just be integers。

they could have something after the，decimal point something like 2。8 or。

something else that might have a decimal，in it and then numeric is another。

category for data that's just more，generally some sort of number that might。

number like data so something like a，boolean value or something like a date。

for example might be stored using this，numeric type where it's not really an。

integer or a real number though you，could represent it as such it's other。

numeric type of data and then finally，blob which stands for binary large。

object is any type of other binary data，just zeros and ones that you might want。

to store inside of your database so for，example if you're storing files maybe。

they're audio files or images or other，types of files that you want to keep。

track of inside of your database you can，store just pure binary data inside of a。

sequel database as well so these now are，the basic types of sequel Lite supports。

but other database management systems，well，MySQL for example has a much longer list。

of other types that it supports in，addition to just supporting a text type。

for arbitrary length text MySQL also has，a type called char that takes an。

argument of size for saying I want like，size characters worth of data that we're。

going to store inside the database and，you might imagine that this can be。

advantageous in situations where you，know that your data is going to be。

within a certain number of characters so，if you're storing a zip code for example。

in the United States a zip code in the，United States might just be 5 characters。

and so you can allocate a character，length of 5 characters worth of space。

for storing every single zip code inside，of your database table so for efficiency。

sake if you know the maximum length and，you can fix that in that length inside。

your database that can be an efficient，choice varchar' of a size is similar and。

this is a variable length character if，something isn't going to be。

exactly a certain number of characters，but maybe up to a certain number of。

characters you can use varchar' to say，you know maybe sometimes it's gonna be。

fewer characters but it could be up to，size a number of characters and there。

are trade-offs there too，then there are various different types。

of integers so it's not just a single，integer type but small int + int and big。

int each of which uses a different，number of bytes in order to store an。

integer data so if you want to be able，to store much larger or much smaller。

numbers you might need a bigger type，like an int or a big int but if your。

numbers are gonna be pretty small maybe，you're okay with just a small int and。

likewise there are similar types of，trade-offs for floating-point numbers。

where much as in programming languages，like C if you're familiar have both a。

float and a double type where a double，uses more bytes of memory in order to。

store information here - we have float，and double which allow us to store。

floating-point numbers as numbers that，might be real numbered values where a。

double just allows us to express a，number to a little bit more precision。

than a floating-point number might be，able to and there are many other types。

as well but the general idea is that，here even in sequel much as in a。

language like Python we have types for，each of these various different kinds of。

data so now that we understand that each，type of data has types what we'd like to。

do is to be able to inside of a database，actually create a table and there are。

various different sequel commands that，we can run on our database in order to。

perform various different operations and，the first we might want to execute is a。

command that is just going to create a，table for example so how might we go。

about doing that well it turns out the，syntax for creating a table is going to。

look a little something like this this，here is the syntax we would use to。

create a table in sequel Lite for，representing flights for example so we。

begin with the keyword create table to，say I would like to create a new table。

inside of this database next I give the，name of the table every table has a name。

just for ease of reference and here the，name of the table is just the word。

flights then what follows in parentheses，ISM are a comma separated list of all of。

the columns that should be present in，the table I'm not yet adding any data to。

the table the create table query is just，going to decide the structure of the。

table what are the columns and what are，the columns types and so here we see。

that in the beginning of each of these，pair of，clauses that are separated by commas we。

have the name of the column so we have，an ID column because though we didn't，see this before。

often in sequel it's going to be helpful，to be able to have some way of uniquely。

referencing a particular element inside，of the table and you know maybe there。

are multiple flights that are going from，New York to London for example and I。

want some way of distinguishing between，them and one easy way is to give every。

single entry inside of a table a unique，identifier or a unique ID represented。

here by this ID column and that's going，to be of weight making sure that we can。

always access a particular flight，uniquely so we have an ID column an。

Origin column a destination column and a，duration column and each of those。

columns has a type so the types here ID，is an integer it's just going to be some。

number representing the flight counting，1 2 3 4 so on and so forth origin and。

destination well label here as text that，you'll see that if we were using MySQL。

for example I might make these a，variable length character that could be。

up to a certain number of characters if，I know you know there's probably not。

going to be a city that's longer than a，certain number of characters for。

instance and then I have a duration，which here then is an integer some。

number of minutes that is going to be，how long it takes for this flight to go。

from the origin to the destination after，the types for each of the columns I have。

additional constraints that I might add，to the columns as well so integer。

primary key the primary key here means，that the ID is going to be the primary。

way via which I uniquely identify a，flight and there's gonna be some。

optimizations here to make it very quick，to be able to look up a flight by its ID。

and not know as a constraint that I can，place on columns to be able to say I。

don't want to allow for this particular，column to ever be empty I don't want。

there to ever be a flight that doesn't，have an origin or doesn't have a。

destination or a duration so I can add，constraints to a particular column to。

say you know what for the origin，destination duration columns those。

should not be allowed to be no I want to，always have an origin and a destination。

enter duration and then finally this，auto increment after the primary key is。

a queue in the sequel to automatically，update the ID every time I add a new row。

into the table so if I add a new flight，I can give the flight an origin。

destination and duration but I don't，have to worry about giving it。

Eydie sequel is gonna handle that for me，automatically automatically giving that。

new table the next or the no new row in，that table the next available ID number。

so here then it's the way we create a，table by giving the name of the table。

each of the columns the types for each，of those columns and then any。

constraints that we would want to place，on those columns and it turns out there。

are a number of different types of，constraints that I can add to a。

particular column not know is one we've，seen before you can add a default which。

I just adds a default value to a，particular column primary key we've seen。

unique guarantees that every value is，going to be unique so if you don't want。

to allow for the same value to appear，twice for a particular column you can。

add a unique constraint to a particular，column to enforce that as well and then。

check can be used to make sure that a，value obeys a certain condition like a。

number falls within a certain range for，example if you have like movie ratings。

for example and you're storing movie，ratings inside of a database you might。

care to make sure that those ratings are，within the one to five range or the 1 to。

10 range or whatever it range you deem，valid for the database and so via。

constraints you can begin to ensure that，as you add data to the table that data。

is going to be valid in some way that it，needs to obey and certain constraints。

otherwise if you try to add it to the，table it's not going to be accepted at。

all and so that leads into the natural，next question which is I now have all of。

these various different tables that I，can create using these create table。

commands but how do I actually add data，into those tables and the way we're。

going to do that is via an insert，command where we're going to insert data。

into a sequel table and so what might，that command look like the command is。

generally going to look like this where，we're going to say insert into to say I。

would like to add a new row to a table，following that we provide the name of。

the table something like flights to say，I would like to add a new row to the。

flights table and following the name of，the table we need to provide in。

parentheses a comma-separated list of，all of the column names for which we are。

going to provide values so here I've，said I want to provide values for the。

origin destination and duration of this，flight note that I'm leaving out the ID。

column I don't have to worry about，adding a value for the ID because I said。

the ID should Auto increment，it's going to automatically give the。

next available ID and what values am I，going to provide well after the word。

values I provide again in parentheses a，comma separated list of all of the。

values that are to be associated with，those columns in the same order so。

origin was the first one here so origin，will correspond to New York destination。

will correspond to London duration will，correspond to 415 so this query then。

lets me take the flight's table that，i've already created and add some data。

into that table as well so you can use，these insert queries so once you have a。

table to be able to add new rows of data，to that table every time a new flight。

comes up for an airline the airline，might behind-the-scenes be running an。

insert into flights command that takes，data about that flight and adds it to。

the table but of course once we've added，data to a table we'd ideally like some。

way to get data out of that table as，well but once we've stored data inside。

of our database we want to retrieve that，data too and to do that we're going to。

use a particular type of query called a，select query and what select is going to。

do is it's going to take a table that，already exists and allow us to get data。

out of that table it's not going to，modify the data that's there it's just。

going to retrieve data that might be，inside of a particular table so what are。

those queries look like well the，simplest query might look a little。

something like this select star from，flights select from flights means I want。

to select data from the flights table，and this star is a wild-card that here。

just means that select all of the，possible columns that you can and so if。

this is my table my table of flights，where each flight has an ID an origin a。

destination and a duration then select，star from flights will select all of。

that data all of the rows and all of the，columns are going to come back to me。

when I run a query like this now it's，possible that when I'm running these。

queries when I'm accessing data that I，don't actually care about all of these。

columns especially if I have a table，with many more columns than just this。

maybe I only care about particular，columns and it would be wasteful to。

query the database asking it to return，to me a whole lot more data then I。

actually need so instead I could run，query like this I select instead of star。

I'm saying select origin comma，destination，from flights so I'm again selecting from。

the flight stable selecting all of the，rows of still but the difference is that。

instead of select star which means，select all of the columns that are。

present in the table select origin comma，destination means I'm only going to。

select these two columns the origin，column and the destination column so。

highlighted in blue here is the data，that would be returned if someone were。

to run this particular sequel query now，especially as tables begin to get larger。

and begin to have more and more rows，here I just have six rows but you might。

imagine a table with thousands or even，millions of rows within it you probably。

don't want to be returning every single，row every single time so just as you can。

constrain which columns come back to you，likewise you too can constrain which。

rows come back to you when you perform a，query - so I could say something like。

select star from flights where ID equals，three again this reads is very English。

like I'm saying select all of the，columns from the flights table but not。

all of the rows I only want to select，the rows where this is a sequel keyword。

where ID equals three ID is the name of，a column three is the value and it's。

going to look through this table only，find me the flights where the ID is。

equal to 3m and I'll just get back that，one row as a result it finds the row。

with an ID of 3m and it gives that back，to me if instead I said select star from。

flights where origin equals New York I，can see that I don't just need to filter。

on the primary key the ID I can also，filter on any other column I can say。

give me all the flights where New York，is the origin so all the flights leaving。

from New York and you might imagine that，in New York's Airport for example they。

likely want some sort of query that's，going to find all the flights leaving。

from New York such that they can display，on a screen of some sort all of the。

departures from that particular airport，so you could run a query like this and。

get back only the rows in this database，inside of this table that happen to have。

an origin of New York for example so，let's go ahead and take a look at how we。

might actually run some of these queries，inside of a sequel database so in order。

to create a sequel Lite database which，is really just a file I can start just。

by creating the file and it turns out，that in the terminal there's a command。

called touch that will create a brand，new file for me，so I'm going to create a file called。

flights SQL it's gonna be a sequel Lite，database file that by default has。

nothing in it but then assuming you have，sequel Lite installed，I can run sequel Lite 3 followed by。

flights SQL and now I'm inside of the，sequel Lite prompt I can now begin to。

write commands that will be executed on，the sequel database so one thing I might。

do is create a table called flights this，table I want to have an ID column which。

is an integer it should be the primary，key the main way via which I identify a。

flight and I would like to auto，increment it I would also like for the。

flights table to have an Origin which，will be a text field that does not know。

I'll add a destination field also a text，field that it's not know and then。

finally I'll add a duration field which，is an integer that also shouldn't be。

know I'll end with an end parenthesis，and a semicolon press return and that。

execute that command on my database I，have now created a table called flights。

and to verify this in sequel Lite in the，prompt I can type dot tables and that。

will show me all of the tables that，currently exist in my database and it。

just so happens that I have a table，called flights of course there's nothing。

inside this table which I can verify by，running select star from flights meaning。

get all the data from the flights table，if I press return alright nothing。

happens I don't see anything there's no，data that happens to be here but now I。

could say something like insert in two，flights then I'll provide in parentheses。

the names of the columns and on the，slide a moment ago I showed this on。

multiple lines that was just for visual，sake these command can be entirely on。

one line if we would like it to so I can，say origin destination and duration and。

then provide values I can say let's add，New York to London and I'd like for this。

flight to be duration of four hundred，and fifteen minutes so I press type in。

that command press return that adds a，new row to my flights table and I can。

verify this by running select star from，flights and I see that now I have this。

table whose ID is one that's the ID，column from New York to London with a。

duration of 415 so I could do this again，cup，of insert queries just to give us a。

little bit more data each of this is，just a different insert query that's。



![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_4.png)

gonna add one new flight into our，database so I'll go ahead and copy those。

and then into the database I'll go ahead，and paste in all these insert commands。

to insert a whole bunch of flights into，this database and now if I run select。

star from flights what I get is all of，the flights and this is not formatted。

particularly nicely sequel Lite has some，additional tricks if you'd like to。

format it a little nicer so I can say go，ahead and put this into columns mode and。

gives me some headers yes，so header headers yes and now if I。



![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_6.png)

select star from flights the data is，organized a little more nicely where。



![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_8.png)

things are really into columns and their，headers for each of the rows where I can。

see but all right I kind of have a，text-based representation of what I was。

displaying graphically a moment to go，that inside of my flights table I have。

four columns an ID column origin，destination and duration each flight is。

just one of the rows that's inside of，this table and now I can begin to run。

additional select queries if I want to，do something like select star from。

flights where origin equals New York，well then instead of getting back all of。

the flights I'm only going to get back，the flights where the origin is New York。

so I can very quickly filter down on，this data only getting the information。

that I actually care about taking a look，at and there are other ways of。

interacting with sequel light as well，but this sequel I prompt is a very。



![](img/a0f15bc3e6e547ec0a3492b79f92e8c7_10.png)

direct way of just being able to write a，query very quickly and see the results。

of that query so it turns out there are，other types of queries we can run as。

well so we'll take a look at some others，we don't just need to say where。

something equals something else other，types of boolean expressions are allowed。

as well so I could say something like，select star from flights where duration。

is greater than 500 where the idea here，is alright let's look at the duration。

column it's an integer so we can do，arithmetic expressions on these values I。

can take a value and see is it greater，than 500 or not and when I do that what。

I get back is all of the rows that have，a duration that's greater than 500 so I。

can begin to query not just on whether，one value equals another value but also。

other types of comparisons as well and，much as in Python is when we had boolean。

expressions in Python I could join，multiple，expressions together using words like。

and' and or' sequel has the same type of，thing in its own query syntax too I。

could say something like select star，from flights where duration is greater。

than 500 and destination equals Paris，and as you might logically Intuit this。

means this means get me all the flights，that are going to Paris and that take。

longer than 500 minutes and it turns out，there's only one such row inside this。

table that satisfies both of those，constraints of course instead of using。

and I could have also used or to get a，different query where now I'm looking。

for all of the flights longer than 15，minutes or longer than 500 minutes or。

the destination in Paris is Paris so as，long as either of those conditions are。

met I'm going to get results back and so，when I get back are some of the rows。

where the destination is Paris some rows，where the destination is in Paris but。

the duration is more than 500 minutes，and of course any row that satisfies。

both of these constraints in particular，flight ID number two that gets come to。

get resulted as well when I run this，particular query on this table and there。

are other types of queries I can perform，in addition to that so I can say。

something like select star from flights，where origin is in and then in。

parentheses New York comma Lima to say，check if the origin is in this sequence。

of possible values the sequence of New，York and Lima as long as it is one of。

those two then I want for the results to，come back and so then you'll get back。

rows that have an origin of New York，rows that have an origin of Lima as well。

so you can begin to construct more，sophisticated queries that are able to。

check for whether an origin is in a list，of possible values or even if it matches。

a particular pattern that may be you，know that one of the columns looks a。

certain way or is formatted according to，a particular structure you don't know。

exactly what the value is I could run a，query like select star from flights。

where origin not equals but where origin，is like and then in quotation marks have。

a bit of a strange expression percent a，percent this percent again stands for a。

wild-card and this time the wild-card is，looking at the values of a particular。

column in this case the value of the，origin column meaning the percent stands。

for zero or more characters no matter，what those characters are we're looking。

for some number of characters maybe zero，maybe more，followed by an a followed by some other。

number of characters may be zero many，multi maybe maybe more and ultimately。

what this query is going to do is look，inside of the flights table and get back。

to me all of the results where there is，an A in the origin as long as there is。

an A in the origin column doesn't matter，if there are characters before it where。

characters after it all of the roads，that come back are going to be the rows。

that just so happened to have an A in it，so lots of ways we can begin to run。

select queries and there are even，additional functions you can add to your。

select queries as well where if instead，of just selecting the values of columns。

I want to compute the average duration，of a particular category of flights or I。

want to count how many flights are，coming out of New York or I want to find。

the longest flight that goes to London，or the shortest flight that goes to。

London or I want to add up all of the，durations for a whole bunch of flights。

maybe their flights that are connected，to each other and I want to add up the。

total travel time that might take sequel，has a number of built-in functions that。

allow us to perform these sorts of，calculations as well so a couple of。

different sequel commands we've now，taken a look at we've taken a look at。

create table that allows us to create a，new table insert that lets us add data。

to a table and then select which lets us，take data inside of the table and。

retrieve it but of course often when，we're dealing with databases the data。

doesn't just get added the data changes，in some way so we also need some way of。

being able to update data after it's，already inside of our database and to do。

that there's another query for that，which is an update command that we can。

execute on our database and that command，looks something like this again。

displayed on multiple lines up but you，could put this entirely just on one line。

sequel doesn't really care if you add，line breaks it just knows that when it。

sees a semicolon at the end of the，command that is the end of this。

particular command but here what I said，is use the update keyword to say I would。

like to update a table，what table would I like to update I'd，like to update the flights table and。

then what would I like to do well I'd，like to set the duration equal to 430 so。

whatever the value of duration happens，to be right now change it to 430 but of。

course I don't want to change it to 430，for every single flight just as in a。

select clause I could say where，something equals something or where and。

then some other Clause to specify where，I want the rows to be selected from。

likewise to an update I can say set，duration equal to 430 where a particular。

condition is true so here I'm going to，look through the flights table find。

myself all of the flights where the，origin is New York and the destination。

is London and for those rows I'm going，to update the value of the duration。

column setting the duration column equal，to 430 so using that syntax I can take。

data and update it changing one value to，another value by pinpointing which row。

or rows I would like to change if I only，want to change one row I might do like。

update flights set duration equal to，something where ID equals a particular。

ID to be able to pinpoint one ID and，then take that row and make some。

modification to it and in addition to，inserting data selecting data and。

updating data the last main command will，concern ourselves with is the ability to。

delete data the ability to take a row，and say I'd like to get rid of it or。

taking multiple rows and get rid of them，and so a command like delete from。

flights where destination equals Tokyo，as you might imagine deletes from the。

flights table all of the rows satisfy，this condition where the destination is。

equal to Tokyo so number of different，operations now that we have the ability。

to do the ability to delete from a，particular table where a condition is。

true the ability to update a table based，on particular conditions the ability to。

select data from a table and insert data，into a table as well and there are a。

couple other clauses that can be used to，add the sequel queries as well just to。

add additional functionality if I don't，want all of the rows to come back from a。

particular sequel query I can limit the，results that come back so normally。

select star from flights would get me，all of the flights inside of the table。

but I could say select star from flights，limit five to just say you know what I。

only want five results to come back from，this table order by allows me to decide。

how the results are ordered，inside the results to come back so I。

could say select star from flights order，by destination or order by duration to。

get all of the flights in order by how，long they are grouped by allows me to。

group a whole bunch of rows together so，if I wanted to group all of the flights。

by their origin so I can get all of the，flights leaving New York and all the。

flights leaving London and so forth I，could do something like select star from，flights。

by origin to group flights by their，origin as well and having as a。

constraint I can place on group I'm to，say that I would like to select all of。

the flights front from the grouping them，by their origin but they need to have a。

count of at least three meaning there，need to be at least three flights that。

are leaving from that particular city，and for all of these particular clauses。

these are helpful to know if you're，going to be directly writing sequel we。

won't worry about them too much here in，particular because fairly shortly we're。

not going to be writing sequel ourselves，we're going to just be writing Python。

code and Django is going to under the，hood be manipulating the database and。

creating the sequel commands that it is，going to run on the underlying database。

and so we will see how we don't actually，need to worry about writing the specific。

syntax but Django is going to handle，much of that for us so here now we have。

a flights table a table that keeps track，of all of the flights that we have。

organizing them by their ID and their，origin and their destination and their。

duration but oftentimes when we're，dealing with data especially in a larger。

