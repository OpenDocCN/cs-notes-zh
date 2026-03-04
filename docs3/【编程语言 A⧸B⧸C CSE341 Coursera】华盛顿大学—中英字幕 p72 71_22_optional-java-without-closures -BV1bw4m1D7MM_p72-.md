# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p72 71_22_optional-java-without-closures -BV1bw4m1D7MM_p72-

In this optional segment we'll see how to use objects in a language like Java to simulate closures。

 it won't be pretty， but we will be able to successfully port the ML code from the previous segment。

Just to be fair to Java， the next version of Java Java 8 is supposed to have closures that are much easier to use and very amlike if you will。

 many languages that also support object oriented program these days also have closures this is a great bit of progress for programming languages and software and you'll be able to write you know convenient things using map and filter and length in a reasonably object oriented style this was done for a number of reasons I won't claim to speak for the designers of Java but it's going to make using collections easier。

 it's going to encourage a style that has less mutation which will make it much easier to write parallel code and Java so for a number of reasons after 15 to 20 years of living without it Java programmers will have closures but that's not really the point of this segment the point of this segment is how could you take a language with classes and objects like the core of Java is and write code like the。

Ml code we saw in the previous segment。 if that's what we wanted to do。 Now。

 there are perfectly fine， decent list libraries and Java that are not written in this style。

 They're not about map and filter en closures and things like that。

 They're in a more object oriented style。 They use more mutation。 And that's okay。

 But we're interested in seeing what our M code would look like using Java's language constructs。

So the key technique to fake closures， if you will。

 is to define interfaces with one method in them because a function is a lot like an object with one method。

 you can just call a function。 So for example， here's a generic interface in Java using the generic type parameters。

 A and B for alpha and beta that just has one method So anything implementing funk of type 1 and type 2 is something that has a method that takes a type 1 and returns a type2 and we'll be able to create objects that implement that interface and then those objects will act like functions from the argument type to the result type。

 we will have to put in those objects， fields that have whatever private data our closure would want。

Similarly， if we wanted to predicate something that returned true or false given an argument。

 here's a generic interface that for some type A takes in an a and returns true or false。

 So the key is to implement these interfaces with objects that have whatever fields we need。So。

 there you go。So now with that background and we'll get back to those in just a second。

 let's just start building up our linked list library and we'll start pretty much as you might expect for an object oriented library。

 we' create a generic type list that's parameterized by the type of the elements of the list will have fields for head and tail and we'll have a constructor here that initializes it with the head for X and the tail for X's Now this constructor simply will not work for the empty list。

 What should we do for that。 So here I'm going to take make a choice that I'm going to regret in a couple minutes。

 which is to have null represent the empty list。 It's a special constant in Java。

 This is fairly conventional that will use it for the empty list so the empty list will not be an object and will not have a class and so the special null constant and we'll see in a minute where that's going to get us into a bit of trouble。



![](img/ff3cef6949c17a63d6bf29b5cc3c62d2_1.png)

Okay， so now what we're going to do is we're going to implement map， filter and length。

 Those were the three functions in our library in ML for this list type we've defined and I'm going to make them static methods and I'm doing this because of that decision for nu so you see the code here。

 but it'll be easier to read and highlight if I flip over here to Emax where I have all the Java code I've already shown you is up above and here is my method for map。

 So this is the entire thing here。 it's a static method it is it is polymorphic。

 it is generic in two types alpha and beta because sure enough the result type is a list of beta and one of the arguments is a list of alphas。

 the other argument is one of these functionss from alpha to beta remember that interface it just has one method M and that method takes an a or an alpha and returns a B or a beta So given these two arguments。

And then I want to return the appropriate list of betas。 At this point。

 I can pretty much write the code like I do in M。If x is is null， the empty list， return null。

 the empty list。 Otherwise， return a new list of betas， and I call the constructor。

 I' build my new list out of F dot M of x's dot head。 So let's talk about that。 F is this function。

 That's an interface。 It has one method M。 I pass it in appropriate alpha。

 I get back the appropriate beta。 And then let's just recursively called map with the same object for the first argument and x's dot tail。

Pretty much like the M code does。 All right， So that's pretty nice。 Now， you might argue in Java。

 We don't encourage so much recursion because recursion is usually not as efficient in Java。

 particularly we do not have tail calls and things like that。

 I would argue this is better than the alternative。

I encourage you to code up the version on your own that uses a while loop instead of recursion。

 keep the pointer to the previous element， it's a bit of a mess。

 so I find this much easier to explain reason about I prefer this version。

So that's map filter is fairly similar， filter takes a list of alphas and returns a list of alphas so it's only generic over one type alpha Its argument is not a funk from alpha to beta。

 it's an implementation of the interface pre of alpha。

 but otherwise it's essentially filter again the body of the function once you survive the complicated first line without any type inference is not too bad if we have the empty list return the empty list。

 otherwise if taking this object calling its M method on the first element of the list gives back true。

 then we want x's do head in our results， so we return the new list of alpha with x's dot head and then calling a recursive call the filter with the same pre object and x's do tail。

 otherwise just filter of f and x's do tail。And then finally for length that's the third function we needed。

 I could again produce a recursive solution， but here actually the while loop version isn't so bad so I decided in importing my code to go ahead and just say static method。

 return an alpha length， take a list of alphas， no a closure needed， walk down the list。

 setting x is equal to x is do tail， incrementing a variable ants mutation。

 imperative update and then just return ants so that is my library。

Let's flip back to the slides here。😊。

![](img/ff3cef6949c17a63d6bf29b5cc3c62d2_3.png)

And talk about why I made these static methods。😡，So a more object oriented approach would be to make these instant methods。

 instance methods that the class would have methods map， filter and length that look like this。

 they wouldn't take list arguments because the enclosing object this would be the list they would just take a function that took an element of type T the type of the list and return a B and then we would make a list of B's。

 similarly filter would take a predicate over T's and length would take no arguments and just return an int The reason why this doesn't work very well is that it interacts poorly with our decision to represent the empty list with null Now clients users of our library will not be able to take a list X's and say xs do map or x' is filter if that list might be empty because if you try to call a method on null。

 you get a null pointer exception。 I think every Java programmer ever has suffered through null pointer exceptions and。

would force every client to check for null and deal with the null cases themselves before calling map filter or length。

 whereas our static methods could handle the null case for them。

So it turns out this is not picking on object oriented programming。

 The real problem here was our choice of using null。 In fact。

 a more objectoriented approach would be to not use null for the empty list to instead have two subclasses of the list class one for empty lists and one for non-empty lists I have not written that code for you。

 but what you do is you take the empty list subclass you implement map filter and length quite easily。

 map and filter just return another empty list， length return0 and then everything works correctly。

And there's no problem with it。 And I actually prefer that。 in my opinion。

 if you want to do object oriented programming， you need to rid yourself of the bad habit of leaning on null when it gets you into trouble for a code like we're writing here。

Alright， so now let's finish this story。 If you remember our ML code。

 we also had some clients of our library。 We wrote two functions。

 one that doubled all the elements and a list mapping across it and the other that counts how many ends are in it。

 Here is the code。 and it is admittedly a bit of a mess。 So let me explain what's going on。



![](img/ff3cef6949c17a63d6bf29b5cc3c62d2_5.png)

When we want to call double all， we want to define a double all method。

 I'm making it a static method here。 It wants to take a list of ints or integers and return a list of integers。

 All it's going to do when you call it is called list dot map with X's。

 And now what I need to do is pass in the appropriate object that is acting like a closure。

 So what I need to do is I need to make a new instance of that interface。

 And I'm using here an anonymous inner class。 this if you've never seen this syndax。

 it's mostly just syntactic sugar for defining a class that implements an interface and then providing an implementation of the appropriate method。

 But right here I'm saying make a new。Object that implements the funk interface for arguments integer and integer and let its method M take in an integer X and return x times 2。

 So a lot of clumsy syndax， but it gets the job done and that will double all the elements in the list。

 As for counting the ends， I can write the same code I wrote an M。

 I want to take the length of filtering to include only numbers that equal n。

 I do the same thing where now I create an implementation of the pre of integer interface and the body of one。

 my one method M takes an x and just asks if x equals n the one thing that's neat here is in Java。

 you can use this n that is in scope here。 but only because it's declared final Java will not let you do this。

 If N can be updated and it's a longer story than I want to get into here。

 but there are good reasons for it。

![](img/ff3cef6949c17a63d6bf29b5cc3c62d2_7.png)

And so that's the end of our story。 So essentially what our clients do is if you want to map from a list food to a list bar。

 you define a class C that implements the interface funk bar commafo and use its fields to hold any private data because we didn't need any of those fields。

 we just used this anonymous interclass which is mostly syntactic sugar。

 and then we passed the resulting object to map the count ends example was more interesting because we did need that n in our environment。

 we could have created a class with a field instead we did that trick that if you put final you're okay All right。

 that's your advanced wizardry for Java closures faking closures in Java by using objects。



![](img/ff3cef6949c17a63d6bf29b5cc3c62d2_9.png)