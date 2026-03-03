# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P40：-040-Packet Switching 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

In this unit you will learn a lot about packet switching it's quite an intense unit and your head might be spinningitting with packets by the end of it。

But's that's why we have videos， you can cover the material at your own piece and review it several times。

We'll start out with a leisurely look at why the internet and almost all modern networks are built on the foundation of packet switching。

Packet switching is simple in the sense that each packet is a self contained unit of data that carries information necessary for it to reach its destination。

Packet switching is efficient in the sense that it keeps a link busy whenever there is work to be done。

 rather than have dedicated capacity reserved for each user or each application。

So after a leisurely introduction to packet switching。

 we'll dive deeply into some of the consequences we'll take a journey that includes more math than you'll see in any other unit in this course。

 the math might seem a little daunting at first but it's actually quite simple Once you learn the math so many other details and complex questions become really easy to answer and understand。

For example， you'll learn why two packets traveling between the same two end hosts might encounter a different delay。

While the time they spend traversing each link is the same。

 the packets might take different path and experience different queuing delays in the router buffers。

Make sure you fully understand the three main components of packet delay。The pization delay。

The propagation delay and thequeuing delay。And that you understand the physical processes that caused them。

By the end of this unit， you'll be able to answer questions like。

 how long does it take a packet to get from here to London or how many packets can I fit in space between the moon and Mars？

You'll understand why routers have buffers and how queuing delay leads to uncertainty about when packets will arrive。

For most applications， this isn't an issue， but for realtime streaming applications like Skype and YouTube。

 they need to play back smooth， pick up free audio and video to the user。

 and they need to absorb the variation delay across the internet you learn how playback buffers are designed for this exact。

Finally， you'll learn about how packet switches work in practice At the end of the unit you'll also be able to answer the question。

 how does an internet router actually work and how is it different from an Ethernet switch。

 how does a router arrange its lookup tables internally and so on it's quite a whistle stop tour of packet switching and by the end of the unit you should have a good intuition of how packet switching actually works in the internet。

