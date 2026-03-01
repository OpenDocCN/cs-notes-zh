# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p86 11_02_02_使用getline读取文件.zh_en -BV1Kp42117vh_p86-

![](img/9d310eb8bdde3aa3f3ee9b8228b62042_0.png)

In this video， we're going to walk through an example of using a very convenient function called Gitline。

We begin in Maine， and there are several local variables we need to initialize to Skitline。

We have a size variable， a length variable， and a line variable。

We're going to be reading lines from a file one by one。

 and line will always point to a buffer containing each line currently being read from a file。

 The size variable will tell us how large the buffer is。

 and the link variable will tell us how long the actual string is that we've stored in the line buffer。

 We also need to open the file itself in read mode。

 We can see that the file contains three names that we're going to read from it。

Now we're going to start reading these lines。One by one， using the getline function。

Usually for a library call， we abstract away the details， but in this case。

 we want you to learn what Gitlineang does， so we're going to create a stack frame for it where you can see its three parameters。

The first one is a pointer to the line buffer。 So we've passed in the address of line。

 We haven't actually allocated memory for this buffer。

 So line P is pointing to a pointer that has the value null。 And that's fine。

 Get line can handle that。The second parameter is a pointer to the size。

 so we've passed in the address of size。 This tells us how large the buffer is。

 and since we haven't allocated the buffer it zero。

The reason Gitline takes a pointer to the size variable， not the size variable itself。

 is so Gitline can change the size once it allocates a buffer of appropriate size。

The third parameter is a pointer to the file to be read， so we've passed in F。

Now we're going to call getline。Making note of the call site location and moving our execution arrow into Giline。

 we're not going to show you the actual code for Gitline。

 rather we're going to use an appropriate amount of abstraction and list the four primary tasks that you should know about。

The first thing Giline does is allocate memory if necessary。In this case。

 the buffer we've passed in is null， so Git line will allocate space on the heap where it can write the first line it's going to read from this file。

In this case， it allocated 8 bytes， it's Giline prerogative to decide how much memory it's going to allocate。

 but we will find out exactly how much was allocated because the next thing Gitline does is update the size variable。

After creating a buffer and updating the size， it then reads the line of the file and stores it into the string。

As you can see， we've read in a word as well as the backslash in or new line character。

 which indicated the end of the line， as well as a backslash0。

 which indicates the end of the string inside of the buffer。

The final thing Gitline does is return the length of that string。

 which is4 back to the calling function。Keep in mind， the new line character。

 but not the null termminator is counted in the length。Next， in this assignment statement。

Length will be updated from 0 to 4， and we go inside the while loop。Where we print out the line。

Notice that we didn't have to include a new line character in the print statement since it was included in the string itself。

Now we're ready to read the next line， once again， we create a stack frame for a gi line。

 passing an a pointer to the buffer。A pointer to the size and a point to the file that we're reading。

We note the call site location and step into the function when it's time to allocate memory。

 line actually points to something， a buffer of size 8。

 so we don't actually need to allocate more memory。We also don't need to update size。

Now we read a line from the file into the string。Notice that we overwrote the original buffer because we gave Giline the same buffer that we had been using before。

If we had wanted to maintain the first string， we would have had to store it somewhere else。

Now we can return the length of the new string into the calling function where we complete the assignment statement。

 updating length to6， and enter the while loop。Where we print the new name。

Now we are ready to read the next name from the file。 We place another call to getline。

It doesn't need to allocate memory。Or update size。So it reads into the string。

 but the buffer has insufficient size to read the whole line。

It is important to realize that Gitline might need to reallocate memory。

 in which case it allocates a longer buffer， copies the existing data， freeze the old buffer。

 and updates line to point at the new buffer， and update size。

Now it can continue reading into the string。This time there is sufficient space。

 so we return the length1 the10 and go back to the call site。We complete the assignment statement。

 enter the while loop， and print the name returning to the top of the while loop。

We place one more call to getline。We don't need to allocate memory or update size。 However。

 this time， when we read into the string， it reaches EOF and returns negative 1。

 so we leave the function without executing the other steps。

Complete the assignment statement and skip the wire loop since length is not greater than or equal to 0。

 Since we are done with the memory allocated on the heb， we need to remember to free it。Finally。

 we can exit our program。Note that in a real program， you would also want to close the file。



![](img/9d310eb8bdde3aa3f3ee9b8228b62042_2.png)