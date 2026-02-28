# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p17 -17-Lets Debug Catbook Part 1 Answers (debug-challenge).zh_en -BV12Ux5zTE9p_p17-

![](img/1a232db6f1b106c0e9eb52878eaa12b3_0.png)

Everyone。So we're going to attack the catbook debugging challenge， step one。So before we get into it。

 I'm going to get check out， well I'll get reset。😊。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_2.png)

Just to make sure that I don't have anything there because I don't need anything and then I'll get check out debug challenge。

All right。I'll make sure that NPm start and。MPM run Do are running properly。

And now before we do anything， let's just see what's going on in， oh。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_4.png)

Yeah book。Okay， what does this error say， it says let cannot be used in the identifier in strict mode。

 I don't know what the heck that means。I don't know what the heck this means either。

But I do recognize， okay， syntax are in。The feed dotjSx file。So I'm going to click on that。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_6.png)

Or rather， I guess I'll just go here。 feeddo J S。 X。 Oh。

 and I get a red thing from my V S code saying reverse story objects， comm expected。

I don't know what that means， but I do know that it not then。

The argument to a then is a callback function。 This right here is not a function definition。

 A function definition has。Pheses where you put in the input and then an arrow and then curly braces to denote the body of the function。

So there that's one thing fixed。But then。Notice out here we're using this thing called stories response。

 so probably that would be that wouldn't be defined unless we defined it here。

I'm assuming that's going to be an input to my callback function。

Now what does St response actually represent well in this case。

 we do a get request to slash API/ storiesor。And then。We take whatever we got。

Which is stories response， and that gets fed into this callback function as stories response。

So then that's a list of all this different stories so we just reverse that list and then set that。

 set our react state。To the output of that or to the reverse list of stories that we got back from our get endpoint。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_8.png)

SoLet's see if that works。We'll refresh the page。

![](img/1a232db6f1b106c0e9eb52878eaa12b3_10.png)

Oops， need to make sure I save my file。Oh， 404 not found phenomenal。So in this case。

 since the error is on the browser side， it might be that I always like to check the browser console first。

So let's see O。Reference error props is not defined at single storyory， so let's go to singlestory。

jsX。

![](img/1a232db6f1b106c0e9eb52878eaa12b3_12.png)

And a here。We're using prop creator name and prop content clearly this single story component is supposed to take in props。

 but right now we are not taking that as an input to our function remember that a react component is just a function that takes in props or takes in some kind of information。

😊，And then， spits out。ACtm or more specifically JSX， which is basically like a react version of HTML。

😊，Based on those props， so we need to take in the props as an input。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_14.png)

All right， let's go back and see if we fixed things。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_16.png)

Okay， that's promising， this looks a little bit better than before。

 but oh in my console I have these errors， get something not found。😊，Okay， that's odd。

And it has says here it slash API slash comments。 And here I'll notice that I can't see the comments。

 So clearly there some issue with the get request that allows us。

To actually get and display our comments。And if I want to look into more detail as to what these requests actually are。

I can go to the Network tab。And see where。A so I get this error in the response that says root not found。

And then the request URL， it says local hosts slash API slash comments parent I D equals3。 Well。

 that's odd because typically when we send a get request， there use。

 there has to be a question mark that separates the。

The URL that we're requesting from the query parameters and here there's no question mark between comments and parent so that's probably where the error is coming from but we don't know where exactly that question mark。

Is。Like coming where that should go。So， here。Let's look at where this comments。

Get request is being sent。

![](img/1a232db6f1b106c0e9eb52878eaa12b3_18.png)

I could search around to find it， but I know off the top of my head that that's in card。

 I'm going to open up card。By the way， if you want to search for file， you could just do control。

 or I'm guessing on Mac command and P and then type in the name of the file。Okay right。

 so I'm going to look at where this get request is being made here。

I use the built in get function or the web lab staff provide a get function。

To get slash API slash comments with this parent。It seems like here is not where we're actually constructing and putting together the URL for the get request。

🤢，It seems like that logic has been compartmentalized into this get function。

 so let's go to where that's defined。I'll right click on that and go to go to definition and it takes me to utilities。

js。Ah here it is we do constant full path， which is just the full like。😊。

Thing that you might put in a URL bar， like the full URL basically。Is the endpoint。

Which in this case， when we called get。Was slash API slash comment so slash API slash comments plus。

The parameters that we passed in， which in this case is parent Pros。 ID。

It seems like we're supposed to have a question mark。

 but we don't have one between the end point and the parameter so I'm just going to add that。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_20.png)

And now let's see what happens。Let's refresh the page。 it works。

 As so now you'll notice in the network tab that these comments are made to the correct URL。

 Now they're being made to。😊，Our local host。Slash API slash comments and then the question mark and then parent。

And then our query parameters afterwards。Great， now we can correctly view our comments。All right。

 let's test things out and see if there are any other。Bugs that we might be able to find。嗯。Oh， well。

 one bug here is I typically were supposed to display whoever wrote the story。

 but right now these are just blank。So。I'm not getting any errors or anything。

 but it seems like something is not displaying that should be displaying。

 So let's look at where that might be coming from。I'm just going to pull up real quick。

To reference the react component tree。It seems like， okay， in feed。

 there's card and then a single story。I'm guessing single story or maybe card is where。

The creator is supposed to be displayed， so let's check both of those and see where the issue might be。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_22.png)

So let's go into single story。Here， single story is the one displaying the creator name。Here。

 and it's passed into single storyory as a prop。Well。

 it seems like there's no problem with single story just taking the prop taking the prop and displaying it。

Let's see where single story is where we're actually like creating a single story component。

 what's the parent of the single story component？If we look at our react component tree again。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_24.png)

Then we notice that the parent of single story is card。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_26.png)

What does that mean， Well， that means that。Card。

![](img/1a232db6f1b106c0e9eb52878eaa12b3_28.png)

Has this。Single story component defined within it。So remember that a parent and child relationship in react is just a。

It just means that there is a component inside of another component。

 so here there's a single story component inside of a card component right here。

 and that's what it means that single store is the child of card。😊，Okay。

 so here in card we're passing in an ID which looks like the same as what single storyory expects。

 and then we're passing in a prop called creator with the prop creator name that card received from its parent。

But that's kind of odd because here it names in in card when we're passing this prop into single story。

 we're naming it creator， whereas here， it looks like single story expects。

The prop to have an attribute called C name。So this disconnect is what creates the problem。

And so we just need to make sure that creator that this is named the exact same thing when it's being passed into the single story component。

😊，As when the single story component is receiving and using that problem。All right。

 let's see if it renders properly now。Cool， now I can see who wrote all of my stories。Alright。

 and then。Let's try posting a story。That works fine if I refresh the page。

 let's try posting a comment。And if I refresh， oh， what happened there， if I refreshed the page。

 my comment is gone， that's odd。So what does that mean Well， since I type in a comment。

Here and it displays properly on the front end， that means that the front end knows the comment that I type so there's no issue with me like typing stuff in and then hitting the submit button。

😊，It's some issue with how that information is getting sent to the back end or maybe how the information is getting stored in the back end some lack of。

Getting sent properly or getting stored properly so。This will require us to trace the whole line of。

Where of how this comment gets sent to the back end？



![](img/1a232db6f1b106c0e9eb52878eaa12b3_30.png)

Okay。So。😊，I know that when I type in。The comment and then hit the submit button that's in the new comment component。

 So I'll start my search there。 Let's go to new comment。Oh， that will be a new post input。

jsx and then here I've defined my new comment component。Okay。So。

Here I have a new post input with this on submit， and then I pass in a function called add comment。

And what happens with new post input is new post input takes in that prop the on cement for new comment。

And then it says the ons submitm should be a function that's triggered when the post is submitted。

So basically as soon as I hit the submit button I know that the punk function that I pass into the on submitm for a new post input will be called。

 so the function that's called in the case of a new comment is this add comment function which is defined right here so what I have in here is exactly what I want to happen when I hit the submit button。

😊，InIn the comment type of thing。Well， that's reasonable enough。唉。But then。

Here's something interesting。Um。The add new comment。Function is calling there sorry。

 this add comment function is calling。This add new comment function that was passed into new comment as a prop。

Well that's kind of odd， what is that doing？In that to figure out where that is。

 we need to figure out what the parent of new comment is。

So here I'm going to just take a look at my nifty component tree again and notice that here new comment is a child of。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_32.png)

Comments block。Okay。So let's look at comments block and see what's going on there。Just going to hear。

Comments block。Just as we expected， comments block imports new comments that's promising。

And here it looks like， oh。Here Anti Commons block where we have a new comment component。

But here it looks like we're just passing down in for the add new comment prop。

Passing down whatever we receive from comments， the parentent of comments block。

So here there's an identical prop add new comment that we're passing basically through comments block from whatever is above comments block。

So let's look at our component tree again， oh， it looks like new comment is the child of Common book which is child of card so let's go to look at card because it looks like the add new comment function。

😊，Might have been originally passed down to card and then to comments block and then to new comments。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_34.png)

If we open up card。jsx。Card is the parent of comments block。Oh。

 this looks promising and add new comment function。

 let's just make sure that this is exactly what we think it is okay。😊，So here inside card。

 there's a comments block because comments block is the child of card。As we can see。

 comments block is below card in our component tree。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_36.png)

And。That is passing in this annual comment function， which。Is defined right up here in card。Okay。

 so now we can figure out finally what this does。 What add new comment is actually doing。 here。

 it's just sending a。Post request to slash API slash comment with。

Whatever it receives as an input to this function。Okay。

 so this is a function that takes in some kind of input and just sends that input directly as the body of a post request to the back end。

😊，All right， interesting。When do we call this a new comment function？Well。

 in new post input but we saw earlier that this is the place where the add new comment function is called so this add new comment function is defined in card gets passed down through comments block and then to new comment which is this component here and then in new comment it calls this。

😊，Function。With。This whole representation of a comment as a JavaScript object。As the input。

So we call this function and what that's going to do is it's going to call the function that was defined here。

😊，With all of this。As the input。And then it's going to pass that into the post request to the back end so eventually what gets sent to the back end is this stuff right here that I've have highlighted。

So now we just need to make sure that what we have。

 what we're sending to the back end here is what we want to be sending to the back end and what the back end expects to be receiving。

So I'm going to get rid of these guys for the time being。

 so we can just compare this and I'll just reformat it a bit so it's a little easier to read。

Is what the backend expects to be receiving？our back end is defined in APIpi。js and lets screen that。



![](img/1a232db6f1b106c0e9eb52878eaa12b3_38.png)

And this is the post comment endpoint that's going to be receiving this。As its body。Okay， so。

Here we have。It just takes in the body， which is this comment， which is this thing。

And then add it to our list of comments。And then sends it back to the front end。Okay， interesting。

 well， that doesn't really quite tell us what we expect the comment to look like。But here's。嗯。

I suppose。Okay。One thing I could do is to use if I'm debugging， and I'm not sure what is。

What this back end expects。 Well， one， if I'm writing a backend。

 this is a good reason why we have API documentation， which this API is not super well documented so。

When you're making your apps， you typically want to write up a document that tells you that tells like you as the developer exactly what your backend expects to receive。

 but for the since we don't have that yet and we're going to add that once we do databases I'm just going to look at what the comments look like and just see if the format matches properly。

😊，So here I have underscore ID that's present here， okay， that's promising。

Here I have creatorator underscore name with the string。

Here I also have creator underscore name with a string， okay。Here I have parent and then some string。

 Oh， well， that's interesting。 This says parent' story。Is that a parrot？

Dang it's a different it's a different key name so basically JavaScriptscript won't be able to understand what that is and the reason that our bug looks the way it does。

😊，As in。I can add a new comment， but then when I refresh， it's all gone。Is because。

We're adding a comment to this that has the attribute parent story equal to something， not parent。

 but when we get the comments， remember we're filtering out for the comments where the attribute parent is equal to the parent that we're looking for。

And so。If these new comments that we're adding don't actually have the attribute like parent。

 just parent， not parent story。Then。Javascript isn't going to know what that is and parents going to be like this is going to say like undefined that's not going to be equal to anything all of our comments will just kind of be。

Disappeared。So we just need to change this。To be parent。And then hopefully we will be chill。Okay。

And we just refreshed and it stayed there。

![](img/1a232db6f1b106c0e9eb52878eaa12b3_40.png)

Amazing。And this is all of the debunk changes that we had for。The original debug challenge bridge。

This was。Hopefully the video， hopefully or the video went a little fast。

 but if you really take the time to sit down with it and make sure you understand how everything works。

 then I hope that it will be a good way for you to learn。Thank you。

