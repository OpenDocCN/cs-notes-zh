# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P28：27_模块3 3 1 结构体.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/845c326dc3518609a3516f8f08ba2ac1_1.png)

🎼う。🎼Yeah。So astruct is another aggregate， another composite data type is an aggregate type。

 meaning it groupss together objects of arbitrary data types into one object。

And and it's useful for a lot of things， usually it's for organizational purposes。 it really helps。

 So let's give an example， easiest way to talk about it。

 you got let's say you want to make astructstruct is short for structure， by the way， and by the way。

 this is taken also straight from say C Csstructs 2。

So let say I want to make a structure that describes a person， a personstruct。

So say every person has certain features， a name， an address， and a phone number。So for every person。

 I want to represent these three different aspects of a person。So what option？

Would be to have three separate variables for every person。 I'll have three separate variables。

 and the programmer has to remember that they're related。 So maybe I have name one。

 and I might use naming for that。 So I might say well name 1， address 1， phone one。

 I have three different values， right， And I put one after all of them。 So I。

 as a programmer can remember， okay， this is name one and address 1 and phone 1。

 they must be related。 They all have one after them。 And then the next person I make。

 I'll call it name 2 address2， phone 2， and so on。 So So this one way。 And in that that scenario。

 these three piece of information， name address phone。 They are related。

 they have to be the programmer themselves has to remember that they're related。

 that this name is related to this address in this phone where this other name is related to this address in this phone。

😊，Now another way， probably better way to do this is option2。It's to make a singlestruct。

That represents a person。 And that struct， it aggregates all three variables。

 So this one object now contains a name， address and phone number of one person。

 So they are related because they are in the same object。 And so when you're accessing them。

 it is obvious that if you're accessing them from the same object。

 you know that they are related to the same person。

 So that's what a struct is for for bringing together different variables that are related in the application。

And putting them together so that you as a programmer。

 know that they are related and they are related to the same person or whatever the object is in the application that you're talking about。

😡，So here's an example of a struct。You've got so we're defining a typestruct type。

 and we're going to call it parson。And this person has three fields， three pieces of information。

 a name， address and phone number。 so notice how I'm defining this thisstruct type is called person。

 I give it as name as a person， and each one of these fields， name， address and phone has a type。

 name， string， address， string， phone string。After that， once I define this type。

 I can define any number of persons right I can say Var P1 is a person Var P2 is a person and so on and P1 in this case。

 it's going to have a name， address and phone number all its own。So each property is called a field。

 so names a field addresses a field， phones a field。

 and P1 can have values for all of those fields that are unique from another variable P2。

 which is a person or P3， so I can have any number of persons in there。

So if I want to access the fields of the structure by access， I mean read from them or write to them。

 change them， I use dot notation， this is not like with a arrays with a arrays。

 you use a square brackets and use an index， use dot notation here so P1t name if I want to assign that to Joe。

 I can say P1 dot name equals Joe and that will assign the field the name field of P1 to the string Joe。

😡，Also I can read in the same way I can say x equals p1 dot address and that will assign x to be the address of P1 so use dot notation rather than the bracket you would use with arrays。

Initializing structures， you can initialize them using the new function。

One way to make sort of an empty struct。 It initializes all the fields to 0，0 values。

 So like in this person structure， the the values are all strings， right。

 So the0 value is going to be empty string。 So I could say P1 colon equal new person。

And it'll make a new person that's empty， they'll zero it out， so the name。

 address and phone number will all be empty strain。

Another way you can initialize the structure is you can initialize it with astruct literal。

 so if you want to give values to all the fields right when you create the person and we're showing that here。

 P1 colon equals person， then in parenthees I'd give thestruct name。

ThatLet give me the struck name and then struck value， right， So name Col。

 Joe comma address Col A dot S T A street， and then comma phone colon 1，2，3。So in this case。

 I'm using a struck literal， and I'm making a new structure。

 but I'm also assigning all the fields to different values， Joe and A Street and 1，2，3。

 so I can do that too。

![](img/845c326dc3518609a3516f8f08ba2ac1_3.png)