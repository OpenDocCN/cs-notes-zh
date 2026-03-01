# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p96 07_01_06_可见性与可追溯性.zh_en -BV11y411z7Dn_p96-

Bibility and accountability is a crucial component of DevOs Now these are not foundational pillars of DevOs explicitly but it is one of the side effects that happens after you start implementing DevOs functionality and systems and processes in place so that your team can function better I want to show you here。

 this is the grip project from anchor which is actually go is not a bra project。

 but the same the same concept that I want to try to explain applies so you can see here that I've opened up a pull request and I found two bugs regarding a component and I'm referencing an issue。



![](img/dcadb24aabe00e07b4a8bb97d9e1be79_1.png)

And I'm telling everyone that by the way， it needs something else to be merged as well。

 Sos that's the rough the rough idea here。 I'm trying to get something merged Now what are some of the transparency。

 some of the visibility things that we can see here Well， first off。

 I'm receiving a very good review。 Alex who is like a very good software developer。

 he's providing me some some output， not output， but some some common。

 some feedback and he is starting to produce very good very good pull request review。

 Now you would argue like well， is this necessary is this level of granularity of feedback coming in and like me asking questions。

 is this a thing that is required。 Well， it is because not only we're talking about code as we're making changes but we're also talking about a system that will。

Track opinions。And track questions that might be clarified for future reference。

 this is crucial because someone can come in and say， well。

 you know this makes sense or might not make sense。

We let me continue here because this is a very rich， I mean it's been a few years。

 this was from 2020， but it's been a few years about this and it's still pretty accurate。

So one of the last comments here is that currently XmL Li is not using the vulnerability extension。

 so it's giving providing more details and I was like very surprised so I said very good catch。

 I thought it was， let me fix that。So not only we're producing code and we're verifying what what has to change。

 but we're actually improving based on my initial take and I'm go ahead and make some changes and I'm going to scroll here all the way down。

And it doesn't necessarily show what is going on here with this project。

 but all along whenever I'm making changes things start to automatically get executed so I'll show you I'll show you here with with actions and grippe is a great example of DevOs in action for accountability and visibility so let's take a look at these we have fill out new version notice so it seems like they're preparing to do certain things and so let let's see why this is why this is useful in why accountability or related to accountability Well things are happening and the transparency is the visibility is right there you can see here that Linux is running Mac is running other CI tests are running and this can accurately point back to a specific commit so if we click on this one。

うん。😊，It will take me to the actual change Why is this useful and especially in the context of DevOs Because if you're in a build process and you're making changes and you're pushing to production。

 you're implementing all of these steps， you want to know exactly what is happening here and you can see that there' are some changes。

 some additions， things are changing here to a new type of variable， you know if something breaks。

 this is crucial， if something breaks if something's not quite working well you can go back to this specific pull request or commit or change set and investigate exactly what was going on so all in all like a a great example of things that can happen with not only with issues but going going back to like a conversation and discussion on proposed changes。



![](img/dcadb24aabe00e07b4a8bb97d9e1be79_3.png)

![](img/dcadb24aabe00e07b4a8bb97d9e1be79_4.png)