# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p30 p29_03_java-enumset -BV1fryaYgEqb_p30-

![](img/b5803d809892444a2adfbc546f0e44d5_0.png)

Hi there。 Today in this session， I will talk about Java Enum set class and its various methods with the help of examples。

 so let's get started。😊。

![](img/b5803d809892444a2adfbc546f0e44d5_2.png)

Basically， the EnM set class of the Java collection framework provides a set of implementation where the elements are of a single enum。

I hope you remember I told you the In map earlier with the same iteration you need to come up here。

 it extends the abstract class and implements this set interface in Java。

 It helps in high performance set implementation， which is much faster than the hashet。

Unlike other set implementation， EM set does not have public constructors。

 so we must use the predefined methods to create the EM set。

All of the elements in the inM set must come from a single animation type that is specified when the set is created either the explicitly or implicit。

It uses a fail safe iterator irverent through the coning modification exception if the collection is modified while iterating。

Eum provides an efficient way to store the Eum values than the other set implementations like haset and threeet。

An enum set only stored the enum values of a specific enum， as I told you。

 we can only insert the element of enum type。It's because we created our empty inner earlier。Hence。

 the JVM already knows all the possible values of the set。

 and this is the reason why enum sets are internally implemented as a sequence of bes。

That's a hierarchy of enum sets Object is the base class from that the abstract class interface and then abstract set being inherited to the enum set。

Where is a type of a generic type， whichever type you pass to store the values of the enM type。

 And these are the common methods， all of clone complement of copy of。



![](img/b5803d809892444a2adfbc546f0e44d5_4.png)

Where the copy of goes for the collection in inum sets， none of as well。

So let me help you out practically implementing the NM sets。



![](img/b5803d809892444a2adfbc546f0e44d5_6.png)

Here， I'm going to create。Eum at the class level。There I have specific sizes， small。Medium。Large。

An extra large。In this public main method。Creating a enum set of type size。

Where I say enam set dot all off。Size dot class。Printing all the sizes right here。Both that。

The nunov method creates an empty inum set。Eum set。Of type size， Inum size。Equals to enum set dot。

 none of。Size taught class。But it should， it is none of It will not take the inum elements and into the。

Putting into the size。You can now use the range of method。Also。Similarly， just right。Eum said。Size。

Sizes 3 equals 2。Enum set。Dot。Range of。From size， to medium。Through size， do extra large。

Let's print our sizes to this time。And see the specific elements from the。Eum gets itated。

We can also use off method to create an inum set containing the specific elements。Inum set。

Of type size。Sizes 3 equals to enum。Set dot off。Size starts small。Size start large。

Now let's print this sizes3。So it's just taking small and large。Apart from that。

 we have moreover methods to be added。 You can use add method。

To add the implemented elements or add all to combine two or more enums as well。You can use ittator。

 That's a property where you can itrate your all sizes。Ittraator of type size。 Ittraator equals 2。

Anyone you can take I'm digging sizes tot itdrtor。Checking while I trade。The dot has next。

Come inside the loop。 and print。Itrate。Dot， next。I treat a dot next。Just like this。

 we do have remove methods。 We can just check， says out。Sizes dot remove method。

 where I would like to remove。Size or medium。Only and after that。

 you can even though remove all the element that says sizes not remove。系。

So that's how your removal also works。 You can remove the specific elements， the beauty of。

Enum operations are it will remove true or false， whether the operation gets successfully completed or not。

I hope the inim operations are pretty clear to all of you rest whatever methods you know。

 add contains compare all you can access with the help of this operation or object from the collection interface as well。

Until next time， see you in the next session。 Stay tuned。



![](img/b5803d809892444a2adfbc546f0e44d5_8.png)