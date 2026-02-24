# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P16：3 - -61B SP24- Regular Discussion 3 Problem 2 Walkthrough.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Hello， in this video， I'm going to walk over spring 24 regular discussion 3， Quetion 2。

So this is an updated version from the previous semester。

 so make sure you use this semester's version when looking at the worksheet。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_1.png)

Now。This is the type of what would Java do question。 And let's try to break it down line by line。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_3.png)

In lines 3 to 6， we are having these places where in new objects， ABC D。

 So let's take a look at the static and dynamic types。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_5.png)

So we have ABC D。Then， the static type。And there are dynamic types。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_7.png)

We as follows。So recall that what we written on the left hand sign when we declare the variable。

 it is known as the static type。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_9.png)

So。I' probably write animal cat dog for AD for short。 So I'm going do。AACD。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_11.png)

And then， for dynamic type。It's going to be。Di。😔。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_13.png)

AD。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_15.png)

Now we want to take a look at line 8。 So line 8， we're trying to have this cat E equals the new animal。

So what is on the left hand side is a cat。 What's on the right hand side is an animal。

Remember that for these assignments， the rule is that the right hand side must be a left hand side so we can ask ourselves。

 is animal。A cat。Well， not necessarily because animal is more general than a cat。

 So this would result in a compiler error。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_17.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_18.png)

Now， for compile time， this would have been like cat or animal。

 but that just doesn't really apply here。 Maybe the static would be cat。

 but we wouldn't really be able to instantuiate this object。 So the runtime wouldn't really matter。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_20.png)

Now， let's look at。A dog Gr C。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_22.png)

So the first thing is's going to do during compile time is to verify。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_24.png)

During verify， we only know about the static types。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_26.png)

So we're going to take a look at this static type of just animal。

 and we're going to look this method up。So do we have greet and does it actually take in a C。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_28.png)

Well， it turns out that we have great animal A and C static type is a cat。Well。

 a cat is not an animal。But the cat is like the cat class is different from the animal class。

 but the cat is always an animal。This means that this is actually an acceptable method。

 so we're going to write that down。It's gonna be。Anal。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_30.png)

Dot。Get。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_32.png)

Now I notice that during runtime， we're using the dynamic type of that instead。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_34.png)

So if we take a look at the dynamic type。We notice that the greet method is actually overwritten。

That means we can just run that method instead， so we'll run。Dog。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_36.png)

Dog great。And it's going to be。dog。😔。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_38.png)

Name is gonna be。Putau。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_40.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_41.png)

Dog Pluto says。Wof。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_43.png)

Now， we're also going to take a look at line 10。So line 10 has a dots sleep。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_45.png)

So we're just going to check whether an animal has sleep。So it does have sleep。Now， during runtime。

We're going to notice that sleep is a static method instead。

 that means all these D M S rules do not apply。 We're just going to run whatever the static type tells us that it is。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_47.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_48.png)

So， it's just gonna be。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_50.png)

Animal。Doalt sleep。And also。Animal dot sleep。 And then it's just gonna be nap time。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_52.png)

Now to line 11。 so line 11 is see do play。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_54.png)

C is a cat in static type。 So we take a look at cat and say and take a look whether it actually has a play method。

And it does。Now， notice that C is dynamically also a cat。 So there's technically no。

Flexible D M S here。 So we're just gonna run the play method instead。 So it's gonna be C dot play。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_56.png)

C大 play。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_58.png)

And it's gonna be the， that woo， something， something， something。 and then。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_60.png)

Miao。Now on to line 12， so line 12 has C do Greek D。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_62.png)

C， iss also cat。And it calls method greet。And that a D is a dog。

So if we take a look at this greet here。In the cat class， that also takes in an animal。

 but a dog is an animal。 that this is also acceptable。Now。During runtime， because。

The static type is the same as the dynamic type。 The method that we select here is actually the one that's going to be run。

 So we can just say， you know， this method will be run。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_64.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_65.png)

So， let's。Put sea out great。C， dot。Great。And then it's gonna be cat。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_67.png)

Carfield。Says。😔。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_69.png)

Well， it's a cat， so。没有。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_71.png)

Okay， on line 13。 so line 13 has a cast。 that means we're treating this part as having static type animal。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_73.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_74.png)

And when we call this Greek D， we're going to instead checking the animals class。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_76.png)

So greed De well Di is still a dog。 And in the animal class， we still have great animal。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_78.png)

This means that this is still the valid method， and we're going to write that down during compile time。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_80.png)

It's gonna be。A dot。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_82.png)

Great。Now， during runtime。The cast doesn't actually change the dynamic type of the variable。

 So C is still a cat。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_84.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_85.png)

Now， if we take a look at cat the cat down there。It's actually overriding the animals greet method。

 So we'll run that instead。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_87.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_88.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_89.png)

So it's actually same。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_91.png)

And lastly。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_93.png)

Now let's take a look at line 14。Line 14 has D dot sleep。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_95.png)

Here D is a dog。 So we're going to take a look at。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_97.png)

The dog class and check whether there is a sleep。Well， there is a sleep。

 and it's also a static method。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_99.png)

That means we can just use what the compiler knows， use the static type and run that instead。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_101.png)

So， this is gonna be。Do not sleep。Do you nott sleep？



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_103.png)

And then， I。Love napping。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_105.png)

Now on to line 15。 so on line 15， we have a equals to C。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_107.png)

So here's an assignment， and we need to check for the static types。So， recall that A。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_109.png)

The static type is an animal。And for C， the static covers。C。So right hand side is cat。

 Left inside side is animal。 right hand side cat is always an animal， so this line is fine。Now， also。

 from this point on， because a is now pointing to whatever C is pointing to。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_111.png)

A's dynamic type is no longer dog。So after line 15。

A's dynamic type actually becomes whatever C's dynamic type is。It's going to be change to a seat。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_113.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_114.png)

Now we take a look at line 16。Sorry， I need to first write down 15。 So 15。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_116.png)

I guess it's like， there's just nothing here。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_118.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_119.png)

Yeah， and for a。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_121.png)

That'll be。So I guess we can just write down A's compile time and dynamic type。

 because this is really a little bit different from the above so we can just do it like that。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_123.png)

Now line 16 has a do play 14。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_125.png)

So， as static type。Is。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_127.png)

Still animal because it doesn't change。 it's defined as A'， so it would never change。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_129.png)

We're calling play 14。 so now we're go inside an animal and see there is actually a playing method。

That takes into the 14th。Well， it turns out the plate doesn't actually take any argument。

 So Java would not be able to find such a method。 So that'll give us a compile time error。

So I would put not applicable here as well。Because you couldn't even find like a ma matching method。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_131.png)

Now let's take a look at line 17。So in 17， we have a cast。 Ca be into a dog。 sorry， Ca be into a cat。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_133.png)

So， during compile time。We' go inside Cat class and see there is a play method。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_135.png)

So as it turns out， cat does have a play method， so during compile time， that's fine。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_137.png)

And during runtime。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_139.png)

Notice that B's dynamic type is an animal。So now we're trying to cast a more general thing。

 An animal to a more specific thing to a cat。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_141.png)

This is not allowed during run time and will give a class cast exception because we are forcing something very general to be something very specific。

 which is not allowed。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_143.png)

So it wouldn't really run anything and it just R。No to line 18。So for line 18。

We have D equals to dog A where A is cast at their dog。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_145.png)

So again， first of all， we want to check static type。Stic type of tea is a dog。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_147.png)

Now。A is being cast to a dog。So that is also okay here。One tricky thing about casting， though。

 is that you cannot cast between。Siblings。As it turns out， though， because during compile time。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_149.png)

We know that a static type is still animal， and we're casting animal to a dog。

Whereas might give you runtime error if these are the dynamic types during static type。

 during static type checking， you' are allowed to cast between any parent and children。

 no matter like the order。Things might actually get wrong when we enter runtime。

 So let's keep an eye on that。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_151.png)

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_152.png)

Now， notice that something really weird is happening。 So age's dynamic type is a cat。

 but we're forcing it to be a dog。 You cannot cast between siblings。

 so this would also be in runtime error。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_154.png)

So if I were to write down on what D's compile time is， well， D static are still going to be D。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_156.png)

But。It's not going to even run。Because it's just gonna be not applicable because we're trying to cast from a cat to dog。

That will be another class cast exception。Now， let's take a look at line 19， which is c equals to a。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_158.png)

C， U static type is C。Or cat。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_160.png)

And then。A static type is an animal。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_162.png)

So。During compile time。We have something like this。

The Kmala wouldn't allow to do this because the right hand side static type is more general than the left hand side。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_164.png)

So you don't want to really。Do something like this。 compileer is going to say， hey。

 I know that an animal。Might not necessarily be a cat。

 So I'm not going to allow it unless you tell me to cast it。

So this is actually going to be a compiler error。Now， as it turns out， I bring this to our next part。

On which is there is there in the last line line 19， so。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_166.png)

Whereas cat is actually。A subclass of dog。 We can just do some sort of casting。

 and we do C equals to animal。 Sorry， not animal。 C equals to。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_168.png)

cat。Okay。So this is going to work during compile time because it's going to see that this is a cat。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_170.png)

It is also a cat。And during runtime。

![](img/2cf9ded88a5a9b2c5637088e4553bfb4_172.png)

Ages dynamic type is a cat because it it has been reassigned to a cat。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_174.png)

So， we're casting。During the casting， well， the cat just say， okay， you're actually a cat。

 And you said you were casting to the cat。 So he didn't lie。 And you're just going to pass that。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_176.png)

Now， C is gonna be assigned。To whatever a is assigned to。



![](img/2cf9ded88a5a9b2c5637088e4553bfb4_178.png)

And it works。