# CppCon【中英⚡CppCon 2024】 p47 P49 Build Safer Modern C++ Application： Mix Assertion, Logging, Unit Testing and -BV1NHEEzdE92_p47-

🎼Attending any conference， it's incredibly important to be there that's kind of the only way to really dedicate your time。



![](img/50fb15cb35071c98c58dd6bf56a33ed6_1.png)

To be there and kind of be immersed in the whole thing and not distracted by other stuff going on。

 even if you do get distracted with interesting conversations in the hallway。



![](img/50fb15cb35071c98c58dd6bf56a33ed6_3.png)

![](img/50fb15cb35071c98c58dd6bf56a33ed6_4.png)

Hi， everyone， thanks so much for coming us today。 I'm Sha。

 This is my first time come to CBB Co as a speaker。 This is also my first time to join。😊。



![](img/50fb15cb35071c98c58dd6bf56a33ed6_6.png)

if people call on face to face and' really exciting today， okay。

 I'm going to share a new framework on Euroro era。I made in recent two years， which mixing assertion。

 logging， union testing， and causing gas。124是该。It could be helpful for you to build a safer modern activity。

哦。Before we get started， let me first introduce myself。

My name is Xo7 years ago I came to American studying computer science and last year I got my PhD from this riverside。

 I've been starting automatic testing of multithor programs during during my PhD I have papers related to symbolic execution。

 concolic execution for improving those parallel program testing and detecting and for detections in concurrent data structures。

 for example， databases， now I'm working in V hardware infrastructure team。

 my job is about like designing domain specific language for registers。Okay， let's get started。

 First， let me tell you the story of zero error framework。Two years ago， I was still a PhD student。

 you know， being a researcher， that is always a nice time for me。 So you could do a lot of things。

 You could do try the newest technique。 You could really make the things。

Could be influence for others。 and really quite exciting to see the papers influence。

 That's most enjoyable part of the job。 But things has two face。

 there are also some painful time for me。 One example， I will ever say。

 please think you are a PhD student。 this is your final seasons。

 you will be called a doctor after you graduate。 you deadline on left two weeks。

 But when you collecting the date， there is one experiment logged date， is showing something error。

 error code， something， something。 then。😊，Okay， I made， it must make something wrong， right？

 No has a choice。 Let try to， try to figure it out and debug it before the deadline， so。You know。

 what is the difficulty in debugging。 The debugger sometimes won't work because but for complicated these structures。

 you have too many linkage between node to check。 There are so many information。

 So that I heavily relies on the logging on the those information to debug it。So let's have a look。

 what I have to print。 There are some。嗯。Customer classes structure date。

 definitely those structure date class are the most common ones like containers。

 we have some data that are in map which index using a string。There are smart pointers。

 which when they use in the product， Os sorry。And there are also third party libraries like L VM。

 which is a famous compiler infrastructure library I use。

 So there are many different types that I have to print。

I was using J log and smart assertion library to make the output can be both used by log and assertion。

 So I have to make a huge list of printing functions like。Like this one。

Most of them are right of my customer these structures or customer containers。 So I was thinking。

 could I make a template based library focusing on printing those types and could be reused across different products。

Right。Yeah， that's an idea。However。There are many issues in streaming operator implementation。 First。

 there are name namespace pollution。So if you write this function。

 you must define it in a global scope。 So it's sometimes hard to be like to control when to use those functions。

Second， it's also hard to implement with templates。 Don't worry， I will explain this later， so。

And otherwise， there is no extensibility。 So if the library will define a template。

 then user lose the ability to define their customer template to override it。So that's an issue。

 And you can。Easily customize， you cannot easily customize the behavior for like printing the same time for different scenario。

 For example， if you want to print additional landbreaker。

 it's hard to configure that because theres no， this function is not stale and no additional parameters could be passed into the functions。

So I was thinking， maybe I should not use a stream operator。 And by the way。

 is to make the log using like a strify strify function with a format lag interface。

 and we can't implement it as a stateful function。Like this one。So you could see。As a fun。

 you have states， right？We noticed that both logging and assertion， even more。

The check in unit testing， they are they all needs pretty printing in an accession micro。

 no matter it is used in user code or in unit testing， it's all。

 is's also quite helpful if we can print an error message when it's filed。In this example。

 assertion in print the message， a should not be0 and the input as well I think took log and assertion macros are the ones that I'm looking for。

So that I was thinking， maybe what I need is a framework that makes assertion。

 unit testing and logging， they all use the same printing interface。

Other than a simple stratify library。Okay， let's go back to debugging。

It's a bad habit for me when I'm working on something urgent。 I usually get off the topic。

 You may ask， then did you find the web， Yes， and each I actually inside a unit test case。

 I think I have tested。 and there is no error detected。😊，Then the question is。

 why it passed the test？Here is an example shows what happened。

 Let's say we have a function pass expression need to be test。Inside function。

 there is a simple cache system， which will cache the result to speed up the next time when you see the same input。

 So if cache not hit， we will run the pass function， which did the real work。Otherwise。

 we will return the clone expression from the cash system。Okay。There is a bug。

I mean everyone made those kind of bags。It's quite annoying if you write a clone function in the class。

 One month later， when you want to try to quickly change something， you add a field。

 which is a member variable。 And， but you forgot to change the copy function。

 Then not all the information， Some of the information is missing。

 That's quite common mistake we may meet。 however， why the past test。This is what happened。

I this see what's going on？Yes。There is a space， so the cache didn't work so that U E2 both created from past the Inter function。

Of course， the bug is is not detected because you you didn't run the code。Yes。

 I should test the the clone function individually。

 but I was thinking to test the cache system as well， but made a mistake。 However。

 my point is there is no way to check if the cache system worked or not by only looking at the output。



![](img/50fb15cb35071c98c58dd6bf56a33ed6_8.png)