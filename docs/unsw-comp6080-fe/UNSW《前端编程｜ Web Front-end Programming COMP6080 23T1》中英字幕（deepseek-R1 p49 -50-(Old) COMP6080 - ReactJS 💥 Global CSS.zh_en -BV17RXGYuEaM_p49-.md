# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p49 -50-(Old) COMP6080 - ReactJS 💥 Global CSS.zh_en -BV17RXGYuEaM_p49-

Hi and welcome back to Com 6080 React plus CSS。 My name is Tom。

 and today we'll be talking about integrating CSS into HTML to make beautiful user interfaces。😊。

When we make Re applications， it's great to get all the additional functionality， the neatness。

 the isolation， but if it just looks like text on a screen， it's not going to delight our users。😊。

React shouldn't be a framework for building user interfaces。

 It should be building great user interfaces， and luckily for us。

 we already know a little bit about styling our HTML with CSS。

 and we can use CSS just as easily in react。

![](img/03a2b8446d64abda3de52228d31a3d13_1.png)

We'll start today by creating a new react app to play around with。

 We'll use createreate React app again from our intro to reactact lecture。

 and we'll be creating a new project。😊。

![](img/03a2b8446d64abda3de52228d31a3d13_3.png)

Let's move over to the terminal。So here I'll use createre React app to create a new react app to test out our CSS。

Once complete， let's open it in the editor。

![](img/03a2b8446d64abda3de52228d31a3d13_5.png)

In the last lecture， we changed our app function so that it returned a div that contained the date and time。

Let's do the same thing again， Once we're finished， we can start to give it some style。

Just like in HTML， we can pass in a style attributee to our JSX， which contains our CSS style。In JSX。

 the style attribute accepts a plain JavaScript object， where the key is the CSS property。

 and the value corresponds to the CSS value。Like in JSX。

 any CSS property with a hyphen gets converted to Caml Ca。

Here we've defined an object with a colour key that has a value of red。 If you apply this style。

 the date and time text should change to a red color。Now。

 because the style attribute accepts a JavaScript object。

 there's actually no need to define it as a variable and pass it in。

 What we can do instead is we can define it in the same line that we pass it in。

This technique is referred to as inline styling。It is useful。

 but it's subject to the same limitations that you get when you define styles in HTML。That is。

 it's hard to keep track of what your styles are， particularly in larger code bases。Also。

 it can be difficult to apply the same styles to multiple JSX tags at once。Luckiily for us。

 we've already seen a solution to this。Inline styles have their place。

 but we can use CSS classes in JSX， just like we do in HTML。

You can see here that I'm passing the class name attribute with the capital L。

 This replaces HTML's class attribute and accepts a string where you can specify the class name。



![](img/03a2b8446d64abda3de52228d31a3d13_7.png)

Now we can use class names， We can make our app look really unique。

You'll notice in your application folder that there is an app。 CSss file。

 What I've done here is I've removed the existing classes in the CSS file and replaced them with my own。

I've given the app component a maximum width， aligned the text to the centre and provided some paddings and margins to make it look better。

I've used border radius to make the corners of the box rounded and inverted the components's colours so it has white text on a black background。

It also has some behavior when you hover over with the mouse。

Feel free to have a play around with the CS file yourself to make a component that feels more like your component。

 Go crazy with it。 do whatever you like。😊。

![](img/03a2b8446d64abda3de52228d31a3d13_9.png)

Now we've written a CSS file， and we've given the tag a class name。

But in order to tie the two together， we need to import the CSS file。

 So the JSX has a place to look for the class we provided。

We can import the CSS file like we would any other file when the page reloads。

 the app Jodge As file will load the classes inside the CS file。

 and the date will have the correct classes attached。 As you can see。

 it's very easy to create styles this way。

![](img/03a2b8446d64abda3de52228d31a3d13_11.png)

Let's try a live demomar。Okay， first things first， I'll create the date component。

I've given it a class name， named app。And I've inserted the date locale string in the middle。

As you can see， the application is now rendering the date。So let's add some attributes。

I'll provide the max， width and alignment。As well as in margin and padding。

It's nice to make the borders curved， and it'd be good if the background was a little more interesting。

😊，Not only that， but I'll give it some behaviour for when I hover over it with the mouse。

We'll make it enlarge， a little。When I refresh the page， nothing has happened yet。

 but that's because I haven't imported the file。And there you have it。



![](img/03a2b8446d64abda3de52228d31a3d13_13.png)

You can see here the app component is looking a lot nicer。Here's a more advanced example。

In this example， you can see I'm mixing a class name with some inline styles。

We can combine inline styles and class names。 however we like。 There aren't any restrictions。

Here I've got a header and a paragraph， both of them use inline styles。

 but the rapping div uses a class name。Also， you might notice in the inline styles。

 attributes like font size and margin top have been converted to use Caml case。



![](img/03a2b8446d64abda3de52228d31a3d13_15.png)

Unfortunately for us， it wouldn't be programming if everything was this simple if we're importing CSS in a file。

 you would assume that we can't use the same CSS in another file After all。

 we've imported it only in one， and if that was true that' would be great because it would mean that we no longer need to worry about problems like overlapping class names between different CSS files。

Unfortunately for us， this is not the case when we import a CSS file。

 the classes within that CSS are available in all other files。

This can be a little confusing to grasp， so I'll show you what I mean。



![](img/03a2b8446d64abda3de52228d31a3d13_17.png)

Okay， so here we have an app component and you can see that I've imported another file into it。

 The other file is called other component， and it returns to div with a class name of app。

You can see that I'm not actually rendering other component。 I'm just importing it。

In the other component CS S S file， I've got the app class name， but nothing's in it。

 Let's try adding something。Firstly， I'll try changing the text color to lime green。

Nothing's happened so far。I'll try up in the font size。And I'll refresh the page， and there we go。

 for some reason， even though I'm not using other component and I'm only importing it。

It is adjusting the font size on our app， and it shouldn't be。If I change the import order。

 so I import other component after Ab dot CSsS， you can see now that the color is lime green。

 so the behavior is inconsistent。In the first example， when I set the font size。

 the component change behavior， the reason for this is that my original app does not have a font size attribute。

 but other component does。Similarly， if I switch the import order around， it will load all the app。

css attributes first and then overwrite them with other components。

 meaning that the tax becomes lime green instead of white。

So you can see here that we've got a problem。We've got two components， both of them import CSS files。

 both of them use the same class name， but when the page loads。

 the class name gets meshed together in weird ways， depending on how we import。

So you can see that importing CSS in this way， while useful， is a bit of a blunt instrument。

 and it has a lot of problems and inconsistencies that we'd like to solve。



![](img/03a2b8446d64abda3de52228d31a3d13_19.png)

Part of making our components truly isolated means we need to make sure that if we import a CSS file。

 we can only use its classes within the file that we imported in。

 and it doesn't get mixed up with other components。

The good thing is that there are many methods to do this。

 methods like CSS moduledus or CSS and JS in later lectures we'll cover these。



![](img/03a2b8446d64abda3de52228d31a3d13_21.png)

Okay， that concludes our reactant CSS lecture。 Great job。😊，In later lectures。

 we'll examine some of these advanced CSS methods with react and how they can help us level up our components。

 For now， you're able to style your components， and we're excited to see what you come up with until next time。

 take care。😊。

![](img/03a2b8446d64abda3de52228d31a3d13_23.png)