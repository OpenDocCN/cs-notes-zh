# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p169 28_07_mixins -BV1bw4m1D7MM_p169-

In this segment， let me show you Ruby's mixins。 These are a nice alternative to multiple inheritance。

 and they're very similar to what are called traits in some other programming languages。

 so what is a mix in？It is a collection of methods and only a collection of methods。

 So it's not a class。 You can't instantiate it。 You can't call new on it to get an instance of a mix in。

 It is just a bunch of method definitions。 Now， what do you do with a mix in。Well。

 languages typically let you in a class definition， include as many mixings as you want。

You can still have a superclass。 you still inherit those methods， then you can also include mix ins。

 and you get all of their methods too。 It is like you typed out the same method definitions by including the mix in。

 you avoid that copy and paste。 So it really is just adding method definitions to some class when you include the mix in。

That way you can extend your class definition with those methods， you can by including a mixing。

 override a method that was typed into a superclass and so on。

So this is really quite powerful and the key reason we're going to see is those mix in methods that you include in your class can use self。

 they are so much part of the class definition that they can call other methods that you define in your class。

 and that's going to be the key power we see。

![](img/e67e249d6561307e233a88ff666cf200_1.png)

So let me show you a simple example first。 we'll get to the cooler stuff in a bit。

 So it turns out in Ruby， we use this module keyword to define a mix in modules also support namespace management So we're kind of getting two different things。

 but here I'm just going to call them mix ins because that's what we're using them for。

 So here is a mix in。 I'm calling Doubr that happens to just have one method defined in it。

 we could define as many methods as we want。😊，And this method is called double。

 And when you call this method， it sends self the plus message with self as an argument。

So in this mix in， we are not defining plus。 we are only defining double。

 We are assuming that any class that includes us will have plus defined。

 and then we will call the plus method。So what we could do is define a class like you see here point。

Define the plus message。With which just， you， takes the X coordinate and the Y coordinate and adds them together。

Then by including doubler。 So you just write keyword include and the mix in。

 you want to include this class now has a double method。 And when you call it， that method。

 we'll call the plus method method。 So I've already loaded everything up over here。 In fact。

 I've already even defined a point that I just previously created and set the x coordinate to 3 and the y coordinate to 4。

 And now if， you know， it has a plus method。 So I could say p plus you know， well。

 I guess p is the only other point I have。 But I don't have to do it that way。

 it also has a double method。 And you see as a result here that x is it's returning a new point where x is 6 and y is 8。

 And， of course， that point also has a double method and so on。 And this works great。

 So we successfully did it。😊，Now you may have seen here over in the code that I also went and added the doubler mix in to the class string。

 Now this is questionable style going and changing an existing class， but it does work and indeed。

 if I come over here and I type hello do double， it now has that method。

 it all it's doing is calling the plus method on strings with hello itself and since plus concatenateates。

 we get hello hello back。So you can do this， you can include as many mixs as you want。

 mixings can have as many methods as you want， and this all works great。



![](img/e67e249d6561307e233a88ff666cf200_3.png)

So we do have to be a little careful here。 I was so careful to precisely define method lookup now that we have other ways to add methods to classes。

 it turns out Ruby has to have written out a bunch of rules on how you look up a method M。

 What if multiple mixins define the method。 What if the mix in defines it and the class defines it and so on。

 So just so you know， here's the rule。 When you're looking for a method M for some object object object so you can call the method。

 you look in objects class。😊，Then you look at any mixins that it includes。

 then you look in the superclass， then any mixins that that superclass includes。

 then the super superclass and so on。 So you check the class definition， then the mixins。

 And it turns out you check the mixins in order where a later include will shadow any earlier includes。

 I will not test you on that， I just wanted you to know that as part of a language definition。

 you have to resolve these issues and so Ruby did。As for instance variables。

 mix in methods can get or set instance variables if they do those instance variables are part of the regular class。

 and so if methods from two different mixings both try to use the same instance variable。

 they could mess each other up， so many people consider it poor style for a mix in method to access instance variables in any way。

On the other hand， in other situations， it is what you need to do or want to do。

 so I will not resolve that style issue。 I will just tell you that in terms of semantics。

 mixing methods can access instance variables of the object they are a part of。

So now that we've seen what mixins are， let me show you what everyone really loves about them in Ruby。

 turns out there's two mixins that are just everyone。

 they're just widely used and they make you smile because they really make it easier to program。

The first one is a mix in called comparable。 And here's what it does。

 It defines methods less than greater than equals not equals greater than or equal to or less than or equal to。

 And it assumes that any class that includes it defines just one thing。

 which is this threeway comparison operator。 This is sometimes called the spaceship operator。

 And what you're supposed to do with the spaceship operator。

 So I would take two arguments and return a negative number if the one on the left is less0。

 if they're both equal and a positive number if the one on the right is less。

 So let me just show that to you， I can show that to you just with numbers。

 the spaceship operator is defined on numbers3 spaceship 4 is-1。

3 spaceship 3 is 0 and three spaceship 32 is one。😊。



![](img/e67e249d6561307e233a88ff666cf200_5.png)

So it turns out that on numbers when you say is three less than 2 and you get false。

 that is actually implemented by the comparable mix in defining less than to call the spaceship operator。

All it's doing is that finding less than to call the spaceship operator and then see if the result is less than one。

 And if it is， then you return true。 Otherwise you return false。 Let's do that for our own class。

 I have an example here。I have a little class name all right。

 so name has three kind of fields in variables， first middle and last here's an initializer where you pass in first last and middle name。

 and then I define the spaceship operator and I define the spaceship operator take one other argument。

 the thing I'm comparing against and there's a bunch of logic here you know I compare the last name if the last names are equal I compare the first names if the first names are equal I compare the middle names。

 and I do all that using the spaceship operator on strings which is defined which is what all these are doing okay and so this is defined。

So in fact， I already have over here。 I've already defined two names。 N1 is Daniel Joseph Grosman。

 although I got it first last middle， that's not actually my name。

 and I made the same mistake here on N2 for Barack Obama Hussein instead of Barack Hussein Obama。

 but that doesn't matter。 I have these two names。 and the spaceship operator is defined on them。

 So if I ask N1 spaceship， N2， I get1。 and if I ask N2 N2 spaceship N1， I get minus-1。

 if I ask N1 spaceship， N1， I get zero。 that's all fine。 So it's a proper comparison。

 but I can ask all my other operators2。Can ask N1 equal equal N 2。 can ask N1 not equal N2。

 And the whole reason I can do that is this one line where in name， I said， include comparable。

 which defines all those other operators by having them called the spaceship operator。

 That's what mix ins are all about。

![](img/e67e249d6561307e233a88ff666cf200_7.png)

So let me show you the other main one that I think is even cooler。

 and that's this one called innumerable。 So innumerable defines lots of iterators。

 lots of those higher order methods that take blocks in terms of each All you have to do as the class implementer who's including innumerable is define each and then you get all the other ones for free。

 So I have an example of that as well。 I've defined my own little range class。

 of course you wouldn't do this because ranges are built into ruby just fine。

 but you know this range class defines each。 So the initialized methods sets a low and a high instance variable and then what each does is four low up to high。

 actually using a while loop it yields so it calls the block with I then sets i equal to i plus1 and goes around the loop again So I've already created a couple ranges over here。

 R1 is the range from3 to7 and r2 is the range from 5 to 12 and of course since I define。😊。



![](img/e67e249d6561307e233a88ff666cf200_9.png)

Each I could take R1， and I could say put S。 I could pass it a block that for each thing in the range。

 prints it out。 And sure enough， I get 3，4，5，6，7。 And if I did that with R2。

 I would get5 up through 12。But I also have all the other iterators too。

 comparable defines them all in terms of each。 So for example。

 count is defined in the comparable mix in and how about I count how many of the numbers are odd。

And I would get 4，5，7，9 and 11。 if I ask it on R 1， I think I'm going get3，3，5 and 7。

 you have R1 dot map。 you have r on do any and so on。 they're all defined。

 They're all included by comparable and they're all defined in terms of each。

 The mix and has no idea how to iterate through the elements of my range except that it knows to keep calling each to just call each with the block and then they do the right thing with the result。



![](img/e67e249d6561307e233a88ff666cf200_11.png)

![](img/e67e249d6561307e233a88ff666cf200_12.png)

Okay， so that is what everyone loves about Ruby mixs。 They are nice。

 I think this is a wonderful thing。 You don't need the full power of multiple inheritance。

 Ruby style mixins are enough。😊，But they're not a full replacement for multiple inheritance。

 So let me just wrap up by saying， you know， they would work fine for our kind of 3D color points。

 What I have over here in the code down at the bottom is suppose I defined a mix in color。



![](img/e67e249d6561307e233a88ff666cf200_14.png)

Now， this is controversial because it's using an instance variable at color。

 but it defines a getter and a setter and a method darkened。

 Then what I could do is my 3D points could subclass point。All right。

 my color points could subclass point and include color。

And my 3D color points could subclass  point3D and include color。 And this will all work out。

 And my 3D color points will have exactly the methods in the behavior I want。

 because I only get one super class， but I can include any number of mixs。



![](img/e67e249d6561307e233a88ff666cf200_16.png)

It does not work as well for artist cowboys。 so if I want an artist cowboy。

 I want everything that an artist has everything that a cowboy has。

 but it doesn't really make sense to me for either artist or a cowboy to be a mix in。

 A color mixing is arguably okay。 but artists and cowboys should really both be classes and if they're both classes you cannot inherit from both of them。

 So that is why while mixings are great。 I think they're a really neat thing in Ruby。

 I would never suggest that they are a full replacement for multiple inheritance。



![](img/e67e249d6561307e233a88ff666cf200_18.png)