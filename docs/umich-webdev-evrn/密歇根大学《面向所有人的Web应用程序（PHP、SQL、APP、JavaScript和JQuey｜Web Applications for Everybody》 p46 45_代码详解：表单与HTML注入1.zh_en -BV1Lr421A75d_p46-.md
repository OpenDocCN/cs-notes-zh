# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p46 45_代码详解：表单与HTML注入1.zh_en -BV1Lr421A75d_p46-

Hello and welcome to Web applications for everybody。 Today， we're playing with a bit of the code。

 sample code from the from the course doing some of the form code。 So let's take a look at the forms。

 a form1 dot PhP， the idea of a form tag in。

![](img/398e0a3e1840668173960960252eb859_1.png)

![](img/398e0a3e1840668173960960252eb859_2.png)

HtML is to describe some input that allows the user to type in or interact with and then submit data back to the screen。

 So you have to think that at least the way this works is it comes through with a get request and print this out and then when we hit the submit button。

 it goes to a new Re response cycle。 So there's the source and let's go into developer console so you can watch what's going on。

 take a look at the network。 Okay so when I hit enter and do the original get request there's the get request or Form Form1 do PhP and it just runs this code and there's no PhP in here。

 but it's H and so it just prints that out。

![](img/398e0a3e1840668173960960252eb859_4.png)

![](img/398e0a3e1840668173960960252eb859_5.png)

![](img/398e0a3e1840668173960960252eb859_6.png)

![](img/398e0a3e1840668173960960252eb859_7.png)

And then basically the form describes a bit of text area that says， oh。

 we're going to put an input area type equals text。

 and then this name equals guess tells the browser how to submit this data that we're going to enter to the server。



![](img/398e0a3e1840668173960960252eb859_9.png)

And I D equals guests。 the fact that I use the same one doesn't matter。

 I'm using the I has to do with marking this label。

 has to do with semantically marking up your code for accessibility。

 And that is that we can look when we're visually looking at this。 We can know that， oh yeah。

 this seems to be associated with that。 But for a screen reader。

 they want a more accurate and clear association。 So this I D。

 that's really just for Cs name equals guests name equals on input tags are the things that are sent to the server。

 So input type equals submit shows a submit button andtys text gives us a little spot， so。



![](img/398e0a3e1840668173960960252eb859_11.png)

If we say 12 and then we press submit。It is going to do another request response cycle， right。

 and going to run this code again， except at this time， it's going to add this parameter。

 question mark guess equals 12。 And so that's how that works。 And now inside of our PP code。

 we are going to want to be able to take a look at that。

 And P P has some magical variables that are superg called dollar underscore get。

 And what dollar underscore get does。 Let's take a look at Form 2 do P P。



![](img/398e0a3e1840668173960960252eb859_13.png)

![](img/398e0a3e1840668173960960252eb859_14.png)

Well， I'll just leave the guess equals 12 on what dollar get does。

Is dollar get takes and PhP parss these key value pairs on the query string after the question mark and then gives us things in here。

 And if I put like  a% x equals 42， then it would give me guess equals 12 and x equals 42。

 And so then this allows us inside of our PP code to sort of detect the time when it's coming in with just no parameters versus parameters are being sent。

 And we， So there's no parameters and we're printing out an empty array。



![](img/398e0a3e1840668173960960252eb859_16.png)

![](img/398e0a3e1840668173960960252eb859_17.png)

![](img/398e0a3e1840668173960960252eb859_18.png)

![](img/398e0a3e1840668173960960252eb859_19.png)

And we， as the developer， are giving our user a easy way to send us data。

 And it just concatenated on。 And so that's， that's form2 Ph P。



![](img/398e0a3e1840668173960960252eb859_21.png)

Form 3 dot PhP says there are two ways to send this data。 One way is as parameters。

 but this gets kind of ugly， and there are reasons not to do it。

 and you're not supposed to modify data。

![](img/398e0a3e1840668173960960252eb859_23.png)

Now， guessing in a guessing game is probably okay to use as a get but。



![](img/398e0a3e1840668173960960252eb859_25.png)

All we have to do to switch to sending the post instead of get is to say method equals post。

 So the form is exactly the same constructed in exactly the same way。

 And we have get parameters and dollar underscore post is a new thing。

 I'll take off this guess equals 12 and switch to form。



![](img/398e0a3e1840668173960960252eb859_27.png)

3 dot Ph H P。 And so I did， that's a get request。 If I take a look here， that was a get request。

 So if I come here and I hit the enter key， that forces a get request to that URL。

 hittingtting refresh does not as we'll soon see， doesn't always force a refresh。

 If the last operation was opposed， it does the post， if the last operation was a get。

 But in this particular bit of code here。View page source。In this particular bit of code。

 we have told it that we want to send the data that you entered by the user， like our 1，2，3。

 is sent by a post。 And so you'll see。That if we look at what's gone on here。

 it's sent a post to this URL。 and if you cruise down。

 the data was actually sent as part of what's called form data in a format called URL encoded。

 and we could look at more detail。 But the first thing you'll notice is it's not on the URL as a question mark as a query parameter。

 And that's because it's actually sent as part of the connection。

 the connection connects to WA4E do com on port 80 sends post to that URL。

 and then it sends these request headers。 These are actually part of the what is sent and then a blank line and then form data is sent。

 The response headers are what come back to our application after in the request response cycle。

And basically， just like with get。

![](img/398e0a3e1840668173960960252eb859_29.png)

Dollar post is created for us before the first line of our program， and it just handles this stuff。

 and it's all magic。 You make a form， and then when the post happens。

 Doll underscore post has key value pairs that are properly set for us。



![](img/398e0a3e1840668173960960252eb859_31.png)

![](img/398e0a3e1840668173960960252eb859_32.png)

Okay， so let's take a look at。4。phP， the one thing that you'll notice here is my previous guess was 123。

 but it didn't show up here。

![](img/398e0a3e1840668173960960252eb859_34.png)

It's so often that forms put their old data there 125 submit， where do 125 go。

 we kind of expect that the 125 is going to be there。But it's not。

 And it turns out that we have to just explicitly put it there。

 And so it's so common that developers grab this post data as it comes in and echo it back right there so you can actually modify it。

 So if your guess was something， you know along and you wanted to change it。 right， It's not there。

 I wish it were changed。 And so in Form 4， we show how to solve that problem。So let's go to Form 4。



![](img/398e0a3e1840668173960960252eb859_36.png)

And view the source of form4。Which of course， is also over here。

And so what we're going to do is we know this code is going to run once to do the get。

 And that just is drawing the form。 That's when I hit this enter key。

 and it draws it and it sends a get， sends a get， right， we。

 when I hit the button because method equals post， it's going to send us a post request。

 And the key is is I just have as input tag。 and I add value equals。

 And then this little bit of stuff。 And this is a contraction for P P to print out this variable。

 and the variable is if there is data in post sub guess， I'm going to take that data， Otherwise。

 it's a blank。 And so if I do a view source here。

![](img/398e0a3e1840668173960960252eb859_38.png)

![](img/398e0a3e1840668173960960252eb859_39.png)

![](img/398e0a3e1840668173960960252eb859_40.png)

In this value here， there is no data because that was a get request， the post is not set。

 But when I do a dollar， when I send a post like， Ho， this is not a number。And hit submit。Well。

 it comes back。 And so if I now do a view source on this page。

 you will see that my Ph P code particularly put this in right here。

 using this little bit right here to say， oh， generate the HTML。

 but replace this little variable old guess and whatevers an old guess。

 which came in in posts of guess。

![](img/398e0a3e1840668173960960252eb859_42.png)

![](img/398e0a3e1840668173960960252eb859_43.png)

Okay， now a nice thing is now I can fix this。 I go， oh， I type that wrong。 And now it works。

 And so the idea of here's a is a post still。 But the idea that this stuff is persistent is not something the browser does for you automatically。

 Sometimes the browser does autofi in， which is tack E。Of of certain fields。

 it does autofilin of those fields， but in my browser， they're yellow。

 which is different than the server restoring the data。Okay。So。



![](img/398e0a3e1840668173960960252eb859_45.png)

That's cool。 That's easy。 But in doing this， we just violated the first and most fundamental rule of P P application。

 security。In the first and most fundamental rule of PhP security， and you can go on Google like。



![](img/398e0a3e1840668173960960252eb859_47.png)

Cross。Site scripting and learn more about this。 Cross sight scripting。 Oh blah， blah， blah。

 It's excess S S injecting。 blah， blah， blah。 go ahead and read all that。 Okay， and it's nasty。

 And how did we just。🤢。

![](img/398e0a3e1840668173960960252eb859_49.png)

Allow the user into our back。 Well， the problem is。

 is this post sub guess right here is data that came from the user。

 Whatever I typed here shows up here。 And so if I am clever， I can actually make old guests contain。

Sort of a snippet of valid HTML。 So what I'm going to do is I'm going to make my old guess start with a double quote。



![](img/398e0a3e1840668173960960252eb859_51.png)

And。I'm going to say double quote slash。 And that's going to end the input tag。

 And then I'm going to start another input tag。 type equal submit value equals monster。

 But notice that I only have the opening quote and not the closes quote。

 Now Let's put a B R tag in here or an HR tag。So there is an HR tag as well。

And so when I submit this， you're going to see what happens。So now。I have this monster button。

And the monster button is something that I created。

 I could do something evil with this little monster button。 How did that happen。

 Let's take a look at the view sources of this。And you can see with syntax coloring。 Now。

 this part here came out of my PhP， and this part here came out of my PhP， but all this stuff。

All that stuff there came from me typing。 But the browser， when it sees this， it's like， oh， no。

 that's not good。 And so then。The browser sees that as an input tag。 It sees that as an HR tag。

 even though this came for me， sees this as an input tag and。This is the input tag。

 Even though this last part of the input tag came from the Ph。 P。 It doesn't know the difference。

 It just can't tell。 Okay， And so that's really bad because this could do something like take your bank account cookies and send them to my evil server。

 if I was super clever and did this。 So this is called cross sight scripting。

 which means that I have typed something into your application。 Hopefully。

 I get someone else to stumble into my typed in stuff。 So you're viewing somebody else's information。

 And then in that information。 It is stealing something from you。 So that's really bad。

 So this is like this is like。

![](img/398e0a3e1840668173960960252eb859_53.png)

Terrible， terrible PhP。Good news。 Not hard to fix。Take a look at form 5 do Ph P。

 There is this function called H entities。 And as long as you print out H entities of that value instead of the value directly。

 then you're generally safe。 And that has to do with this。 So let's go to form 5 dot P P。



![](img/398e0a3e1840668173960960252eb859_55.png)

And let's type that same。Same thing here。Got it here。Okay。

 we're going to type this same thing and we're going to submit it and。It's going be like， okay。

 And now if I do a view page source， it'll be far more clear as to what is going on。

 So this part came from my P P。This part came from my Ph P。 This part came from the user。

 But what H L entities did is it saw dangerous characters like double greater than less than greater than less than single quote。

double quote and it turned them into these things called HTML entities and HTML entities are a sort of ampersand form of those characters。

 but now even though the browser knows that's a quote and it shows it as a quote right here。

 it does not then allow this user to escape and start entering HTML into my background document。

You can actually note that this kind of messed up because my debug output messed up， right。

 because my pre tagag is still printing that value up without filtering it。



![](img/398e0a3e1840668173960960252eb859_57.png)

So be careful because I've fixed this error， I mean， this error right here。

 but I didn't fix that error right there。Okay so just rule number one is if this data came eventually or at any point came from the user。

 just wrap it in HTML entitiesities， you can wrap things in HTML entities that didn't come from the user it doesn't harm it it's harmless but always for user data wrap it I tend not to wrap everything in HTML entities so that I can kind of mentally know where I was getting user data so that is a zip through some of the forms sample code for web applications for everybody we'll talk about some of these others in an upcoming video so again I think hope this was helpful。



![](img/398e0a3e1840668173960960252eb859_59.png)

![](img/398e0a3e1840668173960960252eb859_60.png)

![](img/398e0a3e1840668173960960252eb859_61.png)