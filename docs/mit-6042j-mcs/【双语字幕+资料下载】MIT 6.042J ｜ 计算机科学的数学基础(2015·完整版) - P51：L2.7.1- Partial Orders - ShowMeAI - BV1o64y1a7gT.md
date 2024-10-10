# 【双语字幕+资料下载】MIT 6.042J ｜ 计算机科学的数学基础(2015·完整版) - P51：L2.7.1- Partial Orders - ShowMeAI - BV1o64y1a7gT

partial orders are another way to talk，about digraphs and they offer to us an。



![](img/559c2df900d71d932b56ddb44e816727_1.png)

interesting lesson in the idea of，axiomatic a mathematical structure and。

mathematical ideas so let's begin by，discussing some of the properties that。

we're going to use to axiom a ties，partial orders and digraphs so if we。

think about walks in a digraph the basic，property of walks is that if you have a。

walk from u to V and you have a walk，from V to W then you put the two walks。

together and you wind up with a walk。

![](img/559c2df900d71d932b56ddb44e816727_3.png)

from u to W expressed in terms of the，positive pet walk relation in G what。

this is saying is that if u g + v + v g，+ w then u g + w and that abstract。

property which i'm highlighting with the，magenta box when you apply it to an。



![](img/559c2df900d71d932b56ddb44e816727_5.png)

arbitrary relation is called the，transitivity property so a relation R on。

a set that is R is relating the domain，and codomain of are the same is that you。

are V and V are W implies you are W and，a relation that has that property is。

said to be transitive and of course what，we've just seen is that the positive。

path relation of any graph G is，transitive another way to say，transitivity is to read you are V is。

saying there's an edge from u to V and，what this says is that if there's an。

edge from u to V and an edge from V to W，there's an edge from u to W or in other。

words if there's a path of length 2，there's a path of length 1 and then by。

easy induction it follows that if，there's a path of any length between of。

any positive lengths between two，vertices then in fact there's a path of。



![](img/559c2df900d71d932b56ddb44e816727_7.png)

okay so the basic theorem that we have，to begin with is what is transitivity。

capturing as a property of a relation。

![](img/559c2df900d71d932b56ddb44e816727_9.png)

and a relation r is transitive if and，only if in fact R is equal to the。



![](img/559c2df900d71d932b56ddb44e816727_11.png)

positive walk relation for some digraph，J the proof of this is basically trivial。

because you can let the relation R be。

![](img/559c2df900d71d932b56ddb44e816727_13.png)

the digraph that it's the positive path，relation of if we look now at directed。

acyclic graphs then what we have is that，if there's a positive length path from a。

vertex u to a vertex V then since，there's no cycles in a directed acyclic。

graph there can't be a path back from V，to u and that property is called a。

symmetry so the plus which is the，positive path relation in a dag has this。

asymmetry property namely if you can get，to V by a positive length path and it's。



![](img/559c2df900d71d932b56ddb44e816727_15.png)

not possible for V to get back to you by，a positive length path so abstracted you。



![](img/559c2df900d71d932b56ddb44e816727_17.png)

are V implies Naqvi are you that's the，asymmetry property of an arbitrary。

relation r and by definition of a cyclic。

![](img/559c2df900d71d932b56ddb44e816727_19.png)

d+ is a such is a symmetric in a graph，without cycles okay a strict partial。

order is simply a relation that has。

![](img/559c2df900d71d932b56ddb44e816727_21.png)

these two properties of being transitive，an asymmetric and some examples of。

strict partial orders are the proper，containment relation on sets which we've。

previously commented can be viewed as a，dag but now it satisfies transitivity。

and the fact that if one sets properly，contained in another the second one。

can't be properly contained in the first，because proper means you have something。

extra the indirect prerequisite relation，on MIT subjects would be another example，of a strict。

was it if I'm a prerequisite of you you。

![](img/559c2df900d71d932b56ddb44e816727_23.png)

can't be a prerequisite of me and，finally the less than relation on real。



![](img/559c2df900d71d932b56ddb44e816727_25.png)

numbers these are all examples of strict，partial orders and putting together the。



![](img/559c2df900d71d932b56ddb44e816727_27.png)

previous reasoning what we can say is，that a relation R is a strict partial。

order if and only if R is the positive，path relation for some great dag Dean。

so the axioms that define strict partial，order namely transitivity and asymmetry。

can be said abstractly capture the。

![](img/559c2df900d71d932b56ddb44e816727_29.png)

property of a relation that it comes。

![](img/559c2df900d71d932b56ddb44e816727_31.png)

from a dag another important property of，partial orders is the idea of being path。

total or linear as some authors call it，and the simple definition of path total。

is that given any two elements one is。

![](img/559c2df900d71d932b56ddb44e816727_33.png)

going to be bigger than the other with，respect to the relation most familiar。



![](img/559c2df900d71d932b56ddb44e816727_35.png)

example that would be the less than，relation or the less than or equal to。

relation on the reals given any two，distinct real numbers x and y either X。

is less than Y or Y is less than X and。

![](img/559c2df900d71d932b56ddb44e816727_37.png)

we take that property for granted now，the frontal definition then is simply。

that if X is not equal to Y then either。

![](img/559c2df900d71d932b56ddb44e816727_39.png)

X are Y or Y are x and a relation R that，has that property is called path total。



![](img/559c2df900d71d932b56ddb44e816727_41.png)

another way to say it is that there are，no incomparable elements under R and。

I've again highlighted with a magenta。

![](img/559c2df900d71d932b56ddb44e816727_43.png)

box this property which is called path，totality what another way to say that。

path total is that the whole order looks，like a chain if you give me a bunch of。

elements there's gonna have to be a，biggest one and then its next biggest。

one and so on assume you give me any，finite set of elements so the basic。

example again of path total would be，number properties of bigger than and a。

basic example of something that would，typically not be path total would be。

lets say subset containment where you，can perfectly well have two sets neither，of which。



![](img/559c2df900d71d932b56ddb44e816727_45.png)

is contained in the other so a weak，partial order is a small variation of a。

strict partial order that is another，familiar concept where we take the。

strict property which guarantees that。

![](img/559c2df900d71d932b56ddb44e816727_47.png)

nothing's related to itself and we relax，it so a strict partial order is just。

like a weak partial order except that，the condition that there's no positive。

length path between an element and，itself is relaxed so in fact it's not。

only relaxed but it's completely denied，in a weak partial order we insist that。



![](img/559c2df900d71d932b56ddb44e816727_49.png)

every element is related to itself an。

![](img/559c2df900d71d932b56ddb44e816727_51.png)

example of that would be the less than，or equal to relation sorry the the。

improper containment relation the，ordinary subset relation on sets where。

now a is a subset with a bar under it a，is just a subset of a not necessarily a。



![](img/559c2df900d71d932b56ddb44e816727_53.png)

strict subset or a proper subset means，that in fact a is a subset of a and then。

less than or equal to when you put the，little bar under the less than sign to。

indicate that equality is also a。

![](img/559c2df900d71d932b56ddb44e816727_55.png)

possibility you get a weak partial order。

![](img/559c2df900d71d932b56ddb44e816727_57.png)

on the real numbers so the property that，distinguishes the weak from the strict。

is this property of reflexivity a，relation R on a set is reflexive if。

every element is related to itself if，and only if a are a for all little a in。

the domain capital A and what we can，observe immediately is that the path of。

the walk relation G star which includes，walks of length zero is reflexive。

because by definition there is a length，zero walk from any vertex to itself so。

if you're going to play with axioms then。

![](img/559c2df900d71d932b56ddb44e816727_59.png)

you can reformulate a symmetry the idea，of a symmetry except for elements being。



![](img/559c2df900d71d932b56ddb44e816727_61.png)

related to themselves，it's called anti symmetry and it says。



![](img/559c2df900d71d932b56ddb44e816727_63.png)

an，if it's asymmetric except for the AR a。

![](img/559c2df900d71d932b56ddb44e816727_65.png)

case and more precisely the difference，between asymmetry and anti symmetry is。

that in asymmetry a ra is never allowed。

![](img/559c2df900d71d932b56ddb44e816727_67.png)

and an anti symmetry a ra is a，possibility it's not disallowed so an。

anti symmetric relation on our stated，abstractly is that you are V implies not。

V are you for you not equal to V so the，first line is exactly the statement of。

asymmetry and then I add this proviso，that it only has to hold when the U and。

the V are not equal that's the formal，way of saying anti symmetry is the same。



![](img/559c2df900d71d932b56ddb44e816727_69.png)

as a symmetry except for a ra and the，the walk relation in a digraph which。



![](img/559c2df900d71d932b56ddb44e816727_71.png)

includes length zero walks is。

![](img/559c2df900d71d932b56ddb44e816727_73.png)

anti-symmetric so with partial orders，just what you get when you put these。

things together weak partial order is，transitive anti-symmetric and reflexive。

so in a weak partial order we insist，that every element be related to itself。

so there's a lissa is the quick remark a，symmetric means implies nothing's，related to itself。

reflexive implies everything is related，to itself and it's possible that there。

be some graph that in which some，elements are related to themselves and。

some not that would be something that，order，it would just be transitive and。

anti-symmetric those don't come up much，and so we don't bother to give them a。



![](img/559c2df900d71d932b56ddb44e816727_75.png)

name or talk about them and finally the。

![](img/559c2df900d71d932b56ddb44e816727_77.png)

theorem that summarizes up this whole，story is that R is a weak partial order。

if and only if R is equal to the walk。

![](img/559c2df900d71d932b56ddb44e816727_79.png)