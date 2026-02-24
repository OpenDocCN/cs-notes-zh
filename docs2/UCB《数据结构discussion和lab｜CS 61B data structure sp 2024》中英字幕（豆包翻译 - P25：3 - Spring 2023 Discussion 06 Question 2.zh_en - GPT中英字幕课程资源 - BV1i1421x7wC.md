# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P25：3 - Spring 2023 Discussion 06 Question 2.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼哈比哈比。🎼Oh你。

![](img/d67b3a65bf717c4fa80c5a3df2b68546_1.png)

All right， so moving on to question two， which is the disjoint sets problem of discussion six。

 we're told to draw the Union fine tree an underlying array of these nodes in our disjoint set。

After we use， we run the operations on the left using a weighted quick union implementation of a disjoint set。

So the problem statement I'm just going to read it to you from the worksheet it's not on the slide for space purposes。

 but assume we have nine items represented by integers 0 through8 what we have here all items are initially unconnected to each other so that is to say they're in each of their own disparate disjoint sets we want to draw the union fine tree and it array representation after the series of connect and find operations and write down the result of the find operations using weighted quick unions without path compression we want to break ties by choosing the smaller integer should be the root so as a reminder in weighted quick union technically speaking when we are connecting two nodes in two separate disjoint sets we should break ties by merging the。

😊，The disjoint set with these fewer number of elements into the one with a larger number of elements。

 but sometimes even when we do that we can't totally break ties so when we actually need to break ties when to a call to connect is trying to merge to sets of the same size we'll default to have the smaller integer one be the root and we'll see this in action in a little bit okay。

And a very quick note about this array representation here。

 in case you missed it during content review， but basically you'll notice that every number in this array of length nine。

 right because each number is represented in the array at that particular index。

It starts at negative one。So， as a quick refresher。Like node5 corresponds to index 5 of this array。

 node two corresponds to index2 of this array， and every the element。

 the number in that particular index of the array tells us one of two things。

 either it's going to tell us the parent of that that node in our disjoint set representation or it's going to tell us if it's a negative number is going to tell us how how many elements are in the set rooted at that node。

So when we start off everything is in its own disjoint set right and so every node is the parent of itself so as an example let's say node two we'd come over here and see that there's a negative one here and this is telling us that node two is rooted at itself in its own disjoint set there's one element in that set and we negate it here to represent that two is rooted as at itself okay two is its own parent all right so now I we've established that let's get started。

So first when we call connect2 comma 3， we will notice that two and three initially are in their own disjoint sets right so they're both in sets of size1 and because this is wayed quick union we should break ties using size but here we can't really break ties because they're both in disjoint sets of size1 so here in the problem statement we were told to choose the smaller integer to be the root so here when we connect two and3 for the first time we're going to set two to be the root of3 and let's see how the underlying array array changed we'll notice that these two numbers are no longer negative one so。

Index 3 has changed so that its value is2 and this is saying that three's parent is2 okay and then in two index 2's position we'll see that this became negative2 because two is still rooted at itself right2's parent is itself and this negative sign tells us there that not only is two rooted as itself but two the this joint set rooted at two has two elements in it oh my god what mouseful okay？

Then when we call connects one comma2 we're basically trying to merge this disparate one element disjoint set containing only one to the set with two and three well in way to quick union we break ties according to the size of the set that we're trying to merge into right so that means that one after we call connect is going to now have its parent be set to two so it's going to look like that。

And we'll notice that in position one of our underlying array instead of negative one it's now two because one has a parent that's two and then in index 2。

 we see that two is still rooted at two but we are going to make this number over here three because there are now three elements in the disjoint set rooted at two All right。

 so following along with the same logic when we call connect five comma 7 we are once again going to break ties with five being such the parent of seven because five is a smaller integer than7。

And then you'll notice that seven index7 of the array now contains five because fives7's parent is five and then index5 itself contains negative two to note that five is its own parent and there are two elements in that。

Djoint set rooted at five， okay？Likewise， when we connect8 and4。

 we're going to break ties one more time where in index8 we'll see that it's4 and then in index 4。

 we'll see that this updates to negative2 because4 itself is the parent of four and there are now two elements in the disjoint set containing or there are two elements in the disjoint set rooted at four。

And now things get a little more interesting when we call connect seven and two。Okay。

 so we're asking to connect node7 and node two， but what this is really doing when we do weighted quickun is we're trying to connect the roots of both of these sets so what happens when we run connect is we are going to look at seven and find the parent of seven and that parent and the grandparent of seven until we can't find any more parents aka we found a root of that disjoint set containing seven and then we're going to connect that root to whatever the root of the other node is so in the other case to happens to itself be a root node so we don't need to worry about that。

But basically when we make this comparison here， we're going to see that oh。

 seven is in a disjoint set of size2 and two is in a disjoint set of size3 so when I call connect between7 and two this instead of rooting seven directly to two。

 that would be path compression right we're just doing the regular old way to click union here instead of rooting seven to two。

 we are actually going to root this five over to the two。

So what that looks like is there is now a five's parent is now two， so if we go over to the array。

At index 5 we'll see that there's a value of2 and two has updated the index 2 has updated to say negative 5 aka2 is itself rooted at2 and there are five elements in this disjoint set rooted at2 okay something important to note is that index 7 still contains five right it's not containing two because once again that would be path compression right that's as if we would set sevens parent directly to two but that's not true we're setting we didn't change what sevens parent was it's still five it's just that sevens parent5 itself is now rooted at2 okay so following along when we call find3 remember that find basically tries to find the root the root node of the set that the past in node is in so here we're saying we're going to pass in three what is the root node of the disjoint set three is in so we're basically doing to traverse as far as far up as we can。

So we're going to start at three， and we're going traverse up to threes parent。

 and we're going to try to traverse up to two's parent， but we're going to find out， oh。

 actually choose's parent is itself so find out that find three is going to return two。Okay。😊。

Then when we connect zero and six， oh， I realized zero was cut off by my Zoom video in this little corner。

 but that's okay， when we connect zero and6， we're going to do the same thing that we did before when we were connecting two disparate single element justjoint sets we're just going break ties。

 we're going to set six as parent to be zero and update that change in the array accordingly。😊。

Then when we connect six and four once again， we are when we're connecting six and four。

 we're really connecting the roots of the disjoint sets that six and four are in respectively so when we look at six is root that's zero and then four is root is just four and then since they're the same size we're going to make a comparison of the。

The values of the roots。 and we know that zero is less than 4。

 So we know that this4 and 8 destroyt set is going to get tacked onto this zero disjoint set where。

Fors parent is now zero。And once again， that's going to update in the underlying array accordingly。

 so zero now is an a disjoint set rooted at zero containing four elements。

 for's parent is zero8s parent doesn't change it's still four because we're not doing path compression。

Then when we tried to do connect six comma  three。We're once again， trying to connect the。

Root of the。Just joint set that6 is rooted at Aka 0 to whatever3 is rooted at， which is two。

 So once again， we're going to make this。Comparison with size and we'll see that this disjoint set with rooted at two has five elements and the disjoint set rooted at zero has four elements。

 so that's how we're going to break ties and we're going to put zeros parent to be equal to two。

We update update that in the array accordingly， so now we have this underlying array where at index 0。

 the parent is2 ones parent is also to。Two itself is rooted at2 with a disjoint set of size 9， right。

 there's nine elements in the disjoint set rooted at2， threes parent is2， fours parent is 0。

 five's parent is2，6's parent is 0， seven's parent is 5， eighths parent is 4。

And now when we call find eight， we are looking for the roots of the。

Of the node that got passed in right so we're looking for the root of the disjoint set that eight is part of so how we're going do that is we're going traverse starting from8 so we're going to go from8 up to four just four have parents yes it does we're going to go up to four is parent zero does zero have parents yes it does we're going go up here to two just two have parents no two is its own parent and therefore when we call find on8 that's going to give us two。

Likewise， when we call find six。We're going to start at six to six have parents， yes it does。

 we're going to come up to zero to zero have parents， yes it does。

 we're going to come up to two and see that two doesn't have parents， it's just itself。

It's like its parent is itself basically and then so that's going to return to as well and that's the end of 2A。

So2 B， on the other hand。Asks us to draw the worst case structure and run time for find this function。

 And we want to assume that this is not an implementation that uses weighted quick union。

 So weighted quickun， remember that it breaks ties when it's trying to connect two elements。嗯。

When it's turned to connect two nodes in a disjoint set。It breaks ties by determining whichever。

One has a larger size。 We should merge the smaller disjoint set into that larger one right and that's what helps us get this nice runtime for is connected sorry for connect the connect operation specifically right So in an implementation that doesn't use weighted quick union if we want to look at what fine does。

Fine basically tries to get the parent of a value repeatedly right and it stops if we find that the value is the parent itself。

Otherwise， we recursively chain this call to find where we keep going up the disjoint set through parent through parent through parent like all the way until we hit the root of the disjoint set right so that means that if we don't use weighted quick union and we are just。

Like randomly smashing disjoint sets together without regard to size。

 we could feasibly get an implementation that looks like a link list right that means that our set looks like when we call find on our disjoint set that looks like things might be linear or close to linear right like you can imagine that if we ran weighted quick union and let's say we tried to connect three to five trivially without wayed quick union or with wayed quick union if we initially had three and five connect we would not be able to really break ties anyway because like they're the same they're the same size right but let's say we have five and three and then we want to connect three and seven。

If we had weighted quick union we'd see that oh7 is in a disjoint set of size 1 versus5 and3 or disjoint set of size2。

 I better connect7 to the root of this53 set right so basically we would have like a pointer going from five down to seven because seven's new parent5 but because we're not using weighted quickun there isn't a guarantee that we'll connect seven up with the five right we could feasibly change chain7 to be the child of three and you can imagine that in the worst case scenario。

 every time we run regular old quickun or regular old like implementation of disjoint sets that doesn't use like the weighting aka the size comparison。

 we might get something that's linear so when we look for fine let's say we call fines on one we'd have to go through every single element that was previously added to that disjoint set in order to find the root which is basically like a linklet right that's linear。

Cool， so that's a bit of the intuition behind 2b。Finally， in2 C we're told that okay sorry。

 this is an insides for the purposes of space， but using a function set parent which takes in an integer value and an integer new parent which updates the value of Val's parent to new parent modify find to achieve a faster runtime using path compression you may add at most one line to the provided implementation so remember path compression on top of weighted quickun is basically this idea that when we call finder when we call connect with path compression。

😊，Remember how in part A， when we were connecting two disjoint sets with regular old weighted quick union。

 we did not update， let's say we called like。Let me come back here， actually。

When we called connect7 and two notice that we connected the parent of or the root of the disjoint set that seven was in to the root of the disjoint set that two was in right which is why there's a pointer from five to2 and not from7 to2 if we had a pointer directly from7 to two that directly connected nodes7 and2 that would be an example of something called path compression which is the idea that any time you connect two nodes like those nodes will have like a direct parent child link between them in the disjoint sets representation so that means when we come back to two C in the context with set parent with path compression the idea is we can improve find by every time we get here down to this case where we actually find the root of the disjoint set that we're in we can just set the parent of the value that we were looking for the root of the disjoint set of the value that we were looking for directly to the root right？

So that is going to look like after we run Find many times is let's say we had this implementation over here with the5371 that's a bit annoying。

 but let's say what we called we ran find on three with our path compression no find let's say let's yeah。

 let's say we ran find on seven with our new path compression with set parent then。

After we find that five is the root of seven， we're going to set five directly to be the parent of seven Likewise we're going to come down here to the one and when we try to find the parent of five sorry the parent of one。

 we're going to go all the way up to the root and find that the root of the set that one is in is five and then we're going to make a direct connection from one to five where five is the parent of one。

😡，So subsequent calls to find would be completed in amortized o of log star end time and that's just inverse Ackerman you don't need to like know that in great detail I think Josh talks about it in lecture but the point is that path compression helps us build on top of existing functionality in weighted quick unit with a very small change so that it runs even faster when we call find and make calls like connect and is connected all right I believe that is it for this discussion。

😊。

![](img/d67b3a65bf717c4fa80c5a3df2b68546_3.png)