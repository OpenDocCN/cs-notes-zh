# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p51 25_05_01_Django通用视图.zh_en -BV1Kt421V7EE_p51-

We're onto to our last mini lecture about views and it's a big one， it's about generic views。

s it's a really big lecture so that we end up with little tiny views with one line of code。

 so I've been building up views and we talked about inheritance with the templates and now we're going to talk about inheritance and views and we've been inheriting all along with views so here we are in the views dot py this whole thing these particular kinds of views we define them in views dot py。

 but they're very informed by the content of model do py which means that views are constructed automatically。



![](img/d919a8d493d6377bea13111017692e3a_1.png)

Just looking at the data in the models。pyy so it's again sort of the logic of don't repeat yourself if you have a thing in models。

pyy you've defined exactly what the fields are and things like you what the help text is for this field and what the description for the field is that has nothing to do with the database but it can inform the views and so it's just a way for you'll see how it all fits together nicely but sometimes when we use these super awesome techniques。

 we end up with a little tiny bit of code and it's really important to deeply understand that tiny bit of code because you can sort of just fade away and not realize what's going on because this code is so cleverly reusing a ton of other code and pulling stuff in from other places。



![](img/d919a8d493d6377bea13111017692e3a_3.png)

So。If you all the way back to we talked about SQL， the four basic operations are put data in a database。

 get data out of a database， delete that data， or update that data， cru， create， read， update。

 and delete。

![](img/d919a8d493d6377bea13111017692e3a_5.png)

And we're going to build a bunch of things， whether they're ads。

 add things or auto things where we' got to insert an auto， update an auto， delete an auto。

 list all the autos， insert a cat， delete a cat。List all the cats updated cat right and so we have a bunch of user interfaces that we're going build over and over and over again and as you build your own projects。

 you'll probably have four or five tables and then little crud user interfaces for each of the tables and sometimes you make them a little different and there's pretty stuff on them and they're customized but surprisingly often these things just look the same and we end up repeating ourselves。

 which is something we don't want to do as software developers。



![](img/d919a8d493d6377bea13111017692e3a_7.png)

![](img/d919a8d493d6377bea13111017692e3a_8.png)

So here is a simple cruD application， it's theC， createate and read or no actually it's this one here is only read and detail。

 so we have a list of cats and then you click on the cat list and then you see the data for a particular cat and then a link back to the list。

So this is like a detail page。But we're going to do a lot more than that。

 but this I just want to show you how these generic views by keeping work by keeping things very。

 very simple， so we're going to talk about a generic view in the list in the detail which are two of several generic views so this is our GVi application and here's the URLs do py in this G view it has a list of cats an individual cat a list of dogs an individual dog and so you see this sort of repetition and I'm putting so many of these in here because I'm going to show you sort of different approaches to implement them using less and more detail and less and more inheritance so they're all kind of the same I give them a name you know some have integer primary keys and a way you go。



![](img/d919a8d493d6377bea13111017692e3a_10.png)

![](img/d919a8d493d6377bea13111017692e3a_11.png)

![](img/d919a8d493d6377bea13111017692e3a_12.png)

And so here is the cat list， I'm going to start with a template。

So we're going to expect in the cat list template that there is a context variable called CA_ list。



![](img/d919a8d493d6377bea13111017692e3a_14.png)

And that is a list of cat objects。And then we are going to iterate through the cat list however many cats there are with inside of a list and generate an LI tag and then create a link URL。

And then pull out the name of the cat so the cat has a name and the cat has a primary key and so we are going to generate a link to the cat Sophie and underneath that link is the link to slash cat slash 12 whatever that number is and if the cat list is empty we're going to say there are no cats in the database now we've actually got a script that you use to preload all of this data so there's instructions in in the sample code as to how to preload that data to take a look at the Readme for it。



![](img/d919a8d493d6377bea13111017692e3a_16.png)

![](img/d919a8d493d6377bea13111017692e3a_17.png)

![](img/d919a8d493d6377bea13111017692e3a_18.png)

And so if we're in the detail page。We're going to pass a cat object in and that has a name。

 and then we want a link to go back to the cat list and so again we're using something from the immediately previous lecture where we're using the URL macro passing in the name of a view within within an application so this is the GV applications。

 the cat view， and then that makes a for an HRF that makes a valid link with the string go back to list to be the thing that that does。



![](img/d919a8d493d6377bea13111017692e3a_20.png)

So。We're going to build all this stuff and that's the basic idea that that template and the HTML that's how we're going to do it。

 but we're going to look at how the views work and again this is a reminder of the dry principle that don't repeat yourself principle again。

 sometimes this dry principle gets us in trouble because we the idea is that some bit of logic is placed one place and reused as many places as possible because don't repeat yourself would probably。



![](img/d919a8d493d6377bea13111017692e3a_22.png)

As well described by calling reuse， reuse， reuse， reuse。

 do it once and then reuse it as many times as possible so that if you have to fix it and you've got a bug in it。

 you don't have to find the 49 places that you put all this code。

And because we do the same thing over and over and over again， cats， dogs， horses。

 we do it over and over and over again， cars。The idea that you have a list view or detail of view。

 edit view， etc， it's a common thing and really if you're going to do this stuff。

 why not make it look consistent and function consistently if you have one developer build the cat's editing interface and another person develop the dog's editing interface and they like go off the same you know go off in their own way and they got some groovy design but it's different。

 you know who cares right it's inconsistent so consistent。

 you still want a beautiful design but you want the cats data and the dog's data to make sense with that consistent design。



![](img/d919a8d493d6377bea13111017692e3a_24.png)

So both of them can have a nice design。

![](img/d919a8d493d6377bea13111017692e3a_26.png)

So。We got templates， the templates expect variables like the list expects a thing called cat underscore list or dog underscore list or whatever。

 and then the cat detail just has a cat variable in it and then we call it so if we just。

Forgot about all the stuff that we're about to learn。 And we just wrote a view。

 It would look like this first one。 this cat list view here。 And so we would inherent from view。

 We're going to go go to the database。 We've imported the cat model， cat dot objects。

 This is the way to query all the cat objects and get a list of cat objects and put it in the variable stuff。

 That's what cat dot objects dot all does。 Now， we've done this before， like in the shell。

 But now we're doing it in actual Python code in the views。 Like I said。

 views are where all the stuff happens。 So that says make a database call load all the cat records。



![](img/d919a8d493d6377bea13111017692e3a_28.png)

Turn them into objects and give me a list of those objects and then I'm going to pass in the context into the template。

 the Gview/catlist。 HTMLt I'm going to pass an entire list and if you go back and look there was a little loop in the template that printed out you know Sophie Frankieen made links underneath them into the detail page。

Okay。So this is how we would do it if we were going to not repeat ourselves。Okay， now。

This next way of doing it for the dogs。Yeah， for the dogs， we're going to do it another way。

And so what we're going to do。

![](img/d919a8d493d6377bea13111017692e3a_30.png)

It looks like it's more work。But it's more reusable。 So the stuff that we're doing here。

 So what we're doing is now we have a dog list view， which is just a class。

 and we're going to create。An attribute variable in this object called model。

 and we're just going to say that this model for this particular one is dog。

So the idea now is in this git method， we take this code right here and every ser we said catt。

 make that be generic and have it be driven by this one variable。Okay。

 now the tricky part that makes this a little tricky is sometimes we're just using the model。

And then other times we are going to actually turn it into a text string。

So if we take a look at this。呜oo。We have this variable model。And in the get request。

 self dot model is the way refer to the particular instance that we're in that model variable。

His little metaver both underscore name title to lowerercase。

You could figure that out by yourself by going to stack Overflow eventually。

 that's how I figured it out I wanted to get a lowercase version of the model name。

 so the model's name is a string DOG which is not the same as the dog model。ok。

And so that just as a way， model name is going to be lowercase dog， but if model is cat。

 then model name will be lowercase cat in this bit， so I'm trying to make reusable code so yes。

 the reusable code looks a little more complex because it's generic。

But you'll notice that I'm creating a variable called model name underscore list because I'm just concatenating it together so it's model name and is going to be dog underscore list so that's what's going to happen I am going to talk to the model and retrieve all the objects that's okay I don't have to change it to a string Sedot model is dogg。

objects。 all so then I'm going to get a list of all the objects and stuff and I'm going to put that in context。

And then I'm going to go get myself a template out of the GV folder with the model name underscore list so that what used to be cat list and here is now dog underscore list。

 I'm it concatenating it together and I passed the context in and so then when that happens then you get a dog list and some the dogs in the way you go So what I did is I generalize this code and put it in here and then I passed in in a sense to the object that was made from the dog list view class。

 the actual model that I wanted to operate on。Okay。😊。

So I do this to give you a sense of how this works。You can do the exact same thing for horses。

By doing this and that is。You import the generic。Dango viewss generic right here， and you say。

 I'm going to make a class called H L Views。I'm going to extend not just view but generic list view。

 so this is a generic class， you can go look at the Django documentation for this。

 it's a generic class that does a list view in general。

And the rule for the class is you have to add one line here to say which model it functions on。

And that's it。And that's because the get code。Is already in this model or' extending that model or inheriting all this code。

 not from dog list view， but instead from generic listist view。



![](img/d919a8d493d6377bea13111017692e3a_32.png)

So we took something that was five lines， a little more generalizeds like eight lines。

 and now it's one line。And so that's how the extension works。

 but you have to trust and you have to go read the documentation for list of you to know how it is that you inform it as to what model you're supposed to use。

So I want to show you a little bit of how this is happening by making one of these。

List views that's mine it's not as cool as the real Dngo list view。

 just to give you a sense of what's going on behind the scenes in the Django list view。



![](img/d919a8d493d6377bea13111017692e3a_34.png)

So if you say so I'm going to make a new class， DJ4E list view， and then I'm going to extend view。

And then I'm going to have a get method， and it's going to be all this code。

 it's looking for a variable called model and you'll notice that it's not defining model up here because it's intended that this is a class that's going to be reused。

 so I'm going to say， oh， well whatever the model is that's been set up here。

By the class that's being created while we're extending it， go grab that， convert it to a text。

 get the title of it， and then convert it to lowercase， make that model name， whatever the model is。

 retrieve all of its objects and put it into stuff， and then put model name underscore list。You know。

In this case， car underscore list and then pass that list into the template and then render GVi car underscore list context。

So this is not doing anything per se DJ4E list view is creating a class that I'm going to extend later。

 and I'm going to extend that two lines light， I'm making a car list view that extends DJ4E list view。

And the only thing I need to do to get all of this code in here is extend it。

 and then I do need to add model equals car， so you'll notice that Carless view or Carlless view has the exact same syntax as horse list view。

 right？

![](img/d919a8d493d6377bea13111017692e3a_36.png)

Horseless view， you basically tell it the generic list view。

 Tell what model to work on and then generic list view does it all。 And if you look at Car list view。

 it says use this generic list view that I just invented to show you the source code of what it is。

 That's the source code behind the scenes。 Like I said。

 it's way more complex and sophisticated than what I did。 This is the crudeest。

 simplest version of an extendable generic list view。



![](img/d919a8d493d6377bea13111017692e3a_38.png)

![](img/d919a8d493d6377bea13111017692e3a_39.png)

But when it's all said and done， you don't write any of those versions。

 you literally make a list view and tell it what model it is。

 you make a cat view and tell it what model it is， and you just reuse the list view over and over and over again。

 so the fact that I give you four different ways to do this。Yeah， I think four different ways。

Maybe five， four or five different ways to doing this。The real way to do it is one way。

 but when you look at code like that， you're like horse list view is an extending generic list view and the model is horse。

I'm trusting a lot and the answer is yeah， you get used to it and now the code you have to write is only two lines of code and you have to write the template still because it's gonna to call your templates but it knows the name of the template by looking at that horse right it knows oh horse oh yeah horse underscore detail right or horse underscore list and so this is the actual detail page that shows you the horse and goes back to the list etc。

 etca etc and so using these generic views you can make things really short and really succinct and really simple So generic views are excellent。

 they allow us to produce lots of similar pages without repeating ourselves they keep your code consistent they don't the repeating yourself doing the same thing over and over even seems quick to cut paste change。

 cut past change cut paste change if you really want to build reliable code and code that's thousands and thousands of lines。



![](img/d919a8d493d6377bea13111017692e3a_41.png)

![](img/d919a8d493d6377bea13111017692e3a_42.png)

![](img/d919a8d493d6377bea13111017692e3a_43.png)

With hundreds of features。You able to don't want to be pasting the same thing over and over。

And so less lines of code means fewer mistakes， so this is kind of the end of our talk about views。

It's really where we're going to start doing most of the work， the URLs， the models。

 they sort of don't get the kind of activity， although we are going to talk upcoming about forms which touch on views and they touch on models and they touch on templates so forms are one of the things that lets take our user experience。

Really up it， so we'll see you soon。