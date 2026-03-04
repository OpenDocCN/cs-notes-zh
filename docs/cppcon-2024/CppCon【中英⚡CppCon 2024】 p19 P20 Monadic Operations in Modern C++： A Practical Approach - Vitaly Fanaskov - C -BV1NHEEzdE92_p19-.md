# CppCon【中英⚡CppCon 2024】 p19 P20 Monadic Operations in Modern C++： A Practical Approach - Vitaly Fanaskov - C -BV1NHEEzdE92_p19-

There's more value in the connections outside of these talks and actually it's sooner the talks themselves like we've spoken to a lot of very experienced。

 very tenured people who have lots of you know great stories and mistakes that we can learn from so that we don't have to make them as well。



![](img/f1599a3e6d2318b31828297e9b7f6a7f_1.png)

Hello， everyone and welcome here。 The talk about Ma operations。 And today。

 we are going to talk about practical approach。😊。

![](img/f1599a3e6d2318b31828297e9b7f6a7f_3.png)

To this technique， let me introduce myself first。My name is Vitai and I've been doing C++ for quite a while。

So more than 10 years of experience in developing different things from the framework libraries to。

Vfiix and geopatal systems。 And now I'm working as a senior software engineer at remarkable。

We are Norwegian company， and our main product is this nice。Ink tablet for those who make in notes。

Sketches， diagrams and stuff like that。I'd be happy to share more。 But after talk。

 it's not the main point here。And as I agenda for today。

 we are going briefly talk about two classes with mon operations support。 The first one is optional。

 The second one is expected。 This talk is mostly about expecting monoical operations。

Then we are going to talk briefly about common use cases。And tips and tricks at the。

I'm not going to talk about any theory here， not even about category theory。

 There will be examples from the C plus person， there no hkell or any other functional languages。

And I will be showing a lot of practical examples here。

So you can ask questions during the talk and I will probably ask you to raise your hand a few times there will be some questions to you。

And I also put 10，15 minutes aside at the end of the talk for questions。

 If it's more comfortable for you。 So let's get started。First of all。

 I already mentioned two or three times the examples and where do the examples come from。

We have our own internal framework that we use for development on our devices。

 And from the very high perspective of you， there are three main components that we have libraries。

There's basically shared functionality than modules。 They represent the certain。Caapbilities， like。

 say， for instance， the last generation of our device may support the colorful display or the plugable keyboard or something like that。

And when we combine those modules altogether， we get in bundles right here。 so and those bundles。

 they do represent the certain piece of software。 for instance。

 we have the previous generation So software。 then we have the desktop emulator。

 if you don't want to test everything on the device and so on so forth。In this framework。

 we have like a lot of different subsystems。 And one of the most interesting。

 perhaps subsystem is the user interface subsystem。

That's responsible for primarily collecting Windows and widgets for modules and Windows。

 mostly in terms of like mobile development， not like operating system Windows and widget that the small parts that we that the modules can share between each hast to display some pieces of information。

Like settings， for example。We use， of course we do not render it ourselves。

 we use findingss to some sub patchy libraries and for the devices that a library。

And this module also used for navigation between Windows， say we want top this certain window。

 certain route。 That module will be used for this。Okay， now my question is。

 how many of you are familiar cuted？All right。I will briefly talk about it， then。Oh， first of all。

 the technology is reviews it's also an interesting part。So the we use C plus plus 24 our product。

 We have V C package as a package manager。 So we have like 30 plus different set p libraries。

In use like ranges， deal L expected K2 for tests and many other stuff。 And as I mentioned。

 put for U I on the devices。Cute that the interesting thing kind of has two words。

 The first word is a word of C plus plus ch。 And in this word， we define our business logic do。

Integration with subpa libraries， some system level or say， nontro platform abstraction。

And on another side here we have Kl code， and Kl is a declarative language that's used to describe the UI。

And in this code， there also can be some logic， say animation related states related and tons of horse。

 And there is a connection between all of those two stuff because from C+ plus code。

 you can create curl objects and manipulate Ql objects and from Kl objects。

 you can use C+ plus objects that are exposed some way。And this interesting。

That was one of the motivation why I decided to talk about this specific system。

 because the error handling， the approach to how we work with a code。

 the paradigms are completely different in Q mail， for instance， iss completely normal to say。

 just print all errors， warnings and stuff in the user output。The default one。

 whereas in C plus plus， we can do mans。 We can throw exceptions and error costs and many other things。

Now， let's talk about classes option unexpected。 There were many good talks during the conference。

 so I will just not that different it。 Just talk very briefly。The first。Think iss stood optional。

The closest。Abstraction， or we can think about it like about pay off。Certain type and bull。

 which is not like this in all implementations。 But still， it's easy to understand。

And this stuff can contain either value or nothing。 Here， we have optional box of in。

 I will be using this technology， because。for many reasons。

 but it's super easy to visualize it as a box where I can put Samsson and there will be Samung or Na。

And now we put in this box 42。 and then we can extract this value from the box。Like this。

We usually use optional when an operation can fail， but we don't care why。 For instance。

 here is an example of。The same vector class。 and it's about separation index of if element is not found to be simply return special objects student lot that indicates the absence of object of the result。

 And if the element is here， we can return its index。 So in this particular case。

 which has don't care。 Okay， like， or there is like only perhaps one reason why index of。

Return something else in index。 right。 There is no element in the vector。From time to time。

 I don't like this one in particular， but I said many times。

Then we use optional to pass some additional arguments。 Like， for instance， here。

 we have a function to resolve URL， and then we have optional configuration。

If there is a configuration， we can resolve a URL from there or input accordingly。

Or if there are no configuration， we resolved to use in some default settings。And yeah。

 from C plus plus 26 or probably the next standard， the optional will be it。 it will be range。A view。

 But with the difference。 if you read the last sentence here。

 So it's kind of the lifetime of content till bound to the。Object out to this range。

 And it's kind of。Interesting stuff。 We will see how to use it when it' will be in place because they can the range of either zero element or one element。

 So like。Interesting thing。So now let's talk about expected。 and expected is very similar， in a way。

With the difference that there can be either。Object of T or object of E。 So like left or right。

And their closest implementation would be like stood variantant target Union of T， O E。

And if you have expected box here， for instance， of int and some error class， because in C plus+。

 we think about it like the first one is a value。 and the second is an error type。

 and we can put something here。 Now it's value by default to put an error introduce an expected title I'll show you later how。

And then we can extract it from the books。When do we use it and we use it when an operation can fail。

And we potentially want to know why。For instance， here， we have a function for loading a widget。

 We have stood expected of wget。

![](img/f1599a3e6d2318b31828297e9b7f6a7f_5.png)