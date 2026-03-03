# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P128：Chapter 8 13.Virtual Memory Summary.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/9c697395637b4f75411afc16cdcdf4ba_0.png)

So a summary of virtual memory， virtual memory offers memory protection。

 multiple processes or programs that run at once can't access the same physical memory because each process has its own page table。

Each process can use the entire virtual address。So in the case that we had two to the 31 bytes of data or two gigabytes of data。

Instead of being limited to just a small amount of data because the other processes need memory as well。

But a process can only access a subset of that entire address virtual address space in physical memory。

And those are mapped in its own page table。And so only a subset of that virtual memory can be pulled into main memory at any given time。

Virtual memory increases capacity and again， just a subset of those virtual pages or physical memory。

 but it appears as if。You canAnd you can access all of that memory， just not all at once。

A page table maps virtual pages to physical pages， does the address translation and a TLB。

 A translation looks side buffer speeds up that address translation。

Different page tables are for different programs， so each program has its own page table and that provides memory protection between those processes so they can't overwrite。

Data in another running that another program is using。



![](img/9c697395637b4f75411afc16cdcdf4ba_2.png)