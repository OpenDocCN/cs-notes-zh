# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p85 85_04_06_BigQuery数据探索.zh_en -BV11y411z7Dn_p85-

![](img/bfcaa920e46554256c90e8bcf710dacd_0.png)

One of the more powerful tools on the Google Cloud platform to explore data is BigQury。

 If we take a look at this overview here， we see that you could compose a new query， add some data。

 even upload a local file。 So there's a lot of easy ways to get started。

 but probably one of the most powerful is to use the public dataset。

 So if we go ahead and we take a look at a existing Google trends data set here。

 This is a great way to dive into understanding how to use a particular data。

 The first thing that I typically will do is look at what the metadata is about this particular data。

 you can see it was last modified September 20， 2022。😊，And this is a Google trends data set。 Now。

 if I wanted to go ahead and query it， a good way to do that is to go to the toggle node。

 and you can see the different sections of this particular data。 And in particular。

 let's say I wanted to look at some top terms。 right， I could look at you know， term。

 weak score rank， those kinds of things to figure out you know。

 what it is that I actually wanted to do。 In fact， if I just select this term。

'll it'll actually try to figure out a query for me automatically。

 So there's really not a ton I have to do to query， for example。

 you know a top term and look at maybe the the first 10。Items here from this particular data set。

 you can see Lakers are really popular right now in terms of terms because they're playing in the playoffs。

 Similarlyly， if I want to look at score， rank， etc cetera。 I could do the same thing。

 So what we can do here is start off with making a query that shows us a little bit more detail。

 So let's go ahead and close this， close this。And what I'm going to do is I'm going to format a query here that will show me you know the different top terms and even maybe make it a little bit cleaner。

 So if we go through here and I say let's go ahead and put a select here， select term。

 and let's look at the refresh date as the top date。

Let's go ahead and look at different times between 2023401。To 2023，417。

 and let's do a limit of 100 here。 And also， if I go to more， I can even format my query。

 So this is often a good idea to format it if you want to save the query and you can even go save as well。

 and this is nice because you can call it something like you know top terms。

 you know whatever it is you want to do and and go from there。

 and I can reuse it over and over again。 So this could be actually something that data scientists may want to run on a regular basis and they could just tweak it to run it。

 if I go through and I run this， you can see here that I've got all the different top terms here over this particular date range。

Here we go， and I could actually go through and look at you know whatever time in history。

 you can see there's lots of key terms that people are interested in looking at across you know popular culture。

Now， one of the things that is a kind of fun thing to do once you've got a data set like this is to explore the data further。

 right， So as a data scientist， if you're going to build a machine learning model。

 a lot of times you need to first look at the data even beyond just a SQL query。

 And this is where these other features come into to play。 So let's go ahead and take a look at this。

 and we click on explore data。Notice I have three options。

 A spreadsheet is actually a pretty good option for many scenarios。

 I also could open it up with coab notebook and do some queries， which also is a very good option。

 I also could look at it with a dashboard type tools。 So let's go ahead and look at this first。

 let's go ahead and look at Looker studio。 And if I dive into this Looker studio here。

 It'll give me some default queries， I can actually go through and look at different you know fields and terms。

 etc ceter。 and and query from there。 And if I wanted to as well。

 I could save this and I could share it with somebody else。

 So really a great comprehensive story here for doing exploratory data analysis。 Now。

 let's dive into a little bit more， though， beyond just these things that we've showed initially here。

 So one of the things I'm going to do next is I'm going to look at other data sets。 So notice。😊。

In this public data set here that I'm in the Google trends and I'm looking at top terms but what about like international top terms or top rising terms or et Well I've already got a query here that I'm going to go ahead and throw into this window and I'm going to put it in right here and I'm going to actually save this query and I'm going to call this one same thing top terms here and if I go ahead and run it you can see that this is actually in international top terms query and again we see that this is from 417 you can see all the different top terms here and very different results so again if I want to take that put it into Looker Studio this would be a good way to do it。

Another thing we can do， though， beyond just this particular dataset is look at other dataset sets and find new information about it and maybe combine those different sources。

 So you can look through here。 There's a lot of different data sets to play with Google ads。

 Google Cloud releases， political trends。 know lots of different things here。

 I'm going to take one that is kind of a fun one to play around with， which is hacker news。

 And if we take a look at hacker news。 we can see that this data contains all the stories and comments from hacker news from 2006。

 So this is kind of a smaller aggregator that aggregate stories and a lot of tech people are interested in this particular data。

 And you can see here that。It's pretty new as well。 So this is last modified September 20， 2022。

 And so we could be able to find some really cool information。 Let's say the stories， right。

 if I want to go through here， I can see the fields again。

 So it's always important to first look at the schema and see what are the different field names that I would want to care about for example。

 the story score would be a good one right， Like how powerful is the particular score know what are the most popular stories of all time and what have they actually scored。

 What's the median score， What's the 25th percentile， What's the 75th percentile。

 All these kind of descriptive statistics are helpful when you're first looking at things。

 So that's the one I'm going to query here。 So I'm going to go over to query and let's put this into a new tab and again。

 it gives us kind of a default here。 But I already have a query that I'm going to start with。😊。

Which is I want to look at the top stories that have ever been created on hacker news。

 Let's go ahead and query this。 Here we go。 select ID。

 We're going look at this as a readable time so I can look at the timestamp and we're going query by the story type and we want to have a descending query here。

 So this looks pretty good。 again， I can just format it to make sure everything looks good。

 Oftentimes that's a good idea to just make sure you've got the syntax correct。 And again。

 I could save this and we could save save query and we could call this you know top。Hacker news。

 stories， something like that。And we can go ahead and save it next up。 I select run。 and again。

 it's going to go through here and give us this nice query。

 Now this is a little more rich if I was going to do some natural language processing because we've got the author here。

 We also have the scores， which is now getting very interesting right。

 we see there's 6000 here 4000 right and you can see there's some really big differences between even these top 10 scores right。

 this seems a little bit unusual。And notice that we see a trend as a data scientist right。

 we see that Stephen Hawkins has died。 That's one of the top stories of all time。

 Steve Jobs has passed away， one of the top stories at all time。

 if we look at people leaving companies you can see that there's a certain kind of a style where maybe people are looking at stories and if we look at maybe even more let's look at 100 stories do we see even more information that we we can dive into and we can see Google searches dying so you basically there's some stories here that are very interesting that you could dive into。

Alright， so let's go ahead and explore this data a little bit more。

 and I'm just going to go through here and I'm going to look at 10 here。

And I'm going to run that query again。And then I'm going to go ahead and I'm going to explore the data with Loer Studio。

And from here， this is where I could dive into the details a little bit more as well。

 where I could look at particular you fields or look at ways to you know manipulate the data So for example。

 now this is the author but the ID doesn't give us anything this is not something we care about So instead if we want to go down here where it says some of the I that doesn't make sense。

 we want to actually maybe maybe we care about the sum of the score right that's probably what we care about more likely and so I could go ahead and change that query and get a different result inside this visualization similarly if I wanted to change this one know maybe I would go through here and I would change instead of by the ID here maybe I would change by you know some other field So you can go through here and query different fields。

 create different visualizations very easily by using this and again share。Out with another person。

 But this does get me thinking here since we see these are the scores here is。

 you know what can we know about this particular data set if I wanted to create a predictive model。

 I there you know a linear relationship between scores or is it like a power law。

 theyre like really popular stories and not popular stories。

 So one of the things that we can do next is go back to this hacker news query here。

 and let's actually。Pull up a query that looks at the quartiles， right。

 And so this would be a fun thing to， to play around with， which is。

If I want to go ahead and create a new window and we can take a look at this。 It says with quartiles。

 let's go ahead and figure out four。And let's let's actually figure out a first quartile， first 25%。

 second 25%， which is the median third quartile and the fourth quartile。 And let's actually look at。

 you know what is a good way to look at this particular data set。

 So if we go through here and we say save query。 we can look at hacker news quartiles。And from here。

 what？We make it as a result is shocking。 so we see there's a bug here。

Let's go ahead and format this。There we go。 Let's go ahead and run it。 There we go。

 We've got a result。 So what we see here is that's。

 what's kind of strange is that in terms of the the first quartile， right， the first 25%。

 a lot of stories are low。 The median is is extremely low as well， right， Like the typical story。

 right， which is where the median is 50% are below this， that。

These are actually also very low scored。 75% of the stories even have a score of three。

 But in this top 25%， you can see here that theres there's a very small percentage of stories that get really。

 really high scores here So we can see here from from the fourth quartile。

 So we can potentially consider this information when we want to create a model and even model things out in a way that looks for maybe like hit stories if we were going to use this data to do some other kind of prediction model。

 So really， that's a good way to get started with the big query engine on Google Cloud you know。

 doing SQL queries， iterating with them back and forth and then also going into tools like Looker。

And then saving those results and then sharing them out with other people on your team。



![](img/bfcaa920e46554256c90e8bcf710dacd_2.png)