# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P55：55_06_05_5-水平集与曲线演化-时长-25-34-可选休息点-14-30.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back which is finished learning about curve evolution There's one thing that is missing that we need to learn is how do we implement curve evolution in the computer we saw that curve evolution is important for example to regularize curves with curvature motion but even more important for active cons and we need to learn how do we implement in a friendly fashion that in a computer we have discrete images so we need to talk about the numerical implementation of that one of the areas that has had a tremendous impact in image processing in particular when we talk about PDs in image processing is level sets methods and I want to explain that and with that we are going to know how we implement any type of curve or surface evolution in a computer so what is all this theory all this framework of level sets。

So we have talked about curves and it's going to be the same for surfaces。

 but it's much easier to present these four curves。

 We have talked about curves and curve representations and we see that here we have a curve that is parameterized and remember for every P we have basically a different point on the curve Now this is not the only way to represent curves theres a very different way to represent exactly the same curve that is actually even more familiar when we are talking about shapes and the basic idea is that instead of parameterizing the curve we're going to represent the curve by all the points on the plane that hold a certain equation equal to0。

So let's look at this figure。 We're going to put a coordinate system。X。And why。

And then we say every point in the curve。Its a point such that phi at that point is equal to0。

 so we have to define this function phi and for example we can define the function to be positive inside and negative outside and one example is to define that as the distance to the curve for of course。

 the distance，To the curve add the curve itself is 0。 The distance to the point itself is 0。

 So every point on the curve has0 distance to the curve。

 every point inside has a positive distance and we define every point outside to be a negative distance。

 In that way， we define a function phi。 that the0 set。

 that's called a0 level set of that function meaning all the points on the plane where that function is0 define a curve。

 Let's look at a profile of this。 And we see that here。

 If I have a function that is positive inside and negativeifies outside， and I cross it with a line。

 then this is the profile we are going from negative。😊，To positive。 So this region is positive。

 Then we go again outside。 So we have negative again， and we go again inside。

 and we go again outside。Now， which are the points that belong to the curve this point。Basically。

 this zero。This point， this point and this point， every time the profile of phi crosses the 0。

 That point belongs to the surface。 In that way， we are belongs to the curve。 Sorry or a surface。

 if we are in higher dimensions。 In that case， in that form。

 we are defining a curve on the plane by all the points that hold this equal to 0。

 And these two are just two different representations of exactly the same curve。

 This is kind of painting inside the curve and painting outside the curve in such a way that along the curve。

 that paint is equal to 0 now。With this representation， we have compute tangents。

 normals and curvature。 we need to be able to compute it with this representation。

 otherwise we won't be able to do curve evolution， so let's see how we do that and we're in proof a couple of things as we have told this week is one of the most theoretical ones but we're doing everything in selfcon so I'm explaining everything inside and I think we are learning a lot of new concepts。



![](img/02d034561737d7984369bc9f30ae30e5_1.png)

So let us show that basically， if we define the curve as before as the0 level set of the function phi。

 the normal is the gradient of phi divided by the magnitude little， actually with a minus。

 that's a convention because I want the normal two point inwards， it just a convention。And of course。

 the tangent will be this。 It's basically a perpendicular vector。

Let's prove that It's not hard to prove。So remember， we have the function fee。

And all the points that belong to the curve is where phi is equal to 0。 So along the curve。

 phi is not changing。 it's always0。 When I travel the curve， it's always0。

 Then the derivative of the function along the curve。

Along the arc length because I'm traveling along the curve is equal to0。

 let's compute that derivative， so I want to take the derivative of this function。

 remember the function exists all over the plane and I'm taking the derivative in the direction of the curve with the arc length along the curve。

Now we have it here。 This is just the chain rule basic calculus。

 So if I have to take the derivative according to S is the derivative according to x X according to S and the same for the Y。

 So that simple calculus。 Now what I wrote here is this inner product。

 remember the inner product of two vectors。 So I'm going to write it here in case you don't remember if I want to multiply。



![](img/02d034561737d7984369bc9f30ae30e5_3.png)

2 vectortas。A B， I want to do the inner product。 Let's say we see D is a times C plus B time D。

 So this。It's nothing else than the inner product of the gradient of fee。With the tangent。

 remember x S YS is the tangent is the unit tangent we saw that a couple of videos ago when we were talking about differential geometry of curves on the plane and Ph py is just a gradient so this is what we have here now。

This is 0。Okay， we have it here， of course。This is the 0。 So I'm going to go here。 And， of course。

 I'm allowed to normalize。 So here I have proved that the gradient。

O the curve is perpendicular to the tangent。 then I normalize the gradient。

 So if I have a vector that is perpendicular to another， of course。

 any change in magnitude in the vector still perpendicular in particular I want to basically normalize it to have unit normal。

 and then I get this equal to0。 So if this is perpendicular to the tangent， then this is the normal。

 So I have a perpendicular， this is the normal。 And now once again as a convention put the minus because we if we have positive and negative。

 we want the gradient to point to point basically we want the normal to point inwards。 once again。

 it's just a convention。 So a very simple proof that basically shows that this is the definition of the normal。

 So having I can compute the normal with absolutely no problem and of course I can compute。

The dungeon， just the perpendicular vector to it。And。We have the first。 actually， we have two。

 the normal and the tangent。 Now， let us compute the curvature。 And again， a very simple computation。

 as we have here。 Just maybe two more steps， and we get the curvature。

So what we want to show is that the curvature I only have phi。 remember。

 the curvature is the second derivative according to S， so the curvature was CSS equal k n。

That's a curvature。 This is I want to compute。 I don't have C。 I have Phi。

 I have C the curve defined implicitly by phi as its0 level set。

And I want to prove that is this formula in case you don't remember what div is div divergence and the divergence。



![](img/02d034561737d7984369bc9f30ae30e5_5.png)

Of a vector， alpha。Beタ。Is basically alpha X。Plus。Beta y。 So it's a scalar。

 the first term of the vector， you take the derivative according to the first coordinate x。

 the second， according to the second coordinate。 Okay， let us prove this formula right now。

 So now we are basically are still going along the zero level set。

 So we still have this relationship。 and lets us exploit it Now。

 we are going to compute the second derivative of phi。Along the curve with alands。

We just compute the first one in the previous slide when we're computing the normal Now I want to compute the second derivative。

 so I have the first derivative， and I want to take one more derivative Now once again。

 this was nothing else than the gradient inner product with T as we saw the previous one and I have to take a derivative。

Remember， derivative of a thinner product is derivative of the first。Times the second plus。The first。

Times derivative of the second。 Now， what's the derivative of the tangent。

Second derivative is curvature in the normal direction。

 so here it is curvature in the normal direction， so once again derivative of the first one。

Times inner product with the tangent。 and then the first one。

Inner product with the derivative of the second one， which is t。

 but we know that derivative of T is kn。 and this basically is equal to 0。

 So what we have So this is equal to 0。 So what we have is that this term。

Is equal to minus this time。And basically， I wrote that here。 So this term。

 I can take the curvature outside。Okay， that's not a problem。 iss a scalar。

 I can take it outside of the inner product。 That's the first thing we do。

Oh I apologize there is here a typo， this should be a fee， basically a kind of a capital fee。

 but I apologize for that typo we are going continue its just a very easy to see that going from here I just made a typo and we basically have the curvature goes outside that's here。

Then we have this again here， and the normal， which you saw in the previous slide。

 is gradient divided by gradient。So we have curvature here now this product is the gradient square because I'm multiplying this by itself。

 so it's the gradient square divided by the gradient。

 they cancel each other and I get only one gradient。So， this term。Is here。Okay。This term。

I'm not going to write it down， but by now you're an expert because we are just doing derivatives and chain rule。

 if you want to take the derivative of the gradient according to S。

 remember you have to take the derivative according to x。And then X S plus derivative。

 according to Y，y S。 So you do chain rule again。 and then you're going to get this expression。

This expression is basically this derivative。 and that the tangent once again。

 we have from the previous one。No。We got this equality here。

If you now open this with this definition， you're going to see that it's identical to here。

Times this。 And then we got basically， the formula。

For the curvature of a curve that is represented in implicit form。Now， pay attention。

 This is extremely important。 It's gonna be very important next when I explain the forming curves in level sets。

 I don't need to have the curve。 I don't know C C is in implicit fashion defined。

 All I need to know is phi and I take regular derivatives in the x direction in the y direction。

 We know how to do that。 So this is the x direction。 This is the y direction。

 We know we just take derivatives， as we have been seeing many times in this class。

 this pixel minus this pixel or this pixel minus this pixel when we are taking derivatives in the y direction。

 and we do that a number of times just following this formula and we get the curvature。

And or we get the normal or we get the tangent So it's much simple I don't have to go and take derivatives along the curve。

 I take derivatives in the grid basically in the image really， really much simple。

 So now we know the curvature we know the normals do we know how to deform curves Let's see about that。

So the next step is to learn how to deform a curve。

 how to deform phi in such a way that the boundary basically is deforming as I wanted。

 so we have a function that is representing a curve in implicit form。Okay。

We know that the curve that is defined in this way it's moving with this velocity。

 And we ask ourselves， how do I have to change。Phi for the level set of phi to move according to this velocity。

 And it turns out that it's this formula。And I'm going to prove to you here in just a couple of lines。

But before we do that， please pay attention to what's happening here。

 The fee is once again elips on the image， e livess on the grid every time I'm talking about derivatives and talking about derivatives on the grid。

 so the pixels are moving up or down， there' is no derivatives on the curve which are very difficult to implement this is like when we know we have seen how to compute a gradient you。

 again， this minus this。 we have seen those things。

 So implementing this is much easier than implementing this。Let us prove this formula。

So the basic idea is once again very， very simple。 I'm going to take the derivative of phi according to T okay and。

This is where I'm going I'm going to take the derivative according to T of this side and the derivative according to T of this side now this sign is0 is a constant so the derivative on this side is also0 here it is。

The derivative here， I wrote it here。And now once again。

 chain rule and this is what we have the derivative of this function of X。

 Y T according to T is what I have written here。 So I take the derivatives according to x。

 then xt plus derivative according to yyt plus derivative according to T。

 these are partial derivatives。 So this is what I have okay。那。This。

 I move to the other side because I have a0 here， and I get minus the derivative according to T equal to the right hand so this。

Part is equal to minus days。This we have seen before okay。

 is an inner product as we have seen already at least two times in the previous slides。

 so it's the gradient of phi because of this part and this part and this xt YT is C is basically my curve theforming。

So we are here now。 We have one more step。 city， I know what it is。VN， so I write VN。

It's the motion of my curve， exactly what I want。So once again。

 the V can come out because it's a scalar and I have this。Now， remember。

 I want to write everything as a function of phi。 That's the important part。 Okay。

 so we just saw that the normal is minus the gradient normalized okay so。

Here we basically plug that we replace minus the normal。Buy the gradient of fee， normalize。

And this as before is gradient times gradient， that's gradient square divided1 gradient。

 we get one gradient， so this is gradient。These days。And we got this。

AndBecause there is a minus here。It cancels with the minus here。

 and then we have that this is equal to this， which is what we want to prove。

Okay so once again you can look at this if you want to just you can post the video now and look at the proof。

 there is nothing here but applying the chain rule and then writing everything as a function of V。

 that's the important part and we get that when we want to move a curve according to V in the normal direction。

That's obtained by moving phi up and down whatever this formula tells us， and then we cut。

 so you want to go for t equal5， do this for t equal 5。

 find a zero level set and you got the curve evolution。So everything now is in implicit form。

 We have functions defined on the plane， and by moving those functions。

 we are moving the zero level set， and we are getting curve evolution。 for example。

 we are getting active contours。

![](img/02d034561737d7984369bc9f30ae30e5_7.png)

Why is this so important。Let me just illustrate a couple of ideas。

 which I think will help us to illustrate how important this is。

 So remember that sometimes when we deform a curve， the topology can change。 I'm going to ask you。

Which was the curve motion that produces changes in topology， that might produce changes in topology。

 I it the curvature motion， is it the fine motion or is it the constant motion？We know that。

And we know that is the normal motion。 The normal motion can change topology。 Now。

 when the topology of a curve is changing， if you discretize the curve。

 it's very difficult to understand at this point that was neighbor of this point actually ended up here。

And this one ended up there now there are no neighbors anymore。

 there were neighbors one step before but because of topological change they are not anymore and numericalmeric analysis is very complicated when those things happen when neighbor thinks neighboring things just stopping neighboring things is very。

 very complicated Now when we are in this phi function so imagine that this gray is the phi and basically the two planes the two green light green and dark green are just at different times you are cutting these phi function the phi function is moving according to V gradient p and all what I have to do is cut and be surprised is there is a topological change and don't have to worry about connectivityivities。



![](img/02d034561737d7984369bc9f30ae30e5_9.png)

No worry at all， because I'm working on a grid， as I'm going show here。 so I don't have to work with。

Particles and this critics a curve and remember who is neighboring with whom and how to enable him the neighborhood is changing when their are topological changes。

I don't have to do that。 I'm basically working with Phi defined on a grid as we have it here。

 This is just another profile， and Phi is changing Phi T is V。Graient。Gradient fee。And that's it。

 So we discretize that the same way that we disccratize before goes up。 it goes down。 And at example。

 you say I want to all the state of the curve evolution right now， you just slice it。

 you look at every place where the current fee is equal to0。

 you look at every coordinate or every coordinate here。 If there is topological change or not。

 you don't have to be aware of that。 And that's the beauty of this。

 And this is how the active conours that we talk at the end of the previous video is implemented with this where V is that velocity of active contour。

 So V can be。😊，In a simplified fashion， G curvature where G was this inverse gradient of the image or some function that makes it stop。

 So you want to implement active counters。 All what you have to do is P T。eququal。主。

Carurvature times。The absolute value of the gradient， and we know that the curvature previous slide。

 we can also compute as a function of phi。 So everything is a function of this surface that is defined on the grid。

 And that's the beauty of the level sets， it simplifies the whole numerics。

 and with it we can implement the curvature motion， constant motion。

 Const motion is absolutely trivial。 Let me write it here。5 T。Equal gradient。So the gradient。

 you might discretize the same way that we talked before， the pixel on the right。

 minus the pixel on the center， the pixel on the top， minus the pixel on the center，50。

 you discretize like phi at t plus 1 minus phi at t。Any type of time disctization。

 we are not discussing a lot of numeric analysis， but just relatively standard numerical analysis that you can use to implement smart numeric analysis。

 but relatively standard instead of having to discretize a curve。 Very， very simple。

Equations for as complicated as we want curve evolutions， curve motions。

 and I prove this only for curves happens the same four surfaces and actually the formula is exactly the same formula but V is not a function in higher dimension。

 So exactly the same formula。 So now you have the tools to do active conours and we are gonna actually see more of active contours later this week in some of the future videos。

 but you know， curve evolution and you know how to implement curve evolution as well。 and as I said。

 we are learning a lot of new material and as I say， you can go back and recheck this video。

 the proofs are really， really tool line proofs with basically calculus and algebra from very。

 very relatively simple calculus and algebra， but you don't have to be aware of it I just explain it to you during this video and during the previous videos so。

Keep advancing， and I'm going to see you again in the next video。 Thank you very much。



![](img/02d034561737d7984369bc9f30ae30e5_11.png)