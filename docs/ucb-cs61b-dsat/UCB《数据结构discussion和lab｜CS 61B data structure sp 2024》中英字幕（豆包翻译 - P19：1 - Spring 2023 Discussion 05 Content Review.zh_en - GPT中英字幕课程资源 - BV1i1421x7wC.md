# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P19：1 - Spring 2023 Discussion 05 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼For me for me。🎼Oh比。

![](img/eee5baf3bc5adf7412c9a1620d8d59eb_1.png)

Hello everyone and welcome to CS6 UNB Spring 2023's Walkthrough of discussion number five。

 which is about iterators， iterables and polymorphism。First up。

 some quick announcements which again may or may not be relevant to you by the time that you see this walkthrough。

 but weekly survey for is due on Monday the 13th。Lab 5。

 which is about Git is due on Friday the 17th Project 1 B Array deck is due on Wednesday。

 February 15 and lastly Project 1 C， which hasn't been released yet at the time that I'm recording this I don't think will be due next Tuesday February 21 All right let's jump right into some content So first we will talk a little bit about polymorphism and more specifically subtype polymorphism General speaking polymorphism describes the ability for methods to work on a variety of types this gives us more general code or in other words a single uniform interface that can work with many types I think how Josh introduced this in lecture with generics was with this this stand in character that was like literally the letter T so T represents some generic type object in Java and it's just a stand in for what comes later so as an example of that we。

😊，Haven't really gone super I don't think we've gone super in depth in the idea of parameterization and Java。

 but I'm gonna to give a brief feeliel about it right now。

 but sometimes actually I think this is a great analogy to make to project 1 a but I believe that in project1 a when you're writing tests for like your linkless deck or whatever it was good for you to test with linkedless decks of type string and also type integer or whatever object you wanted to pass it like dogs even right and whenever you specified whether it was a linkedless deck of type string or of type dog you put that type inside of the angle brackets right so it would say like linkless deck and then the angle brackets and then string or something like that So when you implemented。

😊，Link was deck to use the deck interface Do you remember how the deck interface also itself had the parameterization with that generic stand in T the same idea here where you're saying okay T is going to be some object in Java we don't know what it is but we want our program to work on all types of objects regardless of what t is that's a good example of polymorphism okay。

😊，Subtype polymorphism more specifically describes the fact that subtypes of a class or interface are also instances of that class or interface。

 so maybe maybe you do or maybe you don't remember from last week when we did discussion for and we were doing dynamic method selection with inheritance so we had an animal class and we had dog the dog and the cat classes which themselves were child classes of the animal parent class。

😊，Well， the idea here is if we have some function like gr that takes in an animal。

 if we pass in a dog or we pass in a cat to that gr function。

 that function will run just fine in Java for us because dogs and cats themselves are types of animals right so we know that we' be okay because of subtype polymorphism。

A good example of this down here would be so remember that any method that takes in the parent type will take an instance of the subtype and as an example let's say we have this public comparable array and then we bind its type to be of type T where T implements comparable so here we're saying we have the class comparable array and it's going to be of objects of type T that are comparable and comparable array itself implements comparable。

😊，So our comparable array is polymorphic It can work with any type that is comparable because we bind our generic type T to be comparable items only with these this parameterization over here and now we can do something like T item1 some variable T item two is some variable and item1 do compared to item2 we know that's going to work because we said that T is comparable right and even more broadly we say that our comparable array is comparable so we can compare a comparable array object with another comparable array object and within that compare the elements within each comparable array because they're going to be of type T okay which itself is comparable so that's like a whole lot of words I feel like this slide never really makes too much sense to me until I start like coding up the questions so I'll leave this to question one and feel free to post on Ed if you ever have any questions about this because I know it's a little bit confusing。

😊，But yeah， okay。So next up a little bit about comparators which is a pretty common example that you might see of polymorphism and subtype polymorphism generally in the real world or in Java specifically so comparators I believe Josh talked a little bit about them in lecture。

 but they are an interface in Java and comparators like many other interfaces take or are parameterized by type T okay so we're saying here that this is a comparator that compares objects of type T。

😊，And the big like most important method that you need to fill out if you're implementing comparator is this compare method which turns an int and takes into two objects of type T。

So it takes in two objects of the same type and outputs a negative integer if01 is less than02。

 a positive integer if  O1 is greater than 02 and it will output 0 if01 is equal to02。

So you notice that on the slides the less than the greater than the equal to are in quotes and I was also doing like air quotes and the reason for that is because what does it even mean for an object to be like less than another object right like if we got lucky and our T was like an integer great cool we can just compare numbers directly with like a less than or the greater than symbols right but T could be anything in Java it could be any kind of object right it could be a string it could be a character it could be a dog it could be a C62 andB student how do we compare these in。

😊，In a way such that it outputs a number because like those are not inherently or at least not obviously numerical in nature right like dogs。

 how would you compare two dogs numerical it's kind of hard to do that right and that's the beauty of the interface and polymorphism generally speaking because we're like hey like。

Here's what the comparator interface should do or like here's an idea of how it should function and then I'll just leave the classes that implement comparator to figure out how they want to compare their how they want to compare their object right like I don't need to worry about that for myself I just know that the compare function is going output an integer based on however the class that implements comparator decides that it wants to compare these like two objects of type T how it decides I want to compare like the two dots or the two strings or whatever okay。

So just a cool little thing that you'll see in the worksheet， okay。

As a quick refresher from last week， a class can implement many interfaces and extend only one class Inters tell us what we want to do but not how and classes tell us how we want to do it and like I previously mentioned remember that interfaces can have empty method bodies that must be filled in by subclasses or default methods that need to be overriden by subclasses but like let's say you're like implementing like comparable sorry comparator or something you'll notice back here that the compare method is not filled out so if you were to implement comparator you would need to fill out the compare function in yourself。

😊，And then with the extends keyword subclasses inherit their parents nonpriva instance and static variables methods that can be overwrittend and nested classes so something really important here that's going to be relevant in the worksheet actually it's this idea that subclasses will inherit variables and methods but as long as they're not private so if I have like going much like the animal dog and cat example let's say animal has a private variable called name that means in dog or cat I can directly access name I can't be like this do name because job will be like what are you talking about like I don't have a variable called name even though a dog and a cat is an animal and should have a name it's kind of like a weird its it's like a weird access kind of thing I don't know if Josh talked about it super in but like this kind of all you really need to know that like private is like specific to a class only。

One more thing is that subclasses do not inherit their parents constructors。

 so if we wanted to refer to the parent class in any kind of context whether to refer to the parent superconor or to refer to the parent methods we would use super so if we were to refer to the parent constructor within like a child class within the。

Within the constructor of the child class， we make a call like super and then in parentheses pass and whatever arguments go into the super constructor。

 the parent class constructor。And let's say we're in the body of the child class and let's say we want to call the parents this parents method or something like that so let's say we're inside of dog and we want to call animalsim bark instance method。

 we could say something like super dot bark inside of dog and that would call animals bark method for us。

 right？So going off of that， let's now talk a little bit about two interfaces that will be really important for us on this worksheet。

 which are iterator and iterable。So iterators are objects that can be iterated through in Java in some sort of loop and an iterator is an interface and here you'll see that iterator is parameterized by T once again。

 like the polymorphic general type generic type， and any class that implements the iterator interface will have to fill out Boolean has next and T next so has next is a function that just returns true。

 if and only if the iterator has another element left to iterate through。Likewise。

 that's going to play in very closely to the implementation of next。

 and next just returns the next object in the iterator of type T。

 which is what we establish when we create our variable。Oh yeah， create our iterator class， sorry。

Iterables on the other hand are objects that can produce an iterator so here we have iterable once again it's parameterized by T and the only function you really need to implement if you're implementing iterable is this iterator function which returns an iterator over objects of type T okay so what does that all mean because I know it's like kind of abstract I think this sums it up nicely so you might have seen syntax like four string X colon and list of strings and we kind of just hand wavedd in the beginning of the semester where we were like oh this is an enhanced for loop like you don't need to be like four inch I equals zero etc this just like goes through all of these strings in list of strings and this works because lists sets and arrays are all iterable。

And what I mean by that is that this syntax is shorthand for this down here so effectively what we're doing when we see this colon is it's basically calling the iterator method of an iterable list of strings variable right and it sets it equal to an iterator over like say like a string here right and then the continuing condition is while iter dot has next right while the iterator has something left to iterate over we set string x equal to iter dot next the next element that the iterator is going to output for us。

😊，Okay， so I think this kind of ties in what we understand about like iterator and iterables。

And then you know， as a very quick conceptual check， let's run through these。

 you can pause the video here if you'd like， but you don't have to， because I will just keep talking。

 but for question one， if we were just define a class that implements the interface iterable of dogs。

 what method would this class need to define？😊，So if we come back here we know that iterable of dog is an interface and we know that it would need to implement or fill out this function iterator or it's called iterator and it returns an iterator of type T and we've established that the class is going to implement iterable of dog so if we pattern match the T to over here we know that we're going need to have a function called public iterator of dog iterator and remember that I just tack in the public on there because interface methods are inherently public so the method signature is going to look like this all right。

😊，Then for part two， if we were to define a class that implements the interface iterator over an integer。

 what methods would this class need to define so hopping back over here we see that iterator of type T is this interface。

😊，And that means we're going to have to in a class that implements iterator over integers。

 we're going to have to implement public Boolean has next and once again pattern matching the T to be integer will also need public integer next。

😊，So it's going to look like that。And then finally， as a final check for understanding。

 what is the difference between iterator and iterable？

So iterators are the actual object we can iterate over and you can think of it like a Python generator over a list。

If you're not totally familiar with like Python or you didn't take CA that's totally okay。

 but you can kind of think of like the list as the iterable object and I like to think of the iterator as this like giant arrow that moves along this object and spits elements out of the object like one at a time。

 okay？So on the other hand， iterables are objects that can produce an iterator that somehow iterate over its contents。

 usually some kind of collection so for example， like I was talking about previously like arrays。

 sets and lists are all iterables that produce an iterator right so as an example an array is iterable and an iterator over the array could go through the element every index of the array for example okay。

😊，Awesome。Now， one final slide that Josh talked about， I believe in this Monday's lecture。

 which is the idea of the double equals versus dot equals， so they're both useful in different ways。

So equal equal compares the literal bits at the location of the variable。

 and it's typically only used for primitive types， but not always So going back to the analogy where let's say we represent every variable as a box and the box contains some kind of value for primitive types。

 the value goes directly in this box right， let's say we have int x equals5。

 that means5 goes directly inside of the variable x's box。 However， if we had like dog X。😊。

Equals some new dog off in memory what we'd have inside this box is not the dog itself but a pointer right on memory address to the location of the dog in memory so that's kind of what we mean here。

So if we are comparing two reference types， it's going to compare the memory addresses of those two reference types which can be useful if you're trying to determine if two variables point to the same object in memory。

 and I think you might have seen this kind of usage when you're doing project like1 a when you're trying to figure out it like a node is like the Sentinel so you'd be like if current node equal Sentinel as an example right equal equal Sentinel。

The one exception though， to the equal equal reference type conundrum is null and just remember that N null is a special pointer that you're generally almost always going to compare with equal equal。

😊，We do have an alternative for equal equal though because what if we want two objects that say have like two lists。

 for example， that have the same contents to be considered equal。

 even though they're like two different lists and memory so let's say you have a list A containing  one23 and a list B containing 123。

 but they're two different list and memory how do we get them to or how do we get Java to consider them equal that's where the dot equals method comes in and you'll see this in the syntax of like object dot equals。

Oh goodness， excuse me， you'll see this in the context of like some object dot equals some other object。

So the equals method is an object is is an object like the literal Java object method with that all other objects and Java inherent from so that means that equals can be overridden on a class by class basisis but it's going to default to objects dot equals method which just compares memory addresses like the double equals so basically if you don't override equals dot equals I mean it's just going to default to comparing memory locations okay。

As an example to illustrate the difference between equal equal and dot equals。

 say we make the dog classes dot equals method return true if and only if both dogs being compared have the same name。

 so as an example， if we had this variable dog phyto equals new dog where the name is phyto and we have another variable dog other phydo equals new dog where this dog's name is also phto。

😊，If we evaluated phyto equal equal other phyto， this is going to return false because phyto and other phyto point to two different dogs in memory。

 they just happen to have the same name， but they're two different dogs in memory On the other hand。

 if we do phyto do equals other phyto that's going return true because we defined the dogs equals method to return true if both dogs have the same name and both dogs have the name phyto here so we treat them as like equivalent objects all right。

 and there's a really fantastic。Ja visualizer Java visualizer walk through that another TA Alexander wrote up while he was queuing this discussion。

 I'm not going to run through it here necessarily for the sake of time。

 but you can like definitely feel free to hop through the sidess and check it out yourself。

 all right？😊，And I believe that is it for content review。



![](img/eee5baf3bc5adf7412c9a1620d8d59eb_3.png)