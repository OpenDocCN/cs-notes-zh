# 哈佛大学《2D游戏开发｜CS50 Introduction to 2D Game Development 2025 Fall》中英字幕 p07 CS50 2D - Lecture 6 - Angry Birds .cut.zh_en -BV15xsPzEETf_p7-

Hello world。 My name is David Malon and I am here with Colton Ogden and this is the third of three lectures today if you tuned in for the first two my apologies。

 I know they took a while， but this one is now Colton as well as our final live stream tomorrow morning roughly around 9am Eastern time the URL is at CS 50 Ly zoom as always please forgive as always if we start and stop just to fix some things along the way feel free to ask questions the chat I will surface them with my hand in the air fun fact now for Colton would be what is your favorite mobile game in recent years。

 Probably candy crush overall but I did I think Abu Birds was the first one of the first games I really played a lot of on ios back in the original sort of early ios boom of sorts and we were talking earlier about cut the rope which some of you might know which was just super fun and all you had to do was cut the rope with your finger。

 but it was very well done too really nice elegantly designed， very beautiful game。

 Yeah it was really good game mechanics I thought for such a simple device like just the swiping motion is what fruit。

as that was even better because you could kind of swipe through the various yeah。

 that was gratifying times all right， it's well without further ado。Hello world。

 this is CS52D Le 6 today we're going to take a break away from the older NeES titles。

 even as pleasant and nostalgic as they are for me and we're going to venture back towards more modern mobile oriented games in particular which we looked at with Match3 previously Candy Crush being a good example of that and Angry Birds is an example of another franchise that is very popular。

 this is an example from one of the mainline titles Angry Birds1 or two。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_1.png)

Originally it wasn't quite as large as this this looks like it was probably done on a tablet thereabout。

 but it encompasses the overall gist of the game， which is essentially that you're controlling the slingshot here。

 which you have a bunch of these angry birds as the name of the game suggests that are trying to get revenge on these pigs that have sort of started to build fors or whatnot to take over their territory。

 not entirely sure of the exact lore behind the game if any such exists。

 but the pigs are sort of blocked by these obstacles here made a various materials would， glass， ice。

 metal and you have varying types of birds that you can use to effect damage onto these structures and ultimately the pigs whereby if you do a certain if you were able to take out the pigs with a certain number of birds or without depleting a certain number of your limited birds you can see here the person has three sort pieces of ammunition in the form of birds left before they run out in that level。

 you can accomplish getting higher scores for that level in the form of stars typically you can aim for three stars or you can get two or one depending on your performance and there are many。

of the franchise。 This is another version which just set in a more tropical setting and there's all kinds of different versions。

 there's a Star Wars one and I'm not entirely sure how far the franchise has gone in recent days and how they even have TV shows and the like very popular franchise。

 one of the first mobile series I ever played really big fan on iOS。

 especially in the early days of the platform and this allows us to really look at in a unique way physicsic that we haven't really looked at in games thus far where we've sort of done everything ourselves with simplistic overall physics calculations with velocity and manipulating positions directly and sort of approximating collisions and bouncing and whatnot but Box 2D is this sort of library that love2D embeds within it。

 Box2 is this separate library that you can actually embed in any compiled framework or use in any situation that you want to It's just a set of code a set of functions for modeling physical interactions it's very popular and love2D exposes it as a set of these raper functions that essentially defer。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_3.png)

to the underlying box 2D functions that you might normally expect to see in something like C or C++ and so today we'll be looking at box 2D as our main focus with a bunch of various underlying parts including bodies and fixtures and shapes and joints and things like that and then we'll also be looking at because we're dealing with angry birds which is a sort of mobile game that has this mouse or finger touchbased input in order to drag the bird on the slingshot and then release it and send the bird flying we'll look at for the first time besides just clicking how to actually use mouse movement with X and Y and track key released in key pressed and so on and so forth and so our goal is to approximate angry birds per the screenshot that we showed previously of those titles with a very simplistic version but nonetheless we do see we have a alien creature here we are using another  Kenny sort of open source creative commons tile set that allows us to use to accomplish the same thing but with a different aesthetic we're using a sort of aliens aesthetic is how they term it in the sprite pack I believe and so we have this sort of alien。

Here a circle which is our character and then we have a square-based enemy alien there in the obstacles。

 and then we have of course these obstacles here that are protecting it very much in the same vein as we saw previously with the first slide。

 these obstacles will be able to be deleted by colliding with them and then they'll break thereby exposing the alien on the right which after a certain collision or should the obstacle collide with the alien itself。

 the alien will be defeated， removed from the game world。

 and then we will therefore achieve victory in our play state。And so in order to illustrate this。

 I think it's appropriate as we always do by tradition to take a look at the actual implementation of it。

 if I could have a volunteer whom I want to come up on stage， yeah， I why don't you come on up。

 we'll take a look。At。Our implementation。don't believe you Matt， David。

 nice to meet you nice to you okay， so I'm going to go ahead and start this up right here。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_5.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_6.png)

Sorry， I didn't realize I had that open yet， sorry。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_8.png)

Oof。And quick question， can we bring mics down？And so this being our goal。

 why don't we ask tradition take a look at an actual implementation of it and do a demo if we could get a volunteer that could maybe come up on the stage？

Don't believe Davidton nice to meet you， Okay， so let's go ahead and run this here。

And we'll see we've got the window there can see we see， click the start for the first time， maybe。

So it does detect it does detect if you are going to shoot the sort of bird slash aliens to the left on this example。

 but as you can see， very nice， you're able to defeat the it does detect collisions and in the boxes and whatnot will break if they hit your alien or there's a velocity calculation between the two objects that' perhaps a certain threshold and then it restarts after a certain period of time you can try again if you want。

 it was very quick。We can see there's sort of randomization occurring to with the alien there。Nice。

 so then that breaks the top part so then that won't end up fully defeating the alien this time。

 but after a moment once the velocity sort of begins to get really slow， you'll notice that。Yeah。

 that's just like the real one。Here go。Very nice and then you'll have another shot here we're very generous with this implementation where we give the user unlimited birds。

 but sometimes you might run out of birds at this point then the level you would sort of lose。Well。

 I think I should put an end to this game。Very nice， achieved victory， excellent job thanks so much。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_10.png)

And so。We saw a great many pieces there that we haven't really looked at yet。

 certainly it's very different than what we've done so far although on the surface you know we might look at something like that and see okay we're doing AabBB in some form that we usually done we haven't really dealt with circles as much so that part might be a little bit different but overall we might presume that okay the circle maybe is using its own rectangle and doing AabB in that way but in fact really there's not a whole lot of manual physics we have to do this time thankfully B2D as we will see shortly is going to take care of a lot of these things for us and allow us to do very interesting physical things that having to worry necessarily about so much of the underlying mathematics in detail but to get started I think it's important to point to our spritehe as is tradition as well what we're actually going to work with so we saw that we had a few different things on the screen we had the ground which is ultimately just this repeated tile here and as we'll see we don't actually have a physical ground that we're modeling as much as we have an edge and then we're going to be drawing a bunch of ground。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_12.png)

Underneath it， something that Box Studio lets us do。

 we have varying shapes and colors of aliens circular and square circular to be our alien character square to be the sort of enemies that we're going to be targeting。

And then we have all these different amazing tiles set for various types of obstacles that we could add to the game and it is named as such in the distro。

 we are only using a couple of very simple examples as being sort of these vertical blocks here。

 but you'll notice there are some sort of cracked version of these which we use will be expected to be used in the problem set which is currently as folks probably observed the the bird or the alien if it were to collide with any of those wooden pieces is going to just instantly destroy it and have that deponwn from the game world and what we really would probably want is different materials and for those materials to have differing values for how much they can take damagewise and so part of the problem set will be okay detect based on the hit based on the material。

 if it's a lighter material like glass， maybe break it in one hit。

 but if it's would maybe have it take two hits and have the first hit trigger it into being some sort of this cracked variant herein and thankfully all of the tiles sets that we'll be using of the different materials that are also included。

Have all these for you。So some useful links for folks if they're digging into Box 2D will be the following。

 all thankfully located the first two located on Love2D's actual documentation。

 a very handy blog with a lot of Box 2D information which I consulted and many folks point to on the internet is this iforce2D。

net blog which has a ton of really useful deeply detailed articles on Box 2D in its mechanics and some of the algorithms you can use to do various things。

But the very first thing we should begin to talk about with Box 2D is this idea of the world and so Box 2D is ultimately just a rigid body physics simulator of sorts where everything that exists in the world is this sort of rigid definedfin body。

 this sort of entity that takes a shape and can collide with other entities and there are various coefficients and multipliers for various things you can perform impulses on things and get angular velocity and linear velocity for things and damping and so on and so forth and these things allow you to do all kinds of very complicated physics。

 realistically modeled without having to necessarily know every single thing about the math to do it。

 and so it empowers people beyond that also just create very interesting assortments of shapes that model physical sort of more complicated engineering projects that allow you to do very complicated things which we will only briefly allude to。

 but for example you could get very creative and create things like cars and things。

like automated systems and pulles in one mouth that do all sorts of really sophisticated things but the place that we begin is the world and that's where the physics actually gets simulated。

 there's this overarching and we've sort of thought about it in our own way with place dates and levels and dungeons and whatnot you can think of the world as this box 2D container for all of your bodies in the world which we'll look at in a moment and the world's job is to just update periodically with you pass it in DT just like you would pass it in DT to update anything and it will actually take charge of performing all of the collision detection including continuous collision detection for very fast- movingov things to make sure that they don't clip through each other depending on whether you've set certain bodies as dynamic。

 kinematic or static。And so the function that you would use to create this new world would indeed be love。

physics。neword， you would pass in gravity， remember that we did have gravity in our own world with Mario。

 for example， in that it had a positive y value that would apply to anything that was sort of in the world period and that would affect things moving downwards and unless they hit the ground and then their velocity would be set to zero for example。

 but you could jump and same with flappybird and then have this positive y value。

 cumulatively affect your。Actual y axis value and therefore change your velocity and therefore change your movement over time Box 2D takes care of that for you。

 but you pass that in at World time and you can set an X gravity and a Y gravity and if you are doing a top-down game for example you might not have either of those sets of anything and you might instead be doing everything without gravity but still performing physics calculations in some 2D plane which is totally possible with B 2D。

And so before we can， we'll shortly start to look at some code examples。

 but the first thing we need to talk about is well we've alluded to， we have the world。

 we know we have this simulator that's going to exist。

 that's going to perform all these calculations for us。

 all this physics that we don't necessarily like to worry about as much at least in terms of the nitty gritty but we do need to actually have things that can operate in this physical space。

 the first step towards that is defining a body， and so what a body is is essentially this abstract container that can hold these things called fixtures that apply shapes and the body's job is to essentially take those physics calculations and then perform just basic mechanics without a shape without any sort of idea of mass or any particular friction or anything。

 its sort of this invisible thing that can have physics applied to it almost like a particle but it can be aix to it can have fixtures affix to it that therefore influence its shape and therefore allow it to perform collisions with other entities。

 and so the body is are sort of like the nucleus behind all of the things that。

Actually interact in your world， they're the things that you build pieces on top of fix things too。

 to create behavior in your world space。And to do that you'll again with a similar API。

 you'll call love。physics。newbody which takes in the world itself so that the world has a reference to it and then an x and a Y and then a type and the type is very important。

 so here we're going to transition to the next slide which we'll talk about the three different types of bodies and this is essentially the core behind behavior besides efficiency and applying forces and whatnot to your objects but you can think of three different types of bodies as being static。

 dynamic and kinematic and so if a static body you can think of something that literally will just not have physics essentially applied to it。

 it's there it's statically there， its position is fixed。

 it doesn't do anything to anything else really it can still affect things in the sense that it can be it can still have physics applied to it and things can bounce off of it。

 but it will itself not be affected by other objects。And it cannot move， it is fixed。

 it will not change， a dynamic body will actually move and perform bounces off of things and affect other things and it is by its nature a dynamic body in the world。

 the opposite of a static body， a kinematic body is similar to a static body in that it can move around and influenced behavior。

 but it does not get the usual behavior affected towards it。

 it cannot be influenced by other objects colliding with it。

 it is affected by gravity and so you might have something like a moving platform that is kinematic and actually affects other objects should they collide with it。

 but it itself is not being， for example， affected by gravity。

 it is not falling like a dynamic body would if you had a dynamic platform it wouldn't really work。

 but it would fall to the ground because it be affected by gravity or it could be affected by other objects。

And lastly， before we actually look at some code， we'll look at fixtures。

 fixtures are you have a body Sure you can move it around or you can know that it will apply physics or not be applied physics to in your world but on top of that you need to have some sort of shape you need to have some sort of idea how much friction does this body have how does it actually affect things before we can actually see something on the screen what does it look like what are its edges and so to do that it needs to take a shape and to take a shape。

 it needs this thing called a fixture fixture will essentially literally be you can envision a car which has sort of this nucleus and then you can imagine the chassis being the first fixture on the car and then having more fixtures for the wheels where now they've got places where you can start to put wheels and you can start to envision this object being built up with shapes but you need places to actually put those shapes and that's what fixtures allow you to do and therefore。

After you define a fixture， you can then decide， okay now I want to put these various kinds of shapes onto that object to give it form to allow it to actually collide with things in the way that a rectangle would or a circle would or so on and so forth。

 therefore allowing you to finally visualize what these physics operations are doing in your game world so a lot of detail before we can actually get to some code but now we'll take a look at some examples and we can see what this looks like in practice。

So I'm going transition over here。And we're going to look very first at static so we looked at we talked about static bodies being sort of the simplest thing。

 which is just the static thing that's not going to move， it's going to be fixed in space。

 it's not affected by gravity or anything like that。

 it's not affected by other objects and it can't move it's just there in space So if we look here I'm going to run it。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_14.png)

And we will indeed see we have this square being rendered right in the middle of the screen。

' we're rendering it as just a white square， it's not doing anything。

 it's not really all that different really from the pong paddle that we the pong ball that we created in week0。

 which is just a rectangle that's in the middle of space。

 but the difference is that we are actually this is being rendered and done in B 2D in Lua or in Love's physics system。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_16.png)

Box 2D's Ph system。So let's go ahead and look at what we're doing to accomplish this。We can see here。

Right below the usual boilerplate that we are creating a new world。

 this new world is taking a 0 x gravity， 300 positive gravity， which is kind of the standard。

 if you assume like a 9。8 meters per second， like a 300 will be essentially like a 3 meter per second downward force。

 or rather， sorry scratch that。And so you can see here we have a world which is being instantd with no gravity on the x axis and a 300 pixel application of gravity on the Y axis。

And then if you were to look down here。And see that we and this would be this 300 would essentially be。

 so love 2D's physics space has a 30 pixel per meter approximation for gravity， and if you assume 9。

8 meters a second，9。8 times 30 is almost 300， so we just kind of round up to 300 to apply roughly earthlike gravity if we assume the 30 pixel per meter approach to gravity。

And so here we can see， and we'll use that relatively consistently throughout the rest of the examples。

 but that's a tunenable parameter just like any else。

We have here the first instantiation of a body so we're calling love。phys。

newbody which takes the world that we just find up here。

 we're going to put it right in the center of the screen。

 notice that we aren't shifting backwards by x or y。

 everything in box 2D is relative to its center unlike love 2D's default。

 which everything is relative to its top left corner。

 so there is a little bit of difference in how things should be rendered and how physics should be sort of looked at in box 2D versus the AABB stuff that we've looked at so far。

 but it's a relatively simple shift if anything is simpler in a lot of ways thinking in terms of the center points of objects and notice that we are passing static as the string value to the end to tell love 2D that this box body should indeed just be some static thing that we have in our screen。

Now we're going to create the shape first， so we're just going to say， okay。

 I want a rectangle shape which is going to be 10 by 10 pixels and then I want a fixture that's going to apply the shape。

 the second parameter to the body relative to its center point。

 meaning that now it's going to know all physics calculations will be based on these sort of edges that take place within this rectangle and it will know based on whatever shape that we pass to it。

 if it's a circle if it's some other shape， it knows how to actually calculate all of the physics。

 even if it's not as simple as AABB anymore， to a properly effect。

 especially when we get past static examples， things interacting and colliding in very interesting ways。

 which we'll see some examples of。You can see an update we're just updating the world itself。

 it will defer all of the necessary physics calculations and then here which is common if we're not rendering a circle。

 you could just render a circle for most circular shapes and based on rotation it won't matter everything's fine。

 but in the case of love do graphics do rectangle if you were to rotate that rectangle then it won't quite work because lovedo graphics do rectangle doesn't quite work very easily with rotations but instead if we just say okay we're gonna to render a polygon at that particular spot in the game space we can do what's called with this body get world points function it expects its shape it needs to know its shape and then it can based on its body and the shape get you back all of the Xy pairs that will approximate will not approximate all the XY pairs that will equal the polygon's shape for drawing to the world love do graphics do polygon essentially can take any number of Xy pairs and it will create a polygon based on those vertices and connect all of them so whatever shape you。

Into it， it will just like it can take in a line or fill string just like love Do graphic do rectangle。

 but unlike love Do graphicstock rectangle， it can take any number of vertices， 3，4，5， however many。

 and this will return all of the points for whatever that shape happens to be and so you end up with the result that you get this square rendered right in the middle of the screen nothing really fancies happening we can't really tell that we're doing anything meaningfully different other than rendering a rectangle as before。

 but we' are actually using a polygon rendering function instead。

 and we're doing it all based on getting love 2D or rather box 2D's values for the body based on that body's shape that we gave to it。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_18.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_19.png)

So that is the static example now as we talked about there are also dynamic bodies and kinematic bodies so the next step will be let's take a look at a dynamic body so we saw what a static body is some folks might even be able to anticipate what the dynamic example is going to look like but let's just run the dynamic example and we'll see indeed rather than the sort of static rectangle being fixed to the middle of the screen and just there the whole time not moving not affected by gravity。

 we can now start to see the equivalent to when we started applying gravity and prior example is in our own games being applied and done for us by love2D's world and it's really not all that different than just doing all the same code that we did previously only now we're passing in the string dynamic to the constructor for a new body we're not calling static and then we get all of that functionality。

 all the gravity， everything for free， presuming that we define gravity as some positive value on the x axis here and you can manipulate these values to affect any kind of gravitational effect。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_21.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_22.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_23.png)

That you want， we're going to presume and assume is sort of consistent。Feel for it based on Mario。

 based on angry birds and the like bypassing in 300 as our example there， So not all that different。

 very different behavior。Now what we can do， recall that we have static and dynamic bodies and then kinematic is the sort of different type of body and this is a common type of body used in a lot of games。

 folks might be aware of many obstacles in games or things moving around that seem to affect other objects but themselves are sort of like defying the laws of physics and that's kind of when I think of a kinematic body that's sort of what I think of in fact if you were to think about the paddles in pong for example。

 those are sort of these kinematic bodies that can have their positions directly affected。

 but themselves are not affected by gravity， mean the ball for example。

 can sort of be affected by gravity in a sense， but it too can be modeled as a kinematic object if you were to think about it in a particular way like that。

 but it can be thought of as a dynamic or kinematic body。

 paddles are based on the fact that they're very confined in a non-gravitational sense to the Y axis and are also handcontrolled and not sort of moved by any sort of impulses or forces。

 those can be thought of as very classic textbook。bodies and so I came up with a fun little example here to illustrate what a kinematic body and a static and a dynamic body altogether might look like if we were to run this example in kinematic。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_25.png)

We'll see that we get。Very funnily， sort of the green ball falling to the bottom of the screen there。

 we've got this red line at the bottom of the screen， which is a static edge shape body。

Then we have on top or in the middle of the screen these three rotating rectangles and we haven't even done rotational collision typically because it tends to be quite a bit more complicated than just AabBB collision detection。

 notice that it was working just fine， the game was detecting the rotation and which parts of the rectangles were affecting the green rectangle。

 the blue rectangles are affecting the green rectangle， the green rectangle here is dynamic。

 it fell down， it was affected by these kinematic bodies and then it eventually fell to the bottom of the screen it hit the red plane and then it just came to a stop。

 it even had some sort of friction you saw it slide at the very end there。

 another thing that boxed exist for free， but these blue bodies in the middle of the screen。

 they're just statically there at least in terms of their X and the Y but the R rotating constantly。

 they're not falling， they're not affected by gravity but they do have this effect onto the green body which is that they were able to sort of bounce it around and then make it fall to the bottom of the screen and this I think illustrates the difference between what a static body is this floor at the bottom which doesn't。

But it it can still have things， for example， fall and touch it and be affected。But it's static。

 it is there it's fixed， it's not going to move， we have these kinematic bodies which are not technically fully static in that they are rotating。

 they're constantly moving， but they are imparting force onto other objects， the green body there。

 that dynamic rectangle that fell down was affected by those rotations。

 it was affected by the vertices of those rectangles sort of applying some force to it。

 and then it fell to the bottom of the screen and then it sort of came to rest eventually after a certain period of friction。

 we'll run it one more time just so folks can see that happen。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_27.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_28.png)

So it falls down very briefly， it gets bounced around a little bit。

 there's rotating forces applying to the rectangle and then it comes to stop again there's a little bit of sort of chaos and randomness that affects exactly where it ends up landing and how the rotation affects things but you can see that it does function very all three of these function in very different ways so let's take a look at the code real quick and see what we're doing for that it's not really all that complicated which is kind of the fun part。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_30.png)

So we have the classic as usual， the world， we've got the actual。

Dynamic body here for the rectangle we've got the shape of the rectangle as usual we're using a fixture for it。

 the ground is this static body which is an edge shape so love or rather box 2D and therefore love 2D by extension gives us this thing called an edge shape which is just a really nice way to sort of allow us to think of planes for example the ground and angry birdss is also an edge shape but just if you have borders in your game。

 they're often very well approximated with edge shape。

 they don't really need depth they're just kind of this hard barrier for things and so we're using the edge shape here or're just using the same fixture applying to a body in that way。

And then so if we have also these set of kinematic bodies that we want to render。

 we're going to need three， and so we're just creating a loop here， we'll create three bodies。

 three fixtures and we can actually use the same shape。

 the same shape can be used across multiple fixtures。

 multiple bodies and it will just essentially it's essentially just going to copy whatever that data is for that shape and then reuse it across the different fixtures。

 the different bodies but every body is going to move their copy of that shape around and therefore be able to calculate sort of how what the polygonal vertices of that should be if we were to try to get its position in the world at any given time for any individual body so you'll see here what we're doing is we're just creating three of those bodies。

 we're just going to shift shift them kind of like relative to the center a little bit。

and have them sort of offset and then we're applying this angular velocity so that we do essentially a full spin per second。

 which are multiplying by degrees to radians， most of the functions in B2D will take radians as their sort of unit for rotation。

 which sometimes can be less user friendly to think of in terms of degrees。

 but thankfully these are constants that I was able to acquire online。

 but you have degrees to radians and radians to degrees。Sort of constants here。

 these multipliers that you can use if you want to be able to think in degrees but then pass in some value into a function that accepts radians or vice versa。

 you have a couple of constants here that are handily being used and so here what we do is we essentially just say for every one of those kinematic bodies we can set its actual angular velocity。

 meaning it how it's spinning how fast it's going to spin and there's a lot of these kinds of methods across all of the bodies in box 2D and love 2D things like angular velocity。

 linear velocity so on and so forth， friction and all kinds of different fields that affect how things physically modeled should affect each other。

 and so we'll see a handful of those， but folks are encouraged to explore the docks to see all of them there's a great many of them that we won't have time to explore in tremendous detail but lastly we do see we have the love graphic do polygon actually drawing all of our various types of boxes and the ground as well which is just a line that we're drawing here across the bottom of the screen and then again another polygon for all。

Kinematic bodies that are spinning in the middle of the screen。

 which will just because their we're going to get all their points and they're just rectangles。

 it won't even need to worry about rotation， it'll just give us all of their individual points as such。

Okay， cool， I' going to take a grab a beverageverage real quick。我。

So with that now we've been able to look at all three main body types here， which is pretty cool。

 I think that example illustrates the difference between them。

 although it's a little bit underwhelming， so what I've gone ahead and done is added an even more illustrative example which I thought was super fun。

 which is called ball pit and if we go ahead and run ball pit here。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_32.png)

We'll see。Quite a different example and notice just also the sheer number of these bodies that are currently in our scene here。

 if I go ahead and hit hit space bar， you'll notice that there was a sort of heavier object。

 the square that's like semi- rotateated now towards the bottom left if I hit space its program such that we will hard set the X and Y to a different position so we can simulate the sort of physics occurring and I'll just go ahead and do this a few times and we'll see we can just keep repeatedly doing this and sort of everything sort of pertus and。

It's kind of a fun。Way to see a little bit more chaos。I enjoy it quite a bit because it illustrates。

 I think some of the power in having such a robust physics system that's pretty flexible。

 all of these circles here are also differently modeled than squares。

 they're all circular shapes and they're all very closely touching each other and some folks might even notice that just in a very organic sense。

 for example， as we just let the whole pile sort of like resolve itself。

 you'll see these physics calculations in these larger sort of like almost fluid type。

Movements occurring within this corpus of objects here。

 and there are a lot of things possible with physically modeling things in this way that are harder to achieve and certainly less obvious to achieve if we were thinking a bit more literally with physics like we've done previously where we've gone through and we've sort of modeled our X and Y velocity and things sort of bounce off at particular angles and so on and so forth。

 here， everything is just kind of automatically figured out in that way。

 and we're able to focus more on the emergent behavior， which I think is super fun。

 But this also is the same example just taken to the next level。

 we've got all these dynamic bodies that are in the center。

 we've got this sort of like static bottom。😊，floor edge plane and technically the square here is actually also a dynamic body。

 there was not necessarily utility in it being kinematic。

 but folks could imagine there being platforms in the middle of all of these that do illustrate sort of like the kinematic presence of objects with all of these moving around dynamic sort if you're in a ballpit as a kid some folks might remember have had this experience of just like jumping into something like this and it's just kind of fun and theres really the sky is the limit with something like this or like a gumball machine or something I I think about something like this and just somehow get a little bit of dopamine from it。

 but there are a lot of really the sky is the limit with stuff like this and this is just essentially using the fundamentals too because as we'll see later。

 there are things like joints which allow us to do a tremendous more but I would say that even with just these pieces we've essentially got a lot of the things that we might need to think about in terms of box2 in order to create angry birds because if you think about just the alien as a circle shape that can get launched。

A direction we'll look at something called an actual impulse which will actually set a linear velocity on an object or will apply an impulse to something to send it in a particular direction but that will have the effect of that thing then being taken over by the physics system by box2ti at which point it will as usual gravity will fall down or gravity will apply a force that makes the object fall down and then it will end up colliding with something in the world。

 we haven't talked about how to resolve collisions in a way that does things that are not just the usual bouncing off of each other because as we recall with angry birds if we pay attention a ball pit。

 for example， all of these things are sort of moving around and they're staying exist and they're bouncing and they're doing all these things but not none of them are disappearing per se and that is kind of an important detail with angry birds as you're playing angry birds and you're throwing the bird from one place to another。

 you have this effect where the bird is actually depending on how fast it's moving。

 it might destroy the obstacle or it might destroy the pig or s。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_34.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_35.png)

anmy alien and so we're gonna a way to resolve that and so let's take a look at a couple of things to sort of take us closer to that direction and then we can actually start diving into the code itself for angry birds before we you take a look at things like joints so a couple of functions that we should look at first is love mouse press which we haven't really looked at so it takes it an X and a Y and then a key and then we briefly might have looked at this but essentially this is what we're also going to look at in conjunction with mouse released which is if you press the mouse at an Xy and then the key you'll have this result where you'll know exactly on the screen where you clicked and therefore assuming that you then maintain a state of okay now we're clicking and dragging you can take that Xy and hold onto it and this is what we do with a slingshot right if folks recall as you're clicking and holding the bird on the left and you're moving it around it's sort of manipulating the trajectory and then once you release which is what。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_37.png)

This then gets looked at when this fires， which is another love callback that very similar to sort of the keyboard and mouse that we've looked at before。

This will actually have a different function that will fire on key release。

 which is when we want to finally by also extension， release the bird and therefore have it perform。

 send it on its way and then perform the collision should it hit something in our game space And so that brings us to what is how does collision actually work in Box 2D in a way that allows us to do this。

 Well， essentially there are a set of callbacks that boxox 2D will hold a reference for for us that will then fire and we can define those not all too dissimilar from the callbacks that we can define for the love's main functions like Key pressed or mouse pressed or key released or mouse released。

Except they're a little bit different in that they have different points at which they occur at a collision。

 there's a begin contact end contact presolve and postsolve set of callbacks。

 there's four stages of essentially resolving callbacks that you can decide to place your resolving code on that will' only actually need begin contact in today's example。

 but there are instances where you might need to determine at the beginning and at the end。

 certain things should take place and these all have different sorts of parameters and conditions within they're used and you can refer to them here at this link on love 2D if you want more detail on them。

 we'll only use begin contact。And so you can see here world set callbacks takes in four functions。

 those being just anonymous or named functions that we define。

 and so it'll store those functions in memory and call those every time some object in our scene collides with some other object。

 some body collides with some other body in our scene and therefore if we can determine by that。

 like okay， if this body is a bird and it's colliding with an obstacle， okay cool。

 how fast was the bird moving， was it moving fast enough to collide with it and destroy it。

 was it moving fast enough to deal a point of damage if we were looking at different materials。

Did it collide， did the player collide with the enemy。

 and if so was the player moving fast enough to defeat the enemy， and if so， despond the enemy。

 increment our actual score， or go to the next level， so on and so forth。

And you can do the same thing for is it an obstacle colliding with the enemy because every object should be considered relative to every other type of object and we'll differentiate those。

 we'll see how we differentiate those in our code， but you can see here they're all just four different functions that take place at different times So that brings us to the close of the core concepts we'll need to talk about angry birds conceptually and now we'll spend a couple of minutes looking through all of the pieces that actually bring this together。

 So I'm going to go ahead and close all of these examples。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_39.png)

And then most of all of this will be an A 50。And then we'll just run it again。

And then we'll see if we got a start state here which decides to for fun。

 create a bunch of these aliens that are squares， these are the enemy aliens that fill the space much the same way that the ball hit did it's kind of the same logic but we see we're using it again here just for fun like oh here's all the enemies right click to start and then these obstacles here are essentially three bodies everything is dynamic here at least in terms of the player and the alien and the obstacles and so what they're going to do is be they can have their X and y and their velocity set and updated manually which is what we're doing but at the time that we actually launch the bird or rather the alien as a dynamic body it will perform physics and collide with things like the obstacle and the player and therefore trigger those callbacks we talked about but right now we've essentially just hard set these obstacles such that they form this structure that's stable nothing is colliding with anything else technically speaking。

 everything is。Sort of there itss dynamic is resolved it fine。

 but things are ready to be collided with and as soon as I do this。

 you'll notice we have this predicted trajectory being rendered。

 which is using a sort of algorithm that's calculating the application of gravity over time to every frame from now until the time it would collide with which is about 1。

5 seconds that sort of endpoint of the trajectory by release it， dynamic operations will occur。

 we collided with two things， they both instantly called that begin contact callback function。

 they resolved， they got eliminated if folks recall from previously if I were to restart this。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_41.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_42.png)

Run this and then if I were to aim for instead notice we have some randomization visually occurring as well just for fun。

 folks might also notice that we have this ground at the bottom of the screen。

 it is a static edge shape that we are just essentially rendering tiles underneath。

 but if I were to aim for that bottom piece notice at the top piece because it's dynamic it will automatically just fall knowing that there's not an actual support for it。

It falls， it collides， everything rotates and functions exactly as it ought to。

 and so all the pieces are there for us to do some pretty sophisticated。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_44.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_45.png)

🎼prettytty sophisticated physics simulation with pretty simple parts。 nothing。

 none of which you haven't really seen minus the callback function portion。

 which we will take a look at。 So most of this， as usual occurs in the play state。 But really。

 there's not a whole lot in the play state that's of note。

 There is an additional feature that we added for folks。

 in case the bird kind of scrolls off screen a little bit。 I added the ability to。

 if you were to press left and right。 you can scroll on the screen。

 and you can see that offsets of things for fun。 And so that's something that we get for the play state。

 not of tremendous necessarily relevant value。 But sometimes the bird or whatnot， will transition。

 you could set this to scroll automatically。 if the bird were detected past a certain point。

 if you wanted to。 But that's all the playstates essentially doing。

 Most of the bulk of the work is actually in level。 So if we're to look at level， for example。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_47.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_48.png)

We'll come all the way up here， folks might see some of the callback functions taking place there。

 but notice that again as usual we have the world， we have a set of destroyed bodies。

 we're going to take charge of like which bodies should we destroy。

Love 2D does not want you to destroy bodies during the actual callbacks as they're being processed because if it's the way that internalback internally does physics calculations。

 you want to do all the removals after all of the callbacks have resolved。

 otherwise you run into some issues that can crash the library and so this is something that you want to not do in the actual callbacks itself。

 this is documented as creating stack overflows and the like if you were to not do this if you were to do it directly。

 delete your stuff directly， typically want to do all your deletions not in your callbacks。

 you want to it in some sort of cleanup post stage。

And there's references throughout of blog articles on iFor 2D that showcase different parts if folks want to dig into more detail for their own applications。

 so they want to pursue more complicated collision or resolving of collisions。

 we're only going to use the sort of begin contact stage。

 which is literally when two objects that are colliding begin contact。

And then you can notice that we have this sort of like types and then we have this thing where we're getting the user data of each A B object。

 the two objects that are colliding and we're setting it to true in our sort of table and this is where we can gather information about okay。

 what are the two things that do and so before we maybe even fully look through the begin contact function in detail。

 why don't we take a look at alien first which is going to be the sort of class for anything that is。

Interactive or rather our player that is actually being moved around on the screen。

 we're actually using both of them for the player and for the enemy。

 but we're going to flag one as the player and one as the enemy and that's how we're going to get that piece of information and metadata that allows us to differentiate between the two of them。

 but it takes a reference to the world as usual and then we're just creating the new body here。

 it's dynamic we're creating based on whether it's a square or a circle and this is a piece of information that we pass in to as its type because we want to differentiate visually between whether we are a bird in the case of angry birds or whether it's an enemy in the case of a pig in the case of angryng birdss。

Our tile set uses square in circle shaped aliens， so sort of arbitrarily I've decided， okay。

 we'll make the circles the player and the squares the aliens。

 and then you could do any sort of version thereof if you wish to。

 as long as you can visually differentiate them and they have semantic differences。

 that's really all that matters。Self-dot spreadite is just going to be like a quad index。

 same thing as we've always done before we create a fixture and then here we have this set user data variable here。

 the set user data function and what set user data does is allows you to actually put a piece of information onto a fixture and fixtures are besides just attaching shapes to your body。

 they also represent various aspects of this sort of way that collisions should behave and they can house metadata so that your objects can do fancy things like this of flagging okay this thing is an enemy versus this thing is my player。

 this thing is an obstacle， this thing is this breakable。

 this thing is this much strength has this much health so on and so forth。

 you can pass in the actual user data。Two this function。

 and we're passing it into the constructor here on alien in it。So。Then lastly。

 the important thing we should take a look at is when we render the alien。

 we recall that we rendered everything previously as sort of for these shapes。

So we had squares that we were rendering or circles that we were rendering previously in the ball pit or in the kinematic example。

 and in the case of a circle you can just render a circle， but in the case of a rectangle。

 you have to render a polygon for rotations。But when you're rendering quads。

 it's a little bit different in that you can't really all quads are thought of in square shapes and they are square portions of your textures by the way that they're designed by their nature。

 and so you have to render a quad as a rectangle and then you have to perform a rotation in order to achieve the same effect。

 whether it's a circle， whether it's a square you still have to draw a quad of your texture at a particular place and then perform a rotation on that quad。

 and so that's all we do here。 We do a sort of。the self get angle will actually perform that for us。

 it'll actually get the angle of whatever the body is currently in its data by the box 2ds world said to have it will actually give us that which we can then pass in to the render function or the draw function of loveoc graphics do draw it will then perform that rotation recall anything we draw that has a rotation should be in order to be fixed to its center。

 it needs to have its offset be at its center point， and so that's what we do here。

 everything is 35 by 35 pixels in the case of all of these sprites for aliens at least and so we draw everything relative to its center at 17。

5， 17。5 which then rotates based on the center point if we were to not do that it would rotate based on this top left which would have this weird sort of this alien sort of moving in a circle or whatnot。

 which is not the behavior that we want and so that's why that's what we have to do in order to draw the actual sprite even though we might be drawing circular aliens。

It's a square in the texture in the actual quad that we are drawing onto the screen。

 it therefore needs to be rotated at that stage and notice that we also have this get X and get Y that we can call on the body in order to get its actual X and Y world space。

 everything in box is relative to its center so we don't have to do anything complicated there to just we can literally just use the XY。

 but with that we now have the ability to draw render the alien。Okay。Need a sip sip sip。

So one of the last piece too also before we go to the next part might be love got physics that new circle shape。

 again another type of shape， we I don't think we looked at that specifically。

 there's a new rectangle shape which we have seen and then this new circle shape just takes in a radius of 17。

5 which gives us the full 35 by 35 circle object that we can then use for the circle type aliens。

 so that's how we create an alien。Now。Recall that we。Had the get user data。

 We had the ability to set user data rather， which was just a， in our case。

 it's going to be a string。 So if we were to go to the actual。Sorry， actually one second。

Brain farted on where the actual。Spot is where it gets created。

Ailey Martin Lu Parker is not where it happens。What the state， did you hear that notification？

Was that earphone that dinged？re。2。😔，And also the last thing too in alien is that we have this new circle shape that we're creating here。

 which we only looked at rectangles before， but we can also do this。

 we can create a new circle shape with a radius of 17。

5 and then you know that's 35 in either direction which gives us the 35 by 35 pixel alien and so therefore we now have this ability to create aliens in a way that works in our game world so then if we go back to。

The level that we were looking at previously。And then if we recall。

 we were looking at this get user data function， which this is essentially the crux of how our collisions are going to work。

 we're going to launch the bird at a certain point， to launch our alien at a certain point。

 it's going to then have to collide with fixed with our obstacles and then with the other alien and of course this means that we need to differentiate between the types as I alluded to previously。

 and so in order to do that if I scroll down here past all of our callbacks。We'll see。

That we do have a sort of like list of aliens in our scene that we're going to care about。

And then here， if we look at， for example， when we。To a table insert of our self aliens。

 this is sort of setting up the scene but we do have this sort of constructor for an alien which takes the world。

 it should be square as we saw previously that was for our alien and we're going to place it right about here which is kind of to the right side of the screen more or less and then this last parameter here is that user data parameter that we saw in alien which essentially just defs to calling set user data of a body or of a fixture rather on that body and so what this allows us to do is then say。

 okay if I get that user data which can be just about anything you want。

 but we're choosing to make it a string and we're just going to set strings on various types of entities in our world to set them as being whatever it is that we want them to semantically represent。

 be that the alien be or rather the player or an alien or an obstacle or so on and so forth。

We can just pass that string in， it'll set that in the fixture， and then at collision time。

 that is what is happening when we actually look at。The get user data function here。

 we're essentially just setting， we're going to essentially at the beginning of our contact。

 which is between two things in our world at this particular point in time， we're then going to say。

 okay， I'm going to create a table， I'm going to flag true on the key what we're assuming their strings so they will effectively be at key alien or key obstacle or key player or whatever。

We're going to set that to true。And then we can then say， okay。

 if types at obstacle and types at player meaning did we get an obstacle and a player colliding with each other and if we did。

 then we can get whichever of the two was the player， whichever one was the obstacle here。

 which is just doing a comparison on that get user data and then setting it to either a or B。

 then we can get the velocity of the player fixture here or it's body rather get because all of these are relative to fixtures。

 a body can have multiple fixtures that collide and so every AB comparison is technically done between fixtures。

 which is why we set the actual user data on the fixtures and not the body。

 but so we're going to essentially get whatever the linear velocity。

 meaning whatever it's going X and y value， of that fixture。

 the player in particular because that's what we care about if the player is moving fast。

 we want to determine that or fast enough， and then we can essentially take the absolute value of that vector and say if it's greater than 20 which is essentially just like meters per second。

Cumulatively between the two axes， then we can say。

 okay then in this instance then we're going to insert into a destroyed bodies table。

 which is what we cared about before， and a lot of these numbers to are tweakable as well。

 the higher the value is the faster the bird needs to be moving in order to affect that destruction that you trigger and then this goes to all sorts of variables that we see that we will see coming up。

 including friction and rest things called restitution for bouniness and so on and so forth。

But essentially then if we put this into the destroyed bodies， the fixture。

 the body rather through the fixture， into the destroyed bodies table。

 this means that we've essentially flagged it for removal from the scene later recall you're not supposed to do this in the callback because that causes issues with the way box study does collision detection it's a no note to do that so don't delete it inside the actual body here but we're essentially just duplicating this code in multiple places more or less but we're doing it through different means we're doing it through different creature so we have type obstacle and alien。

 meaning recall we can hit the alien ourselves with the player and that should of course defeat the pig s alien but what if we as we saw defeat that lower maybe that left obstacle therefore allowing gravity to bring down that top obstacle to also hit that pig well that should as an angry birds itself the game very well does that should also trigger deletion on that obstacle on that creature and we can do the same sort of calculation here it ultimately adds。

amounts to the same thing， and then same thing for the player and the alien。

And then player in the ground so if the player and the ground were to hit at that point we should stop essentially we should just create we're not really do anything because we don't want to actually stop the player。

 we don't want to do anything meaningful that will get taken care of by the physics engine。

 we'll just bounce， but we probably want to play a sound effect if we hit the ground。

 recall the ground as static the ground's not going to move anywhere， nothing really needs to happen。

 we're not also going to destroy the player if we were to hit the ground but we do want to like trigger some kind of a sound effect just for feedback and in general across all of these sorts of things you want to typically do feedback in that way and so if we scroll down。

Notice also we do have the sort of spawning of obstacles。

 which isn't really too fancy that we've seen so far。

 although then some folks will notice we have the vertical and horizontal flags here。

 which is sort of like setup code in our constructor for obstacle， which we'll briefly just look at。

 nothing too fancy that we haven't seen just yet， but in our update。

We can essentially do this function now， which is this loop。

 which is that will'll iterate over destroyed bodies in update and we'll just call this destroy method。

 which box 2D will then take care of the actual。Sort of work involved in safely deleting these objects from the scene。

 ensuring that there's no weird issues or stack overflow type things that might occur if you were to try to delete something in the midst of its actual of note in the scene besides just those actual core moving the character over to or rather shooting the ball over to the obstacles affecting various collisions and destruction and defeating the enemy which then triggers victory is the fact that we have this sort of sd trajectory which is kind of interesting so we can take a look at that in alien launch marker。

 also of note is this is where the actual player gets created and added to our world。

 we're actually simulating that we have a alien in our world on the left。

 we don't actually until we let go the sort of mouse click that we saw previously。

But if we come down here to update， we'll notice that we have this launched flag。

 which is essentially just like are we not launched yet。

 in which case should we render the trajectory if we are actually pressing the key to launch the alien。

 we're going to grab our coordinates， and then we're going to essentially set aiming to true if we did press if we did press left click is what one is。

And we're not launched， we're just going to set aiming to true。

 which is then going to toggle rendering that shows the trajectory relative to where our mouse is。

 but if we did release one and we're aiming。That means it's time to actually spawn the alien to go shoot towards the obstacles or rather to shoot wherever we left off wherever we left we released the mouse because that's going to set the impulse that should fire the alien or rather we set the linear velocity here。

 you can do this in multiple ways with box 2D， you can hard set velocities。

 you can apply impulses to objects to allow physics to do it for you so on and so forth。

 we are essentially saying okay where was your Xy， was it to the bottom left at this amount or this amount or this amount。

 and then depending on where it is， there's going to be a delta between that and the actual like point where we are rendering the bird。

 which is the slingshot sort of behavior in the game in angry birdsrd。

 and then so we can apply the sort of difference as linear  velocity going in the opposite direction which affects a kind of similar to when we set a velocity when we jump it's going to set of velocity in Mariio or angry birds or a flapybid previously。

 it's going to set an XY that。Box2D is going to take over because we're essentially instantiating a new alien which is going to know again it takes a reference to the world。

 it's going to create a new box 2D body which then takes on all that physics work and it's going to start to be simulated with Box2s on gravity and physics calculations and the like there's a couple of flags here like restitution and angular damping。

 restitution is like bouniness， the closer to zero， the less you bounce， the closer to one。

 like you essentially preserve your bouncing perfectly。

 there is no lost energy effectively and then angular damping is like how much your rolling is effectively is affected by。

Or rather is。Your angular damping affects how much your body is affected by gravity beyond just gravity where you actually lose like there's essentially air friction will apply that and rotation as well if you're on the ground too。

And so we want to set that to one， we don't want that affected any more than what the game is already going to do。

 but this could be effective for making sure your materials are rougher or smoother depending on what you're going for。

 one is essentially just a very light amount， like almost none。And so when we render。

 if we come down here。We'll notice that we essentially are going to create an impulse that is based on the difference between the base X and y。

 which is where the bird gets rendered on the screen statically。

 I'll rerun just so we can see what it looks like visually again which might be a little bit easier to talk about。

 so I'm going to run this。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_50.png)

And you notice that there's sort of like an alien texture being rendered there。

 that is modeling the base X and Y of the bird and is not going to。

This is not actually a physics object that's being manipulated， it is just a representation。

 it's just a drawing， or just drawing the texture there。And so if I click and hold left clickick。

🎼That the XY gets preserved wherever that was is preserved。

 it's still like essentially keeping track of that position， but now when we move our mouse。

 the drawing is going to stay on our mouse， it's going to keep rendering there but we're essentially taking the delta between where we are now and where that base X and Y was and we're going to create an inverse impulse that we're modeling with this arrow or with this trajectory with this set of magenta colored circles so we're essentially just saying what's the difference between the Xy and our current Xy which will be some sort of negative value right now because we went to the bottom left。

 but we want to invert that and turn that into a positive Xy impulse that's going to go or velocity that's going to go to the up and to the right and we do that no matter where we move relative to that center point it's going to affect that trajectory and also just again we showed this at the beginning but if you were to go here for example there's some code to just make sure your alien ends up back at the point where you started and doesn't continue doing physics calculation。

🎼And the light but it's all relative to this center point here which ultimately we can use that delta to then create a velocity that then lets B 2D take over and then perform all of its collision detection stuff。

 but because this is just kind of a weird sort of like UI limitation where we want to be able to model where we're moving the bird slash alien but still like know where our physics is going we need to have this not be a physics body。

 this is just a graphical representation essentially of where our bird is relative to the center point which creates our sort of impulse that then spawns a trajectory which will then get calculated by box 2D The way that we calculate that trajectory is we essentially do a simulation of what gravity will do to that impulse over time So if I go back to the alien launch marker。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_52.png)

Over 90 iterations， which is going to be 90 frames。

 which is going to be if we're running at 60 frames a second。

 that'll be well rather we're doing this over physics calculations and we're assuming we are always doing 60 physics calculations so this will be consistent no matter what。

 but essentially over 90 frames of a 60 frames assumed computer， we will essentially do。

We'll get the trajectory on the x based on that amount of time I over 1 over 60 and then we're going to multiply whatever the impulse x is。

 and then that's just going to essentially at any given point on that set of I up to 90 will calculate where it should be at the x should be at frame I we'll do the same thing here with the y axis only and there's a reference here that calculates the or shows the math behind why this works。

 but you' essentially have to perform gravity operating over time。

 so sort of like pixels applied per second per second。

 so acceleration of gravity applied to the sort of like some of all operations that have happened over two which is equivalent to like the additive series or like the triangular number of iterations that have occurred up to that point in time。

 which is going to be the accumulated effect of gravity on the y axis as it's applied over time over a set of however many frames you want to model it in this case for modeling it over9。

You could do this over any number of frames or 60 if you wanted to and then what we're doing is rather than rendering that Xy that circle every single time。

 which would essentially be this continuous line of information we're instead going to mod it by5 and just draw every five iterations which comes out to 1890 divided by 5 being 18 which will then just draw a little circle at that Xy of radius 3 which then gives us this model trajectory and allows us to know in advance using some math how we're going to actually look at the time that box 2D takes over our algorithm and applies gravity to our ball or R alien rather and so that's the crux behind the alien launch marker which is sort of like the key and sort of making sure that things work properly and we looked at that in the context of the obstacles and things calculating as well spawning an object into boxox 2D。

 we didn' actually look at the obstacle class itself， so here's what it looks like it's very simple。

Really， ultimately， it can take a horizontal or vertical sort of flag。

 which then we'll use to determine whether it should be wider than taller and then assign at the right quad as we need to as well。

 notice as we take a rectangle shape， new fixture。All these things are things we've seen before。

 but we are setting its user data to obstacle， which allows us to now okay this thing will be in the world and we will decide that it will be an obstacle at collision time and therefore takes on sort of new behavior doesn't need to really be updated or anything。

 B2 will do that for us and we just draw the right frame of assuming that we've spliced up a set of quads called wood here at that particular frame in this case we assume if it's horizontal。

 it's frame2 if it's vertical it's frame4 and we included many different examples I should say a few different examples of different materials here。

 we have a lot of different stuff if we go to the physics assets here， the spreadite sheet。

There's actually quite a lot of quite a lot of things， there's like for example。

 an explosive sort of like warning sprites sheet here。

 and then there there's like a glass version if you wanted this to be like a really brittle sort of material but then we've got metal for harder materials and then even stone so this is a really cool open source graphical set for angry birds or these kinds of physics games for folks for the problem set to be able to take this on and then add whatever they want for different materials having different sort of semantic purpose。

 semantic meaning for their durability， but that's ultimately the crux behind how the game works。

 you have this alien that launches， physics calculations occur and then at a certain point if they collide with your alien and the speed of the velocity of the bird is fast enough if it's cumulatively absolute value added up。

 same thing with obstacles， you decide that that's the threshold you want to allow for that to。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_54.png)

Create a defeated entity。 then you can just therefore know。

 if you've defeated all the pigs or whatever in your stage， just assuming mean you have multiple。

 we only have one in this example， but you've got multiple。 just check。

 do I have any bodies left that have that user data in the scene。 And if so， cool。

 then we've we've got or if not， then we've got a victory and if so。

 then just keep iterating and maybe have a limited number of times that you can do it so on and so forth。

 The problem set is gonna to be a little bit different and that there are other things worth exploring in this space and other aspects of A birds even that are worth exploring And so I think it's cool to now transition a little bit to talking about joints。

 which is going to be sort of the next stage in box 2D and sort of where we're venturing for the problem set as well。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_56.png)

Okay。So what joints allow us to do is kind of fill in this other missing piece which some folks who have seen B 2D might have seen。

 which is that you're capable of much more than just simple shapes moving around which is you can actually create compound objects of a sort and there are many types of joints by which we can accomplish this we'll look at a few simple ones but certainly the sky again is the limit there are just so many ways you can mix and match these things to create and physically model so many different things we'll be looking at things like pulleys and welds。

 revolute joints you can sort of envision most physical contraptions modelable inbox 2D and here's a nice cool fun example of somebody made on a blog and it's a very customizable functioning car device of sorts that's very sort of modeled off with axles and it's got like a suspension' there's a lot of really interesting aspects involved in building complicated objects like this and we'll be looking at some ways to do that so let's go through just kind of a whirlwind tour of some example。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_58.png)

That I whipped up that I think will give folks a taste for what's possible in the library and as part of the problem set。

 you will be required to sort of implement one of these so you can choose to your discretion but ultimately they'll be a tool for you to sort of impact gameplay and aesthetics sort of in a joint way and interesting way and this is common even in angerbirds nowadays I've seen there are sort of complicated moving things that are interconnected and joined and such so if we close out some of these things here。

 I'm going close all of these and if we go to， for example。

We won't spend a tremendous amount of time necessarily looking at the code on most of these。

 but we will just kind of quickly go through them， the simplest one that we can start looking at。

 for example， is a weld joint so if we just go ahead and start this up right here。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_60.png)

You'll notice that we've got like these two different objects， they're slightly differently colored。

 ones a lighter blue， one's a darker blue， and there's this red sort of circle right between the two of them and that is essentially marking the joint。

 the well joint and as the name implies sort of like they are welded together effectively such that they are two separate bodies。

 but are in fact affix to one another such that if I were to apply an impulse to let's say the top body by pressing left towards the left。

 you'll notice that it sort of falls over and it retains its shape overall， it is in fact。

Just hard welded like you would see a big metal structure welded together and I can break the weld if I just press B。

 you'll notice that the weld disappears and it becomes two separate physical bodies。

 rectangular bodies that are just now dynamic rectangles much like we've seen previously and so this is probably one of the simpler joints to look at if we were to go over here to our code this is going to go ahead and scroll up just a little bit。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_62.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_63.png)

You'll see and again we won't spend a tremendous amount of time looking at the specifics of all of these things。

 we have a ground much as we did before which is just an static edge shape and then if we go down here we can see we have a head body and then a handle body these are two separate bodies recall we have the actual head we have the handle those areix with a sort of anchor point being the weld in the center between the two of them roughly and so what we do is we just as is usual we apply fixtures to them and then we're going to create this new weld joint here。

Wwhich is going to be placed at about the start x and start Y plus head H divided by 2。

 which is going to be right about where we spawn the actual head itself。

 but it's going to be slightly in the center between the two or sorry the handle itself but between them a little bit and then given the handle body and the head body together as parameters to this that will tell the well joint that okay your goal is to fix these two together in this static way and then if we just were to go over to for example this key pressed here and press B。

 you can see we just destroy it， otherwise it'll for all intents and purposes be treated like one object that now can just kind of move around and be physically modeled like anything else and you can imagine just creating and welding some big thing together the static thing and that might work great for something like a building or some sort of larger structure that is composed of these multiple bodies and then maybe by affecting some sort of like force on certain things you can begin to delete some of those weld。

and then therefore crumble the structure while still maybe preserving the underlying pieces。

 so that's the example of welding。 So if we were to， for example， then，Go to， let's say。

 something like a pulley device。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_65.png)

Which is fun if we go ahead and run this。You'll see that we've got what looks just like a simple pulley I can press the arrow keys to move one side or the other in this case the left box is weighted as twice as dense as the one on the right so the pulley is going to skew to the left it's always going to fall to the left much like a pulley system would work in real life where you've got one thing and another thing that sort of have a sort of like invisible string connecting them that will affect each other is sort of。

Vertical movement that's effectively what's happening here。

 If you apply a force to either of these up or up or down they are capped at their actual like invisible strings so to speak is capped at a certain length and they will always retain that difference between the two of them and so we can go over to our code here if I go up to the actual part where we're playing a joint you can see we've got like two different bodies A and B which are part of the Poley we're applying a force to them which apply some sort of positive or negative force or impact on a particular axis x or y we're just doing everything on the y axis for right now and then this Poley joint here effectively takes in a set of parameters the body。

 the grounds for the actual places where the strings would be in the Poley effectively and then the positions of where the box A and B happen to B。

 and then that gives you a pulley system and there's a lot of these types of again the folks can go to love 2Ds physics actual documentation。

 the wki and see all the different joints that box 2D has in B 2D's documentation will。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_67.png)

larargely aligned with love 2Ds， assuming that the version is similar and a boxox 2D is up to version 3。

 something now and love ships with either 2。3 or 2。

4 and so depending on which version of love that you're using。

 so some things maybe if you're looking at newer boxox 2D documentation。

 some things might be too new for what's in currently in love 2D so I encourage folks to maybe stick to the 2。

3 or 2。4 series， but effectively if you stay with the love 2D documentation and their love do physics namespace or box 2Ds with and you do the sort of like calculation to get to the love's functions or consult loves wiki for their functions。

 you can arrive with the same understanding of what the different parameters do。

I'm going to go ahead and open up that was the Pol example， let's go ahead and open up pendulum。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_69.png)

And if we run this， you'll notice that we have now an anchor point that's kind of in the center of the screen is kind of like up to the top。

 you'll notice we're just rendering a line that sort of goes from whatever the anchor is wherever the joint is effectively to the actual body that the joint is connected to so if I press left or right I can start to nudge this pendulum left or right and I can spam it in multiple directions you can see it kind of like always staying a sort of sort of the same distance radiuswise away from that joint as a pendulum would and eventually I can kind of have some fun and make it go all the way around if I keep doing it they almost did it if I。

There we go got it， got it to do a full rotation， and so it stays very fixed to its joint。

 it's always going to be the same radius away from it。 and so if I stop that we go over to here。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_71.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_72.png)

We can see we're creating the anchor point and the ball and then we have the actual it's called a revolute joint that accomplishes this meaning that whatever the joint is affixed to will revolve around it and so we are accomplishing that again we have an anchor and a ball then the anchor X and Y and these are just various variables that it expects in a particular order that you would look at just by looking at the wiki so that's pendulum then if we look at the same example but this one is called a rope。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_74.png)

If I run this， folks might notice that it looks very similar to the sort of pendulum idea。

 but rather than using a revolute joint in this example。

 we've decided to use a what's called a rope joint。

 meaning that now no longer will it hard enforce that unilateral distance along that joint now if I we were to spam some directions and try to get it up close。

 you'll see that it does function much more like a tether ball where the actual rope is sort of like。

Not hard defined as being that unilateral radius away from that sort of anchor point center。

 which allows you to simulate what a rope would do in something like a tther ball instance or whatever you want to use it for it's very similar to a revolute joint in this instance。

 only it's just a it's functioning like a rope instead of a of a hard metallic pendulum or the like。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_76.png)

And so there are many examples of that。

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_78.png)

And that is essentially the gist behind what joints are and folks will be required to implement at least one of those for their problem set。

 there's lots to do obviously beyond what we just did even today there's for example。

 more shapes theres with polygons you can model in box 2D any kind of shape that you want to you could have very complicated geometry for example。

 in even Ang birdsrd itself as we saw in the screenshot there's like triangular pieces and whatnot and those can be modeled using polygons in boxox 2D you can have levels that are separate only at one level。

 but maybe you have a table that creates obstacle definitions that you can then instantiate and then load into box 2D every time the level loads and you've got multiple aliens。

 you've got this big complicated structure that you've defined in code that you've tested as stable。

 its of different materials so on and so forth which we didn't have the chance to do and then this is also part of the problem set which is that in Abirds you have the one bird。

 the red bird that you start with that just moves in a direction it hits something its velocity will determine。

or it breaks something， but maybe you want to spawn off three birds as is the yellow bird or maybe you want to blow up or the blue bird and then you want to blow up with I think it's the blackbird if you press a button after the bird goes forward。

 it will explode and then cause damage to the surrounding blocks and then of course different materials which is also part of the problem set which is can you affect a。

Differing amount of damage to something and cause。Cracks。

 so they like to represent that you are partially through breaking something but haven't fully broken it。

So the assignment for next week will be。When you hit the space bar after you spawn your first bird。

 you should spawn three birds and they should essentially have the bird go the normal bird that you were shooting should keep going。

 but then two more should spawn off， going a certain angle away from that center bird and all three should apply collision in that instance。

You want to also add glass and metal to the world and these should have differing numbers of hits they should take in order to break。

 I would propose glass is one， what is two， metal is three。

 but folks are welcome to choose whatever they want for that。And then also， as we talked about。

 when you do make them take multiple hits， for the ones that are not just one hit。

 the second hit should affect a crack and the third one can affect a deeper crack should you wish or should just render the same crack。

And then lastly。Incorporate at least one joint in your level in some way that is tied to the mechanics of the game。

 It should affect the game。 either it be an obstacle or something that the player can interact with that could therefore。

 by proxy trigger a collision onto a bird or something or an enemy so on and so forth。 So next time。

 which will be our last lecture for the course， which is' already。

Come to an end and it feels like it hasn't been that long at all。

 We're going to look at Pokemon this is an example of the actual battle mode of Pokemon which has a couple of modes to it also has a top-down walking view which will talk about gridbased movement and sort of locking yourself to this smooth gridbased topdown movement much like in Zelda which is classic of Pokemon but also be an opportunity for us to explore two huge topics that being not just state machines but a state stack which is an evolution of the state machine that gives us very interesting robust sort of memory behavior from prior states that we were using previously like pause states and whatnot and also it gives us a chance to look at Gui elements as you can see even in this example we've got a text box we've got progress bars and the like and Pokemon's got a lot of UI and so it'll be a great opportunity for us to break down various UI elements and take a closer look at those so that was lecture 6 A birds where weve got to dive into box2D and very interesting physics look forward to seeing what everyone puts together for their own projects this is lecture 6 we'll see you next week。



![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_80.png)

![](img/9c3de7f23cdbbb15bab4f8b08a5d0b11_81.png)