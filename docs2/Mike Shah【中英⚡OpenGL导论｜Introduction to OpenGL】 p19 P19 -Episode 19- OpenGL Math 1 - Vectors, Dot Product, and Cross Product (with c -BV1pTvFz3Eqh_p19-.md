# Mike Shah【中英⚡OpenGL导论｜Introduction to OpenGL】 p19 P19 -Episode 19- OpenGL Math 1 - Vectors, Dot Product, and Cross Product (with c -BV1pTvFz3Eqh_p19-

![](img/915ef04e3cab8ef4cddf0b65c89e1157_0.png)

Hey， what's going on folks This iss Mike here and welcome to our next lesson in the modern Open GL series In this lesson。

 we're gonna be talking about some mathematics involved in OpenGL。 So with that said。

 I hope you went ahead and watch the previous lesson where we are setting up the GL mathematics library If you weren't able to do that。

 you might want to watch that lesson prior to this one because we're actually going to be explaining the mathematics as well I'll demonstrate the actual C+ code to use some of the tools that we're gonna learn about today So with that said。

 go ahead and check in the description if you need to get to the previous video in the OpenGL playlist or check out our communities or membership options or all those great things that you probably already know about with that said though let's go ahead and dive in this lesson and talk a little bit about some mathematics。

 So what I'm going go ahead and do to just go ahead and get us started again is to set up a basic code for us So again I've got here set up how to compile the GLM library and again I've got the thirdpart GLM library here with my main here and I've kept all the includes here from our previous lesson。

😊，And just so we can get started as well as just two vectors here that we can create here， Okay。

 so let's go ahead and talk a little bit about the mathematics， which is this grid above me here。😊。

And what I see above me here is what's known as a 2D。Cartesian coordinate system。

And today we're going to be talking in 2D because it's a little bit easier for me to illustrate。

 but all the rules apply in 3D， if you're following this series。

 you're probably interested in 3D computer graphics。

 although again these same principles apply to 2D or 3D likewise， so with that said。

 the very first concept that I want to demonstrate and we'll go ahead into our code here to show this as well。

And let me go ahead and give us a little bit of room here is we're gonna to be talking about this data structure here a V3 Okay so what exactly is a V3。

 I'll make a little bit bigger for you here。 Well this is a way to represent an X Y in a z point。

 So for instance， I have one martier at 1。0 f1。0 and we're just going to ignore the z component for now。

 So that would plot some point here for point a and then point B would be about halfway across the x axis and on the y here and again。

 we're just ignoring the z but there would be our point B。 So we just plot those there。😊。

Now we use the Vc3 data type to represent two things。

 which can be a little bit confusing to start The first is just as I've used it to just represent a point。

 some quantity， X， Y and Z。But what we're going to be talking about today。

 which is our sort of mathematical tool， is this thing known as a vector。 Okay。

 so here I'm actually creating some vectors and I'll go ahead and just spread them out just a little bit and let's go ahead and put zero in the Z coordinate just so we don't worry about them。

 Let's go ahead and make it three。😊，0ero， something like this， and maybe 4 here in the Y axis。

 So I'll go ahead and redraw these just to give us two different quantities here。 So vector a。

 which is going to be3 in the X axis。 So here it is at this point here。

And I'll go ahead and label it。 But this time when I draw it。

 I'm gonna draw it with a little arrow at the head here and coming out of our origin here。

 So let me go ahead and just draw this point here。 Now the origin is a specific point at00 of our coordinate system and since I'm just talking in 2D today。

 I'm going to go ahead and simplify our view of things just a little bit and just give us one of these quadrants here where we'll be focusing in this space。

 of course， in the game， you could go negative or whatever and that's fine。

 but let me just focus us here for moment and then let me go ahead and do something the same for our vector at B here and I'll try to again get this as close as possible。

 So I'll go ahead and just label this here with B here and you'll notice again that we have this arrow here which is the head of our vector So let's go ahead and label these and for both them this is the tail of the vector so what is a vector。

 how is it different from a。PoinWell， a vector is something that has magnitude and direction and you can sort of see or imagine this as if you're throwing some object and let me go ahead and get rid of our annotations that it's traveling along this vector。

 each of them。In this direction where the arrow is pointing。 So again。

 imagine yourself throwing a baseball or these types of things。 Now。

 this becomes particularly important in computer graphics because oftentimes we're going to want to know the direction or where something is facing or moving from various lighting and rendering techniques。

 So that's why we need to talk about this as our basic primitive here。😊，So with that said。

 let's just go ahead and create our vectors as we've done here A and B。

 and I'll go ahead and just print them out here。 Now before I go ahead and print them out though。

 what I want to go ahead and do is talk about one very important quantity regarding these particular vectors And that is their length here。

 So again， let's go ahead and just take one of these vectors here， vector A， for instance。

 and I've got my vector B and the length of this vector is well。

 how long or the size of this vector is so we can easily see that from a it's three units and B。

 it's four units。 but let's go ahead and compute it just so we can go ahead and C。

 So I'm just going to go ahead and do a simple C out statement here。😊。

And then I'm going to use the GLM length function for a。And I'll put an end line here。

And let me go ahead and give us a label here just so we can see things a。

And let's go ahead and do the same for。vector B。And let's go ahead and compile。See our result。

And we can see that A's length again， is 3 and B's length is four here。 So how did we get to this。

 Or what if I had something that's a little bit less trivial。

 So let's just go ahead and give ourselves one vector to look at here。

 And this time I'm going to put a at 3。0 and 4。0 here。 So let's go ahead and clear our grid here。

And again， we're going three units along the X axis， four units on the y axis here。

 and that's going to land us something like this or exactly like this。

 and this is our vector here with the arrow here and we usually call this since we have this sort of origin point here。

We would say or how this is represented in text is usually with a bold vector and usually with a little arrow above it to indicate that this quantity is something with a magnitude in a direction。

 It's not just a point here。 So I'm being careful not to draw points and just to draw the arrow ahead here。

 so you know， that's a vector。 But let's go ahead and see what the length of this vector is here。

 Okay， so I've got to recompile my program。 rerun it。 And actually， before I do that。

 let me go ahead and put a little colon in here。 just so you can see a little bit more cleanly。

 What we've got。😊，And well， we go ahead and see that our vector's length is 5。 Okay。

 so how did we get to this or how do we compute this distance？ Well。

 some of you might remember your Pythagorean theorem here， where if I go three in this direction。

And for in this direction， I can take three squared plus4 squared equals c squared here。 Okay。

 so c squared here，9 plus 16 equals C squared，25 equals c squared。

 So I take the square root of each side。 C equals 5， and that is our length here。 Okay。

 and we usually indicate that with the double bars here to indicate length here for our vector。

 Sorry， I'll write that just a little bit meter。 So the length。Equals5。 And we usually put bars here。

 Now， this again comes from your geometry。 So you might remember this。 and it's the same in 2D or 3D。

 So it's the square root of the sides here。 So I'll say in the x axis that we were moving in this direction。

 and then the y axis that we're moving up and down。 So x squared plus y squared equals R length。

 okay。Now， if we're in 3D， I just go ahead and add a separate the other component here， z squared。

 and that'll also compute the length。Now we also have another word for this。

 so I'm going to go ahead and clear this out as we do another example here。

 and you'll hear this as length， or remember what a vector is。

 something with a direction here and a magnitude， so it's sort of synonymous with magnitude。😊。

And again， think about this in this sort of physics sort of world or domain of how much force you had so again if I was throwing a ball or something and it was traveling you know across this distance here starting from your position at the origin right it's traveled five units out and in this direction that was the length of how how far excuse me you through the baseball okay so hopefully that makes sense and we can see how we get the length here。

Okay， now whats something， or rather the way to SS is something that's important in computer graphics is that we often work with what are called unit vectors。

 So again， I'm going to go ahead and let me write this term down here。😊。

And I'm just going to write this as unit。Vctor， so we know we're currently talking about here。

 And I'm just going to indicate this as a with a little hat on top of it。

 which means this is a unit vector。 and what that basically means is。The magnitude or length。

Magnitude。Is one， okay， and why is this a nice property you to have。 Well， you know。

 I'm not going to go super deep in this series unless folks want it to probably belongs in its own series。

 But the idea is， if we have something that adds up to one here。

 that tends to make the mathematical formulas that we utilize very simple because one times anything。

 you know， the result doesn't matter。 And we're going to see that in a moment with something called the dot product that is very useful。

 So you will occasionally see。😊，A hat。 This makes it a unit vector。

 And how we do this is by normalizing our vector。 So let's go ahead and try this out here。

 So I'm going to go ahead and do print out。 And I're just going to put a hyphen hat。Which， again。

 is how you might see it in text or just as we know， the normal vector。

And let's just go ahead and normalize it。 So GLM normalize a。

And let's go ahead and just print that out。Just so we can see。Oops， let me go ahead and see。

We're getting all these template errors here， so sorry。

Let me go ahead and just give me one second here。 I believe in the last video。

 we can't just print out the vector， so we need to do GLM2 string here。😊，And for our vector。 Okay。

 so let me just go ahead and get everything here on one line so I can read it as you're learning this again。

 And I'll just make things a little bit easier。 So let's go ahead and give that a try now。

And that's working much better。 And now we can actually print this out and we can see our normalized vector here。

And again， you could kind of do this in your head if you wanted 0。6 squared would be， you know 0。360。

8 squared， it would be 0。64。 And if you add up those components， you get one。

 take the square root of that， then you get one here Okay so that again。

 we can confirm that it is actually a unit vector。But just to be sure。

 let's go ahead and add it in here。Actually， let's say A。Nized。And I'll print that out。

And let's just go ahead and get the。Length here， so we're going to normalize it。

And then compute the length of our normalized vector， which should just be one here。 Okay。

 I don't think I'll need a two string here。 Let's see if it complains。 Yeah。

 it's going to complain because that's just a scalar quantity。So let's just compute the length here。

 and we should just get 1。0 here， let's see。And there we are here。 Okay。

 so we again have the length of a any unit vector is just going to be one。 Okay。

 so hopefully we understand these concepts just a little bit better。

 and we can start to see how they're being coded here a little bit。 Okay。

 now let me go ahead and rewind this one more time and tell you about some important tools because。

 you know it's interesting enough to have this vector here， a。

 but what about if I have some other vector。 I told you it might be interesting to。

 you know know the direction of this particular vector。

And you know there's different operations we can certainly perform on these vectors like again。

 if you want to think about， you know， here's a person here。

 let me draw this and you imagine you start at the origin and maybe you you know travel or fly in this direction and then you have another。

 you know， do another traveling up here and then you're you know in this direction right。

 we can certainly do vector A plus B。And then we get the result of， well。

 let me write this out for A of x plus B of x。A of y plus B of y。

 So all I'm doing is summing the individual components of this vector and this vector。

 and that gets us the final position。 So we can certainly do things like addition and subtraction。

 which just add the particular components of each of these vectors。

 But one are the tools that's going to be very useful for you。 And let me model another vector here。

😊，And I'm drawing them at the origin here， but it doesn't matter if if I draw this vector here that I have here。

 and let me be careful I， if I start， say from this point and I go1 to3，1，2，3，4。

 and I draw this vector。 these vectors are equivalent A and B。

 they both have the same magnitude right， I've gone three units over and four units up on both of them。

 So they're effectively the same vector。 Okay， when I do this。😊，But because again。

 a vector is just a a magnitude。 So it's length。 So those would both have the same length and the directions would be the same。

 Okay， but just for simplicity， I'm just kind of drawing these from the origin here。

 but let me draw another vector and I'll draw it again here。 Let's draw it as vector B here。😊。

And I'm going to draw it up to7 here and I'll label it B with a little error on it。

 So we know it's a vector again， sometimes in the literature。

 you'll see them bolded fonts to indicate their vector， but that's how you know。

 And I put it at 7 here。 So let's go ahead in our code and do something equivalent。

So we're at seven here and zero。So the question that I might ask you if you're just watching this is how similar is B to a okay if I'm throwing a ball you know over here and over here。

 are they moving in the same direction or how similarly would they be moving in the same direction。

 that's a question you might want to know here。And the reason we might want to know this between two quantities is so we can find the angle between them Okay。

 and I guess the the ball isn't as great of an example。

 so I'll give you just the real world example here where when we have a light source and this is something we're going to be talking about in this series here and I want to know if this light source。

😊，Is directly above， it's at this sort of position。How much of that light source？

You know what what angle between this actual surface here。

 and let's pretend that this is an actual surface here。

 so this is the you know top of the table or something。And again。

 I'm just quickly drafting this right on top of this table here。

 how much would actually be hitting this surface， so we need some tool to figure out what this angle is。

😊，And the sort of experiment that you can do for this。

 and I'll go ahead and just do this now because this is what I usually do with my students is I take a light here。

 So apologies that this is gonna be a little bit bright。

 I just go ahead and take it and point it directly at something。

 So if I point it directly at the camera， it's gonna to be very bright right thats sort of makes sense。

 But if I change the angle so that the direction of the light traveling isn't facing towards you is perpendicular。

 none of that light is hitting you right now So it is kind of interesting to know which direction the light is traveling and you can see that you know more of that light is hitting a surface then we are lighting up that surface more。

 And this is exactly what we do is sort of a hack in computer graphics to estimate or approximate lighting well enough in realtime applications。

 so anyways， what's the mathematical tool that we have for this。 Well。

 it's something called the dot product。😊，And the dot product here tells us。How similar。

To vectors are。 Okay， that's the way I like to think about it。 you know， for。

 for what these are doing。 And if we know how similar they are。

 that is the direction that they're sort of traveling on their magnitudes。

 then we can figure out this angle between them。 Okay， or actually， this really just depends on the。

Direction to get this angle here。So anyways， let me go ahead and just show you how we compute this here。

 Okay， so let's go ahead and take our two vectors here。

And looks like I added an extra character here。 So I'll get rid of them here。

 And let me go ahead and print out the dot product here from GLM。G OM。

And the function call for this is simple enough， it's dot and A and B。

And we're going to have to cast this to a string so that we can get a nice printout here。

And let's go ahead and put a end line here okay。Okay， now let's go ahead and try this out here。

 Go ahead and compile this。 Oops， or sorry， yeah， I'm not gonna need the string quite yet。

 Sorry about that。 Yeah， let's just compute the dot product here。

 because I guess that's like the question。 you might ask yourself you're first learning this。

 What am I actually getting out of this。 So anyways， I compile this， I get the value 28。 Okay。

 so how do we get that value 28。 Well， I'm actually， what I'm doing here is I'm multiplying。

Each of the components here。 So again， the component of a， the x component times this component。

 which is gonna to be 0，4 times 7。 And that's what gives me 28 to then 0 times 0。 Okay。

 that's what the actual component by component multiplication is。 So again。

 let me just go ahead and highlight this。 So the dot of a。And B。Equals3 times 0 plus4 times 7。

Plus0 times 0 because we're just ignoring the Z or the other way to drive this A X times。

B X plus a Y times B Y plus and I'm just going to ignore the Z here。

 but this is what we are actually doing here。 Okay。

 so the components multiplied and then there' some。Now value 28 at this point。

 if I told you is giving us some sort of angle is it's kind of hard to read what that actual value means。

 So what we usually do in computer graphics is we use one of our tools here。

And we normalize our vectors here。 So let me go ahead and normalize our vectors。

 So we're going take the dot product and normalize a。And a separate line here。I'm going to do GLM。

Normalize B。And make sure I spell everything out。And now I'm going to rerun this here。

And now I get a value0 a tier okay， so since I know these are both unit vectors。

 so they're both going to be， you know smaller vectors here， you know。

 something very close to the origin， something like that， right。

 I've normalized them so they are again， unit vectors， they fit within our unit circle。

I get this value 0。8 now what can I do with this here Well。

 this is where I can use an actual function here。And I can actually get the angle between these。

 Okay now usually between in computer graphics。 Since these are both normalized。

 we get a value from negative one to one here。 And basically that's something that we can do to use and say。

 hey， this is receiving on this particular surface 80% of the light here。 Okay。

 is' going to hit this surface。 So don't make it you know， fully lit up but make it 80% lit up。

 Okay so that's where you can just directly use the 0。8。

 but sometimes you might want to use or figure out the actual angle here。

 So what we going to go ahead and do。😊，Is copy this here。

And let's just go ahead and store our angle here。So the angle equals this here， this value here。And。

嗯。Or actually， let me， let me write this out a different way because this is actually going to return us the。

Dot product here。And then what I'm going to want to do is I can use the math library here in C++。

Let's use standard arc cosine here。Of our dot product results。

 And let's go ahead and see what this gives us here。 I might need to include the math library。

 Let's see if it is。 Nope， this gives us a value 。64。 Okay， again， what can we do with this？ Well。

 this is actually give us the angle in， or excuse me， not the angle， but in radance here。

So I need to multiply this here by 180。0 divided by， let's see if M is defined here。It maybe。

 it may not be。And this tells us this angle is 36 degrees here Okay， so it's pretty， pretty similar。

 right the actual angle， if you took your hands here and just kind of angled them at 36 degrees。

 they're moving in a pretty similar direction right again， if I'm throwing a ball here。

 they're landing， you know， maybe in a similar region。

 Now let's go ahead and play with some other vectors here。

And what I'm going to go ahead and do just to make something completely obvious。

 let's make this move 0。1 here。And vector A at 1。0。Okay， so they're already normalized in a sense。

 but I're going to leave our code here， but you see that they're moving across different axes， Okay。

 so let's go ahead and save this code here。😊，I'll go ahead and rerun this。And print this out。

Here we are， and we can see our angle that's printed out is 90 degrees， okay？😊，Now。

 let's go ahead and see。 so again， they're moving completely perpendicular。 So again。

 let me just draw that out here on a little mini axes here right。

 vector B was moving up in this direction。 Here's B and vector A is moving in this direction。

 So again， they're going perpendicular。 Okay， so 90 degrees。

 Now I want to just go ahead and show you， you know， I computed the angle here。 But let's actually。

 again， just print out what the dot product is。 Okay。😊。

And I'll tell you why this is important for you to know and let me go with it and say dot is。

That product。Let's go ahead and spell things out here， dot product。And just put an end line there。

 Alright， So let's go ahead and run it。 to get some of you who are familiar with your geometry will realize that the dot product is 0。

 Okay， so just to bring this full circle here， the idea is， well， how similar are two vectors。

 That's what the dot product is。 If you get a zero， that means they're moving in。 you know。

 totally perpendicular directions。 Okay， they're not gonna get any closer to each other as time goes on。

 you know， that's the sort of idea。 so let's go ahead and see what this relationship is。

 if I make these vectors the same here。 Okay， in our actual code here，0 and 1。0。

 So this time the vectors are the same。😊，And our dot product is one。 Okay。

 the angle between them is 0 because there's no difference， right， They're moving exactly together。

 Okay， and let's go ahead and try the final extreme case。 If I make this negative one。

 So they're moving in completely the opposite directions。The dot product is minus1。 Okay。

 they're moving as far apart as they can right， if you can imagine these vectors as enemies or something。

 they're just running away from each other Okay， and thus the angle between them is 180 degrees okay。

😊，So that's dot product。 That's the code for dot product。 Here's the derivation。

 Sorry if I was covering that up a little bit here of doing each of the component additions here。

 Okay， so that's dot product。 Let me go ahead and give you one more tool。

 and then we'll go ahead and wrap this up here。😊，For something else that is useful for our vectors。

And for this one， I'm going to need to draw here。 so let me go ahead back here。

 we going to need to draw a 3D system here。Just to help us out here。So again。

 we can ignore our coordinate system here。And again。Here we are。 Here's our X。

 This is going to be our Y， the positive and the Z positive here。 now， if you want。

 I could do a lesson on why that is， but。Why Z positive is coming out to us。

 That's again because we're using a right handed system and open GL or you can Google that。

 But the idea here is I'm going to go ahead and draw one vector out something like here。

 Let's go ahead and let's again just start with something trivial here。Maybe 4，0，0。

 something like that for our vector， and I'll go ahead and draw a vector here。

 let's go ahead and just make this one0，40 okay。All right， so let's go ahead and。

I'm just going to comment this out now because I want you to have you know see all the code at the end here。

So let me go ahead and just comment all of this out here。And give you another tool here。 Okay。

 so let me go ahead and just introduce the tool。 And the tool is for the cross product。 Okay。

 so what I'm going to go ahead and do here。 and I'll just go ahead and put it at the top here。

We're going to create another vector here。 I'll explain what this is vector C。

 and this is going to be the cross product of A and B here。 Okay。

 and let's go ahead and print this out。And give ourselves a label。Cross product。Okay。And。

So the cross product is going to be GLM to string of C。And let's give ourselves an end line here。

And then I'll go ahead and define it。 but let's go ahead and run it here。

Make sure it runs and we get a cross product here， oops。

 and let me put in our numbers that we are using here。That's we're using for a。

 we said let's just going to be 4，00。And this one can be zero， four， something like that， okay。

 there we are。And let's go ahead and here we are。 Okay， so our cross product。

 we get in the Z direction 16 here。 Okay， so let me go ahead and draw this one。

 I'm just going to draw the dotted line here。So something like this in our diagram here is our cross product。

 Now， if you look carefully at this， what did this generate for us？ Well， I mean。

 this looks like in axes， right， They've got something here， here and here。😊。

But the actual result is of this new vector， and let me make this even a different color here。

Just we can see。A little bit clear， there we are。And let's go ahead and draw this here。Ohpe。

 there we are。All right， so sorrys a little purple here， you know， something in this direction， 0。

016。Okay， is a new perpendicular vector。 Okay， so let me go ahead and bring this back here。

So cross product。Gives you。A perpendicular。Vectctor。Okay。2。Two other。Vectctors。Okay。😊。

And that's the idea Okay， even if we didn't normalize them。

 we can still see that this is perpendicular and again， normally as I tell my students。

 we usually almost always normalize our vectors unless we need to know that magnitude for instance。

 to model some sort of force but that's the idea of what cross product is giving you and again。

 sorry if you can't read this as well， just play back as as I'm reading it， but again。

 cross product gives you a perpendicular vector to two other vectors okay and the actual order that we perform these operations in a and B。

😊，This matters。 Okay， that's going to tell us the actual direction。

 So let's go ahead and just see it again in code。 So I'm going to flip these here。And give B and A。

And go ahead and compile this。 Go ahead and run it。

 And you'll see now that our cross product has reverse directions。 right， when I did B， cross A。

 it's now going outwards in our Z negative direction there。 Okay。

 so the order does actually matter for our cross product。

 Now cross products got some other interesting features of what it's actually doing。

 And you can kind of see with this。😊，Example right at four and four if I drew this as a square and then if I modeled this as some shape with you know a width of4 and a height of416 actually gives me the area here okay of that actual crossproduct here so there's an interesting relationship as well of what crossproductduct gives us but mostly what we're going to be using in this series as we sort of get introduced to these tools crossproduct a tool for computing another perpendicular vector now why do we sort of need this sort of thing Well oftentimes what we're going to have to do if we have a camera and we're moving in some sort of direction we need to sort of build a coordinate systems so that we know which vector to rotate around we're going to talk about transformation shortly here and one of the next lessons in this series so this is gonna to be a lot of our tools we have to understand what it's doing for us all right so with that said。

 we've seen how to do this in GLM as I've talked about and sort of introduced these tools。😊，Normally。

 when I would introduce something like this， you get some slides or something。

 but now you can at least see the code as we introduce the concept。 Let me know if that was useful。

 But now what I want to go ahead and do is just summarize what we have learned today in this lesson here。

 so you can recap。 Okay， so starting with， you know， just 2D and 3D points。😊。

Then we talked about vectors， something with a magnitude and a direction。

 and we talked about some of these properties specifically how to compute the magnitude。

Do you remember your Pythagorean theorem here？Then we learned about normalizing。

Then we learned about dot product。And then we learned about cross product。Okay。😊。

And these all have lots of interesting properties with them so you know we can dive a little bit in between。

 but again， just remember things like dot product again is and I'm going to put in how similar。

Vectors R and use these for computing angle。Between two vectors and cross product gives you a new。

Perpendicular vector。To both of vectors Okay and that's the math symbol for those of you who might remember in that geometry class what per particular means All right folks so with that said。

 this is a bit of a monster lesson here on mathematics doing this in GLM but I hope it's enough to get you through the rest of the series these really are the tools that you have to understand how to use in 3D computer graphics and 2D computer graphics so you can progress so I felt that we needed a lesson here hopefully it was useful go ahead and let me know in the comments below if you liked it give us a thumbs up if it was useful subscribe so you don't miss the other lessons and of course all the other things with that said thank you for your time and we'll see you in the next lesson。

😊。

![](img/915ef04e3cab8ef4cddf0b65c89e1157_2.png)