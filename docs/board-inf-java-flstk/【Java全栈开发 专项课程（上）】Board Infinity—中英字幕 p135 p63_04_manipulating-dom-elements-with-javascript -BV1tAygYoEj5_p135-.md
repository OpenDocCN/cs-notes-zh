# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p135 p63_04_manipulating-dom-elements-with-javascript -BV1tAygYoEj5_p135-

Hi there。In the previous video we learn how to access dom elements now in this video we will learn how to manipulate dom elements using JavaScript。

So let's get started。When we talk about manipulating the dom with JavaScript。

 we mean that it can be used。To dynamically modify the elements on webage without having to reload the entire page。

For example， suppose we have a web page with a button and a paragraph element。

You can use JavaScript to change the text inside the paragraph element when the button is clicked without having to deode the entire page。

To do this， you first need to select the element you want to modify using a dom selector。

A dom selector is a method that allows you to select an element or group of elements on our web page。

There are several different dom selectors you can use and we have covered them in the previous video。

Once you have selected the element， you want to modify。You can then access and modify its properties。

Properties are characteristics of an element that you can change such as its text content attributes and styles。



![](img/e3d62bedadbc423dac23fd386405a16d_1.png)

Let's see some examples。So now I am here in my Vs code and I have a indexed HTML with its spoiler plate ready。



![](img/e3d62bedadbc423dac23fd386405a16d_3.png)

I also have a script tag where we can write our JavaScript code。

And this is getting outputed in the web page。

![](img/e3d62bedadbc423dac23fd386405a16d_5.png)

This is a very basic HTML page， and this is what is called as Dom。 You can say console dot log。

And there is one more keyword that is console or Dr that gives you the directory or you can see properties or methods that you can use to manipulate the dom if I say console or Dr document。



![](img/e3d62bedadbc423dac23fd386405a16d_7.png)

Let's click on save， lets go to inspect and console。

 you can see that it lists down all the properties and methods that you can use。We have URL location。

 background color， base U， all elements， we have a lot of things here。

You can go through them and you can use whatever you want to use as per your use cases。



![](img/e3d62bedadbc423dac23fd386405a16d_9.png)

So if I want to get the domain， I can say。Console lot log。

 and we can just log the domain so we can say log document。L domain。



![](img/e3d62bedadbc423dac23fd386405a16d_11.png)

So if I click on save， you will see that we get domain that is 127。0。0。1 in this case。



![](img/e3d62bedadbc423dac23fd386405a16d_13.png)

If I want to get the URL， I can just commend this and I can say document dot URL。



![](img/e3d62bedadbc423dac23fd386405a16d_15.png)

Fally on save， we will see that we get the URL of our web page。



![](img/e3d62bedadbc423dac23fd386405a16d_17.png)

If you want to get title， we can get the title or lets say if you want to change the title。

 we can say document dot title and we can make it equal to lets say dom manipulation。

So if I click on save。It should be basically a string。



![](img/e3d62bedadbc423dac23fd386405a16d_19.png)

If I click on save， you can see that the title has changed to dom manipulation here。



![](img/e3d62bedadbc423dac23fd386405a16d_21.png)

Similarly， if you want to get body， you can say document dot body。

 It gives you the body of your entire web page。

![](img/e3d62bedadbc423dac23fd386405a16d_23.png)

![](img/e3d62bedadbc423dac23fd386405a16d_24.png)

If you want to get head， you can see document or head， you can do a lot of stuff。



![](img/e3d62bedadbc423dac23fd386405a16d_26.png)

Let's see how we can add a text。😡。

![](img/e3d62bedadbc423dac23fd386405a16d_28.png)

So first you want to select the element， so you want to select this body element。So we can see。



![](img/e3d62bedadbc423dac23fd386405a16d_30.png)

Here， let's say con。I coned。Body would be equal to。Document， dot body。

We have selected the body element， Then we can use method like body dot append or append Cha。

 and we can just append a text here。 let's say hello if I click on save。



![](img/e3d62bedadbc423dac23fd386405a16d_32.png)

You will see that Hello comes here on the Web page。Let us say we want to create a new element。

 so what we can do is we can go here and we can just create a dev so lets create a variable that is constant de。



![](img/e3d62bedadbc423dac23fd386405a16d_34.png)

And we can say document dot create element。 So this is the method you can use to create an element。

Wwhichch element want to create we want to create a de so I can write dev at this point you can write h3。

 you can write p tag， whatever the element you want to create you can just mention it here。😊。

And then if I say console dot log div， lets commend the others。



![](img/e3d62bedadbc423dac23fd386405a16d_36.png)

Lets target the body only at this point。 if I click on save。

 you will see that in the console we are getting div， but is this div actually getting added。

 Lets find out so we can go to our element section。

 This is our STml inside the body you can see that there is only h1， so where is this div gone。

Actually， what we have done is we have just created an empty div。

 We have not yet added it into our document。

![](img/e3d62bedadbc423dac23fd386405a16d_38.png)

So for that， we can use a pen childil。Before that， you want to add some text to div。

 so you can say div。Dot inner text。And let's say we are adding a jascript text here。

 and then we want to add the divff inside the body so I can see body dot a pen or a pen child。

 and we can add a div。

![](img/e3d62bedadbc423dac23fd386405a16d_40.png)

Now， if I click on save， you will see we have a div with text of Java。

This is how you can create the elements。Let's also see how we can remove them。



![](img/e3d62bedadbc423dac23fd386405a16d_42.png)

So if you want to say body。And you can say body dot remove child。



![](img/e3d62bedadbc423dac23fd386405a16d_44.png)

And you can pass dev here， So if I click on save， you will see that that particular div is gone。

This is all you can remove。 There is one more method， that is。



![](img/e3d62bedadbc423dac23fd386405a16d_46.png)

Directly remove you just have to target that de and you have to say de taught remove that it。

It will also remove this particularic tip。So， we have seen couple of methods here that is inner text。

 append and append child and remove as well。

![](img/e3d62bedadbc423dac23fd386405a16d_48.png)

Let's summarize this。So accessing Dom elements with JavaScript allows you to select and modify elements on a web page without having to reload the entire page。

You can use dom selectors to select elements and then modify their properties such as text content attributes。

 styles。And child elements， and then so on。This is all for this video in the next video we will cover modifying styles and attributes to JavaScript。

See you in the next video。 Thank you。🎼。

![](img/e3d62bedadbc423dac23fd386405a16d_50.png)