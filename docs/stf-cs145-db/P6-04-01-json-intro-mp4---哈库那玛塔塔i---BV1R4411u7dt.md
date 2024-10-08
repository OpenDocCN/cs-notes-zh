# P6：04-01-json-intro.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 This video introduces JSON。 Let's start by talking about its pronunciation。

 Some people call it JSON， and some call it JSON。 I did a little bit of investigation and discovered that the original developer of JSON calls it JSON。

 so I'll do that too。 Like XML， JSON can be thought of as a data model。

 an alternative to the relational data model that is more appropriate for semi-structured data。

 In this video， I'll introduce the basics of JSON， and I'll also compare JSON to the relational data model。

 and I'll compare it to XML。 But it's not crucial to have watched those videos to get something out of this one。

 Now， among the three models， the relational model XML in JSON， JSON is by a large margin the newest。

 and it does show there aren't as many tools for JSON as we have for XML and certainly not as we have for relational。



![](img/6a2fc62e24a1743a802a9119373e7f3a_1.png)

 JSON stands for JavaScript Object Notation， although it's evolved to become pretty much independent of JavaScript at this point。

 The little snippet of JSON in the corner is right now mostly for decoration。

 We'll talk about the details in just a minute。 Now。

 JSON was designed originally for what's called serializing data objects that is taking data objects that are in a program and sort of writing them down in a serial fashion。

 typically in files。 One thing about JSON is that it is human readable。

 similar to the way XML is human readable， and it's often used for data interchange。

 So for writing out， say， the objects in a program so they can be exchanged with another program and read into that one。

 Also， just more generally， because JSON is not as rigid as the relational model。

 it's generally useful for representing and for storing data that doesn't have rigid structure that we've been calling semi-structured data。

 As I mentioned， JSON is no longer closely tied to JavaScript。

 Many different programming languages do have parsers for reading JSON data into the program and for writing out JSON data as well。



![](img/6a2fc62e24a1743a802a9119373e7f3a_3.png)

 Now let's talk about the basic constructs in JSON， and as we will see。

 these constructs are recursively defined。 We'll use the example JSON data shown on the screen。

 and that data is also available in a file for download from the website。

 The basic atomic values in JSON are fairly typical。 We have numbers， we have strings。

 we also have boolean values， although there are none of those in this example that's true and false and null values。

 There are two types of composite values in JSON， objects and arrays。

 Objects are enclosed in curly braces， and they consist of sets of label value pairs。



![](img/6a2fc62e24a1743a802a9119373e7f3a_5.png)

 For example， we have an object here that has a first name and a last name。 We have a bigger。

 let's say， object here that has ISBN， price， edition and so on。 When we do our JSON demo。

 we'll go into these constructs in more detail。 At this point， we're just introducing them。

 The second type of composite value in JSON is arrays。

 and arrays are enclosed in square brackets with commas between the array elements。

 actually had commas in the objects as well， and arrays are lists of values。 For example。

 we can see here that authors is a list of author objects。 Now。

 I mentioned that the constructs are recursive， specifically the values inside arrays can be anything。

 They can be other arrays or objects， base values， and the values making up the label value pairs in objects can also be any composite value or a base value。

 And I did want to mention， by the way， that sometimes this word "label" here for label value pairs is called "property"。

 So just like XML， JSON has some basic structural requirements in its format。

 but it doesn't have a lot of requirements in terms of uniformity。

 We have a couple of examples of heterogeneity in here。 For example。

 this book has an addition and the other one doesn't。

 This book has a remark and the other one doesn't， but we'll see many more examples of heterogeneity when we do the demo and look into JSON data in more detail。

 Now let's compare JSON and the relational model。 We will see that many of the comparisons are fairly similar to when we compared XML to the relational model。

 Let's start with the basic structures underlying the data model。

 So the relational model is based on tables we set up， structure of tables， a set of columns。

 and then the data becomes rows in those tables。 JSON is based instead on sets。

 the sets of label value pairs and arrays， and as we saw they can be nested。

 One of the big differences between the two models， of course， is the schema。

 So the relational model has a schema fixed in advance。

 You set it up before you have any data loaded and then all data needs to conform to that schema。

 JSON on the other hand typically does not require a schema in advance。 In fact。

 the schema and the data are kind of mixed up together just like in XML。

 and this is often referred to as self-describing data。

 where the schema elements are within the data itself。

 And this is of course typically more flexible than the relational model。

 though there are advantages to having schema as well， definitely。 As far as queries go。

 one of the nice features of the relational model is that there are simple。

 expressive languages for querying the database。 In terms of JSON。

 although a few things have been proposed， at this point there's nothing widely used for querying JSON data。

 Typically JSON data is read into a program and it's manipulated programmatically。

 Now let me interject that this video is being made in February 2012。

 So it is possible that some JSON query languages will emerge and become widely used。

 There's just nothing used at this point。 There are some proposals。 There's a JSON path language。

 JSON query， a language called Jackal。 It may be that just like XML。

 the query languages are going to follow the prevalent use of the data format or data model。

 but that has not happened yet as of February 2012。 How about ordering？

 One aspect of the relational model is that it's an unordered model。 It's based on sets。

 And if we want to see relational data in sorted order， then we put that inside a query。

 In JSON we have arrays as one of the basic data structures and arrays are ordered。 Of course。

 there's also the fact like XML that JSON data is often is usually written to files and files themselves are naturally ordered。

 But the ordering of data in files usually isn't relevant。 Sometimes it is， but typically not。

 Finally， in terms of implementation for the relational model。

 there are systems that implement the relational model natively。 They're very mature。

 generally quite efficient and powerful systems。 For JSON。

 we haven't yet seen standalone database systems that use JSON as their data model。 Instead。

 JSON is more typically coupled with programming languages。 One thing I should add， however。

 is that JSON is used in no SQL systems。 We do have videos about no SQL systems。

 You may or may not have watched those yet。 There's a couple of different ways that JSON is used in those systems。

 One of them is just as the format for reading data into the systems and writing data out from the systems。

 The other way it's used is that some of the no SQL systems are what are called document management systems。

 where the documents themselves may contain JSON data and then the systems will have special features。



![](img/6a2fc62e24a1743a802a9119373e7f3a_7.png)

 for manipulating the JSON in the documents that are stored by the system。

 Now let's compare JSON and XML。 This is actually a hotly debated comparison right now。

 There is significant overlap in the uses of JSON and XML。

 Both of them are very good for putting semi-structured data into a file format and using it for data interchange。

 Because there's so much overlap in what they're used for。

 it's not surprising that there's significant debate。 I'm not going to take sides。

 I'm just going to try to give you a comparison。 Let's start by looking at the verbosity of expressing data in the two languages。

 It is the case that XML is in general a little bit more verbose than JSON。

 The same data expressed in the two formats will tend to have more characters in XML than in JSON。

 You can see that in our examples because our big JSON example is actually pretty much the same data that we used when we showed XML。

 The reason for XML being a bit more verbose largely has to do actually with closing tags and some other features。

 I'll let you judge for yourself whether the somewhat longer expression of XML is a problem。

 Second is complexity。 Here too most people would say that XML is a bit more complex than JSON。

 I'm not sure I entirely agree with that comparison。

 If you look at sort of the subset of XML that people really use， you've got attributes。

 sub-elements and text， and that's more or less it。

 If you look at JSON you've got your basic values and you've got your objects and your arrays。

 I think the issue is that XML has a lot of extra stuff that goes along with it。

 So if you read the entire XML specification it'll take you a long time。

 JSON you can con-grasp the entire specification a little bit more quickly。

 Now let's turn to validity。 By validity I mean the ability to specify constraints or restriction or schema on the structure of data in one of these models and have it enforced by tools or by a system。

 Specifically in XML we have the notion of document type descriptors or DTDs。

 We also have XML schema which gives us SSDs， XML schema descriptors。

 And these are schema like things that we can specify and we can have our data check to make sure it conforms to the schema。

 And these are I would say fairly widely used at this point for XML。

 For JSON there's something called JSON schema and you know similar to XML schema it's a way to specify the structure and then we can check that JSON conforms to that structure。

 And we will see some of that in our demo。 The current status February 2012 is that this is not widely used at this point but again it could really just be evolution。

 If we look back at the XML as it was originally proposed probably we didn't see a whole lot of use of DTDs and in fact not X SSDs for sure until later on。

 So we'll just have to wait and see whether JSON evolves in a similar way。

 Now the programming interface is where JSON really shines。

 The programming interface for XML can be fairly clunky。 The XML model。

 the attributes and sub elements and so on don't typically match the model of data inside a programming language。

 In fact that's something called the impedance mismatch。

 The impedance mismatch has been discussed in database systems actually for decades because one of the original criticisms of relational database is that it's not a problem。

 The difference of relational database systems is that the data structures used in the database specifically tables didn't match directly with the data structures in programming languages。

 So there has to be some manipulation at the interface between programming languages and the database system and that's the mismatch。

 So that same impedance mismatch is pretty much present in XML where in JSON it's really a more direct mapping between many programming languages and the structures of JSON。

 Finally let's talk about querying。 I already touched on this a bit but JSON does not have any mature widely used query languages at this point。

 For XML we do have XPath， we have XQuery， we have XSLT。

 maybe not all of them are widely used but there's no question that XPath at least and XSLT are used quite a bit。

 As far as JSON goes there's been a proposal called JSONPath that looks actually quite a lot like XPath but maybe it'll catch on。

 There's something called JSONQuery， it doesn't look so much like XMLQuery， I mean XQuery。

 And finally there has been a proposal called Jackal for the JSON query language but again as of February 2012 all of these are still very early so we just don't know what's going to catch on。



![](img/6a2fc62e24a1743a802a9119373e7f3a_9.png)

 So now let's talk about the validity of JSON data。

 So do JSON data that's syntactically valid simply needs to adhere to the basic structural requirements？

 As a reminder that would be that we have sets of label value pairs。

 we have arrays of values and our base values are from predefined types。

 And again these values here are defined recursively。

 So we start with a JSON file and we send it to a parser。

 the parser may determine that the file has syntactic errors or if the file is syntactically correct then it can be parsed into objects in a programming language。

 Now if we're interested in semantically valid JSON that is JSON that conforms to some constraints or a schema then in addition to checking the basic structural requirements we check whether JSON conforms to the specified schema。

 If we use a language like JSON schema for example we put a specification in as a separate file and in fact JSON schema is expressed in JSON itself as we'll see in our demo。

 We send it to a validator and that validator may find that there are syntactic errors or it may find that there are some semantic errors so the data could be correct syntactically but not conform to the schema。

 If it's both syntactically and semantically correct then it can move on to a parser where we'll be parsed again into objects in a programming language。



![](img/6a2fc62e24a1743a802a9119373e7f3a_11.png)

 So to summarize JSON stands for JavaScript Object Notation。

 It's a standard for taking data objects and serializing them into a format that's human readable。

 It's also very useful for exchanging data between programs and for representing and storing semi-structured data in a flexible fashion。

 In the next video we'll go live with a demonstration of JSON。 We'll use a couple of JSON editors。

 We'll take a look at the structure of JSON data when it's syntactically correct。

 We'll demonstrate how it's very flexible when our data might be irregular and we'll also demonstrate schema checking using an example of JSON schema。



![](img/6a2fc62e24a1743a802a9119373e7f3a_13.png)