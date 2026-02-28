# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P7：6_模块1 2 2 工作区和包.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/e2066f196f55dff60980703f12621619_1.png)

🎼う。🎼Yeah。Right now， we're going to talk about how code is organized in go。

First we'll start with a workspace， so there is this idea of a workspace。

And it's basically a directory where your go stuff will go， so your go files。

 your go source files and other files will go in this workspace directory。

And typically there is actually a hierarchy of directories within your workspace where you will store the different types of go files that you're working with。

Now， the reason why we're doing this， why the go language defines this hierarchy of directories is because common organization is good for sharing。

A big motivation behind the go language is for people to work together easily。

So remember that when you're programming not necessarily in this class in this class。

 you know you're working on learning the language， the different aspects of the language。

 but when you get outside and you're working in a company or something like this。

 it's never one person alone， it's always a big group right you're working with people all over the place and they have to be able to work with your code。

 look at your code， merge it with their code， link it to their code， that sort of thing。

So there's always this sharing going on， maybe you want to upload the GitHub and have a communal group of people working on code together。

😡，So for that， it is nice to have a common standardized organization of your files， right。

 it makes it easier to share because then everybody knows where everything is。

 tools know where things are， stuff like that。So。Inside your workspace directory。

 what is recommended are these three subdirecties， the source directory。

 it contains the source files， your source code， your go code， package directory。

 it contains packages， the other packages that you're going to link in that you need。

 and then the bin directory that contains all your executables， your compiled executables。

Now the programmer typically has one workspace for many projects。

 so I typically use my one Workspace directory and I can have 20 projects。

 20 different go projects I'm working on in the same workspace directory that's common。

 you don't have to do that， but that's common。So one thing to remember about this directory hierarchy is that it's recommended。

 but it's not enforced okay so this idea of having the source subdirectory in the bin subdirectory in the packet subdirecty that's not you know it's not enforced So for instance。

 you can have an executable in the source directory if you want it is not neat and it's harder for people to share。

 but it's going to run。 you can compile it and put it anywhere you want and run the executable right so it's not enforced it's just this is a recommendation to make it easy to share with other people。

So the Workspace directory， you do have this one workspace directory though。

 and this workspace directory is defined by the Gopath environment variable。Now。

 the GoPA environment variable depends on how you set environment variables is going to depend on your operating system。

Normally what happens is like on my Windows machine。

 but this should happen on a Linux and an OSx machine too is that the gopath directory is set for you automatically by during the installation process So that wizard that then install wizard it should define the gopath environment variable and certainly on on a Windows machine。

 the default directory where it sticks it where it puts it is see colon slash uses s your name So for me slash user slash go know it sets that as your go as your workspace directory Now I noticed that when I installed everything that was my gopath that was my gopath what you see up there use s E slash go but it actually didn't create a go directory So there was slash uses s Ean I had to create the go directory myself which is fine I had to make that directory and put my stuff in there。

But understand that that's the default workspace。 You can change that。

 You can go to your gopath environment variable and change your environment variable in your operating system if you want to。

 but for now I'm just assuming that we're using the default Gopath。

So the go tools all assume that the code is inside the go path somewhere。

Now there's this another concept of packages， your code is organized into packages。

 a package is a group of related source code files。Each package can be imported by other packages。

This is the use for this， the main use for this is when you're working with other people。

 other groups of people in other places， you write all your code in one package。

 they write all their code in another package and then if you need to use their code。

 you can use their code， you can import their package so I say have it's so it's good for software reuse that's the main goal。

😊，And the first line of the file names the package so what I'm showing here in the picture。

 you can see these two pink boxes up here， these are two packages that are defined and you can see the first line of so those are two different files。

 two different source code files and you can see the package names are listed at the top package package and there's a bunch of code in there and theyre all in they're associated with that package name。

Then in blue， I have some other piece of code in a different source file and it needs to use the packages from the other two people right so I have an import statement at the top of of my blue file and I import I give the package names that I want to import so I can use these other two packages in my code if I want to So this is how packages get connected to each other and it's very convenient if you're working with somebody remotely or somewhere else you can sort of a clean separation of the code。

😊，Now， there always has to be one package called Mainine。And that's where execution starts。

 So there's got to be one package called Main。 And you'll note that in the code that we're working on in this course。

 were we just have one package and it is called main because we're not making such big code that where you have different groups of people working together with different packages right now。

 we're focusing we're just writing one package called Main。

 but there must be one package called main and when you build the main package when you compile it。

 it makes an executable of that So note that when you build another package the non-main packages it doesn't make an executable for those or not a running executable because it's not going to be exe directly。

 it'll be incorporated into some other package， but the main package that's what's going to be run。

 So when you compile that when you build buildlash compile， you get an executable file。

So the main package needs to have a function called main。And mainine is where code execution starts。

 So you can see the example code right here。 It's just's just print hello world。

 we say package main import format。 So that is that import right there is importing a package。

 format is not a package that I wrote format is one of the packages that comes with the go tools。

 So when you download the go tools， you get all these standard packages， including format。

 and the format package has a lot of functions in it， we'll talk more about it later。

 But one of the functions that it has this print statement。

 So print F is included in the format package。 So we have to import that package。

 And then we make our function main。 And in there it just says format print F hello world。

 So pretty straightforward。😊。

![](img/e2066f196f55dff60980703f12621619_3.png)