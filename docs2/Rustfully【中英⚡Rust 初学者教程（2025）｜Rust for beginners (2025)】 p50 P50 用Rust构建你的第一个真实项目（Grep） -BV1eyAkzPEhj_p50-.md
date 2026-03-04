# Rustfully【中英⚡Rust 初学者教程（2025）｜Rust for beginners (2025)】 p50 P50 用Rust构建你的第一个真实项目（Grep） -BV1eyAkzPEhj_p50-

How's it going everyone In today's video， we're going to be building Gr a command line tool to search for lines matching a pattern in text files。

 This is what it's going to look like。 We're going to open up the terminal And here we're going to type in cargo run and using the command line we can insert some text or a pattern that we want to search for in a text file For example we might want to search for the occurrences of Bob in a text file。

 so we can do that And next I'm going to insert text1 do Txt。

 And then add a flag which triggers case insitive mode Since I'm searching for Bob with a lowercase B。

 Now if I were to run this what I would get back are these lines from my text file Each one of these lines contain the term Bob and if I go to my text file you'll notice that Bob is mentioned in each one of those lines So this practically filtered out the lines that did not mention Bob and we can even search for。



![](img/08e3e4950ee4c0131327b3c6bc9de685_1.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_2.png)

Bob in multiple files so here I'll clear the console and instead of just searching in text1。

xt I'll also search in text2 doxt And just in case you guys are curious I have these text files directly in my folder as you can see here I have text1 and text2 and this is in the folder that contains the Ta and the source anyway as soon as we tap on enter it's going to search in both files right now in text2xt I only have one line that says Bob in T2 but otherwise it found all the lines that contains Bob in those two files we can even get more specific with our pattern by entering a string such as Bob was en tapping on enter and just like that we were able to search for this very specific pattern and it gave us this back Bob was powerless up against such a question and there was only one line that mentioned that in text1 TXt so that's what we're going to be learning how to make today a very simpl。



![](img/08e3e4950ee4c0131327b3c6bc9de685_4.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_5.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_6.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_7.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_8.png)

Version of Gr， the more advanced version has many more features that you can use。

 but for our first official project， we're not going to be using all of those advanced features and we're going to save that for a future project so the very first thing we're going to do is create astruct called config and that stands for configuration and it's going to contain a pattern the files to search through and that will be a vector of type string and a flag called case insensitive。



![](img/08e3e4950ee4c0131327b3c6bc9de685_10.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_11.png)

And I know very well that we have not covered vectors just yet。

 but for now just think of it as an array which you can add and remove elements from as soon as we're done with this project。

 we will continue with the rustbook and cover vectors then right below thestruct we're going to create an implementation block for our configuration and the very first method we're going to add is the new method which takes arguments and those arguments are going to be a slice of string references and here we pass a borrowed part of a vector so we can look at the arguments without copying or taking ownership of the whole vector and this will return to us a result which will contain config if it is okay or a string if it is an error and the very first thing we want to do inside here is check that at least a pattern and one file is provided So what we're going to do is type in if ags dot length。



![](img/08e3e4950ee4c0131327b3c6bc9de685_13.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_14.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_15.png)

Is less than three then we're going to return an error and here we're going to call format and tell the user exactly how they should be using our program。

 So here we'll type in usage placeholder pattern I don't know what that is but that's not a pattern pattern file or files and the optional flag of dash E and right outside we can pass in as at the index of zero Now what format does is allow us to place as inside the parentheses and return all of this as a string which we can return with our error because we defined here that we want to return a string inside the error as part of the result So if the user gives us a command。

 which does not have enough arguments chances are that they are not providing it in the correct format。

 So here we're just telling them that hey you should provide it in this format if you want to get something out of it but right under that check we can type in let's mute case insitive。



![](img/08e3e4950ee4c0131327b3c6bc9de685_17.png)

嗯。Equal falses by default， we want case insivity to be false。

 then we will let mute non flag arguments。

![](img/08e3e4950ee4c0131327b3c6bc9de685_19.png)

Of type vector string equal a new vector and a non- flagag argument is practically anything that's not something with a dash。

 such as this over here。 This is a flag argument So everything that's not this will be considered a non flagag argument that means that if we have a search pattern such as Bob and we have a text file that we want to search for such as text dottxt。

 these are non flagag argument So what we have to do next is check for argument in argument from the index of1 onwards。

 if the argument is equal to the flag of dash I， then we want to toggle case inensitive so that it is true else we will type in non flagag arguments。



![](img/08e3e4950ee4c0131327b3c6bc9de685_21.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_22.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_23.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_24.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_25.png)

Dot push arguments dot clone And what push does is append an element to the end of the vector。

 And for now to make all the errors go away， I'm just going to type in okay and pass back a unit because that's very annoying。

 Also we have a little error up here and that's because I forgot to add the parentheses。

 But going back here， we use push to append an element to the back of a collection such as this one over here and we're pending the a dot clone。

 which is just a copy of the argument。 Now right below that we're going to type in if non- flag arguments is empty return this error error。



![](img/08e3e4950ee4c0131327b3c6bc9de685_27.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_28.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_29.png)

Patttern not provided two string because this has to be a string So all we're doing here is checking whether the user has provided a pattern。

 otherwise we can't look for it if there's no pattern provided below that we need to grab the pattern and that's going to equal nonflag arguments at the index of zero and we want to make a copy of that so now we have the pattern all that's left is to grab the files so if nonfl arguments dot length。

Is less than two then there's a chance that they did not add any files to their command。

 which means we need to return an error and here we'll type in error。

 no input files provide dot2 string， but if we pass this we can grab those files because there are files and that's going to equal the non flag arguments。

From the index of one。

![](img/08e3e4950ee4c0131327b3c6bc9de685_31.png)

Forward and we're going to convert that to a vector so now we have a list of the files and we have the pattern to search for plus so we don't forget we also have the case insensitive Boolean and this is all information that we want to give back via the OK return So we're going to return okay with the config and inside we will pass in the pattern。

 the files and the case insensitive flag and that's all the code we needed for the implementation of config right below that implementation block we're going to create a function called Gr file and this function will search for the pattern inside the files all type in function G underscore file and here will pass in the file which will be a string slice and the config which will be a reference to the config Now inside here we want to match。



![](img/08e3e4950ee4c0131327b3c6bc9de685_33.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_34.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_35.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_36.png)

File and this is going to import file from the standard library。

 so make sure that you get this import at the top， usually if you're using Zed or any other code editor as you're typing it it's going to give you the option to import it as you type it out Sometimes I mess up and I miss that so I continue typing file but the import isn't there and that obviously causes my program to not compile or to even panic but as long as we have this file we can open the file and the first thing we're going to do inside here is handle the okay case。



![](img/08e3e4950ee4c0131327b3c6bc9de685_38.png)

So inside here， what we want to do is wrap the file in a bufferuffett reader for efficient line by line reading。

 and it's going to look like this。

![](img/08e3e4950ee4c0131327b3c6bc9de685_40.png)

Let mut reader equal a buff reader like a very strong reader， okay。

 that was a terrible joke and we're going to import this one from the standard library。



![](img/08e3e4950ee4c0131327b3c6bc9de685_42.png)

New and file then right below this we were supposed to use Gr but because I messed up the script and I created the function after this。

 we're just going to add a placeholder and we'll come right back to this but to make sure that we don't forget about it we're just going to panic here with the reminder add Gr function and just because this really bothers me I'm also going to provide the error and here we're going to type in。

Error print line。Could not open file， placeholder in quotes。And placeholder。

And that will contain the file and the error message。 So once again。

 we do not have the grab function just yet。 That's something that we're going to code right now。

 So right below Gr file， I'm going to do it right above it， because for some reason。

 I defined it right below Gr file。 That's why in my script。 I didn't see it。 We're going to type Gr。



![](img/08e3e4950ee4c0131327b3c6bc9de685_44.png)

It's going to take a reader。

![](img/08e3e4950ee4c0131327b3c6bc9de685_46.png)

And that's going to be a mutable reference to Buff reader。

 which will be wrapped around a file object。 Then we want to provide the pattern。

 which will be of type string slice and case inensitive， which will be of type bulloleing。

 and the very first thing we'll do inside here is let a mutable line equal a new string。

 Next we want to create some functionality that reads each line until the end of the file。

 So what we're going to do is type in while let OK。



![](img/08e3e4950ee4c0131327b3c6bc9de685_48.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_49.png)

With the bytes red， equal the reader dot read line and pass in the buffer。

 which will be a mutable reference of our line。 So Read dot read line grabs a line on each iteration and assigns it here。

 If it is okay， it will continue with the while loop Otherwise the while loop will terminate and on each iteration。

 line will contain the current text of the line Now to exit out of the while loop。

 we need to add a check called if bytes is equal to0 break。



![](img/08e3e4950ee4c0131327b3c6bc9de685_51.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_52.png)

And this should actually be by red because even if the status code is okay if there are no byte red。

 it means you are at the end of the file so you want to break out of the while loop then right below this we want to check whether our line matches the pattern so here we can type in letmated and we will initialize this later for now we just need to create it and then we can type in if case and sensitiveitive is true。



![](img/08e3e4950ee4c0131327b3c6bc9de685_54.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_55.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_56.png)

Then matched is going to equal line2 lowercase and check whether that contains a reference to pattern。



![](img/08e3e4950ee4c0131327b3c6bc9de685_58.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_59.png)

To lower case else matched is going to equal line dot contains pattern。

 which is K sensitive and finally。

![](img/08e3e4950ee4c0131327b3c6bc9de685_61.png)

If we have a match， we're going to print the current match and at the end of each iteration we want to call line do clear to clear the buffer so it can be reused for the next line and that takes care of our Gr function Now we can go back to our Gr file function and add the Gr code here so here well type in add mutable reader and then pass in a reference to the configuration do pattern and the config do case insensitive bullole so pretty much if we manage to open a file successfully we can then attempt to use Gr on it otherwise we'll return an error Now the very last thing to do is to create our main function and inside here we're going to return a result with the unit type and a string for the error and at the bottom we're just going to return okay with the unit type so that we don't have to deal with all that syntax highlighting at the top we're going to type in let arguments equal a。



![](img/08e3e4950ee4c0131327b3c6bc9de685_63.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_64.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_65.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_66.png)

of type string and that's going to use something new called an environment which we can import from the standard library once again and here we want to call arguments and collect so this part over here returns an iterator over command line arguments and what collect does is consume the iterator and collects all the elements into a vector which is a type that we can use much more easily then we can type in let the configuration equal config new and we're going to pass in a reference to our arguments and call the trioperator and that's the only reason I decided to return this result so that we could keep this nice and clean but of course you're more than welcome to remove this and just use a match expression to handle what happens to the config finally the very last thing to do is to loop through the files so for file in the reference of config do files grab that file。



![](img/08e3e4950ee4c0131327b3c6bc9de685_68.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_69.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_70.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_71.png)

![](img/08e3e4950ee4c0131327b3c6bc9de685_72.png)

ThatAlmost sounds dirty。 And that was the last line of code we needed to make this program work。

 Now it's finally time we open up the terminal and navigate to our project。

 which in this case is called main and try to use Gr on these two text files。

 So here we're going to type in cargo run dash dash followed by the command line prompt。

 So to get started， I'll type in Bob followed by the file。

 which will be text1 do Txt and I'm not going to include any flags just yet。

 we're just going to leave it as is As soon as we run that。

 we should get back all the lines that matched our pattern。 So this one contained Bob。

 this one contained Bob。 This one contained Bob and this one contained Bob。

 Next we can try to match for something called his cat。

So I'll clear this and instead of Bob we'll type in his cat。

And we have to add quotation marks for that。 Then I'll also add text2 just to check that it works。

And tap on enter。 So Bob did not respond to his cat。 and that worked perfectly。

 As you can see inside here， we had a line that contained that pattern going back instead of his cat。

 Let's change that back to Bob。In upper case characters。

 and this time I'm going to use the case insensitive flag。

And what we should get as an output are all the occurrences of Bob in all the files。

 regardless of how it was written and that concludes our very first project in rustt or at least our very first real project in rust and there are still a lot of problems with this program but it's good that we're starting to get some practice with coding in rust and also one last thing in case you want the source code for this project I will be uploading it to my GitHub repository so feel free to check it out and to copy it into your own code editor in case you find that to be much easier or in case you missed something and your program won't compile for whatever reason but otherwise with all that being said thanks for watching and I'll see in the next video。



![](img/08e3e4950ee4c0131327b3c6bc9de685_74.png)