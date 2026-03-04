# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p74 4_PHP中的对象生命周期.zh_en -BV1Lr421A75d_p74-

![](img/5c63a13ef88ece9ba5892698a8bd3d18_0.png)

![](img/5c63a13ef88ece9ba5892698a8bd3d18_1.png)

Okay， so one of the things I talked about in that previous section was how cool the PhP object model is in particular because it's aware of sort of things like session and the kinds of stuff we use in web applications。

 But now I want to talk about sort of the classic things when we talk about object lifecycle about the definition of the template。

 the creation initialization of the objects and then the destruction of those objects。

 and we have special methods that we get called and we saw that in some of the documentation。

 the constructor and the deor that is a bit of code that you as the object builder get to say。

 you know what call me when you're setting me up or calling me when you're throwing this thing away。

 We use constructors all the time so that we can get our data into the right state when we set things up and the deor is used less often。

 So like I said， the constructor is there to get us started and set up some primary instance variables so they have the right values as we'll talk about in a bit you can sometimes have these hidden variables。

 they're nonpublic and the constructor can set those values up to what they're supposed to be when the thing first。

So here's a little sample。 We're not going to do anything intelligent in here。

 We're just going to kind of show how this constructor and constructor start working。

And so we're going to have a class， our template party animal。

 And it's going to have a method called underscore underscore construct。

 It's a specially named method。 And then one' called to underscore underscore to constructstruct。

 And all we're saying is call us back when you are creating us and then call us back when you're destroying us。

 So let's run the code then right So we print out one。 and we say let's make a new party animal。

 And that says， oh， run the constructor as that moment of creation is happening。

 It's before the assignment statement comes back with X。 So we say we're construct it。

 then we say two。 and then we're construct again。 So we're running the second one。

 So we're creating Y now。 and it constructs it， It makes the template。

 then calls the constructor and then gives us back the object。s that's the order in which it happens。

And then we say three。And then we say something which just runs something， right。 And so now。

We're at the end of the program。 so we did all these things。

 and now we're running the end of the program， except that this is the last line of the program。

 And so it's going to clean all these variables up。

 So x is going to go away and y is going to go away。 But before x and y go away。

PHP calls us back for X and gets rid of that and then calls us back to get rid of Y when there's no code writing whatsoever。

 because at the end of a request response cycle， when this file is all done。

 then it's going to garbage collect and get rid of all these things。

 and so it's going to carefully call our destructor。And like I said there。

The construct's used a lot the de in PhP is actually more consistent about calling the de than other languages because we know when we're done with the request in PhHP。

 and so you tend not to see deors in other object or languages because the timing of the deor is not as predictable as it is in PhP。

So again， object and instance。😡，Each instance has its own distinct variables。

 and you can have many instances of the same class。 And so we've been doing this all long。

 And so let's just talk about something where we're going to set a variable in the constructor that's going to control the behavior of this application。

 So now we're going to pass a constructor parameter in。

 and that just becomes a parameter into the underscore construct method。

And we're going to do this to set up this hello translator。

And we're going to tell it what language it is that we want to translate。

 and so we're going to pass that in and PhP is going to build a hello object。

 it's going to put a variable in here and we're going to have a method in here。

 and now this is sort of empty and now it's going to call the constructor。

And the constructor is going to copy this variable that came in through laying into the instance。

 So E S is going to be in here。 And then after the constructor is done。

 then this assignment finishes。 And so we have variable high now。

 which high points now at this object that's been constructed from the template。

 except we put some data in in the constructor。 We're using this to say this one versus layng is the one that came in。

 This is the one that's actually in the object。So that's what happens in this line。 Constructor runs。

 We copy a little bit of data from the parameter to the constructor into the object itself。

 and now we say high Greek， which means we're just going to find the Greek code within high。

 That's this code right here， Greek， we're going to run it。This points to this instance。

 and we can see what the current language of the current object is if it's French。

 we're going to do one thing， if it's Spanish， we're going to return Oah and we're going to return Ho if it's none of the above。

 and so in this case， because we got E in this particular instance， we're returning Oah。

 and so that's what prints out here。Okay， so we're passing stuff in in the constructor to kind of。

Personalize or unique eyes that particular object in the right way。

So that's the constructor that's called at the moment of creation，'s kind of the you create it。

 you construct it， and then you give it back to us， and then we get to use it。

The next thing we'll talk about is inheritance， and that's how we take the capabilities of one object。

And inherit them when we make a new object。

![](img/5c63a13ef88ece9ba5892698a8bd3d18_3.png)