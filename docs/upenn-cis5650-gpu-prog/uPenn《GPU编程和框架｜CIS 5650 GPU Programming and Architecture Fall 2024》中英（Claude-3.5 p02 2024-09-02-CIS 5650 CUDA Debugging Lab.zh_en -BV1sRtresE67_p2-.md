# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p02 2024-09-02-CIS 5650 CUDA Debugging Lab.zh_en -BV1sRtresE67_p2-

Welcome， if we went to this recorded session of the 565 coa debarking lab。

 we'll start with a few slides to give you an overall view of what Qa debarking looks like and then we'll dive deep into showing what the visual studio insight can actually do。

So on today's list is talking a little bit about debugging tools on a very high level overview。

 part about the visual Studio debugger a little bit to show you how the CPU side of debuing works and the insight debugger to show you what the Q side of debuing looks like and how how to manage millions of threads running at the same time。

So with these tools you can do， you can figure out things like incorrect launch configuration。

 your thread increasess， block ins， you can figure out synchronization problems or atomics and find where your problem lies and correct that。

So in practice， most of us probably follow this order of debugging as soon as something's not working you probably add a C out or a printf and figure out what the values are where and this works。

 but it doesn't scale for that having a proper debugger like the visual through your debugger is much better because you get to walk through it in practice。

 I always recommend that if you're writing any kind of algorithm。

 it is always good to walk through the debugger to ensure that your algorithm is working as expected。

 even if the output is you think is correct， make sure that you're walking through the debugger and evaluating each step。

However， when it comes to GPU programming， we should studio your debugger doesn't cut it。

 although it can do multistared programming on the CPU side。

 it can do it can debug the kuda side of things because it needs access to those resources。

 That's where endsight comes in， which allows you to debug the kuda side of programming along with profiling and other graphics tools。

So other debugging tools that exist on the whole side are the visual through your debuer。

 as we spoke about， GDP on Linux。On the device side we have the InSight Pre Studio Ed。

 Insight Aclipse Ed， and HuA GDP， which is essentially GDP， but for Hua programming。

So this is something we'll discuss in class about which which debuing tools do we know and commonly use print F out Sstream。

 these are all programmable tools， so essentially you' are putting these in your code to get some sort of an output breakpoints。

 conditional breakpoints allow you to step through your code call stack shows you the function stack that you're using currently and autos local watches are windows visual studio based windows that you can see what the variables are。

So on the Qa side， you can debug using Insight or Ka GDP to profile we have the N visual profile or NVVP for short with Insight modern tools now include Ins compute and inside systems to help you do deeper profiling and the QD SDQ also provides an Excel spreadsheet called the QUDa occupancy calculator where you can plug in things like how much memory you're using。

 how many registers you're using to figure out what the optimized occupancy calculators to get the launch configuration that would work best for your kernels。

So， just。Going through a high level overview of Ka GDP， which is on Linux。

 because we won't dive deep into it in this recorded session。

 Ka GDP is an extension of standard GDP on Linux， which is a command line de parkinging tool。

It allows you to debug code on actual GPU。 So you're getting the value use right off the GPU itself。

 and it can debug both the CPU and GPU code。 So you don't have to switch between GDP and Ka GDP when you're trying to debug。

Set setting the compile flags is easy。 You add the small G and the capital G flags to generate S debug info for both the CPU and GPU side。

And all the usage for Ker GDP is very similar to GDP itself in the sense of breakpoint shortcuts。

 walking through lines and jumping around。 So if you're used to GDP， Ker GDP could be a great tool。

I would always recommend using inside for kuda debugging， even on Linux。

 But if you awarded try out Quda GDP， then there are plenty of resources online。

 or you could send me an email。A few terms that you should know before we dive into insightsight are software coordinates and hardware coordinates thread blocks and kernels。

 you know already we've gone through this in class on the hardware coordinates when you're debuing code。

 you're going to see these be used a lot more where a lane is。A lane where a thread is executed。

 So you're always gonna have a one to one match between lane and thread。

 Warp is a set of 32 threads that execute together， and many wars make up a block。

SM is one streaming multi process on a GPU， depending on what your GPus。

 you may have anywhere from 2 to 16 or more Ss on a device。 and of course， device is the GPU itself。

On a high level Insight can do help with both debugging and profiling tools， it has a GPU debuer。

 a graphics inspector and system profiler and new tools also include Ins systems and Ins Ins Comp so feel free to try these out I have linked to the user guides for both the Vi Studio and the Eclipse Ed for you to try。

So how do you set debug in for before you can actually use the inside debuggs for all the class projects we do this in Cic by adding the flags。

 otherwise if you're using your own projects， then these are some of the steps that you need to follow to enable the debug in for。

And follow these steps as well， where you're generating the debug info for both the host and GPU side and make sure to set the correct compute capability。

 because if you don't do this， you're not going to get the correct hardware codes back and you'll see bad information。

So with that， let's dive into Incite itself and walk through what information it can give us。

So let's look at insight and what it can show us。 First。

 I have insight installed in my virtual studio 2017 edition。

 So I'm going to go in and go into Windows first and see system info。

 So let's walk through that first。When you open this。

 it's going to show you all the hardware information， so we start with the system tab on the left。

This is going to show you what hardware information is there for your laptop at desktop so you can see the number of cords on your CPU。

 the total physical memory install， so I have 32 G。

 it shows you hybrid graphics if that's available your Windows version and the inside versions。

The display devices tab shows you all the GPUs that are available。

 so in this case it showing me the Intel UHD graphics that I have built into my Intel CPU。

And then if you go into NVIDdia GPU devices， this is going to show you information about your specific GPU so I have a force GtX 1650 installed the driver I have installed as 452 which I believe is the latest driver model there are two driver models that NVDdia follows WDtM which stands for Windows display driver model and if you're using an NviIDdia GPU for display that's the model it's going have and the other one is TCC which stands for Tesla compute cluster So if you have GPUs that don't have displays or are using a remote GPU sometimes these GPUus can go into the TCC mode。

 which means they don't run graphics applications but can do computebased Quda applications。

The Kuda device index starts from zero and implementcrements for each individual Ka GPU you have。

 I have only one GPU so that's going to remain zero。

The GPU family gives you information about the GPUs architecture。

 so my 1650 GPU is a touring class architecture so and the architecture specific architecture in touring is 117 A。

 so if you have a pastal GPU is going to start with a P Kepler GPU is going to start with a K。

 Maxwell GPUs will have Maxwell architecture code。This compute capability is important to note。

 It defines the architecture once again， but in a way that the system can read。

 you can find this on the Web as well。 what your compute capability is。 So Kepler was 3 point x。

 Maxwell was 5 point x and the parcal was 6 point x。

And tutoring is 7 point x and the new MPpi GPUs RTX 3080， 3090 are going to be 8 point x。

So number of SMs is the streaming multiprocesss。 So these are individual units of many ka cores that form a multiprocessor。

 So knowing this number is also important。 So I have 16 on mine。 I have 4Gb of GPU Ram。

This is my frame for bandwidth which is essentially the maximum copy speed if you were to copy memory from the device to the device without actually going to PCIE so if you were just copying two arrays or one array to the GPU again。

 this is the maximum speed of copyer that you're going to see and we revisit this in the performance lab。

These three numbers are your speeds， talk speeds that you can get these essentially go into how many teleflps you can expect。

 so when you're doing something that matrix multiply you would use these to calculate what the theoretical maximum of your GPU is。

And the right type， of course， is GDDR 5。 You may see GDDR 3， GDR 5 x， GDDR 6 x for new GPU。

 So if you do it doesn't really matter in code， it just defines how fast your memory can be。

So moving on， this is a key tab for you to know。 this is this shows you the ka information for your GPU。

 So we're going to go through a few of these， not all of these。

 And so let's start with the top and we'll go an alphabetical order。

So as engine count it defines how many asynchronous operations you have most of the start of the semester。

 we're going to do synchronous operations， but once you get to advanced Kuda where you can do compute and copy at the same time。

 this defines how many of those operations can be happening simultaneously。

The clock rate is the same as the GPU device clock rate of 1560 megahertz maps to this number here。

 compute capability major and minor are there so that you can use this programmatically this again maps back to the compute capability number here。

Compute mode is zero for WTDM models and one for Tcc models。Concurent kernels again。

 goes back into the async engine about how many simultaneous kernels you have running。

 so in this case， my GPU has one。This is the GPU name。

 So if you were to query the coda properties for the GPU name， you would get this back。

The global memory bus bandwidth again， if you want to use it programmatically for advanced programming and to figure out how much time you would need to copy something。

 then this is something you would use。These。Now， these numbers are important note as well。

 These define the maximum block and thread size in any one dimension。 Not that these don't define。

The total number of blocks or threads you can have， but defines what the max is per block。

 So if you look at the block numbers， you can have 1024 in x 10 to 24 and y and 64 degrees Z。

 That doesn't mean you can have。64 million threads in a block。

 What it means is you can have a configuration that is 1024，1，1 or 1，1024，1， or if you have 1，1，64。

 then you only have 64 thirds in a block。 These are the maximum per dimension。

 The maximum per block remains 1024。And similarly with this。

 the number of blocks in a grid are defined。 the maximum number of blocks in a grid are defined in the dimension。

 It's a large enough number that you never have to worry about it。

Coming to some of the memory resources here these essentially define how many registers and shared memory you can have per block and per multiprocessor。

 so multiprocessor is the hardware SM and we'll talk about this more once we get into the advanced programming about how QUDa kernels map onto multiprocessors but for now keep an eye on this block which essentially defines how many registers you can use in a kernel per block and in this case for me it's 64 kilobytes。

And if you exceed this， then Kda is going to have to reduce the amount number of。

Active blocks that are executing in order to manage the resources。

We haven't spoken about sharedd memory yet， but once we get to it。

t have this number in mind and we'll talk more about it then。

The the other thing that we spoke about before was the number of threats per block。

 so in my case it's 201024 and for most， if not all the GPUs it's 1024 the number of threats per multi processorces which is again the hardware concept is also 1024 for me so once we get into advance Ka where we are determining how many resources we have this number would play there as well。

Again， multi processces account， another programmatic way to access this。嗯。

This number is useful to know to， especially if you' are doing double precision programming。

 what this tells you is the the speed slowdown。For doing floating single floating point versus double floating point precision computation。

 So 32 means the a double precision computation is 32 times slower than a single precision computation。

 and compute stands for a multiplication or addition。So if you， if you by mistake。

 use doubles instead of floats， you're going to see the slowdown happen very rapidly。Finally。

 what size， this is going to be 32。 it's been 32 for the longest time。

 and I don't believe Enia has any intention of change again。

Now you can find openCL information here too， it's generally going to map straight to the Qa information you have。

 it's just different definitions on how you access this programmatically。

And you're also going to see the intel graphics chart show up here because OpenCL is platform agnostic。

So one thing I want to show you before diving back into insights is the kuda samples。

 and these are generally available at sea program data in video corporations。

 kuda samples and the version number of your kuda SDK。 Now， obviously。

 if you have these on a remote machine where you don't have access to the admin panel。

 It would be best if you go a step up， copy these and paste it to your local directory。

 I don't have to do that because I'm using this on my own laptop。

 So what I'm going to do here is open utilities and open up device query and open my visual studio version of the solution。

So in the scooter device query project， what it shows you is how to query device information programmatically。

 So we saw how inside chose the information as the table。

 but you can query this information directly through the APIs as well。

 So you can make runtime decisions based on what GPU this is running on。

 So you don't always have to know with GPU it's on beforehand。 you can do this programmatically。

 The important。Structure here is called Kuda device Pro。

 and you can find complete information about this structure on the Q SD get documentation。

 And the way to populate this kuda device drop is to use this kuda get device function pass this as input and pass the device I So this program is itrating over all the kuda device available。

 on my laptop is just going be one。 But if you have a multi GPU system。

 then it's going to ittrate a all of those。 and once this device drop is populated。

 it's going have a bunch of properties that we can look at name， of course。

 and you can get the runtime versions you can get the number of G of Ram the number of core and multiprocesors you can get clock rate。

 cash and other information that's all here。 So let's go ahead and run it。And as you can see。

 this is all CPUU side code。 There's no GPU code running here。



![](img/e9b4133f917741e64e39c7849cde36c8_1.png)

So looking at the output， you can see that this is， of course， formatted using the prints。

 but this gets you pretty much all the information that you had through the table。

 but now it's done programmatically。 So if you， let's say wanted to understand the amount of global memory available before you ran assist ran your kernels you can do this programmatically and then not just how many kernels or threads you're launching similarly for the number of multiprocessors for me it's 64 and 64 co course per multiprocesor。

 but this can be different on different GPUs， So this is a great thing to do when you're optimizing your k kernels and ka programs。



![](img/e9b4133f917741e64e39c7849cde36c8_3.png)

So here I've opened up the coa documentation。 So this is both the API documentation and performance and optimization guides。

 It has the runtime API driver API math API， which are the math functions and gives you the API for all the libraries。

 So some of you may have used Gola or Co FFT and others。 So this gives you all the API for that。

 it gives you samples， demos， and how to optimize your program for each architecture。

 So if you're targeting a specific architecture for your program。

 it gives you the guides on what settings you should use and how you should tune them also has the guides for compilers inside inside compute and others。

 So this you can't spend enough time on this。 there's so much to learn here。

 So please use this as much as possible。For this specific debugging recording。

 I've opened up the QUDa device Pro that we were just talking about。

 so exploring this page will give you all the information about each of those properties that are in the structureut so you can use them programmatically。

And finally， coming to the Insight visual Studio Ed， this is the documentation for that。

 everything from installation to compiling， running， debugging， profiling， inspecting the states。

 inspecting memory all of that you can find on this page。

 I'm also using this page as a guide to doing this recording itself。

So if project one could avoids open here。 we are going to be using this for showing how insight and we should studio your debuggle works。

 make sure you're on the debug configuration here so that all the debug symbols are compile into the cord。

 if you're in one of the release ones， then the symbols are not going to be loaded and either you won't hit the big points or you'll see garbage information。

As you can see I've set a breakpoint here which is on the host side。

 the great thing about the next gen debuger is that it can do both host antiwise side debugging so we can get started with that I've precomped the code to save time and I'm going to get started with the Qa debugging side of things。

So we've hit the Bitcoin here as you can see and before we start walking through the code。

 I want to show you a few windows so if you go to debug windows。

 some of the best windows here are watch and you can have multiple watch windows， autos。

 locals and call stack。So before we before we walk through let's walk through these windows itself。

 So call stack shows you the depth of the function called youre making。

 so right now we had main which called in it So we are seeing that here in the call stack so as you call more and more functions this will get populated。

The auto function autos window shows all the variables that are currently in scope。

 there is a select set of variables that are picked by Viual Studio based on the line you're currently at and giving you the variables that are probably most pertinent to debugging you can't add more variables here but it's a quick way to get started with what visualual Studio pretty well picks the relevant variables。

And then if you go into locals， these are all the variables that are in scope within the function。

 So for example， if you had， let's say a for loop or if statement and you were defining variables within those blocks。

 then those variables will be shown in locals when you are in those blocks。

 but rather and will get removed when you step out of those you can see all of them again。

 you can't add any more here because visual Studios picking all of those for you。

 and these are going be the top level。 So if you have any arrays。

 youll have to do you'll have to expand these to know more about them。

The watch windows are where you can add more variables。 So I'll get to this in a second。 So let's。

 let's walk through this and I'm going to step through and I'm going to go to the locals window just to keep an eye。

And as you see here， if something changes to red， that means the previous line has just changed that value。

 So we set GPU device to 0。 And in the current line， we're gonna set device current to 0。

 So I'm gonna highlight this line here。 and you can see it's some garbage value。 And now。

 as I step through it， it's changed to 0。 And you can see that it's red because it's just updated。

Let's keep stepping through。 And now that we are at Ka device drop and could the device prop variable is gonna get populated。

 I'm gonna highlight that and expand it just to make sure that we are seeing the right information。

 And as I step through it， you're gonna see that the entirestruct has been updated。

There might be some variables here that won't get updated， for example。

 Max T dis is probably the same by default and same for the GPU。

 so that's going to remain same And thus you're not seeing that change to red。So I'm going to。

Keep going on。And。I'm going to come here。Because there's a nice trick I want to show you。

 So if we go into。Name into the watch window。 And let's step through one more line。

 So now we can see that device name has been populated。So I can type device name here。

And this shows you the entire string。 and you can see that the type here is highlighted as an STD string。

What you can also do is。Do something like。0 there。 So now you're only getting the first characters。

 So now you can see that the type is cat。呃。And I'm although I'm showing this with a string。

 which is essentially a character array with other functions around it。

 This works with other types of arrays， too。 So if you had like a vector of floats or a regular integer array。

 these， these strings would work there as well， so。What I can do is I can say device name comma 10。

 So what this is doing is asking for the start of the device name and 10 elements after it。

 So when I hit enter， you can see that this goes to 5，6，5 space Kuda。

 which is one of the four space I。 So that's 10 characters。

So you can do this with floatatingning teacher raised to。

So the other thing you can do is if I were to con get the C string behind this。

 which is the regular cab string and do the comm 10， It will still work。

 So now you can see that this is cons card 10 as sub type。And then if I do， let's say。Plus 5。

 this is adding an offset to the start of the string。 So instead of seeing 5，6，5 cota I。

 you're gonna see the first five characters disappear。 So until C will be offset。 So we'll start。

 we'll see that the new watch variable starts from U。 So I'm gonna hit enter。

 And now you see that it's UD space intro which with the colon， which is again，10 characters。

 So this works with other types as well。 So although I'm sure you just。

 it will work with other array types as well。Alright， so which with that watch shown。

 I'm gonna go into the kernel side of things。 and I've placedd a breakpoint here。

And the reason it gives me this error is because the execution is currently on the host side。

 So you can see that up here in the thread。 it says main thread。

 And that's why this is showing that this big point would be hit。 But we know that it's in a kernel。

 and it's going to run。 So I'm just gonna hit continue。 And we'll see that this。

This break point would be it。 There you go。 Allright， so let's jump back into our autos。

So the great thing about insightsight is that it uses all of these same windows as visual Studio does。

 so we are seeing that all of these autos， locals and watch are still populated。

 of course watch is going to be used as now because that was populated with the all variables so I'm going to delete that。

 but now if you come back to autos you're going to see the block IDX block name and T IDX for the active thread now remember that when you're in a kernel there are there is a war running so a warp is 32 threads but each of these breakpoint is at a specific thread so we are seeing that the current active thread is 0。

00 of block 0，00。So that's important to remember， make sure that when you're debugging。

 you are on the right thread that you want to be。So let's see just like the debug had Windows inside has a few windows。

 too。 So let's jump into that。 We've already seen system info。 I'm going to open war in for now。

So like I said before， a war is a set of 32 sets that execute together on the GPU this。

This tab is going to show you all the wars that would be launched for the current kernel and you can add a filter here that you can type out we are not going get into that right this moment。

 the important things here are the shader info which shows you the block and the thread I block ID X for the entire warp。

 a warp cannot be split across multiple blocks。 Each warp is within the same block。

And the thread IDX of the first thread in that warp。

 so you're not going to see the offset you're going to see between each warp are 32 because the warp size is 32 and youll see that these are four groups of eight just for visual representation but in total 32 sets。

So CPA is the blockite index and thread it shows you the thread index of the first thread in that warp。

So the the other thing you can do here is if you wanted。

 you could double click each of these boxes and you can go to that thread if you want。

 we can we can do that later。The other windows here are what watch。

Which is the same as the the regular watch， except that you can add codea variables on it。

 and you'll see that each of these has 32 rows in it。 So you're going to show the entire w。

 So if I pop this out。And。Populate this。 And let's go back to the kernel。 so I can add a variable。

 like index。And maybe step down so that it gets assigned。

 So now that you you can see that we are in a right the standard index equation。

 So each of these values is unique and populated now。So that's what watch。

 Let's see what the windows are there。 Let's go into lanes and let me bring that there。

So like I said before， lanes is a representation of the threads in hardware so you're going to see each one of them has thread index and this is going to show you what state they are in so in Quda you can have branching war so this is a great way to know which threads are active which thread has the break point which threads are inactive。

So that's lane。 Let's go into resources。And this has a few tabs in it。

 So I'm going to put that there。And I'm gonna put this here， too。So in in resources。

 we have a few drop downs here and I'll walk to some of them Dev is going to show you the same information about the device it's executing on so just like we saw in inside Windows system info that you're going to get to see here as well。

嗯。Context， you can have multiple kuda contexts for multiple threads。

 So that's going to show you in most cases， you're just going to have one context。Again， streams。

 you can have multiple streams going on for increased efficiency and optimization。

 we'll get into this later in the class。Funs show you all the device functions these include both Kuda and sorry global kernels and functions so you can see the name here the demand name which is the full definition of it mangled is the name in the object code and you can see the number of threads per block amount of registers they're using the number of bytes so we' are not using too many of these but as we advance our understanding of Kuda you'll start seeing these be populated to so I'm just going to find one that we were currently using which is。

Keep going generate random position array。So let's go into resources。

 I'm going to sort by name name for that。So that it's easier to find。嗯，Yeah。

Con generator random position。 So here we can see that once I go back， you have an index defined。

 You have 1，2，3。3 variables coming in as function arguments。 So that's 24 by。

 And then you have a vector pointer as well， which is gonna be additional byte。

 And then we have an another 4 by for the index and another vector3 being defined in local。

 So if we go back to resources。 This is telling us that each thread is going to use 29 registers and 184 B of local memory。

So that's a great way to find out what your resource requirements are for each kernel as you write them。

So I'm gonna to skip graphs right now because that's when you use graph functionality for like machine learning。

 So that's not necessarilyly important for debuing right now。So let's see what other windows we have。

 And finally， we have GPU registers， of course， which give you all the register information this。

 this may be hard to read right now because it's all in hexa decimal and registers。

 but once you get used to advanced quoa programming， you'll be able to decipher this pretty easily。

Alright， so I'm gonna to close most of these。 So I'm gonna to close GP P registers， lanes， resources。

 I'm gonna keep what in for around and what， what watch around。 And I'm going split the window。

So that we can see both sides。So I've already added index to the word watch。 just for showing you。

 I'm gonna also add time and and scale because these are input static variables。

 So these are gonna to be same for all the way， all the threads。

 So I'm adding time there and and scale。 And you can see that these are all gonna be the same。

 So I'm gonna again， back delete these because they're not necessarily important。

I'm going to add and block IDX and T IDX。Now， although these are three component structuress。

The watch window is gonna be showing them pretty easily。 So you don't have to do block I D X text。

 although you can do them if you want。 So I can show you said。Id X star X。

 And that's going to be unique。You don't have to。 You can do them as three component strips。So。

 let's step down。And now we can see that we are about to generate a random number using this function。

 So if we pick definition here， we see that this is a host device function means it's going to run it can run both on the host side or the device side and it's going to generate a random three random components and return a vector3 for that。

So I'm going to close that， and。Let's， I'm gonna a you。Now remember that this is a GLM V3。

 which is coming from the GLM library， so this may not show up directly。So as we see。

 this is a local key vector here， but the debug is not able to see the right values。

 so how do we how do we get to see this？What we can do is。Open a double bracket。

 do underscore Ss go local and we are doing local because Rand is local to the kernel here。

 it's not coming in as global memory or it's not sharedd memory。 it's local。 So I'm going to do that。

 I'm going to do flow star to typecast it。 and I'm going to put an am in to get the pointer to it。

And I'm going to close that bracket as well。 So once I hit enter。

Now you're seeing that this is a memory address now。And I I add zero off index。

This should convert to values。 There we go。 So now all the values are populated for all the texts here。

I'm curious why these are zeros， but I assume that the GPU hasn't sent that information back。

So we can do the same for。嗯。Oh， you know what， these are zero because。Not all。嗯。

Registers may or not all threads are using the same point or probably。 That's why。

 So it's using the address for ran from thread 0， but not populating it correctly for the other threads。

The other way to do this is if you want to copy this and put it into our watch window。

 that works as well。 So here we can。I'm going to copy that again。So this is what I made a mistake。

 I did of index， where I should have actually done 0， because the R is X， Y， Z。 So it。

 we can also use 0，1，2。 And that's why it's probably running into garbage。 So now， if I do 0。

 then all of these pop values are populated correctly。 So we can do the same thing for。1。And。2。

So let's squeeze that back in。So that's how you would read GLLbacteries。So now let's step down。

So that values are getting assigned to AR， which is the global array。So if I type a error of index。

The thing is AR of index is also a GLM V 3。 So we are going to run into that same issue。However。

 we can't use this local descriptor with AR because it's not a local variable。

 It's a global variable that's coming in through the function pointer。

So to visualize this ARR global memory， what you're going to do is going to debug windows and you're going to see this memory。

 and you can open one of these watch memory windows。

And then what you have to do is in this address address field， get the address for ARR。

 So if we highlight it， you can see it or you can copy it from this box here。

 So I only copyied the hexad decimal part。And。Let' put at that。

So normally normally this is set to1 byte integers。

 I was testing it so I'd switched to 32 bit floating point。

 we know that GLM V3s are 32 bit floating points， so we're going to set it to that。

And because we initialized this on the host side to be all zeros。 this global memory is all zero。

 So now if we step into the next line， you're gonna see the values update。

Now you can see this that some values update， but it doesn't seem to be in any irreg pattern。

 Can any of you think why。I'll give you three seconds to pause this video， 3，2，1。

So remember that we are not， you know， we are， we only assign the X components。

 and these G vectorctories are three component structuress， right， So you're gonna get X， Y， Z， X， Y。

 Z， X， Y， Z。So if you see the first value got updated， but  two zeros， then one value， then 2，0。

 So 1，2。 So what we can do is because we know this is a V 3。

 we can change the number of columns to 3。 So this fills to 32。 I'm going to backspace as and hit 3。

 Now you can see that all the first column values have been updated and。

Only 32 of them because we are running a war， so 32 threads have executed and updated the values。

Let's do another line。So now you can see that all the y values updated。And let's do。

 if we do another line， then it may exit the kernel because we are done。 And the。

 the the execution on the kernel will end。 So we may step out of this。 So for you。

 of warning before we do that。 So I'm gonna do next step。Okay， so we've updated and it has it exited。

 so that's great。 So you can see that the red bodies have changed。

So that's one way to visualize global memory using this kind of memory watch。So let's。

 and I'm gonna in that here so that we don't lose it。So once we have that， let's， I'm going to stop。

This， and the other way to visualize global data is。To use a。Flot 3， So float 3。

 or I'm gonna type this second。 So if I type 1， you can see that there are multiply float 1， flow 2。

 float 3， float 4， These are intrinsic variables in Kuda。 So the debugger and Quda understand them。

 So we can do flow 3 temp value。Equals another built function in Kuda is make floor 3， because we。

 and then we give it A R R of index。Dot x。Plus， or not plus E our index。Dark， why。

Here at our index3 C。So if you do this， float3 values will inherently be visible in the word watch and in auto。

 so you can use that those as well。 So that's another way to visualize data without having to go into the memory window。

 which which could be confusing or may have way too much data to look at。

So the other thing I want to show you is about branch。 So since it may changes this。

 I'm going to first go ahead and compile this。So。Our size for generating these random numbers is 5000。

 So n is 5000。 But if we look at our block size and block threads。

 we are launching 40 blocks of 128 threads each， which results in 51，20 threads in total。

 So that means we are launching more threads than we have elements。So some elements are。

 some threads are gonna meet this condition and exit。So that's called branching or early exiting。

 So I'm gonna put condition here。And add the expression index。Equals 4，9，9，9。

 because 5000 would be exceeding this condition， and 4，9，9，9 would be within it。 So save that and。

Let's start deeppoing this。As we look into。The kernel。 and we hit the breakpoint。

 And you can see that this yellow arrow is marking where index is 4，9，9。 And look at this。

 All of these are carried out， even though the index is populated correctly。

 all of these threads are cr out。 So let's look at lanes。And this is interesting， too。

 so all of these threads are marked as inactive。And if you look at warp pinfall。

 the other thing to note here is that all the other warps that were before this have completed their tasks and exited。

 So we see a few green here which are active and the grays here are essentially inactive。

So what do we mean by inactive if we go back to our kernel any threads that don't meet this condition。

Have nothing else to do。 So they are exiting。 And that is called early exiting。

 So it's a way to optimize your kernels。 Now， if there was an else condition here。

 if index does an N else do something else， that would be called branching。 So in that case。

 some threads in the warp are doing one thing。 and the other threads are doing another thing。

 That's called warp divergence and we'll talk more about this in class。So if we stepped through this。

We can see that some values update and none of the other threads are doing anything else。

So I've closed the project one， and now I want to open a simple example from the Qa samples。

 which is vector add to show you some of the more basic things without going to GLM V3 and stuff。

 So I'm opening the 2017 version of vector to add。Let's open the file。Compile it。

And while that happens， I'm going to place a bit point here。So in this kernel。

 we have three global memory arrays coming in and all afloat。

 So let's see how we can visualize simple arrays like that in terms of having to go into GL vectories。

Allright， so let's start debugging this。All right， let's add。 Let's step down。1。

 and let's add block I D X dot egg。And thrive。80x。If you double click these tabs。

 it they'll auto size。 So I I use that quite often。 And then we want I。 and let's go for a of I。

And be off， I。And C or I。 Now， assume your first question is， hey。

 why is A B And C working here when it's coming from global memory。

 But when we were trying to access A R R in the points example， it didn't quote。

 That's because A R R was a GL M V 3。 And there are the watch window didn't exactly support that strap。

 So that's why we couldn't visualize it。 But here that's fairly simple to do just because these are types identified by the watch watch window。

So we can step through this quite easily。 and as we step down。

 then we see the values getting updated。So now that C is updated。

 Let's see what happens when we go beyond the execution。 So in a normal function。

 this would just return to the next。It would step out and go to the next statement of the previous function。

 But this is a ka kernel。 So there's more threads to execute。

 So let's go into locals or add a watch for thread I D X dot。T I D X， and。Block Ax。

I'm not using this because this is also going to change。 So keep an eye on this。

 So thread I D X is all 0。 block I D X is all0。 So let's step down。 So what， let's see what happens。

So now what's this。 So third IDX has increased to 32， which means we are in Warp 1。

 so let's go back here and you can see that I can't scroll up anymore and there's no0，0，0，0，0。

0 for the first block first warp that has exited。 So now we are looking at this warp。Now。

 how can we instead of going to the next warp， I there a way to go to the next block， for example。

 So to do that， going to inside。嗯。You can either jump the wars here if you want， if they are active。

 So the previous warp is no longer active。 So this doesn't really make any sense。 So but what we。

 if we want， let's say， jump the block， what we can do is come into freeze and do schedule locking resume block。

 Okay， so keep an eye on this now。32，0，0，0，0，0， right。So let's step through this。

And none of these change， because we are still on the current same thread。 So now what happens。

 Let's step through that。And look at this。 now， block IDX has increased 1，0，0， and thread IDX is 0，0。

So that means instead of jumping to the next warp in block  zero， we jump to the next block。

So if we go back into our war。 now， look at this， I can't scroll up anymore， but all the 0，0。

0 blocks are gone。 And now we are at block 1。So let's try that again。So step down， step down。Now。

 what do you think will happen here。 Take a guess。So this is increased to two now。 again。

 we're staying at the first wart because we are essentially starting a new block。

 So only the block index has increased。So let's change the freeze mode。To resume warp。

 let's see what happens， so。I'm going to step down now。And we are on the second block，0 warp。

 Let's increase that。 And now we go to 32。 So we have， weve changed the warp。

 We went to the next active warp。 So if we go here and look， the starting index of that is 32。

So similarly， we can we can have different locking and different wars。

 so feel free to try this out at your own convenience and see what happens when you choose different freeze options as these are called。

The last thing I want to show you for today is how to add。

Command line options when you're using the inside debugger。 So you go to this button here。

 inside units properties， and you can use this working directly and working environment and add command line arguments here。

 which are generally picked up from the visual studio debugger。 So if we go to。

Project escape that properties。嗯。Going to debugging。 So if you add any， any arguments here。

 that's gonna get picked up。 But if you want to add specific inside debugging arguments。

 then you can use you add those here as well。 So that's， that's another useful tool for you。

So that's all for the debugging session for now if there's more questions or more things and tips and tricks I can share with you I'll do that in class and as we do more advanced ka learning getting into wars and scheduling。

 you'll understand how to use these tools more to optimize your Qa kernels as well。

So please bring any questions you have to class， I'll be sure to cover those。

 but I may not repeat everything that we've done in this recording in the class as well。



![](img/e9b4133f917741e64e39c7849cde36c8_5.png)

![](img/e9b4133f917741e64e39c7849cde36c8_6.png)