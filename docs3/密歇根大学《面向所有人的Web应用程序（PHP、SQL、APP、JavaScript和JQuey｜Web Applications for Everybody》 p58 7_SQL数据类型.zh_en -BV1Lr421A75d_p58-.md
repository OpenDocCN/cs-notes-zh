# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p58 7_SQL数据类型.zh_en -BV1Lr421A75d_p58-

![](img/c4d9613186cba7acf7f9848901a217c4_0.png)

![](img/c4d9613186cba7acf7f9848901a217c4_1.png)

So now we're going to talk about different kinds of ways that we can describe the columns that make up our table。

 so were in a table and we're working on columns， difference kind of text fields， binary data fields。

 numeric fields， auto increment fields and other kinds of fields。

So the first two columns I made of name and email were of T varchar。

 which is probably one of the most common fields are character fields char and varchar are character fields。

 they are aware of character sets， which meaning they can be Latin character sets or Asian character sets or Russian or Persian or whatever。

 a lot of what you're doing to the database servers you're giving a clue that says， look。



![](img/c4d9613186cba7acf7f9848901a217c4_3.png)

This might be 512 characters long， but it might also be 4。

 So come up with a way to store things that will be efficient。

 both for four character strings and 512 character strings。 If you not， if you don't say varr。

 if you say char， what you're saying is。This is 20 characters。 And pretty much all the time。

 it's mostly going to be 20 characters， which means if it's only 5。

 it might not be efficiently stored， but it'll be very efficiently stored for things that are 20 characters。

 So if it's somewhere between 5 and 500， you want to use a v cha。 And if it's pretty much always 20。

 Now， the lengths that you give to these things are absolute maximum。 That's not like it compromises。

 like in the previous example， we did 128。 And that's it。 that's a contract。 You're basically saying。

 please enforce upon me。 The rule that these are no more than 128 characters。



![](img/c4d9613186cba7acf7f9848901a217c4_5.png)

And so there are some text fields that the key to the text fields is that they're not indexable in the same way。

 sorting like the order by doesn't work so well with them。

 But if you were like putting in a blog post or a comment in Facebook。

 you'd probably put one of these things in。 They all have a maximum length。

The text field is up to 65000 characters because it might be a small blog post or medium text or。

 long text。 You can have 4 gig of text of characters。 Now。

 because this is a character set aware field， they're real characters。

 And so 65000 Latin characters is the same as 65000 Asian characters。

 and it's capable of handling all that。 So text， the text field in the varchar field understand characters sets。

Now。The types that are very rarely used are byte types。 And so in the Latin character set using ASI。

 a character is 8 bits。 That's just how big it is。 And so if all you're doing is Latin。

 one character is 8 bits。 whereas if you're doing other uniccode things characters can be up to 32 Bs。

 whereas a byte is exactly 8。 And so you can say you can tell。

If it's binary data and you know really that it's only up through values from 0 through 255 characters。

 you can say， hey， I'd like a binary stuff like a byte field or a variable length binary field up to that many bytes。

It's not really commonly used， you don't want to index， you don't want to sortsort it。

 it's sort of not aware， it's very unaware of its content， but sometimes you're putting stuff in。

 you're pulling something off， perhaps a sensor or something and you're putting it in and it's just a bunch of zeros and ones。

 that's what this is used for。You can also store things like images or PDFs or videos in databases。

 It turns out that databases are pretty good at this。 And these are called blobs。

 binary large objects and they also have various lengths depending on whether tiny regular medium or long。

 So it turns out the databases are really good at storing the stuff。

 but the problem you run into is that it starts to slow your database back up down quite a bit after a while。

 And so what you find is that if you're doing mediumsd things like maybe a picture here and there or profile photo or something。

 we tend to put that in the database because then it's kind of with all the rest of the database about you。

 But if we're doing things like videos or large documents。

 we tend to find some other way to store them inside the computer usually just as a file somewhere。

 and then we serve them up。 But it's not bad to store binary objects like this in a database except when it comes to getting your backup getting too large。



![](img/c4d9613186cba7acf7f9848901a217c4_7.png)

![](img/c4d9613186cba7acf7f9848901a217c4_8.png)

Integers， there's a different sizes of integers。 And you say why。 And the answer is， well。

 we're going to have millions of these things。 And so if your integer is only really， you know。

 a number somewhere between 1 and 15， we don't need to store the same amount of space as if it's a 2 billion number。

 right。And so we have tiny integers， small integers， normal integers。 that's 0 through 2 billion。

 like int is a 32 B integer。 If you're sort of nerdy like that。

 and then there's even larger big integers that you can store。

 that take up more space integers are nice， especially the int integer， the ones0 through 2 billion。

 They sort really fast。 They take up not that much storage， They're easy to compare。

 They're easy to sort。 They're used for indexes， and so we tend to use integers and a lot of things。

 and we tend to prefer them over strings as we will soon see representing information floatinglo point numbers。

Floating point numbers work like all programming languages if you've been using things like 98。

6 or you know blah， blah bla 。14 or something 6。02 times 10 to the whatever you've been using floating points inside computers all along the key thing about floating point numbers like you 1。

7 they're not perfectly represented and because they're not really real numbers they floating point numbers but they're approximations so the way to think about floating point numbers float is the small one。

 it's a 32 bit floating point number has a range of up to 10 to 38th power。

 but the key is is no matter how big or small it is there's only seven digits of accuracy and so for things like temperatures or speed or things like that we tend to find floating point numbers are perfectly good because can you really measure speed to more than seven digits of accuracy if you can do better than that then you go up to 14 digits of accuracy but after a while。

You're like， okay， 14 digit of a probably enough， you just have to understand that you don't want to store money in a floating point because you know $10。

25 is not perfectly represented and so you get inaccur。

 so you actually use scaled integers to store money， it turns out。

 but for scientific calculations and you put so plenty of scientific data into databases。

 floats and doubles are great。

![](img/c4d9613186cba7acf7f9848901a217c4_10.png)

There's a number of different times， time and date formats。



![](img/c4d9613186cba7acf7f9848901a217c4_12.png)

There's a thing called the timestamp and the timestamp is the number of seconds since 1970 and it's stored in a 32 bit number and it's really efficient and easy to sort because it's really an integer。

But it has a couple of problems， it can only handle seconds， it can't go below a second。

 and it has an absolute sort of length。

![](img/c4d9613186cba7acf7f9848901a217c4_14.png)

Be that this timetamp idea was invented in 1970 something， they said oh。

 it's the number seconds in 1970， January something 1970。

 which means that we have kind of a Y2K problem in Uni systems and in database systems in 2037 because that's when the 2 billionth2 after 19 January of 1970 happens。

 but until then they're fine and then we'll just make it a 64 bit number and then we'll have you know until the sun dies or something like that and so we don't have to worry about that too much。



![](img/c4d9613186cba7acf7f9848901a217c4_16.png)

So a data item that is only per second， like when a record was updated or created。

 we tend to use timestamp for all that Date time is more general， takes up a little bit more space。

 and it can really represent any year like the year 1300。

 you can still represent because you can't put 1300 in a timetamp because it's before 1970。

 So date time takes up a little more space， but literally any number that you can represent in this format。

 and it's beyond  Tony 37 and it'll be fine And the same is true for a date。

 which is just any set of year month days that fit in a time that is hours， minutes and seconds。

 And there is a built in function in my Sql that tells you the current date。

 So you'd be like insert created at。Falue now。 So now as a way to say what time is it now as as understood by the database server。



![](img/c4d9613186cba7acf7f9848901a217c4_18.png)

So up next， I'm going to talk to you a little bit about how to give even more detail。

 not just about what kind of data is in each column。

 but something about how you intend to use that data in each column。



![](img/c4d9613186cba7acf7f9848901a217c4_20.png)