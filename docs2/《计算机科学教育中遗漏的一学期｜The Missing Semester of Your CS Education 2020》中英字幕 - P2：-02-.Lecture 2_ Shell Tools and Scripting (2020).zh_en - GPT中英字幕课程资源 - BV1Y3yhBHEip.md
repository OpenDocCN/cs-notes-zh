# 《计算机科学教育中遗漏的一学期｜The Missing Semester of Your CS Education 2020》中英字幕 - P2：-02-.Lecture 2_ Shell Tools and Scripting (2020).zh_en - GPT中英字幕课程资源 - BV1Y3yhBHEip

啊。Okay， welcome back today。 we're gonna cover a couple separate like two main topics related to the cell。

 First we're gonna do some kind of cell scripting， mainly related to bass。

 which is like the cell most of you will start like Mac or like most Linux systems as the default cell。

 and it's also kind of backward compatible through other salt like CC pretty nice。

 And then we're gonna cover some kind of other cell tools that are really convenient So you avoid doing like really repetitive tasks like looking for some piece of code for some elusive file and there are kind of really nice building command that will really help you to those things。

😊，So yesterday we already kind of introduce you to the cell and like kind of like some of its quirks and like how you are executing commands directing them。

 they're going to kind of cover more about like the syntax of what are like the variables。

 the controlflow functions of cell。😊，So， for example， once you're kind of drop into a cell。

 say you want to kind of define a variable which is kind of of one of the first things you learn to do in。

In a primary language here， you could do something like P equals bar。

 And now we can access the value of foo by doing dollar fo。And that's bar perfect。

 one  query that you need to be aware is that like spaces are really critical when you're dealing with bars。

 mainly because spaces are reserved and that will be for sean argument。 So for example。

 something like P equals bar won work and the cell is going to tell you y is not working is because the full common is not working like full is not exist and here where it's actually happening were not assigning fu to bar what is's happening is we're calling the full program with the first argument equals sign and the second argument bar。

😊，And in general， whenever you are having some issues， some like some files with the spaces。

 you need to be careful about that。 you need to be careful about like quoting strings to that。

 So going into that， how you do strings in bass， there are two ways that you can define a string。

 you can。Define strings using double quotes， and you can define strings using single sorry。

Is in single quotes。However， for literal strings， they are equivalent， but for the rest。

 they are not equivalent。 So， for example， we do。Equals dollar。Value is dollar full。

The dollar full has been kind of like expanded like string sensitivity to the value of the full variable in this cell。

 whereas if we do this with a simple string，We are just getting the dollar full as it is and like single quotes won't be replacing and again。

 it's really easy to kind of write a script， assume that this is kind of like Python that you might be more familiar with and not realize all that。

This is the way you will assign variables， then bath lot of like control flow techniques that we ci later。

 like four loops， while loops。 And one the thing is you can define functions。

 and we can access like a function they have defined here and here we have the MCD function has been defined。

 and the thing is so far we have kind of seen how to execute several comments by piping into them so that briefly yesterday。

 But a lot of time you want to do first one thing and then another thing。

 And that's kind of like the sequential execution that we get here here， for example。

 we're calling the MCD function。 and。😊。

![](img/39bd3610e0a9db5421dd0a55406b48ab_1.png)

We first are co with the me their command， which is like creating this here Do one is like a special variable。

 and this is the way that bass works whereas in another scripting languages that will be like RV。

 the first the first item of the array R toV will contain the argument in Ba is dollar one。

 and in general， a lot of things in Ba will be dollar something and we be reserve we will be seen more examples later。

 and one we have created the folder we C into the into that folder。😊。

hich is kind of like a vaguely common pattern that you will see。

We will actually type this directly into our cell and it will work and it will define this function。

 but sometimes it's nicer to kind of drive things in a file and what we can do is we can source。



![](img/39bd3610e0a9db5421dd0a55406b48ab_3.png)

This， and I will execute this script in our soul and load it。 So now it looks like nothing happened。

 But now the MCD function has been defined into our soul。 So we can now， for example。

 do like MD test。And now we move from the tools directory to the test directory。

 both like we created the default folderer and we move into it。

What else so a result is like we can access we access the first argument with dollar one。

 there's a lot more kind of reserve comments。 for example。

 there0 will be the name of the script Do are2 to through Do9 will be the second through the ninth arguments The deviceva script takess Some of these reserve keywords are more can also kind of be regularly used in the cells。

 for example。Dollar interrogation mark will get you the error code from the previous command and which I will also explain briefly but for example。

 dollar underscore will get you the last argument of the previous command so another way we could have done this series we could have say like n K mete test and instead of kind of realwriting test we can access that last argument as part of the using the dollar。

Dollar underscore。 like that will be replaced with test。 And now we go into test。嗯。

There are a lot of them you should kind of familiarize with them。

 Another one I often use is kind of it's called B bang。 You will run into this whenever you。

 for example， are trying to create something and you don't have enough permissions。

 then you can do pseudobank bang and then that will replace the command in there and now you can just try doing that。

 and now you will pro you for password because you have pseudo permissions。And。

Before I mentioned the kind of the error command yesterday we saw that in general there are like different ways a process can communicate with kind of other processes or comments。

 we mentioned the standard input which was course like less than like getting stuff through the standard input getting putting stuff into the standard output there are kind of a couple more interesting things it's also like a standard error stream where you kind of write errors that happen with your program and you want to pollute the standard output it's also the error code which is kind of like a general thing in error programmingming languages of like some kind of way of reporting how the entire run of something when。

So we do something like Eco。Hello， and we。Like query for the value is 0。 And it's0。

 because everything went， okay。 And then one where any issues and a0 X code is the same as you will get in a language like C。

 like 0 means everything went fine。 There are no errors。 However， sometimes things won't work。

 Like sometimes like if we try to grab for。Fub bar in our MCD script。

And now we check for the value is one。 And that's because we tried to search for the fullber string in the MD script。

 and it wasn't there。 So like， grab doesn't print anything。

 but lets us know that things didn't work by giving us like a one error code。

And there are some interesting common like true， for example， we always have。

0ro error code and false will always have one error code。

And then there are like these logical prayers that you can use to some sort of like conditionals。

 For example， one way， you also have Es analysis that will s， but you can do something like false。

And Eco Oops fail。 So here we have two command connected by these or operator is where Ba is going to do here is going to execute the first one。

 And if the first one。The order is gonna execute the second one。

 So here we get it because the like it's gonna try to logical or。

 if the first one didn't have a zero error code， then it's gonna try to do the second one。

 Similarlyly， if we instead of use false。 we use something like true。

 since it's true will have a zero error code， then the second one will be short circuit and we don't。

 it won't be printed。Similarly， we have an an operator which will only execute the second part if the first one like run without errors。

And this same thing will happen if the first one fails。

 then the second part of this statement won't be executed。Kin of not exactly right to that。

 but another thing that you will see is。Then no matter what you execute。

 then you can concatenate commands using a semicolon in the same line。

 And that that will always print。Beyond that what we haven't seen， for example。

 is how will you go about doing kind of？Getting the output of a command into a variable。

 And the way we can do that is doing something like this where。

 what we're doing here is we're getting the output of the PWD command。

 which is just printing the present working directory where we are right now。

 And then we're storing that into the full variable。So we do that and then we ask for who。

 we wear our string， and more generally we can do this thing。Call common substitution， or。

By putting it into any string and since we're using double quotes instead of single quotes。

 the thing will be expanded and it will tell us that we are in this working folder。

And interesting thing is right now， what this is expanding is to a string instead of kind of like this is spending as a string。

 and if the and like less non tool is called process substitution。

 which is kind of similar where we will do。In。It will here， for example。The less than parentheses。

 some command and then another parentheses that we do is that will execute。

 that well get the output to kind of like a temporary file and you will give the file handle to the command。

 So here what we' are doing is we're getting where a less in the director kind of putting into a temporary file doing the same thing for the parent folder and then we're concatenulating both files and this we might be really handy because some commands instead of expecting the input coming from the SDN they are expecting things to come from some file that is giving some of the arguments。

So we get kind of both things concatenated。诶。Thing like so far there has been a lot of information。

 Let's see kind of like a simple like an example script where we see a few of these things。

 for example here where having like a string and we have kind of these dollar date dollar date is a program。

 So again， thiss a lot of programs in Uni you will kind of slowly familiarize with a lot of them data just prints what the current data is and you can specify different formats。

😊，Then we have this dollar0 here， dollar0 is the name of the script that we're running。

Then we have dollar has， that's the number of arguments that we are giving to the command。

 and then dollar dollar is the process I of this command that is fine。Again。

 there's a lot of kind of these dollar things they are not intuitive because they don't have like a mnemonic way of remember maybe dollar has。

 but it can be you just kind of will be seeing them and getting familiar with them here we have this dollar ad and that will expand to all the arguments So instead of having to assume that they say we have three arguments and writing$ dollar $1。

 $23。If we don't know how many arguments we can put all those arguments there。

 and that has been given to like a for。 and the for loop will。In in time。

 get like the file variable and it will kind of be given it one of the arguments。

 So what we are doing is for every one of the arguments were given then the next line。

 we are running the G command which is search for a sub string in some file and we' are searching for the string fullbar。

In the file here， we have kind of put the variable of the file to expand。And yesterday。

 we saw that like， if we care about the output of a program。

 we can redirectact it to somewhere to save it or like to connect it to some other file。

 but sometimes you want the opposite。 Sometimes here， for example， we care。

 we're gonna care about the error code about this grip。

 We're gonna care whether the G runs successfully or it didn't。

 So we can actually discard entirely what the output。

 like both the standard output and the standard error of the Gr command。

 And what we're doing is we're redirecting the output to dev no。

 which is kind of like a special device in in Uni systems where you can like write。

 and it will be discarded like you can write no matter how much you want to there and it will be discarded。

 And here's the kind of the great in symbol that we suggest for predirecting the output here we have like two greater man。

 And as some of you might have guess right now this is for directing the standard error because those two streams are separate。

 and you can have to tell bars what to do with each one of them。So here we run。

 we check if the file has Fber and if the file has Fbar， then it's going to have a zero error code。

 If it doesn't have Fber， it's gonna have a non0 error code。

 So that's exactly what we take in this if。Part of the command we say get me the error code again this dollar question mark and then we have a comparison operator which is an E for not equal。

 And like some other primary languages we you have kind of like equals equals equals these symbols in theyre like of like a reserve set of comparisons and it's mainly because there's a lot of things you might want to test for when you're in the cell here。

 for example， we're just checking for the two values。

 two interiorte values being the same or for example。

 here the minus F check will let us know if a file exists which is something that you will run into very。

 very commonly。诶。Going back to the example， then what happens when we what happens when we go into if the file did not have F like there was like a non CR error code then we print like this file doesn't have any F。

 we're gonna add one and what we do is we echo this like has fullber hoping this is a comment to the file and then we're using the parameters suggest of like greater gradient to append at the end of the file and here since the file it has been fed through the script and we don't know it before and we have to substitute the variable of the file name。

We can actually run this。 We already have like correct permissions in this script and we can give a few example。

 we have like a few files in this folder and CD is the one we saw the beginning for the MC function that have like some script function and we can even feed the own like script to itself to check that like has fullber in it。

And we run it。 and we first we can see that like this different like variables that we solve that has have been successfully expanded。

 We have date has been replaced to the current time。

 Then we're running this program with three arguments， these random as。PD， and then he's telling us。

 oh， MD doesn't have any。 So we are adding a new one and this， the beam。

 the script file doesn't have one。 So now， for example， we to。



![](img/39bd3610e0a9db5421dd0a55406b48ab_5.png)

AndCD has the comment that we were looking for。

![](img/39bd3610e0a9db5421dd0a55406b48ab_7.png)

诶。One other thing to know when you are kind of executing。This script is the。Here。

 we have like three completely different arguments。 but very commonly。

 you will be given like arguments that can be morely given in some way。 So， for example。Here。

 if we wanted to refer to all the dot essay scripts， we could just do something like less。

Astra is dot essays， and this is a way of kind of fine name expansion that most cells have。

 iss called glin。 And here， as you might expect， this is going to say， oh。

 anything that has any kind of sort of characters and in depths with essays。So。

 un surprisinglyprising， we get kind of example sites and ND datas。

 we also have this project one and project 2。 And if they were like we can do like a project。42。

 for example， more。 And now if we just want to refer to the pre that have a single character。

 but not two characters after course， like any other character， we can use the question mark。

 so question mark will expand to only a single one。And we get like kind of。

 were L S in first grade  one and then project 2。In general kind of like the gling can be very powerful。

 you can also kind of combine it。😊，连。A common pattern is to use what is called curly braces。

 so let's say we have an image that we have in this folder and we want to convert this image from P and G to JpeEC or we could maybe like copy it or is like really common pair and have two more arguments that are fairly similar and you want to do something about something with them as arguments to some command。

 you could do it this way or more suly you can just do。I meet the。Open curly bracket， then P And G。え。

Yay big。And here and and getting kind of some color feedback。

 But what this will do is like expand into the line above and actually can like add seaage to do that for me。

 And that what's happening here this is really powerful。 So for example。

 you can do something like we could do thats and like a bunch of foods and all of this will be expanded。

😊，You can also do it at several levels。 and you will do the Cartesian。We have something like this。

 we have one group here， there's like one comma 2 and then here is like one，2，3。

 and this is going to do kind of the Cartesian product of these two expansions and it will expand into all these things。

EThat we can。Qu that， you can also combine the asterisk G with the cur braces G。

 You can even use kind of ranges of like we can do like M KD and we create the full and there were directories。

And then， we can do。Something along these lines， this is going expand to F A，4 B。

 like all these conditionss through J。And then the same form bar， like， I I haven't really tested。

 but yet， like， we're getting all these combinations that we can touch。 And now。

 if we touch something， there is different。Between。This two， we can again showcase the subtle the。

The process sub that we already。 say we want to kind of check what files are different between these two folders for us is obviously a sell because it's x and y。

 but we can ask the cell to do this di for us between the output of1 L S and the R S kind of unsurprisingly we're getting like x is only in the first folder and Y is only in the。

Sickle folder。诶。What is morning is right now the we have only kind of seen bass scripts。

 if you like other script， like for some task， bass is probably not best， it can be tricky。

 You can actually write scripts They interact with the cell in a lot of different languages。

 So for example， let's see here Python script。

![](img/39bd3610e0a9db5421dd0a55406b48ab_9.png)

have a magic line at the beginning that I'm not explaining for now。 Then we have like import S。

 It's kind of like the Python。 It's kind of not by default， trying to interact。With the cell。

 So you will have to import personal library。 And then we're doing a really silly thing of just iterating over the six door R V 1 a me columnlon。

 which is6 do R V is kind of similar to what inba we are getting as like the dollar，01， etc cetera。

 et cetera。 It's like the vector of the arguments were fitting。

 Were printing in in the reverse order。😊，And。The magic line at the beginning is called a ci。

 and it the way that the cell will know how to run this program。 Like。

 you can always do something like， oh， Python script and then like ABC。😊。



![](img/39bd3610e0a9db5421dd0a55406b48ab_11.png)

And that will work like obviously like that that will work。

 But what if we want to make this to be executable from the cell。

 the way the cell knows that it has to use Python as interpreter to run this file is using that that first line。

 and that first line is giving it kind of the path to where that thing lives。



![](img/39bd3610e0a9db5421dd0a55406b48ab_13.png)

However， you might not know like different scenes will have probably different places where they put Python。

 and you might not want to assume where Python is installed or any other interpreter。

 So one thing that you can do is。Use the M command。 So you can。

 you can also give arguments in this sequence。 So what we're doing here is specify or run the M command that is for pretty much every system that like an system。

 But like for pretty much every system is called is in user bin， where a lot of binary left。

And then we're calling it with the argument Python。

 and then that will make use of the path environment variable that we saw in the first lecture it's going to search that path for the Python Min and then it's going to use that to interpret this file and that will make this more portable so they can be run in my machine and your machine and some organ。



![](img/39bd3610e0a9db5421dd0a55406b48ab_15.png)

诶。AndAnother thing is that the buzz lag。This node really like modern it was developed a while ago。

 and sometimes think a bit tricky to the。 And like by default， the ways it will fail。

 sometimes are intuitive。 like the way we saw before of like full common node system。

 Sometimes is not。 So there's like really nifty tool that will have link in the electro nodes which called salt check that will kind of give you both warnings and like syntactic errors or of things that you might not have quote properly and might mis file have like a spaces in your files。

 So， for example， for extremely simple MD S file wherere in a couple of errors saying like， hey。

 surprisinglyingly， we're missing a， like these minor interpret correctly if youre running the different system。

😊，Also， this C is taking a command and it might not expand properly。 So instead of using C。

 you might want to use something like C and then an or and then anex it。

 we go back to what we explain earlier。 what this is what this will do is like if the C doesn't incorrect it you cannot C into the folder because either you don't have permissions doesn't exist。

That will give like a non zero error comment。So you will execute exit。

 and I will like stop the script instead of like continue executing。

 assuming you're in a place that you are actually notdding。And I could have tested， but the。

I think we can check for the example site。And here we're getting that we should be using。

 We should be checking the exit code in a different way because it's probably not the best way doing this way。

One last remark I want to make is that when you're wearing bass scripts。

 there are like or like functions for them， there's kind of like a difference between writing bass scripts。

In isolation， like a thing that you're gonna run and thing that you're gonna load into yourself。

 We will see some of this in the command line environment lecture where we'll kind of be tooling with the bus RRC and the C H RRC。

 But in general， the if you make changes to， for example， where you are。

 like if you C D into a pass script and you just execute the bus script。

You won C into the cell that you are right now。But if you have loaded the code directly into yourself。

 so for example， we loaded these we the function， and then you execute the function。

 then you will get those side effects and the same goes for defining variables into the cell。

AndNow I'm gonna kind of talk about some tools that I think that like。Ny。

 when working with the So the first， we was also briefly introduced yesterday。

 How do you know like what fls or like what exact command can do， Like。

 how I'm supposed to know that like L minus L list the files in a list format of the like if I do move minus I is gonna like pro me for stuff that what you have is the man command and the man command where you kind of。

Have like a lot of information of how will you go out， For example， here will expand for the minus I。

Flag， there are all these options you can do。 And that's actually pretty useful。

 and it will work not only for kind of really simple command that kind of come packet with your O S。

 but it will also work with some tools that you install from the internet， for example。

 if the person that did the installation made it so that the man page were also installed。

 So for example， a tool that were gonna cover in in a bit。

 which is called and is called with RG like this didn't come with my system。

 but it has installed it on man page， and I have it here and I can access it。诶。For some comments。

 the man page is useful， but sometimes can be tricky to the cipher because it's more kind of like a documentation and a description of all the things the tool can do。

 but not sometimes it will have examples but sometimes not。

 and sometimes the tool can do a lot of things。 So a couple of tools that I use common convertt or FFMPG。

 which deal with images and video respectively and the man page are like enormous。

 So it's like one if tool called T LDR that you can install。

 and it will have like some nice kind of expplanatory examples of how you want to use this。

 and you can always Google for this。 But I find myself saving like going into the browser looking about some examples and coming back where like the LDR are like kind of community contributed。

 and they are like fairly useful then like the one for。😊，Yeah。

FMPE has a lot of useful examples that are like more nightly formatative if you don't have like a huge font size for recording。

Po in simple commands like guitar that have a lot of options that you are combining。 So， for example。

 here， you can be combining two， three different flags and cannot be obvious when you want to combine different ones。

That's how you kind of will go about kind of finding more about these tools on the topic of finding。

 Let's try learning how to find files。 like you can always go less and like we can go like less project one and keep less in all the way through but maybe we we already know that we want to look for all the folders called SRC。

 then this is probably a very common for doing that。

 And that's fine like find is a tool that pretty much comes with every Uni system and find we're gonna。

E give it the。Here we're saying we' are going to call find in the current folder。

 remember that dot stands for the current folder and we want the name to be source and we want the type to be a directory。

And by typing that iss gonna recursively go through the current directory and look for all these files of folders in this case that match this pie。

 And F has like a lot of useful flux。 So， for example。

 you can even test for the path to be in a way here。 We're saying， oh。

 we want some number of folders。 We don't really care that many folders。

 And then we care about all the python scrape。 like all the things with the extension do pi。

 that are within a test folder。 And were also checking just in case pre silly。

 but we're checking just that is also a type F， which stands for file。😊。

And we're getting all these files you can also use different flags for think that are not like the path or the name。

 you could check things that have been modified like M times for like the multi time things that have been modified in the last day。

 which is gonna be pretty much everything So is gonna print a lot of the files we created and files that were already there and you can even use all things like size。

 the owner permissions you name it。😊，What is even more powerful is fine， can kind of find stuff。

 But it also can do stuff。 when would you find those files， so。

We could look for all the files that have like a TM extension， which is like a temporary extension。

 and then we can still find that like for every one of those files just execute the RM command for them and that will just be calling RM with all these files so let's first execute it without。

And then we executed with it。Again， as with the common line philosophy。

It looks like nothing happened， but since we have a non0 sorry a serial error code。

 something happened。 It's just like everything went correct and everything is fine。

 And now if we look for these files， they're in there anymore。

Another nice thing about about the selling journal is that like there are like these tools。

But people will keep finding new ways or like alternative ways of writing these tools。

 And it's kind of nice to know about them。 So， for example。

 find if you just want to match like the last， like the things that and in TM can be sometimes weird to do this thing。

 like it has like a long common。 And there is like things that。😊，Like F D， for example。

 there is like a shorter comment that by default will use reex and you will ignore your git files so you don't like search even for them。

 and it will color code。 It will have like better uncode support。

 It's like nice to know about some of these tools。 But again， the main idea is that you。😊。

If you are aware that these tools exist， you can save yourself a lot of time from doing kind of men interive tasks。

Another comment to bear in mind is like fine。 like for some of you maybe be wondering like fine is probably just actually going through directory structure and looking for the things。

 But what if I'm doing a lot of fines a day wouldn't be better doing kind of like a database approach and like build an index first and then use that index and update in some way。

 Well actually， most most Uni systems already do。 And is this is through the locate command and。😊。

The way that the locate will use， it will just look for paths in your file system that have the sub that you work。

 and I actually don't know。If it will or it working， let me try to you something like。Missing。

Semeister。It's gonna to take a while， but it's only like found all this file that are somewhere in my file system And since it has like built an index already on them is much faster。

 and then to like keep being updated data using like the update D command that is running through Chron。

😊，To update this database。Finding files again is like re useful sometimes you're actually concerned about not the files themselves。

 but the content of the files for that you can use the Gr command that we have seen so far so you could do something like Gr fullber in MCD is there what if you want to again like find recur sleeve search through the current structure and look for more files right like we don't want to do this manually。

 we could use find on the Xec， but actually Gr has like the minus capital R flag that we go through the entire。

A directory。Here。And is telling us that， oh， we have the full line in ex essays at these three places and in these two places in four。

诶。This can be really convenient when mainly kind of the use case for this is， you know。

 you have written some code in some like primary languages。 And you know。

 it's somewhere your file system。 I actually don't know， but you can actually quickly search。 So。

 for example， I can quickly search。For all the python files that I have in my scratch folder where I use the like Request library and if I run this like it's giving me like through all this files exactly what line has been found And here instead of using Gr。

 which is fine like you could also do this， I'm using rip grip which is kind of like the same idea。

 but again trying to bring some more nice these like color coding or file processing and other things I like has also very uniquecode support it's also pretty fast。

 you are not paying like a trade off on like this being slower。And there's a lot of useful flags。

 Like you can say， oh， I actually want to get some context around those results。

 I don't know if it committed yes。 So I want to get like five lines of context around that。

 So I can say like， see where that import lives。And you kind of go around it here in the import is' not really useful。

 But like if you're looking for， you use a function， for example。え。It will be pretty handy。

We can also do things like。We can search， for example， here some like a more advanced use。

 We can say you is for like don't， don't ignore like hidden files。

 sometimes that that can be then like you you sometimes you want to be ignoring hidden files say you want to search。

Confit files of that that like by default hidden， then instead of printing the matches。

 we're asking to do something that will be kind of hard， I think， to do with Gr out of like my head。

 which is I want you to print all the files that don't match the pattern I'm giving you。

Which might a weird thing to ask here， but then we keep going and this pairing here is like a small rex。

 which is saying no， at the beginning of the line， I have a has and a bang。

And there's a C bank like that we're searching here for all the files that don't don't have a C bank。

 And then we're giving it like here like。T minus Ss to only look for like S files because maybe like all your all your python or text files are fine without like a sequence。

 And he is telling us all like MD is obviously missing a even。诶。

We can even have like some also sort nice flags， for example， if we include the stats flag。

I havent read。Actually， right bit。It will get all these all these results。

 But it will also tell us like information about like all the things that it search。 for example。

 like the number of mats， the matchess that you found， the maths lines。

 the file guide search the Viter printed， etc。 similar as as with every， sometimes its not as useful。

 using one specific tool or another。 And in fact， as regroup。

 there are like several other tools like a is or you know。

 kind of grab alternative that was written then was like。The silver searcher A D was another one。

 and they're all pretty much interchangeable。 So like maybe you're a system that has one or not the other。

 just knowing that you can use these things with these tools can be really useful。Lastly。

 I want to cover kind of how you go about not finding files or。

 but how do you go about finding command that you already sometimes like figured out。

 and the first obvious way is just using the app arrow and like slowly going through all your history and like looking for this matches。

 this is actually not very efficient as you probably guess So the Ba has ways to do this more easily。

 there's the history command that will print your history here I'm mean C and only print some of my history。

 but if I say I want you to print everything from the beginning of time。

 it will print everything from the beginning of whatever this history is and since this is a lot of results。

 maybe we care about the ones where we use the convert command to go from some type of file to some other type of file so image sorry then we're getting all this。

And results here about like all the ones that match this substrate。

What even more the pretty much all cells， but default will link control R。

 which is like a key binding to do like backward searchs and here we have like backward searchs where we can like type convert and it's finding the commander we just type and if we just keep hitting like control R。

 it will kind of go through these matches and when like it will let us like reexcut it in place。诶。

Another thing that you can do really to that is you can use this really nifty tool called FCF。

 which is like a fy finder， like it will you it will lead you do kind of like an interactive grip。

And we could do， for example， this where we can cut or example S H command that will print it to the standard output。

 and then we can pipe it through FF and just get in all the lines and then we can interactively kind of look for the string that we care about。

And the nice thing about FF is that if you enable the default bindings。

 it will bind to your controller cell execution。 And now you can quickly and dynamically like look for all the times you try to convert a Figgon in your history and it's also like fusy matching。

 whereas like by default grip all these things， you cannot have to write a rex or like some expression that will match the thing here here I'm just typing convert onphagon and it's just trying to do the best it can do the match in the lines it has。

😊，诶。Lastly， a tool that probably you have already seen that I've been using for not retyping these extremely long comments is this history sub string shirt where the as I type in my cell and both failed to mention but both face。

 which I think was who introduced this concept and then C has a really nice implementation。

We' let you do is as you type the command， it will dynamically like search back in your history to the same command that has like a common prefix。

And then， if you like。诶。it will change as the match list stops working。

 And then as you do like the right arrow， you can like select that command and then like reexec it。嗯。

More。嗯嗯。I've seen a bunch of stuff，I think I have a few minutes left。

 So I'm gonna cover kind of a couple of tools to do kind of really quick directory listing and directory navigation。

 So you can always use the。Minus R to kind of like recursively list of some directory structure。

 but that can be like so optimal。 Like I cannot really make sense of this easily。

 There's like a co tool called 3。 will。Be like like the mat more like friendly for like print all the stuff。

 It will also color code based on here， for example， who is blue because it's a directory。

 And like this is red because has executed permissions。But we can go even further than that。

 there's like really nice tools， like a recent one called Bru that will do the same thing。

 but here for example， instead of doing this thing of listing every single file。

 for example in buy we have this a through J files it will say oh theyre like more unlisted here and I can actually start typing and it will again facility Mats to the files that are there and I can quickly select them and navigate through them。



![](img/39bd3610e0a9db5421dd0a55406b48ab_17.png)

![](img/39bd3610e0a9db5421dd0a55406b48ab_18.png)

So。Again， it's good to know that youre not like that these thing exist so you don't lose like lots amounts of time like going for these files。

 there are also I think I think how install also like something more similar to what you will expect your O to have like now tous or like one of like the Mac finder that have like an interactive input where you can just like use your navigation arrows and quickly explore it might be overkill but you'll be surprised how quickly you can make sense of some directory structure。

 but just like navigate through it。 And pretty much all of these tools will let you edit or like copy files if you just like look for the options for men。



![](img/39bd3610e0a9db5421dd0a55406b48ab_20.png)

ELaadeendum is kind of going places like we have C and C It nice。 like C， will get you。To all places。

 but it's pretty handy if you can like quickly go places you are either you have been recently or that you go frequently。

 and you can do this in many ways。 There's probably you can start thinking， you know。

 I can make bookmarks。 I can make like I can make aliases in the cell that we will cover at some point。

 Ss。But， at this point， like like programmers have like built all these tools。

 So the parameters have already figured out a really nice way of doing this。

 And one way of doing this is using what is called autoja， which suppressing is not loaded here。

This is concerning。啊。わ。Okay， yeah no， worry。 I will correct it in the common environment。

I don't know what isn't the latest。I think it's because I disabled the。

The controller and that also affected other parts of this group。 think at this point。

 if anyone has any questions that are like related to this。

 I'll be more than happy to answer them if anything was left and clear。 Otherwise。

 there's like a bunch of exercises that we wrote kind of touching on these topics。

 and we encourage you to kind of try them and come to office hours where we can help you kind of figure out how to do them or like some like bass querks that are not clear。

