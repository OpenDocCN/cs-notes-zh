# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P54：-054-Modules and Structures Chap5 Video 2.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Structures give us hierarchical namespaces in OcaMl。Let's take a look at some code we saw last week。

We have a type for lists and a type for trees and two map functions over those。 Now。

 this time I've named both of those map functions， just map。

That creates a problem when I go to do a map over a my list because the word map here。😡。

Means the most recent definition of it， which is the map function here over trees。

That is shadowing the earlier definition of mapping over lists。

There's really no way to recover that earlier definition。Unless we use structures。

Let's enclose the definition of my list here in what's in Ocamel called a module。

We'll name that module my list。And it is a structure which begins with the keywordstruct。

And ends with a keyword end。I'll do the same thing for trees， module tree。Is a structure？

And it ends there， and now when I say you'll notice that VS code reformats and indentense all of those pieces of those structures inside。

Now， the word map is unbound。Because it's not defined anymore at the top level of scope as it were。

 instead I now have to say my list dot map to get the my list version of it。

 which is what I want here， or tree dot map， which of course is not what I want。

 it gives me back that original error we saw earlier。😡。

So we created a module which is named My list and we bound it to this structure inside that structure is all the kind of code that we've been writing all ofla。

So basically， this gives us a way to create nested levels of code with hierarchical names。

 One possibly surprising thing about structures and module names is where the name itself goes when types are involved。

If we hover over list， you can see that its type is int My list dot My list。

My list was the type constructor that we defined inside of the module my list。

 that type constructor is parameterized on a type variable alpha。So the type of list。

Is an int my list dot my list， Because the name my list is defined inside of the module capital My list。

 That's why the module name dot goes in front of the type name。

The module name does not go in front of the type variable。😡，Again。

 think of that type variable as a parameter being passed to a kind of type level function。

 so int here is being passed， if you will， to my list dot My list。😡。

We could also coat up trees and see the same phenomenon。

Now you see we have an error because Ocaml doesn't know what node means here。

 It doesn't know that we mean the node inside of the tree module we could show Ocaml。

 we wanted that in a couple different ways we could say tree dot node here and now once Ocamll knows that it's not going to force us to write tree dot leaf in the rest of these places the type inference engine will'll figure that out。

Another way of helping type inference here would be to give an manual annotation on the type of T。

Now we don't have to put the tree dot in front of either of the constructors。

