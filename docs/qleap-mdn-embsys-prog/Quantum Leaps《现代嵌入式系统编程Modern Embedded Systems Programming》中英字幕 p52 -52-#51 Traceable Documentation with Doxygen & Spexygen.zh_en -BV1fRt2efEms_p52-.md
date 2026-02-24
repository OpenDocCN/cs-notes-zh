# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p52 -52-#51 Traceable Documentation with Doxygen & Spexygen.zh_en -BV1fRt2efEms_p52-

![](img/c3a5a3b4c487d4f61b3a7a6537600393_0.png)

🎼Hello and welcome to the Moern Em Systems Program course I'm Miro Samec and in this lesson I'll show you how to document your software with oxygen however I'll go several steps beyond just documenting the source code you will also see a oxygen extension called Specgen for creating traceable for more specifications such as requirements architecture design and many others mandated by functional safety standards。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_2.png)

Let me start by giving you an idea of what such traceable documentation looks like。

 because if you think of a career in embedded systems。

 you will be increasingly required not only to create documentation but to create traceable documentation compliant with international functional safety standards such as IEC 61508。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_4.png)

Tracceability is the cornerstone of any formal documentation system。

 especially those intended for managing functional safety。

It is the explicit representation of the relationships among work artifacts。 For example。

 a requirement can be connected to a code element that fulfills the requirement。

Or a code element can be connected to a unit test that tests that code。 The IEC 61。

508 functional safety standard addresses the bi directionional nature of traceability。

 backward traceability begins at the specific work artifact and links it to the upstream artifact。

 For example， a code artifact can be linked with an original requirement。

 or a test artifact with an upstream code artifact。

Backward traceability is the most natural and efficient way of specifying hierarchical relationships such as subclass。

 superclass in object oriented programming， OO P。In most documentation systems， including spec。

 the developer explicitly defines backward traceability links among work artifacts。

Forward traceability begins at the original artifact and links it with the resulting downstream work items。

 For example， a requirement can be linked with the source code element that implements that requirement。

 In contrast to backward traceability。 forwardward traceability links can and should be generated automatically based on the existing backward traceability links。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_6.png)

Please know that forward traceability is typically recursive。

 meaning that if an artifact such as a unit test traces to a code artifact and that code artifact traces to a requirement。

 then the test artifact also traces to the requirement artifact。

Spexygen generates recursive forward traceability because it is needed to identify the potential consequences of changing a given artifact。

 which is called impact analysis。 In the end， backward traceability and forward traceability。

 result in bi directional traceability， which is highly desired for functional safety certification。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_8.png)

Of course， commercial application lifecycle management。

 ALM tools can automate traceability management， but specgen offers similar capabilities as a free and open source alternative。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_10.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_11.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_12.png)

Spexgen's most significant advantage is that it seamlessly incorporates source code in the bidirectional traceability management because it is based on oxygenx。

 In other words， specgen is a universal system that combines functional safety specifications with source code documentation。

Now， let me step back and show you how to create traceable documentation with Sp。

You need to start with oxygen。Type oxygenygen in the search box and go to the website。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_14.png)

Download oxygenuxion for your platform， which is Windows in my case。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_16.png)

The installation is straightforward。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_18.png)

Now， in the downloads for this lesson number 51， you will find the examples for oxygen。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_20.png)

Let's open the folder for lesson 51。And look inside example 0。

This is just some code organized as Herot H file， sorted C file and a couple of tests。 At this point。

 the project knows nothing about oxygen。But launch the freshly installed Dox Suwiizard application。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_22.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_23.png)

For the working directory， select lessons 51 example 0。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_25.png)

For project name， type example。For project synopsis type， Do example。For project version type 0。0。0。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_27.png)

You can select the project logo。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_29.png)

For the directory to scan for source code type dot， meaning the already selected working directory。

But here you need to check the scan recursively box because the code is in subdirectories。

 INC source and test。For destination directory type dot as well。Next， the desired extraction mode。

 all entries and include cross reference。You can select optimizeim for C because this is C code。Next。

 you can leave the pre selectedlect HTML and latex output formats。

And you don't need to change anything in the diagrams tab。 Finally， you can run oxygen。

 after which you can click on Shall H Ml output。 This opens your browser。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_31.png)

The main page doesn't show much， but you can view your files such as Heredod H。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_33.png)

And source that sea。Doxygen has generated some documentation boxes for functions and datastructs。

 but they only show the signatures。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_35.png)

However， when you go to the source code for this file and hover your mouse over various code elements。

 you can see the balloon help for them。 This is useful and might be a faster way to explore and learn new code base。

 Although modern ideass also have this capability。 Now。

 let's look at the project directory because the oxygen has produced some output there。😊。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_37.png)

You can see the new HTML directory， which contains the static website you just browsed。

 but you also see the latex directory because you allow oxygen to produce latex output。

This directory does not contain any P D F yet， but it has a make batch file， which you can run。 Now。

 this batch file requires a attack processor， and I've installedmicite。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_39.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_40.png)

But eventually， the make batchch produces Pf output called Refmanot Pf， which looks like this。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_42.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_43.png)

Before moving on， save the Douxy Rezard project， which creates the file douxy file in the project directory。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_45.png)

Now， let's move on to example 1， which already has its dox file。

 So let's open this one in Doy wizard。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_47.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_48.png)

Not that the version number， for example，1 is 0 do 0 do1。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_50.png)

Now， let's compare the whole example0 directory with example one to see the differences。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_52.png)

The Herod H file contains the same code， but now it has special oxygenxygen commons。

These oxygen commons are just commons， so the compiler ignores them。Actually。

 so does oxygenxygen unless the common starts with a special character。To be processed by oxygen。

 a multiline comment must start with an exclamation point or a star。

A single line double slash comment must start with again， an exclamation point or a slash。Most often。

 a oxygen comment must precede the documented element。

 but oxygen also supports comments after the element。

 when they additionally start with a less than character。Inside the oxygenxgen Commons。

 you can see some special oxygenxygen commands that start with an ampersand or a back slash。

To use oxygen effectively， you need to learn about the available commands。

 But here you will see some of the frequently used ones。

 The brief command provides a brief description of the element。

Power command starts a paragraph with a title， and parameter command documents a function parameter。

Compared to example 0， example 1 adds a new file， main dot docs。

 which consists of one big dox comment。 This file provides the main page with the description of the project。

Here you can see that Doxygen allows you to create textual documentation of any kind。

 not just code commentss。Again， this textual documentation uses some oxygenxy commands。

 such as main page， section， verbatim or reference。

 You can also see an example of using an image in the documentation。Finally。

 let's look at the difference between dexiophiles。The version number in example 1 has changed to 0。

 0。1。 The project logo has been changed to the relative path instead of the absolute path previously。

The image path has been added as dot dot， meaning a relative directory1 level up。

And the HTML option generaterate tree view has been changed to yes。

You can access and change all these options from Duxy Wiizard， but now you should use the expert tab。

So finally you can run oxygen and review view they generated HTML output。

This time you can see the main page generated from your main dot Dos file and the tree view along the left edge。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_54.png)

The generated links from thef commands allow quick navigation。 for example， to the Herdot H file。

 which now contains all brief descriptions。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_56.png)

Detailed descriptions and parameter descriptions。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_58.png)

The last example number two shows how you can add a formal specification。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_60.png)

Such as a software requirement specification， SRS。The goal is to represent the requirements so that oxygenxygen can display reference and search the individual requirement work items。

 There are a couple of ways to achieve this， but the simplest way applied later in speciggen is to represent work items as doxygen subsections。

 You'll see in a minute how it looks and works。 However， once the work items are specified。

 you can reference them from other work items or code items。

 This is the explicitly provided backward traceability。

One more thing I wanted to point out with example too is that the SRS can be incorporated as a subage of the main page。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_62.png)

When it comes to generating the HTML and Latin outputs， you could do this from Duxy wizard。

 but you can also do this directly from a command prompt where you can change to the project directory and type Dxygen。

The oxygenxgen directory should be added to your path during installation。When you launch it。

 Dxygen will look for the douxy file and process it if found。

The generated HTML output is located in the HTML directory where you can just double click on the index。

 HTML file to open it in your browser。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_64.png)

So here is the example 2 in HD。 The main page now lists software requirement specification。

 So let's click it and take a look。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_66.png)

The requirement artifacts are clearly visible in the S RRS document and the tree view。

 You can also quickly navigate to the individual requirement items from any view。

When you copy a requirement name and paste it into the search box， Doxygen finds it。

So these are all the properties you wanted， but they are enabled by the names assigned to the requirements in the industry。

 Such names are known as unique identifiers or U I Ds。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_68.png)

Many naming conventions exist to ensure that the U Ids are indeed unique。

 but specifically for oxygenxgen， the U Is should follow the naming restrictions for identifiers in programming languages such as C or Python。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_70.png)

You should use only underscore and avoid dashes or dots to separate the various fields in the UidDs。

All right， So example 2 shows how far you can push it in pure oxygen。

You can write specifications such as S RRS， and you can create your own traceable work artifacts alongside already traceable code artifacts。

But there is undoubtedly a lot of room for improvement。 First。

 the specifications can be better structured and better formatted。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_72.png)

But most importantly， the documentation contains only the explicitly created backward traceability links。

Of course， you could manually add and maintain forward traceability links as well。 However。

 this would quickly go out of sync with the backward traceability because it would violate the dry principle。

 Do not repeat yourself。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_74.png)

As mentioned before， forward traceability can and should be generated automatically。Additionally。

 in any traceability view， the brief descriptions of work artifacts next to the cryptic Uids would be very useful。

 so they should also be generated automatically。Which leads us to the specgen system that provides precisely the features just described。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_76.png)

First， you need to get specgen and put it on your computer。

 The easiest way is to search for specgen and click on the Gitthub link。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_78.png)

In a Github reportpo， you can just click on the code， drop down and download zip。

You can unzip P into the lesson 51 directory。Spexgen comes with an example that is very close to the examples you just saw for pure oxygen。

 So again， let's examine the differences from the last example， too。

 to see what changes were introduced in the example for speciggen。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_80.png)

Let's start with the differences in the SRS software Re specification。On the spec side。

 you can see that each work item specific starts with a custom spec command and percent U I D。

 which takes two parameters。 the unique identifier and a brief description。

The U ID command ends with the N UID custom Sp command between those two。

 you can have various line items such as description defined with the U ID L item custom Sp command。

The backward traceability of the work item is specified by the U ID BW tracece custom Spec command。

This command takes a parameter brief， which indicates that you want Spgen to generate a brief description of the following traced Uids。

The traced UIDs are specified with the TR custom Sp Command。Finally， the custom Sp command。

 Amreu ID FW trace indicates that you wish specgen to generate the forward trace in this precise place in the work item specification。

In other words， the UIDFW tracece command is a placeholder for the generated forwardward traceability section。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_82.png)

All these commands are documented in the spec manual generated with spec。

 You can access it from the spec Github repo。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_84.png)

Besides being used by specgen to correctly parse the specification。

 the custom commands provide a formal structure for the work items。 Of course。

 you can easily impose your own company's standards on top of those commands。 For example。

 you can have templates for U I D light items that must be present for requirements， design。

 functional safety docs， et cetera。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_86.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_87.png)

Spexian also provides a separate set of custom commands for specifying code items。

These are similar to command for work items， but I use insideted oxygen code Commons where oxygen already applies a specific formatting。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_89.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_90.png)

You can find examples of the custom code commands in the head H file。

The crucial aspect here is to properly define the U I D of the code item。

 which spec will later use for traceability。 The code U I D you provide must be recognized by oxygengen。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_92.png)

Once you prepare your documentation by applying the customs spec commands。

 the next step is to generate the traceability information。 The spec system provides a Python script。

 Spgen dot P， Y that automates this step。Before you can run the script， however。

 you need to tell spec which files you would like to generate and where to generate them。

 This is done in a configuration file， Spect Jason located in your project directory。

In the adjacent file， you specify the files you wish to trace。

 which means collecting the traceability information。

You can also specify the output director of the generated documentation。

 The name of the include file for oxygen and the set of files to generate。 At this point。

 you are ready to run this dot P Y script and see what it generates。 At first。

 you will run the script manually for this copy the current project directory and open a command prompt。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_94.png)

Change to the project directory and type Python relative path to the specgen directory and Spgen。 P。

In the console output， you can see that Specgen reported that the requested forward traces for two UIDs were missing。

 which probably means that you still need to provide some tests。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_96.png)

But more interestingly， the spec at P Y script has generated a new folder。

 specs in your project directory。 This folder contains the code you told it to generate。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_98.png)

To see what specig has done， say to the S R document。

 let's give the generated S R S the ducks against the original。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_100.png)

As you can see， Sp generated the forward traceability sections and also added the brief descriptions to the backward traceability sections。

The generated traces include both work items， such as requirements and code items， such as full X。

The forward traceably sections are also recursive， whereas the levels of dependency are indicated by the indentation of the trace commands。

 You'll see in a minute how it looks in the oxygenxgen H M L output。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_102.png)

Speaking of which， the final step is to run oxygen， but before that。

 let's examine the doxyophil because now it needs to contain some spec stuff。First。

 the Dxy file includes the spec file from the spec installation directory starting the spec environment variable。

 This spec file defines all the custom spec commands you have seen before。Second。

 the doxy file input comes from two sources， fileses that were not processed by spec。

 such as main dot docs and files that were generated by spec。

 conveniently listed in the generated specxy Ik file in the specs directory。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_104.png)

All right。 So now let's run oxygen manually， remembering to define this oxygen environment variable。

As usual， oxygen has generated the HTML output in the HTML folder inside your project directory。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_106.png)

Please note the more attractive and modern styling of the oxygenxgen output。

 This styling is coming from specogen， which in turn customized it from the Doxogen A project。😊。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_108.png)

As you can see， the work items such as requirements。

 are consistently formatted with clearly delim line items and now contain all the backward and forward traceability links。

You can easily navigate to any work item or code item。

You can also search for them in the Doxygen search box。

You have arrived at this final output by running oxygen and oxygen manually。 But， of course。

 these two steps can be merged and ordered。

![](img/c3a5a3b4c487d4f61b3a7a6537600393_110.png)

In fact， this packaging example comes with a make that batch file。

 which runs the whole process in one step。By default， this batch file produces HTMLmL。

 but it can also generate PF when invoked with a minus PF argument。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_112.png)

🎼This concludes this quick introduction to oxygen and spec Together these two tools provide a powerful automated documentation system that is a free alternative to costly commercial solutions。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_114.png)

![](img/c3a5a3b4c487d4f61b3a7a6537600393_115.png)

🎼The toy example presented here doesn't relate to justice to specygen's power， however。

 you can view a real life documentation created with specgen by visiting statemachine。com/qPc。



![](img/c3a5a3b4c487d4f61b3a7a6537600393_117.png)

🎼Happy documenting。 And thank you for watching。