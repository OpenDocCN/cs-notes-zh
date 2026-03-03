# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P53：Chapter 4 9.Testbenches.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

So let's talk about the last topic which is test benches， and we're going to use test benches。

 these are not synthesizable， this never turns into hardware。

 but test benches are for helping automate our simulations。

So we don't have to laborly go through and set the inputs and maybe toggle the clock。

Instead we can use a test bench and perhaps we fix something in our module and then we can rerun the test bench and see how it worked。



![](img/b6c8d193c1bf9a570a3bd9dff04b68de_1.png)

So a test bench is an HDL module that tests another module and this module that it's testing is called the device under test or the DUT。

you also see it called the unit under test or the u u t，系。So this is not synthesizable。

 a test bench is not synthesizable。This is just for simulation only。

And let's talk about three different types of test benches。A simple test bench。

 self checking and self checking with test vector so we're going to kind of build upon each other。

So let's start by writing the system barrel code for the module under test。

 the device under test this is some simple function y equals B bar， C bar， or A and B bar。

So pause the video and write a module for that function。Okay， so we write this module。

 we have the keyword module， the name of the module， the inputs， A， B and C， the output Y。

And now we specify the function assigned Y equals B bar， C bar。Or A And B bar。

So this is our device under test or the module that we're going to test in our test bunch。

So here's the first version of the test bench， the simple test bench。So we have the keyword module。

 and then。Our module name in this case， test bench one， you notice there are no inputs and outputs。

Get some internal signals， ABC， and Y。And now we're going to instantiate the device under test。

The silly function module。DT is the instance name。And we connect it to a b c and y。

And now we probe these input values， A， B and C。 So we set A， B and C all to 0 to start with。

 and then delay 10。10 ticks。In simulation， again， remember。

 this is just simulation and test button generally are just for simulation。

They cannot be synthesized。A B and C are zero， we pause for 10 or delay for 10。6ix。

So that we can see the output on the simulation waveform。Let me make c1。 so now we have 0，01 again。

 delay。 so we can see the output y， how the output y changes。0，0，1，0。0，0，1，1。And so forth。

 till we have all of the input combinations。 This final one is going to be。1，1，1 on A， B and C。

And now we run this and we can look at the waveform。

 but instead of having to do this manually setting our A B and C values and then delaying the clock。

 we can just run this simple test bench and so we can。

 but then we have to still manually view the waveform to see if we got the correct results on why。

This is the second test bench， we're going to use a self checking test bench。

And so this part is this looks the same。 we need it test bench2， but everything up here is the same。

And now we start this initial block。Occurs at the beginning of。The of the simulation。And so now。

 in addition to。Seudtting the input values， A， B and C are 0 and then weighting 10。

 we also check the output we say， oh for this one because because of our function。

 y should be one so it's not equal to one。Print display this on the simulation monitor。

On the you know， the text output of the simulation。So display， hey， the0，0。

0 input combination failed。And we make C1 and now is 0，01。

 Y should be 0 in this case if it isn't and print is failed。

Of course you could make an error in this right， you could think it should be zero。

 but it really should be one so now that you know it's a little bit more complex。

And also more opportunities for making errors。But saves a lot of time， right。

 So Im sort of having to go through the waveform and seeing， okay， for 0，0，0。有死。b and c。0，0，0，0，0，1。

0，1，0。 And then we have to look at what the output of the actual module did。And we see。

 hopefully we see it correspond to what we expect。 blah， blah， blah， whatever it did。

 instead of having to go through and look at why now we can。Have a test bench test for it， hey。

 we expect Y to be one here if it isn't。Display some text that that failed。

Expect it to be 0 in the 001 case， ABC equals 001。Otherwise。P that it failed。

 And then after we see the failure。Mesages on our simulation。

 we can go back and check the waveform for those as well。So this is a little bit more automated。

But it's， you know， kind of annoying still to write ABC0，0，0，0，01。

Kind of be nicer to output as a truth table， right， for the00，0 combination， we expect to get one。

So here's our A，BC， and expected。W value。Why expected。0，0，1。expectpect to get 0。0，0，0。We get one， 0。

01， we expect to get zero。0，1，0。 this case。HeExs it get。0。Andt dot dot， until finally the last case。

 111， we expect to get zero as well。And so。Be a lot nicer。

 This is basically our truth table to input that as text instead of having to input it。This way。

And just read that text file and it's super easy to change too if we made a mistake， oh， I actually。

 in this case it's not a mistake， but。for that combination， it should be zero instead of one。

 and I just changed the text file。That I read or live you essentially the truth people。

So we're going to now upgrade this test bench， test bench two into a third test bench。

 and this is the final type of test bench and this is the one that we use most often。

This is a test bench with test vectors and these test vectors are basically those truth table rows。

So the test vector is this 00，0，1 showing A，B， C and the expected Y value。This is called a vector。

So these are our test vectors for the 001 combination we expected0 or 010。Whatever。

So for this test bench， we're going to generate a clock。For assigning inputs and reading outputs。

We'll read these test vector file into an array。We'll assign inputs and the expected outputs and then compare。

For given input。The outputs with the expected outputs and report errors。

 just like we did in the last one。The last test bench will report if the actual output from the module from the device under test and the expected outputs didn't match。

So we generate this clock and on the rising edge of the clock。

 we're using the clock basically to delay the time we assign the input and then look at the output so it's basically doing that the pound 10。

 this is saying， hey， delay for a bit， let the module calculate what the output should be and then falling edge of the clock。

And the clock goes from one to0。Falling edge， we're going compare the outputs。

And the next slide is just like new inputs。Compare the。Outputs， new inputs and so forth。

 So this clock is basically helping us just produce that delay where we want to assign inputs and then wait for a bit before we compare。

The actual outputs of the module with what we expect。

If our device under test is a synchronous circuit or synchronous sequential circuit。

 we can also use the clock to run that circuit as well。So here's an example test vector file。is。

Basically what we just drew on the prior slide， example。 text， this is just a text file。

Comments are ignored that help us remember what these are。 So here's ABC。When they all zeros。

 we expect output y to be1。When it's 0，0，1， we expect it to be 0。Et cetera。

 This is not the actual output， why。Because the actual output Y， we're setting the inputs A， B and C。

 but then the module the device under test is giving us Y。

These expected values we're going to assign to some。Some wire。Some signal what expected。

And then we're going to compare， hey， is what I expected， the same as what I actually got。

Or why and why expected the same。So here we have the test benchch， test bench three。

 we have it know it seems a lot more complicated， we have our clock reset， ABC and Y expected。

 the reset is there so that if it is synchronous sequential。

 you can reset your synchronous sequential logic。At the beginning of the， of the simulation。

And we have our inputs， ABC， our output Y， and then we have that extra wire Y expected。

And now we have these kind of。Bookkeeping， variables， vectorum and errors。And also， an array。

Of test vectors。 So this three column 0， saying the width。Of this array。 So we have4 bit。With。

And this happens to be have 10001 entries， so0。阿超。😔，10000。And we won't use all of those， but。

Just made it larger just in case。And so。We're going to instantiate our device under tests。

 just like we did before。And now we have this。Always block that generates the clock because there's no sensitivity list。

It always executes。So we have always。No sensitivity list。Begin clockicles1。5ive tick later。

 clockicle 0，5 tick later。And it will repeat。 So it's going go one。5ive tick later go to0。

5 tick later go to1。啊大大。Thats our clock generation。And at the start， again， this initial block。

Runs at the beginning of the simulation。And we're going to start by reading。Memory。So read man B。

B says it's in binary format。And we're going to read this， this should be examplet text。

Flow test vector into our test vector array。So we call it happened to close。example that text。

And we're going to read that into our test vectors array and remember that test vector array looks like this。

 and so it will read 0，0，0，1 into entry。0ero or index 0，0，0，1。

And those underscorees really aren't there， they're just for us。That's why it's a four bit。Wade。

Aray0，01，0，0，10 do all et cetera， right in our case， we'll have entries from zero to entry7。Right。

 we just won't use the rest of the entries in the E。And the test vectors are array。Okay。

 so this line reads。The test vector file。Into。The test vectors array and resets the bookkeeping variables。

 vector and errors。 So there are no errors。 And we're going to start at vector。Z。

 so vector number is0。And we're going to toggle reset。AnAert reset。For 22 clock ticks。

And then simulation tick。And then make reset back to zero in our case。

Our device under test doesn't have a reset input， it's not synchronous sequential logic。

 so that doesn't really matter， but for synchronous sequential logic you'll want to reset the system to start。

So a note here is that we could have read or we could have written our test vector file in hexadecimal。

 and then we would have need to use the readMM H。call instead of read men b。So if we had written。

 for example， so if we had0，0，0，1，0。0，1，0。 You could have written that in Hex and said one。只。😔， dot。

 dot， whatever the next lines are。But then we would have had to write。

have read it in using read man H。Okay， so we're going to apply the test vectors on the rising edge of the clock。

So always at pause edge clock。We're going to delay just one tick and say， okay。

 I'm going to sign ABC。And the expected value of Y。 So ABC is assigning。

The inputs to the device under test。But it is not assigning the output Y that will be driven by the device center test itself。

But it is assigning this extra wire over here。 It's called。Why expected。

And then on the falling edge of the clock， always at Neg edge clock。

We're going to skip this test if reset is one， so if not reset， that means reset is0。

Check if y is equal to y expected。 So the output from the device under test。Being driven by A。

 B and C。 I it the same as that。Why are we assigned that why expected wire we assign from the test vector。

If it's not equal to that， we have this not equals equals。It's not equal。W is's not what we expected。

 then we display， hey， we had an error。And this was the input combination that we had， A B and C。

And this is the output we got。And this is the output we expected。

 so this is in the order of the argument。 so we have a 3% B that says print it in binary。

Is that first argument after the。Quotes。And this next argument after。Before the quotes。

Corsponds to what I expected。And we increment this bookkeeping value errors。

 so errors equals errors plus one。And we could have printed， for example。

 things in using hexadeadecimal。For example， A B and C we could print in hexadecial， in this case。

 binary makes sense。But you could also， you know， sometimes textx deimal makes more sense。

And we're going to increment the vectorum。 So in our test vectors array。We have。

 we read the first one and then the second one。so it was zero。

 and now it's going to increment to one， and it will use that to assign at the right next rising edge of the clock。

 ABC and Y expected。And so now it checks and says， hey。

 are we done with valid values in the test vectors array？If it's。Test vector vector numb。

 So for example， after the first run through， we had0 plus one。

Test vector of1 is undefined four bits of binary x。Then。

We're done with there are no more test vectors to assign the inputs。And so in this case。

 that wouldn't happen until vector no equals 8。As test vector。Z through7 are defined。

 but once vector nu is8， it would say it would get to okay， vector nu is 8。Okay， these are undefined。

 they're equal to four bits of binary x。And then， we would print。This kind of summary statement of。

Completed in this case， it would say eight tests completed with however many errors happened。

So remember， this first percent D corresponds to this first argument after the quotes and the second percent D is second。

Argument， if we could have you know， more if you had more percent， you wanted to print other things。

We just have more arguments listed here。Okay， and then if we don't have more test vectors。

 then we stop at the simulation。And you can view the results in the waveform viewer of the simulator。

So what if we have equals equals equals and not equals equals。

 So it seems like there's an extra extra equal sign。

 The reason we use that is because those can compare on not just one and0， but also x。N z。So。

 I'm definedfined and floating。So if you're changing this test vector。

 this test bench and you're using it to test another module let's say it has five inputs and one output。

 they're all one bit inputs， then you would make sure to change this with five inputs and one output all one bit。

I am bit width。Then you would change that to6 bit。Binary X。

 so that's a common error people forget to change that。That bit with。



![](img/b6c8d193c1bf9a570a3bd9dff04b68de_3.png)