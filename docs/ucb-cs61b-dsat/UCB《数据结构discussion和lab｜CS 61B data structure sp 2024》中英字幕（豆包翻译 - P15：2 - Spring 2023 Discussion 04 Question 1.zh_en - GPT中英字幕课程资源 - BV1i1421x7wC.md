# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P15：2 - Spring 2023 Discussion 04 Question 1.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

🎼发明发 me。🎼Oh你。

![](img/a8ac2ed02c64bd48af8e5b46f429048e_1.png)

🎼And。🎼Yeah。

![](img/a8ac2ed02c64bd48af8e5b46f429048e_3.png)

![](img/a8ac2ed02c64bd48af8e5b46f429048e_4.png)

Allright， let's get right into question one， it's a bird。 It's a plane。

 It's a cat bus on a research expedition studying air traffic， we discovered a new species。

 the flying interfa in catbu， which acts like a vehicle and has the ability to honk because safety is important。

 So in part A， given the vehicle and honker interfaces fill out the cat bus class so that cat buses can rev their engines and honk at other cat buses Okay so we know that we want cat buses be able to rev their engines like a vehicle and we want them to be able to honk like a hounker So we see here that we have two interfaces so remember that when we have an interface and we want a class to take on the behavior of that interface we want to use the implements keyword so we'll say cat bus implements。

😊，And remember that a class is allowed to implement as many interfaces as it would like。

 but can only extend one class， but because we're dealing with interfaces here。

 we'll say that it implements both vehicle。😊，And honker。Okay。

 so the important thing to remember about interfaces is that any class that implements an interface must define or must implement its own version of the methods that are declared in the interface so what we mean by that is over here in vehicle as an example we see that it has a method void rev engine but it ends in a semi colonlon there's no open brackets。

 there's no method body for this right so this means that if CAus implements vehicle it has to implement its own version of rev Engine okay the exception to that would be if this was like default。

😊，Void revenge， And in which case， default methods in。

Interfaces are have their bodies filled out and they don't need to be overridden in classes that implement them。

 So as an example， let's say we want all vehicles to rub their engines by like printing。Um。

 dot print like room or something like that。If this were the case and rev Engine had a default implementation。

 then it's not necessary for classes that implement the vehicle interface to fill out Re Engine。

 we can just like take for granted that the oh sorry we can take for granted that rev Engine is already filled out in the vehicle class as a default method。

 but you can override the default method if you'd like in your subclass， okay， that's all。So。

 given that。We know that CAus implements vehicle and honker。

 we need to make sure that we actually implement these methods inside of both a vehicle and hounker because they're both declared right neither of them have a default implementation。

So。We're going to come over here it says CAus revs its engine implementation not shown so we know that this is return type void this is going to be called Re engine right we see the override tags so we know we're expecting the exact same method signature and then down here we have CAus hos implementation not shown we know that this is going to be avoid void。

And also honk right because honk is declared inside of the hounker interface and you notice that there's one more blank over here。

 This is kind of like a subtle thing because it's not inherently clear。

 but interface methods are public by default， so we're going to want to put public here。

In both these blanks。And that's just like a teeny， tiny implementation detail that Java is like not very helpful about。

 but just know that interface methods are inherently public， even if it doesn't stay here。

 like in fact， if you go to IntelJ and you wrote up this interface vehicle and you did like public void web Engine。

 the public would be grayed out in Java would say something like。

The public part of this like method signature is like。

It's it's basically a moot point because it's already implied to be public that's it that's just like a teeny tiny quirk of dollar。

 okay。Now down here in part B。It's a lovely morning the skies and we've encountered a horrible goose which also implements honker。

 it has a knife in its beak。By the way， like when I wrote this question just made me so happy。

 but if you this if you recognize this reference with like the knife in its speak。

 please give me a shout out or like give me a haulller on Ed or something because hopefully you understand that gaming reference modify the conversation methods signature so that cat buses can honk at both cat buses and gooses will having only one argument target。

Okay， so what we're concerned with is this conversation method over here and we see that this conversation method takes in a cat bus target。

 but we want to be able to hnk at gooses as well Okay。

 so let's draw some things out so we know we have this class goose。😊，Implements。Hunkker， right？

We're not going to worry too much about。What goes inside of the class body and then if we were to draw out the the inheritance diagram。

 it would look something like。We are a vehicle。That's an interface， and then we also have。Hunkker。

That's an interface and then we have cat bus， which is a class and we also have goose。

Which is a class and we know that oops。A kus implements vehicle and Kus also implements Her and goose implements hungerer。

 Okay， so given this inheritance diagram， how do we modify this method signature of conversation。

Keep this one argument target， but change it so that catas can honk at geese as or goose geese。

 and I really know how to call it in this case， honk at other gooses。Okay， well。

 something to consider when we do a question like this is like。

What the heck do the cat bus and the goose even have in common。

 right because we're only allowed to take in one target and currently it's a cat bus。Well。

 if we refer back to this diagram over here， we'll notice that the commonality between Kas and goose is that they both implement hnkers so they both inherit from honker。

 therefore they both are honkers right so goose definitely will have a honk method so in order to get around that remember that interfaces can be static types so basically for part B。

😊，We can knock out this cat bus target and change it into a hounker。

Target right so in the body of the conversation method， we have a call to honk， which is implicitly。

It's implicitly this dot honk， right where this is referring to an instance of the cat bus class。

 right？And then we also have target。hnk。Well， now that we've made target of type Hunker。

 we know that since Her is a is a static type and the interface has a ho method， we know that all。

All classes that implement the hunker interface should have a hunk method and therefore this will work and compile。

Alright。😊，And then moving on to part C finally， assume that cat bus and goose both use the default constructor and what I mean by the default constructor is just like。

New cat bus with no arguments taken in， which of the following lines compile， okay？

So up first we have this honker CB equals new CAus Okay。

 so we see that the static type of CB is honker， the dynamic type is CAus is CAas guaranteed to be a honker well when we come up here back to our diagram。

OhExcuse me。 when we come back here to our diagram， you know that Kus is a hoer， right。

 and it inherits from hungerer。 Therefore， it is a kind of honker。

 so we can safely say that Kus is guaranteed to be a hungerer。

 Our right hand side is guaranteed be a left hand side。 So gay compiles。😊，Then in the next line。

 we have Hnker H equals new hounker。 This is a bit more of a subtle thing。

 but if you watch content review， it's totally okay if you didn't。

 but hopefully you remember from like lecture or something that honker is an interface and interfaces cannot be instantiated interfaces cannot be dynamic types but they can be static types like we see over here and like we see in the conversation method that we updated in part B as well right we just cannot instantiate an interface because that doesn't really make sense right like a hounker is defines like a narrow a narrow range of ability that an object should have So how do we like generally make a constructor how do we generally instantiate a hungerer we can't really do that right because it describes an attribute it describes an ability of an object So this doesn't compile because。

You can't。Instantiate。嗯。An interface。Which Sam misfield that， oh gosh。Cool。

 and then on this last one， we have cap plus G is equal to new goose， so once again， we look at this。

Is the right hand side， a left hand side iss a goose guaranteed to be a kappas， We come up here。

 a goose doesn't oops。A goose doesn't seem to be a cat bus， they're both kinds of honkers。

 but just because they're both honkers doesn't mean a goose is a cat bus right there's more like siblings in this case。

 but I would describe as like sister classes and sister classes don't really make sense to to line up against each other right like a goose is not necessarily a catus a cat bus is not necessarily a goose gets kind of weird so this line is not going to compile。

嗯。Gose。Is not a kappus。

![](img/a8ac2ed02c64bd48af8e5b46f429048e_6.png)

All right， and that's the end of question one。😊。