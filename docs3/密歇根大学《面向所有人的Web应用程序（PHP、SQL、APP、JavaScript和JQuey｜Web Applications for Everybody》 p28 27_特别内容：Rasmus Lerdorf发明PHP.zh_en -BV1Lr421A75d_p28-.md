# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p28 27_特别内容：Rasmus Lerdorf发明PHP.zh_en -BV1Lr421A75d_p28-

🎼你是。🎼宝宝。so it started in 1993 when I saw the Mosaic web browser。

 that was when I got really interested in the web。I've been doing Gopher and IRC and other Internet related things before then。

But with mosaic， I could suddenly explain what I was doing to my mother。

 so I knew this thing was going to be very， very interesting。I was living in Mountain View。

 California， but I moved back to Toronto to do consulting。

And I ended up consulting for a number of companies， and I wrote the same code over and over。

 basically CGI script written in C。And I wrote similar code to handle forms and post data。

Filtering and all those sort of common web things you end up having to write and see if you're writing raw CCGI programs。

So。That was getting tedious， I'm not very interested in programming， it's kind of tedious and boring。

 so if I could reduce the amount of time I had to spend programming and maximize the output。

And get to the solution quicker that that was my goal with PhB。

 I put together all my common stuff into a C library。

pack it into the NCSA web server and then added a little templating system on top of that to let me easily call into it and that was the first version of PhB it was a productivity tool for myself so I could very quickly go to a new client and whip up a new web application for him and tie them to their database or whatever they needed and every client had slightly different requirement so I kept extending my tool。

Then other people started asking me。About this stuff。 They asked me how I built these things。

 And I said about using it's a little tool I built， and they asked if they could have。

 It'm sure why not。 I mean， that's not what I'm selling。 I'm selling my services of solving problems。

 The tool itself is irrelevant， really。 It's just my hammer。Anybody can use my hammer or I car。A。

And then they started sending me patches， which I thought was really。

 really cool and they found bugs in my stuff that I hadn't found yet。

 and which meant I could also go into clients and say， hey。

 here we go here's a new version it fixes this， this and this。

 and they thought it was being extremely productive。

Writing all this code and fixing all these things so fast。So that's when open source really hit me。

 this was in 1994， '95 before the term open source existed。But it really caught on with me that。

I got together with a group of my peers， other people interested in the web solving the web problem from all around the world。

 we all had similar problems， we faced similar issues and collaboratively we could build a tool that solved this problem。

That was really。How PhP got off the ground。嗯。I learned a bit along the way that in order for this to grow。

 I had to give up control。Of a PhP， I had to let other people have some control。

 I couldn't rewrite everybody's patches both because I'm pretty lazy it's a lot of work。

But also to give people some ownership in the project。Once they have some ownership。

 once they have full control over their part of it。

 then they become much more invested in it and they become passionate and it becomes theirs。

 not just them contributing to my project， it becomes our project and that really changed the nature of PhHP and that happened around 1997 or so where it really delegated it out and gave people full access to the CBS repository that I was using。

To develop this stuff in。And it grew like crazy after that， both because the web grew。

PHP was sold in the right time， the right place。But also because it was very。

 very easy to get in and get started。Contributing to PhP and using PhP as well。

 obviously has a very low barrier of entry。 So both on the using PhP side and also contributing to PhP side。

 I tried to keep the barrier of entry really low。It does not take much even today to get a CVS account on the PhP project。

Soce revision control is a wonderful thing， it doesn't really matter how bad the initial patch is from some contributor。

 we can always fix it。Much rather welcome new contributors and guide them along and get them to be productive and useful。

Then yell at them for having a bad initial patch。You know， from the outside。

 you look like a well oiled machine， you know you know it's a well oiled machine that accomplishes things you know more effectively than a commercial organization。

 but at the same time it's sort of a it's a loose， it's a band of Brothers to some degree。

 we have close to 1，400 people with CVS accounts， which means those people can all commit to some part of the repository。

 either PhP， paraar pele， the documentation tree。Anywhere in there。Now they're not all active。

 obviously， we probably have maybe slightly over half the people have committed something in the last year and a half。

嗯。There's no management of these people really they sort of self organize into smaller groups。

 it's impossible to manage 1400 people， obviously， especially when they're volunteers and they're not actually。

Go into shop to a meeting or read their email or whatever。

 but they self organizeize around what they're interested in so we have documentation teams for the various languages there's a big French documentation team that just worry about the French translation of the documentation it's a Japanese translation team。

Big group of core documenters and those guys。organize themselves there's no big chief of this whole thing。

 I don't tell people what to do I can't， they're not going to listen to me。

 why would they listen to me right they do what they're interested in that's the only way volunteers work。

U， then there's the peckle guys that build peckled extensions。

 generally that's sort of where we test out new extensions and bring in certain ones。

 like in PhP51 we brought in the JSON extension， which started its life in Peckle。Next。

 maybe OAth or some of the others that are big right now。So。

That's sort of how new features and new things eventually creep in。

 they live outside of the core tree and they get enough penetration。

 there are enough people install them we see Linux distros pulling them in and their core version of the PhP they pull in some of these things so we sort of look at what's happening out there and that happens but there's no real management of that either。

And it's a meritocracy I mean code speaks if you write a patch or you write a piece of code to implement a feature that says a lot。

 if someone wants to disagree with that way of doing things。

 if they can offer an alternate implementation that's a really good argument if all they do is whine about it。

 that's a really bad argument and chances are that the implementation will win even though it may not be the best way of doing things there's code it's sort of works that's what we go with and that's always been a default。

It doesn't always lead to consistency， but it does lead to getting the features and actually being able to do something。

 being able to connect to this type of database， even though it may not be the best way of doing it。

 at least it gets you there and that's always been what PhP is about is solving the problem。

We'd rather have an ugly feature than not having the feature at all。

