# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P97：33_星球大战API接口演示（第二部分）.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

Welcome back to a continuation of our Star Wars API， we have loaded all of our data。

 Star retrieved it， we've expired it， we found the new links and we've loaded it all and so we have we're completely full。

 I can say select count URL here。Select count URL。From Swy。嗯。So we're all good。

 we got 207 documents loaded。And so let's play right。

 so we can look for the URL inside the body tag and convert it right， So there we got a string。

We can ask for the URL of body where it contains Director Carl and George Lucas。

So we can have wear cls。It's working now again， there's no indexes involved in here where we don't have an index yet。



![](img/1abeb2513ff62456969e1857ead8d2d0_1.png)

So if we do an explain， we're going to find that that just is a sequential scan。

 select body URL from swapy where Bo contains director George Lucas。

 and it's a sequential scan is exactly what we'd expect we haven't put anything in so let's go ahead and insert 4000 meaningless rows of Doddgeneon race car。



![](img/1abeb2513ff62456969e1857ead8d2d0_3.png)

SQL it doesn't even have a URL field or nothing， so it's just extra crud 4001 and now we're going to create our index。

 we're going to create a generalized reverse index swapy Gin on the body with pathOs and so JSON PathOs gives me the key value pairs and allows me to look up by key value pair。



![](img/1abeb2513ff62456969e1857ead8d2d0_5.png)

![](img/1abeb2513ff62456969e1857ead8d2d0_6.png)

It's kind of a smoother thing so and then we got to be careful because it might take a little while let's take a look at。

Let's do an explain select to see if we can turn this select body URL from swapy where body contains George Lucas。

 well， it's done already， so I don't have to go about the thing and like hey。

 let's wait a while sometimes it happens fast sometimes it doesn't happen fast but if again if you do this explain select and it doesn't get you what you want。

Yeah。Wait a bit， have a cup of coffee， come back， shouldn't be too much coffee。Okay。

 so we got an in index。

![](img/1abeb2513ff62456969e1857ead8d2d0_8.png)

So there we go。 So let's， let's like look at some stuff here。

 Let's say I want to find the films that aren't。George Lucas， so we can say what are the films？

That George Lucas was the director of do that。嗯。There's four of them。

So let's see if we can figure out how find the films that George Lucas is not the director of。

 so I put a big knotd around this， knot body contains George Lucas， JON B。I cast that to Json B。



![](img/1abeb2513ff62456969e1857ead8d2d0_10.png)

And oops， we got a whole bunch of URLs， a lot of URLs， not so good， right， and there's even blanks。

 there's even page。 Some of those pages are giving me trouble because I put all that extra cru in to make it big。

 but。

![](img/1abeb2513ff62456969e1857ead8d2d0_12.png)

![](img/1abeb2513ff62456969e1857ead8d2d0_13.png)

So we can fix that with another aware clause right。

 we can say we can ask what are the things where the body URL is got a pattern of HDPS swapy co API films followed by something so we can use a light clause so we can of course do that and then we'll find。

Only the films。 so those are the films， there's only six records that contain films。

And if we do an explain， we will。

![](img/1abeb2513ff62456969e1857ead8d2d0_15.png)

The bummed out because we'll see that it's a sequential scan。

 Now one of the things you probably could do is you could say。

 you know what I think what I'm going to do is put a B3 index on body URL and that should hit on prefix queries we could see。



![](img/1abeb2513ff62456969e1857ead8d2d0_17.png)

But we can look for the films that aren't directed by George Lucas。

 the Star Wars films not directed by George Lucas by saying not body contains director George Lucas and body is like a film is a film。

 so that will do it and we will find it， but that will be a sequential scan。

 so that will show us the films， the three films in the Star Wars that were not directed by George Lucas。

 which is fun。

![](img/1abeb2513ff62456969e1857ead8d2d0_19.png)

![](img/1abeb2513ff62456969e1857ead8d2d0_20.png)

So。🤧嗯。Let's。Yeah。So we can do this light clause， we can see you know， the URL， the people clauses。

 we can see the people with a light clauses， and you can。

 in a sense you could think of the prefix of this URL as a type， you can see all the species。



![](img/1abeb2513ff62456969e1857ead8d2d0_22.png)

Species and their URLs， and that would be kind of a useful thing to do。

 but it means that everything is a sequential scan。



![](img/1abeb2513ff62456969e1857ead8d2d0_24.png)

So what we're going to do is we are going to put a little effort and we're going to hack the JsonN。

Okay we're going to hack to JSsonN we've done this before and so we're going to hack the JSON by a regular expression and so first I'm going to show you the regular expression the regular expression is HB swappy co API and then parentheses is the start of an extraction bracket A through Z is the letters A through Z plus means one or more and the extraction So if you run this。

And all it's going to do is the regular expression extraction on the URL。

But you see that it says films， if I make this。

![](img/1abeb2513ff62456969e1857ead8d2d0_26.png)

Limit 10。See film species， whatever。 Now I want to these nulls are those those neon records that I put in。

 so don't worry too much about that。Um now。If you recall in the previous thing when we're going to mess with the JSON itself。

 we have to ultimately use the concatenation operator here。

 we're going to have to do the JN B concatenation this is a string concatenation double vertical bars is concatenation so eventually we've got to do a JN B concatenation which means we're going to eventually construct a big long string and then convert it to JN B and then merge that into body just like we did before so。

Let's start by looking at this string。Which is really is a string concatenation here。

 type colon concatenated with the the the the regular expression that pulls the the the word。

 the type out， and then in double quote。 So first we got to build。

We've got to build a string that represents the new JSON that we want to put in。



![](img/1abeb2513ff62456969e1857ead8d2d0_28.png)

And so this is a string type colon films， right， That is the new Json。 Now。

 in order to blend it with existing Json B， that's a Json string。

 we've got to cast that to JsonN B by adding the Json B cast on there。 right。

 So we'll cast that to Json B。

![](img/1abeb2513ff62456969e1857ead8d2d0_30.png)

So it's going to look roughly the same， except that this is Json B， a type of Json B。

 which means we can blend it together。 And so if we now look at this， we're going to select the body。



![](img/1abeb2513ff62456969e1857ead8d2d0_32.png)

This is going to be gigantic。Concatenated a Json concatenation， not a string of this big。

 long string converted Json B。And so I'll select this， but it'll be really big。Yeah。

So somewhere in here， let's find it。Let's find it。It's fine type。Type film， right， so we got the URL。

 but we extracted this little bit in type films。Okay。

 so we've added a bit to the JSON and we've done this well。

 we added one to account in the previous in one of the previous examples。

 but now we've added something to this JSON， right？So we're going to do an update， which is， again。

 this whole body concatenated with Json B。 that's the record we just selected。

 So we're going to take and extract the， pull out the body for all of the records。

 set it to be the add the tight variable to it。 so this is going to do it for all the records。

So it've updated 4，208 records， and if you now you can select those records。Select。Swappy。bodydy。

From， oh， oh， sorry。 Yeah， wrong， wrong， wrong。Body。Type。Com onわり。URL。From。Swappy。Limit 5。

Why did I get wrong， Why did I get wrong？swapppy limit oh， I'm getting too many of the blank ones。

 so don't worry too much about that。Okay， so。So now I've added that。So now I can use this in。

A we claws， right， select body URL from Swwampy， where body is type species。系。Limit 10。

So I'm going to pull out the URL and I'm going to use a wear clauses which will actually find me some stuff and that's because these blank ones it went past the blank ones and got to some that actually had type equal species because these neon。

 those are all the neon ones that I just did so the dang thing would actually do my explains the right way。

So。I now have this new thing。 I can talk to it。 my index should understand it。

 and so I should be able to explain that。 And if all goes well， the new field that I did。



![](img/1abeb2513ff62456969e1857ead8d2d0_34.png)

Should do a bit mapap check， swapy g， this update statement， this update statement here。



![](img/1abeb2513ff62456969e1857ead8d2d0_36.png)

![](img/1abeb2513ff62456969e1857ead8d2d0_37.png)

It updated it and then within like a couple of seconds。

 the gin was up to date and if I had done this update and like right away did the explain select it。

 the index might not have been completely updated， so these indexes lag a little bit and this is where I keep saying that insert performance update performance versus the query performance and Jin is this is a gin with text offs so it's the most difficult to update。

 but with only 4001 records it's only a few seconds。And so that shows you how to like augment it。

 which is another thing。 and so now I can actually say， you know， show me。

What's going on with George Lucas？

![](img/1abeb2513ff62456969e1857ead8d2d0_39.png)

And let's actually just run that select statement， select URL。George Lucas。

And I can explain that and let me not that。

![](img/1abeb2513ff62456969e1857ead8d2d0_41.png)

He had a knot oops， not a note。I sure hope that I'm going to get my index to work because I worked really hard to make this work。

So we're saying。Oh， I think I might not parentheses wrong here。Yeah coat right in front of you。

 hopefully I get it right。It's not as easy as it looks， let's see if I got it。No what happened。



![](img/1abeb2513ff62456969e1857ead8d2d0_43.png)

What just happened？The body doesn't contain George Lucas type films。Oh。Yeah， so this one。

 this is not going to work because this is all the things that don't have the combination of type films。

 So let me try to fix this。Doる。It's going to take a little work。sSee if I could make this work。

So the first knot。And。bodydy。Contains。Type films。嗯。Let's get this one， right。

So what I'm going to say is I'm looking for things that have the body that contain tight films。

I'm going to have an a of extra parenthesesis back there。

It would probably be better if I make more sense if I flipped this。To the end。make more sense to me。

 at least。So if I got my syntax right， I'm interested in URLs that have a body of tight films and do not have the director of George Lucas。

And so I got to have my parentheses， oh， I'm pretty sure that's going to work。嗯， yes。Now comes the。



![](img/1abeb2513ff62456969e1857ead8d2d0_45.png)

Big test。Cs。Get rid of those。 Those aren't any fun。 Those don't teach us anything。

The always payoff is， did I get this in a way that my indexes worked？And I sure hope so。

 so let's run the explain。Hello， Postgress， did my indexes work。 Yy， my indexes work。

 I always feel great when I don't see sequential scan。 I see I heap scan。 I see that Sppy gin worked。

😊，So there you go， you will see this without the must there we go。

 type is films and body is not the and the director is not George Lucas。There are。3。

Three films in the Star Wars set for which George Lucas was not the director。



![](img/1abeb2513ff62456969e1857ead8d2d0_47.png)

And。And that is all I have for you， I hope， as always that you found this demonstration useful。

 cheers。