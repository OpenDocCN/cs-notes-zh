# Engineering Clinic《网络模拟器3教程｜Network Simulator 3 Tutorial Series》中英字幕deepseek翻译 p06 -06-NS3 Introduction _ NS3 Tutorial 2.zh_en -BV1aQmtYZEPr_p6-

![](img/940df16f7acfbadc396567b6fb70622d_0.png)

I am predict much。From the university since the flight get delayed for two hours。

So in this midnight I'm just recording the lecture on NS3。

 so I'm just going to tell about the basic introduction to network simulator3。

And so after this video I will be just taking you to the set of slides where you can able to install network simulator3 and with some basic introductions of network simulator3。

Actually NSS3 NSS3 it is not the upgraded version of network simulator to because NSS2 has been basically primarily focusing on two languages called as VoTclL and the C++ whereas NSs3 is mainly on C++ and with optional Python binding so that means either if you are comfortable in C++ you can try with C++ or if you are comfortable in Python you can able to do everything with Python but the C++ is more powerful and advantages for NSs3 for NSs3 as well so many modules are available for C++ in the NS3 but since Python developers are very less in the market so Python is just now coming up in NS3 but very soon in future NSs3 will just gearing up for Python。

So that's why these very good advantages of NS3 so NSS2 they have stopped with the development I mean almost in 2011 they have stopped it so beyond 2011 no new version have been come up due to the reason that NS2 was so the architecturee is vague it sort of that means you need to learn two languages C++ as well as what you sell for dising any protocol or any algorithm or any performance matrix so you need to know two languages but in NS3 so learning one language is enough so that particularly C++ is very much advantageous for that。

So in this session I'm going to just talk about NS3 and it's a basic installation。Thank you。

So this is about introduction to industry architecture and I am Praip Kumar。

So here is my URL where I just post lectures about the network simulator3 and here is my Twitter handle and this is my email I the us at Gmail。

com。So in the NSS3 introduction。The NSS3 is a simulator is a discrete even network simulator targeted primarily for research and educational use so similarly NSS2 NSS3 also has a discrete event simulator it targets towards the research and the education rules so the main advantage of NS3 is this open source as well as three so you can able to download it freely you when deploy any number of machines so you need not pay a single penny for it。

NS3 is not backward compatible lessons of NSS2 as I already pointed out in the beginning。

 NSS2 and NS3 are both are different， so NSS3 is so powerful when compared with NSS2。

So it is a new simulator so some model from NSS2 have been already been imported from NS2 to NSS3。

 so when NSS3 was developed so they have taken the help from the NSS2 team and they have imported so many modules from NSS2 and they have just redesigned everything for NSS3。

Also NS3 is designed as a set of libraries that can be combined together and also with other externals after libraries so when you are learning NSS2 you are other than NSS2 you can able to learn two or three third parties afterwards for any graphical and other simulation purposes but for NS3 you have to learn so many things so shortly we will be seeing all those tools what are we need for learning NS3。

So several external animators and data analysis and visualization tools can be used with NS3。

 so that's what the any the external third party libraries third party tools can be extensively used along with NS3。

So NS3 is primarily used on Linux systems， although support exists for a free BSD Swin a native Windows visual Studio support is in the process of being developed。

 so that means NS3 supported in3BSD Linux as well as Mac O but Windows the native Windows visual Studio support they are still being developed and very soon they media may be launching for Windows also。

So NS3 is not an officially supported software product of any company。

 so no company held responsible for their NS development。

 It is a full to the open source software developed by year。Now free community。

So now NSs2 versus NSS3 so I hope most of you here you would know about NSS2 or not。

 I don't know but there was a tool available for the past 15 years and still people are doing in something an NSS2 and now NSs3 is picking of the market so there is a difference between both of this so NSS2 uses whatTclL and C++ so whatTCL means object oriented tool command language and C++ is a general C++ what we learned using the object orientation。

But NSS3 only C++ with optional Python bes， so if any user wanted to use Python as one of the preferable language。

 they can use the optional Python betics else only C++ is enough enough for running any applications。

So NSS2 have its own animator called the network animator that is called us NAM whereas NS3 have new animators and visual lasers available under current development so for example we can see Y shark we can see net animator in net an and we can see visual laser。

And trace metrics， so there are so many software that is available for NS3。

So Gen is its own trace file which can analyze with the limited number of external tools。

 so there are some tools like trace graph x graph， there are some tools available。

So Ns2 generates its own trace file and that can be analyzed using this graph and trace graph。

Whereas in industry， a P cap trace packet capture trace file。

 so it is a very industry standard packet capture trace filess。

 so that can be rent by so many tools like WeshR the PCB T。

 There are so many isolation tools available be。😊，So NSE is so advantages it uses the generic tools and techniques for development。

NS3 is actively maintained with an active responsive user made English。

 while NS2 is only lightly maintained and has not been significant development in its main code。😊。

For over a decade， so over a decade， which almost for the past 10 years。

 there was no appd or no new set of tools have come in N2 whereas as N3 every three months once they are releasing a patch。

So industry provides featuress not available in NS S2。

 such as implementation code execution environment。

Actually NS3 have a good advantage colors direct code exhibition B。

 they call Bc direct code exhibition， so what this direct code exhibition will do is。

This direct code exhibition suppose I have a router I have a real hardware router available so I want to configure the router using NSS3 code so assuming here develop code for NS3 and you want to deploy the same code into the direct hardware and then hardware will work as where the logic what you return in NS3 so such kind of facility is not there in NSS2 but NS3 has there。

But there are some limitations found in NSS2 such as supporting multiple types of interfaces and nodes correctly have been remedied in NS3 NSS2 have so many disadvantages。

 but all these disadvantages have been converted as an advantage in NSS3。

So now this will be the five things you have to know so in person we will discuss about these things like node application channel naivs and topology helpers so you need to understand all these five abstractions available in NS3 node application channel nas and topology helpers so we see in person what each and everything caters to so in the meantime we will just go through some the installation procedures of NS3。

So in the installation so actually in this lab in this lab I think you will be having Ubu212。

04 which is a longter support so LTS wins it a long term support so that means the operating will be supported for the next five years so 12。

04 wins it was launched there 2012 and it will be supported till 2017 so next year by this time the support for this operator would have been strapped so now the current version this 14。

04 that is launched in 2014 so the support will be available till 2019 so if at all if you' are planning to install NS3 on a machine so you just prefer 14。

04 but within a week or so 16。04 will be launched I mean might be in the last week of April that 16。

04 will be launched by Ubu2。So I have used Ubu2 as well as next min for Lgi session。

 I think in this laboratory also we can able do do。

So whenever you start any new tool for excling so you first update the existing libraries so the command will be pseudo app hyphen gett update so that means so open a terminal so in the terminal you just type a pseudo app hyphen gett update。

So once you do this so there will be whatever the packages were missing in these two years or three years。

 so everything will be updated but dont worry it will not take much space as you like as you feel it will take some limited amount of space and it it updates the entire package manager。

After that you start the installation so I just tell you each and every tool so buildEssentials is one of the thing which shows you about the developmental libraries for any Linux machine like CC plus plus Python TclLTK everything comes along with this build essential。

So whenever you are installing any developmental tools in an operating system like Google do。

 you refer this build essential tool。Next thing is auto configuration。

 so we would like to have some configuration management so further that I want to have automatic configuration so you can use auto con。

Then you can use autom。And live XMu iPhone DV So this software is mainly for XM U win it is a X libraries software that means you want to have a GY window so for this we can have this software IEA 32 libraries so this package will not work under Ubudo because this is for the 32 bit libraries because so many softwares we might be using which would have been developed the five6 back so for those softwares those who would have been returned 32 bit libraries but nowadays we are all these things we have 64 bit libraries So if at all if any software needs 32 bit libraries。

 then we have to go for 32 bit libraries that's why so IEA means Intel architecture 32 bit libraries So this package will work only on the next winter So if at all if you are installing now so you please remove this package alone。

Then net an， so please see that the M is capital letter and the A is capital letter so you have to prefer the same so network animator。

😊，Next thing is wire sha so wiresha is a packet capture analyzer。

 so it is a industry standard tool so that is very powerful and and free really available so this will be instant so these things we can able to see during in person session。

Then Python， hyphen， Pgo canvas。 So you have to have a hyphen also here， Python and Pgo Can。

 So these things are for。The GY in Python because so many NSs2 S NSs3 is after the backends are supported by Python libraries also。

 so if you want to see some kind of visualization so we have to go for this graphical interfaces so further we have Pu canvas and P graph visualizer。

And we have a we should have a Python development also， then 2 T4 development。

 so this 2 T4 development for the network animator。

This network animator we have to have this and p7 zip full。

 so this will be for the zipping and unziping compress anti compression。

 then B that is the buzzar software then C make。Meercurial。G I T CS Python Kiv。

 Python genome 2 Python genome 2 hyphen desktopta and Python RSBg so every there is a blank space in between each and every packet so all these packages are mandatory for installing NS3 so you please see that see to it so you can enter。

Software has to be installed。So next thing is so as per my discussion I am just using 3。24。

1 this is the version I am using so the same version I can you can also follow but the current version is 3。

25 so have these have been launched possibly around three months back so now they have launched a 3。

25。So， but we will be using this three point to four point that one。

So what you can do is download this folder， so download this file and save it in a folder。

Preferably slash slash but it make case so you can able to you can copy this file in slash form slash user maybe some user name might be there in a machine name so you can copy this and issue this commander so either you can use the Gi you can right click or file and click extractor there could be one easier method in Gi but if you want to do a terminal mode you can use T Jx vf and thats all in one iPhone 3。

24。1 Vi2。tThen this will extract the entire thing and create a folder like this and go inside this folder c N alignment hyphen 3。

24。1 so once you are in this folder。Now we are going to build NS3 so we cannot say compile NS3 so we can able to tell build NS3 so that means all the motives of the NS3 can be built using this commander。

 so the command is dot slash。Buildedar pipe， hyphen， hyphen， enable hyphen examples， space， hyphen。

 hyphen， enable hyphen test。So this command will enable all the examples available in the NS3 build as well as it enable all the test that is available in NS3 bundle。

So there are so many build procedures available by debugging configuring there are so many things available but for the most of these cases this will be the optimal one enable all the examples and enable all the tests so we are going to see the next two we are going to see these examples available in NS3 so because if if you are starting learning any tool any tool or any programming language the first thing we is there could be any examples so that I can practice so NS2 and NSA there are specialized tool they are having their own set of libraries so before we start exploring the libraries given by these tools so we have to see how the programming has been already written by the developers so that tools will that examples will be enabled using this commander。

So when once you press enter after this typing design line， so it will take。

Let's say 5 to 10 minutes or sometimes it takes 20 minutes also to get the complete packages installed so at the end of this session I mean at the end of this installation it will show you what other the models have been built each other the models have not been built so hardly you can see there are four models that could that could not be built who might be because of some reasons but there are so many other models would have been completely built。

Then what you can do is to run a simple example so you can go inside this folder now so n' hyp 3。2 4。

1 and there is a command so this is a web application file so that is what we call wF so dot slash wF hyphen hyphen run。

Hello hyphen simulator so sorry it is not web application。

 so I will tell you what is this graphboard dot s wf hyphenhen run hello simulator so this will print hello simulator in the M so this is the way we can able to run all the c plus plus files so even if you have a dotcc file so you cannot mention dotcc here。

Dot slash wave hyphen hyp run hello hyphen simulator so like this we can able to see so many examples that are available in the N3 software。

Suppose if you want to run examples in the industry。

So there could be there are so many example so for each and every model so one example is so if you want to do a work on Zigp protocol。

 if you want to do a work on Wifi， if you want to do a work on propagation model。

 if you want to do a work on satellites and if you want to do a work on NPLS networks if you want to do on peer to peer networks。

 TP， UDP。And ACDP， so what kind of networks you can take for each and every network they have given the source file as well as they have given some examples。

So， a user need not worry about an example how to write an example or how to write a particular necessary file we they need not worry about only thing they have to worry about is they know the C++ or not so when you read the code you should understand what is this code all about。

So that is what the prime importance of being an industry developer。

So in there are so many examples for until this I have seen0500 of examples in NSD。

 so if you want to run these examples， so all these examples have to be put inside this folder called this scratch。

So inside NSS iPhone 3。24。1 last scratch so all these example have to be put in there inside this folder scratch so for this folder scratch NSs3 given a special meaning then so every file can be put here only then it will be executed or it will be compiled。

So you need to copy the dot CC or dot P files from the example folders to this scratch folder so you can put everything inside the scratch folder。

So， once copied you can run the exam using so you can just give this command and then dot slash w hyphen hyphen run scratch slash file because this is a scratch folder and this is the name of the file so actual the name of the file is file docc but for running C+ plus file you need not give dotcc extension so you can simply stop it at。

肥。If you you suppose if the name of the file is P2 p docc， then I can use P2 P here。

 similar if you want to run Python file， then you have to go Py here so but in this case hyphen hyphen py run so pi Py or even scratch or file Py。

So this way， you can able to run the examples given in the NS3 folder itself。Okay。

 so as as per time being I am just saying here thank you so sorry that the flight get delayed because we have no other option other than book of flight。

Elier are the the previous day， so all the flights were running for five hours or six hours so this is the only optimal flight。

So any help thanks for listening to this video lecture。

 So remaining things I will just discuss you with。In person， Thank you。



![](img/940df16f7acfbadc396567b6fb70622d_2.png)