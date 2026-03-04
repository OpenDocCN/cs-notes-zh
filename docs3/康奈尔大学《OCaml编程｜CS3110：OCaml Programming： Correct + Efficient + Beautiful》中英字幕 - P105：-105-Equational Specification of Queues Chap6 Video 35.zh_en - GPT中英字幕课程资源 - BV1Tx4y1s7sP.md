# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P105：-105-Equational Specification of Queues Chap6 Video 35.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As another example of equational specification， let's look at our old friend， the Q。

So here's the specification for Qes and actually here's the specification for stacks once again。

 notice if I flip back and forth between these really quickly。

 the only thing that's changing is some identifiers here。

 just the names of the module and the operations， all of the types stay the same。😊。

So clearly we need more to specify a queue than just the names and types of the operations to do an equational specification for this。

We'll start off the same way as we did with stacks。What is is empty of empty， Well。

 of course that's true。What is empty if you apply it to an N cubed element？😡，Well。

 of course that's going to be false because now there's at least one element。As a third equation。

 how do front and in Q go together。This is kind of similar to how did peak and push go together for stacks。

Well it's more complicated to write down this equation for Qs than it was for stacks。

 and that's because it depends on whether the queue was already empty or not。

We're going to come back and look at this in more detail in just a second。

Let me also point out that the same phenomenon though is going to occur with the fourth equation。

 so for stacks that told us how P and push interacted， here it's telling us how DQ and inQ interact。

And it's again， more complicated because it's going to depend on whether the queue is empty or not。

Okay， let's drill down into those third and fourth equations now。

Suppose you were going to go get lunch at Louis's lunch。Well。

 here's what that third equation is telling us about the Q。What if the queue is already empty。

 so there's no one standing in line at the food truck。Then you can just walk right up to it。

 You will be at the front of the queue after being ined。 That is。😡。

And then you can get whatever you want， maybe some tasty cajun fries， for example。On the other hand。

 suppose you arrive at the food truck and there's a bunch of people in the queue in front of you。

 all socially distanced appropriately， of course。Well， in that case。

 what's going to happen after an NQ？You're going to be at the back of the line there。

 You've got to wait for all the other people to get their food。

So the front of the queue doesn't change， it's still the same person after that in queue operation。

So that's how the third equation works。What about the fourth equation？

Wellll suppose once more that you arrive at the food truck and the queue is empty。

 There's no one else there。

![](img/adef8b14e3696996f5165513270ffa05_1.png)

Then after being ined。So you getting in queued on the queue first。Then， being deed。



![](img/adef8b14e3696996f5165513270ffa05_3.png)

The queue is going to be empty。So that's what the first half of this equation is telling us。Okay。

 but what if there's people in the queue already， so it's not empty？😡。



![](img/adef8b14e3696996f5165513270ffa05_5.png)

Okay， then if we in cue you， you're at the back of the line waiting for your food。

And then we deque somebody。Then we get this Q， so that's the result of the left hand side of the equation here。



![](img/adef8b14e3696996f5165513270ffa05_7.png)

Notice that there's two people in front of you and you're at the end。



![](img/adef8b14e3696996f5165513270ffa05_9.png)

Okay， now let's look at the right hand side of the equation。Okay。

 so I'm resetting here we're back to the beginning and there's three people in the queue。

 Now the first thing is we deque somebody so the first person gets their food。

And then you come along and get ined on the end。

![](img/adef8b14e3696996f5165513270ffa05_11.png)

So it's the same cue that results either way， still two people in front of you and you're at the end。

So that's what the fourth equation is saying here， how DQ and NQ interact by being swapped around like that。

That's definitely more complicated than we saw for stacks。

We can once more implement cues very simply as lists。Just using mostly list module functions。

 append and so forth。And all of these equations that I just showed you do hold simply by evaluation for this implementation as well。

 There's nothing very deep about them。But we also have our old friend。

 the two list queue that we've studied a couple times now。

 and here we'll come back to it a third time。😡，So remember that with the two list queue。

 we have two lists that represent the queue。And together， they represent a queue。

 which is the first list followed by the reverse of the second list， so the front and the back list。

And we have a repin variant， which is that if the front list is emptied。

 then the back list has to be。So before I've shown this to you in a couple different implementations with maybe records before and now I'm using two pools。

 there's no essential difference。So the empty queue is just empty， empty。

To figure out whether a queue is empty， well all we have to do is look at the front list because of that repin variant。

 doesn't matter what the back is if the front's empty， the back has to be empty。

So in queue an element onto the queue， while we can check and see if the front is empty， if it is。

 then we have to leave the back empty， but we can put the new elements into the front。Otherwise。

 we can cons that new element onto the back queue because we're guaranteed that the front is not empty so we're not going to accidentally violate the weapon。

To figure out what the front element of the whole Q is， we can just take the head of the front。

And now， unlike before when we were talking about stacks。

 this is a piece of code that could legitimately raise an exception。On the other hand。

 if we go back and look at our equational specification。

 you'll notice that that specification says nothing about what front does when applied to an empty queue。

So we've left that behavior unspecified， and therefore we're not going to have to reason about it when we do proofs based on this specification。

Next， for DQ。This is the most complicated of the operations。

We need to see whether removing one element from the front is going to cause the front to become empty。

 If so， we reverse the back and install it as the front。Otherwise。

 we just get to remove that  element。Again， our equational specification says nothing about what DQ does to an empty Q。

 We've left that unspecified， and that's why I'm given away with raising exceptions here when I try to take the tale of a potentially empty front。

Now， the proofs for these are not straightforward。 They actually require a considerable amount of work。

 and I've put them all in the textbook for you to read。

The interesting thing I want to talk about now with those is the abstraction function and the representation in。

The rep invariant， you should recall， is a precondition for every operation of a data abstraction。

Which is to say we get to assume that it holds。For any queue that's passed in to say in queue。

So in this implementation of NQ， if F is empty， then B must also be。

And that's essential to being able to prove that this implementation of INQ is correct。

Because if the back weren't empty in the then branch， well then we'd be losing elements from the Q。

 there'd be some elements in B， we're throwing those away when we return an empty backlist in the then branch。

😡。

![](img/adef8b14e3696996f5165513270ffa05_13.png)

![](img/adef8b14e3696996f5165513270ffa05_14.png)

So it's essential that that reendant holds。The other place that's really interesting in those proofs is the abstraction function。

We eventually reach a place in those proofs where we need to show that two cues are equal。

 but actually they aren't the same two lists。So we end up needing to show that the reverse of F。

 the front list。

![](img/adef8b14e3696996f5165513270ffa05_16.png)

Followed by a back list that's just the singleingleton element X。Is equal to the reverse of x conf。

 followed by an empty back。

![](img/adef8b14e3696996f5165513270ffa05_18.png)

Now， of course， as Ochemel pairs and as lists， those are not the same expressions。

 they do not evaluate to the same code。But， they represent。The same cu。

Both of them represent elements in the same order， which is to say the Q that has all the elements of F and reverse order followed by X at the end。

That's what both the left and the right hand side there。

So we end up introducing a new notion of equality。 Well， not a new one。

 augmenting our existing notion of equality to say that。



![](img/adef8b14e3696996f5165513270ffa05_20.png)

If the abstraction function。Applied to two expressions。Is equal。

Thenhan the two expressions we can treat them as equal in our equational proofs。



![](img/adef8b14e3696996f5165513270ffa05_22.png)

But that lets us establish that these two cues really do represent the same thing and thereby prove the correctness of the implementation of two list cues according to oures specification。



![](img/adef8b14e3696996f5165513270ffa05_24.png)