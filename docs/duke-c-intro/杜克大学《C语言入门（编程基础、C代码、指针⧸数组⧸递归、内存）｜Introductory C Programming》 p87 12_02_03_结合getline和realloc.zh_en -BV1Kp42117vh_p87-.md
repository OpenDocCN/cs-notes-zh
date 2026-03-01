# 杜克大学《C语言入门（编程基础、C代码、指针⧸数组⧸递归、内存）｜Introductory C Programming》 p87 12_02_03_结合getline和realloc.zh_en -BV1Kp42117vh_p87-

![](img/2fa159a7a25255d9abd95a5dce16c6cd_0.png)

In this video， we're going to put together some of the concepts we've seen in this course。

 as well as previous courses in the specialization into a slightly larger example。

We're going to use get line and readalEC to read lines from a file。

 increasing the size of the array that holds the lines each time we read one so that we can store them all in memory at once。

Once we have them all read in， we're going to sort them。

 and then we're going to print out the sorted result。

 This sort function is not something from the C library。 We've written it ourselves。 It uses Q sort。

 which you saw in the previous course。 We're not going to show the details。

 but it will rearrange pointers in an array， such that the strings they point to are sorted with string compare。

Now， we're going to step through the coat。We declare the variable lines and initialize it to null。

We declare the variable current and initialize it to null。

 We declare the variable size without initializing it。 We could， if we wanted to。

 but this will illustrate that get line will give it an appropriate value。And we initialize I to0。

And then we call getline。 We set up a frame and enter the C library。

Gitline determines that current is null， so it allocates memory and sets current to be a pointer to that memory。

Then it changes size to be the number of bytes allocated。 Next， it reads from the string past N。

 which in this case， is standard n。 So it reads the string cat followed by a new line and a null terminator。

And returns to Maine。The call succeeded。 So we enter the while loop。

 We're going to call realc on lines， which is null passing in 0 plus 1。

 which is one times the size of stard lines。 So we need space for one cha star。

 Re Allicking null is just like mallicking。 So we're going to get one box， which is uninitialized。😊。

Lines at I equals current。 So we're going to give the zeroth box of lines a pointer to the string cap。

Then we set current equal to null because when we call getline again。

 we don't want it to change this string。 We want it to all memory for a new string。

We increment I and return to the start of the while loop。Now。

 rather than stepping into getline again， we're just going to show its effects this time。That is。

 it's going to allocate memory for a string， change size to be the number of fights allocated。

Read in the string and from standard in。 This time， we showed it allocating a different number。

 a different amount of space， Only 5 by， which is exactly what it needs。

 We don't actually know how much space it will allocate。

 We just know that any space left over will be uninitialized。 In fact。

 how much space it allocates will be platform dependent。

We enter the while loop and reallic lines to be two char stars now。

 So we create a new two element array， copypy in the value of the previous array。

 leaving the second box uninitialized and get an arrow to the newly allocated memory。 lines at one。

 is going to get the value of current， which is a pointer to the string ant。 We set current to null。

 So we will get a new allocation next time we call get line。😊，Increment I， and go around again。

We call getline again to read the last line in the stream。 We read Alec our array。

And update lines at 2 to be current。 We set current to null， increment eye。

 and go around the loop again。Now， when we call getline， it is at the end of file。

 So we skip the wild loop。Notice that it still allocated some memory， which is uninitialized。

 so we need to free that memory。 We're going to call sort on the lines。 However。

 we're not going to step through it。 We're just going to know that it reorders the pointers so that ant comes before bread。

 which comes before cat。Now we're going to enter the loop that prints each string。

 so we print lines at0， which is ant。And then， we free that memory。Then we print lines at one。

 which is bread。And free that memory。We print lines at two， which is cat and free that memory。Now。

 we're done with this for loop。 Next， we're going to free lines。

 The memory pointed to by the blue arrow。 So that's going to go away。

Notice that we've cleaned up our heap nicely and freed all of that memory。 Now。

 we're going to return， destroying main frame。