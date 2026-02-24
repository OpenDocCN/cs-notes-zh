# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P23：1 - Spring 2023 Discussion 06 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明哈 me。🎼Ba。

![](img/84dd4592bb9e443af96b74cbac671f35_1.png)

🎼And。Hello everyone and welcome to CS6 UNB Spring 2023's Walkthrough of discussion number six。

 which is about asymptotics and destroyed sets。First up。

 some announcements that once again may or may not be relevant by the time that you watch this video weekly Sur 5 is due on Tuesday。

 February 21st Project 1C which encompasses Max arrayray deck iterators and equals is due on Wednesday the 22nd labb6 is due on Friday the 24th and labb six is really important because it's one of the few labs that we require attendance app this semester it's basically just going to be a code peer review where you get together with your fellow students and then staff is going to present a bit of the solutions for Ar De and Li list deck and you get to basically take in those solutions and look at your own code and look your partner's code and talk a little bit about things that went well on things that maybe didn't go so well but the point is attendances mandatory you must be there there are some caveats however if you can't make it or you're not done with the project yet those are detailed in one of the announcement posts on Ed。

Yeah， and then finally homework I percolation just got released， it's going to be due on Wednesday。

 March 1st， okay。😊，So jumping right into some content we have a bit of a heavy set of topics today so we'll go slow first up we have asymptotics so asymptotics basically allow us to evaluate the performance of programs using map and when we say performance we typically mean in terms of the amount of time that the program takes to run we also can talk about it in terms of like the memory use so we would call that space complexity but we don't typically talk about space use 601 B that's more reserved for us on upper digs like 170。

😊，Anyways yeah this quick tibit and when we are looking at asymptotics we ignore all constants and only care about the total work done in regards to the input as it grows very large and we usually define the input in terms of n so there's three big symbols that you really need to pay attention to an asymptotics the first one is big O we call this the upper bound in terms of the input in other words if a function has a big o in F of x。

 we say that it could grow at most as fast as F of x but it could grow more slowly so we can say that for example。

 if we have a linear function and a quadratic function。

 we know that the linear function has big o in the quadratic function because we know that a linear function could grow at most as fast as a quadratic function which is trivially true because we know a quadratic function grows faster than a linear function every time but we know that it could grow more slowly so in other words we would say something like linear is in big O of quadratic okay。

Or in plain English， we could say that the linear function is upper bounded by the quadratic function。

 okay？On the other hand。We have big omega， which is the lower bound in terms of the input。

 In other words， if a function has big omega in f of x。

 we say that it could grow at least as slowly as f of x， but it could grow more quickly。

 So here we're like setting like a bottom line we were like this function will not grow slower than this effectively is what a big omega is saying so going back to the example I just used with linear and quadratic we could say that the quadratic function has big omega in the linear function because we know that the quadratic function is going to be lower bounded by the linear function right we know that trivially a quadratic function always grow faster than a linear function no linear function will ever grow faster than sorry then a quadratic function in the long run as the input gets very large right？

Then finally we have like the combination of these of big O and big Oomega which is the symbol of big theta and we call this the tight bound and it only exists when the tightest upper bound and the tightest lower bound converge to the same value so in a little bit in the next couple of slides we'll talk a little bit more about what we mean by like tightest upper bound and tightest lower bound。

 but effectively if you have some function and it's upper bounded by f of x and it's also lower bounded by f of x then we can say that the tight bound for that function exists if the upper bound and the lower bound for f of x are the tightest possible bounds。

 aK they are like the most specific bounds that we can get。

I know that probably doesn't make a whole lot of sense right now。

 but we'll see an example in a couple of slides and hopefully it'll clear things up， okay？😡。

So some common orders of growth that we often see in our programming from day to day would be constant log N N N log n n squared and C to the N。

 and then alternatively you can think of it as constant growths slower than logarithmic。

 logarithmic grows slower than linear， linear grows slower than n log n and then N log n grows small slower than quadratic and then trivially quadratic grows slower than like n cubed and n to the who and stuff like that until you get to exponential。

 which is the fastest growing of them all not including things like n to the n or like n factorial necessarily。

So I think this is not necessarily like the most intuitive thing to pick up unless you've like。

Taken some like nasty calculus before like I remember like in high school and having to learn about Lapeal's rule。

 which is where like orders of growth mattered like this so I am'm going to pull up a doesmos example I just like typed in a little graph so you could see like the orders of growth and you'll see that constants do not matter in the long run so。

😊，In the sesmos graph I have the I have a bunch of orders of growth so this one this what oops。

 that's not way I want to the y equals zero here， this one is constant this one's logarithmic。

 then we have linear and then like what's basically n log n。

 then we have quadratic and then we have exponential so you'll see here that if we let the input which is x defined to be x here grow in the long run we'll see that the orders of growth kind of hash out into this way such that constant grows the slowest Aka doesn't grow at all right and then log X grows the next slowest。

And then then it's linear this green line here， right。

 so you'll notice that in like the first couple of。In the first couple。

Of x's like between like0 and 10， you'll see that x log x grows slower than linear function， right。

 which is why I think students tend to be a little confused about this sometimes because it's like wait a second like when x is5 or something like that like my X log x is literally a smaller number than my x。

 But the issue is that you have to consider asymptotics when n is very。

 very large right like when n is approaching like a million2 million like infinity like you can kind of think it like that like these small numbers。

 they don't count when we're doing asymptotic analysis of like a function Okay and then you'll notice here that if I were to put like。



![](img/84dd4592bb9e443af96b74cbac671f35_3.png)

Let'Let's call this like。Let's call this like 3 x or something like that， eventually。嗯。Oh。

 this is like quite annoying。Now I'm going to make it a small number I'm going to make it's like2 x or something。

Yeah， so if I make this like the linear line， like 2 x。

It does grow it does grow faster than X log X for like a while。

 but eventually we're going to get to this intersection point where X log x starts to grow faster than 2 x right So basically what I'm trying to demonstrate here is that no matter what you like do with your constants like let's say we have like linear and that we did like2 x plus 100 as opposed to x that doesn't that like really does not change anything as x gets very。

 very， very large right because eventually according to these order of growth rules like x log x will overtake x。

 which is why these constants don't matter in the long run and that's why we don't really look at them when we're doing asymptotic analysis okay。

So back to oops， Yeah， back to here。

![](img/84dd4592bb9e443af96b74cbac671f35_5.png)

We have my laser pointer back on yeah so basically the idea is constants do not matter in the long run。

 so you could have like n log n plus 1 million but in as n gets really really large that would still grow slower than n squared okay。

And then some fun sums that might be helpful to like write on your cheat sheet or just like keep on hand like as a reminder or like while you're doing the discussion worksheet is that if you see so what we're what we're showing here in the sums is like let's say there's like work for iteration and in the first iteration you do one unit of work and the second iteration you do two units of work in the third iteration you do three units of work and that's a pattern that's going follow up to n units of work if we add all this together because we want we want the total amount of work to sum to like the runtime right this is gonna to sum to n squared likewise what we have down square down down squared down here with one plus two plus four plus8 where we see that the terms double every time。

This is like a。Geometric sum that sends to n in the end。

 So here the these are like pretty common asymptotic patterns that you'll see and these come from we're not going to get too deep into the math here。

 but you can like look at it if you'd like maybe like in high school or in college you did some things with like geometric sums where it was like a summation like you know that big like sigma sign from like I equals one all the way up to n and then youre summbling over I or you're sum over like I squared to something like that it's the same idea where effectively if you sum over these numbers all the way up to n you're going to get。

You're going to get a runtime that's approximately n squared。

 And so like an example of this would be。Going back to the example I brought up where let's say you're doing the summation from one to n or I equal1 all the way up to n and you're just summing over I so it's effectively one plus two plus two plus four plus pi is to6 plus all the way up to n right and then I believe that like the formula breakdown for that that you like had to memorize is like that the overall sum of that is going to be like n times in parentheses n plus one all over two and then when you multiply that out that's going give you something like oh gotta so bad I it's going to give you something like one half n squared plus。

And over two， I think that's what it is。 Yeah， like and over two。 And then when you knock out。

The lower order terms like so basically here we know that n squared is going to dominate right so we don't care about that linear term and then we take out the one half because we again don't care about constant that amortizes to like n squared right so that's kind of what we mean and if what I've said just like made like zero sense like you don't even need to worry about it I promise just know that these are the sums that you'll need to really know or these are the common ones that we often see like in discussion with you on the example or like honestly in real life okay。

Cool so revisiting the question that we had before about like what exactly does it mean for us to have like a tight bound or like the tightest bound right so what we mean is that it refers to the most specific bound possible so as an example given F of n is built to2 n plus5 we could say that F of n is in big O of n to the n but that doesn't tell us very much it's like not giving us a whole lot of information because a lot of functions are bound upper bounded by n to the n because n to n grows really。

 really fast right like that's literally n times n times n n times n like n times and like you know you can imagine as n gets very very large like that's a function that grows very。

 very fast right。😊，So telling us that 2 n plus5 is upper bound by n to the n doesn't give us a whole lot of information about how fast it actually runs so a better tighter bound would be that f of n is theta bounded by n it's tight bounded by n because we see that this is a linear function over here right and when we knock out the constants we knock out the two we knock out the five because we know they don't matter in the long run we'll know that this linear function is both upper and lower bounded by n because n is just like like the basis linear asymptotic function right we know that it like could run as fast as or as slow as a linear function and therefore we can define the tight bound for this right we'll see more of this in the workshe this doesn't make a whole lot of sense right now。

And then sometimes we'll talk a little more about something like best versus worst case like in the discussion when she leave the exam and something important to note is that the best versus worst case is not necessarily based on the size of the input it's more about inputs that cause specific behavior we represent them with the tight bound theta because best and worst cases should always be consistent aka they always run in the same amount of time because they're limited to the scope of these very specific cases or very specific inputs that cause particular behavior right so how to identify like when you're like so。

Or let me preface this with like a sometimes when you come across a function。

 like the best in the worst case is going to be the same because it's just going to run in the same amount of time regardless of whatever the inputs are。

 but an easy way to identify whether or not a function might have a different best versus worst case is to look out for branching statements。

 loop conditions and breaks which we'll talk about in the example below。

And then Alex at T and our staff came up with this analogy in describing best and worst case versus upper lower bound analogy because best and worst case are not necessarily the same or。

You like you can't really think about best and worst case in the same way as lower and upper bound。

 even if like the functions like are upper and lower bounded by the same thing versus like the best and the worst cases are the same like runtime but the question like by an analogy let's say we have a question。

 how much does it cost to eat at a restaurant the best versus sorry the best and worst case like way of thinking is like the cheapest thing on the menu is $5 and the most expensive is $50 from a lower and upper bound perspective will say that we'll spend at least$5 and no more than 50 so lower and upper bound is almost kind of like a range right and best and worst case is like what are and the specific endpoints of that range okay？

So to illustrate I have a little example down here。

 so let's say there's this function example that takes an net integer N。😊。

And we have this y loop that runs while n is greater than zero。 And in this if statement， we have。

 we say if funk of n， then break。Otherwise we are going to decrement n sorry yeah we're going to decrement n by one every single time so we know that funk n is going return a booolean for us right and in the best case possible we break immediately out of this loop right regardless of what number n is we break immediately so the best case would take us constant time because we pass in some n and then we break out of the while loop and our function is done executing so that's like on the very first iteration of the while loop it's consistently going to stop executing that loop on the first try so we want n here to be some in for which funk n is immediately true that's what we mean about specific inputs right。

In the worst case， we're going to get linear time because let's say n is some integer for which funk n funk n minus1 funk n 2 all the way down to funk1 are all false。

 so basically we never trigger this statement so this loop is going to run to completion all the way down until n hits zero right at which point we' have done linear work well have gone through the loop n times all right。

😊，Cool。So shifting gears a little bit， let's talk a little bit about this joint sex I know that was like。

Quite some whiplash from the asymptotics that we were talking about。

 but asymptotics is like directly relevant to the implementations of disjoint sets that we're going to discuss below disjoint sets are also known as union fine and it supports two it's an interface that supports to operation the first one is connect which takes in an X and a Y and it connects nodes X and y you may also see this called get called union like union X and y or connects X and Y and then the other function is Boolean is connected and it returns true if the inputs X and y are connected aka if X and y are in the same set okay so。

😊，Oh I thought I updated this slide， but very quickly I just want to talk about that Quick find uses an array of ins to track each set which set each element belongs to Quick union stores the parent of each node rather than the set to which it belongs and merges sets by setting the parent of one root to the other so quick find and quickun we don't really like I know that Josh went over them in lecture but。

I think it was more of like an intuition building exercise as to why weighted quick union and weighted quick union with path compression are important like we don't really talk about quick fine and quick union in like the context of like a discussion or like。

Or like an exam problem because they are less efficient than weighted quick union and weighted quickun with path compression so I'm just going to gloss over these very quickly because really they should just be motivation for these two implementations over here。

😊，Because they build on each other so like quick union builds on quickfin and the way to Quick union builds on quick union as an the of path compression builds on regular to quick union。

 these are the two that we want to focus on here okay。

So weighted Quickun does the same thing as quickun except it decides which set is merged into which by size。

 so we want to merge the smaller set into the larger set。

 which helps us reduce stringiness and by stringiness we mean like we don't want our disjoint set to start looking like a linkless right where like it's just like a long chain of elements。

 we want it to be as like bushy as we can right so like reduce runtime of looking for things。

And then finally， weighted Quick union with PA compression builds upon regular weighted quick union。

 and it sets the parent of each node to the sets root whenever find is called on it。

And then find okay， so to quickly reiterate find is an operation that we'll see in the worksheet more。

 but it's basically a function that helps find the parents of two input nodes。Oh sorry。

 sorry to find the parent of one input node， sorry， yeah and we'll see that shortly。😡，So。

Oh I did leave this I did have this note down here but the point is for just asymptotics。

 the reason why we wanted to have weighted curriculum union and weighted curriculum union with pack compression is that。

😊，Quick union and quick find， although they're fine like they like run in linear time。

 it's not necessarily like the most ideal way that we can implement things right so way to quick union every everyone has like a constructor that's linear。

 but way to quick union improves upon the connect of quick find and quickun by making it a log end operation right at the very slowest it's going to run in log end time versus quick find and quick union it's going to run in linear time at the slowest right。

Yeah at the oh I always like to mix it up let's yes at the list on the other hand we do have a bit of an increase and is connected in weighted quick union versus quick finds constant time but we still like to stick to weighted quick union because the connect operations faster and then finally wayed quick union with path compression。

😊，You see this like weird notation over here and this is called the inverse ackerman function you like like you do not need to know like the nitty gritty of this at all。

 I think Josh briefly talked about it he may have gone over like the mathematical idea behind it。

 but the point is that with path compression because we're setting the parent。嗯。

Of like a node that's getting merged in directly to be the parent of the other set that is being merged into over time the more times we call find or the more times we call connect on our way to quick union with path compression the amount of time it's going to take for us to like do the connected that is connected and the find operations shrinks into this like inverse acumen function like you don't you don't need to know the nitty gritty of that but just know that like these are motivations for why we have way to quick union way to quick union path compression that builds upon regular weighted quick union and if this didn't make a whole lot of sense that's totally okay we'll get to it into the worksheet。

Al right。I think this might be the last slide， but very quick note about disjoint sets representation so we use a single array to represent our disjoint set when implementing connect optimally so for example。

 when we use weighted quickun and the array index I contains the parent of element I in the set the index of a root contains negative the number of elements in the set rooted at that index okay that's a huge amountful let's go over that in the context of this problem so basically what this means is that we can represent a disjoint set entirely in an array of length size where size is the number of elements in the disjoint set initially。

😊，So like when we like start out with our disjoint set every element is in its own disjoint set right but then after we call a bunch of connections and stuff we have to like be able to represent like the parents of each node in the disjoint set right and you'll notice here that we have each element each node in the disjoint set we have it represented by an integer and so like。

Noode zero is going to be represented in position  zero of the array。

 node3 is going to be represented in position3 of the array， node sevens in like position7 array。

 so on and so forth。 So what this looks like is let's go through these one by one。So。

Here in position zero， we'll see that this is negative9 and the reason that that this is negative9 is that when we look at node0。

 we'll see that node0 doesn't have a parent right that means that node zero itself is like the root of its own disjoint set。

 So then we want to count the number of elements in that set that are rooted at that index。

 So when we do this we're going to count up all of the elements that are。Ultimately rooted at zero。

 so we'll see that there's one，2，3，4，5，6，7， eight， they're all traversible up to0 as the root of this like one giant disjoint set after a bunch of like connect operations presumably right and we also can't forget that zero itself is in its own set so we'd say that there's nine elements in this set and we're going to mark the the number nine in position zero with a negative sign to note that it's the index of the root okay so zero is its own root。

Then when we move on to position one or index one， we'll see that index one's parent is zero index twos parent is also zero index3's parent is also zero index four is parent is also zero and then when we move on to this row down here well note that fives parent is one right index5 it says one here because it represents that five's parent is directly one notice that it doesn't say that fives parent is zero even though five technically speaking is in a disjoint set that is rooted at zero if five was pointing to zero then that's effectively weighted quick union with path compression right like anytime we call connect we set the。

The node that we want to connect into like the。The overall destroy sets that's being added to we set that new nodes parent to the root of the set that's being added to we're not doing that here。

 this is regular weighted quick union so we'll see that five's parent is one like why six six is parent is one sevenths parent is three and then eighths parent is four all right and I think yeah that's time for the worksheet。



![](img/84dd4592bb9e443af96b74cbac671f35_7.png)