# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P68：-068-Include vs Open Chap5 Video 16.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Include and open can both seem very similar at first， and indeed， they do have some similarities。

 but some differences。 Let's take a closer look at that。

Here I have a module M that defines a value X， and then I have two other modules， N and O。



![](img/63bc9066a6e750deeeb3962ffe9cf892_1.png)

The only difference between them is that N includes M。And O opens M。If we load them into U。

 we can pretty quickly spot the difference。Module N ends up with two values defined in it X and Y module O ends up with just y。

Include is， as the name suggests， actually including all of the definitions from module M inside of N。

😡，So because M has a value X， N does as well。But in module O， we don't include M， we just open it。

 we open it into scope， we make its names available for use internally。

 but we don't export them again as it were。

![](img/63bc9066a6e750deeeb3962ffe9cf892_3.png)

So even though we can use the x from M to define y inside of O。

 you can see that in the outside world， x is not exposed。

So that's the difference between include and open open imports the definitions from a module。

 it makes them available for local consumption， but it doesn't export them to the outside world。

Include also imports the definitions from M and makes them available for local consumption。

 but it does export them to the outside world。

![](img/63bc9066a6e750deeeb3962ffe9cf892_5.png)