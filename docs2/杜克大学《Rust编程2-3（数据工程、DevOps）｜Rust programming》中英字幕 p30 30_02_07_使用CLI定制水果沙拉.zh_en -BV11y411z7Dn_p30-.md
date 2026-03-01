# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p30 30_02_07_使用CLI定制水果沙拉.zh_en -BV11y411z7Dn_p30-

![](img/91ebf1a7144246dff11ef80f8a1c6b5a_0.png)

对。Here we have a example of a way to customize something in rust by using a little bit of randomization here in this particular function that's in Lib do Rs。

 the code is going to take a mutable vector of strings as an input and return a new vector of strings that contains the same element as the input vector。

 but the difference it's a random order。 So some of the unique things here about rust， first of all。

 is the pub keyword here。 so what this does is it says that I can use this inside another module。

 So it's publicly available so I can pull it into my main which is a great security default here。

 Also the name here is is pretty intuitive， you just do fn for function。

 and then the inputs would include a mutable fruits。

 which is a vector of strings and also the return type is a vector of strings。 So what's。

Really powerful about this style of programming in rust is that。We're able to explicitly say。

Whether something is exposed inside of another part of the rest code。 Also。

 we're explicitly saying what are the input types and what are the output types， But even further。

 we're also showing that in fact。In terms of the mutability that we're explicitly saying that the vector here is mutable。

 Now， how do we use this， Well， inside of the main here。

 what we're going to do is we're going to use this to manipulate a CSv file。

 So the way you actually execute this code is cargo run dash fruitrus cv or you could actually explicitly put this in。

 Now， why would we care about this。 Well， in terms of data engineering。

 This is a very common problem is you have some input data and you want to make some changes to it。

 and it could be running you know hundreds of thousands of times per year。

 And so if you're able to add as many security defaults as possible and safety defaults as possible。

 you're going to have a better experience so。We're going to use this command line parser here clap。

 We're going to import the code that's in the Lib do Rs。 And then we have our setup here。

 So this is really boilerplate type code。 The only thing that's too important to really cover in more detail is thestruct ops here。

 And what this means is that。We want to actually put in fruits。 We want to put in a CSV file。

 So these are fruit inputs as a string of comma separated values。

 Then if we go down to this particular function here。

 this is going to convert a CSV file to a vector of strings。 So again。

 a very common task in data engineering is to take one data form and manipulated into another。

 what's powerful about this particular piece of code is that again。

 we're explicitly saying what the input is， it'll be a string and the output is a vector of strings。

And then it gets manipulated Finally， in order to display the fruit salad here。

 we're able to put it into another function and then finally at the very end inside of the main here。

 we actually take the option parsing pull together and then we say use fruits from the CSV file or commandline input so we can actually use either one and this is what this match does here it says in this scenario we're going to read it in otherwise we're going to actually take this as an input and then finally at the very end。

 you actually go through and display your fruit salad。

 so in order to run this typically even if I don't have to look in the documentation where I don't have access to it you know handily I can always with a rust project really in an intuitive way kind of figure out what's happening。

 So I'm going to go to the CLI here。And the first thing that I typically would do is just type in cargo run。

 if cargo run works， that's a good sign。Okay， let's go and see what happens when we compile this。

 it says your fruit salad contains， well， it doesn't contain anything because we didn't put anything in there first。

 Now notice that there is the fruits here， which we could use so。

Now that I know that it has some kind of a command line parsing input。

 what I could do is I could do dash and then do dash help and this says to the cargo tool listen pass in my input into whatever it is that you're executing and then we can see here that it's got a set of instructions this is one of the nice things about using the parser tool here。

 the library is that instead of you having to deal with all this stuff somebody else already wrote it for you and what's great about this is that I can now essentially figure out what is going to happen by just reading the instructions that come with this particular standard library。

And if we take a look at fruit salad here。Here we go。 You know， C I customized fruit salad。 Okay。

 it has options and has CSV file。 So let's go ahead and do that。 Then let's go ahead and say。嗯。

Pass in the name of the fruits right here and see what happens。 Okay， your fruit salad contains。

 So it's going to take that， that input from the CSV file， and it's going to randomize essentially。

 So if I run it again， we're gonna get a slightly different， you know， mix of of fruits here。 Now。

 we also can do more things， though， right， If I go back to the help menu。

We can actually take a look， okay， we have the ability to run a version， right。

 so I can go through here， and I can do dash dash V， big V。It's going to say， oh， it's 1。0 version。

 And I also can take fruits as an input as a string of comma separated value。

 So let's go ahead and do that as well。 so we can do。Dash dash， fruits。And we can say， you know。

 Apple。How about pair。And we can say strawberry。There we go and again。

 is able to randomize it and put it together。 So really， this is a simple example。

 But the reason why it's important to talk about is that this is a great formula to use when you're building tools for data engineering in particular。

 and you want to have something that's extremely safe and robust and can run for， let's say。

 a decade or maybe two decades， that's one of the powerful things about rest is that the language is designed in a way that it makes it very easy to do the right thing。

 which means that your code is going to be extremely reliable in the future and intuitive to other people that run it。



![](img/91ebf1a7144246dff11ef80f8a1c6b5a_2.png)