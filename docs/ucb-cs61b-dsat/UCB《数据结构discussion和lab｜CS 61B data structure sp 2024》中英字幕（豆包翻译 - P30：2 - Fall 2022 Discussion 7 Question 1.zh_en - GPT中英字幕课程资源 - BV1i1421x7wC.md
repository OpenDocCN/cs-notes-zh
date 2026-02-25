# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P30：2 - Fall 2022 Discussion 7 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

![](img/6ac2ae8468250a697a6cd3c7b07b4bdb_0.png)

![](img/6ac2ae8468250a697a6cd3c7b07b4bdb_1.png)

Okay question one ADT matchmaking match each task to the correct abstract data type so our options are list map Q set and stack each of these will be used once。

 which means that there's a one to one correspondence to each of these questions so it won't be more used more than once so number one says you want to keep track of all of the unique users who have logged onto your system。

So the unique keyword is really making me think that we shouldn't have duplicates。

 so I'm going to go with a set here and the reason for that is like let's say there's like a user who logged in and then they logged out and then they logged back in well。

😊，If they already have like their username in our collection of like all of the users that we're keeping track of。

 they shouldn't appear again right because we only want to keep track of unique users。

 they shouldn't have their name appear twice because like it's not that like logging in and then logging out and logging back in made them two separate users right it's the same user logging in and out。

Number two， you are creating a version control system and want to associate each file name of the blog。

 so the keyword here is associate so I'm going to go with a map。

So here we want to put our file names as the keys in our map and they map to blob values， okay？

Number three we are grading a pile of exams and want to grade starting from the top of the pile so I think this one that is a little bit tricky but if you watch the content review video hopefully it should come naturally but this is going to be a stack and the reason for that is if you think about how like papers are piled on top of each other or a stack of things are piled on top of each other the first paper that was put into the pile is at the bottom of the stack right and the paper that is at the top of the stack was the last paper added to the pile so if we want to grades starting from the top of the pile we're doing a letFO a last and first out kind of kind of approach here right but we're taking the last paper that was put in we're taking it off and grading it and then the next last one taking it off and grading it and that's why it's going to be a stack okay。

Number four we are running a server and we want to service clients in the order they arrive so the order they arrive that is kind of a giveaway in my opinion for a queue so a queue remember is the opposite of the stock where it's Fifa it's first in first out so whatever element got put in before another element it's going to for sure be serviced before the other element and you can kind of think about this likequeuing for queuing for like a movie which was the example I use in the content review so whoever got to the line first will be able to buy their movie ticket sooner than someone who came in the line behind them right so that's a queue。

And lastly we have a lot of books at our library and we want to want our website to display them in some sorted order。

 we have multiple copies of some books and we want each listing to be separate okay so there's a lot going on here some keywords are we want to display them in some sorted order so this means that it has to preserve the order either of the ordering of in which they were added or maybe like alphabetical order or something and we have multiple copies of some books okay so that means there should be this data structure should allow duplicates。

Okay， so this is。What I think would lead to a list and this is because a list does preserve ordering right like we could start at the front of the list and no matter how many times we iterate through the list。

 it's going to give us the same order right as opposed to something like a set right where the elements in our set if we queried our set it could return the elements to us in any order right and the other thing is that we want to allow duplicates which something like a set would not allow and so because we have multiple copies。

 we want those to all appear separately in our data structure which would be best done a list。

All right。

![](img/6ac2ae8468250a697a6cd3c7b07b4bdb_3.png)