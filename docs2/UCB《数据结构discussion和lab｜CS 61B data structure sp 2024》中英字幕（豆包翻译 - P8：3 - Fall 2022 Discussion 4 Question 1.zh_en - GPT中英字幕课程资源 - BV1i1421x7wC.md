# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P8：3 - Fall 2022 Discussion 4 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/b795f4ddd1a6706f7124d92d73749d56_0.png)

Allright， let's get right into question1 rotate。 so we want to write a function that when given an array A and inger k returns a new array whose contents have been shifted k positions to the right wrapping back around to index 0 if necessary for example if a contains the values0 through 7 inclusive and k equals 12 then the array return after calling rotate a comma K is shown below on the right。

 So we have 0，1，2，345，6，7 and becomes 456，7，0，1，2，3 and how that happens。

 let's take an example with the 0 over here。 so we want 0 to be shifted right 12 times in our array and wrap back around to 0 index0 if necessary So0 is going to move 12。

345，6，789101112 positions so it should end up in index 4 and this should happen for all。😊。

Elements of the original a where they shift over right and then we're able to calculate what index they should end up in based on whatever k is wrapping back around as necessary Okay。

 we're told that k can be arbitrarily large or small that is k can be a positive or negative number if k is negative we want to shift an absolute value number of k positions to the left and after calling rotate a should remain unchanged。

And a hint you may find the modular operator useful note that the modular of a negative number is still negative Okay so going back to what we have here。

 we know that k can be a positive or negative number so when it's negative it should shift left and if it's positive it should shift right right so in the example where k was 12 and it was larger than the size of RA。

😊，You'll notice that when we wrapped back， we ended up in position4。 So we started at  zero， right。

 and we ended up in position4。 And so we were told that we really just need like or。Rather。

 we were told that when K is 12。When we want to shift 12 units to the 12 positions to the right that's really the equivalent of shifting this array for positions to the right so how did we determine that well that's where the modo comes in handy right because when we have a positive number modo some n that's going to give us some number between zero inclusive and n exclusive right？

So this is the functionality that really helps us wrap back to the beginning so what that looked like in the context of this was that we did 12。

 which is K modo。😊，The length of the a array， which was just a and that gave us four。

 and this is what told us how many positions we needed to shift right in the context of a number that was between the zero and eight right or0 and  seven inclusive。

So。That's going to tell us that we probably want to have。Some integer right shift。

That breaks down whatever k is to be some nice number between 0 and n right because like shifting right 12 positions doesn't exactly make sense because we have to wrap back around right and so doing the modulus takes like the remainder it basically tells us like the smallest possible number that we can conceptualize the shift as Okay。

 so we're going to say int right shift equals k。Maud。Aultly。Okay。

 now we're almost like ready to move our elements into a new array， but we have to consider， well。

 what if。K was a negative number， right， because we told here that the modo of a negative number is still negative。

 So even if we do K mod a dot length， right shifts might still give us a negative number。 Okay。

 so how do we deal with this。 Let's think about it。Let's pretend like K is negative 1。In which case？

This array over here would become。One，2， three， four，5，6， seven， zero。

And if we think about if we try to conceptualize k equals negative one in terms of a right shift。

 right because we're told that we want to shift k positions to the right。

 if we conceptualize it in terms of a right shift， what does 0，1，2，3，4，5，6，7 all the way to 1，2，3，4。

56，7，0 look like in terms of a right shift？So you'll find that when k is negative  one。

 the equivalent right shift would be as if k was equal to six， right。

 the zero goes six positions to the right and ends up on the end over here。So the idea is。😊。

If we have a negative K， we can find the right shift by adding the a length of the array to the negative K to get the proper right shift that we need。

 So we're going to do here is say。If。Okay， is oh sorry。If rate shift is still。A negative number。呃。

Then。We'll want to add。Aight out length to it to ensure that it's a positive number now。

Right and well this is basically going to get us into a positive number that is the equivalent of shifting the original number left all right so we're going to get a sorry I mean we're going to get a positive number that represents the right shift that is necessary to make the same change needed as if。

K was negative。 The the shift was negative。 I mean， Okay， so now that that's done。

 we have to create a new array。So we're going to say int array new array equals a new。Into j。

 that's the same length as a， right， We're not resizing or anything。 We're just rotating。

 We just want a new array with the same length。 And inside of this， well。

 now that we have this new array and we have our right shift and we have our original a array A。

 we now have to start putting the original elements of a into the correct indices in our new array new R。

 So what that's going to look like is we'll want to go through。Oive。The elements of a。

So I'm going to say I is less than a dot length。I plus equals one。So inside this for loop。

 we have to calculate the actual index， the target index of the new array right and what that's going to look like is it's going to be the original index I right because we're running through the whole length of a so it's going to be I plus the right shift。

This is going to take us the correct number of positions， right？

And then to ensure that we still have a valid index that falls within the bounds of 0 and the length of the index。

 we're going to once again， take the modo。Of I plus right shift and modo against a dot length okay。

 so what this line is doing over here is it's going to take its original index， shift it。

 right shift positions， and then to ensure that we still fall within the about correct index index bounds of the array we'll have to modo it by a dot length。

😊，And now that we've discovered the new index， we can update。New R at that new index。

With whatever was originally in a at index P。Okay， and at the end of all this， oops。

At the end of all this， well want to return。New art。



![](img/b795f4ddd1a6706f7124d92d73749d56_2.png)

Alright。😮。