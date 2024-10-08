# P15：08-01-xpath-intro.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 Now let's turn to the subject of querying XML。

![](img/0f5de7bb441237afcc827578b43efc02_1.png)

 First of all， let me say right up front that querying XML is not nearly as mature as querying relational databases。

 And there are a couple reasons for that。 First of all， it's just much， much newer。 Second of all。

 it's not quite as clean。 There's no underlying algebra for XML that's similar to the relational algebra for querying relational databases。

 Let's talk about the sequence of development of query languages for XML up until the present time。

 The first language to be developed was X-Path。 X-Path considers consists of path expressions and conditions。

 And that's what we'll be covering in this video once we finish the introductory material。

 The next thing to be developed was XSLT。 XSLT has X-Path as a component。

 but it also has transformations， and that's what the T stands for。

 And it also has constructs for output formatting。 As I've mentioned before。

 XSLT is often used to translate XML into HTML for rendering。 And finally。

 the latest language and the most expressive language is X-query。

 So that also has X-Path as a component， plus what I would call a full-featured query language。

 So it's most similar to SQL in a way， as we'll be seeing。

 The order that we're going to cover them in is first X-Path。

 and then actually second X-query and finally XSLT。 There are a couple of other languages。

 X-Link and X-pointer。 Those languages are， for specifying as you can see， links and pointers。

 they also use the X-Path language as a component。 We won't be covering those in this video。 Now。

 we'll be covering X-Path， X-query and XSLT。 In moderate detail。

 we're not going to cover every single construct of the languages。

 but we will be covering enough to write a wide variety of queries using those languages。



![](img/0f5de7bb441237afcc827578b43efc02_3.png)

 To understand how X-Path works， it's good to think of the XML as a tree。

 So I'd like you to bear with me for a moment while I write a little bit of a tree that would be the tree encoding of the bookstore data that we've been working with。

 So we would write as our root the bookstore element。

 and then we'll have sub-elements that would contain the books that are the sub-elements of our bookstore。

 We might have another book。 We might have over here a magazine。 And within the books， then we had。

 as you might remember， some attributes and some sub-elements。 We had， for example， the ISBN number。

 We had a write as an attribute here。 We had a price。 And we also had， of course。

 the title of the book。 And we had the authors， excuse me， over here。

 I'm obviously not going to be filling in the sub-element structure here。

 We're just going to look at one book as an example。

 The ISBN number we now are at the leaf of the tree。

 so we could have a string value here to denote the leaf， maybe 100 for the price， for the title。

 a first course in database systems。 Then our authors had further sub-elements。

 We had maybe two authors sub-elements here。 I'm abbreviating a bit below here， a first name。

 and a last name again， abbreviating。 So that might have been Jeff， Omen， and so on。

 I think you get the idea of how we render our XML as a tree。

 And the reason we're doing that is so that we can think of the expressions we have in X-Path as navigations down the tree。

 Specifically， what XML consists of is path expressions that describe navigation down and sometimes across and up a tree。

 And then we also have conditions that we evaluate to pick out the components of the XML that we're interested in。

 So let me just go through a few of the basic constructs that we have in X-Path。

 Let me just erase a few of these things here that got in my way。

 I'm going to use this little box and I'm going to put the construct in and then sort of explain how it works。

 So the first construct is simply a slash。 And the slash is for designating the root element。

 so we'll put the slash at the beginning of an X-Path query to say we want to start at the root。

 A slash is also used as a separator。 So we're going to write paths that are going to navigate down the tree and we're going to put a slash between the elements of the paths。

 All of this will become much clearer in the demo， so I'll try to go fairly quickly now so we can move to the demo itself。

 The next construct is simply writing the name of an element。 I've put X here， but we might。

 for example， write book。 When we write book in an X-Path expression。

 we're saying that we want to navigate， say if we're up here at the bookstore。

 down to the book sub element as part of our path expression。

 We can also write the special element symbol star and star matches anything。

 So if we write slash star， then we'll match any sub element of our current element。

 When we execute X-Path， there's sort of a notion as we're writing the path expressions of being at a particular place。

 So we might have navigated from book sort of book， and then we would navigate， say。

 further down to title， or if we put a star， then we'd navigate to any sub element。

 If we want to match an attribute， we write at and then the attribute name。 So， for example。

 if we're at the book and we want to match down to the ISBN number。

 we'll write ISBN in our query or path expression。 We saw the single slash for navigating one step down。

 There's also a double slash construct。 The double slash matches any descendant of our current element。

 So， for example， if we're here at the book and we write double slash， we'll match the title。

 the authors， the author， the first name， and the last name， every descendant。 And actually。

 we'll also match ourself。 So this symbol here means any descendant。

 including the element where we currently are。 So now I've given them a flavor of how we write path expressions。

 Again， we'll see lots of them in our demo。 What about conditions？

 If we want to evaluate a condition at the current point in the path。

 we put it in a square bracket and we write the condition here。 So， for example。

 if we wanted our price to be less than 50， that would be a condition we could put in square brackets if we were actually better be the attribute。

 if we're at this point in the navigation。 Now， we shouldn't confuse putting a condition in a square bracket between -- with putting a number in a square bracket。

 If we put a number in a square bracket， n， for example， if I write 3， that is not a condition。

 but rather it matches the nth sub element of the current element。 For example。

 if we were here at authors and we put off square bracket 2。

 then we would match the second off sub element of the authors。 There are many。

 many other constructs。 This just gives the basic flavor of the constructs for creating path expressions and evaluating conditions。

 X-Path also has lots of built-in functions。 I'll just mention two of them as somewhat random examples。

 There's a function that you can use in X-Path called "contains"。

 If you write "contains" and then you write two expressions。

 each of which has a string value -- this is actually a predicate --。

 will return true if the first string contains the second string。 As a second example of a function。

 there's a function called "name"。 If we write "name" in a path。

 that returns the tag of the current element in the path。 We'll see the use of functions in our demo。

 The last concept that I want to talk about is what's known as "navigation axes"。

 There's 13 axes in X-Path。 What an axis is is sort of a keyword that allows us to navigate around the XML tree。

 For example， one axis is called "parent"。 You might have noticed that when we talked about the basic constructs。

 most of them were about going down a tree。 If you want to navigate up the tree。

 then you can use the parent axis that tells you to go up to the parent。

 There's an axis called "following sibling"。 You'll see how that works when we get to the demo。

 The following sibling says "match" -- all of the following siblings of the current element。

 If we have a tree and we're sitting at this point in the tree。

 then the following sibling axis will match all of the siblings that are after the current one in the tree。

 There's an axis called "descendants"。 Descendants， as you might guess。

 matches all of the descendants of the current element。

 It's not quite the same as "slash/slash" because as a reminder。

 "slash/slash" also matches the current element as well as the descendants。 Actually， as it happens。

 there's a navigation axis called "descendants and self" that's equivalent to "slash/slash"。

 By the way， there's also one called "self" that will match the current element。

 And that may not seem to be useful， but we'll see uses for that， for example。

 in conjunction with the name function that we talked about up here。

 that would give us the tag of the current element。 Just a few details to wrap up。

 XPath queries technically operate on and return a sequence of elements。

 That's their formal semantics。 There is a specification for our XML documents and XML streams mapped to sequences of elements。

 and you'll see that it's quite natural。 When we run an XPath query。

 sometimes the result can be expressed as XML， but not always， but as we'll see again。

 that's fairly natural as well。 So this video has given an introduction to XPath。

 We've shown how to think of XML data as a tree， and then XPath as expressions that navigate around the tree and also evaluate conditions。

 We've seen a few of the constructs for path expressions， for conditions。

 We've seen a couple of built-in functions， and I've introduced the concept of navigation axes。

 But the real way to learn and understand XPath is to run some queries。

 So I urge you to watch the next video， which is a demo of XPath queries over our bookstore data。

 and then try some queries yourself。

![](img/0f5de7bb441237afcc827578b43efc02_5.png)