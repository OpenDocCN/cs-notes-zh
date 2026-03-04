# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p07 P7 Why Applications Are Operating-System Specific -BV19h48zoEeB_p7-

This video was sponsored by Brilliant。If you copy an executable file from a Windows machine to a Mac。

 you'll notice right away that the program won't run on the Mac。



![](img/235fff35369d6c6923b0960ab976c8af_1.png)

![](img/235fff35369d6c6923b0960ab976c8af_2.png)

If I were to ask you why， you'd probably say it's because Mac use Ar CPUs。

 while most Windows machines use Intel X86 CPUs。A reasonable answer， but not the full story。

 because if we go back to 2019 when virtually all Macs were still running on Intel。

 you would have had the same problem， In fact， you can run multiple operating systems on the same hardware。

 for example I use both Linux and Windows on the same machine。

 but that doesn't mean I can run Windows programs on Linux， even though both use the same CPU。

But why？Isn't compiled code supposed to translate directly into machine instructions that the hardware can execute if both operating systems are running on the same CPU。

 shouldn't the program work on both？

![](img/235fff35369d6c6923b0960ab976c8af_4.png)

This is a tricky question to answer， but that's exactly what we're going to explore in this video。



![](img/235fff35369d6c6923b0960ab976c8af_6.png)

Let's break it down。Hi friends， my name is George and this is Corre Dumped。

It turns out applications are not only architecture specific。

 they are also operating system specific。I want to start this video by saying that the world would be a much better place if this limitation didn't exist if you ask this question to a computer science graduate。

 they'll likely answer system calls。Some of you might already have an idea of where this is going。

 but for those unfamiliar with system calls， I've got what I believe is one of the best videos on the topic on this channel。

 but for now， I'll explain it as quickly as I can。General purposese operating systems are designed to run multiple processes simultaneously。

 which means they must share hardware resources， one of the most important being the CPUU。

The CPU is the central piece of any computer controlling nearly everything This creates a potential security risk because any process could theoretically exploit the CPU to take control of the system。

 bypassing the operating system and performing malicious actions to prevent this。

 CPUs operate in two basic modes， user mode and kernel mode， in kernel mode。

 also known as privileged mode， the CPU can execute any instruction in its instruction set。

 granting it full control over the system。

![](img/235fff35369d6c6923b0960ab976c8af_8.png)

This includes the ability to manipulate IO devices and hardware components like CPUU timers or the Me management unit。

In user mode， the CPU is restricted to a limited subset of instructions；

 this subset allows it to perform tasks such as moving and copying data。

 performing mathematical operations， evaluating conditions， and running loops。

While these instructions are still very useful， in this mode。

 the CPU cannot execute privileged instructions required to directly control hardware。

As you might have guessed， user programs run in user mode while the operating system operates in kernel mode。

The operating system uses privileged instructions to ensure that no user program can ever gain unauthorized access to kernel mode。

This separation is crucial for security， but it introduces a problem。

Even for trivial tasks like reading a file or more complex ones like sending a message over the network。

 user programs need a way to access hardware。The solution Well。

 if a user program cannot manipulate hardware， it can request the operating system to do it on its place。

For example， if a program needs to open a file and write to it。

 it calls a corresponding system function， requesting the operating system to handle tasks like locating the file on disk and writing to it。



![](img/235fff35369d6c6923b0960ab976c8af_10.png)

And that's exactly what system calls are。System calls provide an interface to the services offered by the operating system。



![](img/235fff35369d6c6923b0960ab976c8af_12.png)

By the way， I'm not sure why the book I use as a reference for operating systems has dinosaurs on it。

 but since we're running JavaScript on the server， I guess we can't really complain。Anyway。

 system calls are usually available as functions written in C or C++。

 and they can be broadly categorized into six major groups；

 each operating system provides its own unique set of system calls。

 and this is where compatibility issues begin to arise。In practice。

 most programs rely heavily on system calls， even the program you're using right now to watch this video is constantly invoking the operating system。

 making thousands of requests per minute for various services。



![](img/235fff35369d6c6923b0960ab976c8af_14.png)

![](img/235fff35369d6c6923b0960ab976c8af_15.png)

And you can check this yourself if you're running Linux， try this command。

 replacing the number with the process ID of interest。

This will display information about your process， and you'll find a field called voluntaryuntary context switches This value represents the number of times the process has invoked the operating system using system calls to request services。

And notice that the number is not small。This highlights the core problem。

User programs are so dependent on system calls that if another operating system doesn't implement them in exactly the same way。

 the programs simply won't work。

![](img/235fff35369d6c6923b0960ab976c8af_17.png)

And it's not just about naming differences， even when system calls have equivals across operating systems。

 their functionality can vary significantly。For example， on Windows。

 you can use the Create Proces system call， which receives the path to the executable file of a program to do precisely that。

Create a new process straightforward， right？Now if you're not familiar with systems programming。

 you might assume the UniIX equivalent， the ForRC system call， also creates a new process。

 and it does， but not just any process， instead it creates a clone of the calling process。

 with the only difference being that the new process has a unique process ID。So on UniI systems。

 additional steps are required to run a specific program right after using Fork。

 the child process must invoke another system call。

 such as exec to replace its text section with the contents of the executable file it needs to run。

This topic is very interesting and probably deserves its own video let me know in the comments if you'd like me to cover it in a future episode。

These kinds of design decisions create significant differences between operating systems on one platform。

 a task might require a single system call， while on another it might require several。

 so when compiled into machine code， platforms will generate different instructions to achieve the same result。

Even though both programs are compiled for the same CPU architecture。

 those extra instructions will lack meaning on the other operating system。

 leading to undefined behavior and ultimately crashes， and it doesn't stop there。

 even if two operating systems defined the exact same set of system calls。

 other low- levelvel implementation details could still create compatibility issues。

 and that's what we'll cover next， after a quick message from Bri。



![](img/235fff35369d6c6923b0960ab976c8af_19.png)

On New Year's we often resolve to learn new skills as developers。

 one of those should definitely be improving our problem solving abilities。With Brilliant。

 you gain access to dozens of interactive courses designed by experts。

 enabling you to learn by doing rather than just reading their first principles approach helps you build a deep understanding from the ground up。

Each lesson is packed with hands-on problem solving activities that allow you to engage with concepts。

 a method proven to be six times more effective than simply watching lecture videos Brilliant is also available on your phone。

 making it easy to build real knowledge in just a few minutes a day。

 unlike mindlessly scrolling through PDFs， their latest courses including applied Python。

 creative coding and thinking in code are perfect for building foundational skills and learning real-word applications。

Helping you to develop the mindset to think like a programmer and begin creating complex programs to build games and apps。

 you can try for free 30 days of brilliant premium and get a 20% discount on your annual subscription by scanning the code on the screen。

 or by visiting brilliant。org/coreDed， also linked in the description below。



![](img/235fff35369d6c6923b0960ab976c8af_21.png)

And now back to the video。When a program needs to request something from the operating system。

 it triggers and interrupt。

![](img/235fff35369d6c6923b0960ab976c8af_23.png)

This interrupt causes the CPU to switch to kernel mode and hands control over to the operating system。



![](img/235fff35369d6c6923b0960ab976c8af_25.png)

On architectures like X8664， a special instruction called Siscoll is used for this purpose。

But once the operating system takes control， how does it know which system call was requested。

 and if the system call requires parameters， how are those parameters passed from the user program to the operating system。

 the common approach to identifying system calls is to associate each one with a unique number。



![](img/235fff35369d6c6923b0960ab976c8af_27.png)

Before invoking the system call at the hardware level。

 the program writes the corresponding number into a register；

 when the operating system takes control， it reads the value in that register and consults a cis call table to determine the requested system call。



![](img/235fff35369d6c6923b0960ab976c8af_29.png)

On the source code of the Linux kernel you can actually look up the number associated with each system call by checking architecture specific files this also reveals just how many system calls Linux supports the ones we've discussed so far are only the most commonly used。



![](img/235fff35369d6c6923b0960ab976c8af_31.png)

Once again， if two operating systems don't provide the same system calls using the exact same table。

 the same machine code could request entirely different services depending on the operating system。



![](img/235fff35369d6c6923b0960ab976c8af_33.png)

Let's assume both operating systems use the exact same Cs call table。



![](img/235fff35369d6c6923b0960ab976c8af_35.png)

Does that guarantee compatibility unfortunately no if one of the operating systems use different registers to specify the Cis call number。

 the program would break running on that OS because it would read the wrong register。

 identifying the wrong system call and leading to undefined behavior？Okay。

 but what if both systems read from the same register， does that solve the problem， still no。

 many system calls also require parameters and how those parameters are passed depends on the operating system。



![](img/235fff35369d6c6923b0960ab976c8af_37.png)

Some systems require parameters to be stored in registers。

 while others write them to a specific memory region， or a combination of both。For instance。

 on Linux， if a system call takes fewer than six parameters， they must be stored in registers。

If more than six parameters are needed， the remaining ones are written to memory。

These seemingly small details matter。

![](img/235fff35369d6c6923b0960ab976c8af_39.png)

This is yet another example of how a program designed for one operating system might technically execute on another OS running the same CPU。

 but behave unpredictably， for example， the OS might expect parameters in memory while the program has stored them in registers or vice versa。

If parameters are stored in memory， the method matters， does the program use the stack。

 or is there a specific memory location for this purpose？



![](img/235fff35369d6c6923b0960ab976c8af_41.png)

If the parameters include pointers， the address width becomes important。

These are just a few of the low level details that need to align This set of conventions is known as the application binary interface or ABI。

Just as an API defines functions at the application level。

 an A defines how different components of binary code interact on a specific operating system and architecture。

And this is just in regard to system calls， yes， we're not done yet。

Even if all the issues we've discussed were resolved。

 other lowlevel details could still cause compatibility problems。

 one of the most significant factors is the executable file format， As we know。

 an executable file is what compilers produce after translating source code。

 but this file doesn't just contain instructions， it also includes data and metadata that allows the operating system to load and execute the program。

Where in this C of ones and zeros is each part of the program located。

 does it look like this or like this， or maybe like this？



![](img/235fff35369d6c6923b0960ab976c8af_43.png)

Each operating system has specific rules for this。This structure ensures that the executable can be loaded and run properly by the operating system。

 while also supporting various features like linking， debugging， and dynamic library usage。

 if you're interested in this topic I recommend looking into the executable and linkable format used on Linux and the portable executable format used on Windows。



![](img/235fff35369d6c6923b0960ab976c8af_45.png)

Another reason that comes to my mind is runtime environments。

Some programming languages don't compile directly to machine code。

 they run on a virtual machine or an interpreter instead。

This means that as long as the virtual machine is installed on the system。

 the same code can run across multiple platforms。Ironically。

 virtual machines and interpreters are designed to bypass many of the compatibility issues we've discussed throughout this video。

 however， modern applications are often built in a modular way。

 if all the modules are compiled to machine code， that's great。

But if even one module depends on a runtime， and that runtime isn't installed on the machine。

 the entire application might fail to function。I have nothing against languages that require a runtime。

 but maybe we should stop writing critical components of our systems in them。Then again。

 we're running JavaScript on the server， so I guess we can't really complain。

Let's wrap things up for now， there are more exciting topics coming soon， like CPU scheduling。

 so make sure to subscribe you won't want to miss it。

If you enjoyed this video or learn something new， please hit the like button。

 it's free and it helps me out a lot， see you in the next one。



![](img/235fff35369d6c6923b0960ab976c8af_47.png)