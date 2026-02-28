# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P31：30_模块4 1 2 JSON.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

🎼。

![](img/41c23f46d1bac9d3d38a5a4e181abdee_1.png)

🎼う。🎼Yeah。So JON as a format has several properties that are advantageous。

One is that it's all Uniicode okay so any JSsonN object， once you convert something into JSON。

 it's going to be represented all as Uniicode characters。

 which is good because Unicode is understandable by people。 In fact。

 that leads another thing it's generally human readable right a human could look at the JSON format and understand for the most part what it is。

 it might be slightly complicated， but it's readable by a human。Now。

 it's also a fairly compact representation。 I say fairly compact because it's not completely compact。

 if we were to the most compact， then you wouldn't， it wouldn't be human readable anymore。

 So if you took the JSson object and just compressed it。 You would get something that was smaller。

 but you couldn't read it。 Okay so it's fairly compact。 It's human readable。

 it's as small as you're going to get and still be human readable。 put it like that。

And so the types inside JSON can be combined recursively when I say the types the different types of data that you're putting together。

 so remember that in JSON， we're going to want to represent these different data structures that we have。

 these objects that we have in Golan， we're going to want to represent them as JSON objects。

So they can be combined recursively so you can have an array of integers or an array of structures or a structure with structures inside or a structure with arrays inside and integers and strings so you can combine them all hierarchically right a structure with structures inside which have other structures inside and so on so you can get arbitrarily complex goalang objects and convert them into JSON so that's a pretty good advantage。

So JSON marshalling， marshalling， the term marshalling means to in this case in JSON marshalling。

 you're generating JSON， a JSON representation from an object in our case a go object right so we've got some object arbitrarily complex and go we want to make turn it into something that adheres to JSON format so that's called marshalling。

 JSON marshalling。😡，So in this example we're going to start off with our person struct and heres here's the general structure。

 typestruct got a name， address address phone， they're all strings and this is the structure。

 so let's say we create we have an actual person an object of this particular structure of this type and and this person P1 it has a particular name Joe address a street phoneone 1。

2，3， we've seen this before so now we want to take this person destruct and we want to make it turn it into a JSON object so we call this function JsonN Marshall Json。

marshall。And notice that we pass as an argument， we pass P1， the structure。

 the go length structure that we want to convert， we pass that as an argument to JO Marshall。

And it returns two things。In this case， they called B the first thing is B array。

 I'm calling it and X is error。 So the error is， it's a nil if there's no error。 if it cons properly。

 then this should be a nil， therell be no error。 And what the real what it returns this B array is actually going to be a byte array。

Whi it contains the JSsonN representation so and remember that JSON is all Uniiccode。

 this byte array is a bunch of ruins basically an array of them that that is the JSOsonN representation so what Marshall does JSON Marshall does is it takes a goall object returns you a JSON representation。

So JSON Unmarshaing is going in the opposite direction What you're trying to do is you take some byte array which represents which contains a JSON object and you want to convert that into a goal lay object which stores the same information So going from the last slide where again talking about this personstruct so let's say we have already made our BA RR our B array and that's a person it's a JSsonN representation of a person。

😡，Now we want to unmarshal it， so we want to take this JSON representation and create a J excuse a golstruct。

 which contains the same information。So what we do is we declare that goal lengthstruct up there at the top。

 we say var P2， we call it P2 person， so it's a person， but we haven't created it yet。

 we haven't filled in the name， address phone yet， so we just have a person and it's basically empty。

Then we call Json dot on Marshall。 Now notice there two arguments were pass into JSsonN dot on Marshall。

 first argument is the B array which is the actual byte array， which contains the Json object。

The second argument is the address of the go structure that we want the results to be placed into。

 So address of P2 because remember that this B array it contains information about a person。

 We want that to be put into this P2 that we've created that is as of now empty。So when you call it。

It just basically unpacks the BRA and puts the fields into the appropriate that attribute values into the appropriate fields of the person structure。

 P2。Now one thing about this is that one constraint is that this P2。

 whatever the second argument is to unmarshall， it needs to fit the JSON data， the JSON byte array。

 when I say fit， I mean， the JSON object is going to have a set of attributes and values of those attributes。

P2， the second argument， it's got to have the same attribute。 So if it's astruct in this case。

 it's got to have the same those have to be the field names。

 So if the JSson object has an attribute called name than the goaling object P2。

 it better have a field called name So that's the idea so it has to fit。😡，But if it does。

 then what will happen as you call on Marshall and in the NP2 have will will be a struct that contains all the information that was contained in the JSON object and that error value that's returned by JSO。

 on Marshall， its nil if everything works， everything fits， if it doesn't fit， it'll throw an error。

Thank you。

![](img/41c23f46d1bac9d3d38a5a4e181abdee_3.png)