# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p145 4_02_classes-and-objects -BV1bw4m1D7MM_p145-

To begin our study of Ruby， we really need to understand classes and objects because they're the center of the entire language。

 so let's jump right in。There are just a few rules that will guide pretty much our entire understanding of the Ruby language。

 so let's go through those and then write some code that shows how they work。So in Ruby， all values。

 every result of a computation of an expression is going to be a reference to this thing we will call an object。

And these objects communicate with each other and we use them by calling their methods。

 Me are things like functions， but they belong to objects， as a synonym。

 we often sometimes say that we send an object a message。

 so sending it a message or calling one of its methods are really the same thing。

We'll say that each object has its own private state， I won't show that in this video。

 but we'll see it in just the next one。And then each object has a class that's the other thing we'll introduce in this segment。

 And what that class does is determine the object's behavior。

 It's the class that defines the bodies of the methods that then belong to that object。

 so the class is going to contain those all important method definitions。

 If you've seen another object oriented programming language， some of this will be seen similar。

 Ruby is just more extreme about it， in that every object only has private state and all that we have in our language。

 our objects。So what we need to do first is learn how to define classes because then we'll use the classes to make the objects。

 and you see here the basic syntax and I'll show you an example here in just a second。

 You say keyword class the name of your class which has to be capitalized actually then in equals then one or more method definitions。

 which all look like deaf name of the method and so on I'll show you an example and then that can be your class definition。

 We'll have some additions to class definitions as we go through the language but this will get us started。

 So let's just go over here and do it a little bit。

 I've got a blank file with just some comments in it so far。 and let's just define a class A。

 I don't think I need the equals actually， which I had on the slide。 I'll fix that later。

 and let's define a method。 This is a method M1， that objects that have class A will have。

 And when you call this method you always get back 34。 So that's all there is to it。



![](img/193ff8d955b4ce60417ff5f3eabc8861_1.png)

Let's define a second method， let's have this one taken in two arguments X and Y I'm in a dynamically typed language so I can pass in any objects at all。

 and then let's have the body of my method first have some local variable Z that will hold7 then how about a conditional about if x is greater than Y then false else X plus y times Z end so this that if elseN that's my conditional statement it turns out that these new lines are actually important。

 you need the then branch on its own line if you want to put it on the same line。

 you need more syntax， you need the keyword then and you can look up in the ruby documentation。

 the 50 different ways to write a conditional expression and I'm only exaggerating slightly and then a second end that will end the method definition and then if that's all I wanted my class I could then end the class and if that were my file it turns out I can then go over to IRB which I。

They have open here， and I could load the file that I just made。And that would work fine。

 And then I could。Make objects whose behavior is defined by that class。

 And the way you do that is you write the name of the class dot new。 and that would make an object。

 Now， since I want to use this object later， how about I assign it to a variable。

 So a equal a dot new。 And now what I can do is I can call that object method。

 So a refers to an object。 So if I wanted to call the M1 method， I take the object right dot。

 then M1。And I get back 34， because if you remember here from the code， the M1 method returns 34。

If I call the M2 method， I get an error if I don't pass the right number of arguments。

 it really is a two argument method so I can pass arguments in parentheses with commas in between them。

 so if I for example， a do M2 with 3 and 4， I'll get back 31。

 and that's because over here in the code if you follow the arithmetic if x is 3 and y is 4 I end up taking the L branch and 3 plus4 times 7 is 31。

So that's just one class I could make as many objects of that class as I wanted。

 but instead how about I make a new class to show a couple different things。

 so how about I make a class B and it can have an M1 method that takes no arguments and returns for how about it also has an M3 method that takes one argument X。

 you can put parentheses around it if you want to it's optional and what it does is it takes that X object。

Sends it the message abs， So it calls its abs method。Multiplies that by  two， and then adds。

What I'll call self dot M1。And there and there。 So what is self。 Se is a special word。

 It's kind of like a variable， kind of like a keyword。 And what it says is this object， myself。😊。

So whenever I execute this code， it'll be because I called some method on some object。

 and what self always means is the object I called the method on。😡，So in this case。

 if I say self do M1， that means called this method with the same object on the same object。

 So it'll be sending yourself a message， in particular， this message， which will then return a four。

So if I had this， I could go over here， let's real quick。

 quit the IRB and start over and load classes objects。Dot R B， Okay。

 and now what I could do is I could make， you know。

 I could continue just like it did before of saying， you know， A is a dot new and then M dot M1。

 But I could also make a variable that holds a B object。Did I forget to save this here， I did。 Okay。

 let's just reload it。All right， and now it should work good。

 and now I could say B dot M1 and I would get 4 because its M1 method always returns4。

 or I could try B dot M2 here， it's an undefined method， even if I pass with two arguments。

Objects that have class B do not have an M2 method。 If you remember back here over the code。

 instances of class B have an M1 method and an M3 method。 So similarly。

 I could not say a equal a dot new and then a dot M3。 that would not work。 But I could say B do M3。

 It takes one argument， how about 5， And it ends up returning 14。 Why is that， Because if you send5。

 the abs message， you end up getting back 5， it turns out this is the absolute value method。

 if you called numbers with a。 So if I say5 dot as， I get back 5。 And if I said-5 dot a。

 I would also get5 multiply by 2， you get 10， then call self dot M1。 and you get 4 back。

So that's most of what I wanted to show you in terms of code。

 I'll show you one more thing here in a second， but just to review what we've done so far。

 once we've defined a class， then you can say class name dotnu to create a new object。

 whose class is that class name。

![](img/193ff8d955b4ce60417ff5f3eabc8861_3.png)

Whenever you write E do M， E is an expression M is some method name。

 What that does is evaluate E to an object and then call that objects M method。

You can also if you're calling a method with zero arguments， right left parenthesis。

 right parenthesis， if you want， it's optional， it's a matter of personal taste and style。

 methods that take arguments， you separate by commas， these parentheses are occasionally optional。

 but you usually need them， and I recommend you just always put them in if you have even more than one argument and even one。

 it's probably wise。In terms of variables， we did see a few variables here。

 methods can use local variables。 They just start with a letter and you just put them anywhere you want in the method body and their scope is the entire body。

 So this is a strange thing we haven't seen in languages we've studied before。

 You don't declare your variables。 You don't have any kind of let expression。

 You just assign to them anywhere and they spring into existence for the entire method body variables are mutable。

 I didn't show you that but I could have， for example。

 over here where I had this local variable Z in this method M2 anywhere I wanted in the method set it you know maybe made it plus equal 3 that would turn Z into 10 for example。



![](img/193ff8d955b4ce60417ff5f3eabc8861_5.png)

![](img/193ff8d955b4ce60417ff5f3eabc8861_6.png)

Variables are also allowed in the Reel or outside of a class a top level for when you're testing your programmer playing around with things。

 and a variable will always have as its contents a reference to some object。

 if you update a variable， then it will refer to some different object。

 but it always refers to an object。And finally， we have this special thing called self。

 Se is a special word。 It refers to the current object whose method is currently executing。

 And so when we wanted one method to call another method in the same object。 we wrote self dot M。

 Now， the truth of the matter is I was showing that to you so that we understood the idea。

 you do not have to write self dot， if you call a method without anything to the left and no dot。

 it's implicitly self， that's the default。 So the syntactic sugar you can leave off the self dot。

The one other thing I wanted to show you is that you can use self by itself。

Pardon the expression there。 When you just write self rather than calling a method of self。

 you really do mean the whole object that is currently executing。 And that can be a useful thing。

 So let me show you a quick example here。 I have another class down here already defined C that has three methods。

 M1 M2 and M3。

![](img/193ff8d955b4ce60417ff5f3eabc8861_8.png)

M1 and M2 just print a string higher by and this print command doesn't put a new line afterwards。

 and then M3 just prints out a new line。 So you move to the next line。

 But instead of just ending with the print statement， they then。

 as their next expression on the next line returns self。And what that does is kind of weird。

 It has these methods return themselves as objects。 And as a result。

 it lets us string methods together in kind of a convenient way。

 So let me show you that here in the code。 Let me just make a new C object。Okay。

 so now what I could do is I could call C dot M1， and that would print high。

But because it gives the object back， I could take the result and call M2。

 and then it would print high by， and I could string these together as long as I want how about dot M3。

 dot M3， do M1， do M1 do M3， and then it printed high by a blank line and then high and high。😡。

This is not a particular language feature。 All that's going on is since C do M1 returned an object。

 I can then call its M2 method。 It just so happens that what C do M1 returned is the same object as C is。

 so I could string together these multiple calls in this way。

 and this is a fairly common idiom that you see in Ruby。😡。

The last thing I will mention about the code before we end this segment is that I didn't write any semicoons here between my expressions。

 you can do so。 you're welcome to do so， but in Ruby， often new lines。

 putting things on separate lines have significance that because these are on separate lines。

 I don't need a semicolon。 but if they were on the same line than I would。 So in Ruby。

 it often matters where you put new line characters and that can take a little getting used to。

 So to assure you of any concerns， indentation never affect semantics in Ruby。

 it does in some languages， but indentation， like in the other languages we've studied is just a matter of style。

 So we've seen a lot of new things here， but the two important things we saw where classes for defining methods and the new operation for creating objects of certain classes and then we could call those methods。



![](img/193ff8d955b4ce60417ff5f3eabc8861_10.png)