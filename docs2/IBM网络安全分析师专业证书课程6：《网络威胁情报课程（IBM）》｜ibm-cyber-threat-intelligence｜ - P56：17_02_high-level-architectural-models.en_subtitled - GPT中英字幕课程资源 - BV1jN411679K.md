# IBM网络安全分析师专业证书课程6：《网络威胁情报课程（IBM）》｜ibm-cyber-threat-intelligence｜ - P56：17_02_high-level-architectural-models.en_subtitled - GPT中英字幕课程资源 - BV1jN411679K

Welcome back to the unit on security Arch concepts。 In the last video。

 we discussed how architecture is important to the construction of robust security。In this video。

 we will continue our conversation on concepts that will help you describe your high level security architecture。

I will explain the characteristics of a high level security architectural models。

 discuss the different representations at different levels of abstraction and when to use the model in practice。

Architecture is defined as the arts of the A building。When buildings are been constructed。

 they often start with an overall picture that gives the visual idea of what the building will look like。

It does not define how the building will be constructed。And tells us little about the context。

In this example， for a building， it does give us a little bitss of context in terms of contour lines and a lake。

 but it does not tell us the details that would allow us to construct the building。

In it architecture， this is what could be considered as an enterprise level architecture。

 There will be further drawings that will give detail on the context and the implementation of the system。

Let's start with different types of high level architecture。

We can break the problem down into further levels of abstraction。

 enterprise architecture and solution architecture。First， the enterprise architecture。

Considers a wide scope for the whole enterprise。 It shows the main components of the problem space at a very high level。

 with a small number of components。It might show some interrelationships and contexts。

 but a very high level。It could show processes， high level business services or different domains。

 that representation is very loose。As we。As we decompose the problem。

 we need to go and add context and technology components。

 We start to move into solution architecture。Now， we start to add the context about the environment and the technology perspectives。

 The architecture diagrams become more complex。Let's look at how we represent these architectures。

We use what is called building blocks。These will be used to represent a business need。

 It could be a capability domain Act or a business service。

 These building blocks are there to represent a grouping that is loosely coupled。

At an enterprise level。Architectural building blocks or A BBs are high level guiding。

Components divide guiding the development of the solution architecture。

The A BBs are product and beer neutral。At the solution architecture level。

 solution building blocks or SBB specify technical components or particular products to implement a function。

Context is is added in terms of the platforms and the environments。

 They may be product or vendor aware。Let's look at some example building blocks。In this example。

 we have five high level architecture building blocks。

 They are general security domains like data and application security。

 They are not specific security functions。And the solution building blocks show security functions such as certificate authority or application firewall。

 but are not specific to any vendor or product in this example。Let's look at an example。

 enterprise architecture。This is a high level example of an enterprise security architecture for hybrid multi cloudud。

 with architectural building blocks showing there are five domains for logical security that are supported by physical security。

As this is about security for multiple clouds， it shows integration takes place with multi cloud security management。

 with oversight through governance， risk and compliance。

This is good as a high level set of domains to help organize projects or decompose problems。

 but it tells us nothing about the context of technology， capabilities or environments。

 So let's look at another example。In this example of an enterprise architecture。

 we start to add groupings of security capabilities to provide more detail on the composition of each domain。

But it still doesn't have any context。This can be useful as a heat map to describe the maturity of capabilities being delivered。

I've seen organizations use this sort of diagram to assess maturity and then colour the capabilities red。

 amber or green to enable a focus on remediation of security controls。

Let's go on to look at the next level of detail。In this enterprise security architecture。

 we've taken security domains and split them into security controls built into the cloud infrastructure and security added on top of the cloud infrastructure。

With the built in security domains， the controls can be deployed onto network。

 compute and storage platforms that are then decomposed further。For networking。

 the controls can be in the physical underlay network， software defined overlay network。

 and the container communication using a service mesh。

Then each of these platforms can be deployed into different environments。

On premise in a corporate data centre， a private cloud。

 a public cloud and an on edge computing service。The same security domains are used for the built in security and the add on security。

 as every cloud is different。In what is included and often security will be needed as an atdom。

Across the top， the picture shows multiclo security management again。

To integrate each of the environments。Overall， governance risk and compliance is needed to ensure security is working effectively。

This sort of architecture diagram is used to describe the dimensions of the different perspectives of security controls that need to be considered in the context of that I T environment。

In this case， it helps a security architect describe the complexity of the security controls in a hybrid multi cloud environment。

It can be used to discuss the need for a common I and security platform。

Across the different environments， Otherwise， this gives rise to complexity。

 resulting in increased cost and reduced effectiveness of security。

All of these architecture diagrams you'll see at a very high level。

 they don't describe the physical implementation。In the next video。

 you'll get to understand further representations of a solution architecture。

As the solution is decomposed into specific implementations of a solution。That's it for now。

 I'll speak to you in the next video about decomposing the solution architecture。



![](img/ace2ff739f96f99db9c02a77a2208d75_1.png)

![](img/ace2ff739f96f99db9c02a77a2208d75_2.png)