# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P55：26_文本生成与扫描演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another SQL walkthrough。In this one we're going to go through a bit of the material on how to how to handle text So here we go's there's some things that are kind of cool so sometimes you want to generate a bunch of data because you're going to do some queries you're going to do some explains or explain analyzes and you want to fill up a table with a bunch of stuff and you don't want to type a bunch in so let's take a look at some of the sort of building blocks of doing this。



![](img/8121de047e9f9f2c2e30dfba23e036b5_1.png)

First there's the number random， so if we do select random random。

 random is a number between 0 and1 that's random if you call it more than once you're going to get a different number。

 so if I do this over and over， different number， different number， different number。

 and if you want to sort of get a number between0 and 100， you do a trunk。Of the random times 100。

 so the floating point number is multiplied by 100 away you go。 So that's one thing。

You can also sort of concatenate。

![](img/8121de047e9f9f2c2e30dfba23e036b5_3.png)

On a string together to make long strings if you want。 So if you want to make some gibberish。

 this generate series is really awesome because what it does is it。

 it looks like is's just one thing。 but sort of like every time it hits it。

 it forces the generation of a new row。 So this generate series is like， you know。😊。



![](img/8121de047e9f9f2c2e30dfba23e036b5_5.png)

5 rows with the number one through 5 in it。And then we can concatenate that select and so this is this double vertical bar is a string concatenation。

 This is one field right， except that this is going to generate five rows。

So we take a look at this guy， generates five rows and each row is concatenating the word neon2，1，2。

345 and if you think about this from a Python perspective。

 this is kind of like a list comprehension where it's making a five element list， neon 1， neon 2。

 etc。

![](img/8121de047e9f9f2c2e30dfba23e036b5_7.png)

And so we can fill some things in， right， let's make a little table here called textex fun and we can use this。

So this select neon that generates five rows， but we can also just say insert into text fun。

 instead of saying values we can say select not the key to it is there's got to be a column here and there's got to be the same number of results of that select at the end as there is in the insert column list and we have insert in a text fund content and then a select that comes right after that。

 and I can say then select。

![](img/8121de047e9f9f2c2e30dfba23e036b5_9.png)

Star from。Text fund。Or I can fix my typo because I type too fast。So that's how it works right。

 so again that's inserting multiple rows， the select is sort of driving it。

 but the generate series is what's driving the multiple select。



![](img/8121de047e9f9f2c2e30dfba23e036b5_11.png)

![](img/8121de047e9f9f2c2e30dfba23e036b5_12.png)

So let's throw that little。Bit away。

![](img/8121de047e9f9f2c2e30dfba23e036b5_14.png)

Let's play a little bit with some larger bits of data。Let's make ourselves a。Let's make ourselves。

AT state of another。It's add an index， I' name my index。

 create index on text that's the name of the index。 and this is the the。

Text fund underscore score B is the name of the index， text fund is the name of the table。

 and then content is the column。

![](img/8121de047e9f9f2c2e30dfba23e036b5_16.png)

This shows that you can sort of create an index of your choice after the fact。

 and so this will actually do on a working it's like an al table works on a running system。

NowYou can ask how much data is allocated on disk for the relation itself。

 which is basically the rows， and then how much is in all of the indexes and right now we have 8K。

 but they're empty so we can fill it up。Now， this is another one of those things that's going to generate bunch of rows。

 you'll see that it's concatenating with generate series。1000 through 1005。

 and I'm going this is just case statement。 It's kind of like an if then else。

 except that its it's not like choosing a code path。 It's actually generating one of two strings。

 So random remember every time you hit it gives you another number if it's less than 0。5 i。

e less than 50% of the time。 So case when this is kind of like the if clause then the word then。

 and then this is a string。And then elses， that's a string。 And so what this does。

 this part right here in the parentheses is it either returns one of those two strings 50 per cent of the time and then concatenates that。

 So if I can， if I just do this part right here。And I put a semicolon after it。

It'll give me that one。You'll give me that one。give me lemons。

 So select case when random lesson than 0。5 then so this is returning a string。

 but it's flip flopping based on a random number。 So the case is not exactly an if then else。

 it's sort of a more of a when because it's evaluated over and over and over again each time there is a row。

 But then when we cancatenate that with generate series from 1000 through 1005。

 then we get five rows and the random cat concatetnation lemons neon lemons。

 lemons neon and its driven 5 rows and then generate series。

 So you can think of it as every time that case bit is hit。

 it picks it picks randomly between those two strings and then it does it five times with that number going from 1000 to 10005。

 So we can use this sort of。Mechanism， and we can fill up some data。

We're going to do an insert into text fund， and then we're going to have those rows。

 except now we're going to go and do 100000。 Now， I would say watch out when you're doing this。

Because oh it took a little bit of time because we're going across the network actually that's kind of impressive that there's a database on the far end that can insert those rows and make indexes。

 etca， etc cetera， etc ce。So that's been inserted and so I can ask how big did the relation size and the relation size this number here。

 which is about6 meg， the relation size correlates very directly to the rows the index of size is pretty big it can be bigger than it in this particular case because there because we're only indexing one column and so the index's size is pretty big。

 but you can see how the index grows as we insert data and how the relation grows。

So let's take a look at some string operations， so the part that's the most standard across databases is the like operation and it has a keyword that I mean it has a wild card that is a percent sign so that basically says it's go through here。

🤧。Findint the content that has this number somewhere in it。

 so the percent is like any number of characters followed by any number of characters。

And so that's like anywhere in the string， it happens to find it here at the end。We can ask。

For that material at the， I mean， oops， that didn't come out， right？Oh。

 you can take the upper case of that， sorry， I was missing what the difference was。

 that's the upper case， so that does the upper， you can do a lower case。

 you can grab the rightmost four characters。You can grab the leftmost four characters。

 you can call Stpo。And you can say where within the string am I looking at now this that says find the position in the string where content like。

150，000， so that's going to show us。That it's in position too because it would be in TTP。T TPS。

 colon， where is it。Oh， that's a zero because it's is not HTPS at all， it's actually HTTP。

 so it didn't find it。I take the S off。It'll work just fine， so it shows us in position too。

All right， sometimes it's HtTP and sometimes it's says I should probably fix that。In the future。

 when you're doing this， it'll just work a lot better。Yeahや。

Okay so we got a couple other functions we can play with。

 the split part is like a lot of languages that allow you to do splitting。

You give it a how many pieces you want and which piece you want。

 so that's basically breaking it into pieces。Let's just say select。

It splits it based on slashes and gives us the fourth one， which is12，3，4。

 so it's the fourth one so it gives us lemons so you can use that's just like a split in any normal programming language This programming that translate is kind of weird in that it's going do a one to one mapping the lowercase T is going to map to uppercase T。

 the lowercase H to uppercase H the dot becomes exclamation， etc ceter。

 So this is got five characters and this is just going to transform five characters Why you want to do this。

 who knows you probably not do something nearly as silly as that So we see the HtDpss are all uppercase the slashes are underscores and and so you can kind of see's that's just a tool that you may or may not need to use。

So。🤧嗯。So another kind of wild card， the percents are wild cards that match many characters in this like style。

You can。又不是。There is another wild card which matches a single character and that's an underscore。

 so these are not regular expressions， they're not command line things。

 they're not those kind of things， they are just that's a single character so it's 150 followed by some character followed by two zeros and so that's how we get these things right here。

You can also say you can give a list of things with an in you where content in and then parentthesize list。

So that that。Okay， is that because we don't。Ss。I'm sure I mismatched my S's and P's and the neoons。

 et cetera， I got my essays backwards， but then I'll fix that later。I think this should be S。😔。

You can find it where it matches。And still didn't find it。

 That's because the random numbers didn't didn't work out in my favor this time。 So so there you go。

 now when we're all done with this， let's just drop that table and so we don't fill our server up okay。



![](img/8121de047e9f9f2c2e30dfba23e036b5_18.png)