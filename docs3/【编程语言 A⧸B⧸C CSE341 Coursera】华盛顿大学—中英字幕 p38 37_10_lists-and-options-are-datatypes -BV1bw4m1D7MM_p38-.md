# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p38 37_10_lists-and-options-are-datatypes -BV1bw4m1D7MM_p38-

In this segment I want to go back to talking about the lists and options that we learned earlier and tell you the truth about them。

 which is that they're actually data type bindings and a better way to use list options is with case expressions so to explain that let me first show something that's not the builtin list and options。

 let's see that we already know how to use data type bindings to define our own recursive structures like the arithmetic expressions we've been dealing with。

Now， we can realize that that's all linked list is。 is itself a recursive。Little data structure。

 So like you see here on the slide， if I wanted to create my own list of integers that had any number of integers in it that I wanted。

 I could define a data type my int list that was either empty for the list that has no items in it or maybe built out of the cons constructor where I would have an int and then another int list So then I could do a couple things。

 I could create a variable of type my int list， like I do here。

 This is the list holding4 and then 23 and then 2008， which happens to be into my nephew's birthday。

 And you see that this is just using constructors the way we understand them。

 the cons constructor here has to take two argument， an int and my int list。

 So 2008 and empty that fits that should type check。 So this here， cons 2008 empty is a my int list。

 So that my int list could be the second argument to this cons constructor with the 23。

 and then that can be the second argument to this cons constructor with the first argument of。

So this overall variable X holds in my inlist。 So that's an example of using this list type that we defined ourselves。

 And then we could write in append function， for example， over these things。

 So we would just use case expressions。 We'll use our append algorithm that we understood for the built in list。

 but we'll use it for this data type binding instead。 So if x' is was made by the empty constructor。

 then just return Y。Otherwise， we can pattern match X's as X and X is prime。

 You can't do this in many programming languages， but it's a nice sort of mathematical name for a variable here。

 X is prime。 and then what we will do is we will create the my int list that you get from calling the cons constructor with X that's the first element here and the result of the recursive call of a pen my list with X' is prime and Y。

 So that's simple。 There's nothing to it。 so we don't need the lists and options that are provided by M。

 but they are there， they're convenient。 You should use them when they're available。

 so this is bad style。 You should use M's built in list。

 I just wanted to show it to you so that the pattern matching I'm about to show you for the built-in type definitions seems as unmysterious as it should。

Okay， so let's do options first just because they're a little easier to read and understand。

 It turns out I previously told you that you made an option either with none or sum。

 and then you tested whether you had a none or a sum with is sum and you got the value out of a sum with vala。

Well now what I'm going to do is I'm going to stop using is some In as soon as I tell you a tiny little truth。

 which is that option types are made from a data type binding and none in some are just constructors。

 So yes， you can make things with none in sum， but you can also use them in patterns and so you can use them in pattern matching in case expressions。

 So here's a little function that takes in an int option and if it's given none， it returns0。

 if it's given sum of I it returns i plus1 and it uses pattern matching exactly like we've been studying。

All you have to know is that N ON E， all capital and SOmeE all capital are constructors for a data type binding so they can appear in patterns。

 None carries no data， so you don't have any variables here。 sum carries one thing。

 So we'll have one variable here， which will then be bound to whatever is under the sum。

So why is this better style than using Ium In for all the reasons that we like case expressions。

 you can't forget one a case or the other， it's pleasant to read。

 you never make the mistake of applying a Val to a nun which leads to a runtime error and so on so for homework2 and in general when programming ML you usually prefer this style to Ium In we just use those so that we could learn one thing at a time they work fine。

 they're enough for options， but I like case expressions more。So that's options。

 Now let's do the lists that are built into ML。 so it turns out that they are just constructors as well。

 So the same way we're not going to use isum orvallo anymore， we're not going to use head。

 tail or null either。OkayInstead， we're going to use case expressions。

 and our patterns are going to use bracket bracket for the empty list and colon colon for non-empty list。

 Now， these look strange because they're not。 They don't look like the other constructors。

 And I actually kind of wish M had not made this decision of having them look different。

 it's kind of a historical thing， people find it more pleasant to read。

 it just makes the patterns look a little bit different。

 even though the exact same thing is going on。So let me show you two examples here。

 a function for summing all the elements in a list and a function for app two list together All right so this first one。

 I have this list x's and I have this case expression and my pattern for the empty list just looks like bracket bracket So just like none No& E was a pattern bracket bracket is a pattern and it matches the empty list and the sum of all the numbers in an empty list is just zero that is the proper base case for a recursive function when you write a pattern for colon colon you might expect here let me just flip over to over here you might expect that the pattern would look something like colon colon x comma y for the two variables the head of the list and the tail of the list it doesn't look like that instead we put the colon colon in the middle So this is just a pattern just like with any other constructor but we put the first variable on the left and the second variable on the right and then we can use those variables as always in the right hand side of the pattern。



![](img/584ea48dab86e19aa7cb835ab9481beb_1.png)

![](img/584ea48dab86e19aa7cb835ab9481beb_2.png)

We write x plus sum list of x is prime， and this I find to be a very elegant short function that directly captures the idea of how you sum the elements of a list。

 You see if the list is empty， then return 0， Otherwise。

 let the first element be X and add that to the sum of the rest of the list。

 which is in the variable x is prime。So I was like showing aend。

 here is the proper way to write aend using case expressions。

 it's the same algorithm we've been using， I already showed this to you for the list type that we defined ourselves now here it is for the built- in lists and this is very pleasant to read as well pattern match on x's。

 if it's empty the result is Ys， otherwise it's the first element of x's cons on to the result of a。

 the rest of x's onto Y'。Allright， so。Why do this， As I mentioned for options。

 and it's the same for lists。 You won't forget any cases。

 You'll never make the mistake of applying tail to the empty list， that Tl function and so on。

 Since I really want you to learn this， the same way that on the first assignment。

 I required you to use is v of null head and tail on the second homework， I forbid you from doing so。

 Any time you want to access the thing under a sum or any part of a list。

 anytime you want to see if a list is empty or or see if option is none or sum。

 you have to use case expressions， you have to use pattern matching because I want you to get used to them。

Now there is a fair question here。 if there's so much better。

 why are null and tail and vvin is some predefined for us。 I mean， after all， Dan。

 if case expressions are so good， why would the makers of M and providing the library and provide these little helper functions。

 Well， few reasons。 first of all， they are useful， sometimes as passing as arguments to other functions and we will see that once we start talking about first class and higher order functions in the next section of the course。

 The second reason is I will be honest with you， they are sometimes more convenient than putting a little case expression right where you need it。

 but for the sort of examples I've shown you here like some list and append list that really is not the case And the third reason is they're easy to define they're not a big deal。

 you could define them yourself So the creators of M thought this way by providing them to everyone will all kind of use consistent names for these little helper functions in the situations where people want to use them。

😊，So what we now see is that our language ML is actually getting smaller here。

 We didn't actually have to add options and lists to the language。 We have data type bindings。

 they're just convenient useful ones that were predefined for us。

 and we'll see that we couldn't quite define lists and options the way I've shown them here ourselves and I'll explain why that is in the next segment。



![](img/584ea48dab86e19aa7cb835ab9481beb_4.png)