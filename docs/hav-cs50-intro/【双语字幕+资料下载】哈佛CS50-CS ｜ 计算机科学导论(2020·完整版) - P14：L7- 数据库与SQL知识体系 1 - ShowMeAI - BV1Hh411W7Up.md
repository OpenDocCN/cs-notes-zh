# 【双语字幕+资料下载】哈佛CS50-CS ｜ 计算机科学导论(2020·完整版) - P14：L7- 数据库与SQL知识体系 1 - ShowMeAI - BV1Hh411W7Up

![](img/f5dc569293e2d8c4779cf89dd8d3088f_0.png)

![](img/f5dc569293e2d8c4779cf89dd8d3088f_1.png)

all right。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_3.png)

this is cs50 and this is week seven and，today's focus is going to be entirely on。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_5.png)

data the process of collecting it the，process of storing it the process of。

searching it and so much more，you'll recall that last week we started。

off by playing around with a relatively，small data set we asked everyone for。

what their preferred house at hogwarts，might be and then we proceeded to，some python。

and counting up how many people wanted，well，and we ultimately did that by using a。

google form to collect it and we stored，all of the data in a google spreadsheet。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_7.png)

which we then exported of course，as a csv file so this week we thought。

we'd collect a little more data and see，start using，only a spreadsheet or in turn a csv file。

to store the data that we care about so，this url，here that you see you should see another。

google form，this one asking you some different，questions all of us probably have some，perhaps。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_9.png)

and what we'd like to do is ask everyone，to input into that form，genre or。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_11.png)

show，falls so go ah**d and take a moment to，do that。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_13.png)

and if you're unable to follow along at，home what folks are looking at is a form。

quite like this one here，whereby we're just asking them for the，title of their preferred tv show。

and the genre or genres of，that specific tv show so go ah**d and，fill that out if you could。

we'll keep an eye on the responses。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_15.png)

coming in we'll give everyone a few，moments to think about，their preferred tv show。

i myself have uh been re-watching a bit，of the office，i have been watching a lot。

of reruns of older shows i probably i，think the point is been watching too，much tv。

during all of this but in my defense，it's on in the background while i'm。

doing work on my laptop so hopefully，that makes it okay，let me take a look at the responses that。

have come in all right we're getting a，hundreds，of responses give you just another，moment or so。

the question at hand again is favorite，tv show the title thereof，and the genre or genres into which。

that tv show falls，brian are you okay with my starting to，look at the data it's okay if we keep。

collecting some more but i'm going to go，ahead and show the top，uh few rows if that sounds good。

all right so let's go ah**d and start to，look at some of this data that's come in。

here is the resulting google spreadsheet，that google forms has created for us and，forms。

this particular tool has three different，columns at least for this form one is a，gives us that。

based on what day and time everyone was，buzzing in with their responses，for title。

and genres i've manually bold faced it。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_17.png)

in advance just to make it stand out but，you'll notice that the。

headings here title and genres perfectly，matches the question that we asked in，the google form。

responses，with our questions and you can see here，punisher was the first。

favorite tv show to be inputted followed，archer，another office and so forth and in the，third column。

under genres you'll see that there's，something curious here while some of the。

cells that is the little boxes，of text have just single words like，comedy or drama。

you'll notice that some of them have a，comma separated list and that comma，separated list is because。

some of you checked as you could，multiple check boxes to indicate that，drama。

and also thriller and so the way google，forms handles this is a bit。

lazily in the sense that they just drop，all of those values，as a comma separated list inside of the。

spreadsheet itself and that's，potentially a problem if we ultimately，download this as a csv。

now you have，commas inside in between the commas，fortunately there's a solution。

to that that we'll ultimately see so，we've got a good amount of data here in。

fact if i keep scrolling down we'll see，a few hundred responses now。

and would be nice to analyze this data，in some way and figure out what the most，popular tv show is。

maybe search for new shows i might like，via their genre，so you can imagine some number of。

queries that could be uh answered by way，consider，just，a spreadsheet like this all of us are。

probably in the habit of using，occasionally google spreadsheets apple，numbers。

microsoft excel or some other tool so，let's consider what spreadsheets are，good at。

and what they are bad at would anyone，like to volunteer and answer，to the first of those what is a。

spreadsheet good at or good for，or not quite sure how to answer that。

what do you use spreadsheets for，what are some useful problems they solve。

uh yeah andrew what's your thinking on，over to andrew park oh hey um。

they're very good for quickly sorting，okay very good for quickly sorting i。

like that i could click on the top of，the title column for instance。

and immediately sort all of those titles，by alphabetically i like that。

other reasons to use a spreadsheet what，problems do they solve what are they，good at。

other thoughts on spreadsheets yeah how，storing large amounts of data that you，can later analyze。

okay so storing large amounts of data，that you can later analyze it's kind of。

a nice model for storing lots of，rows of data so to speak i will say that。

there actually is a limit and in fact，limit is。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_19.png)

long story short in graduate school i，research data，excel，supported rows for specifically i had。

some 65，536 rows which was too many at that，point for excel at the time because。

long story short if you recall from a，spreadsheets，every row is numbered from one on up。

well unfortunately at the time microsoft。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_21.png)

had used a 16 bit integer。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_23.png)

of those numbers，and it turns out the 2 to the 16th power，is roughly 65 000。

so at that point i maxed out the total，number of rows now to peter's point。

they've increased that in recent years，and you can actually store a lot more。

data so spreadsheets are indeed good，at，everything because at some point you're，spreadsheet。

than your mac or pc can handle in fact，if you're actually trying to build an。

application whether it's twitter or，instagram or facebook or anything。

of that scale those companies are，certainly not storing their data suffice。

it to say in a spreadsheet because there，would just be way too much data to use。

and no one could literally open it，on their computer so we'll need a。

solution to that problem of scale，but i don't think we need to throw out。

what works well about spreadsheets so，row form，but it would seem that you can also。

store a lot of data in column form and，even though i'm only showing columns a b。

and c of course you've probably used，d e f，model，for how to think about rows versus。

columns in a spreadsheet，i feel like we probably use them in a，somewhat different way。

conceptually we might think about them a，little differently，what's the difference between rows and。

um adding more entries like adding more，data is，those are within the rows but then like。

the actual attributes or characteristics，of the data should be in columns。

exactly when you add more data to the。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_25.png)

spreadsheet you should really be adding，to the bottom of it，adding more and more rows so these。

things sort of grow，vertically even though of course that's，just a human's perception of it。

they grow from top to bottom by adding，more and more rows but to sophia's point。

your columns represent what we might，call attributes or，fields or any other such characteristic。

that kind of is a type of data that，form，timest*mp is the first column title is，the second column。

genres is the third column and those，fields or，attributes properties of your data and。

really decide on，in advance when you're first creating，the form in our case or when you're，your in。

another case you should not really be in，the habit when using spreadsheets。

be in the habit of adding data from left，unless，you decide to collect more types of data。

so just because someone adds a new，favorite tv show，to your data set you shouldn't be adding。

that from left to right in a new column，to bottom，but suppose that we actually decided to。

collect more information from everyone，maybe that form had instead asked you。

for your name or your email address or，any other questions，those properties or attributes or fields。

would belong as new columns so this is，to say we generally decide on the，data。

in advance and then from there on out we，proceed to add add add more rows。

not columns unless we change our mind，and need to change the schema。

of our particular data so it turns out，that spreadsheets are indeed wonderfully。

useful to peter's point for you know，large or reasonably large。

data sets that um we might collect and，we can of course per last week export，those data sets as。

csv files and so we can go from a，spreadsheet to a simple text file rep。

stored in ascii or unicode more，generally on your own hard drive or，somewhere in the cloud。

and you can actually think of that file，that dot csv，database。

a database is generally speaking a file，that stores data，or it's a program that stores data for。

you and all of us have probably thought，about or use databases in some sense，you're probably。

familiar with the fact that all of those，same big websites google and twitter and。

facebook and others，use databases to store our data well，those databases are either just really。

big files containing lots of data，or special programs that are storing our，data for us。

and a flat file is just referring to the，design，decided，when storing data in simple text files。

that if you want to store different，types of data like to sophia's point。

different properties or attributes，well let's keep it simple let's just，separate those columns，aka。

a csv you can use other things you can，use tabs there's things called，frankly you can use。

anything you want but there is a corner，it，what if your actual data has a comma in。

it what if the title of your favorite tv，show has a comma，what if google is presuming to store。

genres as a comma separated list，bad things can happen if using a csv as。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_27.png)

your flat file database，but there's solutions to that and in，whenever you have。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_29.png)

commas inside of your csv file，you just make sure that the whole string，is double quoted。

on the far left and far right and，anything inside of double quotes。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_31.png)

is not mistaken thereafter as，delineating a column，as the other commas in the file might so。

that's all that's meant by a flat file，database and csv is perhaps one of the，thereof。

if only because all of these programs，numbers，allow you to save your files as csvs now。

long story short those of you who have，used fancier features of spreadsheets。

like built-in functions and formulas and，those kinds of things，those are built-in and proprietary to。

google spreadsheets and excel，csv，file or a tsv file or in a flat file，database more generally。

unchanging，values so when you export the data what，you see is what you get and that's why。

people use fancier programs like excel，and numbers in google spreadsheets。

because you get more functionality，but if you want to export the data you。

can only get indeed the raw，textual data out of it but i dare say。

that's going to be okay in fact brian do，you mind if i go ah**d and download。

this spreadsheet as a csv file now yep，all right i'm going to go ah**d in。

google spreadsheets and go to file，download and you can see a whole bunch，of options pdf。

web page comma separated values which is，the one i want so i'm going to indeed go，ahead and choose。

csv from this drop down in spreadsheets，that of course downloaded that file for。

me and now i'm going to go ah**d and go，that last week，i was able to upload a file into the ide。

and i'm going to go ah**d and do the，same here this week as well。

i'm going to go ah**d and grab my file，which ended up in my downloads folder on。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_33.png)

my particular computer here，and i'm going to go ah**d and drag and，drop this。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_35.png)

into the ide such that it ends up in my。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_37.png)

home directory so to speak so now i have，this file favorite tv shows forms and in，ide。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_39.png)

comma，title comma genres is our header row，that contains the names of the。

properties or attributes in this file，then we've got our timest*mps comma，favorite title。

comma and then a comma separated list of，genres and here indeed notice，quotes around。

any values that themselves had commas so，it's a relatively simple file format。

and i could certainly just kind of skim，through this figuring out who likes the，shows。

but per last week we now have a pretty，useful programming language at our，disposal python。

that could allow us to start，manipulating and analyzing this data。

more readily and here to my point last，job，you could absolutely do everything we're。

about to do in all weeks prior of cs50，we could have used c，for what we're about to do but as you。

can probably glean c tends to be painful。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_41.png)

for certain things like anything，involving string manipulation，changing strings analyzing strings is。

just a real pain，right god forbid you had to take the csv，file and load it all into memory not。

unlike your spell checker you would have，to be using malloc，all over the place or reallock or the。

like like there's just a lot of heavy，lifting involved in just。

analyzing a text file so python does all，of that for us by just giving us more。

functions at our disposal，opening data，so let me go ah**d and close this file。

let me go ah**d and create a new one，called favorites。pi wherein i'm going to，if we can start。

answering some questions about it and，frankly to this day 20 plus years after，time。

i myself am very much in the habit when，simple，and not solving the problem i ultimately。

want to but something，simpler just as a sort of proof of，plumbing，ahead and write a quick。

program that simply opens up this file，bottom，and just prints out each of the titles。

just as a quick sanity check that i know，data，they're in so let me go ah**d and import。

csv and then i can do this in a few，different ways but by now you've。

probably seen or remembered by using，something like the open command。

and the with keywords to sort of open，file for me，dash，form responses 1 dot csv。

and i'm going to open this up in read，mode strictly speaking the r。

is not required you might see examples，online not including it that's because，c。

and f open i'm going to be explicit and，actually do quote unquote r。

and i'm going to go ah**d and give this。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_43.png)

a variable name of file so this，that csv，file in read-only mode and creating a，reference it。

now i'm going to go ah**d and use some，of that csv functionality i'm going to，reader。

which i could call it xyz anything else，but reader kind of describes。

what this variable is going to do and，it's going to be the return value，of calling csv。

reader on that file，and so essentially the csv library per。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_45.png)

last week has a lot of fancy features，built in and all it needs as input。

is an already opened text file and then，it will then wrap that file so to speak，functionality。

like the ability to read it column，and row at a time all right now i'm，for now。

i'm going to skip the first row，i'm going to skip the first row because。

the first row has my headings timest*mp，title and genres and i know what my，that。

line for now and now i'm going to do，this for row in，reader let me go ah**d and print out。

quite simply，row and i only want title so i think if，it's three columns。

from left to right it's 0 1 2 so i want，to print out column，bracket 1 which is going to be the。

second column 0，indexed all right let me go ah**d and，save that go down to my terminal window。

and run python of favorites dot pi and，cross my fingers，okay voila it looks like it flied it。

flew by super fast，but it looks like indeed these are all，of the tv shows that folks have inputted。

scrolling up，so it looks like my program is working，but let's improve it just a little。

bit it turns out that using the csv，reader isn't necessarily the best。

approach in python many of you have，already discovered a，dict reader a dictionary reader which is。

nice because then you don't have to know，or keep double checking。

what number column your data is in you，can instead refer it to by the。

header itself so by title quote unquote，or by genres，this is also good because if you or。

maybe a colleague are sort of messing，around with the spreadsheet and they。

rearrange the columns by dragging them，left or right，any numbers you have used in your code 0。

1 2 on up，could suddenly be incorrect if your，colleague has reordered those columns。

so using a dictionary reader tends to be，titles，not the mere numbers it's still fallible。

if someone yourself or someone else，changes the values in that very first。

row and renames titles or genres，then things are going to break but at。

that point we kind of have to blame you，for not having kept track of your code，versus your data but。

still a risk so i'm going to change this，to dictionary reader or dict reader here。

and pretty much the rest of my code can，be the same except i don't need this，hack here on line five。

i don't need to just skip over to the，next row from the get go。

because i now want the dictionary reader，to handle the process of，reading that first row for me but。

otherwise everything else stays the same，except for this last line where now i，think i can now use。

row as a dictionary not as a list，title，from each given row so let me go ah**d。

and run python of favorites。pi again，and voila it looks like i got the same。

results several hundred of them but let，me stipulate that it's doing the same，those。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_47.png)

side by side all right before i forge，ahead now to actually augment this with，new functionality。

any questions or confusion on this，python script we just wrote。

to open a file wrap it with a reader or，dict reader，and then iterate over the rows one at a。

time printing，the titles any questions confusion on，syntax at all it's okay we've only known。

or seen python for a week it's fine if，it's still quite new，anything brian we should address。

yeah so why is it that you don't need to，close the file，using the syntax that you're using right。

here really good question last week i，more pedantically used open on its own，and then i later used。

a close function that was associated，with the file that i had just opened，if you will。

is actually to use this with keyword，which didn't exist in c。

and it just tends to be a useful feature，in python whereby if you say。

with open dot dot dot it will open the，file for you。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_49.png)

then it will remain open so long as your，code is indented inside of that。

with keywords block and as soon as you，get to the end of your program。

it will automatically be closed for you，so this is one of these features where，python in some sense。

is trying to protect us from ourselves，it's probably pretty common for humans，file。

that can create problems with saving，things permanently it can create memory，leaks as we know from c。

so the width keyword just assumes that，i'm not going to be an idiot and forget，to close the file。

python is going to do it for me，automatically，other questions or confusions brian。

how does dict reader know that title is，the name of the key，inside of the dictionary really good。

question too so，it is designed by the authors of the，python language。

to look at the very first row in the，file，first row，phrase，before the first comma is the name of。

the first column，that the second word or phrase after the，first comma is the。

name of the second column and so forth，so a dict reader just presumes。

as is the convention with csvs that your，first row is going to contain。

the headings that you want to use to，refer to those columns if your csv。

happens not to have such a heading，whereby it just jumps right in on the。

first row to real data then you're not，correctly，configuration，all right so。

let's go ah**d and now i feel like，there's a whole mess here and you know。

some of these shows are pretty popular，and as i'm glancing over this i，bunch of you like。

the office a whole bunch of you like，breaking bad game of thrones and a whole。

bunch of other shows as well，so it'd be nicer i think if we kind of。

narrow the scope of our look at this，data by just looking at unique values。

you're looking at unique values so，rather than just iterate over the file。

top to bottom printing out one，title after another why don't we go。

ahead and sort of accumulate all of this，data in some kind of data structure。

so that we can throw away duplicate，values and then only print out。

the unique titles that we've accumulated，so i bet we can do this in a few ways。

but if we think back to last week's，demonstration of our dictionary。

you'll recall that i used what was，called a set and i'm going to go ah**d。

and create a variable called titles and，set it equal to something called。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_51.png)

set and a set is just a collection of，values it's kind of like。

a list but it eliminates duplicates for，me and that would seem to be exactly the。

characteristic that i want，each title，which is now premature if i want to。

first filter out duplicates，i'm going to go ah**d and do this i'm。

going to go ah**d and add to the titles，rows，i'm instead，adding to the title set that particular。

deal the set，data structure in python is going to，throw away the duplicates for me and，uniques。

now at the bottom of my file i need to，do a little more work，admittedly now i have to iterate over。

the set to print out only those unique，titles so let me do this for title in。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_53.png)

titles go ah**d and print out title and，user friendly，less than。

n or whatever you can just say for title，in titles，and if the titles variable is the type。

of data structure that you can，list，or if it's a set or even if it's a。

dictionary another data structure we saw，last week in python，the for loop in python will just know。

what to do this will loop over，all of the titles in the titles，sets so let me go ah**d and save this。

file and go ah**d now and run python of，favorites。pi，and it looks like yeah the list is。

different in some way，up，definitely fewer than before because my。

scroll bar didn't jump nearly as far，down but honestly this is kind of a mess。

let's go ah**d and sort this now in c it，would have been kind of a pain to sort。

things we'd have to whip out the，pseudocode probably for bubble sort。

selection sword or god forbid merge sort，and then implement it ourselves。

but no with python comes really the，proverbial kitchen sink of functions。

so if you want to sort this set you know，what just say you want it sorted。

there is a function in python called，sorted that will use one of those better。

algorithms maybe it's merge sort maybe，it's something called quick sort maybe。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_55.png)

it's something else altogether，it's not going to use a big-o of，n-squ*red sort someone at python。

probably have spent the time，implementing a better sort，for us but it will go ah**d and sort the。

set for me now let me go ah**d and do，this again let me increase the size of，my terminal window。

and rerun python of favorites。pi okay，and now we have an interesting。

assortment of shows that's easier for me，to wrap my mind around，because i have it now sorted here。

and indeed if i scroll all the way up we，should see all of the shows beginning，with。

numbers or a period uh which might have，just been someone playing around。

followed by the a words the b words and，so forth so now it's a little easier to。

wrap our minds around this，but something's up i feel like，a lot of you like avatar the last。

airbender and yet，i'm seeing it indeed four different，times，but i thought we were filtering this。

down to uniques，by using that set structure so what's，going on and in fact if i keep scrolling。

i'm pretty sure i saw more，duplicates in here bojack horseman，breaking bad breaking bad。

brooklyn nine nine brooklyn nine-nine，cs50 and several different flavors。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_57.png)

um and yes uh keeps going friends，so i see a lot of duplicate value so，what's going on。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_59.png)

yeah so your current sort is case，insensitive，someone，places。

then it's going to be a different result，each time yeah exactly some of you。

weren't quite diligent when it came to，capitalization，and so in fact the reality is is kudana。

notes that there's differences in，capitalization now we've addressed this。

before in fact when you implemented your，own spell checker。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_61.png)

you had to deal with this already when，text，some words might be capitalized some。

might be all lowercase all uppercase and，you wanted to tolerate，different casings and so we probably。

solved this by just forcing everything，to uppercase or everything to lowercase。

and doing things therefore case，insensitively so give me just a moment，a quick。

change to my form here and i'm going to，go ah**d and，i'm going to go ah**d and change this in。

such a way，so that we have instead，let me shrink back my code let's go。

ahead and change this in such a way that，we actually force everything to。

uppercase or lowercase doesn't really，matter which but we need to canonicalize。

things so to speak in some way，and to canonicalize things just means to。

format all of your data in some standard，way so to katana's point，let's just standardize the。

uppercase all，lowercase we just need to make a，judgment call so i'm going to go ah**d。

and make a few tweaks here，i'm still going to use a set i'm still，going to read the csv as before。

but instead of just adding the title，with row bracket title，i'm going to go ah**d and force it to。

uppercase just arbitrarily，just for the sake of uniformity and i'm。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_63.png)

also going to be，and then let's go ah**d and check what，exactly has happened here i'm not going。

to change anything else，but let me go ah**d and increase the，size of my terminal window rerun。

python of favorites。pi and voila，it's a little harder to read just。

because i'm not used to reading all caps，kind of looks like we're yelling at，ourselves but。

i don't see wait a minute i still see，the office，over here twice if i keep scrolling，strange。

stranger things that just looks like a，typo i see two sherlocks though，you。

and i don't seem to have solved things，fully。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_65.png)

and this one's a little more subtle what，more should i perhaps do to my data。

to ensure we get duplicates removed，maybe trimmer around the edges and we'll，of that but。

what do you mean what does that do oh，like trim off the extra spaces in case，words。

yeah exactly it's pretty common for，hit the space，bar where they shouldn't and in fact i'm。

kind of inferring that i bet，one or more of you accidentally typed，sherlock space。

and then decided nope that's it i'm not，typing anything else but that's space。

even though we can't quite see it，obviously is there and when we do a，structure does that。

it's actually going to be noticed when，they're not going to be，the same so i can do this in a few。

python，you can chain functions together which，is also two kind of a fancy feature。

notice what i'm doing here i'm still，accessing the titles，set i'm adding the following value to it。

i'm adding the value row bracket title，but not quite，speak，i'm going to go ah**d and strip it which。

means if we look up the documentation，for this function to olivia's point it's。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_67.png)

going to strip off or trim，all of the white space to the left all，of the white space to the right。

whether that's the spacebar or the enter，key or the tab，character or a few other things as well。

it's just going to get rid of leading，and trailing white space and then，whatever's left over。

i'm going to go ah**d and force，everything to uppercase in the spirit of。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_69.png)

kadana suggestion 2。 so we're sort of，combining two good ideas now。

to really massage the data if you will，into a cleaner format and this is such a，real world reality。

like humans you and i cannot be trusted，to input data，the way we are supposed to sometimes。

it's all lowercase because we're being a，little lazy or a little social，from amazon。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_71.png)

and trying to input a valid postal，because uh，i can think of a few people in my life，thing just yet。

and so things might be all capitalized，instead this is not good，for computer systems that require。

precision to our emphasis in week zero，and so massaging data means cleaning it。

up doing some mutations，that don't really change the meaning of，the data but canonicalize。

it standardize it so that you're，comparing apples and apples so to speak，not apples and oranges。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_73.png)

well let me go ah**d and run this again，in my bigger terminal window。

python of favorites stop high voila and，scrolling up up up，see，up and up and up，related to。

white space and i think we have a much，cleaner unique list of titles。

at this point of course if we scroll up，i would have to be a lot more clever。

if i want to detect things like，of you，was very diligent about putting f period，got。

bored at the end and left off the last，period but that's going to happen when。

you're taking in user input，we've of course got all these variants，clean up。

because now you can imagine having to。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_75.png)

add a whole bunch of if conditions and，else's and l-tips to sort of clean all。

of that up if we do want to canonicalize，unquote。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_77.png)

cs50 so this is a very slippery slope，like you and i could start writing a，up。

but that's the reality when dealing with，real world data，well let's go ah**d now and improve this。

program further，do something a little fancier because i，now can trust that my data has been。

canonicalized except for the actual，the like，let's go ah**d and figure out what's the。

most popular favorite tv show，among the audience here so i'm going to。

start where i have before with my，current code because i think i have most。

of the building blocks in place，i'm going to go ah**d and clean up my。

code a little bit in here i'm going to，go ah**d and give myself a separate，variable now called title。

just so that i can think about things in，a little more orderly fashion。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_79.png)

but i'm not going to start adding things，to this set anymore，in fact a set i don't think is really。

going to be sufficient，to keep track of the popularity of tv，shows because by definition the set is。

throwing away duplicates，but the goal now is kind of the opposite，i want to know。

which are the duplicates so that i can，tell you that this many people like the。

office this many people like，uh breaking bad and the like so what。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_81.png)

tools do we have in python's toolkit。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_83.png)

out，that information any thoughts on what，data structure，out，show popularity show popularity and by。

it，um i guess um one option could be to use，dictionaries so that you could have like，the office。

i don't know 20 votes and then game of，thrones another one so that。

a dictionary could really help you，visualize that，yeah perfect instincts recall that a。

dictionary at the end of the day，no matter how sophisticated it's。

implemented underneath the hood like，your spell checker，it's just a collection of key value。

pairs and indeed it's，maybe one of the most useful data，structures in any language。

because this ability to associate one，piece of data with another。

is just a very general purpose solution，point，if the problem at hand is to figure out。

the popularity of shows well let's make，the keys the titles of our shows，to speak。

the values of those keys we're going to，map title，to votes title to vote title to vote and，so。

let me go ah**d and scroll up and i can，set，i can instead say dict and give myself。

just an empty dictionary，there's actually shorthand notation for，that that's a little more common。

to use two empty curly braces that just，means the exact same thing。

give me a dictionary that's initially，empty there's no fancy shortcut for a。

set you have to literally type out s e t，open paren close paren but dictionaries。

are so common so popular so powerful，they have this little syntactic shortcut，of just two。

curly braces open and close so now that，i have that，let me go ah**d and do this inside of my。

for loop，instead of printing the title which i，don't want to do and instead of adding。

it to the set i now want to add it to，the dictionary，so how do i do that well if my。

dictionary is called titles，i think i can essentially do something，like this titles bracket。

title equals or maybe plus，equals one maybe i can kind of use the。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_85.png)

dictionary，numbers，that start at zero and then just add one，add two add three so every time i see。

equals 1，plus equals 1。 we can't do plus plus。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_87.png)

because that's not a thing in python it，only exists in c，but this would seem to go into the。

dictionary called titles，look up the key that matches this，specific title。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_89.png)

and then increment whatever value is，there，by one but i'm going to go ah**d and run。

this a little naively here，let me go ah**d and run python of，favorites dot pi。

and wow or it broke already on line nine，so it's sort of an apt uh choice of show，to begin with。

we have a key error with punisher so，punisher is bad something bad has just。

happened but what does that mean，a key error is referring to the fact，that i tried to access。

an invalid key in a dictionary this is，code here，even though titles is a dictionary and。

even though the value of title，singular is quote unquote punisher i'm，getting a key error。

because that title does not yet exist so。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_91.png)

even if you're not sure of the python，the，intuitive solution here。

i cannot increment the frequency of the，punisher，because punisher is not in the。

dictionary it's almost，i think that you need first of all to，create the for loop and maybe assign a。

value to every，thing in the dictionary for example the，value zero and then add。

one yeah so good instincts and here i，can use another metaphor i worry we。

might have a chicken in the egg problem，there because i don't think i can go to，the top of my code。

at a loop that initializes all of the，values in the dictionary to zero because。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_93.png)

i would need to know，all of the names of the shows at that，point now that's fine。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_95.png)

i think i could take you maybe more，literally gray，and open up the csv file iterate over it。

top to bottom and，any time i see a title just initialize，of zero。

zero zero then have another for loop，maybe reopen the file，and do the same and that would work but。

it's arguably not，very efficient it is asymptotically in，terms of big o。

but that would seem to be doing twice as，much work iterate over the file。

once just to initialize everything to，time，just to increment the counts i think we。

can do things a little more efficiently，i think we can achieve not only，thoughts。

on how we can still solve this problem，without having to iterate over the whole，twice，to check if。

that key is in the dictionary and if，it's not been added，and then go ah**d and increment the。

value after nice and，we can do exactly that so let's just，apply that intuition if the problem is。

that i'm trying to access a key，that does not yet exist well let's just，somehow its point，if it does。

then increment it but if it does not，then and only then to grid's advice。

initialize it to zero so let me do that，let me go ah**d and say，pythonic。

beautiful way of asking a question like，that way cleaner than in c，let me go ah**d then and say uh。

if the，called titles，well that's okay too i can go ah**d and，say titles，bracket title equals zero。

so the difference here is that i can，certainly inc，i can certainly index into a dictionary。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_97.png)

using a key，that doesn't exist if i plan at that，moment to give it a value。

that's okay and that has always been，okay since last week，but however if i want to go ah**d and。

increment the value that's there i'm，going to go ah**d and do that，in this separate line but i did。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_99.png)

introduce a bug，i did introduce a bug here i think i，need to go one step further。

logically i don't think i want to，initialize this to zero。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_101.png)

per se does anyone see a subtle bug in，my logic here，if the title is already in the。

dictionary i'm incrementing it by one，any subtle catches here yeah olivia what。

i think you should initialize it to one，since it's the first instance。

exactly i should initialize it to one，otherwise i'm accidentally overlooking。

this particular title and i'm going to，go ah**d and undercount it so i can fix。

this either by doing this，or frankly if you prefer i don't，technically need to use an if。

else i can use just an if by doing，if，title not in titles then i could go，ahead and say titles。

bracket title get zero and then after，that i can blindly，so to speak just do this so which one is。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_103.png)

better i think this second one is maybe，line of code。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_105.png)

but it's ensuring with that if condition，to someone's advice，dictionary。

until i'm sure that the title is in，now，python of favorites dot pi enter。

and okay it didn't crash so that's good，information，but i now have access to a bit more let，program。

where i have now this loop let me go，ahead and print out not just the title。

but the value of that key in the，dictionary，by just indexing into it here and you，but with print。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_107.png)

you can actually pass in multiple，arguments and by default print will just。

separate them with a space for you you，them with anything，but this is just meant to be a quick and。

now the，popularity thereof so let me run this，again python of favorites dot pi。

and voila it's kind of，all over the place office super popular，with 26 votes there a lot of。

single votes here uh a lot of big bang，theory has nine，feel like this is going to take me。

forever to wrap my mind around which are，the most popular，shows so of course how would we do this。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_109.png)

well to the point made earlier，with spreadsheets my god in microsoft。

excel or google spreadsheets or apple，heading and boom，sort it we seem to have lost that。

capability unless we now do it in code，so let me do that，for us let me go ah**d and go back to my。

code and it looks like，sorted even though it does work on。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_111.png)

dictionaries，is actually sorting by key not by value，and here's where our python programming。

techniques need to get a little more，sophisticated and we wanted to introduce。

another feature here now of，python which is going to solve this，general way。

so if we read the documentation for，sorted the sorted，they're in。

it sorts lists by the values they're in，it sorts dictionaries，by the keys they're in because。

dictionaries have two pieces of，information for every，element it has a key and a value not。

just a value so by default sorted sorts，by key so we somehow have to override，that behavior。

so how can we do this well it turns out，that the sorted function，literally called。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_113.png)

key and the key argument，takes as its value the name of a，function and this is where things get。

really interesting if not confusing，really quickly it turns out in python，arguments。

by way of their name and technically you，can do this in c it's a lot more，syntactically involved。

but in python it's very common in。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_115.png)

javascript it's very common in a lot of，languages it's very common。

to think of functions as first class，objects which is a fancy way of saying。

you can pass them around just like they。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_117.png)

calling them，yet but you can pass them around by，their name so what do i mean by this。

well i need a function now to sort my，dictionary，this，and perhaps so let me go ah**d and give。

the moment called f，because we're going to get rid of it，temporarily。

define a function called f that takes as，input a title，and then it returns for me the value。

corresponding to that key so i'm going，to go ah**d and return。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_119.png)

function，whose purpose in life is super simple，you give it a title。

it gives you the count thereof the，looking it up，simple，but that's its only purpose in life but。

now according to the documentation for，sorted，what it's now going to do because i'm。

passing in a second argument called key。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_121.png)

the sorted function rather than just，alphabetically by，key it's instead going to call。

that function f on every one，of the elements in your dictionary and，depending on your。

answer the return value you give，instead，to determine to determine the actual。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_123.png)

ordering，so by default sorted just looks at key，what i'm effectively doing with this，value。

corresponding to every key and so the，logical implication of this even though，the syntax is a little。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_125.png)

new is that this dictionary of titles，by key，because again by default it sorts by key。

but if i define my own，key function and override that behavior，to return the corresponding value。

it's the values the numbers the counts。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_127.png)

thing，all right let's go ah**d and see if，that's true in practice let me go ah**d。

and rerun python favorites dot pi，i should see all the titles and voila。

conveniently the most popular show seems，to be game of thrones，27。

followed by the office with 26 and so，forth but of course the list is kind of。

backwards i mean it's convenient that i。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_129.png)

can see it at the bottom of my screen，but really if we're making a list it。

should really be at the top so how can，we override that behavior turns out the。

sorted function if you read its，documentation，also takes another optional parameter，called reverse。

capital t，in python that's going to go ah**d and，give us now。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_131.png)

the reverse order of that same sort so，window，rerun it again and voila if i scroll。

back up to the top it's not，alphabetically sorted but if i keep。

going keep going keep going keep going，the numbers are getting bigger and voila。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_133.png)

now game of thrones with 33，is all the way at the top，all right so pretty cool and again the，least。

is that we can actually pass in，functions two functions，and leave it to the ladder to call the。

former，so that just complicated just to say but，any questions，or confusion now on how we are using。

dictionaries and how we are sorting，things，in this reverse value-based way。

any questions or confusion anything in，the chat or verbally brian。

uh looks like all questions are answered，here okay，then in that case let me point out a。

common mistake notice that even though f，is a function，would be，incorrect the reason being we。

deliberately want to pass the function f，into the sorted function so that the。

sorted function can take it upon itself，to call f again and again and again we。

don't want to just call it once by using，the parentheses ourselves。

we want to just pass it in by name so，that the sorted function which comes，with python。

can instead do it for us santiago did，we，put f of title uh so like why wouldn't。

i was going to ask that question，specifically oh with the，uh，because that would call the function。

once and only once we want，sorted to be able to call it again and。

again now here's actually an example as，we've seen in the past。

of a correct solution this is behaving，as i intend a list of sorted titles uh，from top to bottom。

in order of popularity but it's a little，poorly designed because i'm defining。

this function f whose name in the first，place is kind of lame。

but i'm defining a function only to use，it in one place and my god the，waste。

of keystrokes to have defined a new，function just to then pass it in。

so it turns out in python if you have a，very short function，whose purpose in life is meant to be to。

that's it，and it's short enough that you're pretty，sure you can fit it on one line of code。

without things wrapping and starting to，get ugly stylistically，it turns out you can actually do this。

instead，you can copy the code that you had in，mind like this，function name。

you can actually use a special keyword，in python called lambda。

you can specify the name of an argument，for your function as before。

and then you can simply specify the，return value，thereafter deleting the function itself。

so to be clear key is still an argument，to the sorted function，it expects as its value typically the。

name of a function，but if you've decided that ah this seems，like a waste of extra waste of effort to。

define a function then pass the function，in especially when it's so short。

you can do it in a one-liner a lambda，function is an，python，its name。

therefore you don't have to choose a，name for it but it does care still。

about its arguments and its return value，so it's still up to you to provide zero，or more arguments。

and a return value and notice i've done，that i've specified the keyword lambda。

followed by the name of the argument i，want this anonymous，nameless function to accept and then i'm。

specifying the return value，and with lambda functions you do not。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_135.png)

need to specify return，whatever you write after the colon is，literally what will be returned。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_137.png)

automatically so again this is a very，pythonic thing to do it's kind of a very。

clever one-liner even though it's a，time，but it allows you to condense your。

thoughts into a succinct statement that，gets the job done，so you don't have to start defining more。

else，then need to keep track of，all right any questions then on this and，i'm pretty sure this is as。

complex or sophisticated as our python，code today we'll get，i was wondering why lambda is used as。

like specifically rather than some other，keyword，yeah so there's a long history in this。

and if in fact you take a course on，functional programming，at harvard it's called cs51 there's a。

this，let me defer that one for another time，but indeed not only in python but in。

other languages as well these things，have come to exist called，lambda functions so they're actually。

quite commonplace，in other languages as well and so python，just adopted the term。

of art mathematically lambda is often，used as a symbol for，functions and so they borrowed that same。

idea in the world of。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_139.png)

programming all right so seeing no other，questions let's go ah**d and solve。

a related problem still with some python，but that's going to。

push up against the limits of efficiency，when it comes to storing our data in csv。

files let me go ah**d and，start let me go ah**d and start fresh in，this file favorites dot pi。

all of the code i've written thus far，though is on the course's website in。

advance so you can see the incremental，improvement i'm going to go ah**d and。

again import csv at the top，and now this let's write a program this，time that doesn't just。

automatically open up the csv and，analyze it looking，for the total popularity of shows，csv。

and then go ah**d and output uh the，popularity thereof and i can do this in。

a bunch of different ways but i'm going，possible，i'm first going to ask the user for to。

input a title，i could use cs50's getstring function，but recall that it's pretty much the。

same as python's input function，so i'm going to use python's input，function today。

and then i'm going to go ah**d and as，before open up that same csv called，favorite tv shows。

form responses 1。csv，file，i'm then going to give myself a reader。

and i'll use a dict reader again so i，don't have to worry about，knowing which columns things are in。

passing in file，and then let's see if i only care about，one title i can keep this program。

simpler i don't need to figure out，the popularity of every show i just need。

to figure out the popularity of，one show the title that the human has。

typed in so i'm going to go ah**d and，give myself a very simple int。

called counter and set it equal to zero，i don't need a whole dictionary just one。

variable suffices now，and i'm gonna go ah**d and iterate over，uh the rows，gonna say。

if the current rows title uh，equals equals the title the human typed，by。

one and it's already initialized because，good，and then at the end of this program。

let's very simply print out the value of。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_141.png)

is to，and then just，report the popularity thereof by，in the file。

so let me go ah**d and run this with，python of favorites。pi，enter uh let me go ah**d and type in the。

office enter。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_143.png)

and 19。 now i don't remember exactly，what the number was but i remember the。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_145.png)

office was more popular than that，i'm pretty sure it was not 19。intuition as to why this program is。

buggy，or so it would seem what have i done，any thoughts in the chat or。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_147.png)

a few people in the chat are saying you，need to remember to deal with。

capitalization and white space again，yeah so we need to uh practice those。

same lessons learned from before so i，should really canonicalize the input。

that the human i just typed in and，also the input that's coming from the，this is up here。

to first strip off leading and trailing，white space in case i get a little。

sloppy and hit the space bar，where i shouldn't and then let's go，because。

it doesn't matter if it's upper or lower，that way，and then when i do this look at the。

current rows title，i think i really need to do the same，thing if i'm going to canonicalize one i。

need to canonicalize the other and now，compare the all caps white space。

stripped versions of both strings so now，let me rerun it，now i'm going to type in the office。

enter and voila now i'm at，26 which i think is where we were at。

before and in fact now i the user can be，a little sloppy i can say the office。

i can run it again and say the office。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_149.png)

space bar a lot，enter it's still going to work and，indeed though we seem to be like。

belaboring the pedentic here with uh，trimming off white space and so forth。

just think in a relatively small，audience here how many of you，accidentally hit the space bar or。

capitalize things differently this。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_151.png)

happens massively on scale and you can，imagine this being important。

when you're tagging friends in some，social media account you're doing at。

brian or the like you don't want to have，to require the user to type at。

capital b lowercase r i a n and so forth，is such，a common uh problem to solve including。

in today's apps that we all use，all right any questions then on this。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_153.png)

then let me ask a question of you in，what sense is this program poorly，designed。

in what sense is this program poorly，designed，this is more subtle but think about the。

running time of this program，in terms of big o what is the running，time of this program if the。

csv file has n different，shows in it or n different submissions。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_155.png)

so n is the variable in question yeah，what's the running time andrew。

is the big o n because you're using the，linear search yeah it's big o of n。

because i'm literally using linear，search by way of the for loop that's how，c。

starts at the beginning and potentially，goes all the way till the end and so i'm。

using implicitly linear search，because i'm not using any fancy data，just，imagine that。

if we surveyed not just all of the，students here in class but maybe。

everyone on campus or everyone in the，world maybe we're internet movie，database imdb。

there could be a huge number of votes，and a huge number of shows。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_157.png)

and so writing a program whether it's in，a terminal window like mine or maybe on。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_159.png)

a mobile device or maybe on a web page，for your laptop or desktop。

it's probably not the best design to，constantly，loop over all of the shows in your。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_161.png)

database from top to bottom，just to answer a single question it。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_163.png)

would be much nicer to do things in，log of end time or in constant time and。

thankfully over the past few weeks both，in cnn and python we have seen，practicing。

what i've preached here and in fact at，some point，this notion of a flat file database。

starts to get too primitive for us flat，file databases like csv files。

are wonderfully useful when you just，want to do something quickly。

or when you want to download data from，standard。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_165.png)

portable way portable means that it can，systems，csv is about as simple as it gets，word。

or apple numbers or any particular，product it's just a text file so you can。

use any text editing program，or any programming language to access it，but flat file databases aren't。

necessarily the best，uh structure to use ultimately for，larger data sets。

because they don't really lend，themselves to more efficient queries so，to search，out that there。

are better databases out there generally，known as relational databases that，store data，store data。

now to be fair those programs use a lot，of ram memory，where they actually store your data and。

they do certainly persist your data they，keep it long-term，by storing your data also in files but。

between you and your data，there is this running program and if。

you've ever heard of oracle or mysql or，postgres or sql server or microsoft，access or bunches。

of other popular products both，commercial and free and open source，alike relational databases are so。

similar in spirit，to spreadsheets but they are implemented，in software。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_167.png)

and they give us more and more features，and they use more and more data，structures so that we can。

search for data insert data delete data，update data，much much more efficiently than we could。

if just using，something like a csv file so let's go，ahead and take our five minute break。

here and when we come back we'll look at，relational databases and in turn a。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_169.png)

alright so we are back and the goal at，hand now is to transition from these，fairly simplistic。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_171.png)

flat file databases to a more proper，relational database and relational。

databases are indeed what power，so many of today's mobile applications，web applications and the like。

now we're beginning to transition to，real world software with real world。

languages at that and so now，uh let me introduce what we're going to，call sql lite。

so it turns out that a relational，database is a database that stores all。

of the data still in rows and columns，but it doesn't do so using。

spreadsheets or sheets it instead does，so using what we're going to call。

tables so it's pretty much the same idea，but in with tables do we get some，additional functionality。

with those tables we'll have the ability，to search for data，update data delete data insert new data。

and the like and these are things that，we absolutely can do with spreadsheets。

but in the world of spreadsheets if you，the human doing，it by manually clicking and scrolling。

typically if you want to insert data，it's you the human，typing it in manually after adding a new。

row if you want to delete something it's，and，deleting a whole row or updating the。

individual cells they're in，with sql structured query language we。

have a new programming language that is，very often used in conjunction with。

other programming languages and so today，we'll see sql used on its own initially。

but we'll also see it in the context of，python，can itself use sql to，alone。

could do so with that said sql lite is，like a light version of sql it's a more。

user-friendly version it's more portable，it can be used on macs and pcs and。

phones and laptops and desktops and，servers but it's incredibly common in，phone。

many of the applications you are running，today on your own device。

are using sql lite underneath the hood，so it isn't a toy language per se。

it's instead a relatively simple，implementation of a language generally。

known as sql but long story short，there's other implementations of。

relational databases out there and i，rattled off several of them already。

oracle and mysql and postgres and the，like those all，have slightly different flavors or。

dialects of sql，language，for interacting with databases but。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_173.png)

communities，have kind of added or subtracted their，own preferred features。

and so the syntax you use is generally，constant across all platforms。

but we will standardize for our purposes，on sql lite and indeed this is what you。

would use these days in the world of。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_175.png)

mobile applications，so it's very much germane there so with，sqlite。

we're going to have ultimately the，ability to，query data and update data delete data。

and the like but to do so we actually，need a program，so the way，your data still。

in a file but it's a binary file now，that is it's a file containing zeros and。

ones and those zeros and ones might，represent text they might represent。

numbers but it's a more compact，efficient representation than a mere csv，file would be using ascii。

or unicode so that's the first，difference sqlite，uses a single file a binary file to。

store all of your data and represented，inside of that file by way of all of，those zeros and ones。

are the tables to which i alluded before，which are the analog，in the database world of sheets or。

spreadsheets in the spreadsheet world，so to interact with that binary file。

wherein all of your data is stored we，need some kind of user facing program，but the most，sql lite。

is called sql lite3 essentially version，tool，similar in spirits any of the commands。

you've run in a terminal window thus far，that allows you to open up that binary。

file and interact with all of your，tables now here again we kind of have a。

chicken in the egg problem if i want to，use a database but i don't yet。

have a database and yet i want to select，data from my database，how do i actually load things in well。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_177.png)

you can load data into a sqlite database，in at least two ways，just import，csv。

and what you do is you save the csv on，your mac or pc and your cs50 ide，and it will just。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_179.png)

out where all of the，commas are and it will construct inside。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_181.png)

of that binary file，the corresponding rows and columns using，the appropriate zeros and ones。

to store all of that information so it，just imports it for you automatically。

approach two would be to actually write，other，that actually manually inserts all of，the data。

into your database and we'll do that as，ahead and run，for instance sqlite3 and this is。

pre-installed on cs50 ide and it's not，that hard to get it up and running on a，mac and pc as well。

i'm going to go ah**d and run sql light，3 in my terminal window here，output。

it's telling me to type period help if i，want to see some usage hints but。

i know most of the commands and will。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_183.png)

that you might need，in fact one of the commands that we can，import。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_185.png)

so generally you won't use these that，frequently you'll only use them when。

creating a database for the first time，when you are creating that database from，an existing csv。

file and indeed that's my goal at the，moment let me take our csv file。

containing all of your favorite tv shows，and load it into sql lite in a proper，relational database。

so that we can do better than for，instance big o，of n when it comes to searching that。

data and doing anything else on it，so to do this i have to execute two。

commands one i need to put sql light，into csv mode，and that's just to distinguish it from。

other flat file formats like tsv for，tabs or some other format，and now i'm going to go ah**d and run。

import then i have to specify the name，of the file to import which is the csv。

and i'm going to go ah**d and call my，table shows。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_187.png)

so dot import takes two arguments the，name of the file that you want to import。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_189.png)

to create，out of that file and again tables have，rows and columns，delineate。

where those columns begin and end i'm，going to go ah**d and hit enter。

it looks like it flew by pretty fast，nothing seems to have happened。

but i think that's okay because now。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_191.png)

ability，to actually manipulate that data but how，do we manipulate the data。

we need a new language sql structured，query language，is the language used by sql lights and。

oracle and mysql and postgres and，bunches of other products whose names。

you don't need to know or remember，anytime soon，but sql is the language we'll use to。

query the database，for information and do something with it，generally speaking。

a relational database and in turn sql，which is a language by，which you can interact with relational。

databases support four，fundamental operations and they're sort，of a crude acronym。

pun intended that is just helpful for，remembering what those fundamental。

operations are with relational databases，crud，stands for create read。

update and deletes and indeed the，acronym is crud crud，so it helps you remember that the four。

basic operations supported by，any relational database are create read，update delete。

create means to create or add new data，read means to，access and load into memory new data，files。

update and delete mean exactly that as，well if you want to manipulate the data，in your data set。

now those are generic terms for any，relational database those are the four。

properties typically supported by any，relational database，specific，implement。

those four uh functionalities，they are create and insert achieve the。

same thing as create more generally，the keyword select is what's used to，read data from a database。

update and delete are the same so it's。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_193.png)

kind of an annoying inconsistency the，acronym or the term of art is crud。

create read update delete but in the，decided to，these five，will，in the language sql so what you are。

looking at as are，five of the keywords you can use in this，new language called sql。

to actually do something with your，database now what does that mean。

well suppose that you wanted to manually，time，what do you do well back in the world of。

spreadsheets it's pretty straightforward，right you like open up google。

spreadsheets you go to like file new or，whatever and then you just voila。

you get a new spreadsheet into which you，the like，microsoft excel apple number same thing。

file menu new spreadsheet or whatever，and boom you have a new spreadsheet now，in the world of sql。



![](img/f5dc569293e2d8c4779cf89dd8d3088f_195.png)

interacted with，code however there are graphical user，interfaces guise by which you can。

interact with them as well but we're，going to use code today to do so。

and programs at a command line it turns，out that you can，create tables programmatically by。

running a command like this，so if you literally type out syntax，along the lines of create。

table then the name of your table，indicated here in lowercase。

then a parenthesis then the name of your，column that you want to create。

and the type of that column a la，columns。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_197.png)

you will use，to create in this language called sql a，again like。

table in lowercase is meant to represent，table，column in lowercase is meant to be the。

name you want to give to your own column，maybe it's title maybe genres。

and dot dot just means of course you can，have even more columns than that。

but literally in a moment if i were to，type in this kind of command。

into the terminal window after running。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_199.png)

the sqlite3 program，i could start creating one or more，tables for myself。

and in fact that's what already happened，for me this dot，import command which is not part of sql。

option，in excel or google spreadsheets dot，import just automates a certain process。

for me and what it did for me is this，if i type now dot schema which is。

another sql light specific command，anything that starts with a dot，is specific only to sqlite 3 this。

terminal window program。

![](img/f5dc569293e2d8c4779cf89dd8d3088f_201.png)

notice what's outputted is this by，running dot import，table，in my database called，timest*mp。

title and genres where did those column，names come from，come from well they came from the very。

first line in the csv，and they all looked like text so the，type of those values was just in，clear。

i could have manually typed this out，created these three columns in a new。

table called shows for me but again the，dot import command just automated that，from a csv。

