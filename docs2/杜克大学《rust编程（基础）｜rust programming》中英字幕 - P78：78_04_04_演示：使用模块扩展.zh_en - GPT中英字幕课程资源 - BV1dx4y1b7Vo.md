# 杜克大学《rust编程（基础）｜rust programming》中英字幕 - P78：78_04_04_演示：使用模块扩展.zh_en - GPT中英字幕课程资源 - BV1dx4y1b7Vo

![](img/0d1632f29ca7b4bdd6dea00d302c31ae_0.png)

This CI U library is very useful already and one thing that we want to do is to try to extend it now。

 so CI utilities are meant to be utilities for command line tools that I want to build and that's the use case that we have here。

 so so far we only have one function and I want to add more things but instead of polluting the lid that Rs file I want to use a separate file。

 one common thing and one common pattern for command line utilities is adding colors and colors for for especially for terminal output。

 so I'm going to go to SRC I am going to say I want to add another file called colors that Rs。

So in here， I'm going to create a function。And this is going to be。Red color。

 we can say S is going to be。Slicide string。 This looks correct。

 So let's let's figure out a little bit what's what's going on here。

 So this function will take a string slice。 It will return a string with color output。

 What is this thing doing is formatting the string to have this anCscape codes and then。

I's using that variable and I's going to put a right there in between this is how you this is the foundations of coloring output you have like like a beginningscapecode and an endingscapecode for specific coloring of of something that you want to colorize in this in this case。

 so let's very quickly start documenting this and we're going say。We're going to say returns。

 say string wrapped in n red colors and then we're going to provide some examples and tripleactctics and to say C us colors and then we're going to say red that looks correct and that's how you that's how you will use it We're not panicking we want to save that and this looks this looks pretty good Now what's one thing to consider here once you start doing that unlike other languages like say for example Python the fact that I've created a file here called colors that Rs doesn't mean much for rust。

 the one specific file that has meaning for rust is the Lib thatRS for libraries。

 main thatRS for executables So everything has to like this is the entry point for everything we want to lose so let's go back to Lib that RRS and。

What we're going to do there is， we're going to say。

We're going to go right here right below these imports and I're going to say。Bob。Moud collarers。

And why are we doing that because otherwise colors wouldn't be available。

 so like let's take a quick look again at colors that rest。

 see this example that I have here in line number5。The CI underscore till doublecol colors。

 doublecol red means that I'm expecting that to be available in that shape and that form so by putting things in a different file that means that I'm naming that file like colors so and I'm making that module available and I'm exposing red otherwise these wouldn't work and that so that's to have these availability I have to go to my special Libda file and make it work like these so this is a very simple。

 very straightforward way where we can actually start exposing things and adding more things that don't necessarily pollute or go into LibarRS you can most certainly have these red function in Libda R and have something else to have these colors in there but。

Choosing to have these separate in a separate file so when would you want to have things in a separate file well it's just an organizational decision there's no hard decision here that you have to have things in a separate file。

 you could very well still add things on LibarRS but keeping things separate might be a good idea for easier parsing and reading and understanding what different pieces of the code is trying to do。



![](img/0d1632f29ca7b4bdd6dea00d302c31ae_2.png)