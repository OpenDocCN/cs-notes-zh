# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p23 23_01_08_强连通分量检测——Kosaraju算法深度解析.zh_en -BV11y411z7Dn_p23-

![](img/64bc584b17033a1bc8f4405c470c7621_0.png)

All right， here we have some community detection with Neo4j， which is a graph database。

 and they were able to detect trolls in tweets during the last 2016 US presidential election。

 So what I've done is I've gone over to Ru here and implemented some ways of detecting these community by writing pure rust code。

 So what we're going do is we're going to go into the world of community detection with social networks focusing on these Twitter users。

 And so I took some real data actually and and also mixed it with some hypothetical data and these Twitter username are going to be using the community detection module that I wrote。

 So let's go ahead and take a look at lib here。 you can see here。

 these were some legitimate troll accounts that I was able to capture。 And then at the very end here。

 I put in some fake community here。 So the idea here is that we're going to model another community that I'm going to detect as well。

😊。

![](img/64bc584b17033a1bc8f4405c470c7621_2.png)

By you know the subsequent tweets here are going to detect who is going to be associated with another user because they're retweeting their content and however are you going to do this well if we go back to the code here。

 we're going to import the code first and this is going be the data that I'm going to use which is the Twitter username and then we're going to use this pet graph library which is useful for both including algorithms as well as doing graph structures and we're going to use this Cojis algorithm to detect strongly connected components so this is really the trick here is that this will detect strongly detected components in a graph and then we're going to use a hashmap to store you know essentially who's talking to who。

And then if we go through here first， we're going to create the graph。

 and we're going to store the node indices by username and then we'll iterate through that other file here。

 which has all of the username here。 So this is a user and then the next is the mention so we're going to add those nodes to the graph and the hashm at the same time。

 finally we add the edge to the graph and this would be what we would call a retweet and then this algorithm is going to detect strongly connected component。

 So pretty slick here and that all we're able to do here is to put them into a vector and then each subsequent user is assumed to have retweeted the other one and so we can easily design a community detection algorithm that's very efficient and we're going to say for component in scCC again。

 this is the discovered community go ahead and print it and you could put more。you know。

 descriptive statistics if you wanted to like counts of nodes or even maybe dynamically generate a name for the community you've discovered。

 this is again a very small sample set here where I have some legitimate trolls that were used in the Neo4j data that was discovered by NBC News。

 but I also have a fake one created here just to show that there's a difference between the community so。

All we need to do is Cd into this directory here， I'm going to go ahead and go to community detection and then I'm gonna type in cargo run and you can see that it was able to easily discover that there's three nodes in one community which is journalist one journalist two journalist3。

 they seem to be retweing very frequently with each other and then we find again the legitimate troll accounts that were discovered in 2016 where all in there as well。

 so this could really be an efficient runtime algorithm for let's say a social network or maybe a company that has lots of customers or users。

 etc ce， and you could build it completely from scratch yourself and rest and have extremely good performance and in fact even distribute it as a binary tool that you could put into production。



![](img/64bc584b17033a1bc8f4405c470c7621_4.png)