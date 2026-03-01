# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p136 16_03_05_原地算法.zh_en -BV18U411U729_p136-

![](img/157854231dd0fbb068f27b1f47d667a1_0.png)

You have just written a sort which destroys the input and produces its output in a new array list。

 However， programmers often want to sort in place， modifying the input array list to be sorted without making any other new array list to hold the output。

 You can sort in place with a similar principle to what you just did。

 except you swap the elements inside the array。 Let's see more。First。

 we are going to look through each element from lowest to highest index and find the element that belongs there。

 We'll use this arrow to indicate that position。The element that goes in this position is the smallest element in the entire input array list。

 so we swap them and go to the next position。The element that belongs here is the smallest element in the rest of the input shown with a dotted box here。

 In this case， it is 17， which is already in the right place。 we can just leave it where it is。

 although if we swap it with itself， it will not hurt anything and remove a case from the code。

The rest of this process proceeds similarly。Until finally， the input has been sorted in place。Hi。

 we are now going to sort the earthquakes by their magnitude。So I have started our method here。

 which is called sort by magnitude， but we're going to write a helper function first because what we need to do is we need to find the index location of the smallest magnitude of a part of the array list。

So I've actually already written that code here， let me just go over it real quick。

We have the method get smallest magnitude and we are passing in the array list of type quake entry。

 and then we're also passing in a second parameter from so this is the index position we want to start at and we want to find the smallest magnitude from that point over in the array list。

So we're going to assume the smallest one is the first one to start with because that's all we've seen。

 and we're calling that mint index， and then we're going to loop over the rest of the quake entries in this for loop here。

And then what we'll do is， we'll compare。The current one we're looking at。

 which is the I position with the current min index position that we found and whenever we find one smaller。

 we're going to reset the min index equal to that I location。

And then once we've looked at everything from here over。

 we would have found the index position that has the smallest magnitude。

So we're going to return that where you see return index。

So get smallest magnitude will return the index location of the smallest magnitude。From over， okay。

So now we want to do the sort。 We want to sort them by their magnitude。

 and we're going to use this helper function。So the first thing we're going to do is we have an array list of quake entries and that variable is called in。

 and so we're going to iterate over that list。So we'll create a for loop here。

We're going to look at everything。 So from 0 to in dot size。And we'll increment by one each time。

And then we're going to find them in index by just calling our helper function。

 So the first time it'll look through the whole array list and tell us the index of the smallest。

So we'll say ant min index。Let's just call our method。I won't pass。In， and we'll pass。I。

 so I the first time is zero。The first time I is going to be 0， and it will find the smallest。

 the the index position of the smallest throughout the whole array list。Now。

 once we know where the smallest is， we need to put the smallest where it belongs。

 So the first time the smallest belongs in slot 0。 So we find the location where the smallest is。

 We're going to call that min index。 And then we're going to swap it with the thing in slot0。

 So we need to write the code for that。 So we're going to。Create a quake entry。Called Q I。

And this one will store。Temporarily。The quake entry in the I slot。And again。

 the first time we do this， I is 0， so it's grabbing the one there because we're going to have to swap it with what we're going to create a quake entry。

For the one where the smallest magnitude is， we'll call that one Q min。

And that one is at location Min index， where we just found out。

And now that we've temporarily stored them， we can now set the one at location。I。To cu in。

And then we'll set the one at location min index to I。

 So we're just swapping the two in the I position and the min index position。Let's see， okay。

All right， and then we'll compile this。Okay so that's good so far。 Now we have to test this out。

 Let me just go over what we just did again。 So we have a loop that's going to go all the way through。

 The first time I is 0。 it finds a min index by calling our helper method in slot 0。

 and then we swap slot0 with min index the second time through the loop I is 1。

 So now we're looking from one over because we know the smallest is in slot0。

 And then at that point we're going to find the smallest from one over。 we'll set it to min index。

 we'll swap that with position1 and so on as we go。 Now we need to test this。

 So I now have a tester method。Down here that I've started。

 and we're going to have the normal thing where we're going to get our earthquake data here。

 we're just getting it from a file。And we're going to right now。

 all we do is just print out all the quake entries。

 but we want to sort them first before we print them out。

 So we're going to call the method we just wrote， which is called sort by magnitude。Here。

 so we'll just type this in here。😔，Sort by magnitude。And we're gonna pass it the quake entry。

 which is in this case， called list。And then we'll print them out。 So here they should be。

 our qua earthquake should be sorted by magnitude when we test this。 So let me compile it。It's good。

 now we want to go over to Blue J。And we want to create a new quake sort。And we're going to call our。

Test sort method。 and let's see what happens。All right， so we get lots of data。

And you can see it stopped， but you can see they're sorted by the magnitude because the largest one is 7。

 then 6。5，5。95。8 and so on。 So away， it looks like it worked。 All right， happy coding。

