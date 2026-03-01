# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p141 52_03_03_在Rust中使用JSON.zh_en -BV11y411z7Dn_p141-

Let's take a look at how we can work with Jasonson in rust we've had seen already a few examples on how to accomplish these。

 but let's dive into a little bit of details of what is it needed first let's start with the dependencies and both C and insert Jason are very common to use especially the feature of C which allows us to give some attributes to our strs and all of our vectors and all of the things that were well not the vectors。

 but thestructs and sometimes the types we can actually say well you know we want to make these be able to serialize and sometimes dec serialize into JO so both of these things are usually needed and in this case we are going to build a program that is going to define some rules in Jason and I actually have that。



![](img/d6d4d7fc5a51aa5e57df6a36a61d5c08_1.png)

File already there， but I'll tell you all about it in a second next what I want to show you is our main DRS file I'm going to go all the way to the top so that you can see where we using these things so we have these serialized there。

Because we are going to get JasonN as input and we're going to use Ct J later to work with that Jason al right so the first thing that you might want to do I mean depending on what type of application you have is that you're going to load the JN rules that are defining your program like now if you're going to do this and you're going to package that you will have to include rules that Jason of course but why would you want to separate these two things and we'll see that in detail later is because you may have you may not have like two or three or10 or half a dozen rules。

 you may have like you know 2000 rules and that starts becoming unmanageable if you start doing that with rust itself so having something separate like Jason is a good approach now might as well。

Be using something like YaAml as well or Tamil or any other type of plain text file。

 but definitely having that separation allows you to be very flexible in separating what's the logic。

 the business logic of your application。But we're concentrating today in seeing how we can make it work so first is make sure it's included。

 we're going to define this as a constant and then these is are going to be our main thing we're going to rely on statictyping for our for how we're going to handle the reading of the JN and serializing or desalizing into rust now this struck here will have basically the definition on how these data is going to be structure so we're going to have a path regular expression file permissions and require field files which is going to be a vector of strings what does that actually mean in JSON that we're going to have an array of strings there so that looks fine and this new method right here will allow us to create this ones very easily when we're dessealizing I'm going to scroll all the way here。

I'm going to load the rules， this is going to be how you're usually going to this is a very common approach to loading and deerilizing that So we're going to not accept necessarily anything into our function and we're going to return a vector of rules that are going to be read from that JSO file so the loaded JN is going to come from search JsonN and we're going to say from string we're going to load all of that JN that was loaded at the very beginning of the file as a constant and I'm doing very sloppy handling here not dealing with errors but for the example it is just fine so I'm going to read from that and then we're going to create a new vector if we were talking about ja this would be kind of like a new array but this is a vector。

 this is rust and what we're going do is going to loop over all of the loaded JsonN because we're assuming that this is going to come in a big array that is going to have all of our rules which in fact is because I know because I wrote。

The rules that Jasonson so I know the format and for every single rule I'm going to push a new compliance rulestruct and that's going to have the rex the file permissions and the required files and finally i'm going to return the rules which is what this is going to be the vector that has compliance rules so that's it that is how you would load things from J into rust and then use them and then main the main function is not doing anything it's just loading them and then printing them tag character right there ensures that it pretty prints the output on the terminal take a look at the rules that J for a second here and again like I told you this is going to be a big array is going to be a of objects this is one object and we're going to be able to produce all of these rules that we have here so we have the regular expressions。

 the file permissions and password password and group in a required files inside。

The etsy directory so pretty useful where we are seeing you know， let's see several several files。

 several rules here， not tremendous at tremendous amount， but just for the sake of the example。

 it's very useful indeed so。Whenever we are reading into this， will it will go into a was no problem。

 so let me actually toggle the terminal so you can see this I'm going to do cargo run。

And you can see that I was able to now this is no longer Jason。

 I'm loading all of that into into rust and then printing all of the output。

 so this is actually rust already things loaded into rust these theseses arestruct。

 it is no longer Jason so pretty useful there on how to accomplish this and do this into rust and have the ability to work with external data that might be living in a file with a format like Jason。



![](img/d6d4d7fc5a51aa5e57df6a36a61d5c08_3.png)