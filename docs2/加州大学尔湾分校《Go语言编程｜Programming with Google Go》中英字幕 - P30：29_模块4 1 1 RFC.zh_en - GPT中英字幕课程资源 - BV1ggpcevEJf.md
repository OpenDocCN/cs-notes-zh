# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P30：29_模块4 1 1 RFC.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/1f8725a497a1ac48b8048201edcce966_1.png)

🎼う。🎼Yeah。So an RRC is a request for comments， that's technically what it means。

 but what it really is is a definition of a protocol or a format， a standard definition。Now。

 reason why we're concerned with these， they're not part of goal lay directly。

 But whenever you write a big program， you will to do something。

 you're going to want to interact with other systems， other blocks of data somehow。 I mean。

 it is extremely common。 So， for instance， maybe you want your program to。Read files。

 read database files and process them。 right So these database files。

 they maybe they came from some other source， you know， some data。

 maybe somebody inserted them on the web added to MysQql database and you want to be able to read those files。

 right， So there's got to be some format that everybody agrees on that you can communicate through。

 So， you know， this is going to be in this particular format and your code can process that format。

 Sam thing goes for。😊，Maybe it's a network protocol right， So maybe your your machine。

 maybe you want to do a client server thing right， so you want you want to make a web client。

And your web client needs to talk to a server over the network。 and in order to talk to a server。

 it's got to send messages in with that adhered or particular protocol so the server understands what it's getting and then on the other end。

 on the receiving end your machine， your program has to be able to understand the format。

 the protocol of the message that it receives in return So whenever you make some kind of a bigger system and it needs to interact with other systems through data transfer。

This data has to be formatted in a way that everybody understands it， say so。

There are many of these formats and protocols that are well defined and are standardized and used for communication and trading data between different systems。

 There are many， many of them， and RFCs are are the name that are used for for a lot of these standards。

 Now they are non RSC based standards， but RCs are a sort of a broad swath of standards。

 So for instance， let's give you some examples。 Take HTMLml。 Hypertexts markup language。

 Hml is the language in which web pages are written。So。😊。

It's a standardized language actually it's RFC。 I got the RC number right there on the slide and it's a standardized language so that all clients。

 all web browsers， they have to understand this language so they know how to render it on the screen and so on。

 So that's one of those languages。 It' a standardized and you can trade data between a client and a server between a web client web server using this standard。

Also URs right these are also it's an RFC2 URI stands for uniform resource identifier it's basically the addressing method used on the web right so you've heard of a URL that type of URL so there's a particular format in the way that it's supposed to see and that it's got to adhere to a particular format so that every client。

 every server can interpret the address。ACtP。That's a network protocol web network protocol defines the web hypertext transfer protocol。

 and that's RFC 2616。 and that describes how the messages should be transferred on the network。

 So what information should be included in each message and what the headers are where the data should be。

 the content and so on the length， stuff like this that's all defined so that a client can talk to a server。

 web browser can talk to a web server， something like that。

 So these are just a few of the protocols of these standard protocols。

 that are defined by RFcs and they are a lot more and these protocols can be arbitrarily complicated。

 some of them some of them as simple， some of them are complicated and so what happens in Going and language like Goang。

 they provide packages that help you to process these formats， a lot of these not all but a lot。

So there are packages for most of the important RSCs。

 there are packages already built that you can incorporate， you can import into your program。😡。

So and these packages， they provide a set of functions that you use to encode data into into whatever the protocol is。

 the format is and also to decode right so if you're receiving something in a particular format from some other source。

 you need to decode that information into structures or maybe structures or maps or some kind of goal lay objects and encoding is the other direction where you take some kind of go objects and you convert them into this common protocol or format。

So as an example， there's a net slash HTP。That' that's for HTTP high protectects transfer protocol and you have that package and it provides a bunch of functions in there that I allow you to make to make messages and send them。

 So for instance， I've got this example， Http。 get that makes a get message you pass it as an argument a web domain and it will make a request to that domain for a web page and it'll return the actual content of the web page for you So there are a set of functions like that defined in this package that allow you to to communicate over the web and send send so if you want to make a web client or web browser web server or something like that you would use a package like this。

Another package， a more basic one is the net package， and this is for TCPI and socket programming。

This is sort of a long description， but TCPI basically define the Internet。 So internet。

 you can do webbased communication on the Internet。

 but you can do all kinds of communication protocols over on the Internet。

 FTP secure shell a whole list， but all of them share in common。

 this basic TCP IP UDP stack the set of protocols they all have to adhere to。

 And so the net package gives you a set of functions that allow you to。

To use that protocol So for instance， this example here。

 net dial TCp says look I want to make a tCp connection and you give it the domain UCci。

ed called an 80 tells you the port number you pass that and it establishes a communication a connection internet connection TCP connection specifically with UCcidu on that particular port which have to be web port but so there are a lot of these packages that are used to support to make it easy for you as a programmer to use these different protocols。

 communication protocols and data formats that are commonly used by different systems and it's just a very useful thing to have these packages and to use them because when you don't have them you have to do it from scratch meaning you have to for parents to take Http if I didn't have the Http package I would have to understand everything about Http and make the packages on my own I have to basically make the message format and my own I have to write my。

to do that Now this is not impossible， but it is time consuming。 Why do that when you can call http。

ge It makes it a lot easier for you as a program。So JON is one of these protocols。

It's not a protocol。 It's a data format， commonly， commonly used data format across the world。

 And we're going to talk about that and the package associated with it。

 So Json stands for jascript to Object notation。 We are not programming in jascript。

 but Json is bigger than Javascript。 Now， JO is， is's just widely accepted as a common way to represent structured data。

 It's R C 71，59。It's a format to capture structured data and by structured data。

 I mean a set of attribute value pairs。This is a natural a natural for a struct or a map。

 right because if you rememberstructs， they have keys， they have not keys。 they don't call them keys。

 They have fields and values of the fields， right， so a field value pair could be an attribute value pair in JSson。

 or a map has key value pairs， right， that's the same that can easily be an attribute value pair。

 So these attribute value pairs in JSson sort of naturally map naturally。

 and I shouldn't use the word map。 they naturally correlate tostructs and maps inside inside golan。😊。

And now the keys and values， or rather attributes and values， as they're called in JSO。

 they can be basic value types， so you can take boolean numbers， strings， arrays， objects。

 and they can be combined。Herarchically， so it's easier if we see some examples of this。

So let's take an example of a start off with a ghost structure， a ghoststruct。

 the person structure that we had before right so this person structure， I'm making P1。

 I'm saying P1s a person with a name of Joe， a address of A Street and a phone number 1，2，3。

So that that that information， maybe we if say we want to transfer it to another machine somewhere else。

 okay， we want to give it to somebody， so we want to take it from you know right now we have it represented as a structure and go。

 we want to represent in this common JSON format so that somebody else， some other program。

 some other system somewhere can interpret that。😡，So what we're showing below is the equivalent JSON object。

 so up above you see the struct as we would define it in go and in JSON what it would look like as a JSON object is shown right there。

😡，noticeice this is very similar to the structure to what astruct looks like or what a map looks like。

 It's basically name Col Joe address Col a street Ph， colon 11，2，3。

 Now one thing to note is that the name the field names， the attribute names， name。

 address phone they're in quotes which they weren't when we define the go structure。

 we didn't put them in quotes。 So it's a little bit of a difference。

 but notice that it looks very similar to the struct right So that JSsonN object。

 we can take that and pass that on to some other machine， some of the program。

 and if they can interpret JSson， then they can extract all the information that we were using in our program about this person。

 And this is of course， one person， but I could have a database full of people。

 and I could just make a set of JSsonN objects past somebody and they could read this database full of people。

 So this is just a sort of a simple example of Json。

 but JSsonN's actually nice and it's a good format is well accepted。



![](img/1f8725a497a1ac48b8048201edcce966_3.png)