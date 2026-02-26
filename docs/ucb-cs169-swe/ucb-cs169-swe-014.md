# 014：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p14 14 CS169 14.zh_en -BV1UsB7YPEMj_p14-

Y'all don't belong here。真明白。I can get that。No， what， what room are you looking for？

OhThe wasaz is one level up and at the end of the hallway。Did you change it。No。

 this is course that's scheduled all semester in here。This is HP auditudorium。So that as it was。

I'm sorry， weird。Upstairs on the fourth floor and at the end of the hallway。家咩。Not a problem。Yep。

Yeah。Cool， let's move this thing out of the way。All right， well， there is a micro quiz today。

 not a lot of people that are here。 so fun for them。 Before we start the microquiz。

 just some a couple fun birthday history things so。😊。

This year is apparently the 50th anniversary of Uniix The exact date is not really sort of known like many softwareer projects。

 you know they evolve or over time， but in the story so there's two pieces there's one from Bell Labs where the creators of Uniix worked and they have sort of a ceremonial piece and then there's a more interesting article from。

😊，About six weeks ago on our Technco。But one of the cool things is in the history of computing。

 since obviously Berkeley has its place。The founders or the critters of Uniuchix can。

Ken Thompson and Dennis Ritchie， a couple of them actually went out to Berkeley during the time that they spent like a first few weeks of developing their early versions of UniX in 1969。

 so they actually took a trip out here， kind of unrelated but just another thing in the history of computing that ended up happening at Berkeley and then of course later in the '80s and '90s。

 there' was this thing called the Berkeley softwarefter distribution which is a version of UniX where that software lives on。

Well， there's versions of it that live on every Mac and most versions of Linux as well。

 which also means things like your iPhones and iPads。 So a long history of Uni there。

 And then less long history。 But perhaps more interesting and fun。 this is apparently today。

 But comic Sans turns 25 years old。😊，Comic Sand is a really interesting story。

 besides the fact that it is the thing that everyone wants to hate on， which is。

Why this medium post by Microsoft is why we love to hate comic Sans。

The other really cool thing about comic sands， though。

 from just like a computing history perspective， is that it was designed to be sort of a playful。

 readable font。 It turns out to be a really useful tool for people with dyslexia。

 So if you have dyslexia， the sort of style of handwriting the difference in the characters。

 which we might find sort of unpleasing and in poor taste， if you are design critic。

 mean that if you have dyslexia， It's an actual advantage in terms of being able to distinguish letters from one another。

 so。😊，Those are a couple cool pieces of history and so the microquiz it should take about 10 minutes。

 it should be up now in gradecope there is a password this time so if you don't get question one right you can't get any points in the microquiz。

And don't text your friends， even if they pay you like 100 bucks。

 I really hope no one's offering that much money。But。

Point being that you're supposed to take them in class。 So there's a， there's a password。

 It's active record， a lowercase， although it shouldn't actually matter how you type it， but。Yeah。

 password is active record， and then it's three multiple choice questions。嗯。Thanks。I mean。

 they're not even worth that many points， but you know。Yeah。对反应。嗯。Its。嗯。といって。Yeah。

Sometimes I use the micro symbolymal and sometimes I don't。Okay。😔，Yeah。All。

 the microquiz will close in about two minutes at 955， so if you're still working on it。

You want to get credit for being here， just submit something， but yeah。

And we'll go over the answers after it closes。なんだよ。All right， it should be closed about now。



![](img/cec59051d50a9267f627797e1dc8713b_1.png)

あ。Yeah， that's fine。Okay， how to not。There we go。So I'll go ahead and publish these after class as well。

Let's just go through these。A few questions about testing。Stment that's not true。

 most people got this one right， but it is impossible to achieve 100% test coverage。And。

 you can achieve 100% test coverage by certain tools。

 but it's impossible to use that to ensure that an implementation is correct。

What's it mean and I test this？Yeah， okay yeah， test that's outlived its useful。

 that's a good question。So whenever you adapt a software project over time。

 the requirements may change。 So a test that sort of outlived its usefulness could be a test that。

It like is functionally is just duplicated in multiple places。

 So maybe you wrote an initial like cucumber steps and then you rewrite a feature a feature and then that that step is now or is now duplicated by a similar set of features or another file。

 And so if you have just literally something that's duplicated in multiple places。

That could be one place where going through and actually cleaning up the tests is a useful step。

 It's one that's often forgotten because if you are just in a mode of sort of adding code and you look at like a pull request。

 it's easy to sort of miss that stuff。 Another place where tests really outlive their usefulness is if you're adapting features in an application and you're sort of softly deprecating some functionality where maybe you're not deleting that code yet。

 but you're not intending to support it， it can be useful to just like remove a test case if you say like I no longer care about this piece of the application。

 Other things that happen。Maybe not specifically related to。Test cases。

 but sort of just in the spirit of like cleaning up your testing setup。

 a lot of applications will have fixtures or factories that are in use that don't represent sort of the current and accurate state of data。

 so if you've updated your data model over time or you have a bunch of sort of craft in your test setup that can be things to clean up over time now that's not always bad to have if you have like some legacy features that you still need to intend to support。

 you want to make sure you have that coverage in your test cases。

 but it kind of depends on what what you might be going for in your application。

So this is the one that was， at least by statistics， the hardest question。

Ruby hackcker creates a controller action that responds to an Aject request producing a JSON response。

She and Railsapp are discussing what tools and tests they must use to test the controller action。

 so we have a few options here， they can use an option like fakeakeWeb or webmock or any other library to stub out the server response。

They could use jasmine to test it from JavaScript。They could use R specEC or they could use cucumber。

 so why is R specEC test the best thing here？In this case。It's a controller action。

 and so separating out just checking the response。You could。Yeah， so in this case。

 with controller actions， you generally want to spec them out at an R spec level。

Of picking a single option， this probably would have been better as a multiple select question which that may have been a bug in the way the question was formatted stubing things out is also should be a correct answer here。

 so that may have been a formatting question issue。

 but you'll get credit for both answers but credit really doesn't matter as much as participation does on these things as well。

Yeah， so this one should be A and D， and actually let me just go ahead。And tweak that right now。

Because。No。All right， I'll save that in a second。Yeah， so this one。For Rails app should be A and C。

 you'll get credit for both， the credit Sc interface doesn't show it。

 but I know that it actually works correctly。There are advantages to knowing the implementation of software。

 even when you。hi。The UI doesn't always show things。 So the last question。

 and I'll go ahead to later today and also add explanations for these so you can review them later。

The last question is， Sally is writing an additional test case。

And she's trying to decide try to she wants to create a dating website。

 decides to write an algorithm that takes a list of male and female user preferences and returns the best matching to test her algorithm she calculates the best match。

 She wants the algorithm and checks the output as desired。

 So what of our testing principles is her method not following so。

Remember that we have these first testing principles， which in this case。

 you don't have to have them memorized because they're all written there as options， fast。

 independent， repeatable self-checking and timely。 so her test case is good the main thing that it's violating this case is self-cheing and that she is manually going through and doing the work。

 you could also argue that it's not fast depending on how good she is at mental math。

 they're running through code or if she wrote another script to do the checking maybe this process could be fast。

 but based on the information here， what we do know is that it for sure is not a self-cheing test and again。

 with our first principles， there is going to be need for manual QA。

 but when we want a set of automated tests for those to be useful you'll notice when you use get into using Travis CI with your projects。

A test that can't report to whether or not it passes or fails is not very good as feedback in an automated build。

TheThe issue here is that this test is not self checking， and it probably is also not fast。

 but we don't necessarily know that given the information that set up。



![](img/cec59051d50a9267f627797e1dc8713b_3.png)

呃。So that is the microquiz for today。So what's this week going to look like so today are tools that Rails gives us on the database side。

 so we're going to talk about active record， we're going to talk about a little bit of what it will do with the database that you're using and the great thing is for active record。

It is a framework which is independent of the actual database。That your application is using。

 So this is not something that happens very often， but in theory， with active record。

You can totally switch out your production database。

From MySQL to Postgres or vice versa and your code should still work for most of your projects。

 you'll be using SQL light on your development machines because it's fast and easy to install it's fast for local development at least or fast enough and on Heroku you'll be using Postgress because they have it all set up and for production applications that's better。

 but the really nice thing is active record provides us a bunch of tools that interact with just about any database and the way that we're gonna to explore things is in the model of having good code reuse being clear of sort of what the intentions of our applications should be doing。

Thursday we'll continue with some stuff on associations and later we'll talk specifically about what those mean and then'll look at legacy codes so for those of you who are working on legacy projects you'll get a bunch of experience with that throughout the semester for those of you who have newer projects you won't get as much handson experience。

 but the lectures then will be sort of content that's useful we don't have these videos up yet they'll be linked to on B courses later this week we'll post on Piazza when they're actually up but content that we're not covering in lecture but is useful and interesting and sort of helpful for your projects。

Additional screencasts on drying out rails， so that relates to some of the stuff today。

More information on associations that's going to be later this week and then also exploringing codebase。

 So just same stuff that we're talking about in lecture， but more in depth， you more detail。

 which is good study material， good background for your projects。

 and then also if you are curious to see the list of past projects that CS169 students have done。

 there is a wide range。 So you at this point hopefully know the project that you're working on。

 if you don't， there's some other issues going on there。

 but projects do saasclass org has the list of example projects from the past few semesters so。嗯。

These slides have a graphical representation of what each iteration looks like。

 I do know that the second half of the syllabus。 the dates are still messed up。

 The ordering is correct， but the dates need to be changed。

 But basically the way that this works is your first week。 So we are in we're going to be sort of。

We're sort of in the second now the first week of iteration one finishing up iteration zero stuff。

 which is its own special case， but the normal schedule is going to be that you have a customer meeting that starts off the iteration when you're done with iteration one。

 you'll have a retrospective meeting and this is with a customer， this is just with your team so。

Two sort of meetings with your team， which is， you know。

 what are we going to do this week and then the retro meeting is what happened， how did that go。

 this is a great time to as a team ask yourself， you know。Do we think this went well。

 did we accomplish what we wanted to， what might we change for these upcoming two weeks if you are switching roles as product owners。

 which we are encouraging you all to do。Now would be a good time to sort of talk about that process。

 hand things off GSI meeting。In sections meeting with your GSI， they'll give you feedback， review。

 any code， any questions， tracker updates， things like that。

And then you should have a final meeting with your team to that definitely has to happen after the customer meeting of planning out the stories and the work that you'll be doing in that meeting is where you would be tending to tracker。

 moving your stories around， all that kind of stuff。

The only really hard constraint on order is that the iteration planning meeting has to happen after the customer meeting since to plan your work。

 you have to have feedback from the customer as to what's important。

 But within your sort of team meeting cycle， as long as you're meeting the due dates。

 then you could sort of schedule。around your team's needs。Week two。Coding and if standups。

 we will be adding everyone to Slack very soon and there will be some tools in there that help you sort of。

Go through some of this process。 We are encouraging everyone to use the ones that we set up。

 but you don't have to use them。And we'll post notes and links on Piazza about how those work when they're set up。

 It's a bit of a process to add 100 people to these tools， some of which has to be done manually。

That will get fixed at some point， but those will be available to you。

 and then the self assessment survey is just。That one is one that you will do individually。

 which is how did I do， how did my teammates do that will be private feedback to me and your GSI so hopefully no one has complaints about their project partners invariably something will probably happen。

 but that will be a place for that kind of stuff。嗯。

So this kind of lays out a visual flow for how these meetings might work。

We're not going to go through all of it， but in general， the dates will be on here for reference。

 So we're going to try and stick to the same sort of types of deadlines， so。

Wednesdays of week one for customer meetings， So a day after section， again。

 if you have an issue meeting with a customer particular week。

 talk to your JI or post a private note in piazza。 and as long as you have made effort to meet with the customer。

And schedule something。 that's really what we're looking for。

 But you really can't be pushing that meeting back too often。

 because if you don't have that meeting at some point in the first week。

 you won't have much to go on for the second week。 And we do recognize。

 especially when you're working with external customers that you're sort of at their mercy as well。

 So you're not going to be penalized you know， for things that。

They might not do or if they can't schedule something at the right time。

 but you will be expected to make effort and contact them and set up meeting notes and all that kind of stuff。

Iteration planning meetings。 those are gonna gonna be due at the beginning of week 2。

 I highly encourage you to have them you know， at the end of the first week， if possible。

 so that you at least have， if it's helpful the weekend to start coding since that maybe。😊。

 more productive in your schedule， just you know， the sooner that you could push this stuff up on your own team。

 the better that just gives you more freedom and flexibility in terms of doing the coding。呃。

After an iteration you'll have some assessments due for the previous iteration so week three is already the start of the next iteration。

 but it's sort of wrap up work for the past one so week three of iteration one is also week one iteration2 and then that includes self-assessment retros and so on。

 so this is a reference here but the dates will also all be on B courses and we'll post announcements on PiLs as well。

So getting into the meat of today's lecture。Validations and action filters。

 so drawing out model view controller。One thing that is really common in our applications is we have these things that are called cross cutting concerns。

Crosscutting concerns are features specifications that would appear in multiple places in our application。

 So a really common example here is we have a movie title。

 we might have some restrictions that says a movie title cannot be more than 40 characters。

 we might have something depending on the nature of your application。

 this may be more or less complex。 but when a user signs up。

 they have to enter their birthday and they have to be older than 13。

 which is a legal requirement for most。Commercial applications。😊。

That one actually doesn't apply to most of these projects， but it could potentially， you know。

 you might have something about the restrictions of names。

 So we could go through a code base and say every time， you know。

 every possible way that a user could sign up， we'd have to check the thing Every possible place that we could update the title of a movie。

We could write a check to make sure that the titles valid。 And while your applications are small。

 you know， writing something like this in the controller may seem reasonable。

 There's only one controller action that handles this update。 It's easy enough。 But after time。

 as as your applications grow， movies might get updated in more than one place。

 You might have Ajax calls。 You might have different kinds of associations that change things so。

The goal is to say， what's one place where I can describe this feature that says a movie title can't be more than 40 characters and where do I put that soap？

U。There is this idea called aspect oriented programming， and it's。

It's idea to use a specific piece of code that implements a concern that's cross cutting。

 So basically， the idea is we're going to put some code in one spot and it's going to be injected called wherever it wherever that piece of code should be running。

 So the framework in this case。 Rails is what's going to help us inject that code in the right spots and call it。

And call it for us。 So the word aspect is just advice plus point cut。

 which is an interesting description。 That's the definition again， not the most important piece。

 but the idea here that we're gonna take some logic。

 put it in one place Ras is then going to help us call that logic at all the right spots。

 And so the goal again is so that we dry our code。 And if you don't remember from the previous lectures。

 dry stands for don't repeat yourself。 So giving us one's place to describe one feature。And so。

What does this look like in practice？We have models and rails， they live in our models directory。

 so to continue with our movie example， we have a movie model。So features that apply to a movie。

 things like the title must be less than 40 characters。

This is something that we would say describe goes on our model these are validations on the data so where in rails will we put these in well rails gives us a really handy method called validateates we briefly describe this a couple weeks ago this was of course a question in the midterm which you will get back later this week。

And。The idea with the validateates method is it is a way of saying to rails that I have some type of data constraint that I want to be enforced whenever a movie is created or updated。

 And by specifying it in one place。Whenever you create or update a movie in whatever part of your rails application。

 Ras is going to handle this work， so in this case we have two validations here。

So the way that there's a bunch of different ways to write rails validations。

 we'll see the format that we described in the midterm。This one is a simplified format。

Which is probably a little bit more common， but this takes an attribute， so our title，Psence true。Is。

A shortcut that says this thing is required to be present whenever we save or update。Our data。

 And this prevents things from being nil。 I believe it also prevents the empty string。

 but you would probably want to check on that。Normally you don't really want empty string data。

 but you might for some reason。 And then we have an attribute called length。

 And it has a couple properties。 So length is just part of the rails validations API。

 it has properties that are maximum and minimum。 if you want to specify minimum length。

 but we say length。 maximumum 40 rails gives us all the stuff。 we just have to learn how to use it。

 So that's really handy in one line， we specify that we are validating the title of our movie that it is no more than 40 characters and we'll see in a second what rails is gonna do。

 but essentially everywhere that we could change that title。Rils is going run this check。

 We have a second one that a release date is present。

 and in another example will work on updating this。

 So this is a way similar example to what we use in the midterm。

 You can create your own custom validations。 So these take in the method name。

And you define your own method。 So this is all in our movie model。This case released 1930 or later。

 And the way that these validations work， if this method returns nil or returns true or really anything。

 the validation passes， if an error is added to our model class or object， excuse me， another class。

 if an errors is added to the model object， then the validation fails。

 So whenever there are errors present the validation fails。

 And the reason for that is so that you could have multiple errors returned at once so that in a rails model。

 you could be you could have a validation that adds errors for a bad release date。

 you could have a validation that adds errors for missing the title And so if a user。You know。

 just saves an empty form。 They would see all the errors present at once and not just one at a time。

 In this case， this is written in a single line of ruby。

 So it's indented to hint that it would be one single statement， which is。

Add an error for the release date must be 1930 or later。If the release date is present。

 so this is just saying if this is here and if the release date is before a certain date。

 so this is saying that we're not going to accept movies released before 1930 because this is the restriction in a database。

Or whatever application feature we have， but basically this is just a ruby feature where you can write statement。

 if condition and the statement on the left side of our if only runs。

If the condition on the right is true， so it just sort of inverts the order。

 but it works the same way that a normal， if statement would。

We can extend these again to write all sorts of additional custom validations。

 so one of the examples that we've used in past descriptions。

 is's the fact that the PG13 movie rating was introduced only in 1972。And so。Or excuse me。

 this one is ratings in general were only introduced in 1972， the PG13 case comes later。

But we could add a second validation that the rating。

That a release date is only or a rating is only required if the release date is after 1972。

There's a really additional handy thing that you'll see here inclusion in rating。

 this says this value rating has to be one of the values that I specify up here this percent W syntax is really handy ruby this just turns strings a set of white space delimited strings into an array of strings so you don't have to put single quotes and commas around things you just do percent W and a delimiter which could be curly braces。

 it could be a vertical pipe， it could actually be an array character ruby syntax is pretty wild。

 it's very forgiving but that's just a handy ruby feature。And so if we write。

Unless grandfathered than in this rating validation， it will call that method。 and so。

Unless is the same as if not。 So that is a Ruy keyword that you can just translate to。 if not。

 Some people love it。 Some people hate it。Your choice as to how you want to write。

Your you know your own code， but unless is an option here that says only do this thing if this thing is not true。

 so unless grandfathered if not grandfathered， you could choose to write if and invert your condition but up to you in terms of that code so。

That's how you write validations at a very high level。

 you have a keyword or a function called validateates， you pass in the arguments。

 and what is rails as a framework going to do？Well。Every time you go through and access a model。

 save， update a model， railils has a bunch of steps that it goes through。 And for the most part。

All this code is configurable to your application， but in most cases you probably don't need to mess with it。

 but you can see on this list， we do things like before validation。

 before validate on update before validate on create。

 so rails gives you the hooks and tools to really customize the entirety out of this process of going through making and making or're updating an object。

 you can separate， create an update if you need to for the most part you probably won't。

 but it's available to you。And so after we Ras runs。

 it's before validate callbacks or hooks you can call them， it runs the validations。

 and then depending on the results of those validates validations。

 it will run some additional methods that you could pass in。For the most part。

 you're not going to need to worry about specifying before and after validate。

Functions or customizing that behavior。 But it is available to you。

 So every time we see movie do create rails is going to run through all these steps when it gets to the validation section。

 it's going to go through every single validation that you've defined in your model。

 Run all that code。 If there are no errors returned。

 It saves it to the database if there are errors returned depending on what you do in your application。

 It may display those， it may raise an error that's up to you to decide and it does the same thing for updates。

 So rails gives you a bunch of hooks。 The main thing is in the middle of all of those。

 It will always run your validations for you and you don't have to worry about where that happens where you call movie do update movie dot create。

😊，嗯。And so。Yeah， if things fail they fail when errors which is an object。

 it's basically an array of possible error messages。

 although it's a little more complicated than that。

 but if theres ever more than if there's one and more errors。

 then your validation is said to have failed and Ruby or rails will not persist that object to the database。

 so validations are really handy tool if you have a legacy project there will likely be some created and you should have seen a couple of experiments or a couple examples in homework assignments。

 questions on validations so far before we go to controller filters。

 which are another handy tool for drying out code yeah。The code that is。

Where you would have to update。This code or the steps here。Yeah。Pretty much。

 so if you have a validation on object， so in this case， a movie。

Then where you only need to define it once in the model。

 so wherever you create or update those validations will get run rails。

 because it gives you a ton of flexibility， does give you specific methods that you can use that will skip validations。

 so there are certain ways of you could say when I save this this particular instance of a movie don't run the validations and that's sometimes useful but for the most part。

Wherever you do Mo。ave， Mo。create， those validations will always get run and it doesn't matter whether you do that in a controller。

 whether you do that from another model。If you have any background processing。

 so tasks that happen asynchronously。You know， your validations will get run in that scenario as well if you have any library code。

Excuse me， whatever。wherever you make that call to Mo。ave， Mo。 updatedate。

 your validations will get run and the active record documentation lists any methods that will skip validations if you have a need to。

 for whatever reason， skip a validation， so it's possible to skip them， but for the most part。

 it is automatic everywhere。You would update things Yeah， another question。啦，呢啲。

the whole table like can you。有哋先。Yes。Yeah， so there is a。

There's an attribute to a hash key for a parameter that it' unique true。

 so that's probably the easiest way。 the other common way to validate uniqueness at the database level is to use a database index so your database will enforce that and rails makes it very easy to add them。

Especially modern versions。 The other thing is， if you're defining a custom validation。 So you know。

 method here， released 1930 or later， our grandfathered method。

 these methods are normal ruby methods。 So they have access to do whatever they want to。

 So you could say， you know， movie dot all。I don't。

 Maybe you have a wacky constraint that says the sum of my release date years cannot be greater than 100000。

 Don't really know why you do that because you couldn't have any movies。

 but you could do something that says like movies dot all some of these release dates and fail for some additional constraint。

Performance wise， you， if you're checking your entire database on every single save and you have millions of objects。

 it might be slow， but rails will let you do that。So yeah， you can uniqueness though。

 is the easiest thing to do when you just。Provide the correct attribute and I believe it's just unique true。

 but it's in the documentation。For that one。But yeah， anything else that you want to do。

 you have free range in custom functions。Yeah， good question。

Uniqueness is definitely a common thing that you would probably want to validate。

Other questions on validations so far。It's one in the middle？Cool。

And we'll have a couple clicker questions in a second as well。

 So validations so far have applied to our models。 So our movie model data that applies to a movie。

The next thing that we'll look at are controller filters。

Controller filters are a tool that do some before or after processing for actions on our controller。

So。There's there's before filters。 So before we render something or before we even sort of get into our show method or our create method。

 we can run some action and we'll see the most common example of this in a second。

 there are also after filters。 So after we have run this action。

 you can run some additional checks or perform any additional actions as well。So。

These are some of the two most common filters。Or actions。

 So depending on the version of rails that you're using， they used to be called before filters。

 they are now called before action in modern versions of rails。

 So you may need to look at your specific version of rails and the documentation to see which exact keyword。

 they behave the same way。 So if you see before filter before action they do the same thing。

 It just depends on which version of rails。But before action is the most current version。

 which is also to say， it hasn't changed in Ra 6， as far as I'm aware。

 But who knows what the future may hold， we could come up with a new term。 So we have an。

A user or a sessions controller， so this is something that would be for logging in。

This inherits from our application controller。 so it's something that is in sort of the normal setup of our application。

 and we define a before action set current user。 So this set current user action is going to be run before every single method that is in our sessions controller。

 So before show before index， before create， update， etc ceter。And。

Oh we define what this method is below。So set current user。

 it's going to check for the instance of a current user if it's not present， so or equals is。

Ruby syntax feature， so if this is already set， it would return current user if not。

It's going to sayMogoerfin by session ID， so if there is a session ID。

 make sure that we have the current user for this request。And if the current user is not present。

 it will redirect them to the login page。So this is one form of a before action。

 a before filter that almost every rails application has at some level。

 which is to say in one place I want to declare that a user is always logged in if they are not logged in。

 I want to redirect them to the login page and the method for you finding and setting that user instance variable may vary by application。

 but user dot find by moviegoer do find by in this case。

 it would be a lot clear in this application if we just call them users。

 but that's neither here nor there， you moviegoer do find by session ID。

 so this means that we are storing the session ID in our moviegoers's table。

And we are setting the user for that request。 So this is a really common pattern。

 And the great thing is， with just a bit of syntax， we can say。😊，Before every action。

 make sure that someone is logged in and what you might be thinking is， well。

 if we do it before every single action， you know， you like how do you get to the login page if you need to be logged in to get to the login page that would that would be a little bit unfortunate。

 we can say accept login so accept any particular methods or routes we could accept from a filter we have the option to say only so maybe there's。

only one specific page that you need people to be logged in for， depending on your application。

 there's a whole host of control here， you can say if and write a custom function you could say unless and write a different function。

 it rails gives you all the tools that you might need the other really awesome thing about before filters is they take full advantage of the object oriented nature of controllers。

 so if you have controllers that inherit from other controllers。

 your before actions also inherit as well。 so you could specify one action in an application controller at the very top of your application and then if you have a user's controller and a sessions controller and a moviess controller that before action that's sort of at the top of your inheritance level will be called in every single action for your application so。

That is a really useful tool Yeah so there's plenty of different ways that you can combine these login is the most common。

Something that I built for gradescope。 we have an after action。

 So this runs after a request has finished that logs page views。

 So we are logging things in a particular way， but after every single request is finished we log that this page view has completed and the really cool thing is I can write like an if condition and say if like the request type was HTML and not JSson so I could log only HTMLl page views。

 So I'm not tracking API usage and we had a particular way of wanting to track things server side instead of on the front end。

 but you can combine these in lots of ways。 So in in gradescope。

 we have a thing that's like after action track page view if a certain condition is met。

 you can do unless all those same sorts of things so。😊，Up to you how you combine these。

 but they are a super powerful。Technique， so we'll get to questions in a second。

 but to sort of run down the differences。Validations and filters do very similar work at a conceptual level。

 but they' are used in two different purposes， which validations are around data on your models。

Filters are for ensuring some prerequisite setup is there on controller actions or doing some consistent action if it's both after action。

 an after action of course， can't stop the request from happening since that happens at the end。

 but it's a hook that's available。嗯。So validations happen for all of the model lifecycle hooks。

 so update， save， create that kind of stuff。Filterters happen for whichever public controller methods you specify。

 so index， update， edit， etc ce。嗯。Validations， so this is an important thing。

 so validations themselves will not interrupt your execution flow。 So if errors are present。

 your code isn't going to necessarily stop running。

 it's up to you to figure out how to respond to those errors there are methods like update bang and save bang that will raise and stop execution if errors are present。

 you may have a need for those， but filters if they return false will stop the execution of your your code if necessary。

 so you could say。yeah。You could say like false。 and then it could redirect。

 It could just air out depending on what you want to do。

 But filters like changing or redirectt whoops。 that's like what。

Filters you like redirecting would be a good way or good place that change execution。

And they're both good shortcuts for common cases。So。The and then this is just another handy bit。

 The recommended path for errors for before filters is to use。Objects like flash or session。

 which would persist to the next request， but you could choose to store errors in another way if you needed to So the one con that is mentioned here is that if you have too many of these。

 it can be hard to tell what's going on if you have hundreds of before filters and suddenly your request starts failing。

 you know， you may have to go through and debug more of more of that code because they are not always in the file that you're looking at right。

 if you have a before filter on your application controller and you're working on a movies controller you have to be aware that the code that you're looking at may be affected by a whole suite of other code that you're not even aware of necessarily exists or is at play right there so。

Be aware that， you know， if you spread them all over the place， they could have adverse effects。

 but in general。I deployed for the right reasons， they're incredibly handy tools。嗯。

So all the things that we talked about， main thing。

 validations for model data filters for controller actions。

So let's handle this question or this clicker question。

 and then we'll go for some more generic questions as well。So， if。Invalidd movie data is entered。

 The user should be come on eyeicleer system。

![](img/cec59051d50a9267f627797e1dc8713b_5.png)

No。Oh， that's good。 it died in the middle， that's fine。嗯。It does this sometimes， I don't know why。



![](img/cec59051d50a9267f627797e1dc8713b_7.png)

ok。And。嗯。I'll just do it the menu one so if that says invalid movie data。Is entered。

 the user should be redirected back to the input form and fix errors。

Which of these is not required to implement the behavior in a dry manner？All right， well。

 responses are leveling off at 45。A couple E's， so we'll talk about things。

 but a pretty even distribution。 so that's good。 There's some disagreement， so take about 90 seconds。

 talk with your peers。And convince them to change their answer。还是。确是。睇先。要收热点啦啊。This is where。Okay。也是。

Val。Like please。男性。最。This。So。啊。解觉。我出现。再说了。Or you's as library。Yeah，谢谢。嗯对对。I just like， oh。眼星喺边。左右。

Yeah。Yeah。嗯较真。Should I think you。Yeah。Could you like to。All right。

 take a few more seconds and put in a vote。新。I。系出。so。这大。Like down。Good。ほら。say call。All right。

 let's see if we can get to 45 votes again。 Maybe maybe we can get everyone to vote a second time。

All right， well it's stopping at 42。So more sees this time， no ease。Come on here。

 So this one is hard。 This one is something that is。

Well be more clear after you have experience working with rails applications。

 So the fact that most of people did not get this is not at all。Not at all problem。So。hy。

Why are controller filters the only thing that are not required in this setup。

 So what happens with rails so。Let's just think of a really simple case。Where。

InIn our application we。Actually， I wonder if I can just demo something like this really quick is do I still this I still just quiz up so on gradecope we have a validation that points are required and actually let me save my yeah。

 this will still work so when I hit save on this quiz。



![](img/cec59051d50a9267f627797e1dc8713b_9.png)

It's going to tell me that I need to fill in this blank field。

 which is an interesting choice of wording， but again。

 whatever So points are required for this thing so when I hit save and there is a validation that says every question requires points with presence true。

And so， you know， at some point， that validation either in some specific method or。

custom validation added an error that said， fill in this field or points were required and that got sent back to the browser。

In our controllers， this would probably happen in either the create or update controller actions or the places that。

We would you do in this case， this might be assignment do save since this is an assignment。

 if I were updating， if we had the ability to update only a single question and I'm just going to go ahead。

Actually， saving that might show grade， so I will save that after class。But when I click save。

 I would， in this case， be saving a whole assignment。 So like assignment dot save。

 it raises some errors about a specific question。 and then it redirects me back to。

This specific page。 or in this case， if it's something that happens over Ajax。

 it might just render some results。 But basically， what happens in our controller actions。

 if you're working on a。

![](img/cec59051d50a9267f627797e1dc8713b_11.png)

。If you're working on a specific form， you'll get errors back and we'll have something， we'll sayMo。

ave， assignment。save。And。😡，Our validations don't stop our code from executing。 So at that point。

 we have a thing that we could say movie dot errors。

 and we could check if it aired correctly or excuse me if it saved correctly or if errors are present and from there we could decide what to do so。

Because this happens after the fact。Or it happens sort of in the I shouldn't even say after it it happens sort of in the middle of a processing of a controller action。

 so update some stuff， movie。 save， get some errors。

 controller filters aren't necessarily going to help us here because the place that controller filters run or either before something happens or after our request is done and right now we're in the middle of processing some data so。

What you will typically see is if movie dot save， so the movie save method enrails very handily returns a boolean value true or false。

 whether that save was successful so if there are validation failures to save is not successful so it returns false so a common thing that you'll see is if movie dot save and then else redirect to or flash errors equals this redirect to somewhere else。

 and so controller filters are not helpful when we have errors that we need to deal with in the middle of processing a request。

 so that could be a user up in a form that could be responding to an API value that has that's returning some JSON whatever it may be。

 but if the errors happens sort of in the middle of that processing is the key reason why we don't need or controller filters gonna to be helpful for the key part of this question was。

The dry piece， so we would make use of validations because validations don't stop our code from running。

 we do need our own error checking code and because we said B is not required that eliminates or B is required that eliminates D as the correct option。

 but you would need A and C。Before we continue on to some database stuff， questions about filters。

 validations， that kind of stuff。There were a couple E's。 but then they disappeared。

 So I don't know if we answered them or not， but questions on filters， validations。In the back， yet。

 no。Okay， that's true thing。No。All right。So。嗯。Validations and filters help us dry at our code。

Associations help us very cleanly define the relationships between models。 so in grade scope。

 I just showed an assignment。 an assignment has many questions is something that a relationship that exists and has many is a rails keyword that we'll see。

And so。There's a lot of data modeling that will exist in your applications and associations are a really handy tool that are one of。

I think honestly the best features of active record， that means that when we talk about SQL later。

 you don't have to write much SQL yourself。So our goal is that we want to easily represent the idea that a movie has many reviews so。

We can say we have a movie inception in this case。We find some moviegoers， we find their reviews。

 and then we attach them somehow to this。Movie inception。

 So Alice left a review on a movie called Inception。 Bob left a review on a movie called Inception。

We save the reviews， this is kind of a confusing scenario。

 what is really nice is if we could have rails do that for us and we can。😊，The question becomes。

 how what do we need to get this？To work。 And so this is the first time in this course that we've talked specifically about databases stuff。

 How many people in here have taken 186， just for reference， Okay， a few people， but not most people。

 So you don't need experience in 186 to do anything in this course we're not going talk about implementing databases。

 we are mostly going to just be using them， we are going to talk in a few lectures a bit on writing SQL。

 but it's not going to need to be anything super crazy， but just for reference。

 So if you have taken 186， some of this will be。A bit of review。嗯。But to make our associations work。

 we need to do a bit of upfront data modeling。 So the stuff that goes in our database needs to be set up in a way that。

ItTells us something useful。In this example， we have a table called artistsists。

 so artists have a name。And ID。Justin， Shakira and Brittany， okay。

 and we have a table called Reviews， so reviews have an ID。They have a description。

And they have this thing called artist ID So artist ID is a is a term called a foreign key。

 it says that this thing of 12 refers to the artist with ID 12。And so in our databases。

You can avoid having numerical IDs， but by default， every row。

 every record in your database should have its own unique ID which is sort of separate from the rest of the data。

 you could avoid doing this but it will make your life a lot easier if we have an ID numbers that are just sequentially ordered are the easiest thing。

 but you can imagine that this is some other format of data。

 but what we have here are these people that are artists， we have reviews of these artists。

 and we have this key called artist ID that you can think of it as a reference to this artist。

 but all we're doing is referencing that row in another table。

So we have this thing called the Cartesian product， which is when we're looking at a database。

 we can join two tables of data together and find all the rows that they have in common so if。

If we take or before you even get to all the rows that they have in common。

 we could just say for all the things on the left side。

 repeatat them with all the data on the right side many times over。 So we have four。For Justin。

 we repeat Justin with all the different reviews that we have for Shaki。

 we repeat it with all the reviews that we have there。And what we want to do is at the end。

 find all the rows where the artist ID on the left of this table。

Aligns with the artist Id in our reviews table and the Cartesian product。

 which is all the combinations of possible rows between these two tables would be in particular。

 kind of an inefficient way of doing things。 So databases themselves make it very easy to calculate and find the rows that are in common。

 But what we're essentially doing is saying we have two sets of data。

 I want to find all combinations of those data。 And then I want the ones where things align where my artist Id on the left is the same as my artist Id on the right。

 And in this case， we have。I have3 artists with three reviews and there's one review for each artist。

 you could imagine that on our right side we have multiple reviews for each of our three artists and we would get multiple rows in a result set。

 but in this case right now each artist has one review we match them up by using this artist ID which is just ID on our artist table and called artist ID on our reviews table。

 importantly rails will let you name these columns just about anything because again。

 you can make computers do what you want them to， but。If you have IDs that reference other tables。

 you should name your columns， table name， underscore ID， it makes things nice and simple。

 the invisible people who take 169 in the future and will be working in your project we thank you and they will not hate you for doing something confusing which if you care about your peers would be a nice thing to do。

And so。Our database has all this information that we need。

 The question is then what can we do in rails to get this So As I mentioned， this I。

 So back to a movie' example is called a foreign key。

 it says this thing points to a specific foreign object in another table For meaning that it's just different than the thing that I have right now。

 So a reviews could point to a movie ID， they could point to an artist ID whatever you have there。

And when we have that set， this is what will define our relationship between multiple objects。So。呃。

When we are doing things， we can。We could write the SQL， so select star。

 so select everything in my tables from two things。

 movies and reviews where movies ID movies ID equals reviews。mo。 ID。

 So this is one way of grabbing all the data in two tables selecting the data where these two things line up。

And we get the three or whatever rows in this case that we should get back。

 So this is your first set of sequel on these slides。 You won't need to write this at this point。

 We'll talk in the future about what's。Where you might need to write your own set of SQL。

 but the great thing is don't worry about exactly how this works right now because Ras is going to do the hard work for us。

Just talking about foreign keys in the。In the abstract and we're going to continue with this on Thursday。

 which of these relationships cannot be represented using this particular foreign key schema。

 so we have a course has many students， so we have two tables。A course with an ID。

 we have students that have an ID and each course has a student ID。A student cant have many courses。

A student can have zero courses and all the above relationships can be represented in the schema。

We are just about the end， so we'll just vote once and talk about。Of the options that are here。

See if we can get up to again， about 45。All right， well in the sake of time。

 we're going to continue on， most people picked A， which is nice。Nope， not that one。 So yeah。

 in this case， the relationship that we cannot represent is a course has many students。

 So the illustration of this question is that。The data modeling that we do is important。

 this is something that takes a lot of practice if youre setting up a new application I encourage you to ask questions about this on Piazza but why can a course not have many students in this case each course in our database is one row right so each course has an ID CS169 if we put student ID on course then each course could only have one student。

A particular student could be enrolled in multiple one student courses in this case because。

A student there could be multiple courses with the same student ID but in this model each course would only have one student ID so that would be the restriction there of course if a student is enrolled in no courses。

 they could have a row for a student in the student table but there would be no course with their ID as a student ID so on Thursday what we'll talk about is how do we model complex relationships like students that can be enrolled in multiple courses and courses that can have multiple amounts of students and there will be a lot of ways that we can model this data and a lot of tools that railils gives us to make this easy so。

Section meetings today with your GSI for projects and we'll see you on Thursday。



![](img/cec59051d50a9267f627797e1dc8713b_13.png)

![](img/cec59051d50a9267f627797e1dc8713b_14.png)