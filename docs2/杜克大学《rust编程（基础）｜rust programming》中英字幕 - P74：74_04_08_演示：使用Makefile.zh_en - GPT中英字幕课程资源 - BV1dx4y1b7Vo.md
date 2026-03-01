# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P74：74_04_08_演示：使用Makefile.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/e0fa15077621c5744ef185542eaeeded_0.png)

Back in our CI U library， one of the things that we haven't done and so far we've been calling cargo the tool and we've been doing several different things on the command line。

 but there's one thing that we haven't done and that thing is green a make file in a make file very quickly we're going to agree one here。

And the make file will allow you to normalize what you're doing with your project in such a way that regardless where you what projects are you using if you're always using a make file with the same commands。

 you'll have an abstraction that can help you build a normalized normalized processes around your tool。

 but that might feel very abstract， so let's get started Now one of the things here that is interesting is that because we have compiled enabled。

 we're going to be able to go pretty fast and build something that is really nice。So first。

 we are going to， let's just write some some sample targets， as they' are called in in a make file。

 So we can say clean and that could be。We can do cargo cargo clean and then that's fine。

 and then we can we can create like build and then call cargo build。

 So these right here are called targets and when you run them when you run these targets these are think about these as a subcommands so the way the way this would work is that these would get executed。

 So whenever you're calling clean cargo clean would run whenever you're calling build cargo build will run and we can try it really quickly on the terminal so let's toggle the terminal。

 let's get rid of the Exper for a second and we can say make make clean actually let's just bring the explorer because I want to show you something see target target should go away once I say make clean。

Target went away if we say make build。Cargo bill will run cargo Bill。

 Do you see these cargo Bill will run cargo clean will run and things are getting executed。 Okay。

 so that that is very basic And understandably so you might think， well。

 how much am I gaining here for doing things like just abstracting a command that is really literally there's almost the same typing as as the ability of just saying cargo clean。

 Like there's no difference。 Let's keep exploring。 and let's see by the end。

 we have something that is worthwhile one caveat of writing your make file in this way。

Is that you might not know what or all of the targets are。 So let's try to make that better。

 Let's go into first list's is usually a good idea to。Say what shell are we going to be using。

 So we're now tying ourselves a little bit with system dependencies and we are going to default like that phony means that we're going to default to an action。

 like if no arguments are getting past。 we're going to default to a target。 In this case。

 compilepir thinks that cleanbu would be good， but I don't want that I want to do something else that I think is going to help us no pun intended。

 help us try to get things documented。 So we're going to create a help target。

And this help target instead of， instead of like doing it like this like copal suggesting。

 I want to do something， something different。 And this this is a very nice way。

Of dealing with help targetrg that it will allow me to and this is exactly what I wanted from coppilot。

 so let's take a quick look at what we have here。 This doesn't look this doesn't look very good but what is going on here。

 let's go step by step we're going to parse the whole make file So that's that gripping is using this regular expression we're going to capture everything that is a character and everything that is separated by two hash marks and we are going to then sort them out and then we're going to use Og and the the Og command is going to parse every line that has those two characters and then it's going to print with some coloring。

 those are ans scapecodeats and will allow us to use coloring and then the extracted things will。

Ped like that。 Now， that sounds very abstract。 However， there's nothing like trying it out。

 So now we don't need the Expr， but we can use the terminal。 And now we can say， make help。

 make help doesn't do anything。 So why is that？ Well。

 Because now we need to actually document what we're doing here。

 So we're gonna to clean the project using cargo。We can actually say。Cargo with lowercase。

 and this one would be。Build a project using cardgo。 I'm going to save that。

 So what does this mean that by separating this double comment or double hash mark or miracle sign。

 what we're going to do is going to document the actual the actual target。

 that was not want I wanted to say subcom， but that's not， that's not quite right。

 So let me make sure that I've saved the project now， if I do make help。

Now we'll have this niceed documented output of our make targets now remember we added that phony。

 that means that if I don't pass any arguments， if I just say make it will default to using help。Now。

 this is all very good and you can you can keep adding more targets if you want to， you can say Li。

And Linda project using in cargo， there's a format。You know， format。

 you can do that and format will do a cariggo format。

 Now there's a way that you can even make this a little bit better because sometimes clippy is not installed。

Before that， let's just make sure everything works。 Everything's very well documented。

 so we're making some progress there。 Now certain certain components like Cy need to be installed。

 and I'm implicitly relying on them。 So what would happen if I'm relying on these and I want to run some CicCd or automation for my project then thesecs where we're gonna to start seeing the make file shine a little bit because we can abstract things inside the make file。

 So let's do make format and see what happens。 So make format says cargo format is not installed for the tool chain So we have to say rust up component at rust format。

 So instead of adding it here and then running the make command。

 I can just make it part of I can just make it part of the the abstraction。

 So we'm gonna say component at rust format looks correct。

And then I am going to make it go to dev null。 So if any output goes there。

 I don't really care about like seeing that output every single time。 So now if I say make format。

It will just work。 and my code will be formatted correctly， and it will ensure that this is not seen。

 So what is one of the the the great things about this abstraction is that whenever these runs on an automated unmonitored or unmanaged automation system like on a CicCD system or a pipeline。

 you call make format like these， it will just work。 Now， you feel free to call this FMT as well。

 that's fine。 and。And that will double just work work correctly as well。

 So you start building this automation and making sure that these things are correctly。

 correctly working。 And you can make sure that clippy is the the same， the same way。

And then that's good enough。 Now， let's take it a step like a step beyond one thing that I really like when I'm releasing is or when I'm creating new versions of my project that we will see later is I want to bump the versions。

 If I go here to explorer and look at cargo Tail the version and this is by default fold you get a0 that1 that0。

 So let's just make sure let's just assume that I'm building a0 that1。1。 And instead of coming here。

 making that change， making sure that I got it right。

 you can actually build some automation and put it in the make file as well。

 Now I've already written that so that you don't see me fumble while I try to write all of these but that is this bump target。

 So let's take a look at what's going on here， there's a lot of stuff going on。 So first I'm saying。

 hey， the current version is this one， there's cargo package I right so let's see what cargo。

Package I does and it will print that file and it will say so that's parsing this thing right here that'0 that1 that0。

So then I'm gonna get prompt for a new version。 That's what read dashp does。

 and then I'll slap that into I'll use that into the updated version variable and I'll do cargo package I again and I'll cut and parse and extract that and I'll do that replacement then I'll do that replacement to cargo that Ta and find exactly where that line is and then I'll say hey。

 the new version by the way is this other thing here with package I So why don't we run that and see what we get So toggle terminal and I'm going to I know it's getting very crowded in here。

 but I want you to I want to show you the cargo that Ta how it changes So now I'm gonna say make bump。

Current version is0 to1 to0， which is correct， I want0 that 1 that1。And new version is well。

 this is not correct because the file， the file is just modified。 So that's definitely a bug。

 But if I go here to cargoel， you'll see that my version got updated which is pretty neat。

 Now I also get these cargos dash E， which is the previous version and you can certainly build more onto that make file to get rid of that or prevent that extra file being created。

 but this is like a safety measure that is nice to have if you're messing up or or your writing code that messes up completely the cargoel and you want a way of getting back of course。

 if you have version control， no big deal， you can always revert。

 So that is that is the make file and start going to close all of these things So like we can take a look at this make file and you can normalize these across all of your different projects。

 if nothing else， I would 100% suggest doing the。Help target default into that。

 making sure that you have some shell support if you don't have that。

 you might get problems when you're trying to execute some commands。

 but this is already very good now。Make sure that you're using make file in a simplified way。

 if you require lots of logic or executing things that require multiple different things to be running。

 while that's going to get a little bit more complicated but off the bat。

 you can you can start normalizing these， and these will make。

Managing all of your Ru projects as well as other projects as well with otheral languages in a normalized way that then you can use to build on CICD。

 continuous integration， continuous delivery systems。



![](img/e0fa15077621c5744ef185542eaeeded_2.png)