# 051：-MemSafety3, Video 12- Harder printf Vulnerability - Controlling What We Write - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay， so we are halfway done。 We have successfully gotten this printf function to write to the address deadbe because when Prif sees this percent n。

 the next unused argument on the stack is arc 4。 and it just so happens that I put the address deadbe at the memory box corresponding to a 4。

 The next thing that needs to be true is I need to get that target number into memory。

 the number 100。 And remember， the way that you control the number written into memory。

 whether it's 100 or 50 or 200， the way that I control that number that I write into memory is by controlling the number of bytes printed so far。

 because what is percent and do， it writes the number of bytes printed so far into memory。

So specifically， I need so that by the time this percent and occurs。

 100 Bs have been printed in total。 So let's do some counting。 What does printf do。

 It prints the E F， That's one byte， Then it prints B， E。 That's another byte， then it prints A D。

 that's three Bs， then it prints D E。 So by printing out this value。

 deadad B 4 bytes get printed in total。Okay that's good。 That's not 100， though。 If I stop there。

 I would get the number four written into memory and that's not what I want。

 So I'm actually going to use a little trick here because I want to get to 100 characters。

 So I could just try writing 96 A's and be done with it。 but that's not going to fit in my buffer。

 I can't fit 96 A's in there。 So I'll use a little trick。 in printf。

 if you add a number before the formatter， you're telling printf to pad。

 So if I say something like percent 94 C， I'm telling printf， go on the stack。

 take the next thing on the stack and print it， but when you print it。

 please pad it to 94 characters。 So add extra space characters so that the total number of bytes print it is 94。

 So that's a nice little hack that's going to allow us to print out 94 characters without writing 94 A's because that would have been very annoying and also would not have fit in buffer。

 So this percent 94 C to make a long story short。 It print out 94。ChaersIt goes on the stack。

 takes the next unused argument， print it out。 And if it's not 94 characters。

 it will add extra spaces until it's 94 characters。 So how many characters have we printed so far。

 We printed for from dead beef。 And when we saw this percent C。

 we substituted it with something on the stack， pated it to 94。

 and we printed another 94 for a grand total of 98。 So we printed 98 characters so far。

The next percent format is percent C， so I go on the stack。

 I take the next argument and I print it out and I guess I haven't told you this so far。

 but C stands for character， so it takes up one byte， so when I take percent C and I print it out。

 print out one more byte， I am now at 99 bytes print it。There's another percent see。

 So I go on the stack， take the next unused argument， which happens to be this one。

 printed out like a character， which takes up 1 byte。 and now I am at the magic number of 100。

 and just so happens the next input is percent n。 So when percent N thinks how many bytes have been printed so far。

 Well the answer is 100。 And so at this point when I see the percent n I will write the number 100 into memory So that was the last piece of juggling I had to do and notice that all of this had to happen at the same time。

 which is where the trickiness of this exploit comes in I had to simultaneously think about each of these percents matching up with someone on the stack and percent n had to match up with the dead beef that's how I control where I am writing。

 But also I had to make sure that the total number of bytes printed thanks to this padding formater。

 that had to add it up to 100。 and that was controlling what I write the number that I write。

But if everything lines up correctly， I should get the case where when I hit the percent n。

 I look up the next unused argument happens to be dead beef。

 I count the number of bites printed so far。 happens to be 100。

 So this exploit' is going to write the target number 100 to the address deadad beef。

 and we are finally done。One very small ni that sometimes people ask about the percent C format is kind of weird when it goes on the stack。

 it does read four bytes， but it prints it out as a1 byte character。

 so it ignores the top three Btes， kind of a weird quirk of how C works。

 but in case you're wondering why it looks like this。 all the arguments， percent C percent n。

 whatever they all consume four bytes on the stack， they match up with one of these memory boxes。

 even though some of them only print one of the characters kind of weird。

 but that's what it does not the most important thing here。But something people ask about。

