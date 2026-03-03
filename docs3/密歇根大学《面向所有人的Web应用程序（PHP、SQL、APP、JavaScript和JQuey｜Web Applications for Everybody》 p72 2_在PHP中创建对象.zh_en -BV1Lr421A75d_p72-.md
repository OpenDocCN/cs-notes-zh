# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p72 2_在PHP中创建对象.zh_en -BV1Lr421A75d_p72-

![](img/4ae628335b5a73a8673ad2452141ca33_0.png)

![](img/4ae628335b5a73a8673ad2452141ca33_1.png)

So while I'm not going to have you build your own objects。

 I think it's really instructive to take a look at the syntax you use to define them。

 to help understand how they work。 Again， my goal is is that you are going to look at objects and you're going to use them。

 read the documentation and make use of them。 But let's just take a look at how you might build such a thing。

But before we do that， let's kind of go back to PhP4。And the concept of data structures。

 and I mentioned that one of the things that people love about PhP is how that using arrays。

 especially key value arrays， you can sort of like make data structures and。

 and you might even just like。Not even realize how awesome you are。

 that you're sort of making clever data structures by making a raises with keys and values that have conventions。

And so let's say we're going to deal with people's names and sometimes we have a full name and sometimes we have a first name and last name right。

 we call we decide to call the last name family name because it's culturally incorrect to call it last name because family name and some cultures comes first and given name come second。

 So that's the cool thing we're going to do。 So were going to have some objects。

 Some objects are going to have a full name。 Some are going to have a family and given name and every object is going to have a room。

Now， that's not really an object。 It's just common using object terminology。

 So we've created data structures。 and the problem is is that。

We're going to want to print people's names out and so we are going to want to write some code and so we're going to have write a function called dealing with the two variations of these objects。

Which are really just a。 We're going to look through this because we're gonna to print these things out so much。

 And there's going to be thousands of these things。 right right now， we've only got two of them。

 but there'll be thousands， and they'll all be different。

 And why don't we write a bit of code that handles the fact that sometimes we use the full name and sometimes the give the given name。

 So let's write write a thing that takes this as parameter person as parameter。

 checks to see a full name is set。 If so it returns the full name。 And if indeed， instead。

 the family name is set and the given name is set， We're going to concatenate the given name and the family name。

 there might be something more complex to say which culture you're in。

 And then can't concatenate the given name and the family name。

 And our family name and given name in some order。 So assume there's some nontrivial complexity in here。

 So there's code， we don't want to just do it over and over。And now we can pass Chuck in。

 let's get print Chuck's person's name and let's print Colleen's person name， all this code runs。

 out comes Colleen Van Lent and Chuck Severance the right way， and we have these sort of variations。

 right？And that's the non omage going way to do it， right。

 you just make an array and maybe give yourself a little support routine to save yourself reusing this code。

But now if we were to recast this as object oriented pattern。

 what we would do is we would create a template and say，Ps look this way。Okay。

And so we're going to use class。 Class is new keyword that we're seeing。

 Class is kind of like function， where it's defining a function。 So we're going to make a template。

 Now， this code doesn't run。 It's parsed and looked at。

 But the side effect of this is there's going to be added a new person。Which is a template。

 It's not really code。 it's just grabbed all this， and it's put it in。

And then what we're going to do is we're going to put some variables in it。

 So I said that an object is data plus code。 So we're going to say there's an attribute a full name。

 an attribute， a given name， an attribute， a family name and room。

 and there are variables in every person object。 and we're going to study them to false in the beginning。

 and then every person object will also have a built- in function。

 And so this is a function that is part of every person object。

 and it looks like every other function you can even parameterss。

 which we'll see in a bit except that it uses this weird little dollar this。Okay。

Dollar this is a predefined constant that you can only use inside of a method that's inside of a class。

Okay， and what is this， Well， if you remember the picture I drew before or I had one object。

 which was now and another object， which is next week now。And then， next week。Right。

What happens is this code getname is part of both of these。

 right so get name is really in both of these。But when we run it in this one。

 it needs to look at the data that's inside of itself， and when we run it inside this one。

 it needs to look inside data inside this cell。So what happens is it's as if there's a parameter。

Called dollar this。 And dollar this always points to the。One that we're in right now。

So it's like this one。 So there could be thousands of objects。

 thousands of person objects sort of floating around。We're still in the class。

 But like we'll have one called Chuckkin well have one called Colen。 and we' make a bunch。

 but we could have be making them in a loop。 And so there could be thousands of these things。

 This always points to the one that you're in， right， So when you're executing code in this one。

 it points to the data in this one。 when you're executing code in this one， it points to that one。

 So you say the one that's in this instance or this object。So that's really， really important。

If you know about Python， there was this concept of self。In Python。It's the same thing。

But you don't mean we're not talking Python right now。

 Most objects or languages have some way of doing this。 I think Java uses this with no dollar sign。

 And that's where the， where this came from。 I think it was borrowed from Java， if I'm not mistaken。

Okay， so here comes our class。 It's got four pieces of data and one method，1 bit of code in it。

 And that's just a template。 It's a shape that we can then instance。 So then we run。

 We're going to like， oh， let's make one of these things。 So we take the little template。

 We make an actual class。 It has four pieces of data and one function inside of it。 and then。

We're going to put that in Chuck， so dollar Chuck points to this one。

And we can access the data items with this little arrow operator。

 but it's really just an operator that says go in find full name。

 which is like this and put Chuck severance in here。 So fill that Chuck severance in there。

 And then the room is going to be4 for blah， blah， blah North Quad。

 And then we're going make another one。 So we're going to take this template again and make another one。

 It's going have four pieces of data in it and one function in it。

 And we're going to say the family name is Van Lt。 and we're going say the a given name is Colleen And we're going to give her at 34 North Quad。

 right。Okay， so now we have。 And that's gonna， that's going to be this guy。 So we filled it up。

 We built it， and then we filled it up with stuff。 right？ So that creates this object。

 And now I'm going to run the get name function inside of Chuck， which is this function right here。

 It's identical to this one here。 But except that the this is pointing up to that data。

 So when this code runs， this full name is this one。 and the room， et cetera， is this one right here。

 And so it runs， we do the get name and says， oh， well， this one， full name is not false。

 So we're going to return Chuck severance。 Then it goes back。Code comes back and then runs this。 Oh。

 let's go find the Colleen object， which is right here and run the get name code there。

 Except this is going to point at this data。 So it runs。 And in this case， full name is false。

 but family name is not。 And so it returns this code。 And so it returns the code。

 prints that out and out comes Colleen Vanlint。I hope you understand it。 Go back and watch it again。

It's really just code and data， name spaced。 And this is the， this is the powerful concept。

 The dollar this is a powerful concept。

![](img/4ae628335b5a73a8673ad2452141ca33_3.png)

Okay， so now。Though we talked about making one and you sort of see some new syntax。

 we're going to talk a little bit more about reading documentation as if you're going to have to use objects okay。

