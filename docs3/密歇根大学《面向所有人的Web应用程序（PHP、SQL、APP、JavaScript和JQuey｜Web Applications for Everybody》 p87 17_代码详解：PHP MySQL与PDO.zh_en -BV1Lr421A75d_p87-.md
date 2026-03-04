# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p87 17_代码详解：PHP MySQL与PDO.zh_en -BV1Lr421A75d_p87-

Hello， everybody。 and welcome to another code walk through on Web applications for everybody。

 The code that we're going to walk through today is the code for。

PDO Now one of the things that'll be interesting is everything we've done up till now you can actually run on web applications for everybody but since this one needs a database and I didn't set the database up for everybody to share on web applications you actually have got to download the PD。

 zip and get it somewhere onto your local hard drive right so I've got actually all the code sitting right here。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_1.png)

And and so I've got all the code here。 so you'll don P do zip and you'll extract it somewhere in your H docs in a way that you can find things。

 And then eventually you'll have this stuff on your local host。 So code P。

 that's all those files so that now I can you know run these things。

 this Aa error check thing checks to see if you got display errors off right so that's nice if you get a different。

 you might want to click on that and just see if it checks your errors。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_3.png)

Always is a good idea。 So one of the things that's important is it's got some notes in here and you got to run some SQL commands。

 And so I'm going make a database here， so I'll do some SQL， go back to these notes。

 create database M，na。Make a thing called Fred and Zap， otherwise the things won't work。

Now I've got a new database， so I go into that MisC database。If I am。On command liner in Linux。

 I might have to say use Mk。 And then I want to create some tables。

 and they're going to have use I D name， email password and make the logical Q B email。 By now。

 you should know your S Q L right。 And so this ought to be completely normal。Boom。

 I don't know what was mad about that。 What was he complaining about when he typed that in。

A comma or closing bracket was expected near key。哦。But it worked。韩尔农。Clear。Now。

 and the last thing I've got to do from the notes is insert a couple of users。Chuck and Glen into it。

 Glen is a real person， by the way。I'm a real person。 So now in database M I've got users' table。

 and if I take a look at that， I got two user accounts。 so there we go。

 Now we can start playing with some PhP。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_5.png)

So。Let's take a look at the very。First bit of code。 So this is important。

So I'm going to put out a pre tagag and then I'm going to call and construct a PO object using the PDO class。

 and there are three parameters to the constructed。

The first parameter is what's called a connection string。

And it tells what kind of database we're going to be connecting to， which is mysQL。

 where it's connected now， most of the time in production。

 you put your database on a different server and it's got an address here。

 localhost just means we're on the same server。 And we are。 And then there's a port。 Now。

 if you are using Xamp on Windows or Linux， you're probably going to choose 3306 here instead of 80889。

 And then you have to have the name of the database。

 And that was the name of the database that I just created the Mi database。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_7.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_8.png)

and then you have to have the account in the password， and I did that in oops。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_10.png)

In these notes， I made the count named Fred， and I named named Pass Zap。

 And you can just do this on your local computer。 It doesn't really。

 There's not a lot of security holes of a database server because you have to be coming from local host or from your。

1，27，0，0，1 is another version of local host。 And so you you can't connect from the outside world into this database unless your computer's been completely compromised。

 And then it just doesn't matter。 So this is， you don't really have to be too secure about this。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_12.png)

Okay， so this creates a connection， it doesn't move any data。

 it just is a way for us to send SQL commands back and forth。And then we can use this returned。

Object and then call the query method and send some S QL。

 So this is the same select star from users that we would type。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_14.png)

Now there we go。 The same S select our users that we would type right there， star from users， say go。

 and it returns these four rows as a record set。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_16.png)

And then what we get back here in Ph P is a statement。

 and then we can use that statement to fetch one row at a time using we call and fetch associative array。

 says we would like each row given to us as a series of key value pairs where the name of the key is。

 Oh'll come back。 The name of the key is the name of the column。

 user I D equals 1 name equals chuck E equals C sub Baard equals 1，23。 And so。

 and this will give us a false row will give us a false， which will stop the Y loop。

 So this is a quick way to loop through all of the rows。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_18.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_19.png)

That are going to be retrieved and print them out with print R with a row now。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_21.png)

If this database doesn't exist or something is wrong， this will cause trouble。

 But now I've got it all set fine。I can say goodbye to that。 And if I run first， it should。Show that。

Now， there's lots of things I could change。 Let me just change something here。

 If I change that to be the wrong password， we'll see what happens here。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_23.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_24.png)

So I run first， and it blows up。 And that's because， and this is why air are turned off。

 because I just。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_26.png)

Bluirted my password to my database。 So I'll fix that。 And it will work。 And so it， so this P D O。

 this will blow up if you don't have these things right。

 And so sometimes making this stuff work when you first start out。

 that is the hardest line to get working。 once you have that working， the S， Q L usually is correct。

 Now， it'll make a different mistake。 if I。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_28.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_29.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_30.png)

Make a mistake with the SQL。 It'll blow up a different way。 It says， oh， you。

 you got some bad SQL there。 so I'll fix that。 We'll talk a little bit more later about how errors work so。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_32.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_33.png)

There we go。

![](img/61c6fbfbca3e8a551df9e832a9bafe67_35.png)

Now。Another way that we do this is we don't necessarily just use printnr。

 And this is a good example of reading data from the database and turning it into a table。

 And we're just using echo statements cleverly to construct all of this data。 So if I go to second。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_37.png)

It looks nice。 And if you just do a view source， you just see that， you know， there's table。

 And then there's the beginning of a table。 and then the data that came from the database。

 the end of a table data， a new one， data that came from the database on and on and on and on。

 And so we just construct， we loop through。 And instead of just dumping it。

 we actually produce some kind of pretty meaningful H T M L。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_39.png)

Now， another thing that we do is we tend not to want in to put this this statement in every line of every file that we're ever going to do because a lot of websites have like hundreds of files。

 and we don't want to put the password and all the database connection information into every single file。

 So we refactor it。 and we use a require statement to pull in another file。

 the rest of this is just a read to read and print all the stuff。 So if I look at third here。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_41.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_42.png)

Oh she comes， but then I look in P。phP and all this does is does a sets up this variable dollar P I could name this anything。

 I just happen to name a dollar P。The class's capital P and dollar P is the variable that I made。

 And I'm setting an error attribute， and I'll talk about this in a bit。 This error mode。

 I'm saying be aggressive with your errorss and blow up and stop rather than continue on， so。

That is this all we did here between first and third。🎼First， we did it here。 And in third。

 we turned that into oops， me select save。 And in third。

 we just did it all in require and put it in a separate thing。 And it's so you don't。

 you don't leak the passwords。 And， you know， that that's just a really general， good pattern。

 So that gets us sort of started talking about how we make a connection to the database and how we send an SQL command and how we loop through the data that we get back。



![](img/61c6fbfbca3e8a551df9e832a9bafe67_44.png)

![](img/61c6fbfbca3e8a551df9e832a9bafe67_45.png)