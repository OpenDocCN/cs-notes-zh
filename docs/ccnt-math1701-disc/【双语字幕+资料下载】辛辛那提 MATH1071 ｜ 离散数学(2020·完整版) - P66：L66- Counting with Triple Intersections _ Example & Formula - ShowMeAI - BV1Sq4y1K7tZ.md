# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P66：L66- Counting with Triple Intersections _ Example & Formula - ShowMeAI - BV1Sq4y1K7tZ

I was trying to figure out over the three different math courses that I'm teaching this summer。

 how many students am I actually teaching。 It turns out that the answer to this problem uses a classic counting argument from discrete math。

 So in this video， I'm going show you the triple intersection method for counting something where there's a lot of overlaps。

 My first approach to solving this problem of counting number of students was to look at the three different classes I have。

 And to say， well， how many students do I have in each class。 And indeed。

 I have 250 students in calculus of 150 students in linear algebra and 120 students in discrete math。

😊，So what I was trying to think how many students do I have。

 My first thought was maybe just add all of them up and get that the 250 plus the 150 plus the 120 was 520 students。

 Does that seem reasonable to you。 Well， the problem turns out to be that I have students who are taking more than one course。

 there's an overlap between these。 So for students who's taking multiple different courses when I just add the numbers up。

 that students getting double or even triple counted。 So this method actually isn't gonna work。

 So what I did next was investigate， well how many students were in both of say calculus and linear algebra。

 And I went down the line this way， and I got a bunch of different numbers。

 It turned out that I had 20 students who are in calculus and linear algebra。

15 students who are in calculus and discrete math，8 students who are in linear algebra and discrete math。

 and one rather enterprising student who was in all three at the same time。

 that students definitely gonna have a lot of fun with me this summer。

 So I actually have seven numbers here。 The three numbers for the total。😊。

The three numbers for what I'll call the double intersection。

 So that's students who are in two of my classes。 And then I have this one final piece of data for the student who is in all three classes at the same time。

 There's a great pictorial way to visualize this with Venn diagrams。 Here's the idea。

 These circles represent the calculus students， the linear algebra students and the discrete math students。

 But they overlap。 and the overlaps between them indicate students who are in both of the two courses or all three of them at once。

 And so what I'm going to try to do is basically fill in the socalled Venn diagram with appropriate numbers。

 And I'm actually going to work from the smallest numbers out。

 The smallest one is the triple intersection， The student who's in linear algebra who's in discrete math and who is in calculus who's in all three of them。

 So that student belongs。 well， right in the very middle。

 that is where the overlap between the calculus， the linear algebra and the discrete math is。

 And so I'm going to put that one student right there and fill it in with one。😊。

Next thing I want to look at is this next region so this denotes the students who are in calculus and linear algebra who are in both but who are not in discrete math I left the triple intersection Okay so what number should I put in here Well I know there's 20 students in calculus and linear algebra in general however。

 of those 20 students one of them is already accounted for one of them is in all three so that actually means there's only 19 students who are remaining the 19 students who are in calculus and linear algebra but not in discrete math。

Okay， wonderful。 let's maybe move on to the next of these double intersections。

 So these are students who are in calculus and discrete math， but not linear algebra。

 for all of calculus and discrete。 theres going to be 15 students。

 One of them is already in the triple intersection。 so I to subtract that out。

 And that gives me just 14。 I actually going to encourage you at this point to pause the video and see whether you can just fill in all the different locations on this diagram yourself。

😊，If you've managed to go and do that， then great。 And if you're just here to watch the show。

 then well， the other double intersection。 This is the eight people-1 is just gonna be 7。

 And then I've got the three outsides。 like for example， the portion that are in calculus。

 but not a linear algebra or in discrete math。 I have 250 to start with。

 But then I have to subtract off the 19 plus the1 plus the 14。 So I'm taking the 250。

 I'm going be subtracting the 34。 I'm gonna get 216。 So this is my result to 16。 So again。

 these are students in calculus， but none of the other courses。

 same sort of story for the linear algebra， there's 150 to begin with。 there's 19 plus 1 plus 7。

 which is 27 already used up。 and that leaves 123 remaining。

 and then the final one is how many discrete students are there。

 Well there's 120 discrete students total。 there's 22 of those are in some other courses and that leaves me with just 98 students to fill here。

 So what I've done here is I filled out all the possible places in this Venn diagram。

 And now I can get an answer。 If I want to figure out， well， what is the total number of students。

 I just add。😊，All these numbers add up the one， the 7， the 14， the 19， the 98。

 the 123 and the 216 and I added that up and got 478。

 So that's how many individual students I am teaching this semester。

 So that's one way to answer these kind of triple intersection arguments you write down the V diagram you try to figure out like what numbers go in each possible region in the Venn diagram。

 I also want to show you a bit more of a formulaistic way to do it。

 We're gonna to come up with a generic formula for the triple intersection moving over to my chalk board Imagine to begin now by just considering two different sets。

 I'm to imagine these two different sets S1 and S2 are overlapping。

 which means that there's some intersection in the middle Now the terminology that I use here is I use the union symbol S1 union S2 to denote both of these sets together。

 Basically if an element is in one or the other。 That's what the union side means。😊。

And then the intersection sign that looks like an upside down U。

 it means for elements that are in S1 and S2， so unun sort of associated with or's and intersections associated with ans。

So then my formula for the number of elements in， well， the entire union。

 the S1 union S2 is this formula here。 Okay， so what's going on with this formula。 So first of all。

 by n， I just mean the number of elements in a particular set。

 So the number in S1 union S2 it just read in English as the number of elements in either S1 or S2。

 And then what the formula says this is equal to is， well it begins by taking the number in S1。

 It adds to that the number in S2。 and then it subtracts the ones that are in the intersection。

 the ones that are in both it subs the number in S1 intersect S2 Now I need to be careful about why this is the case。

The idea is， if I just had the first two terms， the number and S1 and the number and S2。

 then elements in the middle would be double counted。

 They would have been counted when you added the S1。 They would have been counted when they added S2。

 So you have too many in your count because of this double counting。

 So all of the ones that are in the intersection。 All the ones that are double counted can be represented by the number in that intersection in S1 intersect S2。

 And as a result of that if I subtract off this double counting。

 it now means that every element is counted exactly once。 So you take the number in the S1。

 you added to the S2， which means it have some double counting。

 but you subtract all of that double counting the N of S1 intersect S2。

 and that just leaves every element being counted once。 So this is my formula。

Okay so that was the double intersection problem what about the triple intersection problem so I've got an S1 and S2 and an S3。

 and then I'm going to be interested in how many are in all three of these。

 the union of the S1 S2 and S3。When I look at this， there' are some double intersections。

 for example， the blue S1 and the red S2， they intersect and everything in the intersection can be written as the intersection of S1 and S2。

 Likewise， for S1 and S3 and4 S2 and S3， There's a lot of different double intersections。

 And then right in the middle is that triple intersection。

 These are things that are in all three of them， the S1 and the S 2 and the S3。😊，Okay。

 so what should I a formula B， I'm going to again begin with the number in the Union， S1， Union S2。

 Union S3。😡，The first thing I'm going to do， I'm just going to add three different big steps。

 the number and S1， the number and S2， and the number in S3。Yeah we run into the same issue。

 which is that we haven't dealt with the fact that some of these elements are double counted and in fact ones in the triple intersection are being triple counted。

 they are part of the S1 and the S2 and the S3 so they get added up three times。

So following the previous formula， why don't I get rid of all of those double counting。

 all of those ways in which you could have an intersection between them。

 I'm going subtract three things， I'm going to subtract the intersection of S1 and S2。

 I'm going subtract the intersection of S1 and S3， and I'm going to subtract the intersection of S2 and S3。

😡，So this has gotten rid of any of the double counting where one element was in two different sets at once。

 and so the just adding up those sets would have double counted that。But now there's a problem。

 Imagine you're in the triple intersection。 You get counted in the S1。

 counted in the S2 counted in S 3， So you've been triple counted。

But then for those elements in the triple intersection。

 I then subtract off the one double where its in it， I subtract off the other double wear' in it。

 and I subtract off the third double where it' in it。😡。

So things in the intersection got counted three times and then eliminated three times。

 things in the intersection are not counted at all。

 I have to add back in n of S1 intersect S2 intersect S3。And so that is my formula。 Now。

 I don't encourage you to just memorize this formula。

 The way I just think of it in my mind is that you add up the three sets。

 That's the n of the S1 and the S2 and the S3。 And then I have to subtract off all the double countings。

 But then when I do that， I'm missing the triple intersection。 So I have to add that back in。

 So I keep that process in my mind and can reproduce this formula if need be。Okay。

 so now let's see how that works for the specific example that we had with the calculu students the linear algebra students and the discrete math students so in the Normanclature of the formula the S1 might be the calculus students。

 the S2， the linear algebra and the S3， the discrete math students Okay so writing out the first line。

 the number who in any of my courses of the S1 or the S2 or the S3 then I write down with my union symbol well I'm going write out the big numbers first。

 the 250 the 150 and the 120。😊，Then I have to subtract off those three double intersections。

 So that's the students are in calculus and linear algebra。

 calculus and discrete math or linear algebra and discrete math。 So in other words。

 a -20 and-15 and a -8。 Then I have to take that one enterprising student who is in all three of my courses。

 and I'm just gonna add them back in。 That's adding the triple intersection back in at all these different numbers up。

 I get 478， this is the exact same number that we computed out。 when we just saw the Venn diagram。

 we're filling in numbers in the Venn diagram。 as a challenge。

 I would encourage you to try to now do a quadruple intersection。 And indeed。

 this general counting argument generalizes very nicely lit。 All right。

 so this video was part of my discrete math playlist。

 feel free to check out the rest of the playlist right here。 If you have any questions。

 leave them down the comments， give the video and like for the YouTube algorithm。

 and we'll do some more math for the next video。😊。