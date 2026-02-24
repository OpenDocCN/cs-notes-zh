# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p50 -50-#49 Embedded Unit Testing #embedded_systems #embeddedsoftware #testing -BV1fRt2efEms_p50-

![](img/128e5f352d65ab8f30c4858da6c22d07_0.png)

🎼Hello and welcome to the moderndern Embeded System Program course。I am Miseic， and in this lesson。

 I'd like to discuss testing and its central role in software development。

 We will also see some ways of testing embedded embedded software on the host computer and on embedded targets and how to obtain the necessary tools。

My main goal today is to explain testing in a broader context of software development。

 which in its essence， is creating complex systems。

So let's examine how complex systems generally come about because our understanding of this process has dramatically changed。

The change I am talking about is one of the most profound in all science and concerns the most complex systems we know of living organisms。

Before Charles Darwin published on the origin of species in 1859。

 the established thinking was that all living things were created in a divinely inspired act in their current perfect and final form。

The Darwinian theory of evolution by natural selection offered an entirely different explanation。

All living organisms come into being through a gradual。

 incremental and cumulative process of evolution from simpler to more complex forms。

The critical and most radical idea of the time was of natural selection that constantly and relentlessly weeds out the lessfiit adaptations。

 leading to the constant struggle for existence。Following Darwin's publication。

 the most significant intellectual challenge was imagining and accepting that such a process could produce complexity on this scale。

Nowadays， science has come full circle， not only is evolution capable of producing complexity。

 but in fact， it is now recognized as the only process through which anything complex can be created anywhere。

 not just in biology。A little known scientific fact is that shortly after Darwin's publication。

 another lesser known author published on the origin of software by means of artificial selection with the subtitle Preservation of Fed code in the struggle to Sur testing。

In this work， which， frankly， was far ahead of its time。 The author， yours， truly Misic。

 generalized Darwin's ideas to software development。

Here are the three most important findings from that forgotten book。First。

 a complex system that works is invariably found to have evolved from a simple system that worked。

Second， a complex system designed from scratch never works and cannot be made to work。

 You have to start over， beginning with a working simple system。And third。

 actually a corollary from the first two。In embedded systems， nothing works until everything works。

 I'll come back to this fact later。Unfortunately， that important work has been forgotten By the time software was actually invented。

 People still believed in a divinely inspired act of creation， known as the wonderful process。

Such a big upfront design culminating with big bang final testing cannot work because it lacks the critical evolutionary aspects of incremental development。

 combined with constant selection， which are indispensable for anything complicated to actually work。



![](img/128e5f352d65ab8f30c4858da6c22d07_2.png)

Well， it seems that every discipline must repeat the same mistakes and separately rediscover the universal rules for creating complexity in software。

 the importance of evolution by selection was rediscovered and forgotten several times。



![](img/128e5f352d65ab8f30c4858da6c22d07_4.png)

But only the most recent movement called Agile of development。

 fully acknowledged and embraced testing as the primary selection mechanism that must be applied continuously。

Not just without the bad adaptations known in software as bugs。

But to guide the whole development process， this use of testing for guidance is also known as test driven development。

 T D D。Other agile best practices such as continuous integration。

 C I and continuous delivery C might seem like recent inventions。 however。

 they merely acknowledge that the software system must keep working continuously like any complex system。

If it ever stops working， making it functional again is like trying to resurrect a dead organism。

With these general insights， the question is no longer whether evolution coupled with strong selection applies to software。

 We know for a fact that it is the only way。 The question then becomes how to evolve their software and what kind of selection mechanism testing should provide。

Obviously， in software development， we don't have eons of deep evolutionary time to emulate natural selection。

 and the customers certainly won't appreciate testing all iterations of the software on them in the wild。

But natural selection is not the only way。We can use artificial selection。

 which is how humans evolved and transformed all domesticated plants and animals。

Artificial selection works on much shorter time scales。However。

 artificial selection requires much more than natural selection because now we must take full responsibility for what we want to select and precisely how we do this。

For that， we obviously need a suitable starting point for the software evolution。

 the first working version。But we also need to create an artificial habitat for the software to live in。

Of course， this artificial habitat depends on the type of testing you wish to perform。

Today I will focus on unit testing， which involves the smallest surface components that can be isolated and individually tested。

 such as functions and modules in C。Unit testing is。

 or at least should be the most extensive type of testing the original developers perform as they work on their code。

Generally， the lower the testing level， the more extensive the software habitat must be。

For unit testing， this artificially created habitat is called testing harnessness or testing framework。

Several such unit testing harnesses exist， most based on the heritage of the original X unit。

Harnesses that made their way into embedded software include CPP U Test and Unity。

 both used in the book Test driven development for Embedd C by James Granning。

Another popular testing harness is Google test or G test。

The links to all those testing currents will be provided in the video description。Today， however。

 Id like to show you a unique testing harness called embedded Test or E T。

 because it is much simpler than any of the alternatives。

 yet it can run all tests described in Granick's D D book。It T is written in C， but unlike unity。

 it requires no test runners。 I will explain that， in a minute。

The E T framework runs on host computers and embedded boards， with minimal porting。

ET is permissly licensed open source， and you can get it from GitHub either by downloading the zipped code or cloning the repository with Git。

Assuming that you have downloaded ET as a Z file， un zipip it into the directory where youll keep projects for this course。

After doing so， rename the embedded test main directory to lesson 49。

Get into the lesson 49 directory and right click on the Windows Explorer to open a terminal in this directory。

So far in this course， we have only used embedded integrated development environments such as K microcrovision。

 IER embedded workbench or TI code composes studio。

But unit testing is often performed directly from the command line。Therefore， today。

 you will also use just a terminal to see how this works。And by the test comes with examples。

 So let me just explain some of them。The most basic is their basic example。Simple as it is。

 it demonstrates the typical code organization for unit testing。

 where the code under test CUT is located in the SRC subdirecty。

 where the tests are in the test subdirecty。I will then first go to this test subdirecty to show you what the test run looks like。

 and then I will explain the details。So to run the test you type make， this invokes the make utility。

 which executes the build process prescribed in the make file located in the current directory。

After building this software， make immediately runs the tests。

 which is also customary in the unit testing。However。

 I need to back up at this point because it won't work like that on your machine。

 You probably don't have the Mac utility or the Gcc compiler installed。

 So your attempt to runmake will look like this。

![](img/128e5f352d65ab8f30c4858da6c22d07_6.png)

You have several options to get make and other unique style utilities commonly used in building and testing。

First， you can use Linux or Mac O OS instead of Windows。

 and the provided make file should work without any modifications。But even then。

 you must ensure that make and Gcc are installed。

![](img/128e5f352d65ab8f30c4858da6c22d07_8.png)

Another option is to activate the Windows substem for Linux WSL。

 but this requires installing a whole Linux distribution on top of which you'll still need to install。

 make Gcc and perhaps other things。Instead of all that。

 I use the Kos collection for Windows which has been specifically designed to provide everything in one simple installation。

Kuts downloads are available from Gitthub and contain all units like utilities commonly used in make files as native Windows executables。

To get Cs from GitHub， go to Cuils releases and download the latest digitally signed Windows installer。

 which is the easiest way。If you are allergic to installers。

 you can also download cuts as a zip file， but this requires additional steps to set the path and some environment variables。

You can install the Cs Windows executable or unziiv the Cus Windows zipip archive in any location。

 but I highly recommend avoiding locations with spaces or special characters such as program space files。

I installed my tus in the default location， C/ QP。After installation。

 the content of the cuts folder should look as follows。In the bin directory。

 you'll get the unique style utility such as make and commands commonly used in make files such as CPRM。

 M KDR， etc。In the min GW 32 directory， which stands for minimalist G for Windows。

 you get theno CC plus+ compiler for Windows。This is useful for building and running tests on the host computers。

And finally， in the newar non EAP B directory， you get the new cross compiler for Ar CPUus。

 This is useful for building and running tests on arm boards such as your TV C launchpa or STM 32 nucle。

If you installed ktos using the Windows installer， the following ktos directories will be added to your path。

Additionally， the environment variable kudos will be defined。However。

 if you install cuts from the zip file， you must manually modify the path and add the cuts variable。

 You'll need these settings to conveniently access the tools from the command line。Allright。

 this would be all regarding general tooling general testing habitat， if you will， for unit testing。

All this is not specific to the ET testing harnessness and will also be useful for other testing harnessnesses。

So now let's go back to the basic unit testing example and look at the COT code and the test and the tests around it。

The CT is trivial in this basic example and consists of the file sum dot H and sum dot C。

 The header file provides the prototype of the functions sum。

 while the source file contains the implementation。

 The function simply calculates and returns the integer sum of the integer x and y parameters。

The test file in the test subdirecty is more interesting。

 It starts with including the CT and the embedded test unit Test harness。

Next are two functions set up and tear down， which E T executes before and after each test。

 Next comes the test group， which provides the name of this group of tests and produces the output shown in the terminal。

Next come individual tests。 They start with the macro test with the test description。

 which in ET is an arbitrary string displayed in the terminal。Inside the test。

 you see the verify macros， which evaluate the provided boolean expressions。

 The test passes only when all verify expressions in that test are true。Otherwise。

 the test fails at the first failing verify。

![](img/128e5f352d65ab8f30c4858da6c22d07_10.png)

If you watched previous lessons 47 and 48， you might have noticed that the verify macro resembles the assert facility。

Indeed， other unit testing harnesses provide various test assertions to verify test conditions。

 However， this might create confusion with the true assertions in the code under the test。

 and therefore， E D provides the verify facility。This basic test group also demonstrates a skip to test。

 which E T does not execute。 temporarily skipping a test is often useful when you work on a quickly changing code。

Finally， this example contains an intentionally failing test which terminates the test run with a printout of the line number and the failing expression in the verify facility。

E T does not execute any tests after a failing one because the system might be in an unknown state and any subsequent tests might give incorrect results。

Of course， ET has many more interesting features， such as a special way of testing assertions in the CT。

 where you specifically test for and expect an assertion failure resulting in a passing test。

 but perhaps the most significant difference from other un testing harnesses written in C such as unity shown a moment ago is that ET does not need any test runners。

Unlike inity， tests are not separate C functions in E T。Instead。

 individual tests are just code blocks with their own scope for local variables。

 all within the test group， which is a function in E T。All right， with this quick introduction to ET。

 you should be able to explore other ET examples on your own as a homework from this lesson。

For instance， you should take a look at the log Free ring buffer code。

 which is quite useful in embedded programming。You might also like to see how to test C plus plus code with ET。

Finally， you might enjoy the LED driver example， which demonstrates that Ikey can test most of the code from the already mentioned TDD book。

 which I highly recommend。Speaking of James Granning's book。

 you might have noticed that I have performed the testing on the host computer。

Granning calls this strategy do all targeting， meaning that from day one。

 your code is designed to run on two platforms。 The final embedded target and your development host computer。

Dual targeting is sometimes confused with emulation of the embedded target on the host with software such as Q。

 E M U。But dual targeting is actually simpler。 You really build the embedded code with a native compiler on your host。

 such as Mink W Gcc。 And you also run the tests on your host。

The dual targeting strategy has a number of benefits， such as a much quicker evolutionary cycle。

 because you avoid a target hardware bottleneck。Also， it's easier to automate host based tests。

But above all， dual targeting influences your design， because to test embedded code on the host。

 you must pay close attention to the boundaries between the hardware and software。

I have used old targeting for many years and cannot imagine embeddedbed itself a development without it。

A team that embraces dual targeting will easily outperform any team that doesn't。

This is one of the most powerful tools in the war chest of professional embedded developers。

Having said all this， running the tests exclusively on the host will not cut it。

 And at least occasionally， you need to run the tests on your embedded target as well。

 The E T E testing harness has been specifically designed to make it easy。

 which I'd like now to demonstrate。So let's go back to the basic ETE example besides the make file used to build and test on the host。

 you can find two dot Mac files for testing on the EKTM4C and nucle C031 embedded boards respectively。



![](img/128e5f352d65ab8f30c4858da6c22d07_12.png)

Let's start with the EKTM4 C AK A Tiva Launpad board。

Plu it into your computer and open the serial terminal， such as termite。

 which the Qtools collection conveniently provides。

 You can launch termite from your terminal by typing termite ampersand。Now。

 type make minus F E K T M 4 c，1，2，3 G X， L dot Mac。This builds the same test code as before。

 But this time， using the new arm cross compiler from kos。As usual， immediately after the build。

 make uploads the code to the target， and normally， it would also run it。

 But the L M flash utility for the Tiva sea board has some quirks with resetting the board that I couldn't figure out。

 Therefore， this make file asks you to reset the board manually。After you receive the board。

 the tests execute， and the serial terminal displaypls the test run。

 which is identical to the one produced on the host。

You can also try the make file for the nucle board for that。

 plug the nucleo C031 board into your computer。If you still have the serial terminal open。

 close it and launch it again to connect to the new board。Now type make minus F nucle C0，31。

 c6 dot Mac。This produces the message that the USB drive is not provided。

 That's because nuclear boards show up on your computer as USB drives and can be programmed by simply copying binaries to that drive。

 This is very convenient because you don't need any additional utilities like L M flash for Tiva C。

On my computer， the nuclearcle board enumerated as the G drive。

 so I provide the USB drive as follows。Of course， you need to use the appropriate USB drive for your newcle。

 The main command， build， upload and automatically executes the basic tests on the board。Again。

 the output sent to the serial terminal is identical to the previous one for the Dva C and the original testing on the host。



![](img/128e5f352d65ab8f30c4858da6c22d07_14.png)

So now， let me quickly explain how this testing on the embedded boards， as well as on the host works。

As always in the method systems， the biggest problem is getting the information like the test results in this case。

 from the board to the host。Youve encountered this before in this course back in lesson 45。

 about software tracing with Prif。The solution applied in E T is also similar to lesson 45 in that the communication happens over a U art。

 This always depends on the particular board。 So in the test directory。

 you have the board support packages， BSPs， for Tva C and the nuclearcle board。

When you look inside one of these PSP， you see three ET called the functions。

 E T on in it initializes the Uart。 ET on print car transmits one character to the Uar。 And finally。

 E T on exit implements behavior after all tests finish an embedded target cannot really exit。

 So this function hangs in an endless loop， blinking the onboard LED。Here。

 I'd like to note that E T does not actually use Prif because it is a huge function and customizing it to work with any specific Y is implementation dependent。

 Indeed， one of the design principles for E T is to carefully avoid any dependencies on the standard library or anything else。

But none of these restrictions matter for the host computers。

 where the3 ET callbes are provided in the file EThost。 C in the ET directory。

That implementation uses the Fput C and exit functions from the standard library， but again。

 this is only for the host。This concludes this quick introduction to testing embedded software。

The most important takeaway from this lesson is that the only way to create nontrial software is to evolve it。

 And the winners of the software development game are those who evolve the software faster by applying better。

 smarter and more effective testing techniques to eliminate more defects sooner。

This software evolution is guided by artificial selection that requires building artificial environments for testing the software。

This lesson gave you a general idea about one such artificial environment for unit testing。

 a unit testing harness， but the general idea is similar for most such harnesses。

Newcomers to Unii testing are often confused as to what exactly is being tested。

 A first impression might be that testing is only about the C T code and the test。

But you must realize that all tests necessarily exercise both the CT and the test environment。

Therefore， methodologies like test driven development T D D recommend starting the process without the C T。

 The purpose of this first failing test is really to test the environment。And finally。

 when you start testing more systematically， you will accumulate many tests。On the one hand。

 such tests are valuable for checking that your software keeps working。

 and the new features don't break the old ones， which is called regression testing。On the other hand。

 tests are code， too， and the more code you have， the slower you can progress。

 The trick is to find the right balance and discard the less relevant tests。

 Keeping all tests for is a mistake。🎼If you like this channel。

 please give this video a like and subscribe to stay tuned You can also visit statemachine。

com/video course for the class notes and project Fire downloads Finally。

 all the projects are also available in Gitthub in a Quantum Le repository Mo embedded embedded programming course。



![](img/128e5f352d65ab8f30c4858da6c22d07_16.png)

Thanks for watching。