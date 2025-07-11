# 前言

**深度学习（DL）**是一种相对较新的机器学习类型，在自然语言理解和计算机视觉等任务中展现出了惊人的效果。有时，DL 的准确度甚至超过人类。

得益于开源框架的普及、公开可用的模型架构和预训练模型，许多人和组织能够成功地将前沿的深度学习模型应用于他们的实际用例。然而，开发、训练和部署深度学习模型还需要高度专业化且昂贵的硬件、软件栈、专业知识和管理能力，这可能会显著减缓其采用进程。

本书重点介绍如何在 Amazon SageMaker 上设计和管理深度学习工作负载，从而帮助您克服上述障碍。SageMaker 是一个广泛的 AWS 云机器学习平台，具有多种功能。本书并不打算详细介绍所有 SageMaker 功能，而是深入探讨与深度学习工作负载相关的特性。在编写本书时，我们优先考虑了深度而非广度。本书的目标是为您提供有关如何高效地在 Amazon SageMaker 上实施实时深度学习模型应用的实用指南。

由于云计算和机器学习的采用正在加速，本书可能对广泛的受众群体感兴趣，从初学者到经验丰富的机器学习从业者。具体来说，本书适合从事深度学习模型开发和训练的机器学习工程师，以及负责设计和优化深度学习工作负载的解决方案架构师。

假设您已经熟悉 Python 生态系统，以及机器学习和深度学习的基本原理。熟悉 AWS 并拥有与之合作的实践经验也是有帮助的。

随着章节的推进，从入门和概述主题到高级实现和优化技术，章节的复杂性逐步增加。您可以跳过某些章节，或者选择与您当前任务相关的具体主题。

本书的大多数章节都有相应的代码示例，您可以通过这些示例获得使用 Amazon SageMaker 的实际经验。建议您亲自尝试运行代码示例，当然，您也可以查看它们。我们还为每个章节的代码示例提供了注释。

请注意，运行代码示例会产生 AWS 费用。请确保查看 Amazon SageMaker 定价页面以获取详细信息。

我们欢迎您对本书的反馈和建议，并希望您享受您的学习旅程。

# 本书适用对象

本书是为已经具备深度学习（DL）领域基础知识，并希望学习和获得在 AWS 云上使用 Amazon SageMaker 服务功能训练和托管深度学习模型的实际经验的 DL 和 AI 工程师编写的。

# 本书涵盖的内容

*第一章*，*通过 Amazon SageMaker 介绍深度学习*，将介绍 Amazon SageMaker：它如何简化基础设施和工作负载管理，以及该 AWS 服务的关键原则和主要功能。随后，我们将重点介绍托管训练、托管基础设施以及与其他 AWS 服务的集成。

*第二章*，*SageMaker 上的深度学习框架和容器*，将详细回顾 SageMaker 如何广泛利用 Docker 容器。我们将首先深入了解流行深度学习框架（TensorFlow、PyTorch 和 MXNet）的预构建容器。接着，我们将探讨如何扩展预构建的 SageMaker 容器和使用自带容器。对于后者，我们将回顾在 SageMaker 中训练和服务容器的技术要求。

*第三章*，*SageMaker 开发环境管理*，将讨论如何使用 CLI、SDK 和 CloudFormation 以编程方式管理 SageMaker 资源。我们将探讨如何使用 SageMaker Studio 和 Notebooks 组织高效的开发流程，以及如何与您喜欢的 IDE 集成。我们还将回顾如何使用 SageMaker Local Mode 排查深度学习代码的问题。我们将回顾 SageMaker 的各种功能，帮助我们组织和管理数据集，并讨论 AWS 上的各种存储选项及其应用场景。

*第四章*，*深度学习数据集管理*，将提供关于在 SageMaker 上设置第一个深度学习项目的实用指南，然后构建、训练并使用一个简单的深度学习模型。我们将提供该项目的跟随实现，以便读者可以自行学习和实验 SageMaker 的核心功能。

*第五章*，*深度学习训练硬件考虑*，将讨论最适合深度学习模型的实例的性价比特点，并覆盖在不同场景下如何选择不同实例类型以获得最佳性能。

*第六章*，*工程化分布式训练*，将重点介绍分布式训练过程的常见方法，并解释为什么深度学习模型可能需要这样做。然后，我们将概述开源训练分发框架以及 SageMaker 原生分布式训练库。

*第七章*，*深度学习训练的运营化*，将讨论如何使用 SageMaker Debugger 及其 Profiler 监控和调试深度学习训练任务，以及如何通过管理型 Spot 训练、提前停止和其他策略来优化成本。

*第八章*，*考虑硬件推理*，将提供使用 PyTorch 和 Hugging Face 框架构建 NLP 最先进模型的实际指导。读者将跟随代码学习如何准备用于在 Amazon SageMaker 上进行分布式训练的训练脚本，并监控和进一步优化训练任务。我们将使用 SageMaker 数据并行库来分配训练计算。

*第九章*，*实现模型服务器*，将从回顾 SageMaker 托管服务的关键组件开始，例如实时端点和批量推理任务、模型注册表和服务容器。读者将学习如何使用 Python SDK 配置其端点部署和批量推理任务。

*第十章*，*操作推理工作负载*，将专注于 DL 服务器的软件堆栈，特别是模型服务器。我们将回顾 TensorFlow 和 PyTorch 解决方案提供的模型服务器，以及像 SageMaker 多模型服务器这样的框架无关模型服务器。我们将讨论何时选择某一选项而非另一选项。

# 为了充分利用本书

| **书中涵盖的软件/硬件** | **操作系统要求** |
| --- | --- |
| 已建立本地 SageMaker 兼容环境 | Windows、macOS 或 Linux |

**如果您使用的是本书的数字版本，我们建议您自己输入代码或从本书的 GitHub 仓库获取代码（下一节提供了链接）。这样做将帮助您避免与复制和粘贴代码相关的潜在错误。**

# 下载示例代码文件

您可以从 GitHub 下载本书的示例代码文件，网址为[`github.com/PacktPublishing/Accelerate-Deep-Learning-Workloads-with-Amazon-SageMaker`](https://github.com/PacktPublishing/Accelerate-Deep-Learning-Workloads-with-Amazon-SageMaker)。如果代码有更新，它将在 GitHub 仓库中更新。

我们还提供了来自我们丰富书籍和视频目录的其他代码包，网址为[`github.com/PacktPublishing/`](https://github.com/PacktPublishing/)。快来看看吧！

# 下载彩色图片

我们还提供了一个 PDF 文件，里面包含了本书中使用的截图/图表的彩色图片。您可以在此下载：[`packt.link/FXLPc`](https://packt.link/FXLPc)。

# 使用的约定

本书中使用了多种文本约定。

`代码文本`：表示文本中的代码单词、数据库表名、文件夹名、文件名、文件扩展名、路径名、虚拟 URL、用户输入和 Twitter 用户名。以下是一个示例：“在以下代码块中，我们使用`'_build_tf_config()'`方法来设置此变量。”

一段代码块设置如下：

```py
estimator.fit({
"train":"s3://unique/path/train_files/",
"test":"s3://unique/path/test_files"}
)
```

所有命令行输入或输出如下所示：

```py
conda create -n sagemaker python=3.9
```

当我们希望引起你对代码块中特定部分的注意时，相关的行或项目会以粗体显示：

```py
 tensorboard --logdir ${tb_debug_path}
```

**粗体**：表示新术语、重要词汇或屏幕上出现的单词。例如，菜单或对话框中的单词通常会以**粗体**显示。举个例子：“在**创建默认的 IAM 角色**弹出窗口中，选择**任何 S3 存储桶**。”

提示或重要说明

看起来像这样。

# 与我们联系

我们始终欢迎读者的反馈。

**常规反馈**：如果你对本书的任何内容有疑问，请在邮件主题中注明书名，并通过 customercare@packtpub.com 联系我们。

**勘误表**：虽然我们已经尽力确保内容的准确性，但仍然可能会有错误。如果你发现本书中有错误，我们将非常感谢你向我们报告。请访问 [www.packtpub.com/support/errata](http://www.packtpub.com/support/errata)，选择你的书籍，点击勘误提交表单链接并填写相关细节。

**盗版**：如果你在网上发现我们作品的任何非法复制品，无论何种形式，我们将非常感谢你提供该材料的位置地址或网站名称。请通过 copyright@packt.com 联系我们并附上该材料的链接。

**如果你有兴趣成为作者**：如果你在某个领域拥有专业知识，并且有兴趣撰写或贡献一本书，请访问 [authors.packtpub.com](http://authors.packtpub.com)。

# 分享你的想法

阅读完 *《使用 Amazon SageMaker 加速深度学习工作负载》* 后，我们很想听听你的想法！请 [点击这里直接访问亚马逊的书籍评价页面](https://packt.link/r/1-801-81644-1)，并分享你的反馈。

你的评价对我们以及技术社区至关重要，将帮助我们确保提供高质量的内容。

# 下载本书的免费 PDF 副本

感谢购买本书！

你喜欢随时随地阅读，但又无法随身携带纸质书籍吗？你的电子书购买无法兼容你选择的设备吗？

别担心，现在购买每本 Packt 图书，你都可以免费获得该书的无 DRM PDF 版本。

在任何地方、任何设备上阅读。可以直接搜索、复制并粘贴代码到你最喜欢的技术书籍中。

优惠不仅仅到此为止，你还可以获得独家折扣、新闻通讯以及每天直接发送到邮箱的精彩免费内容。

按照这些简单的步骤来获取优惠：

1.  扫描二维码或访问下面的链接

![](img/B17519_QR_Free_PDF.jpg)

https://packt.link/free-ebook/9781801816441

1.  提交你的购买证明

1.  就这些！我们会直接将免费的 PDF 和其他福利发送到你的电子邮件中

# 第一部分：在 Amazon SageMaker 上的深度学习简介

在第一部分，我们将从简要介绍深度学习和 Amazon SageMaker 开始，接着重点讲解在本书中将使用的 SageMaker 关键功能。

本节包含以下章节：

+   *第一章*，*通过 Amazon SageMaker 引入深度学习*

+   *第二章*，*SageMaker 上的深度学习框架和容器*

+   *第三章*，*管理 SageMaker 开发环境*

+   *第四章*，*管理深度学习数据集*
