# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p40 14_03_06_Django模板语言-DTL.zh_en -BV1Kt421V7EE_p40-

So now we're going to talk about the actual template language as I mentioned before there's more than one templating language we're using the default one and I think it's actually one of the better ones。

 this whole notion of double curly braces there's all kind of templating engines and a lot of them use these double curly braces sometimes there's one called mustache because the curly braces looked like a mustache so this double curly braces。

 you learn it in django and you'll find it all kinds of other places。

 I've used it in frontend processing， this is backend processing because we're doing all the substitution in the backend。



![](img/931c9321510c5c5beba61b5fd553efb1_1.png)

So there's basically a couple things you can do， the double curly braces。

Do substitution and one thing that's cool about this if you recall I talked about how you have to escape data that came from the user anything in the double curly braces is automatically escaped as a matter of fact you have to do something to not escape it because it turns out that 98% of the time you want to escape data that you're printing out because it doesn't change what it looks like but it does make sure that it's safe if you add this vertical bar safe afterwards this vertical bar safe afterwards that's like a modifier I think it's called a filter injango that says look don't run this don't run that filter on it to do the HTML entities just do it as is I know there's maybe be HTML in that but I've taken care of that because I am the application developer。



![](img/931c9321510c5c5beba61b5fd553efb1_3.png)

You can call functions。Like with the code is the percent curly brace percent and and there you tend to call a code。

 this is like code this is like calling a method or a utility code and so the first part of this is what you're calling and then later you can have some parameter so this URL says I want to find a URL for the view cat detail and I'm going to take the number that is the current cat primary key for the cat record and put that on as the URL as well the author in this case is a and we'll see this later is a model item and get absolute URL is a method inside that model item you can have sort of ifs and if then else's it's kind of Python like which is nice and that you don't really have to learn new things there is looping code that's in there and like a for loop that we'll talk about in a bit and then there is X blocks that can be replaced so you can have a template that sort of pulls in another template and then substitute。

In part of it， so you can have whole blocks of substitution， not just little strings of substitution。

 and so we'll talk about each of these in turn。

![](img/931c9321510c5c5beba61b5fd553efb1_5.png)

So here we go we'll start with a real simple one and we're and you'll notice that in this particular simple one。

 we have no parameters on the command on the URL we so we don't have any parameters here。

 I'm going back to a nonclass style just a simple function and I'm not sending a context the context would be the third parameter on the render call and so I'm just saying hey and this is what you do。



![](img/931c9321510c5c5beba61b5fd553efb1_7.png)

When you just have some static HTML that you don't really need to change anything。

 and so that's what's sitting in here， it's just a simple page。

 there's this thing called a builtin template view class that sort of does exactly this thing that just grabs a template。

 grabs a file， turns into an HB response， and sends it back to Django。

 so that's just a super simple template。Now here's one we're going to take a parameter to the context and I'm not taking it from the command line quite yet。

 I'm just going to make the parameter always be 42 and the key is this is a key and this is a value so Zap in this case is the key and 42 is the value。

I often call this variable context， but the fact that's just a mnemonic memory thing for me。

 context or CTX is what I tend to call it and now I'm passing in the， the template。

 this template here， the guest at HTML template and it has one little。

Curly brace substitution and remember that does。Escaping for us automatically so there's no need to use escape the way there was when we're doing this via concatenation that alone is a good reason to use templates and so this ends up sending out your guess is 42 so this is just really focusing on what's in that context and how the things come out of the context this name here Zap in the context means pull the thing out of the context under the string name Zap and then it substitutes。

The results like the 42， so instead of it saying guess what Zap， it's your guess is 42 so。

Really focusing on the substitution。So this is showing us how we do the safe stuff in case you actually want to pass some HTML into a template and actually want it to render as HTML。

 not as HTML entities or。

![](img/931c9321510c5c5beba61b5fd553efb1_9.png)

Ht entity a E style so we're sending in a thing that's bold with a B and less than B that's HTML it's got less thans and greater thans in it and then we got Zap and so you can see that。

The Zap comes out as 42， it's HTMLM entitiesities but it has no special characters。

 but if we escape text， text is the one with the HTML N characters。

 that automatically escapes it so that you see the less thans and greater thans in the browser output escaped less than B bold greater than B。

 right？And if you say text and then add the safe filter to the end of it， that says don't escape it。

 And so then this bold goes right into the HTML document and instead of you seeing the less than and greater thans。

 you're actually seeing the text turned to bold now usually the bad folks that are trying to get into your computer are not just turning your text to bold。

 they're trying to run JavaScript and all we're showing here is that whatever less than and greater thans would be in that context value Txt。

 they're going to end up literally in the document and the browser is going to interpret them as HTML I mean there's just no way that somehow your browser knows the HTML that came from your program versus the HTML that came from a context variable because by the time it gets to the browser it's all one thing and so it doesn't know oh wow that's dangerous that came from a variable now by the time the response goes back to the browser it's just a blob of text。



![](img/931c9321510c5c5beba61b5fd553efb1_11.png)

Now we can talk about some loops here。I am passing in two arrays， apple orange banana and lici。

 and then I'm passing another array called N with peanutut and cashew。

And then I'm going to create a context， and in that context I'm going to have fruits point at the list F。

 nuts point at the list and list N， and then Zap is just the string 42。

 and do I even use Zap in this one？No， I think there's another place that it。No， oh yeah， yeah。

 I just don't have it in there。So here's the here's the template。

 a part of the template is's not looking at Zap。 And so here's the key。

 So you we got this for loop4 x in fruits， well fruits is looking up something in the context under the key fruits。

 their' string they don't look like strings in。They don't look like strings in the template。

 but it looks up there and it finds a list， so that little list F is what really is going on here and F is a list of apple orange banana lici。

And then X becomes the iteration variable that's only within the template。

 and then I'm going to print it out and then I'm going to end it so that's like the start and end of a for loop。

 Apple orange， banana light sheet now you'll notice that I have an L tag which is the list item tag and it just generates all that HTML and again。

The double curly braces are doing HTML entity escaping automatically。So we take a look at nuts。

So we ask is nots present because that's a way to tell if variable is present or absent。

 if it's absent， I'm going to ask another filter on the end saying how long was it？

And so this is just， this is the N。Nuts is the end list。And it has a length of two。

 which means it has two elements in it， and so we see the number two。

And so you can do various things， and this is an if then else， the syntax of an if then else。

 with curly， curly brace percent。Now we can pass objects within objects and so it's a little tricky。

 we have a context in this X variable。And the sort of the outer key is pointing the key is outer is pointing to another dictionary and in that dictionary there is a key of inner with a value of 42 and then we render the Nta dot HTML and you see the outer。

But then outer dot inner that's so outer is that object and then object dot inner。

 then this thing becomes 42 okay， so you can kind of walk through objects if you have hierarchical objects。

Objects that are objects that contain objects or list that contain objects or any number of hierarchical structure of list and objects。

 you can walk through them。Yeah。So here's just another simple example。

 this one has data coming in instead of hardcoded so we again have you know game 200 and we're running into game view it's a class view and the 200 comes in is the parameter because we said it's the parameter that comes after the word game and so guess comes in as 200 it's a string at this point it hasn't been converted to an integer so when Django pulls these off well it does some validation based on the types but it doesn't actually necessarily convert them and so we're going to create a context x equals a key of guess and convert it to an integer to pass it in。

And then we're going to pass the context in and the template in and so the word guess is going to come out and we sort of saw this。

 the guess is 200 and then depending on the ifN else logic it's going to say in this case。

 too high because your guess was 200 and of course the right answer is always 42。



![](img/931c9321510c5c5beba61b5fd553efb1_13.png)

So now we're going to talk a little bit about how you manage a common text going from one template to another through template inheritance。

