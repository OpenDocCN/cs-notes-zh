# 哈佛大学《CS50P shorts｜ Introduction to Programming with Python (CS50P) 2024 shorts》 - P16：-17-Reading and Writing CSVs - CS50P Shorts.zh_en - GPT中英字幕课程资源 - BV1MS42197Vo

![](img/9137c940096fb5e246eed99e8fe90e73_0.png)

Well hello on and all and welcome to our short on reading and writing CSVs Now CSVs are great for storing data in terms of comma separated values and they're great for analyzing data。

 particularly when coupled with Python so I have here a program called views do pi which is not yet but will be soon the goal of it is to read in some data from views do CSsv these comma separated values in this file here and notice how I have in this case the names of each of the 36 views of Mount Fuji。

 some prints produced by the artist Hokuai in the 1830s。Now I have here three columns of data。

 if you will， one called ID， which implies the ID of the print， one called English title。

 which is the English title of the print， and one called Japanese title which is the Japanese title of the print as well so notice here if I go to one do JPG2。

 I actually have a picture of the great Wa of Kanagawa。Right here as well。If I go to2。 JPEG。

 I'll see fine Wind clear warning， so there's actually a correspondence between the IDs of the pictures here and the actual pictures。

 the dot JPEG I have stored in my code space here as well。

So I'll go ahead and close these and our goal is to read in this CSV of views and do a bit of image analysis on them。

 think can be interesting if you actually find out how bright or not bright each of these photos is。

 in fact we have a function here called calculateulate brightrightnesss which takes input a file name and returns to us zero to one on a zero to one scale。

 how bright or not bright， how dark， the image is one being brightest， completely white。

 and zero being the darkest， completely black in this case。

So let's see if we can maybe start off by just reading whatever is inside of this CSV file and focus on the analyzing just a little bit later。

 so our first step will be to try to open this CSV file and maybe get a sense for the data that's inside of it and make sure we can actually see that data in Python too。

So to read a CSV file， we've seen we should use the CSV library， I'll import CSV up top。

 and turns out that we've also seen CSV of the library comes with an object called a dit reader diict reader。

 which actually allow us to take a file and read each row of it as a dictionary。

Before we can get there， we need to open our file first and we've seen two to do that。

 we can use a keyword called with， which takes care of opening and closing our file automatically for us thanks to the magic of Python。

 so I can type with open and then give the name of the file I'm hoping to open， in this case views。

csv。Now views。 csv， I want to open it and you just read data inside of it reading being。

 I don't want to change anything， I just want to see what's inside。

 so I'll say as the second argument to open R which stands for reading mode I'm going to just simply just read whatever is inside of views。

 csv Now I'll go ahead and give a temporary name to the file I' have opened here I'm typing with open views do csv R as file。

 meaning in this case file refers to now the file I have opened views csv for reading。

Now within this block of code that I've opened up with with。

 I can do all kinds of things that while this file is open， one thing I can do， as we said before。

 is use csv。dict reader and pass as input in this case file。

 giving myself a reader I can use to loop over every kind of row that I'll see inside of this views。

csv file。And we've also seen I can type this for row in reader， meaning every row。

 this reader gives back to me， I want to keep looping and looping over it until I have no more rows to loop over。

 and I could make sure everything's working， type print row just like this。So what have I done。

 I've opened up views。csv called it file so long as we're inside of this indented block here。

 lines 8 through 10， I'm looping through every row I receive from this object called a di reader built into the CSV library and I'll print the results as a row。

Let's go ahead and run Python of views。t pi。嗯。😊，Here we actually see。A lot of dictionaries。

 I'll scroll up a little bit here and we'll see our very first dictionary。Id1。

 which makes sense because we have a column called ID English title， the Great Wave of Kanagawa。

Make sense because they have a heading English title。

 and then Japanese title with this text right here。

So it seems like we've gotten back every row in our CSV now as a dictionary。

 and this is likely the most convenient way to read your CSVs， every row is its own dictionary。

 you can access the values at that row using the keys which are the same names that you'll get at the top of your CSV file。

 for instance。So that seems to be going pretty well for us。 let's see what else we could do。 I mean。

 our goal ultimately is to open up these JpeEG files and calculate how bright they are on a scale of zero to1。

So notice how we said the IDs in each of these rows matched to are matched with the file names so here again the great wave has ID1。

 meaning it matches with the JPEG file 1。 JPEG so maybe let's focus on the IDs here as you said。

 every row is a dictionary and I can access the value at a given row by typing in the column name。

 if you will， so here our column name our header was ID I can access one for this particular row and every other row as well。

2，3，4，5 and so on。I'll go ahead and run Pythonofview。

pi and notice how now I'm looping over and getting the IDs from each particular。So。

Then we can use this to calculate the brightness again。

 all calculate brightness needs is a file name， so I could maybe do this。

 I could say brightness equals the result of calling calculate brightness given some particular file name and here what I'll go ahead and type is the file name I'm looking for on each iteration。

😊，I'll begin first with row bracket ID using a Python F string here， So if row ID was1。

 I would have one if row ID was two， I would have two， I'll then type dot JPEG。

 which should complete the file name for me。So now what's happening is calculate brightness is receiving for each row。

 the file name it should look up to calculate the brightness from and storing that result in brightness。

 I'll go ahead and print now the result of brightness and why don't I try running this down below。

 I'll go ahead and type Python of views。 pi。And oops。

 brightness does not seem to be defined Ha ha okay。

 so I should not have done this equals equals we've seen before that means comparing two values。

 setting an equal or testing if they are equal what we want instead is just equal so typo on my part。

 I'll go ahead and now run Python of views do pi and。We'll see a lot of brightness values。

 and so we said before that in this case， we're actually getting brightness on a scale of zero to1。

 so higher numbers mean more brightness， lower numbers mean less brightness or more darkness in this case。

So these are pretty long numbers in terms of decimal places。

 so I could also round them if I wanted to as well。

 I could type round in this case brightness two to round to two decimal places。

 and I we'll get a more friendly output here， I'll see for each file that I've opened and tested brightness for some brightness value for each of those。

But these numbers don't really mean much to me if they're not alongside。

 let's say the file names and the actual painting names too。

 so why don't we go ahead and try to make that happen for us as well？Well。

 what I need to do is not no longer just read in this csv views。csv。

 I might also want to make a csv write some new one that has as part of it， some new column。

 let's say maybe one called brightness， which actually includes the value we've found for each in this case。

 print that we have been thinking about in this collection of prints here。

So I can actually go ahead and open up not just one file， but two at one time using with。

 I can specify that I want to open one for reading right in here， but also one for writing as well。

I'll type comma and then open again， open in this case， maybe a new CSsv called analysis。csv。

 and I'll open this one， of course， in writing mode W here stands for writing。

 and I'll give this one a name we can use inside of this indented block of code that's part of this with block。

So now I actually have two files open at once， one called views。csv in reading mode。

 which we're calling file for now， and one called analysis。

csv in writing mode which we're calling analysis for now， and for consistency。

 why don't I call file here views instead， and I'll update this down below as well。

So with these two files open， what can I do， I can both read from one file and write to the other now to write to a CSV。

 we have a very similar object to di reader， but instead one called diict writer。

 so maybe I'll meant for myself a new object， one called CSv one called writer， which is a CSV。

 diict writer， which can take as input dictionaries and write them each as their own row in my new CSV file。

I'll say that this dictator should be operating on the file we called analysis all the way over here。

 and now I have for myself a new object called writer。But to create this writer。

 I still need more information， notice how in views。csv， we actually have what's called a header。

 some column names， if you will， ID English title， Japanese title。

 we decided to specify the same things for our new CSv called analysis。 CSsv。

 and we do so when we create this diict writer， in fact it has another argument called field names。

 where field names refers to the header names you'll see up top。Well。

 what should field names for analysis be equal to Well they should be equal to of course the same the same column names as before。

 so ID English title Japanese title， and I could type these out just like this or I could make use of the reader itself。

 the reader actually stores those same field names in an attribute called field names。

 so I can type reader dot field names。What we're saying here is that this new file analysis should have the same field names。

 the same header as we see in views。csv， thanks to them being stored in readerer。field names。

 which is created from Dick Reader on this views file here。But now we also want a brightness column。

 a new field name here so I could go ahead and combine various lists this field names is a type of list。

 I can go ahead and add a new value to that list with a syntax here plus some new list I'm going to go ahead and call this brightness brightness so now I have for this new writer on this file analysis I have not just these headers。

 ID English title and Japanese title but also now one called brightness as well。

And just to be sure we're making progress here， I could even go ahead and I could try to write the header turns out this writer object has a method called write called write header just like this and if I were to run this co as is we should hopefully see a new file called analysis。

 csv with those headers in place I'll run Python of views。

 pi and we'll see of course our brightness being printed out thanks to 12 through 14。

 but also we'll see analysis do csv which has。All the same field names as before， the same headers。

 as well as one called brightness。So now we have the basis for our analysis。 CSsv。

 but we still need our rows， so in views。 pi， what can we do。

 we could probably as we loop over the rows in this reader object， maybe also write some rows。

 maybe let's say read in some row， find the brightness for that print and then go ahead and write some new row in our analysis。

 CSsv over here。So let's try this， maybe inside of this loop on line 12。

 I still want to calculate the brightness just like this。

 but rather than printing what I really want to do。

 what I really want to do is write a new row so writer。This CSV。

tator object has a method called right row， allowing me to pass in a dictionary。

 a dictionary that will then be written to this file， in this case analysis。

Now we can specify here the keys which should match， in this case， the headers of our CSV file， ID。

 English title， Japanese title， and brightness， and provide some values that this row should have for each of those columns。

I'll go ahead and type I， which is a key， same thing that we have as a field name as a header here。

 I'll then go ahead and say row bracket Id。 So in this case， the Id。

The value for ID of this new row should match the ID of this row。That makes sense。

 so first one then two we'll have one then two as well in analysis do cv Now really same thing for English title that should be the same as the current rows English title where row here refers to a row from views do CSv so again if we have the great wave we would also see the great wave is the English title in analysis。

 CSv。Same thing here for Japanese title。Japanese title。

 we would have of course the Japanese title from the row。

 and now here comes the actual the change we're making here， if I wanted to include brightness。

 I can do that as well。I can specify a key called brightness， matching in this case。

 this column named brightness， and specify the value that should appear on any given row。

 in this case the brightness we calculated up above。

Let's go ahead and try this out and again here was our full。Our full。Code here。

I'll go ahead and run down below Python ofviews。pi。And we'll see no output， at least in our terminal。

 but now if I look at analysis。csv， well， I'll see the very same data from views。

csv and now this new column called brightness with the brightness value we calculated。

Probably still want to round this though， so I'll go back to views。

 pi and I will round brightness here。Just like this， and then I'll go ahead and run Python of views。

 pi again。If I go back and look， let's see， I'll have those rounded brightness values as well。

NowLet's test visually to see if this is actually correct so we said before that numbers closer to zero were darker and numbers closer to one were brighter now I have here online painting or print ID3 0。

34 which seems like pretty low value compared to other ones let's go check this out I'll go now to3 do JpeEG and we'll see。

Pretty dark print if I go back to analysis。 CSv here， let's find a pretty bright one。

 I think in this case looks like a view of Mount Fuji that one seems pretty bright 0。

75 we look at this one we'll see it is， in fact among the brighter of these as well。

 so just to be clear， we had before three among the darker and now 35 among the brighter。

 so a neat way of analyzing these images by their brightness。



![](img/9137c940096fb5e246eed99e8fe90e73_2.png)

So I'd argue that our code seems to work we're both reading and writing from a CSV。

 but our next step could be to improve the design of our code notice here on 15 through 20 there's a lot of redundancy we said before that we really want the same data from the rows we're reading from to show up in the rows we're writing to so it turns out I actually don't need to make a brand new dictionary。

 I could probably just add on to the row dictionary itself。

AndI'll show you what I mean here if I go now if I go now to just underneath brightness。

 what I could try to do is the following， I could try to not make a whole new dictionary。

 but instead maybe add on a new key to row so recall row here has all the values for IDd English title。

 Japanese title and so on， all we're doing is adding on some new key with some new value just like this one called brightness and if I wanted to in this case write this row。

 I could simply type write writer writer do right row， given the row we're currently reading。

 but now adding in this new key called brightness so much simpler， much fewer lines of code。

I'll then go ahead and run Python ofviews。 pi and we'll see the same results as well。

 of course no longer rounded， so I'll go ahead and go back here and say round this to two decimal places and now I'll run Python ofview。

 pi andvoilah， there is our new CSsv analysis。csv with that same information plus brightness as well。

So this was our brief foray into both reading and writing CSVs thanks to the CSV library and objects like Dick Reader and Dick Ri。

 we'll see you next time。

![](img/9137c940096fb5e246eed99e8fe90e73_4.png)