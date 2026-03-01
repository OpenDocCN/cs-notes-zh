# 密歇根大学《数据结构和算法｜eecs281 Data Structures and Algorithms Winter 2021》中英字幕 - P12：-13-EECS 281_ W21 Lecture 13 - Strings and Sequences.zh_en - GPT中英字幕课程资源 - BV1snk5BWEfc

Yes。嗯。I'm going to give it just a few more minutes to let people drift in。

 I know we're not starting on Michigan time anymore。

But I'll still sort of be cognizant of the fact that we have a few minutes and this lecture I don't think is going to fill the whole time。

One quick question， can everyone hear me it looks like that's happening？Based on the settings。

 but I wanted to check。Awesome。😊，Thank you so much。Okay。Thank you。Yes。Okay。Okay。

 I'm going to go ahead and get started。My name is Brian Noble。

 I'm a professor of computer science and engineering。

 I introduced myself really briefly at the beginning of class on the first day but。

Before we dive into the topic of today of strings and sequences and a few interesting algorithms on them。

 I want to just take a few moments to introduce myself。Um。So I grew up， so here's Ann Arbor。

 we're here。 I grew up in a little town called Liberty Township。

 which is about 40 minutes west and a little bit south of here， and I lived there until I was 16。



![](img/56a6f95de5e72dd835005dc9960b8379_1.png)

Then when I was 16， my family moved。To Palo Alto， California。



![](img/56a6f95de5e72dd835005dc9960b8379_3.png)

And I at the time， I sort of had a good idea that this computer thing was kind of interesting to me。

 but I had no idea what Palo Alto was and what that meant I just sort of was knew I was moving to California。



![](img/56a6f95de5e72dd835005dc9960b8379_5.png)

![](img/56a6f95de5e72dd835005dc9960b8379_6.png)

嗯。When I graduated from high school， my parents moved back。

And I was choosing between two undergraduate schools。

 the University of Michigan and the University of California at Berkeley。

 I arguably chose poorly and ended up going to UC Berkeley。

 where I graduated with a degree in E engineering and Comp science with a computer science focus。

 then I overshot Ann Arbor and ended up in Pittsburgh at Carnegie Mellon where I did my master's in my doctorate degrees I finished my doctorate in 1998 and then joined the University of Michigan shortly thereafter。

 so in the fall of 1998 I started at the University of Michigan and I've been here continuously since then。



![](img/56a6f95de5e72dd835005dc9960b8379_8.png)

![](img/56a6f95de5e72dd835005dc9960b8379_9.png)

![](img/56a6f95de5e72dd835005dc9960b8379_10.png)

![](img/56a6f95de5e72dd835005dc9960b8379_11.png)

![](img/56a6f95de5e72dd835005dc9960b8379_12.png)

![](img/56a6f95de5e72dd835005dc9960b8379_13.png)

嗯。

![](img/56a6f95de5e72dd835005dc9960b8379_15.png)

However， this is the first lecture I have given in approximately eight and a half years because I spent some time in addition to taking a sabbatical。

 I spent some time as an associate dean and then a little bit of time as a department chair during which time I wasn't teaching and so not only have I never taught online in remotely so this is the first time I've ever used a broadcast platform。

 I haven't been in the classroom for a while so I hope you'll bear with me while I make some inevitable mistakes。



![](img/56a6f95de5e72dd835005dc9960b8379_17.png)

![](img/56a6f95de5e72dd835005dc9960b8379_18.png)

![](img/56a6f95de5e72dd835005dc9960b8379_19.png)

![](img/56a6f95de5e72dd835005dc9960b8379_20.png)

Today's topic is strings and sequences。which is a little bit of a standalone topic。

 so we're talking about it right before the midterm to forestall the inevitable questions， yes。

 this material might find its way into the midterm。

 but probably not a lot of it so you should know it and you should pay attention to it。

 but you can expect that it's a relatively small fraction of what you might see on the exam。

 but it is fair game the things that we talk about today。



![](img/56a6f95de5e72dd835005dc9960b8379_22.png)

![](img/56a6f95de5e72dd835005dc9960b8379_23.png)

![](img/56a6f95de5e72dd835005dc9960b8379_24.png)

The lecture is broken into three sections， the first two will be algorithms that I think we've seen before。

 although we may not always remember them， but we've seen them and may become familiar as we talk about them。

 the third segment today is going to be something that probably will be new to most of you。

 but I think is a really interesting way of searching for strings。



![](img/56a6f95de5e72dd835005dc9960b8379_26.png)

![](img/56a6f95de5e72dd835005dc9960b8379_27.png)

![](img/56a6f95de5e72dd835005dc9960b8379_28.png)

![](img/56a6f95de5e72dd835005dc9960b8379_29.png)

So the first question that's worth asking is why are we thinking about these questions so first I want to sort of formally define what I mean by a string。

 a string is a sequence of zero or more characters where each character is taken from some finite alphabet。

So for example， sentences in English are strings because they're taken from the 26 letter alphabet capitals uppercase。

 lowercase， plus a defined set of punctuation terms and spaces。

Then we talk algorithms on these structures or these sequences of zero or more characters drawn from a finite set。

 we refer to as array algorithms or more commonly sequence algorithms。

Sequence algorithms on their face aren't very complicated in part because the data structure isn't very complicated。

 but some of them can be very subtle， so even though it may look easy the first time we see them。

 we may sometimes need to be able to appreciate some of the details。

What makes them interesting or special and why would we think about them what they're really， really。

 really common and lots and lots of compute power across the world is devoted to solving problems on these topics。

Anything having to do with human readable text is at its core a sequence algorithm。

If we're categorizing things， naming things， labeling things， so for example。

 one of the areas that I do work in is autonomous vehicles and automotive telematics。

 so being able to label objects in the vision field of the car's cameras， that's a car。

 that's a pedestrian， that's a bicycle， that's a traffic light， those kinds of things， those labels。

 the actual management of those labels， not the vision parts。

 but the management of the text is a sequence algorithm。And then of course。

 something that's been in the news a whole lot lately is DNA analysis and sequencing。

 so the way we've been able to track mutations in coronavirus as fast as we have been is in large part because of sequence algorithms running on DNA。

 which is just another kind of a string。One of the things we won't be talking about is sequences of arbitrary objects where they aren't just drawn from a set of finite from a finite alphabet that we can more or less easily enumerate。

 and we also won't think about sequences of doubles because doubles are at least even though they are finite because they're represented by bits。

 they are in practice in they are in principle infinite。

 so we aren't talking about those kinds of structures when we talk about this today。😡，U。

Typical questions we'll ask sort of the elementary building block questions as we're thinking about strings and sequences。

 are two sequences equal？Given two sequences and a notion of order on that family of sequences or that universe of sequences。

 which one would go before the other in a dictionary， we sometimes call that lexxiographic order。

Or dictionary order。Do they have subcompons in common or substrs that's really common in DNA analysis。

 which does the sequence of DNA that encodes the protein spike on the coronavirus。

 is that sequence the same or does it differ and if it differs， how does that matter？嗯。

So we might find where they have things in common or we might look for differences。

 so if we're looking for important differences in the coronavirus。

 we might look for differences specifically in the gene that encodes for the protein spike。

Given a collection of strings， we might sort them， provide them in lexiographic or dictionary order。

 and of course one of the things we've learned so far in some of our earlier work is that when we have data elements ordered in some way。

 searching them is easier because we can use binary search and divide and conquer rather than rely on linear search。

嗯。So when we talk about strings， we also will sometimes talk about texts。

 a text is a collection of one or more discrete strings， and so given some string P。

 something we're looking for in some larger string S a text or a collection of those strings。

How do we find the instances of P within S and we might be interested in just the first instance。

 we might be interested in the last instance， we might be interested in the next one or all of them。

 we might be interested in approximation， so the example in this slide we have regular expression。

 but we also have rex or rex P so different ways of talking about the same idea and we might have notions of how to approximately match things based on the contents of the words。

U。We also might preprocess the texts S before we know what P is going to be to optimize the search time for many independent queries and that's how things like Google work。

 so Google doesn't just store the data items of a web page it actually stores a preprocessed version of those to make queries of keywords on those web pages faster。

We will sometimes talk about a text， a text is a string with a particular denoted separator character of family of separator characters。

 which delimit words in our corpus， so for example in English text。

 we might think of the separator characters being white space characters， space， tab new line。

 and punctua and some of the punctuation characters， period comma， semico exclamation point。

And so given a word or a phrase， we might look for instances of that word in text。

 these are all really common examples of problems we might be solving。I used the word earlier corpus。

 a little earlier， a text corpus is a collection of documents each containing a text。

 a sequence of these sequences， it might have other things。

 it might have titles and other attributes， the URL。

 some other things that are interesting that talk about that describe the overall text and the text corpus so if you have a very large text corpus。

 say all of the patents that have ever been patented in the United States and we're looking for things that might talk about this new invention that we've just come up with of a new way say a new vaccine。

 we might want to search all of the patent literature for things that might be relevant to the vaccine to make sure that what we've invented is actually something new so given a search strain consisting of one or more words。

 find all of the documents that contain those words and again we might not just be interested in exact matches。

 sometimes we are so if I'm looking for all of the people who have。

Particular last four digits of their US Social Security number。

 that's something I really want an exact match for。

 but sometimes I also want approximateimate matches。

Where where I have an idea and I want things that are related to that idea or I maybe capture common misspellings or stems of the word。

 like we looked at the regular expression example in the past slide。

There is an absolutely huge industry built on this and it's not just Google and Bing and other common search engines。

 so there's a company in Arbor called ProQuest that one of they sell lots of products like this with search tools over interesting corpusees and one of the things they sell is a tool to search patent literature。

 I was an MDVP mentor last year with a team that was working on an improvement to their patent literature search mechanism and there's a lot of money in being able to find the right information quickly。

Another example that could be thought of as a sequence algorithm is given all of the Project one submissions。

 how to find pairs of similar programs， it turns out that that's more of a graph problem。

In addition to being a sequence problem and we'll talk about that more when we talk about graph later in the class。

 another really common example is text compression。

 so find repeated words or repeated phrases or repeated sequences of characters and replace them with much smaller numbers so that we have a much more concrete representation and when you download the starter files for the projects they have that dot GZ suffix that's called GZ that's a very common compression algorithm that's used to compress the text that is most of those documents down into something much smaller and make it easier to transmit。

And I also alluded to this example earlier and this has been in the news a whole lot lately and as someone who is anxiously awaiting his opportunity for a vaccine。

 I'm really grateful for this one， DNA and genomic sequences， DNA structure very simple。

 the alphabet has four letters total A， C， G and T。

Then there are pairs of those letters and sequences of those pairs of letters form genes or genomes。

 so entire the entirety of life on planet Earth is described by the sequences of pairs of these four letters in different orders and in different combinations in different ways of making them。

In people there there are 23 identifiable chromosomes with pairs if you get half from one parent。

 half from the other， that those 23 chrom chrom paired chromosomes comprise 3 billion of these base pairs of these pairs of。

Drawn from this four character set and a particular gene is a particular sub sequenceequence of one of these DNA strands and some genes we've identified genes that may identify I think we know which genes code for eye color for example。

 and there might be a few others that we think of those that。Think of like that。

My mother in lawaw had early onset dementia， there's also a genetic test that identifies for propensity to that。

 so there are lots of important string algorithms for comparing chromosomes， looking up genes。

 assembling long DNA strands from short sequences and the mRNA vaccines use a lot of techniques that are based in these underlying tools。

The two most common data structures you'll encounter for strings and string related activity in our everyday lives in 281 are individual strings。

 see the nut terminated strings that we've seen in C。

 and the more object oriented more functional strings that we've seen in C++。

And we can think about their overheads for C strings， it's just a pointer to the start of the string。

 and then the null character， so we have a sequence， this is our string。

 there's a null character at the end， and then there's a pointer to the beginning of them。

For a C++ string。I'll do this one in blue is。Two pointers， one to the beginning。

And one to the current end of the string and maybe some more that describes how long this buffer is and maybe how big the size is and a few other details that we may keep track of as we。

Oops sorry。As we are looking at strings， so for example， to compute the size of a C++ string。

 we need to count all of the characters because there's no place to store the size to compute the size of a C++ string。

 we can do that in constant time， we can either subtract the two pointers to get the number of characters between them or we might even store the size separately as another data structure or as another data element。

嗯。The operations possible， we can perform direct pointer in arithmetic on C strings。

 we tend not to use direct pointer arithmetic， we tend to use iterators and said on C++ strings。

 the standard C library options for anything with a C string。

 a much richer variant of library functions in the C++ standard library。

 the standard template library， the standard algorithms。

 and there are a bunch of things and we'll see some examples of that as we go through today's lecture。

嗯。Sequences as I mentioned before， C++ strings support begin and end iterators and we normally will use those and just as a reminder the begin iterator is the first valid character of the string。

 the end iterator is the first position after the end of the string so it's sort of like where the hypothetical next character would go and one of the things we'll see later on in today's lecture there are also reverse versions of those iterators and we'll talk about those in a bit。

We may also have specialized containers to hold multiple strings。

 so a dictionary might allow us to add words， remove words， look words up。

 we might also have a data structure that supports a very efficient representation of strings with common prefixes。

 so all of the words that start with an might be stored together reusing those that stored for an and so on and so forth。

There's also an STL algorithm that will tell us whether two sequences are equal。

It takes as an argument。嗯。It it's templated over two different iterator types and they have to be input iterators and input iterators are a defined notion。

 they allow increment， they allow you to read the data。

 but you can't perform point arithmetic on them and you can't write data to them or at least you may not be able to。

 but this allows you to have iterators over different kinds of structure。

 so the input iterator one could be over a vector while the input iterator2 could be over a deck or any other structure that supports an input iterator。

Then it defines two ranges， the source range is started by the input， the input。

 the first iterator input one。And the last iterator off the end of the range of interest。

And the second iterator is just the pointer to the beginning of an iter of a range。

 it is required as part of this method and assumed that the range that's pointed to by first two。

 the second this iterator that I've written on the bottom in red here。

 it is assumed that whatever range that iterator points to is at least as long as the range described by the first two iterators。

 so that's just a requirement of using this function。

UmSo the idea behind equal is that it's going to return true if the range from first one inclusive to last one exclusive。

Like we normally do with iterators and STL is equal to the range。Of an equivalent length。

In the second。Sequence so as long if these if this sequence of characters is identical to this sequence of characters。

 standard equal will return true， if it's not equal。

 it will return false and the way to think about this is standard equal will look at each one of these one by one if they're equal it'll keep going if they're not equal it returns false if I get to the end I'm done。

And that's exactly how it's implemented so we don't need any initialization because everything we need has been passed for us。

 we have first one， we have first and last one which describe the range of that's the source range or the first range。

 we have the point at the beginning of the second range and。While we have it。

I can't use my finger to do this while we haven't ended， so while first。

Remember first starts out here， last starts out at the end。When they're equal。

We've looked at all of the characters in this range。

 so as long as we haven't looked in all of the characters in this range， well。

 we compare the characters they're currently pointppointing to if they're not equal。

 we return false because the entire sequence isn't equal， if they are。

 then we'll increment each one of them and keep going and if we make it all the way to the end of this sequence。

 then we return true as the overall result of the function。

So here's a pretty interesting example of how to use that and this is a palindrome。

A palindrome is a sequence that reads exactly the same forward as it does backward。

So in our example at the bottom radar， RADAR going forward is the same as RADAR going backward。

 but hello H ELLO going forward is not the same as OLLEH going backward。

One of the things to think about is that sequences of length zero or1 are automatically palindromes。

 the letter A is a palindrome， whether you read it A forward or a backward。

So that means we have a very simple sequence， so we have a string。And this is a C++ string。

And then we say。If going to we're going to divide the sequence into two。

And this may be odd if it's odd， it's going to ignore the first character because this is integer division by  two。

嗯。So we're going to have one set of iterators。That goes forward。And then。

The iterator2 we're using is a reverse iterator。So this reverse iterator is going to point to the last legal character within the sequence。

 and when we apply the increment operator to a reverse iterator，It goes backward。

So what this will do is it will compare。These characters in that order。

With these characters in the forward order， and if they're the same until we get to the middle it'll return true。

 otherwise it'll return false， and here's a little driver that makes it a little easier to read and prints a convenient message for us and if we passed radar to this it would say radar is a palindrome and if we passed hello。

 it would say hello is not a palindrome。Okay， that's the first the first segment。

 I don't see any questions that either means that none of you think this is。

All that interesting or that I've been clear so far and knowing myself I'm usually not that clear。

 so I'm encouraged。I'm interested if in case anyone has any questions， I'll wait a second。

 maybe refill my water and see if anything pops up and if not we'll move on to the second topic in the class today。

Okay。Like I said， this is the first time I've ever done this。

 and it's a very weird to sound like I'm speaking into the void。

 so hopefully this is coming across and if not， I guess I'll find out later from the Piazza posts。

Why don't we check the length of the second string。

 you could check the length of the second string and。

That would be in some senses be safer one of the principles of the design of the language C。

 which C++ inherited and was also inherited by the STL is that。



![](img/56a6f95de5e72dd835005dc9960b8379_31.png)

You can either spend the time to check that what the programmer is doing when they call these functions was correct。

 or you can tell the programmer this is the way you correctly use this function。

 it's up to you to do that correctly。

![](img/56a6f95de5e72dd835005dc9960b8379_33.png)

Now the advantage of the second one is pretty clear。

 the advantage of the second one is that it's a little safer to use and it's safe against program or error。



![](img/56a6f95de5e72dd835005dc9960b8379_35.png)

but it comes at a performance cost， so if you're going to commit to checking the length of the second range every time you call equal。

 that means you first check the link， you have to check that that comparison， which you can do。😡。



![](img/56a6f95de5e72dd835005dc9960b8379_37.png)

Potentially in constant time。But that。But that you also have。

But it's also a check you have to make the STL is committed to performance。

 so when the STL has an opportunity to decide between telling the programmer to do something correctly and spending time in case the programmer did something incorrectly。

 the STL usually will commit to the former it usually err onto the side of performance。



![](img/56a6f95de5e72dd835005dc9960b8379_39.png)

![](img/56a6f95de5e72dd835005dc9960b8379_40.png)

嗯。And yes， that's also a good point when checking for equality。

 if the two strings are different lengths that are not equal。

 and one of the things we'll see is that it does do a short circuit of that comparison in some situations。

 but that's a case we'll talk about a little bit later。



![](img/56a6f95de5e72dd835005dc9960b8379_42.png)

So the real answer one way to think about the answer is it's a design decision of the STL to not check for things that they think the programmer can get right now I'm one of these people who get stuff wrong all the time so I actually prefer it if someone would check my mistakes but unfortunately STL isn't that person。



![](img/56a6f95de5e72dd835005dc9960b8379_44.png)

![](img/56a6f95de5e72dd835005dc9960b8379_45.png)

![](img/56a6f95de5e72dd835005dc9960b8379_46.png)

嗯。

![](img/56a6f95de5e72dd835005dc9960b8379_48.png)

And Alan， I'm not sure I understand the question about would iterating the begin iterator until it's equal to the last and vice versa be a bad idea。



![](img/56a6f95de5e72dd835005dc9960b8379_50.png)

嗯。I might have to think about that， let me come back to that but in general。

 if the answer is it uses redundant comparisons， the answer is the STL tries to avoid that whenever it possibly can。

 again， because it's a design philosophy for the STL。Okay。嗯。



![](img/56a6f95de5e72dd835005dc9960b8379_52.png)

The next topic I want to talk to is lexiographic comparison。

 so that first piece we talked about we've introduced the notion of sequences。

 there are sequences of characters drawn from a finite alphabet， zero or more characters in length。

 and we've talked about how to tell whether they're equal or not this next piece is lexiographic comparison or given a definition of before and after defined over this family of strings。



![](img/56a6f95de5e72dd835005dc9960b8379_54.png)

![](img/56a6f95de5e72dd835005dc9960b8379_55.png)

![](img/56a6f95de5e72dd835005dc9960b8379_56.png)

![](img/56a6f95de5e72dd835005dc9960b8379_57.png)

How do we decide whether one comes in front of the other？

So here are the basic rules and I'm going to state these a little differently than they're stated in the slides because I like to define these。

 I tend to define these recursively。Two empty ranges are equal to one another。😡。

An equal range is always before， always comes before a non equal range。

So I'm almost doing this from the bottom， so the first one is。You know if two empty ranges are equal。

 an empty range is always less than a non empty range。嗯。And。

And then the question is what happens in the other cases so we compare element by element if we have two elements they're of equal and they don't have to be of equal length。

 if their first character is the same， the first character can't distinguish them so we move to the second if the second character is the same we can't distinguish them so we move to the third if the third character。

Differenterence is different， so the first mismatching element we have。

Defins which which sequence comes before or less than or comes after is greater than the other and that's defined by by a comparison over the individual characters from which the sequence is drawn so less than or greater than is defined by the characters。

Which in turn infers a definition for less than and greater than on sequences。嗯。😊。

If they match all the way， but one range is a prefix of another the shorter range is less than the longer one and that's this is a consequence of the fact that empty ranges are always less than non empty ranges so we can think of the ranges as being broken into two pieces the the。

We can think of the range as being broken into two pieces， there's the piece that's identical。

Those are equal， and then there's a zero length sequence that comes before whatever happens to be in the rest of the range。

So if two ranges are equivalent。So only if two ranges have equivalent elements defined by our comparison operator。

 so they don't need to be bitwise the same， but they need to be the same defined by our comparison operator。

And they're the same length， then they are lexiographically equal。

So another this is an example way of describing this。

 so the empty string is always less than a non empty string， a is a prefix at AB。

 so A is less than that。A comes before B， so A B comes before the single character B。

 B is a prefix of BA。A comes before C in the dictionary。And BC is shorter than BC0。

 so BC comes before BC0 in the dictionary， so this is an example that iterates each of those different conditions that we saw about earlier。

嗯。😊，When when we're implementing this， we can implement all of these comparisons with two operators and in fact this is typically what the STL requires us to provide whenever we're providing something that talks about in order。

 we have to provide some notion of equality and some notion of less than and that's all you need and you can write the other four in those terms and if you've taken each270 you've probably seen examples of this or this kind of thinking where we use fewer circuits to pretend that we have more circuits than we've actually built。

And this is the same thing， so not equal is the same as equal not。

And A is greater than B is the same as B is less than a。

A is less than or equal to B is the same as B is not less than a。

A is greater than or equal to B is the same as a is not less than B so the other reason we don't want to write all of these six operators is well it's complicated and also if you get it wrong you have to fix it in six places instead of two and I'm a big fan of fixing things in as few places as I can possibly find。

One of the other things that's worth thinking about。

 you definitely don't want to implement while you can implement less than or equal using both less than and equal。

 it's better to use it to use this other comparison so instead of using less than or equal this one is much preferable。

 the reason is this costs you linear time and that costs you linear time。

 so while it's still asymptotically linear it's a factor of two and we'd like to avoid that whenever we can。

U。So one of the other things that we'll often do a common way of encoding this lexiographical order is that we'll have a function that does a comparison helper。

And so for any particular class T， if we want to provide some kind of comparison over it。

 we'll take have a function that takes two constant references to these， returns zero if it's equal。

 negative one or more generally a negative number， if they're less than positive one or more generally a positive number if x is greater than y。

 so so I'll say compare x y， if it's0 x and y are equal， if it's negative x is less than y。

 if it's positive x is greater than y。And then once you've given this。

 you can implement all of the comparison operators with post processing given that particular function。

There are a couple of other optimizations that this STL uses。

 so STL in general stores strings in dynamic memory on the heap because remember C++ strings are allowed to grow arbitrarily。

 you don't need to know how big they are in advance whenever you have something that grows arbitrarily。

 it is inevitably going to be stored in the heap and by he I mean the memory management heap。

 not the heaps that we're talking about in project2。

As an optimization short string strings that are 16 bytes or less are stored instead within the actual representation of the string itself。

 so the string has we talked about the string has these pointers。One pointer to the beginning。

 one pointer to the end and a size field and some other stuff。For very short strings。

 they just go in here and for those strings。Instead of of pointing。Yeah。Stop。All right， like I said。

 I haven't figured all of this out yet。Instead of pointing at the reference， oh。

 it looks like I can't do it from there， oh that's really awful。嗯。Instead of。Sorry。

 the operator error， like I said， please be patient instead of pointing off into the heap。

 it'll point back。Into this area on the stack， which just avoids an allocation and a delocation。In C。

 the null terminating operator simplifies the less than operator because。

The null character is represented by bitY zero， so it's less than every other character that you ever care to compare。

 so this null character that's implied at the end of this string is less than D。

 which means ABC is automatically less than ABCD。And again。

 this was mentioned as an optimization earlier by the staff member who's joining us on the chat today。

 but in C++ because strings of different sizes have to be not equal。

 it just checks the size for the not equal comparator and finally this is a pretty interesting place where you can use parallel computation because。

Equality is an embarrassingly parallel thing and even some of these are amenable to something called single instruction multiple data。

 so you can simultaneously compare a group of individual characters using vectorized CPU instructions。

 which is something you'll learn a lot more about in maybe 370 but if not 370， certainly 470。

 and you'll learn later in some courses like 477， some algorithms that take advantage of this CPU hardware。

There was a quick question that came up in the chat why is less than the de facto comparison in C++ and I have no idea that's a really good question my guess is that it was historical accident。

There may be some really interesting corner case in the hardware that makes less than more efficient。

 but I don't know that off the top of my head， it's sort of like why do we start at zero because we did it may be nothing more interesting than that but I'm not sure。

So here's a simple implementation of how this might work。So we're going to take two strings in。

We're going to。Grab their links so we don't have to continuously call that method so even though this is constant it's constant time to obtain the link out of each of these strings we'll often cache it in a local variable so that it makes it a little easier for the compiler to optimize things it also I think makes it a little bit easier to read and I use this trick a lot so I will often also create constant references to things that I don't want to have to keep typing over and over I use that a lot in Project1 so I didn't have to keep typing out the subscripts of all of my three dimensionmensional arrays and I could just remember what some of those were。

U。Then we have a counter， it starts at the beginning。

And while it has not reached the smaller of length zero or length one。

So once we've compared the prefix of those characters， we have an answer。

Either the string length are the same， they have the same length or S0 is shorter than S1 or S1 is shorter than S0。

 this compares against the shorter of those。If the character in sequence zero at this position is less than the character of sequence one。

 so at any point。Where I， I is somewhere in。Arbitrarily in the middle of the sequence。

 everything to the left of I was already compared and judged to be equal。

 we haven't compared anything to the right of eye yet and I is the one we're thinking about。

So if at this point in the algorithm if。If the character in string zero is less than the character in string one。

 well then the whole sequence string zero is less than string one， so return negative one。

If the character in string zero is greater than the character in string one。

 then the whole sequence is greater than return positive one。This。

Is this compares the prefix of the length。If the two strings。Are potentially of different links。

 but they're equal in their prefixes， then the question is which one is shorter。

 if zero is shorter than one， then string zero comes before string one in the dictionary。

 if zero is greater than one， then string zero comes later， otherwise。

 if we make it all the way down to the bottom， they are completely equivalent。Okay。

 how does this work， runtime analysis， it's linear worst case time， it requires constant extra space。

 and I'll go back to that the extra space is these sizes and the iterator。

And you can't do better this is the this is the do not pass go do not collect $200 you can't make it any faster than this you can just be done here average case complexity though for random strings is constant because random strings are very if they're complete if they're truly random strings then they're almost certainly different in the first character so we really only need to compare the first character and we're done the problem with that is strings are often really not random。

So we do a lot of things where we're traversing directory trees and the entire prefix of those directory trees is completely the same。

 and if we keep comparing those over and over and over again。

 then maybe we're wasting a little time and that's why we sometimes use what are called STEM data structures we'll store the common prefixes together。

I do not speak German， I looked up these words last night as I was preparing this lecture。

 I don't remember what they translate to and I wish I did I'm really sorry about that。

But words with common stems。Common prefixes have the same problem， words with common suffixes don't。

 so that's nice but。Likewise， if we're just comparing things that are likely nearby in a dictionary。

 we run into this problem as well and so there are some tricks we might resort to to make this a little bit faster in general。

There is a function， as there is for most things， there is a function in the STL that will do this for us。

So。The basic one just takes the iterators that describe the two ranges。

With first and last on the first range， first and last on the second range。There's another version。

 so I'm going to call this version one， there's version two。

Wwhichch allows us to specify a comparison function。

 so if the default standard less than is not the one that we want to use to compare items that these iterators point to。

 we can specify a comparison function sort of like we specify a comparison function in project two that compares Jedi deployments and creates an order for them。

These other ones I'll call this 1 a and 2a use this thing called an execution policy and you might remember from an earlier slide I mentioned that some of these algorithms are really easy to parallelize or interesting to parallelize those execution policies talk about how to parallelize these structures and we won't talk about that a whole lot in 281。

 we might touch on it really briefly， but again when you start taking things in 470， maybe 42。

 maybe 370， but I don't think so， but I think 470， 477， 442。

 we'll start talking about more of these parallel algorithms which can be really， really powerful。

So here's a simple implementation of that。This is the equivalent of that iterator or the index not being equal to the smaller of those two ranges while the first while the first so what we're going to do is we're going to walk。

We we have a range where we have a first iterator and a last iterator。

 we're going to walk the first iterators forward comparing as we go。

 if those iterators ever overlap or they're equal， that means we've reached the end of that particular sequence。

 so the termination condition of the while loop。Is。

While the first iterator is not equal to the last and so if either first is equal to last。

 that means we're done with the first sequence or if first。

Is for the second iterator is equal to the last。Of the iterator， the second range we're done too。

 so this is the have we exhausted all of the characters while we haven't exhausted all of the characters in the first range and the second range。

Well。Compare the characters at those iterator locations。And again。This is a lexographicical compare。

 so again， remember we're returning true they if the first one is less than the second one。

 just like we're using the comparison function in the sorting algorithms in the binary cues that you're writing in Project2。

So if the first is less than the second， then this is true。If。

The one and the second sequence is less than the first sequence because remember we only have the comparison less than that are handy to us。

 then we return false， and if they're the same we iterate our pointers forward and we keep going。

When we get to the end。We're going to return。True if the first one comes before the second one。

And the first one comes before the second one。If。嗯。They're equal then we don't care。

 because it's less than or equal or first two，' if they're notaught， if we're at the end。

 one of these is zero。So if the first one is zero and the second one is not zero。

 then before the first comes before the second， if not， they're the same。wait。

 can you just separate two increments with a comma， you can。

 and I think this was only done to make this slide fit because I would generally not write it that way。

 I would generally write it as as individual lines。So the comma operator。

Takes two expressions E1 and E2， it evaluates first E1。Then it evaluates E2。

 and the result of that expression is the result of E2。

 So the result of plus plus first one comma plus plus first2。Is the incremented first two。

 but since we're not using the value of that expression anywhere we just throw it away and again。

 I really almost never do this， I very rarely use the comma operator。

 I might sometimes use it inside of contaminat conditions of a loop but even that's pretty rare。

 I don't like it because I don't think it's all that readable。

 but again I tend to resort to very simple code。Okay。

 here's an example of how we might use lexical Compare。

And this is something that you can just type in and run。

 and so let me just run through what it's doing。The print characters's function takes a。

Takes a vector of characters， it's going to print each of those characters followed by a space。

And at the end of printing those characters， it will print out a separator string。

 and that may be an empty string or it may contain characters。

 it may contain a new line it can contain whatever you want。嗯。Then I'm going to define two vectors。

 V1 is ABCD， and V2 is just a copy of V1 using the initializer syntax from C++。嗯。Then。

This is a me and twister， this is just a way of randomizing things。

What this is is while V1 is not before V2。Because remember。

 lexical compare returns true if V1 is before V2， while that's not true。

 then I will print V1 is greater than or equal to V2。

And then I'll shuffle them and see if the shuffle gives me one and I'll keep going until I happen to get a shuffle permutation where V1 is less than V2 so you can type this in and try it out and it'll give you a sense for how these things work。

嗯。Another application that we often use for these algorithms。

 given a container of string objects we only want to find we only want to leave one copy of each string so for example。

 here's one that I often use， suppose I wanted to know the unique names of students who have submitted project to。

At this point in the project， I've submitted it bunches of times and I'm still not I have a few things I want to tweak on it。

 but at this point in the semester probably many of us have submitted many times so I don't want to have be noble be noble。

 be noble， be noble be noble be noble， which is my unique name many times I just need my unique name once。

 so if I just wanted a list of all of the students who have submitted project 2 a I might use an algorithm sort of like this。

So the first is I would sort those strings so that even though if maybe I got the unique names in the order in which they submitted the project。

 so B Noble， then Piti， then MM Darden， HD Garcia， I may sort them so that all of the B nobles appear together。

And then。All of the HDG Garciaas and then all the MM gardens and then all the Pas。嗯。Then compared。

 as I walk through the list of strings， I can compare each adjacent string。

 if this string is the same as this string， ignore it。And standard unique does that for me。

 so this is just using the STL I sort the strings that I have with the comparison operator that I want and then I write the unique that only gets the individuals from the equal operator and it's pretty simple。

So it's another way where you can stitch things together in the STL to accomplish more interesting questions。

诶。Yeah， so let me show that message because that's totally fine。嗯。And then yes， so Samuel。

 the question that is that's a lambda expression， autoC means it automatically derives the type of C。

And did I have one of those？And I just missed it， yes ah。Thank you。

 I just I did just I read right over it， so this is a lambda expression we talked about these maybe about four or five lectures ago。

 but we talked about them pretty much in passing and what this says is this is a function that doesn't have a name。

It takes one argument and I'll let the compiler figure out its type。😡，It's going to。嗯。

Past that argument to the insertion operator of C out followed by passing the space to the insertion operator of C out Now this auto is going to be a character because it's vectors of characters。

 one of the interesting things to think about here is could you templaize this that it could print anything for which the insertion operator was defined。

And wow， that's completely unreadable because I scribbled all over it， apologize。Okay。

 so let's see we had some things in the chat。So we talked about the comma operator。

We talked about the lambmbda lambmbdas are really cool I'm going to put in a plug for lambdas I know when we introduced them to you。

 we said you know you might find these useful you don't really have to know them it's up to you if you decide you want to use them or not I'm a huge huge fan of lambmbdas。



![](img/56a6f95de5e72dd835005dc9960b8379_59.png)

![](img/56a6f95de5e72dd835005dc9960b8379_60.png)

![](img/56a6f95de5e72dd835005dc9960b8379_61.png)

For a couple reasons， one is so lands tend to replace the use of functors or function objects and the nice thing about land is is you don't ever have to name them and they don't have to own a type。

Function objects have to have a type name attached to them and sometimes you don't want to do that。😡。



![](img/56a6f95de5e72dd835005dc9960b8379_63.png)

The second thing is that landNes also make the code a little more compact LA is are also very useful in something called functional programming。

 which you might learn more about when you take 490 which is the programming languages course and we might touch a little bit on it here too。

 functional programming is really interesting because in functional programming。

 once you have a value in a variable， you never change it。



![](img/56a6f95de5e72dd835005dc9960b8379_65.png)

Um， that turns out to be really weird if you've never written it before。

 although if you think about it， the first real project in 280 was that way。Um。

 but once you get used to the idea that I'm going to have these variables that I never change the values of。

 that becomes a very， very powerful idea。Because in particular。

 one of the things you'll learn when you take， for example。

 42 is the way you get in trouble in parallel programming is that one processor writes a value while another processor is trying to read it。

Well， if no processor ever writes a value once it's created， you never have that problem。

W eliminates an entirely huge class of bugs， which is way way cool。Frankie。

 when would be a time when you don't want to make a func and use a lambmbda other than being lazy。

 the other cool thing that lambmbdas do is that they have a capture。

 so if you have a lambmbda so you have a scope that has some local variables。

 you can create a lambmbda within those that bind some of those variables or bind all of them without having to name them。



![](img/56a6f95de5e72dd835005dc9960b8379_67.png)

![](img/56a6f95de5e72dd835005dc9960b8379_68.png)

That turns out to be a very powerful mechanism again we see that often in functional programming but it comes up quite a bit and Ian you're welcome to plug rust。

 I am not a rest programmer， however I know all the rest programmers I know like it。

 although that's a little bit like all the Crossfiitters I know really like Crossfit and I'm a sourdough baker and so I really like sourdough so I'm not convinced about the rust thing yet but but it's on my list of things to try this summer it's to learn more about rust because everyone I've ever talked to who's ever tried it thinks it's really really cool。



![](img/56a6f95de5e72dd835005dc9960b8379_70.png)

![](img/56a6f95de5e72dd835005dc9960b8379_71.png)

![](img/56a6f95de5e72dd835005dc9960b8379_72.png)

![](img/56a6f95de5e72dd835005dc9960b8379_73.png)

![](img/56a6f95de5e72dd835005dc9960b8379_74.png)

![](img/56a6f95de5e72dd835005dc9960b8379_75.png)

Okay。

![](img/56a6f95de5e72dd835005dc9960b8379_77.png)

The next thing I want to talk about is searching within strings。

 so searching within strings is something we do an awful lot。

And it turns out that in many very common situations， searching within strings is expensive。

And DNA is one of those， so I talked a little bit earlier about the idea that I have you know。

 a gene that encodes the spike protein of the COVID virus。



![](img/56a6f95de5e72dd835005dc9960b8379_79.png)

![](img/56a6f95de5e72dd835005dc9960b8379_80.png)

And I'm looking for interesting mutations of those genes so I'm looking for places where or maybe I have an interesting mutation and I want to see if that mutation is in this other other sample of the virus that I just sampled well mutations are such that they only change a few bits。

 a few characters so most of those characters will be the same so if I'm looking for those and I'm doing this comparison of equality I'm going to check a lot a lot a a lot a lot of things before I discover that they're not equal same with the directory prefix so this question of searching within strings really quickly turns out to be an important one and we're going to learn a really cool technique for doing that in this is the third segment of today's course and。



![](img/56a6f95de5e72dd835005dc9960b8379_82.png)

![](img/56a6f95de5e72dd835005dc9960b8379_83.png)

![](img/56a6f95de5e72dd835005dc9960b8379_84.png)

![](img/56a6f95de5e72dd835005dc9960b8379_85.png)

![](img/56a6f95de5e72dd835005dc9960b8379_86.png)

![](img/56a6f95de5e72dd835005dc9960b8379_87.png)

![](img/56a6f95de5e72dd835005dc9960b8379_88.png)

![](img/56a6f95de5e72dd835005dc9960b8379_89.png)

This is really related if you hear finding a needle if， well。

 finding a needle in the haystack is an English idiom。

And what it means is something that's a really hard thing to find is a search that goes forever。

 it's like me trying to find my keys in the morning because I can never find them and if you look at what this actually looks like you know。

 look pawing through this hay， looking for a teeny tiny needle。

 if you're doing that with your hands that's going to take a long time。

If you're doing with the metal detector， it's a little faster。

 there may be more than one thing of metal in the haystack， but the needle is metal。

 so if you're only paw through the hay when the metal detector tells you there's something metal there。

 you're going to really shorten your search and that's we're going to do something kind of similar when we talk about what we're doing next。

嗯。So there's a public algorithm that does this， string find， string takes。嗯。It takes a string。嗯。

Let's see so searches the string for the first occurrence of sequence specifies by the argument。

 so this is a method of string， you pass in something you're looking for that you want to know if that's a substr of the string and it will return true if it is and and it will return the index sorry not true。

 it returns the index of where this thing lives if it happens to live in the string。And if it's not。

呃。Then it returns where to go。No， I can't find it。The first occurrence of the string specify the sequence of charges。

 if not， it points to the off the end of the string。U。So brute force string searching。

 pretty straightforward。We have a small string we're looking for。

 this is the small string we're looking for， we have a larger string that might contain it and we sort of line it up。

 well is a equal to A， yes is B equal to B， yes， is C equal to C yes。Is D equal to a， no。Okay。

 well then we sort of think about this as。We take our small string and we slide it over one character and then we compare again。

 well is a equal to B no， okay， we slide it over one more character is a equal to C no and we keep going until ABCA。

 we end up lining the windows up here， ABCA and we find that's the place and so that's the thing we return。

嗯。The worst case time of this is the length of the needle， this is our needle。This is the haystack。

Sorry， I'm totally incapable of them。Let's try this again in a way that's maybe possibly readable。

So this is our haystack， this is our needle。Um。We we might end up comparing almost all of the needle every time we look throughout the entire haystack。

 so if you think about AA A B， A A A， A A， not a B， okay， A A A， A A A， A A， not a B， A A A A A A。😡。

Not a be。And we keep going， so we keep recomping all of these first ones。

 which which again can be pretty painful if these strings are random。

So if I randomly pick a needle and randomly pick a haystack， well。

 then it's basically the length of the haystack because。

Two characters chosen at random are very likely to be different。So the average case。

 if the inputs were truly random and remember， average cases are only about。Truly random inputs。

 we sometimes call them ID inputs so they don't have to be， but they do have to be random。

The problem is lots of strings aren't random。And so the worst case happens。

And surprisingly often now I will say that the STL implementations often choose this algorithm because it's really simple and it's simple is nice because it's easier to make simple programs correct than hard programs correct and it's usually fast in practice。

either because the strings don't share lots of prefixes or the strings are small。

 you know I just saw a tweet yesterday from the computer science account。

 which I follow and I retweeted that fancy algorithms aren't very important when n is small and n is almost always small。

So STL implementations often will use the brute force of them because you know， it's fine。However。

 there are cases where this matters。You can fix this with a little bit of work using some preprocessing。

 which we're not going to talk about this is an algorithm that's sort of beyond the scope of 281 you might look at it in 477 but there is there is something called the canuth Morris Pratt algorithm and that Morris is the Morris of the Morris Internet worm Fa if you're wondering Canuth is Donald Canuth who wrote the books about algorithm so another name you might know I didn't look up Pratt I should have done that。

But so these do happen quite a lot and you know one of those places where they do happen。

 where they can happen， again， they can happen in these genetic sequences because we're only drawing from four characters and so we might by accident have sequences that are pretty similar a lot of the time。

So instead。There's。Another thing we're going to try。

 so remember I talked about what do we if we were looking at the haystack。

If we had to look at each piece of hay by itself that was going to take a long time。

 but if we could wave a metal detector over it， we would find things that are metal and then we take that well no that's a quarter well no that's a diamond ring well oh that's the needle so we're going to have this metal detector that'll tell us where in the haystack we need to focus our more careful attention otherwise you know we can kind of ignore a bunch of stuff。

And if we could do that， so if we're waving the metal detector over the hay without having to look at each strand of hay to see。

 is that really a needle， then it runs in length of the haystack rather than haystack times the needle。

So the idea is。We're going to only perform sequences when we think there's a really good chance these things are the same rather than they just happen to be same by there's a really good chance that they're actually the same rather than just sharing a really long prefix。

Now the worst case this idea isn't actually going to improve our worst case performance。

 it will still be worst case length of the needle times length of the haystack。

 however it turns out that in practice worst case inputs are really。

 really hard to find you can't easily construct them just by thinking about it like we could for the earlier one like here。

😡，If we just thought about these two strings， we can sort of construct a bad input for the brute force algorithm。

 for the algorithm that I'm going to show you。Oh， too far。For the algorithm I'm going to show you。

 it's actually really hard to just sit down and write down a string that turns out to have bad worst case performance。

 even though such a string exists。Right。What this is sometimes called we're going to take advantage of some probabilistic things and that's the idea behind this next algorithm。

Big idea。What we're going to do is we're going to give it a string。That might be arbitrarily long。

 we're going to have some function over that string that just gives us one integer。

And the idea is that we want to choose our function F so that strings that are the same always have the same integer。

But strings that are different almost always have different integers now they can't always have different integers because this integer has fewer bits than this string。

 so there's no way to encode all possible strings with different integers。

 there just aren't enough bits， but if we're clever about how we choose F。

We can choose an algorithm we can choose an f that where we compute the F's of these strings and then we just compare the integers and if the integers don't match。

 then we're pretty sure the whole thing doesn't match， but this is much shorter。

 this is a constant time comparison instead of a comparison in the length of the needle。Okay。Um。

 so a really simple example of F that turns out to be a bad idea is just treat every character a as an integer value and add them。

😊，And the reason that's a bad idea is that anagram。

 so this is an anagram if you happen to have read the Harry Potter books。

 if you haven't read the Harry Potter books I have really bad news。

 this is a reveal and it's a spoiler and I'm sorry。

 but I figure at this point if I'm spoiling the Harry Potter books it's probably okay because I am Lord Volemort is an anagram of Tom Marvelow riddle with an extra space I think Ro forgot that bit but we'll cututter some slack on that and because these characters are all the same and because addition is irrespective it doesn't care about the order in which things happen it's commutative。

 these two both compute to the same integer and it turns out lots of things work that way so addition is just a bad choice for F。

Um。So I talked about this， if we had fingerprint functions with few these collisions。

 a collision is defined as when this F produces two results that are the same。

Where the strings are really different so again collisions are inevitable。

 but we want we want them to be rare in practice and if we had that。

Then all we have to do is compare the fingerprints when the fingerprints match we have to check for equality。

 but if the fingerprints don't match， we know they're not equal and again。

 if we pick a really good F with very few collisions， we check uselessly very， very rarely。Okay。

So here's the function， it's called a rabin fingerprint and I've used this in a couple of research projects。

 this idea turns out to be really really easy， so instead of adding up the character codes we view them as a sequence of decimal numbers。

😊，And what we're going to do is we're going to treat each of those as if it was in a different tense place。

 so this is the ones digit， this is the1s digit， this is the hundreds digit。

 this is the thousandss digit， this is the 100s digit。Okay。

So T and what we'll do is we'll start with the first character treated as the one's digit。

 and then every time we add a character， we multiply what we have already by 10。

So multiplying by 10 shifts it over one decimal place。So T is 84， we represent TO by taking 84。

 multiplying it by 10， adding O， which is 79。We take TOM， this is TO， which is 10 times 84 plus 79。

 that's TO， multiply that by 10， add M and so on。So the idea is that we shift the characters over as we go and I'm using days 10 only for illustration just because it's sort of a natural way to think about you know ones digit。

10s digit， hundreds digit， we will end up using much larger numbers and then much larger numbers we' use will turn out to be chosen carefully。

What this means is that if we have a permutation of the characters。

 just the same characters in different order， we almost always get a different result because this function。

Takes advantage of spatial locality。So。Spatial。Localality。

Where the character appears determines how much it contributes to the integer function we're going to use to represent this。

Now what's cool about that is that we can use a sliding window if we have a really long string。😊。

And we're looking at only。We're looking at only a piece of it。

 we can slide the window forward by one character by subtracting out the contribution of the largest character。

Dividing it by our base and adding this character back in。Okay， so removing this。

 that's just a subtraction。Sliding this， that's just a division。Adding this is just in addition。

 that's constant time。So I can compute the values of all of these things once。

 or I can just recompute them， it's not that complicated。So removing the characters's constant。

 adding the character is constant。The initial computation of the window across the whole thing， well。

 that takes M time because we have to do M windows。And each of the slides is constant。So if， again。

 if the fingerprints differ。We can compare this window with a comparison window in constant time。

But if the fingerprints are the same， then we have to check to see if the strings are actually the same。

Okay。So we can compute the fingerprint of the needle that's just one thing。Linear time。

And then we'd start at the beginning of the haystack。

 we compute the fingerprint of the beginning of the haystack。If those fingerprints are equal。

Then we have to actually check check the string if the fingerprints are not equal。

 then we slide this window over by dividing out the largest character by subtracting out the largest character's contribution dividing the entire window by the base and adding the new character's contribution we compare that new fingerprint with our needle fingerprint and we can keep going so most of these comparisons will be not equal。

 so we incrementally update the fingerprint of the window as we go by taking one character out。

 adding one character back in。If the fingerprints are ever the same。

 we check to see if the strings are the same if they are， we're done。

But if there are more characters， we just keep going。So the idea is， again。

 if we've chosen F carefully。And in practice， different strings have different fingerprints with very high probability。

 then this will speed this algorithm up in the worst case。Okay， there are a couple things。

 there's one very important twist to this and this is going to rely on a little bit of math that came out of 203。

 which hopefully will ring a little bit of a bell， but if not that's okay， we'll explain it again。

For really long strings as we perform these additions and multiplications。

 we're going to overflow the integer。So one of the tricks we'll use is what's called modular arithmetic。

And the idea behind modular arithmetic is that we're going to pick some pretty large prime。

 this is a pretty decent one， we actually might even pick a larger one this is a pretty good one for integers though。

 especially for 32 bit integers。Then whenever we multiply two integers together。

 instead of just taking the result， we multiply those integers， mod this prime number。

Whenever we add two integers， instead of just adding them together。

 we add them and then modD by prime the prime number。

 what I mean by modD is if it's 11 o'clock and we add four hours to 11 o'clock。

It becomes three o'clock。If you're not using military time， if you're using military time。

 11 plus four is 15。100 hours， so the military uses the hour of the day mod 24。

 most of the rest of us in civilian life use the hour of the day Mo 12。

 so one in the afternoon is really the 13th hour of the day。

 but it's one because we take hours mod 12。Now one of the things that I'm just going to say and I'm not going to prove and it's something that hopefully we've talked about a little bit in 203 or maybe in some of your other earlier math courses。

 is that all of the usual rules of math work the same way。

 even though after every one of these operations we're going to apply a modulus to it。

So the order doesn't matter for multiplication or addition。

We can can rearrange orders and all we can do the Associative Rule still holds all of this just still works。

 which is cool because then we can keep this modulus around。

 but continue to use all of it as if it were just regular math。Okay。

 so what's the time complexity of this， well if the different substrs never collide so they never produce equal fingerprints。

 the runtime is the length of the haystack。Every time there's a collision。

 we have to spend an additional runtime of the length of the needle to perform the equality check。

And again， if we picked one of these largest primes and a pretty interesting base number that we're multiplying by。

 the collisions are rare and don't correspond to things that tend to turn up in practice。

 so we'll choose a larger prime is our modulus， and our base we choose is a power of two。

And we choose a power of two and that power of two is approximately so where k is approximately the number of bits。

In a character。And we'll see why in a second， so in an ASI character set we don't use the higher order bit of the eight bits。

 so there are seven bits in a character so we're going to use something that works kind of like this so。

As long as two to the K is co prime with the original prime number， in other words。

 none of them share a factor， then collisions will turn out to be very rare。And again。

 because we've chosen a larger prime as our modulus。

 anything else is co primeme with that because everything is co prime with a prime。

 and also we choose this tower of two because the multiplication turns into a binary shift rather than an actual multiplication and binary shifts in practice are faster on most hardware。

Okay， this is the algorithm and it's a little complicated but'm and I know we're running a little bit short of time。

 but I'm going to walk through it。So here our base is 128， which is two to the seventh。And again。

 that's because there are seven meaningful bits in a character。

 so this means the characters don't ever overlap in our math。Size N and H， the length of the needle。

 length of the haystack。Z。Is。Going to be。嗯。The Z is the multiplier of our largest character because remember the first character is based is multiplied by b to the zero。

 the second character is multipplied by b to the1 and so on and the most significant character is multiply by B to the n minus1 where n is the length of the needle so this number is the multiplier Z that we're going to multiply by the largest character so we want to subtract the largest character out we multiply that character by Z and we can drop it out of our window。

And is the needle fingerprint， H is the base finger is the window fingerprint。嗯。For each of the。

 we're going to precomp it。嗯。For each of those for the length of the needle。

 and now we start our window， if the two fingerprints are the same。

 then we have to brute force check the strings。And if they're equal， we're done， we found it。

If they're not equal。And if we're not at the end， so remember I points at where the current starting position that we're searching。

The needle is N characters long， so as long as I is no farther than that， we're not done yet。Well。

 we subtract out the contribution of the oldest character。Modulular by prime。

We multiply that entire thing by the base to shift it over that' sliding the window。

 and then we add the youngest character and we modlo the entire thing by prime again。

Now there's one little correction if that turns out to be a negative number。

If we're talking about negative 11 o'clock， we have to add the modulus to it so that we get a positive like negative one o'clock is positive 11 o'clock。

So because we need to make sure that we're not working with negative numbers and then we return if we get all the way through。

 if we've slid this window all the way through and we've never found this inner loop to be true。

Then we can return negative1， and we're done。Okay， so I went through that a little fast。

 but we're also just a couple minutes over time and I want to be mindful of the fact that we end at 10 minutes before the half hour。

 so let me take a few questions for people who want to stick around。



![](img/56a6f95de5e72dd835005dc9960b8379_91.png)

嗯。Let's see so we talked about the question about why do we divide because we're moving sorry you're right。

 it's multiply that's that was a mistake on my part and I was standing too close to the board。

 sliding the window to the right multiplies the existing characters by the base。

 not dividing my mistake。T entirely my mistake， Richard， you're completely right。

Again what is the constant expression？I'm not sure which constant expression you mean。

If you're still around。Oh why not just hash define the a cost expression versus hash defined that's a matter of style you can hashtag define the problem is when you hashtag define the compiler no longer knows its type。

And sometimes you want to carry the type around because the type sometimes allows the compiler to make better optimization decisions。

 or it allows it to do some more strict type checking， which we sometimes want to do。

The reason we sometimes use these things and constant expression means it's only an expression value。

 it's never one that it's not one that I ever have to store。

 so it really gets treated as if it were a defined， but the compiler knows its type for sure。

 so that turns out to be a handy thing to do every once in a while。

So I think that's that's the answer to that one yeah so as Ian points out it's a compile time optimization。

 they're both compile time optimizations， the advantage of constant expression int is that the compiler then also knows definitively what its type is and that turns out to be useful for a variety of reasons。

Yeah， so if you can get away with using a con expression， I sometimes just use the cons。

 but cost expression is probably even even preferable。

 it is preferable to pound define in C++ because it gives you're giving the compiler more information。

And whenever you can give the compiler more information about what it is that you're trying to do。

 the compiler can make better decisions on your behalf in terms of checking for correctness and in terms of checking and in terms of implementing optimizations。

You know， the compiler writerss， so for example， Professor Malkey is a compiler author。

 Professor Malkey is a lot smarter than I am， so I am happy to have him make those decisions on my behalf when he writes compilers rather than me trying to write programming rather than write code。

I'll stick around for a few minutes if people have other questions for the next minute or two。

 but otherwise we won't have a lecture on Thursday and Professor Darardin will be doing the review on Tuesday so I will see you again after the midterm。

Oh， there was， I see one question answered in the text， the question about。The fingerprint RSA。

All right， it looks like people are starting to drift out so I'm going to go ahead and close the stream good luck on the midterm everybody based on the conversations I've been having you in office hours I think everyone's going to be really going to do great on it and I'm really looking forward to seeing how it goes because I'm excited to see all the things that you all have learned take care。

