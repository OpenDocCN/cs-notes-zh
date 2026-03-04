# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P27：-027-Record Syntax and Semantics Chap3 Video 5.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

We introduced two new data types in OcheMl records and Tupples。

We want to study their syntax and semantics。So I snuck in along with these a new kind of definition。

 a type definition， we had seen definitions of values before with the let syntax now we have type definitions with the type keyboard。

And we have two new kinds of types， record types， and tuple types。For record syntax。

 we write records inside of curly braces。With field names separated by semicolons。

 we use an equal sign between the field name and the expression we want to have stored in that field。

So F1 equals e1， S equal and f2 equals e2 is a record with field names F1 and F2。

Now the order of fields as we write them down inside of a record is irrelevant。

 we're free to write them in any order we want， and OM will not distinguish one record from another based on the order of the fields。

You have any number of fields you want inside of a record from one up to somewhere around 4 million。

 honestly you would never have a record that big， really， you might have three， four， five。

 even eight fields。We write dot。To access a field from a record。

 so E dot F accesses the field named F of a record expression E。

It's important to bear in mind that F here is a field name。

 and it must be an identifier syntactically。😡，It cannot be an expression that you compute。😡。

If the latter is what you want， then really what you are thinking of is a dictionary and we will come to dictionaries later。

How do you evaluate records？It takes a lot of notation and words and math here to write down what's really a pretty simple concept honestly。

Just evaluate all of the expressions to values。So if you have a bunch of expressions。

 E sub1 up through E sub n， I'll just say E sub I for all of those。

If E sub I evaluates to v sub I for all of them， then the record expression with all of those E's evaluates to a record value that just contains values inside of it。

And as fort field access。If E evaluates to a record value and that record value has a field named F。

Which is bound to a value V。Then E dot F evaluates to V。

All we're doing is getting the value of that field out of the record。For type checking。

 there's one little quirk here， which is that record types must be defined before you use them。

Actually， this is not so surprising， you can't use classes in Java before you define the class。

 for example， you can't use record types in OcaMl before you define the particular record type。

 and that's so that OcaMl knows what the field names are going to be for that record type。

Turns out it is possible to engineer record types and type inference such that you don't have to define them first。

 but you don't get as good of type inference for it。Okay， as for type checking rules for records。

If you form a record expression。Then all of the sub expressionions that are part of it need to have the right type according to the definition of the record。

If you have a field named。GPAA， whose type is float， you can't stick an int into it。

 and if you go to access a part of a record with the dot notation。

 then you get the field of the appropriate type。One other piece of record syntax that we haven't seen so far is record copy。

So if you write curly brace E with F1 equals E1。That creates a copy of record E with a new field value for F1。

Let's actually try an example of this quickly。

![](img/3eee69545bd15806ba9f5214da011b14_1.png)

Back here， we had records and we had RBG。Let's go ahead and load that code into U。



![](img/3eee69545bd15806ba9f5214da011b14_3.png)

Use records。 Ml。We could create a copy of RBG。Like writing RBG with and suppose we wanted to change the name。

Name is Ruth。Better。Ginsper。Now we've got a new record in which the name has been changed。

Now this didn't go back and change the original record， it's immutable， as always。

 still just Ruth Bader。So record copy is not mut， it leaves the original record unchanged。

You can also replace many values if you want at the same time inside of the record by just chaining the mom with semicolon field name equals some expression。

In reality， record copy is just another example of syntactic sugar though。

 it's really sugar for just rewriting the entire record with all field names。

 using all of those field names in the width clauses。

And then all of the field names that you didn't happen to mention in the with clause from the original record。

But it's much more convenient to be able to use the record copy syntax if there's a lot of fields and you only want an update of the record with just one field changed。

Now you can't use this to add new fields。😡，That would change the type of the record。



![](img/3eee69545bd15806ba9f5214da011b14_5.png)

That's not permit。

![](img/3eee69545bd15806ba9f5214da011b14_7.png)