# 密歇根大学《互联网历史、技术和安全Internet History, Technology, and Security》中英字幕 - P11：10_超级计算机中的历史印记.zh_en - GPT中英字幕课程资源 - BV1DE421c7CT

Hello and welcome back。I just wanted to give you sort of a sense of the actual physical experience of connecting and communicating and computing in the 60s and the 70s。

 the 70s was when I got my start and the lucky people got to use teletype like was being used in that video and other people used punch cards you also heard the squealing sound of the data being converted into sound and back and forth you knows the key goal was there would be if you were lucky one computer within a 20 mile radius of where you were sitting so you could use a local phone call and you could be on all day and do things all day long and that was really exciting and a lot of fun and this was sort of a common if you were sort of。

knowToday you have a $2，000 laptop， the fancy people had these teletypes right in their office because then they could conveniently sort of do computation and not have to go somewhere to do that computation。

 so that's pretty exciting and so dial up was kind of like the way the campus operated。

 but you could also do data transfer with lease lines。

And the typical thing about lease lines is that they the phone company。

 if it's going between two cities， digs a hole and puts a cable in and has some number of copper wires in between those cities。

 this is back then， of course it's fiber optic now but back then it was copper。

 and every time you would make a call between those two cities it would have to find a free piece of wire and connect up so that your call。

 the audio of your call would go through that wire。And。😊，If you wanted to。

 you could pay them to lease one of those pieces of wire。

It meant that people couldn't use that wire for phone calls。

 so you would sort of take it out of service and if they had 500 wires between two cities and you lease one of them。

 then they had 499 wires and so it was rather expensive。Really， very importantly。

 the cost was based on distance， right？A mile versus five miles versus 20 miles versus 100 miles。

 the cost would kind of go up linear based on distance and so that's a key thing that distance is important in these very limited resource copper wires where you had to dedicate a wire either to a phone call or to data and so we ended up evolving in the academic world what we called stored and forward networking with the sole purpose of compromising everything so that we would keep our cost that we paid for our phone lines to a minimum we wanted to communicate in academia with people all around the country and all around the world so we had to keep the cost low and so we would a lease line you know so so。

So here would be us sitting with terminals in our offices and we would use dialup to get connected and so this might be a few miles like one to two miles。

one to two kilometers and that's what you had to do live near a computer or have an office near a computer and then you would use the local telephone network to dial and to do your work and then there would be one connection up the back of that computer to a another computer that would also have users on it and then other computers with users on it other computers with users on it so this might for example。

 B。Michigan。This might be Stanford。Stanford would have a computer， Michigan would have a computer。

 the Stanford people would be connected to the Stanford computer。

Stanford would have one little connection out itss back end and to the rest of the world so you sitting here want to talk to somebody sitting here so this is how it worked you were sort of always connected so your data would be inside you know you type an email into the computer and then you'd say。

Send that out to my colleague at Stanford。And so the problem is as everyone else was sending and so let's say for example。

 that somebody sent a pretty big thing， big purple circle is what they're sending。

 and then somebody next to you in the office down sends a kind of mediumsd orange circle and they're sitting there being stored in the local computer and then you finally finished typing your email message and it's kind of a small green circle and now the problem is is you're in a line。

The way this worked is the software would keep a queue or a line of those who are going to use the the line。

 and then it would sort of start streaming this stuff out and once it started。

It just kept doing the same file over and over and over now if it died。

 it would just start from the beginning again， and so it takes some time for that thing to move across the network。

And then when move across the network， the next message in line would start to be sent across the network and it would use that link come on finish up there we go okay。

 it takes a while for these things to move across the link and then finally and this could be 10 minutes later finally it was your turn and your stuff would work its way through the network and get to the next computer the problem is that once it's in that computer。

 you face the same problem because if all these messages are going from Michigan。嗯。

We got to hit the button thing from Michigan to Stanford and they're all on the way。

 they got to go through all these links because there wasn't a direct connection because the direct connection to Stanford would be very expensive and so we find ourselves in a situation where you're stored you sat on these computers and if there was an outage of a network。

Or say this one， this might be hours， you might be sitting on this computer for hours on their disk drive right。

 not even in their memory， you'd be sitting on their disk drive for an hour。

 and then finally this would come back or maybe this computer was down。

 they'd come back up and then the data would start flowing again。So， it was。Hlfphazard。

 I keep telling you it was awesome。It was just slow。 It was awesome but slow。

 So don't dont don't feel sorry for us。 We loved it。 We enjoyed it。

 It was great talking to colleagues all over the world。

 So we ended up with a network architecture that。😊，encouraged more hops。

 which means it encouraged more latency and encouraged the likelihood of getting stuck behind something large as it worked its way through the network。

So for example， we were going to send a message from East Lansing to say the East Coast somewhere。

 and we would have two connections， maybe we would have a connection between Michigan State University and East Lansing and Ann Arbor。

 and then we'd have the data would get stored and forward in Ann Arbor。

 and then we get further sent to Cleveland。And if you think about it。

 the wire between Ann Arbor and Cleveland goes like this， right。

 they probably buried wires onto the ground。And if we could。Actually convinced Toledo。The cost of。

The big wire versus the cost of the two shorter wires。

 the cost of the two shorter wires is almost exactly the cost of the big wire because it's not really a big wire and so if we can convince Toledo to join our little club。

Then。We don't increase the cost of our communications because we're it's about the same right the wire length is about the same。

 but we've got one more school for the same cost and if you keep doing that and you keep saying， oh。

 well let's put a school here and I put a school here and put a school here in the middle of a lake and put a school here in the middle of a forest。

The economics said that you could connect more schools with effectively fixed cost by shortening the distance every time you made a connection。

 and sometimes they would sort of make two connections， but the way it often worked was。

From the perspective of。This whole thing is the data would sort of tend to go you know up to some central location and then kind of fan back out from the central location and so these there wasn't a lot of redundant links in this whole situation。

So we find ourselves in a situation where we can save more money saving money by just simply adding hops so in this environment we had a lot of email back in those days we didn't have a lot of images。

 computers you know barely could do upper and lowercase sometimes it was impressive when we finally got to upper lowercase let alone images and so for the longest time everything we did was very text oriented sometimes we would send small files like programs to each other but it was either text and these days those are tiny it's almost like SMS right it's almost like the size of an SMS message was the size of a typical mail message back in those days images we didn't have computers that could even display them and so hardly mattered so you focused your life on this one computer within a 20 mile radius and it had this connection to like a snakelike connection that sort of went over hill and Dale and to somewhere and it finally got to Stanford or wherever your mail had to go。

But again， it was awesome to be able to sit into a keyboard and talk to people all over the world。

 even though it took four hours， we didn't send as much email back then。

And a number of networks came up， one of them that would became sort of pretty widely used was a thing called Binet and it was where everything kind of came back to Princeton was one of the main hubs of Binet and it worked really well and you could there was a way to say。

 oh， I need one more school and we'd go find the ones that are closest and we'd make the connection。

And so that's pretty much how。The average academic saw networking。

 one con campus computer and sort of this weird， slow St forward networking that worked well enough。

 but during that exact same time from the 1960s to the 1980s。

 the US Department of Defense was investing in a research network called ARPpant。

And ARPNt was funded by the military， ARPA Defense Advanced Research Projects Agency。

 and we'll meet later in the lecture， we'll meet Vint Surf will tell the story much better than I can tell。

 but I'll just tell you a short version right now。A lot of people wonder why the Department of Defense started this project and a lot of people say。

 oh， it's because of the fear of nuclear war。And the project was very long and there were various motivations throughout the various phases of the effort。

But if based on what I've been told and what I've read。

 I think it's safe to say that the primary motivation was to improve the use of their computing equipment that they were used for military purposes。

 make it easier to access them make it so people didn't have to travel as much made it so that people could work from their office on many different computers and also so that people could actually talk more effectively so they could send email real fast so that the email would move faster for military people so the first thing is really kind of an end user focused to make them more useful to people and get people working together more effectively that was the first kind of heavy motivation the second motivation was actually had to do withably reliability and redundancy and resistance to partial failure and that really wasn't so much about nuclear attack that was more about battlefield attack so the notion that once you start having all these links and you make。

Wireless and you put them in trailers on a battlefield and you know you got a few hundred miles and the data is moving back and forth。

Then we have to worry about in a battlefield situation。

 one of those trailers might get hit and how would you keep the network running if one of those trailers got hit so the notion that we have sort of a whole nation and we are worried about communications。

 I'm sure there was so worry about that， but it wasn't really the main reason。

 I mean the exciting thing to me is the main reason was a very people centered reason of people working more effectively。

But this was a rather exclusive club， rather exclusive network because it was only for the people who were either military or funded to build it。

 so in 1969 there were four hosts on it。Again that's research and these were lease lines。

 the same ones we were all using to do our email and they were expensive， very expensive。

 but because it was a large grant， they just paid it because the research was not about the money。

 the research was if you had these connections what would be the best way to use them and how to deal with redundancies and how to deal with multiple paths to the same place all that stuff is interesting research questions that computer scientists spent many years。

Conceiving of and so by 1972 looks like we got about 20。

 we got a couple of crosscount links and multiple connections and this looks like a great test bed to see you know so all of a sudden this part goes down how quickly can we reroute around the outage and literally these things these days reroute around outages in far less than a second and so that's really impressive。

Our current internet can owes its history to the research that was done in the 1960s and the 1970s。

But what was fundamentally different between the store and forward networks of Bitnet and this ARPAnet research network was the notion of packet switching。

So it's a real simple concept it just takes a little more complex software to solve the St and forwardward network would start sending data across the link and then keep sending it until it was done that was seemed to be very efficient you didn't want to like you wanted to use it as fast as you can and then put in next one out。

 put the next one out put the next one out it was really simple and it dealt with outages in a simple manner by storing them all locally on the disk but what if instead you made it so。

You broke every message， let me see if I can even draw this and I should probably make a slide about this。

 so if there's a network here and here here's my computer and it's got a network connection。

And it's got one really big message。Broken into pieces。Many pieces。

And it sends the pieces one at a time。If you show up。😡。

With a really short message with only three pieces。

 all you have to do is wait for one piece to go and then your piece goes in and then you share for a while。

You share for a while and then you have made it through because you only have three packets this has like thousand packets and then once your message is through they resume sending this data in order and so you were able to sneak and bypass the traffic jam that was this large amount of data and so that's the idea of packets and packets are these chunks to say what we're going to send is a piece and then at the end of that we're going to maybe send a piece of a different message it was allowing simultaneously multiple message to be in flight at the same time。

That's packet switching。And what happened then is we also ended up with these special purposepo computers called routers。

 they're still computers， but they weren't doing storing in the same way， they were just forwarding。

 they weren't storing forward， they were merely forwarding so we'll get back to that in a second。

So my favorite analogy to talk about how packets work is postcards。

 so let's say that I want to send a 30 character message to my friend Daphne at Stanford。

 but all I have is 10 character postcards so off I go。

 I break my message into three bits of 10 characters。

 I write each piece on a different postcard I address with a from and a two address from Chuck to Daphne。

 and then I give a sequence numbers so that when she gets the postcards she knows what order to put them back together。

So I have to label each of these， and these are fixed width and fixed length。

They you know it's like a packet right it's I'm breaking a long message that might be very long into nothing so that each piece is a certain size so that we can all share it right and so then what I do。

Is I send these， I put them all in my mailbox。And then I wait and this magical thing called the post office picks them up。

Puts them in buildings。People sort them again upon trucks。They end planes on trains， on donkeys。

By hand。And each of my postcards might take a different route， I mean， one of my postcards。

Should have a map here， you know， one of my posts， not that one。that one of my postcards， you know。

 goes from Michigan to Chicago to Kansas City to San Francisco。

Another of my postcards goes from Michigan to Chicago to Dallas。to Denver， Kansas City。

 to Chicago to San Francisco， and my third postcard goes really crazy， it goes to Cleveland。

 and then it goes to Atlanta， then it goes to Washington， DC， and then it goes to Chicago。

 and then it goes to Kansas City， and then it makes it to San Francisco。

Now the fact that they took different paths and they might not even arrive in order。

 some might get past each other， they might get stuck somewhere。

 it doesn't matter because each one of these has been labeled both with the from and the two destination so each of these intermediate locations。

 doesn't have to get it to the final destination， they just have to get it closer。

 they make choices and even if they make the wrong choice。

 it can be sort of dealt with one way or the other okay so this is some big mystery it's called the post office it just takes these little cards with labels and moves them。

 it doesn't know if that's a YouTube video or if it's an email， it doesn't really care。

 it just has these little chunks to move around that have from and two addresses I mean that's the essence of the network。

The internet， the cloud that's why that's why we draw this picture。

 you'll see likeoo it's a cloud and that's because it's don't worry about what's inside here。

 it's all super mysterious and。Don't worry about it， it just comes out so after all that happens。

Daphne， who happens to have the exact same mailbox as I do。

Kin of rare we both have a mailbox that's copyright creative Commons that's what's cool about this mailbox at some point later these things start appearing she goes like well it looks like Chuck is sending me a note but because of his limitation of postcards he's only sent me one I know who it's from and I know who it's to and I know that's the first of some number of messages and then the next day out comes another one because that was the one that sort of went the more southerly route。

And she goes， well I'm missing something I'll just sit and wait and see what happens and then finally many。

 many days later the the one that took the circuit to circuit most circuit is。M。

Most roundabout route。Comes， and now Day can reassemble the messages， because she has。The sequences。

 so she simply puts them back together， one， two， three， boom， so she puts them back together。

 she has it， she sort of throws the postcards away and she has the ultimate final message that's packets packets are breaking a big message into small parts labeling each one of them individually and then throwing them into the shared network and so this is what it looks like。

The post office in this。Is called a gateway。今晚。Gateway。Okay， so that's a gateway， so here's Michigan。

Here's Stanford。Stanford has a gateway too， that's like their post office in the middle is the post office box。

and the post office box basically the post office has intermediate locations and it has trucks and locations。

 these are links and routers。And messages can take different paths。

And then they arrive and they're reassemmbled。And we have like the ability to hook from home and stuff like that。

 so there's a local area network， land， land， and then there's this sort of like internet。

 the network of networks。It's like the post office and it still breaks things into packets。

 they still come out as packets and then Daphne has to reassemble them on her computer to create the message so the research network ARPt solved a lot of engineering problems and that was sort of what they did。

So here is an example problem to solve。Now。None of the mailbox run of the routers。

 none of the post office offices know exactly where the thing is going and they don't transport it to the final destination all they do is they transport it to the future to a further down destination but what if they get it wrong what if one this is like Michigan this is Chicago this is Dallas and what if Michigan thinks sending to Chicago is a good idea Chicago thinks sending to Dallas is a good idea and then Dallas thinks sending to Michigan is a good idea well then Michigans going to get it again and send it back to Chicago and so then what you end up with is this situation where your packet your data is in a loop。

This wouldn't be good for the post office and it's not good for the internet。

 so you have to say how do we solve this problem when something's wrong right you wish it were perfect but it's not。

And so this is the kind of research question as to how to solve this kind of problem。

 and we'll talk more about this in a bit when we get into a little more technical detail。

 but I just wanted to sort to say that's the kind of research and engineering that took literally 20 years and four different versions of the ARPE to get right。

And so。By the end of the 1970s there was quite a sophisticated network。

 like I said they agreewritten it four times， it had gotten to be very sophisticated。

 they' had been good investment， they had been careful about understanding how to improve it each time they rebuilt it and so it was a really a fine working piece of software and the people who used it at these research universities and。

At the military it was kind of like a futuristic world right you could send email and a second later it would appear right it was really quick and everything was nice and you could even have instant message like interactions where it went right then and the problem was is this was a small group of people this is maybe it looks like 60 or so that was all the computers on the entire internet right I mean now we have。

Our cell phones and we got billions of them right， but this is like 60。

So a real question is how did this go from 60 computers of a very narrow group to a much larger group and the answer to that question。

Is at Urana Champaign， Illinois。And so。At the same time。That it kind of goes back to Bletchley Park。

 right， where the computers were part of science。Throughout the 50s and 60s and 70s， scientists。

 much like the military were realizing the computers were mighty useful to advance scientific research。

And so the National Science Foundation would fund universities to buy computers。And theyd say。

 give me $10 million to buy a computer and another university be like give me$10 million to buy a computer and then three years later the first university said my computer's obviously I need another $10 million。

Now the research questions were good research questions and they were important to society。

 but the National Science Foundation got tired of giving 10 million to everybody， going to say。

Ma of fact， I was part of this because I used to be a high performance computer guy this is a。

Convex C3800 supercomputer。I would be about this tall on this supercomputer。

 this is a lovely and very expensive model that I was given after。Afterwards。

 we're going to throw it away because this is from like 1987。嗯。

And basically I wanted one of these terribly badly， each one of these is about 2 million。

 this is like 24， six， eight， 10 million， and I so badly wanted this and I thought that I deserved a $10 million toy and I could do such great research。

 but unfortunately everybody else wanted the exact same thing。

And they were important too so the National Science Foundation said to themselves， hey。

 this isn't going to work very well， if I can't find a pen。

 you know we're not going to be we're going to make a network。

we put a few of these things in and then make a network and connect them together。Of course。

 it's never as simple as that。 so now we're going to meet。Larry Smart。

At the National Center for Zoo for Computing Applics， NCSA at the University of Illinois。

 Ubanish Champaign。And Larry was the director of NCSA and one of the many people。

 but one of the most instrumental people in creating the national network that we now think of as the internet and getting it。

 moving it from being a research project to being a project that we。

All both academics and regular people that we all can make really good use of and so let's take a look at Larry Smart。

