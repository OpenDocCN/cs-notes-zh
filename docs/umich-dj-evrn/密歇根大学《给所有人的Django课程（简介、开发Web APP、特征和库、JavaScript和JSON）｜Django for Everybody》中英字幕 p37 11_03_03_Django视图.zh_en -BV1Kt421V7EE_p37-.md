# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p37 11_03_03_Django视图.zh_en -BV1Kt421V7EE_p37-

![](img/9c9f7e1d1bd9c3d0974389e7500a9514_0.png)

So now we're going to take a look at the code that actually writes the views。

 the code effectively in views。 py Now the first view that we're going to take a look at is one where we're not even writing any code at all and this is that predefined view that template view and again template view is code that a class that's given to us given to us from Django template view and you pass it a parameter so we're actually kind of calling a function here and passing a template name to it and that is a file views main do HTML so if you this is the application views there's a subfolder called templates and then I'll talk about this in a bit we repeat the application name twice so that's a little bit weird but it has to do the fact that these names are global across all of the application and so' you want there to be possibly more than one main do HTMLtml and so that's why you have this。



![](img/9c9f7e1d1bd9c3d0974389e7500a9514_2.png)

folderold name and you put this there even though that feels a little bit redundant。

 but it's okay and so this is what this is just a static HTML file。

 I'm not going to read any data from a database I'm not going to write any data to the database I'm just going to read this file and send it back to the browser and that's a common thing where we just have a file that we want to send back to the browser and so we just don't even have to write any Python code other than add this entry into the URL patterns。



![](img/9c9f7e1d1bd9c3d0974389e7500a9514_4.png)

In URLs。pyy， so that's a view where you wrote no Python code。Now。

 for the parts where you're going to write Python code for a view， you're going to be passed in。

Variables， the variables are all about the request object。

 The request object is all the data coming in and the response object is something you produce in the view and you send it all back。

 So the request object is an object instance of class HttP request。

 This is a predefined django and there's just a whole bunch of things。 the scheme。

 Now what does the scheme， whether or not it's secure or insecure Https， the body， it's the string。

 So there's like about 20 or 30 attributes， we're going to use some of them。

 but you don't have to use all of them， but you can go look up the documentation in the more sophisticated your applicationplication becomes the more likely you're going to have to go digging in to find some little bit of the incoming request。

 You could think of this request data is all that data you see in in your browser tobugger about what data was sent to the server that all ends up somewhere in this object。

Now when we return from a view， we have to send a response back and so the response is something that we create inside of our view。

 it might be simply text that's HTML or it might be a redirect object， redirect response that says。

 hey， go to a different page and so we make that the main job at the end of the view is to produce a response and then return it back to Django。



![](img/9c9f7e1d1bd9c3d0974389e7500a9514_6.png)

And so here is a very simple。Viュー。So here we're saying。

 you know we're in the views application we're going to go to the view funky right and so in the in the URLs PY we say map slash funky to this。

Function named funky， it's a funky function。That's why I call it funky and so when it sees this。

All the data coming into the request shows up in this variable that is the first parameter sent to that function。

 so that's what this is saying in URLs。pyy。Take everything that goes to view slash funky。

 gather up all the request data from the browser， put it in an object。

 and then pass that request object in now in this。I'm not really going to do anything with that request object because I'm always returning the exact same thing and so I just have a nice triple quoted string of some HTML with less thans and greater thans and I'm going to basically return it is my job in the view to give back a response there's a couple to two main types of them ones an HP response which is just like a body of text and that's what I'm sending here I'm sending an HB response that's a constructor we' constructing a HB response object and taking that string that I put in there and a away we go okay and so that basically if you hit this path you're going to get this page back and it sort of looks like that when it's all said and done。



![](img/9c9f7e1d1bd9c3d0974389e7500a9514_8.png)

Okay， so now we want to talk about how we can get at parameters。

 so I mentioned that this request object that comes in to your view function has all the data from the request。

 well， if we send。To a view with this question mark， key value pairs that's guess equals 42 on there。

 and we're going to route danger toview。anger inurls。pyy。

 and so all this data is wrapped up in this variable called request passed into the function named danger。

And so inside a request is some data。Request dot capital G ET is a dictionary of the key value pairs that are on that URL。

 So to pull the 42 out， we can say request dot get bracket quote guess quote and that pulls that out。

 And so thats all we've got here is a really simple HTML page。

 and we are replacing that little chunk with 42。 And so whatever this number is comes back out in the output。

 So your guess was 42。 So that's how we pass。

![](img/9c9f7e1d1bd9c3d0974389e7500a9514_10.png)

Get data into a view。

![](img/9c9f7e1d1bd9c3d0974389e7500a9514_12.png)

Now， up next， I'm going to explain to you exactly why it is I called that function。



![](img/9c9f7e1d1bd9c3d0974389e7500a9514_14.png)

🎼Danger。