# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p01 -01-#0 Modern Embedded Systems Programming_ Getting Started.zh_en -BV1fRt2efEms_p1-

。

![](img/c6310ad84cb61b574b82e56aa7526205_1.png)

Welcome to the modernern embeddedded System programming course。In this course。

 you'll learn how to program embedded microcontrollers that modern way。From the basics。All the way。

To the contemporary modern embedded programming practice。

The unique approach of this course is to step down to the machine level frequently and show you exactly what happens inside your embedded microcontroller。

This deeper understanding will allow you to apply the concepts more efficiently and with greater confidence。

My name is Miro Samak， and I am an embedded software engineer with over 30 years of experience。

I enjoy teaching and this video course， my books， articles and conference presentations helped many developers improve their skills。

 pass job interviews and get hired for embedded programming positions。

This embedded programming course has been going on since 2013。 So people ask， is it still relevant。

The answer is yes， perhaps even more so now than in the beginning， for two main reasons。First。

 this course focuses on the essential and fundamental concepts in embeddedmed programming that never go out of style。

And second， this course is based on the prevalent arm cortex M architecture。

 which has exploded in popularity。Knowledge of arm cortex M is the most sought after skill that employers are looking for。

As far as the prerequisites for this course are concerned， I start with the basics。

 but this part is short and focused on the embedded aspects of programming in the sea。Therefore。

 you might need to supplement this course with additional study of the C programming language。

It would also be good to know how a CPU works。

![](img/c6310ad84cb61b574b82e56aa7526205_3.png)

To get the most out of this course， you can and should follow along and run the discussed projects on your PC。

To do this， you will need some hardware， an embedded board， and software。

 an embedded development tool set。The main embedded board used throughout the course is Stephen C launchpad from Texas Instruments based on the Ar cortex M4 F CPU。

The board is inexpensive， self contained and includes the build in hardware debugger that enables single step debugging and inspecting the internal CPU state。

 which is essential for this course。The board is still in production and is available from numerous distributors。

The course downloads now also contain project versions for the newer STM 32 Nucle C031 C6 based on the arm cortex M0 CPU。

The board is also inexpensive， self contained and includes an even more versatile built in hardware debugger。

Other inexpensive arm cortex M boards， like the first two， might be added in the future。Also。

 the first few course lessons use a simulator。 Therefore， you don't need the hardware immediately。

 However， later lessons where you interact with the MC U peripherals require an embedded board。



![](img/c6310ad84cb61b574b82e56aa7526205_5.png)

After you receive your embedded board and plug it into a USB port for the first time。

 you need to check for the proper installation of the USB drivers。

 Open the device manager by right clicking the Windows icon and choosing the device manager option。



![](img/c6310ad84cb61b574b82e56aa7526205_7.png)

For the Tva seaboard， the correct driver should be the Stlaris in circuit debug interface。

 If you see anything else， you need to reinstall the driver。For that。

 you first need to download the correct USB driver。

 either as described in the packaging of your embedded board or from the companion page to this video course at statemachine。

 co/vide course。After downloading unzipped the driver somewhere on your disk。 next。

 right click on the device description and choose update driver。

Select browse my computer for drivers and point to the directory where you unzip the drivers。

If for any reason the USB installation doesn't work。

 you can always click on uninstalled device and try update driver again。

The described procedure needs to be done only once for a given board。

 but you need to repeat it when you get a different board。 For example， for the nuclear board。

 you need to use the S link drivers。As far as the software is concerned。

 you need an embedded development tool set。The course started with the I R embedded workbench for arm。

 a professional tool set with good compiler and stable debugger。For many years。

 this toolt used to be available under a free size limited kickstart license。But recently。

 this has changed， and the only free option left seems to be a two week evaluation license。

For that reason， the project downloads for this course have been updated and now contain versions for multiple tool sets。

 including Kyle M DK， which I introduce later。But going back to IER。

 if you wish to use the same tool set as the video Le 1 through 18。

 you can download the IER evaluation。The installation is straightforward， although it takes a while。

I only suggest installing the tool set to a directory name without spaces and special characters。

 For example， I installed my IR tool set in the C tools IR directory。

After launching the IAR embedded workbe for the first time you might need to request the license。

 you'll need to register it with IAR and receive the license key via email Once you get it。

 you need to type it into the license dialog box。Kilm De Microcontroller development kit is another professional development toolet used in this video course。

In contrast to IAR embedded Workbench， KilM DK has been offered under increasingly permissive licensing。

 including free KilM DK V6 community Edition。This course has used Kyle M decayK starting from lesson 21。

 but project versions for Kyle have been added for all lessons， including lessons 1 through 21。

 which were initially presented with IR embeddedded Workbench or T I Code composeosr Studio。

For this course， you need to download Kyle microcrovision。



![](img/c6310ad84cb61b574b82e56aa7526205_9.png)

On the next page， click on download KyleM De。Next， you need to log into the Ar developer Port。

 If you don't have an account there， you must register first。



![](img/c6310ad84cb61b574b82e56aa7526205_11.png)

![](img/c6310ad84cb61b574b82e56aa7526205_12.png)

After you log in， you are finally allowed to download the latest MK edition。

The MDK installation is straightforward and the default locations for the MDK tool set and the so called MDK packs are acceptable。



![](img/c6310ad84cb61b574b82e56aa7526205_14.png)

The finishing step launches the Kyle pack installer。

 but you can close it for now because the purpose of the packs will become clearer when you open one of the K microvision projects。

I will explain how to get the project for this course in a minute。

 but to finish the tourrset installation， let's open a Kyle project。

 Sa for lesson1 by double clicking on it in the file Explorer。



![](img/c6310ad84cb61b574b82e56aa7526205_16.png)

![](img/c6310ad84cb61b574b82e56aa7526205_17.png)

When such a project opens for the first time you get a dialog box informing you that the required device family pack is missing。

 It means that the project uses a device TM4 C in this case。

 for which the toolet still needs information when you click install the pack installer automatically download and install the specific device。

The next issue you need to address is license installation。 Select the menu file， license management。

 and in the dialog box， click on get license via Internet。

This will send you to the Ar Kyle website where you need to fill out a lengthy registration form。

 but eventually you should get your MDK community license via email。

The final issue you need to fix concerns the stellarlaris IDIDbuggger on the TvaC launchpad board。

In the project view， right， click on the Dbug target menu and choose options for target debug。Next。

 click on the Dbug tab and expand the drop down list。

 St La's IDI is missing because Kyle M DK no longer supported by default。However。

 you can add the St Las IDI support by downloading the MDK extension from the companion web page to this video course。



![](img/c6310ad84cb61b574b82e56aa7526205_19.png)

After downloading， just run the provided installer。



![](img/c6310ad84cb61b574b82e56aa7526205_21.png)

When you open any Kyle project for Tivai now， the Stlaris ID ID Dbuggger is available。



![](img/c6310ad84cb61b574b82e56aa7526205_23.png)

In the last minute of this video， I'd like to describe how to download the projects for the lessons of this course。

Also， I need to explain the new structure of the project。

 because it has changed from what is shown in the videos。

So the project for all lessons are available for download from state dashmachine。 co s video course。

 which is the primary resource for this course。Additionally。

 an increasingly important resource is the GitHub repository， which also hosts all projects。

The projects are organized hierarchically to accommodate multiple embedded boards。

 tool setss and generally offer extensibility for the future。For example。

 projects for lesson 4 are located in the directory lesson dash 0，4。Inside。

 you can find subdirectories named after the embedded boards and embedded toolets。

Projects for Tiva C are abbreviated to TM4 c 1，2，3。

 while SDM 32 Nucle board is abbreviated to STM 32， C 031。

This is followed by the name of the embedded tool set， such as I R or Kyle。Inside the subdirecties。

 you can find the actual project for the corresponding toolet。

 the source code and all other code the project needs。

This makes the project self contained and free from external dependencies。

Special cases are simulator projects which don't require a physical board。

 although they are prepared for a concrete target， typically Tiva C。



![](img/c6310ad84cb61b574b82e56aa7526205_25.png)

🎼。🎼This concludes this introductory lesson to the modern embedded system programming course。

 I hope you find it informative and interesting。 learn something useful。

 sharpen your skills and think about embedded programming differently。🎼If you do。

 please support this channel by subscribing， clicking the like button for the videos you like。

 posting comments and spreading the word about this course。

