# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p45 44_表单数据处理与HTML注入.zh_en -BV1Lr421A75d_p45-

![](img/dc81736a817f303d2c3452885baf45fd_0.png)

![](img/dc81736a817f303d2c3452885baf45fd_1.png)

So now I want to talk about how you think about data when you receive it from the server。

 So up to now we've been talking about how you make a form in HTML。

 We've talked about how that comes in in Do underscore post。

 Now we're going to start talking about what you do with Do underscore post。

 And the first thing we're going to talk about is persisting form data from one screen to another。

 and we do this so much， it's done so commonly and so often that we just assume it magically happens。

 but it doesn't。 It turns out that we as the developer have to work pretty hard to make that happen。

 right， And so you type something like 20。 you hit submit。 and if you don't persist it。

 this comes back blank， right， So we just sent the data and there was a 20， but where to go。



![](img/dc81736a817f303d2c3452885baf45fd_3.png)

And what we want as users is to see the 20 in case there was a mistake， right， see the old value。

 So we have to specifically copy the old value from one request to another request on down。

 if that's what we want。 And we turn out we want that a lot。

 And so the idea that we're going to take the post data and generate a form that has the post data in it。

 that turns out to be a real common problem。 And turns out one of the most common sources of security errors。

 And so think about it this way， right。

![](img/dc81736a817f303d2c3452885baf45fd_5.png)

This script we've got is going to be run。As a gut request。

When we first go to the URL and then we type something in hit submit。

 then it comes into this same script again as a post request。And so we have to use I set to say。

 is this a post request with guess as a value， or is this a get request。

 And we'll just have to show the form。 So on the first one。

 we show the form on the second one we want to show the form with the previous guess already persisted from the previous request。

 So what I'm going to do is I'm going to use the ternary operator。 I don't like it。

 but I use it mostly only in this exact form。 If there is a guess value in post。

 stick it an old guess， otherwise put a blank and old guess。

 So old guess is this variable that will fall through into this templating code。

 Now the rest of this is just a form post yada yada yada， except right here。 we say value equals。

 So value equals is a way for us to put an old value into the form as we're displaying the screen。

 So we're writing back the form。And if we put value equals in the form and put something in it。

 then that's going to show up。42 in that little screen box。

 so that's how we put something in by generating HTML with value equals。Now。

 this is also the moment where I'm showing you this little syntax of shortcu。So normally。

 I would say double double quote PP echo old guess semicolon less than question mark right that says switch into PhP that says run the echo command。

 semico is the end of command， and this says switch back to HTML。 That's what that does。

 And if I put double quotes around it like here。 then the H will just be like quote 42 that's what we're gonna to see although spaces don't matter because that's just code running This is such a common thing that they actually have a shortcut for it。

 which is less than question mark equals So less than question mark PP is the long form and than question mark equals is the short form。

 and what it is is just a short syntax to do exactly this thing and that is to echo the value of a parameter。

 So what this says right here is print old guess right here and we're done。

 So we use this short form a lot， especially when we're doing stuff like this where we're mixing H and we switch into PhP just to get a value。

then we're back to HTML。Okay。😊，So。If we do that。That means that。

That means that we're going to see that old value。But it turns out that that code that I just wrote for you。

 this code right here is like。The worst possible code you could ever write in an application。

Because of。The problem of what we call HTML entities in our HTML injection。

And the problem becomes is if a user is particularly smart。

They could type something into the form field that is going to become valid HTML。Okay。

 and so they know that you're going to say value。Equals quote， whatever， quote， but what if I。

Stick something in there that itself is a quote。And then I put my own code in here。

And so what I've typed carefully here is double quote end bold， die die die， and when I hit submit。

I don't see the old guess anymore。 I see bold die die die。 right。

 And so this is called HTML injection， where what's happened is is the user was capable of typing something at the prompt that sort of took over the page。

 Now， usually they're doing something much more evil than just putting out the words die die die。

 they're doing things like taking your credit card number。

 they're taking things like if you're the teacher logged into a system and they go change their grade。

 they cause you to execute code in your browser that goes't change their grade。

 So this is HTML injection and the whole idea is you're breaking the HTML and putting code in that the bad person wants to put in on your computer。

 So let's take a look at what happens there， right， So you type this thing。

 And so this bit right here is exactly what the user typed And so they typed single double quote。

 blah， blah， blah， blah， blah blah。 But the problem is when the browser pars it。

 it doesn't really know what came from the code and what didn't come from the code。

 And so that's how。Sees it。 And so this is just an HTML text。 And this is a bold tag。

 And then this little quote here。 This crap shows up right down here。 see that crap showing up。

 but that's broken HTML， ultimately， actually it not broken HTML。

 because you can put a double code and a slash less than inside of it。

 But the user has sort of permuted or messed up the page And again。

 usually they put something bad in here。 something really bad that is going to do something to your system or do something to the server etc ce。

 et， et ce。 But that's the key。 the HTML injection is when they put some highly crafted character in that is designed in a form field。

 And because it's so easy to write code like this。 It's so easy write code like this that we end up in trouble as software developers。

 we have to have a little warning message go off any time we are producing HTML output with data that originally came from the user。

 So dollar old guess is not just any old variable， it is。



![](img/dc81736a817f303d2c3452885baf45fd_7.png)

Variable that came from user input。 So the danger is when you're printing out user input。

 you have to make sure that you do it in a very clean way。 Now， thankfully。

 there is a real easy way to fix this。 after all of my fuss。



![](img/dc81736a817f303d2c3452885baf45fd_9.png)

There is this function called HTML entities。 And what HTML entities does is if we go all the way back to the very beginning when I talked about HTML。

 I told you that if you're an HTML and you want to represent less than you say ampersand L T semicolon。

 If you want to represent a ampersand， you go ampersand a MP semicolon。

 And if you want to represent a double quote， which is the one that's causing my problem right here。

 you say ampleand， Q U O T or something like that。 These things are called HTML entities。

 These little alternate representations of these characters are HTML entities。

 So there is a function inside a Pp that just takes that data and converts anything that can be represented as an HTML entity。

 and print it out as an HTML entity。And so that's what this does we're running old guests through the HTML entities function。

 and then we're printing that out between the double quotes。

 so let's take a look at what comes out at that point。



![](img/dc81736a817f303d2c3452885baf45fd_11.png)

This is what comes out at that point， right， we see value equals。

 and now these are quote greater than less than B greater than。Less than。Greater than。

 So that's what they typed。 But now it's been converted by HTMLml entities to B HTMLm entities。

 And so what happens is when your browser parses this。

 it sees that is the beginning of the value and that is the end of the value。 because in there。

 there are no double quotes。 There is a double quote。

 but it's not represented in that string as a double quote。 And so the browser knows that。 Oh yeah。

 And so it puts the double quote right back in。 So you can submit the double quote。

 you submit as crazy as stuff as you want。 and away you go。 Now。

 if you're using the auto graders for this course， this is a thing that I check over and over and over again。

 because。

![](img/dc81736a817f303d2c3452885baf45fd_13.png)

It's the way that a lot of people make mistakes in building web apps that they open themselves up to what's called HTML injection。



![](img/dc81736a817f303d2c3452885baf45fd_15.png)

And you just have to keep in mind which and I'll remind you this like 8 million times over the rest of these next few lectures just so you know。

 things coming from the user are dangerous and we have to escape them。 That's called escaping Okay。

 so now we've talked about ways to take data and then put it back in a safe manner using HTML entities and now we'll talk about checking the data when it comes into the server before you do something with it。



![](img/dc81736a817f303d2c3452885baf45fd_17.png)

![](img/dc81736a817f303d2c3452885baf45fd_18.png)