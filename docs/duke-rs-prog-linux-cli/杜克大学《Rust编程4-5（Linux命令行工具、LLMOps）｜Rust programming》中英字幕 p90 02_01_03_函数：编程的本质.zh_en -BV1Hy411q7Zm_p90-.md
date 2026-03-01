# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p90 02_01_03_函数：编程的本质.zh_en -BV1Hy411q7Zm_p90-

![](img/16ae250f40c73845a674df67f7b97fc9_0.png)

。When you first start learning to program one of the things that is very confusing is what is necessary suffering and what is useless suffering。

 and this can be a process that can take years to master。

 I'm going to break it down in a way that I believe can help people shortcut this process by。

 let's say five years。 So first up， let's look at what's actually programming and what's essential。

If you think about a function here which has an input in x and a y。

 it does a unit of work and this is， let's say a total which would return back the sum of x and y and then the return。

This is all programming languages。 It could be。Rust， it could be Python， it could be JavaScript。

 it could be Ruby， but the essence of programming is you have a unit of work that takes inputs。

 it does the work， and then it returns back。Anything else other than this is either useless suffering。

 which you should automate or it's optional。 It may or may not be useful。 So first。

 let's take a look at useless suffering。 These are things that you should automate。

 So debugging runtime errors。Really this is not something you should be doing manually when you first start programming。

 you get overwhelmed because you think that you're making all these mistakes。

 well that's true in programming everything's broken all the time but really the role of a programmer is to fix this with automation。

 so you should be using continuous integration， make files， really good Linting tools。

 potentially using copilt or some other coding assistant to help you with runtime errors。

Likewise packaging systems， this is another one that can really confuse people when they're first starting to program。

 they think that using Conda or PIP or some other tool is programming is nothing to do with programming in fact it potentially could be called a bad environment and so many packaging solutions are really not well designed and they're competing with each other and this has nothing to do with programming and so if you feel like you're not making progress。

 it could just be that you're wasting your time spinning your wheels on something that doesn't make sense even for experienced developers so this is something that should be automated as well and it's not something you should spend a lot of time worrying about as a newcomer。

Syntax errors another one， if you're using formatting and Lintin tools that automatically check for this。

 you really don't need to worry about this。 The editor can help you with syntax。

 This is not something you should spend a lot of time on Boerplate code is another one let's say that you're defining a class or you're working with some kind of framework etc the boilerplate code if you don't understand it means nothing this is just useless suffering that can be solved by tools like generative AI for example。

 or maybe a really good editor virtual environments。

 I think this is I would call that a tax in languages like Python where there's a productivity tax because it's a scripting language where you have to constantly remember whether you're in the right virtual environment etc。

 This is absolutely nothing to do with programming and it's suffering that you hopefully can automate logic errors as well once you start building some code Why won't you put some automation in place so that。

You don't have to make logic errors and this is a unit test and if the unit test runs automatically when you' check in your code。

 you don't have to worry about this。 Another one that's actually pretty much solved now with tools like GitHub codespaces is your development environment you shouldn't be spending two weeks setting up an environment this was very common early in my career where a new developer with a master's degree or a PhD would spend two weeks setting up their environment so they're obviously extremely talented but the development environment was horrendous to set up nowadays with tools like GiHub codespaces Doc or etc ce or cloudbased environments it should be instantaneous it's not something you should be spending a lot of time on。

Now let's talk about things that may or may not be useful。

 This is also something that people that are new to programming get confused about is that let's say I would call this a kind of maybe elitist type programr would say to somebody if you don't do object oriented programming you're not programming Well。

 that's just false And the reason it's false is that this is programming and it's not object oriented programming。

 you can do programming that doesn't require objects。

 It's a potentially useful abstraction to do object oriented programming。

 but has nothing to do with learning to be a programr or programming you can solve programming with just an input。

 a unit of work and an output Likewise with concurrency。

 It's very easy when you first get started with programming to get trapped into thinking you should always spin up threads or processes or do async you network IO。

 but in fact that can be a real burden for the problems that you're trying to solve so it may or may not be useful same with complex algorithms。

It's easy to get excited about the most complex algorithm you can think of。

 but initially when you're first starting out， it may or may not be useful to use the best algorithm。

Another one is test drivenn development。 A lot of times you'll hear people who are more I would say like zealots in terms of testing and they will say to you that you can only write a test first before you write code。

 that's simply not true this may or may not be useful for the project you're on Also frameworks a lot of times people confuse programming with a framework a framework was written by a third-part developer the framework may or may not be useful if it's a web framework or Camme and tool framework In fact it may be so complex。

 you don't understand it。 it doesn't mean that's a reflection on your ability。

 it could just be a bad framework。 Likewise， with project management a lot of non-technical people especially gravitate towards scrum and agile because it's easy to get certifications and then they push these I would say agendas on the developers and developers can feel like they're confused because they're not making progress。

 but the reality is that the methodology itself may just be flawed so it's important to identify。

sSo that you're focused on what's important， which in my opinion， is an input， a unit of work。

 and an output if you understand this and you slowly build up results based on this and you automate the stuff that you can' automate and you avoid doing things that are optional until you actually need them。

 you can probably take a fiveyear shortcut in productivity in your career。



![](img/16ae250f40c73845a674df67f7b97fc9_2.png)