# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P52：18_模块4 1 3 接口与具体类型.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

Module 4 interfaces for abstraction， topic 1。3 interface versus concrete types。



![](img/32a573e4a7bee048b864bff71e4515af_1.png)

So concrete types and interface types are fundamentally different， fundamentally different。

 a concrete type is a regular type， it specifies the exact representation of the data and the methods。

 data specifically but also the methods that are using the type as a receiver type。

 so they are fully specified， and it has complete implementations method of all the methods。

 so any methods that use this type as a receiver type that are completely specified。

But the first thing is sort of a big difference between interface types and concrete types is that the exact representation of data and the data is in there。

 So if you have a concrete type it's going to have a bunch of data。

 one or more pieces of data that are associated with the type Now an interface type just specifies some method signatures so no data is specified just just the methods and even the methods。

 their implementations are abstracted， you don't have implementations you just have the signatures to the methods so。

😊，That's the difference between the two， but remember that when you give an interface。

 interface eventually gets mapped to a concrete type and we'll see that in a second。

So an interface value， when you create an interface， you havent declared an interface type。

 you make a value of that type， you can treat it like other values， right， ants floats and all this。

 you can make a variable of that type， so I can make a variable of the type of a particular interface like my a shape 2D。

 I can make a variable of that type。😊，Now interface values， the value of an interface like that。

 has two components。First， there's the dynamic type。 second， there's the dynamic value。

 So dynamic type is the concrete type is the concrete type that it is assigned to so。

The the dynamic value， though， is actually actually the the dynamic It's the value of that dynamic type。

 So the dynamic type is just the type which is associated to。 So to be more specific。

 let's say we're talking about shape 2 D。 That's my interface。 right， This interface。

 There are several concrete types which satisfies my interface， like rectangle。

 that satisfies my interface。 triangle satisfies my interface。

Now when I make my actual my interface variable right and I give it a value。

 that value has got to be mapped to a concrete type。

 maybe it's mapped to a rectangle or a triangle or something like that。 and that rectangle triangle。

 whatever it is， it's going to have a value So the rectangle might have some points in it and the triangle might have some points in it。

 So there's a dynamic type which is a type of the concrete concrete type that the interface is assigned the interface value is assigned to and the dynamic value is the value of that dynamic type。

😊，So an interface value is actually a pair， the dynamic type together with the dynamic value。

This probably will become more clear with the next slide when I' give a bit of an example。

 so defining an interface type。 So we got this type speaker interface right。

 it's a speaker interface and all we define in there is this speak method which takes our arguments。

 returns， no value， so very simple interface。So that's our interface type up at the top。Now， then。

I also define my dog type。 Okay， it's a type called dog as a structure。

 and it's got just a string in there。 Okay， the name of the dog， let's say， right。

 name is called name。 So it's just got， that's my whole whole dog type。

 And what I'm going do is I'm going make this dog type。 make it satisfy my speaker interface。

 So I declare a function called speak。 It's receiver type dog。

 and it just prints the name of the dog。 You know D do name。 right， So that's what the dog speaks。

 So， so now dog is a type that satisfies this speaker， the speaker interface。😊，Now in my main。

 first thing I do is I declare a speaker， so at S1 S1 is a variable and it is going to actually have a speaker value。

 so it's a speaker type， it's going to be a speaker value right so it's that S1 is an interface value。

Next I declare a dog， D1， it's going to be my dog type， but it's going to have a name equal to Brian。

Now， then I can say S1 equals D1。 Now that is legal because the dog type satisfies the S1 interface。

 So S1 can be a dog right so there because it satisfies the interface。 So I can say S1s equal to D1。

 So now S1 which is a speaker S1 speaker type。 It is now is' concrete type that is assigned to is D1。

 That is the concrete。 that is the concrete object that it's assigned to。

 which is the concrete type is going to be the dynamic type is going to be the dog type and the value is going to be the dog value。

 which you know it name is Brian。And then I can say S1。peak， and it'll call the Spak of the dog。

 right， which will just print out Brian。So the dynamic type in this case of S1 is dog is the dog type。

 and the dynamic value is D1， which contains that name Brian so this S1 which is a speaker object。

 is oh sorry， it's a speaker object which is an interface， it is a pair， the dynamic type dog。

 that's the type and dynamic value， dynamic value which is D1 in this case。

 which has this dog name name Brian this all it has in it。Okay。

 so an interface like just to repeat has dynamic type and dynamic value。Now。

 interface can have a nil dynamic value， meaning no dynamic value。 It can have a type。

 a dynamic type， but not a dynamic value。 So let me give you an example of that。

we got a variable S1 is a speaker， okay， then I have my dog D1 and I make it appointed to a dog star dog。

Then I say S1 equals D1 Now when I do that， I'm assigning S1 to D1， but D1。

 it's not a concrete object。 its type is dog or star dog， it's pointed to a dog。

 but it doesn't have any data in it so remember dog has this data， this name which is a string。

 but D1 is a pointed to a dog， so it's not an actual dog， it doesn't have the data in it。

 so D1 has no concrete value as at this point。But it has a type。 Okay， It's associated with a dog。

 It's appointed to a dog。 So what that means is S1。S1， when I do that assignment， S1 equals D1。

 S1 has a dynamic type， dog or a dog pointer， but it has no dynamic value because D1 doesn't have a dynamic value yet。

 because D1 is appointed to a dog。 It doesn't actually have dog information in it， namely the name。

 so this is a situation where you've got an interface。 It has a nil dynamic value。

 Neil means nothing。 It's sort of the empty and goal。 So it has a nil dynamic value。

 but it has a dynamic type。And this is legal， you know， to have a dynamic type。

 but no dynamic value is legal。So when you have that situation。

 we have an interface like that with a dynamic type， but no dynamic value。

 you can still call the methods of S1。 So in this case， S1， its method is speak。

 right that's the method that's defined the interface and dog or at least it's specified in the interface。

 And then dog defines that method， right So when I say dog defines that method。

 there is a method dog， whose receiver type is dog method speak。

 whose receiver type is dog and that method is fully specified。Now。When this S1。

 it has a dynamic type， the fact that has a dynamic type means that the compiler knows that when you call speak。

 call that speak method on S1， it can look at the type and say， oh， the type is dog。

 dynamic type is dog。 So I know that the method implementation that I want is dog method implementation。

 So you can it can call that function， that method speak， even without having a dynamic value。

 All it needs to know is that dynamic type。 The dynamic type is enough information to go find which implementation to speak you want to use。

😡，Now it would be wise inside your function， inside the function of the speak function to check to see the variable has if it has a dynamic value or not。

 but the point though is that you can make the call even without a dynamic value all you need is a dynamic type so we take a look over here we got this function dog speak rather。

 and its receiver is dog。😡，And notice inside the function says if D equals nil， then it prints noise。

 some generic thing， else， it prints D dot name prints the dog's name。

 know Now what that does is it checks saying D equals nil， it checks， look。

 it does this have a dynamic value or not。If it doesn't have a dynamic value and D equals nil。

 then it just does what it says there prints noise because it doesn't have a dynamic value yet。

 prints something generic else if it does have a value， then it knows it can actually access D name。

 D do name， and so it prints out the name。AndThen the rest of the code maybe that would appear inside a main or something like that。

 which I'm not drawing here， but so I declare the speaker S1 I declare the dog pointer D1。

 I said S1 to D1， so now S1 has a dynamic type but no dynamic value and then I can call S1。

 speak and it works I call S1。 speak， even without the dynamic value because I can because it can figure out the compiler can figure out。

 oh， I see S1 is mapped to D1 which is a dog so I can find the dog the method of speaker that is associated with dog that I have defined up above。

So this is actually legal。 So the point of all this is legal to have a speaker sorry。

 an interface with a dynamic type but no dynamic value and in that situation。

 you can still call the methods of that interface so it's legal to do that now it would be wise like we do here to check inside the method if if the dynamic value is nil or not because you might want to do something like for instance。

 if we didn't do this check， this is where we say if D equals nil， if we didn't do that check。

 we might try to print D dot name， even though D was nil and that would throw an error at runtime So we don't want to it's probably wise to check it。

 but it's allowed this is a legal state to have a dynamic type but no dynamic value。

Now on the other hand， people use the term a nil interface value。

 this describes an interface with a nil dynamic type。

 so it not only does it not have a dynamic value， it doesn't have a dynamic type and that's a different situation。



![](img/32a573e4a7bee048b864bff71e4515af_3.png)

In that situation， when you don't even have the dynamic type。

 then you cannot call the methods on that interface because without the dynamic type。

 you can't know which method you are referring to。 So for instance here。😡，If at the top example。

 I got this speaker S1 dog D1， and I say S1 equals d1。 So it has a dynamic type。

 but no dynamic value， So the compiler can figure out if I were to call speak it would be able to figure out oh I see it's the dog speak the one whose receiver type is dog But if I have a no dynamic type So if I just say var S1 speaker and leave it at that then I don't have a dynamic type yet because I haven't assigned s1 to anything so S1 is just sitting there with no dynamic type。

 no dynamic value and in that state there's no actual method to call if you tried to call speak on that it would throw an error because there's no method implementation。

 remember remember an interface doesn't specify that it doesn't give the implementation of the method it specifies just the name and the arguments in the return value。

 but it doesn't actually define the method。 So if you just say var S1 speaker。

 there's no method that is associated with there's no speak method。Associated with S1。

 So this would throw an hour。 So the point here is summarize that if you have a no dynamic type and no dynamic value on an interface。

 then you can't call the methods of the interface。Thank you。

