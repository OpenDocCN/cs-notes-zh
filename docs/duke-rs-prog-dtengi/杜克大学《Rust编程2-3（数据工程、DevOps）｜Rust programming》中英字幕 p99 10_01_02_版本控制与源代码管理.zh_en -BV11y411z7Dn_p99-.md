# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p99 10_01_02_版本控制与源代码管理.zh_en -BV11y411z7Dn_p99-

![](img/cf409bd0bdd9e920fc795be38ef72f56_0.png)

Berstion control and source code management in general is essential and not only in applications。

 but as you will see later， when we're building automation。

 when we're creating projects that are going to help us produce a pipeline something that will allow us to deploy something to production is critical because it allows us to have things like identify when when something happened and in this case this is yesterday and the first first commit was five days ago and all of these are allows us to pinpoint exactly where where in time was a change made and let's take a look at why this is also important So let's go to some of these commits。

 I'll click here and commits this application doesn't have that many commits So let's say for example we have here。

Severaleveral commits group by day， which is an interesting way of grouping。

 but it allows us to try to understand more when a change happens。

 So let's just assume that something weird started happening here that wasn't happening in August 18 so we have the working functional test commit and then things started to be slightly odd like let let's take a look we have the identify right there so we can actually see when when that commit happened。

 what are some of the changes I'm going to click there and we're going to see that several different things started changing well some of them are not that complicated this just change position the red here indicates that that was eliminated and the green is that this is added that effectively means that this was changing position now let's take a look at the message and add working function。

okay so that sounds okay， but we also see that there's some dev dependencies that came in。

 so that is not clear by the the message of the commit So that's something to take in mind when you're making changes like thiss I tend to prefer to have more granular changes that actually capture exactly what's going on Some other folks tend to group things together and that is also a fine approach is just just have to pick a strategy and go without one。

 I tend to have granular commits and we'll see in this case that we'll find surprising things like dev dependencies are getting at it。

Alright， so if we continue going down， we're going to go to the actual application in this case and we'll see more reorganizing of imports here at the very top。

 but more importantly we're seeing that some of the application is changing so we're getting that this attribute in rust is getting removed and that is kind of like surprising so usually in these web framework for rust。

 which is acts it requires or one of the ways of exposing the routes is by using this attribute right here at the very top。

 So by removing that。That seems to imply that that could be problematic because then how is acts。

 which is the webframe we're going to understand that this is something that it needs needs to expose at the s health So let's take a quick look here we're gonna to keep scrolling and we're going to identify some of the changes here we can see it also happens on the slash redact。

 but remember that this change was to introduce functional testing。

 we see also that when it's setting up the httP server。 certain things are changing。

 It's no longer using redacting health。 the functions directly。

 They're getting configured with these web resource call So one is slash redact and slash health is here and one is post and the other one is a get and it maps directly to this function。

 so that sounds reasonable。 let's keep scrolling and we will find functional tests addition so were。

ing to see that there was an addition to get some changes in and why am I describing all of these changes because this is what allows us to identify what changes went in and when and how effectively changed the application not only that do you see how this is getting removed and all of the green is getting added So if we scroll I'm going to scroll all the way to the top and then go4 change files。

 60 editions， when we identify that something is not quite right。

Version control and source course management allows us to go back in time。

 we could actually go back to the list of commits and say well。

 these set of commits and this set of changes， a single commit and several changes once problematic and custom problems。

 we can actually go and change our code base and go to this one right here or even go backwards to to some of the initial state of the application。

And here with the GiHub service with the GiHub website we are actually can browse that state so I can actually go to the first initial commit。

 so let's take a look at how that main thatRS was much more different so we can see I'm going to scroll all the way to the bottom do you see the tests of course not because we don't have tests at that point in time and we can actually go and revert those changes easily。

One thing that happens when you don't have source management or version control is that this is not exactly possible if you were just copying files around and pasting them and sharing them around。

 you wouldn't be able to attribute changes to someone specific in this case this is a project of mine so Im this sole contributor however if you were collaborating with 20 30。

 50 people， different people or a big team or even just two folks collaborating the same project who change what and at what time and that is actually not entirely possible if you don't have source management。

So some of the core things that version control gives us， it allows us to identify changes。

 not only the changes， but at what time they when and at what time they happened and who made them and allows us to roll back。

 go back in time when we identify things are not quite correct and sometimes historically。

 it allows us to go and do a little bit of investigation as to let me see like the implementation a year ago and let's see how that looked。

 that would be completely impossible if we were just looking at plain files and sharing them around。

So in this case this is a rust project and we're able to see some of that activity in bigger projects is even more critical and when you're talking about DevOs principles。

 it allows you to build infrastructure and build configuration changes that can also be be in source control because the same thing that applies to software can apply to configuration settings in the past when I've managed big infrastructure changes。

 I've also used GitHub to try to capture those， remember those and make sure that whenever there's a change that is accurately captured with version control so that I can have that granular policy or process in place that allows me to make a decision or flexibility if I also want to go back。



![](img/cf409bd0bdd9e920fc795be38ef72f56_2.png)