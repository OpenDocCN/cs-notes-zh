# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p40 40_07_01_DJ4e网站图标-favicon示例代码实战.zh_en -BV1rNibBuEwD_p40-

Hello and welcome to another walkthrough for Django for everybody。 In this particular walkthrough。

 we're going to play with the favicon。 And so the favicon is a special little icon that shows up at your root slash favion dot I。

 there's a whole series of favicons。 But this is sort of the original classic one。

 And you should be able to see it。 And it's also what happens in your bookmarks or your little tabs。

 And so it's kind of a fun little way to brand your site。 And if you've been grabbing my code。

 you have got a favicon sitting here in djagosho static favion do Ico。

 And if you look at Us do P Y down。😊。

![](img/db818326272591908e206dfcbb424cdd_1.png)

![](img/db818326272591908e206dfcbb424cdd_2.png)

Later， it adds a path using the static file server and it sort of goes to the base directory of the Django application adds home static and then if there's a path that matches。

 this is the path it matches， then this is the file that it looks up and then that serves up the contents of that file at。



![](img/db818326272591908e206dfcbb424cdd_4.png)

Favavicon。icco now。

![](img/db818326272591908e206dfcbb424cdd_6.png)

What you want to probably do is make your own fabcon。

 so let's go ahead and make our own fabcon here is a fabcon converter and let's go ahead and grab a file let's see。



![](img/db818326272591908e206dfcbb424cdd_8.png)

![](img/db818326272591908e206dfcbb424cdd_9.png)

Schiger going to make a little sager icon instead and so I did it and it converted it to an icon。

 let see what we got here and I'm going to download a zip file with a bunch of icons and it'll go into my downloads so here it came into my downloads it's already downloaded it and that is an icon and so an icon is a special kind of an image and so now what I'm going to do is I'm going to go into here and I'm going to upload and overwrite this with a new file。

And so here we go， I'm going to upload that fbicon and I believe it's up to uploaded right this second。

 Now， here's a weird thing。 Now I should be able to go here and I should be able to press refresh。

 I don't think reloading my application is going to make much difference at this point。

 but icons are heavily cached by the browser。 So one thing to do is just I mean to start that。



![](img/db818326272591908e206dfcbb424cdd_11.png)

![](img/db818326272591908e206dfcbb424cdd_12.png)

Get me to start Camtasia。

![](img/db818326272591908e206dfcbb424cdd_14.png)

I'm sorry， dot need to start that。So I can go here in a different browser。



![](img/db818326272591908e206dfcbb424cdd_16.png)

And I can see。I can。

![](img/db818326272591908e206dfcbb424cdd_18.png)

嗯。Or I can add a get parameter， and then I can see that icon。equals3。 and now I can see the icon。

So it。So if you come here and you press refreshsh， what you'll find is these icons are heavily cached and that's just because you don't want to overload the server getting an icon on every page。

So to really do this right， the way to force the cache and we've seen this like in JSON。

 you can add a get parameter x equals 42， and that basically says it's going to ignore this and it's just going to get because that's a query parameter it's not part of the path。

And it's going to load the new icon。 So it might take a while before you're going to see that icon show up。

 And so don't feel too bad if you can do this thing where you go directly and you add this question mark。

 you should be able to see your brand new icon。

![](img/db818326272591908e206dfcbb424cdd_20.png)

![](img/db818326272591908e206dfcbb424cdd_21.png)

And then later， or maybe if you run with a different browser。

 But if you've used a different browser and it's got a cache icon way it goes。

 And you can go Google how to clear the fvocon on my browser。 And you'll find it's not trivial。

 So this is the way that I do what I just add a get parameter。 And then that does it。

 So I hope this little favicon walk through was helpful to you cheers。



![](img/db818326272591908e206dfcbb424cdd_23.png)

![](img/db818326272591908e206dfcbb424cdd_24.png)