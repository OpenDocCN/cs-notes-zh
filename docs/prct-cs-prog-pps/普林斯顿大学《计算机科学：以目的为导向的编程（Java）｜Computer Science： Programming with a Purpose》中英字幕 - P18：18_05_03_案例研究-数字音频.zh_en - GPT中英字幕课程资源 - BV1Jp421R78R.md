# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P18：18_05_03_案例研究-数字音频.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/060f8ac4647e0c332310e29ec9cd9b37_0.png)

As a really compelling example of the utility of being able to define our own functions。

 we're going to talk about digital audio。We'll give a quick crash course in sound。

 this is not a physics course and we'll do the minimal amount in terms of what sound actually is。

 but we'll say it's the perception of the vibration of molecules and we're going to work with musical tones which are steady periodic sounds。

A pure tone tone is a sine wave， a sinuc settled waveform。

Now in music it's the frequency of the sine wave that makes the different notes。

 so 440 hertz is concert A， and there's a 12 notes in our scale and they're spaced logarithmically。

 what that means is so concert A is 440 frequency， 440 peaks per second。

Then the 12 things are 12 notes are space logarithmically。

 that means their frequency is 440 times 2 to the I over 12。

 where I' is the index of the note above concert A， so B is 440 times 2 to the 16 power and so forth。

And by the time we get up to the 12th note。Whi is an octave higher than that's 440 times 2 to the 12 over 12 or it's double。

 so if we double the frequency of concert A we get 440 to 880 and we get a note that's an octave higher and those are the waveforms。

 the peaks occurring more frequently。So that's the basic idea of how we get music。

 we produce sinusidal waveform， and that vibrates molecules that we hear。All right。

 so what we're going to do with digital audio is represent a wave by sampling it at regular intervals and saving the values in an array。

 just the same way as we did when we plotted a function in the previous lecture。

So this is concert A taking 5，512 samples per second， and so140th of a second is just 137 samples。

In the same way as in the previous lecture when we plotted a function， if we take more samples。

 we get a more accurate depiction so this is 275 samples per second。

 is I'm sorry for 40th of a second 275 this one's 22000 samples per second so there's 500 in our 40th of a second and this one's 44100。

 and you can see that's a there's a lot of samples。

 but it's a pretty good representation of the wave。

 This is the standard that's used for digital music in CDs for example。

 so that's the one that we're going to use Now there's a lot of points but we have a computer and so we can represent a lot of points and we have arrays and we have functions and you'll see that even though there's a lot of data it's not difficult to write programs to manipulate it and therefore process sound。

So sound is nothing more than as of double values， these samples。

 and we're going to write programs to manipulate them， so let's take a look at how that works。

So the main thing is our standard audio library， which is like our standard draw library and others。

 providing output of your program， we developed it for this course but it's available from a standard download of our course software。

 so what we do is the main function in this library is to play a sound wave。

 it's given an array of double values and it plays the sound wave on your computer's audio output。

 and there's a standard file format called the do WAV file format that you can also store arrays of doubles the library converts those into the standard format。

So there's a method play to just play a given file。

 there's a method to just play the sound wave that's in the array now so for a second the size of that array is 44。

000， so for 10 seconds it's half a million。Double values。 And so you can if you have a lot of sound。

 you're going to have a lot of data and these arrays are going to be big， but that's fine。

 you have a fast computer。 You can play 144，100th of a second， you can save to a wave file。

 you can read from a wave file， but what our library does is allow you to hear the results of your program that manipulates sound。

 It's an output library for sound。In just a few methods。 So let's take a look at how to use it。

 Again， this is the hello world， the simplest program to play some sound。

So we're going to use a function that takes as argument， the pitch or the hertz。

 so it's 440 for concert A or 880 for an octave higher in a duration。

 so how long do you want to play that？And that's in seconds。

So for one second it's 44 or 100 samples for 10 seconds it's 10 times that and so forth so n is the number of samples that we have to take it's also the size of our array so we build an array that's the size n well n plus1 to handle the endpoints and for i from0 through n what we do is we sample the sine wave and the sine wave we have to sample you can check this math it's not a big deal we want to we want to take whatever the hertz is and then multiply that by2 pi divide by 44 or 100 and then for each integer I that's the point that we want to get so i's along this scale and that's the function that we want to sample。

In return A， so that's all that does is it takes that particular sine wave。

 the one that's governed by the pitch and samples it 44100 well multiplies the duration。

 samples it 44， 100 times。It creates the array that corresponds to a tone at that pitch for that duration。

So that's our function that we're going to use to manipulate tones and this is just the hello world。

 so what we're going to do is take the pitch from the command line and take the duration from the command line。

 and then just fill up an array， create an array， and fill it up with a tone of that pitch and that duration and then play it。

So that's all there is to it， so let's hear what it sounds like。

 so if I invoke this program with 440 for concert A in three seconds， then here's what I get。

If I want to play an octave higher。I just put 880。I don't necessarily have to do something that's on the Western music scale。

 you can put any frequency you want。Well， that's lower。That's an octaive lower。

 and then this is just an arbitrary frequency。So fill an array and play it in that sound。

So now let's look at something a little more interesting。

So what we're going to do is have a data driven program where we put a list of tones and durations on standard input and then we just read them and that way we play a tune so this tune many of you maybe are familiar with you'll hear it in a second how's this code going to work so our。

What we want to do is we're going to control the tempo from the command line。

 so we'll multiply all these relative durations by another number that comes from the command line。

And then we'll go in and read from Standard in， we'll read our notes。

So the first thing is the pitch that's what step is it above Con A， second thing is the duration。

 so we'll take the relative， that's an eighth note but we'll multiply it by the tempo。

Then we'll compute the frequency from the pitch。So we numbered the notes zero starting at concert A up through 12 and octave higher。

 and we want to take two to that number divided by 12。

 and so that's what mapped that pound and multiply by 540 and that gives us the frequency from the formula that gave right in the first slide。

Then we'll just play on that note so that was in the previous slide we had the code for tone and that's how you invoke that function from here we play it for the given frequency in the given duration we'll talk about this mechanism more later on。

And then play it so create the note and play it and stay in the while loop reading the notes from standard input and then when you're done we have a closed function that eliminates an annoying pop so let's see how this works so I'm going to Java play that tune I'll play it slow first。

So there's really quite a amount of data flying around with this program。

 each note involves thousands and thousands of doubles， but you can seede the possibility I think。

 want to play it twice as fast。Yeah。Yeah。So opens up endless possibilities and all you need is a file like that and you can play a song and you go to the book site there's lots of files that students have created over the years Its just something to think about before we move on to a more complicated program What sound does this program produce what it does is fill an array with random values。

 a big array 44 100 times 11。And the answer is。It plays noise。Random values， that's what noise is。

It's playing for 11 seconds， I'll stop it now。Okay。

 so now let's do something more interesting now one thing that we can do is make chors if you take two waveform and you average them。

 then it's like playing the notes at the same time so。What's a waveform。

 a waveform is an array of double values if we have two of them， let's say A and B。

 they've got to be at the same length， then we'll take a new array C and just go all the way through and just set C to the average of the values in A and B and that's a new waveform so if this is a and Bs fluctuates more often if you just average them you get another looking waveform and it's like playing the notes twice so let's look at a。

More complicated library that is going to have now we're going to have that average function and then we're going to have a function chor that takes two pitches and a duration and then what it will do is get the it'll compute the frequency for both pitches it'll create an array with the tone for the first one again using our tone function and another one with a tone for the second one and then it'll average those twos and return it so this is just crunching the numbers。

 make one make another one average the values and that's a chord well technically it's a two note chord so and then we'll just have a driver that takes the two pitches from the command line and the duration and then puts that in the new array and then plays it。

So。Here's A and C for five seconds。It's like playing the two notes simultaneously。

And we can say play concert A and an octave hire at the same time。

That's known as a harmonic and actually harmonics are important in music。

 so what we can do is make the tune sound a little more natural， more realistic by adding harmonics。

 so let's look at how that works。So if we have concert A。

 then we can go ahead and make an array it's get all those numbers。For the duration。

 but then what we can do is take double the frequency so that's an octave higher and make that one and we take half the frequency。

 that's an octave lower and make that one and then what we can do is average the high and the low one and we get something in between that's both harmonics and then average that one with our main tone and that' we get a different thing it's not a pure sine wave。

 it's got the harmonics included。And most often， when you listen to music， you're hearing harmonics。

 you can do more， much more complicated things to get a more interesting sound。

 but let's look at what happens when we do that。 So now our note includes the harmonics。

 And so if we add that to play that tune。 I won't do the code。

 It's just substituting in this function that plays that does a more interesting note。

 Sound like this。🎼，🎼，🎼，🎼，Not perfect， but much more realistic than our original with pure tones。

 and you can see where to go if you're interested you can add in other harmonics。

 add chords as many more things that you can do just with standard audio having the ability to compute with and play music。

And again， you can。There's no end to what you might do。Oh。



![](img/060f8ac4647e0c332310e29ec9cd9b37_2.png)

Bottom line is that you can write programs to manipulate sound。

 you can provide inputs of any type that you want to add harmonics or do what you want。

 but let's not lose sight of the original purpose of this lecture and that's really it's a case study of how useful functions are this computation is organized as a bunch of functions there's a lot of function calls the flow of control is quite complicated。

 but there's no problem understanding what this is doing。

Functions provide us with the flexibility in the flow of control to organize our computations in small pieces。

 that's modular programming and that's what functions are all about and we'll have assignments where you get to do some more interesting things with musical tones。



![](img/060f8ac4647e0c332310e29ec9cd9b37_4.png)