# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p109 p37_09_css-display-grid-part-1 -BV1tAygYoEj5_p109-

Hi there in our previous video we have seen how we can style tables in CSS。😊。

And we have also created a table and styled it with multiple cs properties。😊，In this video。

 we'll be discussing about CSS grid。It is one of the most powerful layout tools in CSS。

It is a two dimensional layout system that allows you to create complex layouts using rows and column。

In this video we will be covering the basics of CSS grid， including how to set up a grid。

 how to defend those columns， how to place content within the grid。

 so whether you are a beginner or an experienced web developer this video is for you。😊。

What is CSs grid CSF grid is a two dimension layout system that allows you to create complex layouts using rows and columns。

😊，With CSF grid， you can easily create responsive and flexible layouts that adapt the different screen sizes and devices。

😊，Unlike other layout tools in CSs such as Flmos and floatat。

 Cive grid is specifically designed for creating grid based layouts。😊。

This is an example of layout with CSS grid。You can arrange HTMLl elements in rows and column giving you complete control over the positioning and sizing of each element。

 you can also put them as headers main empty space sidebar which gives them some meaning。Well。

 let's just implement the CSS grid in our own HTML document。



![](img/c8074a937b6d1beccddd3c48d591ff3a_1.png)

So this is our HTMLl document and over here what have。😊，You're done。

We have created a grid container and inside that we have multiple grid items。

And we have applied some styles to them， so for the container we have put a background color blue put some padding and for the items we have a background color of grayish and we have put some bottom。

We also align the text and increases the font size。Let's just see how it is looking in the browser。

So now for applying grid into this， what we will do。We will use the property display。

 but this time we will put value as grid。

![](img/c8074a937b6d1beccddd3c48d591ff3a_3.png)

And after applying this， you can see。Nothing has happened。



![](img/c8074a937b6d1beccddd3c48d591ff3a_5.png)

Because we need more properties to define a grid currently we have just told our browser that will be using grid。

 but currently we have told our browser。Currently we have told our browser that will be using grid pulling out all the elements which are present inside this grid container so what we can do is we can use a property called grid template columns。

😊，And inside this we can put the column sides， lets say we put 100 px。

 it will create a single column of 100 px and well arrange all the grid elements inside that。😊。



![](img/c8074a937b6d1beccddd3c48d591ff3a_7.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_8.png)

Now， let's say we want multiple columns so what we can do， we can put。One more column 10 px。

 and now we have two columns。Now， similarly， let's say if we want multiple columns。

Then we cannot keep writing these 00 Bxs multiple times。Let's say if you want four columns。

 what you can do， you can put repeat。How many times you want to repeat it。

 let say4 and then whats the size of each column you want， you can put100 p。



![](img/c8074a937b6d1beccddd3c48d591ff3a_10.png)

And now you can see we have four columns of 100 P。

![](img/c8074a937b6d1beccddd3c48d591ff3a_12.png)

But now， let's say this size that we have put over here。



![](img/c8074a937b6d1beccddd3c48d591ff3a_14.png)

We don't want it to be。嗯嗯。

![](img/c8074a937b6d1beccddd3c48d591ff3a_16.png)

Now， let's say the size which we have put over here， we don't want it to be absolute。



![](img/c8074a937b6d1beccddd3c48d591ff3a_18.png)

We want it to be keep changing so what we can do instead of using the Px。

You can put something called FR。So with one fR， what it will do it will create four rows of equal sizes as you can see over here。

 they are adjusted there with automatically by themselves。😊。



![](img/c8074a937b6d1beccddd3c48d591ff3a_20.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_21.png)

Now， if we use them without this repeat property， how it will behave。



![](img/c8074a937b6d1beccddd3c48d591ff3a_23.png)

So if we put a single row one F， it automatically takes the whole space， it means take the pull row。



![](img/c8074a937b6d1beccddd3c48d591ff3a_25.png)

Then let's say if I create one more with one fR。

![](img/c8074a937b6d1beccddd3c48d591ff3a_27.png)

They will divide the space between them。

![](img/c8074a937b6d1beccddd3c48d591ff3a_29.png)

And if I change this one。To2 Fr and the second one to one Fr now you can see this one is double of whatever is assigned to this one。



![](img/c8074a937b6d1beccddd3c48d591ff3a_31.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_32.png)

So this is how we can create columns。And let me just create。To call them for myself。

 which we can use。Yes。All let you see how we can create ruless。For creating rows。

 we have something called grade template row。And grid template row we can put。Similarly。

 what we have done for column， okay we need to put over here。



![](img/c8074a937b6d1beccddd3c48d591ff3a_34.png)

And now we can see the first words become。

![](img/c8074a937b6d1beccddd3c48d591ff3a_36.png)

500 Bx。Let me justfuse this ones。It now become 200。Similarly， if we want multiple rows。

 what we can do， we can either add values over here。The seconder will also become 2 px。

Third one will also become。200 px， if I add it。And let's say we are fourth one。



![](img/c8074a937b6d1beccddd3c48d591ff3a_38.png)

Then we don't have any content， so it won't appear， but if we add some more。

Then it will also be 200 Bx。

![](img/c8074a937b6d1beccddd3c48d591ff3a_40.png)

And just remove this one for now。And now what we can do， we can also repeat them。So similarly。

 we can do something called repeat。都。And we can put the value 200 Tx。Now we have done that。

But there is one more way of adjusting the rows that is。Instead of using grid template room。

 we can use a property called grid auto because as we have seen that。

We cannot keep defining growth as per our choice because we don't know what could be inside this。

So what we will do will put grid。Otoo。And we will put let's say 200 p over here automatically whatever rows will be created they will be created of size 200 p。



![](img/c8074a937b6d1beccddd3c48d591ff3a_42.png)

![](img/c8074a937b6d1beccddd3c48d591ff3a_43.png)

No， if。We define the grid template row。And put 300 px。

Then it will make the first row which is defined as 300 and others after that as 200 px。

Let's just see something else。Lets just do something like this that what if we don't have any defined role？

And we put some text inside this whole text。Let me put some dummy text inside this one。Like this。

And then let me put some dummy text。Inside this one also like this。And we save these two。We can see。

That the text inside this adjusted itself automatically。But what if we have something？

For defining the o size， we will put。Great。Otoo again。And we will put size as 200 px。

So you can see the texture of the workflowing。How we can handle this。Well， for're handling this。

You can do something good。Minmax。And we can give a minimum value and a maximum value in this scenario。

 we can give it auto。So what it will do， it will adjust the ones with the data inside them。

As per the data and for the others。It will take。那么 value。That is how we can make these roads dynamic。

And you can adjust them according to the content inside them。

Now let's just look into one more property。Now if we remove this data again， and let me put。

One over here again。And do over here。Again。So what would happen in this scenario that let's say？

And we put it like this。We have all our rows and columns back now。



![](img/c8074a937b6d1beccddd3c48d591ff3a_45.png)

We want to add some gap between them as they are currently cod together。



![](img/c8074a937b6d1beccddd3c48d591ff3a_47.png)

So what we can do， they can。But。Gooded。

![](img/c8074a937b6d1beccddd3c48d591ff3a_49.png)

我谂夹。To add gap between them， let's say 10 px。

![](img/c8074a937b6d1beccddd3c48d591ff3a_51.png)

And the gap between the columns has been added。Similarly， we want to have。

Tap between rows instead of column willard row。

![](img/c8074a937b6d1beccddd3c48d591ff3a_53.png)

And well have a gap of 10 px between the rows。

![](img/c8074a937b6d1beccddd3c48d591ff3a_55.png)

This is how the gap look。And if we don't want to define the gap between rows。

And columns differently than we can do something like。Grid gap。And we can put some value， let's say。

 20 px。In this scenario， a gap between the rows of the left columns will be added。



![](img/c8074a937b6d1beccddd3c48d591ff3a_57.png)

So I hope you all are able to understand how you can use grid and create rows and columns。

And how you can manage them。I assume you'll use them in your next project。See you next video。🎼。



![](img/c8074a937b6d1beccddd3c48d591ff3a_59.png)