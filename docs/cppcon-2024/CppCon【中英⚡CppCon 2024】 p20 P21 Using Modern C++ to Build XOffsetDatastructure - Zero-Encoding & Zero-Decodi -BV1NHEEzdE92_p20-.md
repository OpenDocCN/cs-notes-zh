# CppCon【中英⚡CppCon 2024】 p20 P21 Using Modern C++ to Build XOffsetDatastructure - Zero-Encoding & Zero-Decodi -BV1NHEEzdE92_p20-

From game development to high frequency trading， thanks to QDC， the QuaDevelop C。Okay， let's begin。

Hello， everyone。 Welcome to my session。 Today， we are talking about using modern simple parts to build x of satellite data structure。

 A 0 encoding and0 decoding high performance， The library in the game industry。😊。



![](img/f6985a85419577500cdeaa82e01d2283_1.png)

We要 look at how to use modern simple parts to create a solution solution that move data quickly without slow down from encoding and decoding。

Let's start。hom IM to方程from China。Oh， oh， the signal is not。



![](img/f6985a85419577500cdeaa82e01d2283_3.png)

Yeah， itO。这是肯定的。hom II'm fromI'm速方程 from China。I lead a game research and development team in a large video game company。

I have been programming with C plus plus for over 20 years。

 and I'm good at making code run fast and writing code easy to have day。😊。

I got my PhD in computer science from Wuhan University in 2012。Today， we will cover several topics。

 First， well explore the title to understand the project's name。😊，Next。

 we will discuss why this work is so important followed by what the project achieves。😊。

We will then reveal the performance numbers。 After that， well explain how the methods are done。

We will also look at the limitation and plans to address the challenge and future goals。 Finally。

 we will end up with a summary and takeaway highlighting the key point to remember。😊。

This start by breaking down our title。 It packs pack packed with information In this section。

 we will unpack the key concept in our title。 Give you a clear picture of what X of satellite data structure is all about。

😊，The title contains three key elements。 Firstly， what we did。 We created X data。

 a satellite library for the game industry。Secondly， why we did it to achieve high performance。

 which is important in game applications。 Thirdly， how we did it by using0 encoding and 0 decoding。

 which removes unnecessary processing steps。In the following slide。

 we will discuss three key concept mentioned in the title X of theory data structure，0。

 including 0 decoding and high performance。😊，Let's start with the X in X of data data structure。

 It stand for extreme。 and here is why for design， where aim for a big improvement。

 instead of modernization that keep us at O N， we are pushing for a leap from O N to a1。

 This could lead to a greater improvement in efficiency。😊，For in， for implementation。

 we have improved data processing and management for ensure high performance at every step。 In short。

 X represent our commitment to extreme efficiency in both design and implementation。Now。

 let's focus on the offset。 We use offset based points instead of floor points。

 This approach allow us to create data structures that are memory copyable。But why is this important。

Imagine a big game world with thousands of play。 A single process can handle it wall。

 So we divided the world into small areas， each managed by its own process。😊。

As they play move between these areas， their data need to be migrate simultaneously easily。

 Look at the diagram。It showss a large game scene divided into9 areas。

 Each area is handled by a process。Now， let's look at the data structure part。

 X of the data structure is the collection of data structures， including base type custom types。

 different containers and nest types。 The diagram shows how we can combine them to create complex data structures。

Let's talk about zero encoding and0 decocoding。 Our approach is simple。 First。

 civilization without encoding， we store data directly。Secondly， decentization without decoding。

 we access data directly。 Look at the diagram。 It shows that we are removing the encoding and decoding steps。

 The result， faster processing and less resource use。In the game industry， performance is important。

We need every operation to run fast。This operation， including civilizationization， deilization。

 read and right。Now， look at the diagram。 It shows a lot with block causing traffic to Dao。

 This is similar to what happens in a system with performance issues。

 Our goal with X is remove these blocks。 We want our data to flow efficiently without any slow down。

这。Now that we know what our title means， they talk about why we created ex data structure。

In this part， we will look at the reason behind our project and what problem we are trying to solve。

In this section， we explore civilizationization and decentization。

 Serization is the process of converting data structure into data buffers。

This conversion allow data to be reviewed later， even in different computing elements。

We will break down civilizationization and dissization into three parts， input， process and output。

Let start with the input。 The input of serialization is the data structure in the diagram about the data structure burau。

 You will see lines connecting different fields。 The these represent point and references。

The structure form is carefully designed。 taking both time and space consideration into account。Now。

 let's look at the output part of civilization。 The output is a data buffer。

 and the the buffer is a flight continuous block of data is for storage and transmission。

As the diagram shows， the data is a single un interruptterted space that holds the data。Finally。

 lets talk about the process part。 The process involved converting between structure data and flight data。

So that this transform structure data into flight data at Xiao in the up diagram。

D disization does the reverse converting the flight data back into structure data as shown in the lower diagram。

Why is civilizationization so important。Here are three key numbers。

 a study found that civilizationization and I PC use 12% of all processing power across Google's applications。

 Secondly， another study showed that big data apps can spend。

18 to 90% of CPUU time加 the patentthon data。Sly， in games， over 20% of CPU time is spent on sale售这些。

This is really affect how game runs and fails。In games， we need to move data in several areas。

 firstly。Between server and clients， loading plays and NBC data when new scene。

 secondary between server， including R between different services， salary。

 data migration will game data between things， areas and lies。

When the same process become overloaded， it divided into area and lies as Xo in the diagram。

 Things are divided into different area。 A area is a part of thing， managed by one process。

As showing in the diagram， thing are divided into different lines。

 A lie is a logic group of play managed by one process。😊。

S division is good to manage stable load and keep the game smooth， even with lots of play。

 Diding into area and lights give us more control。 But it also't means that we need to move data efficiently between these divisions。

😊，As play move between area or switch lines， their data needs to be quicklyized。

 transformed and deized。Now， let's look at the calendar civilizationization method。

 They fall into two categories。 The first category include measuring pack and Pluto buffers。

 The second category include flight buffers and capital Pluto。We will look at them in terms of input。

 output output and process。For the face group。

![](img/f6985a85419577500cdeaa82e01d2283_5.png)