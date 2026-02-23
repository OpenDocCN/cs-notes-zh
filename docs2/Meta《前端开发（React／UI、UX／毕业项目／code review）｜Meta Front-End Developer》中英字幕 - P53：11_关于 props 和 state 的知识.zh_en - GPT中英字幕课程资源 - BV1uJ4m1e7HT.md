# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P53：11_关于 props 和 state 的知识.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

![](img/40371164cb824da28d92d6800811c1c1_0.png)

Imagine that little Le has been such a success that the restaurant will be expanding to other locations As a part of the construction project。

 the architects have created blueprints with the kitchen and dining areas set to be identical in size。

 Although the blueprints have been defined， it will still be up to each restaurant manager to decide various things。

 such as the size， shape and number of tables， type of chairs。

 kitchen crockery and utensils and wall collar。😊，In this analogy。

 the blueprints for the new locations are react components。

 whereasas the specific configurations for each location are what react props in state represent。

 So what are props in state， Pros in state are both plain jascript or J S objects。

 The react uses to hold information。 As you progress through this video you will discover The differences and similarities between props and state in react。

You'll also learn how to identify whether something falls into props or state and when state is needed。

 as well as how to differentiate between different react components based on props and state。

While both props and state influence the render output， they are different in one important way。

 props get passed to the component like parameters in a function where state is managed within the component like variables declared within a function。

 So even though props in state are inherently different， there are areas where they overlap notably。

 when designing a component， its main responsibility is to translate raw data into rich Hm L。

 in the react ecosystem， the props and the state together constitute the raw data that the Hm L output derives from。

 Both props and state are plain J S objects and are deterministic。

 This means your component always generates the same output for the same combination of props and state。

Another similarity is that props and state changes both trigger a render update。 Now。

 how do you know if something goes inside props or state。

 The rule of thumb is that if a component needs to alter one of its attributes at some point in time。

 that attribute should be part of its state。 Otherwise， it should just be a prop for that component。

Let's explore this in greater detail。 Pros， which is a shorthand for properties。

 are a components's configuration。 They are received from parents in the tree and are immutable as far as the component receiving them is concerned。

😊，A component cannot change its props， but it is responsible for putting together the props of its child components。

 In addition to prop， react components have another built in object named state。

 This object is a way to allow react to determine when it should re rendernder a component。

 React is set up so that any change to the value served in the state object will trigger a re rendernder of a given component。

St's life cycle starts with a default value when a component mounts and then modifications of that value happen over time。

 mostly generated from user events。 So state is a serializable representation of one point in time。

 or in other words， a snapshot。A component manages its own state internally。

You could also say the state is private。Now， another question you may ask when designing a component is whether it should have any state at all。

 well the answer is that state is optional。Since state increases complexity and reduces predictability。

 a component without state is preferable。 although you can't avoid having some sort of state in an interactive app。

 you should avoid having too many components with state。 Finally。

 let's examine one of the main ways of differentiating types of react components based on props and state。

 componentsons can be stateless or stateful。Stateless components have only props and no state。

 There's not much going on besides the render function and all their logic revolves around the props they receive。

 This makes them very easy to follow and test。 On the other hand。

 stateful components have both props and state。 there in charge of client server communication。

 processing data and responding to user events。These sorts of logistics should be encapsulated in a moderate number of stateful components。

 while all visualization and formatting logic should move downstream into as many stateless components as possible。

 Well done。 You have completed this lesson on the two types of data react uses to build applications。

 props and state。 going forward， you'll be introduced to an additional approach to managing information called context。



![](img/40371164cb824da28d92d6800811c1c1_2.png)