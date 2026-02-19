# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p10 10 - Machine Prog_ Advanced Part B -BV17jcReyETC_p10-

![](img/89b2d05443e959e6e7bec266bcac1c3a_0.png)

![](img/89b2d05443e959e6e7bec266bcac1c3a_1.png)

Okay。Back in action。 So now let's just talk about one last little aspect about memory allocation。

That we haven't gotten to yet。And that's unions。 So in see。

 there's three different ways you can aggregate data to form larger data structures there's。A rays。

 there'sstructs or structures and unions。 So you've already looked at arrays and structures。 Now。

 let's talk about unions。 And you'll see that the decoration for a union looks exactly the same as the declarationation for a structure。

But its meaning is very different。 So the lower part shows the structure and its layout。

 And what a structure is， is there's a sequence series of fields。

 and I want to be able to use all of them。At any given time。

So I have to allocate enough memory and insert padding bites and deal with alignment issues and so forth that will give me all the fields of the structure and make them all available。

On the other hand， a union is a way of saying。I don't want to use this all these fields I want for each field to be able to use it。

At any given time。But trust me， I know what I'm doing。

 I'll be careful because they'll actually line up so that all these fields are allocated in the same region of memory。

And they all start at the same address。 And they're as big as they need to be for that particular object。

So you can think of the total size of a union as a maximum of all of its fields。

 where the total size of a structure is the sum of all of its fields。

 plus whatever padding you had to insert。

![](img/89b2d05443e959e6e7bec266bcac1c3a_3.png)

So why would a program have a union， It sounds like a kind of useless thing， Well。

 there's a couple clever things you can do with a union。

 one of which is actually you saw an action in the data lab。

 Remember where you wrote these floating point functions。

 but you treated the number as an unsigned so that you could manipulate the individual visual bits of that number and then magically。

 it got turned back into float and used for testing。 Well， this is the code that we used to do it。

 See you see bit to float， It takes an unsigned number and creates a float with the same bit representation。

 So it's different from a normal cast。The way it does that is it。It uses an union。

 So it writes an unsigned value to the union and retreats afloat from it。

 But since theses are really the same four Bs， what we're doing is just converting how we view these bys from thinking of it as a sequence of bits an unsigned to afloat a4ing point number。

 And I can go the other direction as well。But it's important to note that it's very different from a normal cast to a float or an nu sign。

Another thing that shows up when we use unions is it gives us visibility to the byte ordering that this particular machine used。

 and we mentioned this earlier the idea of byte ordering， which is for larger words。

 how should they be ordered in memory， should they be least significant first or most significant first。

 and there's two conventions for most of the machines that you'll encounter at least in this day and age are little Indian machines。

 Intel machines and arm processors can actually the hardware can support either byte ordering but both Android and iOS and I think Linux as well？

I'll use little Indian by ordering。A but big Indian is used on the Internet。

 So when larger numbers are sent over in internet packets， they're actually sent in big Indian order。

 The most significant bites are first。

![](img/89b2d05443e959e6e7bec266bcac1c3a_5.png)

So this example kind of is involved， but the idea of it is。

When you use a union and you have different fields of different data types。

 then the byte ordering and actually how long the different words are for a particular machine is going to affect how those patterns interact with each other when you read one and you write the other。



![](img/89b2d05443e959e6e7bec266bcac1c3a_7.png)

And so I won't go through this code too much， but you can read it on your own and you can test it out yourself。

 But what you'll find is it prints different things。

 depending on whether it's a 32 B or a 64 B machine。



![](img/89b2d05443e959e6e7bec266bcac1c3a_9.png)

呃。And whether it's little or big Indian， it's pretty tough to find a big Indian machine day anywhere。

 actually ran these experiments years ago when there were big Indian machines were commonly available from Sun microcrosystems。

So that's sort of ramping it up， as I mentioned， there's three different ways to create compound data types。

 arrays，structs and unions， and they have some similarities。

 but they're very different in other ways。All of them involve。Some contiguous region of memory。

 But in array， what it does is create replicates a single type over and over again and lets you access it using an integer。

呃。Index to get element I。Astruct is a way to create a series of fields。

 each of which has a name to it。And they can potentially be values with different types。

And then unions are way to overlay on a single region of memory。

 multiple different fields that give you different interpretation。 And if you are also seen。

 these can all be nested recursively。 so you can have a arrays of structures containing unions。

Coning arrays and so on and so forth。 So that all these become recursively defined what the ideas are。

 But the critical idea is to understand is this idea that each of these objects has a size。

 its total by allocation and it has an alignment。 How many。

 What multiple does the starting address have to be typically some power for to satisfy the alignment requirement of all the data within it。

And you can see other slides in here， which go through some examples of real life examples。

 but a bit old of different buffer overfo attacks。 Nowadays， buffer over attacks still occur。

 It turns out the biggest source of vulnerability nowadays are what are called social engineering attacks where people try to trick you into clicking on a link or。

Are responding to some fake email or something like that。 But these technical ones。

 buffer overflows is still a problem。 There's been a lot of work trying to make them less common and less easy to exploit。

 but they still exist。 And it's still important to understand them。



![](img/89b2d05443e959e6e7bec266bcac1c3a_11.png)

So thank you very much。

![](img/89b2d05443e959e6e7bec266bcac1c3a_13.png)