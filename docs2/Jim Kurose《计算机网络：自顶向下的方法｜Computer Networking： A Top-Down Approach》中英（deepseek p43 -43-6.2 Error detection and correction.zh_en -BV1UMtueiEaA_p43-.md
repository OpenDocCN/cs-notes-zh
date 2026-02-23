# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p43 -43-6.2 Error detection and correction.zh_en -BV1UMtueiEaA_p43-

![](img/1d5e0af67d2c04ac480f4f71b943d78b_0.png)

![](img/1d5e0af67d2c04ac480f4f71b943d78b_1.png)

In this section we're going to revisit a topic that we covered in section 3。

3 when we were studying the UDP protocol we encountered the Internet checkum remember the internet checkum is used to detect bit level errors and datagrams by UDP in this case we're down at the link there of course we're interested in France we're going to add to our earlier discussion in two important ways。

First， by way of example， we're going to introduce this notion that bit levell errors cannot not only be detected at the receiver but they can also be corrected and corrected without retransmissions that's a pretty cool idea Secondly。

 we're going to take a look at error detection technique known as the cyclic redundancy check that's used in practice and is much more powerful than internet check something so not too much to cover so this should be short and sweet。

Here's the error detection scenario that we studied earlier。 Now in a link layer context。

 the network layer will pass a datagram down to the link layer for transmission。

 The sending side link will then take the datagram at some header fields to create a frame with D bits here。

 and thens going to compute and append error detection and correction bits。 EC here。

 The frames then transmitted over a link that can introduce bit errors。

 The receiver then performs a check to see if the bit frames have been corrupted。

 We'll see how that's done in just a second。 and if the frame passes the check。

 Itll extract the datagram pass it up to the network layer。

 Otherwise the frame will be dropped or perhaps a retransmission procedure be initiated with a and nas just as we studied in chapter 3。

 What we want to focus on now is how this check is done to understand that We' need to understand how these EDC bits are computed for here on the sender side。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_3.png)

Perhaps the simplest case of error detection and correction that we can think of is simple pary checking。

 where a single parodity bit is set to 0 or1 so that the total number of bits among the original debits and this additional parodity bit is even in the case of even parodity。

In this example here， there's an odd number of parody bits in the first D bits。

 so the parity bits set to one so that now there's an even number of one bits among the D+1 bits。

At the receiver side， the check is simple， the receiver simply determines whether or not there's an even number of one valued bits in the received data。

 including the parity bit。If there's an odd number of one valued bits。

 the receiver knows there's at least one bit error， there's an even number of one valued bits。

 the receiver knows well， either there's no errors or possibly that there's an even number of errors Well that's the simple one- dimensional parity check and we can generalize this to a twodimensional parity check laying the bits out on a grid like here and computing a parody bit for each row and for each column and then have the receiver check both row and column parody。

Well， we're using additional bits here。 so you'd hope that this additional overhead would somehow bias better protection。

 And， of course， it does。 You should convince yourself now that two bit errors can always be detected。

 but the twodimenional parity check buys us something more。

 something really special In the case of a single bit error。

 it also allows the receiver not only to detect that there's been a bit error。

 but also detect where that bit error occurred and correct it without retransmission。

 How cool is that。 Let's take a look at an example of twodimensional parity。

Here's a case with our deep bits again arranged into a grid for the first row。

 we now compute the row parody bit to be1 for the second row。

 the parodity bit is 0 for the third row， the parodity bits 1。

 And we can compute column parodity bits as well。 Now。

 let's suppose a bits flipped in transmission as in this example here。 In this case。

 the receiver says， hey， there's a parody error in row 2 and there's a parody error in column2 as well。

 And so it knows that the bit in row2 column2s been flipped。

 The error can be detected and corrected without retransmission。 Well。

 this is just a simple example of what are called forward error correction techniques。

 They're used in DVDs and compact disks in digital subscriber line DSL access networks and in deep space communication We center a receiver delays are very long。

 You'd much rather correct an error on receipt， rather than having to request and wait for retransmission。

 There's a whole field of study。On error correcting codes。

 it's a great area to look at if you love math and math with very practical and very cool application。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_5.png)

Well， we've covered the Internet checksum already in Section 3。3。 and in some ways。

 the checksum is very similar to parody instead of adding up bits， though。

 or're adding up bytes with the Internet checkum。 But conceptually。

 the behavior is the same on the sender side， we simply add up the bytes。

 compute the checksum and send the checkum along with the data being checkumed。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_7.png)

![](img/1d5e0af67d2c04ac480f4f71b943d78b_8.png)

The receiver action is also conceptually similar to what we've seen above。 Well。

 we've said and seen that the Internet checkum isn't particularly strong。 And so it's not used。

 as far as I know， in any linger layer protocols。 Instead。

 a much more powerful techniques used in ethernet and Wi Fi known as a cyclic redundancy check， CC。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_10.png)

So let's take a look at the cyclic redundancy check Here again。

 we have D data bits that we want to protect。 A CRC has what's known as a generator G。

 which is a carefully chosen bit pattern of R plus1 Bs that's been standardized agreed upon by all since both the sender and the receiver will need to use the same value of G。

 the CRC 32 iE standard has a 32 B generator。 So we see here the D data bits that we want to send along with the R CRC bits。

 If we think about these D plus R bits， the given bits capital D and the CRC bits capital R。

 we'd compute the D plus R bits that we want to send first by left shifting the data bits to the left R positions。

 and then adding in our xoring in the R CRC bits。 And here's what the sender does。

 It's going to compute the R CRRC bits such that this quantity here is exactly divisible by the grid upon generator G。

Since the receiver knows G， it's going to take the receive bits divide by G and if there's a nonzero remainder then it will be able to detect an error CRCs are more powerful than the error detection techniques we've studied in that they can detect all bursts that's all runs of consecutive bit errors of less than R+1 bits that's pretty powerful。

And it's because of these powerful properties that the CRC 32， for example。

 is used in both Ethernet and WiF frames for error detection， the link layer。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_12.png)

But we still have one important question to answer。 How does the sender compute R。 Well。

 we know that the sender wants to compute R such that the bit pattern sent is exactly divisible by G。

 Well， let's X or R and each side of this equation， giving this。

 which is really just a mathematical way of saying that if we divide this quantity here。

 D times2 to the R by G R is the remainder。 And this then gives us an algorithm for computing R。

 Let's look at an example。 This is just a toy example with a small for bit generator G here。

 Here's D。 and here's D left shifted by 3。And now if we want to follow our algorithm over here。

 we divide this quantity here by G。 and here's an animation of doing that division。

 and the result that we get the remainder is the value of R that would be sent。

 So's all there is to it， although in practice again。

 the standard generators are a lot longer than four bits。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_14.png)

Well that wraps up our quick study of error detection and correction at the link layer。

 I hope you found the notion of forward error correction as neat as I did when I first learned about it and I hope you also enjoyed learning about S like redundancy checks。

 it's a little bit dry， something that's really good to know about since as we've seen CRC codes are widely used in practice。



![](img/1d5e0af67d2c04ac480f4f71b943d78b_16.png)