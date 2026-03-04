# CppCon【中英⚡CppCon 2024】 p45 P47 Boost Your Intra-Process Communication Programs With C++20 & Contract-Concep -BV1NHEEzdE92_p45-

🎼。

![](img/8b28a98a31c01162adee9dcab027205e_1.png)

Hello， everyone。 Good morning。 Thank you to come for coming to White talk。

 I'm really glad that you are here， and I hope that you are going to have a wonderful experience。

 I'm Arian， and today we are going to write some contracts。 As we know。

 performanceform is one of the main staples of C++ and I would say the main reason of why we write the code and for that reason I made sure that I have a super catchy title on in order to draw your attention。

 but for the purposes of this talk。 I would like you albeit for a short moment to completely forget the title。

😊。

![](img/8b28a98a31c01162adee9dcab027205e_3.png)

So。What I noticed during my lifetime is that with communicating with people or during getting a new job。

 I was always presented with different kinds of contracts that I had to sign。

As being a technical person， as I am during my sleepless night， instead of counting sheep。

 I was trying to solve this problem。 and I came to the conclusion that everything that we do in our lives is sort of an arrangement or a contract。

As I。Took a deep dive to the problem。 I noticed that the crux of all of these contracts is just generating new information or exchanging existing information。

 And I came to the conclusion that the C plus plus itself as a programming language。

 it's a contract that is given to us in order to express ourselves。 Therefore。

 instead of having a usual arrangement where I am the presenter of the talk and you the audience。

 I would like that for all of us to put on the head of the lawyer。

 and let's start writing together some contracts in order to supercharge our inter process communication programs。

😊。

![](img/8b28a98a31c01162adee9dcab027205e_5.png)

So let us set some rules into place first， IPC stands for Interprocess Communic。

Programs stand for software running in a constrained environment， I would call them embedded devices。

 but for some people， embedded devices would be tinyny tiny devices that have barely maybe 64 mebytes of RamM。

 but in our case， what we are going to do， we are targeting those embedded devices that have at least 512 mebytes of RamM。

 that means the ability to run the full Linux kernel and use all the facilities that Linux provides As for the CCciI。

 it stands that for contract， concept and implementation and this is the pattern that we are going to utilize in order to supercharge our intra process communication。

What is the problem that we are trying to solve with an IPC As we know。

 images are widely available and they are used in different kinds of applications。

 And one of the basic operations that we can do in the image is just basically extract the image channels。

 the color channels in computer world images are made from three main colorss。Red， green and blue。

 And we would like to have a service which allows us to extract a particular channel from image。

For interprocess communication， we are going to use a facility called Dbu that is just an an abstraction written E C which sits a top upon the Linux sockets that introduces some abstractions like for example。

 bus service， object path， interface and methods， which makes our programming more easy in order to explain to you what these mean I will take a simple analogy。

 for example， a bus， you can think all of the network communication that happens for service。

 you can think of process group that live under one single parent， for example。

 under PiID one for object path that could be your executable for interface it is astruct or C plus plus class and for method name are just the methods that belong to this particular class。

So the people who have designed the system D have provided us an interface in order to achieve this and we are going to use this contract。

 which is a low level in order to be able to extract the specified color for the image that we upload in order to do that first we need to define astruct which is called error and we use a macro definitionfin and we don't have idea what is going behind。

 but that's how the interface is working， that's how we are applying the contract provided by the system D then we need to declare a pointer of type SD bus message。

 we need to declare itself bus as SD the bus pointer in order to store the results。

 whether it was successful， we just declare a constant in 32 and when the methods are executed from the Dbus if we want to get the results back。

 we just store them in the variable called R。Then for input parameters we are going to use two static strings first one is just going to be the file path to the image that we want to perform this operation the second one is that we provide a path where we would like to save a new image with the extracted channel and with the on site in8 we are just telling that we want to extract a particular channel in our case with number one we represent the green channel。

And in order to do that we call the method called SDD bus called method。

 whereas as you can see we provide a huge number of input parameters。 we have bus。

 then we have three constant strings that we have the method name which is explained as an excerpt channel。

 we provide the reference to the address actually to the error message。

 we provide something in the constant string with these weird letters called O O Y and we provide our three input parameters。

 so without further ado I would like for you to raise your hands things that this is a wonderful interface。

The call function。 Well， you think， would you like to elaborate more But you think this is。And。

 and like wonderful， basically easy to use and easy to access， not to make mistakes。 Well。

 as I predicted， nobody one would raise ahead。 So I'm going to at the opposite。

 who thinks that this is not a good interface。 That could lead to disasters， everyone。

 So it's obvious。😊，I think that by applying CCI pattern。

 we can make this interface much better because with this interface。

 I see problem with every possible parameter。 Let's start for example from bus bus it's a pointer and in the C language we need know that we need to manage its lifetime So the creation and the destruction no matter how experience a programmer you are when youre retired it or when you didn't get enough coffee for that day you will forget to use free that happens it's quite normal。

 then we have a constant string which are three constant strings which specify the service name object path and the interface name and we see that are very particular in the way that they specify the service name uses dots then the object path uses four bus ses and if you make a mistake or you don't follow the convention the code compiles it works correctly but when you go to your better device and flesh it to use you run to a runtime error So for three parameters we have some runtime errors that we need to take care of。

AndThe biggest problem that I see is that for the input parameters that you have to provide in our case being file。

 save path and channel， you need at the same time to provide their signature。

 so if you didn't write00 why which is the signature of these three input parameters。

 the code would compile you would get zero complaints but when you would go and flash your device or embedded embedded device and try to use your code you would be met up with an error message and now imagine that your embedded embedded devices youre living in a car。

 you compile the code and you go to your car in 10 minutes and you hope for your program to work and you just run in run-time error。

 a big waste of time。So what we are going to do， we are going to create a contract which specifies the characteristics of data type。

 then we are going to create a concept which enforces the contract and finally we are going to create an implementation which is constrained by the concept。

So I have just like a general questions on who of you likes writing contracts or reading through them？

I guess nobody who hates going through long contracts and trying to understand them。

I see some hands up。 so don't be bothered and I try to make this contract as easy as possible。

 So we are just going to define some vocabulary which will serve us during our talk in order to understand what we are actually doing。

 So contract is just a bunch of papers that you get and our bunch of papers in our case will be represented either with astruct or the C++ class In the contract。

 you have many paragraphs which explain the conditions or what is going to happen with you when you sign a contract。

 So our conditions in our case are just going to be the。Members of a type or the member facts。

 they are going to be templated and for the type， they are going to take the type upon which we are applying the contract and most of them unless specified differently。

 they will always have a bullolean as a return type。

 So either it's satisfied with true or it's not satisfied with false。

So what I wanted to do with a bus object， I wanted to convey through the contract that I wanted to be inside a unique pointer。

 which gives me the guarantee that the lifetime when it's created and going out of the scope will be destroyed properly and I want to make sure that I only have one instance of bus because again I am repeating myself if you happen to create two bus instances the code will compile correctly but when you go to the runtime it will crash because you cannot have two bus instances。

 I created a simple type depth which called as the bus inner type which is unique pointer of。



![](img/8b28a98a31c01162adee9dcab027205e_7.png)