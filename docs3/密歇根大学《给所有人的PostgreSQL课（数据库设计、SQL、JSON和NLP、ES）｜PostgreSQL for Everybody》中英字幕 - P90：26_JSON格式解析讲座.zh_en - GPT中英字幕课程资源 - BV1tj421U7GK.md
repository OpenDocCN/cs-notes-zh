# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P90：26_JSON格式解析讲座.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Welcome to our lecture on JSON Eventually we're going to talk about Postgres。

 but for now I want to talk a little bit about JSON give you a bit of historical context the URL for these lecture notes is Https called www。

pgfree。com/lects/06Json。So one of the things that JSON is very much about is data serialization。

Da serialization is a problem when we are transferring data structures between programs in different languages or just programs in the same language running across a network exchanging data and so the two most common data structures that we use inside of programming are linear structures and key value structures and in Python we think of those as a list as a linear structure just 01。

2，3 and then the dictionary is the key value structure。

 but if you look at languages like JavaScript or PhP or Java。

 they all have these and while we have more sophisticated data structures they kind of all fall into in general you can kind of model them as either key value pairs or as linear list。

 the only other data structure is actually a tree of information and we'll talk about that in a second。

But the problem is and what the word serialization means is if you have a dictionary in Python and you need to send that to PP or to JavaScript where it needs to be an object in JavaScript。

 you need a format that both Python and the JavaScript can agree on as the interchange format we call it serialization because it was what was sent across the wire back when we had networks that were made of wires and so it was a serial set of bytes of set of characters that were sent across a wire。

 and if you cut it in the middle and you watched went back and forth what went back and forth between the two systems。

 you'd say that's our wire protocol and it goes by serially and you say， well。

 okay we're sending a dictionary to an object but what's going across the wire so the serialization format。

And another word for this is marshalling and unmarshalling so you marshal the data to prepare to send it and then you unmarshahal it when you receive it they're basically identical terms now in the early days so from sort of 1990 like the 1990s when HTML came out and so in the early days we looked at this less than greater than HTML format and we're like we can use this to represent data so we come we came up the world came up with a thing called XM which stands for extensible markup language and it's basically a tree of tags like array and slash array and then now we have some entries and I array they don't mean anything special。

You just put stuff in， but know we were using this format to serialize or to marshal and unmarshahal data between systems。

 you also would tend to serialize it when you put it in a database or wrote it to a file and then read it back from the file you tend to serialize it so you could think of as you're editing in Microsoft Word for example。

 Microsoft Word is like you're moving stuff and it's updating its internal structure but then it had to serialize that data into a doc X file。

 and in that case we use XML so XML was the format of choice for serialization and when we used it a lot there was all kinds of libraries。

Frameworks and strategies for XML that were very， very， very popular。嗯。

But then what happened is as we move from sort of servers talking to servers on networks and then instead we started having servers in the backend talking to browsers and browsers talking JavaScript originallyigin we just had request response cycles where you would go to a page it would paint and then you'd click on an HF an anchor tag and you would go to a next page but as we wanted to add more interactivity we would write more of our application coded JavaScript and sometimes we would talk to the server。

 pull data back and then update the document object model without actually refresher in the whole page that's how things like Facebook has a little red thing with the number of messages that is either update or show up when something happens it's not changing the whole page it's just changing a little corner of the page。

And this pattern， when it first came out， well， we still call it AjaX， the pattern was basically。

 let's take XML and have the JavaScript in the browser read the XML from a server。

 now that server often didn't have it an XML， it just took whatever dictionary or list or whatever it had。

 and it would turn it into an XML and then in the browser。

 you'd take the XML and turn it back from the XML into an array or list or whatever it was。

And that was how we started。The problem was， is that XML。Is a hierarchy。

 it's a tree and it's really good at representing things with trees and it's a bit self- documentcumenting because you can choose the names of the tags in Xm。

 not like HTML but in Xm you choose the names of the tags so people can look at the Xm and go I kind of have a guess as to what that is although lots XML is hard to read this particular one says I'm an array and I got an entry and each entry has a key of value I kind of know what that means this kind of looks like an array of dictionaries or an array of objects or a list of dictionaries or an array of objects。

嗯。But the problem is in general it was。Complex to go through that and reconstruct the arrays when you actually just wanted to send an array or send a list or send a dictionary or send an object。

And so Douglas Crockford， and I really encourage you to watch this video interview that I did of Douglas Clckford in Yahoo a number of years ago。

 Douglas Crockford said， you know what， there is this format that we use to specify object and array constants in JavaScript。

 why don't we just use that as the serialization format？

So that's why it's called JavaScript objectject notation。

It should really be JavaScript object and array notation， but that would make it JON。

 but it's not JSON， JSON。And so the idea was is that you have this way in JavaScript of just saying。

 you know， and in Python， we you do the same thing， we can say x equals curly brace， blah。

 colon and blah， and you can make yourself a dictionary。

And so this is like making an object in JavaScript。

 which is the same as making a dictionary and Python。

 and they can be nested so you can have an object that has a key that the value of which is a list。

Or whatever and so Douglas Crockford said let's just use this as our serialization format， it's nice。

 it'd be nice to pretend that in 2000 Python was part of the reason he picked it。

 he picked it because it was JavaScript。And it just so happens that Python looks pretty much identical to it。

JaSON is a little more restrictive than either dictionaries or JavaScript code JavaScript is actually looser。

 so what he did was he basically came up with a subset of the JavaScript syntax。

 the constant syntax format that was a little easier for serialization decserialization because he really knew that we were all going to have to build a bunch of libraries and then those libraries for Java and for PhHP。

 JavaScript kind of already existed although by now we've actually built libraries instead of just like executing JavaScript which was kind of dangerous。

The earliest parsers where you just ran the code， which is a little scary actually。

Now we actually parse it so that he knew that we were going to build all these backend languages like PhP and Java and ASP。

 and we had to teach them JON made really cool JSON Library so in Python you just say import JSON and then poof your serialization。

 your low S and dump S and doing serialization and decserialization and it's awesome。

But he basically said we better not make it as flexible as JavaScript because JavaScript allowed constants and variables and all kinds of substitution and so it was just like look it's got to all be strings。

 et cetera， et cea， et cetera so we put up a website called wwgun。

org it's kind of fun to look at it's crude it's simple but it's precise and it was a way that allowed people to carefully develop。

 it's very well thought out everything Douglockcckford does is really smart。

And so it allowed people to start building libraries and testing those libraries。

 and if one library like the PhP library in the Java Library disagreed with one another。

 then you could at least go to JO。org and so it really kind of brought some order to this general notion of using JavaScript constantss as a serialization format。

And like I said， it。We can't claim that Python was too particularly influential。

 but it's really nice that Python and JavaScript are the two languages that are probably the most going to be the widely known languages and they look the same in JSO looks like Python it looks like JavaScript and it looks like JO。

 so that's kind of nice。So ultimately JSON became very dominant。

 later things like JavaScript in the server with node JS made it so that JSON was even more natural there and then databases that are based on JSON started to emerge like MongoDB so if you had a JavaScript in the client then node in the server and then a MongoDB in the back end。

 you were basically doing JavaScript everywhere and JSON everywhere and it's really really pretty。

It turns out that it's still difficult to write applications in that environment。

 but it was nice because you were using one language and one serialization format from the database on back and so we'll talk a little bit about this。

 the emergence of these no SQL databases， which was really a code word for all intents and purposes for JSON databases for many situations。

 but then what happens is that，As these NoSQL databases became popular things like Postgres。

 MySQL and other databases are like， you know， we could just add a JSON column and kind of do what you fancy brand new databases that are nowhere near as mature as us and so in an upcoming discussion we will talk about some of the what's going on between the NoSQL and the SQL movement and how you can somewhat get the best of both worlds in a current generation relational database like Postgress。

🎼The。