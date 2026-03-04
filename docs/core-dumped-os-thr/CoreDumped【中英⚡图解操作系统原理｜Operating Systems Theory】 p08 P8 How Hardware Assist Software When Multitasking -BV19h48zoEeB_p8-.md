# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p08 P8 How Hardware Assist Software When Multitasking -BV19h48zoEeB_p8-

![](img/95d4514d71e1c1a183277c7e499a1521_0.png)

This video was sponsored by Skillshare。When a process is running。

 it continuously uses the CPUU to execute instructions one after another During this process。

 the result of executing an instruction depends on the entire context in which that instruction is being executed。

 especially on the state of the registers。

![](img/95d4514d71e1c1a183277c7e499a1521_2.png)

![](img/95d4514d71e1c1a183277c7e499a1521_3.png)

The same instruction can produce different results depending on the values held in those registers。



![](img/95d4514d71e1c1a183277c7e499a1521_5.png)

When talking about concurrency， if a process is interrupted。

 the CPU can't simply be given to the next process because the data stored in the registers at that moment belongs to the interrupted process。

 if the new process were to resume execution without handling this properly。

 it would operate in the wrong context with incorrect data。Therefore。

 every time a process is interrupted to allocate the CPU to another process。

 the state of the registers must be captured and stored in memory and the state of the new process must be loaded so it can continue execution correctly This is known as a context switch and it's called that because we are changing the context in which the CPU is operating the problem is that this doesn't just magically happen as I'm showing you in this animation the operating system actually needs to run some code to accomplish this Every time I've mentioned this concept in one of my previous videos。

 someone in the comments asks how this process is achieved without altering the state of the interrupted process so today we are going to answer that question。



![](img/95d4514d71e1c1a183277c7e499a1521_7.png)

Hi friends， my name is George and this is Core Dumped。

It's important to note that we are going to talk about interrupt-based switching in a very simple CPU that doesn't provide an interrupt handling mechanism like the one we built a few episodes ago。

 context switching depends entirely on software in such systems。

 each program is responsible for storing its own state before giving up the CPU to other programs。



![](img/95d4514d71e1c1a183277c7e499a1521_9.png)

![](img/95d4514d71e1c1a183277c7e499a1521_10.png)

Fortunately for us， those kinds of CPUs are quite rare because they are neither safe nor particularly useful。



![](img/95d4514d71e1c1a183277c7e499a1521_12.png)

Interrupts， sometimes also called traps， are an essential feature of computers。



![](img/95d4514d71e1c1a183277c7e499a1521_14.png)

The legendary Mas 6502， one of the most popular CPUs of all time and nearly 50 years old。

 had interrupts。Even microcontrollers， which are designed to be simple processors for controlling electronics。

 have interrupts。

![](img/95d4514d71e1c1a183277c7e499a1521_16.png)

Computers with an interrupt mechanism have been with us for more than 70 years。



![](img/95d4514d71e1c1a183277c7e499a1521_18.png)

So yeah， computers wouldn't be the same without them。As we already know。

 a process can be interrupted in two ways。It can voluntarily interrupt itself by triggering a software interrupt or executing a special instruction to ask the OS for a resource。

Or it can be interrupted by a signal from a hardware component， such as a timer。

 if it takes too long to release the CPU or an IO device。In both cases。

 the effect of the interrupt is the same， the CPU finishes executing the current instruction to prevent inconsistencies。

 and then the program counter is immediately overwritten。

 making it jump to a specific memory location， this memory location contains the executable code needed to handle the interrupt。

 including the code required to capture the state of the interrupted process。

Notice that even before fetching those instructions。

 the program counter has already been overwritten by the interrupt。

 meaning we no longer know where the process was interrupted。Unfortunately。

 we can't avoid this problem， as we'll see in a moment， but before that。

 let's think about the code needed to capture the CPU state of the interrupted process to keep things simple。

 we'll write it in code。To start， we need to capture the values in the general purpose registers。

 so the interrupt handler routine could begin with some instructions like these。

This requires dealing with specific memory locations reserved for this purpose， which can be tedious。

To avoid that， it's easier to push the values onto the stack。The flags are also important。

 so let's say we push those onto the stack as well， and the same goes for the stack pointer itself。

But wait， the stack pointer is currently pointing to the Use program stack。

That's a huge problem because these instructions are meant to be executed by the operating system。

 which has its own stack。Yes that's right， remember the OS is also software， so it has its own stack。

Executing these instructions would modify the stack of the interrupted process。Well。

 maybe we could start handling the interrupt by modifying the stack pointer so that the register state is pushed onto the kernelel stack。

But now we've overwritten the stack pointer before saving its value to avoid that。

 we could store the stack pointer value into a memory location before modifying the stack pointer and then simply push the value from that memory region。

And we could spend hours fixing little details like this in the most convenient way。

 In fact I'm pretty sure some of you are already thinking about other ways to do it， but ultimately。

 the issue of the program counter being overwritten by the interrupt itself。

 makes this problem impossible to solve， at least by software。



![](img/95d4514d71e1c1a183277c7e499a1521_20.png)

Because there's no instruction we could run right at the beginning to save that value。Of course not。

 by the time the CPU runs the first instruction， that value is gone。

 This is one of those rare but exciting situations we encounter on this channel。

 when hardware needs to support software and not the other way around。

 we'll cover that right after a quick message from Skillshare。



![](img/95d4514d71e1c1a183277c7e499a1521_22.png)

![](img/95d4514d71e1c1a183277c7e499a1521_23.png)

Something not a lot of you know is that I've been working on a book。



![](img/95d4514d71e1c1a183277c7e499a1521_25.png)

But since I've never done self- editing or publishing before， I needed to learn how。

 and Skillshare made it easier than I ever imagined Skillshare is one of the largest online learning communities for creatives。

 offering thousands of expert- led classes across film， development， illustration， design。

 freelancing， productivity， and more whether you're looking to level up your career。

 develop a new skill or explore a passion project， Skillshare has you covered plus there are lessons from hundreds of popular content creators。

 so you can learn directly from the people who inspire you。



![](img/95d4514d71e1c1a183277c7e499a1521_27.png)

![](img/95d4514d71e1c1a183277c7e499a1521_28.png)

Just a few weeks ago， I was still writing my book in Word， but now I'm doing it the right way。

 with professional software designed for authors， and it only took me a few hours to get up to speed。

 thanks to Skillshare， it's all about making the choice to learn。

 grow and invest in your creative journey。And I'm currently learning from this class with Marcus Brownley。

 where he shares his skills in content creation， including script writing， filming， and editing。

So if you've been wanting to pick up a new skill， nows the perfect time。

 the first 500 people to use my link in the description will get a one month free trial of Skillshare。

 don't miss out， Jo today and start learning。

![](img/95d4514d71e1c1a183277c7e499a1521_30.png)

And now back to the video。Any architecture that supports interrupts should provide a mechanism to prevent losing the state of the interrupted process；

 In other words， it should offer at least minimal hardware support to ensure the software preserves the program counter of the interrupted process。

There are two main solutions for handling interrupts。

Keep in mind that each architecture has its own way of doing it。

 and these are just two general approaches The first approach is the easiest to understand instead of depending on a single register set。

 the CPU can provide multiple register sets。Multiple register sets can be assigned to different processes this way。

 when a process is interrupted， the next process can simply switch to another register set。

 avoiding any modifications to the state of the previous process。However。

 there may be more processes than available register sets。

 and since registers are part of the hardware， we can't increase them at runtime。

But here's the thing， we don't need an infinite number of register sets。

2 is more than enough if the CPUU supports operational modes。

 one of the register sets can be shared by multiple user programs。

 while the other is only accessible to the operating system in kernel mode。Remember。

 while the CPU is running in kernel mode， it can do virtually anything。In this situation。

 that means the OS can manipulate and access the additional register set for convenience。

 let's call these the Common Reg set and the privileged register set。When an interrupt occurs。

 the CPU switches to kernel mode， deactivates the common register set。

 and starts using the privileged Reg set， ensuring that the state of the interruptted process remains unmodified。

This way， the interrupt won't overwrite the program counter on the Common register set。

 but on the Privige register set。Special privileged instructions allow the OS to access the disabled registers and copy their values into the currently enabled registers。

After each one of these instructions， a normal instruction moves the value just fetched from the disabled registers into a memory location。

This can be the stack as we attempted in the first part of the video。

 but eventually it will be copied into the process control block of the interrupted process Of course this involves extra instructions not shown here to look up where the PCB is stored in memory。

Next， the PCB of another process is red， and the opposite process occurs。

Normal instructions copy values from memory into the active register set。

 followed by privileged instructions that transfer that data into the disabled Regs。Finally。

 a privileged instruction is used to set the timer if preemptive scheduling is used。

 and then the cisret privileged instruction is executed。In this type of architecture。

 CiRt does two things， swaps the active register set。

 locking the user program into using one of them， and switches back to user mode。

Since instructions are now executed on the Common register set in the next cycle。

 the CPUU resumes execution of the selected process， pretty easy， right？Unfortunately。

 this approach is not very popular， especially among modern architectures， I'm not a hardware expert。

 so I can't give a definitive reason， but my best guess is that it's not worth it to duplicate the exact same circuitry on the CPU dye。

 especially now that modern architectures have hundreds of registers and even more complex components like S IMD registers。

Also， as some of you might have noticed， it isn't really necessary to duplicate the entire register set。

 It should be enough to have a separate set for only critical registers like the stack pointer and the program counter。

 as we discussed in the first part of this video。Let's explore other options。

What if we could automate part of the process in hardware， minimizing the amount of software needed。

 I won't go into too much detail here since each architecture implements this differently。

 but in general this is done in two ways。Instead of duplicating register sets。

 the hardware can automate certain steps， these steps function like hardwired instructions built directly into the CPUU。

Just as we sometimes hardcode things like a database URL or a private key in source code instead of fetching them from an environment file。

 instructions and data can also be hardwired into the CPU circuitry。

This allows them to be executed right before an interrupt takes effect。

One approach is to ensure that the operating system's stack pointer is always accessible to the CPU。

 either through a memory location hardwired into the CPU or a special register。

When an interrupt occurs， critical registers like the program counter and the Sta pointer are automatically pushed onto the OS stack。

 right before the program counter is overwritten to jump to the interruptt handler。

From this point forward， it's the software's responsibility to preserve the rest of the registers。

We must be careful not to write to any registers before copying their content into memory。

 which is exactly what we attempted to do in the first part of this video。

 except now the program counter and stack pointer of the interrupted process are safe thanks to hardware support。

And then we have crazy architectures that take things even further。

 performing most of the context switch entirely in hardware。

This is usually achieved through a segment register that points to a memory region managed by the operating system。

 where a special data structure resides。In some architectures this data structure is known as the Task state segment or TSS。

 and the corresponding register is called the taskask register in very simple terms。

 whenever an interrupt occurs， the CPU automatically copies the entire content of all registers and paste it into the task state segment。



![](img/95d4514d71e1c1a183277c7e499a1521_32.png)

So let me quote myself from the beginning of this video when I said。

 the problem is that this doesn't just magically happen， as I'm showing you in this animation。



![](img/95d4514d71e1c1a183277c7e499a1521_34.png)

Well， it turns out it can magically happen， at least from the software's point of view。

This is huge because it makes this whole video kind of pointless。

 except for the fact that for some reason， major operating systems avoid using this feature。

Of course， this is actually more complicated than I'm making it seem。

 so if you'd like me to cover specific architectures like X8664 or arm， let me know in the comments。



![](img/95d4514d71e1c1a183277c7e499a1521_36.png)

Before ending this video， just wanted to let you know that my friends over at Codecrafters have added new challenge based courses。

 including this one on how to create an interpreter from scratch。

 so you can start creating your own programming language。



![](img/95d4514d71e1c1a183277c7e499a1521_38.png)

![](img/95d4514d71e1c1a183277c7e499a1521_39.png)

![](img/95d4514d71e1c1a183277c7e499a1521_40.png)

I'll leave you a link in the description if you want to support me by subscribing。

And that's it for now， there are more exciting topics coming soon。

 so make sure to subscribe you won't want to miss it。

If you enjoyed this video or learn something new， please hit the like button。

 it's free and it helps me out a lot， see you in the next one。



![](img/95d4514d71e1c1a183277c7e499a1521_42.png)