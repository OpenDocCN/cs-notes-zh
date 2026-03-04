# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P166：-166-Small-Step Evaluation Chap9 Video 13.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

The final piece of our interpreter was what I'll call for lack of better name and evaluator。

 by the way we're skipping over type checking here。

 we'll come back to that at the end of this unit of the course。😡。

But for evaluation of the abstract syn tree for our simple calculator language。

 we took a complicated tree and eventually reduced it down to just an int node which represented a value for this language。

We did that by taking steps， our evaluation strategy was to take an expression。

And cause it to take a single step to expression E prime by simplifying some subexpression of it。

And then we kept stepping and stepping and stepping until we got down to a value。

 values would never step any further。So with this tree here that has nested pluses in it。

 we evaluated the left hand side of it first and caused that plus at the bottom left to step to 11。



![](img/95ddb5708f20a96f91de3ca5a7e42609_1.png)

We then stepped the next plus that also became an 11。



![](img/95ddb5708f20a96f91de3ca5a7e42609_3.png)

And we stepped to the highest level plus， and that became 22。

We're going to look in the next set of videos at this kind of small step evaluation model much more closely。

😡。

![](img/95ddb5708f20a96f91de3ca5a7e42609_5.png)