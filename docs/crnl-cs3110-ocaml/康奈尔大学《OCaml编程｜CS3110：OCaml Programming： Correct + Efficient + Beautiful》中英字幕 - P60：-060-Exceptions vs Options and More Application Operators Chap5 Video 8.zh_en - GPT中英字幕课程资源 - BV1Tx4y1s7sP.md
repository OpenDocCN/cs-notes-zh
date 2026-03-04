# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P60：-060-Exceptions vs Options and More Application Operators Chap5 Video 8.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We've implemented both stacks and cues with lists。 Here are both those implementations side by side。

 for easy comparison。They're very similar。Maybe the biggest difference that you notice is really just the use of options versus exceptions。

There's nothing essential to the data structures about this。

 it's more the interface that one wants to them。Exceptions make it easy to pipeline together operations。

I can just keep adding on new operations as I go。Options make that a little trickier。

They get a type checking error。Because DQ returned an it list option， an optional Q， basically。

Whereas in queue is not expecting to take in an option， it's expecting to take in a queue。

We can see that in the types。NQ is expecting its second argument to be an alpha list。

Whereas DQ returns an alpha list option there's an extra option getting in the way there of the pipeline operation。

 let's put some of that code into our editor so we can play around with it a little bit better。

There' is the error we were getting before。This expression has typetlist arrowlist。

 but an expression was expected of type int list option arrow， something。

The option is what's getting in the way。One way to resolve this problem would be to write a new pipeline operator that takes care of that extra option。

Recall what the original pipeline operator is defined as。

It takes in an argument and a function and applies the function to the argument。Now。

 suppose that the argument might be an option and we want to deal with that option。Okay。

 so I've given this a kind of crazy punctuation mark here， let's come back to that。

 but this operator is going to take in an option and a function。



![](img/9094f368a82606b190eb6b8301597972_1.png)

If the option is none， then this operator is going to return done。

 so it's going to just kind of carry that none through。But if the option is some x。

 then it's going to apply f to x。

![](img/9094f368a82606b190eb6b8301597972_3.png)

So this is basically doing the same thing as our pipeline operator is just taking care of the option around that value X for us This operator is actually available in the standard library under the name option dot map。

And maybe you can see why this is kind of mapping a function through an option。

 similarly to how we've seen you can map a function say through a list。

 this is applying the function F to the value inside the option。

 much like how list dotmap applies a function to all of the elements of a list。

The punctuation for this， yeah， it's a little crazy looking。

 but it is the traditional way of writing this operator。Now， I can use my。Option map operator。

To fix the error that I had before。One thing that does have to change here is that the return value of this entire pipeline now has an option around it because DQ could return an option and so NQ now。

 once I pipeline it through also has to respect the possibility that there is no Q there that none was the ultimate return value Now what if I wanted to do a DQ after that？



![](img/9094f368a82606b190eb6b8301597972_5.png)

HThat doesn't work why Well， because DQ itself is expecting a Q， not an optional queue。

Could I fix that with my new operator？Oh， no， I can't。This expression has type inlist option option。

 I've got an extra level of option wrapped around everything because of my new option map operator。

Essentially， the problem is that I want an operator here in between the NQ and the DQ that's like my map operator and that it can handle taking an option as an argument。

 but I don't want to wrap it in an extra level of option at the end。😡，So let's write that operator。

Okay， let's pause here。This is the operator I want， again。

 has kind of crazy punctuation that's traditional for it。

This operator is like the reverse supply operator， like the pipeline operator。

 it's also like optiontion dot map in that it takes a function and applies that function to an argument。

It's like option。map in that it finds the argument inside of the option the only difference is its return is not going to add an extra level of option around。

 which is what was giving us the two levels of options up above。



![](img/9094f368a82606b190eb6b8301597972_7.png)

And now with that operator， everything type checks。This operator goes by the name bindd。😡。

And you will find it in the standard library under that。By the way。

 once you have this many elements in a pipeline， it can be nice to reformat the code to put each element of the pipeline on a separate line。

Now the eye does not have to take in so many characters across the width of a screen and can instead read each line of the code as doing a separate step in that pipeline。



![](img/9094f368a82606b190eb6b8301597972_9.png)