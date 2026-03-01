# 杜克大学《Rust编程4-5（Linux命令行工具、LLMOps）｜Rust programming》中英字幕 p97 09_01_01_应对受损资源与工作负载.zh_en -BV1Hy411q7Zm_p97-

Today we're going to talk about a crucial subject which is responding to compromised resources and workloads within AWS。

 and this area is critical for maintaining security， compliance and operational continuity。



![](img/139498c2186413ebc977f00345ffb054_1.png)

To start off with， let's define what a compromised resource is。

 it is any network or device that has been altered maliciously。

 Some examples include an EC C2 instance or an unauthorized S3 bucket access and impact can range from data loss to legal liability and also making a prompt that is vital。

 So let's go ahead and talk about a AWS security incident response guide。

 AWS offers a specific guide to handling security incidents tailored to an environment。

 and this guide includes identifying the incident， isolating affected systems and also coordinating with legal entities。

 and it's a critical resource for any AWS security professional。



![](img/139498c2186413ebc977f00345ffb054_3.png)

When you talk about isolating a compromised resource。

 what it means is that you're preventing it from causing further harm like a virus。 for example。

 in AW S， this could mean disconnecting in easy C to instance or even restricting S3 bucket access。

 This quick isolation would minimize the risk and is the first step in most response times。



![](img/139498c2186413ebc977f00345ffb054_5.png)

Now， if we talk about root cause analysis techniques here。

 it means that you're understanding why a resource was compromised and it's the key to preventing a future incident。

 this could involve looking at Cloudtrail logs or analyzing guard duty findings or other AWS tools。

 but the core goal here is to understand what went wrong and how to make improvements going forward。

Also we have data and log analysis and the idea here is that you're capturing data like an EBS snapshot or a memory dump。

 and this helps you understand what's actually happening。

 This log analysis includes concepts like querying logs in S3 so that you can provide contextual information and these techniques support a detailed understanding and proper reporting。

There also is the concept of automating remediation。

 and this means that AWS offers services that can do automated response。 For example。

 you could have serverless automated response that sends out emails or notifications。

 and this speeds up the recovery。 The automation of the response also would reduce the human error。

 and it also can be tailored to a specific incident。

It's a powerful tool in a modern incident response， orchestration。

Forensic data protection is critical for legal and compliance reasons。

 some examples are tools like S3 object lock or isolated forensic accounts that can be used to secure evidence。

 and this is going to ensure the integrity of the investigation and any potential legal proceedings。



![](img/139498c2186413ebc977f00345ffb054_7.png)

Also， it's important to understand the preparation and recovery。

 This means being prepared and having plans and tools and training in place before the incident even occurs。

 The recovery includes restoring the services， learning from the incident and even improving for the future。

These are continuous processes in an effective security management organization。

 so it means that you're constantly updating these procedures。

So really the next steps here are to remember to respond to compromised resources using a mix of technical skills planning and understanding of AWS。

 this includes isolation， recovery and also steps like maintaining security and compliance afterwards。

 it's also important to understand that continuous learning and practice is critical to maintain a secure organization。



![](img/139498c2186413ebc977f00345ffb054_9.png)