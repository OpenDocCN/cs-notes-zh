# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P41：41_05_03_3-霍夫变换与MATLAB演示-时长-20-59.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 I want to talk now about a half transform。

The half transform is a really nice technique to detect objects to segment out objects for which you know there are shape。

 maybe a straight line， maybe a circle， as we have seen in the previous example， for example。

 we want to detect the ball。 We know it's circular。

 So can we include that information in our detection in our segmentation technique to detect that is actually circular can we use the information that we are expecting here a straight line and basically get a straight line So the half transform allow us to do that。

 And in a very simple and really， really nice fashion， Let's illustrate that。

The basic idea is quite simple， and we' are going to start with ideas on how to detect straight lines。

 and then we' are going to move to cers， but starting with straight lines makes it much。

 much easier to understand。In school， I mean probably in elementary or middle school。

 you have learned how to represent a straight line that is on a plane。

 and I'm going to write down the questions and explain them to you again。 So here we have the plane。

 This is the image plane， the X Y。 This is the image plane。

 and we have points on a straight line on the plane。 For example。

 this straight line might be this one or this one。Now。

 a straight line on a plane is represented can be written down in the following form。 We have row。

 and I'm going to explain each one of these symbols in a second is X。



![](img/e4f36f7f30a9da76ea508959bc9431e1_1.png)

Cosine theta plus y。Sine theta。So row is the distance from the coordinate systems center to the straight line。

 and this should be perpendicular。 Of course， its a distance。 might a bit tilted in the video。

 They should be basically a 90 degrees angle。 So row is the distance to the straight line。

 and theta is this angle here that basically is the angle with one of the axis。

 Let's pick this one in this case。With the line connecting the center with the straight line that we are considering。

 So basically， every point that is on the line holds this equation。Every single point。

 this one and this one and every point in the line will hold this equation。 usingsing that。

 here is the idea of the half transform。 We take a point on the image。

 and that comes from the edge detection。 So basically。

 every point that the edge detector said there is an edge going through。For every point。

 we basically have an infinite number of lines going through it。

This is one of them with a particular row and a particular theta。 Now， let's draw a different one。

This line has its own row and its own theta。 This will be row。This will be theta。

 We can go and draw a different line， all the lines going through the point。 So here is another one。

 It has its own row here and its own theta。 and we can keep doing that。 We can pick yet another one。

 for example， Let's pick this one。And it has row。And it has。Theta。

 so every point has an infinite number of lines。 And basically。

 every point will go and say any of those lines is okay with me。 The point will go and vote for。Roe。

And theta for a series of them， It should be voting for an infinite number。

 but we're going to discretize。 We're going to do this in the computer。

 So we won't be able to vote for an infinite number。

 We're going to vote for a discrete says of row and theta。 Now， that's only one point。 And basically。

 every possible line that goes through that point will get one vote。 Okay。

 Now what happens with this other point。 This other point has its own lines that go through it。

 So it's going to go and vote for its own lines。 It's going to vote for this one， of course。

But it's also going to vote， for example， for this one that has its own row。And its own theta。

 And it's going to vote。 And I don't want to draw too many because it will make the picture very unclear。

 but it's going to vote for an airline here， an airline here and so on。

 So it's basically going to vote also for a series of robe。And theta。

 And all the votes will get one vote。Paedook， what happened。This line is common to both of them。

 and we know that in a Euc clideon space through two points， there is a single line。

 So there is only one line， the one that we are looking for that' is going to get two volts。

Basically， and that will help us to understand what's the row and the theta for this line。 But。

 of course， not only twovols， because theres going to be another point here。

 There is also going to go vote for a series of row and theta， but it's going to vote for this one。

 So this one is now getting threevols。 One for each point。That the edge detector found。

That is on that line。 Now， of course， the edge detector my fan points that are outside of that line and those will also make their own votes。

 but hopefully the only line that gets a large number of votes is the line of interest。

 So that's a basic idea of the half transfer and we're going to provide more details in a second。

 but every point that the edge detector fan votes for the possibilities in this lines。

 if we have multiple points on the same line then we're gonna to have multiple votes So how do we do that in reality。

 So in reality we're going to go from the X Y coordinate system。

 which means the image coordinate system to a new coordinate system which is theta and row。

That coordinate system the same way that our image is discretized。It's going to be discretized。

 So theta can be anything around the circle， and we basically discretize as fine as we want as fine as our memory or our computational time allow。

 Let's say we can discretize every one degree。 We do the same for row。 We discretize it。

 We know that row cannot go farther than the size of the image。 So we know is bounded。

 And then we basically discretize it。 And then what we' are going to do。

 Let me write the equation again。 We have the equation， row X。😊，Cosine theta plus y。3。Theta。

 so what we're going to do is the following。 We go to every point。



![](img/e4f36f7f30a9da76ea508959bc9431e1_3.png)

Let's say this one， So every point gives us x y， the coordinates of that point。

 then we run through theta， and we say let's say one degree。

 So we have the coordinate x and y we put cosine of1 sine of1 that gives us a row。 we go and vote。

For that one， with， let's say。Add one vote。 This is sometimes called the accumulator。

Then we go and say okay Theta now equal2， we have x y， we define theta2。

 we have cosine of 2 plus signine of 2， we get a new row， we go and vote for that one as well。

 and we keep voting for every single point now it's not very hard to see that once you think x and y if you vary theta as here or as here。

 row changes in a sinoidal fashion。So that's very easy。 And it comes from the co and sign。

 So your votes will look like a sinenooidal fashion for every single point， remember。Now。

 when I go to a second point， I will get more votes， a difference in a soda。

 so I will get different votes， and there will be a place the place corresponding to this trade line that is starting to accumulate votes。

Every。For every point we are going have that sinusoidal。

 we vote basically on that sinusoidal and we start to accumulate。

 And now the next step is to go into the accumulator and find the maxima。

 maybe multiple if there are multiple straight lines， but we go and find and say， oh。

 this is the row and theta that many points like， and that's how we detect these lines。

 So let me just run you through the pipeline again。

 you start from the image and you do an edge detection。

 every point some of them in the lines that you care about。

 some of them outside every point defines an equation like this。

 Every point gives you the X Y coordinates。 So you go into the accumulator space and you vote sinusoidal vols。

Or you just run through the thetas in the discretized space and you vote for every row that you get from this equation。

 Every point a vote， then when you finish， you basically say。

 let's go and look which areas which basically entries in my accumulator have enough votes。

 that means that there is a straight line going through them。 Now。

 this concept of voting goes very far and you can actually do many。

 many things beyond detecting straight lines。Let's just show one example。Yeah。The basic。

 So here we have。4，5 points。 and then the accumulators。 So just going。

 And you will see there is a straight line。 So there will be three votes for that。

 And there is another straight line。 There will should be three votes。2 votes。

 two votes and so on For this very， very particular example。

 I just want to use it to show how we basically get this sinusoidal type of votes for every point。

 Now， let's see that on a real image。 So what we see here is an aerial image。



![](img/e4f36f7f30a9da76ea508959bc9431e1_5.png)

Here， and we clearly see that there are some straight lines。 This is the result of edge detection。

 In particular， it a canny edge detector。 Now， it's a bit confusing from it。

 We want to get the parameterized straight line。 We want to go the row。

 We want to get the row and theta for this one。 This is the picture of this accumulator that went through all these points。

 Now， you don't need to use all of them。 You can just sample some of them。

 There's plenty of points on the straight line。 So you will get very high accumulator just by using a subset of them。

 But this is the result of the accumulator。 and then you go here and you look for the maximum values。

😊。

![](img/e4f36f7f30a9da76ea508959bc9431e1_7.png)

And from then， you get the row and the theta that correspond to those maximumimal values。 Remember。

 this is your。Cta。Row accumulator。 So wherever is the maximum。

 it gives you a value for theta and a value for row。 And those corresponds to what we see here。

 And then you can put it back on the picture and say this is my most basically extreme line。

 my most prominent line。 Then there might be other maxa。

 they will certainly be for this line and this line and this。 And you can go and pick all of them。

 in this case， we are only marking the most prominent one。

 a very simple and extremely powerful technique。 I want to show you also how we do this for circles。

 But before that， I want to run this example of matla。 Let's see that。😊。

We're now as we say inside the Matlaav environment。

 and let's see the type of operations that we are going to do to illustrate they have transformed to the text straight lines。

So there is a bunch of commands here， but I'm going to describe them to you。

 most of them are just to make nice plots， I'm going to describe to you those that are important to understand what basically the half transform is doing here。

So first， as we have seen many times in the past， we read the image。 This is the first operation。

 Then we are going to rotate that image。 This is just for the fun of it。

 I don't want you to believe that we can only detect horizontal or vertical lines。

 So we are going to rotate that image。Here we do edges。 Remember。

 the first thing we need to do is detect the edges in the image。

 That's the input to the half transform。And then here it is。

 they have transform in MAla that would basically create this accumulator in the theta row space。

And these are a bunch of operations just to illustrate， to visualize。

 We're going to run it in a second。 I'm just describing the operations for now。

Then the next we need to detect the peaks， we need to detect the maxa in the accumulator。

 and that's this operation， and we're going to plot it。Now we have the max。

 which means that we have the row and the theta and we need to detect the lines。

 we actually need to draw those lines and that's what this operation does is's basically finds the lines and then the rest is going to draw them and actually it's going to draw them as segments and with the images I'm going to illustrate you how we do that。

 So let just run all these operations and they just see the results。So here are the two images。

 as you see， it's pretty fast。嗯。We see the original image。This is accumulator and here the squares。

 the white squares are basically the peaks， they basically the most important maxima in the accumulator。

 and those are these green lines that we see here。Once again， in aumulator， we have row and theta。

 Once we have that， we can go back into the image plane and draw the lines。 Now。

 you may wonder that wait a second， row and theta will give us straight lines。

 but all across the image。 How do we get to segments。 If we need to get to segments。

And the basic idea is that there are many ways of doing that。

 but one way of doing that is you go and put the line back in the image as we have here and then you can go around that line and see if there are actual points in the image。

 which were detected by the edge detector that voted for that line。

 and you basically can get what actually was the real segment and not the whole line in the image。

That's just one way of doing that。 And as we see here， we got these straight lines。

 very fast and very simple operation to get straight lines。 There are others。

 just their votes are weaker， and we need to decide to put a threshold in theccumulator。

 We might put a threshold that says。Don't give me any line that has less than certain amount of votes。

 or we can say， give me the 10 top lines， give me the the the five top lines or anything that is application dependent。

 So with this image and with this example， we see the whole pipeline from the image。

 detect the edges， create accumulator find a maximal。Draw those lines back to the image。

 and if you need。Basically， find the segments by looking in the image。

 Where do you have actual points that voted for that， If you need just the segment。

 So now we're going to go back and I'm going to describe what we do for circles。

What about circles then？

![](img/e4f36f7f30a9da76ea508959bc9431e1_9.png)

So here we have an image of circles， and we want to know if we can basically find the circles using the half transform。

The idea is exactly the same。 Now， a circle can be written down in the following form。X minus。It0。

 That's the x coordinate of the circle。Square plus y minus y 0 square equal to the radius square。

 So every point in a circle holds。This equation were the center of the circle。Is given by these pans。

These are the coordinates of the center， what we need to find。 and the radius of the circle。

 which is also an unknown。Is given here。 If you don't remember this formula。

 just pick any of the elementary geometry books or just believe me that this formula is the right formula for a circle on the plane。

 Now， in the same way that we needed to find row and theta first straight lines。

 We need to find the center and the radius for a circle。 So we need one2 three parameters。

 So now our accumulator won't be on the plane。 It will be a three dimensional accumulator。

 But we are going to do exactly the same。 We are going have an H detector。

 Every point is going to vote four circles。 Every point is going to give us。It coordinates。

 and then we're gonna run through the accumulator on the x coordinate of the center。

 the y coordinates the center and get the radius。 So we I'm gonna run through that through the x's run through the ys and then get the radius。

 We accumulate。 We pick the maximum one and we basically are done。 We got our center and radius。

 So let's just illustrate one example。 here we have the edges and I want to repeat that once again。

 Every point here we vote for multiple centers。 multiple radius。 We can， of course。

 limit the centers because we know the dimensions。 We can also limit the votes for the radius because we also know how large the objects can be in the image。

 We are gonna vote for that。 There are gonna be multiple votes for the real。



![](img/e4f36f7f30a9da76ea508959bc9431e1_11.png)

Cs in the images。 And then we basically detect them。 And here they are。

 We basically went through the accumulator and find the top votes， and we get our results。Basically。

 the half transform can be used for any parametermetric curve。

 anything that we need to vote for some parameters of that curve as row and theta。

 the centers we can find parabols。 we can find any， any curve that we can write with parameters。 Now。

 the more parameters you have the more expensive。 The half transform is。 So normally。

 the half transform is used for finding straight lines， circuits， ellipses。

 relatively simple objects that have a controllable number of parameters。

 Otherwise your accumulator spaces huge， takes a lot of memory and takes a lot of computational time。

 both to compute it and to find the maxima。 But for those simple shapes， there's。😊。

One of the best techniques out there is the half transform。 So I hope you enjoy this video。

 and I see you in the next video。 Thank you very much。😊。



![](img/e4f36f7f30a9da76ea508959bc9431e1_13.png)