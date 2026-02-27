# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p21 -21-MIT web.lab (6.962) - Day 5_ Databases.zh_en -BV12Ux5zTE9p_p21-

Okay， hi， everyone。 Hope we all had a very productive morning debugging catbook。

 I saw a lot of really good thinking going on。 Anyways， today。

 we're gonna be talking about databases。 I'm Annabelle and。😊。



![](img/edb38c130361ed335351fa952a6e528e_1.png)

I'm Sophie。 Yeah， so let's start with a quick introduction to what databases are。

So currently the way that we are storing data in catbook is that when a client sends a request and they ping like the API slash storyory endpoint。

 for example， like trying to write a new story， this is sent to the server and all our data is stored directly on an array called storiesies in our server So this is going to add a new story directly on our server So here's like the code in API。

 Js right now right we have like this data object that has the array of all of our stories with fields like ID creator name and content。

😊。

![](img/edb38c130361ed335351fa952a6e528e_3.png)

But there's a couple of issues with storing data in our server just as a variable。

 and you might have already encountered some of them or have already like an idea of what some of the issues might be。

So let's say everything is fine and we're all good， right， we're posting stories on our capbook。

 You guys are like busy debugging or whatever the clients are sending are payinging the API slash story endpoint。

😊，And then our stories object is being updated accordingly right， so we're adding the high hello。

 but let's say， oh， no， our server crashes。😊，So our server is down for some number of unbearable hours。

 and let's see what happens if once our server comes back up。

All of our data is going to be lost inside the stories array。

 So everything that was just sent is now gone。 And obviously， we don't want this， right。

 Like we don't want all of our data to just be gone if the server crashes and it's not just if the server crashes。

 if we close our terminal or if like your laptop runs out of battery。

 then all of your data will be gone and all the stories that you just posted are not going to persist on catbook and you can imagine that with any web application。

 you want your data to persist and you want to be able to retrieve and display the data that your users have previously submitted even if something crashes。

😊。

![](img/edb38c130361ed335351fa952a6e528e_5.png)

The other thing that happens is， let's say our server never cachees。

 and it's some like super powerful like mega server。 But catbook has a lot of users， right。

 like all of you guys are already using it in class right now。

 And this is going to lead to a lot of Ram issues because that's gonna be a lot of memory。

 And we're starting like hundreds of gigabytes of stories and comments。

 So this is also kind of an issue。😊。

![](img/edb38c130361ed335351fa952a6e528e_7.png)

So we want to start our data permanently。And so one of the other ways the alternatives that we have instead of storing the data directly on the server is that we can use a text file and we can store this text file on our hard disk instead of soaring everything directly on the server。

 So this seems more permanent， right。😊。

![](img/edb38c130361ed335351fa952a6e528e_9.png)

We also have like functions that we can use to access and send data to our text file。

 So if we want to load data， we can use read data from file。

 which if you guys have taken in like 608 before， you' probably seen it's like a very basic like read data function。

 And basically， this is just taking in what we have in our data do T X T file and reading that。

 And then if we want to save data to data dot T X T， we can use the function right data to file。



![](img/edb38c130361ed335351fa952a6e528e_11.png)

So here's how we would implement it， for example， in like our API yeah， in our API endpoint。



![](img/edb38c130361ed335351fa952a6e528e_13.png)

This is if we wanted to like load the data from the file。



![](img/edb38c130361ed335351fa952a6e528e_15.png)

So you might be thinking， yay， we solve the problem。

 Now we are like sting everything in this text file on our hard drive。

 And it's all goodca now it's like permanent。 But there's still a couple of issues with this。

 So what's wrong with data do T XD。 Does anyone want to take a stab at just like one problem that they can potentially think of。

😊，Yes。Yeah， exactly。 So one of the big issues is if we're looking up things。

 it's going to be extremely slow。 So that's like one of the issues I'll talk about later。

 But some of the other issues we have are also like kind of like adjacent to what you mentioned is if we're saving stories and comments。

 the right speed is also gonna be very slow because we have to call that function every single time。

 And you can imagine that's gonna be very tedious and slow。 The other thing is。

 you can imagine we're still keeping everything in our Ram。

 So we can still run out of storage on our hard drive。

 So it's kind of similar to the problems we had before。 Like if you run out of storage in your Ram。

 This is still like an issue。😊，Also， this is like what youre saying， right。

 The query speed is very slow because like， if we w to just return one story posted by like a given user I D。

 right， we have to linear search through every single one of the stories， and this can be very。

 very slow。😊，Also， your laptop hard drive can still break。 It's not immune。

 You can like drop your laptop in a pool or something like this is not not failproof。 Also。

 if two users post at the exact same time， we don't actually know what ends up getting stored in data dot T X T because we don't know like which users' request was actually fulfilled to like write data to the file。

 so。That's kind of scary if we don't know what's being saved in data。 T T。Now。

 how do we fix all these issues？Well， we have this really cool thing called databases。😊，Yeah。

 so there's like SQL databases and then also like Mongo DB。

 which is what we're gonna be using for our web application。

 which Sophie is gonna talk more about later。 But basically。

 SQL databases are like really good for like relational data and like very structured data。

 but we're gonna use Mongo D B because it's a little more flexible for our purposes。😊，Basically。

 a database is just a really organized collection of data。

 and it's a way to store all of the data that you're going to be handling in your application in like an organized manner。

 a database management system DBm is basically a collection of functions that lets you perform operation on your data from your database like retrieving data。

 adding data， modifying it， deleting it etc。 So our database is basically like our substitution for data do txD。

 but much better。 and we'll talk about the reasons why in a bit。

 and the database management system is very similar to the read data from file functions that we just talked about earlier。

 but also better and well also talk about why So there's a lot of different types of databases。

 but we're not really gonna get into it if you're interested。

 you can like do more reading on your own， but some cool examples I think are like graphbased databases。

 which show kind of like really emphasize the relations between data and also time series databases like influx Db which shows like timestamped data So it's really useful if you're trying to track things over time。

😊，And then hierarchical databases like IBM IMS S， which shows everything in kind of like a tree structure。

 So it'll show relationships using like nodes。 So that's cool。😊，Anyways， now。

 Sophie is gonna talk more about how we can perform different operations with our databases。 Yeah。

 so we just went over how we're gonna replace data dot T X T with a database。

 and we're gonna replace our read and write functions with a D BM S。

 So let's talk a bit more about the reads and writes through the D BM S。😊，So yesterday in workshop 3。

 we talked about how we can make a get request from our front end to the s API/coms endpoints to request comments from our server。

By doing that， our back end server is going to send the comments back to the front end。

 So what actually happens in the back end if we now have a database and。Is this better。Test， test。

 test。OK。嗯。So let's talk about what actually happens in the backend server。

So after we make the API request to the backend server。

 our backend server can call a read function through the D BM S。

 and the D B S is going go to our database。Gather all the stories from the database。

Send it back to the server， and the server can now send that back to the friend and client。

So similarly for writing to the database， if you remember in workshop 3， yesterday。

 we learned how we can make a post request to slash API/com in the backend server and what this does is we write a new comment to the backend server and now the backend server is going to store it in the data variable and tell our front end that it has been successfully posted。

SoNow let's take a look at what happens in the backend with our D B M S database system now。

SoSimilarly， our server is going call a right function。 And through this right function。

 this D BM S is going take the new story。And add it to our database， yeah。

So let's take a look at some pseudo code for。Read and write functions through CB， B， M， S。

So typically， our DB M S is gonna be a package that will want to import into our backend server。

And one operation we can perform is a read。 We could read all of the stories in the database。Okay。

Another read we can do is with a query。 we could filter the database for certain stories that we want。

 So in this suit code， we'll be filtering for all the stories with I D 4。

 and that'll just be one story since an I D is a unique identifier for each object in our database。😊。

We can also do it right as we're familiar with yesterday。

And we could also delete and delete by a query， so this example might delete all the stories posted by a certain user named Joyce。

We could also update a story that's already been written to the database。 And this would make。

An update to stories with the author Jay。but yeah， this isn't real code。

 So don't try writing it in your back end。So let's talk about what types of databases we might use。

So， the。Common example of storing data you might be familiar with is through like Excel and Google sheetets。

 And usually you'll be storing data like in a row column format so。A relational database。

In a relational database， each spreadsheet is called a table and you'll have rows and columns。

For categories of data。 So for our catbook example。

 you might want a userss table showing all the users using your app and also maybe a stories table showing all the stories being posted for your catbook app。

 And you'll have relations between the users and stories。 For example， in the stories。

 you might want to call them。😊，Showing the user I D。 So for each story。

 which user is posting the story。And you want。But for a relational database。

 you'll need to write overhead code for dictating the relations between the users and stories table。

 as shown here。 So example of relational databases is SQL。

 which stands for structured query language。So we have some problems with this。

And the tables shown earlier， the data for one user is spread out across multiple tables。

 And as your web application gets larger and you'll want to be storing more data。

 this can get really complicatedcause you'll have to write overhead code for any relationship between tables。

So this can make our code hard to understand。 And as your web app gets larger。

 it will make adding features a lot more difficult。 And as I mentioned earlier。

 you'll need overhead code for dealing with the relations between tables。So as a programmer。

 we'll have to write all the code to accommodate the structure of our database and that's bad。

 We want our database to adjust to the needs as a programmer and have it be flexible。😊。

For adding new features and data。So instead of thinking about our data in terms of rows and columns。

 we can think about a piece of data as an object， as we're already familiar with。

 So this is called a document database。 instead of storing。Your objects in rows and columns。

 we can think of a object with all the fields as a document。

 and this is very similar to J Sha object that you've been working with in Cap already。

And documents don't need to have the same field。 So this allows for a lot of flexibility。 So。

 for example， this is what a document database might look for look like for the example earlier。

 But in this example， the object for Annabels。Annabelle's user object doesn't have any content。

 so you can have very flexible fields。 But as we'll see later。

You might want a structure for your fields。 and we'll talk about how we can do that in the back end。



![](img/edb38c130361ed335351fa952a6e528e_17.png)

So back to yesterday's workshop 3， we were working with comments that look like this and as you see this has the same object layout that a document database will be using。

 so it's a lot more natural and intuitive to work with as a programmer rather than working in rows and columns。

😊。

![](img/edb38c130361ed335351fa952a6e528e_19.png)

So the specific document database we'll be using is called Mongo DB。

 and this is a document database that stores data in Json like documents。

So you have documents which present each object in。A collection of data。

 and maybe you'll want very similar looking documents that live in a collection。

 So you might want all your common objects， which are not called documents to live in a common collection。

 And similarly， you might want a stories collection containing all of your stories documents。

Which are like Json objects。 And you want all of your collections to live in a database， which will。

Correspond to all the data you want to hold for your web application。

 so we might have a cap database。So now， instead of having a text file that lives on our hard drive。

We could use mango D B and the corresponding database management system。

So this optimizes our right speed because a lot of engineers at Mongo DB have thought about this and thought about ways to optimize it。

We're also optimizing our memory usage because we're no longer storing all of our data in a variable in our server。

Query， speed and concurrency issues are also solved thanks to engineers at Mongo D B。 Yeah。

 just as a reminder， earlier， we were storing all of this data as a variable in our server。

 So that takes up a lot of Ram。But there's still one more issue。Our hard drive could still break。

 We want to make sure that our Web app is fullproof so that any fault we might encounter is tolerated and doesn't interfere with the。

With how our web app operates and how our users use their web app。

So how do you make storage of our database fault tolerance， Does anyone have an idea？Yeah。Yes。

The naive solution is redundancy。 And that's exactly what Mongo D B does。

 It duplicates data across different hard drives that in case anyone fails。

 we can just access a different hard drive that contains all of our data。

So Mongo Db Atlas does this for us。 instead of storing our database on our computer's hard drive。

 we can use Mongo Db Atlas and store somewhere over the cloud。 And this makes our life easier。

 We no longer have to deal with running the database on our laptop and dealing with problems in case it breaks。

 The database is managed for you by Mongo Db Atlas。

 And you can also share your data with your teammates as you're working on your weblab project。😊。

And this is a lot more reliable than your laptop's hard drive because it replicates your data。

So now your backend server is going to store your data over the cloud。😊。

And what this looks like is it'll be accessing a primary Mongo Dbi instance on one hard drive。

 And you have replicate sets of this hard drive of this instance。

 So in case the primary Mongo Dbi dies， the hard disk breaks。You can access a replicas set。

So let's take a look at the Mongo Db user interface。 So if you have here's a catbook database。

 and in it， I have comments， stories and users collections。 right now。

 I have the stories collections clicked and inside the stories collection。

 I have different documents。 These look like JSson objects and they have different fields。

 And if you're working on making some data like Mkey mouse data for your。😊。

Web application later on for your Web lab project。 You can just edit fields and directly from the Mongo D B interface and add new documents。

So let's put everything together。When we make a get request。

 the front end code is gonna send that request to the back end。

And it's gonna make it to the API stories end point if we're trying to read stories data。

And now the back end， instead of sending data from the stories file， it's gonna make。

It's going to call the DBMS， which is going to go to the database， find all the stories。

The database is going to send this back to the back end。

 which can send it back to the front end as we went over yesterday。Similarly。

 we can now make post requests to create， update or delete data。 So the front end。

 maybe your user is making an edit to their story or adding a new story。

The front end will make a post request to the slash API slash stories and point。

The backend receives this request， it's going to call maybe some right function or delete functions via the DBMS。

And now it can perform the operation in the database。 So in summary。

 rather than storing data on our server or in a text file。

 we'll be using a database to store our data and the specific database we'll be using is a document database called Mongo Db and specifically instead of running Mongo Db on our hard diskk。

To make our database for fault torant， we'll run it over the cloud using Atlas because Atlas automatically has redundancy for us in case。

The primary Mongo D B hard disk breaks。So after lunch， we'll talk about how we can。呃，O。

So now we'll talk a bit about Mongo Db specifics。

![](img/edb38c130361ed335351fa952a6e528e_21.png)

Feel free to leave some feedback for the in databases like She。



![](img/edb38c130361ed335351fa952a6e528e_23.png)

Yeah， okay。

![](img/edb38c130361ed335351fa952a6e528e_25.png)

Yeah， okay。 now we'll talk about manga D B specifically。



![](img/edb38c130361ed335351fa952a6e528e_27.png)

What is mango D B。So as we just mentioned， it's a document database that allows our JSO objects to be stored directly in the database like we're familiar with。



![](img/edb38c130361ed335351fa952a6e528e_29.png)

So here's an example of a Json object。 There's three fields， a name field for my name， Sophie。

 my age， which is a number and my hobbies， which is an array of strings。😊。



![](img/edb38c130361ed335351fa952a6e528e_31.png)

So these are examples of objects that might be stored in the database。 So why are we using Mongo Db。

 So it's efficient when we need to write a lot to the database， a humongous amount。 So actually。

 Mongo is an abbreviation for humongous and it's also useful for the when our the structure of our data is very prone to changes because just as we talked about。

The fields allow us a lot of flexibility'cause we can add new fields or change the amount of fields in a document。

 And it's relatively easy to use as a programmer'cause it's very intuitive in the object oriented nature。

😊，So let's talk a bit more about the structure of Moga D B。 So in each object。

 we might have fields to describe the object。 So maybe we'll have a field describing the color lay or how poofy or how angry our object is。

 I've been calling it a corgigi。 But apparently， this is a Shiva。Yeah， okay。

 and we'll have documents which correspond to each object。 So inside the document。

 we have fields in this document might correspond to a corgi。

 and we might have a collection of corgis， which might look like。Oh， oh， by the way。

 I'm trying to make a parallel to a warehouse。 So paralleling to a warehouse。

 a collection might be a crate of corgis。😊。

![](img/edb38c130361ed335351fa952a6e528e_33.png)

And a database might be a bunch of crates， which are collections。

 So your database might hold a bunch of different types of collections。

 which each have different objects in them。And a Mongo D B instance might be like a warehouse of storage units。

So to reiterate in words， a Mongo DB instance is a group of databases that live on one server。

 And remember that we have duplicate replica sets of mongoDB instances。😊。

A database lives inside your instance and it usually corresponds to one web application and holds all the data you want to store for that web application。

 and a database might have a bunch of different collections and each collection is a group of very similar pieces of data。

 So maybe we'll want a collection for our stories， a collection for our users。

 a collection for our comments and and etc。Inside each collection。

 we're gonna hold many different documents， which we want to have similar structures。

 So maybe in our stories collection， we want all our documents to share similar fields such as name。

 content， I D and。Yeah。So， this。Here is a diagram of the structure of our storage facility。 And also。

 this is a sneak peek of the prizes we'll have at our hackathon。😊，Or give away prizes。

 So make sure to come。And this corresponds to these mango DB。objectsject。Yeah， okay。

 So if you have any questions， feel free to drop them in Webla dot is slash questions。So remember。

 we talked about why we're using Mongo DB and it's because it allows our databases to be very flexible compared to a SQL database。

So this means that different documents in the collection can have different fields as we just went over。

 So here's an example。 So say we have a Corgi collections with these three documents。

 a document for three Corgis named Sophie， Annabel and Abby。

 All three of these documents have the name field。 But you notice that they shared the other fields that they are other fields that they have。

 they don't share。😊，But if we working on a Web application。

 we might want all of our documents to share the same fields in a collection。

So what if we want to enforce the same structure for all documents in a collection。

So that all of these quigi documents have all same five fields with the same type for their value。

We can use Mongoose。 Mongoose is an object data modeling JavaScriptscript library that we'll use in our backend s that will allow us to enforce a structure for the documents in our collection。

😊，So fun fact， amongs is also a mammal。And the plural is among gooses， not among geese。Okay。

 so what is mangos， Mongos is a jascript library that we'll use in our backend server。

 and it allows us to interact with mango D B。😊，It allows us to enforce a structure for our collections from the very beginning。

 So once we start making post requests and get requests to our database。

 they'll already have this structure。So what does Mongo do， It connects to the Mongo Db cluster。

 which will cover code for it in the workshop。It enforces schemas and models which dictate the structure of the documents in the collection。

It allows us to create documents by having functions that kind of parallel the D BMS S。

And that allows us to interact with the database using with create functions， read， updates。

 deletes and more。 And I think we'll end here， Yeah， okay。



![](img/edb38c130361ed335351fa952a6e528e_35.png)