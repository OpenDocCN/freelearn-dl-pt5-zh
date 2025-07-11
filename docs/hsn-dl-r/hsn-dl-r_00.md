# 前言

深度学习能够从海量数据中高效、准确地学习。深度学习被越来越多的行业采用，因为它可以帮助解决许多传统机器学习方法难以解决的挑战。

使用 R 的开发者将能够通过这本实用指南将他们的知识付诸实践。这本书提供了一种实践的方法，结合了实施和相关方法论，你将在短时间内开始运行并高效工作。书中详细讲解了关键概念和实际案例，你将从深度学习的基本概念入手，了解深度学习的优势和架构概览。你将探索各种深度学习算法的架构，并理解它们的应用领域。你还将学习如何构建深度学习模型、优化超参数并评估模型表现。

本书结束时，你将能够使用针对你的问题的深度学习框架和算法，构建并部署自己的深度学习模型和应用程序。

# 本书的适用对象

本书的目标读者是数据分析师、机器学习工程师和数据科学家，他们熟悉机器学习，并希望巩固深度学习的知识，或者通过使用 R 让他们的机器学习应用更加高效。我们假设读者具备一定的编程背景，至少掌握一些常见的机器学习技术，并且有一定的 R 语言经验或了解。

# 本书内容概述

第一章，*机器学习基础*，回顾了机器学习的所有基本要素。这个快速复习很重要，因为我们将进入深度学习——机器学习的一个子集，它包含了许多共通的术语和方法。

第二章，*为深度学习设置 R 环境*，总结了在 R 中用于深度学习和强化深度学习的常见框架和算法。你将熟悉常用的库，包括 MXNet、H2O 和 Keras，并学习如何在 R 中安装每个库。

第三章，*人工神经网络*，教你关于人工神经网络的知识，人工神经网络是所有深度学习的基础构建模块。你将构建一个简单的人工神经网络，并学习它的各个组件如何结合在一起解决复杂问题。

第四章，*用于图像识别的卷积神经网络（CNN）*，演示了如何使用卷积神经网络进行图像识别。我们将简要介绍为什么这些深度学习网络优于浅层网络。该章的其余部分将讲解卷积神经网络的组成部分，并考虑如何做出最合适的选择。

第五章，*用于信号检测的多层感知机神经网络*，展示了如何构建用于信号检测的多层感知机神经网络。你将了解多层感知机神经网络的架构，并学习如何准备数据、定义隐藏层和神经元，以及如何使用反向传播算法在 R 中训练模型。

第六章，*使用嵌入的神经协同过滤*，解释了如何使用分层嵌入构建神经协同过滤推荐系统。你将学习如何使用自定义的 Keras API，构建具有用户-项目嵌入层的架构，并使用隐式评分训练一个实际的推荐系统。

第七章，*自然语言处理的深度学习*，解释了如何创建文档摘要。本章开始时将去除文档中不应考虑的部分，并对剩余文本进行分词。随后，将应用嵌入并创建聚类。这些聚类随后被用于生成文档摘要。我们还将学习如何编码**限制玻尔兹曼机**（**RBM**），并定义吉布斯采样、对比散度和自由能量。最后，本章将通过编译多个 RBM 来创建深度信念网络。

第八章，*用于股票预测的长短期记忆网络*，展示了如何使用**长短期记忆**（**LSTM**）RNN 网络进行预测分析。你将学习如何为 LSTM 准备序列数据，并学习如何使用 LSTM 构建预测模型。

第九章，*面部生成对抗网络*，描述了**生成对抗网络**（**GANs**）的主要组成部分和应用。你将了解生成对抗网络的常见应用，并学习如何利用 GANs 构建面部生成模型。

第十章，*游戏中的强化学习*，演示了在井字游戏中使用强化学习方法。你将了解强化学习的概念和在高度可定制框架中的实现。此外，你还将学习如何创建一个智能体，为每个游戏步骤选择最佳动作，并在 R 中实现强化学习。

第十一章，*用于迷宫求解的深度 Q 学习*，展示了如何使用 R 实现强化学习技术以应对迷宫环境。具体来说，我们将创建一个智能体，通过训练它执行动作并从失败的尝试中学习，以解决迷宫。

# 为了最大限度地利用本书

我们假设您已经熟悉并能顺利下载和安装计算机上的软件，包括 R 和从 CRAN 或 GitHub 安装的额外 R 库包。我们还假设您有一定的基础，能够根据 R Studio 控制台输出独立地排查和解决打包依赖问题（如有需要）。您需要在计算机上安装 R 和 R Studio 版本，最好是最新版本。

所有代码示例已在 macOS X 10.11（El Capitan）及更高版本的 R 3.6.3 上进行测试。此代码应该也能在未来的版本中运行，尽管这可能需要更新第二章中列出的某些深度学习 R 软件包，*为深度学习配置 R*。

| **本书中涉及的硬件/软件** | **操作系统要求** |
| --- | --- |
| 适用于 Intel Mac 的 64 位 | macOS X 10.11（El Capitan）及更高版本 |
| R 版本 3.6.3 | macOS X 10.11（El Capitan）及更高版本 |
| R Studio Desktop 1.2.5033（Orange Blossom 330255dd） | R 版本 3.0.1+ |

在您的计算机上安装了 R（[`www.r-project.org`](https://www.r-project.org)）和 R Studio Desktop（[`rstudio.com/products/rstudio/download/`](https://rstudio.com/products/rstudio/download/)）后，您应该准备好安装第二章中概述的其他深度学习软件包，*为深度学习配置 R*。

**如果您使用的是本书的数字版本，我们建议您自己输入代码，或者通过 GitHub 仓库访问代码（链接见下一节）。这样可以帮助您避免因复制和粘贴代码而导致的潜在错误。**

# 下载示例代码文件

您可以从[www.packt.com](http://www.packt.com)的帐户中下载本书的示例代码文件。如果您是在其他地方购买本书，您可以访问[www.packtpub.com/support](https://www.packtpub.com/support)并注册，文件将直接通过电子邮件发送给您。

您可以按照以下步骤下载代码文件：

1.  登录或注册到[www.packt.com](http://www.packt.com)。

1.  选择支持选项卡。

1.  点击代码下载。

1.  在搜索框中输入书名并按照屏幕上的说明操作。

下载文件后，请确保使用以下最新版工具解压或提取文件夹：

+   WinRAR/7-Zip for Windows

+   Zipeg/iZip/UnRarX for Mac

+   Linux 版 7-Zip/PeaZip

本书的代码包也托管在 GitHub 上，地址为[`github.com/PacktPublishing/Hands-on-Deep-Learning-with-R`](https://github.com/PacktPublishing/Hands-on-Deep-Learning-with-R)。如果代码有更新，将在现有 GitHub 仓库中更新。

我们还提供其他代码包，您可以在我们丰富的书籍和视频目录中找到，访问地址是**[`github.com/PacktPublishing/`](https://github.com/PacktPublishing/)**。快来看看吧！

# 下载彩色图像

我们还提供了一份 PDF 文件，其中包含本书中使用的截图/图表的彩色图像。你可以在此下载：[`static.packt-cdn.com/downloads/9781788996839_ColorImages.pdf`](https://static.packt-cdn.com/downloads/9781788996839_ColorImages.pdf)

# 使用的约定

本书中使用了多种文本约定。

`CodeInText`：表示文本中的代码词汇、数据库表名、文件夹名称、文件名、文件扩展名、路径名、虚拟 URL、用户输入和 Twitter 用户名。例如：“`linear_fits`函数随后再次使用，绘制另一条线。”

代码块设置如下：

```py
linear_fits <- function(w, to_add = TRUE, line_type = 1) {curve(-w[1] / w[2] * x - w[3] / w[2], xlim = c(-1, 2), ylim = c(-1, 2), col = "black",lty = line_type, lwd = 2, xlab = "Input Value A", ylab = "Input Value B", add = to_add)}
```

当我们希望提醒你注意代码块中特定部分时，相关的行或项目会以粗体显示：

```py
results <- softmax(c(2,3,6,9))
results

[1] 0.0008658387 0.0023535935 0.0472731888 0.9495073791
```

**粗体**：表示新术语、重要词汇，或屏幕上看到的词汇。例如，菜单或对话框中的词汇在文本中会像这样出现。这里有一个例子：“ReLU 的一个潜在问题被称为**dying ReLU**，因为该函数将所有负值赋值为零，信号在到达输出节点之前可能完全丢失。”

警告或重要提示如下所示。

提示和技巧如下所示。

# 联系我们

我们始终欢迎读者的反馈。

**一般反馈**：如果你对本书的任何内容有疑问，请在邮件主题中提到书名，并通过`customercare@packtpub.com`联系我们。

**勘误**：虽然我们已经尽最大努力确保内容的准确性，但错误总是难以避免。如果你发现本书中的错误，我们将不胜感激，如果你能向我们报告。请访问 [www.packtpub.com/support/errata](https://www.packtpub.com/support/errata)，选择你的书籍，点击勘误提交表格链接，并填写相关信息。

**盗版**：如果你在互联网上发现我们作品的任何非法复制形式，我们将非常感激你能提供相关的地址或网站名称。请通过`copyright@packt.com`与我们联系，并附上该材料的链接。

**如果你有兴趣成为一名作者**：如果你在某个领域具有专业知识，并且有兴趣撰写或参与撰写一本书，请访问 [authors.packtpub.com](http://authors.packtpub.com/)。

# 评论

请留下评论。阅读并使用完本书后，为什么不在你购买书籍的网站上留下评论呢？潜在读者可以查看并参考你的中立意见，从而做出购买决定。我们在 Packt 可以了解你对我们产品的看法，我们的作者也能看到你对他们书籍的反馈。谢谢！

获取更多关于 Packt 的信息，请访问 [packt.com](http://www.packt.com/)。
