# UNSW《高级C++编程｜Advanced C++ Programming COMP6771 21T2》中英字幕（claude-3.7-s - P14：-14-COMP6771 21T2 - 5.2 - Smart Pointers.zh_en - GPT中英字幕课程资源 - BV1NGQcYLEiV

🎼，Hi， everyone。 Welcome to second lecture of week5。

 where we're going to be going through some really cool smart pointers。

 a little bit of an extension of last night。 I am sorry that， you know。

Some of you felt a little bit confused last night。 I know there was a few people kind of like trying to piece things together。

 So I hope that tonight。Things can be a bit better for you。

 like you'll hopefully we can glue some pieces together before we get started。

I would like to just touch on a quick comment around assignment  too。

 particularly in relation to testing。 So this is something that the tutors were chatting to me about today。

 which I think is。Its a really good topic， and。The thing is with assignment2。

 it's the same marking criteria as assignment one， you know you've got this 5% clang format。

 you've got C plus plus best practices， which is you know。The same kind of stuff。 But， you know。

 we touch on a few more things。 You know， that's kind of a。

 that's kind of one of those like are you paying attention criteria。 And then we have correctness。

 which。In this kind of assignment。Most of you would do pretty okay out because it's pretty easy to get most of it correct right And then it's usually that last 30% like people get conness wrong they'll get in some cases' they'll misunderstand a behavior here they'll get the Euclidean norm done incorrectly like there'll be a mishmash of things but the testing part I really I think I just want to kind of emphasize because the criteria for assessment to is the same as number one and。

The our expectations of what you do based on。Prior testing experience you might have are still the same。

 However， it's a little bit harder to get the marks in this one because with word ladder。We。

 we gave you such a simple problem。 You know， it was like， here's a function。 It gives an output。

 You just got to test it with a bunch of cases。 And many of you came up with a bunch of different cases。

But it was structurally pretty straightforward。What I want to highlight。In this particular。

Like in terms of test design。That's's important， is that。When you write multiple tests。

 what's different about assignment 2 compared to assignment 1？Is that in assignment2。

 lots of your tests will they kind of inherently rely on other tests。Okay， so。What I mean by that is。

For example。To。To test。Like the constructor， like to test say operator equals。You， naturally。

Need to be able to construct something。Right， like。

 you need to be able to construct something to do that。

 So when you write your test for operator equals equals， it's going to depend on the constructor。

 It's going to。是吧。Assume that the constructor works and this is something that's unavoidable when it comes to testing complex types because with complex types。

 you can't just test an operator equals equals in a vacuum right need to you need to construct it and then with other tests you need to be able to compare if they're equal like for instance。

 a plus operator test if you want to test if the addition works， you're going to have to。

Add two things together and then check if they're equal or you're going to have to use the subscript to check if the the values are equal。

 Like you're going to have to use some kind of either like subscript or at or equality to test it。

 So there's this inherent dependency here and a really critical part of writing good tests。

Good tests that are like， you know， not brittle and very kind of clearcause， I mean。

 there's things here that aren't overtly written into this criteria that are kind of， you know。

Part of good testing。 and one of them is reducing the amount of dependencies in your test。

 So what that means is that dependencies are unavoidable in testing。

 but every single test should be designed in such a way that it depends on the least number of other things possible。

And your test should be split apart as much as possible。 You know。

 so you shouldn't be testing operator equals and operator plus in the same test， you know。

 and you shouldn't be like。And they should be ordered in a certain way as well。

 right So your earlier test like your test1， however you name the files or whatever。

 it should be very clear that， you know your first test tests the most basic thing。

 So from a structural perspective， we should see your test for the constructor。

Before the test for your operator equals。嗯。Naturally。

 the first few tests are going be a bit chicken and egg。 you know。

 like to check if the constructor works， you kind of need the subscript or you kinda need the the print or something。

 but。But yeah， just be very thoughtful about the ordering and the dependencies and the layout of your tests because that's kind of the difference between。

 you know， like a student who's getting 95 out of 100 in assignment to and the student who's getting 100 out of 100 in assignment to。

So yeah， just keep that in mind。 And I think just last thing。

Printing is not a great way to test things。 And we saw some students do this last year。

Where like all their tests would actually like print。

 they'd like output it to a string stream and then compare the outputs and stuff that's not really good testing practice in any kind of language because you're essentially pausing outputs and stuff。

The better approach is to like generally speaking， if you're doing any kind of comparisons。

 if something works， you should be using either the comparing two whole Euclidean vectors with operator equals equals。

 or you should be using the dot at or the subscript to get the values and do like a line by line comparison of things I hope that makes sense anyway。

 just before we move on。Thought we'd spend 10 minutes at the start just touching on this because as you'll start to notice soon。

 this assignment isn't too hard， but the testing component is actually a little bit more difficult。

 I guess than the previous assignment。 So you probably spend half your time writing tests。

 And in fact， I would encourage you to write tests first。 I know that's like。

 I don't know that's an annoying thing that everyone says， like， write your tests first。

 And you're like， yeah sure I'll do that。 But it's such a straightforward concept。

 This assignment that you actually could。Like you actually could write your tests first and you could stub out all like you could stub out all of your code with like stub code and then you could write your tests and then you could write your code and you'd actually be amazed I've done this like three or four times in my life which is nowhere near enough And it just like it like blows your mind how rapidly you can develop code and you actually get good results in the end because you wrote your tests in a vacuum and you weren't biased by your particular development behavior。

 So it's good all around。嗯。So。Yeah， anyway， any questions， otherwise we can move on。Great。Okay。

 let's get into。How many people got here tonight？51 party。

So let's get into the actual content so lectures tonight we're looking at smart pointers。

 smart pointers as opposed to dumb pointers， so smart pointers the topic is somewhat self evident。

 we're looking at pointers but we're hoping to find smart。😊。



![](img/2234d19c866af44cea776f9097826c88_1.png)

Pointters。UmAnd。Like what we're talking about here is that。😡。

As we learned yesterday in managing resources sources。

 managing unnamed or heat memory can be dangerous。As there's always a chance that you don't release something or free it properly。

 And like， yes， sure， you can wrap it inside of。Like sure you can use things that abstract it away from you like standard vector。

 but someone still has to write standard vector， someone still has to work with those dumb pointers and manage them like the class we were writing yesterday。

 the my V class。So we need to find good solutions to make this robust as opposed to just you know praying nothing goes wrong so we're going to learn about smart pointers then the two main types are unique pointers and sharedd pointers and then we're going to talk about partial construction which is a really useful example of why。

Smart pointin is really valuable。Okay。嗯。Bit of a recap on yesterday R AII Re acquisition is initialization。

 The purpose of that was to make unnamed objects safe by wrapping them in a named object。

 So this is just a bit of a reminder for anyone from yesterday or however long ago you're watching the lecture or if you're binging this sometime later in term。

10 minutes ago。Where we have a class here called My Intpointer。

And it follows the same behavior we've seen before where when someone gives us a pointer to a value。

😊，嗯。When someone gives as a pointer， the actual endpointer is responsible for destroying it。

 for deleting it， removing it from the heap when it's destructed。

So that's good behavior right because we haven't had to free anything we're using the stacks like lifetime scope rules to invoke destructors which free things for us。

 so we're managing unnamed resources with named resources。嗯。

Where we can make this even simpler for ourselves。😡，Right， and by simpler， I mean。

 avoid this murky stuff over here where we're like， I've got to destruct and free things。

 which we don't like is that smart pointers are a type that's baked into C plus plus from C plus plus 11。

 You don't have to。

![](img/2234d19c866af44cea776f9097826c88_3.png)

I du't know。 Do you have to， Do you have to hash include anything。It's I always get these mixed up。

 I think you do have toh include。Something， I think I get these mixed up with Yes， it's memory。

 That's right。 So because I forget thats so static cast。

 you don't have to I always get static cast and unique pointer mixed up in my head for some reason。

 so。There's a library called a memory library which has these pointers defined in it。

 it was added to the C++ 11 standard， and what a unique pointer is is it's a way of wrapping an unnamed heap object。

Into a named stack object so that that stack object can maintain， you know。

 can deal with the object's lifetime。 So it's a great。😊。

It's a great mechanism for doing all the stuff we talked about yesterday， without having to。

You know without having to manage all the the BS of trying to， you know。

 worry about destructors and freeing stuff。And if we do this correctly。

 what this inevitably leads to is。Uk not having to worry about heap stuff at all。Okay。

Cole of people in the chatter talking about lag。If there's lag on the stream。

 I can't help you much because like the problem with these lectures being at this time at is that this is peak residential internet usage time。

It's kind of annoying。 So if there's lag， I'm sorry， I wish I could fix it， but like。

The upload speeds here are normally way fast enough to stream to YouTube。 And if it's terrible。

 you might just want to pause it and watch it later or watch the recording， but。

But the recordings good。 So if you're watching this on YouTube later， that's fine。

 So we have these smart pointers。 and there's two types of。

Kind of smart pointer pairings that we work with， which either we use a unique pointer which is one of these special smart pointers and raw pointers which are just like dumb pointers。

 C style pointers， we use these two things in conjunction or we use a shared pointer with a weak pointer。

And unique pointers， Sha pointers， weak pointers are all special types inside of the memory library。

And what's what's the kind of difference between them is that they all have different properties in terms of whether they can share ownership over a resource。

Or whether they can take ownership over a resource。 So this will make more sense soon， but。

Unique pointers and shared pointers actually take ownership of something and what do we mean by take ownership？

第一。One of a simple way of understanding it for now is that if you look at this old example here。



![](img/2234d19c866af44cea776f9097826c88_5.png)

The my int pointer class takes ownership of this pointer we pass into it because it basically says I'm going to be responsible for making sure this is cleaned up right So that's a really simple way you can think about ownership。

 It's like this is my problem。 This is my responsibility I'm going manage this unnamed resource。

 So all four of these things just to see style pointer and when I say raw pointers there I'm actually talking about you know like in star I。



![](img/2234d19c866af44cea776f9097826c88_7.png)

![](img/2234d19c866af44cea776f9097826c88_8.png)

That's a roll pointer in C。These four things are going to be named stack objects that are managing heap objects in different ways because remember。



![](img/2234d19c866af44cea776f9097826c88_10.png)

A stack objective in star I is a stack。Object that's a pointer to a heap resource。

 So they're the four kinds of things we're going to look at。 Now， the first one is unique pointer。

 This one is probably by far the most relevant， by far the most。



![](img/2234d19c866af44cea776f9097826c88_12.png)

Commonly used， you'll be using it in assignment too。🤢，Which will solve some of your problems。

 I mean you're already actually using it if you've used the stub code we've given you。

And you use it like this。 It's a little bit like a standard vector in that you say standard unique pointer。

 And then you give it a type inside the， the little side bracket things。

 I still don't even know what they're called。Side hats。嗯。

So it's a library type STD column colon unique pointer。A unique pointer's job is to own the object。

 to take ownership of the underlying he resource。And what that ownership means essentially。

 is that when the unique pointer， which is a stack object， is destructed。

 the underlying heap resources too。So I'll come back to the next part。

 but let's have a look at an example， because this one。



![](img/2234d19c866af44cea776f9097826c88_14.png)

Demo 5，5，2。So I'll have a look at this example， and I'll start off with something even。 sorry。

I'll start off with something even simpler。Demo 5，5， oop， see。

 I just changed the kit to the wrong thing。 kit，6，7，7，1。V S code。I like VS code， it's cool。

 I think it's one of the best editors out there but。😊，The reason I still use sublimmescause I get。

 I get so， I get so anxious when it just spams crap at me all the time。 And I feel claustrophobic。😊。

You know， I used to blow my mind really quick tangent。 People used to like。Lecture with V S code。

 which like always fascinated me because like one really novel thing that most of you probably don't think about much is that the like a lecture theatre at UNSW is like a projector that's like。

20 I don't even know what the resolution is， it's like 1024 by 768 or something like it's nowhere near 1080p so。

It's so nice to lecture at home， and I would probably I would probably very much resist lecturing at the uni again without 1080p monitors because essentially when you're lecturing on like a 1080p monitor。

 you're basically lecturing on something that is like this big。😊。

So it's like really hard to really convey much information in general It's kind of whack Anyway。

 thanks for listening Some tutorial rooms actually do 1080p projectors， which are cool but。😊。

I'm going to delete most of this code here， and then we'll we'll unwind it。

 So I might just copy and paste this and then hide it。And start with a really simple。Thing。

We demand 4 K projectors。I remember someone told me once I was talking to someone in facilities management at UnSW。

 And I think they told me that UnSW spends。Think it was like a million dollars a year changing projector bulbs so that they spend a million dollars a year just on projector bulbs。

 That's a very unverified fact， but。Sounds about right。Okay， so we're gonna build this now， build。

Wrong build， sorry。You just zoom in slightly。So I'm going to build。5ve。Goodness， gracious。

Thanks for being so patient with me here。啊。Stop being difficult。That's the wrong file。

 I want to build 5，5，2。 So I'm going to build 5，5，2。And this one will build。

 And if you have a look at this code here， let's think about what's actually happening。

 I just zoomed in really close just for those with a bad connection。 So I have a mean function here。

And what I'm doing is I'm creating a new heap object。 I don't think this star is actually necessary。

On the order。So yeah， I'm building a new heap object here。



![](img/2234d19c866af44cea776f9097826c88_16.png)

And then I'm creating a unique pointer。嗯。And a unique pointer。Is of type standard string。

 So what this says is that unique pointer， which is a smart pointer。

 is simply an object that will own a raw sea style pointer for us and take responsibility for it。

And then we give it that heap pointer in this case。

 So what a unique pointer constructor generally takes in in this case。

Is a pointer of type string standard string， So it expects the type of the subject to be standard string pointer。

Because you know it looks after a pointer， so the way this program works is that we create a new standard string。

On the heap program managed， we wrap it in a unique pointer。And then when this program。

 when this SArs scope ends。We get the destructors called on UP1 and because Uni pointer is a resource because it's a stack object acquiring a resource。

It gets like destructed， right， like all stack variables， it gets destructed。

 which calls the destructor unique pointna。 And what do you think the destructor unique pointa does。

It's going to do exactly what you expected to do。 It's going to call free on the thing you gave it。

So very capable of just simply handling that for you。嗯。

You'll also notice here and this is one of the other interesting things about a unique pointer is that we can use a unique pointer as if it is a raw pointer。

 so the interesting thing about how this is implemented is that the operators that are overloaded。

The D reference operator， the stab operator， as one of you called it。

 they all just simply pass through So when I call like when I call D reference on U1 somewhere inside the unique point of class。

There is， you know， inside a public， there is like an operator star。And what this will basically do。

Is it will essentially just like， let's imagine that the unique pointer has a just this is for strings。

 We we're doing templates next lecture week。 So let's say you have a string object inside of it called Lake pointer。

 So that's the， that's the pointer that it's managing。 All it's going to do is simply return。

Pointter， it's going to dereence it。For you。 So the way the operator works with a unique pointer is it essentially just kind of like passes that information up through。

 So when you dereence a unique pointer， it just gives it's like， oh。

 you want to dereference me Well I think what you really mean is you want to dereference that pointer I'm looking after So it just gives you the dereference of that。

So it's a little bit of a pass through thing。 So that's the cool thing about unique pointers is that and smart pointers in general。

 is that you can effectively treat them like raw pointers if you were to。😊，Subscript this。

 that might even work。 I'm not too sure， but you can do something like this。 You can。

 you can do that on it。 You can totally just dereence it and， you know， call like dot size。

 So I could do something like this or dot。What is it for strings to get the length？

Is the dot length or dot size always for。

![](img/2234d19c866af44cea776f9097826c88_18.png)

Someone will probably tell me quickly。Both。One of them is deprecated， isn't it。



![](img/2234d19c866af44cea776f9097826c88_20.png)

That I can't remember。 I think one of them is not recommended。嗯。Yeah， so now when I run this one。

Demo 5，5，2。It prints out， you know， what is this too？

So I'm actually able to treat the unique pointer as if it was a point to the string itself because。

What you would normally do in your program is you'd normally have。My heap object here。

 So normally you'd have this like stack， so this over here， like if this is your stack。



![](img/2234d19c866af44cea776f9097826c88_22.png)

You'd have like my he object。 And over here， you'd have your he with your actual。A。

Like string with all the data of the string。And this here would be a pointer that points to that。

Whereas what we're actually doing here is saying that， you know。

 I'm going to create a unique pointer。And。This points to that instead。 Now， I mean， in actual fact。

 what happens is they both point to this。 Like if you think about this program here。

 both my heap object。

![](img/2234d19c866af44cea776f9097826c88_24.png)

And UP1 both point to it。 so like I could， for instance， print this line out again。



![](img/2234d19c866af44cea776f9097826c88_26.png)

With like my he object， and I could build it and run it。 And is that the right one， yep。

And it would work fine。So they're both pointing to it。 it's just like one of them owns it。

So the language that we actually used back in the previous slide here was that often when we work with unique pointers。

We sometimes have raw pointers as well that point to it too， that we call observers。



![](img/2234d19c866af44cea776f9097826c88_28.png)

So in this case here you would call my heAP Ob and observer because it doesn't take ownership。

 so this UP1 has ownership over the heAP resource because it's like a unique pointer。

And ownership basically means it's responsible for figuring out whether it should be freed or not。

Because like， I'll show you what happens here， right， Like， pay attention to it。 So if I。

If I was to say， for instance。Do this。This program will run， but it will not work。Yes。

Let me put this on release for a second so that we don't have the。

Address sanitizer picking up on our stupidity。 So have a look at what's happening here。

 Think about this one for a sec。 So we have a my heap object， which is a new standard string。

 So this is on the heap。 and my heap object is pointing to that heap thing。

Then we create a unique pointer。Of type standard string。

 where we give it the pointer because remember we give unique pointers a pointer。So， I like。

I want you to take this， take ownership of this pointer form me and it's like yes。

 I will do that for you and then we try and print it out。

 we print out the size effectively but then this scope ends and what happens when a scope ends all of the names。

 the variables that we defined in that scope are popped off the stack。

So if I define n equals0 here and order U1， both of these variables are popped off the stack in reverse order。

And the destructors are called and the destructor of a unique pointer frees the resource。

 So if I delete a unique pointer， it's like， oh I'm taking the heap resource with me and it calls delete on it。

 that's the benefit of it。 But in this case here what's happened is like the actual heap object here has been freed。

But the original item that we。

![](img/2234d19c866af44cea776f9097826c88_30.png)

We had here。Is still pointing to basically a free piece of memory。

 So it's kind of like pointing to an invalid thing。 That's why this doesn't fail。

 This is undefined behavior。 This might have segaled。 We got lucky that it just printed zero。

 And when we're on debug mode， the address sanitizer picked that up for us and was like， hey。

 you can't touch this。 don't do that， please。嗯。Our observe is bad practice。 No， they're not。

 We'll get more into best practice in a sec。 I was more just demonstrating basic mechanics。

 So let's actually keep going through this example because I want to show you a few things about the unique pointer。

 So now that I've demonstrated the absolute basics of scope。

 let's actually look at how this thing might be used。



![](img/2234d19c866af44cea776f9097826c88_32.png)

![](img/2234d19c866af44cea776f9097826c88_33.png)

In practice， so I've got this really long function here。And it's very similar to what we had before。

I might I might comment out a few extra lines， and we can uncomment them all progressively。

So look at these first two lines here。 we create ourselves a heap object。

 new standard string like this。This is exactly what we had before。

 we passed that pointer into the unique pointer， so the unique pointer now owns that pointer。

And then this program will still compile for us。 However， have a look at this。

If I build this and try and compile this。It actually fails to compile。And that's because。

I forgot to put a comment there， but let's try again， and it will fail to compile as well。



![](img/2234d19c866af44cea776f9097826c88_35.png)

And the reason is， if we scroll up to the top， it will say。

Called to implicitly deleted copy constructor， So we learned about copy constructors yesterday and we learned about defaulting them。

 synthesized， deleting them， and in this case here what we've learned is that a unique pointer has no copy constructor。

 it has been deleted from the type。Now， why doesn't it have a copy constructor？ Well。

 that actually makes a great deal of sense， because if I have myself a unique point of one here。

And it points to a heap resource that let's say， is like a string。You know， strings AB，C， DE。

What happens if I copy UP1？You know now you could think of two things you could say。

 oh well U's one job， UP1's job should be to like copy all the resources when I copy construct it。

 so if I try and create UP2， maybe its job is to create all this new heat memory。

 copy all the heap objects across。And then it's like a new thing。

 But that's not really the behavior of a unique pointer that we want。 Like we don't。

 that's just not how we're going to define it。 It could be defined that way， but。

That's how you end up with like a whole bunch of sprawling data。

 So the other way you could do it is you could literally just copy the object。

 What would the default C plus plus synthesized copy constructor do。Well。

 we could kind of imagine that the unique pointer has a pointer in the data members。

 in the private data members。So maybe we'll just copy that。

So maybe there's a data member inside unique pointer1 called light pointer。

 like we had in our example with the string。 So now it's just both point to the same thing。

 but that would make even less sense。Because now， as soon as one of those goes out of scope。

 like we saw yesterday， it's going to free the resource and the other one' is going to be pointing to an invalid resource。

 So for the sake of just simplicity and clarity， a unique pointer can't be copied。

Because we don't want to copy resources and we don't want to have two unique pointers pointing to the same resource and in fact that's why we call it a unique pointer because it it uniquely points it has a unique ownership。

 it's the only one who owns a particular underlying pointer。



![](img/2234d19c866af44cea776f9097826c88_37.png)

![](img/2234d19c866af44cea776f9097826c88_38.png)

So that's one attribute of it。If you wanted to create a second unique pointer。

 you could do it like this。You don't have to split this up into different lines and in fact。

 we don't recommend that you split that up into different lines that's more just there to demonstrate behavior again。

 So in reality， this isn't a great way to split things up because now you've actually got this slight pointer on your stack called my heap object。

That someone might kind of use inadvertently。So if we actually make a unique pointer。

 a better way to do it than what's up here is to actually put the new directly inside the constructor for the unique pointer。

Because that means that the only time after this line here。That anyone can get。

The value in the unique pointer is through the unique pointer itself。So that's a good thing。

So youd probably that's better than what we saw up here。Now。

 you can store standard move on a unique pointer。 You， you can use unique。 Sorry。

 you can use standard move on a unique pointer because its move constructor makes sense。

If I want to create a new unique pointer called UP3。And I would like to move UP1 to it。

 all we're really saying here is I'm going to get UP3 to point here now and I'll get UP1 to point to null。

So we're just moving it。So moving makes total sense。



![](img/2234d19c866af44cea776f9097826c88_40.png)

Oh my god， Miss chairs。Fuck。没啊。哪。啊。Okay， sorry， it's like eight years old。

I love this chair so much raised me， but。Yeah， sad days。F was is it， What are the money say。

 press F for the。Fallen chair。 Thank you。So you can move a unique， a unique pointer。

 That's a good property of it。 And you can see here that， you know， our first unique pointer is high。

 Our second unique pointer is goodbye。 We move。The first unique pointer to the， the third one。

 And let's see what happens when we try and print it out。 Now。

 what do we learn about yesterday when you move an object， it's in a。Mm。You're all great。

 It's in a valid but unspecified state。um。So then what happens here？

When we run this is what's going to happen。Well， we're going to have a similar kind of problem。

 I think， where in this case， were seg faulting because。

A unique pointer looks like like a unique pointer looks like that when it moves when it's moved from。

 when it relinquishhes access and gives it to someone else。

 it sets its internal pointer to null pointer。So when we tried to dereference UP1。

 after we moved it to UP3， we get a Seg fault on unknown address null OXO0。So。Yeah。

So that's in now a valid but unspecified state that we should not work with。

 we should like it is not to be used anymore。So we can move things。You also can't copy assign。

 It's not just copy construction you can't do remember this one's a construction because the variable is being created on that line。

 you also can't do copy assignment， so there's no copy semantics for a unique pointer。

There are a whole bunch of other interesting behaviors that you can express with a unique pointer。

Which I'll how do you comment line quickly again， I don't remember。

And let's have a look at all of these together。Oh， what did I do wrong。

 Are was still printing that out。Oh， what's happening now， What have we done， Someone will know。嗯。

I'm just gonna get rid of these lines here。 Maybe， maybe there's something wrong happening now。

 or maybe I just missed a problem。 Maybe I've misdiagnosed something。 Nope， it's something here。



![](img/2234d19c866af44cea776f9097826c88_42.png)

Alright， well， let's take it slowly then， so。We've got UP3 because we move UP1 to UP3。

Kai says when you move U1 to U3， does U3 get freed automatically。

 That's a good question because we had two heap resources here。 we had high and goodbye。

 So when you move U1 to U3 U3 does free what's there previously。

 So the unique pointer handles that too。 So it's freed the goodbye for us because it's no longer it had ownership over it and it no longer points to it。

 So as it relinquished ownership to take new ownership it freed it。

 So it very much is a you know a managing resource for us。 Now there's a bunch of other commands。

 you can see on a unique pointer if I go to CP reference， we'll see some of these。Unique pointer。

There's reset and release that we've looked at。嗯。So reset。And release。 So what does reset do。

 Reset replaces the manage object。 Okay， so that kind of makes sense。

 It's kind of like saying I'm gonna replace the manage object。 It。

 it seems a little bit like assignment。Not copy assignment， just assignment generally。You know。

 that's interesting。 I'm looking at the。The operators and it looks like the operator equals might do a similar thing。

 perhaps。Oh， nope， this one is。Okay， what do we got， we got move assignment。Yeah。

 it looks like it can't really。Do it。Anyway， this is kind of like how you would say reset what the pointer is。

 So the actual reset method here replaces the manage object with something new that you pass into it and you pass it in a pointer to now point to。

嗯。Given current pointer， the pointer that was managed by this performs of following action saves a copy。

 the current pointer overwrites the current pointer with argument that if the old pointer is non empty police approved。

 so it does the same thing as like move assignment。

 it frees what it currently has and it takes on something new。

 and then we have the release method which releases the ownership of the object if any。

So essentially a release release is kind of like transferring out。 it releases control of it。

 but it doesn't free it。And that's a really important thing。

 So you know how like when we started this whole thing。

 we like this was kind of the step of a unique pointer capturing a resource and taking ownership of it。

Well， we can release it as well by saying UP1。Don't release。And when you do that。

 you're essentially saying to the unique pointer， I want you to no longer manage this。

Forget about it。Doesn't exist。Except it doesn't free it。 That's， that's kind of the key thing here。

 So you could actually， this will actually return the pointer that it was managing。

 So that's kind of a way to like ununique pointer things if you want。

 So U P3 dot reset and U1 dot release is a little bit like a very verbose confusing way to do a move assignment or a move constructor in this case。

um。We could move UP3 to UP4 if we want Another thing we can do is the dot get method。

 so when you have a unique pointer like UP4， which I think is high at the moment。

Let's see what the do yet does for us。So， the dot get。Actually， gives us。Right。

The do that make this clear returns a pointer to the managed object。

So the dot get gives us the actual pointer there It gives us the same value of my he object and you can see this right。

 Watch what happens if I try and print out my he object。

 which was the original malik we did because that high was like Malik up here then it was given to the unique pointer transferred to U3 then move to UP4 and now let's print out what UP4 points to and let's print out what the original stack object points to and we will see probably the same thing。

Right， so it's still the same heap resource。 Everything on the stacks just pointing to it like you know。

 the stacks job is just a point to these objects。And then if you try and dereference U P4。

 what so like。Dereferencing UP4 is the equivalent of doing this。

Which I know might let me just comment out more in case there's problems。

And I want you to think about how the operators work here。 Have a look at this。

Dereferencing UP4 and dereencing UP4。ge gives you the same thing。Because again。

 when you call the Dreence on UP4， the unique pointer is operator overloaded。

To simply give you like it does like a two level thing， right。

 it just deres its underlying pointer and bubbles that back up to you。

 So dereencing a unique pointer is exactly the same as dereencing the thing that the unique pointer points to。

 And this is why with your assignment。We kind of say to you。

 you can start it without worrying about much because like， you don't need to worry about the。

 the where is it and the compulsory data members because we're like， oh， magnitudes here。 Yes。

 that's a unique pointer。

![](img/2234d19c866af44cea776f9097826c88_44.png)

Sure。But as we've just demonstrated， you can actually treat a unique pointer like it's a raw pointer in many ways。

 So you could subscript a， de referenceence it like。All those like a lot of standard things here。

 There's not like a whole other semantic associated with it。 Ryan says。

 is using standard making unique bad。 No， it's not。 We're gonna talk about that soon。

 So it's definitely not bad。It's raining again， Do you guys like the rain， hope you like the rain？

I like the rain a lot， makes me really happy。Once have a look at this example。Okay， yes。 I mean。

 this gets straight to your question。Ryan。嗯。Just before I get to that， Sus says。

 what does get return if we make a new object inside the unique pointer？Well， it。

 it returns whatever was like wherever it， wherever it maled。 I mean， like in this case here。

 it's gonna return like。Remember that the actual Malik is what returns a memory dress。

It's an R value， right it's just a value that is assigned to an L value。That is the address， so。

This here， this is actually what the address is， the return of this statement。

 It just so happens that we were capturing it in this variable here and then putting it in here。

 So this kind of thing is exactly the same。 It's just going to be another kind of pointer。

So to come to this question here， an observer pointer。

 like what is the usage of an observer pointer well。Theres。

You'll kind of see this with assignment 3 with graphs。 But the point is that quite often。

Quite often you actually want to have many things pointing to a resource。

 like not just one single variable in one part of the stack。嗯。



![](img/2234d19c866af44cea776f9097826c88_46.png)

You know。Like， let me give you an example。 This is a very quick tripe example that I'm just making up。

 but it's like。If you have a unique pointer like UP3 here。嗯。

And you want to call a function that takes in， say a to a string。Like this。

You can't like you can't firstly， you can't really pass a unique pointer in as an argument。Because。

 I mean， firstly， in this case， the type's not right。

 but you couldn't even pass it in generally because when you call functions。

 they copy semantics It'll copy construct and， So it'll fail to do that。

 So the anyway way you could pass a unique pointer into another function is by reference。

Which is like， okay， though。An example of where you might use a raw pointer is to simply say。

 I'm going to call do something， but I'll just call U3。ge。So I'm just going to kind of。

Get the pointer from the unique pointer。

![](img/2234d19c866af44cea776f9097826c88_48.png)

Go do some stuff with it in a function without having to like reference the unique pointer or anything like that and then the functional end and all of that。

 So it's really just a way like a raw pointer or an observer pointer which are the same thing is really just a way of saying I'd like to create more things that point to this。

 but they're just not going to track whether it should be freed or not。And again。

 this will make more sense for like assignment three because assignment 3 is going to be。

Need to use that。Assignment 2， though， you don't really ever need observer pointers。

 assignmentsment 2 is really light on the smart pointer stuff。

 Pink Oomega says we are playing around with those pointer stuff to avoid copy when returning， right。

 That could be one reason you're doing it like that。

 I know you could also pass in the unique pointer by reference。Its again。

 it's hard to explain without more extensive examples。So for now。

 you just have to kind of not think too hard about it， but。The point here is that。

I create a unique pointer called U P1。 I assign the value to 5。

 It was originally constructed with value of 0。 I assign the value as 5。 I print it out。

 I now create an observer pointer。That points to the same resource。

This doesn't O P1 does not point to the。Smart point it points to the same resource the smart point it points to。

 and then I can use the observer pointed update things and so forth。

 So this is just this is just behavior that exists when where where it's best applicable。

That might be harder to make sense of right now， but there's a question at the bottom here， which is。

Can we remove the new completely。Like this， this thing， here。And the answer is yes。

 through the use of standard make unique。 So there is a function in the SDD namespace inside the memory library called make Uni。

 And what make unique does is it provides the exact same behavior of constructing with。



![](img/2234d19c866af44cea776f9097826c88_50.png)

A unique pointer。For instance， if I have a program like this。Very simple program。That runs fine。Then。

When I。If I want to make this even cleaner， I could do something like this and say auto UP4。

 I'll just do UP3 and U4。Equals standard make unique。 Give it the type I want it to make。And then。

 simply give it the value。So make Unis quite interesting because it essentially takes all the arguments that you give it。

And it kind of delegates them to a constructor of the type you passit。Which it puts on the heat。

 it's a very straightforward idea， right， because。Calling unique point is always generally going to follow the same behaviour。

 It's going to be like unique pointer， the type， new type， and then all the arguments we're calling。

So with make unique， we're like， oh， let's just skip all that， I'm just going to make a new unique。😊。

Heap object。 And here's the arguments for it。 So it's really just collapsing those。

 those little levels of abstraction。The reason this is great is because it pretty much means that in our code。

 we never， ever have a reason to use new and delete。

 There's no real possibility that we could accidentally。

Recreate like we could create an like an unnamed stack resource that isn't managed properly。

 So Diamm says， which do you recommend for the assessments， absolutely make unique。

 So make unique kind of like the gold standard for this stuff because we don't want to see the new and delete keyword in your code because there's no reason for it。

嗯。第二。

![](img/2234d19c866af44cea776f9097826c88_52.png)

Cool。Okay， that's pretty much it on unique pointers。 We're about to move on to shared pointers。嗯。

Before we do that， though， let's take a five minute break because we're close to 7 o'clock。

 Let's start up back up at 7 and get into shared pointers。 So yeah， sounds good。

 I forgot to un pause the recording for like 60 seconds。

 but I don't think we talked about anything riveting just some questions on the chat。

 but we're looking at make unique and unique pointer， so。Make unique and unique pointer。

This code works， right， if I go and run it。Hello， hello， let's see what happens if I try say。😊。

You know， int。 Now this one will also make sense because I could just say five here。5，5，4。

Works like that。 Let's try those standard vector。 Now， what do I pass， standard vector of nts。

 What do I pass into this， Do I pass into a standard vector of Ns 1，2，3， Is that what I pass in。5，5。

4。m's not very happy about that。Why is it not happy about that instantiation of undefined。So。

In this case here， I believe you would。Go， sorry， I can't remember this right off the top of my head。

I think you might do this。 I don't know。 Let me。No。I am not quite remembering this one。

We gonna do one and 2。 Let me try this。Oh， sorry。 I missed that one。 I wasn't。 This。

 this is why I hate This is why I hate the small。Screen because I'm trying to skim read these and not actually。

Not actually read them correctly。And now we can't print out a vector， which makes perfect sense。

 That's kind of normal。 But we can print out U P1 or something if we want。 So again， you。

 you kinda have to， you kinda。You kind of have to imagine。The unique point is is essentially like a。

A totally transparent abstraction。Of。What they're a pointing to。

And the kind of design philosophy of things like Me unique is like totally the same， too， where。

Make unique has a desire。Such that the arguments you give it。

As is as if you're constructing the actual resource itself。

 so if I wanted to use an initialr list here， which I believe works。

That one wasn't too happy with me， but probably doing something tiny wrong。

 But like what's happening here is we're calling that standard constructor of like create 1。

 two times。 I think it is。 I can't remember if it's2，1 time or1， two times。 I think it's one。

 two times here。 but're actually calling that on the vector。

 So what what make unique is doing is it's actually saying， okay。

 well I'm going to take your arguments you've given me here。

 I'm going to go and create a new vector on the heap。With new with those arguments you've given me。

 and then I'm going to store that in a unique pointer and return that。

So it kind of just does it all in one for you here。 and that's why in the previous example。

ToWhere we had standard string。We just had Ho， like this。Which is also why it worked here。Originally。

嗯。Sorry， I keep using， keep using the brackets。Like a silly。嗯。Yeah， so that's why this worked here。

Like even though this is a string literal， which I think is why you could get confused with it because you're like。

 oh， it's already a constructed string technically， it's just a string literal。 It's like， no。

 it's actually saying I'm going give this information to standard strings。

 So so these two things here are virtually equivalent。 They might be literally equivalent。

 I think they're literally equivalent。 I can't see all the differences。

 They're equivalent in the sense that the outcomes the same。

 Like the right hand side of this producers is the same。

 make unique is just an abstraction that generates a unique pointer It means we don't have to put any new in our code anywhere because when you start putting new in your code。

 you can expose yourself to some。You're going to start making mistakes eventually， right。

 because programme like， you know， humans aren't that smart。

 Like that's kind of one of the basic things you need to get your head around with code， right。

 It's like humans will break things。So that was， that was answer to that。 Now。

 the second part of this smart pointers topic is share is Sha pointers。

 So you already talked about unique pointers。 Now， what was different with Share pointers well。



![](img/2234d19c866af44cea776f9097826c88_54.png)

Shared pointers。 Take ownership。Of a resource， of a heap resource。

 But what's unique about them is that they also share ownership。Of a heap of that he resource。

 And what that means is that there can be multiple shared pointers that are looking at a heap resource and keeping an eye on it。

 taking a responsibility for it to decide whether or not it should be。

Like what like to make sure it's deleted Okay， because that's the whole point the smart point is it's to take responsibility to take ownership of a heat resource to make sure there's no memory leaks。



![](img/2234d19c866af44cea776f9097826c88_56.png)

So Sha pointers， you can have several of them pointing to the same object。

And it's quite smart because what happens with a unique pointer。

 We saw this in one of the really early examples。 right， If you have a unique pointer 1。

And it points to a heat resource over here。And then we have unique pointer2。😊。

And it points to the same heapy sauce， which is a big， big bad。嗯。Then。Once either of these。

Goes out of scope because they are designed for unique ownership。

 and because they all take ownership， once this goes out of scope。

 it will free this and it will screw up the other one。

So what we want to do is we want to find a better solution。

 and that's kind of where shared pointers come in in this case where with a shared pointer。

 let's just call the shared pointer one。And shared pointeder to。Oops。Shared pointer2。

 and let's just have another Sha pointer called Share pointer 3。

Or three of these can point to the same heap resource。 They can all be owners of it。

 They can share that ownership between them。 And the way they work is that when shared pointers go out of scope。

They check if they're the only shared pointer pointing to that resource left。

 so when this shared pointer here goes out of scope。It goes， how many are left three， Okay。

 I'm not going to do anything。 And then when this shared pointer goes out of scope。

 it says how many of me are left2， okay I'm still not going to do anything And then when the final shared pointer goes out of scope。

 it says， oh， I'm the only one left who owns this pointer who's responsible for it。

 I'm going to free that on my way out。So Sha pointers are another way of handling pointer ownership。



![](img/2234d19c866af44cea776f9097826c88_58.png)

And， you know， there's a few key details here like the way Sha pointers workers with reference counters。

 It's a bit like what we had in the week three shoot where we we had a static member that was reference counting。

 how many instances it's kind of like that。 There's a reference that's shared between them basically。

 and as I said before， when a shared point when a shared pointer is destructed， it is only。

The if it is the only shared pointer left， then the object destroyed only in that case。

Does checking for other shared pointers cost much， I mean， it would cost something， but negligibly。

 you know， no， you wouldn't。 you wouldn't ever make a decision about not using a shared pointer for some。

Cost reason associated， I can't imagine you'd ever do that。嗯。

I feel like if you're getting to that level of optimization。

 you're basically you'd probably just be better off writing C code and trying to get that last little bit out of the system or writing C like C++ code。

Because remember the reason we teach you these C++ best practices is they're naturally going to be a little bit slower。

 right？Most like not all the time， but， you know， a standard vector is probably not going to be quicker than a working with a C style array。

 but。You know， does like a 10 times increase in the complexity and likelihood of error of your program。

 Is it worth like a。Oh， a trivial increase in the performance， like not really。 So again。

 that's why we we refer to C plus plus as a language of lightweight abstractions because abstractions are powerful for code readability and for reducing errors。

But we want them to be lightweight， so it's not like having to choose between really fast C and really easy to read Java and you don't get that balance between the two。

嗯。With shared pointers， we also have weak pointers。 Now， naturally。

 I don't think anything would stop you from using raw pointers with shared pointers for observers。

 But there's another type of smart pointer that's attached to a shared pointer called a weak pointer。

 And what a weak pointer is able to do is weak pointers are used with shared pointers。Such that。

When you want to point。Do something when you want to observe the thing that the SharePoint is apointing to。

 but you don't want to add to the reference count。Because every time you create a new shared pointer。

 you add to the reference count。The one benefit of weak pointers over like raw C pointers is that with weak pointers you can actually do a check。

 it's a tiny little operation to check if the underlying data is still valid so what that means just to kind of give you some some examples a video of me doing this in 2019 with real people is let's say you have a program like this where you have three shared pointers and say two weak pointers。



![](img/2234d19c866af44cea776f9097826c88_60.png)

Like this。They can all point to the same thing。But。Once the last shared point is deleted。

 it deletes the resource like normal， so the weak pointers don't reference count。

 that means that they're not like when when we say reference counting we're just talking about are they all keeping track of how many there are like those three shared pointers are aware how many of them there are they know know not literally but you know they're talking they get it weak pointers don't add to that count So like when this program starts。

 there are three owners， three shared owners of this resource。When I delete S1， there's now2。

 when I delete S2， there's now1， and when I delete S3， there's now 0。

 which is why it's deleted the resource。 Now， of course， you could have some C style pointers here。

That point to the heap as well。 But the benefit of weak pointers is they don't increase the reference count。

 of course。 but there's actually a function we'll see in a second that you can call to check if this heap resource has been freed on not。

 So you have a little bit of protection because that's one of the dangers of using like a C style observer pointer is that there's always a chance that。

Someone's freed it。You know， like all the share pointers are gone。

 and you've got this weak pointer that's kind of dangling by itself。



![](img/2234d19c866af44cea776f9097826c88_62.png)

Now a bit of an example of。She had pointers。We have here like。



![](img/2234d19c866af44cea776f9097826c88_64.png)

We have a main， I might open this up in the S code。Demo 5，5，5。Why is that one slightly different。

 Did I make a tweak to that， and I did make a tweak to that， and that's okay。make a note of that。嗯。

So now we've got this main function here and inside of that we're creating a shared pointer。

 I'm doing this with just slightly different function syntax like syntax again。

 so we're creating a new shared pointer called X， which simply manages a new end5 Now naturally again we could use standard make shared and we could construct it like this if we wanted to。

 which we should do in this case， but then what we do is we're going to create a second shared pointer called Y and Y we made by copy constructing with X。

 so a shared pointer unlike a unique pointer does have a copy constructor and the copy constructor of the shared pointer actually makes a lot of sense because if I have SP1。

😊，Pointing to the heap things。When I copy， construct it。It doesn't recreate the memory。

 it just points to the same thing。 So the semantic of copy construction here is not to copy the resource。

 It's to just copy what it points to。 That's how that one would be overloaded。



![](img/2234d19c866af44cea776f9097826c88_66.png)

Now， after I've created those two shared pointers on either of them here。嗯。I could。I，By the way。

 make shed should be like this。 That's my bad。嗯。I could print out the use count。

 So we talked about reference counting before。 So any shared pointer knows how many other shared pointers are sharing ownership with it。

 And let me just build this。 So demo 55，5。Use count too。 So it knows that there's two。Okay。

How does it know that there's two？That's an interesting question。嗯。

You might have some thoughts on it， but what's important in the understanding of this is that the reason it knows that it's too is because it was copy constructed。

 like it doesn't just scan all of the heap。And try and see if anyone else might be pointing there。

It knows it because we copy constructed it because when X was copy constructed here。

 the shared this shared， the new sharedd pointer and the old sharedd pointer had a moment to talk right。

 they had a moment where like the copy constructor was like， oh okay。

 y I can see that we're linked here。 The reason I point this out is because this isn't just some magic Like they figured that out through talking because check this out right if I do a similar thing up here。

Where I create a SharePoiner A。And a shed point of B。And let's just say for simplicity。

 I say auto i equals new int 5。And then I pass I into both of these like this。

So I create two shared pointers。A and B that point to the same thing。Watch what happens now。

Both of my shared pointers point to the same thing， but when I print out the ref。

What have I done wrong。Oh， they're going out of scope。Yeah， okay， well。

Let me let me put it in the release mode。It the the， the address sanitizers like。During destruction。

 the address sanits crapping its pants。So if we look at this for a， the use count is1。But for X。

 the use count is too， and the reason for this is because those Sha point is again。

 they they kind of link up during copy construction and copy assignment and all those other kinds of。

 you know。Core creation thing。 So this is actually another reason why we like using make shared instead of like the new thing。

 Because if you're using new， you actually have this capacity to separate it out。

 like without realizing you might do a silly thing and you might。You know。

 pull it out here and then try and create two shared pointers with the same thing and think， oh。

 they're all sharing。 That's really nice。 But it's kind of like you create a shared point at once that totally encapsulates the object。

 And then you're like copying or。You're essentially copying that shared pointer。

 And that's how they're all。That's how they're all linked up。

 So Nathaniel in the chat says you need to copy the shared pointer。

 you can't just initialize the pointer since otherwise the shared pointer doesn't know another shared pointer is also looking at it。

 Yes so that's exactly so there's no magic here that happens。

 they know what's happening because you copy constructed it So I'll do a similar thing here I'll say auto x equals make shared and then here I'll say auto Y equals X。

Clean up my code a little bit。Now they both own the memory which is great and then this should still work for us。

Can't write code， That's my problem， not yours。Reference counted2。Now。

 I remember the reason this was crashing before was because both shared pointers were pointing to the same thing。

 but they both had a reference counter1。 So then when my main function finished。

 it was popping these stack objects off and calling the D structure on the shared pointer。

 Both shared pointers thought they had to free the same resource。

 So that's why we got the address sanitizer getting really upset。Now。

 shared pointers can be dereferenced。 They can be reset， just like unique pointers。

 So the same kinds of things there。 And we can have a look at。The value。

 So let's try and run this and just look at a few of the results here。

So the use count here is two because we have two shared pointers looking at the heat resource。

 if I de referenceence x， it's the equivalent of de referencing what the shared pointers。Pointing to。

 so that's why I get five printed out。 when I do x dot reset。

 we saw that X dot reset essentially resets what it points to and because I give it no arguments。

 it resets it into nothing。So therefore one of the shared pointers no longer points to that resource。

 so therefore the reference count goes down， so that's why the use counter still is one now because x no longer kind of looks after it。

 but then if I was to reset X。Reset y as well， which is the last shared point at a point to it。

 It frees that underlying memory。 So the use count， the use count would then be 0。

 And if I tried to print something out there， I would get an error。

So you see what's actually really interesting here is that the two sharedd pointers are actually still valid。

Well， they're valid in the sense that they're both objects that exist and I can query them for the use count。

But at this point in the program， the heat memory has been freed。

So if I was to try and de referenceence why I'm probably gonna get a sanitizer thing because it's been。

Let me make it。The bug。Because it's been free at this point。Yeah， so similar thing。

 Se fault and unknown address 0，00 because the shared point is pointing to null pointer。

 And when I dereence the Sha pointer， it's going to try and dereference what it's pointing to。

 I get a null pointer here。Okay， I'm just having a quick look at this。

 So I'm probably moving a little bit too slow， though it's good to really go through this。



![](img/2234d19c866af44cea776f9097826c88_68.png)

A little bit of a demonstration about weak pointers， again， weak pointers。

 it's really hard to really convey the value of these in such small examples but。Essentially。

 where you get weak pointers from is you can you can I don't want to call it copy constructing。

 but you can construct a weak pointer by essentially constructing it with a shared pointer。

 So if we have a look at。

![](img/2234d19c866af44cea776f9097826c88_70.png)

![](img/2234d19c866af44cea776f9097826c88_71.png)

We have a look at piece of code here，5，5，6。I one's a little bit different too so I've changed this clearly if I have I've cleaned I cleaned up a few of these code styles this term to like make it look a bit more normal and I think I forgot to update the slides。

 but here I can actually construct a weak pointer with the shared pointer。 So then what happens is。

You don't need any make week or anything。 make week。 So now I have my shed pointer。

Which points to the heat resource。And now I have a weak pointer。But there's any one stack item。

Managing that resource， which is the shared point so the weak point is not adding to the reference count。

If I want to use the shared pointer， typically I might be able to do something like this where I say auto y equals WP dot lock。

 Now what does lock do What happens when I say weak pointer lock。 Well。

 let's go and check this out CPP reference。When I say weak pointer dot lock。

What Lock does is it creates a new shared pointer that also owns it。If there's no manage object。

Then the returned shape， the returned shared pointer is also empty。 So essentially。

 what this does is the weak point is pointing to the same thing as the shared pointer。

 And if the heap object still exists， it gives me a shared pointer to it。Otherwise。

 it gives me a null pointer。 So what that means is that while this weak pointer points to it。

 if I want to do something with this weak pointer， I can say， you know， dot lock。To give me this。

 And if this share pointer still exists， it'll give me a point to it。

 and I'll be another shared pointer。 And if it doesn't exist， this will just point to null。

The return return sorry I should say the return will just be null here。

 which is what we're really checking in this code we're essentially saying giveive me the weak pointer。

 try and get a lock on it。If it still exists， then give me a Sha pointer that I can work with so why here is a shared pointer？

But if it doesn't exist。You know， give me an old pointer so I know I can't work with it。

Now you might be asking why does it return a Sha pointer。

 well that actually makes a lot of sense because otherwise what would happen is if the weak pointer could just access this he thing。

 imagine in more complicated C++ code where it's like multi threadreading going on or some other kind of you know nonlinear code where you start accessing this via the observer。

But then the shed pointer goes out of scope say in another thread or something。

 and then suddenly the heat of resource is freed in the middle of you using it。Not very good。

 So what we actually do is we we if we want to use a weak pointer， which is just like an observer。

 we create another shared pointer so that if this first one over here goes out of scope。

 this piece of memory will stay in scope。😊，Until we're finished using it。

 And then once this goes out of scope， it's all over with。 So it's。

 it's a really good way to kind of deal with more distributed situations。

 which I know this code example here is a bit more long。 But I think it gets a bit too confusing。

 I think that's why I simplified it。

![](img/2234d19c866af44cea776f9097826c88_73.png)

But this leads to a really important question， which is。Which no one's asked yet。

 but normally we get it all the time and you're probably thinking about it， which is like。

 when do I use unique pointers and when do I use sharedd pointers because they're kind of the two big things and。

Shared pointers can get really complicated。 They can make code complicated。 They can do all of that。

 So the rule that we encourage you to follow is that you pretty much always want to use unique pointers。

 pretty much always。The only times you want to use Sha pointers。Or if an object has multiple owners。

And you don't know which one will stay around the longest。

 you don't know which one's going to own it the longest。嗯。Or you need temporary ownership。 But。

 but like generally speaking， this is interesting because like。In， in a lot of programs。

 you might have quite a few pointers pointing to the same thing。 You know。

 like some obvious funds might be。

![](img/2234d19c866af44cea776f9097826c88_75.png)

Here's one， you know， you have a tree。Like a binary tree。Yeah。

 but like a double binary tree where all the children also point back to the parent。

So you've got pointers in both directions。So in this case。

 you have an interesting scenario where this resource here。Is pointed to by two children。 Now。

 this may maybe not the best example， explicitly because， you know， if you get rid of two children。

 you don't want the parent to be deleted， but just bear with me for a second。 I have other examples。

 but I don't want to go through them。You know， you have two things pointing to it。

 and it's like you have to ask yourself the question。

 is it noble in my code which one will live around the longest。And if the answer is yes。



![](img/2234d19c866af44cea776f9097826c88_77.png)

Then you go for it because the common mistake I think a lot of people make is they say。

 do I need many things pointing to the same resource and they go yes。

 it's a shared pointer then because they are all going to share pointing to it。

 but you're not trying to share the pointing。 You're trying to share the ownership。

Becauseuse you can share pointing with a unique pointer at a bunch of raw pointers and stuff。

 but you're trying to share the ownership So the only time ownership sharing matters is if you don't know who's going to go out of scope first now why would you not know who's going to go out of scope well again this will depend a little bit on implementation details but generally probably two of the most common things I can think about any programs where the order of freeing particular resources depends on user input or some kind of thing unknown at compile time or again concurrency situations where you actually don't know which order that threads will operate on shared memory so if you have three separate threads running or trying to share a resource that's a heat resource that's a good example of why you might use a shared pointer or something like that。

嗯。Examples of smart pointing usage is honestly pretty much anything that is a point to like structure。

 which are many data structures in programming。And then this is just a little bit of a， I guess。

 a helpful diagram here that's like saying that。

![](img/2234d19c866af44cea776f9097826c88_79.png)

While we do talk about all these resources and Sha pointers。

 pretty much all the time you really want to always be using like stack objects to do things。

You know， so。Like even though we talk about new and delete。

You would much prefer to put things on the stack and not use pointers in any way。However。

If you really need heat resources， then you go to make unique and unique pointer。

That'll get you through a lot of the rest of that。 and then if for some reason。

You're dealing with a situation where you need heat resources where you dont with multiple things pointing to it and you don't know which owners are going to live。

You don't know who can own it because you don't know which ones is going to live the longest。

 then that's where you get into the the shared pointer stuff Diammd says the shared pointers have built in concurrency control。

 I don't know。 I'm probably oversimpling concurrency a little bit I've done a lot of concurrency with C+ plus explicitly most things over written C+ plus on a single threaded。

 so。I mean， to be honest with you， there's just very little。

 very little common use for Shad pointers， though I know Nathaniel's floating around in the chat。

 he's written substantially more than me。 So he'll probably have a。Comment to make on that No， no。



![](img/2234d19c866af44cea776f9097826c88_81.png)

Don't have to， of course。The last topic before the end of the lecture。嗯。Is yeah， I mean。

 just to be clear， it's not some magic solution to concurrency， I wasn't trying to imply like。

 oh yeah， just like this solves all the concurrency problems。

 It's more just like there are there are lots of random situations where you just don't know which of many pointers will go out of scope last。

And， you know， we， we looked at。Like there's some few examples here。

 a Doubly link list might be another example， but。Quite often。

 you don't really share ownership ship to different。Yeah。

 it's it's hard to say without going into more detail。

 but that's what assignment3 is like like this is the kind of stuff that really starts to make sense when you deal with bigger files and I do think we have some some cute questions on it as well in the coming weeks。

😊，But one of the most important things about why smartPoers Matt is to do a stack unwinding。

Stack on Mins a topic in the week five C， and I talk about it pretty extensively in my tu。

 which I'm uploading tonight。So I probably won't go through a ton now because you'll either get it covered in the ch or you can go watch my tu。

 but essentially pretty straightforward concept， you have a main function。

You use new to create some heat memory。Then you call something that happens to throw。

 so you call something that does not have a no throw guarantee。

So it throws and then it immediately kind of stack on wines and pops stack frames off。

 and this delete pointer line is never executed。It's because you've been managing that。

Hate race yourself。That's all very good。嗯。So make sense how we would solve that。😡，We would。I mean。

 I don't really know。This doesn't even make sense。It's not safe， and it's not smart。

 But so we we understand now that， you know， the whole point of the smart pointer topic in the tail end of yesterday was when we actually create a heat resource。

 let's do it with a make unique or unique pointer so that this stack object pointer， which is just a。

Jesus Christ。This stack object pointer essentially just is a unique pointer。And therefore。

 if an exceptions thrown， as part of stack unwinding as it's popping off stack frames。

 it will free all the local variables。 What happens when you free a local object。

 It calls the destruct on it。 The destructor make unique， freeze the underlying pointer。

 So one of the biggest benefits of unique pointers isn't just like， oh。

 now you don't need to remember to free it。 It's actually that。😊。

During stack unwinding for an uncot exception， which is totally possible。The resource will free it。

 the resource will be freed for you by that smart pointer。

So don't just think I know how to put deletes everywhere so I'm going to write code myself。

 it's like it's really hard to write code because otherwise you have to basically put tries and catches everywhere with deletes everywhere and your code gets really complicated really quickly。

We talked about exceptions last week， we talked about a couple of these things。

Such as like during exception stack on winding， if an exception is not caught and it makes it all the way to the top standard terminates called Another important thing about C plus plus is that。

If there's an exception that's thrown in a Dstruct。Then the entire program terminates。

That's just like a rule of the language。Like if there's an uncot exception in a destructor。

 something's gone terribly wrong。 So you know， standard terminates called and the program terminates。

So。对对对。Blah， blah， Let's look at some card。Now this is the last thing we have to talk through today。

 which is this concept of partial construction。And it's really asking the question。

 what happens if an exception is thrown halfway through a constructor。 And again。

 this is just a demonstration of why we。Why we want to use smart pointers even inside libraries themselves。

 Like don't think it's just， oh yeah， this is， you know， if I'm writing a library。

 I can go all low level on stuff。 But have a look at this piece of code here。

 we've got we've got a class called unsafe class。 It takes in two ins。

It takes in copies of those two ins and it essentially creates new heap objects for those two ins so now we have two new ins in the heap and our class is made up of two pointers to those two new ins and when this class is destructed。

 we call deletete on those two heap resources Now this seems to make sense right this seems to be consistent with what we learned yesterday about like your classes need to free the things that they create。

Sure makes sense and then we've got this class Mayant up the top here which is what we're actually creating so sorry before when I said oh our class stores two pointers to ints。

 it's actually storing two pointers to another type which is a Mayant and a Mayant simply stores that int it's kind of a benign abstraction it's a bit of a stupid class but what happens is if you try and construct a Mayant with the value2。

The class is an exception。And stack on windining begins。

 And what we do what this program tries to do is it tries to just create an unsafe class with pass in1 and 2。

 So we call unsafe class with one and2 calls this constructor。

 We construct two new heap objects of type might。So that calls the constructor for my end once and then twice。

 and then the stored there and then the deleted once unsafe class goes out of scope。

 So if the exceptions not thrown， this follows the standard like RAII principle of like， you know。

 we try and manage our resources effectively。 Now， the C plus plus standard says that an object that is partially constructed or partially destroyed will have its destructed。

 executed for all of its fully constructed subobject。Bit of a mouthful。

What this means is a destructor is not called for an object that was partially constructed。

Except for an exception thrownr in a constructor that delegates。 Don't worry about that last line。

 so。What this means is that if during construction， an exception is thrown that is not caught。

The program will not call its destruct。So a partially constructed object。

That has an exception throne。Does not call its destructor。But it does try and destruct the。

The the members。So think about how this program runs for a sec， we call ina class with one and two。

The one into a post in here， we create a new heap object。

By calling Mayant with one Mayant is successfully constructed， storing an int。

 So a benign abstraction for an int is created。 So we've created a new heap object。

 Then we call new Mayantt。With2。This comes up here。

 it tries to construct a Mayian an exception thrown because the number was two。

 and that's what made it throw an exception。So now at this point。

This object doesn't complete construction because an exception was thrown。

 So it bubbles up to this constructor。 Now， this constructor。

Is not doing any kind of exception catching。Nor even can it inside the I don't even think it can inside of the uniform initializer。

So this， this class is basically a partially constructed class now， so objects， sorry。

 so during the stack onwinding。It's like， oh， man， we partially constructed this class and there's been errors thrown。

 it's going to hell， let's just destruct it and keep popping off the stack。 But here's the problem。

 The partial construction rules save an object's partially constructed。

It'll call the destructors on its members， but only the fully constructed ones and not on the destructor。

 So this delete never gets called here。 and it simply calls the in this case， it will just call the。

It will just call the D structure on the A name。But we know what happens when you call a destructor and a pointer。

 nothing， nothing at all， because it's just a pointer， like there's nothing to do。😊。

So we have a memory leak。Myant A was a piece of heat memory created that was never called in the destructor because it was a partial construction and freeing the data member that points to it useless because of the rules of C++。

So what we need like where we can use smart pointers instead to really make things easier is it's the same piece of code here。

 but we've replaced the new with make unique。嗯。And we don't have a destructor anymore。

 and we've replaced the private members here with we've replaced the raw pointers with unique pointer Pin says。

 so a underscore doesn't count as completely constructed。 No， it is completely constructive。

 But the point is that there's a difference between deleting a which is saying remove from the heap。

 what a points to。 That's what delete a says and destructing a。

 which is just saying destruct a pointer。You' like there's a difference between saying delete a pointer and delete what it points to in the heap。

So our point is that this destruct is never called， so therefore。

We never actually free what's in the heap。 but calling the actual destructor on a itself is like。

 you know， somewhat pointless。 So again， to recap， the unsafe class destruct is never called。

But there is a destructor called on both of these little subtypes here because remember most of your program is just like a tree of types。

 right， like this this objects made up of these objects， which are made up of these objects。

 So it's kind of like it calls the children， but not the node itself。

 if you want to think about it like that。 But if we use a make unique in a unique pointer here。

 we can actually get around these partial construction issues。

Because what happens is when we construct A an A underscore with a unique pointer。

And then we try and construct a B。Even though this construction fails。

 what do we know happens during partial construction。

A D structureor is not called on the class that failed to construct。

 but the destructor is called on all fully constructed subob。 Now。

 of the two data members of safe class， which ones are fully constructed will B is not fully constructed because it's the one that failed to construct。

 it's the one that through the exception， but a is fully constructed。

 So we call the Dstructor on a underscore。And what's the destructive of a unique pointer do。

 It frees the underlying resource。 So even if you think， I don't really need， you know。

 smart pointers because I won't make mistakes。This is somewhat of a challenging problem to solve without them。

So this is actually a great example of why we like to use smart pointers because this essentially totally prevents our code from having partial construction memory leaks。

Now that's actually all I have today， I mean it's nearly the end anyway。

 but are there any kind of lingering questions people have that we can talk to in the meantime otherwise feel free to fill out the survey。

Give some feedback。Jin says， how do people solve this in C？嗯。There's no objects in C， so， I mean。

 C is a very simple language where not a lot's done for you。A。So I mean。

 the short answer I our yes your immediate question is like how does someone solve a partial construction problem in C。

 there's no classes in C。😊，Therefore， there's no objects in C。

 Therefore you're not having to deal with construction rules and stuff because everything's basically just struck and variables and stuff。

 so。嗯。But that means you' got write a lot more code。Pson says does C have exception handling。 No。

 it doesn't。 C doesn't have exception handling。 That's kind of why some people consider it good。

 because。One of the things about C。Is that one of the things about exceptions is that they sometimes put a glove on。

 I'm sorry it's be weird。 I'm just called。 one of the things about C is that it。Sorry。

 one of the things about exceptions is that they break a linear analysis of code。

 so the beauty of code like C without exceptions。Is that you can effectively follow the entire piece of code。

 like with a pen and it just kind of goes in here and loops there and branches here and goes into this function here。

And it follows essentially a very linear flow， you know you could follow like a tree and backtracking。

 unwinding whatever， but exceptions are essentially like you know they stop lines of code being executed and they do some other things So exceptions are really a program as friends。

 a friend I don't think that I don't think they're particularly good or bad。

 I think they make programming easier but you can imagine if you're trying to rely write a system that you need to verify works。

 they can definitely exceptions can definitely add complexity to like aly program flow。

 though I'm not in any way an expert on this and if you go do any kind of course that's in the you know the formal methods。

Operating systems。Space， you'll probably get a lot better answers about that。

 I'm sure if you ask some of those people， do you wish they had exceptions， I mean。

 maybe they'd say yes， I mean， I like exceptions， but I have a feeling they'd say no。

 and they'd probably give you some answer like that。King says Kongang says。

 can you repeat on how we reference and de reference unique pointers， I think。Thank you。

 I bought these in Amsterdam， for $5。They're a bit broken there。嗯。Sorry， mental blank。

 can you repeat on how we reference and de reference unique pointers。

 I'm not really sure what you mean。 I mean， you de reference unique pointers just by。

Doing this like you just do， this is， this is us。 Oh， that's a， yeah， yeah。

 that's us D referencing a unique pointer right there。K a question。

 if you do U P1 equal standard min unique。And do it again。 U P1 equals standard me unique。

 You get a memory leak。 No，ca well， I mean， I don't really understand the code you got there because I don't think it compiles。

 but。

![](img/2234d19c866af44cea776f9097826c88_83.png)

嗯。But just to kind of look at it for a sec。There。I mean， this doesn't make sense per se， because。

I mean， you're trying to create make。Ap point to a string that you're passing， oh。

 maybe sorry the string's taken。Oh， sorry， do， no， no， I understand。

 Standard strings take in numbers。 Do they， Do they have a constructor that I'm forgetting。



![](img/2234d19c866af44cea776f9097826c88_85.png)

They probably have a constructor that does something。There's a constructor for everything。



![](img/2234d19c866af44cea776f9097826c88_87.png)

嗯。Size type count。 Okay， there we go。嗯。Your question。 Oh， sure， yes。 Okay。

 I understand your question。 Thank you。 I understand。Is this a memory leak Yeah， it should be。

 This will be a memory leak， I believe。Now， maybe it doesn't work anyway。 It doesn't matter。

 Let's just change this term。It's raining again， yay。Oh， they're sorry。You're not code。Yes。

 this should be a memory late。Rrong code。Nope， no it's not。 Why is that。No， no。

 I think I think I was just making this up， by the way， I wasn't too sure。I'm guessing。

 assignment must free。Maybe assignment， some I don know。 I。

 I don't keep the same file on the top of my head。Normally， I just Google this， but。Yes， that's it。

 That makes sense。 So that's a very interesting behaviour。 So assignment itself calls reset。

 which actually frees the memory。 So if you were to kind of dig around unique pointer。

 right on CPP reference， you would see that we have。😊。



![](img/2234d19c866af44cea776f9097826c88_89.png)

Operator Wait， is this unique pointer operator equals assign the unique pointer。



![](img/2234d19c866af44cea776f9097826c88_91.png)

Converting assignment operator， I guess this would be it。They'd be see， okay，3。

 effectively the same as calling reset。 Y， so there it is。 It's written in the library。

So the point is that this sign here is equivalent to UP1 dot reset。Do you reset it with。



![](img/2234d19c866af44cea776f9097826c88_93.png)

Oh yeah。 withstand making it。 Yes， it's the equivalent。 Gota damn it。

It's the equivalent of doing that。Those two things are the same。嗯。

F so the destruct is called on the equals overload。I don't want to say the destruct is called。

 I would say that it's effectively the equivalent of reset and reset's job is to delete the heat resource。

 The destructor wouldn't be called because the actual named stack object U P1 is not going out of scope。

It's still in scope。 It's been in scope this whole time。

 The destruct is called when it goes out of scope， It's just resetting it。

 But I know you probably mean by by that， you probably meant， is it。Just deleting the heap object。

Kang says when I try and do star magnitude underscore。

 I would get this error message indirect requires pointer upper end。I post on the forum for that one。

 I'm sorry I just。Don't want to。 nothing jumps out of me immediately。

 And I'd probably just want to see a bit more context。 Kai says so reset calls delete explicitly。

 Yes， because reset frees the the resource it points to currently。 So it has to call delete。Allright。

 well， let's call it there。Let's wrap it up。There are still help sessions in week six。

 you st your shoots this week。嗯。Everything else。I guess I'll talk to you on Monday， week 7。嗯。

5 sensors， well we have an assignment which would require Sha pointers。

 There's an assignment you might be able to use Sha pointers in。 Def。 But yes， thank you everyone。

 please give feedback as always。 if youve got your phone just be like bam bam， I'm done。

 if you're on your phone。 Well， congrats your agenda。 I guess watching lectures on your phone。

 but yeah， have a great night。 and I'll send you notice on Friday。

 hopefully with more information about your assignment one marks and good luck with all assignment two stuff。

😊，And I'll talk to you in two weeks and enjoy your flex week in lockdown if you're in Sydney。



![](img/2234d19c866af44cea776f9097826c88_95.png)

Okay， thanks everyone。