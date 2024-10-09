# 【双语字幕+资料下载】辛辛那提 MATH1071 ｜ 离散数学(2020·完整版) - P79：L79- Intro to Graph Theory _ Definitions & Ex - 7 Bridges of Konigsberg - ShowMeAI - BV1Sq4y1K7tZ

In the 18th century， there was a mathematician called Euler。

 and Euler is one of the most famous mathematicians of all time。 And in particular。

 he really got graph theory Roland。 And the problem that initially motivated him was this。

 There is a place in Kigsburg in ancient Prussia。 And in that city， there is a river。

 And on that river， there are two islands。😊，Connecting the mainland on both sides and the two islands。

 there were seven different bridges。 So the question order had was this。

 I it possible that you can walk through this configuration of islands and bridges in some way where you walk across every single bridge once。

 not twice， not zero times exactly once for every single bridge。So I sat down and tried this myself。

 so like one example would be this kind of path。😡，What I noticed very quickly was that when I did that first path。

 there was one bridge that was missing。 or if I tried to get that bridge。

 it'd have to go over other bridges twice。 Now， maybe I just have a bad path here。

 Maybe you can pause the video and find a path that works。 or maybe you can't， but even if you can't。

 do you know that it's impossible or is it just that you and I haven't thought of one。 Now。

 we're not going to answer this question for a couple videos。

 But we're going to use this to motivate our definitions in graph theory。

 So what I want to do when I look at this particular island here。

 is I realize that there's sort of four main places to stand when you think of them all sort of clump together。

 There's the A and the D here， which are the two land masses on either side of the river。

 And then the B in the sea are the two different islands。if I'm trying to walk through here。

 I try to look at the number of connections。 and what I can do is draw a sort of little pathway that connects each of what we call these vertices。

 the ABCD。 Now the key point is that the exact location of the A and B。

 as long as they're on the same land mass doesn't really matter the exact way I draw the path between say A and B doesn't matter as long as it goes over the one bridge。

 So I can sort of wiggle this whole thing around a little bit， which makes me think。

 why don't we just get rid of the map entirely and just sort of study this configuration。

 And if you prefer kind of looks a little bit messy and hand drawn right now。

 why don't we just go and clean it up and make it little bit more of a straightforward thing。

 So what Ive come up with is the idea of a graph。 So formerly what we say is that a graph is something with vertices。

 the ABCD and edges。 So the way I formally define this is that I'm looking at a pair of things a V and an E。

 the V is just a set of vertices in this case， the ABCD and the。😊。

St for edges is a list of two element subsets the vertices。 So in particular， the subset。

 which is A B， is an edge that goes from the vertex A to the verdex B。

 So it's a two element subset with a starting point and an end point， which are both vertices。

 So in this specific one that I have here。 Let's codify exactly。 my vertices， my A BC D。

 Those are what I will call my vertices。 And then my edges is all the different connections。

 So I see in the graph that there are two different ways I can go from A to B。

 So I write down the two element subset bracket A B， I write that down twice。 And likewise。

 there are sort of one connection from C to D。 So I put one of those into my edge set。😊，Now。

 some of you might recall that back when we did set theory， we said that a set。

 it didn't matter whether you had repetitions and didn't matter what the order was。 Well。

 technically， this is going to be called something called a multiet where I'm say I do care about repetitions。

 If I repeat them twice， that is a different thing than repeating them once。

 So this is truly a multiet。 But the order of it still doesn't matter。

 So it didn't matter whether you listed the order of the ideas differently。

 just says is there a connection between C And D， That's all it matters。😡，Now。

 I have a particular configuration in the plane when I chose to go and draw this。

 But what about the following thing， This is a different graph。 It's still got an ABCD。

 and it's got a bunch of connections between them。 Is it the same graph or is it a different graph。

Well， I think it actually represents the exact same set。 So， for example， the A B。

 there's two A Bs down here and two A Bs up there。 There's two B Ds up here and two B Ds down there。

 So indeed， even though this looks very different from the configuration that came out when we were studying the seven bridges of Kigsburg。

 even though it's completely different looking than that， it really represents the same graph。

 because as the same vertices and the same edges between the same vertices。Indeed。

 if I took the ABCD and I say， okay， what if I make it one， two， three， four， it all looks the same。

 but I just relabel it again， it's the same graph。The idea that I'm doing here is called a graph isomorphism。

 and it says that look you can go and change the colors of any of these graphs。

 you can change the labeling of them， you can rearrange them in space all you want。

 All that matters is that you have effectively the same list of points and all the same connections between them that's the loose idea I'll add a slightly more precise definition of a graph isomorphism down into the description。

😡，So the point is this。 If you have many situations in real life where you've got sort of nodes and connections between them。

 Another example， by the way， is Facebook。 you have a whole bunch of people who are vertices。

 And then if you're a friends， you have a connection between them and all sorts of different examples in the real world。

 you have graphs。 Now， coming up in future videos， we're going to talk about some properties of these graphs。

 something called the degree of a graph， we're going to prove some theorems about graphs。

 and using that， we're going to be able to finally state the answer to this seven bridges of Ksburg problem。

 whether it's possible to take some path over those bridges that hits every one of them。

 exactly once。😊。