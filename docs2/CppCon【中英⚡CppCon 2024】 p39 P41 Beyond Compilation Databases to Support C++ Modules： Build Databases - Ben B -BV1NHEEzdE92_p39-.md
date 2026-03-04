# CppCon【中英⚡CppCon 2024】 p39 P41 Beyond Compilation Databases to Support C++ Modules： Build Databases - Ben B -BV1NHEEzdE92_p39-

![](img/8cd7ff29af20365aca8a92fbf7d04a20_0.png)

🎼The presentations， you learn something new even in basic presentations。

 but the hallway track is just indispensable。

![](img/8cd7ff29af20365aca8a92fbf7d04a20_2.png)

![](img/8cd7ff29af20365aca8a92fbf7d04a20_3.png)

All right， well， I guess we'll get started。

![](img/8cd7ff29af20365aca8a92fbf7d04a20_5.png)

Hi， welcome toBeyond compilation databases which to Sports host modules，Build databases。

 My name is Ben Bael， I worked for Kitwear， I've been doing build systems and software process stuff for about 15 years now。



![](img/8cd7ff29af20365aca8a92fbf7d04a20_7.png)

I'm a Cic developer。 I've been designing， implementing features， doing performance improvements。

 and then on the using side， I've been maintaining and improving build systems that use CMake for。

10 plus years， and most recently I've been working on C++ module support within CMake and across the ecosystem。

At Kitware we're working with the community to try and improve building software for everyone。

 this includes going to the ISO meetings， doing standardizing formats for dependency discovery for modules。

 forward and pushing forward modules and other build systems， for example。

 XMake and basal N support modules。Due to I've been reviewing code and prodding them to， hey， like。

 hey， here's how CMakeakes going to do modules， maybe you should start considering supporting them too。

So for this talk， I'm going to be going over compilation databases。

 which I'm sure many of you have've used。So what are they and then how do modules change？

Their usefulness more or less。 and then。A solution that I've been working on。

 which I call build databases。And how it solves those problems。So first， compilation databases。

 there are JO documents。They are just top level arrays with objects in them。

 and each object describes a single command that happens within your build。

You have the working directory where the command gets run， the command itself。

 what source you're compiling， and what file it will create on the output。However， that is optional。

 which。Can cause issues。冇。Get there。They are specified by the K project， they're not ISO。

 they're not。Even like LBM Claang is the one that specifies it。

 they are however widely used and available， build systems will generate them across the board pretty much。

 I think basil is the major one that doesn't do it。

 and then static analysis tools and IDEs will use them to understand I'm looking at your project。

 what does this mean。Because just C++ source on its own is not very meaningful without knowing what flags are passing to it。

So here's an example， you have your directory where you're running it， your command。

 which is a string， basically flag soup。And then the file you're compiling and output。

I have a pointer。哦。These are generated usually by your build system， for example， CMake or Maison。

 you can also have your build tool do it， Ninja has support for doing it。

 and there are also tools with tool。呃。Wrap your build and discover what your build commands are。

They're usually if they're done by the build system， they're available with your build rules。

 so when your make file or your build that ninja is generated。

 you'll have your compile command so your ID can just start understanding your source code。This。

Is usually good until you have things， there are exceptions to this。

 which we'll cover in limitations。If you miss the output field， your source files can be ambiguous。

 you can compile a source file more than once， whether it be I compiling it in release mode and debug mode。

 or you can have it because you edit the source to multiple targets and it has different flags。

In this case， your IDE needs to understand which one matters。Visual Studio， for example。

 has a drop down for which configuration am I using。

 and it also understands which target am I working on， by which project you have open。

 whoever VS code or VIM are not necessarily going to understand what is actually happening。嗯。

You also have the string representation for your command， it is specified to be shell E。

Which is woefully underspecified on。Ununix， you can generally just assume Bshell。And then on Windows。

 you have to its usually CMD， but some people use Powerhell and your escaping sequences are very different in those cases。

 but there is no place to tell it what you're doing other than looking at it and guessing based on heuristics。

There's also no extensibility， there's no place for rered field names。

 and so adding any new fields to this format is fraught with conflicts of what else anybody else has been doing in ecosystem。

There's also a portability issue， all your flags are dependent on what the compiler is in use so you can look at it you be like。

 oh yeah， I totally know what that flag means except it's not supported by that GCC and it's actually an error。

The other thing you don't know what your build graph is， you don't know if they're generated headers。

 you're going to be expecting， you don't know if there's generated sources you're not going to be finding。

Those you can usually be like， okay， they're not on disk so we can expect them later。

 but they' are also arguments that take files which may not exist。 For example。

 you could have dash include some generated file and then for modules， there are files that seemMake。

 at least in its strategy will write out during the build that your commands then read。

During the build。 And so your。Configure time information is incomplete。That brings us to C++ modules。

So surprise for anyone who didn't know， modules complicate compiling C++。

 the old days of embarrassingly parallel。I have N cores， here's N jobsbs is over。

This is because SQL plus said， great， we will take the forchan compilation bottle and use that。So。

This means that when you compile a。嗯。A source file， you will get your object file。

 you will also get what is called a BMI， this is built module interface or binary module interface。

 some implementation called a CMI for pile module interface is basically an extra file that when something imports a module。

 that's what it's looking for。But you know， it comes up with a compilation。So。

It's not ready right away。So with C++ unfortunately， the similarities between them。

 they both have compiler specific BMIs， you can't use aCC GCC module on Kang vice versa and with C++ it's even。

More strict where the flags matter。If you have， you know。

Your module is compiled with C++ 23 if you have something that says I want to use 26 and it tries to import your 23 module。

 it won't work because the BMIs are basically abstract syntax tree dumps and when the standard changes。

 the AST changes， which means that you can't read it anymore。

The other thing we have with Fortran in common with Fortran is that what module you're looking for is in the source you don't know。

Just based on some。Inherent。Property， what module is going to be created or which modules you're going to use。

 So you have to look at the contents。 This means that you have to either every time a source file changes。

 go and rebuild your graph。Bill graphra or during the build。

 discover what your build graph is going to look like。I'll get to how Cic does that in a bit。

The differences are in details for trans supports what they call submods。

They're basically just forced nested modules， and then they also support multiple modules exported from a single toU。

C++ does not do that instead it has partitions， but partitions are pretty much modules。

 you just can't import them directly。And then。Again。

 the Fortran doesn't have the flag problem that C++ does。

So a bit of a history on how For modelss got built。So they were introduced in4 90。

 the official documentation from one of the vendors was run a parallel build until it works。嗯。This。

Is fine until you write cycles or you import something you don't make。

Which means that you end up with a build that never ends。Following their instructions。Eventually。

 someone would make F90 depth， which will look at your forran source and write out a make file snippet that says。

When you compile this object， you need to first compile this one。

And then you can include it in your make file and you'll get a reliable build。Brad King， the。

Current maintainer of CI imported this into Cic and implemented for the make files generator in the late 200s。

And then in the mid 2010s， he went to Ninja， implemented D debt support。

 and we carried that patch set for。

![](img/8cd7ff29af20365aca8a92fbf7d04a20_9.png)