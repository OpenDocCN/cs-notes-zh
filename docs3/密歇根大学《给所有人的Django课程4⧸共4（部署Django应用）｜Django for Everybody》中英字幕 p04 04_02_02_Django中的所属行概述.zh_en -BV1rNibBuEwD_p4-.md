# 密歇根大学《给所有人的Django课程4⧸共4（部署Django应用）｜Django for Everybody》中英字幕 p04 04_02_02_Django中的所属行概述.zh_en -BV1rNibBuEwD_p4-

Hello and welcome to our lecture on O rows in Django。 So what do I mean by anown row。 Well。

 up to now every crud application that you've written。You got a table or you know model or two。

 maybe they're connected， but basically if you log in。

 you can edit every row and so if you do a list， you see an updating and delete button on every row。

Real applications don't work that way if you're building a classified ad system。

 some ads belong to you and some ads belong to other people， you can see them all。

 but you can't edit them all so we have to decide when to put the edit and delete buttons up and only do those for the owner and we have to make it so you can't like sneak in and edit and delete other people's stuff and so we have to protect these rows from being edited or deleted by anybody but the owner。

 but anybody can see them and so that's why I call themown rows if there's a row that you own。

You will see an editit or delete button if there's a row you don't owe。

 you'll see the row and the data and you'll be able to read it and view it and that's it。



![](img/ba1a81ab15cfef41f32e27e6092ef590_1.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_2.png)

And so if we go back to how we were working in our crud application。

 we were making heavy uses of these generic views， the generic list view。

 and so when we're all said and done after a whole bunch of you know machinations。

 you ended up with a very， very simple view you ended up with a horse list view that extended generic list view。

 generic list view is provided to us by Django and the only thing we had to do， was take this code。

 which is several thousand lines of code and inform it as to which model we want it to be and then we make another view right so we make the horse list view by extending generic list view and informing that list view that we want to do this in the model with horses and from that point on all kinds of convention。



![](img/ba1a81ab15cfef41f32e27e6092ef590_4.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_5.png)

Happens and so we know things like the variable will be namedd H list。

 it'll be a list of objects that are retrieved from a list of model objects that are retrieve from the database。

 and so we kind of know how that works。And it makes things really simple， not a lot of repetition。

 every view kind of looks the same， you've probably done cats of dogs autos。

 a couple of different things， and they all look very much the same and if you get good at it。

 you should be able to make these changes very rapidly。



![](img/ba1a81ab15cfef41f32e27e6092ef590_7.png)

So if we look at how this is working kind of from an object oriented perspective。

 we are making a new class called Gview。views。horselessview。

 and we are extending our parent class is the generic list view and we're sort of adding our own little special sauce by saying one class variable model equals horse。

 so that's kind of what's going on here。

![](img/ba1a81ab15cfef41f32e27e6092ef590_9.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_10.png)

Now。In this owner view， we're going to do something quite similar and that is when we're going to have an article and this is all from the Dj for samples My arts example。

 we're going to extend owner list view now we and soon we will look inside owner list view and well see that owner list view is extending generic list view and this model equals our model equals article is informing owner list view。

 the difference is this is our code that belongs to us and in the last part we will show you everything that you have to do to build one of these things and so we're taking the list view which has almost everything we want and we're going to add one feature to it and then we're going to extend the list view and create a new view called owner list view or you might call it list view for owned rows and at that point。



![](img/ba1a81ab15cfef41f32e27e6092ef590_12.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_13.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_14.png)

You just are you're good and this has this this class ownerless view， which we'll see in a second。

 has everything you need to deal with rows that are owned。And for example。

We're going to have a owner column， so every article is going to have an owner。

 and if that's equal to the current logged in user。

 then we are going to show these little edit and delete buttons， but if the article owner。

 the owner value inside the article object。

![](img/ba1a81ab15cfef41f32e27e6092ef590_16.png)

Or the model。If that owner is not equal to the current user。

 we don't show it now not showing a link does not mean you've protected it from editing。

 we'll show you later how that protection from editing happens。

But this is such a common problem that we want to just be able to， in a sense say， look。

 here's a list view， here's a list view with this special owner column in it。

 and we want to maintain the owner column， we don't want to have to write hundreds of lines of code in every view that we want to have this owner column so we just use object oriented techniques to accomplish this and so we're going to use inheritance and we talked about it and talk about it again。

 inheritance is the idea that you have a class， you're going to make another class that inherits all of its all that parent class and then extends it adds a little bit of stuff to it。

 and it's another form of don't repeat yourself， do something once in a parent class you make the parent class sometimes quite generic and you make a child class that extends the parent class and then we use the child class。



![](img/ba1a81ab15cfef41f32e27e6092ef590_18.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_19.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_20.png)

Or we could call them subclass or child classes， there's a whole bunch of different terminology and it's all pretty much equivalent。

 subclasses are more specialized versions of a class。

 they inherit attributes and methods from their parent classes and can't introduce their own again。

 basic object oriented programming。

![](img/ba1a81ab15cfef41f32e27e6092ef590_22.png)

![](img/ba1a81ab15cfef41f32e27e6092ef590_23.png)

So up next， we're going to talk a little bit about how it is that we can peek into one of these generic views and add our own special sauce for it。

