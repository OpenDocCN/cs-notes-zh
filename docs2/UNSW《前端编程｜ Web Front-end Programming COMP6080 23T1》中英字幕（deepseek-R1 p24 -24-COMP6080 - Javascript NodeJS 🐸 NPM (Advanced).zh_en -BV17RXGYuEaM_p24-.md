# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p24 -24-COMP6080 - Javascript NodeJS 🐸 NPM (Advanced).zh_en -BV17RXGYuEaM_p24-

Hi， everyone。 This lecture explores NP PM and yarn in a little more detail。 Let's get started。So far。

 you should be aware of NPM and Yrn， both the package management systems for JavaScript。

 they allow you to install libraries from the web to use in your app。

You can install new ones using NPpM install and start your application using NPpM Start and so on。

 You should also be aware that package。 JON exists and that yarn is an alternative to NPpm。

On the right hand side， you can see an example of a package dot JO。 There's a lot here。

 but don't worry， we'll be breaking it down into manageable chunks。

The package dot Json on the right is a typical react app created using create react app。

 It has metadata， dependency information， and so on。Please be aware that for this lecture。

 when I'm referring to NPM， especially in the context of package dot JO。

 yarn and NPM can be used interchangeably。Let's take a look at our metadata fields。

When you publish a package on NPm， there are many fields in package。 JO。

 which are used to generate information that is displayed on your package's information page。

 which is located at nmjs。org。Fields like name， author。

 contributors and so on are just package related metadata that relays information to consumers of your package Licence is a special case because while it's displayed on the page。

 it also has legal ramifications。 Let's take a look at an example。Here is the MPM JS page for react。

A lot of metada is displayed here。 For example， the  license， the homepage， the repository。

We also have the version， which we'll discuss later。Collaborators are listed down the bottom。

Just down here。And we have keywords on the left。 And， of course， the name of the package at the top。

Next up is the version field。 It's a specification of your package's current version。

 If you make a change to a package， you should also change the version。When you install a package。

 you specify the version of the package that you wish to install。

 which maps to that package version that is displayed in the package Json。

Versions are specified using semantic versioning。 The first number of the version is a major version。

 The second number is a minor version， and the third number is a patch version。

 These stand for different things。 Whenever you change a major version。

 you're specifying that the API has changed in a breaking way。

 So if somebody upgrades a major version， they may encounter breakages in their app。

A change in the minor version means you have added new functionality。

 but you've done so in a backwards， compatible manner， so。There may be new functionality。

 but if you upgrade， you shouldn't expect any breakages。

And a change in a patch version means that you've made backwards compatible bug fixes。

 so you can safely upgrade a patch version without having to worry if anything will break。

Next up is the private field。 Private stops you from publishing your package to NPM Acdentally。

 you can publish using the NPpM Pub command， but if private is set to true。

 the publish command will fail。You might already be familiar with the dependencies failed。

When you use MPM install or yarn addd， an entry is added to the package dot Json。

A couple of slides ago， we spoke about the version field。

The dependencies list is where you specify the version of the libraries that you'd like to consume。

You can see here there are some special characters at the beginning。

 These allow you to specify version ranges。In the slides。

 I've listed ways in which you can specify version ranges such that you can get the most recent major minorr or patch version。

Depending on your use case， you might choose to use any one of these。

 A production level application might only want the most recent patch version to reduce the risk of having breaking changes。

 but for a fun experiment in your spare time， you might want to take the most recent major version。

There are other symbols that you can use that allow you to specify minimum and maximum bounds on versions or any version greater than or less than these are outside the scope of the slide and I've left a link for you to examine in your own time。

A normal package dot J will have a dependencies field。

 but that isn't the only place where we can specify dependencies。We can also have dev dependencies。

 peer dependencies， and optional dependencies。Any dependency you like can be added to these fields as well。

 But what they do is quite different。Broadly speaking。

 a dependency is just anything that your code needs。 However。

 we have four different fields and they mean different things。

A dependency field in the package dot Json is just anything that the application needs to run。

 React as an example of this。 if you are making a react application。

A dev dependency isn't required to run the application。

 but it is required when you're building the application Test libraries and Ls come to mind because you need these to build。

 but your users don't need these to see your page。Peer dependencies are a little less common。

Say that you have a package A that has a peer dependency B。 If I install package A。

 I also need to install package B independently。 Otherwise， package A won't work。

 React Dom is an example of this in a react application， you not only install the react library。

 you also install the react Dom library。With a normal dependency。

 if I install a dependency that has other dependencies。

 MPM resolves these for us and installs subdependencies。However。

 if it's a peer dependency that does not happen， the transitivity of dependency resolution is lost。

Lastly， we have optional dependencies。This is a dependency that we'll try to install。

 But if NP PMM or yarn can't install it。It still lists the installation as a success。

 and nothing bad happens。In a normal application， you typically won't see many peer dependencies or optional dependencies。

 They're more used when you're publishing a library or a package， however。

 they do have some advantages。Peer dependencies allow you to ensure that a consumer of your package installs a specific version of another package so that these remain in lockstep。

 And if you rely on a feature， that's a newer version。Of that package。

 you can ensure that the user has also installed a version of the package that supports that feature。

Optional dependencies are useful for situations where， while you might want a dependency。

 you may not need it。A good example of this is something like styling your console logs。

It would be nice to have， but if the dependency installation fails。

 you still want the application to be able to run and output to the logs normally。

Next up is the Scripps field。 The Scripps field allows you to specify command line scripts that MPM can run on your behalf。

When you run NPpM start or yarn start， you are actually telling NPpM to run the command Re scriptris start。

 which is specified in the package do JO。The Scpps object is a key value object。

 where the key is the command that MPM recognizes， and the value is the actual shell command that we run。

There are certain commands， however， like install， that cannot be overridden。

Let's take a look at an example。

![](img/3906c0295b08496ac3b7c5e93c63df8c_1.png)

![](img/3906c0295b08496ac3b7c5e93c63df8c_2.png)

So I've got a simple react app here and I've installed prettier as a dev dependency。

 Prettier is a tool that automatically formats your files。

 and you can see here that my app dot JS file on the right is formatted incorrectly。Soir。

I'll build a script that will allow me to run prettier through NPm。I'll add a prettyt entry。

And at the end I， specify the prettier command， which says to write to the source folder。

It's as simple as that。 Now， if I move to my terminal。

I can either use NPM or yarn to run the command。In this case， I'll use NPM。

 so I type NPM run prettier， and it runs the prettier command on the source folder as we specified in package of JO。

If I reopen up dot Js， you can see that the component is formatted correctly as it should be。



![](img/3906c0295b08496ac3b7c5e93c63df8c_4.png)

![](img/3906c0295b08496ac3b7c5e93c63df8c_5.png)

Moving on， one thing to note is the package。 JSON is just a JSO file。

Certain libraries might choose to arbitrarily extend it with new fields。

Which library can attempt to read when it needs to。

Configurations for certain libraries are often held in package。t Json。

Earlink config is an example of this。 It provides a configuration to our lter。 In this case。

 it's saying to use the react up lnting preset。Browsers list is another example of this。

 It is used by a plugin called Bs list， and it allows us to specify what browser types are supported by our application。

The exact syntax of browser's list is outside the scope of the lecture， however。

 you can look at the browsers list package to get an idea of the syntax， however。

 you can see here that we specify different supported versions based on whether we're in a production or a development environment and for our development environment we specify the most recent version of Chrome。

 Firefox and Safari。And that's it for package。 JO， So by now you should have a good idea of what a typical package。

 JO looks like for a basic react application。Now， let's look at yarn and MPm。 What's the difference。

It's important to remember some history here At the time that yarn was created。

 Facebook was using NPM and having some trouble with it。 NM was slow。No deterministic。

 that means that given an identical package dot Json on two computers after installed。

 the structure of the node modules folder was different across both computers。

It also had no way of locking down versions so that every developer was always on the same version of each package。

 version rangers and so on， Inency resolution often led to developers having different or conflicting versions Yrn was developed to solve these problems。

At the time of release， yarn was significantly faster。 It used a deterministic install algorithm。

 and it used lock files， which allowed us to lock down our dependencies。Firstly， in yarn。

 packages that have no dependency on each other can be installed in separate threads。

 meaning that install times are cut down。Having said that。

 MPM has since released an update MPM5 that has closed the gap between the two。However。

 at the time of yarn's release， it was reported that install processes could go down from taking a number of minutes to a number of seconds。

Another significant advantage of yarn is lock files。

 A log file records the exact version of the dependency that has been installed on a computer。

 You can then commit the log file to version control。

 at which point if another developer installs the package。

 they will get exactly the same version as the first developer ensuring that the versions of both packages across two computers are in lockstep and you don't have any issues relating to conflicting or different versions。

In Yrn， a log file is created every single time a package is installed or updated。

 You can check this log file into version control， which ensures the next time it's checked out installed。

 the versions stay the same。However， in MPM， a command called NPM Sh wrap also exists。

 which creates an MPM ShmpC file which does the same thing。

 The difference is that in order to get the log file on NPm you need to explicitly run the shrinkhrimp wrap command。

 whereas in yarn it does it automatically for you。And that sums up the difference between NP PMM and Yrn。

 There are some performance optimizations that I haven't listed that you can find on Facebook's engineering blog。

 or on Github。

![](img/3906c0295b08496ac3b7c5e93c63df8c_7.png)

Great work In this lecture， you've learned about the structure of a package dot Json。

How different types of dependencies work， how to create your own scripts。

 and the difference between Yrn and MPM。Stay tuned for future lectures about NPM， in the meantime。

 all the best。

![](img/3906c0295b08496ac3b7c5e93c63df8c_9.png)