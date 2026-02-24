# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p20 -20-#19 GNU-ARM Toolchain and Eclipse IDE.zh_en -BV1fRt2efEms_p20-

![](img/592bdb63914cd41c46d8e5cc3c6ee4a0_0.png)

🎼Welcome to the modern embeddedd systems programming course。 My name is Miroseec， And in this lesson。

 I have decided to finally give in to the P demand and switch the development toolet from IER to the free and unlimited Gno arm compiler and the eclipse based integrated development environment。

😊，🎼The switch of the tool set is actually a good opportunity to review the code and to see what code portability means in practice。

🎼As you will see， much of the code you've written so far will work with newarm without any changes。

 mostly due to the compliance with the cortex microcrocontroller softwareftware interfaceface standard。

 CMC， however， a few IAR specific extensions in the startup code as well as board support package will have to be replaced with the new compiler equivalents。

So today， let's start with downloading and installing a development tool set for Newar。🎼Actually。

 there are many choices of such to sets， but you need to look for a tool set that supports your board here。

 the most important factor is the support for the specific debugger interface。

 which in case of the Tva C Lapa board is the Stlaris IDI。

🎼Since the board comes from Texas instrumentnstruments， the logical place to look is the ti。

com website， where indeed you can find a tool set called Code Composer Studio CCS As usual these days instead of giving you a specific fixed URL for downloading CCS。

 which most likely won't work in a few weeks from now， I recommend using the search box。

🎼So when you search for CCS， you quickly find the right web page。🎼In the download section。

 you can read that the CCS tool can be used for free with no limits with thegno GCC tool set。

🎼Click on the Windows download， which will lead you to the registration page and some more forms to fill to comply with the Exp control regulations。

🎼Eventually， however， you should be able to download the CCS setup program for Windows You need to launch it and agree to the licensing terms。

🎼In the next step， you can choose the installation directory。

 you can leave the default or choose your own destination。

 but I would strongly recommend against using directory names with spaces or any non standard characters。

The following step allows you to choose the CCS components here you need to expand the 32 bit arm MCUs and select a TV C series support。

 also you need to explicitly select a GCC arm compiler。🎼Yeah。🎼你。

🎼You don't need to make any more choices， so finally click finishinish to start the installation。

 which can take a couple of minutes。🎼When you launch Code composeosr Studio。

 it will ask you for the location of the workspace。

 The concept of the workspace is common to all tools sets based on eclips and is intended to group together related projects。

🎼From what I see， most people tend to use one default workspace for everything they do。

 but I recommend that you use a separate workspace for your different project groups。🎼Specifically。

 I recommend that you use a dedicated workspace for this embedded programming course。

🎼Since I keep all the projects for this course in the directory embedded programming。

🎼I also create the CCS workspace there in the CCS subdirecty。🎼Yeah。🎼So finally。

 you are ready to create your first project。 This part is specific to this particular repackaging of eclipse as code composes studio。

 But the general process is similar in all eclipse space integrated development environments。

🎼The first selection you make for a new project is the embedded target here you need to choose the Tva C family and the specific TM4 CMmCU within the family that is sorted on your TVC launchpad board。

Next you choose the connection to the target， which in case of your launchpad is the Stlaris ICDI。

🎼Please note that the support for this particular debugger interface was the primary reason you selected the CCS Toet in the first place。

🎼。🎼In the next step you will need to name the project here I suggest a generic name lesson for projects belonging to this embedded programming course。

🎼This name will be fitting for all upcoming lessons because you will simply clone this original project instead of creating a new project from scratch each time。

🎼For the same reason， you also cannot create the project in the default location inside the Workspace directory Instead you create the project in the directory where you keep all previous lessons on my machine。

 it is embedded programming， but it can be different on your computer。

🎼To finish with a project location， you need to add the lessonson 19 subdirecty for this particular project。

🎼The next and final step is critical here you need to select the G tool set instead of the default TI compiler for arm。

🎼When you click finishish， CCS will create your lesson project in the workspace and in the lessonsson 19 directory on disk。

🎼You can build a project by clicking on the hammer button at the top。 As you can see。

 the build process succeeds with zero problems。🎼So let's take a quick look at the code that CCS has generated for this project。

🎼First， you get the main do C file with the empty main function。🎼Second is the startup code。

 which is very typical for code supplied by siliconon vendors。 Unfortunately。

 it has all the shortcomings that I've covered in lessons 13，14 and 15。For starters。

 this startup code uses proprietary exception names that are not compliant with CMCs。🎼Also。

 the vector table requires editing every time you start to stop using a given interrupt handler。

 For example， to use the cyst handler interrupt， you would need to modify the appropriate entry in the vector table and you would also need to declare a prototype of the handler at the top of the file。

🎼And finally， the provided implementation of the exception handlers contains endless loops that tie up the CPU。

 In other words， if any of such exception handler is ever executed， the system will freeze。

 which the user will perceive as denial of service。

 This is not acceptable in any production grade code。🎼你。

🎼The generated code also contains the file with the extension do Ls， which is the Lier script。

 The purpose of this file is to tell the linker where Rom and Ram are located in the address space and where to place various program sections。

 You saw an example of a linker script for the IR tool set in lesson 14。

 Here you have a Lier script for the new tool set。This is again a beaten path Lier script。

 which matches the startup code。🎼Among others， it allocates the stack as the last section in Ram。

 In my opinion， this is a mistake， because stack grows toward the lower addresses on arm。

 And so a stack overflow could damage the Ramm sections above it。 In fact。

 this seems the likely cause of failure in the infamous Toyota unintended acceleration cases。

 As I have described in the article， Are we shooting ourselves in the foot with stack overflow。

 I provide a link to this article in the comments section for this video。🎼M。

🎼So it seems that the code generated by CCS is not terribly usable。

 but the good news is that you can fix all the issues in it by applying the lessons you've learned so far。

🎼The first thing then is to copy all the relevant code from the previous lesson 18 to the new lesson 19 folder。

🎼The usable files are RbsSsp。hsp。c， main。c startuptm4 c。c。

 and the masterheader file for your Tm4 CMmCU。🎼Interestingly。

 the final copy to the lesson19 folder immediately show up inside your project This is how all eclipse projects behave All source files in the project directory are automatically included in the project and you don't need to explicitly add them as it was the case in the IER embedded Workbench IDE。

🎼This eclipse policy has its disadvantages， too， however， for example。

 now you have two startup files in the project， so you need to delete one of them。

🎼So let's try to build this project。This time you get some errors。

🎼The first error is that the compiler cannot find the include file core underscore CM4。

 H This file is part of the CMmC， which is not directly available in Code Composer Studio as it was in IAR embedded Workbench。

This is not a big problem as you can easily provide CMs yourself。

🎼Here I have prepared for you a directory CMs， which contains the core header files in the subdirecty include。

You should copy the CMCs directory into the folder where you keep the lessons of this video course。

 that way you can reuse CMCs in all upcoming lessons。🎼Of course。

 copying a directory is not enough because you also need to tell the compiler to look for include files in this new directory cmC/ includelude。

🎼You accomplish this by means of the project Pro dialog box。

 which you open by right clicking on the project and selecting the Pro pop up menu。🎼Specifically。

 you need to choose the directory's property in the new compiler group where you find the include path pane。

🎼To add a new improve directory， click on the plus button。

🎼The first easy way is to simply browse your file system for the CMmC s include directory。

🎼But the big drawback of doing this is that you add an absolute include path。

 which will only work on your computer with this specific C embedded programming CMC's directory。

🎼A much better approach is to create a relative include path， which will work on any computer。

🎼The Eclipse ID allows you to create relative paths by means of system variables。

 specifically in the list of these variables， you can choose Project underscore lock。

 which will create paths relative to the project location。🎼From the project location。

 you need to go one level up and then you append CMmC s includelude。

🎼Regarding the use of directory separators on Windows。

 you can use either back slashes or forward slashes。

 I use forward slashes because they seem more universal。🎼When you build again。

 you see that the previous include error is gone， but you got a bunch of new errors。うん。

🎼As it turns out， most of these new errors come from the startup code。

🎼This should not be actually that surprising because this code was written with IAR specific extensions to the C language。

 which the new compiler does not recognize。🎼So here I have prepared for you the startup code which was rewritten with Igno specific extensions to the C language。

🎼As you will see in a minute， the startup code must closely match the linker script。

 so I included a matching linker script as well。To include these files in the project。

 I simply copy them over to the lessons 19 directory。

🎼I need to allow overr the previous linker script and I also need to remove the previous startup code。

🎼う。🎼When you switch over to the Eclipse ID， you can see that the project is immediately updated within new files。

🎼Let's quickly review the code so that you know how it works First， in contrast to the old file。

 the new O new specific startup code is compliant with the latest Cms 430。

🎼When you scroll down to the vector table。🎼You can see that it has a special attribute section IR vector。

🎼This is a new specific extension which tells the compiler to place the following symbol。

 the vector table in this case， in the specified section。🎼To see where this section is。

 you can open the new Gno linker script。🎼Or you can see that dot ISR vector is the first section in RA。

🎼The RAM section， in turn， is located at address0， so the vector table at the beginning of RAM is also at zero。

 which is exactly what the arm CPU needs。🎼As you hopefully remember from lesson 15。

 the first element of the arm vector table is the initial top of stack。

 so here you see an ampersand meaning address of underscore underscore stack and cast on an int。

🎼The symbol underscore underscore stack end comes again from the Lier script。🎼Indeed。

 when you scroll a bit down， you can see the dot stack section as the first section in RAM。

🎼Contrary to the beaten path approach of putting the stack as the last section in RA。

 I recommend placing it as the first section that way a stack overflow won't be able to damage any other RA sections。

🎼As an additional bonus， a stack overflowing into the unmapped memory below Ram will be detected automatically by executing the heart faultt exception。

 so you will know about it。🎼Speaking of the stack， you can change its size by adjusting the symbol stack size at the top of the linker script。

🎼Going back to the startup code， the symbol underscore underscore T end is provided by the linker。

 but the compiler does not know about it to tell the compiler you need to declare underscore underscore T end as an external variable at the top of the startup file。

🎼你。🎼The other elements of the vector table are addresses of handler functions for cortex M exceptions and interrupts。

🎼As you can see， the table already contains all the specific handlers with names compliant with CMCs。

 so you don't need to edit the code at all to use any of these exceptions or interrupts。

🎼At the same time， if you don't use a given exception or interrupt。

 it will be automatically replaced by the default handler implementation。

This is accomplished by means of a pair of no specific attributes， weak and alias。

🎼The weak attribute means that a symbol definition can be overridden by another definition。

 and the linker will quietly discard the weak definition without reporting that the symbol was defined twice。

 The alias attribute means that if the symbol is not defined。

 the alias symbol should be used instead。🎼So for example。

 if you define the system handler in your application。

 the linker will take your nonwe definition If you don't define system handler。

 the linker will take the default handler alias for it and will not report any errors。🎼Notice though。

 that not all handlers are alias， this is because the standard fault handlers are actually defined in this startup code so that you don't need to define them in your application。

🎼But these handlers are not the primitive endless loops with denial of service。

 The provided implementations use inline assembly to carefully avoid any use of the stack。

 which might be corrupted at this point。🎼The assembly code stores the information about default in R0 and R1 registers and then branches to Ast handler where you can perform your last damage control。

🎼Here you encounter an addict new specific attribute naked。

 which instructs the compiler not to do any stack operations for this function。

🎼When you try to build again， you still have an error this time in PSsp。c。🎼By now。

 you should know what's the problem。 The extended keyword underscore underscore Staless was an I R extension for stackless functions。

 Igno， you need to replace it with attribute naked。Another build。🎼This time。

 the compiler complains about underscore underscore enable Inter。

 which was an IR intrinsic function I I this operation needs to be replaced with underscore underscore enable IRQ。

🎼Another build end。🎼哈利路呀。🎼No errors at all。🎼Congratulations。

 you have just finished your first port of deeply embedded code from one tool set to another。

🎼Time to plug in your Tva Launchpad board to test the code。

🎼To download the code to the flash memory of the board and start debugging。

 you press the bug button at the top。🎼Theeddybugger is set up to stop at the beginning of Maine。

 and indeed it does。🎼Press the go button to run the code and watch the LED change color once a second。

🎼Click on the pause button to break into the code and watch it stop in the background loop。

🎼By the way， the different screen layout that you see now is called in eclipse the debug perspective。

 This is to differentiate this view from the edit perspective that you saw during editing the code。

The debug perspective provides all the debugger views that you encountered in IER。

 such as the disassembly view。You can also single step through the code and watch the LED being turned on and off。

🎼You can set breakpoints， like for example， inside the cysttic handler to see how frequently this interrupt is called。

🎼，🎼。🎼う。🎼，🎼To stop the debug session and return to the editit perspective。

 press the stop button at the top。🎼As the final step of this lesson。

 let's modify the behavior of the code copied from your previous IER project to change the color of the toggled LED from red to blue。

 for example。🎼Build a project and start debugging as before。🎼Watch the LED blink in a new color。

🎼This concludes this lesson about switching the toolet took no arm and eclipse based code composer Studio CC S。

 the startup up code and linkscript from this lesson are much closer to production quality than the typical code distributed by Silon vendors。

 The code is compliant with Cms and will work with any toolet based on Goar， not just with C S。

🎼You can easily adapt it for any arm cortex M microcontroller。

If you'd like to learn more about using the free Gnew Ar toolet。

 I would recommend my10 part articleBuilding Bear metalal Ar Systems with Gnew。

 which in 2007 was the most popular article on embedded。com。

🎼This article talks about the classic arm 7 arm 9 course。

 but much of the information still applies to cortex M as well。

🎼I provide a link to this article in the description of this video on YouTube。🎼。

The project download for this lesson will come in two parts。The usual lesson 19。

zip archive with the CCS project and code for the lesson and the cmcs。

zip archive with the CMmCs code。In the next lesson， I will finally talk about race conditions。

 which is a concept that you absolutely need to understand to effectively work with interrupts。

If you like this channel， please subscribe to stay tuned， you can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/592bdb63914cd41c46d8e5cc3c6ee4a0_2.png)

🎼そ。