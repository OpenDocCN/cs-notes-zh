# 密歇根大学《给所有人的PostgreSQL课（数据库设计、SQL、JSON和NLP、ES）｜PostgreSQL for Everybody》中英字幕 - P108：7_第二代云计算应用.zh_en - GPT中英字幕课程资源 - BV1tj421U7GK

![](img/26f4446a8c88d7b8d371bc43e15c6579_0.png)

So now I want to talk about the second generation of cloud scale applications。

 Gmail and Google search were kind of the first generation。

 the second generation would be like Facebook and Twitter。

 they have a more challenging problem and that is we weren't all looking at our own little corner of the world with very simple interactions between people again Gmail。

 we got our little mail every once a while send a message or get a message but most of the time we're like reading and deleting our own messages or indexing or searching or whatever and we just kind of we have some little corner and we find our way to that corner of the cloud and then we work in that corner。

But in Facebook you add friends， you got to know who your friends are， you have to add。

 you have to have a way to manage them， you have to find them， you got to approve them， et cetera。

 et cetera， et cetera， there's very complex privacy rules and once you sort of start doing social media。

And if you go into Facebook and you go search， you're not searching all of Facebook。

 there's not one search the way there is Google， one search。

 you're searching your view of the world and so now you've got to create like a what search index for every single person so that you can type that and。

And so we are going to shard it， we're going to replicate it， you just can't use a database， RDMS。

 you can't use a single database instance for this。

 and so the idea is is now we're going to shard it the way we do for Google and youve got your little corner but what we're going to do is we're going to find ways to get the data to migrate to you so。

If you're Facebook， you want to make it so that when you log in。

 the thing you see can be shown to you efficiently without going to 10 servers so you don't need it's not like Google own  a0 servers of search。

 you're going to one server and you're saying what's new， what's my status， what's my timeline。

 what pictures came up？And so what they want to do is they want to move these that data to the shard that you're at right。

 and so the idea is then now you post a status update。

And so this is kind of first picture of sharding that I've given you and just imagine that you're you're building Facebook for the first time and we're going to make a and you could even be reusing relational databases and you say。

 look okay we're gonna to do four servers and everyone whose name starts A through F goes to one server。

 G3M goes to another server and through goes to another server and S through Z and maybe there's databases but those databases themselves do not communicate the application is now responsible for moving data back and forth and so Amy's got some friends。

 Greg and Sarah and there's a status so if Annie can log in right now and see， whoa。

 here's your friends， Greg just talked about pizza and Ron can log in torons server and Ron sees all of his status and Sarah sees her status and Greg and so the friends are not in one place the friend list is all over the place and there might be privacy configuration etca。

 et， etc。And so let's just say， for example， something as simple as Annie logs in and gives a thumbs up to Greg's pizza comment。

Now， certainly we've got to send that thumbs up fact to Greg's server。

And so Sarah is also Annie's friend， so I guess do we send the thumbs up to Sarah or is Sarah a friend of Greg。

 oh wait a sec， we probably we probably should have sent that to run， I think。

Because Ron actually is also a friend of Greg， but has Ron blocked Greg？

So you see the problem right so you see the problem there's privacy rules。

 there's whatever and we want to get back to the point where when any of these four people log in。

 they don't have to go to the other servers to pull in the fact that Annie has done a thumbs up on Greg's post and so at some point right you got to get this fact that Annie did a thumbs up on Greg's pizza comment to the right places and so that when everyone logs in they don't have to talk to any other service to see in effect their status line and how many likes and how dislike so this is really dependent on lots of things and you say。

 oh well， if Sarah is a friend of Annie and Annie liked Greg's pizza comment。

Does that mean that we often to have to send Greg's pizza comment to Sarah and the thumbs up and Ron is friends with Greg but not friends with Annie and Greg made a status Greg made the pizza status update and Annie did a thumbs up does Ron see the thumbs up he certainly has to see that Greg's comment because their' friend。

🤧咳。This is hard， Facebook's hard， and this is why the privacy options in Facebook are so complex because I just gave you the simplest example and my head is already like got question marks all over the screen。

Okay。But this really isn't about Facebook。This is about eventual consistency databases and Facebook as an example of eventual consistent databases。

 So there are engineers who are going to try to make this sort of push to the edge。

 And I built some of these applications of what I'll call push to the edge。

 know it's all sharded and you just have to migrate the data replicate the data so that the cost to show you a timeline or a timeline update is as cheap as possible。

 The cost of moving it to 10 different servers because that's how to get to all your friends is cheaper than when you log in to talk to those 10 servers to say。

 oh my friends are on 10 servers。 Let me pull their thumbs ups。 No， no no。

 thumbs ups have got to be there before you log in And so this is very much eventual consistency because you literally could do a thumbs up and it might take5 to 10 minutes before everyone sees it。

 Now， Facebook works really hard to get that latency down but Facebook is absolutely an eventual consistency and you'll notice things like let's make a friend conveniently are done in sort of a two phase where。

Send a note to try to be a friend and then the person accepts the friend and so it's all kind of slowed down so that an eventual consistency database can be。

Can work and so you can imagine that the Facebook engineers are like just every morning。

 they're solving a new problem of how to do this fast and how to move it fast and how to figure out the privacy and how to get everything to the right place that it needs to be within。

 say two seconds or something and you're like， well this' is a big data center and we're talking worldwide right and and there's going to be some central control。

 things like who paid for what ad or something and you know there might even be some combination of database is just using a database that's not like a application wide database is like a common technique。

 it's just is not a problem as long as it's just one database on one server， it's all sharded。

 that's not that's not it because the whole view of it is the base view or the eventual consistency。

And so this is a comic strip from XKCD， and it basically explains what happens to engineers and the person on the left says。

 can you pass the salt？And a the person on the left is waiting for the salt and the person on the left says。

 I said， and the person on the right says，" I know I'm developing a system to pass you arbitrary condiments。

And the person says it's been 20 minutes and the person on the right says。

 it'll save time in the long run。And that is that lots of engineers when they solve a problem。

Over generalize， right to say，ooh， I built this thing for Facebook and it's cool and look how easy it is for me in Facebook to solve this problem of friend list。



![](img/26f4446a8c88d7b8d371bc43e15c6579_2.png)

And then you solve it and it's cool and it runs really fast and then you say。

 I wonder if other people could use this exact same solution and then you say I have a new form of a database。

And so now we'll talk about the emergence of base style databases。

 non asset databases that came out of successful experiments in these second generation cloud companies。

🎼。