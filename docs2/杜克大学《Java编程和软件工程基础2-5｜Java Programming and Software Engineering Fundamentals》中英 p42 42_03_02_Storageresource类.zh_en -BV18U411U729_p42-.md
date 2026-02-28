# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p42 42_03_02_Storageresource类.zh_en -BV18U411U729_p42-

![](img/8ab4e0bb018dcd2e1350be392b657429_0.png)

Okay， now you've learned that you want to store your data in a list so you can separate concerns。

 you learn you'll start out with ouredduu。duke。torage resource class。

 which is a simplified way of doing this。What exactly is a storage resource and how do you use it？

It's a class that holds a collection of strings。 you can call dot add to put a string into the storage resource。

 you can also use dot data to get an iterable so you can iterate over all the strings that have been put into the storage resource you created。



![](img/8ab4e0bb018dcd2e1350be392b657429_2.png)

There are a few more methods and you can read about them in the Duke learnartoprogram。

com website where there's a document page for the storage resource class。

 Let's look at an example of using it。 First we're going to declare a variable SR of type storage resource。

Once we've declared the variable SR of type storage resource and initialized it to a new storage resource。

 we'll see that it's empty， then we might add a string such as hello。

Then we might add another string such as world， and then we could iterate over all the strings in the storage resource by writing a for each loop and using SR。

t data。😡，Let's see what happens when we step through this code， the first line declares a variable。

 so we'll make a box for it labeled SR， and then calling new creates a new storage resource is going to be an empty list of strings which the SR variable will refer to。

We'll add the string hello to the St Re list of strings。Similarly， Sr。adWor will addW。To the list。

 now we're at the for each loop。 We're iterating over Sr dot data。So we'll make a variable。😡。

We're going to use to iterate and have it refer to the first item。😡。

In the storage resource object we created。By referring to this first item in the storage resource object。

 we'll be able to print it。Here it refers to the first item in the storage resource。

 the string hello。Inside the body of the loop， we print out S。 so we print that。

 Then we go back to the beginning of the loop and refer to the next string in the list in this case。

 world。 So we print world as we enter the loop。Once we've reached the end of the loop。

 we go back to the beginning of the loop and see that there are no more strings in the list。



![](img/8ab4e0bb018dcd2e1350be392b657429_4.png)

So we'll go past the loop and we're done iterating over the elements of SR。

If you want to learn more about other methods in storage resource or if you forgot about the details of the ones we discussed here。

 you can find the documentation for this class on Dukeleartoprogram com。 Finally。

 let's see what our algorithm would look like to find all the genes and put them into a storage resource。

 It's pretty much what you had before， as we show here。 except we've made three changes。 First。

 at the beginning of the algorithm， we make an empty storage resource to put。The strings we find。

 the genes in。 after making the empty resource， we do something to each gene we found。

We add it to the storage resource。 Finally， at the end， we give an answer。

 We use the storage resource with all the genes in it， rather than printing them out。

 This method will return a value to whatever called call。

 whatever code called it so the caller can use the storage resource and the data inside it for whatever purpose they want。

 that could be to print it or it could be to process that data further。



![](img/8ab4e0bb018dcd2e1350be392b657429_6.png)

Have fun with storage resource。