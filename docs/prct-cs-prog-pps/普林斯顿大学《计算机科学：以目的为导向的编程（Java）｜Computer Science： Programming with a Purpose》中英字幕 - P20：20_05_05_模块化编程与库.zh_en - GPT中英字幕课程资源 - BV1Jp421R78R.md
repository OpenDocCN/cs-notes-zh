# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P20：20_05_05_模块化编程与库.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/38401db17e402e52783137bfc7ba44d2_0.png)

Now we'll finish with an example that uses a number of different modules to illustrate the power of modular programming。

So the fundamental ideas for module programming first to summarize is that we've got a client。

 we've got an API and we've got an implementation， the API says what functions are available。

 implementation implements those， and the client uses them。

So a client is a module that calls a library method。Libraries methods。

 So that's like our Gaussian plot。 The last one that we did。 It calls the method， Gaussian dot P D F。

The API that's called the applications programming interfaceface or API that tells the client what the signatures are and describes the methods。

 so we usually write APIs like this， you've seen a bunch of them for our standard input and output methods。

 so we specify the name of the library and we specify the functions that are in it。

 most importantly we give the signatures of the functions and then we give a brief description of what they do。

And then the implementation has the actual code that implements the functions。

 and so we did examples for Gaussian and there's plenty of others。

 The idea is that the API is a contract， that between really the client and the implementation that gives just enough information but not too much。

 allowing the implementation to be independently developed and allowing clients of all sorts to use it if we want to later improve the implementation or change it in some way。

 we can do that without requiring that we recode the clients as long as we stick to the API。

So for example， we've built some other libraries for this course and encouraged in all programmers build libraries in order to help them better organize their programs so we're always generating random things so we took all our methods for generating random numbers and put them in one place and again they came with the software that you download at the beginning of the course。

 so if you want a uniform random number between0 and n minus1 well that's a cartoon we try to do better than that but at least we're expressing the abstraction in that what we're computing with is supposed to be equally likely to have any of the values between0 and n minus1 people still working on have efficient methods that can guarantee this in some way or maybe we want a reel this between two given double values or maybe we just want to flip a coin is it true with probability P。

Maybe we want it distribute according to the Gaussian distribution。

 either with mean zero and standard deviation1 or given mean and standard deviation。

Or maybe we want to give a discrete set of probabilities and we want to give an array and then return an index I with probability A of I。

Or also one thing we do sometimes is randomly shuffle arrays。

 So all of these things that we want to do we put in one library。

 So really the first step in developing a library is articulate the API。

 What is it that you think you're going to want to do and we went through many。

 many passes of the material in this course before really settling on okay these are really going to be useful and even without necessarily having clients for all of them。

 it seems as though there's going to be future clients that are going to want to use these and so we're going to articulate this API and then implement it Now some of these are really easy to implement。

 some of them are built in to the Java system， one liners， that's not really relevant。

 what's relevant is that this is the way we want to think of these numbers and we're expressing that with the API and therefore our programs are more compactly or more uniformly expressed。

So this is the implementation of standard random and again。

 a lot of them are one liners and we're not giving all of them and a typical client so if I say well I want to generate random points where the X Y coordinates are Gaussians centered at a half with a certain standard deviation and I'll take n from the command line and I'll draw a lot of them so this is 10。

000 points drawn in that way， immediately we can work with randomness of maybe the kind that we're interested in studying that implementation it's done once and we can work at a higher level of abstraction。

So a lot of these methods we could implement over and over again in our programs they're one liners。

 but you don't have to， you can work at a higher level of abstraction。

 try to achieve that with all the libraries that we build and provide。

So the best practices are to try to make your modules relatively small。

 if you have a big long program， you want to break it into smaller pieces and separate and classify the tasks。

 and then think about how they're going to work together， implement a layer of abstraction。

 like with random。You want to develop them independently。

 you don't want to be developing client and implementation together and in fact one good technique is to code the client before you code the implementation so that you know that your goal after all is to make your client code better and more compact and easier and more self-descriptive and you want to do that first and then decide if you can implement it。

 but you also want to anticipate the needs of future future clients when possible。

And the other thing is you should always have in every module a main test client that at least runs all the code once。

 so for standard random we have a client that generates takes n from the command line and just generates random numbers of the right type calling all all the routines。

 all the functions in the module and you can get a quick look at whether it's doing the right thing and you want to do more extensive testing as a module comes into heavy use in some separate module is it really producing random values or not。

 I'll give an example of such a module in a minute。

So we'll talk more about this kind of design activity as the course moves on as we build bigger and bigger programs here's another example statistics on arrays of real numbers we're doing data analysis all the time and again you want to find the max the minimum the average of standard sample standard deviation。

 the median all of those statistics of any given array of doubles and maybe you want to plot them too so you can plot points you can plot lines。

 plot bars now you could these are easy routines to write and there's a lot of different ways to do them but by condensing these things in one place even though they're easy to implement they're even easier to use and in fact our purpose and in creating the library was to have easy to use things and if you don't like our implementations you can develop your own implementations and you don't have to change。

The clients， the whole idea is to clarify client code and give yourself the flexibility to improve implementations in a controlled way。

So let's look at a example， client that has a program that uses several of the libraries that we've talked about。

So you can run an experiment where you flip in coins and ask how many heads did you get。

 it's called the binomial distribution， so we could put that in randomendum maybe。

 but what we do is take N as an argument and call Sina Rum。

 Bnoulli and just count the number of times that it comes up heads。

You expect to have n over two heads so if standard random do Brnoulli is working。

 we should get about n over two heads actually there's much more that we should expect if standard random do Brnoulli is actually working so let's test it so we're going to run take a and we've done this many times before we'll take a parameter trials and we'll run that experiment。

 flipend coins trials times and ask how many heads we should get a Gaussian distribution for that so what we want to do is write a program that will do this test that's going to be our example。

Now， that program without the libraries that we've talked about。

 it'd be a fairly long program by the standards of the ones we've looked at 50， 60， 7 lines， maybe。

 but with the libraries， it's a very naturally expressed computation。

So there's the binomial that we did on the previous slide。

 so then this code breaks into naturally a few parts。

 we're going to get the command line arguments that control the experiment， so one is in。

 how many flips in trials is how many times we're going to perform the experiment of doing N flips。

Then the next part is to just run the experiments so the for loop just goes trials times and then each time we iterate the for loop。

 we're going to run that binomial experiment flipping the coin n times it's going to return a value which is how many times it came up heads we'll just use that value to index into an array it's got to be between zero and n and just keep just count for every experiment its the frequency of occurrence willll increment the frequency occurrence of its value and that way we keep track of for all values。

 the frequency of occurrence and you expect n over2 to occur more often than others and you expect small numbers in very large numbers to be less frequent。

Then we'll normalize it that's divide out by the number of trials so it's between zero and1 and then call our plot bars function。

 so that'll give the results of the experiments will be a bar graph and we want to test the math says that that should be a normal distribution and so we can use our Gaussian PDF function to plot that theoretical curve。

 we use plot lines for that and this mass a lot of calculation and we can immediately test that Bnoulli。

 our random thing at least satisfies the theory that if it's used as the basis for a coin flipping experiment you get a bell curve with N over2 occurring most frequently。

That's an example of the power of modular programming。And when you look at it。

 have it's a pretty complicated program， but each module is pretty simple and pretty independent。

And these modules are not are useful for this application。

 but they're useful for lots of other applications， like when we talked about standard draw。

 we looked at an IFS application on that used standard random and standard draw so you can get interacting interlocking modules。

 but there's a lot of code here， but it's by putting it into small coherent modules。

 it's much easier to understand it and debug it， maintain it。

 improve it and reuse it all of these things， we can use later。

 that's really the power of modular programming。So why do we do it。

 It independence allows independent development of small programs。

 it allows every programmer to develop and share of layers of abstraction。

 and it provides self-documenting code so our programs are written at a higher level write we develop the API so that the client programs what they want to do is easy to understand it's specified in the name of the function。

the fundamental idea is that separating the client from implementation benefits everyone。

 including clients that don't even exist yet。But the contract between implementation and clients。

 that's the API， that benefits all past clients because the implementation has to stick to the API and that's what the past clients are depending on。

Now again， it's for a given general task， it's not always an easy thing to understand how to break it into independent modules that's part of the art of being successful in applications programming and specifying the API is a deep question can it's one thing to specify the signature of the function it's another thing to say really what it does in some kind of meaningful way that you can stick to for both client and implementation to say that our Gaussian library includes a function that implement that implements the Gaussian cumulative distribution function is shorthand for quite a bit of knowledge and that's going to happen with any different kind of function of really what do you mean by that but that's something that we're going to come back to again and again as we develop more complicated and interesting programs without modular program。

I mean， we wouldn't have much of a chance。

![](img/38401db17e402e52783137bfc7ba44d2_2.png)

![](img/38401db17e402e52783137bfc7ba44d2_3.png)