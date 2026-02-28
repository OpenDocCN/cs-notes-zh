# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P18：17_模块2 2 3 字符串包.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/70a15473eda755c11bc00f1834e239f5_1.png)

🎼う。🎼Yeah。So we've already talked about strings， strings are a common construct。

 you see them in every programming language， and strings are made of Unicode rooms。

 they basically arrays of rooms。So there's a package called the UniIcodeode package。

 which provides a set of functions that actually evaluate the properties of the different ruins inside the strings。

And it's useful if you're doing if you've ever done parsing， you know。

 you want to parse some string of rid out of a file or out of a maybe something somebody typed in in directly is user input。

 and you want to evaluate that string when you're doing parsing， you need functions like these。

 So there are the long set of functions that the Unicode package provides to evaluate the rooms。

Okay right， here some of them here， all right， is digit， tells you if the moon is digit。

 numerical digit is space， this is space character， is a letter。

 the letter is lower or lowercase is punctuation， is puned。So and these all are all binary。

 a boolean， right， so they return true or false depending on if the run is what it's saying to be。

 if it's a dig space or so on。There are also a set of other functions that perform convergence。

 so some of these conversionvergs are possible， for instance， too upper and too lower。

 you can take a lowercase run， turn into an uppercase run right and vice versa so they provide functions for that so they take a run like two upper it takes a run。

 which is a lowercase and returns a run which is an uppercase and so on。

So Unicode package is useful for that， but there are other packages that are also involved in manipulating strings。

There's the strings package， so the strings package。

The functions that it provides are things to directly not look at the individual rooms generally。

 but look at the whole string， so there are a set of search functions that are provided inside the strings package。

 these are common functions that you see in lots of different languages also so for instance。

 first one compare compare AB， you give it two strings and it compares to see if they're equal and actually this compare function it returns a negative1。

 it returns0 if they're equal， returns a negative1， if a is less than B， meaning earlier than it in。

In alphameric order， and it returns to positive one if a is greater than B。

 so if a is later than B in alphameric order。So this compare contains。

 so you give S a string and then a substring， if that substr is contained inside S， it returns true。

 otherwise false， has prefix， so you give it a string S and a prefix and it returns true if that prefix if S starts with the prefix and index S and you give it a substring。

 what that does is a search it searches for the substring inside S and it returns to you the index of where the first instance instance of that substring can be found inside S if it can be found。

So this is the strings package now the strings package also provides a set of functions。

That manipulates strings。 Now， when I say manipulate， you can't change a string。

 a string is immutable， but there are a lot of functions that take an existing string and return a new string that is some modified in some useful way。

 So first one would be replace with replace， you basically take a string and it allows you to replace instances whenever it finds an occurrence of old。

 it replaces it by an occurrence of new。 So these are all string。 So's a big string S。

 there's a substr old in another substr new， it replaces instances of old with instances of new and returns you a new string。

 So S， the original string is not actually changed It returns you a new string with the replacements performed。

To lower， too upper， so this will take the whole string and change it to lowercase or uppercase return I keep saying change。

 it does not change to the string it returns a new string that is modified Also trim space is useful that gets sort rid of leading and trailing white space from a string。

So you get this a lot when you're reading from a file， let's say。

 and maybe the tokens on the file are separated by spaces。

 so if you just read directly from the file you'll also read these spaces in。

 but you don't need the spaces， you just need the token。

 so you may call trim space to get rid of the spaces。

Another package that has a lot of useful functions for strings is a string convert package。

So generally this provides a set of functions for converting converting strings from and from different basic data types to and from different basic data types。

 so some of the big ones a to I as ASI to integer is what it stands for and it converts a string to an integer if that string represents an integer so let's say you're reading from a file you're reading a string from a file and this string is a number 1。

2，3， 123。Now， when you read that and you read that as a string， you can't do math on a string。

 right you can't take that 123 and add one to it because it's a string type， it's not an int type。

 so you need to read that string in and then convert it to an int and then you can do math on it so you would use A to I to do a thing like that。

And Ida A does the reverse。 It converts an ant into a string， an equivalent string。

Then format float basically does a similar thing for floats。

 so it converts a floating point number into a string representation of that floating point number and then par load does the opposite。

 converts a string to a floating point number， so a string， so if you have the string 123。

45 and as a string， it'll convert that to a floating point number that you can actually do math on。



![](img/70a15473eda755c11bc00f1834e239f5_3.png)