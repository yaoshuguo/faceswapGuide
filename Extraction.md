### [Guide] Extraction - A Workflow

FROM: [https://faceswap.dev/forum/viewtopic.php?f=5&t=27](https://faceswap.dev/forum/viewtopic.php?f=5&t=27)

```
https://tool.oschina.net/commons?type=3
```
### Introduction

A lot of people get overwhelmed when they start out Faceswapping, and many mistakes are made. Mistakes are good. It's how we learn, but it can sometimes help to have a bit of an understanding of the processes involved before diving in.<br>
> 很多人在开始换脸的时候会不知所措，而且会犯很多错误。错误是好的。这是我们学习的方式，但有时在潜入之前对所涉及的过程有一点了解会有所帮助。

In this post I will detail a workflow for Extraction. I'm not saying that this is the best workflow, or what you should do, but it works for me, and will hopefully give you a good jump off point for creating your own workflow.<br>
> 在这篇文章中，我将详细介绍`Extraction`提取的工作流程。我并不是说这是最好的工作流程，或者你应该做什么，但它对我很有用，希望能给你一个很好的跳转点，创建你自己的工作流程。

I will be using the GUI for this guide, but the premise is exactly the same for the cli (all the options present in the GUI are availablle in the cli).<br>
> 我将在本指南中使用GUI，但是cli的前提是完全相同的（GUI中的所有选项都可以在cli中使用）。

### Why Extract?

At the highest level, extraction consists of three phases: detection, alignment and mask generation. There are several plugins for each of these. Their pros and cons are detailed in the tooltips (for the GUI) or the help text (for the cli), so I won't be covering specifics. However, detection is the process of finding faces within a frame, alignment is finding the "landmarks" within a face and orienting the faces consistently. Finally mask generation is creating a "mask", that is identifying which parts of the final face image are face and which are background/obstructions.<br>
> 在最高层次上，提取包括三个阶段：检测、对齐和生成遮罩。每个插件都有几个插件。它们的优点和缺点在工具提示（对于GUI）或帮助文本（对于cli）中有详细说明，因此我将不讨论细节。然而，检测是在一个框架内找到人脸的过程，对齐是在一个人脸内找到“地标”并一致地确定人脸的方向。最后，蒙版生成是创建一个“蒙版”，即识别最终人脸图像的哪些部分是人脸，哪些是背景/障碍物。

Extracting serves 2 main purposes:<br>
> 提取有两个主要目的：
- To generate a set of faces, and optionally an alignments file and mask, for training the model
- To generate an alignments file and mask for converting your final frames
> - 生成一组面以及路线文件和遮罩（可选）以训练模型的步骤
> - 生成用于转换最终帧的路线文件和遮罩的步骤
There is technically a 3rd purpose which is when you are extracting for converting and want some of these faces for training as well. I will also cover this off.<br>
> 从技术上讲，这是第三个目的，当你提取转换，并希望这些脸的一些训练以及。我也会把这件事掩盖起来。


