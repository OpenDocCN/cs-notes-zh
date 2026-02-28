# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p103 37_04_03_理解日志文件.zh_en -BV18U411U729_p103-

![](img/12eebd68d45f825cf67c0a7b500ddac6_0.png)

Welcome back。 Now that you know about the importance of web server logs。

 It's time for you to start thinking about writing code that deals with them。

 The first thing you're going to want to do is to be able to read in a web server log file。

 and represent the information in it in Java objects to do this， you need to think about two things。

 The first is what does all of the information in the web server log mean。 And the second is。

 how do you represent it in a Java class here you can see one entry from a web server log file。

 It has a lot of information， and it's not readily apparent what each piece means。



![](img/12eebd68d45f825cf67c0a7b500ddac6_2.png)

To find out what it means， you would want to read documentation about this web server。

This particular data came from the Web server log for an Apache 2。4 web server， so to find out more。

 you could go to Google and search for Apache 2。4 web server log file format。



![](img/12eebd68d45f825cf67c0a7b500ddac6_4.png)

If you do that， you'll end up with a lot of hits and this first one here gives you a link to the Apache documentation site if you scroll down a bit。

 you'll find the information on the access log that is the log of accesses to the web server which is what this web log is。

 and you will see that it has information about each of the pieces of this entry。



![](img/12eebd68d45f825cf67c0a7b500ddac6_6.png)

The first is the IP address that is the address of the device on the internet。

 which made the web request that is logged here。The next two pieces are both dashes that indicates that they're missing information。

 The first dash is for some information about who made this request。

 which you'll see the documentation says is unreliable。

 the user's computer could lie about who they are。 The second dash is for the username if they're logged in with HTTP authentication。

 If they've typed a username and password on the website。



![](img/12eebd68d45f825cf67c0a7b500ddac6_8.png)

The next piece of information is the date and time when the request was made。Next。

 you have the request itself， including what type of request it was。 in this case。

 get where they're asking for a particular web page。 and then what page they asked for。

 Next is the status here， it says 200， which indicates success。 There are many other statuses。

 which indicates success or failures。 you may be familiar with 404。

 which is the very well known status code that indicates that the requested page was not found。

 Finally， is the number of bytes that the server replied with。

 How much data it sent back to fulfill this request。Okay。

 now that you've read the documentation and understand what each of these pieces of information mean。

It's time to think about how to represent them in a Java class。

The first thing you need to think about is what type of information each of these is。

For the IP address， you could use a string since you're interested in just the text of that field。

 Java does have a built- in class for IP addresses。

 which would give us some more features if we wanted to actually connect to that address for example。

 but we don't need that functionality， and we don't need to worry about the complexity that would introduce right now。

We don't need to represent the two fields that we've omitted that have no useful information。

 we do however want to represent the date， you could use a string for that。

 in which case you would just have its text or you could use the built- in Java date class。

 which understands what dates and times are， and how they relate to each other so you could check if one time is before or after another time。

For the request， you can just use a string。And for the status and number of bytes。

 those are both numbers so you can use an end。Now that we've thought through these types。

 it's time to turn this into some Java code here you can see the start of a Java class for a log entry。

 we've declared a public class log entry and written fields based on the types that we just discussed。

You should now think should each of these fields be public or private。

 remember that if a field is public， any piece of code can access it， and if a field is private。

 only code within this particular class can access it。In this particular case。

 it makes sense to have each of these be private and to design your class to be immutable remember from earlier when we learned about strings that immutable means you cannot modify an object once you create it so you're going to write this class so that each of these fields will be set in its constructor but can only be read。

To make anything able to read these fields， you'll write a public giter or accessor method。

 such as these， which will just return the value of that field。

 But there will be no way to set the value of the field once it's constructed。

 Spking of constructing， you need to write a constructor for this class。

 There are two ways you could do it。 The first is to take in this entire string。

And then I have the constructor pull it apart into each of these individual pieces and fill in the fields or instance variables of the class。

The other is to have the constructor take each piece of information separately and simply initialize the fields of the object。

We're going to have you do the second one， just making a constructor that looks like this。

 which is going to fill in the fields based on the information passed in with each piece being passed separately。

Why would you do it this way， well this gives you a little more flexibility if you wanted to create one of these objects from some other source of information。

 you could do so。It turns out that pulling this line apart is actually a little bit tricky。

 so we're going to give you the code for that， it's a little bit ugly and we'll package it up into a nice method for you so you can just use it to read the file。

Here is the final log entry class with all of the things you just learned about。

 you would use this to represent one of these log entries as you work with it。

 so your next task is going to be to use this class。

 the code we give you to split this up into each separate piece and put them together to make code that's going to read the entire log file。



![](img/12eebd68d45f825cf67c0a7b500ddac6_10.png)

![](img/12eebd68d45f825cf67c0a7b500ddac6_11.png)