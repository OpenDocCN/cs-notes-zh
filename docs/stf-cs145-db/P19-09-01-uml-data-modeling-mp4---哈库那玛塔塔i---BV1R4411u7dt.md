# P19：09-01-uml-data-modeling.mp4 - 哈库那玛塔塔i - BV1R4411u7dt

 This video talks about data modeling in UML。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_1.png)

 the unified modeling language。 The area of data modeling consists of how we。

 represent the data for an application。 We've talked a great length about the relational data model。

 It's widely used and we have， good design principles for coming up with relational schemas。

 We also talked about XML as a data model。 XML is quite a bit newer and there are no design principles。

 yet that are analogous to the ones for the relational model。

 But frequently when people are designing a database。

 they'll actually use a higher level model that's specifically for database design。

 These models aren't implemented by the database system。

 rather they are translated into the model of the database system。 So let's draw a picture of that。

 Let's suppose that we have a relational database management system。

 which is abbreviated RDBMS often and I'll draw that as a disk just out of tradition。

 So if we create a database in a relational system， the database is going to consist of relations。

 But instead of designing relations directly， the database designer will draw that up here。

 will use instead a higher level design model。 That model will then go through a translator and this can often be。

 an automatic process that will translate the higher level model。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_3.png)

 into the relations that are implemented by the database system。

 So what are these higher level models？ Historically， for decades in fact。

 the entity relationship model， also known as the ER model， was a very popular one。

 But more recently， the unified modeling language has become popular。

 for higher level database design。 The unified modeling language is actually a very large language。

 not just for database design， but also for designing programs。

 So what we're going to look at is the data modeling subset of UML。

 Both of these design models are fundamentally graphical。 So in designing a database。

 the user will draw boxes and arrows， perhaps other shapes。

 And also both of them can be translated generally automatically， into relations。

 Sometimes there might be a little human intervention， in the translation process。

 but often that's not necessary。 So in the data modeling subset of UML。

 there are five basic concepts-- classes， associations， association classes， subclasses。

 and composition and aggregation。 And we're just going to go through each one of those concepts。

 in turn with examples。 So the class concept in UML is not specific to data modeling。

 It's also used for designing programs。 The class consists of a name for the class。

 attributes of the class， and methods in the class。 And that's probably familiar to you， again。

 from programming。 For data modeling specifically， we add to the attributes。

 the concept of a primary key。 And we drop the methods that are associated。

 since we're focusing really on the data modeling at this point。 So we'll be drawing our examples。

 as usual， from a imaginary college admissions database。

 with students and colleges and students applying， to colleges and so forth。 So one of our classes。

 not surprisingly， will be the student class。 And in UML， we'll draw a class as a box like this。

 And at the top， we put the name of the class。 And then we put the attributes of the class。

 So let's suppose that we'll just keep it simple。 We'll have a student ID， a student name。

 and for now， the student's GPA。 And down here in UML would be the specification of the methods。

 Again， we're not going to be focusing on methods， since we're looking at data modeling and not。

 the operations on the data。 And so one difference is that we'll have no methods。

 Another is that we specify a primary key if we wish， and that's specified using the terminology PK。

 So we'll say that the student ID， in this case， is the primary key。

 And just as in keys in the relational model， that means that when we have a set of objects。

 for the student class， each object， will have a unique student ID。

 There will be no student IDs repeated across objects。 In our college application database。

 we're also likely to have a class for colleges。 So we'll have a class that we call college。

 And for now， we'll make the attributes of that class， be just the college name and the state。

 And again， in full UML， there might， be some methods down here。 And we'll make the college name。

 in this case， be the primary key。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_5.png)

 So we're assuming now that college names themselves， are unique。 So that's it for classes。

 Pretty straightforward。 They look a lot like relations。 And of course。

 they will translate directly to relations。 Next， let's talk about associations。

 Associations capture relationships， between objects of two different classes。 So let's suppose。

 again， that we have our student class。 And I won't write the attributes now。

 I'll just write it like that。 And we have our college class in our UML design。

 If we want to have a relationship that students apply， to colleges。

 we write that just as a line between the students， and the college classes。

 And then we give it a name。 So we'll call it applied。

 And that says that we have objects in the student class。

 and objects that are in the college class that， are associated with each other through the applied association。

 If we want to introduce a directionality， to the relationships， to say that students are applying。

 to colleges， we can put in a little arrow there。 That's part of the UML language。

 Although we'll see that it doesn't really， make much difference when we end up。

 translating UML designs to relations。 When we have associations between classes。

 we can specify what we call the multiplicity of those。

 And that talks about how many objects of one class， can be related to an object of another class。

 So we'll see that we can capture concepts like one one， and many one and so forth。

 So let's look specifically at how we specify those， in a UML diagram。 And for now。

 I'll just use two generic classes。 So let's say I have a class C1 and I have a class C2。

 And let's say that I have an association between those two， classes， so that would be a line。

 And I could give that a name。 Let's call it A。 Let's say that I。

 want to specify that each object in class C1--， I'm just going to write those objects kind of as dots here。

 below the class specification。 Let's say I wanted to say that each one of those。

 is going to be related to at least M， but at most N objects， in class C2。

 So here are class C2 objects。 I'm going to have this kind of fan out in my relationship。

 To specify that in the UML diagram， I write that as M dot dot N on the right side。

 of the association line。 And again， that's saying each object， then， in C1。

 will be related to between M and N objects of C2。 Now。

 there are some special cases in this notation。 I can write M dot dot star。

 And star means any number of objects。 So what that would say is that each object in C1。

 is related to at least M and as many， as it wants elements of C2。 I can also write 0 to N。 And that。

 would say that each object in C1 is related to possibly， none。 For example。

 here we have one that I haven't drawn any relationships。 Possibly none and up to N elements of C2。

 I can also write 0 dot dot star。 And that's basically no restrictions on the multiplicity。

 And just to mention the default actually is 1 dot dot 1。

 So if we don't write anything on our association， we're assuming that each object is related。

 to exactly one object of the other class。 And that's in both directions， by the way。

 So I can put an x dot dot y here。 And that will restrict how many objects。

 element of C2 is related to。 Incidentally， UML allows some abbreviations。

 1 dot dot 1 can be abbreviated as a just plain old 1。

 And 0 dot dot star can be abbreviated with just star。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_7.png)

 So let's take a look at our student and college example。

 and what the multiplicity of the association of students， applying to colleges might be。

 So let's suppose that we insist that students must apply， somewhere。

 So they apply to at least one college， but they're not allowed to apply to more than five。

 And furthermore， let's say that no college will take more than 20，000， applications。

 So this example is contrived to allow me， to put multiplicity specifications on both sides。

 So again， we'll have our student class， and we'll have our college class。

 and we'll have our association between the student， and the college class。

 And I'll just write the name underneath here now applied。

 So let's think about how to specify our multiplicities， for this。

 So to specify that a student must apply somewhere， but cannot apply to more than five colleges。

 we put a 1 dot dot 5 on this side。 It really takes some thinking sometimes。

 to remember which side to put the specification on。

 But that gives us the fan out from the objects on the left， to the objects on the right。

 So it says each student can apply to up to five colleges， and must apply to at least one。

 So we won't have any who haven't applied anywhere。 On the other side。

 we want to talk about how many students， can have applied to a particular college。

 And we said it can be no more than 20，000。 We didn't put a lower restriction on that。

 So we would specify that as 0 to 20，000。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_9.png)

 So I mentioned earlier that multiplicity of associations。

 captures some of these types of relationships， you might have learned about somewhere else called one-to-one。

 many-to-one， and so on。 So let me just show the relationship between association。

 multiplicity and this terminology。 So if we have a one-to-one relationship between C1 and C2。

 technically one-to-one doesn't mean everything， has to be involved。

 What it really means is that each object on what each side。

 is related to at most one on the other side。 So to say it's a one-to-one relationship。

 we would put a 0 dot dot 1 on both sides。 Let's see if I can use some colors here。

 So what about many-to-one？ Many-to-one says that we can have many elements of C1 related。

 to an element of C2， but each element of C2， will be related to at most one element of C1。

 So in that case， we still have a 0 dot dot 1， on the right side indicating that each C1 object is related。

 to at most one object of C2。 But we have the star on the left-hand side indicating。

 that C2 objects can be related to any number of C1 objects。 And as a reminder。

 star is an abbreviation for 0 dot dot star。 Many-to-many has no restrictions on the relationship。

 so that would be a star on both sides， pretty simple。

 And the last concept is the idea of complete relationships。

 So a complete relationship is complementary to these others。

 It says that every object must participate in the relationship。

 So we can have a complete one-to-one， and that would be 1 dot dot 1 on both sides。

 We could have a complete many-to-one， and that would be on the left side 1 dot dot star。

 and on the right side 1 dot dot 1。 And finally， a complete many-to-many。

 would be 1 dot dot star on each side。 As a reminder， the default。

 if we don't specify the multiplicity， is a 1 dot dot 1 on both sides。

 So that would be a complete one-to-one relationship。 OK。

 we've finished with classes and with associations。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_11.png)

 Now let's talk about association classes。 Association classes generalize the notion of associations。

 by allowing us to put attributes on the association itself。 And again， we'll use our example。

 So we already knew how to specify that students apply to colleges。

 But what if associated with the application， we wanted to have， for example。

 the date that they applied， and maybe the decision of that application？

 We don't really have a way to do that without adding a new construct。

 and that construct is what's known as an association class。 So we can make a class。

 and we'll just call it app info。 And it looks like a class that's got the box with the name。

 at the top and the attributes。 And then we just attach that box to the association。

 And that tells us that each instance of the association。

 between a student and a college has additional information， a date of that application。

 and the decision of that application。 Now， there's a couple of things I want to mention。

 First of all， in a number of examples， I'll probably leave out the multiplicities。

 on the ends of the associations。 That doesn't mean I'm assuming the default one one。

 It's just when it's not relevant， I'm not， going to focus on that aspect。 Now。

 when we have students associated with colleges--， so we have a student here and we have a college--。

 and then we have an association between those。 Now， what we're saying is that association。

 is going to have affiliated with it a date and a decision。

 What we cannot describe in UML is the possibility。

 of having more than one relationship or association， between the same student and the same college。

 So when we have an association that， assumes at most one relationship between two objects--。

 so for example， if we wanted to add the possibility， that students could apply to the same college。

 multiple times--， so maybe they want to apply separately， for different majors--。

 that would actually have to be captured quite differently。 We'd have to add a separate class that。

 was for the application information， with separate relationships to the students and colleges。

 So this is my mind， a slight deficiency of UML。 Again。

 that it only captures at most one relationship， between the two specific objects across the two classes。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_13.png)

 Now， sometimes we can make a design that， has an association class， and it turns out。

 we didn't really need it。 And we're going to come back to multiplicities。

 to see how this can happen。 So again， let's take a look at just generic classes--， C1 and C2。

 Let's say that we have an association between them， and then we have an association class。

 We'll just call it AC。 And that's going to have some attributes。 We can call them A1 and A2 for now。

 And of course， there's attributes in C1 and C2 as well。 Let's suppose that the multiplicity on。

 let's say， the left side is star， so anything goes。 And on the right side， we have 1 to 1。

 So what that multiplicity says is that each object of C1， is related to at most one object of C2。

 so-- or actually， exactly one object in this case。

 So we know that there's going to be just one association， for each object of C1。

 And if there's only going to be one association， actually， we could take these attributes， and we。

 could put those attributes as part of C1 instead， of having a separate association class。

 So for example， if this class happened to be the student class， and this was the college class。

 and we insisted， that each student applied to exactly one college。

 then the attributes we had down here， the date and decision， could be moved into the student class。

 because we know they're only applying to one college。 So that would be the date and decision。

 for the one college they're applying to。 Furthermore， if we had 0。1。

 we can still move these attributes， here。 And in that case。

 if a student was not involved in a college--， had not applied to a college at all。

 or more generally， an object of C1， was not related to any object of C2。

 then those attributes would have the equivalent， of null values in them。 By the way。

 it is possible for an association， to be between a class and itself。 For example。

 we could have our student class， and maybe we're going to have an association called sibling。

 a student being associated with another student， because they're siblings。

 An association between a class and itself， is written with a line that just goes between the class。

 and itself， and then we could label that sibling。 And for multiplicities， we can assume。

 that every student has between 0 and an arbitrary number， of siblings， let's say。

 So we could put a star on both ends of that association。

 A more interesting association might involve colleges， where， say。

 we have for every college of flagship main campus。

 but then some colleges have separate branch or satellite， campuses。 So that would be a relation。

 an association， sorry， between a college and itself。

 saying that one college is a branch of another college。

 Now let's think about the multiplicities here。 First of all， when we have this self association。

 in UML， we're allowed to label the two ends of the association。 So I could， for example。

 say on one end， we have the home campus， and on another end， we have the satellite campus。

 And now with those labels， we can see the asymmetry， and that lets us get our associations right。

 So let's say that every satellite campus must， have exactly one home campus。 So that would be a 1。

1 here。 And every home campus can have any number， of satellite campuses。 Or actually。

 let's say something else。 Let's say every home campus can have between 0 and 10， satellite campuses。

 So that would be a 0。10 on that side of the self association。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_15.png)

 OK， we're finished with the first three。 Let's move on to subclasses。 For subclasses。

 we're going to do a fairly large example that， involves students that we're going。

 to separate into foreign students and domestic students。

 We're also going to separately specify students who， have taken AP classes。

 And those will be our AP students。 So we're going to have the student class。

 as the top of our hierarchy。 And the student class will， again， have the student ID。

 let's say the student name and GPA。 And we'll say that the student ID is the primary key。

 for objects in that class。 We're going to have three subclasses。

 One is going to be the foreign students。 We'll call it foreign S。 One is going。

 to be the domestic students。 And then we're also going to have a subclass for AP students。

 And I'm going to assume that you already， know a little bit about subclassing from programming。

 So the idea is that when we have a subclass， there are attributes that are specific to the objects that。

 are in that subclass。 And they'll inherit the attributes， from their superclass。

 So we're going to make student be a superclass here。

 And this is how we draw it with three subclasses here， for foreign student， domestic student。

 and AP students。 And we'll say that foreign students， have， in addition to a student ID。

 a student name and GPA， a country that they come from。

 And we'll say that domestic students are going to have， a state that they come from。

 And we'll also say that they have a social security number。

 which we don't know that foreign students would necessarily， have。 AP students， interestingly。

 is going to be empty。 It's not going to have any additional attributes。

 But the AP students are the students， that are going to be allowed to have a relationship with AP。

 courses。 We'll say that the AP course has a course number。 And that's probably the primary key。

 and maybe a title for the course and some units for the course。

 And then when one of our AP students takes the course， we'll call this association tuck。

 we're going to have an association class that goes along。

 with that that's going to have the information， let's， call it AP info。

 about them taking that particular AP class。 And we'll say that that association class， has。

 for example， the year that they took the class， and maybe the grade that they got in the class。

 And lastly， let's add some multiplicities。 Let's say that AP students can take between 1 and 10 AP classes。

 but they have to have taken at least one to be an AP student。

 And let's say that every course is taken by at least one student。

 and an arbitrary number of students。 So this is one of the biggest UML diagrams， we've seen so far。

 Again， this is a super class up here。 And we have our subclasses down here。

 And then we also have an association and an association， class and some multiplicities。 And again。

 notice that it's OK that there， are no attributes in the AP student subclass。

 That subclass is defined as those students who。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_17.png)

 have taken AP courses。 Here are some terminology and properties。

 associated with subclass relationships。 A super classes in UML are sometimes called generalization。

 with subclasses called specialization。 A subclass relationship is said to be complete。

 if every object in the superclass， is in at least one subclass。

 And it's incomplete if that's not the case。 And incomplete is also sometimes known as partial。

 A subclass relationship is known as disjoint， if every object is in at most one subclass。

 In other words， we don't have any objects that， are in more than one subclass。

 And that's sometimes called exclusive。 And if it's not disjoint， then it's， overlapping。

 meaning that objects can be in multiple subclasses。 We can have any combination of these pairs。

 So we can have incomplete overlapping， or incomplete disjoint， a complete disjoint。

 or complete overlapping。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_19.png)

 Let's take a look back at our example。 For this example， we will probably。

 have the case that it's a complete subclass relationship。 In other words。

 every student is in at least one subclass。 Presumably， every student is either a foreign student。

 or a domestic student。 And furthermore， we're going to say， that it's overlapping。

 because we will have students who， for example， are both a domestic student and an AP student。

 And in UML， the actual notation is， to put little curly braces here to specify。

 that that subclass relationship is complete and overlapping。 To illustrate some of the other cases。

 let's suppose that we didn't have this whole section here， with the AP students。

 We only had foreign and domestic students。 In that case。

 we would say that the subclass relationship， is complete， but in that case。

 it would not be overlapping。 It would be disjoint。

 Or suppose we didn't have this whole left side here。 So all we had was the AP student subclass。

 In that case， it would probably be an incomplete subclass， relationship。

 because not everybody is an AP student。 And there wouldn't make any difference。

 between overlapping and disjoint。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_21.png)

 since there would only be one subclass in that case。 OK， we've now made it to our last concept。

 which， is composition and aggregation。 Let me start by clarifying right off。

 that aggregation here has nothing， to do with aggregation and SQL。

 It's a completely different concept。 So let's first talk about composition。

 Composition is used when we have a database structure， where objects of one class kind of belong。

 to the objects of another class。 And the example I'm going to use is colleges and departments。

 So I've drawn the two classes here。 And let's say for the department， we have the department name。

 and we， have， say， the building that the department is in。

 And so we're assuming that each college has， a whole bunch of departments。 Now。

 we can make a relationship， an association， between colleges and departments。

 to say that a department is in a college。 But when we have the idea that the departments。

 belong to a specific college， then， that's when this composition construct is used。

 And the way the composition is written， is by putting a diamond over here on the end of the association。

 So composition is really a special type of association。 And we'll fill in that diamond here。

 to indicate composition。 Aggregation happens to have an empty diamond， which， we'll see in a moment。

 So when we have the diamond， and we're， creating one of these composition relationships。

 there's implicitly a 1。1 on the left side。 So each department belongs to one college。

 But what's kind of interesting here， what's a little different from a relation。

 the normal relationship， is that we're not， assuming that this department name is a primary key exactly。

 We could have the same department， in fact， even in the same building， in different colleges。

 And that would be OK， because a department is， through this relationship associated with its college。

 So that was composition。 Objects of one class belonging to objects of another。

 Let me give an example of aggregation。 This is a slight stretch。

 But what I'm going to make is a class of apartments， not departments， but apartments。

 So we're going to imagine that there， are apartment buildings represented in our database。

 Maybe they have an address that's the primary key， in something like the number of units。

 And what we're going to imagine is that some apartment buildings。

 are owned by or associated with a college， but not all of them， are。

 And that's what aggregation does。 So for aggregation， we again have a relationship here。

 But in this case， we make a diamond on this side that's open。

 And what that says is that each object in the apartment， class is belonging to a college。

 either at most one college， or no college at all。 So we can have apartments that belong to a college。

 and we can have kind of free-floating apartments。 And that's what the open diamond。

 which is aggregation。

![](img/62d453718a2c5c1e8f95d28df4fe8e84_23.png)

 is about。 So in conclusion， the data modeling portion， of the unified modeling language can。

 be used to perform database design at a higher level。 It's a graphical language。

 We went through the five main concepts of the language。 And also very importantly， UML designs。

 can be translated to relations automatically。 And that is the topic of the next video。



![](img/62d453718a2c5c1e8f95d28df4fe8e84_25.png)