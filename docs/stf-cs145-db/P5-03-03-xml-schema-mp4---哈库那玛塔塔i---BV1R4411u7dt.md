# P5：03-03-xml-schema.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 In this video， we'll be learning about XML schema。



![](img/0fd308dae54064fed2fcaebfb7bf7c02_1.png)

 Like document type descriptors， XML schema allows us a way to give content specific specifications for our XML data。

 As you may remember， we send to a validating XML parser， our XML document， as well as a description。

 We talked about DTDs in the last video， we'll talk about XSDs in this one。

 The validating XML parser will check that the document is well formed。

 and it will also check that it matches its specification。 If it does， parse decimal comes out。

 If it doesn't， we get an error that the document is not valid。



![](img/0fd308dae54064fed2fcaebfb7bf7c02_3.png)

 XML schema is an extensive language， very powerful。 Like document type descriptors。

 we can specify the elements we want in our XML data， the attributes， the nesting of the elements。

 how elements need to be ordered， and the number of occurrences of elements。 In addition。

 we can specify data types， we can specify keys。 The pointers that we can specify are now typed。

 unlike in DTDs， and much， much more。 Now， one difference between XML schema and DTDs is that the specifications in XML schema。

 called XSDs， are actually written in the XML language itself。 That can be useful， for example。

 if we have a browser that nicely renders the XML。 The language， as I said， is vast。 In this video。

 we're going to show one sort of "easy" example， but that example will give very much the flavor of XML。

 And we'll try to highlight the differences between XML schema and using document type descriptors。



![](img/0fd308dae54064fed2fcaebfb7bf7c02_5.png)

 Okay， here we are with our XML document on the left。 On the right。

 we have our XML schema descriptor， or XSD， and we have a little command line that we're going to use for our validation command。

 Now， let me just say up front that we're not going to be going through the XSD line-by-line in detail the way we did with DTDs。

 As you can see， it's rather long， and that would take us far too long and frankly be rather boring。

 So what I highly suggest is that you download the file for the XSD。

 so you can look at it yourself and look at the entire file， as well as the XML。

 and give it a try with validating。 What I'm going to do in this demo primarily is focus on those aspects of the XSD that are different。

 are more powerful than we had in document type descriptors。 First。

 let's take a look at the data itself。 So we have our bookstore data as usual with two books and three authors。

 It's slightly restructured from any of the versions we've used before。

 It looks closest to the last one we used because the books and authors are separate。

 and the authors are actually exactly the same。 They have an identifier and a first name， last name。

 sub-element。 The primary difference is in the books。

 instead of using IDRETs attributes to refer from books to authors。

 we now back our back having an author's sub-element with the two authors underneath。

 and then those authors themselves have what are effectively the pointers to the identifiers for the authors。

 And we'll see how that's going to mesh with the XML schema descriptor that we're using for this file。

 So the other thing I want to mention is that right now we have the XML schema descriptor in one file and the XML in another。

 You might remember for the DTD we simply placed the DTD specification at the top of the file with the XML。

 For DTDs you can do it either way in the same file or in a separate file。

 For XSDs we always put those in a separate file。 Also notice that the XSD itself is in XML。

 It's using special tags。 These are tags that are part of the XSD language。

 but we are still expressing it in XML。 So we have two XML files， the data file and the schema file。

 To validate the data file against the schema file we can use again the XML lint feature。

 We specify the schema file， the data file， and when we execute the command we can see that the file validates correctly。

 So I'm now going to highlight four features of XML schema that aren't present in DTDs。

 One of them is typed values。 One of them is key declarations similar to IDs but a little bit more powerful。

 One is references which are again similar to pointers but a little more powerful and finally occurrence constraints。

 So let's start with types。 In our data we see that the price attribute is denoted with a string and when we had DTDs all attribute values were in fact strings。

 In XSDs we can say that we want to check that the values which are still look like strings actually conform to specific types。

 For example we can say that the price must be an integer。

 Again I'm not going to belabor the syntactic details but rather I'm just going to highlight the places in the XSD where we're declaring things of interest。

 So specifically here's where we declare the attribute price and we say that the type of price must be an integer。

 So our document validated correctly what if we change this 100 to be foo instead。

 Of course with a DTD this would be fine because all attributes are treated as strings but if we try to validate now we see an error specifically foo is not a value of the correct type。

 So let's change that foo back to 100 so that we validate correctly。 Next let's talk about keys。

 In DTD we were able to specify IDs。 IDs were globally unique values that could be used to identify specific elements。

 For example when we wanted to point to those elements using ID RATS。

 Keys are a little bit more powerful or more specific I should say。

 If you think about the relational model a key in the relational model is an attribute or set of attributes that must be unique for each tuple in a table。

 So we don't have tables or tuples right now but we do have elements and we often have repeated elements。

 So similarly we can specify that a particular attribute or component must be unique within every element of the same type。

 And we have two keys in our specification one key which we can see here for books and one for authors。

 Specifically we say for books that the ISBN attribute must be a key and we say for authors that the ident attribute must be a key。

 So let's go over to our data and let's start by looking at the authors。

 So if we change for example GU to HG then we should get a key violation because we'll have two authors that have the same ident attribute。

 Let's try to validate。 In fact we do correctly get a key validation。

 We also get a couple of other errors and those have to do with the fact that we're using these identities as the destination of what are effectively pointers or references。

 So let's change that back to GU make sure everything now validates fine and it does。

 Now let's make another change。 So we have the ident being the key here and we have the ISBN number being the key for books。

 What if we change the ISBN number to one of the values we used as a key for the authors say to HG。

 When we did something similar with DTDs we got an error because in DTDs IDs have to be globally unique。

 Here we should not get an error。 HG should be a perfectly reasonable key for books because we don't have another value that's the same。

 And in fact it does validate。 Now let's undo that change。 Next let's talk about references。

 So references allow us to have what are effectively typed pointers using the DTD。

 So they are called key ref and here we have an example。

 Let me just change this to the middle of the document。

 So one of the reference types that we've defined in our DTD is a pointer to authors that we're using in our books。

 Specifically we want to specify that this attribute here the auth ident has a value that is a key for the author elements。

 And we want to make sure it's author elements that it's pointing to and not other types of elements。

 Now the syntax for doing this in XML schema is rather detailed。

 It's all right here and just to give you a flavor this middle selector here is actually using the X-path language which we'll be learning later。

 But what it says is that when we navigate in the document down to one of these auth elements within that auth element the auth ident attribute is a reference to what we already defined as author keys。

 We've done something similar with books。 We have our book/remark/book ref that brings us down to this element here and there we specify that the book attribute must be a reference to a book key。

 And the book key was earlier defined to be the ISBN number。

 Again I know this is all complicated and the syntax is very clunky so I urge you to download the specification and spend time looking at it on your own。

 Now let's make a couple of changes to our document to demonstrate how the checking of these typed pointers works。

 For example let's change our first reference here to foo。

 Let's validate the document and we should get an error and indeed we do the author key ref is incorrect。

 Now let's change that foo to JW。 So originally it was JU but now we're going to have two authors both of whom refer to JW。

 Now this should not be a problem。 It's simply two pointers to the same author and we did not prohibit that in our XML schema specification and indeed our document validates。

 We'll change that one back and as the last change we'll change our book reference here to refer to JW。

 This should not validate because this time unlike with DTDs we've actually specified typed pointers。

 In other words we've specified that this pointer or this reference must be to a book element and not to an author element。

 So we'll validate and indeed it fails。 I've done that change and now let's move to the last feature that we're going to look at in this demonstration which is occurrence constraints。

 So in let me just bring up the first instance of it。

 In XML schema we can specify how many times an element type is allowed to occur。

 Specifically we can specify the minimum number of occurrences and the maximum number of occurrences。

 As a default if we don't specify for an element the min occurs or max occurs the default for both of them is one。

 So here for books we've said that we can have zero books and we can have any number。

 So this is the maximum flexibility， any number of elements。

 For authors we've also said we can have any number of authors。 That's in the actual database itself。

 Remember that our bookstore consists of a set of books and a set of authors。

 But we are going to specify something a little different for how many authors we have within a specific book。

 So let's continue to look at other cases where we've specified occurrence constraints。

 Here's the case where we're specifying how many authors we have within a book。 And again。

 this is really a lot of XML here。 So take your time when you're looking at it or for now just take my word for it。

 What we're specifying here is how many sub elements。

 how many off sub elements we have within each author's element。

 And here we have no min occurs specification only a max occurs。

 That means by default min occurs is one。 So what this is saying specifically is that every book has in its author sub element at least one off。

 but we can have any number of them。 That's the string unbounded。

 Looking at the remaining occurrence constraints， for remarks we have the minimum number of occurrences of zero。

 In other words， we don't have to have a remark and we haven't specified max occurs。

 So as a default max occurs is one。 So what we're saying here is that every book may have either no remark or exactly one remark。

 but it may not have more than that。 And there's a few more occurrence constraints that you can take a look at again as you browse the XML schema description on your own。

 Now let's make some changes in the document to test these occurrence constraints。

 So first let's remove the authors from our first book。 We won't remove the whole author sub element。

 but just the two off sub elements of authors。 We attempt to validate and we see that it doesn't validate。

 We're missing some child elements specifically the off child elements because we expected there to be at least one of them。

 Incidentally， if we took the entire author sub element out。

 we'll also get an error since we specified that books must have authors sub elements。

 So now we're missing the entire author's structure in that book and again we don't validate。

 Let's put the authors back。 And now let's take a look at the remark occurrence constraint。

 So we said that every book can have zero or one remarks。

 So let's just add another remark to this book。 Hi。 Actually remarks are allowed to be empty。

 In any case we've added a small remark。 We validate and we see that we have too many remarks again because we specified that every book can have at most one remark。

 So that concludes our demonstration of XML schema。 Again， it's been rather cursory。

 We've only covered a few of the constructs， but I did focus on the constructs that we have in XML schema that are not specified in DTDs。

 Finally， one more time I urge you to download the XSD and the document and play around with it yourself。

