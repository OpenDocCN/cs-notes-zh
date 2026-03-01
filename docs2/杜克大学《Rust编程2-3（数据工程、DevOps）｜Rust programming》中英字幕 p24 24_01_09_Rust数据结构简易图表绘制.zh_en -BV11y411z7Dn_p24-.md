# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p24 24_01_09_Rust数据结构简易图表绘制.zh_en -BV11y411z7Dn_p24-

![](img/d0f6cf210883824ca2842ac7db04ff2b_0.png)

Okay， in today's coding session， I'm going to demonstrate how to visualize data using this raski graph library and rust。

 you can see here from the official documentation。 pretty straightforward。

 you put in a vector and it's able to with a few configuration options。

 print out a nice little ASI graph here。 So if I go over to my code here。

 and we look at this main here， I again go to the dependencies and add this Next up。

 what I do is I configure a plot in a config。 what I'm going to do in this particular example is look at several cities。

 So Lisbon， Madrid， Paris， Berlin， Copenhagen， Stockholm and Moscow。

 and I create a vector that shows the distance from each of those cities。 So Lisbon to Lisbon is0。

 Lisbon to Madrid is 502 kilometers， Lisbon to Paris is 1053 kilometersm and so on and so on。



![](img/d0f6cf210883824ca2842ac7db04ff2b_2.png)

Now， what I do is I print this all out using this library and it's pretty straightforward to have it work。

 So let's go ahead and do cargo run here， perfect you can see here that at the very beginning I give a header here that just shows people when they're looking at the code exactly what's happening for example each of the distances and you'll see that they get longer and longer and longer and then what's nice at the very bottom as well I put a little metric here of the travel distances right so I say it's going to be in kilometers and then this has the actual kilometers so for really quick and easy type of ASI charts in a rust-based chamean tool this is a very compelling library and you can put a data structure in here and really get to work very easily So I think this is another thing to point out is it's very simple with rust to create a portable chamalan utility。

That include charts and graphs， especially if you keep it really simple and work within the confines of what libraries are available。

 in this case you can see it's a very small amount of code and to print something that's fairly sophisticated and we're able to communicate very well to the person that's using the tool exactly what's happening。



![](img/d0f6cf210883824ca2842ac7db04ff2b_4.png)