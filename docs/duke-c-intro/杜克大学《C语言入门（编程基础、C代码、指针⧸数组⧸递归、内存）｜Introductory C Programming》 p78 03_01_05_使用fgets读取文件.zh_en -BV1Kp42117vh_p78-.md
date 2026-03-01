# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p78 03_01_05_使用fgets读取文件.zh_en -BV1Kp42117vh_p78-

![](img/ad75d3366909a2c64b08a345fee4ea4c_0.png)

In this video， we have an example of reading from a file with FGS。

 which reads lines of a specified length from a file In this example。

 we will convert each line of text to an integer with the function ATOI。

 add each integer to the sum and print the result。For the purposes of this example。

 the array that we're going to read our characters into is going to have a relatively small size。

 We define line size here as a constant5， make the array that big and also tell F gides that we want to read into an array of size 5 We're going to do this for the purposes of example so we can see what happens when F gides cannot read all of the characters on a line。

As before we've omitted some error checking， assuming that we would print an error message and exit under these two conditions。

We begin with our execution arrow just inside main， where Arg C has the value 2。

 and Arg v is a pointer to the array of command line arguments。

 we assume that the name of the program is some numbers and that Arg v at1 is the name of the input file nus。

 TxT， which has the numbers in it。We see if ArgC is not equal to 2， it is2。

 so we don't do any of that error code。

![](img/ad75d3366909a2c64b08a345fee4ea4c_2.png)

We're going to open this file for reading， as we've seen before。 The file has numbers in it。

 and the current position in the file is at the start。F is not null。

 so we don't do anything special there。We make a box for total， which is zero。

 Then we create the five boxes for line， each of which will hold a character。

Now we're ready to call F gis。 It's going to read into line filling in the boxes with the information it reads from the file。

 We tell it that there are at most five boxes that it can read into。

 which really means four characters plus an null terminator character。

 which it has to put at the end。The last argument tells it to read from F。As we do this。

 notice that the cursor in the file showing the current position is at the start。

 and it's going to read across the line as we fill in the boxes with the text。

So we just read 123 and a new line， as well as a null terminator into line。

 which filled the five boxes， and now the current position is in the file is at the start of the next line。

Remember that the function Stchar takes a string and a character and returns a pointer to the first occurrence of that character if it is found in the string。

If it is not found， it returns null。 So this is going to check if line contains a new line。

 letting us know if F getS was not able to read the entire line。In this case。

 it returns a pointer to the fourth box， which is not null。

 so line contains a new line and everything is good。We're now going to convert the text 1，2。

3 to the integer 123 and add it to total， which is 0，0 plus 123 is 123。

 so we change total to 123 and we return to the top of the while loop。

Now we're going to call F gets another time。 It's going to read this next line into the variable line。

 noticeice that it wrote one for new line， then an alter terminator here。

 and left the last box unchanged because it had already read the entire line。

We again do Stchar of line and the new line character。We find that it is not null。

Then we add 14 to 1，23， and we get 137。We update total to 137。And we go around the loop again。

Notice that the number on the next line， negative 5，6，7，8，9 is too big to fit into the variable line。

 It has more than the four characters we're able to read。

 So F gets is going to read as much as it can and then stop。 It going to read negative 5，6，7。

 and then it' is going to stop because we told it that the array has at most five characters。

 and it needs the last one for the null terminator。The position in the file is between 7 and 8。

 If we were to read again， we would read 8 and 9， whether we use F giS or F gi C or any other function that reads from a file。

 However， for this code， it's not set up to be able to handle that。

 So we have error checking for not reading the whole line。 If we were to make line size bigger。

 we would make this all succeed Here， we do the check for the new line character。

 Stirchar returns null。And we'll do the error handling。 We print line is too long。

 and we exit failure。Notice that we haven't closed the file since we'll learn how to do that shortly。

