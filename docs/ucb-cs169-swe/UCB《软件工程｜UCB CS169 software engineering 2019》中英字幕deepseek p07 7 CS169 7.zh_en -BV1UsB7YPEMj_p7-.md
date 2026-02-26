# UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p07 7 CS169 7.zh_en -BV1UsB7YPEMj_p7-

我就是。Yeah。Yeah。Yeah。这。也就是。佢咁。还有。昨。感谢。Yeah的。过期的。Yeah。All right， so today is microcroquiz2。

 so this is on grade scopepe as microcroquiz 2， it should be open now so two questions。

 it'll take about 10 minutes and then we will get started in about 10 minutes with lecture today but。

You know。Phone or computer to answer the micro quiz。 And then when you're done。

 just please put whatever， you know， close whatever that device is。For the remainder of the quiz。

 and then we'll get started with lecture in about。10 minutes or so。



![](img/7c327a4e1df9b91adc1eb6bb87843859_1.png)

![](img/7c327a4e1df9b91adc1eb6bb87843859_2.png)

OhYeah yeah， if we just came in， the microcroquiz is on gradecope， so just open up microcroquiz2。

 it should take about five minutes， but you have about a total of 10 and then we'll get started with lecture after it。

Yeah。嗯。Si。Internet problems。嗯。Is it not letting at all。ok。It is all also just。Did。Anyone。It。

Yeah question。Yeah。So we。to take just a couple more minutes and answer the microquiz。

 And then when it closes， we'll actually go over。The questions。Al right， so the quiz。

Should be closed now。So we will go over。Question one， can if effect this thing in。

So we'll go over question one in the middle of lecture。 But question 2， So most people。Got it right。

 which is the only correct option is， is the first one。 But let's think about why。 So if I can。



![](img/7c327a4e1df9b91adc1eb6bb87843859_4.png)

Open up a new Ruby console here。Let just go ahead and paste this in。So we have a book。

And then we can do something。系咯。Yeah， so so the standards of what we have for question one， our。

 question two work as we expect we have。A question right have we have a book。

 it has a few properties， it has an author， it has a title， and it has comments。

 So my is muted my mic is muted。

![](img/7c327a4e1df9b91adc1eb6bb87843859_6.png)

Oh， that's better。 Yep， can you hear me now。So it。Can you hear me now。Now。

 it sounds like something's gonna cool， thanks。没有。So for question two。

 question one we'll cover in the middle of lecture going through things with Sinara and rails。

 but question two is all about just Ruy classes。We have a simple class that has three three possible attributes on it。

And we're going to go through each of these options here。 So let me just。Copy the text。



![](img/7c327a4e1df9b91adc1eb6bb87843859_8.png)

Get make sure we get our。Mr。 first quote。So this one is just gonna。

Be a string with some string interpolation。 that's going insert some values in there。

 And this one works， as we'd expect， we have。A title attribute that we can read， and we can。You know。

 get that value back， put in a string， do whatever we need to wh。



![](img/7c327a4e1df9b91adc1eb6bb87843859_10.png)

That title attribute。So let's go through here book dot comments。So， this is the。Be tricky one。嗯。And。



![](img/7c327a4e1df9b91adc1eb6bb87843859_12.png)

Let's see。So。Hello， we have a， we do have a property book dot comments。 We are， in this case。

 trying to add something to the array of comments。 So the。

The two ankle brackets will append to an array。And in this case。

 we get an error undefined method comments。 So why what's going on here。

 So you notice that we have an adder writer comments here。

And this is one of those things that is kind of interesting about Ruby， So if I do book dotcom。

I get the same thing。 And this makes some sense。 Actually， you know， I only defined the right method。

 which means I should only expect to be able to do book dot comments equals。

 and we can put whatever want in there。 But， you know， this is an array。 So I could do my comment。

And this will work as expected because we defined comments equals method by using adder writer。

 We replace the entire array， but we still can't append to the array。

 We can't do anything other than completely resetting the array in this case we。

And because we can't even read the array， this would actually be pretty useless as a structure for a class。

So if we wanted to do this in。The， you know。know， for something sort of quote unquote "re。

 if we had a book， I can just open up the class again。Addtter I can now just specify Add a reader。

Comments， I believe I typed that correctly， and。Book dot。So if I specify now a reader method。

 So in this case， I did add a reader just to add the book do comments method。

 I could have done de comments， you know， return at comments。

But if I go back up through my history here。And I now try and access the comments property of our or insinable of our class。

 You know， I have book dot comments。 I'm now trying to add a thing， and now it will work。

 And so the thing to remember here is that if you ever need to just replace a value。

 if you're just using add a writer， all it's going to do is set an equals method。

And it's not gonna to give you access to any of the more sort of dynamic methods that you might have for an array。

 or you're not gonna to be able to， you know， necessarily increment something。

 So if you have like a booked up price。 And you don't define a read method for that price。 you know。

 you won't be able to do something like price equals plus one or something like that。

 So that's just something to keep in mind there。

![](img/7c327a4e1df9b91adc1eb6bb87843859_14.png)

And then let's say just for complete sake， let's go over the other two options。So。Well。

 now that I defined。

![](img/7c327a4e1df9b91adc1eb6bb87843859_16.png)

The adder writer method that would or adder reader， this will now work。

 If I had not defined the reader method， this would not have worked because the。

 there was no way to just access book dot comments before I did that。 So again。

 if you just specify adder writer， all you get is the comments equals method。

 and you would not be able to do something。 like just calling book dot comments directly。

 if you have a reader method that returns the comments array。 Then this becomes you know。

 a possible option。 And finally。

![](img/7c327a4e1df9b91adc1eb6bb87843859_18.png)

Book title。

![](img/7c327a4e1df9b91adc1eb6bb87843859_20.png)

sly I have my quote close that。 So book do title equals。 So this is again。

 going to try and use a title equals method。 We specified it just at a reader。

 So there's going to be no method title equals for our book class。

 So that's those are the four options。 there is， you know， the the option 2 here was you know。

 the most people selected option  one。 option 2 was the second most selected option。

 I didn't look at the rates of the other two but。

![](img/7c327a4e1df9b91adc1eb6bb87843859_22.png)

That's just something to keep in mind that when you're working with classes， most of the time。

 you'll probably want to do an adder accessor if you are going to need to both read and write an instance of the class Que on this Ruby snippet so far。

Any questions？有。So we're going to head back over。

![](img/7c327a4e1df9b91adc1eb6bb87843859_24.png)

To slides for today。 And then we'll have a couple more clicker questions in the middle。

But so let's just get started。 So you know last Tuesday， we're talking a little bit about Sattra。

 you're gonna to get practice with Sinatra for homework 3。

 but you know this is sort of what we've seen so far， a very simple Sattra app that has some classes。

 We have a route。 And in this case， it's got some parameters in the U R I。

 We have the ability to render ERB file or an HTMLMl file we've seen we could just render strings。

 but that uses the instance variables at session。And， you know。

 the whole app has methods that handle our HP responses。 And then， you know。

 basically we can modify state with a session。 And so a session。

 as you might remember from lecture uses a cookie in the browser you can。

 there's a couple other methods in the Sinatra documentation that let you store cookies permanently。

 The session ones are temporary cookies。 But you know， this is Sinatra， we have。Classes。

 these instance variables correspond in our。And our controllers correspond to an instance variable in our view file。

 And so Sinatra does some work to make sure that those all line up。

 And that's really the way that we get data from this controller method to this view is through these instance variables。

 And so what Sinatra has given us right now is what is essentially a controller and a view file。

 And so today， what we're gonna talk about。Is how， you know。How we can extend this， the。

 the paradigms for building up a little bit more structure。 And so we have a model view controller。

 So model view controller is a bit of a fancy word。 it's， you know。

 it really is just a paradigm that at the core of it has some simple ideas for how we would separate our logic。

 So remember， we've gone through the stack of a web application。 So。MVC。

 so you'll hear the acronym MVC lot is really about how we structure our application。

 So MVC is the paradigm that rails uses， but is by no means specific to rails。 there are dozens。

 if not hundreds of other frameworks for the Web that use MVC。

 there are things like nonweb applications that use MVC as well。

 So if you've ever worked on an ios or Mac application perhaps you've taken the ios decal。

 you'll see MVC there。 and that's all client side MVC。

 but you have sort of a similar structure and presentation。 So what does MVC mean， Well。

 it means that you have three things。 you have a model a view and a controller that kind of goes without saying。

 That's why it's called that and。The idea here is that we know， we know what our views look like。

 right， They are these H T M files。 They could be Json。 They could be， you know， some representation。

 the data。 it could be for a computer。 It could be for a human， but they describe， you know。

 a sense how something should look。What we're going to talk about。

Is how we have a database so we won't get into active record really this lecture。

 but we will start to get into it next week as well。But we have a model which specifies， you know。

 a class。 essentially， if I have a book， that would be my model。 So my model is gonna say。

 I have a book。 What can I do with this book， I can get a title。 Maybe I can add comments to it。

You know， our book has authors， it might have a price。 It might have ratings。

 All those sorts of things would be models。 And then we have a controller。

 and the controller is really our intermediary in this model between in this design pattern to be to not confuse words between our controller our controller is the intermediary between our model and our view。

 And so in rails what this is going to be is it's going to give us a structure for grabbing data from our model and passing it to our view and then you know。

 structuring how we want to respond to any routes and requests。 So at a high level。

 you have three things for NBC， you have the model view and the controller and so。

Each of them has their distinct parts in Sinatra so far， we've seen mostly controllers and views。

 although our controllers are pretty， you know， are pretty lightweight in Sattra。

 So the general idea is that when we're talking about a restful application。

 each of our resources will probably have。Its own set of models， views and controllers in practice。

 you know， this is not always going to be the case。

 You might find that you don't ever write a view for some particular resource， but。You know。

 as a starting point three applications that you're working on。

 it's pretty safe to assume that each resource will have its own distinct model view and controller。

 So in this case， we have our movies app。 So you know。

 movies might be just a thing that holds information about a movie， the title， you know。

 the director， the release date， something like that。

 if we go to our movies page we'll probably get some information about that movie。

 if we have a post route that would create a new movie in our database and make a new instance of our movie model。

This one has movie goers。 So maybe we have， you know， a model that tracks who has been to the movie。

 So， you know， you could say I watched Iron Man。 and then， you know。

 that would be a new instance of a movie goers' model。

We can have you know reviews so if you add a new review for a movie that could be part of a reviews model where you would have a set of reviews and those reviews would have some data and when you ask for you know reviews slash1 or reviews slash 100 in your application you would get back some information about a particular view and so you know each of these things by default in a rails app will have three sets of。

You know， a files。 So you'll have your models， your views and your controllers。

 And what's possible in rails。 And what we'll start to see over the next two weeks is that the NBC pattern also gives us really great hooks for tying things together。

 So one thing that you'll see that we'll be able to do is we we'll be able to say a review belongs to a movie。

😊，So， you know， you might be able to go to， you know， movies to continue with the Iron Man example。

 slash Ironman or slash 100， whatever structure you're using for your URLs slash reviews。

 And that would be a view file of the reviews， but for the Iron Man movie。

 So you can structure things。 you can nest models that belong to other things。 you know。

 all sorts of structure that we'll talk about in rails， but。Henry， but the。

 the main idea here is that we have the ability to take individual routes。

  individual components decompose them to have， you know。

 so that each specific resource of our application corresponds to a specific set of concerns。

 And then in our browser， you know， we get back a view just for that kind of stuff。

 So what's going to happen is。If we go to slash movies， you know， we'll hit our movies controller。

 Maybe we go to slash reviews。 We'll hit the reviews controller。

 And rails is gonna make all of this easy so that you don't really have to think about， you know。

 when I go to this page， what controller am I hitting where you can go。You know。

 the URLs will sort of be intuitive。 So that is a high level of what MVC looks like。

 You have three things， but it's not the only application architecture。

 So this is mostly Sattra where we have a high level application controller。 So there's really。

 one controller for。For that application。 And within that one controller。

 it handles a bunch of different routes。 So ours have just been a couple get routes。

 You can do post routes。 you'll see with homework 3， you know。

 the different routes that you can make。 And each of those routes correspond to a view。 But you know。

 in Sattra， what we have not seen is any data modeling。 We have instance variables。

 we could make our own classes。 But Sattra as a lightweight framework doesn't provide that model to us。

 we have some other。Strucs。 so this one is commonly called frontron controller。 Again。

 don't worry about the specific names for a lot of things。

 But the idea here is that we could have a single app controller and introduce some models that correspond to use。

 but they don't necessarily go through。You know， there's。

 there's only one controller for the entire application， whereas an MVC。

 the idea is that there is a model of you and a controller for each specific type of resource or for as。

 you know， many of them as your app needs and。This is kind of classic PhP from the 90s。

 They are now much more modern PhP frameworks as well。

 But one of the classic ways of structuring your application was that you just had a model in a view。

 So I might define a books model that connects to the database。 and then it renders a books file。

 or Hl file or a Json file， but it doesn't have an intermediary of a controller to help structure how I might handle different routes。

 And so。You know， each of these models have their advantages in terms of， you know。

 there's one less thing maybe to worry about。 but they also have their disadvantages in that they don't necessarily promote a structure that leads to decoupling that you get with MVC。

 And so with rails， what we're gonna see is rails strongly encourages。

Authors of rails applications to follow the MVC paradigm。 like any framework。

 you can go against what the framework ask you to do。

 But your life in rails will be really easy if you stick to MVC， and including。

Ways that rails has really awesome generator functions， which will just scaffold code for you。And so。

 you know， again， you can really， you can build an application that works in any of these models。

 of course。 if you remember， you know， trying completeness， the idea that， you know。

 you don't need much to build anything with a programming language。

 Design patterns are also like this。 You know， you can solve any problem with any particular design pattern。

 but some will be better suited to particular problems than others。 And so as it turns out。

 for Saas applications， MVC is a really good paradigm。

 So we're gonna start with a clicker question and again， take once this opens。Take about a minute to。

You know， read the options yourself， and then we will。Review how people did and then talk about them。

 But first， just think amongst yourself。 So which of these is not necessarily true about MVC as a pattern。

See， so we'll take about 15 more seconds， we usually get around 60。So if we can get to 60。

 that would be cool。Also， while we are voting， someone left an eye clicker in lecture a week ago。

 I mentioned it one of the updates on Piazza， but if you are missing your eyecler and you think you lost it in this class。

 come talk to me and we will。Figure out if it's yours。Let's see。 Okay， it's two minutes。 so we will。

We'll pause that。So。There is some distribution across。A。D and E as well。 So there's a couple E's。

 So talk amongst your friends， convince them that they are either right or wrong。

And we'll come back in about 30 seconds， but。if you think it's one of the options。

 talk amongst your peers， see why you think it might be that way， if you have a question。

 ask your peers and see if they can answer a question about MVC。上去了。store。So。考得。Okay。Yeah。

It't that really。5。Aation which is please。All right， take another 30 seconds。

Keep discussing and then we'll close that at two minutes。broadband。All right。

 1 more seconds put in your votes if you can， and then we'll go through the options。Yeah。Es。点啊。

It depends on if it was in there。 But the， the Icler app is， is a piece of work。我。Yeah， yeah。

 but I doesn't。 The， the sinking mechanisms for eye clickers don't work at all。

 like you would expect them to。Yeah， it's a little bit weird。So I don't actually have access to good。

 like it saves them， but getting access to that data is weird until like you actually spend a lot of effort to sync them together。

Yeah。There are， there are opportunities if people want business opportunities for developing good clicker applications。

嗯。Okay， so we are about three minutes， but not getting too many more responses。

 So things shifted a little bit， and they went more in the B direction， so。

B is indeed the correct answer。 Well， whoops， let's not do that。We'll talk about why。

Let's go through， let's just go through these one by one。 and then we'll talk about questions。

 So all NVC apps。Or in most MVC apps controls and actions use HTUP。All right so。A is true。

 you can't really have a SAS application that doesn't use HtDP when you use a browser。

 the protocol that you're working with is HTDP。 So you know if you're delivering your application through a browser through an internet。

 you device， then you're going to be using HP as a protocol。So then B in MVC apps have both a client。

 a web server and a cloud part rails app or cloud or or cloud。 So why is B not necessarily true well。

MVC is a design pattern。 It says that you have a。Models， views and controllers。

 So you have something that responds to some requests。

 and that controller is an intermediary between some data and a presentation of that data in I mentioned at the beginning in an Ios application。

 you also have an MVC pattern as one of the main structural decisions。

 which means that you might have a controller that handles different types of requests。

 maybe that is rendering a table of data。 And so it gets。You have a controller that specifies。

 you know what， what types of things your application can do that renders views。

 which could be a table， and then your models and your application， you know。

 might be a list of songs or a list of notes or something like that。 You could also build。

An application that uses MVC that is just entirely local。

 it doesn't need to have a cloud necessarily。TheresThere's lots of ways that you can use MVC that isn't specific just to SAS applications。

 although of course in this course that's what we'll be focusing on。

Model view controllers just one of several ways to build a Sa application。 come on。 key note。

 that is， you know， exactly what， whoops， one too far。

that is exactly what's on this slide MVC is just one of several ways to build a SAS application。

 so it is the preferred array of rails， but we've been using Sinatra。

 those could be SAS applications as well， but that's not MVC and there's plenty of existing examples。

Per to peer apps could also use MVC。 So， you know， you might have a bit torrent client or something that would be a peer to peer app that gets a request。

 It has maybe a model of， you know， existing torrent connections that it might be tracking that it response to request。

 So you could have MVC in peer to peer apps。 You could really use MVC in any kind of application。

 So B for here' is the correct answer。 You don't have to have a web application to use MVC。

 but most modern web applications will be MVC questions on MVC。What we've talked about so far。

And as a reminder， if you have a question in the middle， why？Ha， that's fun。 These got duplicated。

We're just going to go through that now here we are。So。啊。

Here's the interesting part we're getting into the meat of the course。Rails。So rails。

It has been linked to in the readings。 If you've been kind of reading in the book， you know。

 the book will give you。A preview of what we're talking about。

 If you've had an internship that uses Israels， you may have seen this before， but。0 to Crud。

 So remember when we said crud， create， read， update。

 delete are sort of four of our primary database actions that we could do on on an instance or model。

 And so how do we get there。 And if someone ever tells you you're building a creditddy Re application。

 that's not a bad thing。 it means that you're following something restful。 So。

Yeah we've mentioned rails as an MVC framework， so railils of course。

 then as we would expect has models， views and controllers and the great thing about rails and one of the biggest differences compared to Sattra is not just that it's MVC。

But。The really interesting bits of rails are the pieces that help you really connect to a database that make that model layer incredibly powerful。

 so。😊，That part of rails is called active record。And we'll talk briefly about that today。

 but we'll get into that next Thursday as well and then on the subsequent homework。

 So your app is a rails app， it has a file， so rails is great。

 it follows MVC so well that it has directories that are named controllers it has directories that are named models and it has directories that are named views So as you can expect。

 your controllers go in the controllers directory， your models go in the models directory and your views go in the views directory you'll see this in pretty much every single rails app it is the default。

 it is the expectation of how you'll structure things but if you search the web hard enough you can find rails apps that do all sorts of funky things but the benefit here of rails is that the model layer is backed by really powerful tools。

callled Act record， which handles your connection to the database。

 It handles your connection to multiple different types of databases。

 It manages switching between test and development databases it does all sorts of things。

 And it provides really nice abstractions for SQL。 And so we'll get into that in the coming lectures。

 but every model in or actually， I shouldn't say every model。

 most of your models in your rails application will be tied to active record。

 although they don't necessarily have to be。😊，And so that will make your life dealing with the database really easy you know for those of you that will be working on legacy projects that will you know all be set up for you and then for those of you starting from new。

 you'll have a little bit of work but you'll hopefully get to see how easy it is for rails too。

To get things set up。 So views belong to this class action view and action view is the thing that like Sinatra will take all the instance variables from your controller and put them in a class that your that your views can render。

 And then action view also provides lots of nice things for dealing with HTMLMl。😊，Handling links。

 you know， generating content that makes your application dynamic in a way that isn't painful to write。

And controllers all belong to this application controller class。 And the nice thing is， you know。

 Ras takes advantage of object jointed principles to give you structure that， you know， you will。

Hopefully see on most of your railLs applications， and then there's also ways of nicely customizing that。

A railils app route star RB。 So this is in the config directory。

 Rails is pretty light on configuration， which makes it a great choice because you can get started pretty quickly。

 But the routes file is sort of your main piece of configuration in rails app。

 And this is the file that will specify。😊，All the places that you could go as a user in your application。

 so you know it's going to have a route for slash probably most applications have sort of a base。

 you know URL that you can access in our movies app。

 this is where we would define a resource for movies you know in grade scope。

 there is a courses route and an assignments route and submissions you know。

 all those sorts of things that you can see in。You know， you know。

 you would see those in a routes file。 and so I've mentioned gradescope since you know。

 building it I know how it works。 but it is a rails application。

 I encourage you that as you you know， sort of work through learning rails to like take a look at the URLs and gradecope。

 notice how they correspond to。😊，The things that you're learning B courses is also a Ras app。

 which has a pretty good architecture and is open source， so if you're looking through B courses。

 you can notice in URLs how you'll see things slash courses。

 slash ID maybe slash users or slash assignments， those are patterns that you'll see you know through all your rails apps and those are all defined in the routes file so。

Again， what we mentioned controllers have instance variables and those variables get sent to views。

 So that's very similar to the demos that we've seen in Sinatra so far。

 So every controller eventually renders some kind of view。 It could render a view that has no data。

 It could render a redirect it could render you some JSson。

 some HTML a P file but controller actions all end up rendering something they have an endpoint that when they finish data gets sent back to to the browser to whatever client we have do that and so。

This is what things will look like。 So we have you know a URL。 So again。

 our simple movies application and this will be rotten potatoes will be the subject of later homework assignments。

 but movie slash3 is a route in our application。 It is defined in our route RB file。

 It looks pretty simple。Rails automatically will。Based on our defined routes。

 create standard method names that we'll use throughout the course。

 so you can customize these method names because everything is customizable。

 but the most common method name perhaps for a resource is show So movies slash three we return a single view for a movie and that corresponds to the show method by default。

 you'll see that there are method names for index for update for edit that correspond to specific routes and actions。

 but so our movie controller will have a show method in this case。

 this is something you'll see so often that you'll probably extract some logic to handle some of this for you。

 but all we're going to do is we're going to look for the I in the URL。

 So in that case three we're going to use our model。

 So our models are a class which has sort of the same name and so you'll notice。

As we're going through this， all our names are pretty consistent。

 you our route has movies in the URL。Our model name is also movies。

 This file is the movies controller。 And so you know we do movie find by ID D。

 and we store this in an instance variable and if we don't specify a render called directly rails because it has a strong set of conventions。

 we'll automatically find in our views folder movies slash show and it will render the show file but we'll see some of that next。

 And so this is what our show file might look like this is pretty basic you in the real world。

 these would be quite a bit more complex but。Even without specifying a line that says render show or render my file to HTML in Sinacho we had to say you know ERB hello or whatever a file name was railils will say okay I know this is a movie I know where the files in my application for movies belong so I'm going to just pull that data in for you and the great thing is this reduces code and it makes it easy that as long as you file follow rails conventions。

 you pretty much don't have to do anything in terms of setting up the structure of your application railils helps you do that for you。

 it answers all the questions of like what should I name this thing where should it go and you get to spend your time on the interesting bits you the interesting bits are what should my application actually do how should I architect my routes what should the design and functionality be？

And ultimately， because you don't have a ton of time in this course。

 the great thing here is that by having a strong set of conventions。

 rails answers a lot of questions that means you could spend time building customer features。

 because I can promise you your customer doesn't actually care what you name your files in your repository they will potentially never even look at your repository。

 although some of them may，But the idea here with conventions is that if we follow these conventions。

 we have， you know we don't have to have a set of configuration。 If you look at the Rails apps。

 So this will be linked on Gitthub， but most of the course projects are on the Gitthub repository SaSbook and you could look through past projects that your peers have built some of them may have built them three or four years ago。

 some of them you were built just last semester， but you'll be able to open one of those applications and you'll see a very similar structure And the great thing is as you move from Rasap Rails app if you're going to have career and software engineering。

You'll start to， you know， those conventions will just become internalized and you don't have to read through and learn a new app structure each time。

 And Ras does a whole bunch of really cool things。 So in our database。

 each model corresponds to you know a database table。 So we have a movie。

 that means we have a table called movies。 we have a movie controller and our model name is movie because generally we'll be working on a single instance of that and so。

When we work on things with rails， it will handle all the nice stuff。

 like knowing when to pluralize or not some item。 And so， you know。

 it will follow the convention for all these things。 And the great thing with there is that。😊。

You know。With with these features， what railils is doing is really just taking advantage of ruby features。

 So if there's anything that you do need to customize， you have the ability。

 And so just to demo something。

![](img/7c327a4e1df9b91adc1eb6bb87843859_26.png)

诶。Really really quickly， and let's clear this。We have this book， right， it has some stuff。This is。

 you know， we could， this is not rails right now。 This is just pure Ruby。

 but we have a class name book。 If I wanted to pretend to be rails， I could do something like this。

 So what is the class name of this object that is a book。 Well， in Ruby。

 there is just a class method on every instance of a class。

 And so this actually gives me back a class with the word book。 So this is the name of my class。

In rails， I mentioned that， you know the。呃。Excuse me， the movie， you know。

 instance would correspond to a table that was named。With an pluralized version。

 so this would not be the actual way of doing this。Did what did I。What am I doing？So， you know。If I。

 if I just do some string interpolation， I can， you know， make this be books and， and I believe。诶。

Yeah， so。Rils is going to do something like this。 It's going to take your ruby classes。

 It's going to say what is the actual name of this class， I'm going to mess with it。

 and then I'm going make it plural。 Of course what I did I knew that adding an s to books is the proper way of pluralizing it railils is incredibly clever so it has this whole class called inflections that you can specify your own pluralization rules if you need to。

 but it actually knows that if you have a model called person that your database table should actually be named people it does not give you back persons。

 it does not give you back peoples， it is incredibly smart and if you ever need to customize things。

 you can specify your own rules。 So if you somehow want your database table to be Mos instead of mice。

 you can choose to do that although there's very little reason but rails will be smart and what what it gives you so that。

系。It understands English， at least very well。 and there's maybe some minimal support for other languages。

 but in terms of English variable names and object names， it's going to do the right thing。

 So all these features are really available in Ruby as a language you don't need to necessarily know how the class method works or how rails is going to implement this stuff。

 But the point being that you you have access to all the same tools that rails does。

 should you want to do something clever。 So this is generally falls under the feature of introspection。

 So that means a language has the ability to look inside its own self while it's running and decide you know what's going on and make decisions based on that so。



![](img/7c327a4e1df9b91adc1eb6bb87843859_28.png)

Ruby as the language is pretty powerful and rails takes advantage of that power。

 So another clicker question， if we open it up here。诶。You know， why must our controllers render？

Eventually have something be rendered。All right， things seem to be stabilizing。

We have a pretty good distribution of answers this time。

Talk amongst yourselves for a minute or so and see what your peers think。

 and then we'll go ahead again and review these so I'll open it back up， but take about a minute。

 minute and a half and decide why rails must eventually render something from a controller action。

I can promise you that something will be rendered。表件。我。Very。上ま。ましだ。佢要人啦。睇睇系。哇。这段来的。그。系。使佢。Thanks。

来是就是。It make every time I。Okay。All right， take about 15 more seconds and。Putting your votes。人民出施。

All right， let's see if we can get it in another 10 or so votes。That's true。 It's true。Okay。バンスです。

Let's close it out。So this is pretty interesting。So we moved in the direction of C。

 That is interesting。 So does someone want to argue。Does someone want to argue for C or for actually。

 does anyone want to argue for any of these answers why they think it might be。A good option。

 We could start with C， since that's what most people pick。

 but if you want to argue for another answer， then we can talk about that as well。

Anyone want to take a stab at something。right， yeah， in the back。Oh， that was a terrible throw。

It did not do that high enough。 Luckily though， that thing is pretty squishy。

You have complete freedom to make fun of me for the rest of the semester for that。Yeah。Yeah。

 so I don't really have an answer among the four。 but I have seen patterns where rails apps just。

 you know return Json objects like in case of a policyqui。

 So I guess none of these would work So returning a Json object is still rendering something。

 its when you know， when you do a post。 So in rails that commonly corresponds to a method that in your controllers will be named create。

 if it is returning some Json data， it is still rendering that data。 how it renders that data。

 maybe a little bit different depending on the structure of your application。

 in the sense that you could actually have a file in your views folder called create dot Json。

 which will correspond to a Json view for the create method。

 it might just be that you put a hash in rails。 turns that into Json for you。

 because rails is a lot of nice things。 but。All that counts as rendering some data because the。

 the server， in this case， Ras is taking that data and sending a response back to the client。

 So I would say that that's definitely a case where data still rendered， but good question， too。

 So that's a good theory。 What else like why else might might we， or might rails do。

To render something or why else we might have to render a response。Any other takers？

One of these answers is definitely true。Any other take us for why rails might render a response or why it has to render a response。

Sure in the front。 or we want to pass the mic。Ft。S。But well。

 doesn't rails have its own subjectories that are like models you using controllers。

 So it kind of assumes that you're already using MVC if you're using rails。 Yeah， yeah。

 so rails assumes you're using MVC。 are you。Do you want to make a specific case for C or you just Oh yes。

 since Ras kind of assumes you use MVC。 And well， I mean， it's kind of in the answer there Yeah。

 Yeah， so let's let's go back to this。 C is a very logical option。Oh what did I make a new oh。

 I did not mean to open that。 Let's go。Back and people just voting randomly。

 That was an accidental question。 Okay， so the correct answer in this case is B。 C。

 So let's talk about this。So。呃。So rails does follow MVC conventions。

 That is entirely a correct statement in your applications。

Most of the data that gets returned back to by or returned by the server will come from you know a file that is in your views directory。

 but it is not the NVC fact that means that rails has to return a response。

 The reason that rails has to return and render a response is because HTDP requires that you reply back to the client。

Yes。Can， can， can't you have like a reals app that is like just like local on your machine， though。

 so。In that case， if a Ras app is local on your machine and you you open a website with like local hosts。

 the only way to interface with a rails application is through HP。 So even if it's on your machine。

That is a good distinction。😊，That， you know， it might not be an Internet connected application。

 It might be talking to。Other， you know， other clients that are other servers and not necessarily a user。

 But the， the mechanism that Rails is using is going to be H T U P。

 And so this is handled in Sinatra。 we saw a little bit of the rack interface。

 So rack is the piece of the stack in rails that handles。Handling， parsing。

 messing with all the HP requests。 And so if rails were never to send a response， the client。

 which could be a user in a red browser， it could be someone using curl。

 it could be another API server making a request to your application， if rails never sent a response。

 that client would be just waiting there forever。 and would probably eventually give up because you know。

 no computer actually since they're waiting forever。

 But the fact that HB is a request request reply protocol that is shocking and hard to say。

Is the reason that we have to return a response。 And so。

There are a lot of ways to return responses in rails。

 So JSOson as a result of a post request is you know， a good option。

 An Hl file is a good option you know， just putting some text in you know if you just render some plain text back is an option the other option that you will see which you know railils sort of nicely has a helper for this is redirecting to another page is also rendering a HP reply。

 So if， you know Rails will give you a really nice method that says redirect to and it will tell the browser you know hey I'm going send the user to a new page。

 but you can also manually just decide to you know render any HP status code with any text as the result。

 So B is the correct answer there。 And then。Not many not many people picked D， but using Ajax。

 So making a call via jascript， your web application might not display that data to the user。

 It might make an Ajax request that returns。You know。

 where the server returns some data and the application front end doesn't display it。

 but the server in this case is actually returning some data as well。

 and I forget the specific response code I believe it is 204。

 but there is a specific HP response code which is a successful response that says you know no content is is the meaning of that response code So you and a rails application might choose to you know say render colon。

 no content as the symbol name and rails will actually translate that into a defined response that means I'm sending something back to the client but there is no content there that could be a redirect that could be something else。

Questions on sort of HP rails replies。 Yeah in the middle back there。Okay。Well， actually。

 so I want the question to be on the webcast for people。 So yeah。Yeah。

 so when you say that every interaction with the rails app needs something to be rendered。 Yeah。

 doesn't that mean that whatever response you give back is being rendered by the browser。

 So there's some like visual output。 No， so render in this case doesn't need to be visual output。

 render means the server is going through and generating a response that could look like anything。

 So in rails， the actual method name is render。 but what that render method does could return lots of different data that could be rendering an XMl file。

 So this is a piece of gradecope and B courses that you probably don't use as a student but a really common thing is if you have a table of results。

 So like in this case， grades you might have an action where the rendered results is an Excel file。

 And so that file gets dynamically built returned and then the browser just downloads。

But the server got a response or got a request for some data。

 and what it rendered was a file that the browser doesn't display。

 but some other kind of client would。So， so that's like， that's still rendering some data。

 If it's Json， there's a million in one ways to actually build Json structures in rails。

 But that's why I would render that。 Yeah， and then a question in the front here。 last question。

 but please， so we can hear the final of question。 just just to clarify。 So in this case。

 rendering is just a response from the rails app。 Yeah， any response。

 Any response from the rails app is rendering something。 So there actual。Just。

 just for like 30 seconds， guys。right， the， the last。Yeah， the final thing today。 So yeah。

 if in rails， any type of response counts as rendering something。

 what rails is going to do is build that response in some way。 It might be an HTML file。

 That's the most typical thing， but it could go through any type of processor to render that response。

 It could be a Json processor。 It could just be some content that's in line。

 but that all counts as rendering something。All right， so we'll end it there for today。

 Tuesday will be a guest lecture with past TAs and students about their experiences as industry and how this relates to this course。

 and then Thursday will be active record。

![](img/7c327a4e1df9b91adc1eb6bb87843859_30.png)