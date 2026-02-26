# UNSW《前端编程｜ Web Front-end Programming COMP6080 23T1》中英字幕（deepseek-R1 p62 -63-COMP6080 - ReactJS 💥 Class Components.zh_en -BV17RXGYuEaM_p62-

Allright， so we're going to have a quick talk。About class components。 Now。

 there's really not much to talk about here at all， in fact。



![](img/288be79a94eec4512de25946cdc4f0b3_1.png)

It's really just such a straightforward demo that I'm just going to give you the title card。

 which is this was a slide deck originally prepared by Faha that had kind of one or two slides and。



![](img/288be79a94eec4512de25946cdc4f0b3_3.png)

Today I'll be presenting it。

![](img/288be79a94eec4512de25946cdc4f0b3_5.png)

I guess just some high level things which are on the slides which are which are relative relevant and important is。

When you build components in react， so if you're watching this we're assuming that you've seen the components lecture。

 there's really two ways to do it， there's one way where you do it with classes which is the old school way which we call class components and there's another way where you do it with functions which is what we call functional components and all of the examples you will have seen in the lectures will be with with these functional components。

So we don't do anything with class components and it's a very rapidly dying trend because it's a bit more of a bo。

 So why are we talking about it， Well， we want to talk about it because it's still riddled throughout the Internet and a lot of legacy projects will have a lot of these class components inside of them。

 So while you won't have to build many of them yourself you will have to probably understand them in some cases。

 So it's very important to get your head around it and。



![](img/288be79a94eec4512de25946cdc4f0b3_7.png)

You can look at them quite simply。I just want to show you this basic app that I've written with a functional component。

 that's essentially just a component as we understand it， it's based on a function。

It's called it's the app components。 It's the main component。

 You can see I've got two state properties here， name and age。Default blank and0。

 I've got a react use effect that only has a side effect。When the name variable is updated。

 so basically if the name property name state is updated， then this function will run inside here。

But if it's not， then it won't run。This is how I can say。

 I only want you to do a particular action or have a particular effect when the name variable changes。

And then I'm returning the actual thing I want to render。 right。

 That's what the return of a function does。 is it tells you what to render。 And you can see here。

 I've got two inputs。 They're both controlled。Controlled inputs。

 controlled components where the value set to the state of name and age and the。

The onchan action simply updates that name and age by calling the set name and set age function。

 And then here I render the name in the age like this very straightforward out Hayn 88， right。

 The other thing you notice is pay attention to this name updated here。

 you'll notice that this only updates when I change my name。 So if I change the age， nothing happens。

 But if I change the name。 then that's triggered。 So that's one of the things you can do with a use effect is kind of really control when a certain side effect because。

Very clean， concise code。 What I want to show you now is essentially what。

 what these components would。

![](img/288be79a94eec4512de25946cdc4f0b3_9.png)

Classically look like。And I might do that just to start by copying and pasting us into another file and we can talk about it side by side。

 so this is the equivalent code but in the old style of components or basically class components and。

Immediately， you'll notice that with class components。It's not a function。 It's a class。

 right We have a class that's called app， not a function that's called app and that that class itself extends react dot component。

 Re dot component is just one of those libraries that's like the base component just like we do react dot use state react dot use effect。

 It's just the base react component Now you see。It's like a class， and。

Probably the only thing that's particularly similar is that the way things are rendered is that instead of your function returning what's rendered。

 you have a render function or a render method in your class that dictates what to render so you'll see these two things here are quite similar in structure one's just a method of a class the other one is the actual return of the function。

Where things get more interesting is the use state and use effect hooks。

 So instead of this nice little syntax you have here with functional components where you have like。

 you know your variable and the update action and a default property。

 how you do it with react components is that you have to create a constructor。

That constructor always takes in props that constructor always needs to construct the parent type。

 the react dot component like that's what super is it's calling the parent type because you're extending something with props and then what you do is you actually set the initial state this way so you set all of the state properties in one place So what we're doing is we're really just doing this step here that initial property for name and that initial property for age and then we're giving them an name and an age Okay so not too dissimilar there I guess in some ways if we jump straight down to our render function this is kind of where。

You gotta pay attention。 I might just wrap both of these。

This is why you really have to pay attention to。The details here， because。

You see that when I'm referencing my state objects， because this is a class。

 I can't just use their names， right， Like because app is just one function when I declare a variable called name。

 it's just name。 That's it。 So I can just use it。 I can just use name here。

 I can say that's what the input value is， whereas because this is a class。

 I need to access the object variable。 I need to access the state property of that object variable。

 which we defined up here， and then I need to access the particular state element。

That I'm interested in using。 So that's why I use this dot state dot name， this dot state dot age。

 this dot state dot name and this dot state dot age。 quite often， these will be abstracted out into。

Like destructured like this， like this dot state， you'll see that quite a lot so that you can get rid of this code。

Clean that up a little bit， but for now just keep that very verbose just so it's quite clear。

And then you'll see that with updating， you have to use with class components you can't actually call like a function per state object。

 you have to call this kind of class wide set state function。s it's a method of react dot component。

And what it does is you give it the new state to update。

It's the same rules as normal functional components， like you have your state that you print out。

 you call some kind of update state function and the react lifecycle will rerender it for you。

 but you can see here what I have to pass into set state is my new overall object。

And this can be kind of challenging because if I， if I really break this out for you， here。嗯。

You see that what I'm doing， unlike in this case。Is that here it was really simple。 I just said。

 you know what， the unchan function is just it's going to take in an event and it's going to set the name to be the value of that event。

Whereas in this case， I have to say a function is called when an event occurs， that event object。

 what it does is it calls the set state for the entire class component。

I need to use the spread operator here to say I would like to include everything from the state object and I would simply like to modify the name。

 So this is really saying like include all of the current state。Plus， the name。

We'll create a new option。The the current state with the new name will create an object out of it。

 and then we'll pass that object to set state and that will update the whole thing。

 It makes sense it's just more code and it's just harder to read。

 That's why it's also not that preferable。 So that's how you set the state。

 You can call set state anywhere inside of your class。 If you want to have extra functions。

 you can call it there。And then the last thing that's kind of different is the use effect。

 So as you know， use effect is used to say， you know。

 watch these particular properties And when they change， execute this dysfunction or side effect。

 you kind of have something similar。hi is a little less like clean。

 And you can do this a few ways in react components where there's a particular method。

 And this is prettyde。 I've actually got a link here that you can go and look up that like shows you all of the react component things。

 There's a particular method called component did update did。



![](img/288be79a94eec4512de25946cdc4f0b3_11.png)

Component did update here and this is just an example I'm not endorsing doing this on the right hand side is you can see what component did update does is it gets called every time the component updates its state and the two parameters it's given are the two parameters it has are previous props in previous state so you can use the current state。



![](img/288be79a94eec4512de25946cdc4f0b3_13.png)

And compare it to the previous state。 So here， the equivalent I can do with user effect stay。

 You know what， If my new name is different from my old name， as in if it's updated。

 then I'd like to。You know， do a particular thing and you'll see that these two things have the same behavior overall So if I run this first app here you know。

 and it's like Hayden and it's like 1，2，3 and then if I use this one instead of my functional component they have the same thing theyre just they're just a name called app that's of a certain type then youll see here when I run this it does the exact same thing。

 and in fact when I change name you'll see that the console log will update as well。



![](img/288be79a94eec4512de25946cdc4f0b3_15.png)

![](img/288be79a94eec4512de25946cdc4f0b3_16.png)

![](img/288be79a94eec4512de25946cdc4f0b3_17.png)

![](img/288be79a94eec4512de25946cdc4f0b3_18.png)

So， you know， it's okay。 It's just for both， right。

 You can see it's not so much that it's more lines of code， like it is a bit。It's maybe like 30。

 40% more。It's， it's also just that there's a lot of not that useful information here。 You know。

 there's this is quite， this is quite lengthy ways to write very concise things。

These are also very lengthy ways to do stuff。The thing on the left。

 functional components came as a natural evolution for react components， which were just again。

 how for a long time you created components that handled state。

 So that's why you've seen the thing on the left use far more commonly。 It's just on the internet。

 you will see both of these kinds of things。 and it's really important to understand they are the same thing。

 just different ways of going about it。 So if you see a react kind of component， a class component。

And you see this somewhere in a book or on the internet or in a resource or a blog， you can say， a。

 this is different to what I want to do， but I can make sense of what this is trying to say here。

 You know like that's that's all I want to give people from a lecture like this short lecture is。

This on the right。You should just be able to look at that and say， okay。

 I'm just gonna write that now as a functional componentca it's a lot simpler。

 Like all of this here is written in just a few lines there， so。And the set states are a lot easier。

嗯。

![](img/288be79a94eec4512de25946cdc4f0b3_20.png)

Yeah， now you know what these class components are。

