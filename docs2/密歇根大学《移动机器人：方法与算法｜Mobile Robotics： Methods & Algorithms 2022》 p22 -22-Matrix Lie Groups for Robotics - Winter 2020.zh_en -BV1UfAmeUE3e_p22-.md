# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p22 -22-Matrix Lie Groups for Robotics - Winter 2020.zh_en -BV1UfAmeUE3e_p22-

![](img/b6596711533b8ea1c8690bac57ba445f_0.png)

So Mannie is off doing， I have no clue what he's doing somewhere。

 so I'm going to be your substitute for today and Wednesday， so a word of warning for you guys。

 I am not an engineer， I am a mathematician， so today and Wednesday I'm going to teach you about four semesters worth of graduate math in two days。



![](img/b6596711533b8ea1c8690bac57ba445f_2.png)

![](img/b6596711533b8ea1c8690bac57ba445f_3.png)

So we're going to see how this goes and if you're not thoroughly confused after this slide then I did something wrong so another thing to keep you guys in mind I'm bad at slides because I go too fast when I just read slides because I don't have to write anything down so yell at me to slow down。

 yell at me to ask questions whatever because we're going to go at warp speed today and Wednesday。



![](img/b6596711533b8ea1c8690bac57ba445f_5.png)

So today's topic is going to be on matrix groups， so in essence we're going to learn how to do calculus with matrices。

 it's going to be a little bit more involved in that but that's the crux and the important part from today isn't so much that you guys can regurgitate formulas。

 but it's more important that you have a vague understanding of what this stuff means。



![](img/b6596711533b8ea1c8690bac57ba445f_7.png)

So。With that let's start so this is a list of books that Monnie put together for you guys to go through because of course you know an hour and a half of me talking is not going to teach you you know something that has a thousand textbooks written on it so these are things for future reading of course if you just Google lead groups。

 the algebras， matrixtri groups whatever I mean learn it from more than just me。

So a matrix group is just a group of invertible matrices。

 so there's three things in this sentence that's important， there's a word group。

 there's the word invertible and there's the word matrices。

 so I'm assuming everyone knows what invertible matrix is right it's just a matrix so you can multiply by something else you know get back the identity。

But I'm assuming that not everyone in this room knows what a group is， is that correct？



![](img/b6596711533b8ea1c8690bac57ba445f_9.png)

Okay so a group isn't well okay well we'll get that in the next slide so of course a couple reasons to study these things is the study of lead groups or matrix groups or whatever you want to call them are ubiquitous in all sorts of areas we're of course going to use them for robot tracking and position orientation garbage of sorts but it's used much more often than that and one thing I want to keep in mind is it's also useful in Rimanian geometry whereas instead of doing calculus on matrices we're going to do calculus on warped curved things and that's what the topic on Wednesday is going to be。

So we're going to see some of the stuff we talked about today a little bit more in depth on Wednesday。

 but they're going to be to a little bit of a different tune。



![](img/b6596711533b8ea1c8690bac57ba445f_11.png)

So to start things off， a group is just a set with some sort of gluing together operation。

 so you have a set G such that if you take any two elements G and H。

 you can glue them together in some sense that gives you back an element。

Their associative suhey placement doesn't matter， there's always an identity。

 so there's always something that if you append it to it and nothing happens。

And the last thing is inverses exist。Okay， so this seems abstract and scary until you start to think about a couple examples and a couple examples make this a little bit less terrifying。

So if there's an eraser。So the very first example of a group you ever see is if you have the integers。

And addition okay， so if we look at this according to these things。

 if we have two integers and we add them together， we get back in integer right the second one。

 if we have you know integers and we add them together。

 it doesn't matter what order we add them in right if we take you know。4 plus 5。Plus6。

 this equals four plus5 plus6 right， so nothing scary going on right behaves the way you want to behave。

 of course， with the identity， what thing when under addition does nothing。Zero right。

 so zero is identity element in this case， and the last thing is the inverse is according to multiplication。

 what's the inverse of sorry of addition， what's the inverse of addition。Subtraction， right。

 so in this language。For inverse。D equals -4 in the sense to when you take4 and you add it to -4。

 you get back 0 is all this last thing is saying Okay， and of course。

 the next example you always see。Is you have the real numbers subtract zero and multiplication。

And of course this follows everything the same as before because if you take two real numbersrs and you multiply them together you get a real number。

 parentheses， of course don't matter， you can multiply things in whatever order you want the identity element here now is going to be one because if you multiply something by one nothing happens and the inverses here now are the usual inverses this is going to be the reciprocals。

O。But one other question to ask。Is if we have the integers。And multiplication is this thing a group。

Y南。Yeah if you have two right the multi game universeverse of two is a half but a half is an integer so an important thing when you deal with groups is the group is really two things。

 the group is the set and the group is also whatever the gluing together operation is so in this sense the integers are a group under addition but not multiplication but of course the real numbers are a group under both or you can multiply them you can add them nothing too spooky happens。

So a matrix group is just a collection of matrices that also follow these rules。

 so its matric is that when you multiply them together， it follows whatever you're talking about。

 the order of the parentheses don't matter， there exists some sort of identity element which is you your identity matrix and you can invert the matrices is all that this is saying。

And we'll come back to examples of matrices that follow these rules。



![](img/b6596711533b8ea1c8690bac57ba445f_13.png)

So again now we're going to get into matrices so MN MmN are going to be M by n matrices and the K means that's what the coefficients are because right a matrix is just a grid of numbers but you got to specify what those numbers are so for the purposes of this class it can be the real numbers。

 the complex numbers or the Qttonians but of course we don't care about the last two everything we're going to deal with the real numbers。

 so if you're not comfortable with complex or quatonians we don't really care everything is just a real number to us anything else is too scary。

And if you're really curious， cage just has to be a community of ring if you know what that means。

 if you don't know what that means， then ignore that sentence。



![](img/b6596711533b8ea1c8690bac57ba445f_15.png)

![](img/b6596711533b8ea1c8690bac57ba445f_16.png)

So the very first matrix group we're going to deal with is the general linear group。

And the general linear group is just the matrices that determinant is non-zero because right if the determinant is non-ze that means you can invert it so that means everything follows through right and of course the reason why so on the last side K could be RC or H but we don't care about that because the general linear group of C we can view it as a general linear group of R and H can be viewed as a general linear group over C and we can just scrub everything off as just being r and forgetting about everything else so I said C and H on this side and last side but just scrub those from your memory everything is just real numbers okay so the general linear group are just square matrices of real numbers that when you take their determinant as non-zero。



![](img/b6596711533b8ea1c8690bac57ba445f_18.png)

![](img/b6596711533b8ea1c8690bac57ba445f_19.png)

![](img/b6596711533b8ea1c8690bac57ba445f_20.png)

Okay， and if we go back to the group。Definition。

![](img/b6596711533b8ea1c8690bac57ba445f_22.png)

If our group is the general linear。

![](img/b6596711533b8ea1c8690bac57ba445f_24.png)

Group over the real numbers， right， the group operation is going to be just good old fashioned matrix multiplication。

 right If you take two non singular。Marices， and you multiply them together。

 is this thing non singular？Right， because if you take the determinant。

RightAnd since we assume neither of these things were0， the composite is not going to be zero。

 So if you take two general linear matrices and you multiply them together you get something back。



![](img/b6596711533b8ea1c8690bac57ba445f_26.png)

Right。You have sociivity。In the sense that it doesn't matter which direction or which order you multiply them in。

 you can multiply GH first or you can multiply HK first， it's fine。And you have。Inverses， of course。

 because since the determinant is nonze， you can always invert this thing。

 So right recall that the determinant。Of the inverses one over the determinant。

And since we assume this thing isn in zero， we're not getting any troubles。And then of course。

 the identity element in this case is just。You know， the matrix with ones on the diagonals。

So this is going to be kind of the parent lead group we're to talk sorry matrixtri group we're going to talk about all throughout today and all the matrix we're going to deal with are going to be things that sit inside of this。

 This is the overarching framework we're going to deal with are just matrix issues determinants aren't zero。



![](img/b6596711533b8ea1c8690bac57ba445f_28.png)

![](img/b6596711533b8ea1c8690bac57ba445f_29.png)

So the next example we have is we have what's called the aine group。

 so the aine group is going to be a square thing where now what we think of is this matrix a in the upper corner is just given by something general linear it's just whatever it is and then this element T which is just going to be a vector so we can think of aine matrices as some sort of a general linear matrix and a vector paired together and the way we think about this。



![](img/b6596711533b8ea1c8690bac57ba445f_31.png)

Is you have your position in RN right so again we can think about n being three if you want to talk about the real world so you have your three vector。

 you pen this one at the bottom， this is called homogenous coordinates for whatever reason。

 and then what happens is when you take this element which is again your general linear matrix in your translation。

 it just multiply it out this way。Okay， so if you think about it。

 this is like you know your screw motion or whatever right where A is going to talk about how you're rotating and T is going to talk about how you're moving and in general rotation plus translation right this is going to be what's called your Aine group。

And again， if you take all matrices of this form and you go through those four rules we had for groups。

 you're going to see that everything works out if you multiply these two together。

 you're going to end up with a new aene thing， right the order of the parentheses don't matter。

 there always going to be an inverse there's always going to be an identity， yada yada yada。

 nothing scary happened， this is just another example。



![](img/b6596711533b8ea1c8690bac57ba445f_33.png)

So。What we can think of is we have the Aine group， which is the collection of all of these matrices to find all the different ways we can move。

 but we also have this thing which just defines how this matrix by itself defines how we move and we define how we move by acting on a thing。



![](img/b6596711533b8ea1c8690bac57ba445f_35.png)

So just this singular ane element gives us what's called an affine transformation。

 so another way we can think about this is the aene group is also the aine transformations。

 but the affene group is all of the transformations under the same roof。



![](img/b6596711533b8ea1c8690bac57ba445f_37.png)

But a specific ane element is a specific aine transformation。And again。

 where you can think of this aine transformation as a function。

 and then you can do function composition and function composition works out to be another matrix group。

 everything follows through， right we're just using things under different languages but nothing different is going on。

Right。And of course， the Aine transformations include translation， which if it's purely translation。

 that means your matrix here is just going to be one and all that you have is T's happening。



![](img/b6596711533b8ea1c8690bac57ba445f_39.png)

![](img/b6596711533b8ea1c8690bac57ba445f_40.png)

You can have similar transforms， you can have reflections， rotations， cheers。

 all this fun stuff and we'll talk about a lot of these different specific examples further throughout this lecture Okay so Aine is kind of。

Well， general linear is truly the biggest and then A is kind of the next biggest matrix group we're going to deal with and of course。

 as we hone these down， they're going to be more useful because we can say more about them。



![](img/b6596711533b8ea1c8690bac57ba445f_42.png)

So again， if we let the matrix A in the aine group just be the identity。

 we end up with what's called a translation group and again， if you look at this thing。

 it's called a closed subgroup because if you just take matrices of these forms。

 all of these count as aine matrices， but these on their own follow those rules over there。

 so if you have a big group of a collection inside them to follow their own group laws are called a subgroup。

Okay。Questions so far。

![](img/b6596711533b8ea1c8690bac57ba445f_44.png)

So probably the most nifty group we're going to deal with are those of the orthogonal group and an orthogonal group right is just made up of orthogonal matrices and these are matrices that when you multiply by your transpose you get the identity。

So you probably have seen rotation matrices before this is just all that are given rotation matrices and again right if you take two rotation matrices and you multiply them together。

 you end up with another multiplication or another rotation matrix and that's what makes the rotation matrices into a group。

 but of course。We call them Ne orthogonal group because we want to call them that instead。



![](img/b6596711533b8ea1c8690bac57ba445f_46.png)

So when we look at the orthogonal group， we have the， well。

 the orthogonal group is defined off the relation that a times a transpose is the identity so we can of course。

 hit the determinant on everything。

![](img/b6596711533b8ea1c8690bac57ba445f_48.png)

![](img/b6596711533b8ea1c8690bac57ba445f_49.png)

And this just tells that that the determinant is equal to plus or negative 1。

 so the orthogonal matrices fall into two camps， we can either deal with the determinant equals one or the determinant equals negative one。

So as a quiz question are it's either of O plus or O minus by themselves a matrix group。

The together is O of N， which is a matrix group， but individually are either of them a matrix group。

Yeah， is the other one。Now， why is the other okay， why is this one not a matrix group？Well。

 if you have two things from here that have determined negative1 and you multiply them together。

 what is their determinant going to be？Positive one， did that live in here？

No it lives up here remember the rule for a group is when you do things together it has to stay in the group so if you take two things down here they pop out up here and that's not allowed right but of course if you take two things in here they stay in here so this is its own self a nice little group on its own right this isn't。

😡。

![](img/b6596711533b8ea1c8690bac57ba445f_51.png)

So again， what we notice is when we take this orthogonal group。

 the intersection of these two decomposes is empty right because something can't have both determinant plus1 and negative one simultaneously you can't really do that so ON is just one copy of O plus and one copy of O minus and there are two disjoint things floating around in space。

Okay and then since as we talked about on the last slide oh plus is by itself its own matrix group。

 we're going to call that thing the special orthogonal group。

 so throughout everything if you don't say special that means a deter can be whatever it wants。

 if you use the word special that means a determinant has to be one。Okay。U。

And in terms of actually like rotating things around。

 what is the difference between the special orthogonal group and I guess the negative orthogonal group？

Right so like let's just talk about， you know if' if we're in the plane， right。

 and so the orthogonal group is just rotating things around in the plane， right。

 What rotations are allowed in S O2 that are not allowed in O2 minus。Like intuitively physically。

 what's special about the special orthogonal group？Well， they both are only one direction。

So think if we have S2。Yes。Yeah。This is just given by you take your thing and you rotate it around。

 right， but if we have O2 instead。This can include reflections。

Right so if you take your hand right this thing and this thing are the same thing under under S2。

 but this thing and this by two hands together are different copies of each other right you can't rotate your left hand into being your right hand and that's what this takes off So when you're in the0 minus this in corresponds to looking at the universe through a mirror when you're in SO this talks about normal rotations that you can physically do So for you guys as engineers you almost exclusively care about this because you can't really take your robot and put it through a mirror and look at like the inside out version of your robot it's mathematically legal but it's kind of stupid in real life So were really only going to care about these and the reason for that is we're just going ignore reflections。



![](img/b6596711533b8ea1c8690bac57ba445f_53.png)

And another intuition to think about if we take two of these things right。

 we're going to pop out up here， so if we do two reflections。

 nothing happens if you look in a mirror twice， it's the same thing as not looking in a mirror at all if you want another intuition on that。



![](img/b6596711533b8ea1c8690bac57ba445f_55.png)

So one of the main reasons that we like the orthogonal group but of course specifically the special orthogonal group is they are called isomeries and an ismetry is something that the distance stays the same so if you think about it if you have your hand and you rotate it。

 you have any two points on your hands， the distance between them after you rotate it I mean the hand distance isn't going to change right as you move these things around distances between these points are going to stay the same and that's entirely what this says here when you have the distance between your two points and you apply an isometry to it the distance stays the same。

And again， if you think about it， if you look at yourself in a mirror right the distance on your face stays the same in the mirror。

 but of course that's not allowed by normal laws of physics。

 so ON is the group of is also a group of isoomeries。

 but they're kind of stupid isoomeries so you kind of got to keep there's a notion of orientation as well as just measure or not measure but distance preservation。

😡，So you can be a little bit sloppy， but again， we really only care about special orthogonal。So。

Another nice thing to know about is if the isometry fixes the origin。

 then it has to be given by something either an ON or SON you can think about if you take your hand and you move it to the left by one。

 again that's an isometry because change no no no distances change。

 but that's not going to fix zero and that's not going to be the same thing as matrix multiplication that's going to be something from the translation group we talked about earlier。

So as you'll see later on， all isome are really given by some sort of a translation and then something in an orthogonal group。



![](img/b6596711533b8ea1c8690bac57ba445f_57.png)

So the special orthogonal group is just rotation about these perpendicular planes。

 so a way you can think about it right is in SO2， this is just rotations of the plane。

 there's just turning clockwise or counterclockwise， SO3 is rotation about yaw pitch and roll。

So a way to think about it is S2， you can only rotate in one dimension。

 so it's a one dimensional thing。In SO3， you have ya pitch and role so you can rotate in three different ways。

 so it's three dimensional。As a quiz question， what is the dimension of SO4？

I'll give you a hint the pattern is 13。Blank。It's not five。nine。S seven， you'll get there eventually。

It's fixed。 So you'll see later on， we'll do the computation for Y it's 6， but it's 6。

 and then SO 5 is 10。 and then。S06 is 16。And then so on and so forth so one of the thing that's odd is you think about it in SO3。

 which is the universe we live in， it's three dimensions because you think about it。

 you have your x your y and your z axis， you can rotate about each of them for yourt pitch and role and that gives you your three different rotation directions The trippy thing is in a four dimensional universe。

 you can actually rotate in six different ways。Whi it makes absolutely no sense why you can rotate in more ways and there are dimensions to rotate in。

 but this is why it's always disappointing we live in a three dimensional universe because it'll be more fun if you could spin six ways。



![](img/b6596711533b8ea1c8690bac57ba445f_59.png)

So。As we talked about earlier， SON are called direct isomeries and the word direct just means there's no mirroring is allowed and while elements of ON are called indirect because indirect just mean mirroring is allowed so again。



![](img/b6596711533b8ea1c8690bac57ba445f_61.png)

We like talking about this distinction a lot just to make sure you guys are aware。

 but right we don't want to do mirrors， but according to just the pure laws of algebra over there。

 the negatives are allowed to。So as we talked about earlier this thing of isoomeries。

 this contains all of the SON ON garbage and it also contains all the translations because of course if we take one step to the left。

 nothing is going to get bigger or smaller so the question now。It really is what is this thing。

 I think that's what we're talking about next。

![](img/b6596711533b8ea1c8690bac57ba445f_63.png)

Yeah。So the isoometry group lives again inside the Alffine group because it has the same form where it's a matrix with upper left hand corners。

 a matrix， the upper right hand corner is a vector。

 the bottom left hand corner is zero in the bottom right hand corner is of one。

Where now what's going on is a is an orthogonal matrix and T of course is your translation。

 so the way you think about this is a tells you how you're turning and T tells you how you're moving。

And in basically every way you can move that doesn't cause lengths to go stupid is just by some sort of a rotation。

 some sort of a translation。

![](img/b6596711533b8ea1c8690bac57ba445f_65.png)

And's a pair of the two。And we call this thing SEN for the special Euclidean group and again。

 the special means we require the determinant to be one if you do just the Euclidean group that allows for reflections which allows for it to be in just ON。

 whereas SEN requires a determminant 1， which requires SON， which requires no mirroring as allowed。

So we're really only going to care about SEN， but again， S just means no。No， no reflections。



![](img/b6596711533b8ea1c8690bac57ba445f_67.png)

So a rigid motion is just something that preserves distance right because if you think about it。

 if you deflect your thing， that means something gets closer to something else。

 so the whole content of any kind of rigid motion we have is the exact same thing as talking about something being an SEN。

So in particular anything in real life that you do that isn't messing with any kind of distance it's something in Se3 so whenever whenever you talk about you know the distance from like a robot manipulator to the robot base or you know you to the lab wall or whatever it is that you're talking about that's all described by something in a special Euclidean group this is just kind of the abstract formalism to put everything together so of course all of kinematic dynamics and all this stuff has lots to do with rigid body things and what we're going to do is we're going to now look at these matrix groups as opposed to you know just you know the equations of motion or whatnot。



![](img/b6596711533b8ea1c8690bac57ba445f_69.png)

So a rigid body again， is just something that is rigid。

 which means that you know nothing no2 particles can get closer further apart。

 which again really just goes back to the special Euclidean nature that you can't get closer further away。

So the only valid thing you can do with a rigid body is you can only rotate it or you can translate it。

 you can't sharear a rigid body because then it would no longer be rigid because then you're tearing it apart。



![](img/b6596711533b8ea1c8690bac57ba445f_71.png)

So again， a rigid motion is anything that takes this thing and preserves the fact that it's rigid。

 so really all this is setting up is you have your collection of points that aren't going to drift closer further away and the only valid thing you can do to this thing is something in a special Euclidean group but you're going to rotate it or translate and you're going to keep points from getting closer and points from getting further apart。

嗯。

![](img/b6596711533b8ea1c8690bac57ba445f_73.png)

So。We're gonna to get into a little bit of terminology right you guys have your body fixed frame in your inertial coordinate frame right so the inertial frame or your lab frame or whatever you engineers call it and the body frame is whatever I guess the body frame right but again right from the body to the lab nothing has happened it's not rigid so the way you go from a body fixed coordinate frame to an inertial coordinate where from an inertial to body or body to inertial is by using an SC3 matrix is a way we can write this down so we can do these coordinate changes all using this language of matrix groups which makes things be very very nifty。

So what we have is we have a let's call A our inertial frame， and let's called B， our body frame。



![](img/b6596711533b8ea1c8690bac57ba445f_75.png)

So we have this nice nifty picture。And suppose what we do is we have X。

 Y and z the coordinates of B relative to A right， so then out of this we can build this matrix。

And according to this slide， this matrix is a rotation matrix， but why is this rotation。

 why is this matrix a rotation matrix？Is the sharing origin？That's not enough。

That means there's no translations。But that doesn't say why the remember to be a rotation matrix are our transpo has be the identity。

So why does RR transpose if you build any matrix this way， why does this have to be orthogonal？😡。

It's not quite。Full rank just means to determine it's not 0。 I want to determine it's one。 I mean。

 I want R our trans post to be the identity， which is a much stronger condition than being。

Nondegen or full rank， whatever language you use。Well， okay， so let's think about this。

 We have these three vectors， x， Y， and z。 What do we know about these three vectors？

They're orthogonal to each other and。Well， okay， yeah， we're in our three。

The orthogonal were an r3 and what's the other nice thing about these？A all unit， right。

 these are orthogonal unit vectors。😡，Okay， so if we take the matrix， R our transpose。

There really aren't enough markers in this room。You' see。So if we have。Our。Our transpose。

what is this matrix going to be？OrWe want this to be the identity， but what actually is it？Well。

 so this is going to be right， so there's three columns， it iss going to be x Y。And Z。Times。

Let's write it this way。Times the transpose， right？

So how does matrix multiplication work where that this comes from going across and down right。

 so when we multiply these things throughout。This matrix is going to give us， well。

 the upper left hand coordinate is going to be the dot product of x and X。

 then we're going to have x dot y， and then x dot z。Y dot X， Y dot Y。Y dot c。Z dot x。This isZ dot。

Why。And z dot C。Right。And then what do we know about all these dot products？Well。

 what do we know about x and Y？the orthogonal so the dot product has to be zero X and Z is again orthogonal so they got to be zero。

 so all of these things are zero。 and then we had to question about why these things had to be unit vectors because when they're unit vectors。

 what does a diagonal have to be。One， so what happens is we get the identity。

Okay so a nice thing to know about rotation matrices if you don't know this it's a good thing to know if all the columns are orthogonal unit vectors。

 then your matrix is that corresponds to it being a rotation matrix likewise any rotation matrix。

 all the columns are going to be orthogonal unit vectors。

 if it's all orthogonal unit vectors it its rotation and back and forth okay so that's how we know this you know change of coordinate frame is going to give us by something it's a rotation matrix。

Okay。Questions about that yeah。Would I mess up？This matrix。Well， okay。Fine。那 good。And again， right。O。



![](img/b6596711533b8ea1c8690bac57ba445f_77.png)

So again， right just reviewing， so now we're considering ourselves an R3。

 so our R matrix that we do to go between coordinate frames， as we said， right as a rotation matrix。

 which just means R transpo or R transpose R is the identity， which we saw from that computation。

And then of course we're assuming it's special， which means there's no mirroring going on。

 so we're assuming that the determine is one。

![](img/b6596711533b8ea1c8690bac57ba445f_79.png)

So we have our group of rotation matrices， this is a typo that should be J3。

 and again now we're just only viewing on three dimensional things as opposed to arbitrary dimensions so you can kind of view this。

The set of SO3， which is again， a matrix group on its own right。

 we're calling this the rotation group。Okay， so03 and SO3 right is again。

 the same thing minus if you get reflected or not， but from here on out。

 we're going to just ignore03 even exists and rotation things mean SO3。Okay。

And any way you can rotate around is described by something in S3 whichs often the last example right if we have any coordinate frame B and any coordinate frame A you can relate the to with just any kind of rotation matrix so if you say A is the one given by God and it's the greatest coordinate system ever every single other coordinate system B is synonymous with just describing your rotation matrix so really orientations and。



![](img/b6596711533b8ea1c8690bac57ba445f_81.png)

![](img/b6596711533b8ea1c8690bac57ba445f_82.png)

![](img/b6596711533b8ea1c8690bac57ba445f_83.png)

Such are synonymous with just being an element of SO3。

And the last thing we want to talk about is a trajectory in SSSO3 is just a curve that slides in SO3 so here we say t is between minus epsilon and epsilon。

 but that's just arbitrary it's just something where we have some kind of time domain and doesn it really doesn't matter what it is just know we have some start time and some end time and all the way in between this is something in SO3 so if you think about it right is your robot arm is moving and the things are rotating at each time instance right it's at some different orientation and the collection of all that trajectory together is full a trajectory。



![](img/b6596711533b8ea1c8690bac57ba445f_85.png)

So again we have our usual composite rules which just mean that these things work the way you think they are right so RAB and RBC are constructed in the ways that you think they should be just given by all of these coordinate expressions and the thing at the bottom says when you multiply them together to behave the exact way you think they should B in terms of A and C in terms of B or when you compose them together you get A in terms of C these things can't stop which means you do you can measure A and B。

 you can measure B and C and that for free gives you the measurement between A and C。



![](img/b6596711533b8ea1c8690bac57ba445f_87.png)

So what we can think about now is if we have our AC which again is artation matrix from before。

 we can view this as a matrix which just takes three vectors。

 you multiply them together and you get another three dimensional vector but if you have these three numbers what it does is your first three numbers are coordinates and according to C and then your last three numbers you get after multiplying this matrix is going to give you coordinates in terms of a so if you have a measurement on some robot and you have you know the angles or whatnot that the robot's hand is saying according to the robot but you don't care what the robot says you care what the room says what you do is you just multiply it by the matrix between the room and the robot and that gives you everything that you need so it's really just bookkeeping which is the boring part。



![](img/b6596711533b8ea1c8690bac57ba445f_89.png)

So everything we've done so far is only for the rotations， we've only dealt with the rotation matrix。

 but of course， in real life you're allowed to do more than just rotate。

 you're allowed to translate as well。So what we have now is in addition to the matrix RB。

 we also have a vector PAB which tells you how much you move in what direction so in real life right is your robot's moving around out you know exploring its life it can both rotate on its own but you got to keep track of and it can else move wherever it wants so again we got to know this translation and rotation and of course this thing together this GAB this is going to belong to the special Euclidean group which just means it's rotation and a translation。



![](img/b6596711533b8ea1c8690bac57ba445f_91.png)

So again， as we saw earlier， the special Euclidean group is just something that is both a translation and a rotation。

And the way you think about it now is you have this element G， but G represents the pair together。

 it's both the translation and the rotation that when you move by G。

 it's the same thing as moving along by P and then rotating by Q。Okay， so a thing to be very。

 very careful about and this is kind of nitpicy is if you translate first and rotate second。

 and then if you rotate first and translate second， you will get different answers。

So it's very important again with your bookkeeping， you keep track with this so according to this。

 right？Forula here， do you rotate first or do you translate first？You rotate first。

Because you think about it， you have your vector Q。😡。

Wwhichch is where you are you hit it with R and then you add on P。 if you translate it first。

 it would be r times the quantity P plus Q， which again would just be a different answer you got to deal with and ultimately it really doesn't matter which one you do you can either do rotations first or translations first。

 the only thing that's important is you're just consistent in what you're doing you can do this however you want you just got to make sure you do the same thing because if you change what you're doing。

 then you're just going to get wrong answers and that's not fun。



![](img/b6596711533b8ea1c8690bac57ba445f_93.png)

![](img/b6596711533b8ea1c8690bac57ba445f_94.png)

So as we saw here， we've kind of seen two different ways to write the special Euclidean group。

 so I like this way more but Monnie， I think likes the other way more。

So I guess I have to tell you both。I still don't have a marker。Is we can think of SE3。

We can either think of this as the set。Of translations and rotations。

Or we can also think of this as something in the Aine group that we showed earlier。

 and these are going to be matrices of this form。Okay and a thing to keep in mind these two are the exact same ways to do it right what we're doing is here we're keeping track of everything as a four by four matrix here we're saying a screw that and we're just recording p and Q separately or sorry Q and P and R separately from one another but these are both the exact same ways to do it I prefer this for I think mine prefers this way it's the exact same thing it doesn't matter and again if you think about this。

If you do PR。Right， so your translation and your rotation and you take。Your measurement Q。

 this is going to be P plus R Q。Whereas if you use the second way。

 you got to use homogeneous coordinates。And you're going to get RPp0，1。Times Q1。

Which is going to give you。RQ。Plus P。1。RightSo when you forget the one and you're going to get the exact same answer。

我 throw。AThat's a lot better。Okay， let's rewrite this then。

All rightSo are two ways of viewing the special Euclidean group。Is we can either say SE3。

Is given as a pair of a matrix and a vector。Or we can view this。As four by four matrices。

And the only difference is the bookkeeping because if we take our P and R。And act on a point Q。

 this is going to be p plus R Q。And if we take our matrix。On Q1。We're going to get RQ。Ppy。

You can to be that better。All right。So again， these are both completely synonymous ways of doing it。

 they're just kind of different bookkeeping right if you're doing the math of things it works probably better this way where you's actually trying to you know tell MatTLb to do something。

 it's easier to store a four by four matrix， but again。

 if using the matrix notation you got to remember that this wouldn't have to end as garbage and you just got to ignore it at the end。

So based off of this。😡，It seems。Like we have this following thing here。So so far。

 it looks like the S3。Is equal。To S， O，3。Times R3 because it's just given by a par it's given by a rotation matrix and a translation and you can either record it just as this pair of the two or you can try to encode it as a matrix。

 but why is this equation wrong or at the very least misleading？Well， if we have two things。

 let's say P and R。And let's say we have。I don't know， Q and S。

If we multiply these two things together。So according to multiplication is the group thing where we translate and rotate and then we translate and rotate again。

Does this thing equal？P plus Q。And then r times S。If you scooch some and rotate some and you scooch some more and you rotate some more。

 does that equal scootch in twice and rotating twice？Is this formula true？No， right。

 what is the correct formula？Well， the way you can think about this correct formula is well you just do these matrices and you just do the matrix multiplication right。

 so we can think about this as RPRP01。An SQ。0ero1。And when you multiply these together， you get Rs。

You get R Q。Plus， P。0。1。Right。So the actual correct answer you get when you compose these is you get RQ plus P and then RS。

Okay， so one of the nice things about this is the rotations do play nicely together if you rotate some and then rotate some more。

 that's the same thing as rotating twice。But if you rotate and translate。

 then you can't just add the translations together， you have this extra term pops in Okay。

 so if you want to really impress your friends what the correct notation is you do with this。

And as's called a semi direct product is a thing on the right to normal subgroup。

 so if you want your $5 word of the day， you can say that。

But again we're not going to go into details as main thing to keep in mind is when you do these。

 it's not just the same as just doing them individually。

 there's a little bit of this crossplay comes into terms here。That you have to keep track of。



![](img/b6596711533b8ea1c8690bac57ba445f_96.png)

So again， that's kind of what we're seeing here， a way you can view these SE3 in terms of homogenous coordinates is when you do this thing with the one on the end。

 you view these as four by four matrices， so if you call homogenous coordinates that means you do the big matrix thing and you have this extra one floating around where of course you don't need to do that but of course you can。

So the homogenant cos of point Q just means to take Q when you turn into a fourth vector。

 but the fourth co is always one。But again， now we're talking about， you know。

 you have your trajectory， you have your actual pathy robots taking through all of these motions。

Which means we care about our speed， which means we care about differentiating things。

So if we take this homogenous coordinate and we differentiate everything。

 well we don't know what these things have to be， but the derivative of one always has to be zero right。

 I mean if you differentiate a constant that's always zero， hopefully you guys know that。

So that's why when you do the homogenous velocities or whatever you want to call them。

 you have these three terms which correspond to how fast these three things are moving。

 but then the last term is always going to be given by a zero because one never changes。



![](img/b6596711533b8ea1c8690bac57ba445f_98.png)

So a couple rules that we're talking about， so a way to think about this here。😡。



![](img/b6596711533b8ea1c8690bac57ba445f_100.png)

Is the coordinates of a point is the actual location that you were at。

 whereas the vector is the velocity that you are going。

 so a way to think about these things is points are locations and velocities are vector。



![](img/b6596711533b8ea1c8690bac57ba445f_102.png)

So in terms of this， if you take the sum indifference of a vector。

 you can do that because the vector is velocity， you can add and attract velocity when we tell them you get back a velocity。

 which is a vector。If you take a vector and a point， that means you have a location。

 you add to it a movement and you're going to end up at a new point。

 so a vector plus a point equals a point。The difference between two points is going to be the distance between them which is going to give you a velocity of some sort。

 if you attracttract two points from each other you get a vector。

 but adding two points is garbage doesn't make sense to add two locations to each other。

This is a bit odd because everything we're dealing with our。😡，4our by one vectors。

 but only the things that we call vectors which are these things where the fourth coordinate is0。

 these are the only things we're legally allowed to add to each other we can add a V to a Q。

 we can add a V to a V but a  Q plus a Q is stupid and another way you can think about this is the last coordinate and always has to be0 or1 if you take two of these and subtract them from each other you're going to get the last coordinate of V which is going to be a vector but if you add two of last coordinate is going to be a2 and that's garbage you don't do that。



![](img/b6596711533b8ea1c8690bac57ba445f_104.png)

So I guess as a way to protect your last digit has to be a zero or a1 last dig it's a zero。

 it's a motion， if last dig it's a one it's a location。



![](img/b6596711533b8ea1c8690bac57ba445f_106.png)

So if the last coordinate is zero， it is motion， it is a velocity vector。

 it is what you're moving somehow， the last coordinateator is a one， it's a physical location。

And if it was anything but zero or1， you made a mistake。



![](img/b6596711533b8ea1c8690bac57ba445f_108.png)

![](img/b6596711533b8ea1c8690bac57ba445f_109.png)

So what we do is if we have an actual element that's a4 by four。

 so it's the other version of Se3 that we talked about that's called a homogenous representation because it actson homogenous coordinates which is this thing with the zero or the one added at the end so as we saw over there write a homogenous so this pair is the thing that Se3 because really all Se3 is as rotations and translations together if you choose to represent them this way。

 that's just called the homogenous way to do it if you don't specify homogenous and you would however you want。

 but if you use the word homogenous thiss going to be done as that matrix and again as we see down here the same rule applies if you multiply the two together the two rotations multiply together but the two positions don't add they have this extra weird in between term going on。

Questions。Yeah。Yeah， I'm going to be a specific one， you know， when we do examples and whatnot。

 but H is just the pair and it's encoded as this4 by four。

So all that we're saying is when we say homogenous， we mean this notation， not this notation。

RightThey're both the same， but in terms of bookkeing。

 homogenous has this extra one thing going on at the bottom， this would be called non。

 I don't know what you would call this top one。Hology specifically means this bottom one。



![](img/b6596711533b8ea1c8690bac57ba445f_111.png)

So again， we can do this and remember this thing has to be a group。

 which means you got to be able to invert them， so homework for you guys is to understand why H invert has this form。

So again it's straightforward enough to tell why this r is r transpose because remember R times r transpos the identity。

 so this is going to give you the identity， but remember this term has this extra r transpose in it。

 so it's your homework， I mean it's a 32 scribble you can do to figure out why HH inverse and H inverse A test to be the identity matrix。

😡，系。Are you guys properly confused because it's going to get more confusing now？



![](img/b6596711533b8ea1c8690bac57ba445f_113.png)

So a matrix group is just a set of matrices that follow the group laws， right。

 it's got to you know be closed under multiplication， it's got to have inverses。

 it's got to be associative and it's got to have an identity element。

But we can view this thing as opposed from just these pure formulas。

 we can also view this thing as an actual geometric object we can actually think about the set of all of these rotation matrices as its own geometry and we can think about the shape of all the different possible shapes on their own if that makes any kind of sense so we can think of right is matrices are just the grid of n by end numbers so that's the same thing is just n square dimensional space so our matrix group lives inside in really large dimensional space so it's just gonna be a shape of its own right we can talk about now about the geometry of this thing that lies inside this big so right over there the homogenous coordinates with a four by four matrix so our special Euclidean group lives in some 16 dimensional space。

 whatever it is okay so again we can talk about the geometry but this is gonna to make your brains bleak because you got think about 16 dimensional geometry for this but I mean。

In math， we can do this， right？And likewise， since we can talk about these as being shaped。

 we can also talk about the tangent space， so as a quick reading， if I say manifold or tangent space。

 does that mean anything to anyone？Okay， then you're going to be in for fun。



![](img/b6596711533b8ea1c8690bac57ba445f_115.png)

落背。So this is where things are going to get a little bit hairy。

 but it's not very important that you understand the equations it's more important you understand what physically is going on so a tangent space is literally the tangent so I mean you guys have all taken cow1 I think and you know what like a tangent is right it's the curve it's the line that lies nestled above a curve right this is just the exact same thing but just more abstract so to draw a picture。

😡。

![](img/b6596711533b8ea1c8690bac57ba445f_117.png)

![](img/b6596711533b8ea1c8690bac57ba445f_118.png)

![](img/b6596711533b8ea1c8690bac57ba445f_119.png)

![](img/b6596711533b8ea1c8690bac57ba445f_120.png)

So we have a picture that's a little bit exciting to draw I suppose we have a sphere。

So this is some shape living inside R3。And suppose we have some kind of a curve。



![](img/b6596711533b8ea1c8690bac57ba445f_122.png)

I got to draw this without making it look too terrible and suppose we have some point on this curve。

It makes sense to ask about the tangent， right， if we do this tangent of this curve， mathematically。

 what's another way to rephrase the word tangent to this curve？Startarch with a D。Drivative。

 right if you differentiate the curve， that's going to give you the tangent on it， right？Right。

So the tangent is going to be given。By this thing， so now what we do is we can ask the question of what are all the possible different tangents right and if we come up with every single possible curve to this point。

 what we're going to end up with is some sort of a plane，Lying on this sphere。

Okay so the tangent space on the sphere is literally you just take a plane and you nestled on top of the sphere right I mean mathematically gets a little funky but the fundamental idea is you just literally just take a tangent thing to it right if you have a three- dimensional thing。

 your tangent space is now going to be three dimensional but the construction is the same it's really you take the curves and you look at their derivatives but you're going to be tangent vectors you take all possible tangent vectors that's going to give you some sort of a plane or a three space or whatever。



![](img/b6596711533b8ea1c8690bac57ba445f_124.png)

So that's what this definition is saying here， we have some kind of a curve。

And we record its derivative and all possible derivatives we have is its tangent space。

 so in space in the same sense we have the tangent space to the sphere as this plane that the plane hold all the possible tangent vectors we could draw at that point。

 which comes from differentiating these curves。So tangent space is kind of。Like the derivative space。

 I suppose you could call it。Okay， and again， this is for a two dimensional case。

 but when you get these larger dimensional things， the idea still hold you just intuition kind of as falls to crap。

m but again， this will be useful because we can kind of。

Write down equations somewhat using this idea。 But really。

 what happens is there' just some sort of a flat space tied to the thing。



![](img/b6596711533b8ea1c8690bac57ba445f_126.png)

So。What we have is right， we have our tangent space。

 which is going to be this flat space that's nestled against whatever our shape is of whatever sort。



![](img/b6596711533b8ea1c8690bac57ba445f_128.png)

But again， if we have our matrix group， we have a very special element of our matrix group that's the identity element。

 if we draw the tangent space at the identity element， that thing is called the algebra。

Guys follow that at all。Now。Let's draw another example。



![](img/b6596711533b8ea1c8690bac57ba445f_130.png)

So let's draw a very simple example， let's draw a circle。O。So if you have a circle。

This is the same thing as S2。

![](img/b6596711533b8ea1c8690bac57ba445f_132.png)

Because if you think about it， each S2 are just rotations in the plane。

 and anyway way you could rotate it in the plane as given by some angle which you could draw in a circle。

Okay， so what you do is you have some point here， let's call it zero。Right。



![](img/b6596711533b8ea1c8690bac57ba445f_134.png)

If you choose the point theta， that's going to be the same thing as rotating counterclockwise by the point theta。

O。And again， so this is a matrix group， but we're just drawing it as a circle。

This point right here is 0， which is the identity， which means if we rotate by 0， nothing happens。

 we can draw a tangent space to 0， which here is going to be this thing。

It's just going to be the line。And this line is called the Le Albra。Okay， so you have a matrix group。

 you pick the identity element that does nothing， you draw whatever the tangent space。

 it's either going to be a tangent line or a tangent plane or a tangent three dimensional thing or whatever it is right this thing by itself is called a algebra。



![](img/b6596711533b8ea1c8690bac57ba445f_136.png)

O。And then the way we do it is you always use the math fracrack font。

And then that's just the same thing as a tan space any， but it turns out this thing is actually very。

 very， very， very important and it turns out if you know what this is。

 you can reconstruct the whole group， it seems a bit odd that if you know just this line you can figure out that a whole circle came from this line it's easy to go from circle to line but it's a bit odd that you can go from line to circle and we'll see a little bit about how you can do that。

And again， we'll also see a little bit if you have scarier things in just a simple circle。

 it's still possible to figure out and say things about the algebra。But I mean， we'll do what we can。



![](img/b6596711533b8ea1c8690bac57ba445f_138.png)

扯来的看。So okay， so if we are in， let's say， SO3。And let's say you have the lab frame and the coordinate or the lab frame in your inertial frame。

And that's say they're currently lined up， nothing has happened。Right。

The tanent space at the identity means you start off at the identity and nothing's going。

 And if you move a little bit， it's going to tell you in essence how fast you're moving。

 So basically， your angular velocities are what's going to live in the Le algebra。

So in the same sense that your Euler angles belong to S3。They' are derivatives。

 which are your angular velocities to live in the the algebra。That makes sense。

Whats the derivative of the reference space？So the lead group， sorry I keep saying lead group。

 the matrix group， which you're going to see matrix groups and lead groups are the same thing matrix groups are your positions。

 your lead algebras are really the velocities。U probably。I don't know how this works。

 Monnie gave me these slides， so I guess if you ask him he'll probably give them to you。

 I don't see why not or if email if you're talking after class， I can email them to you。

 it's not a big issue， I don't have access to Canva so。But of course。

 what you can do is if you Google league groups， there's like an 80 page Wikipedia article。

 which is a good place to start if you' like Wikipedia more than me。



![](img/b6596711533b8ea1c8690bac57ba445f_140.png)

All right。

![](img/b6596711533b8ea1c8690bac57ba445f_142.png)

What we have is the Lee algebra， which is this tan in space。



![](img/b6596711533b8ea1c8690bac57ba445f_144.png)

If we have our matrix group， this is just going to be some subspace of all matrices。



![](img/b6596711533b8ea1c8690bac57ba445f_146.png)

So a little subtle thing to keep track of is remember。

 a general linear matrix means it's not singular， it means the determinant is not zero。



![](img/b6596711533b8ea1c8690bac57ba445f_148.png)

But this thing is allowed to have determinants zero。

Because the kind of way to think about it is this includes all of the speeds you can go at right this is your positions。

 this is your velocities if you're not moving your velocity is zero and of course the determinator is zero is going to be zero so this of course is going to be bigger than that and this of course can contain singular things。

And another thing to keep track of， if we go back here， we have a circle， right。

 what is a dimension of the circle？

![](img/b6596711533b8ea1c8690bac57ba445f_150.png)

RightThe disk which is the filled in circles two dimensional but when I say circle I just mean the skin of the circle and the dimension of the circle by itself is one dimensional and likewise the dimension of this line is one dimensional on this example the sphere and when I say sphere I mean just the skin of the sphere right not the interior is twodial this plane is two dimensional so nice thing that we have that we see down here is the dimension of the matrix hoop and the dimension of the le algebra always going to be the same number。



![](img/b6596711533b8ea1c8690bac57ba445f_152.png)

![](img/b6596711533b8ea1c8690bac57ba445f_153.png)

![](img/b6596711533b8ea1c8690bac57ba445f_154.png)

![](img/b6596711533b8ea1c8690bac57ba445f_155.png)

So a thing to think about with this special Euclidean group。

 what is the dimension of the special Euclidean group？



![](img/b6596711533b8ea1c8690bac57ba445f_157.png)

![](img/b6596711533b8ea1c8690bac57ba445f_158.png)

Well， let's break this down， what's the dimension of r3？Three right what's the dimension of SO3？

How many different ways can you move in SO3？EO3 by itself。Three， right。

 you have y'all pitch and roll。Right， and you have X， Y， and Z。

So if you have three different ways to rotate， three different ways way to train that this is six dimensional。

So if we do the Lee algebra of this， that's going to be six dimensional as well。So whatever we do。

 this thing should be six dimensional， this thing will be three dimensional。

 and this thing will be three dimensional is to try to keep our heads a little bit on straight。



![](img/b6596711533b8ea1c8690bac57ba445f_160.png)

![](img/b6596711533b8ea1c8690bac57ba445f_161.png)

![](img/b6596711533b8ea1c8690bac57ba445f_162.png)

All right， so the very first thing we're going to think about is if we have the general linear group。

 so the biggest matrix group we can think of just anything that's not singular， right。



![](img/b6596711533b8ea1c8690bac57ba445f_164.png)

Lee algebrage， which is a tan based identity is going to include everything。



![](img/b6596711533b8ea1c8690bac57ba445f_166.png)

And so we're going to ask why does this include everything， right。

 why is the tangent space of invertible matrices every single possible matrix？



![](img/b6596711533b8ea1c8690bac57ba445f_168.png)

![](img/b6596711533b8ea1c8690bac57ba445f_169.png)

And if you think about this， if we go back。

![](img/b6596711533b8ea1c8690bac57ba445f_171.png)

to this definition， the tangent space is going to be all derivatives of all curves that pass through that point。

So what we're going to do is we're going to choose a curve that's the identity matrix at zero。

And we're going to differentiate it， and we're going to show that we can get every single possible matrix out as some sort of a derivative。

 and that's going to build a srctent space。

![](img/b6596711533b8ea1c8690bac57ba445f_173.png)

![](img/b6596711533b8ea1c8690bac57ba445f_174.png)

So what we have here。I we choose an arbitrary thing an arbitrary matrix this can be as singular as you want it to be it doesn't matter right then what you do is you take the identity element plus some translation by this and of course when you differentiate this curve。

 what's your answer going to be。

![](img/b6596711533b8ea1c8690bac57ba445f_176.png)

![](img/b6596711533b8ea1c8690bac57ba445f_177.png)

W what's the derivative of I going to be？0ero， whats the derivative of something linear？Just a。

 right？So the derivative of this is going to be a， and likewise， when you plug in zero。

 what are you going to get？Not zero， not a。I， right， so this curve has slope A。

And it passes through the point I。

![](img/b6596711533b8ea1c8690bac57ba445f_179.png)

So what that says is。The point A is in the Le algebra。



![](img/b6596711533b8ea1c8690bac57ba445f_181.png)

If all of this circular logic is making any sense at all to you guys， right。

 it's perfectly fine if it doesn't， this is pi three semesters worth of 600 level math classes you guys have taken in an hour。



![](img/b6596711533b8ea1c8690bac57ba445f_183.png)

![](img/b6596711533b8ea1c8690bac57ba445f_184.png)

So。And again， the only other self that we got to do is we have this curve that at zero gives us our identity element and it has slope a。

 but we got to of course make sure this thing lies in the group of all invertible matrices because if it's not then it's kind of stupid and the way you do that is you say well the determinant of zero is one determinant is continuous so on a small enough interval we can't cross zero if you're at one in you're continuous you can't tele a port to zero instantly it's got to at least take you like a couple seconds to get to zero and in that restricted little window you're gonna be invertible everywhere so you have a good well defineded curve。



![](img/b6596711533b8ea1c8690bac57ba445f_186.png)

![](img/b6596711533b8ea1c8690bac57ba445f_187.png)

![](img/b6596711533b8ea1c8690bac57ba445f_188.png)

So if all of this was Greek to you， the takeaway is a the algebra of all inverttable matrices are all matrices。

 and then we can move on with our lives。

![](img/b6596711533b8ea1c8690bac57ba445f_190.png)

![](img/b6596711533b8ea1c8690bac57ba445f_191.png)

![](img/b6596711533b8ea1c8690bac57ba445f_192.png)

是。The Lee algebra of all invertible matrices are all of matrices。



![](img/b6596711533b8ea1c8690bac57ba445f_194.png)

![](img/b6596711533b8ea1c8690bac57ba445f_195.png)

Everyone， good with this。At least with the takeaway of it。Okay。😊。

The Lee algebra of all invertible matrices is all matrices。



![](img/b6596711533b8ea1c8690bac57ba445f_197.png)

I didn't say this wasn't going to be confusing。So if that was confusing， we would get more confusing。

So the Lee algebra of all invertible matrices is everything。

 what now is the Lee algebra of orthogonal matrices， so if we look at ON？😡。



![](img/b6596711533b8ea1c8690bac57ba445f_199.png)

So again， we know the answer with S2， the algebra is just going to be this line。Right。

So what's this going to be though in more general cases is it's going to end up being skew right if you think about it。

 matric C is that when you add a transpose as zero means that a equals minus a transpose。

 which it is the same thing as it being skeku symmetric right if you transpose it and a minus pops out that skew。

😡，And it turns out the Lee algebra， which is the tangent space at the identity of all rotation matrices is given by all S matrices。

So another way you can kind of think about this is if you have a path of rotations。

 if you differentiate that matrix， that's going to give you a sw matrix is another way to think about it。

So we'll kind of try to come back to some intuition， but first this confuse you a little bit more。



![](img/b6596711533b8ea1c8690bac57ba445f_201.png)

So again we're going to use the same trick where we differentiate things， so we have。

 remember if we have a curve that is a rotation matrix， if you take it。

 times itss transpoer has to be that entity because that's the definition of being a rotation matrix。



![](img/b6596711533b8ea1c8690bac57ba445f_203.png)

What we do here is we differentiate it。which is going to give us gamma dot times gamma transpose plus gamma times gamma transpose dot。

Right。When we plug in zero， we're going to just get back these terms because everything else goes away。

 so I guess to write this down。Okay。Yeah。You have。Gamma of T。

 gamma of T transpose equals the identity。If you differentiate this， you're going to get gamma dot。

Gammma。Transpose plus gamma。Gamma transpo diet。Equals 0。Right。By product rule。But again。

 we're looking at the identity， which means when we plug in zero， we got to get the identity here。

 So what we have is we have gamma dot。Of0 times the identity。I guess we caught eye。Plus， gamma。

 sorry plus I。Times gamma dot transpose。Equals zero， which tells us the gamma dot。Plus。

 gamma dot transpose。Equals 0。Is everyone happy enough with this line of logic？Enough。

So what this tells us is remember this is going to be something that lies in a tangent space because it's a tangent vector。

 and this says it has to be a sku matrix。So what happens is another way you can think about is if you have a rotation and you differentiate a rotation。

 that's going to give you something skew。

![](img/b6596711533b8ea1c8690bac57ba445f_205.png)

Wwhichch we'll look at the cross product later and that's entirely what the cross product is saying so if you've seen the cross product that's just saying a skew thing。

 which is differentiating rotation， it will make probably more sense。



![](img/b6596711533b8ea1c8690bac57ba445f_207.png)

But I'm not going to promise that。

![](img/b6596711533b8ea1c8690bac57ba445f_209.png)

So。What we want to do is we want to choose a normal basis right so if we have S03。

 that's a three dimensional matrix group because you have yaw pitch and roll。

And then what we have now is with the Lee algebra， we have these。

Skeew matrices and what we want to choose is we want to choose them this way right so these are sw matrices and every other sw matrix you can cook up in three by three terms are going to be a sum of these three this is going to give you some sort of a basis of this okay and when you think about it。

 this is rotation about Z， this is rotation about y and this is rotation about x。

So if any of you want to impress me， why is this rotation about Z？Thecon is all here。

 so why is that the kicker？If you're rotating about Z to Z change。😡。

So if you differentiate something that doesn't change， what answer do you get？

Which is why this is all zero on disease， likewise。

 this is all zero on the y's because when you differentiate the y's。

 nothing happens so you get zeros， this one is zero on the x's because when you differentiate x's you get zero。



![](img/b6596711533b8ea1c8690bac57ba445f_211.png)

So。Another thing we can think about is let's say， you don't really to want to deal with all of this garbage because Monnie likes equations and I don't like equations and I don't think you guys either。

 but let's just look at this matrix down here right if you guys have seen notation matrices before what is this matrix describing in R3？



![](img/b6596711533b8ea1c8690bac57ba445f_213.png)

So it is a rotation matrix， but what's going on in this rotation matrix。What's happening？

It is rotation about y by。Well， by angle T， like in radiance， right？Right。

have you guys seen this type of thing before right so this is a rotation matrix about y by angle T。

If you take the derivative of this， what does cosineine T become？



![](img/b6596711533b8ea1c8690bac57ba445f_215.png)

Minus sign， this becomes。If we plug into zero。Right what do we get。

 what does the derivative of this at zero become？0， what is the derivative of this at zero become？

One， this becomes。And this becomes。And then now this is why I'm not crazy because that's entirely what this matrix is。



![](img/b6596711533b8ea1c8690bac57ba445f_217.png)

Okay so this is the derivative of rotating about y and like what we could do is if you do your matrices here the other way right so if you know if it's cosine minus sine sine cosine。

 you take the derivative of that one which is rotationious about x you're going to get the other matrix on the last page and same with all these other ones so if you've seen Euler angles before just the derivative of the oruler angles gives you these three matrices as your yaw pitch in your role like angular velocities。



![](img/b6596711533b8ea1c8690bac57ba445f_219.png)

![](img/b6596711533b8ea1c8690bac57ba445f_220.png)

![](img/b6596711533b8ea1c8690bac57ba445f_221.png)

So hopefully that should make it a little bit maybe kind of clear why the sw thing is not total nonsense。



![](img/b6596711533b8ea1c8690bac57ba445f_223.png)

Okay， but of course， we got to get more nonsensey。

![](img/b6596711533b8ea1c8690bac57ba445f_225.png)

So one of the things that is a great bane to everyone who has ever been alive is if you multiply matrices。

 if you do A B and B A， do you get the same answer。No， so when we do this。

 we got to keep track of what side we multiply on if we go on the left here， if we go on the right。

 we're going to get different answers because you can't flip orders so we have here。

Is if we have a row vector， you can multiply the matrix on the right。



![](img/b6596711533b8ea1c8690bac57ba445f_227.png)

![](img/b6596711533b8ea1c8690bac57ba445f_228.png)

And that's what this are for R gamma means you're multiplying by gamma on the right side。Likewise。

E of Gamma。As you're multiplying it on the left。And the reason for these transpos is x is a row vector。

 x transpose as a column vector， a column vector can get multiplied on the left bio matrixtrix because right the dimensions have to line up。

So L subb， you just multiply it by the blank on the left side。

 R subbk means you got to multiply it by on the right side， and since nature is evil。

 R and L are not going to be the same answer， so again。

 it doesn't matter which one you use you just got to be consistent about it。



![](img/b6596711533b8ea1c8690bac57ba445f_230.png)

And as you'll see， it doesn't matter too too much。So a nice fact that we can say for sure now is that the dimension of the special orthogonal group is given by this formula。



![](img/b6596711533b8ea1c8690bac57ba445f_232.png)

![](img/b6596711533b8ea1c8690bac57ba445f_233.png)

So going back to the quiz question I asked you earlier。

 what is the dimension of rotation matrices in four dimensions？Six does six come from that formula？

And now can you figure out where this formula comes from off of the computations we did earlier？

Or remember， it's all skeosymmetric matrices。So now we can figure out the dimension of rotations by kind the dimensions of sw matrices。

Right。So a thing we can think about。

![](img/b6596711533b8ea1c8690bac57ba445f_235.png)

Before we just jump to that formula here， what is the diagonal on all of these I matrices？😡。



![](img/b6596711533b8ea1c8690bac57ba445f_237.png)

Z right and right that's the thing that all skuw matrices they have to have a zero diagonal because the diagonal doesn't change when you transpose it。

 but the transpose has to be the negative and the only number that's is own negative is zero right so when you have these skew matrices the diagonal is always out。

So you only have the above diagonal and the below diagonal。But again， if you have the above diagonal。

 the below diagonal has to be the negative of it。So if you know what's happening up here。

 you know what's happening everywhere。😡，In this case。

 you have a total of three numbers to choose from。Right in a4 by four you're going have it's going to be these are going to be the triangular numbers right。

 iss going to be three plus another copy of three as the next upper triangular thing goes about and that's how you can cook out this。



![](img/b6596711533b8ea1c8690bac57ba445f_239.png)

![](img/b6596711533b8ea1c8690bac57ba445f_240.png)

Formula right here right so you have a total of n squared entries in your matrix。

 you throw out the diagonal， which is you throw away a copy of n and then you only care about the upper half or the lower half doesn't matter。

 and that is why it's divisible by two。So you have n squared minus n over  two。

 and that's a total number of rotations you can make。

Which gives you in four dimensions you can spin about six different ways。



![](img/b6596711533b8ea1c8690bac57ba445f_242.png)

All right， so to confuse you guys even more。We can now talk about the exponential so if you guys have seen the matrix exponential before this is absolutely the same thing as you've seen before right and of course if you've not seen the matrix exponential。

 if you guys have seen the Taylor series for the normal exponential。

 this is just a Taylor series for the normal exponential okay and we defined exponential of the matrix to just plugging the matrix into the exponential of the normal Taylor series exponential for the normal exponential。

Okay and one of the nice things that we have is this thing always makes sense for any matrix we choose we can exponiate and we get some sort of a matrix that makes sense out of it。

 so probably in your differential equations class right you guys have seen this and this has been useful for you know integrating ODEs and whatnot。



![](img/b6596711533b8ea1c8690bac57ba445f_244.png)

But it's going to be interesting in ways you haven't even fathomed yet。

So remember to come up with something in a tangent space。

 you have to have a curve and the derivative of the curve is going to be a tangent vector and that's how you come up with one of these things in a tangent space。

So the question is， is there a reasonable way to make these curves that give us everything in the tangent space there is there a systematic way to come up with all of these curves that will fill out this plane when we differentiate all of them。

 we can kind of do this ad hoc but is there a uniform way to do it and the way we do this is with the exponential it works out magically somehow。

😡，So again， what we want to do is given anything in the Lee algebra。

 we want to find a curve that when we differentiate the curve。

 it pops out this thing in the the algebra， and again we want a recipe given this find this curve。😡。



![](img/b6596711533b8ea1c8690bac57ba445f_246.png)

So we're going to use this by use of what's called a vector field have you guys seen vector fields before？



![](img/b6596711533b8ea1c8690bac57ba445f_248.png)

This is just ODEs right so vector filled all you're thinking about is just some function RRM that at each point RM it gives you a vector on RM。

 so at each point it gives you a speed in which that you're going so this is just you know you see a ball and you put hair on it and you go about your life。

But a thing called an integral curve now is something that solves this ODE。

 so in the same way that a vector field is just drawing， you know。

Putting carpet on your your shape right， actually following the streamline right is given by your integral curve。

 So an integral curve is just a fancy word for saying a solution to your ODE。



![](img/b6596711533b8ea1c8690bac57ba445f_250.png)

![](img/b6596711533b8ea1c8690bac57ba445f_251.png)

So what we're going to do is these integral curves are going to give us these gammas up here。

 we're going to be able to write down these gammas as integral curves。



![](img/b6596711533b8ea1c8690bac57ba445f_253.png)

So。The proposition is this is just given by exponentiating so if we have a Lee algebra element。

 we exponentiate it， that's going to give us our curve。

 so if we take E to the TA that's going to give us our curve this situation between such that when we differentiate it。

 we're going to get back a。

![](img/b6596711533b8ea1c8690bac57ba445f_255.png)

![](img/b6596711533b8ea1c8690bac57ba445f_256.png)

And the way we think about this is we just do this in terms of the normal Taylor series， right。

 we know the exponentials given by this。When we differentiate it， we get this out right here。

But then what we notice is we going to factor an A out of every single term here。

 when we factor an A out， we get this original term back up here。



![](img/b6596711533b8ea1c8690bac57ba445f_258.png)

![](img/b6596711533b8ea1c8690bac57ba445f_259.png)

So what happens is when we differentiate our curve and8 pops out。



![](img/b6596711533b8ea1c8690bac57ba445f_261.png)

But again， our original curve， when you plug 0 in for t， what answer do we get with e to the0？One。

 but what's one in terms of a matrix？It's the identity matrix right so with this curve when we plug in zero。

 we get the identity matrix， which is where the Le algebra is taking place at and it gives us our velocity that we're looking for so a very useful formula。



![](img/b6596711533b8ea1c8690bac57ba445f_263.png)

For going between this tangent space garbage and the actual locations on it is by using the exponential map if we exponential matrices。

 we can go between the two and of course if you want to go the other direction you got to take the logarith。

Of course， a matrix log is a little bit weirder of a thing。To talk about。



![](img/b6596711533b8ea1c8690bac57ba445f_265.png)

So again， what we're saying here。Is remember， our sub gamma of x is we're just multiplying x on the right by the matrix gamma。



![](img/b6596711533b8ea1c8690bac57ba445f_267.png)

And as we said， and also here， L subgame is multiplying on the left。



![](img/b6596711533b8ea1c8690bac57ba445f_269.png)

And going back here。

![](img/b6596711533b8ea1c8690bac57ba445f_271.png)

Well the nice things that happens with exponentials is you can factor the A out on both sides because normally it matters which order you do first when you multiply matrices。

 but in terms of exponentials it commutes you can either pull the A out first or pull the A out second so in terms when you cook up the curves this way it works left or it works right。

 they both give you the same answer in this case， which is one the reasons why exponentials are wonderful creatures。



![](img/b6596711533b8ea1c8690bac57ba445f_273.png)

![](img/b6596711533b8ea1c8690bac57ba445f_274.png)

![](img/b6596711533b8ea1c8690bac57ba445f_275.png)

So questions about that。

![](img/b6596711533b8ea1c8690bac57ba445f_277.png)

We're getting close to the end， I promise you。

![](img/b6596711533b8ea1c8690bac57ba445f_279.png)

は。So what we can think about here。

![](img/b6596711533b8ea1c8690bac57ba445f_281.png)

Is we can take our left translation， so we have our matrix group。



![](img/b6596711533b8ea1c8690bac57ba445f_283.png)

Of translation just means we multiply on the left by this matrix we use the word translation。

 but it's really multi， it's just left multiplication， so LG just means multiply on the left by G。

And the same way that this causes the points on our circle to move about。

 we can also move tangent vectors around by this point by using the same differentiation rules。So。



![](img/b6596711533b8ea1c8690bac57ba445f_285.png)

How does Moi word this？

![](img/b6596711533b8ea1c8690bac57ba445f_287.png)

So the way to think about this， I guess let's go on to the next。



![](img/b6596711533b8ea1c8690bac57ba445f_289.png)

Yeah， so if we have our original curve。

![](img/b6596711533b8ea1c8690bac57ba445f_291.png)

Here， right， this remember， this thing has derivative A。 We translate it to the left by G。 Now。

 when we differentiate this thing at0， what is our answer going to be， it's no longer going to be a。

 Now it's going to be what。A。You have a constant times an exponential。

 you differentiate it what happens to the constant。Stays the same， right。

 nothing scary is going on for the first time， right？You're going to get just G times a。

So in the same way that we can multiply the actual positions by G。

 we can also multiply velocities by G as well。

![](img/b6596711533b8ea1c8690bac57ba445f_293.png)

Which will come in handy in a little bit。So。What we have， is remember， this thing is a curve。

 right that at zero， it's derivative as a。 if we do left translation。

 it's derivative as you're going to be GA。But likewise we could also do right translation if you wanted to instead and this is going to have derivative AG so derivative GA and derivative AG both makes sense it just depends upon which bookkeeping measure you use and one the truly。

 truly weird thing about this is if you use left translation that gives you your coreorance and body frame and if you use right translation just gives it to you in a spatial frame。

So this is a thing just to memorize if you're feeling really， really adventurous。

 there's a wonderful book by Abraham and Marden called Foundations of Mechanics。

 and in it is about 100 pages using like really scary topology explaining why this actually makes sense。

 but if you aren't super brave， you can just take my word for it。

 that when you use for whatever reason， when you use left translations that tells you things in terms of body coordinates。

 if you use right translations or works better for spatial coordinates。

But in terms of actually doing the math， it doesn't matter， but for your bookkeeping。

 it kind of does。

![](img/b6596711533b8ea1c8690bac57ba445f_295.png)

All right。So。We're nearing the end here。One of the nice things that we can have is if we have a matrix group we can define conjugation so in terms of before if we have we want to do different coordinate changes。

 conjugation is the same thing as doing a coordinate change have you guys seen that before。

So here if G was your RAB， if you do RAB times something times RAB inverse。

 this takes something and you can change your coordinateator frame by doing it so you probably see examples of this at some point hidden somewhere。

 but really all you're doing is you're taking your matrix A and you're just surrounding it by inverses a not。

And then again what we can do is we can differentiate this and when we differentiate this。

 remember we use the words derivative that means tangent space and tangent space in this sense means le algebras。

 so when we differentiate it we're going to get something down the algebra and it looks scary but it's not all that means is now what we're doing is we're conjugating a le algebra element so before。



![](img/b6596711533b8ea1c8690bac57ba445f_297.png)

![](img/b6596711533b8ea1c8690bac57ba445f_298.png)

What was going on？

![](img/b6596711533b8ea1c8690bac57ba445f_300.png)

Is these are raw matrices right G was a matrix A is a matrix， G's is another matrix。

 these all belong to the lead group， whereas when we use the word add joint。



![](img/b6596711533b8ea1c8690bac57ba445f_302.png)

This thing in the middle now belongs to the algebra。

 so basically what's going on now is both G and G inverse are going to be rotation matrices。

 but this B now is going to be a s matrix。But again， you can so this multiply them together。

 so when you ever use the word add joint， that really just means you're conjugating the algebra element。

So it sounds scary than it is， all it is is just multiplying on both sides。



![](img/b6596711533b8ea1c8690bac57ba445f_304.png)

So a thing that interesting is if everything commutes， then nothing happens。 So what that means。

 if you go back here。

![](img/b6596711533b8ea1c8690bac57ba445f_306.png)

If if A and G commute with each other that means you can flop the orders right so you can pull this A out you get A G G inverse and everything cancels out and you're just going to get back A nothing is going to happen so if everything is commutative this map doesn't do anything so when you differentiate it。

 you know if you differentiate doing nothing then really nothing is going to happen so。



![](img/b6596711533b8ea1c8690bac57ba445f_308.png)

That's why if your group is communutative， then the identity doesn't do anything because conjugation doesn't do anything。

So really what's going on when you take your ad joint map。

If it tells you anything other than the identity， this just tells you how much things fail to commute。

 this tells you how much I guess order matters in your procedure。

 if you rotate by something and then rotate by something else。

 it tells you how important the order of your rotations are。

But you can just view it as this conjugation thing。



![](img/b6596711533b8ea1c8690bac57ba445f_310.png)

But wait， we can even make this more annoying。 We can differentiate it one more time。

 So before what we did。

![](img/b6596711533b8ea1c8690bac57ba445f_312.png)

![](img/b6596711533b8ea1c8690bac57ba445f_313.png)

Is we had this thing and when we differentiate this element A， we got the add joint。

 so we had this conjugation by something in the the algebra。

 The next step we're going to do is we're going to differentiate these outside elements。

And when we do that， what we're going to get is the bracket。



![](img/b6596711533b8ea1c8690bac57ba445f_315.png)

![](img/b6596711533b8ea1c8690bac57ba445f_316.png)

So here again， right what we do is our A of T is going to be the thing so there's going to be A of T。

 B， A of T inverse， now we're going to differentiate the A of T as opposed to thing on the inside。

 and this is going to give us something again our the algebra and what's going to be surprising is this isn't going to be too terrible looking。



![](img/b6596711533b8ea1c8690bac57ba445f_318.png)

So。If you differentiate it one more time， the bracket is just A B minus B。 so again。

 if the bracket equals 0， this tells you A B and B are the same thing。



![](img/b6596711533b8ea1c8690bac57ba445f_320.png)

If it's not zero， it tells you A， B and BA are different things， and it precisely measures how badly。



![](img/b6596711533b8ea1c8690bac57ba445f_322.png)

They commute with one another。

![](img/b6596711533b8ea1c8690bac57ba445f_324.png)

So I guess just to keep track of everything。Could this start nega Lord Harry？

Is you have your Lee group G or your matrix group G and you have your Lee algebra。Then you're。哎。

Joint with big a。

![](img/b6596711533b8ea1c8690bac57ba445f_326.png)

And then your bracket。So when you do the bracket of something。

Both the some things live in your algebra when you do the a joint of something。

 only one thing lives in the algebra， and the other thing lives in the actual group。Okay。



![](img/b6596711533b8ea1c8690bac57ba445f_328.png)

So。Something that is very， very spooky is when you do this thing。

 you get back at the algebra element。 So a fun fact。a result of this is if A and B are skew。Then AB。

Minus B is also SU。Okay， so when you do these bracketing elements it stays inside whatever the algebra rule you had。

So it's kind of magical， but it will be useful later on。



![](img/b6596711533b8ea1c8690bac57ba445f_330.png)

So this bracket is actually very， very， very important to everything we do。

 and there are four things that make this bracket。

![](img/b6596711533b8ea1c8690bac57ba445f_332.png)

Well， a bracket。

![](img/b6596711533b8ea1c8690bac57ba445f_334.png)

Okay， and the first thing we notice is it's linear in both terms。

So if we take our a matrix and we add on and we multiply it out and we add on more terms you get the more terms can pop out so if you have the sum of two things it's just the sum of the two brackets。

 if you multiply it by some numbers the numbers can just pull out and the same thing holds true on the second coordinate as well。

So it's just truly a bilinear thing， it skew or anticommulative means that if you flip the order of A and B。

 right you think about you're flipping this thing， you're going to have a minus pop out。

 so if you do AB or BA， they're going to agree up to a minus sign and the last thing is this really。

 really weird thing called the Jacobbi identity。And the Jacob identity is just weird。

 but this is just one of the evils of the world you have to deal with you can kind of view this thing as a derivative as like a product rule if you squint really。

 really hard。对。You just kind of take it as the way it works。

And one of the nice things is this is called， what is it called？

The Ado Iosawwa theorem says if you're given any。Any bracket that follows these four rules。

 it is a matrix thing。Right given no matter how you define this thing， no matter what you do。

 no matter how abstract or arbitrary you make this， it always corresponds to some matrix thing。

 so like the algebras and matrices and this definition of the bracket really are synonymous。



![](img/b6596711533b8ea1c8690bac57ba445f_336.png)

![](img/b6596711533b8ea1c8690bac57ba445f_337.png)

So that's a nice thing to keep in mind。So what we can think about here is remember if we go back to little S03。

 so the algebra of the orthogonal matrices。We have these three things that we looked at earlier and we can compute their brackets so again I encourage you guys to do this right this is just going me this matrix times this matrix minus this matrix by this matrix and if you do this computation you get G3。

Likewise is， if you bracket two and three， you get one， and if you bracket it one and three。

 you get two。

![](img/b6596711533b8ea1c8690bac57ba445f_339.png)

So this is just a computation that I encourage everyone to do it takes five minutes you just kind of multiply some three by three matrices together。

 but it does kind of tell you that this bracket does give you something back that's the right kind of form that you're looking for。

And the other nice thing to think about， this is kind of a spooky thing。If you think so G1。

This was rotations。About the X axis， right？So if we call this thing， so if we call little G1。

Just this vector because right， this is just， you know。

 the coordinate in the x direction right and likewise， G2。Is rotations？About why。And call little G2。

嗯。The union vector in the y direction。What happens when you take the cross product？Of G1 and G2。

You guys don't have to try that hard。I guess the slides call it E。All right。

 this is going to give you what we call G3。Which is in the Z direction。

And what happens when you bracket it？G1 and G2。Well again， it's given by that slide right there。

 right this is just going to be G3。So one of the spooky things about this specifically with three by three rotation matrices is this matrix bracket。

 this anticomutator， whatever you want to call it over there。

 it's the exact same thing as the cross product， if you turn these matrices into these vectors using this usual rule。

 right？Sew matrices and the sp is the exact same thing as three dimensional vectors in the cross product。

And think about it when you do a cross product， what are you doing？Right， I mean。

 what's the rule that your freshman physics teacher told you about crossing G1 and G2？

You start at G1， you rotate the G2， and this tells you whatever G3 is， right？

Right so you're rotating G1 into G2 and that's telling you how you're moving right whereas it's the same thing as rotation group so really the idea that the cross product is you're sweeping one vector to the other to pop something out really represents the fact that we're talking about the rotation group and these rotation things。

And the cross products being the same thing is kind of the same。Think about it。



![](img/b6596711533b8ea1c8690bac57ba445f_341.png)

はい。So what we can think about is if we have our matrix group and suppose our matrix group is dimension D。

Remember earlier， we made a comment that the Lee algebra has the same dimension as the lead group。

 So the algebra is also going to have dimension D。The the algebra now is going to be some vector space。

 so the algebra is just going to be some copy of RD somehow。So we can think of is this。

 these things are some sort of vector spaces to find upon what's going on and our edge right now is just going to be some kind of a map between them so we can think of。

We have our matrices， but now we can think about matrices acting on matrices because we can think of these both as vector spaces and this is a matrix that acts on a vector space of matrices。

 so you kind of have a matrix that acts on matrices by matrices and your brain kind of melts from inception but。

I don't have anything better to say about that。So what we can think of though is we can make this some assignment that we take our matrix and we turn this into a matrix that acts on matrices so we can do some examples later on it's really weird the first time you see it I recommend trying to just read up on it takes probably two years for this to click。



![](img/b6596711533b8ea1c8690bac57ba445f_343.png)

嗯。So moving on。What we so moving on， what we can think about is right， if we have。

 if we're thinking about real numbers， if we expiate x。

 exponentialiate y and we get the exponential of Z， and these things are just numbers。

 What do we know about Z。It is x plus y， but of course this is the world of matrices and matrices are never that nice so when does that formula hold for matrices。

 if you have exponential of the matrix times exponential of another matrix。

 when is that the exponential of the sum。When X commute， okay？But。

Hope is not entirely lost when they don't commute and this is what's called the Baker Campbell Housedf series。

 so again， Google this on Wikipedia you' find a whole bunch of things about where this comes from and we can write down like a Taylor series expansion for what the Z has to be。

But if you think about it， you have x plus y， which is what we would hope they would be plus this other garbage。

 but if you think about it， if they commute， what do all the brackets have to be？

Zero right so if they commute this big long tail has to vanish and then z is just x plus y which is what you want them to be right so the of x and the exponential of y equals basically the exponential their sum plus this error terms which measures how much they don't commute with one another。

And the way you can prove this is you can just write out exponential of x and y into the big long Taylor series for the exponentials and you can just gather terms and you just spend about a month trying to do this algebra and you can get there。

 or you can be lazy and just Google it。

![](img/b6596711533b8ea1c8690bac57ba445f_345.png)

All right。

![](img/b6596711533b8ea1c8690bac57ba445f_347.png)

So the nice thing because remember I said earlier that if we have our matrix group。

 we can draw the tanent space to it and we can go from the circle to the line very easily。

 but what the Campbell Baker house Store formula tells us is we can actually go in the reverse direction right if we know。



![](img/b6596711533b8ea1c8690bac57ba445f_349.png)

![](img/b6596711533b8ea1c8690bac57ba445f_350.png)

What all of these brackets have to be we can solve this right these are going to be things in in our group right so this tells us if we have two things in our group and we multiply them together this formula tells us what the other thing in our group needs to be so since we know this formula right this formula only exists on the Lee algebra we can figure out exactly what's going on in the lead group side so like down here is the formulas of what's going on this line but the exponentials or what's going on up on this circle so so the Baker Campbell house or formula tells us if we know everything there is about the Lee algebra。

 the matrix group follows for free。

![](img/b6596711533b8ea1c8690bac57ba445f_352.png)

Which is what the lead correspondence theorem is says if you know。All these le algebras。

 all these collections of things with these brackets。

 there's a one to one correspond between those and matrix groups and you can pass between them so if you know one。

 you know the other one，And vice versa， so it really doesn't matter you can either deal with matrix groups or with Le algebras they really are synonymous。



![](img/b6596711533b8ea1c8690bac57ba445f_354.png)

All right， so we're nearing the end。

![](img/b6596711533b8ea1c8690bac57ba445f_356.png)

嗯。And this is going to become more useful actually for tomorrow or not tomorrow for Wednesday。

 So what I talked about earlier， right is a manifold is just。

Anything that if you zoom in enough it looks like Euclidean space so right the reason why people say the earth is flat is because if you zoom in enough on the earth Earth just looks like R2 right so all the flat earth is they're just very sophisticated way the saying the earth is a manifold iss all that that says okay so the same thing a donut is a manifold right because a tous。

 the donut right if you zoom in enough on it it looks like r2 right the circle if you zoom in enough on it it looks like a line right any reasonable shape that you can possibly concoct is gonna be a manifold。



![](img/b6596711533b8ea1c8690bac57ba445f_358.png)

There's one caveat I want to talk about though， is and all of the things we're dealing with。

 we care about taking derivatives because we're curious about velocities。

 so the circle is a manifold， but the square。

![](img/b6596711533b8ea1c8690bac57ba445f_360.png)

![](img/b6596711533b8ea1c8690bac57ba445f_361.png)

Is not going to be a manifold。 And why don't we want to call the square？Yeah。

 because at the corner the derivatives are going to be stupid right so we want to just rule out this behavior so when I say anything you can think of as a manifold。

 anything that's not sharp is going to be a manifold so the earth is a manifold。

 I mean not talking about mountaintops or whatnot right but anything reasonably curvy is going to be a manifold and any dimension you can think of and just the formality says if you just zoom in enough on it and you take a spawawn of swath you can turn it into saying thing of RN which is just what a mapmakerrs does with Earth right they take a part of earth they turn it into a plane and that's just plain earth as a manifold。



![](img/b6596711533b8ea1c8690bac57ba445f_363.png)

![](img/b6596711533b8ea1c8690bac57ba445f_364.png)

So what we see is any matrix group that we talked about is going to end up being a manifold Well any matrix group modlo these stupid corners I mean you don't want something silly like this to happen so as we saw SO3 is going to be a manifold S2 is going to be a manifold especiallyuclidean groups can be manifold so we give you these things as these like geometric objects on their own right and that's going to be a lot of a Wednesdaynes is going to deal with but we're going to touch on it a little bit now so。



![](img/b6596711533b8ea1c8690bac57ba445f_366.png)

![](img/b6596711533b8ea1c8690bac57ba445f_367.png)

![](img/b6596711533b8ea1c8690bac57ba445f_368.png)

We can。So a lead group， which I've been mistakenly saying this whole class is just the matrix groups。

 but now instead of assuming that they're matrices。

 we're just going to assume that they're a manifold。

So what we do is as a lead group is just any manifold it's also a group whereas a matrix group is any set of matrices its a group。

 so really they're basically the exact same idea， just calling it a lead group is more you're thinking about donuts and spheres in your heads。

 whereas when you say matrix groups you're thinking more you know ske orthogonal matrices and things along those lines。

As such， everything we've talked about with matrix groups carries over to league group is perfectly fine The other way is a little bit shakiier。

 but I mean really the exact same idea just league group is a more geometric way to think about things whereas a matrix group is a more I guess like an analytical you know matlay type of way to think about things。



![](img/b6596711533b8ea1c8690bac57ba445f_370.png)

So right the lead group is just a manifold， which just means some sort of a shape that doesn't have corners that also is a group。

嗯。And since matrix groups， right， we can view these inside of Rn squared as some giant thing we can also view them。

 of course， as lead groups。

![](img/b6596711533b8ea1c8690bac57ba445f_372.png)

So one of the nice things that we have is when we kind of we can view these things in different ways。

 because what is one of the biggest problems of when you do Eer angles with SO3？

Why do Oer angles suck。Come on， you guys， someone has to know why well their angles are terrible。

Gimal lock right right you get singularities out the wazoo things go terrible so one of the things that we can think about is if we view this instead of oiluler angles if we try to view this more intrinsically as a manifolder more just said that we can avoid singularities altogether in the same way that if you do a sphere。

in spherical cores the North Po and the South Po are going to give you singularities。

 but those are completely artificial， so when we kind of use these things more as the manifold structure。

 we can kind of ignore see past some of these singularities。

 which just makes life a little bit better。And here are just some examples but whatever。



![](img/b6596711533b8ea1c8690bac57ba445f_374.png)

All right。So let's see how much we can do in five minutes。Mani wrote these that he said yell at himm。

嗯。So one of the nice things that we have is if we have a vector and R3。

 so we're view this as a column vector， we can turn this into a skuw symmetric matrix。

 and as anyone know the normal rule to turn to going between three vectors and skuw matrices。

Has anyone seen this before？

![](img/b6596711533b8ea1c8690bac57ba445f_376.png)

This is a useful computational trick。

![](img/b6596711533b8ea1c8690bac57ba445f_378.png)

![](img/b6596711533b8ea1c8690bac57ba445f_379.png)

And if you have the three vector， let's call it A， B， and C。

We can turn this into a sw matrix and the way we're thinking about this， right。

 this is the x direction right when we had a sw matrix， what was rotation about x？

It was all zeros in the x places right， and then what was the matrix for the x rotation。

 it was minus1，10，0，0，0，0，0 and0 right this was the x rotation matrix right but we don't have one what we do is we fill in the A's。

Right。And likewise， what do you expect happens with the B's。

 So the B's are going to be the y component。 How do we fill in this matrix with the Y's。

So what was the Y SU matrix？So again， the y parts， the middle column and the middle row are going to vanish。

So what are going to go on here？Be a negative people， which ones which。Top one is B。

 then bottom one is minus B。And likewise， is whatever we're going to do with C。

I'm going to go for minus C and C。O。And then what we're going to do。

Is let's call if we call this thing X， this thing is going to be x， which way does he do it？

Is an x care at top。Or x。Carrot top。And likewise， if you want to go the other direction。

 if you call the s matrix Y this is going to be y。Oppossite。O。

So if you see thinking of this with a vector。When you put the kerattop over it。

 it means it's a s matrix， if you have a sw matrix and you see the dimple on it。

 it's going to correspond to a three vector。And a fun homework assignment that I'm going to give you guys。

Is。Is to show this。So if you take two skew matrices and you compute their bracket and then turn them into a vector。

 this is the same thing it's turning them both into vectors and then' taking the cross products。

This is a homework because I haven for you guys to fiddle with。So。

We'return back to class what we see here。Is right。 Phi is going to be a vector。

 So fee care at top is going to be given by a S matrix。 when we in it。

 when we expentiate the Sw matrix， we're going to get this thing。

 So does anyone know the name of this formula。You get a pat in the back if you know the name。

Rodriguezs formula， right to answer the Rodriguezs formula， of course。

 Google there all sorts of pretty pictures about how this comes about。

 So we got the Rodriguez formula。And likewise we can invert it right。

 so in the same sense that this takes a lead algebra element and gives this our lead group element being going in the opposite direction by taking the logarithm。

 and then this is the formula for the logarithm just by going in the opposite direction。那我看。

So these are wonderful formulas， but they should be Googled and they take a lot of time to talk about。

 but they are very interesting。

![](img/b6596711533b8ea1c8690bac57ba445f_381.png)

![](img/b6596711533b8ea1c8690bac57ba445f_382.png)

All right， so the last thing I want to talk about because we're about out of time。



![](img/b6596711533b8ea1c8690bac57ba445f_384.png)

Is that of the Jacobian？So。I want to write this thing down。

 and I want to talk about it and then you guys can go。So say。We have the exponential。

Let's say we have C。Carrot top。And the exponential of our carattop。Okay， so C and R are both vectors。

 but ski carroat top and R carat top are both some sort of a matrix。Okay， and again， is it true？



![](img/b6596711533b8ea1c8690bac57ba445f_386.png)

That this equals the exponential。Is this formula true？

Remember the answer is of course not because we talked about this like four slides back right when you do right if you exponentiate two matrices。

 this is the same as exponential sum of the matrices only when these things commute with each other so in general this thing is not true。

Okay， but what can we do， but what we do do？As I got to get my orders right。

 this is going to be the exponential。Of。Of our carrot。Plus。Something。Okay。

 and the thing is we can figure out what something is， that something is not going to be C。Right。

 the something is going to be well something。 so what we say is we say this something。Is。The left。

这靠边。Okay， so the thing is。Right。This is not true， but we add on this whatchajigi and right when we add on this error term。

 it is going to make it true， So this thing is called the Jacobian and what the Jacobian does is it makes this forces this formula to be true。

So what we have right is we can define that J。Of L。

Of R is this thing that's required to make sure that this formula holds right and we can also define by the right to code by switching orders of everything。

 and in these slides we have some of these garbage formulas for this。



![](img/b6596711533b8ea1c8690bac57ba445f_388.png)

So what we see here is right is if we use that formula with's exponential is this is what you're going to get in order to make the things line up and then this is what happened when you invert it。

 so this is just a Jacobian you can Google this again and we are out of time。



![](img/b6596711533b8ea1c8690bac57ba445f_390.png)

![](img/b6596711533b8ea1c8690bac57ba445f_391.png)

![](img/b6596711533b8ea1c8690bac57ba445f_392.png)

So with that， I'll see you on Wednesday and hopefully confuse you guys more。



![](img/b6596711533b8ea1c8690bac57ba445f_394.png)