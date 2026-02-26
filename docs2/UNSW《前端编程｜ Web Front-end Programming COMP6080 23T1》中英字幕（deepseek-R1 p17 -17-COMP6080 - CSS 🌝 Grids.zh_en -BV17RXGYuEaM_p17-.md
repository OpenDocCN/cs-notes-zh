# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p17 -17-COMP6080 - CSS 🌝 Grids.zh_en -BV17RXGYuEaM_p17-

Hi， my names Hayden and today we're going to be doing a really quick bridge lecture to talk about CSS grids This is essentially an extension of the Flbox lecture where we learned about how to create these nice responsive dynamic powerful web pages。

😊，CSS grids are， I would say， a fairly particular use case for a kind of flex environment。

 and it's typically where the structures you're building can all be represented in some way by a series of straight lines separating things out。

 So you know if you have a page like this Anything where you can draw lines through things cleanly like that can become a CS grid。

 What CSsS grids are not useful for structures where you know maybe it's just actually completely all over the place。

 you know like this， then things become a lot harder to represent you could use CSsS grids for it by breaking the grid up and even smaller pieces。

 but that's where you start to get into just the main benefits of flex。

 So if you are truly using a grid， then CSS grids of the way to go how grids used to be built historically on the web was with tables So you might have seen this in the earliest lecture where we had tables sell you know a couple of cells。



![](img/bd16047f6531faa5c0f5c1a866116282_1.png)

![](img/bd16047f6531faa5c0f5c1a866116282_2.png)

And a few things like this。 Now， this has some limitations。

 Tables are not very powerful to style them as very difficult because the elements don't have a lot of inherent properties that are。

 you know， designed for flexible dynamic layouts。 Ts should generally be reserved for tabular data。

 So essentially， if you are actually representing a table。 Like if you were gonna use Microsoft word。

 Google Docs and just like literally insert table and put some data in it or something like that。

 that's the great use case for tables。 If you want to make a tabular structure， you know。

 like a grid， then generally we want to go and use CS grids。 Now， thankfully， Cs grids have a great。

😊。

![](img/bd16047f6531faa5c0f5c1a866116282_4.png)

Have a great C S tricks website page that helps describe how to use them as well。

 And we're going to play around with that just a little bit very quickly， just to get a taste of it。

 So you can see if this is right for you to go and do it in your own time。 So firstly。

 I'm going to go and have a container。 Now that container。😊。



![](img/bd16047f6531faa5c0f5c1a866116282_6.png)

![](img/bd16047f6531faa5c0f5c1a866116282_7.png)

Id container， we'll just actually open this up in another tab， CSS grids。

You can see that if you'd like to use a C SS grid。 the first thing you start with is by saying display grid。

 So it's a not like all the other displays we're doing instead of display Fl。

 it's display grid or in line grid。 but we're just going to stick with grid today。 Oh， See Daisy。

So once you do this， this will now say that everything inside of this container is now some kind of grid structure The next thing we might want to do is specify the size and number of columns and rows so let's say I want to make atict toe game I can say that my grid template column。

Columns might be， say， you know， 50 pixels， 50 pixels， 50 pixels。And similarly。

 my grid template rows might be 50 pixel， 50 pixel， 50 pixel like this。

So now I have this table now you can't see it obviously because there's nothing inside the table yet。

 but how we actually populate that table is we don't have to use any of this TRTD thing。

 we can simply go and put a bunch of dibs here。And in fact， we can put nine of them because。

It's expecting a three by three table， so you go make yourself a little you knowtictk toe game like this。

There you go， you know， someone's won that game， for instance。 So really， really easy。

 simple way to start。 obviously here， like， let's see what happens if we give our container a background of blue。

 take a closer look at it。 You can see that it does actually fill the whole space because it's a div element if we give it say a height of 200 pixels。

 You'll see that the grid will still only occupy the space we've specified because we did it based on pixels。

 But there is another unit with CSsS grids that you'll see C thrown around a lot。

 which is this fr and FR stands for fraction So it's kind of like the flex item where it's like if you say here。

 I actually want the grid to be one fraction for each cell。

 it will go and fill the space because just like how we do flex 1 or flex2。

 This is so many fractions of the grid now。😊。

![](img/bd16047f6531faa5c0f5c1a866116282_9.png)

![](img/bd16047f6531faa5c0f5c1a866116282_10.png)

This might be useful if your grid is perfectly square， for instance， in our case。

 you know it it's not but that's okay because it still kind of looks fun。

 I might also give the text to color of white。😊，So that's something really easy to do as CSS grids。

 We just made a TikToco game。 You notice that it's kind of easier than flex in some ways like。

 you know， the thing about flex is that it's very flexible。

 It's very powerful you can do a lot with it and therefore it's very general。

 the benefit of using grids is if you do truly have a grid structure then。😊。

It's very fast to represent like I've done here， you wouldn't be able to do this as quickly with flex and have it。

Like maybe you could， but just you know， this is just quicker because it's like purpose built。

 it's purpose built for this type of structure， so that that's super massive。😊。

Now that was cute making a little grid， but can we actually structure a web page like this And the answer is yes。

 so let's go and hide this content for now and let's approach things a different way Let's say that you want to create some kind of structure where you want to have a page that is your header and then you want it to be。



![](img/bd16047f6531faa5c0f5c1a866116282_12.png)

A foot are down here。 and then you want it there to be a sidebar。

 and then you want this to be the main content。 So this is where all the main content is。

 So head our foot， that's a smiley face。 head our footer and sidebar like that。



![](img/bd16047f6531faa5c0f5c1a866116282_14.png)

What you could do here is we've got this， you know structure of 1FR 1F 1F if I come along and instead of that。

 get rid of that background blue。I can specify how those nine items should be labeled。 Now。

 bear with me here， if I say grid template areas。I can then， just with strings。

Do something like this Now what I'm actually doing is imagine thattictk toe game from before where we had nine cells。

 I'm giving each of those cells a name so cells go head a head a， head a sidebar main main footer。

 footer footer。😊，And then what I can do is I can take that further and I can now go and find classes for each of those sections such as header which might be and then we have to say grid area header and then we say sidebar。

 which is grid area sidebar， and then we say main， which is grid area main and then we say footer。

 which is grid area footer Now what this is doing is a little obscure but it's saying that hey anything with class header if it exists within ac grid CSS grid。

 then it's occupying the area header， So when I come along down to my container here and I say div class equals header and I write header and then I copy that a few times and I do it for each of the other sections。

 say sidebar main。そだ。Now the CSS grid。We'll be able to pick up on that and space my page out like that now obviously not super obvious。

 it's obviously not obvious， but let's go and give these things all background colours like red。

 green， blue and，😊，orange。And you'll see what I mean。

 See how this is still that kind of three by three grid， but the header is  one，2，3。

 the sidebar is one， the main is  two and footer is one。Now。

 this is quite useful because now you have the structure， you can start saying， well。

 you know what my my my rows are this kind of。😊，1，2，3。 What if I want the middle road to be very big。

So now starting to look like a page and same with my columns。

 what if I want you know the right two columns to be much larger？

You know you can start actually building a page this way and it's super convenient as a baseline structure because again all we had to do is define header head a header sidebar main main you can describe the proportions you don't have to worry about those floats position absolutes or anything like that so super super easy which is good now。



![](img/bd16047f6531faa5c0f5c1a866116282_16.png)

![](img/bd16047f6531faa5c0f5c1a866116282_17.png)

There's a lot more on the CSS tricks page that you can kind of go into if you want to because obviously they talk about grid template rows。

 the columns on the rows， grid columns start grid template areas。

 that's what we just did there where we define specific areas， really， really helpful。



![](img/bd16047f6531faa5c0f5c1a866116282_19.png)

![](img/bd16047f6531faa5c0f5c1a866116282_20.png)

![](img/bd16047f6531faa5c0f5c1a866116282_21.png)

Similarly to the flex， everything on the left here is for the container and everything on the right here is for the item itself。

 So you see these other things like our row gap where you can define for a given row how much space to have between it。

 So if I add this to our container up here and say， well。

 I want the row gap to be two pixels We'll see how that changes our page。

 you can now see that there's two pixels between the rows。

 Maybe you don't want maybe you want a lot of space between the rows。

 but only a little bit of space between the columns。 So you could try doing that。

 So now the rows have lots of space the columns have a tiny bit of space。 you can do gap generally。

 if you just want to kind of again， there's a lot of compound functions you could have here like thiss So a gap5 pixels that'll do both。

😊。

![](img/bd16047f6531faa5c0f5c1a866116282_23.png)

![](img/bd16047f6531faa5c0f5c1a866116282_24.png)

![](img/bd16047f6531faa5c0f5c1a866116282_25.png)

![](img/bd16047f6531faa5c0f5c1a866116282_26.png)

![](img/bd16047f6531faa5c0f5c1a866116282_27.png)

![](img/bd16047f6531faa5c0f5c1a866116282_28.png)

![](img/bd16047f6531faa5c0f5c1a866116282_29.png)

So nice and easy there。 Just items。 How do you spread things out within that。

 So we can try using that one， too。 Let's see what happens。 Justify items。 Let's do center。



![](img/bd16047f6531faa5c0f5c1a866116282_31.png)

![](img/bd16047f6531faa5c0f5c1a866116282_32.png)

Oops。Yep， so now you can see this is quite interesting because like now it has scented each item within the space。

 but is it justify items？

![](img/bd16047f6531faa5c0f5c1a866116282_34.png)

![](img/bd16047f6531faa5c0f5c1a866116282_35.png)

But stretches the default so by default stretch here just pulled everything out to the the right size lots of configuration again point of this lecture is not to show you the whole thing because you can go and play around with it as much as you want。

 but if you're looking for a grid like structure which is essentially again anything that you could kind of just draw lines through and whether no matter how size they are or a proportion they are CSS。



![](img/bd16047f6531faa5c0f5c1a866116282_37.png)

Griids is the right way to go about that。 So just to wrap up。

 I will remind you that the benefit of grids is the responsiveness like this。

 You can see things grow。 They don't have to all be proportional。 You could say。

 I want the sidebar to be 100 pixels and the rest to， you know， take up。That space。You know。

 you don't really need in this particular case， for instance。

 the third column you could just have two columns here because。

 you know and you could just make sure the size of them is right。

 So this would be a reasonable CSS grid。 We get the exact same thing。 So have fun with it。

 it's really useful for some parts of some assignments so don't be afraid to use it and try it out and it's just gonna bet your name。

 So good luck。

![](img/bd16047f6531faa5c0f5c1a866116282_39.png)