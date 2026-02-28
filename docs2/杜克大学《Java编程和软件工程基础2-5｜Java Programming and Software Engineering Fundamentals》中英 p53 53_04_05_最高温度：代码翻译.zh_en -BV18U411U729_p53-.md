# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p53 53_04_05_最高温度：代码翻译.zh_en -BV18U411U729_p53-

![](img/bdcf8e683056c6d102227042704eab94_0.png)

Now we've developed the algorithm for the finding the hottest hour， we're going to write the code。

So I've already set up the class for us with the imports that we're used to having and the class name and the method that we're going to write is this hottest hour in file。

 And we've already started， we're going to start the process with the pseudocode that we developed by the end of the last video。

 So at first， it says start with the largest so far as nothing。

 So we now know that nothing in Java is represented as。Noll， so I'm going to go ahead and。

Set largest so far， I'm going to give it an initial value of null。

 so now it starts out with null as its initial value and it's a CSV record。

 which is what we're planning to return。I'm then going to come down and says for each row in the CSV file。

 And that， again， is our familiar pattern of。Of iteration that we've been using throughout this course。

 and we're going to use the parser that's been passed in as the parameter。As the。

CSV information that were。Looping over in the iteration。

And I'm going to go down to the bottom here and go ahead and close this loop so that again。

 I sort of have the idea of what I'm going to do at each for each record as we it over it。Next。

 it says if the largest so far is nothing。 So this is the first time that we've seen it。

 and we're going to check to see if largest so far。Is null。 And again， this is。

Just like we saw in the last video， we're checking to see if the value equal was null。 If it is。

 we're going to assume that the current。Temperature， the current record， is the hottest one。

So we will call that current row or we'll assign that larger so far gets current row。

That's all we have to do for that if statement， we're just replacing it。



![](img/bdcf8e683056c6d102227042704eab94_2.png)

Otherwise， and that means else in Java， I'm going to compare the two temperature values directly。

That means I need to get those temperature values out of the record。

I know that those values are going to be numbers， but I have a decision to make should they be integers。

 whole numbers， or should they be doubles， real numbers。That's right。

 They should be doubles because doubles， because one of the temperatures was 30。9 in our example。

 And that's a real value number， which is better represented as。A double。

So I'm going to set current temperature equal to。嗱。Current row。But get of。Temperature F。

But getting that value is going to give me a string and what I really need is a number。

 so I need to convert。That string from from a string into a double。 So I'll use that。 I'll use。

Doubled up par double to make that happen。Then because I need to do the exact same thing again。

 I'm just going to go ahead and。Pate that line and I'm going to call this。Largest temp。

And I'm going to get it from。Largest， so far。And now I have two。Double values。

And I can compare them directly。I'm going to check if the current temp is greater than the largest temp。

And if it is， then I'm going to replace that value。The one and largest。So I'm going to say。

Largest so far， gets。Current row。

![](img/bdcf8e683056c6d102227042704eab94_4.png)

So I've replaced it in the two cases that we had checks for。

 and I'm done with my pseudocode for inside the loops。 And I'm going to move to the next line。

 which is outside the loop， and its said that largest so far is the answer， so I'm going to return。



![](img/bdcf8e683056c6d102227042704eab94_6.png)

larrgest。So far。Now I'm going to compile my code just to make sure I haven't made any silly errors。

 it says no syntax errors， so now I'm ready to test my code。



![](img/bdcf8e683056c6d102227042704eab94_8.png)