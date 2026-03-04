# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P82：18_loadbook.py脚本演示.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Hello and welcome to another code walkthrough in Postgres for。Postgre class。

 so we're going to go through now the loading of the text of a book and we're going to be using Python and we're going to be using a bit of code called loadbook。

 PY that I wrote。 So so the first thing we're going to do is we're going to grab ourselves a book。

Using Wget from guttenberg。org， we're going to grab p19337。txt。And I'm just going to download that。

L money sell if we take a look at this Pg。And the funny thing is it's PG is for Postgress。

 but PG19337 actually stands for Project Gutenberg。 And so this is Christmas Carol Thomas Dickens。

 So what we're going to do is we're going to write some code that's going to grab out the paragraphs and then merge all these paragraphs into one line and insert those paragraphs into database so that we can add a full text index to it。

 So we're it's going have some definitions about what a paragraph is， et cea， et ceter。

 one of the things we're going to do is because we're using Ts vector we are not going to worry about punctuation because actually Ts vector knows all about that。

 So that's a local file with 186809 characters So then we're going to grab this loadbook py Wgit using Wgit loadbook py。

'll pull that one down。

![](img/a78c8161079c1752d6d2d212b802d3df_1.png)

![](img/a78c8161079c1752d6d2d212b802d3df_2.png)

![](img/a78c8161079c1752d6d2d212b802d3df_3.png)

![](img/a78c8161079c1752d6d2d212b802d3df_4.png)

And then this one uses a bit library code called myuttails。pyy， so we'll wget pgfree。

com/code/myutils。pyy so I have all that downloaded now it always is going to remind you that you got to fix hidden。

pyy but you don't have to fix hidden。pyy if you just finished the previous example so you don' have to keep editing hidden。

pyy。Then we're going to run it， but let's take a look at the code first and you'll see how this works。



![](img/a78c8161079c1752d6d2d212b802d3df_6.png)

So loadbook。py。So here's loadbook。py and it's kind to telling us how to do all this stuff， blah。

 blah， blah。So we import the hidden stuff when we're going to use the time and we're going to ask for a book file。

 then we're going to split it and take off the TXT because we're going to automatically name the table。

 the book file minus the suffix。We're going to make sure we can open the text file。

Before we bother even opening the database connection。

 then we load the secrets and make the database connection just like we did in the previous assignment。

 and then we grab ourselves a cursor。

![](img/a78c8161079c1752d6d2d212b802d3df_8.png)

![](img/a78c8161079c1752d6d2d212b802d3df_9.png)

So our cursor is effectively the same as our client， our PG SQL client。

 it's the we just almost do exactly the same thing。 So now that we have a cursor。

I'm going to drop the table， I'm going to use the name of the book as the table。

 and then I'm going to create the table with a serial in a body of text right， just two columns。

 one is a big text， and so I do that。Now this year's a bit of Python。

 we're all supposed to know Python already， got some counters。

 I'm doing things like throwing away blank lines， I'm one of the things I'm doing。

 I guess I can open another。

![](img/a78c8161079c1752d6d2d212b802d3df_11.png)

PG。One of the things I'm doing is I'm taking multiple lines。

Until I find a blank line and I'm kind of concate maybe them together and moving the new line。

 so it's like one big long line。

![](img/a78c8161079c1752d6d2d212b802d3df_13.png)

Right like this I'm joining them all together one big long line just did that in my text editor to show you what I'm doing and and so one of the things I'm doing is I'm looking do I see a blank line if I'm in the middle of blank lines I throw them away if I'm in non-b lines I cancatenate to the and if I find myself on a blank line and I've got a the para is my variable for accumulating the paragraph。

If I've hit a blank line， then I take insert， then I insert the paragraph right so I insert it into the table name with a body and a substitution parameter percent S base body values percent S。

 and I cur out execute the thing when you run that SQL and pass in a one tuple and the weird format parenthesesis para comma parenthesesis。

 which is the weird format for a one tuple。

![](img/a78c8161079c1752d6d2d212b802d3df_15.png)

![](img/a78c8161079c1752d6d2d212b802d3df_16.png)

And I'm counting how many times I found a paragraph。

 so here's where I'm going to do a connection do commit。 Now if you made this connection。

 commit every time through you'd actually run a lot slower because you'd retrieve something。

 read something and then every insert would be a commit。

 so I'm going to make it so every 50th record， I commit。And then every 1 hundred0th record。

 I'm going to tell how many was loaded。 and then I'm going to sleep。

 And the reason I'm going to sleep is to allow I put this in a lot so I can blow it up so I hit control C in this particular situation。

 And that just as it gives me a chance to slow it down if it， If I've got a runaway train。

 And so if then this part here is accumulating。 the strip is taking out the new lines and throwing away white space at the beginning and end。

 And then I concatenated， this is what's concatenating pair equals pair of plus space quos line plus line。

 that's what's actually concatenating all the lines together to give me one very long text string。

 And then when the loop is all completely done。😊。

![](img/a78c8161079c1752d6d2d212b802d3df_18.png)

Then I commit the connection and I close。

![](img/a78c8161079c1752d6d2d212b802d3df_20.png)

The cursor。

![](img/a78c8161079c1752d6d2d212b802d3df_22.png)

And then I pronoce some loaded messages and tell me what to create the G index。

 which I've got here also in my SQL so that's the basic idea。



![](img/a78c8161079c1752d6d2d212b802d3df_24.png)

![](img/a78c8161079c1752d6d2d212b802d3df_25.png)

You can look at it as much as you want。So let's get out of here。And just say Python 3。Load book。keyy。

Now， if I hit enter， it's just going to assume that PG 19337。Txt， which is the one I want to do。

So now as you're going， and so I can go over here and I can say Dt and I can say select。Count。Star。

From P D。😀哈哈哈哈哈哈。😊，Select， I can't。 I wanted to catch it while it was running。It got 700。It's at 800。

 Okay， I did catch it while it was running。 If you come back over here， you see it was 0 loaded。

200 loaded，700 loaded。 and it was pausing， and it was committing。

 and you'll notice that the numbers that you see here are all even multiples of 50。

 I didn't catch it at 50。 It does wait every hundred0， but it does commit every 50。

 So that's why you're not going to see like 1 hundred43。

 because it's not going to commit until record 1，50。 And that's。



![](img/a78c8161079c1752d6d2d212b802d3df_27.png)

![](img/a78c8161079c1752d6d2d212b802d3df_28.png)

![](img/a78c8161079c1752d6d2d212b802d3df_29.png)

![](img/a78c8161079c1752d6d2d212b802d3df_30.png)

![](img/a78c8161079c1752d6d2d212b802d3df_31.png)

this is a bit of code right there， every 50th record it actually commits。

 which means inserts come to the database in like blocks of 50。

 this greatly improves the database's performance。

![](img/a78c8161079c1752d6d2d212b802d3df_33.png)

![](img/a78c8161079c1752d6d2d212b802d3df_34.png)

And then amount of network traffic that goes back and forth。Okay。

 so at this point it's loaded 814 paragraphs if I do that select count。

 you see that there's 814 rows， so let's take a look a bit。



![](img/a78c8161079c1752d6d2d212b802d3df_36.png)

If I say select。Star from。PG。1，9，3，3，7， limit 1。It'll be kind of long Oh， that was my first。

Let's do limit five。

![](img/a78c8161079c1752d6d2d212b802d3df_38.png)

Yeah， you see。You see how these。Paragraphs are getting kind of long。



![](img/a78c8161079c1752d6d2d212b802d3df_40.png)

Let's go limit 10， see if I get to a really long one limit， nope。Limit。



![](img/a78c8161079c1752d6d2d212b802d3df_42.png)

22 okay， some of them get kind of long。 So that that's one paragraph， one paragraph。

 And it was my Python code that built all that stuff。 Now。

 if you think about this as an inverted index， you got a， if you just broke this on spaces。

 Christmas comma would be something right， double quote， who would be something。Kindness dot。

IfThat was just a pure inverted index based on words as defined by spaces， that would be a problem。

The good news is。Is that Postgre knows everything there is to know。To know about this。

 And we are simply going to say， let's make an index。都。Using2TS vector of the body。

 using the English language。And so that knows everything what punctuation is in English it knows。

 you know， it is kindness and kind map to the same stem， I all that magical stuff is happening。Okay。

 and so now。Let's just see what we're going to do。So select where the TS query。

 we're going to look to see if。Goose is somewhere in the body， right？And so， there goes。Limit5。

Let me add the ID from that so you see it a little bit better so we can see which paragraph it was。

select id body。I de a body from PG19337 where 2 TS query English goose。

 double at sign2 TS vector English body limit 5， so here we go， So you see in paragraph 412 415 428。

 429， and somehow there is a goose everywhere， It know we could find it right。So there we go。

So it's there now let's check and see if the explain works。

 sometimes this explain takes a while for the gin to catch up。But now it's done。 And so again。

 whenever you're doing and explained， it looks really complex and all this stuff is useful to somebody somewhere。

 I'm guessing。You just don't want to see sequential scan。

 your sequential scan is what slows you down。Kind of like an order of algorithms。

 if you see order n squared， it slows you down， but we got a bitmap heap scan。

 it says that it's using PG 19337 underscore squared gin， which is exactly what we expected。Okay。

We can in this one， see the thing where we do a 2TS query of tiny followed by tiny TimM。

 the less than dash greater than means followed， and so now we can ask for that。Tiny followed by Tim。

And there's 21 bodies where the word tiny comes word Tim comes after tiny。

 it doesn't have to be exactly right after it at that point。And we can do an explain on that。

To make sure that that uses。That query， that's a pretty complex thing because that's tiny somewhere after it。

 that is Tim。 And so can that use the。Oops。Didn't copy it。I need to say。

 I need to copy the explain one。O。Okay， explain analyze with the TS query of Ti followed by Tim。

But you'll also notice something here that this tiny is been stemmed right so it's not TINY。

 it's TINI。So that's cool。Okay， so that kind of gets us through the effort of just kind of loading a book in。

 using Python to concatenate all the lines of a paragraph into one big long line。

 making a real simple vector and then being able to do efficient searches on all that stuff。

 so I hope this walkthrough was useful to you， cheers。

