# 密歇根大学《给所有人的Django课程（简介、开发Web APP、特征和库、JavaScript和JSON）｜Django for Everybody》中英字幕 p83 23_04_06_使用Django Shell探索一对多模型.zh_en -BV1Kt421V7EE_p83-

So now we're going to take a look at the kind of Python code we can write to manipulate these data models。



![](img/c20736d9c0d0d609932484a6154341a3_1.png)

So to do this， we're going to use what I call the Django shell。 Now。

 the Django shell looks a lot like the Python shell。

 except that there's a whole bunch of stuff preloaded。 you can't just run。

 you know Python 3 in interactive mode。 You see the Chevron prompt on Linux you see a bracket prompt。

 it's the same shell。 But in the Django shell。 What happens is is actually reads the settings Py and goes and finds all the applications in settings py and preloads the applications and then gives you a shell。

 So it's like there's a bunch of things that happen。

 that's not just a shell that are done before you're in the shell。

 And this statement of from book 1 models's import book laying instance。



![](img/c20736d9c0d0d609932484a6154341a3_3.png)

![](img/c20736d9c0d0d609932484a6154341a3_4.png)

That wouldn't work if you just ran the Python shell by itself。

 that's because the book1 application was loaded by Python 3 managedage。 Py She。After that。

You've got all these things preloaded， but then you can pretty much run any Python that you want that messes with all of your django classes and objects。

 et cetera， et cetera。 So let's take a look at the kinds of things that we can do。

 So if you remember， our data model was named layng for language。

 And so we can create a new object in memory with laying parenthey name equals quote E， quote。

 and that basically says， give me a new language object and set the parameter the attribute name to be E。

 and give that to me back in a variable。 That's an object oriented constructor that we're constructing an object。

 Now that doesn't store in the database that simply creates it in memory and gives it back。



![](img/c20736d9c0d0d609932484a6154341a3_6.png)

So it's a Python object with a attribute。 it knows it's a language Now the save method Z dot save that is the thing that says。

 you know what， I've got this thing in memory， please persist it to the database， write it。

 transmit it to the database。

![](img/c20736d9c0d0d609932484a6154341a3_8.png)

And come back。 Now， what's cool about that is this I column that's been set at that moment。

 So we can say what I did we get。 So remember how every row that we put in a model gets an I value。

 and we're going to use that I value as the handle to point to。 So this is the primary key。

 which is the way we point to a row in a table。

![](img/c20736d9c0d0d609932484a6154341a3_10.png)

So then what we can do is we can make a book right so we made a language。

 we made a language and we know what its ID is Now we're going to make a book and it's got like a title an IBN。

 And what we do is we say and the language is Z Now Z there is that variable。

 Now we don't use the ID。

![](img/c20736d9c0d0d609932484a6154341a3_12.png)

Jango knows all about how Is work。 And so it knows when you're saying L equals Z that it's going to make a L I D and put the I D of the language grow in Fory。

 All this stuff' is just done。 You just have to have a variable that has an I D value and pass that in。

 And So what that's doing is that is making a book。



![](img/c20736d9c0d0d609932484a6154341a3_14.png)

And then connecting it to a lay， right？Now， that's also not saved until you' save the book。

 the book is now transmitted to the database。 It has a foreign key in it。

 It gets its own primary key。 So it's primary it's the first book that we've inserted。

 So it's primary key， Xdo ID is1。

![](img/c20736d9c0d0d609932484a6154341a3_16.png)

And then we can make an instance and the instance needs a due back。Which is a date。

 And then it needs which book it is。 And we use that variable X to indicate which book that we're talking about。

 So that's just creating a link from the book instance in memory that we get back in the variable A。

 It's a book instance that points to the book。 it's in the variable X， which is Py freey IBN 42。

 And then we save that。And that has an ID。 So now we have created a language record。

Then we created a book record that linked to the language record。

 and then we created a book instance record that linked to the book record。Okay， and so that is。

You know， this whole linking thing right So these are the pointers and what Djago is doing in this situation is Djago was trying to hide from us The whole idea of the foreign keys and the primary keys other than me asking what the ideas。

 It's not really something you have to do。 So all those asking for the ideas aren't necessary。

 You just say， look， I have a book。 And its language is this thing。 I don't know what its idea is。

 You should please make me a column and do all this magic stuff。

 So so much of the bookkeeping of these one to many relationships or foreign key relationships in general。

 And Djago was just done automatically。Now， we can retrieve these and we can sort of walk down these things。

 walk through these things。Here we are again， samples， and we run the shell。

 and we import our models。

![](img/c20736d9c0d0d609932484a6154341a3_18.png)

And we can say book dot objects and book as a class from our models， it's book 1。models。book。

And then a lot of the methods that we talk to inside of these classes are under the attributee dot objects。

 which is you could think of it as all of the rows in a sense or all the objects in this model。

 all the rows in the table that lives there， book objects and then get is like which one do you want get PK equals one PK means primary key。

I don't know。 I think you would make more sensibly call this I。

 but I is the name of the column of the primary key is really just kind of a convention that's done 98% of the time。

 It's not required。 it's not the truth， but it's so common that it might as well be。

 but Pk really means primary key which might be which9 out of 10 times is the column I。

 So we're loading from the books table， we're pulling that in。

 and we're getting the one the row number one from the books table。 So if you say what the title is。

 well， the title of that is。

![](img/c20736d9c0d0d609932484a6154341a3_20.png)

P， Y for。Now。There's a title， but then there's Lang。

 Lang is that foreign key that points to the language。And so we can say x dot Lng。

 that is the entire language row， but X dot lang dot name is within that row。 It's the name column。

 So we sort of walk down the little arrow and grab one of the elements out of that。

 So it's like walking from a book to the corresponding language row and then pulling the name out of that corresponding language row。

 So I think that's a really pretty syntax。 and it starts to make sense after a while。

 You walk down the walk through the little arrows。 And this is why the picture of the data model is so absolutely important oops。



![](img/c20736d9c0d0d609932484a6154341a3_22.png)

![](img/c20736d9c0d0d609932484a6154341a3_23.png)

![](img/c20736d9c0d0d609932484a6154341a3_24.png)

And then so now we're going to go grab the book instance number one。

 the first row of the book instance table， so instance do objects get pk equals1 that says give me that first row。

 give it back to me in the variable Y what is the do back of this one and then you can sort of walk it。

 you can say I'm at a book instance， and I want to follow the foreign key to the book table to get me a book and then give me the title of that book。



![](img/c20736d9c0d0d609932484a6154341a3_26.png)

So from a book instance you can walk to the book table and then get the title of the book and we get PY free。

 so you see this sort of starting from one row， walking to another the corresponding row that's pointed to by this relationship and that's the essence of this。

We're going to do this a whole bunch， by the time we come back to this。

 this will all seem pretty straightforward。

![](img/c20736d9c0d0d609932484a6154341a3_28.png)