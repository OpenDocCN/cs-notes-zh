# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p98 p26_08_css-positions -BV1tAygYoEj5_p98-

快的。In our previous video， we have learned about attribute selectors。

We have used them in our HTML document。And see them in our Bel。In this video。

 we'll be learning about CSS positions。CS positions allows you to control the position of an element on a web page。

It is basically the way how you can put elements in a web page and how they'll appear to the user on a browser。

Now， let's discuss about different types of CS populations。First one is static。

Sttic positioning is a default position of all those HTMLl elements。

Elements with the static position are positioned in the normal flow of the document and cannot be moved or reposition with CSS let's see how we can position an element statically。

😊。

![](img/98aab824d4b448d096a9479cc5acb8dc_1.png)

So this is our HTML page and if we create a dev over here。😊，And let's just put some text。

Let's add some style。

![](img/98aab824d4b448d096a9479cc5acb8dc_3.png)

This is how this de position itself in our HTML document。

 this is called a statically position element why because static is a default position for all the HTML elements。

😊，Novic。Move to our next position。Which is relative。

Rative positioning allows you to position an element relative to its normal position。

You can use the top， bottom left and right properties to move the element up down left or right respectively。



![](img/98aab824d4b448d096a9479cc5acb8dc_5.png)

Let's see how we can do that。

![](img/98aab824d4b448d096a9479cc5acb8dc_7.png)

So let's say we create another day。And we will call it。Second if no。And let's put some IDs over here。

We'll call it first。And a second one。We'll call it second。Let's apply the style on the basis of。

The idea itself。And for second one， this word second。And let's just put some background color。

Let's say blue。We can use the same height of 100 px。We can put some opity。And now what we will do。



![](img/98aab824d4b448d096a9479cc5acb8dc_9.png)

Will apply position relatives。对 initially。Both things same。

Like there is no difference just the color and the op， but when we apply the property called top。



![](img/98aab824d4b448d096a9479cc5acb8dc_11.png)

![](img/98aab824d4b448d096a9479cc5acb8dc_12.png)

You can see it moved towards the bottom， or I can say it moved 10 p from the top。

And if we move the top to bottom。It moved 10 px from bottom。



![](img/98aab824d4b448d096a9479cc5acb8dc_14.png)

And we can see it is overlapping the first element。This is how the related position works。

Now we can apply the properties like top， bottom。Left。And we can see them in action。



![](img/98aab824d4b448d096a9479cc5acb8dc_16.png)

In our HTMLl page， let's move to our next position， which is absolute。

Absolute positioning allows you to position an element relative to its nearest position and sister element。

😊，If no S2 element is positioned， the element is positioned relative to the initial containing block。

 which is usually the body element。It sounds confusing。



![](img/98aab824d4b448d096a9479cc5acb8dc_18.png)

Let's see is in action that it will become easy to understand。What we can do now is。

Let's just change the position。For this element from relative to absolute。If we do this。

And check it out in our browser。

![](img/98aab824d4b448d096a9479cc5acb8dc_20.png)

We can see that now。It is looking different。And I just do one thing that just adds some more divisions。



![](img/98aab824d4b448d096a9479cc5acb8dc_22.png)

After this。

![](img/98aab824d4b448d096a9479cc5acb8dc_24.png)

And now we can see these divisions。Are currently having a similar flow like they are coming one after another。

And they are just kind of neglecting。This division。W it is happening because when we apply。

The property， absolute。It removes that particular。Element from the normal flow of the HTMLl document。

That's the reason it is a bit overhall。We can change the position with the help of。



![](img/98aab824d4b448d096a9479cc5acb8dc_26.png)

Same properties， which we have seen with relative。So let's say top if we put top 10 px。



![](img/98aab824d4b448d096a9479cc5acb8dc_28.png)

You can see it adjusted itself according。

![](img/98aab824d4b448d096a9479cc5acb8dc_30.png)

To the main element， which is body。So it adjusted itself， 10 px from the body。



![](img/98aab824d4b448d096a9479cc5acb8dc_32.png)

If we put 0 px。You can see。

![](img/98aab824d4b448d096a9479cc5acb8dc_34.png)

It has put itself at the top。Without any difference or any space。

If we want to position this element on the basis of some other element。

 let us say if we want to position it on the basis of first division。

 so let me remove all these divisions so we can see it properly。😊，So what we can do。

 we can put the position type。Pelative to our first division。And now it will adjust itself。

On the basis of first division。But for that， we need to put this inside the first division by。

Because。A division or any element with position absolute adjust just itself according to its parent。

So that is the reason we put it inside the first so that the first become the parent and if parent is relative only then it will alter itself according to the parent。

 otherwise it just according to the body tag because that is the highest tag in the hierarchy。

 there is nothing about body tag。😊。

![](img/98aab824d4b448d096a9479cc5acb8dc_36.png)

Now， we see if it is adjusting itself according to the first division。



![](img/98aab824d4b448d096a9479cc5acb8dc_38.png)

Even though we have put the OX over here。Let's say， we put。



![](img/98aab824d4b448d096a9479cc5acb8dc_40.png)

50 px or 80 px。It is adjusting itself according to the first division。

This is how the sal position works。Now lets just see how the fixed position works。



![](img/98aab824d4b448d096a9479cc5acb8dc_42.png)

So for doing that， what we will be doing。Willll be removing death for a while。We'll be adding。

Many of these。So that we can create a scroll effect。



![](img/98aab824d4b448d096a9479cc5acb8dc_44.png)

I see， yes， we are able to create this role effect。



![](img/98aab824d4b448d096a9479cc5acb8dc_46.png)

Now let just create a div at top。啊。What we can do， we can put position fixed， we can。

Apply this ID onto that div。And we can put。

![](img/98aab824d4b448d096a9479cc5acb8dc_48.png)

Fixed stiff。And now。

![](img/98aab824d4b448d096a9479cc5acb8dc_50.png)

Okay， we need to put top。

![](img/98aab824d4b448d096a9479cc5acb8dc_52.png)

Overhe。いいです。

![](img/98aab824d4b448d096a9479cc5acb8dc_54.png)

We can see it is adjusting itself at top。

![](img/98aab824d4b448d096a9479cc5acb8dc_56.png)

And we to remove the position relative， we need to make everything static。No， you can see。

It is positioning itself on top。It is also different from the common flow of this HTML document。

And even though we are spooning。

![](img/98aab824d4b448d096a9479cc5acb8dc_58.png)

It is still fixed on its position。We can say fixed position is similar to absolute positioning except the element is position relative to the viewport。

😊，Or the visible area of the browser window。This means that the element will remain in the same position even as the user close the page。

That's it for this video on C positions。By using the four main positions like static， relative。

 absolute and fixed， you can position elements on your web page in a way that best suits your needs。

😊，Experiment with different positions and see what works best for your design。



![](img/98aab824d4b448d096a9479cc5acb8dc_60.png)

See you next video。🎼。

![](img/98aab824d4b448d096a9479cc5acb8dc_62.png)