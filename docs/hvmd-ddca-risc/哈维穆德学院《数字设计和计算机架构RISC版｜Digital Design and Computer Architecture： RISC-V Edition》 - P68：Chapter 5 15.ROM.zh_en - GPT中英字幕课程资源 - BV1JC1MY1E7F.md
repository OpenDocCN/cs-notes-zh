# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P68：Chapter 5 15.ROM.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/3fc3742190de62daa6b1aeaa3716784b_0.png)

For roMs， we're going to use or we can use dot notation where a dot indicates a one being stored。 So。

 for example， at address10， the value 1。0，0 stored。The address 11。The value is0，1， zero is stored。

And so cells that contain a one。Basically don't have anything there and a cell that contains a zero。

Has a transistor tied to ground。So that when the word line goes high。When this word line goes high。

It's going to pull。Best。Bit line。Down in this case， data bit1 down to zero。It's going to pull up。

Right here， if we draw it here。And that word line goes high。这个蓝头。That bit line down to 0。

And where there's a one here。There's nothing there so when the word line goes high。

That line just stays at one instead of getting pulled down to zero。So here's the storage 010。

At address 1，0， we have 1，0，0， and so forth。And we still just like all memories。

 we have the depth in this case， two to the two or four。Words by the width， the word size3 bits。

Fujiio Masoka developed memories and high speed circuits at Toshiba。

And he invented flash memory as an unauthorized project which he did on nights and weekends。

 the process of erasing the memory reminded him of flash camera。

 so that's why he named it flash memory。But unfortunately。

 Toshiba was slow to commercialize the idea and Intel was the first market in 1988。And it's grown。

 you know， immensely， we all have at least， you know。Several， if not， you know。

 dozens of flash memory devices that we use regularly。

So one thing we can do with memory arrays is we can actually perform logic with them。

And it turns out we'll talk about this later。 This is how logic fill programmable gateator arrays work is they use。

Memories to perform logic。 So， for example， instead of looking across at， you know，0，1。

0 being stored there， we can look down。What's being stored。For any combination of address， buts。

 So if we， for example， call this ace sub one。And a sub 0， right， Those are our address bits。Well。

 this data sub 2 is performing the X or because for the 11 input and the0，0 input， we have 0。

And for the  one，0。0，1 input we have ones， so we have data sub2 actually performs the x or of a1 and a0。

 so data 2 equals a1 x or a0。And you know similarly， we can look at data sub0， for example。

 and that performs A1 and a0。Or we can have。This one where we get。This is equal to。Well。

 it's zero then， so data sub 1。Equals。A1 a0 bar。Bar。Which is equal to a1 bar or a0。

So it's going to output a1 when we have a1 bar。Here's the A1 bar。😔，Those our ones or。Ace 0。

And here's the A1 bar。So we can think of our memory performing logic and that's useful because， well。

 just depending on what Bitsby store， we can perform different functions。So now let's use our roM。

 a 2 to two by3 bit RoM to perform these logic functions here on the left。 So we'll put X， Y， and Z。

tide them to our，Bit lines and put A and B on our address lines。

And so we want to make x equal to A and B。 Okay， so we'll put a one。In that bit。Y equals A or B。

Why we want to have a one。When A is true or when B is true。And Z equals A and B bar。

 so Z would only have a true output when a is true and B is low。

And so we could still think about this as our know values being stored different at our various addresses at address 0 would have the value 0。

0，0 stored， address 1 would have 01，0， address 2，011， address 3110。But now we're using our。

This memory performed logic。For our， different outputs。 So x equals A and B。

And all those different functions。So we can look at this and say， well。

 what what is this memory array， What functions does it perform， Well， data sub 2 is performing。

A sub 1 x or a sub 0。 look at that function， data sub 1。Is performing well。

 this is the same as we had before， is performing a of one。Or。A sub zero bar。s。That function。

 and then finally our last one。0，0，1 datata sub0 is a1 bar and a0 bar。is our。Single one is one。

 A and B， A sub1 and a sub0 are both low。So we could implement the following logic functions using actually any memory array。

 So DRA S Ram or RAM just depending on what bits we're storing。 So x equals A and B。 well。

 here's our X。 we connect our our address inputs to A and B and we get。1，0，0，0。

This is written with zero on the bottom。And then we could do our next one， y equals a or B。

 well that would be 1，1，1，0， this is written know upside down from a truth table。

And then last one z equals A and B bar。That would be this one。Rest are going to be zeros。And so。

The main thing here is that we can perform logic with our memory arrays。And these logic arrays。

 these memory arrays that we used to perform logic have a special name called lookup tables so we can look up the output。

For each input。 So it's basically a truth table。In our memory， right， so in this case。

 we're doing the and operation， here's the lookup table。

We connect our input variables A and B to the address inputs and then。

Our memory acts as a lookup table。For our tree table。And let's say we in this case。

 we're doing an and operation of A and B and we said oh。

 actually I meant to do the I don't know the or operation， so now I just changed。

The value that's stored in my memory and now an origgate instead of an an gate。

And so this reconfigurability is the feature that we're going to use with our lookup tables or our memory arrays used for logic。



![](img/3fc3742190de62daa6b1aeaa3716784b_2.png)