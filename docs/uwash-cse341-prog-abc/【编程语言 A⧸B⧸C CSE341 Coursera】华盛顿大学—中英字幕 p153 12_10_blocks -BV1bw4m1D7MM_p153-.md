# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p153 12_10_blocks -BV1bw4m1D7MM_p153-

In this segment I want to start our study of Ruby blocks B are probably the strangest feature in Ruby compared to similar features in other languages。

 but they're also one of the most convenient and most frequently used。

 so it's worth studying them and the great news is they are so close to closures that we'll find them convenient and useful from the very beginning so let me start with what is normal en closure like about them。

Blocks are things that you can pass to other methods， essentially as anonymous functions。

 so that the callee can then call that function and use them。

Like function closures in other languages we've studied， they can take zero arguments， one argument。

 two arguments， and so on， and like closures， they use lexical scope when the colleague calls the block。

 we evaluate the block body in the environment where the block was defined。

 not where the block is being called。So the examples you hear see on the slide start to show you some of the syntax。

 a block unlike a lambda in racket or Fn arrow in ML is just put between braces So on this first line we're passing a block that prints high as an argument to this method three dot times it's just passed differently than other arguments and we'll talk more about that in a second similarly on this line and then on the last one this one on the last one is on the last line is a block that takes an argument X。

 so let's real quick type all these n so we can see what they're doing。

 So three dot times times is just a method that's defined on numbers and it takes in this block by just putting it next to the method call and it runs the block that number of times so this will print hello three times。



![](img/b9e1ab7cf39582be5843613565d64c17_1.png)

If you have an array。There's in each method and that each method calls the block once for each element of the array。

 So this will also print three times because the array has three elements。 Now。

 much more useful is to do something with the actual elements you're being passed and to do that when you call each on an array。

 you can take an an argument。 How about X。 and then we can just print that。

 it'll convert these numbers to strings and it prints out 4，6，8。

 And just to emphasize that these things really do have lexical scope。

 let's have a variable here where we're going to define our block about I is 7。

 And now let's call each on an array holding 4，6 and 8， where we ask if I is greater than x。

 then let's put print， let's say x plus1， otherwise， let's do nothing。

And that will print 5 and 7 because the8 is greater than the7。

 And so we didn't do anything for the last element of the array。

 So this is high order programming in Ruby。 This is how you normally do it。 And so far。

 I've tried to make these things seem very normal。 Now。

 let me show you some things that are actually a little bit strange。



![](img/b9e1ab7cf39582be5843613565d64c17_3.png)

So one strange thing is that you can pass either zero blocks or one block to any method call in any message you get to pass zero or1。

 you can't pass multiple blocks， but you can pass one。Now， if you pass one。

 the colgue might ignore it。 The colgue might give an error conversely if you don't send one。

 the colgue can even do different things based on whether or not you send one。

 So this is separate from the normal arguments。 You pass your normal arguments in parentheses separated by commas。

 and then on the side， literally syntactically next to it。 you either do pass a block or you do not。

OkaySo the syntax is， as we've seen， just brace and then some expression that is the body。

 Or if you want your block to receive arguments。 when the colleague calls it。

 then you put them between these pipe characters and separate them with commas。

 So this last example here takes two arguments， which we'll call X and Y。

 I'll show you in the next segment how a colleague can use a block。 Here。

 we're just passing blocks and letting the library methods that take blocks call our blocks in their bodies。

 There's a second syntax， I'll show you in a bit， then instead of braces。

 you can use do for the left brace and end for the right brace。 This is the preferred style。

 usually when your blocks are multiple lines long， whereas the braces are usually preferred for one line blocks。

 And other than that， they're almost equivalent， they only have syntactic differences in terms of precedentnce and things like that。

So what are these things so good for I mean3 dot times was nice well we already saw one neat thing which is this is how we can apply the same code to every element of an array by using each method on arrays。

 but it turns out the standard library and Ruby is full of methods that expect blocks to be passed to them。

So because the standard library makes such great use of what is essentially functional programming and higher orderder functions。

 Ruby programmers almost never use explicit loops。 There are loops in the language。

 but almost no one uses them because all the standard things you need to use loops for There is a more convenient way to just take some method that's in the standard library and pass it a block。

 So let me just for the rest of this segment， show you a bunch of examples。

 including those that were on the slide but by typing them out， I think will get a better sense。

 and I will mostly just do things over arrays。 So let's create a new array that takes a size 5 and it turns out the initialized method for the array class will take a block it's optional if you don't pass it。

 then you just end up with5 nils but if you do pass it you can actually have it take the index of the array and have that compute the initial value in that position So with this call here。

 I end up with 48，121620。😊。

![](img/b9e1ab7cf39582be5843613565d64c17_5.png)

Okay， so now if I did something like call a dot each with something that prints x times 2。

 it's going to print on one line each 8，16，24，32，40。

 And this is essentially just applying the same code to every element of the array。

 and it's certainly more convenient than some explicit for loop or while loop。

 like you see in other languages to iterate over array elements。

We have other nice things in this language， how about map？

I told you Ma is a common name in computer science。 Ruby was happy to use it as well。

 What if I mapped the computation X goes to x times 2 across the array。

 Then what I get is a new array holding 8，16，24，32，40。 So I'm not printing here。

 I really am creating a new array。 It has size 5 and its second index is 24 and so on。 So that's map。

 we know map is wonderful。 There's a bunch of other methods essentially higher order functions over arrays。

 How about a dot， any question mark。😊，So what this does is it applies the block to every element of the array until it finds one that the block answers true for。

 and then it returns true。 And if it doesn't find one， then it answers false。

 So a dot any with this computation return true， because there are elements in there greater than 7。

 but there are none greater than 700。 So this is how you find whether some property holds of some element of the array。

 As you might imagine， there's also in all。 It is not true that everything in the array is greater than 7。

 but it is true that everything in the array is greater than -7。So those are useful。 By the way。

 these methods do not require blocks。 If you just pass one without the block。

 it sees if anything in the if everything in the array in this case answers true is true。

 And as I mentioned once before in Ruby， the only things that are false are false and nil。

 So there are no falses are nil in this array。 But if I did a plus an array holding false and asked all I would get false and similarly。

No。I would get false， but anything else， I would get true。And so on。 So there's a few more。

 There's one called inject。This is what we called reduce。 so for example。

 if I have an initial accumulator of zero， that's the ordinary argument and then the block requires two arguments here。

 the answer so far， which I'll call act and the next element which I'll call ELT and we can just add them together and as I've shown you many times that will sum up all the elements of the list it turns out and Ruby if you leave this initial accumulator off it will use the first element as the accumulator which for summing will work just fine other times you want an initial accumulator that's not the first element of your array and then you pass it as the argument to inject so inject is just ruby talk for for reduce and as long as I'm mentioning it a dot collect is the exact same as a dot map they just gave it a second name it is sometimes called elect collect by others what about filter well it turns out there is no filter method。

 that's just an undefined method。 they called it select but it works just like what I like to call filter So if I filter let me just remind you。

It's actually in this array for81216-20， and if I filter or in Ruby talk select for x greater than 7。

 I will get 8，12， 1620， or if I wanted to say and x is less than 18， then I would just get 8。

12 and 16。So let me that's all I wanted to show you with as。

 let me show you one other thing which is really why even when you think you need a loop。

 you can avoid it and that is let's just define a little method here where what I want to do is create the range。

 I'll explain what ranges are a little bit more in a future segment。

 this is just an object that represents the sequence from zero up through I。

And it has an each method， so this is not technically an array， but it acts a lot like one。

 So it has in each method。 This is the other syntax for blocks I promised you that's better for multiple lines。

 So do is just like the left brace。 So for each value J from0 up to I where I is the argument to this method let's do the following let's first print two spaces times J。

 So the times operation on strings will that make that two J spaces。Now in here。

 let's do a nested range from J up to I， and for each of those， let's have a little one line block。

 So for each K from J up through I， let's print K and then a space。And then after we do that。

Let's print a new line character。And then let's end this block。

 So this end matches the do that is four lines above。 and then let's end the method。

 I'm not just to find a method。 Now I'm about to call it。

 You can try to figure out what it's going to do。 It's just little pretty。 If I pass it 9。

 It prints out this nice little grid with triangles of numbers from 0 up to 9。

 This is the sort of thing you would use nested loops for in most programming languages。

 We morally have nested loops here。 But really， what I literally have are method calls the each method on these range objects passing in blocks。

 that then the collie uses， and this is the result I get。 So that's our blocks。

 The next segment willll learn how to use blocks in our own methods。

 And then we'll talk more about how they're not quite fully closures。



![](img/b9e1ab7cf39582be5843613565d64c17_7.png)