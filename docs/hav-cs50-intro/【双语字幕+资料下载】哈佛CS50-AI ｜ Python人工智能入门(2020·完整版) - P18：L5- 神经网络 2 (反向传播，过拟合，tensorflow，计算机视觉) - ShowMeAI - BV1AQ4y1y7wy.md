# 【双语字幕+资料下载】哈佛CS50-AI ｜ Python人工智能入门(2020·完整版) - P18：L5- 神经网络 2 (反向传播，过拟合，tensorflow，计算机视觉) - ShowMeAI - BV1AQ4y1y7wy

actually be and so the strategy people，came up with was to say that if you know。

it what the error or the loss ism on the，output node will then based on what。

these weights are if one of these，weights is higher than another you can。

calculate an estimate for how much the，error from this node was due to this。

part of the hidden node or this part of，the hidden layer or this part of the。

hidden layer based on the values of，these weights in effect saying that。

based on the error from the output I can，back propagate the error and figure out。

an estimate for what the error is for，each of these nodes in the hidden layer。

as well and there's some more calculus，here that we won't get into the details。

of them but the idea of this algorithm，is known as back propagation it's an。

algorithm for training a neural network，with multiple different hidden layers。

and the idea for this the pseudocode for，it will again be if we want to run。

gradient descent with backpropagation，we'll start with a random choice of。

weights as we did before and now we'll，go ahead and repeat the training process。

again and again but what we're going to，do each time is now we're going to。

calculate the error for the output layer，first we know the output and what it。

should be and we know what we calculated，so we can figure out what the error。

there is but then we're going to repeat，for every layer starting with the output。

layer moving back into the hidden layer，then the hidden layer before that if。

there are multiple hidden layers going，back all the way to the very first。

hidden layer assuming they're multiple，we're going to propagate the error back。

one layer whatever the error was from，the output figure out what the error。

should be a layer before that based on，what the values of those weights are and。

then we can update those weights so，graphically the way you might think。

about this is that we first start with，the output we know what the output。

should be we know what output we，calculated and based on that we can。

figure out alright how do we need to，update those weights back propagating。

the error to these nodes and using that，we can figure out how we should update。

these weights and you might imagine if，there are multiple layers we could。

repeat this process again and again to，begin to figure out how all of these。

weights should be updated in this back，propagation algorithm is really the key。

algorithm that makes a neural networks，possible it makes it possible to take。

these multi-level structures and be able，to train those structures depending on。

what the values of these weights are in，order to figure out how it is that we。

should go about updating those weights，in order to create some function that is。

able to minimize the total amount of，loss to figure out some good setting of。

the weights that will take the inputs，and translate it into the output that we。

expect and this works as we said not，just for a single hidden layer you can。

imagine multiple hidden layers where，each hidden layer we just define however。

many nodes we want where each of the，nodes in one layer we can connect to the。

nodes in the next layer defining more，and more complex networks that are able。

to model more and more complex types of，functions and so this type of network is。

what we might call a deep neural network，part of a larger family of deep learning。

algorithms if you've ever heard that，term and all deep learning is about is。

it's using multiple layers to，be able to predict and be able to model。

higher-level features inside of the，input to be able to figure out what the。

output should be and so with deep neural，network is just a neural network that。

does multiple of these hidden layers，where we start at the input calculate。

values for this layer then this layer，then this layer and then ultimately get。

an output and this allows us to be able，to model more and more sophisticated。

types of functions that each of these，layers can calculate something a little。

bit different and we can combine that，information to figure out what the。

output should be of course as with any，situation of machine learning as we。

begin to make our models more and more，complex to model more and more complex。

functions and the risk we run is，something like overfitting and we talked。

about overfitting last time in the，context of overfitting based on when we。

were training our models to be able to，learn some sort of decision boundary。

where overfitting happens when we fit，too closely to the training data and as。

a result we don't generalize well to，other situations as well and one of the。

risks we run with a far more complex，neural network that has many many。

different nodes is that we might over，fit based on the input data we might。

grow over reliant on certain nodes to，calculate things just purely based on。

the input data that doesn't allow us to，generalize very well to the output and。

there are a number of strategies for，dealing with overfitting but one of the。

most popular in the context of neural，networks is a technique known as dropout。

and what dropout does is it when we're，training the neural network what we'll。

do and dropout is temporarily remove，units temporarily remove these。

artificial neurons from our network but，chosen at random and the goal here is to。

prevent over reliance on certain units，that what generally happens in。

overfitting is that we begin to over，rely on certain units inside the neural。

network to be able to tell us how to，interpret the input data。

what dropout we'll do is randomly remove，some of these units in order to reduce。

the chance that we over rely on certain，units to make our neural network more。

robust to be able to handle the，situations even when we just drop out。

particular neurons entirely so the way，that might work is we have a network。

like this and as we're training it when，we go about trying to update the weights。

the first time we'll just randomly pick，some percentage of the nodes to drop out。

of the network it's as if those nodes，weights are so，ciated with those nodes aren't there at。

all and will train in this way then the，next time we update the weights we'll。

pick a different set and just go ahead，and train that way and then again。

randomly choose and train with other，nodes that have been dropped out as well。

and the goal of that is that after the，training process if you train by。

dropping out random nodes inside of the，scenario Network you hopefully end up。

with the network it's a little bit more，robust it doesn't rely too heavily on。

any one particular node but more，generally learns how to approximate a。

function in general so that then is a，look at some of these techniques that we。

can use in order to implement a neural，network to get at the idea of taking。

this input passing it through these，various different layers in order to。

produce some sort of output and what，we'd like to do now is take those ideas。

and put them into code and to do that，there are a number of different machine。

learning libraries neural network，libraries that we can use that allow us，to get access to someone's。

implementation of backpropagation and，all of these hidden layers and one of。

the most popular developed by google is，known as tensorflow a library that we。

can use for quickly creating neural，networks and modeling them and running。

them on some sample data to see what the。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_1.png)

output is going to be and before we，actually start writing code we'll go。

ahead and take a look at tensor flows，playground which will be an opportunity。

for us just to play around with this，idea of neural networks and different。

layers just to get a sense for what it，is that we can do by taking advantage of。

neural networks so let's go ahead and go，into tensor flows playground which you。

can go to by visiting that URL from，before and what we're going to do now is。

we're going to try and learn the。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_3.png)

decision boundary for this particular，output I want to learn to separate the。



![](img/0b60cfa2ad22087bb0426f088d1cbfc6_5.png)

orange points from the blue points and，I'd like to learn some sort of setting。

of weights inside of a neural network，that will be able to separate those from。

each other the features we have access，to our input data are the x value and。

the y value so the two values along each，of the two axes and and what I'll do now。

is I can set particular parameters like，what activation function I would like to。

use them and I'll just go ahead and，press play and see what happens and what。

happens here is that you'll see that，just by using these two input features。

the x value and the y value with no，hidden layers just take the input x and。

y values them and figure out what the，decision boundary is，our neural network learns pretty quickly。

that in order to divide these two points，we should just use this line this line。

acts as a decision boundary that，separates this group of points from that。

group of points and it does it very well，you can see up here what the loss is the。

training loss is zero meaning we were，able to perfectly model separating these。

two points from each other inside of our，training data so this was a fairly。

simple case of trying to apply a neural，network because the data is very clean。

it's very nicely linearly separable we，could just draw a line that separates。

all of those points from each other，let's now consider a more complex case。

so I'll go ahead and pause the，simulation and we'll go ahead and look。

at this data set here this data set is a，little bit more complex now in this data。

set we still have blue and orange points，that we'd like to separate from each。

other but there's no single line that we，can draw that is going to be able to。

figure out how to separate the blue from，the orange because the blue is located。

in these two quadrants and the orange is，located here and here it's a more。

complex function to be able to learn so，let's see what happens if we just try。

and predict based on those inputs the x，and y coordinates what the output should。

be I'll press play and what you'll，notice is that we're not really able to。

draw much of a conclusion that we're not，able to very clean they see how we。

should divide the orange points from the，blue points and you don't see a very。

clean separation there so it seems like，we don't have enough of sophistication。

inside of our network to be able to，model something that is that complex we。

need a better model for the centeral，network and I'll do that by adding a。

hidden layer so now I have a hidden，layer that has two neurons inside of it。

so I have two inputs that then go to two，neurons inside of a hidden layer that。

then go to our output and now I'll press，play and what you'll notice here is that。

we're able to do slightly better we're，able to now say all right these points。

are definitely blue these points are，definitely orange we're still struggling。

a little bit with these points up here，though and what we can do is we can see。

for each of these hidden neurons what is，it exactly that these hidden neurons are。

doing each hidden neuron is learning its，own decision boundary and we can see。

what that boundary is this first neuron，is learning our，this line that seems to separate some of。

the blue points from the rest of the，points this other hidden neuron is。

learning another line that seems to be，separating the orange points in the。

lower right from the rest of the points，so that's why we're able to sort of。

figure out these two areas in the bottom，region but we're still not able to。

perfectly classify all of the points so，let's go ahead and add another neuron。

now we've got three neurons inside of，our hidden layer and see what we're able。

to learn now all right well now we seem，to be doing a better job by learning。

three different decision boundaries，which each of the three neurons inside。

of our hidden layer we're able to much，better figure out how to separate these。

blue points from the orange points and，you can see what each of these hidden。

neurons is learning each one is learning，a slightly different decision boundary。

and then we're combining those decision，boundaries together to figure out what。

the overall output should be I mean we，can try it one more time by adding a。

fourth neuron there and try learning，that and it seems like now we can do。

even better at trying to separate the，blue points from the orange points but。

we were only able to do this by adding a，hidden layer by adding some layer that。

is learning some other boundaries and，combining those boundaries to determine。

the output and the strength though the，size and thickness of these lines and。

indicate how high these weights are how，important each of these inputs ISM for。

making this sort of calculation and we，can do maybe one more simulation let's。

go ahead and try this on a data set that，looks like this go ahead and get rid of。

the hidden layer here now we're trying，to separate the blue points from the。

orange points where all the blue points，are located again inside of a circle。

effectively so we're not going to be，able to learn a line notice I press play。

and we're really not able to draw any，sort of classification at all because。

there is no line that cleanly separates，the blue points from the orange points。

so let's try to solve this by，introducing a hidden layer I'll go ahead。

and press play and all right with two，neurons and a hidden layer we're able to。

do a little better because we，effectively learn two different decision。

boundaries we learned this line here and，we learn this line on the right hand。

side and right now we're just saying all，right well if it's in between we'll call。

it blue and if it's outside we'll call，it or engine so not great but certainly。

better than before we're learning one，decision boundary and another。

and based on those we can figure out，what the output should be but let's now。

go ahead and add a third neuron and see，what happens now I go ahead and train it。

and now using three different decision，boundaries that are learned by each of。

these hidden neurons we're able to much。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_7.png)

more accurately model this distinction，between blue points and orange points。

we're able to figure out maybe with，these three decision boundaries。

combining them together you can imagine，figuring out what the output should be。

and how to make that sort of，classification and so the goal here is。

just to get a sense for having more，neurons in these hidden layers and。

allows us to learn more structure in the，data allows us to figure out what the。

relevant and important decision，boundaries are and then using this back。

propagation algorithm we're able to，figure out what the values of these。

weights should be in order to Train this，network to be able to classify one。

category of points away from another，category of points instead and this is。

ultimately what we're going to be trying，to do whenever we're training a neural。

network so let's go ahead and actually，see an example of this you'll recall。

from last time that we had this，banknotes file that included information。

about counterfeit banknotes as opposed，to authentic banknotes where I had like。

four different values for each banknote，and then a categorization of whether。

that banknote is considered to be，authentic or a counterfeit note and what。

I wanted to do was based on that input，information figure out some function。

that could calculate based on the input，information what category it belonged to。

and what I've written here in bank notes，top pipe is a neural network that will。

learn just that a network that learns，based on all of the input whether or not。

we should categorize a banknote as，authentic or as counterfeit the first。

step is the same as what we saw from，last time I'm really just reading the。

data in and getting it into an，appropriate format and so this is where。

more of the like writing Python code on，your own comes in in terms of。

manipulating the statum massaging the，data into a format that will be。

understood by a machine learning library，like scikit-learn or like tensorflow and。

so here I separate it into a training，and a testing set and now what I'm doing，network。

here I'm using TF which stands for，tensor flow up above I said import，tensor flow as tftf。

an abbreviation that will often use we，don't need to write out tensorflow every。

time we want to use anything inside of，the library I'm using TF dot Charis。

Charis is an API a set of functions that，we can use in order to manipulate neural。

networks inside of tensorflow，and it turns out there are other machine。

learning libraries that also use the，Charis api but here i'm saying alright。

go ahead and give me a model that is a，sequential model a sequential neural。

network meaning one layer after another，and now I'm going to add to that model。

what layers I want inside of my neural，network so here I'm saying model add go。

ahead and add a dense layer and when we，say a dense layer we mean a layer that。

is just each of the nodes inside of the，layer is going to be connected to each。

of the nodes from the previous layer so，we have a densely connected layer this。

layer is going to have eight units，inside of it so it's going to be a。

hidden layer inside of our neural，network with eight different units eight。

artificial neurons each of which might，learn something different and I just。

sort of chose eight arbitrarily you，could choose a different number of。

hidden layer hidden nodes inside of the，layer and if we as we saw before。

depending on the number of units there，are inside of your hidden layer more。

unit means you can learn more complex，functions so maybe you can more。

accurately model the training data but，it comes with the cost more units means。

more weights that you need to figure out，how to update so it might be more。

expensive to do that calculation and you，also run the risk of overfitting on the。

data if you have too many units and you，learn to just over fit on the training。

data that's not good either so there is，a balance and there's often a testing。

process where you'll train on some data，and maybe validate how well you're doing。

on a separate set of data often called a，validation set to see all right which。

setting of parameters how many layers，should I have how many units should be。

in each layer which one of those，performs the best on the validation set。

so you can do some testing to figure out，what these hyper parameters so-called it。

should be equal to next I specify what，the input shape is meaning alright what。

is my input look like my input has four，values and so the input shape is just。

four because we have four inputs and，then I specify what the activation。

function is and the activation function，again we can choose there are a number。

of different activation functions and，here I'm using raloo which you might，recall from earlier and。

I'll add an output layer so I have my，hidden layer now I'm adding one more。

layer that will just have one unit，because all I want to do is predict。

something like counterfeit bill or，authentic build so I just need a single。

unit and the activation function I'm，going to use here is that sigmoid。

activation function which again was that，s-shaped curve that just gave us like a。

probability of what is the probability，that this is a counterfeit bill as。

opposed to an authentic bill so that，then is the structure of my neural。

network a sequential neural network that，has one hidden layer with eight units。

inside of it and then one output layer，that just has a single unit inside of it。

and I can choose how many units there，are I can choose the activation function。

then I'm going to compile this model，tensorflow gives you a choice of how you。

would like to optimize the weights there，various different algorithms for doing。

that what type of loss function you want，to use again many different options for。

doing that and then how I want to，evaluate in my model well I care about。

accuracy I care about like how many of，my points am I able to classify。

correctly versus not correctly as，counterfeit or not counterfeit and I。

would like it to report to me how，accurate my model was performing then。

now that I've defined that model I call，model dot fit to say go ahead and train。

the model train it on all the training，data plus all of the training labels so。

labels for each of those pieces of，training data and I'm saying run it for。

20 epochs meaning go ahead and go，through each of these training points 20。

times effectively go through the data 20，times and and keep trying to update the。

weights if I did it for more I could，train for even longer and maybe get a。

more accurate result but then after I，set it on all the data I'll go ahead and。

just test it I'll evaluate my model，using model evaluate built in the tensor。

flow that is just going to tell me how，well do I perform on the testing data so。

ultimately this is just going to give me，some numbers that tell me how well we。



![](img/0b60cfa2ad22087bb0426f088d1cbfc6_9.png)

did in this particular case so now what，I'm going to do is go into bank notes。

and go ahead and run bank notes top PI，and what's going to happen now is it's。

going to read in all of that training，data it's going to generate a neural。

network with a all my inputs my 8 hidden，layers our 8 hidden units inside my。

layer and then an output unit and now，what it's doing is its training it's，training 20 times。

and each time you can see how my，data，it starts off the very first time not。

very accurate they're better than random，something like 79 percent of the time。

it's able to accurately classify one，bill from another but as I keep training。

notice his accuracy value improves and，improves and improves until after I've，times。

it looks like my accuracy is above 99%，on the on the training data and here's。

where I tested it on a whole bunch of，testing data and it looks like in this。

case I was also like ninety-nine point，eight percent accurate so just using。

that I was able to generate a neural，network that can detect counterfeit。

bills from authentic bills based on this。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_11.png)

input data ninety-nine point eight，percent of the time at least based on。

this particular testing data and I might，want to test it with more data as well。

just to be confident about that but this，is really the value of using a machine。

learning library like tensorflow and，there are others available for python。

and other languages as well but all I，have to do is define the structure of。

the network and define the data that I'm，going to pass into the network and then。

tensorflow runs the back propagation，algorithm for learning what all of those。

weights should be for figuring out how，to train this neural network to be able。

to accurately as accurately as possible，figure out what the output values should。

be there as well and so this then was a，look at what it is that neural networks。

can do just using these sequences of，layer after layer after layer and you。

can begin to imagine applying these to，much more general problems and one big。

problem in computing and artificial，intelligence more generally is the。

problem of computer vision computer，vision is all about computational。

methods for analyzing and understanding，images you might have pictures that you。

want the computer to figure out how to，deal with how to process those images。

and figure out how to produce some sort，of useful result out of this you've seen。

this in the context of social media，websites that are able to look at a。

photo that contains a whole bunch of，faces and it's able to figure out what's。

a picture of whom and label those and，tag them with appropriate people this is。

becoming increasingly relevant as we，begin to discuss self-driving cars the。

car these cars now have cameras and we，would like for the computer to have some。

sort of algorithm that looks at the，image and figures out like what color is，the light what。

cars are around us and in what direction，for example and so computer vision is。

all about like taking an image and，figuring out what sort of computation。

what sort of calculation we can do with，that image it's also relevant in the。

context of something like handwriting，recognition this is what you're looking。

at is an example of the EM NIST data set，it's a big data set just of handwritten。

digits that we could use to ideally try，and figure out how to predict given。

someone's handwriting given a photo of a，digit that they have drawn can you。

predict whether it's a 0 1 2 3 4 5 6 7 8，or 9 for example so this sort of。

handwriting recognition is yet another，task that we might want to use computer。

vision tasks and tools and to be able to，apply it towards this might be a task。

that we might care about so how then can，we use neural networks to be able to。

solve a problem like this well neural，networks rely upon some sort of input。

where that input is just numerical data，we have a whole bunch of units where。

each one of them just represents some，sort of number and so in the context of。

something like handwriting recognition，or in the context of just an image you。

might imagine that an image is really，just a grid of pixels grid of dots where。

each dot has some sort of color and in，the context is something like。

handwriting recognition you might，imagine that if you just fill in each of。

these dots in a particular way you can，generate like a 2 or an 8 for example。

based on which dots happen to be shaded，in and which dots are not and we can。

represent each of these pixel values，just using numbers so for in particular。

pixel for example 0 might represent，entirely black depending on how you're。

representing color it's often common to，represent color values on a 0 to 255。

range so that you can represent a color，using 8 bits for a particular value like。

how much white is in the image so 0，might represent all black 255 might。

represent entirely white as a pixel and，somewhere in between might represent。

some shade of gray for example but you，might imagine not just having a single。

slider that determines how much white is，in the image but if you had a color。

image you might imagine three different，numerical values a red green and blue。

value where the red value controls how，much red is in the image we have one。

value for controlling how much green is，in the pixel and one value for how much。

blue is in the pixel as well and，depending on how it is that you set。

these values of red green and blue，you can get a different color and so any。

pixel can really be represented in this，case by three numerical values a red。

value green value and a blue value and，if you take a whole bunch of these。

pixels assemble them together inside of，a grid of pixels then you really just。

have a whole bunch of numerical values，that you can use in order to perform。

some sort of prediction task and so what，you might imagine doing is using the。

same techniques we talked about before，just design a neural network with a lot。

of inputs that for each of the pixel is，it we might have one or three different。

inputs in the case of a color image a，different input that is just connected。

to a deep neural network for example and，this deep neural network might take all。

of the pixels inside of the image of，like what digit a person drew and the。

output might be like ten neurons that，classify it as a 0 or a 1 or a 2 or a 3。

or just tells us in some way what that，digit happens to be now there are a。

couple of drawbacks to this approach the，first drawback to the approach is just。

the size of this input array that we，have a whole bunch of inputs if we have。

a big image there's a lot of different，channels we're looking at a lot of。

inputs and therefore a lot of weights，that we have to calculate and a second。

problem is the fact that by flattening，everything into just this structure of。

all the pixel ISM we've lost access to a，lot of the information about the。

structure of the image that's relevant，but really when a person looks at an。

image they're looking at you know，particular features of an image they're。

looking at curves are looking at shapes，they're looking at what things can you。

identify in different regions of the，image and maybe put those things。

together in order to get a better，picture of what the overall image is。

about and by just turning it into pixel，values for each of the pixels sure you。

might be able to learn that structure，but it might be challenging in order to。

do so it might be helpful to take，advantage of the fact that you can use。

properties of the image itself the fact，that it's structured in a particular way。

to be able to improve the way that we，learn based on that image - so in order。

to figure out how we can train our，neural networks to better be able to。

deal with images we'll introduce a，couple of ideas a couple of algorithms。

that we can apply that allow us to take，the image and extract some useful。

information out of that image and the，first idea we'll introduce is the notion，of image。

evolution and what image convolution is，all about is it's about filtering an。

image sort of extracting useful or，relevant features out of the image and。

the way we do that is by applying a，particular filter that basically adds。

the value for every pixel with the，values for all of the neighboring pixels。

to it according to some sort of kernel，matrix which we'll see in a moment is。

going to allow us to weight these pixels，and in various different ways and the。

goal of image convolution then is to，extract some sort of interesting or。

useful features out of an image to be，able to take a pixel and based on its。

neighboring pixels maybe predict some，sort of valuable information something。

like taking a pixel and looking at its，neighboring pixels you might be able to。

predict whether or not there's some sort，of curve inside the image or whether。

it's forming the outline of a particular，line or a shape for example and that。

might be useful if you're trying to use，all of these various different features。

to combine them to say something，meaningful about an image as a whole so。

how then does an image convolution work，well we start with a kernel matrix and。

the kernel matrix looks something like，this and the idea of this is that given。

a pixel there will be the middle pixel，we're going to multiply each of the。

neighboring pixels by these values in，order to get some sort of result by。

summing up all the numbers together so，if I take this kernel what you can think。

of it's like a filter that I'm going to，apply to the image and let's say that I。

take this image this is a four by four，image well think of it as just a。

black-and-white image where each one is，just a single pixel value so somewhere。

between 0 and 255 for example so we have，a whole bunch of individual pixel values。

like this and what I'd like to do is，apply this kernel this filter so to。

speak to this image and the way I'll do，that is all right the kernel is 3 by 3。

you can imagine a 5 by 5 kernel or a，larger kernel - and I'll take it and。

just first apply it to the first 3 by 3，section of the image and what I'll do is。

I'll take each of these pixel values，multiply it by its corresponding value。

in the filter matrix and add all of the，results together so here for example。

I'll say 10 times 0 plus 20 times，negative 1 plus 30 times 0 so on and so。

forth doing all of this calculation and，at the end if I take all these values，value in。

colonel add the results together for，this particular set of nine pixels I get。

the value of ten for example and then，what I'll do is I'll slide this three by。

three grid effectively over slide the，colonel by one to look at the next three。

by three section here I'm just sliding，it over by one pixel but you might。

imagine a different stride length or，maybe I jumped by multiple pixels at a。

time if you really wanted to you have，different options here but here I'm just。

sliding over looking at the next 3x3，section and I'll do the same math twenty。

times zero plus thirty times a negative，one plus forty times zero plus twenty。

times a negative one so on and so forth，plus thirty times five and and what I。

end up getting is the number twenty then，you can imagine shifting over to this。

one doing the same thing，calculating like the number forty for，example and then doing the same thing。

well，and so what we have now is what we'll，call like a feature map we have taken。

this kernel applied it to each of these，various different regions and what we。

get is some representation of like a，filtered version of that image and so to。

give a more concrete example of why it，is that this kind of thing could be。

useful let's take this kernel matrix for，example which is quite a famous one that。

adds an eight in the middle and then all，of the neighboring pixels get a negative。

one and let's imagine we wanted to apply，that to a three by three part of an。

image that looks like this where all of，the values are the same they're all xx。

for instance well in this case if you do，twenty times eight and then subtract。

twenty subtract twenty and subtract，twenty for each of the eight neighbors。

well the result of that is you just get，that expression which comes out to be。

zero you multiplied twenty by eight but，then you subtracted twenty eight times。

according to that particular kernel the，result of all that is just zero so the。

takeaway here is that when a lot of the，pixels are the same value we end up。

getting a value close to zero if though，we add something like this 20s along。

this first row then 50s in the second，row and 50s in the third row well then。

when you do this because the same kind，of math twenty times negative one twenty。

times negative one so on and so forth，then I'm going to higher value a value。

like 90 in this particular case and so，the more general idea here is that by。

applying this kernel negative ones eight，in the middle and then negative ones。

what I get is when this middle value is，very different from the neighboring。

values like 50 is greater than these 20s，then you'll end up with a value higher。

than zero like if this number is higher，than its neighbors you end up getting a。

bigger output but if this neighbor does，this this value is the same as all of。

its neighbors then you get a lower，output something like zero and it turns。

out that this sort of filter can，therefore be used in something like。

detecting edges in an image or I want to，detect like the boundaries between。

various different objects inside of an，image I might use a filter like this。

which is able to tell whether the value，of this pixel is different from the。

values of the neighboring pixels if it's，like greater than the values of the。

pixels that happen to surround it and so，we can use this in terms of image。

filtering and so I'll show you an，example of that I have here in filter。

dot PI a file that uses pythons image，library or PIL to do some image。

filtering I go ahead and open an image，and then all I'm going to do is apply a。

kernel to that image it's gonna be a，three by three kernel same kind of。

kernel we saw before and here is the，kernel this is just a list。

representation of the same matrix that I，showed you a moment ago it's negative。

one negative one negative one the second，row is negative one eight negative 1 and。

the third row is all negative ones and。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_13.png)

then at the end I'm gonna go ahead and，show the filtered image so if for。

example I go into convolution directory，and I open up an image like Bridge dot。

PNG this is what an input image might，look like just an image of a bridge over。

a river now I'm gonna go ahead and run。

![](img/0b60cfa2ad22087bb0426f088d1cbfc6_15.png)

this filter program on the bridge and，what I get is this image here just by。

taking the original image and applying，that filter to each three by three grid。

I've extracted all of the boundaries all，of the edges inside the image that。

separate one part of the image from，another so here I've got a，representation of boundaries between。

particular parts of the image and you，might imagine that if a machine learning。

algorithm is trying to learn like what，an image is of a filter like this could。

be pretty useful that maybe the the，the machine learning algorithm doesn't。

care about all of the details of the，image it just cares about certain useful。

features it cares about，particular shapes and are able to help，it determine that based on the image。

this is going to be a bridge for example，and so this type of idea of image。

convolution can allow us to apply，filters to images that allow us to。

extract useful results out of those，images taking an image and extracting。

its edges for example and you might，imagine many other filters that could be。

applied to an image that are able to，extract particular values as well and a。

filter might have separate kernels for，the read values the green values and the。

blue values that are all summed together，at the end such that you could have。

particular filters looking for is there，red in this part of the image are there。

green and other parts of the image you，can begin to assemble these relevant and。

useful filters that are able to do these，calculations as well so that then was。

the idea of image convolution applying，some sort of filter to an image to be。

able to extract some useful features out，of that image but all the while these。

images are still pretty big like there's，a lot of pixels involved in the image。

and realistically speaking if you've got，a really big image that poses a couple。

of problems one it means a lot of input，going into the neural network but two it。

also means that we really have to care，about what's in each particular pixel。

whereas realistically we often isn't，like if you're looking at an image you。

don't care whether it's something is in，one particular pixel versus the pixel。

immediately to the right of it they're，pretty close together you really just。

care about whether there's a particular，feature in some region of the image and。

maybe you don't care about exactly which，pixel it happens to be in and so this is。

a technique we can use known as pooling，and what pooling is is it means reducing。



![](img/0b60cfa2ad22087bb0426f088d1cbfc6_17.png)

the size of an input by sampling from，regions inside of the input so we're。

gonna take a big image and turn it into，a smaller image by using pooling and in。

particular one of the most popular types，of pooling is called max pooling and。

what max pooling does is it pools just，by choosing the maximum value in a。

particular region so for example let's，imagine I had this 4x4 image but I。

wanted to reduce its dimension so I，wanted to make it a smaller image so。

that I have fewer inputs to work with，well what I could do is I could apply。

two by two max pool where the idea would，be，that I'm going to first look at this。

two-by-two region and say what if the，maximum value in that region well it's。

the number 50 so we'll go ahead and just，use the number 50 and then we'll look at。

this two-by-two region what is the，maximum value here 110 so that's gonna。

be my value likewise here the maximum，value looks like 20 go ahead and put。

that there then for this last region the，maximum value is 40 so we'll go ahead。

and use that and what I have now is a，smaller representation of the same。

original image that I obtained just by，picking picking the maximum value from。

each of these regions so again the，advantages here are now I only have to。

deal with a two by two input instead of，a four by four and you could imagine。

shrinking the size of an image even more，but in addition to that I'm now able to。

make my analysis independent of whether，a particular value was in this pixel or。

this pixel like I don't care if the 50，was here or here as long as it was。

generally in this region I'll still get，access to that value so it makes our。

algorithms a little bit more robust as，well so that then is pooling taking the。

size of the image reducing it a little，bit by just sampling from particular。

