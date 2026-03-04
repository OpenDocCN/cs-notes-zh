# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P12：12_03_04_二维数组.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/34709378fb5d8773f6d664dad7b155eb_0.png)

Now we're going to take a look at the next level up of structuring data where we have two dimensional arrays or arrays of arrays。

Two dimensional array is a doubly index sequence of values of the same type。

 and these are familiar if you've done math calculations with matrices， or if we have a table。

 say we have students in grades， then we have a two dimensional array。

 two indices to access an element which would be a grade。Scientific experiments。

 there might be an index by time and an index by an experiment。Transactions for bank customers。

 there's the customer and then which transaction it is。

 we'll look at this one later on pixels in the digital image。

 this image has got x coordinate and a Y coordinate。

 which are just indices and then each value of the coordinates specifies a pixel and the thing there is color。

Or geographic data there many， many applications and again， just as with one dimensional arrays。

 we want to facilitate storage and manipulation of this data and with two indices we have more flexibility for data that calls for it。

So Java also has language support for two dimensional arrays， again。

 basic support that extends the one dimensional array support in a natural way。

So to declare a two dimensional array， we put a sequence of two open en closed braces that says A is going to be a two dimensional array of values of type double。

To create one of a given size， we put numbers in there and we use the new construct。

 so if A's been declared， this says create a new two dimensional array， 1000 by thousand0 array。

 and then to refer an array entry by index we just put any after the name of the two dimensional array。

 we put a row name inside brackets and a column name inside brackets。Refer to the number of rows。

 that's a dot length and the number of columns is A of I dot length。

 and that can be different for each row。 that's a little more advanced than we need to get right now。

 but we put it here for completeness。To refer to row I， that's A of I。

 and there's no good way to refer to column J and that's just the way that the arrays are implemented。

In Java there ares of arrays and once you understand that then you can see these。

 so this is a three by 10 array array with three rows and 10 columns and we think of it as laid out in this row major order where we put all the elements in each row one after the other and then the columns are vertical。

Okay， and then maybe we think of that first thing as being the name A， again。

 it's the real world is slightly more complicated than that。Okay， what about initializing？Again。

 if we write code like a equals new double101000， that's a million different elements and they're all initialized to 0。

0 if they're initialized to  zero if they're booles。

 they're initialized to false and we can declare create initialize in a single statement in a similar way and we can also do literal values。

 so it's an array of array so we put。Curly brackets。

 and then we just put the rows within curly brackets separated by cons。Again， to initialize to zero。

 you don't have to have nested loops like you might expect in which you do need in many other languages。

 but you have to really be sure you take into account that the cost of creating an array is proportional to its size。

Okay， so one application is vector and matrix calculations。

 and these are very familiar to most of you and we won't dwell on it for now。

 but it's certainly a natural application of arrays。

 So if we have two arrays A and B that are both of length n then we can create a new array of C of that same length。

 and then add those to vectors A and B to get the result for C。And so it's just a term by term add。

 or if you have a matrix， then you use a two dimensional array and then you have to for every eye for every J do the term by term add so each entry gets added to create the corresponding entry on the right。

 so that's just a very simple veteran matrix calculation。With vectors and matrices。

 we have more complicated computation like for vectors， the dot product， one dimensional array。

 you multiply the corresponding entries and add them all up。

 So this is just a little trace for these two vectors 1 dimensional vectors first entry0。

 both of them is x of y 0。3 y of i 0。5， you multiply them together， you get 0。15。

 and then do that for one， you get 006 and you add it to the sum and then the third one you add it。

 And so the dot product of those two vectors is 0。25 and you get that for vectors with a single four loop。

With matrices， the corresponding things maybe be matrix multiplication。

If you're familiar with matrix multiplication， you immediately see how this code works。

 And if you're not， you can look in the book for more details， it's the dot product。

 I and J is the dot product of row I and column J in the result。

 So those two give that same result from over there， and that fills in one entry of the matrix。

 this case it's a triple4 loop for every entry in the output you have to do a dot product of two vectors in the row in the column in the input matrices。

So that's an example of two dimensional arrays used to implement a familiar matrix computation。

Just a quick question， how many multipl multiplications do you need to multiply to N by N matrices？

And youll look at this code just for a second and you see， well， it's a triple loop。

 each one executed n time， so the answer is n times n times n。

That's N cubed to multiply two and by n matrices。Okay， so let's look at another simulation example。

 so here we imagine a dog wander that's lost and wandering around in a city that's all square city blocks in being a dog it knows it's a waste of time to revisit any intersection and it can know when it's going to a place that it's been before and won't go there。

 so the question is does the dog ever get out of the city or not。

So what we're going to do is have a random process in an end by N lattice we're going to start in the middle and we're going to move to a random neighboring intersection and but never revisiting anywhere and there two possible things that could happen is one you get out of the city but the other is you get stuck in a dead end and let's look at an example so we start in the middle and in this case move west move west again and then north and then east and then north and so forth randomly choosing a direction now at that point it couldn't go back that way because it's already couldn't go back west because it's already been there now it goes south and then it goes east。

And in this case， looks good， but now it's not going to go west again because it's already been there。

 So there's only one of possible two possible things it could do。 it goes up north。

 So that means it escapes。On the other hand， with this one。After going for a while。

 the dog has the chance to escape if it goes south， but in this case， it chooses to go north。

 and that means a dead end。 That dog stuck all the neighboring intersections he's already been to。

So the question is， what are the chances of hitting a dead end。And again， with arrays。

 we can address this question with simulation we're going to use Monte Carlo simulation。

 we're going to now in the cucon collector we had a one dimensional array in this we're going to have a two dimensional array of the places that we've been。

And with all the code that we've seen in this setup you can this code almost writes itself。

 you can quickly see what we're going to want to do。

 This is a bunch of random walks and you can see in this case。There's eight by 48 of them and  one，2。

3，4，5，6，7，8 of them are dead ends and the rest of them， the dog escapes。

So we want to do a lot of random walks and we want to calculate the proportion for which the dog gets stuck。

So again， this is the same setup this is a third time now that we've used this setup。

We're going to take our problem size from the command line。

 we're going to take the number of trials that we want to do from the command line。

 we're going to initiate count of the variable that we care about。

 which is the number time it reaches dead ends， and then we're going to go into a for loop to do our experiment trials times and just use the variable T to just keep count of the number of trials that we've done。

And so what do we do for our experiment？We create a Boolean array， an end by end Boolean array。

 And again， Java automatically initializes that to false every entry to false。

And then we'll start keep our coordinates X and Y for our starting point。

 and that's going to be in the middle at N over2 and over two。And then this Y loop。

 the condition on the Y loop is that x can't be zero and x can't be n minus1 and y can't be0 and y can't be n minus1 because any one of those conditions means that the dog escaped。

啊。And then what's the condition that the dog is stuck。

 the condition is that every neighboring place has been visited so that's if I'm at Xy， x minus1y。

 x plus1 Y are the ones to the east and west and X Y minus1 xy plus one of the ones to the north north and south。

 so if they're all if I've been to all those places before， then I just increment。

 I know I'm at a dead end and I just increment that and break。

Otherwise I set this position to be true and say， okay， I'm here， I've been here。

 I generate a random number， and then I just take four cases of whether that number is less than a quarter。

 between a quarter and a half between a half and three quarters between three quarters and1。

 all of those equally likely， and if the neighbor in that direction if I haven't been there before。

 then I go there， either by incrementing or decrementing x or by incrmenting or decrementing y。

So that's my experiment I either get out of that by incrementing dead ends or not incrementing dead ends。

 and then when I'm done after doing all the trials， I just print out the percentage of dead ends。

 which is the number of dead ends divided by the number of trials。A pretty short program。

 but for a big value of N and trials， it's a huge amount of computation。

 and it can help us address this question of what's the chance that I reach a dead end。

So if I do it for again， at this time I'm doing 100，000 trials， and if I do a 10 by 10 grid。

 then I have a 5% chance of reaching dead ends。A good chance of getting out as the grid gets bigger。

 I've got a much bigger chance of getting stuck in a dead end， gets to be 30， it gets to be 58%， 40。

 it gets to be 77% and after a while when the grid is really huge。

 I have really not much chance of getting out the size of 100， it's more than 99% dead ends。



![](img/34709378fb5d8773f6d664dad7b155eb_2.png)

And I can go ahead and plot that and get an idea for what the chances are for various grid sizes。

This seems a little bit like a whimsical problem， but this is actually very like many such problems there's very important applications in science so that's our problem it's been used to model the behavior of polymers and solvents and actually Nobel Prize was one for study of associated phenomena and physics of magnetic materials and many other physical phenomena so it's an important problem that scientists want to understand what's the probability of reaching a dead end and you might be surprised to know that nobody knows people have been studying this for a long time and we don't have a mathematical model for telling us the shape of that curve that we just plotted in your one of your early programming lectures so if we know from our。

Simulations pretty clearly that it's going to be 99% plus for big values of n and the point that I want to make is that not only can computer simulation be pretty easy you as a beginning programmer can learn to do it。

 but it's actually often the only effective way to study a scientific phenomenon that's why we have this heavy emphasis on simulation at the beginning of this course it's a very well motivatedtivated application of simple programming techniques and it's important because it's often the only way to do to make an effective study of a scientific phenomenon。

So let's summarize briefly， arrays are a very basic building block in programming。

 they let us store large amounts of data， values of all the same type。

 we can instantly access a given piece of data with index or indices and twodimensional arrays and we'll see later how this efficiency derives from the way that computer hardware is organized。

 and we're going to see several more applications later in this course from a shift register for crypttography to digital audio to processing digital images to simulating in bodies in physics。

So all of those things with this one data structure。

 and we're going to study other data structures as well。



![](img/34709378fb5d8773f6d664dad7b155eb_4.png)