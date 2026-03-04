# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p26 25_15_benefits-of-no-mutation -BV1bw4m1D7MM_p26-

In this segment， I want to talk about how it's a really valuable thing that in ML。

 we don't have mutation for most forms of data that once you create a topple or a list or a variable。

 there's no way to change the contents of that data。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_1.png)

So this is gonna to feel like a little bit of a strange segment。

 but it's actually a big idea in the course because I'm not going to teach you anything new。

 I've already shown you all the features you need for homework1。

 instead we're going to focus on a non-fe， something that M doesn't have。

 So how can the lack of something in a programming language be important for that language naively you might think well you should always give programmers more and more stuff they can use and then they can decide whether to use it or not but when you have a lack of a feature in your language。

 then when you're writing code， you know that no one using your code will ever use that thing because it can't and that will make it easier for you to write your code correctly and to understand the results that your code produces So in fact。

 one of the major things that makes functional programming functional programming is that when you create some data like a pair or a list there's no way to subsequently change the contents of that data you have to make a new。

Of data that has some different values in it。 So let me show you why this can be a valuable thing。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_3.png)

Let's start with a somewhat simple example。 I've shown you a function that does this before。

 This is a sort pair function， so it takes an intstar int and it returns an int star int if you call it with three comma 4。

 you get back three comma 4 but if you call it with four comma 3 you get back three comma 4 because it always sorts the two things in the pair。

 So here are two versions of the function and in the first version when the first component of the pair is less than the second component of the pair we just return the pair because that's already a correct answer whereas in the second version of the code。

 we make essentially a copy of the pair。 we return a new pair that has the first part of pair and the first part in the second part of pair in the second part。

So suppose that you had say this second version and you wanted to maintain it， edit your code。

 evolve your code to be the first version instead， because that seems simpler or more efficient or whatever。

Is it possible that some client， some user of your function。

 would break because of that change you made And in Ml， the answer is no。

 the two versions of these functions cannot be distinguished by any code in the language that uses those functions。

 You can argue the first is better style， but you can't argue that they make any difference to users of the code。

But if your language allows you to mutate， to update the contents of pairs， this isn't the case。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_5.png)

Suppose that we bound to x， the pair of 3 comma 4。And then we bound to Y the result of sorting that pair。

Now there's two possibilities if we don't know how sort pair is implemented。

 maybe as you see in this picture over on the right， Y refers to that same pair that was past the x。

 So x and y are now what are usually called aliases in most programming languages or the second possibilities that x and y are not aliases that y points to some different pair 3 comma 4 in M it doesn't matter。

 but if there were some way in Ml to mutate， say hash1 of x to change it。

 so instead of holding three， it holds5， now we have a very difficult question。

 does that change from three to5 affect what y refers to or doesn't it It depends now whether x and y are aliases。

 If you don't have mutation， then you can't tell if things are aliases or copies。

 This makes it easier to implement sort pair and makes it easier to use sort pair and reason about the results。

 and it even can even make it easier to implement languages like M。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_7.png)

Recentlyly。So let me show you a more interesting example where I'm going go from pairs now to lists and let's use one of my favorite functions in the whole course list the pen。

 This was this elegant recursive function that takes two lists。

 x's and Y's and returns a new list that is all the contents of x's appended to all the contents of Ys right and now we might ask ourselves if I have the list  two comma 4 and the list 5。

30 and I append them。What， if any aliasing do I have。

 Do I have a situation like here in this top picture where x holds the list 2，4。 Y holds the list 5。

3，0， and Z does hold the list 2，4，5，3，0， but part of that list alias is y。

Or does this append function， in fact， make an entirely new list for Z？Well， once again。

 clients can't tell so you can implement a pen either way and it will behave the same way in your program。

 even though this bottom version takes up a little more space。

 it turns out the code up here implements the top picture。Because when x' is is empty。

 we just return Y。 We don't copy wise。 We just return what will become an alias to Y。

 So here we're actually saving space。 and in languages where you can update the elements in a list。

 This is usually a really bad idea because if someone comes along and does some mutation on this list Z。

 it can end up affecting the list Y， which may very well not be what you want。 So once again。

 the lack of mutation is what is helping us not have to worry about all this， Allright。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_9.png)

So in ML， it turns out that we create aliases all the time and we don't even think about it and that's okay because you can never tell if two things are aliases or a two copies of identical values。

 Are they pointing to the same pair of three comma4 or to two copies of three comm4 and in fact。

 the tail operation for list is probably a great example。

 It's a very fast operation because it just returns an alias to the tail of the list that was passed as its argument。

Ml programs would be much less efficient if the tail function made a copy of the entire list minus the first element。

 So when you're writing functional programs， you don't worry about these aliases。

 You just focus on your algorithm because， you know， there's no mutation。

In languages that have mutable data， which is pretty much every nonfunctional language， for example。

 Java programmers are absolutely obsessed with the identity of objects。

 am I making a copy here am I creating an alias are these two things reference equal or do they just answer true to the equals method and I'm not picking on them for being obsessed In fact I think they have to be obsessed because any time you have aliases。

 the assignment statement affects all of them and if you don't have aliases。

 it affects only one of them， and you have to understand this to understand how your program behaves and whether your code is correct so in the next segment I'm actually going to show a rather tricky example of this in Java since we don't require Java for the course itll be totally optional but it'll show you just how hard it is to reason about aliases and assignment statements and in ML the way we avoid having to do that as we just get rid of the assignment statements。



![](img/0d105ca33d1ca7a1fb865515d9b8f3bb_11.png)