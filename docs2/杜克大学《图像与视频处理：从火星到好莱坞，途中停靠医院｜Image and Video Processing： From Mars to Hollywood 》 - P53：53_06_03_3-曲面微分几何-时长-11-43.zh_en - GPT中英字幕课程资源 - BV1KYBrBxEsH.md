# 杜克大学《图像与视频处理：从火星到好莱坞，途中停靠医院｜Image and Video Processing： From Mars to Hollywood 》 - P53：53_06_03_3-曲面微分几何-时长-11-43.zh_en - GPT中英字幕课程资源 - BV1KYBrBxEsH

Hello and welcome back。 I just want to spend a few minutes explaining some of the concepts that we learn about curves on the plane。

 but now surfaces in 3D。 So it's going to be a much shorter video than the previous one。

 and we're going to be discussing surfaces instead of curves， just a couple of concepts。

 Surs are really beautiful。 and we could spend years， Some people spend order life studying surfaces。

 But once again， we only have time for a few key concepts that will help us to understand。

 for example， active surfaces， how to do segmentation of volumes in three dimensional images。 again。

 just a few concepts。 We have a surface as on a surface。😊。



![](img/a9cd72f245265adc530cdb225db114f7_1.png)

Basically， we are only going to be talking about talking about surfaces in three dimensions and basically on a surface we can draw curves here we have curves Now basically each one of these curves is in 3D now so you have to have X Y and z。

 but we basically have the surface imagine that the surface is basically floating on a plane so the way we parameterize the surface is now with two parameters U and V remember for curves we have only1 p for surfaces we have two so we basically are on the plane so we have U。

MV。On the plane for each U and each V， we have an x coordinate， y coordinate and z coordinate。

 and that's how we represent a surface。Two parameters。

 three coordinates in case we had one parameters。Two coordinates because we were on the plane。

 we can have kers in 3D there will be one parametermeter3 coordinates， for example， this one。

So that's a surface Now let's define normal area and things like that on the surface。

 but if we have curves， we can take derivatives as we were doing on the plane so we can take a derivative according to the U parameter and according to the V parameter so we can basically be on a curve and basically say let's just take a derivative of that curve according to U and according to V。

If we do the cross product of these two vectors， we get a third vector perpendicular to these two。

 once again basic algebra， so the normal is the cross product of the two。

That theri of S according to U is tangent， that derivativeity of S according to V is tangent。

 they will define a plane which is tangent to the surface at this point。

 if we do the cross product between them， we get a normal to the surface and again we are going to normalize that because we are interested unit length normals。

So we have derivatives， which means tangents， and then the normal。 If we have derivatives， we can。

 for example， define the element of area。 We know that then once we have two vectors。

The determinant of the matrix composed by those vectors basically defines the area of the parallelogram that we see here。

 So if that's infinitesimal， we have elements of area If that's integrated across multiple across long regions。

 then we have the total area。 So same type of concepts we have length on the plane we have areas here。

 we also have length because the surface it is a lot of curves。

 nothing other than that nicely organized So once again here is the parameterization and here is the normal。

 let's see the example of something that you are familiar with which is basically graphs the same way that we saw graphs on the plane we can see graphs in three dimensional space so we have a coordinate system。



![](img/a9cd72f245265adc530cdb225db114f7_3.png)

Exs。Y and z， and basically we define a graph that's again floating on space so our parameterization is x equal to u basically x is one of the parameters y equal to V and then z basically the height of the surface or in this case the graph or the function it just a function of these two a particular case。

 think about an image for example， an image is a particular surface is a function。

 so the plane of the image is x and y or U and v， the gray values of the image is the height means z。

 so you can think about images as surfaces in particular case as functions or graphs and that's a very interesting interpretation we can basically compute thinks we can compute the normal of an image as。

We saw in the previous slide basically we treat the image as a surface， we take derivatives。

 we compute the normal of an image， so we bring a lot of concepts of differential geometry into image processing Now what about curvatures？



![](img/a9cd72f245265adc530cdb225db114f7_5.png)

So the basic idea is very simple， once again we have curves if you have a curve。

You can take first derivative， according to arc length。

 this is a carv in 3D by the same concept and second derivative。

Second derivative will basically give you the curvature of that particular curve that you took。

 for example， this one。Now sometimes you want to project that curvature remember first derivative is tangent。

 second derivative is perpendicular to the curve， not necessarily to the plane， you have a curve。

 there is a lot of things that can be perpendicular to that。

 so you can take it and project it to the normal or the perpendicular to the plane if you wish。

And that space is sometimes called the normal curvature。 So you take a curve。

You take second derivative that gives you a vector and you project that vector into the perpendicular to the surface。

 but that's about basically maybe you're thinking about a curve， but if I have a point。

 let me just mark that here， if I have a point。On the surface， there are multiple curves。

On the surface that go through that point。 So look at all the curve。There are multiple of them。

 So what exactly defines the curvature at that point。

It turns out that there is one of these curves that when we treat it as a curve and we compute the curvature is the smallest possible。

And there is another curve that is the largest possible。 So we basically define the。

Prinncciipple curvatures。Of a surface in the following way， you're in a point。

And you basically try all the possible curves on the surface that go around that point。

 and you basically compute the curvature。 Now we are talking about curves。

 This curve has a curvature。 This curve has a curvature。 you compute all of them。 There' is one。

Which is the minimal。And one which is the maximal sometimes there's more than one。

 for example a sphere might have basically have more than one all directions are the same。

 but you have for regular surfaces you have at least one which is the max and the are which is the min and those are called the principal curvatures of the surface I'm going to just tell you a bit of extra information。

 the curve that gives you the max and the curve that gives you the min are perpendicular to each other。

Now and there are ways of computing this， you don't have to really try all the curves。

 there are ways of computing， I'm just talking about the concepts here。

 so there is one direction which is max， the other is min Think about a cylinder。

When you cut a cylinder perpendicular to its axis。There is one direction that you basically get a circle。

What's a curvature there， one over the radius， we know that there's another direction in the direction of the cylinder that you get a straight line。

 what's a curvature there， we know it's zero so in one direction we get one over the radius。

That's a maximum the other you get zero that's a very nice thing it's a surface that in one of the directions the curvature is actually zero so on a curve there's only one curvature you are turning and there's only one direction to go on the curve on the surface you can go in multiple directions and then we pick one which is the maximum direction that we curve the most one is the minimum where we curve we curve the least and actually that basically completes what's called the mean curvature which is the average of both of them and the Gaussian curvature which is the product of them so what's a Gaussian curvature of a cylinder zero at every point in one direction basically it's a straight line so it's zero and there is a lot of beautiful differential geometry on surfaces a lot of it due to gaus。



![](img/a9cd72f245265adc530cdb225db114f7_7.png)

。Really beautiful。 But these are the basic concepts。

 So you have the same as on the plane cur the curving of the surface。

 but we have curving in multiple directions。 we have the max themin and normally people say stop taking the max and the mean。

 Let's take the average and the product from this， you can， of course。

 from the average and the product， of course， you can go back to the max mean or vice versa。

 So these are basic concept of surface differential geometry。 Again， we have normal curvatures。

 the same kind of concepts that we have for planar curves。 So now after these two videos。

 one relatively longer than the other you're an expert in differential geometry。

 And at least you have the tools to understand what's coming next， which is theform of curves。

 meaning the formation of shapes and the relationship of that with active contours active surfaces。😊。

And even with image denoing and image enhancement as we are going to see remember images are surfaces so we can treat them with the tools that we just learned。

 they have curvatures， they have normals， they have the same concepts of differential geometry I see in the next video this is getting really really really really exciting I hope you're having fun see you very soon thank you。

