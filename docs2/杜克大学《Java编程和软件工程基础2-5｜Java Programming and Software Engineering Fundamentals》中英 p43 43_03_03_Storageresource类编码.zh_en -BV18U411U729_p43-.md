# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p43 43_03_03_Storageresource类编码.zh_en -BV18U411U729_p43-

![](img/1d558972ae78d86fd7eec74b42e424e0_0.png)

Al right。 so you've learned that what you would like to do now is separate finding the genes from printing the jeans。

 And the way we're going to do this is we're going to take all the genes you find and put them in a storage resource。

 then you can iterate over that storage resource and print them out。

 Or if you wanted to do other things with the genes once you found them， filter them。

Calculate properties about them， whatever， you can iterate over the storage resource and do those without reduplicating all of your code to have another thing that finds them all。

So I've taken our code that prints all the genes， which we developed in a previous video and I've made a couple small changes to it。

 so I changed it from being called print allg genes to get all genes since we're going to get them instead of print them。

Returns a storage resource now because that's what it's going to give back as its answer。

 one of these things that holds all of these strings。

I've altered the comments here with the steps to the ones that we developed in the previous video where we came up with the algorithm and where these have been the same as before。

 which is most of the steps， I've left that code。For one of these。

 where we were previously printing it and are now adding it to a list， I deleted the old code。

 the system out print language we don't want， but otherwise this is pretty much the same and then in our test methods。

I've removed that code because we're going to have to do something a little bit different。

So let's start by turning these steps into code。 The first thing we want to do is create an empty storage resource and call it gene list。

 So gene list is going to be a new variable。 We need to declare。That its type is storage resource。

Gene L is its name， and it's going to be an empty storage resource， a new one with nothing in it。

That's gonna be a new。Storage resource。And then these steps are already translated to code until we get down here to where we want to take that gene and add it to our gene list。

 So that's just going to be gene list。Dot add and that gene。And then at the end here。

 our answer is gene list， as you've seen many times by now。

 when your method or function knows its answer， it returns that answer to whoever called it。Okay。

So now I want to write my method that's going to test this and we're going to test it by printing things out so our the behavior of our code is going to be just what we did before。

 but it's going to be more useful， more reusable， we could put it to other purposes than just printing out these genes So the first thing I want to do is call this method get all genes that we just finished writing。

And storage result in a storage resource variable store。hich I'm not sure I can spell。

We'll just call this genes equals get all genes on that DNA。

Now we want to iterate over the things in it。So I have here the Duke learn to program documentation because I'm not very familiar with storage resource。

 it's not one of the standard Java classes it's kind of a nice simplification for you。

 if I didn't remember how to iterate over all of these things。

 I could look at this and say okay add we just use that size。 data， returns and iterable。

 those are the things that we can write for each loops， even give us this little example here。

So what we're going to do is four。All of the strings， all of the genes。

 which are strings in these genes we just cut back we want。To print that particular gene out。

I'm going to hit compile。Whoops， up here， this was called current gene。

Java is fussing at me because it has no variable there called just gene。Fix that。And here。Oops。

 I looked up the method and then I forgot to call it。That， that was， that was good。Easy to fix。

'm gonna get， get rid of this documentation。 I'm gonna come over here。

 and I'm gonna make a new one of these。And then I'm gonna run it。

 And it ran ran just fine and gave me the same results as before。 But our code is now more reusable。

 We could put it to other purposes， more easily。

![](img/1d558972ae78d86fd7eec74b42e424e0_2.png)