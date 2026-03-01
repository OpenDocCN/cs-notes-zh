# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P72：72_04_06_演示：代码文档化.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/79e2d951c92b8d3752a595d946322cef_0.png)

Documenting your code is a very good way not only so that you can actually understand what is going on here and that you can explain that to others。

 but to be able to make good design decisions if you're able to document your code correctly if it takes you know a lot of effort to document it and and to explain what it does it's probably like a complicated function and maybe you need something else。

 So how do you document things。In rust。 Well， let's actually not document anything。

 Let's just leave it like that and let's see how we can look how the or poke around how the documentation would look like。

 So I'm going to toggle the terminal here。And I am here in the project and what we can do is we can say cargo doc and cargo doc。

 I'm going to do help。You can see here， let me scroll away to the top。

 we'll build a package a package's documentation， so that's pretty nice and we can actually say we want to do certain things here。

 we want to document absolutelyD everything， we want to work with certain features and in this case it is going to build all of the documentation。

 so how does work this work， I'm going to clear this， I'm going to say cargo， doc and nothing else。

 I'm going to hit return。And it finished。 So first， it builds， builds the the project。 in this case。

 my library。 And then it says， well， everything's done。

 So what would you do here if everything's already done。 Well， let's do L S。

And we are going to get things in target。 actually， we can use the Explorer for this。

 We're going to see target， we have debug Dog， some stuff in there。

 but we let's take a look at what Doc is It it's like， oh， we have some jascript， some HTML。

Some more jascript and we have Ci us here。 we have an index that Hm。

 So let's open that very quickly and see what that looks like。

 So I've opened up that index that HTML file you can see here that this is a local file and in my home computer and we have here our Cli us and that's the cr。

 that's the package and we have a read underscore standard in that is our function。

 So does this look familiar Well this is exactly the same as docs that are S。

 So if I go to docs that are very quickly。 This is for example。

 docs that are for the Onyx runtime and you'll see that this is very very similar and we'll have modules straights inums and we have well a fairly。

Robust information here that we can definitely add。 So pretty interesting。

 There's lots of things here and definitely looks nice。

 So that is exactly the same as what we have right here and you can see we have the version all items We have functions and let's take a look at read the standardine or read underscore standardin and we have our function signature we haven't documented anything and we already have all of these building by default fault。

 So how can we go ahead and improve the documentation of these so let's actually go through some of the things that I've mentioned about these functions。

And let's put it into actual English。 So so we're going to say this function reads as a line from standard in returns it as a string。

 It will panic if it fails to read the line with a。Meaningful message。

 which is failed to read input line。 So that feels pretty good to me。

 And one thing we can do is we can say examples。And we can see examples， and。

We can do actually this is a markdown。 Can do you feel does it feel like a little bit like markdown that is because it is。

 So we've done the mark the markdown， we've explain what it is Now let's go ahead and build these again and we can save cargo doc and let's go back to the browser So in the browser you can see that now we get we get these this right here very nicely formatted。

 Do you see how examples looks like a title that is because markdown is being consumed by the cargo doc and it's able to build our documentation and this is the small example that we added to that function。

 Now all of these documentation belongs to our little function here。

 What if we wanted to document what Ci utilities。Well， in that case。

 we need to add something different。So if we go back here to I'm going to close the terminal and I'm going to close the explorer now the documentation is always prefixed with three four slashes unlike comments that are just two four slashes and what we can do is we can actually build a project in this case our library all the way to the top and when I use two four slashes and a exclamation sign so we're going to say this is a library for rain input from no but that's not quite right。

 this is a library that provides。Utilities。For command line tools command line tools that sounds pretty fine and we can we can say that that's pretty good。

 we can say examples again and triple backs。And that looks pretty okay to me。And now panics well。

that looks okay Well compilepi helped us helped us there quite a bit to write that documentation and now we have some examples。

 all right so we have the examples。 these looks pretty neat。

 we use Cli us read standardin and then we read the standardin and then that's where're good to go so how does that look like when we build again the cargo doc。

 let's take a look we have here what we had before let me refresh that and I'm going to go right there to the parent and the parent page and now you can see that we have our grade us Cli us and we have the documentation that we wrote for our library package pretty nifty pretty easy way to do that by dealing with the faults and with the expectations that are coming from cargo so cargo is and cargo doc is specifically expecting these to be for the package and not from the library。

These to be for the function so those are ways that you can use to document your tool and various different ways that you can control what is it that you're exposing in the documentation and what parts are comments versus what are some things that might belong to some other pieces of your library package。



![](img/79e2d951c92b8d3752a595d946322cef_2.png)