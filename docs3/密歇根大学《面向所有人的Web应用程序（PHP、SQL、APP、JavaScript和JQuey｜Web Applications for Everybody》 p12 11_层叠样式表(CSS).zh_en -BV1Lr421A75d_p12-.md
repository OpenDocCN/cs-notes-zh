# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p12 11_层叠样式表(CSS).zh_en -BV1Lr421A75d_p12-

![](img/2544dccbe208fb3324b3ded664ad1618_0.png)

![](img/2544dccbe208fb3324b3ded664ad1618_1.png)

So now we're gonna to talk about cascading style sheets。 like our lecture on HTMLm。

 my goal is absolutely not to make you the world's greatest graphic designer because that it is a lifetime of effort all by itself。

 I want to make you just kind of a crude cascading style sheet hacker。

 this class is kind of a backend development class。

 but we need to know enough about the front end so that our backend stuff looks kind of roughly like it。

 and that's kind of one of the cool things about Cs is the backend developer can should know enough Css to make it so the thing doesn't look dismal and then just hand it to somebody because that's this whole idea of the separation of concerns is that it allows things to do。

 And so here we start whether our picture of the universe， right。

 browser running on your laptop web server running in the cloud somewhere or perhaps on your laptop。

 sometimes all these are learn on a laptop when you're doing development。

 But web server database server talking HtTP back and forth， talking askql to the database server。😊。



![](img/2544dccbe208fb3324b3ded664ad1618_3.png)

So we hit click on it， we go get an HTML file， the HTML file comes back。 we parse it。

 it starts parsing in the Dom， but one of the things that happens is there is a reference in here to a CSS file maybe and so then it has to go。

 oh hang on I got to go get that CSS file pulls that CSS file in and then the CSS affects the Dom too and so the combination of the CSS plus the HTML lead to the pixel perfect layout of what it is that you're seeing on that screen and so in CSS and HTML we are still focusing on defining how the browser is going to render stuff So soon soon soon we will be learning how to code stuff and how to talk database but for now we're really talking about the browser and that's why a lot of this sample code doesn't even have to run off of a web server because we're not really doing anything dynamic when we start doing dynamic stuff you have to have a web server but here we don't have to have a web server。



![](img/2544dccbe208fb3324b3ded664ad1618_5.png)

So if you're going to have Firefox， there is a bit of code that could be really useful to you and you probably use Chrome。

 but some of us use Firefox in addition to Chrome because there's some really cool things that you can do with the Chrome web developer tool that's not the same as developer console it does a lot of cool things and let you debug your CSS quite nicely so you might want to go to Firefox and install this and use it or actually probably works in a bunch of different things So that's different than just the web developer console because it's very much about CSS and other design things。



![](img/2544dccbe208fb3324b3ded664ad1618_7.png)

![](img/2544dccbe208fb3324b3ded664ad1618_8.png)

![](img/2544dccbe208fb3324b3ded664ad1618_9.png)

So。I've said this before HTML is very old。Well over 20 years old now。

 and it started sort of with this gray background and blue links and underline and we were just happy to have a list of things right the stuff we talked about in the previous lecture。

 there's an L tag， there's an a anchor tag， there's an image tag and not much else， right？



![](img/2544dccbe208fb3324b3ded664ad1618_11.png)

Not much else。 And now we have this sort of beautiful corporate commercebased end user oriented money generating UI look and feel。

 And so CSs is that which enables this beautiful look and feel。 And like I said。

 I'm not going to I'm not going to tell you， how to be good at CSs So if you were to look at my website web applications for everybody co and use the web developer plugin to shut off CSS。

 That's one of my favorite things to do is shut off CSs And what happens is when you shut off CSss。

 you see the navigation independent of the styling。

 And one of the things you should do for your website for accessibility and for many other reasons。

 is have what's called semantic markup and that is your markup without CSs should still make sense right And so if you were to look at this with turning CSs off you would see。



![](img/2544dccbe208fb3324b3ded664ad1618_13.png)

![](img/2544dccbe208fb3324b3ded664ad1618_14.png)

You would see that there's links， and there's a list of links。

 And this list of links really is this list of links right here。 In't that pretty cool。

 And then there's another list over here。 And look， how pretty this。 I mean， literally。

If you weren't， if I wasn't trying to impress you with this website。

 this is a completely functional website， oh， and yes。

 there is the next thing you see is a video and then you see some stuff。Right。

 and the thing that's interesting about this for those of us who are not visually impaired is for visually impaired people。

 This is exactly how they see your website。 They see none of this， right。

 They see none of this little，ooh， look at that little cool shading。 Isn't that so awesome。 Well， no。

 you can't see that。 That's for visual folks。 And so this is where you want to separate the visual elements from the semantic elements。

 And it's not just for people with limited vision。 It is for us itself。 and as developers。

 we want to keep this as pretty and as simple as possible。

 And then allow a really good graphic designer to create the beautiful look and feel。 Again。😊。

As backend programmers， we have to make it so it doesn't look craping。

 So if you look at all my websites， you can clearly see that I'm far more a backend developer。

 I use bootstrap and the simplest CSsS。 It doesn't look shamefully bad。

 but it also doesn't look pretty。 Some someday might help me and actually make beautiful CsS for this。

 My goal is to build really beautiful markup and then have adequate CsS。 So it's not shamefully bad。

 and and then have someone more talented than me make it really beautiful。 Like say that Yahoo page。

 It' someone very talented， really made that beautiful。 That's not me。 I don't have that skill。

 Not at all。

![](img/2544dccbe208fb3324b3ded664ad1618_16.png)

So if you look ultimately you have sort of this HTML right and it has CSS that loads， etc cea。

 et cetera， and in the CSS， there is all kinds of highly detailed markupy kinds of things of how much space。

 how wide this little gray bar is and what font we're going to have for that and how much space you're going to have here and how much space you have here。

 All this is in this CSS so you can think of the browser loads the HTML。

 the browser loads the CSS and combines those two things together to produce pixel for pixel for pixel the beautiful visually beautiful look and feel。

 but it's important to keep your HTML technically beautiful or semantically it's semantic HTML。



![](img/2544dccbe208fb3324b3ded664ad1618_18.png)

And so again， we have the sort of the back end and sort of slightly front end developer。

 which is really what this course is aimed at。You know， we're going to generate some HTML。

 we're going to try to make this as simple as possible， we'll pull in some CSS。

 and that's going to tell how to make these things work and in the CSS。

 the CSS is a set of rules that say， you know what， you see that body tag。

This is what I want to happen on that body tag， see that paragraph tag， any paragraph tag。

 this is what I want to happen on that tag， see this anchor tag。Oh there's no anchor tags sorry。

 no anchor tags， but you get oh here's H1 tag see this H1 tag see that I want that to be blue and so but these are two files and so what happens is I code this up by build this and I build a really bad CSS that just gets me through the day but then I can hand this and then someone else can just edit this and keep heat and refresh and make it prettier and prettier and prettier and so it allows and sometimes you're both the developer and the designer。

 but it also allows really talented developers to really specialize in building this and really talented designers to specialize in making developers look really good。



![](img/2544dccbe208fb3324b3ded664ad1618_20.png)

So the CSS syntax is very different than HTML and it's also different than PhP and it's different than JavaScript。

And so HTML and CS are really and truly programming languages。

 but they're not procedural programming languages。 H is a declarative programming。

 You say this is a paragraph。 That's a paragraph。 you figure out how to show it。

 the same is true for CS。 It is a declarative It's a declarative language。

 meaning that you don't write loops。 You don't have variables。 you don't control logic or steps。

 you just declare all the things that you want to happen。 They kind of all happen at the same time。

 basically， And so this is the syntax of the CS programming language。

 even though it's very different than any procedural programming language。 And a lot of people。

 by the way， love nonprocedural programming They be like， I love H and I love C。 and I hate PhP。

 that's because PP is procedural， and it requires far more detail to say do this than do this than do this then do that。

 That's not how CS works。 It's like find the body tags。 find them all。 do them all。

 do it The syntax of CS is pretty simple and pretty elegant。 And a lot of people just learn。



![](img/2544dccbe208fb3324b3ded664ad1618_22.png)

SS without even taking a class。 There is some kind of a selector。

 The simplest selector is body tag and then there's a curly brace and sets the start of the things that we want to apply to the body tag and then we have a set of properties and you have to look these properties up on the web or in a cheat sheet or whatever font family happens to be the property that we set to set the font。

 and then we're saying I would like this to be aerial。 and if the aerial font is not available。

 I would like a generic s serra font。 So this font family happens to be a thing where you give a series of options in decreasing priority order。

 and then you know you separate this with a colon and you finish with a semicolon。

 And so then there can be many of these things here between the open brace and the closed brace。

 but that's the basic CSS syntax。 so you saw in a previous slide where it' was all sort of jam together white space doesn't matter。

 but when humans do this， they tend to indent and make it look pretty even though the indentation is not really syntactically important but cognitively for us poor humans that have to read it it is cognitively very important。

Right so we have the part that the rule applies to body tagag and then we have a series of key value pairs。

 basically property value， property colon value pairs。

 and we have to go read and learn what each one of those things does and how we use it but the web is cr for this you're like what is the CSS property for transparency and like oh and here's a little tiny sample and you copy and paste that and we learn by copying and pasting or stack overflow I'll tell you what's the best way to put a two pixel border around a button let me like stack overflow have like 5000 answers for that。



![](img/2544dccbe208fb3324b3ded664ad1618_24.png)

So you might want to get yourself a cheat sheet， I don't really memorize CSS well maybe that'sca I'm a backend programmer。

 not a frontend programmer I can I know a few things like margin and padding and strong and bold and well emphasize and anchor tag and all that stuff but I have to look stuff up all the time and so Ive gotten better at it because I use CSS more but things like how padding works and how margin works that's really something that you probably need a cheat sheet for a while。



![](img/2544dccbe208fb3324b3ded664ad1618_26.png)

So we're going to talk about a number of CSS properties。

 but just understand that this is by no means the you know end all and be all and so coming up next we're going to cover some of these CSS properties。



![](img/2544dccbe208fb3324b3ded664ad1618_28.png)