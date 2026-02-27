# 《Web开发快速入门｜6.962 Web Development Crash Course IAP 2025》中英字幕 p19 -19-Lets Debug Catbook Part 3 Answers (debug-challenge-3).zh_en -BV12Ux5zTE9p_p19-

![](img/42605c016254f67977f3cbf1ccd968b1_0.png)

Good morning， amazing students， we are going to go over debug challengeenge three。

 so I've checked out already the debug challengeenge three branchn and now I'm going to look at cat and see what peck is wrong with it。



![](img/42605c016254f67977f3cbf1ccd968b1_2.png)

![](img/42605c016254f67977f3cbf1ccd968b1_3.png)

怎噶啦。Make sure that I've refreshed cat bug and when I check out to this branch I'm going to end my server NPm start and rempm start so that I don't have。

Stories all messed up from the previous bang it was doing。



![](img/42605c016254f67977f3cbf1ccd968b1_5.png)

All right， let's try and post a story and see you would have oh， well。

 one thing that I noticed already on the homepage is that comments are not displaying properly。😊，Od。

So that probably means that there's something wrong with the get request from comments because I know there are some comments that should be there。

Normally there are。And I am making requests to comments。

 So let's just see what's going on in the request that I have here。

 just going to open one of these up。The request URL looks right。

 I'm using slash comments and then the parent and then the ID， a get request， got a success back。

All right， now let's see what I got back。So this is what I sent in the request just this query parameters and this is what I got as a response。

 oh， okay， I got nothing。But I'm not sure if that just means there's no comments under this or under this particular story or what。

 so let's check the others also nothing。😊，HAlso nothing。

 so that probably means there's something wrong on the server's side。😊。

That makes it so that we don't get anything for these comments Now a quick side note is that the reason that I love using this network tab for debugging and looking at what the contents of the requests and response are is that I can check to see if things look the way that I expect and if they look the way that I expect then or like I guess looking at the network tab allows us to see what's actually being sent by the client and the server and helps us isolate whether the error might be on the front end side or the back end side。

😊，I think the air is probably on the back end because I should be getting back something here。

 but I'm not。

![](img/42605c016254f67977f3cbf1ccd968b1_7.png)

So let's open up our API。js and see what we're。Stending back。For slash comments。Okay。

 here we're sending back comments and then we're filtering out。The ones that match。The parrot。Okay。

 that seems。Like it should be。啊。Let's double check that。

We're getting the information from the request properly。Actually。😊。

You know what I'm going to do for the sake of debugging， I'm going to add a console log here。

I'm going to log whatever I'm getting back from the request this。Value。

And notice that here I'm putting my console log in API。js。

 which is on the backend that's on the server side。

 so this console log will not appear in my browser console。

 it'll actually appear in the terminal where I'm running MPM start。

I'm going to run this again so I can get that run that get request to comments again okay。

 same thing still don't see them here oh。Interesting。So Icon。t logs wreckbodied。

 parent and it says undefined， but here I should have sent a parent of ID3 ID2 ID1 and oh， well。



![](img/42605c016254f67977f3cbf1ccd968b1_9.png)

![](img/42605c016254f67977f3cbf1ccd968b1_10.png)

Here's the thing。This is Re dot body， which is assuming we sent something in the body of the HTTP request。

 but remember that here。😊。

![](img/42605c016254f67977f3cbf1ccd968b1_12.png)

So if we had sent something in the body， it would be in the payload here， but no。

 here all we put in is a query parameter。Qury parameter that goes after the question mark in the URL bar。

 so this should not be wrecked out body without parent， this should be wrecked outqueried all parent。

😊。

![](img/42605c016254f67977f3cbf1ccd968b1_14.png)

。And I use the console log here to help me figure that out。



![](img/42605c016254f67977f3cbf1ccd968b1_16.png)

Okay。😊，So that was one thing fixed。 Let's go back， and。See if we can get comments properly， amazing。

 that works。 Now let's try posting a new story。😊，Okay， that didn't work， try refreshing。

So when I refresh the page， the story pops up but it doesn't have any content and I did definitely type content in there。

So there's probably some issue with either the front end code that sends the post request to post a new story or the backend code that takes a new story and processes it and adds it。

Let's take a look at the request that's being sent here。

And recall that if you're ever confused about what the requests and responses should look like。

This information is in the LesD bugug cap slides and you can reference it。

So here I would be referencing this slide to post a new story and just looking and seeing， okay。

 like what what are these requests supposed to be doing？

But I will not be doing that in these videos because you can just reference that yourself。

So let's look at the Network tab and see what's going on。So， we're making a。Request to， oh wait。

 this is the slash stories to get all of the stories。

 I want to get the request when I posted news stories。 So I'm going to leave the network tab open。

 try posting a new one。嗯。Okay， here we go。So now we're making a request to localhos/ APIpi/lashtory。

Request header。Okay。What are we sending in the request？Okay。

 so we're sending in an object that has content creator name and an ID that seems right。

I think that's all the fields that a story should have so let's see what the responses that we're getting back oh。

We're not getting back any response， that's odd。Usually when we post a new story。

 we're supposed to be getting back a response from the server that is the exact same as what we sent the story that we just posted。

So it seems like what's coming from the client side is right。

 so i'm going to guess that the problem is inside the server let's look at the API where。



![](img/42605c016254f67977f3cbf1ccd968b1_18.png)

We call Ro dot yes， where we've listened for post request this last story and we do stuff with it。Oh。

Well， here。One thing that's wrong。Is we're not sending back the story。

Because we create a new story and we push it。We're not sending that back to the front end。不。

So let's try this。Let's try doing Resdo send New story。



![](img/42605c016254f67977f3cbf1ccd968b1_20.png)

Save that。And then refresh the page， try posting another story again。And。

We'll find that request Okay， this is the。Content create a name and ID。And let's go to the response。

Oh oh。That's not what it should be。Because we're sending back， let's see。

 what are we sending back in this start we're sending back new story。

 but what we actually ended up sending was an empty JavaScript object so clearly there's some problem with this。

😊。

![](img/42605c016254f67977f3cbf1ccd968b1_22.png)

Clearly New story is not what it should be oh。Because New storyory is Redo query。

And Redot query is the query parameters that were sent in。St from the front end to the back end。

And that's not right because this typically in a post request we send us information in the request body now you can see that this is actually what we are sending from the front end because。

😊。

![](img/42605c016254f67977f3cbf1ccd968b1_24.png)

So here we say you see we have a post request， but you can see that there's no question mark。

 no query parameters after the URL here。😊，And payload is the tab where we can see the request body。

 so this is if you see something in payload lets you know that that's the body of the HP request and it has to be post request。

嗯。

![](img/42605c016254f67977f3cbf1ccd968b1_26.png)

So this is being set in the request body。😊，But here in the server。

We're trying to access Retat query and it's empty because there's no query parameters。



![](img/42605c016254f67977f3cbf1ccd968b1_28.png)

Let's change that direct do body and hopefully that will solve all of our problems。Oh。Amazing。

 that worked。Okay， now let's try adding some comments and see what happens。All right， that works。

 refresh the page， oh man， man。So we refresh the page in the comments gone。What does that mean Well。

 it means since we were able to type and submit this comment， okay。

 the problem was not in the front end code that displays the comment。

 but the problem could have been either。In the front end code that sends that post request to post a new comment or in the front end code that or sorry。

 in the back end code that actually processes that request to post a new comment。

So let's try this again。And this time， take a look at the。

Request that's being sent when I try and post a new comment。Okay。

 I got back a 200 okay from the server， we're sending it to API slash comment。

 it's a post request seems all right。😊，And then what are we sending in the body of the post request we're sending content。

 creator name， parent and underscore ID those fields all look right。 I can open up。



![](img/42605c016254f67977f3cbf1ccd968b1_30.png)

My APIpi。js and just check this and make sure that it looks right， but those are all the same fields。



![](img/42605c016254f67977f3cbf1ccd968b1_32.png)

So。Let's look at the response now from the server。Oh。

 and it looks like the server sending back the response perfectly fine。



![](img/42605c016254f67977f3cbf1ccd968b1_34.png)

I guess that makes sense because if the server recall that in the client。😊，On what is a card。jsx？

When we post a new comment。We post it then we take back then we send back or the the comment object that we receive from the server when we post it is what we add to the end of our comments react date so what we're doing is we're sending our post requests and then we're。



![](img/42605c016254f67977f3cbf1ccd968b1_36.png)

Getting the response back from the server and adding it to our front end。

 So if we didn't get the response back from the server。

 nothing would happen when I type in a comment。That was a mistake by spelling。And then。

Hit the submit button that immediately pops up， which means that。As we see here。

 the server is sending back something totally fine。And。The front end is displaying it。

 but then when I refresh， it's all gone， so that means that there's probably some problem with the server that the server is not storing it the way that it should be。



![](img/42605c016254f67977f3cbf1ccd968b1_38.png)

So let's look at api。js and see what's happening when we post a comment route。tpost/com。😊。

We take wreck out body， which is all it should be， and then we send it back。Oh。Well。

 that's pretty straightforward。Taking it and sending it back。

 but we're not saving it on the server anywhere。Where do we want to save it in the server。

 we want to save it in this comments list。So let's do comment stop push。

 we're adding that to the end of the list。New comment。All right。😊。

So I made this change and now I'm going to try again。



![](img/42605c016254f67977f3cbf1ccd968b1_40.png)

Refresh the page。😮，And my host is going。嗯。Interesting。

So let's see what happens when I try and make a new post。And then I refresh the page。

And it's still there。Re first page。And my comments say， okay。

 I am not going to worry about the fact that my story disappeared earlier because I think that might have been left over from the bug that I had earlier。

Let me just test it out a little bit more to make sure it still works。

Refresh the page and everything stays all right， amazing。

So that was all of the bugs that needed to be fixed for debug challengeen three。

 I'll see you in the last step。

![](img/42605c016254f67977f3cbf1ccd968b1_42.png)