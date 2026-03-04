# 密歇根大学《面向所有人的Web应用程序（PHP、SQL、APP、JavaScript和JQuey｜Web Applications for Everybody》 p31 30_PHP数组函数.zh_en -BV1Lr421A75d_p31-

![](img/6e3458fc1633d0be485b5c718d063fb7_0.png)

![](img/6e3458fc1633d0be485b5c718d063fb7_1.png)

So now we're going to talk about array functions。PHP started out as a non-object orient programming language so it tends to have a bunch of functions that are named in a way to group them together。

 So if we take a look at some of the array functions。

 we'll see that they sort of have array underscore and that's just a way in the global namespace。

 you'll see that string functions have string underscore。 And so that's a way to do it。

 And we do a lot of manipulation of arrays through functions where we pass the array in as a parameter and that's because these are not object orient。

 we'll talk about oh0 later， but these arrays are kind of from PhP。



![](img/6e3458fc1633d0be485b5c718d063fb7_3.png)

One， two， three， four。

![](img/6e3458fc1633d0be485b5c718d063fb7_5.png)

P P 5 is where object learning came in。 And so these are kind of antiques within PhP。

 So we have a lot of things， but。At the same time， there's a lot of really powerful things because like I said。

 programmers build data structures and then they like take this array and then merge it with this array or this array。

 check compute the differences between these things， etc cetera。

 find the position of this key inside of an array So there's a lot of things because that becomes the way that you express your program and allows your programs to be relatively small because you have these sort of these operations on array so here's a couple of it we'll talk about。



![](img/6e3458fc1633d0be485b5c718d063fb7_7.png)

You can ask if a key exists in array。This is kind of a cleaner way to do it。

 but the way everybody does it is this is set function， a sub key。

 and for those of you who know other programming languages。

 this like makes me quizzical how this actually works inside a PhP because if you say a race sub key and a key doesn't exist dollar array。

You know sub quote x and x is not there。 this becomes a non fatal error。

 So what we always ask is when to use one of those two things to see if the key is in there。

And we tend to use this one all the time because it's more succinct。

 but that doesn't cause a non fatalal error。 Neither of these cause a non fatal error。

 If you just access a nonexistent key， it does cause a non fatal error。 We already saw the count。

 which tells you how many things are in there。 One of the things that's really cool about PhP is that you can have variables that are what's called mixed type。

 They might be a string or they might be an array of strings。

 And you can write a function that will take an array of strings or a string。

 but you have to know if it's an array or not。 So this is a logical test， Is that an array or not。

Sorting awesome because arrays maintain the order that you put them in so there's a couple ways to sort which we'll talk about。

 and then you can even sort of randomly shuffle them， make an array of playing cards。

 and then just shuffle them， and it randomly shuffles them， gives you a different order。Okay。

 so let's ask a few questions。Just because of the fact that you can't。

Try to dereference an array dollar Z A sub X in this case， will'll blow up because x isn't there。

 right， And so I got name and course in there。 And so I have to somehow ask， does the key exist。

 Does the course key exist in the Z A array， true or false。And in a sane world， we would do that。

 but we do that way too often because we don't have like a gi operation the way we do in Python。

And actually this gets different in PhP7。 and so you're probably using PhP7 and there's a cleaner way to do this in PhP7。

 but the compatible way of doing this but PhP5 and earlier is to use the turnernary operator and so。

This is the one place that even the turner area operator is a little crazy。 Remember Turner operator。

 which is a question and the true part and the false part。 And so this basically is an expression。

 you could put parentheses around it right there。 This is going to ask is set which is going to return us a true or a false in this case is's going to return true because name is in the array and so it's going to print the two true parts。

 So it's going to say name is set So that prints that out。Now if we do it again。

This is going to ask is set Z a adder and that is going to be false and so it's going to pick the false side and so it's going to take and print out adderss not set。

 And so again， this is the turnernary operator question mark colon that basically is going to take the true or the false depending on the evaluation。

 So it turns out this we do all the time。 and I apologize you'll see this in my code for the rest of this class all the time。

 someday we will use PhP7。

![](img/6e3458fc1633d0be485b5c718d063fb7_9.png)

PHP7 has a more elegant way of doing this with what's called the null coalescing operator。



![](img/6e3458fc1633d0be485b5c718d063fb7_11.png)

It really is an operator that sort of also suppresses that non fatal error。

 And so the null coalescing operator is the double question mark。 This is a PP7。Onlyonely。

So you probably are installing PhP for the first time and so you'll have PhP7。

 so you don't have to use thisterranernary operator。

 you can achieve the same thing by saying username get is an array we'll talk about in a second。

 this but it is just an array， give me what's in the key user。Or nobody if it's empty。

 So it's really， it's really a， you know， this comes across or that comes across。

 And this is kind of like a default。I like this。I wish it was in there all along。Myy face。

 I like that， I wish I was in there all along。

![](img/6e3458fc1633d0be485b5c718d063fb7_13.png)

Okay。And so that's the null coalescing coalescing operator。

 so this is a lot lot prettier you know we can link this array with two things if it's greater than seven。

 we can say if it's there， put the not found in， if it's not there。

 put the not found in in this case， the name is going to go and in this case not found is going to go。

And then， you know， the equivalent is this is gonna be true or false。

 And then the true part happens and the false part happens。 This works in PhP7 as well。

 And so this is why you'll see my sample code， at least for the next couple years until we're at PhP8 or 9。

 I don't like to write code that can't go back to PP 5。 PP6 never happened。

 PP6 is the the release that didn't exist。 So there was 5。 and then 6。 and no one likes 6。

 And so they got rid of it and made it 7。 So the release right before 7 is PhP5。

 Someday will have 8 and 9。 And then everyone will be upgraded。 I'm really conservative。

 So I still use this， But you can use this， because you're starting a PhP 7。But when you go to work。

 you'll probably be in PhP5， Okay， So or they'll tell you got to stay compatible。

 So I want you to know both of them， but I know that the future is bright。

 and I don't have to use the ternary operator ever again， which will make me very happy。😊。

We've already talked about count just tells you how many things are in array。

 is array is it true or false？Yes， it is an array， very useful。

 mostly useful if you're building functions and taking mixed parameters and you'll see when you look at the PhP function specifications。

 they'll say that first parameter is mixed， which means it could be an array it could be a string。

 could be something。And it's really easy to write code that accepts strings or arrays of strings。

 which is quite nice。So let's talk about sorting。So the funny thing is is probably the worst sort that you have in all a PhP is the one named SART。

Because it doesn't sort key value arrays very well。 It does sort numeric arrays well。

 So it redoes the arrays based on the values， not the keys。 And but it throws away the keys。

 So this this resorted them。 So it sorted the things into the right order。

 But then it wiped these things out。If you're sorting a linear array， this is fine。

 but if you're sorting a key value array， it is not a very fine thing to do and so you can do what's called a K sort。

 which is respecting sort by the keys。Course name topic， or you can do a sort。

 which sorts by the values， but keeps the keys in place。Probably this is。

Well depends what you're trying to do。 But this probably is the a sort is probably the what you want to do。

 although when I'm printing stuff out， I tend to like doing a K sort so that I can see the keys。

 So if I'm looking， sometimes there's like， you know，40 things in here。

 So you want to find the thing。 So I tend to sort by keys just because I like， oh is， is。

 is is age in there or whatever it's looking for。 And so K sort an a sort。

 I don't know why this is a sort。 I would call this v sort， because it's like keys and values。

 Why didn't they call it v sort。 I don't know。Don't need to change that。

 I can complain about a lot of stuff， but I't complain about that。 A sort is awesome。 Oh。

 that might be it。 A stands for awesome。 It's the awesome sort。😊。

There's the sort that messes up the keys and then awesome sort that doesn't mess up the keys and then K sort that sorts by keys。

 Maybe that's what's going on here。 Who knows。Someone can like tell me in the comments that that's what's going on。

So another thing that we do in many programming language is string processing and so there is this capability in PhP called Explo what it takes as its first parameter is the split。

 the character to split on the string to do the splitting and then you get back an array so just goes chop。

 chop， chop， chop， chop chop， and so then I get back in temp。

 I get an array that is each word of that in an array， so you can say oh this is the0，1，2，3，4，5。

 so the fifth word sub5 is7， very nice， you can make this be a comma you can make it be a colon。

 semico， whatever it is that you're trying to split on and so that's a great way to parse data。



![](img/6e3458fc1633d0be485b5c718d063fb7_15.png)

So up next， we're going to connect how arrays work with the request response cycle。



![](img/6e3458fc1633d0be485b5c718d063fb7_17.png)