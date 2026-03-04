# CppCon【中英⚡CppCon 2024】 p40 P42 Performance Optimization in Software Development - Being Friendly to Your Ha -BV1NHEEzdE92_p40-

There's more value in the connections outside of these talks and actually it's new the talks themselves like we've spoken to a lot of very experienced。

 very tenured people who have lots of you know， great stories and mistakes that we can learn from so that we don't have to make them as well。



![](img/015dc962402246dc32bbfb563e5d3bd2_1.png)

Good morning。Welcome to a session that looks a little bit into the hardware side of the world。

 so that's a gentle introduction to software engineers about the hardware Memans McDonald's and I will be trying to show you a little bit of what happens beneath but before we go through that one kind of my happy administrative notice from kind of pleasing me as a speaker I came here 10 seconds later to the room then the first indeed and that's Maria I'm over there so she gets a virtual prize thank you for being so much interested in my talk。



![](img/015dc962402246dc32bbfb563e5d3bd2_3.png)

![](img/015dc962402246dc32bbfb563e5d3bd2_4.png)

Then let's， as this is first session in the morning， start from a question。Where is C plus plus R。

 What do you think？Well， you write the code， compile it doesn the magic， and what happens here。받은등。

Yes， it runs on the abstract machine。 That's correct。 Have you seen one。That's abstractized。

So the word is that abstract machine is quite rare。

 although in the universe there are quite many of the rare species， one of them is a spherical cow。

 but here you see a picture of a spherical cow in a vacuum。

 right so that apparently is more real than the abstract C++ machine。

So if we try to look more from the practical perspective。

 C++ actually runs on the computer platform on a mix of hardware and surrounding components。

 So what's that platform。 we are always simplifying the things here。

 so that's a process and that's a memory there's something in between that allows for them to communicate well in the rest of the world is the IO side which is important。

 but we don't care about that in the context of this talk。A long time ago。

 processors looked like that， that's actually the part in the center is a processor。

 with time they shrank a little bit， memory initially was made of inductors。

 then it moved into capacitors。Then there was an interconnector a long time ago I remember soldering one myself。

 similar to that， so he has a processor， he has the memory and the rest is something that we don't care too much if we fast forward 40 years until now processor still looks like that it has slightly few more pins like a few more thousand memory also has increased a little bit in various properties and capacities and the interconnect well that's really scary but we don't care about that in the context of the stock therefore we skip it。

So let's start from memory。In essence， memory， dynamic memory。

 the entity that you are using to store your code and data is an array of capacitors。

 the element that stores the actual logical level there at the lowest level is a capacitor。

capapacitor contains a charge， that capacitor is controlled。

 it can be switched on into the fabric which allows for that value to be read to be written。

 and a myriad of those capacitors eventually forms the memory module which you are using。

How does that work？There's a protocol defined for sending out operations and retrieving back data into the memory and here we are talking about the protocol and electrical domain that means we send in some signals we have timing parameters and after some time we get a response how does the memory interaction look like a note about the addresses and and other parameters here。

 we are not talking about the software visible addresses here that's something very different we'll come to that in the course of this presentation so imagine we have our hypothetical memory array we send command for addressing the portion the horizontal portion of that array that's called activation and we wait a hypothetical nanosecond for that to take effect so basically sending that in。

Memor array and the logic that does the work internally， we have to wait。

 then we send another portion of the address coordinate。

 it selects a fragment of the previously selected row and again we have to wait until all of that happens internally。

 then only then we actually get access to our data that's contained at address is indicated。Then。

After we have finished reading writing writinging especially reading。

 the structure of the dynamic memory is such that any operation is destructive。

 therefore if we read something we actually destroy the value that we have read。

 therefore we need to return it back that's called recharge also memory by itself and that's basically due to the physical nature it cannot hold the charge all the time you need to constantly reread and rewrite that that's called refresh that has to happen on the order of tens of milliseconds for each and every addressable entity。

Then you will ask for that to be recharged and then you wait again。

If you look into all this timing diagram， yes， we are talking about nanoseconds。

 but as somebody here in the audience has on its badge， nanoseconds matter。

 nanoseconds add up and you get quite noticeable seconds overall that impact that's visible in your performance。

And the problem here is that actual data transfer or the useful goodput of the memory interface is roughly 10% of what it is possible from a theoretical point of view。

 why。There are laws of physics。If you want to charge or discharge a capacitor well it has a charge that's voltage you need if you want to discharge it you attach it to some resistance thats current flowing right the large of the current the faster the capacitor will discharge the problem is that if you start talking about a kiloms there this is inside of really small integrated circuit and there are lots and lots of other such capacitor cells around you cannot talk about large currents if you want to charge the capacitor faster well that's simple apply high a voltage again that is controlled by the transistor the switch which has its isolation barrier limit of what voltage you can apply to that so physical properties govern what you can have performance wise。

Now marketeers certainly would be happy to sell you another generation of memory which is an order of magnitude faster if you compare for in say in real world examples。

 DDR1， which is 25 years ago in DDR5， which is today the actual capacity array speed is the same like 200 megaherz for one and the other back 25 years ago。

 DDR1 at 200 megahertz capitor array speed was top of the line for DDR5 today。

 that's well ultra budget。But still the actual speed of the capacitory hasn't changed that much。

 which what has increased substantial and many orders of magnitude is the green part in this diagram that we don't care too much。

 well we care， but it is irrelevant to us the actual speed of transfer of the data has increased。

 Yes， you can transfer a whole lot of gigabytes per nanoisesecond。

The problem is that you cannot source those from array and you cannot sing them into the array。

 So what shall we do Well， first， let's look a little bit from a theoretical point of view what why do we have these specifics in memory。

It's。Herarchtically a two dimensional address structure， again。

 that's done for electrical engineering type of reasons that you cannot have everything aligned in onee and be free from signal integrity problems there's also deep aspects related to the manufacturing process and so well scary analog electronic stuff。

From the protocol perspective， you also have a limited amount of signal pins coming involved into the model and into the actual memory component。

 and that is one of the limitations why you need to have that dynamical structure then you also need to remember that memory is dynamic the dynamic memory is dynamic well it shouldn't come as a surprise。



![](img/015dc962402246dc32bbfb563e5d3bd2_6.png)