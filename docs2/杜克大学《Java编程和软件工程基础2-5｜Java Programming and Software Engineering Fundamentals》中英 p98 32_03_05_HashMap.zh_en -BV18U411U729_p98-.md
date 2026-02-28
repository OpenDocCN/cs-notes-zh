# 杜克大学《Java编程和软件工程基础2-5｜Java Programming and Software Engineering Fundamentals》中英 p98 32_03_05_HashMap.zh_en -BV18U411U729_p98-

![](img/059b632286a2b89a47d1f7fbf22a971e_0.png)

Hi， it's time to learn about a new way of structuring data， this also helps in structuring classes。

You've seen some of the concerns with the design of the Gladlibb class。 The design has flaws。

 but you still were able to add a new label and create new stories to the design works。

 Lager programs with the same flaws might be harder to modify。😊。

You've also seen code to count nucleotides in a strand of DNA and letter frequencies to break a Caesar cipher。

We extended this idea to counting word frequencies in any file with two parallel arrays to count nucleotides。

 we used four int variables to count each time a C， G， T， or A occurred。



![](img/059b632286a2b89a47d1f7fbf22a971e_2.png)

To count letter frequencies， we use an array of 26 int values， one for each letter， A through Z。

To count words， you saw code that used two parallel array list。

 These contained as many values as there are different words being counted。

Now you'll see how to use the concept， a parallel array list to help understand the Java dot Uil。

 hashmap class， a new way to structure data。

![](img/059b632286a2b89a47d1f7fbf22a971e_4.png)

Using a hash map will make it much easier to modify the Glib class。

 The hashmap class is also very efficient compared to using two parallel array list。

 We'll explain the hashmap class using the parallel array list class to help。

 You've had a chance to see this code that uses two array list to count how many times each different word occurs in a file。

😊。

![](img/059b632286a2b89a47d1f7fbf22a971e_6.png)

The method dot index of finds the location of a word in the array list of strings named my words。

If the value returned by the dot index of is -1， then the string read from the file hasn't been seen before。

 and it's stored in my words with a corresponding count of one in my freaks。

 If the string has been seen before， the integer value of my freaks at the same index is incremented by one。

This code works， but using a hashmap will make the code much faster and the hashmap class will make it easier to modify the Gladlo class as well。

Let's work to understand the concepts in the hash map class。

 A hash map object associates keys with values。 In many languages， This is called a map。

 You might think of the key or legend in a map， as you can see here。

 the key helps in understanding the map。 You can look up the color in the key or legend。

 and understand what the color means in the map。

![](img/059b632286a2b89a47d1f7fbf22a971e_8.png)

![](img/059b632286a2b89a47d1f7fbf22a971e_9.png)

In programming， the concept is more mathematical than geographical。

The word map has meanings in both math and geography。



![](img/059b632286a2b89a47d1f7fbf22a971e_11.png)

The key is an element in a domain that's being mapped to a value in the range in math。

 a function is sometimes called a mapping。 And this expresses the ideas in the hash map class。

 as well。In a hash map， you look up a key and you get the value associated with the key。



![](img/059b632286a2b89a47d1f7fbf22a971e_13.png)

In an example illustrated here， we are counting word frequencies。 The word rainbow occurs 41 times。

 so the integer value 41 is associated with the string key rainbow In Java。

 the value returned by the call map dot get raininbow is 41。

The value returned by map dot get truth is 17， indicating the string truth occurs 17 times。

 If football occurs 23 times， then 23 is a value associated with the key football。

 And is returned by the call， map dot get。Football。

Wonderful occurs 23 times in our hypothetical example。 The keys in a map are unique。

 but it's possible to have the same value associated with different keys。To use a hashmap。

 you'll need to understand the operations it supports。

 We'll use one hashm to replace the two parallel array list。

 Here's the code that uses one array list of strings and one array list of integers with the dot index cell function used for associating integer values with strings。



![](img/059b632286a2b89a47d1f7fbf22a971e_15.png)

![](img/059b632286a2b89a47d1f7fbf22a971e_16.png)

The hashmap code also associates an integer value with the string key。

 The key in the hash mapap will be a string。 The value is an integer。

 That's the number of times the string occurs in a file being processed。

To define a hash mapap variable， you'll need to specify the type of both the key and the value。

When calling new， you must specify the key and the value types as well。 The key is the first type。

 and the value is a second type。The code will determine if the key has never been seen before。

 whether it's stored in the hashmap or not。The method dot contains key on the map。

 object returns abuion indicating whether that key is in the map。If it's not in the map。

 the value1 is put in the map with the key using the map method dot put。

If the string is a key in the map， meaning the string being processed has been seen before。

 the value associated with the key is found using the dot get method。

 and then a new value is stored for the key by calling map dot put with an updated value of one more。

In addition to accessing individual map keys and values。

 you'll also need to access all the keys and values in a map。

 Priing the strings and frequencies when parallel arrays are used requires a typical indexing for loop with the index used to access both strings and integers as shown here。



![](img/059b632286a2b89a47d1f7fbf22a971e_18.png)

![](img/059b632286a2b89a47d1f7fbf22a971e_19.png)

Printing all the key value pairs in a map requires looping over all the keys and getting the value associated with each key。



![](img/059b632286a2b89a47d1f7fbf22a971e_21.png)

The method dot keyset returns an intervalable you use to access each key a loop。

 this is similar to using dot words or dot lines with a file resource or URL resource to access elements or the dot data method to access each string in a storage resource。

Iterating over the keyset and calling get for each key allows you to print the contents of a map。

Maps will allow you to modify the GlaAlibub class more easily， but maps are incredibly fast too。



![](img/059b632286a2b89a47d1f7fbf22a971e_23.png)

When files are large， efficiency matters more than when they're small。



![](img/059b632286a2b89a47d1f7fbf22a971e_25.png)

This concept of using efficient structures or code is important。

 Comps are so fast that simple concepts lead to code that's fast enough。

 given how fast computers are today。

![](img/059b632286a2b89a47d1f7fbf22a971e_27.png)

As you can see in the first row of the table， counting how many times each word occurs in Shakespeare's Juliaus Caesar is fast enough on a laptop computer。

 even using the parallel array list。With a bigger file like the sayings of Confucius。

 the code for a Raylist is still under half a second， whereas the hashmap code is incredibly fast。😊。

For the novel， the Slet letter， there are many more unique words and total words。

 but the hashmap code is still roughly 10 times faster than the aist coat。



![](img/059b632286a2b89a47d1f7fbf22a971e_29.png)

For a large file， like the King James version of the Bible with over 800000 words and 32000 different words。

 the Arures code takes more than 20 seconds。 While the hash mapap code is under half a second。



![](img/059b632286a2b89a47d1f7fbf22a971e_31.png)

That's more than 40 times faster。Looking up keys in a map takes time that's independent of the number of keys。

 Roughly speaking， this means getting the value for a key in a map with a million keys takes the same time as looking up the value associated with a key in a map of just 10 keys。

With an array list， you might have to look at all million elements in the array list。

 so a hash mapap is incredibly fast。In later courses。

 you'll study how the hashmap class can be so fast。In this course。

 you'll use hash maps in many examples， happy coding。



![](img/059b632286a2b89a47d1f7fbf22a971e_33.png)