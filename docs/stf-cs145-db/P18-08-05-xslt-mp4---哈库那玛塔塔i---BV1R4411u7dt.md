# P18：08-05-xslt.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 In this video， we'll introduce querying XML data using XSLT。



![](img/ddea30cfec8b93a1142e2df3d1091acb_1.png)

 As a reminder， querying XML data is not nearly as mature as querying relational data。

 due to it being much newer and not having a nice underlying algebra， like the relational algebra。

 We already talked about XPath， which was the first language developed for querying XML data。

 And we've also talked about XQuery， which was actually developed after XSLT。

 but it's similar to XPath in its style， where XSLT， which we're going to cover in this video。

 is actually quite different。 XSL stands for the extensible style sheet language。

 and it was introduced originally， but soon extended to include transformations。

 and XSLT is currently much more widely used than XSL。

 Here's how we can think of XSLT as a query language。 We have an XSLT processor。

 and we feed to that processor our XML data in the form of a document or a stream。

 and we also give the processor a specification in XSLT， which， by the way。

 is expressed using the XML format。 The processor takes the data and the specification。

 and it transforms the data into a result， which is also expressed as an XML document or stream。 Now。

 if we think about traditional database query processing， there's actually a natural mapping。

 If we think even about relational processing， we have a query processor and a database。

 We feed the data to the query processor。 We feed the query to the query processor as well。

 and out comes the answer。 So XSLT processing， although it really is through transformations。

 can be thought of very much like querying a database。

 So even though XSLT can be thought of as a query language。

 the query paradigm itself is quite different from what we're used to。



![](img/ddea30cfec8b93a1142e2df3d1091acb_3.png)

 with SQL or even with XPath or XQuery。 It's based fundamentally on the notion of transforming the data。

 and that transformation occurs with rules。 To understand what the rules do and how the transformations work。

 it's again very instructive to think of the XML as a tree。

 So let's take our bookstore data and again make it a tree as we did before when we were first learning about XPath。

 So we have some books sub-elements， and we have a magazine sub-element。

 And I won't be elaborating all of these。 We'll just imagine sub-trees here。 With our book。

 we have a title， and we have some authors。 The title might be our leaf。

 so we'll have a first course in database systems， for example。

 whereas our authors may have authors sub-elements。 And within those authors sub-elements。

 we might have first name and last name abbreviated here with string values for those。

 And of course more authors sub-elements there as well。

 So that gives the basic idea of a tree structure of XML exactly as we've seen before。

 So now let's see what happens with XSLT in light of this tree structure。

 So the first thing that we have is a concept of matching a template and replacing it。

 So the idea in XSLT is that we can write an expression that finds portions of the XML tree based on template matching。

 For example， we might find books that have certain authors， and once we find those。

 we'll actually replace the entire sub-tree with the result of what we put in our template。

 For example， we might decide that we want to pick the title here and replace this entire sub-tree with the title。

 Or we might match down to our authors， and we might find our first name and last name and say replace this entire author sub-element with the concatenation of the first and last name。

 Again， the idea being that you write templates that match within the tree using in fact X-path。

 as we'll see as one of the portions of writing those templates and then replace that portion of the tree。

 We can also do that recursively。 So we can， for example。

 decide that we're going to replace this book with a different element and then recursively apply our templates to its children。

 We'll see that in a demo。 It takes a little getting used to again。

 The XSLT language has the ability to extract values。

 and again it often uses X-path expressions in order to do that。

 It also has some programming language like constructs。 It has a for each， so we can do iteration。

 and it has conditionals， so we can do if。 All of these will be much better seen in the demo。

 Finally， I'll have to mention that there's some somewhat strange behavior having to do with white space in XML data and some default behavior。

 which we'll see in the demo。 And there's also an implicit priority scheme when we have multiple templates that can all match the same elements。

 So let's move directly to the demo。 We're again going to be using our same bookstore data。

 and we'll see a number of XSLT examples。 Even more than X query or X-path。

 our examples will not be exhaustive， but they will give a flavor of the language and you'll be able to express some fairly powerful queries using just what we show in the videos。



![](img/ddea30cfec8b93a1142e2df3d1091acb_5.png)

 Now let's see XSLT in action。 Let me first explain what we have on the screen。

 In the upper left window， we have the document that we'll be querying over。

 It's the exact same bookstore data that we've been using for all of our examples。

 so I'm actually going to make that a lot smaller so that we can see our templates better。

 In the upper right are our XSLT templates。 And every example we're going to do is going to have as opening。

 closing a style sheet with some parameters that tell us how we'd like to display our results。

 And then I'll be putting different templates between those opening and closing tags。

 Notice again that XSLT is expressed using XML。 Once we have our data and our set of template matching rules。

 we'll run our transformation and in the bottom we'll see our result。

 So you can think of it as a query in the upper right， the data in the upper left。

 and the result displayed in the bottom。 Now even more than X query。

 it's not going to be possible to explain every single intricacy of the templates that we're going to write。

 So I again encourage you to pause the video to take a look as well as download the data file and the transformation file so that you can experiment with them yourself。

 Our first example is going to do some very simple template matching。

 It's going to look for book sub elements and when it finds them。

 it's going to replace those books sub elements with a book title element。

 the value of the title component， the book and a closing tag book title。

 And it's similarly going to match magazines sub elements and replace those magazines sub elements with an element that's an opening tag of magazine title。

 the value of the title sub element of the magazine and the closing tag。 So again。

 the templates will look through the XML tree， they will match the sub elements and the tree will match the books sub elements and the magazines sub elements。

 and for each one it will replace those sub elements with the expression， in this case。

 with our opening and closing tags that have changed and the value of the title。

 We run the transformation and we see indeed that the result are our four book titles。

 now an opening and closing tag that are book title and our four magazine titles。

 For our next example， we're going to only match books that satisfy a condition。

 We do that by in our matching expression using X-Path。

 Now there's one small strange thing here which is we can't write the less than symbol。

 we actually have to use the escape symbol for less than。 But otherwise。

 this template finds books whose price attribute is less than 90。

 just like we do in X-Path using the square brackets for conditions， and when it matches those books。

 what it does here is it copies those books。 So this is an important construct that says if I match the book。

 I'll copy the book， I'll select dot which selects the current element。 So in effect。

 it's saying find the books and retain them exactly as they are。

 Let's run the transformation and take a look at what we get。



![](img/ddea30cfec8b93a1142e2df3d1091acb_7.png)

 We can see that we got this book because its price is 85 and we have another book whose price is 50 and another book whose price is 25。

 but we do see something a little bit strange here。 We got our books。

 but we also have these strings here， these long bits of text that we don't really know where they came from。

 Well， this is one of the peculiarities of XSLT。

![](img/ddea30cfec8b93a1142e2df3d1091acb_9.png)

 When you have elements in your database that aren't matched by any template。

 what XSLT will do is actually return the concatenation of the string leaf or text leaf values of those elements。

 I know it seems kind of strange， there's actually a simple fix for that。

 We're going to add a second template that matches those text elements and for those returns nothing。

 So here we've added the template and let me explain。

 What we're matching here is elements that satisfy the text predicate。

 so that will match those leaf text elements。 And when we write a template that has no body。

 so we open the template and then we close the template with no body at all。

 that says match the element and then don't replace it with anything at all。

 So this is very useful construct， the templates that don't have a body for getting rid of portions of the data we're not interested in。

 So let's run the transformation now and take a look at the result and now when we scroll down we see that all of that extraneous。

 all of the extraneous text that we saw in the previous example is now gone。



![](img/ddea30cfec8b93a1142e2df3d1091acb_11.png)

![](img/ddea30cfec8b93a1142e2df3d1091acb_12.png)

 So as we've seen， XSLT works by defining templates that are matched against the data。

 When a portion of the data is matched by a template， the template says what to do。

 We might replace that portion of the data with something different。

 We might just remove that portion of the data from the answer or we might just copy it over into the answer。

 Now let's explore what happens when we have portions of the data that are matched by more than one template in our XSLT specification。

 So here we're going to have three templates。 The first two templates both match book elements。

 The first template says when we match a book element just throw it away。 Again。

 this is an example of the template when we don't have a body that says eliminate the matched elements from the answer。

 The second template says to do exactly the opposite。 It says when we match a book sub element。

 keep that book sub element exactly as it is。 As a reminder。

 this body here says copy the current element into the result。

 Our third template matches magazines and this one we just have one and it says copy the magazine into the result。

 So let's go ahead and run this transformation and see what happens。

 Well first of all we got an ambiguous rule match。 So that's good。

 The system recognized that we have two different rules that are matching the same element。



![](img/ddea30cfec8b93a1142e2df3d1091acb_14.png)

 But then it did decide to give us a result。 So let's take a look at what happened。

 It did return in fact all of the books in the database as well as all of the magazines。

 So we can see that it shows to use the second template instead of the first template when we had the ambiguity。

 So let's try an experiment。 Let's take our two book templates and let's just reverse their order。

 So now we have the one that copies first and the one that eliminates second。

 Let's run the transformation and indeed something changed。 We no longer got the books。

 So what we can deduce from that is that when we have two templates that both match。



![](img/ddea30cfec8b93a1142e2df3d1091acb_16.png)

 and we get this ambiguity warning it still does the transformation and it chooses the second of the matching transformations。

 Actually it turns out not to be quite that simple。 It doesn't always choose the second one。

 In this example we're going to change our first template to match only books whose price is less than 90。

 So we'll use the same syntax we used for that before。

 We have to escape that less than character like this。 Less than 90。 Close our square bracket。

 So now our first transformation says when you find books that are less than 90 let's return them。

 And when we find any book let's not return it。 So again we're going to have some ambiguity。

 Let's run the transformation。 Well we actually didn't get an ambiguity error this time or warning。

 And the reason is that XSLT actually has a built in notion of some templates being more specific than others。

 And when a template is more specific it is considered the higher priority template。

 So what happened when we ran this particular transformation is the books that where the price is less than 90 were matched by the first template。

 and because that one is considered more specific they were not matched by the second template。



![](img/ddea30cfec8b93a1142e2df3d1091acb_18.png)

 So we can see below that we did get back all of the books that are less than 90 and none of the other books。



![](img/ddea30cfec8b93a1142e2df3d1091acb_20.png)

 And again we got back all of our magazines。 So let's make one last change to experiment。

 Let's take our second book and let's add to it a simple condition that's satisfied by every book which is the condition that the book has a title sub element。

 Again this is X-path。 Now perhaps our two rules have equivalent specificity in which case we would again have ambiguity。

 Let's just delete our result here and then let's run the transformation and see what happens。

 Indeed now we have an ambiguous rule match because both of these templates have a condition so they are considered equivalent again just like when neither of them had a condition。

 And now that they are considered equivalent again the second one is going to take precedence because as you can see we didn't get any books in our result。

 So even though we have some books that are less than 90 those books also have a title so those books were matched by the second template and they were not returned。

 So what you can see from these examples is that you do need to be very careful when you write XSLT programs or queries where multiple templates will match the same data。

 Now let's look at a couple of different ways of copying our entire input data as the result of our query。

 Our first example is the simplest one。 We write a template that matches the root element of the document。

 As you may remember from X-path the single slash is the root element。

 And then as the body we have that copy of template that copies the entire current element。

 Let's run the transformation and we will see that we get our entire database as a result。

 Incidentally we could change that slash to be bookstore and we do exactly the same thing since our bookstore is our root element。

 We can delete this， run the transform and once again we get the entire database as our result。

 Now I'm going to show actually what's a much more complicated way of copying the entire document but it uses an important kind of template that we'll see in other contexts。

 This template is our first example of recursively applying templates to our result。

 What we have here is a template that matches absolutely anything in XML data。

 This is actually an X-path expression that says match an element with star。

 That means any element tag。 Any attribute at star or any text leaf of the XML data。

 So again this or construct here is seen quite frequently in XSLT specifications to match just anything at all in the data。

 When anything at all is matched that element of the data is copied and then the templates are applied recursively to everything that you have。

 So it may be best just to take my word for it or you can spend some time on your own thinking about exactly why this works but again the idea is that we match any type of element in our XML element attribute or text and we copied that object and then we apply the templates to all of its sub elements recursively again copying them。

 Now obviously this is not the easiest way to copy an entire document。

 We saw the easiest way to do it with our previous example but we'll soon see why this particular template is valuable。

 When we run it of course we get back the entire document。

 Now the reason that this type of template is valuable is that we can use this as one of our templates but then add additional templates that give us exceptions to copying the whole document。

 And that will allow us to copy the whole document except with changes in certain parts。

 And what I'm adding here actually is a whole bunch of additional templates。

 So the first one says apply all templates recursively to the entire document。

 The second says when you find while you're applying them recursively that you're at an attribute called ISBN will change that to a sub element。

 So we'll match the ISBN attribute will change it to a sub element similarly to what we saw before by giving an open tag ISBN and the value of the current element。

 We'll similarly take our attributes our price attributes and change them to sub elements and our additions our months and our years in our magazine。

 And last of all we'll also make a change to our authors when we match an author instead of having sub elements we'll convert those sub elements to be attributes the last name attribute and the first name attribute。

 So let's run the transformation and we'll see our data is now significantly restructured。



![](img/ddea30cfec8b93a1142e2df3d1091acb_22.png)

 We have our bookstore we have our books but our ISBN numbers are now sub elements and in our authors the last names and first names are attributes and all of the books are restructured in that fashion and our magazines again have attributes restructured as sub elements。

 Now let's see what would have happened if we ran this XSLT specification but we didn't have this megatep late at the beginning that does the recursive application of templates to the entire database。



![](img/ddea30cfec8b93a1142e2df3d1091acb_24.png)

![](img/ddea30cfec8b93a1142e2df3d1091acb_25.png)

 When we run the transformation now well we get a kind of surprising result we won't try to analyze it in its entirety it's a combination of only matching automatically sub elements and not attributes and furthermore dumping out all the text leaves like we saw in an earlier example。



![](img/ddea30cfec8b93a1142e2df3d1091acb_27.png)

 So again presuming that we would not want this to be a result that shows the necessity of including the sort of generic template that matches every type of object in the database and recursively applies templates to its children。



![](img/ddea30cfec8b93a1142e2df3d1091acb_29.png)

 Now let's switch gears entirely。 What we're going to do in this transformation is effectively write a program。

 We're going to use the for each and sorting and if statement and the program is furthermore going to take the XML data and it's going to transform it into HTML which we can then render in a browser。

 So it's just one template that matches the root element of our document and once that root element is matched it spits out the tag HTML it sets up a table so again we're actually writing the result here and it puts some headers for the table and then we see a for each that says we're going to run the body of the object。

 The body of the for each for each book in the database we're going to sort the result by its price。

 If the price is less than 90 then we're going to generate a row in the table and that row is going to be set up with italics for the title and it's going to give the value of the price。

 It's going to close the row and we're going to close all the tags。

 So again this is quite different in a couple of ways。

 First of all that is written more in a programmatic style and second of all that the result is actually going to be HTML。



![](img/ddea30cfec8b93a1142e2df3d1091acb_31.png)

 Let's run the transformation and we can see the result here which is indeed HTML。

 In fact we can take this very HTML and we can render it in a browser and see how nice it looks。



![](img/ddea30cfec8b93a1142e2df3d1091acb_33.png)

 And here it is。 We can see very beautifully formatted the three books that cost less than 90 sorted by price with the title and italics all formatted in an HTML table。

 And that was with not a very complicated XSLT program so it's not surprising that XSLT is used frequently for translating data expressed in XML to HTML format for rendering as well as being used as a query language。



![](img/ddea30cfec8b93a1142e2df3d1091acb_35.png)

 Our last two examples are back to a more traditional template matching style。

 Again we're going to start with this recursive template match that matches everything in the database。

 That means we're going to copy everything over except we're going to make one type of change。

 Specifically we're going to change， we're going to take Jennifer out of the database and then we're going to change WIDM to Ms。

 WIDM。 So every time place where we have Jennifer's the first name and WIDM at the last time will end up with just a name Ms。

 WIDM。 Specifically we do it with two templates。 The first template says when we find a first name where the data in that first name equals Jennifer。

 So we're again using the dot to refer to the current element the data is a built in function。

 So a first name that's equal to Jennifer。 When we match that we want to。

 we'll actually return nothing。 There's no body in this template so that will remove that element。

 Now you might wonder why we didn't just write a condition that said first name equals Jennifer。

 The problem is to write that condition the current element would be the parent and we don't want to remove the parent。

 We actually want to remove the first name itself。 In addition to removing first names that are Jennifer will also match last name templates where the value is WIDM and we will replace those with an opening tag name。

 the string Ms。 WIDM and a closing tag name。

![](img/ddea30cfec8b93a1142e2df3d1091acb_37.png)

 So let's run the transformation and let's take a look。

 And we will see in the case where the author was Jennifer WIDM， it's now the single element name Ms。

 WIDM and we should see that occur a few other times in the database as well。



![](img/ddea30cfec8b93a1142e2df3d1091acb_39.png)

 As our very last example， let's perform the same transformation but let's do it with just one template。

 What we'll do is we'll look for author sub-elements where the first name equals WIDM。

 Now we don't need to use data。 So first name equals WIDM and we'll take those entire author sub-elements and we'll replace them with an author sub-element where the name is WIDM。

 So we need to put author here。 Let's get rid of this automatically generated closing tag。

 We want it to be over here。 We'll get rid of this first template。

 So again we're going to make exactly the same change what we're going to do with a single template。

 It's going to look for authors where the first name is WOOPS that are make that Jennifer and it's going to replace them with the author sub-element with just Ms。

 WIDM。 We run the transformation and let's take a quick look at what we got and we again see exactly the same result with a somewhat simpler program。



![](img/ddea30cfec8b93a1142e2df3d1091acb_41.png)

![](img/ddea30cfec8b93a1142e2df3d1091acb_42.png)

 That concludes our demonstration of XSLT。 Again we've shown only some of the constructs。

 We haven't gone into great detail or walked through the syntax。 XSLT is very powerful。

 We've seen quite a few different things。 We've also seen a little bit of non-intuitive behavior。

 We have to be a little careful with white space。 We have to be a little careful when we have multiple templates that match the same data。

 But once we get it all figured out it can be quite powerful for transforming data and for querying data。



![](img/ddea30cfec8b93a1142e2df3d1091acb_44.png)