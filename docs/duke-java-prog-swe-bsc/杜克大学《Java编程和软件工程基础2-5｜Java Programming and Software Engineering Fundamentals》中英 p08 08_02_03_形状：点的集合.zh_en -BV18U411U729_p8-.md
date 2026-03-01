# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p08 08_02_03_形状：点的集合.zh_en -BV18U411U729_p8-

![](img/fa3178056d24d2329f0e6e84c55c0fd5_0.png)

Hello， we're going to learn how to calculate the perimeter of shapes using Java。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_2.png)

We'll use what is called a Java class， which you'll learn more about soon named shapepe to model polygons in geometry。

 These kinds of shapes are used in many applications。 For example。

 a triangle is the simplest polygon or shape。 It's simply a collection of three points。

 but triangles can be combined in the complex shapes that are colorful or form the basis of wireframe diagrams used in computer graphics and video games。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_4.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_5.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_6.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_7.png)

We'll use a shape Java class to represent a collection of points。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_9.png)

We'll use a class for point and for shape to understand programming concepts that are applicable across many programming languages。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_11.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_12.png)

We'll need to construct shapes by adding points one at a time。

 This will allow us to create shapes like this six sided shape， which is constructed from6 points。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_14.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_15.png)

Here is a shape with five points。Here is another six sided shape。

 The order in which the points are added to the shape is important。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_17.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_18.png)

When we look at the code for the Java shape class， we'll also need methods for accessing the points。

 either one at a time or using other approaches。We'll likely want to create operations or methods that use shapes。

 like drawing a shape or finding the perimeter of a shape。

We've seen that shapes can have many points。 Our shape class is simple。

 but we could expand it to create complex shapes of many， many points like this butterfly。

When viewed more closely， it's clear that the butterfly is simply a collection of colored triangles。

 like the wired frame drawing we saw earlier。The shape pla we'll look at is very simple。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_20.png)

Circles aren't really a finite collection of points。

 so circles and some other shapes are harder to model using our Java class。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_22.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_23.png)

In geometry， a circle is an infinite collection of points that are all the same distance from the center of a circle。

 Our Java class is just a finite collection of points。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_25.png)

![](img/fa3178056d24d2329f0e6e84c55c0fd5_26.png)

However， even with our simple class， we could model a circle using many points as shown in the diagram here。

 so even our simple class will prove very powerful。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_28.png)

After we cover some of the basics of writing programs in Java。

 we'll explore the point and shape classes in more detail。



![](img/fa3178056d24d2329f0e6e84c55c0fd5_30.png)