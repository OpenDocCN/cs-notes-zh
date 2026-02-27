# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p68 -69-COMP6080 - Testing 🦔 Component Testing.zh_en -BV17RXGYuEaM_p68-

Hi everyone， my name is Brian and today we're going to be looking at unit testing and component testing specifically in react。

By component testing， we mean that we are testing our individual components to make sure that they function as expected。

 regardless of how they're integrated in the broader app。For testing in React。

 there are two main libraries that we'll be using， there's Jest。

 which is a general JavaScript testing framework。And there's react testing library。

 which is a react specific testing framework， which will be helpful for testing our react components and thankfully if we're using Cre React app。

 these two libraries are installed as part of it so we don't need to install any additional libraries。

 which is convenient for us。

![](img/f4205cebe71f10355ab0ce02d8fa4ebc_1.png)

Let's look at an example。Here we've got a button component。It's got three props on click。

 which is a function title， which has a default value and mode。If mode is dark。

 then it gives it a dark mode class。Otherwise light mode。

 and it renders the button with the on clickick class name and title。

Now let's look at how we would test such a component。

We can look at the example test that Craig Gka gives us。This is a test， we can see we use test here。

 we give it a title， we rendered the app。We use screen。 get by textex to query the elements。

This gives us a link element and we can assert that it is in the document so we can do something similar for our button。

Yeah。So here we are writing a test， here we're using it。

 it is just a synonym for test and we also use describescribe here， describe it's not essential。

 but we can use describe to group test together so in this case。

I use describescribe with a title button to group the tests that relate to our button。In our tests。

We use render to render our button in this case we are not using any props just yet。

 we're just render rendering everything as it is by default。嗯。We can then use。Spen do get by role。

To basically query the button。In the dorm。And we expect。对。This thing here。Is in the document。

 we expect this to be in the documents。So this is now a simple test that we've got and we can run it。

With yarn test。Or MBmbM test。All right。So it's running the tests in button。test。chs。

This is handled by react scripts， which we can see in page。Jason， the script， the Test script。

 which is set up by create reactactor， and basically just runs the tests that are in files ending in dotest。

ss。And as you can see， we passed one out of one test。

We can also be more specific with our query here。 So in in here we are querying by role。

 and what role means is just an accessible role that elements have。We can use。It name。

Grameter to be more specific， so we want。To get a button， but not just any button。

 we want the button to have this name， this accessible name， which is our default handle， click me。

This is a regular expression， its syntax。But you can also eat strings。

 this just means that you can this text doesn't have to be k sensitive because we've got an eye there。

And we've passed another way to do it is instead of using get by role， we can use get by text。

 which just gets an element that has。The given text， in this case。

 we get something that has the text include me。And again。

 we can use expect and to be in the document in the same way。Generally for elements like buttons and。

And other things like headings and that sort of thing， those generally have an accessible role。

 so it's preferable to use get by role， but for things like paragraphs and other text。

 we can use get by text。嗯。Now， if you're wondering what queries to use and how to use them。

 I would encourage you to look at the documentation。嗯。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_3.png)

，Cact Library website has some useful information on this。

 so there is a section on priority which will give you an idea of what queries to use by priority so the top priority is get by role。

If an element has an accessible role， you should use this because。

That will make sure that your elements are accessible， for example。

 a button is actually rendered as a button and it will appear as a button to screen readers and other things there's get by level text get by placeholder text get by text which we've also used。

And there's other things that you can see in the documentation。There's also the Gest documentation。

 which has documentation on， for example， the expect。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_5.png)

A method， so you expect here， this is part of the G library。

 which is the general JavaScriptscript testing library， there's information on that。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_7.png)

![](img/f4205cebe71f10355ab0ce02d8fa4ebc_8.png)

And the other thing that we are using is a library called GeestO。

 this is already included by default in setup tests JS， that includes geestO。

 but what it is is it extends the things that you can assert。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_10.png)

On your expect statements， so。Things such as two be in the document。Is part of guest off。这边。

The document。Here we go。 So this allows you to assert whether an element is present in W or not。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_12.png)

And we're using it here， we do expect。We query the element and we assert that it is in the document。

他的嗯。Helpful things when writing tests。Is if we pass an invalid role to get by role。For example。

 just an empty string。The test will fail because there is no elements with the role empty string。

 but。It's good in that it prints out。What roles are available in our component in this case。

 there is a role button with the name click me。And so that can indicate that we can use。

G by row button。But would then I include me。Another thing is。Spring do deeper。

What screen Do Dbu does is it just prints out the dome。Which is good for reference。

 we can just see this is what's being rendered and then we can see what elements we want to query。

And I said the properties are。And lastly， log testing playground URL。

What this does is it prints out a link to this website。Call testingplayground。com。

It is a tool that basically helps us。

![](img/f4205cebe71f10355ab0ce02d8fa4ebc_14.png)

Write the queries for the elements， so here we can see the the HTML that's being rendered。

The markup and on the right we can see the actual thing that's being rendered。

 so in this case it's just the button that says click me。

And we can click on it and it will give us a suggestion of how to query it using react testing library。

 so in this case， we can use get by roll。On the bottom right here we can see the the various alternatives of the different query types。

 so for example， we have text here as well so we can do。Get by text。

 but get by role is generally preferred over get by text。

We can use getby text in cases where it's not possible to use getby role。Oh。

So we've got get by roll here， you can copy this and use。Use these in your test。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_16.png)

Let's look at。Adding some more test cases， so we've got rendering the button with the defaultvolt title。

嗯。Wehe also also want to test with a custom title。To do this simply we can。Again。

 call render with the button and pass。A custom title to the title prop。Then we expect。That。

The same as previous the button element。Except the name here is a custom title。

 so we expect that we have a button with such a name to be in the document。嗯。

If you look at our components， we also have a mode prop。We can test that as well。By default， we use。

Light mode， so render with no crops。Expect the button to have class Light mode to have class is also from Jeest do。

嗯。And。When we pass in dark as mode。It should use should have a class called dark mode。

So we can assert these things。And。嗯。run these tests。They should。Pass。

 so four out of four total tests pass。Now有。Also have the on clickick functionality， so。

The button takes in onc and passes in to the button that's been rendered。In this case。

We can create what's called a mock function。嗯。By doing this j。fn。

 what a mock function is is basically a function， it does nothing but it records when it's being called and what it's being called with。

So we can create an unclicked function。An oncek mock function pass it in as onclick to our button componentnet。

And then we use user event， which is a library。To simulate a click， so we do user events， click。

We do the same thing as we're doing before to get the element。

So what this line does is it simulates a click on the button。We can then expect。

That are on click function。To have been called one time。And。

this test passes as well so here we've got the button which is the title of our describe block。

And then there are five tests within the describe block。

So hopefully these examples will help you get started with testing your react components。



![](img/f4205cebe71f10355ab0ce02d8fa4ebc_18.png)