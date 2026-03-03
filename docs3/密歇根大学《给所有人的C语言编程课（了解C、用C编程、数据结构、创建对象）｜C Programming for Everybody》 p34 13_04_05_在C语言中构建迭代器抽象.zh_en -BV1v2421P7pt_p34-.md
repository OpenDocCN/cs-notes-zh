# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p34 13_04_05_在C语言中构建迭代器抽象.zh_en -BV1v2421P7pt_p34-

![](img/37803759d728039e286da3d071c0fe8b_0.png)

So now we come to the last section of this module and that is iterators。

 it's all been building up to iterators。This is a situation where you might say， wow。

 I don't like iterators， iterators seem like a more complex way to write loops than just looking at like head and next and sneaking in and violating the abstraction boundary。

But as you'll see in the overall next module， you're going to have to。

Have very different underlying data structures， and we want to be able to write the same code over and over again。

 So at some level， what we're doing here is we're building a map implementation that can be a linked list。

 a hash map list。

![](img/37803759d728039e286da3d071c0fe8b_2.png)

I mean， a hash based map， a list based map， or a treaty based map。

And what we want is this code right here。 This code should not change。 We should say， hey。

 give me a map， we got a map entry， we got a map iterator。

 Those are all part of the contract that we have with the object be it a linked list， tree or map。

 our hash。We're going to do a put， put， put， put， dump。Yet， get。Now we're going to integrateerate。

The hash won't even have like a doesn't have a head and the next is' not going to work right。

 so we're going to have to say hey。There's this abstraction。Give me an iterator for your map。ok。😊。

And we don't know what's in the iterator， we don't need to know what's in theerator。

 the only thing we need to know is it has a method called next。That's it， so we're basically saying。

 let's get started。Give me an iterator。From the map call the iterator method passing the map instance as a parameter and give me back iterator and then we write a while loop。

 and we say， hey， iterator， give me the next thing it is up to the iterator to start at the beginning and then advance and move out。

And when we get null， we break， if not， we print key and value from the cur。

 Now cur is of T map entry there's a map enter。

![](img/37803759d728039e286da3d071c0fe8b_4.png)

Inter next and then cur is what we get back from iterators so we get from next we get back a map entry and so if you recall key and value are public in the map entry。

 so we could I could have hedge a hide those behind sort of getters and how get key and whatever and name those underscore。

 but we're just going to leave them public attributes for now。

If we really going to be the if we were implementing Java， I mean。

 right now we're kind of hard codinging this string key integer throughout so it's going to be okay and then of course we call the deor on the iterator once we're kind of done with that loop and then we call the deor on the overall map。



![](img/37803759d728039e286da3d071c0fe8b_6.png)

And this code should be roughly the same。When we go from link list。hashes to trees。

This is the moment， and it says iteration pattern。So。

I'm going to do a bunch of pictures and so I just want to。

I've been drawing some pretty complex pictures on these things。

 but by now the whole pattern of what next means and preve。These things being null。

 a doubly linked list， and that key。Pointing to another little you know， a char Star key。

 which points to another little statically allocated thing and a head points to the tail and head and the tail and all that stuff。

I'm just going to for this section， really simplify these pictures to say， look。

There's a variable called head somewhere and it points to a z equals 22 then it points to a w equals 42 and then that's the last one and that points to the next there points to null。

 and so I'm going to really use a succinct representation of linked lists going forward。

If we review what we don't want to do， right， we do not want our call and code to know about count。

 we do not want it to know about head， we don't even want it to know about next within the entries。

Right we don't want to know that we do want to know about key and value。

 and so the calling code where map arrow number underscore head。Current underscore next。 No， no， no。

 no， no， that's not allowed， right， Those are private。 So in our calling code。

 if if we're looking at things have underscores， technically we could do it because there's nothing in sea that's stopping us。

 right， we create those things。

![](img/37803759d728039e286da3d071c0fe8b_8.png)

Right so we don't want to call head or count because then if we change when we're doing a map。

 head's not there anymore， I mean， a hash head's not there next doesn't work。

 I mean we got to hide that。 we got to like wrap it。

 we got to create a strong abstraction around this notion of starting a loop and then itating one iteration of a loop and then ending the loop we have to abstract that away This is the concept of separation of concerns。

 our calling code does not need to be concerned about how the object can be looped through right so we need a generic notion of looping。

So you can think of the iterator object itself。As thing you create and it sort of starts at the beginning and then you hit it。

Next， give me another one give me another one， give me another one and inside the iterator the state is changing it's like advancing and it just gives them to you one at a time。

 you can't ask it for the same one once you's been given to you it's sort of like ratcheted down to the next one so if we look at this Python code we well we start with a dictionary A maps to1 B to 2 C to3 and we print it and there's the dictionary and we say oh let's convert that to a list and that list is the keys which is ABC and then say give me an iterator from that dictionary we print that out and we print the type of it。

 it is of type di underscore key iterator object。

![](img/37803759d728039e286da3d071c0fe8b_10.png)

![](img/37803759d728039e286da3d071c0fe8b_11.png)

And so the iterator itself is not the entire dictionary， it is not a list of all the keys。

It is an internal structure that Python is going to maintain， and then we're going to poke it。



![](img/37803759d728039e286da3d071c0fe8b_13.png)

By calling next， next， next， Now， the whole next thing that's probably calling an internal method like double underscore next double underscore。

 So next is part is is part of the Python language。 So if you look at the while loop。

 it's a wild true loop。

![](img/37803759d728039e286da3d071c0fe8b_15.png)

We say item equals next， so that means give me the next available item in the iterator and then advance it。

 and if we're past the end， return me false。Then I say if item is false， break。

 and otherwise I print the item。And so I'm getting the item is A， B and C。

 like the key thing here in Python， just we're using Python to keep it as simple as possible is we like the iterator is something that's created。



![](img/37803759d728039e286da3d071c0fe8b_17.png)

The iterator doesn't contain all the data。The iterator contains pointers inside of it so that it knows what to do next。

We repeatedly probe the iterator with the next call to get the next thing， and that both advances。

 returns， and indicates when we have run out of things。

It's weird because we're so used to say like four blah in blah。Or for this that？But。

That's that's not how iterators work。 Iterators want this next thing to happen。

 the C code to do the iterator， you create it， you loop next through and the C1 is going to look pretty much the same as the Python one。

 So if we look at the map it structure。

![](img/37803759d728039e286da3d071c0fe8b_19.png)

It is going to have the kind of things that we we needed。 We just are going to pull them in。

 So the concept of current， like we've used the variable current in the past for these loops is in the map inner structure and it's private。

 So we moved that from a sort of a variable that was in the main scope to inside this and made it private。

 The only public things we have are a next method and a Dell method。

 And so now what we have is a simple contract you can see our kind of outside contract for this class is。

It's not it's created by the map class but once it's constructed。

 next and Dell are the only thing that you can do with this， and that's that。

 and then we get to decide inside this class and so when we construct it。

We're basically going to start it。We're going to allocate the right size。

 we're going to take the current and point it at the first item pulling from the head of the linked list。

And then we're going to set the two methods next in Dell based on the address of the implementations of the functions that implement it。

 and then we're done right and so because we're inside of the map and that's map It。

 so this is what you get when you go map arrow It， you get this code。嗯。

And so we're totally allowed to do everything private with map because again。

 the developer of the map class is the same person or team that developing map it and if we wanted to change head to you know X。

 we could because we would just go inside all our code to change it。

 but head is not exposed to the calling code so they wouldn't notice that change again。

 that's the key at the moment the constructor is called before the first call to next。

 this is what the map it looks like current is pointing to the first item in our length list。



![](img/37803759d728039e286da3d071c0fe8b_21.png)

Then the while loop starts and it calls head。 Now you'll notice that it's kind of got this weird thing where it grabs the current。

 And that's because current starts at， we could have implemented this differently。

 but the way I did it was current is pointing at head。And I have to for the return。

 it's got to return at the first call to next， I grab current。

And then I advance current so that at the moment that it returns， the return value is equals 14。

 and current now points at 21 equals 21， preparing for the next call to the next function。Okay。

 so then it comes in and REtV grabs 21 and that's what we return and then we advance to 19 and you can kind of see REtVal and current chase each other down this linked list。

 so we return f equals 19 and then current points to null and then we notice that current is null and then we return null to tell our calling code that we are finished。



![](img/37803759d728039e286da3d071c0fe8b_23.png)

So to start the iteration to prime the iteration， we call the map object and say， hey。

 give me an iterator for the map。And we get that back。

 and we're going to store that inner variableable iterator。

 then we're going to start an infinite loop that says。Wow1 or while true cur equals it or next。

 give me the next one， which the first time two is going to give me the first one。

Then if I got a null， I'm done with a loop， otherwise I print the key and the value of the one I got and then I go up and I iterate to the next one。

 print it up print， up print up print I got a null and then I delete the iterator and this is super equivalent to what we do in Python where we say x equal give me the iterator for the dictionary X in the variable IT then while true。

 we advance to the advanced next of IT otherwise give me false if we got a false we're done and otherwise we printed it so these two are very very parallel and you'll notice that Java and C plus plus don't do iterators the same thing but I wrote this C code to mimicmic Python's way of doing this。



![](img/37803759d728039e286da3d071c0fe8b_25.png)

So it's been quite a long journey。We really focused on abstraction and encapsulation and we've done it with iterators and all we've done now is we laid the groundwork。

For multiple implementations of the map， we shouldn't have to change our main code anymore we should be able to put a。

We build a list map， a list map and then we're going to build a hash map and we're going to build a tree map those have increasing complexity and improved performance characteristics。

Now you really are going to start seeing why we say have abstraction so that we can fool around underneath the abstraction and accomplish really cool things and get closer to。

What Python really does underneath of a dictionary implementation。



![](img/37803759d728039e286da3d071c0fe8b_27.png)

🎼Yeah。

![](img/37803759d728039e286da3d071c0fe8b_29.png)

🎼Yeah。

![](img/37803759d728039e286da3d071c0fe8b_31.png)