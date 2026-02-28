# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p01 -01-Ph CS 219A Lecture 1 Introduction.zh_en -BV1KgffBoEUc_p1-

。Okay， here we go。 Hi everybody。 I'm John Preskill。

 and we're going to be friends for the next 10 weeks。

And I hope beyond because I'm going to be teaching physics。

 Comp science 219A and you're either taking it or interested in the course material， I guess。

 if you're here。Now I have to tell you that this is my first experience with teaching online and I feel some trepidation about it。

 I realize many of you have had experience with online classes and that's probably how you took your classes in the spring term but I wasn't teaching last spring。

 so this is really the first time for me。And I made a decision that I am going to prerecor my lectures and make them available to you。

 though'll be accessible on our class Google Drive。

I'm going to be lecturing from slides and I'll be providing you with those slides。

I'm a little concerned about that because I've always taught using chalk and a Blackboard。

 I think for a class like this one and any the other classes that that's a good。

Scheme for teaching because it means it's very conducive to presenting the material at a pace which is appropriate。

For learning。But I tried some of the tools that simulate the use of a blackboard and I wasn't very happy with the results for any of those。

 so I decided I'm going to make slides in advance and I hope that's going to work okay and if it doesn't seem to be working。

 maybe I'll change my mind about that。Now we're giving up a lot with the pre recorded lectures because we're missing the opportunity for some human interaction we could have had synchronous classes as some of the classes did at Caltech。

Last spring and will again this fall， potentially that could be more interactive。

 but after talking to instructors who taught last term and students I got the impression that at least for a class like this one interaction through lecturing on Zoom synchronously would not be very effective so we're not going to do that and I know many students might prefer to watch the recorded lectures at some time of their choice anyway it's convenient you can decide one to do it。

 you can pause it， you can take a break if you miss something， you can replay it。And actually。

 something that some of you may find particularly beneficial。

 I've often been told by students that my voice。Is soerific that it puts people to sleep and if that's the case。

 of course you'll be able to pause the video and take a nap or better yet you could try playing me back at a faster speed which might make it seem a little zipier and more exciting and there's a question about whether we really need the video lectures at all a good question about what value they will be adding to the class because we are going to be using lecture notes which are typed and available through our course website so we do want the lectures to be in some sense complementary of course there will be a lot of overlap between what's in lecture and what's in the lecture notes because they're lecture notes。

But I can potentially provide more of a big picture and guidance in a lecture that might be missing if you're just reading the notes。

 if you have suggestions about how to do that more effectively， I'd be glad to hear them。

Now in order to simulate some kind of interaction， we will be making use of online tools in particular we'll be using piazza。

 which is a kind of。Forum for discussions and asking and answering questions and so on I haven't used piazza before probably some of you had。

 but i'm hopeful that that will enable us to kind of stay in touch with one another and have discussions from time to time。

 so this is going to be an interesting adventure。For me and I hope also for you， I hope it'll be fun。

For me and for you， and the good news is that we do have some really interesting science to talk about in this class。

 which I hope you're going to find interesting。Yeah。Okay， and now let's share the screen。



![](img/059369b790d4dfaee85e985249cdae77_1.png)

So we are going to have TAs for the course， Tom and Charles and they will。

Have regularity scheduled office hours on Zoom and they'll also be available to answer questions using piazza those office hours are going to be announced later。

呃。Very broadly speaking， the topics that we're going to be covering in 219A include concepts like density operators。

 quantum operations， decocoherence， quantum entanglement。

Quantum circuits and quantum algorithms and complexity。

 and then the course will continue in the winter term。219 B will be taught by Professor Kataev。

 where the main topic will be quantum error correction and other special topics which he might decide to include。

As I've said， the primary source for。Learning in the class will be my lecture notes and there's some other suggested materials which you can find on the website。

 the course materials will be on the Google Drive which you can log into with your IMSSS credentials that's where it'll keep videos like this one。

And the slides for the lectures and other useful materials。

If you want to go directly to the course website which has a link to the Google Drive。

 if you can just remember my last name， Presll， it should be easy to find because you can Google me。

 I'm the only John Prescoll in the universe that I'm aware of and if you go to my homepage you'll find a link to the course website。

The class is by default graded past fail， there will be periodic problem sets。

 you will be able to hand those in through the Canva site well be using Canvas。

The learning management system that Caltech is broadly using this term to submit your homework and to have graded homework returned and as I said we hope to use piazza to stimulate some contact between the instructor and TAs。

And the students。So now in this first lecture I want to give to sort of an introduction to the subject。

 the style of this lecture will be rather different than the style of subsequent lectures。

 it'll be kind of brisk and we won't give you diving deeply into technicalities。

 but I want to give you some perspective on the subject。

Why I think it's really interesting and where I think it stands where it might be going。

 this is my personal perspective for the most part。

But I hope it will set the stage for what we're going to talk about later in the class。

Now we call the course quantum computation， which is a good name。

 it could have just as well been called quantum information science。

 which is a somewhat broader notion， quantum information science you can view as a kind of synthesis of three of the great themes of 20th century science。

 quantum theory， computer science and information theory and quantum information science。

may be setting the stage for revolutionary future technologies。

 and it's also giving us different ways of thinking about the physical world of thinking about and exploring and asking questions about nature。

Now， quantum information science is actually a rather broad subject and encompasses a number of things that。

We won't be delving deeply into in this class， but which I'd like to just mention in passing。

It includes the notion of quantum sensing， which means using strategies from quantum science to improve measurements in order to make more accurate measurements or to measure things on finer distance scales。

It includes the notion of quantum cryptography， which means using communication with quantum states instead of classical information to protect our privacy that's founded on the notion that if someone eavesdrops on a quantum communication the eavesdropping is detectable。

 and so it provides a kind of unhackable encryption。There's an notion of quantum networking。

 which means distributing quantum states among many parties。

 something that we might want to do for applications in quantum cryptography。

 and maybe for other purposes like making very sensitive networks of measurement devices distributed over long distances。

There's an notion of quantum simulation， which means trying to learn about the special properties of the physics of many particles interacting quantum mechanically using some type of quantum device or technology and quantum computing。

Means using a new type of computer which makes essential use of quantum physics to solve problems that would be too hard to solve using ordinary computing devices。

And another way in which quantum information， science is having a big impact on science very broadly is providing important concepts that we can use in other settings。

Including， as I said， to try to understand fundamental physics。More deeply。And as a physicist。

 the way I'd like to look at。This field of quantum information science。

Is that we're in the early stages of the exploration of a new frontier of physics。

 what we could call the complexity frontier or entanglement frontier because we are now。

Developing and perfecting the tools that we need to create and very precisely control very complex states of many particles。

Systems that are so complex that we can simulate them accurately with ordinary digital computers or understand how they behave very well with existing theoretical tools。

 and that opens new opportunities for discovery。So as physicists。

 if we want to understand the structure of matter at finer distance scales。

 then we build a more powerful particle accelerator。

 if we want to understand the early history of the universe on the universe or the universe on larger scales。

 we build more powerful instruments and telescopes。

And if we want to probe more deeply into this frontier of complexity。

 we will build more powerful quantum computers now I realize not all of you are physicists and the perspective of this class will be more of a computer science perspective to understand the notion of quantum computing as a model of computation and understanding the types of algorithms that we can win。

 that we can run on quantum computers， but I'll also particularly in the early lectures provide a foundation for understanding how quantum information。

 concepts can be applied to physical systems。嗯。So this idea that the entanglement frontier。

 the exploration of very highly entangled systems， and we'll be discussing what it means to be very highly entangled。

The idea that this is a fruitful frontier to explore comes mostly from two ideas， the first。

 I'll call quantum complexity。Meaning that with quantum devices。

 we can do things efficiently that would be too complex to do with ordinary digital computers。

 that's our reason for thinking that quantum computing is powerful as a computational model。

And the second important concept is quantum error correction。

 that's our basis for thinking that we can scale up quantum computers to large devices that can really solve hard problems。

 the reason this air correction idea so essential is that it's very hard to precisely control quantum systems to make a quantum computer perfectly accurate。

 and so we need ways of protecting against the damaging effects of error。Now in the winter term。

 you will delve into the topic of quantum error correction we won't get into that very much in the fall term。

 although we will lay some of the foundations for understanding it when we discuss。

The theory of decocoherence， So will mostly be focused on quantum complexity and algorithms after。

Laying the foundations with a few early lectures， which focus on。

How we think about quantum information。Yeah。Now， both quantum error correction and the notion of quantum complexity rest on a deeper underlying idea we call quantum entanglement。

And quantum entanglement is the word we use for the characteristic。

Interactions or correlations among parts of a quantum system that are different from the correlations we encounter in ordinary life。

The essence of it is that with quantum systems， even if you know everything about the parts of the system。

 you could be missing a lot of information about the whole， so you can envision that this way。

 we can imagine that we have a book which is 100 pages long。

 and if we suppose it's an ordinary classical book written in bits。

 you can read those pages one at a time and every time you read another one at the00 pages。

 you know another 1% of the information content of the book。

And after you've read all the pages one by one， you know everything that's inside the book and now let's imagine that it's a quantum book。

 it's not written in ordinary bits， it's written in their quantum analog， what we call qubits。

 we'll be talking a lot about qubits。And let's suppose the pages are highly entangled with one another。

So that means when you look at these pages one at a time， what you see is just random gibberish。

 which reveals very little information that distinguishes one highly entangled book from another。

And even if you've read all of the pages one by one。

 you're still missing most of the information that's in the book。

And that's because in this highly entangled quantum book。

 the information doesn't really reside on the individual pages。

Rather it's encoded almost entirely in the correlations among the pages。

 so if you want to read the book you have to make a collective observation on many pages at once that's the essence of quantum entanglement that there's information in the whole that you can't see when you look at the parts one at a time and that's a very different notion of correlation than we're accustomed to in the classical world。

Now， one thing that's interesting about these quantum correlations。

 about this entanglement is that it's extremely hard to describe it succinctly with ordinary classical information。

If I wanted to give you a complete description of all the correlations among just a few hundred qubits expressed in terms of classical information。

 I'd have to write down more bits than the number of atoms in the visible universe。

 even for just a few hundred qubits， and so that'll never be possible to do even in principle。

So there's something。Very extravagant。In nature， so that at least from a classical point of view。

There's a vast amount of information needed to describe a quantum system of rather modest size。 Now。

 that in itself doesn't necessarily mean that by operating a quantum computer by。

Performing a computation which processes qubits rather than bits that we can do important things that people would really care about。

But we do have several reasons for thinking that quantum computing will be a powerful technology which can have an impact on the world。

One is that we know by now examples of problems that we believe are too hard to solve classically。

 but which at least theoretically， quantum computers will be able to solve efficiently once we're able to build quantum computers at a sufficiently large scale。

The best known example of this is the problem of finding the prime factors of a large composite integer。

 and we'll be talking about how a quantum computer solves this problem in detail。Later in this term。

 it was really a earth shaking event。At the time it was discovered in 1994 by Peter Sho that quantum computers。

 at least theoretical， had this ability， now the reason we think factoring is such a hard problem。

 is that really smart people have been trying for decades to come up with better factoring algorithms。

 there's a strong incentive to do so because solving factoring can be used to break widely used of the key cryptoystems。

 and yet after decades of effort still the best factoring algorithms that we know have a runtime on a classical computer which is super polynomial in the number of digits of the number to be factored but that's not true quantum mechanically。

 it's not true of quantum computers and so that was riveting to learn it seemed to establish an important separation between the ability of quantum computers to solve problems and ordinary。

Clasical computers。We also have arguments from the theoretical computer scientists that you can do a quantum computation of modest size and then measure all the qubits and that when you do so。

 you are sampling from a probability distribution， which is too hard to sample from classically that can't be sampled from classically by any efficient means。

 so at least in that sense the quantum computer is doing something that we can't imitate in the classical world。

But perhaps most tellingly， we just don't know how to simulate a quantum computer efficiently using a classical computer when I say classical computer。

 I just mean an ordinary digital computer like the ones that are widely used now。

And it's not for lack of trying， physicists and chemists and so on have been trying for decades to come up with better methods for simulating complex quantum systems on classical computers。

 but even now after decades of trying the best algorithms that we have in the hard instances。

 the worst case instances， have a runtime which is exponential in the size of the system that you're simulating in its number of qubits。

Now。We have good evidence on the grounds of these three observations that there's a separation between what quantum computers can do and what classical computers can do。

 we don't have a rigorous proof of that and we also shouldn't think that the power of quantum computers is unlimited there are some things that even quantum computers won't be able to do and for reasons that we'll discuss later in the course。

We think that quantum computers cannot。Efficiently solve exactly the hard instances of optimization problems。

 so called NP problems， the one for which it's possible to verify the solution once it's found efficiently。

Quantum computers can't speed up everything。At least not super polynomially。

 but they cant speed up some things。And so I thought when I heard about this discovery of Peter Sho back in 1994。

 I thought it was very exciting because he was saying something very fundamental about。

Physics about nature， he was saying that there's a difference between easy and hard problems and that difference that distinction between what's easy and what's hard。

 what will be able to solve with advanced technologies and what will never be able to solve even with very advanced technologies。

 that distinction between easy and hard is different than it otherwise would be because our world is described by quantum physics。

 not by classical physics。That was one of the most interesting ideas I ever heard and thinking about it eventually led me to change the direction of my own research from elementary particle physics to quantum information and quantum computing。

Of course， it's a compelling question。To understand what are these problems。

 which are quantumly easy。And classically hard。And we've learned some things about that in the last couple of decades。

Chances are we still have a lot more to learn about that and that knowledge will fill in more rapidly once we can really run algorithms on large scale quantum computers。

But if you are a physicist， there's a natural place to look for problems that are。

Classically hard and potentially quantumly easy。And that's the problem of simulating quantum systems。

 simulating systems described by quantum mechanics。Which involve many particles。

 two great physicists， Bob Laughlin and David Pnes。Some years ago， 20 years ago。Point it out。

That we already have what could be called a theory of everything that matters in everyday life that underlies all of chemistry and biology and materials and geology and so on。

It's just the theory that describes the interaction of electrons with one another and with atomic nuclei interacting electromagnetally。

 and we know the equations， the Schrodinger equation that describes how such quantum systems change with time。

 we know those equations with high compete and with great precision。

 but we just can't solve them when the number of particles is very large in situations when the system of particles becomes very highly entangled。

 the situation in which we don't have any way of succinctly describing with classical information what the state of the system is and they said。

No computer existing or that will ever exist can break this barrier because it is a catastrophe of dimension。

Meaning that the state space of many quantum particles being exponential in the number of particles would always be unmanageable for future computers。

But in fact， another 20 years before Lawughlinn and Pines made this comment。

A kind of rebuttal to their statement had been enunciated by the physicist， Richard Feynman。

 Caltech's own， Richard Feynman， whose lectures on computation at Caltech were captured in this book。

 incidentally a new edition of this book is going to be coming out next year。

 and I've been asked to write an updated chapter about quantum computing and how it has advanced since Feynman's Day。

But it was already almost 40 years ago that Feynman made the statement nature isn't classical。

 if you want to make a simulation of nature， you'd better make it quantum mechanical。

 and it's a wonderful problem， it doesn't look so easy。

What Feynman was thinking was that if you want a simulator or computer that can describe how quantum systems behave。

 it shouldn't be an ordinary digital computer that doesn't speak the right language to describe how quantum systems change in time。

 we should build a computer that processes information according to the laws of quantum mechanics。

A quantum computer。For a physicist like Feynman or like me。

What we expect is that a quantum computer would be able to efficiently simulate any process that can occur in nature。

And we don't think that's true of ordinary classical computers like classical Tring machines。

 which don't seem to be capable of。Efficiently simulating very highly entangled systems of many particles。

So if we had a powerful quantum computer， we should be able to delve more deeply into the properties of complex molecules in chemistry or biochemistry。

 and also novel materials， new kinds of materials that we might find hard to imagine today because we can't simulate them。

 we might be able to discover using quantum computers。And for physicists with quantum computers。

 we'd be able to study fundamental physics in new ways， we'd be able to simulate， for example。

 high energy collisions of elementary particles like occur at the large Hadron collider and current high energy physics experiments。

 but which can't be simulated from first principles today。

 even though we think we know the right equations to describe how those particles behave they're just too hard to solve for the reasons that Loughlin and pines pointed out and we can even imagine using quantum computers to explore the quantum behavior of black holes or of the early universe right after the big bang。

 so for physicists that gets our heart's racing Now， in defense of what Loughlin and P said。

Although we can imagine extraordinary impact just from the ability with quantum computers to simulate chemistry and materials and a regime which has always been inaccessible up until now。

It's been 40 years since Feynman proposed the idea of a quantum computer and we're just now getting to the point where quantum computers are arguably sufficiently powerful to do interesting things。

So evidently building a quantum computer is really hard。

What is it that makes it so hard while it's because。

A quantum computer needs to combine in one platform a set of criteria which are nearly incompatible with one another。

Because we want the qubits， the fundamental information carriers in the quantum computer to interact strongly with one another because we want to be able to process the information that they encode efficiently。

But we don't want the qubits to interact with the outside world。

 that would cause what we call decocoherence， which causes a quantum computer to make errors and fail。

But we do want to be able to control the computer from the outside world to tell it what algorithm to run and ultimately to read out the result at the end of a computation。

And it's really hard to realize in the laboratory a platform that simultaneously satisfies all of these deerrata。

So it's only after decades of progress in fabrication andqubit design and control protocols and materials。

That we've gotten as far as we have。Now why is it so important to prevent our quantum computer from interacting？

With the outside world， it's because of this phenomenon of decocoherence。

And to give an idea what that means， let's imagine as physicists often do that we have a cat in a quantum state which is simultaneously dead and alive。

 I know it sounds a little bit ridiculous and the reason it does is we know very well that an ordinary experience we do not encounter that type of superposition of macrscopically distinguishable states and we understand why that's true。

 it's because with a real cat in such a state， it would almost immediately interact with its environment。

 and those interactions in effect measure the cat and project it onto a state which is completely dead or completely alive。

That's the idea of decocoherence。And it helps us to understand why。

 even though quantum physics holds sway in the microscopic world of atoms， nevertheless。

 classical physics provides a quite adequate， adequate description of what we encounter in ordinary life。

Now decoherence for quantum computer as for this poor cat is a real problem because even though the quantum computer isn't otherwise much like a cat。

 it's going to interact with its environment， those interactions will cause errors in the quantum computer。

 so we're not going to be able to run a large scale quantum computation。

In which we apply many operations to our quantum data。

 unless we can protect the quantum computer from decocoherence and other potential sources of error。

The real problem is that there's a fundamental difference between quantum and classical information。

 namely that you can't observe a quantum state without。

Changing it without damaging it in some uncontrolled way。

And although we might not look at the state of our quantum computer ourselves。

 the environment is continually looking if any information about the state of the quantum computer leaks to the outside。

 that causes decoherence and our quantum computer is going to crash。

So somehow we have to keep the information that's being processed almost completely isolated from the outside world during the computation。

And that sounds extremely hard because our hardware is never going to be perfect。

 so how could we possibly accomplish that？And we think we know the answer that this problem of errors and quantum computation can be overcome。

Through the concept of quantum error correction， it is， of course。

 a cousin of error correction as it is practice in the classical world， but with some new features。

The essence of the idea is that if we want to protect a complex quantum system。

 we should encode it in a very non local form shared among many parts among many qubits。

So the environment which typically interacts locally with the quantum computer might look at the parts one at a time。

 but by doing so it won't be able to gain any information about that non-locally encoded state it's just like that 10 page book I described earlier when you look at the pages one at a time。

 you can't read the content of the book， that prevents the information from leaking to the outside world so we can protect a quantum state and a quantum memory and we've also understood how to efficiently process quantum information which is encoded in that very non-local form and that will be discussed in detail in the winter term of this course。

Now， in order to make highly entangled systems。Wwhichhich are what we're interested in in quantum computing。

 you don't use ordinary bits， you use what we callqubits， the quantum analog of bits。

And the qubit always has some physical realization。

 There are many possible realizations forqubit just as there are for a bit。

 there are many ways of encoding a。System in the classical world that can be in either one of two states。

And same thing quantum mechanically， there are a lot of ways of encoding a qubit。

It can be encoded in。Fundamental particles， single quantum systems like a single atom。

 which could be either in its ground state or in some longli excited state。

 it could be encoded in the spin of a single electron where the spin along some axis can point either up or down。

 it could be encoded in a single photon for example。

 in its polarization state whether it's electric field is oscillating vertically or horizontally and it can also be encoded in。

More complex systems like electrical circuits， which run at very low temperature in order to suppress。

Decoherence and these are all quite remarkable incodings it's remarkable that we've learned after decades of effort to manipulate these single quantum systems like a single atom or a single electron。

😊，Accurately that we really can control such systems and it's also remarkable that this more complex system。

 superconducting circuit， although it might involve the collective motion of billions of electrons。

 we can control it as though it were a single atom so it's really important that we continue to develop these different hardware approaches to building quantum computers because we don't really know at this stage which hardware approach is going to have the best prospects for scaling up to large devices。

 and it could also be something quite different for many of those portrayed on this slide， in fact。

 there's a particularly beautiful idea which was proposed by Caltech professor Alexi Kaya who will be teaching the next term of this course。

 the idea of topological quantum computing， which means that there's a way if you can build the right kind of materials to encode quantum information。

In a physical system which has a kind of intrinsic resistance to decocoherence。

 a kind of intrinsic protection against errors， and there's been some effort put into realizing those kinds of materials。

 it's been slow going because it's a very challenging problem。

 but in the long run that might be the best way to scale up quantum computing at this stage we really don't know for sure。

So let me say a little bit about the current state of the technology。

 arguably we've reached a recent milestone， what has been called quantum computational supremacy。

This was announced with some fanfare。A little less than a year ago by Google's quantum computing group。

This idea of quantum supremacy is that we think we know。

That classical systems cannot in general simulate quantum systems efficiently。

 I think that's one of the most interesting things that's ever been said about the difference between classical physics and quantum physics。

 so we have a very strong incentive to try to validate that by doing。

Laboratory experiments by showing that it's true in the lab and in the case of the Google group。

 they constructed a device。Whi has 53 working qubits laid out in a two dimensional array such that for neighboring qubits in that array。

 it's possible to do an entangling operation， what we call a two qubit quantum gate acting on that pair of qubits。

And they considered executing circuits。Which consisted of up to 20 layers of such two cubbit gates。

 these circuits were chosen to have a kind of。Random structure and of course they were not executed perfectly because the hardware that they were using is imperfect and noisy。

 so that in fact whenever they would run such a computation。

 they would get the right result with about a probability of one in 500， so roughly speaking。

 if they ran the computation 500 times 499 times they would just get random junk out when they measured the qubits at the end。

 but once in 500 times they would get a valid answer。

But then they could run that computation millions of times in just a few minutes and thereby extract some statistically useful results from the computation so they did that with their quantum computer。

 you could ask could a classic computer simulate what that Google device what they call sycamore is doing and of course in principle it can the question is how hard is it。

 and this is hard to pin down precisely， but as best we understand running the best algorithms on the most powerful。

Supercomputers that currently exist， it would take at least days and perhaps longer to simulate what Sycamore does in the lab in just a few minutes。

I called it quantum David versus classical Goliath because the competing classical supercomputer covers about two basketball courts and it's using tens of megawatts of power。

Well while the Sycamore device itself is just a little chip inside a dilution refrigerator。

 a kind of tabletop scale experiment。Now， furthermore。

 although they did this experiment with 53 qubits， the hardness of doing that simulation classically grows exponentially with the number of qubits。

 so if they repeated the experiment， as I'm sure they eventually will with 60 qubits or 70。

 it rapidly becomes far out of reach for any classical simulation。And they had ways。

 which I won't really explain of validating that their device was really getting。Baalid answers。

So this is interesting， this is a programmable quantum computer that they built and operated。

 and it seems to have entered the regime where it can perform tasks which surpass what the world's most powerful classical supercomputers can do。

That's an impressive achievement experimentally it's a kind of testament to the progress that we're making in building hardware for quantum computing you could say that the extravagant exponential resources of the quantum world are validated in this experiment that's not something that comes as much of a surprise to most scientists but it's still a technology。

Milestone to recognize on our planet。We know building quantum computers is really hard。

 but it's not so ridiculously hard that we can't continue to make progress on the hardware and continue to try to scale it up。

Now it happens though， that the particular task that this sycamore device performed to surpass what a classical computer can do is not of any intrinsic value other than for the purpose of。

Demonstrating quantum computational supremacy， they were just running essentially random quantum circuits。

 which because they have no structure that can be easily exploited in a classical simulation。

 are particularly hard to simulate with classical devices。It's kind of nice to have a name。

 a word for this era of quantum computing， which is now starting to dawn， so I made up a word NC。

It means noisy， intermediate scale， quantum， intermediate scale to indicate that we're now talking about quantum devices of sufficient scale that we can't by brute force。

 simulate what the quantum computer is doing even with our most powerful classical hardware。

But noisy to emphasize that these devices are not error corrected and the noise puts a limitation on their computational power。

 we can't do a circuit with any number of layers of gates that we want a circuit of arbitrary depth because we would just get out random junk at the end because of the noise so we can only do quantum computations with this type of device of limited size Now this NIS technology is。

Exciting if you're a physicist。It means that we should be able to study the physics of many interacting particles。

In a regime which has never been experimentally accessible before。

 and we can hope to make new discoveries as a result。

Now it might also have practical applications of interest in the commercial world。

But we're not sure about that and we shouldn't think of NC in the next few years as something that's apt to change the world all by itself。

 I think it's better to regard it as a notable step。

Towards the more advanced quantum technologies that we're hoping to develop in the future。

 I do feel confident that we will see transformative impact of quantum computing。

On society eventually， but that impact could still be a ways off and we're not really sure how long it's going to take to get there。

嗯。There is a kind of emerging paradigm for how。Near term noisy quantum computers might be used to solve interesting problems。

 it's a kind of hybrid quantum classical approach， it makes sense for the time being to use our powerful classical computers to the extent that we can and then to try to boost their power using a kind of quantum coprocessor。

And that might work this way。 We could have a modest size quantum computer。

 which does a quantum computation of。Modest depth and then all the qubits are measured and then the outcomes of those measure measurements are fed to a classical computer which returns instructions to slightly modify the quantum computation。

 and then that cycle is iterated until convergence where the goal is to find some approximate solution to an optimization problem。

Um byum。By this method to find a minimum of some cost function。Now， as I said。

 we don't expect quantum computers to be able to find exact solutions to the hardest instances of NP they find better approximate solutions or find those approximate solutions faster。

 at least that's the hope。So should we expect that this NIS technology will be able to outperform our best classical algorithms？

Running on the best hardware， solving the same problems。

 problems of practical practical interest in optimization， well we don't really know。

 we'll have to try it and see how well it works， but it's really a lot to ask because the classical methods have been well honed over decades of development and these NISC processors are just becoming available for the first time now。

Now， we don't necessarily have to be so discouraged about the prospects for near term quantum technology。

 just because the theorists aren't able to give us convincing arguments that NC devices will be able to achieve speedups compared to our best classical computers。

There are lots of examples in the history of classical computing。

 where algorithms turned out to be valuable and to have extensive impact。

 even though theorists weren't able to validate。Their power in advance。

 we just had to experiment and find out how well they worked。

A good example of that now is deep learning， It's having a big， big impact on the world。

 and yet we still have a quite limited understanding of why， for many cases of interest。

Deep learning networks can be efficiently trained。As so quantum computing might be something like that。

 we're going to be in an age of quantum heuristic algorithms for a while。

 there are things people want to try like these approximate optimization methods and we'll see how well they work we'll experiment as we experiment will learn more and maybe we will find useful applications。

But it's certainly not guaranteed because we'll be limited to relatively small devices with a order 100 qubits and with a number of computational steps。

 probably less than 100 for a while and so we'll need an extensive and vibrant discussion between the application users and the quantum algorithm and hardware designers to find such applications we might have to get lucky。

Now as I've emphasized， these NIS gear devices are limited because they won't be protected by quantum error correction。

 and we think we understand that in the long term， because of the limitations on quantum hardware arising most fundamentally from decocoherence。

Quantum air correction is going to be needed to scale up to large devices that can solve really hard problems。

In principle that works and formally the overhead cost of doing quantum error correction scales in a reasonable way under natural assumptions about the structure of the noise。

 one can prove that， but nevertheless the overhead cost is substantial now how high the cost and additional qubits and additional gates depends on the problem that we're trying to solve the complexity of the algorithm we're running。

In the hardware that we're using。But as an example。

 a recent estimate is suppose we want to use a quantum computer to break。

Widely use cryptoytems based on the difficulty of factoring。

That's possible on a superconducting quantum computer that runs for less than a day if the error rate per gate is about one in a thousand。

 which is。Somewhat better than has been demonstrated in the Google device so far。

But to run that algorithm， although we only need a few thousand protected logical qubits protected by quantum error correction。

 in order to have sufficient redundancy to protect against the errors。

 we need about 20 million physical qubits。So to reach that scale。

 we have to cross a rather daunting quantum chasm。From where we're expecting to be in the next few years。

 dealing with hundreds of qubits， we need to scale it up to millions of physical qubits。

 And that's probably going to take a while。 So it's important in the meantime that we continue to advance。

The gate fidelities if we can make quantum gates more accurate these entanling two qubit quantum gates in particular。

 then we'll be able to extend NC methods to larger circuits and solve harder problems and that will also lower the overhead costs of eventually doing quantum error correction so we really have to keep our eye on bringing us closer to the day of scalable quantum computing based on quantum error correction。

And。That's going to involve improving the qubit technologies。

 the technologies that I mentioned earlier and other potential technologies is really challenging to get the error rates of entangling。

Two cupid gates， for example， down to the levels that we'd like to see。

 I imagine that's going to happen eventually in the long run i'm sure。

Cubbits and quantum gates will be much more accurate than they are now。

 but it's not clear and it's going to take a lot of effort to make big improvements there。

The thing to keep in mind is that quantum computing is really a long-term project。

 we're at a kind of an exciting stage now and there's been a surge of interest and investment。

 a lot of technology companies are building their quantum efforts。

 a lot of startup companies are getting into the game。

 a lot of venture capitalists are involved in theyre great expectations for the field。

 and that concerns me somewhat because although I am greatly enthusiastic about the future quantum computing。

 I don't want people to have unrealistic expectations about the time scale for a really big impact on society。

 I don't expect that something that's going to happen in five or ten0 years it'll probably take longer but well within your lifetimes。

So let me sum up what I've said so far about where the field stands。Arguably。

 we've entered the NS eraa through demonstrations of quantum computational supremacy。

We now have quantum platforms that potentially we can use to do things that we couldn't do with ordinary classical digital computers。

Now for now we're not going to be able to use error correction on these devices。

 which would be too costly in terms of overhead， so we are in the era of heuristic quantum algorithms。

 we're going to try a lot of things， we might in the near term find a quantum advantage for commercially useful applications but that's not guaranteed at this stage。

And to make quantum computing truly scalable， we're expecting that quantum error correction will be needed。

 but because it has such a high overhead cost， it's not likely to be feasible in the near term。

 it's important to continue to lower gate error rates so that we can extend the power of this NC technology and help to pave the way for。

Quantum air correction down the road with a reasonable overhead cost。

 and we just shouldn't think of NC， although it is exciting and from a physics perspective an opportunity for new discoveries。

 it's probably not going to change the world by itself right away。

 the goal in the near term should be to pave the way for bigger payoffs using future devices。

And we really have to keep our eye on making progress towards scalable fault tolerant quantum computing。

So I'm telling you all this just to give you some perspective。

 we're not going to be talking about quantum error correction in the fall term。

 we're going to be talking about ideal quantum devices and trying to understand some of the things that they can do and we're not going to talk about the physical realization of qubits either that's a very interesting subject。

 how these different hardware approaches actually work and what are the prospects for improving them。

 but that's not within the scope of this class。So at this point， I think I would like to。



![](img/059369b790d4dfaee85e985249cdae77_3.png)

Give you a little break and give myself a little break。

 So I'm going to pause the recording for a minute， but then I want to come back with some further discussion。

Fillling in a little bit more technical background for what I've discussed so far in this overview。

Okay。So now for the rest of this lecture。

![](img/059369b790d4dfaee85e985249cdae77_5.png)

I want to circle back to some of the concepts that we've already discussed。

 providing a little bit more mathematical context。To help you think about these things。Now first。

 let me say something about the difference between quantum information and classical information。

When we speak of information， we really mean from the point of view of physics。

 something that we can encode and store and process。In some physical system。

 using some physical interactions。And fundamentally。

 since we think physics is really quantum mechanical。

 quantum information should be thought of is something we store in a quantum state and process in a quantum state now。

For practical purposes， we often。Get away with ignoring。

With ignoring the nuances of quantumness in this encoded information， we can describe it classically。

 it's really because of decocoherence。That we can get away with that。

But it's important to understand that quantum information has features。

Which are not shared by classical information， and here I want to mention a few of those。

The first one is intrinsic randomness。As an example， if I thought about a。Radioactive nucleus。

 which was about to undergo alpha decay。We can't predict with certainty whether that nucleus is going to decay in the next second。

 we can only assign some probability。Stating it's the likelihood of decaying in the next second。

And that's intrinsically random in the sense that。Our inability to say yes or no。

 whether it's going to decay applies even if we have the most complete description of that nucleus that the laws of physics will allow。

 even if we know everything about it。When I speak of intrinsic randomness。

 I'm trying to distinguish between the randomness that we usually encounter。

 which arises from ignorance。Like if I flip a coin and I know I came up either heads or tails。

 but I don't know which until I look at it so I assign probabilities to those outcomes reflecting my ignorance is because I don't know the complete description this intrinsic quantum randomness is different it applies even when we have the most complete possible description。

Another important feature。What we sometimes call uncertainty is that the observables in quantum theory。

 the things that we can measure。Don't necessarily commute and that means different observations can interfere with one another intrinsically。

 so for example， if there are two operators A and B that don't commute and I imagine measuring either A or B if I measure A in some state that will influence a later measurement of B。

 not because I was sloppy but for fundamental reasons。

And the third important feature of quantum information。

 which I've already mentioned a couple of times is entanglement。

 that's this principle that even when you know everything about the whole system。

 you don't necessarily know everything about its parts so。In the case of a two part system。

 that two part system could be in what we call a pure state。

 that means we have all the information that completely characterizes that state as far as the laws of physics will allow。

 but if we look at just part A by itself， if we measure something in part A。

 we are powerless to predict with certainty the outcome。

 even though we know everything about the whole， we are largely ignorant about the parts。

So let's talk a little bit more about the idea of a qubit I mentioned that it can be realized physically in a number of different ways。

 of course that's true of classical bits as well， anything that can be in two possible states which we could label zero and one could in principle serve as a bit。

It's useful to think about bits abstractly without worrying about exactly how they realize physically and that's true for qubits as well in fact that's。

Almost exclusively how we'll be thinking about qubits in this class。

 we won't worry about whether they're carried by atoms or electrons or photons or something else。

And the mathematical description of a qubit is this。

 just as a bit is the fundamental indivisible unit of ordinary classical information。

The qubit is that indivisible unit of quantum information， a bit is a two level system。

 it can be either zero or one， and a qubit can be described as a vector in a complex Hilbert space with two mutually orthogonal basis states。

 which we can label zero and1。So on the face of it。

 it might seem like we need two complex numbers to characterize the state of a qubit。

 the coefficients of the state zero and the state one。

 but in fact there are only two real parameters that come in to completely characterize a qubit。

 that's because we don't really care about the overall normalization of this vector and by convention we typically set it equal to one and wed also don't care about its overall phase so if we multiply it by a complex number of modulus1 that doesn't change anything physically。

 so we really have only two real parameters we characterize a qubit。

Now a bit is the special case of a qubit where we know the state to be either zero or one。

 we can imagine playing a game， let's say Alice is to prepare the state of a qubit and she sends it to Bob and then Bob is to make some measurement on that qubit and he's supposed to determine what state of the qubit Alice prepared and sent。

If it's agreed in advance that Alice is going to send either a zero or a one。

 then Bob can play the game。So that he wins 100% of the time these orthogonal basis states can be perfectly distinguished by Bob he can do a measurement which will tell him with certainty whether the state was a zero or a one。

 but we can also consider more。General states of the qubit and that's where things get more interesting because when two states of a qubit are not mutually orthogonal。

 we can't distinguish them perfectly by any means so if we play the game in a more general setting where Alice can prepare any state of the qubit。

 maybe one of two possible states that are not mutually orthogonal。

 Bob won't be able to win that game with a 100% success probability。To be a little bit more concrete。

I can consider any basis I want for the two orthogonal states of the qubit here to simplify things a little bit。

 I'm representing the states of a qubit in spanned by0 and1 as though the coefficients were actually real so I can draw it as twodimensional real vector space0 and1 orgonal vectors。

 but we can also consider the uniform superposition of0 and1 with a plus or a minus sign I'll call those states plus or minus and they're rotated 45 degrees in the plane away from the basis states0 and1 and plus and minus can be perfectly distinguish from one another and one in0 can be perfectly distinguished from one another。

 but one for example which is not orthogonal to plus cannot be perfectly distinguished from plus。

The game so that Alice is known to have a choice between preparing either a one or a plus and sends it to Bob and Bob is supposed to guess whether the state that Alice prepared and sent is a plus or a one there isn't any way for Bob to win that game with 100% success probability In fact it's interesting to think about what's the best thing for Bob to do in that case。

 remember he can distinguish states which are orthogonal to one another and his best possible strategy in this case is to do a measurement that distinguishes the two vectors that I showed in black which are symmetrically distributed so that the one pointing up and a little bit to the left has a larger overlap with one and the other is more closely aligned with。

PlusAnd based on the outcome of that measurement， he can guess either one or plus and so his basis estates are rotated away from one and plus by an angle of pi over8。

 so it turns out he can win the game with a probability which is the cosine squared to pi over8 a little better than 85% and there's no other strategy that would do better than that。

There's another way that Bob might try to play， he could make a measurement that has three outcomes。

And you might want to think about how this could be done。

Where one of the outcomes is inconclusive and Bob just has to make a random guess。

 but the other two outcomes tell him that the state is definitely a one or definitely a plus。I mean。

 as an example， something that abot could do is he could measure in the10 basis to try to distinguish one from plus。

And in that case， if he gets the outcome zero， he knows that the state couldn't possibly have been a one。

 so it must have been a plus， but in the case where he gets a one he he doesn't really know。

 so that's not an optimal strategy either， but the important conceptual point is that non orthogonal states cannot be perfectly distinguished from one another in quantum mechanics。

Now we can imagine a more general version of the game， or let's consider an alternative scenario。

Alice has a qubit， and maybe we know that she prepared that qubit to be either one of two possible states in this two dimensional。

Fctor space， I've called them phi or psi。And then Alice has a chore to do。

 she has to go to the store or something and she says to Eve who stays home， Eve。

 I don't want you to look at my qubits while I'm gone。

 I don't want you to do anything to find out whether my qubit is a P or a sigh okay and then Alice comes back from the store and now she's wondering whether Eve really obeyed that instruction。

 those instructions or contrary to Alice's preference。

Triryed to collect some information and if he does do that， does Alice have a way of finding out？

Well let's think about what Eve would do if she wanted to get information about Alice's state without disturbing Alice state at all。

 so Eve would perform some kind of unitary transformation because that's one does to a quantum state in quantum physics and then she would make some measurement of some extra register。

 she doesn't want to measure Alice's qubit which would disturb it for sure。

 but her unitary tries to imprint on a register which is labeled E information about Alice's state in a register which is labeled A so。

the way we want that unitary to work is that。The register E will wind up in a state E when。

Alicea state is P phi， and it will wind up in a state F when Alice state is psi。

 and then Eve can measure and try to get some information about Alice state by measuring the register E。

 but let's suppose the states P phi and Psi are not orthogonal to one another。

We know that a unitary transformation has the property that it preserves inner products。

 it won't change the inner product between two states when that unitary is applied to both of those states。

And so we know that the inner product of the initial states before the unit areas is applied and because EVavs register started out in some standard state。

 which I called zero。That inner product is just the inner product of Psi with phi。

 that has to be the same as the inner product of the states on the right with one another。

 and that factorizes into the inner product of Phi with Psi times the inner product of the register states F with E。

And if the states psi and phi are not orthogonal， then their inner product is non-zero。

 so we can divide by that number and conclude that the inner product of F and E is one。

 and that means since these are normalized states that f and E are actually exactly the same。

 So there isn't any information to distinguish phi from psi encoded in that E register if phi and P psi are not orthogonal to one another。

 the situation is different if phi and psi are orthogonal to one another。

 and then we don't draw any a conclusion from this argument because we just have0 is equal to0 and in fact。

 when they are orthogonal， that's just like the classical world where we're guaranteed that aqubit is either a0 or1。

 and then， of course we can find out whether it's a0 or1 without causing any disturbance that Alice would have any hope of detecting。

we can make copies of that bit anytime that we want to any number of copies。

 so this idea that you can't collect information that distinguishes nonorthgonal states from one another if you don't disturb those states。

 that's the foundation of quantum cryptography， that's the basis for quantum encryption namely that if we use signal states that are not orthogonal and an eavesdroroppper tries to learn something about those signal states that will cause some disturbance which can be detected and we can design our protocol so that we won't wind up using compromised information in our protocol to make it secure。

Not because as is usually the case in the public key schemes we use nowadays。

 because breaking the encryption scheme is possible in principle。

 but just too hard to do because it requires too hard a computation。

 rather the security would really be founded on fundamental laws of physics。

 the principle that we can't distinguish non- orthothgonal states without disturbing them。Now。

 to understand quantum computing， we're going to have to understand how in quantum mechanics we describe composite systems when we put two quantum systems together。

 how should we mathematically describe that？So here I have two individual quantum systems A and B。

And I'd like to mathematically describe the composite system， A B。So let's look at system A。

 let's say it has a dimension， which I call Dab Bay。

 that means its Hilbert space is spanned by a set of orthoormal basis states of which they're altogether DA。

And in the case of system B， it has dimension DB， its Hilbert space is spanned by DB mutually orthogonal basis states。

 and now we want our rules for building composite systems to remain compatible with the notion that if states are orthogonal。

 then they can be perfectly distinguished and that tells us how we should define our inner product on these composite systems。

 namely if I put together a basis state from system A and a basis state from system B。

If I consider cases in which the system A basis states are mutually orthogonal。

 then it's possible to perfectly distinguish the composite states。

 in fact I can perfectly distinguish them just by looking at system A and likewise if I consider basis states for the composite system which are mutually orthogonal on system B。

 then those can certainly be distinguish in fact， just by looking at system B so we want our rule for evaluating an inner product of systems A and B where I combine together basis states J and B with basis states I and a。

 we want those to be mutually orthogonal if either I does not equal J or a does not equal B so for example in the case of two qubits。

 we can choose our mutually orthogonal basis states2 B00，01，1011。

Just the way we would label the four possible states of two bits。

And these can be perfectly distinguished， so in the Hilbert space of the composite system。

 they should be regarded as mutually orthogonal states。And of course， we can generalize this idea。

To many qubits so let's suppose I have altogether n qubits and now we can choose mutually orthogonal basis states for the nqubits which are just labeled by bit strings so they're all together two to the n possible strings of n bits and if I choose two of those which are distinct then that means for at least one of the n systems one of them is a one and the other is zero so just by observing that some system。

 I can distinguish the states and so those are all mutually orthogonal states in the Hilbert space of n qubits and they're all together two to the n of them and the possible quantum states which are pure states for which we have the most complete possible description are described by vectors in that two to the n dimensional space with complex。

Coics modo we don't care about the I couldn't hear what you said modo we don't care about the overall normalization and we don't care about the overall phase so that's the basis of the statement that I made earlier that even if we have just say 300 qubits to give a complete description of a typical state for 300 qubits we would need to describe this vector in a space which is dimension2 to 300 and that is something that we couldn't possibly record in the visible universe even if we made use of every atom at our disposal。

So the important。Fundamental principle is that we don't know of any succinct way of describing a typical quantum state of Nqubits now。

If I have n bits and I pick one of the possible strings of n bits and I don't tell you what it is and you wanted to make a list of all the possible strings that I might have chosen。

 of course that would be an unmanageably long list。

 you would have to write down all of the two to the n possible bit strings。

 this a different situation though because in that classical case for any one of those two to the n possibilities。

 I can completely describe it to you just by handing you a single piece of paper with those n bits written down in the quantum case。

 it's different because even when we have the complete description of the quantum system。

 there is no possible succinct description。Now， when we speak of building our quantum state out of qubits。

You could ask， well how should I take this Hilbert space of vast dimension of exponentially large dimension and decompose it into qubits or other lower dimensional systems and of course from a mathematical point of view that's completely arbitrary but from a physical point of view there are preferred ways of doing that decomposition typically the way we decompose of large quantum system into small ones is dictated by spatial locality。

 that is we consider the different qubits to be at different locations so。

It might be that they're in different cities。One is in Pasadena， the other is in New York。

 and so if we want to describe that four dimensional system consisting of two qubits。

 it's very natural to decompose it in terms of the qubits that are at distinct locations。

The two cities， Pasadena and New York， if I have n qubits encoded in atoms and the atoms are spatially separated from one another。

 my preferred decomposition into qubits would be dictated by locality。

 so I would describe the qubits to be the individual atoms。

And the reason it makes sense to use that notion of locality is because interactions and physics are typically。

Physically local， we expect only systems that are in close proximity to one another to be able to interact and so physics gives us a natural way of decomposing into subsystems。

Now， if we have。Cubbits in and different cities， it's quite easy to prepare a so-called product state in which in each one of the cities we prepare the qubit in one of the possible single qubit states。

 each one of those single qubit states as we've seen is only described by two real parameters。

 so all these product states that we can create locally in the cities individually can be described succinctly with a number of parameters which just scales linearly with the number of qubits。

But the states that are not product states are the so called entangled states。

 those are the ones that can't be created。Locally that can't be created just by preparing a state of the qubit in each one of the cities entanglement can only be created through some kind of quantum communication or through interaction among the qubits so if we have N laboratories and in cities and the agents in those laboratories are talking to one another on a telephone if they don't have entanglement to begin with they can't create entanglement the only way to entangle qubits which are in different cities is either to let those qubits come together and interact or to prepare an entangled state and send one of the members of that entangled state to another city technological limitations make it hard at least these days to send a qubit without it being damage due to decocoherence all the way from Pasadena to。

But eventually maybe we'll be able to do that and distribute entangled states among nodes distributed around the globe。

It turns out， in fact， that if I want to make a entangled state of Nqubits。In principle。

 I can create any such state if the qubits interact with one another two at a time。

 so if I have my Nqubits and then different cities。And in a sequence of operations。

 thosequbits are able to come together in pairs and interact in some way。

Then with a sufficient number of such interactions。

 I can make any possible state in this two to the n dimensional Hilbert space for the Nqubits。

The catch is that we can't in general do that efficiently。In fact。

 the space of possible states for Nqubits is really huge， it has a dimension which is exponential。

 it's two to the undimensional， it has a volume which is exponential in its dimension and it' Hilbert space dimension so that's doubly exponential in the number of qubits and if I put together these elementary quantum gates acting on pairs of qubits with altogether。

 let's say t gates， roughly speaking the number of such circuits of two qubic gates is exponential in T so I would need t to be exponential in the number of qubits to be able to reach any state in the Hilbert space I want。

 well'll talk about that in more detail later on。So to sum up this lecture or to conclude it。

 I'd like to describe putting together some of the things we've just discussed our mathematical model of a quantum computer。

So to begin with we have to say what the arena is in which a quantum computation takes place and that's the arena of Hilbert space。

 and it's important that we have not just a very large state space for our quantum states。

 but we also have a natural notion of a decomposition of that big Hilbert space as a tensor product of subsystems in terms of qubits for example。

And as I've emphasized。There's a natural way of choosing such a decomposition based on spatial locality now the reason it's so important to have such a notion is that I'd like to be able to talk about the complexity of computation and the complexity of states and when I speak about the complexity of a state for example。

 I'm talking about how many operations I need to create that state。

So that depends on what your starting point is， so the natural starting point the type of initial state will consider in a computation will be just a product state。

 which we can by convention， say each one of the qubits starts out in the state zero。

And when we speak of a product state， of course I need some preferred decomposition into qubits to say what I mean by a product state。

 and I want to regard those initial states as something that's easy to prepare I don't want to have complexity hidden in the state preparation itself。

 and then I have an notion of complexity which is how many operations how many quantum gates I need to reach a particular state or perform a particular computation without a decomposition decomposition into qubits I wouldn't have a basis for speaking of complexity。

So now to do the processing， I have to have some alphabet of elementary operations of finite set of quantum gates。

Where each one of those gates is just some unitary transformation。

 which I can imagine doing in a laboratory， which acts on some constant number of qubits。

 for example， axon。Two qubits at once since we've already seen or I've already mentioned。

 that's already universal， that's enough for us to build up any quantum state we want or to realize any unitary transformation acting on the states。

So。There's a notion like there is in classical computation of universal quantum gates and typical two dimensional or sorry not two dimensional to qubit transformations do provide us with such a universal set and then we can describe computations in terms of circuits of those unitaries。

 let's say acting on two qubits it wants now the way we choose those fundamental universal gates is highly arbitrary。

You might prefer a different set of universal gates than I do maybe because we have different hardware。

 maybe because I'm doing my computation on atoms and you're doing yours on electron spins。

 there are some operations that are easy for you。In your lab， there are others which are easy for me。

So although we have different universal gate sets， nevertheless。

 we can agree on what computations are easy and which ones are hard。

Because it turns out that I can efficiently simulate your universal gates using mine with just some modest overhead。

 you can likewise using your gates。Simulate mine。And therefore。

 the problems that are hard or easy are the same for you as they are for me。Now。

 we also don't want to hide complexity in the design of the circuit itself， so we can imagine。Thank。

That when we say the problem。And an input to the problem。That there's a classical computer involved。

And that classical computer designs the quantum circuit。

 designs the sequence of gates that we're going to apply to the initial state。

We don't want to hide complexity in the design of the circuit itself， that's the point。

 so we want that classical computation to be efficient in an efficient quantum computation。

 we could use some classical model of computation like the Tring machine model。

And imagine that the Tring machine。Prints out the quantum circuit that is to be executed and that can be done efficiently。

 the circuit can be described efficiently even though the way the circuit acts on the state can't be described efficiently。

And then in the end， we're going to want to read out a result of a computation。

And we don't want to hide complexity in that final readout。

 so we want to make it something very simple like we measure each one of the qubits in a standard basis and we get an outcome for each qubit。

 which is either zero or one。And that's a complete model。

 a mathematical model of what we mean by a quantum computation。

 and what we're going to be interested in is what can this model do。

 what kind of computations can it run， what algorithms can we design in particular that will allow us to get quantum speed ups over the best classical algorithms that we know of。

For solving the same problems。Now it should be emphasized that everything in this model is something that can in principle be simulated by a classical computer while strictly speaking we would want that classical computer to have a random number generator because the final readout the quantum measurement is a nondeterministic process but at any rate if we have a classical computer and a random number generator。

 it can simulate everything that the quantum computer does because really all it's doing is it's taking vectors and it's applying matrices to those vectors to get some final vector and then it's projecting that vector onto some set of axes。

 those are all things that classical computers can understand so there isn't any issue of the notion of computability being different for quantum computers than for classical ones but is computable by a quantum computer is also computable by classical one。

between the models has all to do with efficiency because for the classical computer to simulate the quantum computer。

 it has to deal with vectors of size exponential in the number of qubits of matrices that are size exponential in the number of qubits。

 and we just don't know anyway of doing that classical simulation without resources that scale exponentially with the number of qubits。

Now， from the point of view of physics or even fundamental computer science， which has its。

Rudsson physics， at least from my point of view。It's natural to wonder whether this model is a good one。

 a good model for describing all the information processing that can really be done in the natural physical world。

 and we don't know for sure whether that's the case or not， it's a hypothesis。

 what we might call the strong quantum church Turing hypothesis。

 that this quantum circuit model really captures all computations that can be done efficiently in real physical systems。

嗯。From the point of view of fundamental physics。It's not entirely obvious that this is the case。

When we describe elementary particle physics， we usually use something called local quantum field theory。

And， formerly。Quantum field theory involves a number of degrees of freedom per unit spatial volume。

 which is infinite。And so we can't exactly simulate that infinite number of degrees of freedom in a finite spatial volume。

 so it's an article of faith among physicists。That in fact。

 we never really need all of those degrees of freedom that a good approximation can be obtained by retaining only a finite number of degrees of freedom per unit volume and the number that we need is controlled by other input parameters like the total energy involved if we have a limited amount of energy that puts a limited on how deeply or on how fine a scale we can probe physics at very short distance scales and so we only need a limited number of degrees of freedom to describe things accurately and it's even more challenging if we try to understand the kind of information processing that's done by black holes or the things that are going on inside black holes inside by this quantum circuit model we don't really know for sure it may be it might not be it would be exciting either way if the quantum circuit model really does capture everything that happens in physics than that means that we'll be able to use。

Computers to explore fundamental physics very deeply， if it's not the case。

 that's even more exciting， it means that nature。Is able to realize an even more powerful computing model than the one we'll be studying in this course。

So let me just sum up the three main lessons from this， our first lecture。

We think quantum computers can solve hard problems。

 problems that are too hard to solve with ordinary digital computers that's driving great interest in the subject。

Now there's a great challenge for quantum computers。

 which is that they're noisy for reasons that would seem rather fundamental because decoherence can't be completely suppressed。

But we think we've understood theoretically how to overcome the difficulties due to noise and quantum devices to make them truly scalable。

 though that hasn't been achieved yet。Quantum hardware really exists。

 it's making progress and it can continue to make progress and no doubt will so that the theoretical ideas which we'll be discussing in this course correspond to things that we really can and eventually we' be able to do much better in the lab。

Now there are lots of questions about this subject。

 some of which we'll be addressing what really are the problems that quantum computers can speed up and when we know about what problems can be sped up or at least can be dramatically sped up using quantum computing technology。

Can we build a quantum internet， can we send quantum states around the world， and if so。

 how would we use that type of technology in applications to cryptography for example？

Can we construct much more accurate quantum hardware。

 much more reliable hardware than we have now and what physically is the best way to attain that kind of much better hardware performance。

 and what can these concepts of quantum information concepts like computational quantum complexity and so on。

 tell us about nature？Well， I've just tried to give you a little taste of why this subject is interesting。

 I hope it what your appetite and in the next lecture well it'll have a much different style than this one we'll be talking in somewhat more concrete and technical terms about the mathematics of quantum states and quantum information so until then。

Be well and see you soon。

![](img/059369b790d4dfaee85e985249cdae77_7.png)