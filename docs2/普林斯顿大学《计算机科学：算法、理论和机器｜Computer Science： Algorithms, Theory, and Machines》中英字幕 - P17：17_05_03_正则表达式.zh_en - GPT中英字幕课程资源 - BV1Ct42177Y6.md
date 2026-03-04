# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P17：17_05_03_正则表达式.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

So now let's take a look at regular expressions。Regular expressions are relevant to an important problem known as the pattern matching problem。

We want to know， is a given string an element of a given set of strings， or is it in a language。

 given language， So here's an example from computational biochemistry。

One way to represent an amino acid is with one of the characters， CA VLI that are listed there。

 and each one of those is a standard representation of an amino acid。

A protein is a string of amino acids， so just a string consisting of those letters。

So there's a particular type of protein that is referred to as a C2H2 type zinc finger domain signature。

 and that's well defined by these specific rules。It's a C followed by two， three or four amino acids。

 it could be any one of them， followed by another C， followed by exactly three amino acids。

 followed by one of these nine specific ones， L IVM， FYWC or X， followed by eight more amino acids。

 followed by H， then followed by three， four or five amino acids followed by H。

It's a pretty complicated set of rules， but well， life is complicated。So we might have the question。

 I have a given protein， is does it follow these rules， is it in the situ2 type zinc finger domain？

So there's a protein， so let's see if it actually follows these rules。

 whether it actually follows these rules or not， is it in the language defined by those rules。

 is it in the set of strings defined by those rules and the answer in this case is yes。

 starts with a C。And then there's three amino acids， so that's the first bullet point。

there's another C and then exactly three amino acids， and then the next letter is y。

 so that's one of the next to last bullet， that's one of the ones listed。

 and then there's eight amino acids， and then the next one is H。

 and then there's three that's okay the last bullet point3，4 or5， and then finally an H。

So in this case， this string is in the language， and clearly we want to be able to answer this type of question in for a broad variety of types of proteins。

That's example one。Here's another example from commercial computing。

 you suppose you want to define what an email address is。

 It's a sequence of letters followed by an at sign。

 followed by another non empty sequence of letters， followed by a dot。

Maybe any number of occurrences of that， and then ending up with EDU or comm or org or gov or some other legal suffix where you would expect to find in the end of an email address。

So you can ask them which of the following your email addresses。

 so this one's got a sequence of letters， ad signs， some more letters， a dots。

 some more letters a dot ending in EU， so that one is in the language defined by these rules。

So this phrase not an email address， it's not an email address， doesn't have the at sign or any dots。

There's another one that fits， this one doesn't end in EDU or comm， so it's not an email address。

This one doesn't fit according to those rules， but maybe we need to fix the description to allow for some numbers。

 say。And actually specifying precisely what's a legal email address and what is not an legal email address can get pretty complicated so this is just to indicate that it's not always so easy to specify the rules。

So the challenge is we want to develop a precise description of the set of strings in question。

 and that's true for many of these types of problems。And we'll look at a way to do that now soon。

Here's a third example from genomics， so nucleic acid is one of the letters ACT or G。

 and we've seen examples before with this representation， the genome is a string of nucleic acids。

So there's a thing called a fragile X syndrome pattern。

And so that's a genome that is defined by the following rules， it's got GCG somewhere inside。

 followed by any number of CGG or AGG triplets， followed by CTG。And in fact。

 this is important because the number of triplets correlates with this fragile X syndrome。

So if you have a genome， you might want to know this in order to deal with this illness。

So given a genome， does it have the pattern or so what about this one， does it have this pattern。

 this example is to illustrate the challenge of the pattern matching problem and the answer in this case is yes after a while you can find a GCG and then there's three CGG and AGG triplets then it ends with CTG。

So that's three examples of a fundamental computational problem with all kinds of applications。So。

 the。Tool that we use to address these types of problems is called regular expressions。

It's a notation for specifying a set of strings， otherwise known as a formal language。

So regular expression， an RE is either the empty set or an empty string。

Or it's a single character or a wild card symbol that represents all characters。

 or it's an RE enclosed in parentheses， or it's the concatenation of two or more REs。

So here's examples of these rules， so AAB AAB， that's the concatenation of a bunch of single characters that specifies the set consisting of that one string。

 so only that string AAB AAB is in the set specified by that regular expression or in the language defined by that regular expression。

 and every other string is not in that set。If we use a wildcard character then we can specify multiple strings so we say dot u dot u do u dot that's all those seven letter words with alternating us starting at the second character and there are may lots of words in the dictionary。

 these are the ones in the dictionary but of course it specifies any string of seven letters with those U's in there。

 so those are examples of strings that are in the set specified by that regular expression and then if you don't have the u' strictly alternating like that。

 then it's not matching。So that's simple examples of regular expressions using concatenation and wildcard。

And then we can have more complicated operations for the union of two or more regular expressions。

 that's just one or the other， and we represent that with a vertical bar， so in this simple example。

 only the two strings， AA and B AAB are in the language defined by that regular expression and every other string is not in the language。

And then there's what's called the closure and that's any number of occurrences of BRE。

 so A B star A means A followed by01 zero or more occurrences of B， followed by A， so AA， A BB BA。

 A followed by any number of B's followed by A is in the set defined by that string。

 that regular expression。But these other strings are not in the set defined by A， B star A。

 first one doesn't end in an A， the second one's got an A in the middle there that's not allowed by the definition。

Just interesting to note that the closure operation already takes us to infinity that's specifying an infinite set of strings。

 the number of bees is not as could go without bound。

And then we can use parentheization to make up complicated expressions describing specific sets。

 so for example， A followed by parenthesized A or B， AAB。

 again there's two strings that are in that set， A A， AAB， and A B， AAB。

 and every other string is not in the set defined by that regular expression。Or if we say A B star A。

 that's a way of saying alternating ABs ending in A。

And if you have two A's in a row or two B's in a row anywhere。

 its not in the set defined by that regular expression， again， an infinite number of strings。

These are simple rules easy to understand， but it turns out to be a very expressive notation for specifying sets of strings。

So for example， dot star， SPB dot star， that's all strings that have SPB inside them somewhere。

This type of thing is useful for solving a crossword puzzle。

 you're often interested in answering questions of this sort。

And we could also add the condition that it must be in the dictionary and describe our set that way。

So raspberry and crisp Bread are in the language defined by that regular expression。

 but these other ones do not have SPB in that order contiguous anywhere inside。

 and the dot star just allows matching of any number of characters， so wherever the SPB is。

 that would be matched as long as it's somewhere in the string。Here's a much more complicated one。

 a star or in parentheses， A star B， A star B A star， B， A star， whole thing starred。

With a little thought， you can convince yourself that this specifies all the strengths consisting of just A's and B's。

 where the number of B's is a multiple of three。So BB。

 just take all the stars to mean zero occurrences。AAA thats we can take the star on the right to be0 occurrences so it's got zero Bs。

 we'll count that a multiple of three， but if you have a multiple of three be's anywhere in there you can match it to that regular expression it's in the language defined by that regular expression if you don't have a multiple of three B's。

 then it's not in the set already we're starting to see a little bit of computing just with this simple notation。

So here's another one just using dot dot star0 dot dot dot that just matches all strings that fifth the last digit is zero and here's one for our fragile X syndrome pattern。

 dot star and then we put that GCG followed by any number of occurrences of CGG or AGG star ending with CTG and then finish with dot star so if the genome has the fragile X syndrome pattern inside it。

 that's the way to specify that language and the ones that don't does not match。So again。

 very expressive and actually it's so useful that many extensions have been developed。

 just additional operations that make regular expressions even more useful because sets of strings is something that actually we wind up wanting to specify in all sorts of applications。

So for example， rather than star， we can use plus， and that just excludes the possibility of zero occurrences。

 so one or more occurrences。We can specify a class of characters by putting a range。

 so little A to little Z would be lowercase characters。

 big A to capital A to capital Z is capitalized characters and inside the brackets it says take a character from that sequence and with that we can check capitalization or we can specify languages that have proper capitalization。

Rather than plus or star you might want to say exactly exactly a certain number of occurrences。

 so that's within curly braces， so this says take a five digit number followed by a four digigit number。

 so maybe that specifies whether the string is a zip plus4 code there's all kinds of other strings that are not in the language but at least you can test whether it's legal according to the rule。

Or maybe between J and K occurrences， so that's curly braces 2 comma4 that says two。

 three or four occurrences of dot， which would mean a wildcard character。

 so that's A and B separated by two， three or four characters。OnNgation。

 so that specify a set of characters and say anything but those set of characters。

So this generalized regular expression says six characters that are not vowels。

 and that's a word in the dictionary， six character word in the dictionary without a vowel。

And then there's special characters like white Space。So typical convention is to have backslash S。

Match any white space character like space T and newline and other things like that。

 And that's useful when processing text。Now it's important to note that in applications we're going to want to use these things all the time from the point of view of the theory they're just shorthand。

 they're not essential to understanding the fundamental theoretical points that we're going to talk about。

 so you can always replace one of these shorthand notations by a regular expression that follows the rules using parentheses or star concatenation only。

So here's just an example of the applications that we considered。

 how do we write a generalized regular expression that specifies these rules。

 well it's pretty straightforward， these rules are quite specific and with the generalized notations that we've talked about developing the generalized RE for that is pretty straightforward。

 so we have a C and then we have a dot2 through4 we have the proviso that in this case only the allowed letters representing amino acids are in the alphabet。

So that's two to four of them and then a C followed by exactly three。

 and then something from the one of the characters LIV and FYWCX， followed by eight of them。

 followed by an H， followed by three， four， or five of them followed by another H。

 a pretty compact notation of those rules that is a useful way to specify it。

 not hard to learn these rules and is something that everyone is going to use computers effectively learns to some extent。

 eventually。Here's a real world application having to do with proteins and actually scientists。

 biologists use this website as an integral part of their work and searching in there has to do with typing a regular expression in that window and getting the result and more and more other search type tasks or involving regular expressions because it's an easy to use in compact notation for specifying what it is that you want to see。

So here's just another example with our email address idea。This is， again。

 a generalized regular expression， says at least one lowercase character followed by at sign。

 followed by at a sequence of at least one string of lowercase characters followed by a dot followed by at EDU or comm。

And again， as an exercise， you can figure out how to add other types of extensions or numbers or whatever else。

Again， a very expressive way of specifying a set of strings that you want to consider to be legal or a language that you want to know is a given string in that language。

So now what we want to do is given that setup， now we have a formal and specific way to specify sets of strings or languages。

 and now we want to know how we can determine whether or not a given string is in the language or matches the given regular expression that's going to be our next task。

Here's just a couple of pop quizzes and again worthwhile to study these types of questions to make sure that you understand the basic idea。

 so in any kind of quizz or exam on this material， you might be asked which of the following strings match A star。

 BB， AB or B A star。Well， you have to figure out a way to get through this question by just working through in this case。

 about what do you think about ABB？Well， if looking at the REE， the star says take any number of A's。

 I can certainly just take1 and then I take the BB and then the rest of it I'll take zero occurrences of。

 so that one certainly is in the set it describes。What about the second one？

Second one doesn't work because every string in that language has to have two consecutive bes in it。

What about the third one again， after this one， after you get the BB。

 there's no way to get just a single A at the end， you have to have AB or BA。

So that one doesn't work， that one does no A's， two Bs， then take a BA and an AB。And it works。

There's no C anywhere， so number five is easy， and this one is more complicated reasoning to figure out why that string is not in there。

 don't have an even number of characters after BB。So you can see immediately not so easy to know whether a given string matches a given regular expression。

Okay， here's another one type of question that you would have to answer in any kind of quiz on this material。

G an RE for genes and genes are described this way， you have a characters or ACT or G。

 every gene starts with AG， the length is a multiple of three， and it ends with either TAG。

 TAA or TTG。So think about how you would create a regular expression that implements those rules。

 describe the set of strings that satisfy those rules。

Here's the answer at the beginning there has to be an ATG at the end there has to be one of the three codons TG。

 TAA or TTG。In the middle， you have A or C or T or G， three times any number of occurrences。

We could have used the dot modified dot notation saying just anything from the alphabet if we had wanted dot dot dot star。

So that's a second example and it's worthwhile to go to the book site and practice on other examples of regular expressions and whether or not strings match them。



![](img/d02a2509b905c5d6e8c570635f617645_1.png)

![](img/d02a2509b905c5d6e8c570635f617645_2.png)