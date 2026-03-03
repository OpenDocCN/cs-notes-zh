# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p03 2_我们的技术栈.zh_en -BV1Lr421A75d_p3-

![](img/a084b5518728dd46890cd5a08a3f0681_0.png)

![](img/a084b5518728dd46890cd5a08a3f0681_1.png)

So welcome to Web applications for everybody。 I'd like to take this first lecture to talk a little bit about the core technologies and the people that built some of these core technologies。

 Of course every one of these requires a group of people。

 but I have some cool interviews that I'd like you to take a look at not so much because I want you to memorize what they say but I also want you to kind understand the kind of people that made these things and how technology is made by people。

 we're people and people made technology and nothing's perfect。

 everything is a set of compromises and a set of choices and so there's no magic to all this。

 And so if you say， this is a kind of funkiier flawed。

 it's funkiier flawed often because it wants to be like that or it's naturally someone made a choice。

 And so we'll talk about the web server we're going to talk about that PB programming language SQl the language you talk to databases how we talk inside the browser using jascript and JQuery。

 which is like a library that makes a client side coding so much easier and then how we send data back and forth between the browser。

And the server using a protocol called JSON。

![](img/a084b5518728dd46890cd5a08a3f0681_3.png)

So the kind of the foundation of everything we're going to do is the Apache web server。

 It's an open source project。 It was part of the 1992-93-94 project at NCSA。

 the National Center for Supercomputing applications that was part of the mosaic and the mosaic was a browser。

 a client and the Apache Web server was the HTTPD which stands for Hypertext transfer Pro Demon De was a thing it was always there so the client could talk to it when the Mosaic project kind of went down at NCSA it was open source and a bunch of people picked it up and Brian Baendorf was one of those people Apache stands for depending on your interpretation Apache like verypache web server because they kept patching this thing and that created the Apache Open source Foundation as the first product。

 its open source it's written in this programming languagen called C which is a very lowle and powerful programming language that really underpins lots of the technologies that we use。

And so this is sort of a slide where I talk a little bit about the history of all these programming languages。

C is an interesting programming language because in 1972。

 it's the programming language that was used to write Uniix， was right used to write Linux。

 was used to write Python。 So if you look at Python itself， Python is written in C。And so prior to C。

In the beginning we tend to do lots of calculations we used we saw computers as really fast calculators and so a lot of the things we did was either write very simple machine language programs or fortran programs that really were trying to use it as a fast calculator and so sometime in the 1520 years between the 1950s in the 1970s we realized that computers were going to be used for things like email and social networking sending text and there was a whole bunch of fancy text languages that were built。

 but none of them really were a combination of text savvy languages and super fast languages。

 so the language， the first language that I recall that was both really good with text and good with numbers and really fast and suitable for writing systems kinds of programs was this language called C and a lot of us fell in love with it it was a very succinct programming language it uses curly braces for if statements and four statements that uses this forks syn text with the。

my colons in the middle？If you've seen Java or JavaScript or C++ or objective C or CSp。

 you've seen this language because all of these languages at the top here。

 the kind of systemy programming languages take theirre very much cues。

 JavaScript is kind of on the gray area between fun languages and system programming languages but they all took their cues from this C language which was used to write like I said Linux and Uniix and even Python is written in C。

 so Python was written in C and in addition to the sort of systemy languages。

 there's a whole series of easy to use languages and Perl was this language that stands for something report language and it was about sort of handling simple data stuff and Pearl was really an inspiration for Python and that Python was written in C and so C Python took a lot a lot of inspiration from C I hope by now that you know the Python language and the PhP language which is another of the languages we're going to learn in this series of classes。

It took it's also written in PhP。 it took a lot of inspiration from it from C。

 PhP is written in C and takes a lot of inspiration from it。

 but it also takes a lot of inspiration from Pearl and to a lesser degree probably inspiration from Python and in this bottom set of languages these are really simpler programming languages that have simpler primitives that are easier to use JavaScriptscript kind of lives in the middle JavaScriptscript is increasingly both a system programming language and kind of a lightweight fun language and will use it in some ways for both things So JavaScriptscript is a very interesting language I prefer not to teach jascript is the first language because it's so sort of beautiful elegant and powerful I mean it's easy to find a little bit of code and stick it in your webp page and have it work but to truly understand jascript it's probably better for it to be your third or fourth language that you learn if you learned Python and PhP and SQL H and CSS and then you finally learn ja to me that's the right order and that's the。

That we're going to do in this class。 So， but I still want to introduce you then to some of the folks who've。

 built these basic technologies。So the PhP language is a programming language that is a templating language that's merged into HTML pages and so it's like you've got HTML and then code and HTML and code and HTML and code。

 and so it was very easy to add little tiny bits of dynamic calculations and dynamic code to part of a web page。

 so some of the web page comes from code that runs and has print statements in it and then some of the web a page just comes from the HTML。

So P P was created by a fellow named Rasmus Learorf。

 Now thousands of people maintained it as a large open source project。

 Rasmus was not a trained computer scientist。 I encourage you to watch his video。

 He'll honestly tell you that he's more interested in practical。

 easy to use stuff than he is about building the world's greatest programming language。 Now。

 P P is from the 80s。 And so it's almost 20 some years old。

 And so it's gotten more elegant as time has passed。

 So PP5 and PhP7 are much more elegant that PhP1 and PhP2。 but the idea is。

 is to get you as the programmer building a web application productive as soon as possible。

 He was having trouble in the early in the mid -1990s because he was writing all of his web pages in C and see it a very。

 very， very hard。 So take a look at it。 And Rasmus is a fun guy。

 and PhP is very much reflection of his early approach to building it。SQL。

 I hope by now perhaps you've seen a little bit of SQL SQL is a glorious and beautiful language。

 SQL basically takes a very complex problem and that's how to optimally store data in memory of the computer and on the disk of the computer and get things next to each other that are likely to be pulled up at the same time。

 joins and inserts and selects and updates and deletes。

And databases themselves are like super complex， I mean， you could have 20 careers。

With PhDs and all 20 of them， and you still wouldn't know enough to know all the stuff that database applications are capable of doing。

But we have this thing called SQL where all that complexity is beautifully abstracted for us and we just say I would like to do this and you magically figure it out。

 so that magic figure out is full of PhDs in computer science， but we don't have to worry about that。

 and SQL is such a beautiful language。 the birth story of SQL is a little different than the other languages in 60s。

 all the database vendors， IBM and Oracle and Cyibase and companies that don't even exist were fighting over the marketplace。

 and they all had a different view of how databases should be built so and they did and each one would have their PhDs and computer science they would build different databases and they would build different language just talked to those databases and then the US government in the form of the National Institute of standards and technology N said。

 look。

![](img/a084b5518728dd46890cd5a08a3f0681_5.png)

We're tired of arguing with you about which is the best database。

 And what we need is a standard language to talk to any database。 We don't。

 You can implement them any way you want。 Go ahead。 And so they said， hey you industry people。

 you get together and you develop a standard。 And S， Q L was that standard。And Elizabeth Fong。

 I did interview with her went to visit her at NISist and she talks about how this happened。

 and it was kind of a magical thing。Because all these vendors got together and produced something beautiful and it wasn't abstraction in that it really wasn't a direct implementation the language didn't directly implement。

Any of the vendors databases， but it was a way to talk to any of them in a very beautiful abstraction so it turns out to be a very。

 very beautiful language and I think you'll agree once we get talking to them。



![](img/a084b5518728dd46890cd5a08a3f0681_7.png)

So。After we're done in the server， we're going to start playing in the browser in the client。

 and so JavaScriptscript is like this C like programming language and that has curly braces。

 et cetera， et cetera。 but its early design was in to be done inside of a web browser web page。

 And so it actually has these predefined constants like document in a window that allow it to mess with your browser。

 So you're sort of watching your browser page and JavaScriptscript is sneaking around and fiddling with the page and doing things and you're seeing those changes through what's called the document object model or the window where things that's how you can be in a page and likeop。

 a new thing pops up。 little red bot， that's all done with JavaScript。

And so JavaScript is really cool， it was in 1995， Brendan Ike was the inventor of this。

 it was at the Mazilla Foundation part of the Netscape project。

And I encourage you to take a look at Brendan's video。

 Brendan is very different than Rasmus in that Brendan is even smarter than a computer scientist。

 Brendan is a physicist， which we computer science good computer scientists look up to physicists because physicists are so smart。

 No a lot of math。 Brendan really saw jascript as。😊，His chance， in a very hurry。

 without really telling anybody， building what he considered truly the most beautiful programming language that humanity had ever seen。

 That's， that's how high of a goal he had for it。

![](img/a084b5518728dd46890cd5a08a3f0681_9.png)

And he's just smart enough that he'd seen so many languages。 He had think he liked about。

 and he sort of took that C like language from Java。

 the C like syntax from Java and built a very beautiful language。

 And when I get to telling you about like how object PhP compares with object or a jascript。

 I'll totally geek out about it because I'm like look how elegant this is。 And you be like。

 just show me this syntax。 So what I'm saying is jascript is a beautiful language。

 And that's why jascript keeps increasing in popularity。

 You may be working in an organization that uses javascript in the server。

 in addition in the browser using a framework called No Js or other jascript frameworks。

 And so take a look at the jascript interview， its it's really， I think quite cool。 And again。😊。

Sinceense the personality of these people。

![](img/a084b5518728dd46890cd5a08a3f0681_11.png)

Now。Javascript is this beautiful programming language。

 and it talks to the browsers through this thing called the Dom， the document object model。

 and they standardize JavaScript very quickly。 So JavaScriptscript is all the same。

 but they didn't standardize the document object model。

 The things that JavaScript does to change what's going on in the browser okay and so the problem was as if you had。

Internet Explorer 6 or in an Explorer 8 or Chrome or Firefox， they all were different。

 not JavaScriptscript， but how jascript did things in the browser。

 And so JakeQury was a portability layer that was built by John Ressig and it was a very elegant and portable way to do things in the document object model。

 And so John is like 10 years after all these other folks in that he is trying to make it easier for us to do。

 So a lot of people these days just assume JQury is JavaScript because it's a better way to talk to the document object model and it's a really great way to do stuff and it keeps our code in the browser much shorter And so I encourage you to take a look at John Ressig。

And so the last thing we're going talk about is what's called JSON or JavaScriptscript object notation and that is basically the format of data that once you have really smart browser code and really smart server code and the code instead of the page but the code behind the page wants to talk to the server on your behalf and start sending things without even you doing anything you'll just be like and I'll send something like go check to see if there's any new messages go check to see if there's any new messages。

 Well， the new messages come back in a format called JON and this video that I have Douglas Crockford who is doesn't credit himself as the inventor of JSON。

 he is the discoverer of JON and that's because it was actually part of JavaScriptscript。

 he just took part of the jascript language and created a protocol that then captured that and then we use that for a lot of different things。

 And so I encourage you to take a look at these videos when you have some time They're not essential you're not going to learn JON from talking from watching Douglas Crckford video or。



![](img/a084b5518728dd46890cd5a08a3f0681_13.png)

You're not going to learn from Liz Foong is not going to be able to teach you SQL。

 but I think it helps you to understand。That all these things are the creation of people and we people working together to kind of come up with something and there's all kind of compromises and it's all very interesting stuff and you may ultimately end up writing with node or ruby on Rails or who knows what you're going to write your web applications。

 but at the end of the day， everything is something that we people have created and then we people use and use from each other。



![](img/a084b5518728dd46890cd5a08a3f0681_15.png)