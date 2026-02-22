# Elliot 《CUDA编程｜CUDA Programming Course – High-Performance Computing with GPUs》 - P11：Chapter 10 (MNIST Multi-layer Perceptron).zh_en - GPT中英字幕课程资源 - BV1MA2VYGEdp

Work。

![](img/ae3ba39c4a447415d3fed36690a00a69_1.png)

I am so， so excited for this part。In this last section of the course。

 we're going to be doing the final project。 This final project is awesome。

 We're going to do an Mist M LP training run from scratch。' going to go in the following order。😊。

We're going to start in Python， Pytorrch， super easy， right？Then we're going to go to nuumpy。

 make it a little harder， but understand what's going on and at the hood。

And then we're going to go take our nu P code and port that over to C right it's going to run on CPU。

 It's going to be super easy to read and comprehend and understand right。

 and then we're going to push that over to Kuta。And then we're going to rank it fast in Kuda。Awesome。

 so navigate over to this folder。 we're going do with different ones。

 What it's not going to be slash kuda course。 It's going to be slash Mnes Kuda is like just a separate thing to help organize things better。

 Maybe you want to show this to a friend or whatever or or present as someone。 And this way。

 you can kind of just have things separated out and neatly organized right。

 So you can consider this as like kind of a separate part。

 We're just kind of building on what we did previously。So if we copy this。

 we're going to go ahead and actually clone this into a new directory。

 and I'll kind of walk you through how things are going to go。

 So I'll go ahead and full screen this up。Right。Sure， already saved。

Now I'm going to speedy into that。Going to go。Uv， V and V， just like that。

 I'm going to activate this。 I just create like a Python virtual environment。

 That's all I really did there。 and then we going to go。Pip at U V Pip install install dash R。

Requirements。And it's going to go ahead and install everything that we need。嗯。Okay sweet。Now。

We're going to pop into the。 we're actually just going to open this up into VS code。

Go ahead and do that。Now， if we pop into the。I mean， full screen this。Perfect。Okay。

 so if we go into this Python folder。Just to like help you navigate the structure of this。

 So we're going to what we're going to do is we're going to progress up from Pythons。

 We're going to go through Pytorrch as seen in here。

So it's pretty much just like an entire Pitorrch training run for a multi layerer perceptron。

And then a little Jupiter notebook。 that's like the same as that。

 but just in a notebook format instead。 And then we have a nu pie script。 So just going through。

And writing everything from scratch and nuumpy。This may not look the same by the time you're watching this。

 but it'll be very similar and very easy to understand。 at least for the Python stuff。 So I mean。

 you've probably already written some Pythtor already， or at least you understand like the basic。

 you know， N and dot linear layer， right， You probably understand that already。

So all we're actually doing。In this one。 And this is what I'm going to demo initially is we're just。

 we're literally just training an Mist MLP from scratch using basic P torch。

 So I import everything initially。 So like time， nupy torch rate。

 the data loader and the torch vision for the data set itself。

 which is Mnist we specify hybrid parameters here。 So。You know， learning rate， batch size。

 number of epochs。 I think there's like an extra one here。 I don't know why that's there。You know。

 train size were like number of elements in the train set。

And then we're going to go to adjust this data directory。Let just print this out， actually。Take that。

Injected into here。And we'll go to slash， slash Python， allright。Now。😔，Sure， slash data。 Why not。

Now this is going to make sure that we're using TF 32 so that's going to use tensor cores and make things really fast。

 This is going to initialize the data set properly with like you know amine and standard deviation。

 This is just kind of the best the best practice for MNs。

 So a lot of this here I'm kind of just following some boilerplate code template examples。

 that kind of thing。And now we go down further and it's。You know， we initialize our data sets。

We initialize our loaders。We load in all of the data and we have this exist on the CPU。

 So notice how we're not doing device equals ka or dot kuda yet。 we're not doing that。

 is this just exists on CPU， right， system RA。So。We let all of our train get in。Right。

All of our test data in。We're just printing some stuff at each step here。

 itters per epoch so per epoch， we're going to do train size， which is 10，000 divided by batch size。

 which in this case is4， so it's going to be about 2500 iterations per epoch and we're going to do three different epochs。

 so 7，500 steps total。Now we go down further。And we have the actual architecture for this itself。

 right， So we we taken in an x， our， which is our input。 We reshape this to batch size by 784。

We do our first layer， second layer， third， right， So it's just like。Matal 1 activation， Maal 2。

 and this is organized as such in features， hidden features。

 hidden hidden features and then the output dimension or nu class。We have our in feature set to 784。

 so this way it's going to be like a batch size by batch size is the x and then weight is going to be 784 by 256。

Thats that's the shape of this it's going to multiply by this linear layer。

And then we have the value which is going to take that and it's going to do the value activation on it。

 you can search that up if you don't know what that is already， it's very very basic to understand。

It'sterally just a graph。And in linear， same idea。 we're going to take that previous batch size by hidden features。

 we're going to multiply that by hidden features and nu classes。

 and we're going end up with B by nu classes， right， or B by output but dimension。

 whatever you want to say， right？ And that's the idea is we just want to keep forward and back propagating through that and making the network smarter。

We're going to go ahead and transfer the model to Kuda。

We're going to can do we can do torchch compile for a faster version。

 but we're not going to do that just because it like takes a little bit of extra time to do that。嗯。

We're going to use cross entropy loss for this for the entire project here。

 cross entropy loss is critical to understand。嗯。I'm going go over some of this as well。

 Like don't worry if this doesn't make sense yet。 we're going to like literally write this in C。

 So don't worry if this doesn't entirely make sense。

 I'm just kind of giving you the rundown as to like what everything is based off of We're going to use stochastic gradient descent。

 So that's just your literally your optimizer。 So it's going to just nudge the you know。

 when you calculate like a gradient or the to the error for a given weight。 It's going to just。

Literally， you do learning rate times that and then subtract that result from the from the actual weight itself。

So。Scastastic gradient in acent sounds complicated， but it's not。It's not that bad。

 and then we just have our training loop here。And I'll go through sort of more intimately what this means in the in the numpy script in a second here。

 But all that matters is that we kind of understand this spoiler plate。

 This is designed to be like quite minimalistic， just kind of match what we're doing everywhere else。

And。Yeah， I'm not going to highlight this too much， but we'll go ahead and run this just， just for。

 just for fun， you know。Seeity into there。We'll do Python port reference。

And literally what this is going to do， S is going to install our Ms data。

 so notice how we got it in the Python data directory。嗯。Awesome， so now it's initializing everything。

 It's loading all the data so。We can see this。 This is learning over  three epochs total of 2500 each。

 And we end up with an average batchge accuracy of 90%， which is really good。

So when it's classifying those digits， it's getting about 9 out of 10 of those guesses correct。

 which is really good。 And we can see that by the loss here， right， the losses。I move this up。

The loss。You start from loading everything in。Start from the loss of about 2。38。

 which if we into we pop into Chrome here go to。Go to Wolfram Alpha just to like provide a reference。

E X P。Of negative 2。 was 2。38。That's about 0。92。 if it's like if we round down and say 0 negative 2。

3， it's about 0。1， which if you convert that to a percentage is about 10% accuracy。

 which is exactly what we want。 Their images arranged or the labels are between 0 and 9。 So0。

 literally there's 10 values there， So there should be initialization。

 a 10% chance of getting one correct because it's randomly initialized， right。

And so that's exactly what we want， everything is initialized properly there。嗯。Now。

 before I actually go into the nup implementation， like Numpy is like taking pi torch and seeing like what the heck that's doing under the hood。

Just like kind of a from scratch approach。 I would recommend that you pause the video right now and watch。

Andrearpaththe's micrograd video。 So he made this micrograd video about two years ago。

 It's done really， really well。 And it literally just explains the concept of back propagation on the level of scalar values。

 So in this one， we're using we're using back propagation on the level of tensors。

 but understanding this is crucial for moving up to tensors。

 So after after you're done this And it's like still a little bit confusing about how we're gonna bring this up to like bigger matrices。

 I would recommend that you also take a peek at my back propagation video。

 This is just on my YouTube channel here， Elliot codes。 But right now 5。7000 subscribers。

 you should be able to find me。😊，And I just kind of made like a funny title because back propagation is annoying to understand sometimes。

 And so I， I did a I tried to do my best job to break down what the heck that means on the level of tensors on the whiteboard。

 This does have。This does have 1440 P quality， so you can actually， can you can see stuff。But yeah。

 and then there there's just like a ton of like content that you can watch， right。

 I don't encourage you to just like consume all the content out there。

 but these are the three that I thought were the easiest to like build an intuition on what propagation is。

We're going to be going over back propagation as well， but this is。

This is like where you want to start from if this is like a completely foreign concept to you。

 So Andrich Arpathy does really good。 I， I go above Andrich Arpathy's lecture and go up to tensors。

And then three blue1 brown， which you've probably heard of already。

Does does a quick little lecture on on back propagation intuitively。

 so let's go ahead and jump in an umpie。Okay， awesome。

 So now let's go ahead and take a look at what exactly this diagram is supposed to be。 I could。

 I could walk through and sort of just like， explain what's going down like essentially what is happening step by step in here。

 But first， I want to make this obvious， how our neural net architecture is structured and how the neurons actually work。

 right？ What is the neuron， that type of thing。嗯。So。I drew this little diagram。

 Tell us understand what's happening。 And I'm going to lay this out here。

 So we essentially take an image。 This is the hand hammer and digt。 It's 28 by 28。

 And we're going to have this in a batch right。 And it's going to be 28 by 28。

 And then depth be our batch batch size， you could say。

So there's just a bunch of panes essentially layered on top of each other。We flatten these。

 So 28 times 28。 that's going， it's going to have this this whole image。

 and we're going to take a row。 we're just going to add it to the end until it stretches out to the full length。

 It's going to be 28 of these rows that are added to the edge， right。

And then we plug this into the first weight， so x1 times w1， that's going to be b by 784。

 so B by 784， and then times 784 by 256。So a column。

 the size of a column in the weight matrix of 784， and then the length of a row in x is also the 784。

 so it's going to layer on top of those， right？And we're going to end up with P by 256。

 then we go to the next one。And we get this， we essentially just speed this through the value。

 So it's going just it's going to do the rally function on each value， pretty simple。

Then we do x2 times W2， and that's going to do B by 256， which was output from the re。

 It's going to matrix multiply that with 256 by 10。 10 is our output size， right。

 So we have this B by hidden size， which is 256。 each that's each neuron output。

 That's essentially how many neurons we have 256 in in in our hidden layer there。

And then we just have to ensure that broadcasting is done correctly。 So， I mean， you could always。

 you could pop over to like Pytorrch broadcasting。

![](img/ae3ba39c4a447415d3fed36690a00a69_3.png)

Broadcast of rules。Broadcasting semantics here。 So this is pretty much just how you're allowed to like multiply things and do operations with tensors when there' are certain sizes right So you know if you haven't gone through this already。

 it probably is a good idea。 It's not too hard to learn Pythtor handles this stuff pretty well。

 So it's just a little short short read to do just kind of understand like what's happening there。

 but essentially you just want to make sure those innervalue are the same then the outer ones are going to be your output shape right So we have this B this B by 256 and then the 256 here is going to just it's going to do product。

 It's going to take each column。And do product there。

 and you're going to end up with a total of 10 values for each batch element， right？

And this is essentially this， this， this 10 here is a distribution of probabilities。

 So probably probability distribution in batches and in a batch。

And those are going to be our predictions， the probability of which digit it is。

 So if the screen says like a 0。Then what's going to happen after our network is really smart is the if we go to say any batch element。

 so any any essentially row and we go to the first the zero with index in that。

 that's most likely going to be the highest number in the entire distribution right that's kind of what's going there。

And then we just do a loss function on this called cross entropy loss。

 which I'll explain in a second， cross entropy loss isn't too bad。It's seven than MSE loss。

 but it's better for batches and kind of what we're doing here。So。We get our loss。

 which initially is going to be around 2。3。Based on the alpha based on the Wolfformm alpha calculation you can do right。

 where you go EXP like expentiate negative negative x， so expentiate negative 2。3， you get about 0。

1 for that。Which is 10% accuracy。And then you do the derivative of the loss。

 which is just going to essentially elementwise subtract softmax probabilities by the true one hot probabilities。

 And I'll explain those as well what one hot means。And then we just back propagate right。

 So this is kind of the forward pass here where we go matal 1 activation， Mainal 2。

 calculate the loss， and then we backwards this way。 So we do derivative derivative of the loss。

 and then we do our chain rule back propagation。So we calculate Dw2 and that's just going to be keep in mind the gradient of the weight is supposed to match the shape of the weight itself。

 so notice how W2 here was 26， 256 by 10 here we do 2565B Mattmal that with B by 10。

 and so we end up with the outer dimensions 256 by 10 and that matches up。Then we do Dx2。

 which is needed for continually back propagating through the R out layer。

 and so here it's literally just taking the Dx2 and then doing an elementwise multiplication with with the derivative of the re function of x。

 so whatever whatever the input was into that。And then we end up with the same shape that we got here。

We simply plug this， we plug this value out into both of these。

 We don't actually need to do it for Dx1， but it's just kind of here just in case in case you have like a deeper network and you want to modify things。

嗯。But， D W1。It's gonna to be。 So X， X 1 dot T， right， So we're transposing X1。 X 1 is over here。

 So just flipping those， flipping those dimensions instead of being B by 7，84， it's now going to be。

784 by B。 So you have each column is an image， right， instead of each row being an image。

We maped that with B by 256， which was the rally output， so that's like the last output gradient。

And then we get our weight value， right。And then from here。

We pretty much just modify the the weights value。 We get the same shape there。

 So that kind of checks out。And then Dx1， I mean， we don't actually need Dx1 here， but I include it。

Just in case kind of the point there is， you know， Dx1 relies on W1。So。We， we。

 we don't actually need to like update anything for this。 It's just if there was like a Dw 0。

 if there was like a layer before that， because notice how。Sorry。

 I notice how this re layer relies on this， right？ So if you had like a like if we had a re。

 if we had a re layer like before this， if we had a re layer somewhere in here。

 then you would actually need to like D X0， for example。

 and Dw 0 you would actually need to use this， but since we're not。

 we can kind of just understand that it's something you would have if it was a deeper network。

 but you don't actually need it to make the network improve in performance， right。

 It's just like an extra calculation， that's redundant So you can just kind of exclude it unless you want to modify it。

But I'm not going to ramble on about that for too long。

 Let's actually get to what the heck these neurons are doing， all right。

So I got this little like editor open here。ItsLike my first time using it。

 But essentially what's what's how a neuron works is we're gonna like z in how a neuron works is we're going to take a bunch of x values。

 All right， So x1。X 2。X 3， and。These are going to go， Sa these are going forward。Into a neuron。

 right？What's going to happen here。Yes， these are gonna go。Yeah， I should。Try these a little better。

So this is our neuron here， we're just going to put a plus there and you'll understand why in a second。

This neuron is going to have a bunch of different weights。 Okay， this neuron is going to have。

It's not I'm just going to have one，1 weight for each of these x values。 So W， W1。W2。And W 3。

And all this is going to do is it' going do product these。 So it's going to go。W1。X1。Plus， W2。X2。

Plus， W 3。X 3。And that's gonna give us。Output， right。So。This， this times this。

 this times this and this times this， right， That's a single neuron。

 and what we're going to end up with。Is when we sum these together。

 we're going to end up with a single value。And end up with a single value。1。Bow。1 value here。Now。

 when we jump up to a bunch of neurons。So if we had， say， like X。X 1。X2。And we have， say， one，2。

 three neurons。This one is going to have。 Each of these are going to have two neurons， right。

 So it's going have。1，2。1，2。And one，2。This looks very familiar to something you've seen before。

 which is the MLP that I previously showed you right the images you've probably seen like。

 you know clickbait thumbnails with these before， and this is exactly what it is， right so。

You're going to have two weights in here， two weights in here and two weights in here。

And so it's going to do product with each of these。 you're going to have。And have this。

 which is going to be。You know， like a W1。X1。Plus a W2 x2。And then the same for these as well， right。

It's going to do all of these。 And you're going to end up with three total values。

 So you're going to end up with one，2。Three values in the output。Now。

 if we actually go to linear algebra and try to understand this concept。

 things are going to actually make a lot more sense， okay。So we go to linear algebra。

 say we have something of size 1 by。

![](img/ae3ba39c4a447415d3fed36690a00a69_5.png)

As say。784， right？And then we map Mo this with something of size 784。By 2，56， Okay。

 ignore my handwriting。 It's terrible。But this is going to be each x value， right？X1。And then。X，784。

And we're going to have 256 neurons。 Okay， so this is number one。And this is。u。256， okay。Now。

All we're going to do。Is literally take the at。This is gonna be like， essentially it's gonna have。

That this is the number of rows it has， right， This is， this is the height of the matrix。

 So it's going to essentially just look like a vector。 It's going to be。It's going to be this。

 And this is going to be a line。And this one is going to be quite tall。

 So it's actually going to look like this。 It's going to be。7，84。By 2，56， like that。Now， this。

This column right here。Is going to be a single neuron， right， This is going to be。Sa。Wen。Nuron。

This is going to be a set of weights that's going to map。

 each each of those weight values is going to multiply with a single x value。 right。

 So W1 is going to multiply with this one。嗯。W2 is going to multiply with x2 down here and then all the way down to whatever n is。

Or sorry， down to down to the down to 784， which is the length of it。For the length of the column。

 I guess the height of the column， would one interpret that as。And this acts as a single neuron。

 right， as long as that's clear， we're good。Now we have a bunch of these neurons。

 As a matter of fact， we have 256 different neurons。Right。I don't know how to write with my hand yet。

 I'm still going use to it。But we have 256 different neurons， right？And。

They're each dot product with the input itself。And we end up with a final output。

 So notice these you know， cancel out and we end up with one。By 256。So for one example。

 we're going to get 256 neuron outputs。Now， if you envision this as say。Btch by 784。

 So instead of one image flattened。It's a bunch of flattened images， right。

 each each flattened image is a row。Then essentially all you end up with is this B just replaces the one。

 so you get rid of that。And you end up with this B here。 And this is just a batch of neuron outputs。

 right， So it's like it's like， imagine thinking about this entire this architecture here where you have each X value plugging into like a different neuron just imagine this。

 but but you like layer them on top of each other。 So you have like you have like， say you have this。

 like as it' as it's looking at you at the screen。And then you plop it down like this。

 and then you put another one on top， batch element1， batch element 2， batch element 3。

 batch element 4， and each of these is going to give you something so。This。

All these outputs is gonna give you like。Say at。This is going to give you。What's it called？

256 different outputs。And you're going to have these in a batch of batch size， right。

 so their 256 outputs are all layered out here and then each one stacked on top。

Is just another set of to 56。 right， That's how I like sort of like to to reason through this in my head。

 You might want to reason through it differently， but I find that to be a pretty cool trick of understanding how these are working。

Now， there's another term。That I did sort of leave out。 And this is the bias， right， So the bias。

Eat one of these。Each little one of these neurons。Is going to have its own bias， right？So。You know。

 x。X1， X， X， N。 And now each of these little neurons。It's going to have its own bias。

 So we're going to do， you know， a dog product operation， as we normally would。

 We're going to do like。X2 or x 1 times x1 times W1 plus x2 times W2 all the all the way through all the different weights inside of a neuron。

 And then once we get that， we're going to add a bias to that。

 And the bias is just going to be a single number because， of course， it's a scalar value， right？

 So it's going to be。Essentially， it's going to look like this。W。Times x， we're going to do。

 we're going to do all of these that we need to do product， essentially like a。Like a vector。

 a vector vector multiplication。And we're going to add a single bias value to that， right？

So the vector x is going to look like this。And the vector W is's going to look like this。

 It's going to be a column。So we take this column and we we do essentially a matrix multiplication。

 but they're vector。 So it's like literally what it looks like is。And you just take this element。

 and you。You multiply it with this one， right， So you kind of。

 you kind of like put like a stick through it you go。

And it's like cut up into a bunch of little multiplications and you sum them together and。

You do your bias。And we can back prop you through that as well。

 So hopefully that just clears up some of the intuition as to how we're actually structuring this part here。

 So that rule that I just showed you also applies for the X2 and W2 right The point is。

 we're just trying to understand what the whole design of the neuron is and how we can abstract that up to linear algebra and then write really。

 really fast C and C plus plus and ka code to make this like run fast。

 instead of just considering each little neuron operation independently。

 we can it can put a layer of abstraction up and say we've proven that this is how this works in the linear algebra And now we can step forward and try to really optimize that based on our knowledge about matrix multiplication。

 right， This is one of the reasons why emphasize the Matlen so much is because it's an extremely important algorithm in all of this deep learning stuff right。

But yeah， now we can。Now let's look at how we can like you know cross entropy loss and back propagating through all of this。

All right， awesome。So now we next have to do the loss function and the loss function isn't actually too bad。

 So if we pop over to here。Notice how we have this cross entropy loss， right， This is our。

 this is our loss function once we get the what we do modeled up forward from our X batch and we get the Y predicted and then a cache right。

 Don't worry about the cache。 Just worry about these this Y pre and the the batch Y， right。

 So we go over to our cross entropy loss。And inside of here， we're going to dissect this thing。

 by the way， don't worry too much。Inside of this thing， we have batch size。 So just。

 we essentially just take an element from the shape。

 through our probabilities from the softmax function， which we did go over before。

 We have this piece of work here。And then we just finish it up by calculating the loss， right？

Assuming that we understand how our softmax function works。

 we can actually go ahead and dig into this。So。I'm going to open up。Open up a Jupyter notebook here。

So。I'm going to go at an importump。Then， we're going to。

Define the cross entropy loss function itself and softm。 So let's go ahead and take these。

And poplop these into here。Then we're going to say set our batch size as， as 2。

 And then we're going to set。Classes to5， al right。Then。We're going to go and make a shape。

 we're going to go in and make our both of our inputs to cross entropy loss here。

 the YP and the Y true， all right？So white bread。We're going to set the sequel to this nuie R n batch sized by nu classes。

 right so that's going to be our predictions。 bunch we have a bunch of batch elements。

 each with a probability distribution about which output it thinks should be。

 those are the predictions， right。And then we have a y true， which is going to be random integers。

And I'm going to print these out so you can see。So why print？Looks like this。

 It have batch size of 2。 So 1，2。 And then we have a bunch of these elements。 right。

 This is our probability。 Actually， these are not our our probability probability distribution yet。

 These are actually called logits。 So I skip a step there。

 But loggiits are the step before the softm， right。

 Softm is going to make sure that everything is above 0。 right。

 It's going to make sure everything is 0 between 0 and 1。 right， that that's the idea there。

 And it's going to express with confidence which numbers should should be high， right。

 because it's exponentiating。嗯。These are logits because it's like。Like the lodge its。

 I guess you could say it's like the log， like the log probabilities。

 So because you have to exponentiateiate up to get to Softmax。 It's like log because you go down。

It's going to do LN， not actually log with base 2， or log base 10， it's going to be LN。

 so base E or 2。71。And we can go ahead and print out to our white crew。So this is。This is an array。

It's very， yeah。You're going to see why this is important in a second here。

But if we actually pop to our next step， we can go probabilities equals softm of wide pre。

 so we're going to see these values get expd we can print out。Our probabilities。

We can see that as a part of this Which values were the biggest， right？

 So this one was the biggest you know， closer to positive infinity。 and these this is like negative。

 negative， negative， negative， right， So this is like the biggest。 This is the second biggest right。

 So we can see this is the biggest number。 This is the second biggest。

 And then this is like these are these numbers are like smaller right？ And same for this one。

 we notice how oh， this is 1。95 is really big。 And then we have a 1。

2 So it's like this is the biggest second biggest right， That's kind of how that plays out。

Then we're going to go and do correct。Log pros。Is going to be。A correctect， Correct pros。

We're going to do this part。 We're going to do this part here。 So probabilities。

 And then we're going to stick these two inside of it， all right。So let me do this。

We notice that what this does。Is it gives us。It gives us the indices。

Of the correct pros inside of the prediction inside of the prediction matrix， right？So。

Inside of here。If we actually print out。If we print out。Y。And P dot arrange。Right。

 and then we have our Y true。We can essentially think of this four and one as our correct labels。

 So in batch number and batch in this first batch element， the correct index。

 the correct answer is is number 4 right， So it goes 0，1，2，3，4， this is supposed to be close to1。

 If this is close to one， we're doing a good job， that means the loss is going to be low right this is the correct answer。

 So if everything is like favoring this index here。 If this was the correct。

 say class to pick that's what we want to optimize for。

And then this one is picking out the same thing。 But for the second element。 right。

 So that's why we do when we go up to y true here， we're doing。

 that's why we do this batch size here。 So it's going to span the elements。

 the total number of elements and batch size。And it's going to just select the indices right So we kind of just do a random number here because it's between0 and nu classes。

 So you know it goes from 0 to essentially4， So 1，2，3，4，5 or 0，1，2，3，4。

 And so that that's what's happening there We just initialize things randomly。嗯。

But we see that we did number 4。 So it's going to pluck out number4 of the first one。 So 1。0。165。

 and then same thing to the second， right， we have， we have index 1。 So it's going to go to 0。227。

Now。We have this。 we have this correct probs， which I just explained here。And。

If we go down or if we pop up a little bit further。We see that we just did this part， right。

 So now if I wrap NP dot log around that term。NP。t log。We'll just say。Would to say correct。Log probs。

 we'll just do NP。t log of that。And then if we do correct log probs。

We notice that we're just doing the log of each of these of each of these number， Right。 So。

 so if we go import math， then we go。Maathdot log of。At 0。165。We get this number right。

 so negative 1。8。And we're just doing this for each of these elements， right？

And then we continue further， and we go。Moss。Is the sum of。Lost is the sum of all of those。

 so the correct log problem is going to sum these all up together。

 So it's going to be like a negative 1。8 and the negative what we're around 1。5。

 So they're going to add and we're going to get about negative 3。3 negative 3。47 or 3。27。嗯。

And then we divide all of this by batch size to kind of， you know， normalize across batch。

 We don't want it to be too massive。 Like if you increase your batch size to like 1000。

 then your loss is going to be insanely high and you're going to get numerical instability from that。

 You just don't want it。 So you want to normalize over the over the amount of samples that you actually have in the batch。

 And that's going to help stabilize things for us later。During the training process。

 we don't want things to like step up and get worse every single training step。

 So if we go ahead and print out those loss， we notice， we notice how we get this 1。64， right so。

Go back going back up here。嗯。This was， you know。This was。Quite off。 This was a little bit less off。

 but it's still fairly high。 Like these are still like， this is like 16 per，17 per chance。

 and this is 23 per cent chance。And so。That's not very good。 So our loss is going to be higher。

 but if our， if our correct probs array。All correct， probs array。Was。We should nu dot array。

And we go say。0。9。Ens 0。8。And then we you know continue to go through this， so correct。Correct。

 log crs。equalquals。And then， and then we do our loss。Right。When we print out our loss again。

 loss is going to be significantly lower。Because these values， the， the。

 the difference between the difference between。Our prediction accuracy and the actual label was very close right so we thought there was a 90% chance that this index was going to be it right and we we were correct right so that's a very high confidence that we were correct and that's a good thing This is also quite high confidence that we were correct so we want to reward ourselves for that or minimize the loss right。

So if we have values like 10% chance or 5% chance， our loss is going to be stupid high。

 but if we get closer and closer to what we sort of minimizing the difference between what the model thinks it is and what the actual thing is。

 that is really a good thing， that's what we're trying to optimize for here。Now。

 there's another little step that comes along with this and。That's the derivative of the loss， right。

If you go over to Goc here and say。What。What is。What is the derivative of frost entroing loss。

So it's defined as this， which we just went over。

![](img/ae3ba39c4a447415d3fed36690a00a69_7.png)

So why I is the true label， either 0 or one。And this is the predictor。 So。

 So why I without a hat is the true label and why hat I is the predict probability。

 And we run through this。 We do some， we do some differentiation。嗯。We go a few steps later。

 I'm not going to really cover the math behind this differentiation part。

 this part is you know you can do that on your own if you really feel it's necessary。

 but really what we care about is just the answer。So the actual derivative。

 so putting it all together， look at the gradient what we what we actually care about is。

Why hat minus y。 And notice why hats。Was the predicted probability。 So this， so that soft max。

 the soft max los， right， the probability distribution。 and then just normal Y is the true label。

 So if we go back to our code here。嗯。And we look at how that's calculated。

We pop down and we see it is the softm probability distribution minus the true labels， right。

 So that's exactly what we want it to be。 And a lot of this what we're doing here。

 this is mainly just converting things to the actual one hot vector so。嗯。Yeah。

 that's that that that's pretty much。That's pretty much how you do softm and then derivative or sorry。

 cross entropy loss and derivative of it， right？Now， going back。嗯。What's next。

Now we have now we actually have to go through and calculate the gradient。Of our W2， our X2。

Even maybe possibly forward ones and the bias， right， So let's go and look at that。

I'm going to do an example where we pretty much do， we calculate D W1。

 and then we kind of just bring the intuition from that into everything else and then go ahead and apply it right。

 So in in D W1， I'm I'm actually going to go to this in a second here。But I'll bring a white word。

A little closer， so I don't know if you can see this。But I pretty much did， based on， you know。

 the micrograd tutorialator， I did like an output。 This is a neuron output， right。

 So x1 times W1 plus x here times W2， where it's like each of the x values go in and then。The。

 the neuron will a sink like two X values go in。 And there's a single neuron that has two weights in it。

 W1 and W2。 And then it outputs those by doing。By doing a dark product。Between。

 so it does x1 times W1 and then plus that to x2 times W2。

 And I just wrote this in the context of micrograd。 So there's a data and a grad attribute for this。

There is a data and a grad attribute for this。 So notice how I did the the this is a plus sign。

I know you can't see it because it's， yeah， it's very small， but I've mentioned a plus sign。

 So those two added together。 And the gradients are going to the this gra right here of two。

 that's going to flow to both of these nodes。 this x1 times W1 and x2 times W2。

That's going to flow to these the same。 So when you， when you like， for example。

 when you're trying to differentiate a constant。It it ends up just， it ends up just becoming one。

 right So there's actually no change when you have like a graph。Which is。

 which you add add like a bias to it and just shift that curveb upwards。 It still has the same slope。

 right， So that's essentially what's happening here。 And then we continue forward。

 And this now becomes just a multiplication。 So W2。Or sorry， X1 times W1。

 And then we have a data and a gra attribute for those。

 So that's just like kind I out how a neuron is going to be structured in the context of micrograd。

Now， if we pop over to。嗯。And may pop up to this example。Which is。Over here。 So this D W1 output。

What I pretty much did is we go 784 by B， so let's just draw that out really quick。So。7，84 by。B。😊。

And then we have B by 256， right。This is an at symbol。 It's really bad drawing。Bi。By 2，56。All right。

 so how do we actually matrix multiply here， Well， we take a column of this。

And we do product with a row of this， right？And notice how this is batches， right。

 So this is going to be a batch element。 This is a batch element。 This is a batch element。

 So it's going。 This is， we're essentially doing。We're taking the first pixel across the first batch element。

 So if we were to just go here， that would be an entire image， right。

 That would be the first batch element。 It would be an entire image。

 but we're doing the first pixel across the entire batch， right。

 So across all the different batch elements， we're taking or dot product from， the pixel values。

 So like， for example， X X dot data。At index0， right？And then in this context， this is B by 256。

 which is the same as the output layer。 So if we did like， for example， the， the classical inputs of。

You go back to this， it's like B by 784 times 784 by 256。 you end up with B by 256。

 and that's our output gradient， right？So。we're essentially just taking this and we're shifting it around。

 So we're doing， we're taking this B by 256。 That stays the same， but we're transposing the input。

 So it's like X dot T， or it sorry。X dot data transpose。

Maters multi that with the output output gradient， and we're getting the gradient for the weights。

 right， the Dw1 value。So we go back to here。256 remember 784 is how many weights are in a single neuron。

 but 256 is the amount of neurons we actually have in that hidden layer。

So 256 is going to be like this， this is， these are all the neurons laid out， right。

 But what we're going to do is instead of taking like a single。

 a single set of all the neurons from a single batch element， we're going to take all of the。

 all of the the index0 gradients across the。Across the across。Essentially。A batch element。No， sorry。

 Not batch element 0 across， but we're going to take the first neurons。Across the entire batch。

 that's what we're doing。So this ends up being， we'll just say why dot garage。嗯。

Why dot graite index 0。We're doing it across the entire batch。 So it's just a single neuron， right。

 It's just a single neuron， but we're generalizing that across the entire batch。

 So we have this X component generalizing across the whole batch and this Y component generalizing across the whole batch。

 We use the same intuition that we got from the micrograd lecture。 and we just apply it here。

 except we get that generalization ability from using batch processing。

 That's where the big thing comes in here， because we're doing we're essentially doing columns here。

 do product with rows。 And notice the shapes are oriented in a certain way。😊，Yeah， that's。

It is lot to take in， but in the end。We end up with。So this is。

 this is like 784 by B and then B by 256。 So the bees cancel out and we're left with。

I know these shapes are out of proportion， 74。By 256， right。So this 784。

 that's the first pixel value。 So each of these or sorry， each each of these elements。

 that's a pixel， right？That's a pixel in the whole flatten image。 And these are all the neurons。

So we end up calculating these in a way that we can that we can actually update all of the weights properly。

 right， So when all these are laid out， you have the gradient for each neuron across the first across the first pixel value。

 and that is the that is the same way that our initial weight matrix is organized right。

 So in our white matrix。 It's taking these columns of like a single neuron of weights and do product that with with a single。

With it with a single image， right， And it as doing that。 And that's very intuitive。

 And it makes sense。 But in this example。嗯。You know， we， we end up getting those。

 we end up getting the same ones that we would。 We would want to update those with。

 So you can kind of translate and see like， what is this column here。

 What does that consist of and what does this row here consist of。And we can plug that in， and。

We can see that。Our weight updates are actually going to make sense here。So in this one， we。

 we essentially end up with this thing of 256 values。

 and that is just going to be the essentially the gradient。

Of all of the neurons with respect to a single pixel right。

 because this is a single pixel across an entire batch。 again。

 we're just using the batch generalization idea here。

 We're just like generalizing a crossable batch instead of using one specific sample that way it's like better for stabilizing training。

And， and we're just， we're taking that。 And we're just laying everything out for。

For all of the neurons。Across a single， across a single pixel， right。

 that's how we're calculating these So this。 this， it's going to be like this row。

 This is our pixel across like all the pixels for like for all all the first pixel for all the batches。

And then。We have our， our single。We have our first neuron and it's going to go first neuron boom。

 It's going to put the first value there and then second neuron boom all the way to 256 neurons。

 and it's going to spit this out in a column， right。That's all of the neurons。

For for the entire first pixel。And then if we look at how it goes down， column wise。Then we get。

 then we get all the neurons for the second pixel and the third pixel and the fourth one， right？

And so， it can sort of see。That this ties back again into the original forward pass example that we were doing。

If this doesn't make sense， I know my explanations might be bad。You know。

 you might want to go back and I mean， you could draw this out yourself。

 That does work and just sort of visualizing it in your head。

That's a good idea to do that is a good idea to try to understand how this is working。

Alternativelyly， you can watch mysor my tensor level back video。 I think I did a good job on that。

 It's about 30 minutes long so。Anyways。What我。If this doesn't entirely make sense。

We're going to use this intuition of we have this 784。By 2，56。

And this is the same as just our W dot data， right？Soar w。grad。And our W。

Dot data have the same shape。That' what we can essentially do。Is we can take。

Stay in in the grad in the gradient。 for example， we can take this value。

 multiply it by a learning rate of， say， L R equals 0。1。

And we can then subtract this from the original one。So if the gradient is really high。

 that means there's a lot of error， and if the gradient is really low。That means that there's。

 there's going to be。嗯。That means there's going to be less error， right。

 This is why it's called stochastic gradient asscent because you're descending the gradient。

 So it's going to be essentially。W。 data。Equals。LR Is。St X for times。Learning rates。Times。

The gra element， right。And then we do minus equals。So that。

If the gradient value is really high and learning rate is 0。1。

 then it's going to be positive times negative。 And then this is going to get adjusted in the negative direction。

 If the gradient is really high。嗯。And if the gradient is really， if it's really negative。

gradient is really negative。嗯。Then。This is going to， this is going to multiply with this。

 It's going to give a negative value。 And then since we're subtracting a negative。

 it's going to go up and the way it's going to go up。

that's literally all we're doing in gradient descent。And we're doing that for each element。

Now we can sort of take that intuition。And branch it off to， you know， Dw2， right。

 And we can apply that to D X 2。嗯。You know， this isn't really a course on back。

 so don't worry too much if that doesn't completely make sense， it is important。

 but if it doesn't completely make sense， you're still going to be okay。

Because we're going to implement this and you're going to actually be able to see the network learning。

 and you can actually print out things to understand what's happening under the hood。And of course。

 we do need these x values for calculating these intermediate layers。

 right with activation functions。And the activation functions like literally。

If you want me to like draw out how that would work。嗯。Realue。It goes like this， right？

It's like it's like a line。And it goes up just like that。

So what you can do for this is you can say if my value is zero or less。

I'm going to set the gradient to 0 because there's no slope。 The slope is 0。And if it's if it's。

 if it's greater than that， if it's greater than 0， then we're going to set that to one， right。

 because if it' it really is going to make it remain the same if it's above 0。嗯。



![](img/ae3ba39c4a447415d3fed36690a00a69_9.png)

Okay， awesome。Now let's pop into sort of this this Python script that we have running here and just dissect everything that's happening so we can just tie it back to this image that we that I wrote in excgaally draw just so that everything kind of makes sense on a code on a conceptual Ana code level。

All right， so just kind of going through this numppy script now， we import nuy normally， I mean。

 I actually already went through this part I'm not going to review the skin， but if we go down。

 you can see a bunch of functions here right， and these are all these are all super useful functions that we're going to use to essentially train a single layer。

 single hidden layer， multilayer perron from scratch using the intuition we' previously built on that from you know micrograd。

 etc cea， right？So we we scroll down and in this main function， we declare some， some variables here。

 So hidden size， which I'll just set to like 256 in this case。Output size is 10。

 so 10 different digits，0 through 9， and our input size is 28 by 28 pixels flattened out。

And then we're going to put our batch size。 I'll just put8 here so we can get speed learning rate of 0。

001 or over alternatively1 times 10 of the negative3。 and then epochs we're going to do five。

 So epochs is how many times you go through the entire training set right So you go through it at once。

 That's like certain number of iterations， certain number of like4 and backward passes。

 It's like one iteration。 And then you do multiple epochs， which is。You know。

 times that you go over the training data。So inside of here。We declare this model neural network。

 right， input hidden an output size。 And then we just have this train function。

 which is going to actually do that for us。 So inside of here， we have。

A more of epos that we're going to do。 And inside of each epoC we're going to do we're going to train in batches。

 right， so we have this batch size batch of images that are all flattened。 So it's like B by 7784。

 and we're just going to step through kind of going through one by one here。

So in modeled off forward， I mean we in this one we're just taken。The X train is just input images。

 and then this is the output labels， right， It's the， it's the batch Y。So in the model forward。

 we input a batch and we can output cache and we get， we get y red， right， the y predictions。

 the probability distribution in a batch or in batches， right。After we do this model forward。

 we're going to do take the loss function of YP and batch Y which we got from here。

And then we're going to， so cross cross entropy loss calculates the loss。And then separately。

 we're going to take that output again， which keep in mind this is logits。

 so not actual probability distribution，s cross entropy loss is going to softm those。

And then it's going to return a loss。 right， So it does softm inside of here。

 So when we're actually getting the derivative of the cross entropy loss。

 we have to go and do that separately。 Right， We have to get our probability distribution。

 And then we have to essentially just。Like I walked through before how we actually do the how we do the cross entropy lost derivative。

 I walk through that with Goc previously。 And this is literally all we do。 So， you know。

 feel free to like print this out， but this should be fairly intuitive If you work with Python and Pytor before。

 And then we just， you know， do the do the minus for our grad output。

 and then we back propagate from there， right， So we take our grad output and we use the cache。

 the cache。So keep in mind， when we do model forward， we have Ypreread。

 which is the logits and then we have the cache， which is literally just the inputs right so all the different pieces of the layer that we're going to need like for example。

 our D x2， the derivative of the second the second x value or for example。

 the value output right so so just stuff like this that we're going to need to backproagate through all the layers and not just like a single weight or single weight here。

 we're going to need the whole cache of like through the four pass right so that's what that's all that is just a tuple of those。

And then of course， they'll put the logicits right。

 so just to clear up like what the heck cache means there and now that can be like sometimes misleading。

So。We do model that backward， and then we just do model update weights and we pass in， you know。

 weights， bias， weights and bias again。So。Let's walk through what's happening and forward。This part。

 I assume， can I just make sense， We'll walk through model dot backward and then update weights。

 so and forward。Model dot forward over here。So inside of here。

We have the batch size as x dot shape at position 0。 So it's it's going to list the shape。

 It's going to be B by 784 or sorry B but it's going to be the batch that we get。 So when we。

 when we take this part， we're getting an actual batch。 So I and then to I plus batch size。

 So it gets a little segment of like 88 images。And inside of here。

 we're going to take the first the leading dimension of that， which is batch size。

 and we set batch size here。And then we do reshape。 we go batch size by。And then第一。Essentially。

 just the， the last， the last one。 So it's going to be reshaped to batch size by this is just a short way of doing。

28 times 28。 so 784。 that's what this is going to reshape to。

 And then we go ahead and do our our linear forwards。

 and these are these are should be very sensical right， So in our linear forwards。We take in a wait。

We sort we taken an x， a weight and a bias， right， So we do X at W plus B， right instead of W。

W X plus B， it's x W plus B。So that it's， I mean， it's it's B by 784。 we go back to this。

So we go in here。B by 784 times 784 I at 256， and we end up with B by 256， right？嗯。Toru。

 fairly intuitive。And then we add the， we add the bias as well。

 which is another term I actually did not include in this。

 but we can kind of just we can kind of just think of the bias as like an extra。

 extra thing that it adds on。嗯。Now。Scroll down to。Reue， right， So re， I mean。

 this is self explanatory is's just going to do a point rise value。

 It's going to be nupi dot maximum。 It's going to apply that to every single value in there doing good。

 you know。If its if the value was like negative 1， then0 is going to be the maximum it's like which one is higher 0 or negative 1。

 then it's going to pick0， and if it's like1， then it's going to be like oh one is higher than0 right so it's just kind of the value and then really derivative is you know as we explain before how you have like the chart and then goes like this gradient of derivative of 0。

 then it's going to go a gradient 1 after after the zero right。

So that's just that's what this is doing here。Because we want to re derivative， right？Now。Going back。

Another linear forward， we take the value output， so that's the new input to the next linear forward layer。

The the weight stop， the weights，2， and then the bias， too， right。

 So that that should also make sense。 And then we just return that。

 So forward passes and actually is too complicated。

 We can sort of just walk through and understand how the shapes are changing。

 This is more a template example of how to understand this from scratch。Now we move down to backward。

 which is a little harder。 go to backward here， we have。The W1， B1， W2， V2， right。

 So we put in the grad output。 So the starting that wherever we start from in back propagation and go forward and go backward through the layers and then cache as well。

 which is the， which is the forward pass， like intermediate cash stored values， right。

So we go into backward here。And we see。We get in this gra output and the cache， as we'd expect。

 And then we just lay out that tuple。 So F C1 input。 So we just。嗯。F C 1 input， F1 output。

Ralue output， right？So just kind of just unpacking this again。

 now we go to here and it's linear backward， so if we step back to this。Linear backward  one。

Is going to it's going to calculate both of these， right？ So linear backward is a bit bigger。

 actually。eng。We go here。Take in a grad output， select the output thing， the input。

 and then the weights， right so we can calculate both the grad attribute for both the x and the W value right So in here we do grad weights is x transpose times the grad output And so if we go to here。

 we can see x transpose， and then times the grad output， which in this case。

 in the first layer is derivative of the loss。And then in this D X 2， for example。

 we see the grad output times the transpose weight too， right。So gra output times transpose weight2。

 and then the bias。I'll break that down more so in the C section， but is this is the gra bias， right。

 so I can actually just like print that out。Let's let's pop into here， really quick。

And just exit that。嗯。So how did this go again， We do NP dot sum。 So let'll just do NP let' just do I。

Imports N high。As N P， and we go， x equals。We'll just do porch do the wind。

 and we'll do three by we'll say2 by four right print out。Imports， importm toch。And go back up。

Purt out x。 And we get this， right， So if we do。We print out。Forged dot stung。Of X。

 we do axis equals 0， and we go。Cap dims。 think it's cheap。 I it keep dims。 How does it go。

Keep dims equals true。We can see that literally all this does is it is it mus these together。

 So it's going to go to。Plus one。 And then this is like 21 plus that。 So it's 3。23。

 And then so essentially like motion knees， motion knees， motion knees， right， right。

And it's going to do this across the the across like this， the horizontal rate。

 So it's going to mush cross for vertical， sorry， because that is the that is the zero axis， right。

 the leading dimension here。 So that's that's this vertical part。 So it's going to mush vertically。嗯。

And so that's really all that is。So we're just combining things across the entire batch， right。

 but you'll see this more intuitively in the C version。Now we do the you know this as I。

 as I mentioned before， and we just essentially return those right for the linear backward layer。

We return all of our gradients， and then we perform a optimization step。

 so we do the modeled out backward and we do modeled out update weights and we pass one，2，3，4。

 as well as the learning right in。And inside of update weights，'s see right here。

 we literally just do self dot weights， self dot bias， weights and bias。

 and we do minus equals the learning rate。Times the gradient， right？

 So as I was talking about before， you're trying to reduce。

 you're trying to essentially gradient do gradient gradient descent。 That's what this is。

 just that the stochastic gradient descent because it's。It's doing it constantly every single time。

And yeah，'s， that's how we update the network， so。You know if if the gradient is。

 if the gradient is really high。That means there's a lot of error， right。

 So if we do learning rate times something really high。 So a positive times a positive。

 and then subtract that from here。That's going to mean it's contributing a lot。

 And then it's going to be it's initially contributing you know， a lot of error。

 and we want to reduce that。 We want to change it significantly。

And then if it's like say lower we don' we don't want to adjust that as much， right。

 so it's kind of just going to balance between the middle， whichever one gives us the most error。

 right？嗯。And we do this， we do the same idea for all of these。

 and we just do this essentially this scalar value multiplied by each thing in the entire weights and the bias matrix。

 we do that everywhere。 And that's pretty much it。 We do that for every single every single iteration。

 we do a we do a get we get whatever inputs and output predictions we need。 We do a forward passs。

 We do loss function， derivative of the loss。all out backwards。 So backward pass update weights。

 And then if we need to， we just like print out the progress over time， right。

 So if we go ahead and run this。Python say friendly。

We can go ahead and see this is actually training quite well。Really。

This is training quite fast as well。 You know， Ny is binded to C， which C is really fast。

 and we can see that you know， over the first one over the first 7500 iterations。

 we get 93% accuracy。So just to reiterate a little more about this whole linear backward NP dot sum cross a is 0。

 where you take each column and you squash it together。

 The reason we do that is because each of those。Is like across the entire batch， right。

 So this would be like a single， a single layer， right。

 single bunch of a bunch of biases for like all the neurons or whatever you want to say and。

What we're doing here is we're taking a single neuron and we're squashing everything together because like imagine if you have a really big like a really sparse really big reward signal for a single example and then like you do 20 other ones and they have the complete opposite right。

 The idea is to like kind of average all them together。re you're not like divide。

 you're not adding them all together and then dividing。

 but you' you're just like accumulating all them together。

 So you end up with something that's like close and pushes in the direction of like where generalization should be。

 So I know that sounds like really conceptually advanced。

 But it's not its you're just trying to portion would ever weigh the average favors。

 So that's why you do it across the actual batch itself。

 because if you had just this factor laid out。 I mean， you could do that。

 but training might not go as smoothly， whereas if you were to just accumulate everything。

 So you get like on average， What is the best way to move what is the best way to move that bias value。

 then it helps a little bit more。 So that's why we do that。 But now it's getting into see。

Pretty much a port of just the last script that we ran。This V1。 C。

 you'll find this in the naive CPU because this is the naive algorithms， these aren't like really。

 really fast。 These are just like the easiest way to write them very like intuitive to understand。

 but gives us a basis for how we can modify this and turn it to kuta， right。Since that of here。

We do the same idea。We have little neural network thing。At the top， I mean。

 it should probably go from the top to bottom。 But yeah， so inside of here learning rate。

 same learning rate， we have 10 hippochs， which is a bit different。

 I change batch size to 4 because having it as 8 or 16 or 32 just took a ridiculous amount of time to compute through each layer。

 So I set this a little lower to 4。Inmpput size remains the same。 It has to hidden and size 256。

 outputput size is 10， train size 10000 test size。 We're not going to really need this。

 but 1000 for that。 And then we have this in neural network struck， right。

 so we can't actually do a we cant do a class and see， but we can dostructs。

' We don't have like the class and object oriented as aspect we don't see plus plus right。

 this is a functional functional language。 So we're only allowed to usestructs。 And inside of here。

 we just store a bunch of arrays。 So all the weights and biases and then the gradients for those。

 right just to kind of mark everything down easily and and use this very simplestruct， right。

Now we have some functions for。For actually loading the data。 Now。

 I don't want you to worry too much about the loading data aspect。 on this part。

 it kind of just depends on like which use case you have， but in this case。

 I run the downloader script。 So this downloader script just saves everything to a binary file。

And then。Inside of C， we just write those back again so or sorry we read them。

 we read from the binary。 So it knows how we do like file open and then the file name and then a read binary and then it just turns that into into a useful format。

 right so。Yeah， it's not not entirely too too crazy。

 We essentially just like directly read this into into bytes。

And then we modify that as needed later on。 We do the same thing for labels。

 so very simple data loading functions， not too crazy compared to the MNist one。

 but this is in C right， So it's obviously going to be a bit different。Now。

We have this interesting thing here。 I'll initialize weight。

 which I probably should have shown you back here in our where did it go in our C friendly script。

So notice in here how we have multiple functions， right， We have value， Re derivative。

 initialized weights， initialized bias， and then these other ones。

 which I already went over initialize initializing weights and biases。Are kind of simple。 All right。

 They just follow specific guide。 So if we do it， start off with initialized bias。

 it's literally just going to be just a bunch of zeroes， right。

 It's all it's going to be Just need the bias is a bunch of zeros。 That's okay。 We can start。

 and we can move up and down from there。But the weights so biases bias is floating flowing from the previous layer。

 So having it as a0 doesn't actually matter doesn't affect anything。 the bias。

 the bias gradient are just flowing directly from the previous layer。 those unmodified。

 the same gradients。 But the weights themselves are a little different。 So how we initialize weights。

IsI'm actually going to go over to herem going search up hightorch。Ciming initializations。

And this is how you actually initialize。 Ill do， I'll just do torch do dot Nn do aluminum。

We'll go to linear。So。In Pytorrch。We do this。Where is it？Yes， so。The biases。

Are initialized in this distribution， which we we can， we can do。

 We don't entirely have to worry about that。 It's not a big deal。But then the。

 then the weights themselves， these are normal these are initialized on this basis， right。

 So we have have shape output features by input features。And we make this from。

 from negative square root of k to positive square root of k， where K is。

K is one over the input features。So if we pop back to this。We're doing a random normal distribution。

 right？And with each of these numbers， we have to we have to clump them to this range， right。

 So these values are， these values are in some normally distributed range。

 and all we have to do there。Is。We do。We we initialized to this right， So K in this case。Okay。

 so if we actually go to the hand and slideization paper。8 in minutes paper。And。It is。

 I think this is it。Cimmbing hay， so climbing and ha climbing in knit hay and it are the are the same thing。

 But if we go into here， we go2 divided by， Maybe it's not there。 formulaula is somewhere in here。

Where did it go。I search up。R。Initialization。Maybe that's a better term to look for。Yes。

This right here。So。This leads to a zero mean Gaussian distribution whose standard deviation is squareri root of two over over this term。

 and this term is the。I can't remember exactly what this is， but I think this is length so。

We have an input size here， which you could say is the length。

 I don't know if that's specifically what L ties to。

 but I will just hold that assumption for now that that's， that's the idea there is you would have。

Sand deviation， is this。And。And if we continue to go forward。

 maybe we might find something else here too。If we continue。Yeah， so some layers。

Other solution to small factor on the weights， right？Anyways。呃。Yeah。

 this is pretty much the the inspiration from it。 So just looking at like kind of the purpose of this。

ThisThis specific initialization as compared to the pitorrch one。嗯。

Which I probably should have looked into beforehand。The Pytor one is a little different。

But the ha initialization is designed to work well with R。

 so it uses square root of  two divided by input size。

As a standard deviation for the distribution that it's generated on， right。

It essentially counts out for the re activation to zero out negative values。

 So you might have these so calledled dead neurons that come up when you have like the value that just zeros something out。

 and then when you try to like multiply that by something。

 it ends up just like zeroing it out and you might like end up through the training process with like a row of zeros that just don't do anything and they're like useless。

 And so you're not actually compressing an information down into those because they're just zero。

 So this helps deal with that。Now。Jumping back to our C script。This is what we're doing here。

 So we essentially have this we're just we just have to use like what we' what we're defaulted to with C。

 we get this weights，' the size that it's in， we make this scale so squ root function。You know。

 like we were doing before， square root of two divided by size in this case， which。Size would be。

 you know， size may not be appropriate。 I just kind of found this to work and training did exceptionally well with this。

 So we're going to stick with that with the size we're going iterate through this。

 and essentially for each weight value we're going to generate a value between R。

 So R is going to be anywhere between 0 and RA max So21 whatever this is。

 So essentially this this in here is going to be 0 between that max number it's this is going to simplify to between a value between 0 and1 decimal floating 。

32 number between 0 and1。We're going to multiply this by the scale。Which is， is going to be that。

And then we're going to subtract it by the scale divided by 2。

And this is just going to give us a nice normal distribution for for our weights， right。

 this is going to do essentially the same job as we were doing before。

Bas initialize all these to0 as we were doing before。 Re is also very simple。 The softmax。 I mean。

 I think I showed you the softmax and the Triton section。 So this is yeah。

 this should be fairly intuitive。 we get this know we get this max value right And then when we're actually doing exponentiation。

 we subtract the max value。 So we get still remain with numerical stability not having that。

 We just like give these crazy you know E to the whatever super crazy numbers when we have ridiculous arrays with like you know1 thousand native thousand native1。

 it just gets out of hand right So we want we want max to normalize that and just get rid of any of those instability。

嗯。And then， we just compute the Softmax， right this isn't too bad。

 same function we looked at it before。We have a mat mu。

 So I specifically word these so that it would make the most sense。 It's a mat mu。

 But this treats it as like you're taking in an array， A， and you manage just multiply that with B。

 right， So say， for example， a two by4 is a and a 4 by 3。 And so you'd end up with a two by 3。

 And it would organize that in row major order。 right， made these as simple as possible。

 you can dissect these， but we already did a ton of stuff on matm。 So don't。

 I'm not going go over this for the like 20th time。Then we have a A times B transposed。

 so it's going to take in B is like say it's like a is2 by4 and then B is a3 by4。

 and so it's going to do this operation as if it's transposing B to a 4 by 3 so you end up with a  two by3 right？

And then same idea for this one。 if you end up with  four by two and then a four44 by2 as as a and then a four by3 as B。

 it's going to transpose a。 and it's going to make it a two by4。 and they're going to match up。

 You're going to get2 and3。 right， So that that's just kind of the idea there。 And then we do the。

They rally you forward。I probably wrote an additional and have wrote。Yeah。

 so this is like designed to work in batches。 I might have probably written an additional one。

 just like accidentally， which I'll probably remove。No。Reare you there。Yeah。

 so I should probably remove this actually， but well I'll worry about that later and this will be updated by the time you're working on it。

And then we just have the bias forwarded， which is going to， you know， add the bias。

 So literally what this is doing is it's iterating through。It's， it's going through batch size。

 right？ And then we iterate through the actual size itself， which is。

Which is the actual like the the row length。 So it's going to go skip over as many number batch elements as it needs to。

 So it's going to skip， it's going to stride over。Then it's going to add this I offset to it。

 And it's just going to plus equals bias at that that value， right， So we。

 we essentially just have this this row of biases， and it's going to just。Essentially， add。

Each of those it's for like a given batch element for like batch element one。It's going to just add。

 you know， say it's like 10 values here。 It's going to add all 10 the bias values and it's going to go down。

 It's going to add those same values。 again。 It's just applying the same bias to each to each row。

 right， That's what this is doing。Stcrorolling down further。

 I'm not going to go into these quite yet because there's like more happening， but scroll down to。嗯。

The actual。A train function。 And the。Where is this。The int main function， so in here。

We have a pseudo random number generator。嗯。These are pseudo random。 They're not。

 You can actually have completely random numbers。 That's like a very hard。you know。

 cryptographic problem and everything that's like that's something I'm not going to go into you know in this case we're using Sran to generate random numbers but in KUa you can use Qran so it's going to generate random numbers in parallel really fast so you don't have to like wait for the CPU to do this one and this one and this one right it's kind of faster We initialize this neural network class within N。

sorry， struck， struck。 got to use the politically correct correct terms。

 We initialize the neural map。 So we go here， and we just have this N， N。

 and then the weight attribute， right。Equals， then we do Malik just at regular C Malic。

 So weights 1 is going to be hidden size by input size， right。 So that's the 256 by 784。

And then the weights too， which is output size by head and size。This is going to be。U。

What's it called 2，56 by 10。 So it's going to take the。B by 256， and then 256 by 10。

 it's going to multiply those and it's going to get a beat by 10 output right for the after the weights。

You know， bias。I1 is hidden size。 just adding again to that， to that output of all of those neurons。

 each highest value for each neuron。Bus 2， same idea。The graduates。 So just this。

 but the it's just a different， it's just a different variable。 right。

 So we're sting the gradients of those， the error， and they're just going to be the same shape。

 right。And then we initialize we have initialized weight to initialize bias now this is going back to the timing in that we did。

 the hay initialization and the initialized bias that we did before。嗯。Now。

 now that we've initialized those with random values。We go into here。

So our x train is going to be the train size。So train size in this case is you know，10000。

Let me go down a little bit more。 Tra size times input size。 So an image is 784 flattened。

 And then we have the train size， which in this case， is 10000。

The wide train is just going to be a bunch of integers that are that span this。

 so we don't we don't actually need 784。 There's only one integer value per sample。

 which is the label。And then we have the same F for the for the test set， right？

We load these in using the previousing loading scripts that I showed you before。

We can print the first image in the terminal， So it's just going to print things out using the X thing。

 right？So if I I'm going to compile this later and you'll kind of see what I mean。

 but it just kind of shows us like how good our actual predictions are going to be so we can actually like look at an image in the terminal and see okay what did it think this was What was the actual label right we can kind of like look and sort of match things up in our own head I don't want to use like open CVV or a custom extension to put a window because that's just a bunch of extra work it's easier to do it in the terminal。

And then just the training labels for those as well， right？

And then we go through and we do the train function， which is comprehensive。

 and then we furry everything up。 We don't do coudda free。 This is just Cs。

 we just do free and it it gets rid of the weights， biases， all the gradients for those。

 the train set and the test set， right。Now we go into train。Inside of here。

 there's a bunch of things happening。 All right， So if I click this and see where the end is。

We have this， we have this this hidden right here。 So that's going to be， you know。

 the B by 256 as we looked at and。The be by。Or was it。Btch size by hidden size。

So that's like going to be the actual hidden layer output right， So， so here we got to be by 256。

 that's the hidden layer。 It's the， that's the first， know， Ma output， essentially。

And then we get the output， which is batch size by output size。Which in this case， is B by 10。

And then we do numb batches。 So the number of batches we're actually going to do is train size divided by batch size。

 and the reason we do this。Is because we don't want to just like offset that each time and we don't want to give it the same data each sample。

 So if we take that total 60，000 and divide that by batch size， meaning like four。Or sorry。

 train sizes 10000 and then batch sizes for。 we're going to get 2500 total total batches each with four images in them。

 So we're going to do four and then  four and then  four and then four this way。

 we don't like overlap right containing the same images in adjacent batches。

 We just kind of give it new data every time。And we do epochs over that， right。

 So we do all of the batches。And then we do another epoch over that。 So what's going to happen。

 it's going it's going to do like up to 50% in the first epoch or some number like that，50%。

 And then it's going to start the next epoch。 And it's going to learn from all the examples that it had previously and it's going be like oh we saw those again we know exactly what to do there。

 So it's it's going to get accuracy is going the loss is going to look like this。

 it's going to start figuring everything out， tuning whatever it can get its hands on and it's going to drop because it figures out what to optimize。

 and then it's going to plateau through that epoch。 It's going to sort of plateau out。

 And then the next next epoch starts， and it's going it's going drop again because because it's seen those again and it can optimize for more it can compress more features into that because it's seen that already。

 So it's going to continue dropping again。 and then it's going to sort of plateau and then it's going to drop again and And then we're just going to end up at someplace whenever all the epochs are done So we iterate through epochs Now this is。

If I look at this， actually， this finishes here。So inside of a single epoch。

 this is where most of the work is done， right， We just do like free hidden an output。

 So most of the work is actually done in the epoch loop inside of here， we do total loss。

 which we initialize to 0。 The number of correct answers。 So we also set that to0。

 This is just for tracking the accuracy。 So we can see the loss dropping versus what the percent accuracy is over the over the over the the training samples。

 right， a training step， we can see which or every sorry， every。Every thousand00。

 every 1000 or every 100 training steps， we can see what the accuracy is over the batches。

Then inside of here， we iterate over numb batches， increasing by。By this each time， right？Batch。

 batch plus plus。And then。We do start I X。 It's going to be batch batch times batch size。

We do our forward so we get essentially inside of here， we pass in our neural net。

We pass an out like our neural netstruct pointer。嗯。An input。 So that's going to be train。

 and it's going to be the， the start I D X。So whichever this is， whichever actual batch it is。

Times the。Times the batch size。 So it's going to skip in increments of batch size rates。

 It's going to。It's going to。 And instead of skipping， like。

 this isn't going to actually like plus equals。B itself， this is going to add one each time。

 So this is just going to act as like an increment。 So we're jumping right。

 that's what that's what that's doing is it's going to jump for at a time instead of just one where it's just plus plus。

And then。We pass in the hidden layer。We pass in the output and then the batch size as well。 right。

 So all of the inputs hidden output size， right。And this is just going to do our forward pass all the way from。

 you know， taking this flattened image， which we've done already。

 I'm just because it's just laid out in binary area。 It just like exists as that。

 You can reformat it and interpret it as whatever you want。 But in see in memory。

 it's actually laid out as literally。1 through zero， you know zero through 784 or whatever。

 So it's like not that hard to actually like mess around with。We do the forward pass。

We calculate our cross entropy loss。Right。Using the same cross entrytropy loss idea that we did in the C friendly script。

 So we're just porting that over to C。Which if there's like an， if， if this doesn't like make sense。

 then you can actually go in and you can see， O， well， what are we doing here versus here， right。

 You have It was like language models in and the Internet。

 which you can investigate these things through。 And you can kind of see what's happening。Um。Yeah。

 so we calculate our loss。We add。We add the， we add that loss， the total loss。

 So inside of that actual epoch， we see， okay， well， what was the what was the average loss， right？

You know， in here， we do total lost fight to buy， you know， numb batches。 So we kind of。

 we kind of average that out。嗯。We do that every single epoch and inside of here。

We simply just this just acts as little incrementer for the correct counter。

 So this is just going to see， okay， well， will we close or not。So。

This should be self eplanatory this is also just like not necessarily part of the training run。

 but just like an extra feature that you can use to print out what the accuracy was over time。

 not the loss， but the actual percent accuracy。The backward function。 So this takes in， you know。

 N N。 and it takes a pointer to， to the input。 right。

 So this this is the memory address to this at this index， which is going to be。

Starting index times input size， right， And then inside of here， we pass in a few things。

 meaning hidden， you know。This neural net is going to contain all of our。

 all of our weights and stuff。 So don't this is like all contained within that。 the input itself。嗯。

Hidden output labels and batch size。 So very similar structure to the forward pass。

 except we also include we also include labels， right。Update weights。

 Everything is now updated after that。 And then we can print out some useful stuff， okay。

And that's pretty much all that happens in this train loop。

 A lot of it is just like printing and keeping track of stuff。But yeah。Going up。

If we actually look at our， if we actually look at our。Let me jump up to the forward path。

 where did this go？Okay awesome， so inside the forward it's very simple， right， one， two， three。

 four， five，6。Not too bad。Now， inside of here， I added the extra softm just because I didn't want to be redundant and included in the whole like training loop thing。

 There was a lot happening in there。 It was quite， complicated to sort through everything。

But yeah it's really helpful when you break things up in a smaller chunk。 This is super manageable。

 I wanted to make the forward and backward pass as modular as possible so that you guys could like really perform and optimize it if you wanted to like on the side。

 But this is like literally identical to what we did or almost identical to what we did in the C friendly function or the C friendly script right。

 So in there we had this like linear forward method， which would do the mapmo and the bias。

And then the linear backward， which would do two mapmals and a bias backward。But in this one。

 we kind of just split it into easier， more manageable chunks。 So a map more specifically。

Is like an operation that you can optimize on its own。

 And so like optimizing a linear forward or even more generally linear backward。

 it's like kind of hard to do that。 right， You have multiple things in there。

 you have to like fuse kernels together。 It's more complicated。 So I decided to keep this like as。

 as manageable as possible。 super hackable， you know， modular。But。In the mapmal， the A B。U。Yeah。

 that this is。This is literally the same as sea friendly。 So if I pop this over here。嗯。Actually。

 maybe I'll bring it actually downward。But。In here。Linear forward， right？ We just do x times W。

 This is x times W。 We're not We're x times W， A And B， same thing。 We're not transposing anything。

And inside of there。 mean， I already went over this function。 But， you kind of get the idea。

 We just do a map between and B。 that goes。嗯。We do a bias， bias forward。So that's also going to。

 we pop over to there。Yeah， I already reviewed that， too。 I need to go over that again。Ralue forward。

 it's just going to apply that teach element， very simple。Mapmal A and B。 so same thing again。

 except it's the hidden。s it's actually the hidden to output instead of the output to hidden。

 So next one。And then we do the bias forward again。 and then softmax， right， So obviously。

 like this is very， very simple to follow。 It's more like more of the complexity happens within the actual function。

 So like， this is a lot more to handle than the。😊，Then just the forward pass function clause itself。

 right？So I exc that。And then。And then go down to。Say the backward function， which is a little worse。

Be honest， do it down here backward function inside of here。We're going to0 gra everything。

 So what this means is previously。Our gradients were accumulating items， right， So our grad。

 our grad bias and our grad weights are actually accumulating stuff， so。

We want to just zero those out。 right， This is the equivalent of0 grad and pie torch when we go here。

We do optimizer dot step。 So that's like the actual update weights。 So you， you know， do the forward。

 and then you calculate the loss， and then you do backward。

 and then you update the weights with gradient descent and then use0 grads。

 So you're just zeroing out every single gradient。In the entire network。

 and then you're going to recalculate those when you do the next optimizer dot step， right， or sorry。

 no， lost off backward rather。When you calculate the gradients again。

 they're not going to accumulate further， they're just going to set them initially。

 and then you're going to update based on this gradient and then initial and then put them down to zero again。

嗯。So that that's all we do here。 We zero gra， and there's actually a function for this。 So mem set。

 literally just a C function。嗯。Se set N bytes of S to C。 So set N。Set， set。So bytes of S。

 which is the first one， so grad。And then C is the value we want to set it to。 So 0， and then the N。

 the length of it。Is just the size of grad， right？ So size is the number of numbers。

 And then a float is like the number of bytes， essentially。

 So the number of bytes that a grad occupies in memory。

 we're going to start from the beginning of that。 and we're going to initialize all of those values at at those sequential memory addresses。

 We're going to set those to 0。That's what zero grad does on a very low level。嗯。

So we do that with our weights and our biases。Now we do a gra output。 This is just going mallick。

Batge size times output size。 So B times 10， right， B by 10。 the compute output gradients。

 So we go to this。 Sure all this is doing is it's taking this gra output。

 which we initialize everything is like 0。 And we have this output， which is the which remember。

 from the board pass， is the output of the softm， which is actually a probability distribution。

 It is not logits。 Its not before the exponentiation。

 It is actually a probability distribution with each value between 0 and 1。Then we have the labels。

 and literally all we do here is we just element wise。 we set the grad output to actual output value。

 So which which which floating point number is it right。

 and then we subtract one based on the actual label of it。 So notice how before in C friendly。

 We we didgrad output equals softmax problems minus y true we're doing the same thing here。

 except we can't just do a simple nupy element wise operations， we can't just be dumb and say this。

 right we have to actually we have to be explicit and we can be a little clever by just doing the minus equals one。

There。So。That's it's literally doing the same thing， we're just using a different trick。

What we just continue going through， we just did compute output gradients。

 Now we now we can actually use those gradients and start using like matrix multiple highs and bias backwards and value backwards and all this stuff。

 right， So the first one here is Mattmole， we go through we we calculate w2 dot grad。

 Now W2 do grad is right here。 So x2 dot T times the derivative of the loss， which is grad output。

So here we do hidden， which is x2 here in this case。嗯。Oh， sorry。Yeah， x 2。 So the。Essentially， the。

The input going into that。嗯。And then times， So this is times B right， So B is in this case。

 is the grad output。So we're transposing this with this A here and then times this。

 and then that's going to equal c or the gra weights2 right gras。W2， right？嗯。Yeah。

 so that should be fairly intuitive。Now we go further， we go to bias backward。

B backward isn't actually too bad。 So bias backward。

Is literally just going to we're going to iterate through the size。 I mean， keep in mind。

 we have batch size， right。 So we're going to iterate through the entire size of it。You know。

 iterating at incrementing IH time。We're going to store a bias value。

 a biased gradient at this index。As 0。And we're going to iterate through the entire batch size。

And we're literally just going to set that specific value。

We're going to iterate remember we're iterating through the entire batch size。

 So what we were doing before。 how we were like sming the numbers。We're going to go through that。

 and we're going to just。嗯。Essentially， do B times size。So the entire the entire length of that。

The entire length of， of like， of like a row。And then， plus， I。

And we're just going to set because this is going to increase each time。

 So we're essentially just going down one one row at a time right and we're smushing it together because we're plus equal accumulating that value here。

So our grad biases the， this is the equivalent of N dot sum across axis is 0， keeping dim true。

 right。And then we go back to。Preet。We pop back to the backward function。 A。

 So now we get bias backward。 We pass in the grad bias。 right。

 So we're calculating the the gradient bias。 we pass in the grad。😊。

So that would in this case would be the grad output and then batch size and size， right so。

That should be fairly intuitive。 It's just the gradients are directly flowing。

 And we just do an accumulate operation across the batch because we want to generalize over a batch。

 right？ It's more useful to do that。And then we just do since we're done the W2。

 now we actually move on to the Dx2 right， so dx2 is right here。We mall this because remember。

 this is just temporary。 don't we don't actually need to store this。

 This doesn't need to be updated anywhere。 We're just calculating this because it's a prerequisite for calculating W1 so we need we can free it after we don't need to store this in memory should be like efficient and inside of here。

 We literally just go grab output times W2 transpose， right。

So we go grid output a times W2 transpose T， and we store that in dx2， right？Going down further。

 D re out， which is。This part here， Dre out is dx2 times dre of x。We allocate memory for this。

We go through go through the entire batch。 we literally do Dx2 so。D x2 times D value。嗯。

Dre of whatever of whatever that value is just just going through it， right。

And this is going to be if this is going to evaluate to a true。Or essentially a one if this if this。

 if this value is。Essentially this is rarely derivative， right。Rely derivative， that's all this is。

We might not actually even need the value derivative backwards of and this whole thing。

 but we're going to keep it anyways， this this does work though。So this stores the deel out。

 That's what we want。 right， dealer Del know is's good。Then we update using the using the。

What's it called。 We calculate Dreot from D X2， which we， which we used up here。 right。

 we stored that。 stored the for that。 the temporary gradient there。 we don't need it for later。

 You just need it for now。 calculateulate Dreot based on that。 Then we use Dreot D。

De youvalue out later。And we essentially go to calculate W 1。We go x1 dot T times D value out， right。

 So transpose， So A T underscore B， that's what this is going to be。8ight underscore4 B。We go input。

 so。Input x1 transpose that times devalue out and store that in way it's 1。Awesome。😊。

Bs backward as as per usual。 So we just have the the bias itself。嗯。And then。The。

 the one that it's flowing， flowing from， right， So whatever it's， whatever the。

Whatever the previous layer gradient was， that's just going to flow directly into bias right。

 because you know， adding adding does not change the gradient of something。

 It just changes the like position， the offset of it， but the slope remains the same。But yeah。

 that's literally the backward path。Not too bad。 That might have been a like a little hard to keep up with。

 My might D reue outs constantly， might have could abuse you。But yeah， that's pretty much it。

And then inside of， yeah， so that's backward。And then。After backward， after this。

 we do update weights， then we print some stuff out。

 So let's just pay attention to update weights here。 Don't don't worry about the rest of this。

 you can impartse this on your own， but we really care about is the actual learning mechanics of it。

 right You can print anything out any day you want。 It's very easy。

 but we care about what the actual mechanism is here。So if I got update weights。

We pass in the neural net struct， right the pointer to that。We access we go through each one in here。

And we literally just， we just do the same thing。 So hidden size kind of input size。

 that's going to be， you know，7，84 by 256。 That's the weight one。We。We iterate through each index。

 Remember， this is laid out sequentially in memory。

 So this is going to evaluate to whatever 784 by 256 is。 that's a large value。

 It's just going to iterate through that memory。 It's going to go through the lines or the straight thing and it's just going to do the learning rate。

 times whatever the grad was。 and then it's going to minus equals accumulate that into weights 1。

 It's going to do the same thing for weights 2。 remember weights 2 is output size times hidden size。

 So hidden size 256， output size is 10。Bs in size。That's two of its size。Very straightforward。

And that's pretty much it。嗯。Let's go ahead and train this thing。So going back up。

 let me just make sure these are all set correctly。是。We'll do to this extra。We'll do batch size of 4。

 That's fine。 Learning rate 0。0，01。 That's okay。ll as well。 We'll set the box to 5。

To be less redundant。All said to， like percent to3， Why not。So now we go into here Gcc O V1。

 and then V1。 C， which is the file I compile and we do LM for link math right。

 So inside of here we do the math outage file， we need to link math for this to work。If we don't。

Right in unidentified reference to this， these are all the math functions right。

 but if we do the problem。It'll work。 You can go and run this。 So we get the first。

 this is a five printed out。 first trend training labels is  five， as we see here， and then 0，4，1，9。

2，1，3，1，4。And we can see the accuracy starts off at about well the loss is about 2。3， which is。

Random as we'd expect it to。 So 2。3 evaluates to about 10 per cent accuracy。

 And we can see that they're the first epoch dose there 2500 enters。And we can see that the accuracy。

goeses up to about 60%， which is solid， right losses going down。And then in the next one it sees。

 oh my gosh， wait， we've seen these samples before， and it's going to drop even further。

 it's going to go down to 0。88 and accuracy is going to fly up， you know。

 15% because it's already seen these samples before。And then it's going to do that again。

 we go up to 86%。And we end up with about 88。6% here。And。Yeah， I mean。

 you could always print out the。The ending samples， if you really wanted to。嗯。

You could always print out like some extra samples and just like how it matches those up。

But we're going to notice that in our coudaophil。Anyways， that that was a lot to unpack there。

 But that is the C file。 That's how we transfer from Nie to C。

 It's not actually that crazy of a jump。 It's mainly just writing the algorithm。 You know。

 the hard way。 and just kind of being more aware about things， right。

 It's very easy to run into issues。 But as long as we're careful about things。

 it shouldn't be too bad。 Let's go and jump into couta now。 Okay okay， everyone。

 So this is one of the last parts of the course， actually， And this is part。

 this part is a tenant to be is intended to be a little shorter。

 So this is designed to give you of sort of a template for continuing on。 This is the final project。

 right， So I'm not going to give you all the answers right away。

 A part of your job is to figure this out on your own and use what we've developed beforehand to continue and optimize performance further。

 right。😊，So。I have this。I have this naive GPU file right here。 or sorry folder inside of Kutuda。

 So we go to。We go to the Ka directory and then we see the into an IFGVU。And inside of here。

 you're going to find this file。 this view one， right， I just have this as like versions。

 So you can I'll like update more versions later on if something breaks in future coa releases or whatever。

 But yeah， so this is essentially just a direct port from our our C file so。Literally。

 all we do here is we， we load in the same things。We initialize weight's the same。

 All these are done on CPU as you can see， the only things that we actually change are the Ma kernels right so we can see the there's more than just Ma kernels。

 but you can see so we have this Ma A and B。 so this is this is not transposed。

And then this is B transposed and then this is a transposed right so when we're doing our backward pass and we need to transpose certain values。

 that's what we'll use that for right so we have certain kernels that dedicated for that and we can actually see based on the indexing schemeche in here like notice how we we iterate over n every single time。

Except this one。 This one is a little different。 This one is M， but。If we go in here， we can see a。

 this is just the normal one， right， So row times n。Plus， I。And then if we go to this one， B。

 it's I times K plus column， right， And this is different。 So notice how this a stays the same。

 But because we're changing B and making it transposedse， this part， this indexing changes， right。

And then same idea here。Is。Oh。We just transpose a。 So this part， I K， and then column， I K。

 and then column and。This part is going to be different， right， so instead of row and I。

 it's I N row。And。Yeah， that's。Those are pretty much the major changes。

 The reason why we do this for。We do this for a is because a is transposedse。

And and the M is M is a little different。 but these are these are naive kernels。

 I expect you be able to dissect these， but if we continue further， we have the re。 We have our bias。

 We have a softmax kernel。 So this is going to do a single softmax output。

 So a distribution for every single batch element。 So it's going to go vertically downwards。

 each thread is going to do a row。We zero our gradients with the simple kernels。

 which's just's going to go through every single value and just set that to zero。

Probably faster than meet。 I'm not sure， but。And then we have our Dvalue kernel。

 So this is just a derivativeitive value。Multiply gradients。So。

Elment wise multiplication of gradients， which we can see is used。Down here in multiply gradients。

And this function。Is used is used right here。 So when we're doing our when we're doing our value。

 when we're we're doing our actual。We're going through。Dre， and we need to multiply those values。

 It kind of makes sense why we would put that there。嗯。Going back up。We just have our forward。

 So the typical a times B。 I don't know why this is。八？嗯。Bim is not working。 All right。

And we just do a matimel， add the bias， re， Maimel， add a bias， and then softm， right， very simple。

 Cross entropy loss is going to be done on the host。

We're going to computer output gradients on the GP because there there is actually going to be a lot of。

 you have to consider when you're actually writing kernels。

 you're like what what is the how useful is it right to actually go and write your own。

You to go and write your own。 So like， for example， this one。

 we could probably turn this into CPU and it might be faster。

 But who knows kind of the idea here is like if you have a big one。

 if you have a big update to do like update to gradients and you have these big giant you have these giant W matrices that you're trying to change and modify then having a thread to do each little to do each little like pointwise update will help speed that up。

 But if you're doing just like a B by 10 for example， which is what this is。

 you could probably get away with just doing this really fast on CPU and you'd be you'd be fine because there is like kernel launch overhead when you have to like literally launch this。

 it has to tell the GP what to do。 and then it has to trigger a bunch of threads to go and execute that right。

And then in our backward pass， we zero out the gradients to make sure that they're not accumulating and giving us。

 know mixed signals。We have our compute compute output gradient。

 So that's going to be the essentially the output probabilities minus the true labels， right。

And then we have our。At a transpose times B。 So we go back to here。嗯。This is Dw2。Right。We update。

 we update gradients for bias2 So there's specific kernel for that。

 Now remember when we're launching these there's it seems like there's a lot to sort through。

 but really all this is is looking at that previous technique we did where it's like you have to launch say if you have 1025 elements and you would normally only do like 1024 threads right So what you do is you add on an additional block with with a single with a single thread inside of it or just or another block in general you could say。

And since you have those bounds， those like that little if statement that checks if everything is is where it it's not like out of the out of the matrices that you're working with。

 like out outer outside of that memory。 Then you can that that's essentially what this is， right。

 So we're just being careful about how we launch this stuff。And yeah， this， this goes back to the。

 you know， Cha number5 on on kernels， right？ So these launch configurations can like。

 really mess you up and make things look more complicated than they are。

 But if you can just like look through this one bit at a time， you have the。

You have like the grid size and sorry， the grid dim and the block dim right， and。

 and that's all you're really working with。And then， of course， the。

 the arguments for the kernel launch itself。More mammals， right， going back to here。This times。

 so it's a times B transpose。8 times is B transpose。And then inside here， we just do our。

 we just go backward through our value function。 All of this is like very close to our C files。

 It's just like it's just run parallel， right。U。Sim my dear here。

I'm just going to go further downwards， updating our weights。 You know， it's kind of。嗯。

I guess I have two of these。Are we using this。You see。😔，Yes， we are。 We are using that one。

But this one。Update gradients。Yeah， that's also okay。 So so these are different things， right， Yeah。

 so the the update gradients， that's for the bias and the update weights that is for that that is actually where gradientcent itself takes place。

To。And then inside this loop。We go through initializing our device training sets。

 So when you have this D prefix， remember that's for device。You know。

 why is labels train is the train set？We could a all of those。

 We men copy them over to device because they're initialized as pointers on the host。

 and we have to copy those over with respect to their memory addresses over to device。嗯。

And then aside here， we just iterate over all the epochs we need to do。

 which in this case is defined at the top and then number of batches， right？

And then we we set a starting index。 we make sure to like stride a little bit。

 So we have whichever batch we're at here。 it's a number of batches in the total thing which we actually calculate by doing train size number no divide by batch size。

 So if you have a 10000 training examples and a batch size of four you're going to have 2500 batches right And so when you do whichever batch you're at which is going to go through know it's going essentially going to go03。

嗯。0，3。7。11。It's going to skip by four， right？We do our forward pass， so keeping this simple。

 this nice little concise and instruct right with all of our gradients and and our weights， right？

We calculate the。We count essentially what this part is doing。Is。We're calculating the loss。

We're adding it to the total running loss of。Where is it。On this level， we have。

 we initialized a total loss inside of the epoch loop。 right。 So this is for the entire epoch。

 That's why we're， that's what we're kind of doing there。 is when we add the loss。

 we're just like appending it。 And then we're， you know， dividing it accordingly。

 So we're just taking like the average loss over the entire epoch。嗯m。In this case。

 we are essentially just like we were doing in the C file or just。Adding to the correct counter。

 So however many samples we got correct， that's the percent accuracy。Go into backward Pass。

I already walked through this I mean， you can kind of sort through all these different arguments。

We update， we do an update weights for each of our individual weight matrices。

 so it's just going to essentially element wise。啊。It's going to element wise multiply the gradient times the learning rate。

 And it's going to accumulate that into the weight， right on device。

And then in here we just print some useful stuff， right？Go down here。

 make sure that we free the training sets， the hidden。And the D output that we initialifies before。嗯。

And we have our initialization of the entire neural net， so just essentially doing our Malic。

Initializing those， so each of these are going to be set to like random values or in this case。

 biases are going to be set to zero。And then we do our kudamalic。 So so we allocate on on CPU。

 we initialize everything on CPU， We allocate on device， we move everything to device。

 and then we're ready to run right And then in this case。All we would do is。

Initialize this neural net。We。We initialize it with， with， with random data， with random data values。

呃。Then we load in our entire training set into the host memory。We go and train everything。

 and when we're done， we can free whatever we need to on CPU and free whatever we need to on device。

So if I go ahead and give this a run here。Be one。I'm not going to run with good boss。

So variable I was used member reference。 Don't worry about that。 So warning。

 And then we go and run this， we can see。嗯。This trains insanely fast。We go from epoch 1。

 We have three epochs in here total， each one doing 2500 inters， and we get a loss of about 2。3。

 which is， as we'd expect。 And then we see the accuracy increase up to 60%。

 and then it gets even into it jumps， right， It goes up to。

Goes up to about 87% and then jumps even higher， and we end up at around 90%， right？

So that's pretty good。 And we can， we can actually run this with bigger hyper parameters so I can go ahead and。

I'm click in 1024 there。And use a bigger batch size， maybe like maybe 8。 and then epoch is 5。

We pop them here， compile that。 We go and run it。You can see。That。um。

You get a lot better accuracy right so even up to 92% now So it's kind of what this part is is it's called gring。

 So you get the first part where it where it's like just starting on its training steps and it's sort of figuring out which weights to push in the right direction and and then it figures that out and then it plummets the loss drops like really fast。

 which is what we're seeing right here with the loss is like 2。3 and then it's 1。72 and then  boom。

5 and all the way down to like 2。90。3 ish。And then what's happening here is it now it now can no longer use the easy patterns that it recognized。

 and now it has to search from from more difficult attributes。

 There might be certain images that it has a really hard time recognizing。And it has to。

 and it has to， you know， learn additional stuff， which takes more training steps to do in that process of deeply understanding the data set or or generalizing over it。

 that's called gring， right。嗯。Hence the Gck language model I was using before。But yeah so。

If we step out of this and go over to go over to this this room file。

 I named it B because it's supposed to be fast and it's the one that you're supposed to edit later。

Go to room。And I was doing some comparisons here。 but let remove those compare。And compare。

And we have this other comparing file， which was experimental， but I'll probably remove that soon。

And then we go into this other one， B1 dot C inside of the room file。 and this one。

Is pretty close to what we had before。 Now， the only thing we actually change here is instead of having we actually make this easier for you。

 So in the past one， we kind of simplified it and had all of the and had and did like the mammals a bit differently where we transposed inside of the kernel。

 But in this example， we want to make it easier for you to just plug your own code into here and have it work。

So using like the SGM， the SGM Kuda optimizations we did before in the faster Maal chapter。

 like that's what you would plug into here right or you'd have your own kernel and you would launch it from here。

嗯。And then， inside of。嗯。And then inside of， I go down。We can see a transpose kernel up there。

 But if we go into backward passs， there's nothing modified in the forward because there's no transposing there。

 but in the backward paths， we can see。That there is just transpose matrix function rate， transpose。

 transpose， transpose， because we have to do this three times。 we have to calculate this one。

 this one and this one， there's no D X 1， right， we don't have to。

 that's redundant because we don't have a layer before it。 So we do3，3 of those。

3 transpoposed mammal operations。And so in here， this literally just switches it from。

Colum major to major。Oh that。It's just a qui little trick。

 There is a custom kernel for it that you can review if you want to。We where it go。Right here。

So there's just transpose matrix function that we call we pass in these device inputs into it。

 and then inside of here we actually do the transpose launch and we make sure that no errors happen and we synchronize all of the threads on the GPU right？

This this is where the actual transposing happens， which isn't too conceptually bad。Don't。

 don't worry about this too much。 It's more so worrying about how do you speed this thing up。

So I can go ahead and run this actually and。Like all we change here is literally the just the。

 just the transpose。I had some cool law stuff at the top of me。Remove that。Good loss。

I'll just add that in temporarilyor。那为什来啊。I was messing around with coos like this is a totally experimental file。

 so don't like I'm just kind of like screwing around with this one。

But we could just do link could loss。本案。And go and run this。 And can see it。 sit's also pretty quick。

 too。Yeah， so it trains it trains the same on2 on hidden size 256。

 which is what we have or this is 1024 actually so 1024， you know we give it a batch size of 8。

 only three epochs to learn though it takes， you know， it gets up to about 90% accuracy。

 which is still good。But yeah on a reduced on a reduced on a reduced number of training samples。

 So we do batch size 8 instead of4。 So it gets， it gets more like it gets twice the amount of generalization because it has double the batch size。

 but the amount of training samples is cut in half right？ So it's actually like not that bad。

 When you think about it。 So we could like bump the epox number up to 6。

And you would see how much of it。And much of a difference that actually makes。

So we can see that it's kind of going up to 92， which is， you know， this last phase here was。

 it was rocking of what it was doing there。 but yeah， so we got up to about 92%。

Close to 9093 in some cases， but yeah， that's decent that's you know。

 I know most humans are better than that， but for 10 seconds of training， I think that's pretty good。

For having no knowledge about the world at all， this neural network did fine。Now， over time。

 I am going to add optimizations to this。 But since you' are watching this right now。

 this does not exist in the current repo。The version of this course you're watching right now。

 whether that be five years when it was posted， whether that be two months， one day。

This is the current version that you're seeing right now and。

This might be different by the time I've updated the Gitthub repo in the future。

 I do plan to maintain this and add in you know additional like maybe a V2 with like you know I'll make sure to name everything of course。

 but just to just to go in and like add some extra features， for example。

 like I might I might add in like a really fast like custom row major kernel where we do like tensor core operations So the warp。

The Warped matrix can multiply accumulate the WMMA with TF32 precision。 that stuff is really fast。

And then as well， another optimization you could take over is using kutuda streams。

 So remember in the concurrency chapter and I like no， in in chapter number five。

 where we went know more deeper into kernels and the whole kuta architecture。

You can use streams to make things run concurrently， right。

 So you could be loading in some data and then， you know， doing， say， like a forward。

 you could do like a forward and。A forward and a backward pass。 And then while that's happening。

 you could be loading in the next piece of data， right， So I mean， obviously。

 this is just like a digit classification and you're not going to be super performance limited here。

 There's not a need for like having super， super high throughput because you can。

 you can get this thing up to like 99% accuracy you if you make， you know。

 deeper layers and you increase head in size and adjust all these things。

It's pretty easy to get this thing to perform well。

 but this is the type of thing you want to practice so that when you write more complex kernels。

 it's not as difficult to start with。So， you know， there are lots of optimizations you can do。

 You can add in in this。Where is it。In this matrix multiply kernel， in here。

You can switch this out with stuff。 I'm not going to switch it out right now， because。

That's something that you kind of want to do as a part of the final project。

 something you want to do self guided and sort of go into it on your own。 So， I mean。

 you can use this as is。 But if you want to have some fun， this is just simple mammal curl here。

 There's no transposing or anything。 This is row major， and you can have fun with it。So。

 that's that feel free to change this kernel， maybe experiment with Tensor core operations。

 WMMA stuff。And then， you know， couda streamams or something like that。

 feel free to use the NCU profiler and yeah。Hopefully。

 this gave you a better insight on how to kind of build up projects and how and how while they that might look complex on the outside。

 you can sort of dig in and figure out what's going on。Now just really quick to run all these again。

 just so everything is crystal clear that these are performing the same。

 We'll go ahead and edit each of them back to， you know。56， so。There26 there。Epos。Like three。

 we'll do batch signs4 learning rate is one times 10 of the negative three。And then in here。

 we'll do 256 as well。Bash size will load that down lower that down before。Inside of our CPU。We will。

ITur this up to to 50。56， bapt sizes 4， Epoch 3。 That's good。Then we pop into our Python here。

Set the torch reference script to。This is 256 already。1 times0 of the negative3， batch size4。

 we're looking good。Then we go to the sea friendly script。S a little too far。26， good batch has4。

 awesome。So， now。Now we run to Python， over run Python。Forourth reference。Give this a second。

 The data loading takes a little while on Python。It's not the most optimized thing ever。诶。Awesome。

 so we end up with about 90%，90% accuracy in the end。89。Here we have。87， in this case。

 we end up with about 90 in the end。Let's memorize that number 90。

And then we go to Python C friendly。And we get。87 per cent。89%。About 90%。 I had。

 I had 50 box in there。Yeah。Net about 9090% as well，91%。And then we navigate over to。The speedient。

 I seat you。You got GccC compiled with math。We'll go and run this。In the。

That's as soon as going to take a second。Yeah。It's not used to going this fast。

 I know Nmpy probably has more specialized mammal routines。 So a lot of this is just。呃。Or sorry。Yeah。

 yeah， nuumppy it probably has more specialized routines here。

 so just doing it in raw sea like naively is going to take a while。嗯。Yeah， so we can see this。

We end up。Add about。Give it a second。Pretty close to 90% as well。 So 88。5 slightly worse。 but that's。

 that's almost negligible。Now。We have to see the intoa。Slash， I to you。

And then we'll do NVCC and compile without good loss。On that。Look off much faster that is， right。

New total of three epochs when we end up with boom 90%。 Oh， how convenient is that， okay？

And then we'll head out， and we'll go to the。The ring about room bird。And。

Pile with coupon I just added the Kubos thing because you can add your own Kubos Sjam or like the LT matmen and just play with that。

You run this about the same speed and we end up with about 90% as well。

 So everything's got about 90%， which is good。 shows results are kind of consistent just to like make sure that's hopefully cleared up。



![](img/ae3ba39c4a447415d3fed36690a00a69_11.png)