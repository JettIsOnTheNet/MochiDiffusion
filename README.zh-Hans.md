<p align="center">
<img height="256" src="https://github.com/godly-devotion/MochiDiffusion/raw/main/Mochi Diffusion/Resources/Assets.xcassets/AppIcon.appiconset/AppIcon.png" />
</p>

<h1 align="center">Mochi Diffusion</h1>

<p align="center">在 Mac 上原生运行 Stable Diffusion</p>

<p align="center">
<a href="https://github.com/godly-devotion/MochiDiffusion/blob/main/README.md">English</a>,
<a href="https://github.com/godly-devotion/MochiDiffusion/blob/main/README.ko.md">한국어</a>,
<a href="https://github.com/godly-devotion/MochiDiffusion/blob/main/README.zh-Hans.md">中文</a>
</p>

![Screenshot](.github/images/screenshot.png)

## 简介

本应用内置 [Apple 的 Core ML Stable Diffusion 框架](https://github.com/apple/ml-stable-diffusion) 以实现在搭载 Apple 芯片的 Mac 上用极低的内存占用发挥出最优性能，并同时兼容搭载 Intel 芯片的 Mac。

## 功能

- 极致性能和极低内存占用 (使用神经网络引擎时 ~150MB)
- 在所有搭载 Apple 芯片的 Mac 上充分发挥神经网络引擎的优势
- 生成图像时无需联网
- 在图像的 EXIF 信息中存储所有的关键词
- 生成图像超分辨率 (使用 RealESRGAN)
- 自定义 Stable Diffusion Core ML 模型
- 无需担心损坏的模型
- 使用 macOS 原生框架 SwiftUI 开发

## 下载

在 [发行](https://github.com/godly-devotion/MochiDiffusion/releases) 页面下载最新版本。

## 运行

在初次运行一个模型时, 神经网络引擎可能需要约30秒编译一个缓存版本，后续运行速度会显著提高。

## 计算单元

- `CPU 和神经网络引擎` 能很好地平衡性能和内存占用
- `CPU 和 GPU` 在 M1 Max/Ultra 及后续型号上可能更快，但会占用更多内存

你需要根据不同的计算单元选择对应的模型 (详情见模型部分)。

搭载 Intel 芯片的 Mac 只能使用 `CPU 和 GPU`，因其没有配备神经网络引擎。

## 模型

你需要自行转换或下载 Core ML 模型以使用 Mochi Diffusion。

[这里](https://huggingface.co/godly-devotion) 上传了几个已经转换好的模型

1. [转换](https://github.com/apple/ml-stable-diffusion#-converting-models-to-core-ml) 或下载 Core ML 模型
    - `split_einsum` 版本适用于包括神经网络引擎在内的所有计算单元
    - `original` 版本仅适用于 `CPU 和 GPU`
2. 本应用会在默认将工作目录创建在 文稿 文件夹中，但在应用设置中可以自定义其路径。
3. 在工作目录中，你可以创建一个文件夹，以自己想在应用内显示的名字为其重命名，再将转换好的模型放到文件夹中
4. 你的文件夹路径应该像这样: `~/文稿/MochiDiffusion/models/[Model Folder Name]/[Model's Files]`

## 兼容性

- Apple 芯片的 Mac (M1 及后续) 或 Intel 芯片的 Mac (需要高性能 CPU 和 GPU)
- macOS Ventura 13.1 以上
- Xcode 14.2 (自行构建)

## 隐私

所有计算均在本地完成并绝对不会上传任何数据。

## 贡献

Mochi Diffusion 欢迎贡献者，不管是修复bug，新增代码，还是完善翻译。

- 如果你找到一个bug，对现有功能有意见和想法，或者想要一个新功能，请先 [在这里搜索你的问题](https://github.com/godly-devotion/MochiDiffusion/discussions) 以避免重复。如果你没看到和你一样的问题，请 [发起一个新的讨论](https://github.com/godly-devotion/MochiDiffusion/discussions/new)。

- 如果你想贡献代码，请 [创建拉取请求](https://github.com/godly-devotion/MochiDiffusion/pulls) 或 [发起一个新的讨论](https://github.com/godly-devotion/MochiDiffusion/discussions) 来探讨。

- 如果你想对 Mochi Diffusion 贡献翻译，请 [发起一个讨论](https://github.com/godly-devotion/MochiDiffusion/discussions)，我会提供所需的文件。

## 致谢

- [Apple's Core ML Stable Diffusion implementation](https://github.com/apple/ml-stable-diffusion)
- [HuggingFace's Swift UI sample implementation](https://github.com/huggingface/swift-coreml-diffusers)
- 应用图标作者 [Zabriskije](https://github.com/Zabriskije)
