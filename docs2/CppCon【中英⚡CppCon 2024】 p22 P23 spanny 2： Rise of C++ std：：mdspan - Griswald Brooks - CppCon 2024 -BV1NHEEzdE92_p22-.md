# CppCon【中英⚡CppCon 2024】 p22 P23 spanny 2： Rise of C++ std：：mdspan - Griswald Brooks - CppCon 2024 -BV1NHEEzdE92_p22-

🎼All the presenters， everyone that attends this conference is so friendly， so willing to teach。

 so willing to learn from you too， so it's not just watching these videos。

 it's kind of getting that insight afterwards and around at dinner at drinks。

 like all the other aspects of the conference besides just like that technical information。😊。



![](img/8330ab25c35dfcc71a811dc3a5a984b7_1.png)

Hello everybody。 Thank you for coming to my talk。 My name is Griswald Brooks。

 I'm a senior robotics engineer at P robototics， and I'm also the robotics track chair here at CPPCon。

 and I'm here to tell you a thing or two about MD spam。😊，So。Got to get this。Right out of the way。

 this is very much like I see in many of the talks。

While M span was accepted in C++ 23 at the time that I was working on this project。

 I did not see that Gcc actually supported all the features of M span。

 So while I used stood for you know， the entirety of this talk。

 I was using the cocos library to implement all of this。 So the reference implementation of M span。

 So the thing that should be more or less exactly what's in the standard is what I was using。

 but it was not technically the standard。 And then at the bottom there is Github link is gonna be able to code。

 If you want to go see it。All right， so've got three main goals for everybody here today。

 right I'm going to try to give you all a little bit deeper understanding of MD span layouts and accessoriesors。

By the end of this talk， you should all know， or at least have a starting understanding of being able to implement your own layouts and accessoriesors in M span。

 and I'm going to dispel a number of common myths and misconceptions about the restrictions of MV span。

I'm going to try to do this in three parts。 So I'll briefly go over， you know。

 a little bit of history， a little bit of motivation。 why we have them Depan。

 Then we'll talk about the layout policy， we'll use that in the context of mobile base navigation。

 robots driving around warehouses sort of thing。 We'll talk about the defaults how to do your own layout policy is the same called submas。

 lasers。 Oh my then the last part of it。 we'll do accessoriesors， right。

 talk about what accessors are for， what the default accessor does and we'll use an accessor to get my robots to tell me if I have any beer so。

Let's go。MD span。Now， I am not a historian， but Nevin Liber is。

 So if you want to actually know like the history of Mpan， how it got started。

 how it got integrated in the standard， Nevin has a great talk from 2022 about that。And of course。

 I have to mention the two talks that really like got me going on this project。

 one of them from Timor in 2022， he was actually the talk that really like showed me like， wow。

 MD Sp can do all these really cool things that Amber would have thought of。 and of course Bryce。

 one of the authors of MD Sp and CBB North。 He gave a really good presentation about a lot of intacies。

 MD Sp stuff that I won't get to cover here。 So a lot of it you should go for him because obviously he's the expert。

And I have to give a shout out to Daisy Holman and。Damien Lebrun Gre for helping me with this talk。

 So Daisy actually contributed a little bit of code to this talk。 And Damien reviewed it for me。

 make sure I didn't mess up some of the policies。So first question。

 don't we kind of already have multidimensional arrays in C plus plus， I mean。

 I can think of at least two different ways to do it， right， I can use a C style， you know。

 two dimensional array， I can use a vector of vectors， an array of arrays， right。

 that sort of thing should work， right。Well， yes， but I can think of at least two off the top of my head。

 reasonsons why that's maybe not the best thing to do， right， So if you have a seast array of arrays。

 yes， all of the memory is contiguous。 But， of course。

 those are static dimensions because there're only a compile type， so。If you were going to try， like。

 I don't know， load an image from a file， you wouldn't be able to use this technique。Now the one。

 of course， would be doing a vector of vectors right So now you can do dynamic allocation， of course。

 but now the rows are actually no longer contiguous in memory right now， they're nonlocal。

 so you're gonna to have a little bit of performance hit there。 And of course， because it's a vector。

 there isn't actually anything guarantee that each row is the same length。

 one could be a little bit longer。 one could shorter and there's no like mechanism out of the box to be able to help you with that。

I seem to remember， though， that computers actually don't have like twodial RAM or like threedisional RAM or four dimensionmensional RAM。

 My understanding is that they kind of like store bits like in in like a linear progression and we just kind of like we're not we're talking about a multidimensional data structure or like our programs in general。

 just kind of like map to those locations。 we perceive how that door to data is laid out。

 So we could do that。 And in fact， I bet you half of the engineers here who are roboticists have written this class。

 probably more than once or knew a coworker who wrote this class because this ends up being the standard thing to do if you know Ros2 nav2 the occupancy grids。

 is is how it is implemented So you might take stood array and take the dimensions of N by M。

And allocate that entire and an array。 and then through the call operator。

 map the indices right to the right storage location。Obviously。

 you could do the same thing with vectors that each should have。A dynamic allocation。

For the size and shape of your matrix。So that's great。 We're done。 We don't even to do anything。

Though anyone who's actually worked with， you know， multidimensional data。

 they like to have a few more tools， right， They like to have reshaped。

 So let's say I've got like this 2 by3 matrix。 What if I'd like to look at it as a 3 by2 matrix。

 What if I'd like to look at it as a  one by 6 matrix， right。

What if I'd like to actually take my 1 by 6 matrix and just turn into a pure6 element thing。

 reduceuce the dimensionality。 And， of course， what if I wanted to look at every other element right。

 of of my matrix instead of， you know， taking all of them at once。

 There's a lot of code that we'd end up having to write。So。Clearly。

 the C plus plus needs a more flexible multidimensional view type， which is where MD span comes in。

 So M span is that multidimensional view type that does not have restrictions on memory。

Like the previous example of our hand rolled code， it is a logical， not physical layout of the data。

 which is what I showed in the beginning with the Invim or vector vectors， right。

 So this means that reshaping doesn't take any allocation。

 If you want to like instantiate or copy em， M spans， are're typically very cheap。

 and they have a couple of custom。Customization points via strategy。

So here's where those customization points come in。 This is the template declaration for MD span。

 first off。The T， right， That's the element that your data kind of has， right。

 So you might have a M D span of ins of doubles of position X。

 Y coordinates of sample joint states or particles， something like that。 Probably not particles。

 So you don't need it to be 2D。And then we have this parameter that M D span calls extend with a T。

 not extends， which is the shape。Right of our data， it might be， you know， the number of rows。

 the number of columns would be the way to think about it。

 so it describes the shape or for how far the span extends in each dimension， right。

The extent has a couple different parameters to it， right。

 First of them is the number of dimensions that there are。 This is called the rank。

The length of each one of those dimensions， and then the type used to represent that dimension。

So a couple of examples， right， first one might be， I'm going to describe some data that is2 by3。

 right， And I'm going to use a size t to represent those dimensions。

 So that means there are two elements in one dimension and then three elements in the next dimension。

Next one， I might have something that's 100 by 200 by 800， right。

 and I might want to use an integer to represent that because I'm going to do some sort of math with it。

 right， Those are 100 elements，200 elements and 800 elements。

But those first two IMD span are called staticus extents because we both defined the rank。

 So the number of dimensions and the length of those dimensions at the same time。The last one， right。

 is called dynamic extents， which means that we can specify the rank。

 but not the length of those dimensions。 right here I'm using a double for three。

 I haven't tried this yet， but I'm almost certain that this means I could get an M D span to represent continuous three dimensional space。

First customization point that we have here。 The layout policy。

 So the layout policy is the thing that maps your multidimensional index。To a storage location。

So that's like the whole purpose。 So imagine if you had like this linear piece of data right。

 nine elements here， and we were going to like view。

 perceive this data as let's say row major three by three matrix where we're kind of like putting the data cost top going to on next row3。

3 right row major rows come first column major， another thing you know math people like to represent their data with right you see the data goes down the column first。

 we're going to the next one and the next。

![](img/8330ab25c35dfcc71a811dc3a5a984b7_3.png)