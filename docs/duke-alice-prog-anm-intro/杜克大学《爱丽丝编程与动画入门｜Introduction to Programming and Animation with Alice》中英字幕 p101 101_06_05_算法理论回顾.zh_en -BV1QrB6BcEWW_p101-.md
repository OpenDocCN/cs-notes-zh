# 杜克大学《爱丽丝编程与动画入门｜Introduction to Programming and Animation with Alice》中英字幕 p101 101_06_05_算法理论回顾.zh_en -BV1QrB6BcEWW_p101-

![](img/c768fab2ab1f6d554bcdfe32091578c1_0.png)

![](img/c768fab2ab1f6d554bcdfe32091578c1_1.png)

In this course， we generally introduce the theory behind a particular programming construct or technique before providing a demonstration that illustrates that programming construct or technique。

Here we are going to do the opposite。We're going to reflect on the two projects we just built。

Let's start with a game to click two penguins。We consider the code in my first method。

We want to continue the game as long as either Penguin or penguin2 hasn't yet been clicked and is still white。

So we need to modify the buoing condition in the while loop to account for the fact that the game continues as long as at least one penguin is still white。

Once we go into the while loop， it is possible that both of the penguins are still white。

 or it may be the case that one of the penguins has already been clicked and turned red。

So then only one of the penguins is still white。Thus。

 we need to check each penguin individually to see that the penguin is still white before randomly moving the penguin and then popping that penguin up。

The game for clicking the nine penguins is a bit different。There are two significant differences。

First， we realized that we didn't want a nine way buying condition。

If penguin's pain is white or penguins 2 Pa is white， or penguins 3 Pa is white or et。Instead。

 we'll just call a function that will return true if at least one of the penguins is still white。

Using an array to accomplish this at first seemed strange。

But it allows us to handle an arbitrary number of penguins。

We iterate through all of the elements of the array。

 returning true if we come across a white penguin。If after going through all of the penguins with none of the penguins being white。

 we then need to return falses。The second real difference is that the penguins that are white don't all move randomly。

Rather， one of the penguins that is painted white is randomly selected。

 and that penguin pops up and then back down。In the two Penguin game， initially。

 both penguins would pop up and down。But in the nine Penguin game。

 only one penguin at a time pops up。Except for these two differences。

 the two games are quite similar to one another。When writing a buoying condition involving two penguins。

 it is often easiest to just use an either or tile or build a more complex buying condition。

But once three or more penguins are involved， it is normally easier to use a function。

And that function can iterate through all of the penguins in the array to determine if at least one of the penguins is painted white。

It is worthwhile to run these two previous projects again to make sure you understand the subtle differences that exist between them。



![](img/c768fab2ab1f6d554bcdfe32091578c1_3.png)

![](img/c768fab2ab1f6d554bcdfe32091578c1_4.png)