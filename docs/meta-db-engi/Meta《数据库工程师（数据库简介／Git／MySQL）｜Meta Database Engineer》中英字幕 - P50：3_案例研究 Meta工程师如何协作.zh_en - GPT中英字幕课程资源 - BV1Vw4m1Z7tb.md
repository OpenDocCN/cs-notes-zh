# Meta《数据库工程师（数据库简介／Git／MySQL）｜Meta Database Engineer》中英字幕 - P50：3_案例研究 Meta工程师如何协作.zh_en - GPT中英字幕课程资源 - BV1Vw4m1Z7tb

An interesting fact about collaborating on projects at MeA is that engineers drive every project at MeA。

 they're in charge of coordinating with product， data scientists。

 researchers on what we're building and the timelines for that。

 whereas another company's product managers or leadership is often in charge of each project。

I'm Leila Rizby， I'm a backend software engineer on Instagram calling in San Francisco In this video I hope you learn that effective collaboration is important for engineer success at meta and learning how to use version control at meta is also very important as a backend engineer on Instagram calling for my role I collaborate with other mobile engineers in my department on a daily basis so that we build the best products together I also collaborate with Instagram messaging a lot because calling and messaging are closely tied I also work with non-engineers like product and data scientists regularly as well to collaborate effectively with my cos we message each other on chat to unblock one another but when something warrants a meeting we schedule a meeting when something warrants a document we collaborate together on a document with comments and leave notes for one another。



![](img/1669a38f5b875445f78ff53c55142fcb_1.png)

![](img/1669a38f5b875445f78ff53c55142fcb_2.png)

![](img/1669a38f5b875445f78ff53c55142fcb_3.png)

Version control for Instagram is interesting because we have one giant monolithic repository for all of our code for backend。

 that means that whenever I'm making a change， the code that I'm writing and is shared with every other Instagram team it is risky in some ways but it's also nice in others so I can reuse their code the other thing that's interesting about version control meta is that any engineer can approve any change metata。

 they're big on this saying that nothing at Meta is someone else's problem so that means that any engineer can actually work on any change that they want to work on version control at Meta is a little different than version control at a lot of other places while metata has a giant monolithic repository for our code where we continuously release our code。

 many other companies have smaller repositories called microservices for each team so each team has their own codebase and only they work in it they use branches so that they can take their code and merge it back。



![](img/1669a38f5b875445f78ff53c55142fcb_5.png)

Like the master branch for their team or product this is great for smaller teams in some ways but it has its cons in that you might run into a lot of merge conflicts at metata because we have so many engineers there would be too many merge conflicts if we had branches for each team in the company Some collaboration challenges for version control on my team is that because we use a monolithic repository merge conflicts happen a lot so we try to write smaller changes so that we can easily revert them。

 we also try to add a lot of gatekeepers so that if we ship something to production on Instagram we can easily turn it off without waiting for any rollback We also share our code with messssenger calling so we also have to add a lot of tests a messssenger doesn't break us Gitlame is a way for us to look at the revision history for files it helps us so that if I'm looking at a line of code and I don't understand it I can figure out who wrote that code and reach out to them I can also figure out what they were trying to do。



![](img/1669a38f5b875445f78ff53c55142fcb_7.png)

![](img/1669a38f5b875445f78ff53c55142fcb_8.png)

In that code they write a message saying what the change is for it's also great so that I can figure out what changes to revert if I'm trying to revert a change I use it every single day when I need to understand what some code is doing I'll reach out to the point of contact that wrote that code which is especially helpful at meta where there's so many engineers I often don't know the person I need to get a hold of so seeing their code helps in this video I hope you learn that learning how to work together effectively and collaborating well as well as learning how to use version control effectively is critical for success at meta getting a diverse set of perspectives on what features you should build who you should build for what a feature might need or how it can improve is really helpful and the rewarding part is that your end result your project ends up being better。



![](img/1669a38f5b875445f78ff53c55142fcb_10.png)