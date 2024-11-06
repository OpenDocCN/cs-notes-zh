CSE 331 软件设计与实现

# 作业提交

内容：

+   介绍

+   验证

    +   这是做什么的？

    +   结果是什么？

    +   为什么必须在 attu 上通过命令行运行？

## 介绍

您通过提交到您的 SVN 存储库来提交作业。 如果一切顺利，这就足够了，但我们强烈建议您然后*验证*您的提交，以避免出现您未正确提交作业的严重问题。

## 验证

验证您的代码会检查常见错误，例如您检入的代码在用于评分的编译器中无法正确编译。 这些错误可能会阻止您获得代码的学分，因此您应该在完成作业之前始终验证您的作业。 但是，验证不能保证捕捉到代码中的所有错误。

您应该通过在 attu 上运行`ant validate`来验证您的作业（并确保它成功完成！）通过运行以下命令。

你可以从任何机器上通过 SSH 登录 attu （通过 SSH）。 （即使您在 Allen Center Linux 机器上工作，您仍然需要 SSH 登录 attu。）

```
cd ~/workspace331/cse331/src/hw*N*/
ant validate

```

或者

```
cd ~/cse331/src/hw*N*/
ant validate

```

根据您检出 Subversion 存储库副本的位置，您需要选择正确的版本。 如果您尚未在 CSE Linux 机器上检出存储库（比如，因为您在 Windows 上工作或在家里工作），那么您必须首先使用命令行检出存储库。 请注意，如果您按照建议的位置检出工作副本，那么您项目的路径（如上面的说明和下面的输出中列出的）将不包括`workspace331/`目录。

### 这是做什么的？

这将检出您代码的新副本（到临时目录）并确保您的实现：

+   包含所需的文件

+   无错误编译。 这很重要，因为如果您不在 Allen Center 软件实验室工作，您可能正在使用不同的编译器。 您可以在任何地方工作，但您的代码必须在`attu`上运行（并且必须无错误或警告地编译）。

+   通过**学生的**`hw*N*.test.ImplementationTests`和`hw*N*.test.SpecificationTests`。 （您可以选择阅读更多关于 CSE 331 JUnit 框架的信息。）

### 结果是什么？

如果验证成功，您应该看到类似以下内容的输出：

```
Buildfile: /homes/iws/username/workspace331/cse331/src/hw1/build.xml

validate:
     [echo] Validate checks out a fresh copy of the hw, checks for the
     [echo]       presence of required files, and runs all your tests to make sure
     [echo]       they pass.  This target can only run on the attu IWS machine.
     [echo]
     [echo]       Note: the test reports will be generated under the scratch
     [echo]       directory the validate target creates.
     [echo]
   [delete] Deleting directory /homes/iws/username/workspace331/cse331/scratch
    [mkdir] Created dir: /homes/iws/username/workspace331/cse331/scratch
     [echo] /projects/instr/13sp/cse331/username/workspace331/REPOS
     [exec] A    cse331
     [exec] A    cse331/.classpath

     ...

     [exec] BUILD SUCCESSFUL
     [exec] Total time: 2 seconds
   [delete] Deleting directory /homes/iws/username/workspace331/cse331/scratch

```

如果出现错误，验证脚本应提供有关错误的一些信息：

```
Buildfile: /homes/iws/username/workspace331/cse331/src/hw1/build.xml

validate:
     [echo] Validate checks out a fresh copy of the hw, checks for the
     [echo]       presence of required files, and runs all your tests to make sure
     [echo]       they pass.  This target can only run on the attu IWS machine.
     [echo]
     [echo]       Note: the test reports will be generated under the scratch
     [echo]       directory the validate target creates.
     [echo]

     ...

     [exec] cleancopy:
     [exec]      [echo] Hw directory: /homes/iws/username/workspace331/cse331/scratch/cse331/src/hw1
     [exec]
     [exec] BUILD FAILED
     [exec] /homes/iws/username/workspace331/cse331/scratch/cse331/src/common.xml:106: The following error occurred while executing this line:
     [exec] /homes/iws/username/workspace331/cse331/scratch/cse331/src/common.xml:121: Could not find required file: answers/hw1_answers.pdf
     [exec]
     [exec] Total time: 1 second
     [exec]
     [exec] cleancopy.check:

BUILD FAILED
/homes/iws/username/workspace331/cse331/src/common.xml:160: exec returned: 1

```

此错误表明缺少一个必需的文件，`answers/hw1_answers.pdf`。 确保您已将此文件提交到 SVN。

如果验证输出显示错误，你应该在截止日期之前修复它们，否则你的作业将扣分。如果验证失败是因为公共测试套件失败，你可以在`*YourWorkspaceDirectory*/scratch/cse331/src/hw*N*/test/reports`目录中查看 JUnit 失败的摘要。

**重要提示：**请注意，验证脚本会针对**你自己的测试套件**测试你的代码。尽管默认情况下我们会在`hw*N*.test.SpecificationTests`中填充公共测试套件，但如果你希望验证脚本检查你的代码是否通过公共测试，那么保留这些测试在`hw*N*.test.SpecificationTests`中是你的责任。

### 为什么这个必须在 attu 上通过命令行运行？

大多数由工作人员提供的 ant 目标应该在 Allen Center 软件实验室和你的家用电脑上都能工作，但`ant validate`只在`attu`上工作。这是因为我们在 attu 上评分你的解决方案，所以验证你的代码在确切的环境中编译和运行正确是很重要的。

Eclipse 集成的 Ant 支持不能很好地处理 ant `validate`目标。即使你使用 Eclipse 作为开发环境，你也应该像上面所示在*命令行上*进行验证。
