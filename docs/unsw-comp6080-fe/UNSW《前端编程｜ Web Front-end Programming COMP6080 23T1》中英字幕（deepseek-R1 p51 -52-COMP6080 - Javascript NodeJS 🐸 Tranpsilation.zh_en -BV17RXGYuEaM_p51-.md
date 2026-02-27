# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p51 -52-COMP6080 - Javascript NodeJS 🐸 Tranpsilation.zh_en -BV17RXGYuEaM_p51-

![](img/be6c9fb479170fcc43eec6823a4e9dcd_0.png)

Hi， my name is Nick Barker， and this lecture is Transpolation for Com 6080。

So as with any other very technical term， we want to start with a reasonably lightweight definition and build from there。

 so what actually is translation？Well， the word itself is a bit of a portmanau of what I assume is transforming or transform and compilation and if you're a computer science student or you've been learning about this type of thing。

 you would probably know by now that compilation is the process of transforming source code into machine code。

Transforming code that's written by and can be understood by humans into something that a computer can understand and execute directly。

By contrast， Transpolation is the process of transforming source code into different source code。

 so the output of transpolation still will need to be compiled or interpreted if you want to actually execute it on a computer。

So for a more direct example， compilation would be the process of using a compiler to transform C++ into machine code。

 into object files into executables， and transformpolation would be the process of transforming C++ code into equivalent JavaScript code。

So if you've used C++ before， you would probably be thinking。

 why on earth would I write something in C++ and then transform it into JavaScript？Well。

 there are actually a lot of good reasons and a lot of specific cases where we use transpolation and it's very。

 very heavily used in the web front end space。😊，So why do we need translation and what are the actual use cases for it？

So the first use case that we can think about in terms of what we're learning at the moment is transpirling a different language into JavaScript。

So JavaScript is the only language that's natively supported in the browser， well， you know。

 apart from Web assemblymbly these days。But historically JavaScript has been the only supported language and that means that just by default。

 if you want to run something， if you want to write something in a different language and run it in the browser。

 you have to transpile it into JavaScript and this has been historically a lot of large scale apps have done this for legacy libraries or codebas or just situations where there was a large codebase of people who were well versed in C++ or similar and wanted to transform it to run in the browser。



![](img/be6c9fb479170fcc43eec6823a4e9dcd_2.png)

So this is an example of transpiling some source C++ code into JavaScript that you can run in the browser using a library called Mscriptin。

And you can see that in order to even get it to run because JavaScript and C++ are very。

 very different languages， you need an enormous amount of buffer or wrapping code to mock a lot of the interfaces that are used and mock the expected behavior of functions。

In C++ so you can see， I think there's about 10，000 lines in this file， maybe 12000。

 something like that， just to print a hello worldld writing a hello worldld application in C++ and transfiling it to JavaScript。

The other examples are not this extreme， but this will give you an idea of the kind of machinery required。



![](img/be6c9fb479170fcc43eec6823a4e9dcd_4.png)

So probably the biggest example and still the most widespread usage of transpiring in JavaScript is actually transpiring JavaScript to JavaScript。

 new JavaScript to old JavaScript and what I mean by that is as time goes on。

 more and more new features are added to JavaScript of language。

 more and more new browser and native APIs are added to browsers。

But the thing is with the web that we never know what type of browser someone's going to be using when they access our website。

 it could be very old and if the old browser that someone's using is a browser that we still want to support。

 we only have two options， either we write all of our code in old JavaScript that we know is supported in most browsers。

Or instead we can write our code in new JavaScript and actually transpiile it backwards into compatible older JavaScript so for a long time native classes as in object oriented classes weren't supported in JavaScript and as a result we had to if you wanted to use JavaScript class you had to transpiile it back into an older JavaScript compatible implementation that involved the JavaScript object prototype and a number of wrapper functions that made certain class related builtins work like instance of for example so you can see in this case。



![](img/be6c9fb479170fcc43eec6823a4e9dcd_6.png)

We have some source code that just defines a class in JavaScript。

 that's JavaScript on the left and JavaScript on the right。We have a class that has a class method。

 all it does is console log test and you can see that we need 24 lines of code in an older browser to create something that emulates the behavior of a class so that we can have a compatible API。



![](img/be6c9fb479170fcc43eec6823a4e9dcd_8.png)

So there are even some nice projects online where you can actually try out compiling new JavaScript features backwards to older JavaScript。

 older compatible JavaScript， and one of the most famous transpolation tools for going between different versions of JavaScript is Babel。

So Babeljs。o， you can find the repel there that you can use to test out the trans。

Another great example that's getting more and more popular all the time is transpiring something that's almost JavaScript intocomp browser JavaScript。

So over the years， there have been a number of flavors of JavaScript that have been created to try and address some perceived issues in JavaScript。

Coffeecr was an example that provided a newer set of ergonomic features and compacted the syntax a lot。

 and it was very popular for a while not so much anymore and Tpescript is reasonably new and this brings compile time type checking and type annotations to JavaScript so both of these are very close to being JavaScript but they're not compatible。

 they won't execute in the browser， so we have to transpile them from their current state to compatible JavaScript in the browser。

So you can see in this case， Typescript on the left has a number of type annotations。

 including some generics and type cast with an as。And on the right。

 you can see all of the type annotations have been stripped out and our output is just plain vanilla JavaScript This is called Translation。

You can try out the TypeScr compiler if you get the chance。

 TpeScrri is actually a wonderful language and it brings a lot of safety to JavaScript that we didn't use to have in the past。

 so I encourage you to check it out。Another great example of where translation is super useful in the web is for minification and obfuscation there is a lot of overlap between these two concepts。

 but they are kind of for different things or they have a different type of intention。😊。

So Minification is the process of reducing the number of bytes that a user has to download before they can execute our application。

So web applications have incredible advantage of being accessible from anywhere not needing to explicitly download an executable or compile it for a certain platform。

 they just run in this wonderful VM called the browser。😊。

But one of the downsides to this is because we have to download the entire application before we can execute it。

 it means that we are constantly in a fight to keep our application that we ship to our clients' browsers as small as possible。

So Minification is one of the little hacks that we do in order to get our bundle size down as small as possible。

 So what we do is we take all of our jascript and we do things like removing white space。

 removing comments。Renaming variables to be shorter， you know， all of that kind of stuff。

 we do that in order to minimize the amount of code that we actually need to ship to the client because as long as the execution of the code yields exactly the same result。

 we don't actually care what the code looks like that the client's running， right。

Ofuscation is a similar kind of process that often involves renaming variables and stuff like that。

 but the main point of obfuscation is making it much more difficult to reverse engineer the source code because what the user will download in the browser is actually nothing like the source code that the engineers are actually working on。

 So it makes it a lot more difficult to understand and reverse engineer。

For a very extreme minification and obfuscation example。

 you should look up Google's closure compiler。😊，So closure compiler is used to Minify JavaScript。

 it used to be used a lot more to type checked JavaScript as well。

 but usually these days Typescript is more popular for that type of thing。

But one of the amazing things that close compiler can do in advanced mode is it actually really looks deeply at your code and figures out exactly the bare minimum that is required to actually get the code to function in the browser。

😊，So in this case you can see it's pretty amazing we have a function that takes an argument。

 an object called user。And we call an alert with hello and then the users' the property name on the user and then further down you can see we call our hellello function with a new anonymous object with the name set to new user and you can see Google closure compiler in advanced mode is actually so smart in this case that it's figured out that the function hello is only called once and that the only property we access on the constant user object is the name and so it's actually the resulting output is it's gotten rid of the function。

 it's gotten rid of the call to the function it's even gotten rid of the user object and just replace the name because it's figured out that this is the minimum possible representation of the code that we gave it。

And over a very large application， this can actually save a lot of bytes and as a result。

 can have your users interacting with your website much sooner。😊。

YouC compiler has a nice website where you can go and try it out。

 so if you want to you should take the bundle from your app。

 run closure compiler on it in advanced mode and see how much it can actually compress it down often it's actually more than 50% which is pretty amazing given that GZip can then compress it again after that。

So transpiling seems like a really interesting thing。

 and it's obviously used in a lot of different ways as part of our front end development pipeline。

But how does transpiling generally work I won't go into the nuts and bolts of how we actually parse the code and transpile it from one thing to another because it's very different depending on the outcome in the source。

But in a general sense， these days， when we do front end development in JavaScript。

 we have a build tool like webpack or roll up or gulp， one of the older ones。And generally。

 we will run a build step before we can actually execute our code。

 So our source code that we work on is actually not executable at all。

 usually when it comes to front end jascript code bases。

 We will need to transpiile the source code that we work on onto something that the browser can understand。

 and configurations for tools like Webpack can get very。

 very complicated to the extent where it's many， many people's entire jobs just to run the build pipelines for large front end code bases。

So generally tools like Webpack are a bunch of plugins that run that do different types of transpiles and as a result we can have lots of different engineers working on different open source plugins to do CSS transforms to do JSX transforms to transpile Tscript and that kind of thing and then we can just install the plugins or the loaders that we need to do the work for us。

Now just as a final note for this lecture， it is worth mentioning that transpiling isn't free and you don't necessarily have to write things in a superet of JavaScript or something that transpiles into JavaScript so it's worth mentioning that the build process for building JavaScript doing the translation is slow generally TypeSscript。

 for example， as applications get very large， it can take a long time to actually transpile into vanilla JavaScript and if you're not careful with the way that you build your pipelines。

 you can really slow yourself down by having too many translation steps。

Another thing to mention is that very heavy Trans， especially by something like closure compiler。

 means that the code that's executing in the browser is substantially different to the source code and so this obviously means that when an error gets thrown in the front end。

 the error is being thrown in a completely different place perhaps even a different function stack to where the error is actually written in the source code。

 and as a result we need a reasonably complex system of source maps to actually map the line in the compiled code back to the source code。

And it means that all of our tools， all of our error gathering software。

 that kind of thing needs to support our source maps so we can actually take our production code and understand what's going on where。

 because the production code itself is usually not readable。

 it's compressed down to small symbols and it's all on one line to remove all the white space。

So that's just something to think about。I hope you enjoyed this lecture。

 I hope it gave you a little bit more of an understanding into the machinery that's going on under the hood when you run NPpm run dev or something similar in createate reactact app usually' webpack underneath that's doing that work and there are a number of different steps that your source code is going through being transformed transpired before it ends up being executed in the browser thanks。



![](img/be6c9fb479170fcc43eec6823a4e9dcd_10.png)

Yeah。