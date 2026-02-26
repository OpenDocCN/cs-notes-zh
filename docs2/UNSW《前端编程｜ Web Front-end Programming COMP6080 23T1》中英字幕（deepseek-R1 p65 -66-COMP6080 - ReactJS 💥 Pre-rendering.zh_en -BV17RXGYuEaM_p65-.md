# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p65 -66-COMP6080 - ReactJS 💥 Pre-rendering.zh_en -BV17RXGYuEaM_p65-

My name is Dan and today I'll be talking about prey rendering。



![](img/ae317c542e833dc96e21b4d82bd961bf_1.png)

So let's start off with a review。Single page apps is a concept that you would have learned about halfway through the term。

But as a refresher， they are basically a kind of web application where you only download a single HTML document。

So this means that rather than using the browser to navigate through pages。

 you need to use JavaScript to request and handle responses without leaving the page。

An example of this would be if you wanted to navigate to。

 say the About page rather than clicking about and having the browser send a request back to the server download the HTMLtML and then download further JavaScript and images。

 what you would do instead is use a fetch API with JavaScript to the About route and rerender a select few components to display the about page that you want without actually leaving the one HTMLtML page that you started off with。

So the advantages of this include a faster post load performance。

 so once the Ht document has actually been downloaded。

Any future pages or transitions that you make are quite quick， so go。In the next step advantage。

 you can see it can do near instantaneous transitions between pages。 So yeah。

 once the HTML page has been downloaded， it is quite quick。😊。

Disadvantages also include poor initial load time。Because you need to download a lot of JavaScript。

 you might not see anything for a while if you have eight slow network performance on top of this browser support may not vary so you can have different versions of JavaScript existing on other people's。

Browser environments so you will need to find a way to polyfill and transpile all of your JavaScriptscript。

And finally， and what I think most importantly is that it gives you a terrible SEO。😊，So more on this。

 search engine optimizationim or SEO， it basically means how well webCwl has understand the contents of a website。

So a good SEO basically means that your website will be ranked higher in search engines。

That is extremely important for any business， be a small business or a large business。

 it gets you quite good exposure because most people find information through search engines these days。

So for a SBA， the default HTML document is usually empty。

 meaning there is nothing in the body and you'll just have JavaScript in script tags。😊。

Any web crawler isn't going to be able to understand what content is going to be loaded and on top of that any pages that the website has haven't been rendered by the JavaScripts yet。

 so it's unlikely that a web crawler is going to be able to fully understand the important details of your website。

Now。We've understood that this has been a problem for quite a while and fortunately there has been a solution。

So this solution is called pre renderndering and basically involves generating the HTML for each page in advance instead of having the client's browser do it。

😊，So each generated page includes the smallest amount of JavaScripts needed for that page and once the page is downloaded。

 the JavaScript。😊，That comes with it， runs， and it makes the page fully interactive。

 and this process is called hydration。So two benefits of pre rendering。

 firstly it gives us better performance and secondly it gives us better SEO。😊。

Because there are HTML pages that have content with them。

 it is more likely that a web crawler will understand what is going on and it won't miss any important details for your website。

There are two types of pre rendering first is static generation and the second is server side rendering and we'll be going through both。



![](img/ae317c542e833dc96e21b4d82bd961bf_3.png)

So firstly， static site generation or SSJ involves pre rendering at build time。

Build time is basically a step in your deployment pipeline where you build your application。

Effectively， the HTML pages are compiled， if you will， once。

 and they can be distributed to different Cns from there。Sir。

It's best practice to use static site generation as much as possible because you only need to build your H MLl pages once and from there it can serve heaps of users requests。

Generally， if the pages depends on external data， there are methods to be able to enable you to populate it。

 so pre renderndering isn't disabled because of your dependency on external data。

So I'll show you this later on in a demomer。And yeah。

 the only case where you wouldn't use SSG is when there's external data that is frequently updating。

 so for example， you have a news API that updates every hour in this case you would actually probably be better off having the client browser render it or use SSR which is serverside rendering。



![](img/ae317c542e833dc96e21b4d82bd961bf_5.png)

So yep， serverside rendering basically means that it prerenders every time the user makes a request。

😊，A。This makes SSR slower than SSG because only one pre rendered page will serve one user request。

 you'll need to rebuild the new HTML page every time a user requests that same page。

 so there will be double up if you use SSR。And because of the worst of performance。

 you probably shouldn't use SSR for pre rendering unless it's absolutely necessary。

This basically means you probably won't use it often or use it at all。



![](img/ae317c542e833dc96e21b4d82bd961bf_7.png)

Now NextJS is a very popular framework and it's got pre renderndering enabled by default so one of the biggest advantages of Next JS is that it enables you to choose which type of rendering you want for every page that you have。

B， clientient side， SSG or SSR， it doesn't matter what type of rendering you have。

 it can do at all and it gives you a lot of granularity and flexibility with that。😊，On top of that。

 N JS also has some pretty cool features， they include a intuitive routing system， CSS and JS。

 automatic load splitting， and fast refresh or hot loading。😊。



![](img/ae317c542e833dc96e21b4d82bd961bf_9.png)

Cool so now I'll go on to the demo if you want more information or tutorials please visit the nextjas documentation in fact a lot of the notes that I've made in this presentation are directly from that documentation it's a really good resource。

 especially for anyone who's just starting out with the framework。😊。



![](img/ae317c542e833dc96e21b4d82bd961bf_11.png)

Our Demer， we're going to first create a next JS app using the createre Next app library。Essentially。

 all you need to do is have yarn or NPM installed， and you just type yarn create next app。

So what this will do is install some packages for you basically the minimum amount of packages you need to have a functional next JS app。

The project。W can call next J S Demer。Yep， and itll install all your packages quite quickly。

And I'll just open this up in ViS code。You can see here on the left there is the folder structure of the app so create next app gives you these three folders we'll start with the styles that's basically a CSS folder you can attach an ESS to it。

And the public folder has all of the o static files。Things like images and fabricab con experience。

And finally。Here is the pages directory。Anything that is a route should go in the pages directory。

 Next Js will automatically create a route from that page。 So， for example。

 we see here the index dot Js file that is going to be the home。Rrit。You can see here。

This is the home route， and we have the next JS default page。And you can say the card for it。

 it's in the account。Now the API folder is a special subfold of the pages directory。

 basically any APIs that you have can go in here。Yeah。

Now let's create an example component in the pages directory。Call it a sample。

And if we just do something simple。Expo default。Oops。And we return。The hell world。

A sample component it to come up here。 Hello， wellld。Nowao。If we stop。Dei。

Development server and build our application using yarn build。

Essentially what that's going to do is pre render all of our pages so in this instance since we have a example component here。

 what it should do is build a HTML page that includes this。And generally， the build step is。

A bit longer。Takes a bit longer than using the development server。 So when you're developing。

 remember to use yarn dev rather than yarn build。So as you can see here。

 next JS essentially gives you a rundown of how each page slash component was rendered。

I'm pretty red。This white dot next to the example root。Shows us that。It was statically rendered。

In this case， static rendering means no external data was fetched。

As you can see in our dot next folder。If we go to。sver。Example the H M， L and。We format this a bit。

You can see in here， just in the body， the first line。There is our Hello we line。go sir。

This server folder s the dot next folder will be served on different CDMs。

 so we want our example component to fetch some sort of external data and render it dynamically。

How could we do this with next JS。So first let's just get a example API。

 so essentially this API will fetch some data from a user here we see that is fetch some data from Canva and let's use the name and the location。

To display in this example component it。So in order to get external data at build time。

What we can do is export a function called。啊。Get static props， so。Make it a sink。And we'll just grab。

Our API。바을。再声。Yeah， so within this datastruct， we can expect this object to be returned。Now。

 if we want to pass。If we want to pass props to this example component。

 what we need to do is have get static props return a。Props object， So what we would do。

Is return something like this？And everything inside this object will be passed into example。

 so as said before we wanted to use name and location， let's just do that。At location。Yep。

 so that static props will pass。This object， into example。We can de structure。Like， sir。And now we。

Can just print out。And do you combine it。Let's do。Hello。啊 name。Hows the。Weath in。Vcation。bit in。

There we go。Now。And tell。So as we can see。The G static props function has passed these props into this component。

Now， if we wanted to build。You can see here that our example component has changed the pre rendered method。

 so because we're getting external data via an API。

Next JS has correctly assumed that we need to use a different prere method。

 in this case it's decided to use static generation， static stack generation。

 because as we said before， this is probably the best way to do pre rendering。Now。

 what happens if we want to use server side rendering？

You can see here that this Lambda icon is used for the API Hello。

 so maybe let's try getting it working for the example component。

You can see here that Gt service side props is all you need to actually enable server side rendering。

So if we replace。Good service or。Get static props with Go service aid props。And rebuild。

You can see here that our sample component has。Use serveride rendering for its pre render method。

And yeah， that's a basic rundown of pre renderndering and nextJS。

 thank you for listening to my presentation and I hope you learned something。



![](img/ae317c542e833dc96e21b4d82bd961bf_13.png)