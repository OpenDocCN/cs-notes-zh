# 012：UCB《软件工程｜UCB CS169 software engineering 2019》中英字幕deepseek p12 12 CS169 12.zh_en -BV1UsB7YPEMj_p12-

对。

![](img/ce53b82a2a385784dac80cbbd0fdcbe5_1.png)

Good。Okay， so the midterm scared a few more people than I expected， but that's quite all right。

 either that of the power still out and we haven't really realized it。So because of the power outage。

 we weren't really able to grade your midterms when we expected to because they locked us of this building。

Although I found a way in to at least scan them。But so sorry for the delay in midterm grading。

 but you will get grades back this week， I'm going to go ahead and update the syllabus。

 but basically we plan this course with a bit of leeway in scheduling lectures so we're just going to shift things back so there won't be like an extra lecture that we have to make up or anything like that I'm not going to cut into your dead week。

😊，Also faculty have not yet been given the okay to cut into Deadwe。

 they will probably allow a little bit of that， but just so you' aware in this course at least。

 you we won't have a makeup class session， we will probably have some final project。

 sort of demo wrap up work， something like that that will maybe we do during Dead week just give you time to wrap things up。

 but there won't be class， there won't be a significant hour work and because we don't have a final your course project will replace any of that。

But you know， that's just a bit about that， hopefully otherwise everything is getting back to normal。

诶。Yeah， things that you never expect to happen。Otherwise， projects。

 I believe everyone should have contact info yet， if not， well get that to anyone who needs it soon。

 but start reaching out this week if possible， you should be having an initial meeting to meet with the customer discuss their requirements。

You know， your first meeting again， sort of high level what should you do， well。

 understand from your customer what the goal of the project will be for the rest of the semester。

 you know you're going to be working on it basically now until the end of class。So， you know。

 get to know everyone， spend a few minutes on that， but really try and understand it a high level。

 their goals for this project。 If you're working with a repeat customer， you can always ask them。

 you know what things made their past experience good， what can you do to make it easier for them。

 what could you do differently， you know， if it's a new customer。

Then you're kind of going to be going through this process together but that's quite allright as well so you know keep that in mind definitely though from this point on we will have two more homework assignments homework six will be out today it's going to be due Sunday well probably stick with Sunday deadlines for the next two just because things kept getting pushed back。

But other than that， the bulk of the work will be projects as well。We have midterm grading。

 we'll talk about that， but overall I think the midterm went pretty well and we'll have some updates on there。

We're going to continue along with last week was why do you know？Okay， whatever。

We're going to continue along with sort of testing the。

The theme of using testing to make our lives as programmers easier。

 and so today will be more theory of testing， more best practices and that kind of stuff。

We've spent a lot of time on cucumber， you had a couple questions on that。

 your next homework assignment will be around testing so this will be relevant for that。

And so it is an exceptionally useful tool， but like any tools。

 it doesn't completely solve the job for you， right。

 you have to be aware of how to put that into practice。

One of the most common things that you will see with cucumber is you will test the happyapp path when I log in I am redirected to a page which shows my username with a success message or something like that and that's great。

 that is a perfect use of cucumber but you also happen you also need to remember that the happy path is not the only thing that customers will encounter。

 they will type errors， there will be some unexpected scenario so your cucumber stories should also reflect things that can go wrong。

😊，Sue。U。You know， be careful with your regular expressions and that dot star means that it captures everything and it will try to capture everything because that is what its job is to do so you know。

Just a reminder that therell be you will probably have two step definitions that try and sort of eat each other。

 and you'll have to work on making those a little bit more specific。

Also under careless use are regular expressions that are excessively complicated。

 we are all guilty of at some point in our careers of programmers of writing a regular expression that should not be written as a regular expression。

 I expect you to do this a few times in this course or in your career as programmers。

 but learn from that and then split it up into multiple regular expressions。

 extract your step definitions into multiple methods if you want to share some code。

 don't share code by making more complicated regular expressions that fit into one step definition。

Also be careful about where on a page they will match。

 so we'll talk about the use of selectors in a second but you then I should see some string on a page if this is a username you know if you have a page that has a lot of copy。

 then I should see the word the is something that obviously you would expect the word the to appear multiple times in the course of a Web app and that wouldn't be a very strong test case。

 so be careful with you know where in the page you're matching that as well。And you know。

 when you check your results。Then I should see you know。

 make sure that that is content that was actually exercised。

 you can also in your step definitions depending on the type of test。

Check that something was pushed directly into your test databases。嗯。

So if how do you get around overly broad step definitions。

 Kapy Bar provides a selector called within。 So we mentioned this briefly last week but。

When you search for text you can say within a particular selector。

 so this could be most commonly a CSS selector， so that means an HTML element name。

 if you say within body that would just be the entire contents of your HTML page。

 but you could say in this case div shopping cart ID。

 and I will point out that if you're actually using IDs properly。

 then specifying div ID shopping cart is redundant because there should only be one ID per page。

 so that example will be fixed after lecture。But。You know however you want to write those selectors are up to you so giving good names to your CSS will make this easier。

 that also means when you write your test cases and when you read through them。

 if you have a user profile card， then I should see Emma within dot user profile card or something like that。

That will be clear to the reader of your test cases where they should expect to see this information。

And you could also you know， write something that says within a page component and that would be your own custom step definition that maybe turns this name shopping cart into a CSS selector or something like that。

 So those are all options for you， but just be aware that if you have overly broad cucumber tests。

 they are likely to pass in cases that。They might not actually be passing。Just keep that in mind。嗯。

We talked about this briefly and there was a question about this on last microquiz， oh。

 but it's going to be good to revisit this because。There are debates over these terms。

Cucumber is the highest level of testing people will call these full stack integration acceptance tests。

 so the key thing here is that most of these are going through multiple scenarios and page loads they are。

When I log in， I do this， I am taking to a new page， I see this thing， it may be a scenario that is。

 you know when I add something to my shopping cart and then I click checkout and I complete the checkout process。

 I get an email， you know it's exercising a bunch of different steps in your application。

Module or functional tests are still exercising a large portion of your stack。

 but they're usually constrained to a single page。To a type a single type of controller。

 if it's literally a rubby module that has a shared set of functionality。

 that may be something there， the idea though is they're still exercising most of your stack。

 but they are not necessarily a full user story， they are one page of a user story。

And then unit tests， so unit tests are what we're going to talk about more today。

 but testing a specific small piece of functionality independent of where it sits within the rest of your application。

 so this is sort of where we'll be today。The tool that we're going to use for this is R specEC you'll have seen a little bit of R spec within cucumber step definitions。

 but today we'll be using it directly and showing some examples there。

 so this is the order of sort of tests in terms of highest level to lowest level in this course some people will call functional tests the same thing as integration tests so in the professional world these terms get overloaded and used so with the microquiz I got a really good regrade request which is like well I ordered these tests this way based on this blog post so I gave credit to both answers of swapping these two which is just to say that the point here is not necessarily the terms but the idea of when we test things we're going to isolate our code at different levels。

Each test type is appropriate for different kinds of actions and so you'll get experience with all three kinds of tests。

First click a question if this thing cooperates。W is always a gamble， cool。

When you're visiting your profile page without logging in。

 you should be redirected to the login screen， what kind of a test case is this？AndAgain。

 this is a question which there is one best answer， but there are two reasonable answers here。

We will。Have people vote and then talk about that so it looks like it's leveling off。

Some pretty good distribution， 1 E， that's good so。Talk。

 take about 30 seconds and talk with your peers and see which of the cases you think is better for this kind of test case。

There's good arguments for at least A and B since no one psy。系度出。なか食だす。啲啊不难数。Part。佢度系公。系。原说是吧。你嗰系。

It's kind you。前。有水。你啲啲。I mean there could be a lot。All right。

 take about 30 more seconds and put in a vote。It justま time。Yeah。Yeah， I don't see。系。

All right let's see if we can get everyone to vote。

 we should get up to about 45 and remember with clicker questions there isn't a harm in voting for the wrong answer。

 they are graded on participation so you know in a panic just hit a random button on your clicker and you'll get credit for showing up to lecture。

嗯。If everyone votes randomly， it won't actually tell me that much。

 but you'll at least get the credit。Yeah， there's 1D， but they may have meant tea。

 so we'll talk about the options。We're still behind a little bit， but that's all right。

 we'll talk about this。 Cool， so didn't change too much。

So that's pretty interesting but maybe a little more B's。

 So who wants to make an argument for one of their options， A or B， There's good arguments for both。

 and then we'll talk about why one is a little bit better than the other。Sure。I said A。

 just because for the scenario， there could be a lot of different components involved。

 and we don't know sort of what like exactly we're working with as for like B， right。

 I I believe that functional and like module tests。

 they should be more for like testing these specific like components working together。

 But we never specify that in the test。 So yeah， because of ambiguity I chose A。 Okay， that's。So。

Yeah so the ambiguity is a good point in this case what youve said with B。

 if we know that it's a sort of getting to the idea that we know that it's a single component that would probably change the answer。

 and the reason here that we would say that a functional or module test is a little bit better is，😊。

If you're implementing a function like login， there will hopefully be a single controller which handles the login function of your application。

And so for tests that operate at sort of a single controller level。

 you can test the needed functionality within a single rails4， call them controller tests。

 rails5 and six， I believe call them system tests now， the names change， but the idea is that。

What you could say is when I visit the login page。You could do that in cucumber。

 you could also say within a controller test， describe the login method。

 post with a correct password， and then you get redirected to somewhere else。When。ow。

 what am I going to say？When you're testing in this case， also like a user profile page。

 the key thing here that we're looking for in this test case as well is the word redirected。

You're not expected to notice， but there is an R spec helper method， which is redirect to。

 so it mirrors the rails method， but you can you can say expect thing to redirect to and give it a rails path。

 So in that case， if all you want to test is that something redirected you could do that。

 So if it's an incorrect password， it should redirect you back to login page if you're not logged in。

 it should redirect you back to login page。 And I said starting with a login controller。

 for this scenario， it would probably more appropriate for a user profile controller if we're looking at that specific page。

 but the idea here is if we're looking at one single page。

 we take one action and sort of one response should happen。

 that's something that you can usually incorporate in a single。

And a single sort of module or functional R spec example if the test case said something like we should be redirected to the login page and I should see some information about the user that I was trying to access or I should get a flash message with X。

 Y and Z， that kind of stuff where we want to test the results of what we see on the next page that would be when a cucumber scenario would be a little bit more appropriate because we would be making your request we'd be looking at the results of testing multiple pages at once。

 and so that's really the barrier here is integration test。

 you can think of them as going through multiple pages at once multiple meaning to or more。

 so if it's just two that's fine。And then an R spec scenario of you know this is one request。

 all I care about is the direct response and so if we just care about the redirect that would be one thing。

 a unit test will say examples of， but a unit test would be when I enter an incorrect password。

 you know the user login method returns false or something like that we'll talk about some more of those so。

嗯。Another question。 so again， in your own applications， you can write these tests in multiple ways。

 so you know if you have an application and they do things a little bit differently。

 as long as the test is passing， that is the goal there。

 but a user can sign up for a new account by providing email， password and solving a capcha。

 so what would be the best way to think about testing this。If you can avoid them。

 please avoid captures， they're evil。嗯。There are， yeah， we're going to talk later in the semester。

 hopefully having an lecture in like web accessibility。

 but captures are a terrible thing for accessibility。

 they are also like just slow people down in annoying ways。But in some scenarios， they are necessary。

嗯。Interesting distribution here， so about a minute， and let's see。Kol。So。Good distribution here。

 so let's talk with your peers for about a minute and which of these test cases will be。

Or which kind of tests will be most appropriate for this scenario？这觉得。贵。系。系。都是意见。For similar reasons。

回。就。What。你。When you're all。做成嘅。ok好系。整个意面的。Right。あれ程度。这。唱。你车度去。Yeah okay。So something。是的。Okay。あて。

Yeah是。佢哋边食刻我。Its actually I also drink。嗰个。望。拣个。问下到啲想嘢。結こし。、デスパシュです。开到我。We do。All right。

 so take about 15 more seconds and put in a new vote。And we'll talk about this one。

So we can get to 45。See。Leveling off at 42。So。More movement towards A so that's pretty interesting。

 so a few more C's。So this one is kind of a confusing one， intentionally。

 so the thing about this that makes a cucumber scenario the most likely thing is if you want to test the results of something involving a capture。

Then。That's probably going to involve a cucumber scenario because what you should have as a test case here is if you do something with a capturecha。

 you should have a happy path where that capturecha is successful and they see a success message。

 their user counts created， you will also want to have some specifics about when this process fails。

 what goes wrong。嗯。😊，You know in this case， with a whole sort of signing up scenario you might even be doing this over multiple steps where content is appearing and disappearing depending on how you structure your form。

 if you have a single sort of just login method checking or a user creation method checking that everything is present。

 you like a unit test would would be appropriate to combine with this cucumber scenario so what we're going to talk about in a moment is how you combine your cucumber scenarios with more specific tests that aid in your development。

But in this case， the capture piece is what would make a cucumber scenario most important because that has some interactivity。

And so that would be the place where you would want to have a cucumber scenario there。Again。

 the code that you write， you could write tests that pass or that execute the code in sort of a bunch of different ways。

 but if you're thinking about something interactive， think about something over multiple pages。

 reach for cucumber first。呃。To continue on with sort of how we separate these。

A user cannot specify a blank password when setting up an account。

 so where might we best test this functionality？Again， the word where might we best do this。

 what's most appropriate， because there is room for debate here。

The goal sort of thinking about where to start in different scenarios。

So if we can get up a few more in the next 10 or 15 seconds。Can we get to 50？Maybe not。Cool。So。

This one， I would definitely say a unit test is the best approach there。 Again。

 if you wanted to test the exact response in your application。

 if you wanted to render something special， there may be a use for an additional cucumber center。

 but the reason we would say unit test is best is that。You know if you have a user create method。

 this would probably something that exists on a user model。

 what you would do is you would test that method by just providing an empty input for the password field and that method or。

Some other logic， depending on how you have things set up in your user model。

 should raise or return some error。Part of this will make a little bit more sense as well when you get into working with the guts of rails because the way that you structure a rails app。

We'll sort of also guide you in writing the right level of test cases。

 which is that things that are just exercising the basic aspects of creating， accessing。

 modifying data with your models， those will fit nicely into unit tests that run really well on their own things that work across a controller will sort of fit into these module and functional tests。

 and then your cucumber scenarios will go through multiple steps at a time so。

A unit test would be the best thing in this case for the scenario and then we'll talk about why and how in a moment you want each test case level。

 you know， for each kind of scenario， but questions on on these。

You know whyhy we have different test cases， what we should do with them。

 any questions so far on that？No。Cool。When you're working on apps。

 we've talked a bit about behavior driven development， so that's BDD。

 this is the tool that cucumber is primarily used for。We write some scenarios， they're first read。

 and then we work on code to make them pass。Cucumber scenarios are great because they're really high level。

 they give you good description as to what your application should do from a user's perspective。

 except when they fail as a programmer，It's kind of opaque If you have a scenario that says。

 you know， when I sign up for an account， you know， X， Y， and Z should happen。

 and then I should be on my user profile page or something like that。 And then it fails。

 hopefully you'll have some error message in there that gives you a hint。

 But you know when you're just sort of looking at the build output。

 it could have failed for any number of reasons。 So most of the time we're going to combine our cucumber scenarios with more granular test cases that are going to be unit and functional test cases。

And those will write in our spec， and so what we'll do is we'll start by writing a really high level test。

We'll say， you know， I have no idea how this code is necessarily going to be implemented。

 but I know what my application should do because my customer told me that's what it should do。

 makes that scenario pretty easy to solve。 Then you have to figure out well。

How do I write the code that actually solves the work that this test is trying to do and if we're following a a test driven development pattern。

 so TDD， then what we're going to do is we're going to start writing test cases in our spec that fails。

 So when I create a user account with a email and a username， maybe that's the info that we need。

 it will successfully create it and the first time again you do test driven development。

 it's probably going seem a little bit weird， you don't necessarily know all the code that needs to get written but we'll write a test。

It'll start by failing， but we have our test case， so now that we have our test case。

 we can go implement the function that it's trying to test。

And the idea here is that when you start at your test cases， you start at a really high level。

 you write smaller test cases。And then as you solve those test cases， you start solving the smaller。

 more specific ones first because。And a story that composes。Multiple pages。You know。

 multiple steps to get a cucumber scenario passing， you have to have something in the database。

 you have to have a proper controller action， you have to have a view probably that has the right HTML。

 you know， accesses the right methods so you start writing a high levelve test case so you have a guide as to where you need to go。

 but when you implement those， implement them sort of inside out where you implement the most granular details first。

And the process that we call this is called up。Red green refactor， which is we start。

With a test case that doesn't work， we write code so that we get it passing and then from there we can just iterate on our code to make it as good as we want。

 but the goal here is start from a test case that describes what should happen。Right。

 whatever code we need to get it to pass， and then after we get the test case passing。

 we have a way of improving the quality of our code going forward。You know。

 always aim for working code， which is as you're going along。

 you know your app should be moving in the direction of functional， this is true of really anything。

 you know we strive for high code quality， we strive for readability but you know code that does the correct thing is the most important beautiful code that gives you the wrong answer。

 it may be beautiful but it's pretty useless because if it gives you the wrong answer what good is it there anyway and so。

😊，You know， start off with what getting something functional first and you know。

 if we've talked about the acronym dry， so don't repeat yourself。A good habit to get in but。

Make sure you know repeat yourself a few times before you figure out how you should best refactor something you don't have to start off by having the most perfect abstract solution and so your test cases。

 especially if you're joining a legacy project will be your guide in how you should adapt and modify the code base because you will probably approach someone else's code and be well。

 they implemented this in kind of a confusing way， I see a new abstraction that I can build。

 your test cases will be your guide there as well and so。It goes for yourself， new projects。

 legacy projects， all those things as well。All。Testing， why we have different test cases。

 those kinds of things。Yeah。Cool， so。嗯。To continue on with a bunch of acronyms that are also in the book。

 So we've seen this quote before。This is from Brian Carrigan， one of the founders or Knegan。

 one of the founders of C， which is debugging as twice as hard as I write in the code。

 so if you make it clever you'll have no time to solve the test cases and。😊，This is Edgar Dyextra。

 famous for， of course， Dyktra's algorithm。Testing can never demonstrate the absence of errors。

In software only their presence， which again is a reminder that as we test these things。

 it is impossible to prove that we don't have a certain bugs in our code。But the more that we test。

 the easier this gets and we'll talk about some。Some ways of expecting you know looking for places that we should definitely test or code。

 So we have a method here birthday today， so maybe you're working on an application you have users' birthdays you want to show them a nice little login message that says。

 hey， happy birthday when they log in you know， how might we test if their birthday is today。

 What are some things that we might do to test this method and。Consequently。

 what are some things that we might need to be aware of while testing this method？

What's a big gotcha here if we're testing this method？

Someone wants to answer I can pass it along or you could just shout it out。

 what's a big problem here with this method？So yeah。

 it handles the edge case or it attempts to handle the edge case for。😊，For leap days。

 which I think that code is mostly correct， although there's something missing there as well if we want to get into that。

 but what else is a big problem in this method that might。That we might need to be aware of。Yeah。Oh。

 sorry。It's not deterministic because you yeah do date today Yeah。

 so if we do date today and we don't take into account how we set up our tests。

 then our tests are going to pass one day a year。If you have automated deployments and your test pass one day a year。

 that would really suck for your productivity as a development team。

We need to find a way around you know date dot today yeah。

 so that's going to be one of the main things that we're going to look at in test cases you know。

 when we work with our code， we could say that this has a dependency on the current date。

And that's gonna be something that we'll want to check for。

 There's different ways that you could write the test。

 You could literally just pass date do today into your method so that， you know。

 you always have a test case that's today。 But one day， you know。

 you'll have a test case that you expect to fail that will pass because it will end up being that day。

 So what what we'll talk about are tools for dealing with things like dependencies on a current date。

What you will also want to take care of and test is you should definitely have a test case for things like February 29th and March 1st because you want to make sure that you know。

 if you ever have a conditional a special case， that should also be reflected in your test cases as well。

 and so you know for the most part this handles。The leapap day birthday correctly and that you don't want your birthday to be every four years if you were born on leap day。

 that would be pretty unfortunate。But if this doesn't handle the case where like during a leap year。

 you probably shouldn't have a birthday two days in a row。

 that would be something useful to test for。 but you know there's there's lots of sort of gotchas here with testing dates。

 but the point being that。What you're going to want to be aware of is stuff that depends on other data like a date。

How should we go about testing things that have dependency？

We'll get into this the rest of this lecture and in the next lecture as well。

 but there's a lot of techniques here。嗯。Our goal for tests， so another acronym again。

Not expected to memorize these， but they sort of help guide some ideas so first， so fast。Independent。

 repeatable， self checking。And timely， so let's get into each of these and the data example really。

 the data example kind of illustrates。A few of these that we have to be careful so fast you should be able to run your test quickly otherwise you won't run them at all some of you。

 if you've had internships depending on the company will have experience with tools that have our long build cycles the great thing about ruby and the rails community setup is fast tests are a valuable thing so you even build times of like 20 minutes are considered slow for large ruby apps but。

You want you know want your test cases to run as fast as possible so you could run them as often as possible。

 so independent and this is one of the things that our date gets at if we don't handle it correctly。

 our test cases shouldn't depend on other logic， they shouldn't have a dependency that can change the result of our test case。

 so if it changes from October 15th to October 16th。Our test case should not suddenly start failing。

 and so we have tools to deal with that。Repeatable。 so again， relatedly。

 if we run our tests multiple times， they should not fail。 So what repeatable in the case of。

A date that could be across multiple dates。 What will also be a case that you need to watch out for is if you are ever adding things to the database and modifying database state that will be a case where you want to watchche out for whether something is repeatable Some of your projects will use gems and setup that automatically clean the database after each test so you don't even have to worry about this so there's a lot of different techniques here for how we get to good test cases in practice。

But you know， these are the goals that you should strive for when working on them， so self- checking。

 if a test can't automatically report whether it is passing or not。

 it is not very good as a test case because it means you can't run it as often as possible。

 you don't get that automated feedback。This， of course means that you。

 any of these tests are not a substitute for a manual。Human driven QA。

And having your customer go through and tell you whether or not。Your app is functionally complete。

 but as a set of automated test cases they need to have something that is able to report whether or not they're correct。

 it would be very useless if every single build came back and said hey human。

 I don't know what the status of this build is， you've got to go check it out。

 it wouldn't be very fun。And timely means that they are written in a timely fashion。

 so if you're doing TDD， that means your tests are written first， if you're not doing strict TDD。

 that means your tests were written at the same time as writing the code。

 this is also important because if you ever don't write your test first and you go back to writing a test case for code that already exists in your application。

Which some of you will want to do this for legacy applications because you'll learn the hard way that that test case needed to exist。

 you don't necessarily know what the code should do， you know what it does。

 but you don't know what the author necessarily intended it to do so。Test cases。

 especially when following TDD， are a good metric of saying。

 I intend for this code to behave in this way and if this test case fails， it's because。

You know the code stopped working writing test cases for code that's in production is always a little bit uncertain in terms of whether you're just trying to test what currently happens versus what should happen。

嗯。Which are these things？诶。Can be tested both repeatedly and independently。

And so this will again get into how we can test things like dates。Let's take about 15 more seconds。

 see if we can get。A few more votes in this time。Nice， we got to 50。Okay nice。

 so we have a really even distribution of answers， so that means that you should all take a minute and there should be some healthy debate and hopefully know face you know too many large arguments。

 but there are there's definitely a correct answer for this one。

 but think about if you can't test them， try and tell yourself why you couldn't test these things and if you have an idea of how you might test them。

 talk with a partner and explain to them what tools you might have to test these things。で大丈ですか。あ。不道人。

とです。that also was we don't know what dependencies。I think that point so we。Yeah yeah。最终呢。打啦。先系哋睇到。错。

やつる。话自 don。is。Right。Yeah。喂。注下。有口啊。But I guess its kind of separate that Michael。All right。

 so take another 30 seconds or so， and then we'll come back to this。大か。想下你想。呢嘢。Where。冇关系。

On self portion have。做食品发证啦。I just。All right， let's see if everyone can put in a vote。

Can we get up to 50？Five more seconds。All， so about even from both and neither， that's interesting。嗯。

Andone't want to make an argument for why we can or cannot test a random something that depends on a random number or on randomness in general。

诶。Yeah， why might we not be able to test this， or if you have an idea。

 how could we possibly test something that is random？Yeah， I going to pass it up here。Where is it。

Nice， so if I put D， but I was thinking that for like at least C。

 you could put like both as inputs to like the function。

 So you could say like input time and also input like a pseudo random number into this function。

 And then from there， then you can like it's deterministic。 Yeah， Yeah。

 so the goal here is to make our test deterministic。 And so it is possible。

The correct answer for this one is C， which so that also on a question like this。

 it would be a really sad state in the history of software development if we haven't figured out how to test these things。

Because a lot of code in production depends on things that are random in some way。

That depend on dates， so if you could never test showing someone of message about when their birthday is that would be unfortunate if you're working on a calendar app and we didn't figure out a way for testing things that happen on certain dates。

 calendar apps would be really buggy， although they kind of are already。

 so may not be the best example but。The two things here that we can do are turn things that are non deterministic into something deterministic。

And a random number generator， these are pseudo random number generators。

 One option that you have is to use a seed。 So most of the random number generators that you use will have。

A way of passing in some seed number and when you use a certain seed that makes them now deterministic。

 so you might have an option that says randomize all these inputs。

 but to test that the randomization is working correctly， you might start with。

 you know specific seed and then your test case can look for output in a defined order。With dates。

There's a lot of different ways that we can do things but。

We'll talk about mocks and stubbing of methods， which allow us to say。When I call date dot today。

 Ruby， it should return a specific date and so we can test things that rely on dates and times by in our setup for our test saying what time the test should act like when it runs and so this is a really important thing because it means that our test cases。

They will always think that they're running at a specific time and then our logic that we write。

 you know， if we say before our test case set up today as October 15th。

 then every single time we run that test case， the code inside of it will think that it's October 15th and that will be。

A way that。You know that test case runs consistently and repeatably and so those are both options。

 and so we can definitely test these two things。 they are a little bit more work。

 They are something that you may need to watch out for as well so。

One thing that will hopefully not happen to any of your projects。

 but when you run R specEC by default， it runs all your test cases in a random order and occasionally this random ordering of test cases will lead to unexpected results and so when you run R spec adds a command line tool you can pass in a seed that will define the specific ordering and so in your output。

For each build， if you look for it or each run of test cases。

 it will tell you the seed that it used to order the way that it ran your test cases。

 And so when you're looking through these things， you'll have some information to debug effects of randomness if you need to。

 but for the most part。Hopefully you should be able to avoid dealing with random test case failures because they are unfortunately a pain a bug。

What does it mean to write a good test case and in this example we're talking more on the module and functional test level and unit test level than we are our integration tests。

 but are set up and the things that make a good test case are similar just a little bit different here。

We have arrange， act and assert are going to be our three things。In cucumber there was。

You know a before so that could be our range acting so given when then are going to be the words that we use in cucumber in our spec。

 the words that we're going to be used are things like expect will be the most common but there are a few others but we'll be using expect today and so the idea here is。

Before our test cases， we should set up the environment to be as consistent as possible。

 so that may be。At an entire application level。Some setup。

 it may be specifics to each type of test case。And then if there are side effects。

 you may want to test those depending on what happens or what you're trying to test。

 and then the innovate you're going to assert that something happens。If I say user。t login。

 I might assert that user dot session count is now one instead of zero or something like that。

 there's lots of different ways that we can test this。嗯。

To continue on with computer science's favorite example of Fibonacci numbers。They show up everywhere。

We might write a set of unit tests to test whether our function that calculates a Fibonacci number is working correctly。

In the simplest test case with R spec， we have a new keyword it， it is just a function。

 it takes in a string， which is the name of the test case。And they block， which are。

The lines of code that get run for this test case。Here we create a new instance of our Fib function and we calculate the value of the fifth Fibonacci number。

 and we expect it to equal 5。Which if you1，1，2，35， if you count that way。

 we can debate later about which is the proper way to count Fibonacci numbers。

 but assume that this test case does what it wants to。

And so we have some setup we have some code that does some work that would be our second A we don't have any arranging here。

 and then we have an assert， so expect an assert do the same thing in this case。

 so we have some expression we expect that two is just a nice method that R spec gives you。

To sort of help these methods and our test cases read a little bit more English like。

And it has a method called equal and5。 so the equal method is pretty straightforward。

 It just says the result of this thing or expectation does it equal the thing that I'm passing into the equal method。

 so aptly named there。 So as long as Fibonacci of 5 returns five， we're all good here。We have。

Another method here that tests you conversion from floating point values to integers that it still works correctly and that we return errors in the case of negative numbers which if you wrote your definition recursively is a good test case to have since you don't want to infinite recursion B0 is a method that R spec provides this works relying on some meta programminggramm that Ruby does but you can look up the list of things that makes sense in this case what B will usually do is it will look for a zero question mark method on whatever value is in your expectation so Ruby and Brails have defined a bunch of handy methods so you can do integer do0 is a method that exists。

And so you know B0 maybe be one with an array， you might use a method called has item that would return true if an item exists in array。

 you might。You know， use a method that compares to a regular expression。

 depending on what you want to do。 So there's a nearly infinite set of options here for what will go。

On the right side here of your expectations， but the goal is whatever you need to test your method you have access to and of course。

 before we write some tests we'll need our setup code so any files that need to be required。

So in this case， excuse me， R spec。Our Fibonacci。Our Fibonacci definition。

 and then our aspect tests are all wrapped in a describe block。

 so describe just says these set of test cases are related。In some useful way to the programmer。

 it doesn't do anything on its own， but it does structure test cases in a way that makes them a little bit more readable and more clear too。

To the programmer so a really common thing in rails is each set of controller tests will be wrapped up in a single describe block for that controller。

 so there's one set of controller file， controller spec file for each controller file in your application folder。

 but there's a number of ways that you could structure this。诶。Yeah。

 so we showed you a couple common ways of writing expectations。 And the goal here is。

 come on eye clicker。 Let's open up。 Which of these is valid。

 So which things on the right can be compared to something that will return true or false。All right。

 we're almost to 50。Interesting。Okay， cool。There is a large debate whether they are all correct or whether B might be the wrong one。

 so I'll tell you that B or D is definitely the correct answer。

With the knowledge that the thing on the right is supposed to return true。

Are you supposed to be something that is comparable to true or false values。

 which of these might be correct， so talk for a minute with a partner and then revote。I'm sorry。

 which of these is not valid？Re。都有咩呢。系。し。5 different。There。太多的时候。Yeah。

So what does you mean flash Street was that's to be all explosive。

53 this should be the good value there。Yeah， you should。Thank that。来。我毒。Yeah。

 so you could assume that result is some known value if it is if there's a reason that you're selecting B it's not because the result is a variable。

 that part is fine， there may be other things。But yeah。

 because you could invert the order of your expectation and your variable。

 whether it's on the left or the right， but that may not be the problem there。Yeah。the job。Yeah。

 what does the double arrow do？Answering the question。

 what does a double arrow do would reveal the answer to this question。 So it's a good question。

Everyone is voting for B and D again， which is good so far， so whoops I didn't mean to do that。

 but yeah， so why is B not a valid expectation？😊，And the answer to who I saw valid relies on the question。

 what does。What does the doublearrow do， So this is something that you may have seen And but you may not。

 It's Ruby's comparator method。 So you can think of this as a way of。

Sort of a handy shortcut method for you know， is something greater than or less than another value。

 so if you're implementing your own classes and you want things to be compared to each other。

You know when they could be orderable on a scale。 So in grade scope。

 each school has a series of terms right， and so a course belongs to a term。

 and we could order terms you know by dates， but a term is like fall 2019。 So how do we order them。

 Well we implement a comparator method， and this method returns negative1，0 or1。

 which is less than equal to a greater than。And so a method that does not return true or false does not make。

A reasonable expectation because our test case can't then know whether something is passing if the value doesn't return true or false。

 so not to be is just a negative version of two so there's both not to and to not depending on whichever phrasing of English you like there are debates about which you should use。

 but for the most part that's programmers arguing about syntax be empty is another be method which just checks if in this case an array or whatever it would be has an empty method。

So this is something that you' will definitely see A is pretty common in rails applications。

B would not be allowed。Two match the right side of match。Can take a regular expression。

So if you're looking for an error message that contains。

A certain string to match would be a great option there， and so that leads。To be。

 so questions on the basics so far of our specs。 So we can just kind of go back here。

 This is what a set of。Our spec unit tests look like for a function。

 or this could be a set of functions， but this is something you'll see this structure。

 so questions on this part， expectations， things like that。No questions。こ。So。

We've got a bunch of code here。Why， what are people voting on。嗯。Thats。 Yeah， yeah。

 there's just lots of participation going on。So。We've got a larger art spec example here。

 so we can walk through。This case together， so this is something that you'll see。Again。

 in a common structure， which is we have our setup at the top。

 so we're testing a book in stock class， our top level describe is usually something that says what is the thing that we are testing。

 our book in stock class， our login controller， anything like that。

We have a general thing that just says， does my class exist？

Which for the most part are methods that are there just to sort of make sure that your tests are working as expected。

 that if some configuration changes， this test case will fail right away。

 but not too interesting there， the meat of what were happening then happens in this describe block co getters and setters and so。

Describe really just a way of organizing test cases into shared blocks of code。

But the reason that we might do this is each of these shared test cases rely on some specific setup。

 so to know if a book is in stock， we have to have a book and an instance of this book in stock class so that exists and。

Maybe this one takes an ISBN and some value， and so this is our range step。

 so each of these test cases in this keyword before。We'll have a new instance variable called book。

Before these test cases， then we'll have this setup that's done so are arranging and for each of these test cases this before block is going to get run and we can then execute our own expectations。

Why do we do this in multiple test cases instead of just one giant test case。

 which with a bunch of expectations？The reason for that is that。Twofold。One。

 by giving a human readable name to each expectation when you see build output。

You know those of you who are working on legacy projects， especially the first time you do this。

It's both exciting and nerveracking， but you'll run through all the test cases and you'll see hundreds of test cases。

 hopefully all of which are passing because that is the state that the previous team should have left their application in。

😊，嗯。If they're not passing， we can talk about that， but be a little bit more exciting。

But they give you sort of context around a single thing that's being tested。For the most part。

 you should strive for one expectation to one single I block。

 but there may be use cases where you need to test that something is successful in two different ways and so this is our setup。

If we need to act， acting means that we take some action to。You know， to set some value。

 to update our model object， whatever we need to do。

 and then every test case should end with an assertion。 so if a test case doesn't have an assertion。

 the final result there is no necessarily true or false value so。

Those are at a high level the components that you'll see in writing R spec tests。

Any questions on this Rpect test so far， what we're doing？That kind of stuff。No questions。Cool。So。嗯。

So a little bit of the more of why around test stream development。

 how we can think about making the most out of this。It's a phrase the code you wish you had。

When we're writing our tests， there's a tendency that we have to expect everything to be working complete in place before we continue and in some cases we really want to avoid that scenario。

 we want to say I'm working on a piece of our application。And how I get this， this method， this。

 especially if it's an external API call to work， is going to be difficult。

 So I want to assume that this works and continue on before I actually get to doing some of that implementation。

 so。嗯。So in our in our rotten potatoes app， let's say that we want to add a button that searches the movie database。

 so we have our own local database and we're going to make an API call to an external service doing this。

You，It makes a lot of sense。 We could write a method that。Searches makes an API call。

 searches an external database and returns the results。

 but if we're writing our own controller tests， do we have to wait for that entire method to be complete before we go and write our tests in the cases we don't necessarily need to have everything complete in our application to to write all our test cases to have a test that is meaningful and useful and so。

The idea here is that we have a controller action called search。We are going to， you know。

 it's going to take a PRms， it might just be search string， it might be title。

 whatever our PRms are called， and we're going to call a method in our controller that does the searching of our external database。

And so when we call that search method。We then know that our controller is doing the right thing and whatever that search method returns。

 our controller will return that search method。You know， if we find a value， we'll display something。

 if we don't find a value， then we'll display an error message。

 So here's how our controller spec might work。 So we describe our controller。

 We have a series of tests around searching our database。So our first one。

 it calls the model method that performs a search。It selects the search results。

For the template from rendering and it。Makes the search results available to that template。

 So what we're going to do is we're going to have a controller action called search。

And we're going assert that it does a bunch of useful things with searching our movie database。

 but the goal will be that we don't have to have our function to search this movie database fully complete and written so maybe we don't know how to do that yet。

 maybe it's your teammate working on that part of the code for your project。

 but we want to make sure that this controller works on its own so if we have a method。

 and if you read the last test case， there was a hint in one of the the it blocks but。

The method that contacts TMDB to search for a movie， where would we place this in our Rails app。

 would this be a class method of the movie model， an instance method of the movie model。

 its own controller method， or a helper method。And again。

 you could write functional code that does that gets you a correct result in any of these places。

 but where would the best place？For this go。About 10 more seconds。Well let's see if wa。40。3 is。

Pretty close。So a lot of disagreement here for this one we're going to continue on。

The best answer for this one is going to be A。Now why is that so we have a lot of options here for when we structure our code。



![](img/ce53b82a2a385784dac80cbbd0fdcbe5_3.png)

But what we're looking for is we have a controller method。 It's a search action。

 It's going to take some data from a post request it's going to operate on that data and then it's going to render some results。

 So where might we best put our method that operates on our TMDB database。 So an external service。

 The reason that we'd say a class method on a movie model is most appropriate is that。



![](img/ce53b82a2a385784dac80cbbd0fdcbe5_5.png)

Well， it's not going to operate on an instance of a movie because it's doing something related to a movie。

 but not necessarily a specific movie。 So this external service doesn't necessarily know about the exact movies that are in our local database。

 but we are doing something logically related to a movie， so。

The movie model keeps it organized with the rest of our code that works on movies。

A class method means that we can do something like capital Mmovie。find intmdb。

And that will keep it there。 So why not a controller method so。Our controller methods。

 generally the way that we will keep them is。The only public controller methods you'll have are actions that respond directly to routes。

 so things like index， create， edit， update， delete。

 and you'll have some private controller methods that help in rendering setting up some data。

 that kind of stuff but。For the most part， we want to keep all the logic related to operating on some data in a model class。

 a helper method。Depending on where you put that could work， but because this is。

Operating logic that is similar to a movie， a model is probably the best place there。嗯。

With the last few minutes， the idea then here is how do we get to testing this model logic。

 how do we decide where we're going to separate things out？And we call these places seams。

 so a seam in your application is anywhere that your code。

Is effect or the functionality is affected by code that you didn't write。

 so a place where you can change your app's behavior without changing your source code。

 so these are going to be things like external API calls， things like accepting parameters。

 from a post requests that might change the behavior of an application。

And these are going to be the places where we talk about replacing。

We're we talk about replacing data， mocking data， stubing data。

 and we're going to keep talking about those methods。

 so it's useful for testing because this helps us think about where are the cases that are most likely to break。

 Where are the cases in our application that are going to be really complicated to test。

And when we spot them。How can we go about writing code that tests these in an isolated way？

The goal here is to write a test case that tests find in TMDB without necessarily having to have that method be fully functional yet and so our spec gives us tools which is expect to and receive and so we'll see how that works in a second。

But the goal here is this makes our controller test independent of whatever our movie service is doing。

 so our find TMDB method， it's probably making an external API call to this this TMDB service and。

Now it's great。 we should end up testing that method。

 but we don't necessarily want every test in our application to be dependent on having an internet connection。

 having the find and TMDB service up and running， having an API key set up。

 all the steps that at some point we'll need to do but if we're just trying to test our controller action one step at a time。

 we can avoid that by saying you know we have this model method。

 and we're going to test it later on so。You know calling TMDB is really the job of the movie model。

 It's not our controller job our controller all it cares about as long as it gets valid data back。

 the job of the controller is to render that response for every request that comes in and so the controller itself shouldn't need to worry about what this method does。

 how it works， all it needs to know is does it get the data back。

 does it even call the method that it's supposed to call so。

What we're going to do is we're going to essentially fake the call to find NMDB。

 and we do this by using this syntax called expect to and receive。And so。

Our controller methods here to be correct to have a correct and functioning controller。

 we can just simulate some data and that will make our tests be both independent。

 repeatable and incidentally， it will also make them a little bit faster and that is a great goal here so what does this look like in practice。

In our controller， we'll do something like。We have this method。

 it calls the model method that performs a search。Before we do that in that test case。

 we will say expect movie to receive fine and TMDB with some parameters in this case， hardware。

 so maybe we're searching for the movie with the name of hardware。

 and then we will perform our controller action， which is post search path with our parameter search term。

This is the idea where we are you can call this spying on a function is a term that you might see in other testing frameworks。

 but we are going to say I don't actually care what the fine and TMDB movie does or method does。

 but I do want it to be called， I do want it to be called with the right parameters and as long as my controller action does that。

 then the controller action itself has fulfilled its goals and so。That is。😊。

That is the goal with finding a seam， we separate out that logic， we test it independently。

 we don't care if this method works， and so that is one of the big ideas for testing so any ideas for our last question on why we might need to set this up first before why the expectation comes before the post logic here。

Anydeas on why we might want to write this expectation first？

So this is something that you'll get experience with as you're writing things。In this case。

 this expectation。We need to set it up first because we need to essentially fake our find in TMDB method and so expect method name to receive is going to create a fake method behind the scenes using all the magic that Ruby provides and it will essentially track for you whether that method is successfully called。

And so how it works doesn't really matter。Our spec has given us a tool。

 It's going to count whether this method is called。

 It's even going to track for us that we passed in the right arguments to our method。

 And as long as we did that， this method will pass and so。

This is one technique for making your tests both independent repeatable and a little bit faster as well。

 and so that's where we'll leave things for today， testing will be a component of the next homework assignment which will be up as well today but that will be due Sunday night。



![](img/ce53b82a2a385784dac80cbbd0fdcbe5_7.png)

Thanks。好好好好。If that's wrong。咁日你早紧去啊大。Okay know know。't It doesn't work my use。

 but I I submitted a version。嗯。Okay， and I thought a perfect audit。So I just want to answer her now。

Work my。Yeah like。As long as you submitted it， or it should， it should be fine。

 Did you submit again with a notable version or localcause submitted it。 Okay， yeah， yeah。

 so the version that you submit will be fine。 Yeah， yeah。Oh and if not， then just when it's open。

 you could post a private note something happens to your score， but you shouldn't need。 Oh， yeah。

 I was one。 Yeah， I was working on it for like a couple of hours because I can't figure out how it event。

 And then Jeremy told me there was something wrong with the URL。Yeah and。

Ill just work course for that。Whats different between like two programs。Yeah like they， you know。

 Ki was interact with their website。 Yeah， so。The difference is that。

So they both get used together and。Cucumber so cucumber is the。The piece of the stack。

 so testing when we're doing these interactive tests sort of involves。

I have two different pieces operating at once， which is。



![](img/ce53b82a2a385784dac80cbbd0fdcbe5_9.png)