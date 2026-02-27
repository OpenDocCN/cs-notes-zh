# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p69 -70-COMP6080 - Testing 🦔 UI Testing.zh_en -BV17RXGYuEaM_p69-

Hi， everyone。Today， I'll be talking about automated UI and integration testing in the browser。😊。

We've got a lot to go through today。😊，First， I'll be recapping some theory that I think you would have covered in previous lectures。

 then I'll be talking briefly about the idea of integration testing and automated UI testing。

We'll discuss selenium and the fundamentals behind what makes it run and how it can be used in testing scenarios。

I'll then be talking about how to write a good test。

 we'll discuss the idea of flakkiiness and how to prevent it。

Then we'll jump into a demo using another testing framework known as Cyppress。

So let's recap testing is the ultimate guardrail against software bugs。

It allows us to understand our code better over time and make changes without causing a phenomenon known as regressions。

 where previous functionality starts bugging out because of new stuff that we've introduced。

Not only that， but the mere practice of testing improves the quality of a code base。

Speaking personally， I take a dogmatic attitude towards testing if any nontrivial code arrives without any tests。

 then I see that code more as working by a happy accident than by any developer intent that means there's a lot of software in the world that works more by accident。

So we spend a lot of time telling you why testing matters to your code。

 but probably less time telling you why it matters to your life。And it's pretty simple， really。

 all or most of you listening to this lecture probably have some ambition to being in an IT related field。

 be it as a programmer， a project manager or even like a business analyst。

 the likelihood is that you'll be involved in some way in building software。

So you're employed at a job and you don't write any tests， suddenly your software breaks。

You're the person who will need to fix it。And software doesn't break neatly on a 9 to 5 schedule。

 Sometimes it breaks at midnight or while you're on a date。

 which has happened to colleagues of mine or while you're out with friends。

 depending on the industry you're in， the company you work out and the severity of the problem。

 you might be obliged to fix it immediately。So testing isn't just a guard rail against breaking code。

 It's a guardrail for your professional life。 It allows you to maintain good working flexibility and a good work life balance。

 which is incredibly important。 If you view testing in that way。

 cutting corners on it becomes a lot less attractive。

 The worst case scenario of testing is that you might spend a whole night trying to fix a bug that you could easily have prevent it through a test。

And for some spending a whole night on software is you know， a dream come true， but the reality is。

 if you're spending all night fixing a bug that you caused， you're not really getting anything done。

And personally， while I like software， I also like sleeping。So rant over， remember to test。

 most important thing you can do。Okay。In a previous lecture。

 you would have learned about black box testing versus white box testing， Let's go over it again。

Black box testing is a form of testing where your tests don't have knowledge about how your application is implemented。

 Your main goal is to test behavior and the experience delivered to users。

White box testing is testing the program's structure。The main goal is to test possible code paths。

 edge cases that might not surface to the user and general program structure in white box testing。

 the test does have knowledge about how the application is implemented。Both are important。

 both have their place， but today we'll be really concerned with black box testing。

So how do we black box test an application in the browser well。

Start with what we know about black box testing。In black box testing。

 we don't know about how the code in the application is run， we test against what the code outputs。

Luckily in the browser， the code outputs more code， it outputs the Dom。

 so if we want a black box test in the browser， we'll be testing directly against the output of the Dom。

Time for another recap this time on integration testing， you may be aware。

 but let's refresh our memories。Integration testing is a method of testing the boundaries between different components of an application。

Unlike a unit test， which might test a class or a function in isolation。

 we're really concerned with the interaction between our units。Speaking broadly。

 integration tests are not cheap like unit tests， they're slower to run。

 they take more time to set up and to write， and they can break more easily。

But the expensiveness is offset by their effectiveness。

 A single integration test could cover 20 units of code。

 so they're far more effective at detecting breakages。

 particularly the sort that make their way to the user。A UI test is sort of like an integration test。

UI tests are an important component of integration testing suites。

 They're particularly important in browsers； They're a form of black box testing that test against the Dom。

UI tests generally involves simulating what a user might do in an isolated environment。

 so simulating， typing， click events and so on， they're really effective at catching the things that the user is most likely to notice they can be done manually。

 but they can also be automated。So when should we write an integration or a UI test？

Keeping in mind that integration tests are expensive to write。

 the most common strategy is to start with the most common pathway your users go down。

We generally refer to this as the happy path and an example would be a sign up flow on your website we can make that assessment based on the impact if something goes wrong and the number of users that would use the components affected by your test。

Let's go into this in a little more detail。Integration tests are expensive。

So itll be a poor use of our time to write expensive tests that cover areas that our users aren't affected by or that we don't particularly care about。

In those situations， unit tests might be enough to cover what we need。So often。

 we'll start by writing a test that covers the happy path on our core flow。

A happy path is a path traversed by users where everything goes right。

 and the core flow is the main way that your users are expected to interact with your application。

For example， Google's coreflow is performing a search。

If the happy path on your coreflow doesn't work， then your software is broken。

 Imagine if the search function on Google broke all the time。 Would anyone use it。

In a workplace environment， a breakage of this sort would generally be the highest severity and you could end up doing a lot of overtime to fix it。

So。I've decided I want to test the happy path on my core flow。

How can I write an automated UI test to cover this。

The answer lies in our ability to simulate the browser In previous lectures。

 we outlined that you can either simulate the browser using a fake dom or you can connect to a real instance of the browser in this lecture we'll be testing against the real browser and a real dom。

So this may come as a surprise， but all mainstream browsers can be automated。

 it's possible to simulate any user event you can think of using code。

There are multiple frameworks available that achieve this， but to start with today。

 we'll be looking at Selenium。Selenium is a project that allows you to automate the browser。

At its core is a specification known as webdriver。WebDriver is an interface that was first created and implemented over its Selenium。

 and it allows browsers to provide a common set of APIs used by program languages for the purposes of automating the browser。

Webdriver used to be just a selenium thing， but it's actually now a standard that all browsers adopt。

 You can reasonably expect that any browser that's compliant with W3 standards will provide an interface using webdver for you to automate against。

So how does it work？At the call level， WebDriver talks to a browser through a driver's software。

Think about when you buy a printer。It installs a driver on your computer Without that driver。

 your computer doesn't know how to use the printer。Well， WebDriver is exactly the same。

 but instead of a printer， it's the browser。So you have a driver that sits between your browser and your code。

 and it acts like a proxy between the two。Your code sends information to the browser and receives information back through the driver。

Drivers are generally browser specific， so we have Chrome driver for Chrome。

 gecko driver for Firefox and so on。There's another important caveat。

The driver must always run on the same machine as the browser is speaking to。

 but your code can either run on the same machine or remotely on a different machine。

This shows what I'm talking about。On one end， you have our code， and on the other end。

 you have Firefox。The geckO driver sits in the middle and communicates information back and forth。

So the code might send an instruction to click a button。

The driver will receive that instruction and transmit it to Firefox's native API。

Then Firefox will perform the action and send the result back through the driver。

Chrome works the same way， but as you can see， the difference is in the driver。

 Chrome driver sits in the middle instead of Gecko driver。

Here's an example of the caveat I was talking about before。

While your driver always has to sit on the same machine as the browser you're automating。

 your code can actually be executed remotely。That means that the code will send instructions to the driver over the network and receive information back over the network as well。

Why do we have this， One reason is that integration testing against a local machine is prone to a lot of configuration problems。

What if your local machine is configured wrong， it could create false positives in your tests。

A remote execution environment can be controlled more easily。

 which allows it to be kept in line with an actual user environment。

So WebDriver lets you automate the browser， but it doesn't know anything about testing。

Testing frameworks instead can run and execute WebDriver code to perform UI tests。

 a testing framework might wrap the code， allowing you to perform actions and verify the results against your browser from within the confines of your testing framework。

Here's an example of some WebDriver code。We don't need to get too far into it。

 but essentially what we're doing is instantiating a Firefox browser， navigating to Google。

 attempting to find an input and as to the word cheese into it， followed by the enter key。

 We then do some verification before quitting。As I mentioned before。

 WebDriver is really an interface that any programming language can execute To illustrate this。

 here's an example in Python。It does exactly the same thing as our first example。 But for now。

 let's go back to the safety of JavaScript。Here's some more detail。 Once we have the driver。

 the first thing we do is a await or call to driver dot get。

This is waiting for the browser to load the URL in the function argument， in this case， Google。com。

We then make a call to driver。fin element， and in our function arguments。

 we're looking for an element that has a name attribute of Q。

We await that call to return and then send some keys to it。Again， for each instance。

 we're using a weight here， as we're calling against a driver， which is an external piece of code。

 so it's a fundamentally asynchronous operation。Finally。

 in our last call to drive a dot weight until element located。

 we're putting in a CSS selector using by。csS。In Selenium terms， we call this a locator。

 and it's the bread and butter of our ability to do stuff to the browser。

Locateators allow us to navigate and traverse through the dom。We're always testing against the dom。

 so we need a way to verify and interact with the elements located within locators are like a toolkit that allows us to do this。

A successful locator will always return an element that can be interacted with。

 and the good news is we have many different locators available to us for different situations。

In these slides， I've listed the locators as well as their method name in Python because the Python method names are the most clear。

We have loators for CSS ID and CSS class name， you can see here that the method names are find element by ID and find element by class name。

We also have a locator for the name attributee on a tag， as well as just the general HTML tag name。

We also have some convenience locators for link text and partial link text。

 which allows us to easily find links in our page。We also have a locator for something called Xpath。

Xpath is a very powerful locator， and it's something I'd like to go into in a little more detail。

Before I do though， let's loop back to our JavaScript example。

You can see here I have a find element call， and I use buy dot name。

The combination of Find element and buy dot name means that I'm using a name attribute locator which is provided by WebDriver。

Okay， let's take a look at Xpath。We have a number of convenient locators available to us。

 things like CSS ID， class names and names， but if none of them are sufficient， we can use Xpath。

Xpath is a really powerful syntax that allows us to define a pathway through an XML file。

HtMl has enough in common with XML that we can use it。

So I've included an example X path query here what it does is it finds a form element with an ID attribute of login form。

 then it extracts the first input element from inside the form that is the first child element of the form that's of type input。

So you can see here that Xpath is really powerful。 It allows us to define complex traversals through the dom。

That said， the other locators that we have are generally sufficient for our use cases。

 and we don't find ourselves using Xpath all that often。And with the end of Xpath。

 we'll stop talking about selenium now and we'll start talking about flaky tests。But before that。

 if you need a break， need to pause the video， stretch your legs。

 now would be a great time to do it because the next section is a little bit less related to selenium。

Okay。Let's talk about flakkiiness。A test is flaky if it sometimes succeeds and sometimes doesn't。

 for some reason， this is common with UI and integration testing。Why。😡，Well。

 when we're writing our tests， it's important that they have a key property， that of determinism。

 given the same inputs， a deterministic test will always output the same results。

Writing a deterministic UI test can be quite difficult because the UI is exposed to a lot of asynchronous behavior and time based behavior and so on。

 but nondetermin existingistic tests are not a good option。In this section。

 I'll be talking about what causes a test to be flaky and ways that we can look at fixing this。

The first cause of flakiness we'll discuss today is that a U I generally interacts with some other component beyond our control。

 our back ends。Many of our user flows will involve communicating over the network with some sort of back end server。

 So if the back end server produces a result we don't expect， our test might flake。

 or if it takes longer than expected， the test might flake as well。

One of the key properties of a deterministic test is reliable inputs。

 but we have a problem here where're relying on other components we don't have access to or control。

 We can't lock them down and the input they provide us is fundamentally unreliable。

You might say that a bug on the back end or not receiving the results we expect is a good thing。

But consider that those back ends will have their own tests。

 the test for our page should only test what our page controls。

 so if a bug occurs on the back end and breaks our test， that's not a good thing。

Here's an illustration of what I mean a web page might typically call out to a number of different backends here。

 it calls out to a login and an image service。If the login service has a bug or provides the wrong response。

 this might cause a breakage in our tests。We can solve this using a thing called Stubbs。

The idea is that in our testing environments， we don't call out to our remote back end services instead we create stub implementations of our back ends that will 100% produce reliable results。



![](img/5904220f14fa828c29749b6bdb98d8a4_1.png)

A starb is an object that implements the interface of another object。However。

 the implementation returns a fake response。The idea is that the stub can be switched out with the real object with no disruption。

Here we have a mock or a fake login service。 The real login service makes a remote call。

 but the fake one doesn't and just provides mock information。By using Stubs。

 we can ensure that the backend services in our testing environments always return the same results。

 providing us with a deterministic input for our tests。

Another note to make is that you can see here how testing promotes good code in general。

The existence of stubs implies we need to encapsulate our remote code inside some sort of class or function。

We don't have time to cover this today， but I just want to say the words dependency injection。



![](img/5904220f14fa828c29749b6bdb98d8a4_3.png)

So we have this stub service and it no longer tests against our real backend。But wait you say。

 surely an integration test is meant to test the boundaries between components of our application。

Surely the most important boundary is the one between the front end and the back end。 If that fails。

 everything else falls apart。And you'd be right。But it's more important to be sure that our front end components interact well together as a start。

N to end testing is a form of testing that we might use to test the boundaries between the front end and the back end。

 and it has its own set of practices for running optimally。

The next cause of flaky tests is randomness or entropy。 For example。

 a random number generator that across test runs produces different results。

You may think this is unlikely， but consider the date module in Java， which is time based。

 If your application makes calculations based on the date and time， which is incredibly common。

 and your test attempts to verify these， you may have accidentally created a test， which is flaky。

We can solve this again using proper stubs or by just being a little more careful about how we write tests that deal with these situations。

And just to underline that this situation is more common than you would think。

 there have been situations that I've encountered where tests can fail at specific times of the day。

 like 10 AM， for example。The next major cause of flakkiiness is performance。

UI tests are in the browser， meaning conditions which affect the browser can affect the reliability of your tests。

Your browser might be subject to constraints on CPU， processing power。

 memory allocation or bandwidth。It can take longer， for example。

 to render a page on your phone than on your custom build gaming PC， and this does affect our tests。

Consider this diagram。On the top， we've got our browser。 It's transitioning to different UI states。

On the bottom， we have our test cases。At each stage we perform an action。

 and then we verify the state of the browser。I've put one second between each browser transition and each test case。

 so the test cases and the browser are consistent with each other。In this case。

 the browser isn't affected by throttling memory problems or a slow connection， so the test passes。

Here you can see that the browser took longer to reach the second UI state with the start。

Instead of one second， it took 1。5 seconds。This could be due to CPU throttling。

The test case still ran a second later， but the browser estate wasn't yet where it needed to be。

 so the test failed。Does that mean we have some problem with our functionality， No， of course not。

 The code is still correct， but the performance of the browser LED to a test flaking on us。

So you might ask， why can't we wait until the browser renders the star before verifying it？Well。

 we're black box testing， so we don't really know what to wait for。Unfortunately for us。

 browser performance problems are just harder to solve for。

 They can have multiple causes and multiple solutions for each cause。

Here's a few common levers we can pull to improve our performance woes。The first is timeouts。

 Each test step in selenium can provide a timeout threshold， after which the test will fail。

 This provides us with some time to wait for the browser to catch up。

If a test step is failing consistently， you can increase the timeout on the test step to provide more time for rendering to occur。

Just be careful， though， if you do this every test step。

 suddenly you might have a test that takes 30 minutes。

 it's better to employ timeouts only when you absolutely need to。

We can also have a look at the environment we're executing our tests in。

What if they don't have the correct resources or are in an inconsistent state？You might for example。

 be running your tests on a potato of a machine， Bsers these days are expensive and they hog a lot of CPU in memory so make sure your execution environment can take it。

Finally， another cause of flakkiiness is unfortunately the drivers themselves that sit between the code and the browser。

 Safari is a good example of this。 Safari has a driver which is pretty inconsistent and pretty unreliable。

 and can often cause tests to fail， even though your code is correct。And finally。

 it would be remiss to discount the simple solution of just retrying。 It sounds stupid。

 but sometimes the stupidest solution is the one that fixes your problems for you。Okay。

 so far we've spoken about UI testing and black box testing。

 we've had a look at Selenium and WebDriver talked about our integration test flakkiiness and spoken about ways that we can solve it via performance。

 back end stubing and so on。Now we're going to move on to some practical examples。And again。

 if you're looking for a break， now would be a good time。



![](img/5904220f14fa828c29749b6bdb98d8a4_5.png)

Okay， so today for our practical section， we'll be using a framework to write some automated UI tests for a sample application that I wrote earlier。

The framework that we'll be using today is called Cyppress it was built to make automated UI testing easier and it's generally used for end to end testing but it can be used for integration testing as well。

Now， Cyprus is not a selenium based framework， but don't write it off that does not make the last 10 minutes a waste of time。

So why spend all the time teaching the architecture of Selenium when the example doesn't use it well？

Cyprus is limited to a jascript implementation where selenium is language agnostic。

 That makes selenium really commonly used， But unfortunately， with the driver and everything。

 it's harder to configure。The broad principles we discussed， though， will always apply。

 You'll always need to use some sort of locator。 You'll always need to write deterministic tests。

 You'll always have an execution environment， whether that's local or remote。

 you'll always face browser performance problems， so。Trust me。

 you will end up looking at Selenium at some point。Luckily for us。

 we don't need to spend much time on the theory or architecture of Cyprus because Cyprus is really easy to get running。

 it consists of two things， a test running application and a dashboard for you to look at the tests on。

It does a lot of the setup for you。 It handles timeouts for you。 It takes screenshots。 and above all。

 it's really easy to configure。That said， there are some downsides。

 Cypress only supports JavaScript for creating test cases。

 and it doesn't provide support for browsers like Safari or Internet Explorer at time of writing。

 So Selenia might be harder to set up， but it is a lot more flexible。Now， as I mentioned before。

 things like timeouts， which can help negate flakkiiness。Usually get configured manually in selenium。

 but Cyyprus handles all of this automatically for us。

 One last caveat you may have seen in previous lectures or been taught about this framework Jest。

 which is used for our unit tests。 Cyppress does not support jest。 Unfortunately。

 it supports a library called Mocha and S。 They basically do the same thing as jest。

 but they predate jest by a number of years。

![](img/5904220f14fa828c29749b6bdb98d8a4_7.png)

Okay， let's get started Today we'll be writing some tests in Cyprus In the interest of time I prewrote an application it will be available on the Gitlab。

 however， you can install Cyppress on your own projects really easily using yarn a Cyppress with a capital D flag to make it a dev dependency。

We can then run Cyppress to open the test runner and dashboard。 The first time you run this。

 it will configure Cyppress and create a cpress folder at the root level of your project。

 The command to do this is yarn run Cyppress open。When you run this command as well。

 you'll see a browser window pop up， which is your dashboard。



![](img/5904220f14fa828c29749b6bdb98d8a4_9.png)

When you first configure Cypress， there's an integrations folder inside of which are a number of samples。

 this particular sample gets an object with a CSS class name of action focus and then tries to focus it。

If focused， it will attempt to find the class name and verifies that the class name is focused。

From there， it will look for the immediately preceding sibling of the element and check that it has an inline style of orange。

The samples folder that Cyppress comes with is full of really useful example tests that should help you get started。



![](img/5904220f14fa828c29749b6bdb98d8a4_11.png)

Okay， time for the demo。

![](img/5904220f14fa828c29749b6bdb98d8a4_13.png)

So I've got a sample application here， which is just a simple sign up flow。 It takes a name。

 an email and a password。When I submit。A cool animation will play。Flash just an icon。 really。

 there's a back button there that'll take you back to the sign up form and you can see here it asks you to check your email。

Just a note on the sample application， there's no back end service interaction here。

You can see in my package。 JSON I've already installed Cyppress。

 I've also installed styled components which you might remember from our CSS in JS lecture。

 and there's a library there called Fme Emotion as well。

 which isn't something that we've discussed but it handles quick and easy animations。

So in the application at the top layer we've got two containing components and we've also got some user details that we're st in a hook。

 there's a variable that stores whether the form has been submitted or not and there's a reset call back to set our user details back to Neil。

You can see here that whether based on whether the form is submitted。

 we either display a banner or we display a header and a sign up form。

The sample application has a components folder and a hooks folder inside the components folder we've got a number of just presentational components。

 things like our layouts our containers， most of these are just normal styled components for example the button maps to the button that you see in the signup form。

You can see our root container is just a styled main component that's a flex layout。

Our header is just a styled component as well for an H1 tag just to make the formatting nice。

 but most of the logic lives in our sign up form component。So here's the sign up form component。

 You can see it's holding a number of pieces of state that map to our form。 We've got one for name。

 one for email， one for password。We're also using some hooks for empty validation and email validation。

 which I'll go through in a bit。And throughout all of that。

 we then have a computed ready to submit function， which is just checking that all of our form details are filled out correctly。

If they are， then in our submit handler， we call the on submitubmit callback， which is a prop。

We can see here that because we're using a form， we have to prevent the default event on the form。

 there are some better ways to solve this， but as this is a sample application。

 we just want something quick and dirty。So we call on submit with an object consisting of the name。

 email and password。And this is a callback function that's called in our form。

The form itself is just a simple form， it's got a layout component in the middle with three text input components。

 these are styled components are just the same as the header or the container that I showed you。

The button here is disabled if。🤢，It's not ready to submit and if it is ready to submit。

 it'll show the submit text， otherwise it will prompt you to enter your details。Keep in mind。

 so each text input also has a name， a trie， we've got name， email and password。

In our hooks here we are our empty validation hook is just a hook that we wrote ourselves and all it does is check to see if a string is not null undefined or empty The email validation is an email regular expression test which just checks to see if the string is of the same format that an email would be don't mind too much about the regular expression。

 It looks complicated， I got it from Sta Overflow you can see here that it's not valid。

Unless youd make it an email。So let's open Cyprus。

![](img/5904220f14fa828c29749b6bdb98d8a4_15.png)

。Okay， so I've run Cyppress and it took a while， but it did open。

 You can see here that it's got a list of JS files and these correspond to tests。



![](img/5904220f14fa828c29749b6bdb98d8a4_17.png)

Just heading back， when you run Cyppress Open for the first time a Cypress。

 JSON file gets created and that's for a configuration。

 it's empty at the moment because we haven't configured Cyprus， we're just relying on the default。

A cppress folder is also created。 There are four subfolds in here。

 but the one we're concerned with is integration。Now， if I open it up。

 there's an example subfoldder in here and nothing else。This is where you store your tests。

 and you can see Cyrus helpful adds a list of just example tests that' will help you get started。

So what I'm going to do next is I'm going to create a sub folder inside the integrations folder in Cyppress。

 I'll call it my tests。And inside that。😊，I'll create my first test file。And I've made a mistake here。

There we go。Okay， so this is the test file that we'll be writing our tests in。

The first thing we'll do is we'll create a context。 this is sort of like a describe in jest。

 it's like a parent wrapper for all the tests you need to write。Then we'll insert a before H close。

This will run code before every single test and you can see here we're callingsi。visit。

 Psi is the Raper for the Cyppress API， and we're saying to visit Localhost Port 3000。

 which is where our local Re application runs。I'm going out a test now and it will be a successful sign up test。

This is our core flow， and we're testing the happy path。Okay。So first things first。

 I'm going to define some constants。These are the values that I want to put into my sign up form。

Now I have these。 I can start writing out my test。Thes dot get function allows me to pass in a locator similar to the locators I use in Selenium。

 but here I'm saying I want an input with a name that is equal to the string name。

 so this should find my text input that has the name of name I。e。 my name text input。

Heading into my text input component or my sign up form first。

 you can see that my text input component has a name of name。So it should get this input。

And they link together in that way。The text input takes an input name as a prop。

 but it just passes it to a styled input component。

 so we know that when it goes and outputs to the Dom， it will be an input tag。

So the first thing I'll do is I'll focus the tag。And now I can begin to type。

 So all I need to do is type my namevariably。I can do the same for my next two input tags and it'll function exactly the same way in this one I'm looking to type the email variable into my email。

 into my input with the name of email and I'll do the same for my password here as well。

Now that's done， let's run the Cyppress test runner again and we'll have a go at running our test and seeing what happens。



![](img/5904220f14fa828c29749b6bdb98d8a4_19.png)

So we'll wait for it to load。Here we go。😊，So we've got an examples folder here。

 we also have a My tests folder， I've opened it up and I've got a My test。

js file inside if I click on that。It will run the test。And you can see how quick that is。

 but you can see it's typed in the Jane Doe name， the Jane Do email。

 and the password as we asked it to do。

![](img/5904220f14fa828c29749b6bdb98d8a4_21.png)

Let's extend our test。 First， we'll extend it by getting a button。With a type of submit。

And we'll simulate a click event on it。

![](img/5904220f14fa828c29749b6bdb98d8a4_23.png)

Okay， let's give this one a test。So I can click run all tests here and you can see that the button is clicked and it shows the sign up successcc banner as planned。

We don't really have a way of verifying， though， that the success was correct beyond seeing it on the screen。

 which is technically a manual task。 we don't want to have to supervise our integration tests。

 so what we need to do is we need to verify that the form submitted successfully。



![](img/5904220f14fa828c29749b6bdb98d8a4_25.png)

Over here， I've got my sign up Su banner component and you can see there's a bunch of style components。

😊，There's a wrappper for a div and there's our caption text as well。

 just in the middle there that has a data test target on it called caption Test。

In theres the the code that says check your email and inputs our email。

 So we're using a data test target attribute here。 This is a way of just quickly being able to locate an element in the Dom。

By passing in a customer tribute that is used only for testing。

 we don't generally recommend doing this。 It's better if you can use a CSS class name。

 but we're using style components which handle our CSS class names for us。

The risk of using data to test target is that。Details of the way that your application is coded are leaked in the Dom。

 so the data test target will be visible to users， so it's not advisable to do this if you can help it。

So what I'm doing here is I'm checking for any tag with an attribute data test target of caption text。

And I'm expecting the text inside to contain my email field。So this will go off。

 it will find in my caption， and it will check that the text has the email within it。



![](img/5904220f14fa828c29749b6bdb98d8a4_27.png)

If I run the test。You can see that the assert passed because the email is contained within that text field。

And so we have a successful test。

![](img/5904220f14fa828c29749b6bdb98d8a4_29.png)

And that's it Before we go， I just wanted to reiterate the justification for using data test target here。

 so data test target is a customer tribute it's used here to allow us to get the text really easily。

 but generally speaking it's not a good idea because it exposes aspects of your testing to users。

 which is not something you really want to do。Generally you can use other attributes like here if you wanted the link you could use the ATF class name and ID is a really good one。

 but because we're using style components we don't actually control that as it's a detail of our implementation that we don't know about so that's why we use data test target in this instance but generally speaking you should have some other attribute you can use。



![](img/5904220f14fa828c29749b6bdb98d8a4_31.png)

Anyway， that's it for the demo。😊，In it， we've created a successful automated UI test for the happy path of a sample application and all the code is available on GitHub if you need to have a look。



![](img/5904220f14fa828c29749b6bdb98d8a4_33.png)

So one last thing before I go， something that we do need to cover is just a little bit of a note about this thing called behavior drivenrive development You'll see it around the place and it would feel bad to talk about integration testing without really talking about this BDD is a method of development it's meant to encourage developers。

 testers and business people to formalize like a shared understanding of the way the application works and it has its own language you know we've got this idea of scenario then you outline a pre-existing condition like a given and a set of conditions beyond that which you can specify with and the when condition is when action start to occur and the then is meant to be the verification so you've got this idea of setting up a context saying when something happens then this other thing should happen。

It's often used as an interface to write automatic end to end integration tests in a way that business people can understand。

It's something that you may encounter。 it's quite popular with frameworks like robot frameworkrawork。

 which is a framework that uses this syntax to define automated tests， although。Broadly speaking。

 developers still need to write the code that glues these tests together。

 so from that perspective it's sort of failed to deliver on this idea that business people will start writing automated tests developers still do it。

 You may find yourself doing it， but just a good note and the lecture on that you may see that around the place。



![](img/5904220f14fa828c29749b6bdb98d8a4_35.png)

So yeah， well done。 That was a big 40 minute lecture of testing。 I really hope you learned something。

 Thanks for sticking it through and all the best until next time。😊。



![](img/5904220f14fa828c29749b6bdb98d8a4_37.png)