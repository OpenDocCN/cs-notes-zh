# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p136 p64_05_modifying-styles-and-attributes-with-javascript -BV1tAygYoEj5_p136-

Hi there in the previous video we learn how to manipulate dom elements with JavaScript Now in this video we will learn how to modify styles and attributes using its own methods。

So let's get started。Modifying styles and attributes with JavaScript allows you to change the appearance and behavior of elements on a web page dynamically。

If you want to modify the styles， you can use style property of an element to access and modify its CSS styles。

And to modify the attributes you can use set attribute method to add or modify attributes on an element。

Let's understand all these methods and properties through some examples。



![](img/b680387ab2aea7740997c47b605df7c0_1.png)

So I'm here in my VS code and here we have an index or SML template ready with a script tag。

So we can start writing our code。Here in the body， I want to create a div。And inside this div。

 I will have a span tag。Let's give this I D of one。And let's they a name attribute of。

 let's say first。And then we can just write here。 It is the first span。 This is some text。Similarly。

 I want to create one more span and we can give it an I of two。

And let's give it second and second span。Now we need to write some ja code。

So first we can select all the elements using dom selectors， So Ill say con。

And we can see here document dot query selector， and we can pass div here。Then， we can say con。

Sand one， and we can make it equal to document。Dot get element by Id。

 and we can pass the I D name as one。Similarly， we can do it for two as well。So we can say span2。

 and this would be2。Now lets start manipulating the styles and attributes so let's talk about attributes first。

So if you want to get the attribute， you can say console dot log。

And let's say if we want to get the attribute of span1， so we can say span1 dot get attribute。

 It is a method It will take the attribute。 we want to get the value of attribute name。

If I click on save if I go here。

![](img/b680387ab2aea7740997c47b605df7c0_3.png)

Let's refresh。 We get the output as first， right， because。



![](img/b680387ab2aea7740997c47b605df7c0_5.png)

The name has the value of first， at this point。Let's say if we want to change the name。

 that means setting the attribute so we can say span 1。Dot set attribute。 This is the method。

 We can put the attribute name。 Let's say name and the value in the second argument。 Let's say A B C。

 D， E。

![](img/b680387ab2aea7740997c47b605df7c0_7.png)

If I click on save。You will see nothing here， but if you want to see the actual change that happened。

 you can go to the element section to the body。And here inside the day。

 we will see that now the name has changed from first to ABc D。If you want to remove the attribute。😊。



![](img/b680387ab2aea7740997c47b605df7c0_9.png)

You can just say。San one to to remove attribute， and we can just remove the attribute of name。



![](img/b680387ab2aea7740997c47b605df7c0_11.png)

If I click on save， you will see。In this。San， we only have the ID and name has been removed。



![](img/b680387ab2aea7740997c47b605df7c0_13.png)

A very short feature is also there that you can just say span1 dot I and rather than using set attribute。

 you can directly give it an I name of lets let's say any text。So if I click on save， if I go here。

 you will see that in the body now。

![](img/b680387ab2aea7740997c47b605df7c0_15.png)

It has seems to this sort of unique number， a unique word or letter， right you can name it anything。



![](img/b680387ab2aea7740997c47b605df7c0_17.png)

You can also change classes。Using class methods， So let's say if I target span 2 and I can just say span 2 dot class list dot add and I can add the class。

 let's say a new class。

![](img/b680387ab2aea7740997c47b605df7c0_19.png)

If I click on save， you will see that in the body under the dev span ID 2。

 we get a class that is new class。

![](img/b680387ab2aea7740997c47b605df7c0_21.png)

If you want to remove， you can just。Say， remove。Like this and you can pass the class that you want to remove。

You can actually manipulate the styles using a style property。 Let's do that as well。

 So we can say spanm 1。Tt。Style， dot color。 And let's give it red。 So if I click on save。

 you will see that the text color has changed to red。



![](img/b680387ab2aea7740997c47b605df7c0_23.png)

![](img/b680387ab2aea7740997c47b605df7c0_24.png)

Similarly， if you want to change the background， you can say span 2 torch style。

Taught background color。You can put any property here and let's give it green。So if I click on save。

 you will see that the background of the second span has changed to green。



![](img/b680387ab2aea7740997c47b605df7c0_26.png)

![](img/b680387ab2aea7740997c47b605df7c0_27.png)

So let's summarize this。So the style property can be used to access and modify CSS styles of an element and the class this property can add or remove classes to apply styles。

To modify attributes， the set attribute method can add or change attributes while the get attribute method can retrieve the attribute values。

Lastly， we have also seen remove attribute method through which you can remove an attribute from an element。

These capabilities allow developers to create interactive web pages。😊。

That can respond to user input and change in real time。This is all for this video in the next video。

 we will learn about events and event listeners in JavaScript。See you in the next video。 Thank you。🎼。



![](img/b680387ab2aea7740997c47b605df7c0_29.png)