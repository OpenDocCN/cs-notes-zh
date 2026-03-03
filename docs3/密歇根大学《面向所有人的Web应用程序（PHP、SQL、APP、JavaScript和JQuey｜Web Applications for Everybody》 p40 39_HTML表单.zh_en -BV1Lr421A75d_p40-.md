# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p40 39_HTML表单.zh_en -BV1Lr421A75d_p40-

![](img/95a4bd2af64082136fdcd850294ff784_0.png)

![](img/95a4bd2af64082136fdcd850294ff784_1.png)

So now we're going to talk about forms， if you recall our previous lecture was functions and that's because forms follow functions in my syllabus。



![](img/95a4bd2af64082136fdcd850294ff784_3.png)

Get it warm solid functions。So at the end， we talked the arrays。

 we talked about the superglobal variables and part of the goal is is you're going to process HTML requests and PhHP is designed for that purpose。

 it's not a general purpose programming language， it's a programming language for web applications。

And we use these arrays， dollar underscore， get dollar underscore post， etc。

 So that's how these things work。 So just to review if we put parameters on the end of a URL question mark X equals2 Ampersand y equals4 the question mark is for the first one and ampersand for the following one these are parsed and placed into an array inside your application called get and so you don't have to do anything PhP magically does this before your program starts up right so you click a button or you type that URL into your browser。

 it gets sent using HttP Apache and PhP parse that and set this global variable and then starts your program up the very first line of code So this variable exists and it's called a superglo inside of PhP and then it's in your main code and any functions that you have within your main code。



![](img/95a4bd2af64082136fdcd850294ff784_5.png)

![](img/95a4bd2af64082136fdcd850294ff784_6.png)

And so that's the basic idea of taking data from the outside world。

 key value data from the outside world， using the HtB protocol and getting it into you。 Now。

 there is a more convenient way to enter data in。 and that's what we're talking about now。

 and that is using forms。 and I'll be honest， I'll just sort of step back in time a little bit。

 This would have to be like 90 mid 1994。 and there was a time in 93 that there was a thing called Gopher and Gopher was sort of more impressive to most of us than the web was。

 and the web was like。

![](img/95a4bd2af64082136fdcd850294ff784_8.png)

![](img/95a4bd2af64082136fdcd850294ff784_9.png)

And so I'm like， the web， that's just another version of Gopher that's not is not anydifferent。

 And the first time that I knew that the web was cooler than Gopher was when I saw my first form and I'm like。

 oh， wait a second。 Now we can actually type data and hit the submit button。

 And the first form I saw was from Fedex do com。 And it was pretty much as simple as this。

 and it just said， enter the tracking number。 you click the button and it went the tracking database and showed the tracking information early days。

 the web really simple user interface。 but I'm like。Mind blown。 And， of course， you don't care。

 The webs here Form are a thing we do。 We log in with them。 We search with them。

 We do all kinds of things with them。 And so this is the basic mechanism of creating a screen。

 That's not just a screen for you to read， but a screen for you to put things in and then submit that data。

 And this is sort of the simplest version of that thing we've got so。



![](img/95a4bd2af64082136fdcd850294ff784_11.png)

Just HTMLml is not PhP yet， so we have a paragraph tag and then we have a form tag that says these things are grouped together and so these are submitted together as a group。

 you have a series of input tags， dot dot dot dot and you have some text。

Like input guesses just some text and they say， oh。

 this draw a little fill in the blank and you can set how long it is， et cea， et cetera。

 put a previous version in there if you want， and you are giving a name which is the name that is going to be used to submit this to the server and then you have a button that basically takes this entire form and if there are more things in here and you hit the submit button and it gathers up all the data from all these things and then sends it to the server using a get request in this case。

 Weca will show how a post request works in a second。And so， you know， we type all this stuff in。

 you know， we have the form， we type in the 12， then we hit the submit button。

 and then that paste sends in a key value pair， which it pulls from this name guess and this number 12。

 and so then that sends that in。 and of course when this code runs dollar underscore get。

Sub quote guess quote is where that data ends up， and so the user doesn't have to type input on that form。

OkayAnd so that's the idea is you're constructing with a form a set of data that you would like to be submitted along with the URL。



![](img/95a4bd2af64082136fdcd850294ff784_13.png)

And so if we write a little bit of code here， we would basically have a paragraph tag and then a pre tag。

 and then we print out the dollar get， right， And so the first time this runs。

 dollar get will be empty。 It's there， but it'll have nothing in it。

 And then when you actually send it the second time when you type your 12 and then submit。

 it'll run it and then the second time dollar get will have a 12 in it。

 So the first time through it doesn't have any data， meaning there's nothing on here。

 and then you hit the 12 and hit submit。 and the second time through， you're going to see data。

 So you know， inside of your PhP code， This is in the server Now， inside your PhP code。

 you know whether or not there was a parameter there。 whether or not that's got some input data。



![](img/95a4bd2af64082136fdcd850294ff784_15.png)

So next we'll talk a little bit more about how we can use other kinds of things that we do with forms in different ways of submitting that data to the server。



![](img/95a4bd2af64082136fdcd850294ff784_17.png)