# 欢迎来到Flutter入门体验:

- [安装Flutter框架](#安装Flutter框架)
- [安装Flutter框架的依赖关系](#安装Flutter框架的依赖关系)
- [创建，运行并更改您的第一个Flutter应用程序](#创建，运行并更改您的第一个Flutter应用程序)
- [通过一个小的循序渐进的课程来学习Flutter核心的概念](#通过一个小的循序渐进的课程来学习Flutter核心的概念)
- [下一步的建议](#下一步的建议)

# [安装Flutter框架](#安装Flutter框架)
*   [使用镜像](#使用镜像)
*   [系统要求](#系统要求)
*   [获取Flutter SDK](#获取flutter-sdk)
    *   [更新环境变量](#更新环境变量)
    *   [运行 flutter doctor](#运行-flutter-doctor)
*   [编辑器设置](#编辑器设置)
*   [Android设置](#android设置)
    *   [安装Android Studio](#安装android-studio)
    *   [设置您的Android设备](#设置您的android设备)
    *   [设置Android模拟器](#设置android模拟器)
*   [下一步](#下一步)

## 使用镜像

由于在国内访问Flutter有时可能会受到限制，Flutter官方为中国开发者搭建了临时镜像，大家可以将如下环境变量加入到用户环境变量中：

<div class="highlighter-rouge">

<div class="highlight">

    export PUB_HOSTED_URL=https://pub.flutter-io.cn
    export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn

</div>

</div>

**注意：** 此镜像为临时镜像，并不能保证一直可用，读者可以参考详情请参考 [Using Flutter in China](https://github.com/flutter/flutter/wiki/Using-Flutter-in-China) 以获得有关镜像服务器的最新动态。

## 系统要求

要安装并运行Flutter，您的开发环境必须满足以下最低要求:

*   **操作系统**: Windows 7 或更高版本 (64-bit)
*   **磁盘空间**: 400 MB (不包括Android Studio的磁盘空间).
*   **工具**: Flutter 依赖下面这些命令行工具.
    *   [Git for Windows](https://git-scm.com/download/win) (Git命令行工具)

        如果已安装Git for Windows，请确保命令提示符或PowerShell中运行 `git` 命令，不然在后面运行`flutter doctor`时将出现`Unable to find git in your PATH`错误, 此时需要手动添加`C:\Program Files\Git\bin`至`Path`系统环境变量中。

## 获取Flutter SDK

1.  去flutter官网下载其最新可用的安装包，[点击下载](https://flutter.io/sdk-archive/#windows) ；

    注意，Flutter的渠道版本会不停变动，请以Flutter官网为准。另外，在中国大陆地区，要想正常获取安装包列表或下载安装包，可能需要翻墙，读者也可以去Flutter github项目下去[下载安装包](https://github.com/flutter/flutter/releases) 。

2.  将安装包zip解压到你想安装Flutter SDK的路径（如：`C:\src\flutter`；注意，**不要**将flutter安装到需要一些高权限的路径如`C:\Program Files\`）。

3.  在Flutter安装目录的`flutter`文件下找到`flutter_console.bat`，双击运行并启动**flutter命令行**，接下来，你就可以在Flutter命令行运行flutter命令了。

<div class="alert alert-info" style="margin-top:-5px">

**注意：** 由于一些`flutter`命令需要联网获取数据，如果您是在国内访问，由于众所周知的原因，直接访问很可能不会成功。 上面的`PUB_HOSTED_URL`和`FLUTTER_STORAGE_BASE_URL`是google为国内开发者搭建的临时镜像。详情请参考 [Using Flutter in China](https://github.com/flutter/flutter/wiki/Using-Flutter-in-China)

</div>

上述命令为当前终端窗口临时设置PATH变量。要将Flutter永久添加到路径中，请参阅[更新路径](#更新环境变量)。

要更新现有版本的Flutter，请参阅[升级Flutter](/upgrading/)。

### 更新环境变量

要在终端运行 `flutter` 命令， 你需要添加以下环境变量到系统PATH：

*   转到 “控制面板>用户帐户>用户帐户>更改我的环境变量”
*   在“用户变量”下检查是否有名为“Path”的条目:
    *   如果该条目存在, 追加 `flutter\bin`的全路径，使用 `;` 作为分隔符.
    *   如果条目不存在, 创建一个新用户变量 `Path` ，然后将 `flutter\bin`的全路径作为它的值.
*   在“用户变量”下检查是否有名为”PUB_HOSTED_URL”和”FLUTTER_STORAGE_BASE_URL”的条目，如果没有，也添加它们。

重启Windows以应用此更改

### 运行 flutter doctor

打开一个新的命令提示符或PowerShell窗口并运行以下命令以查看是否需要安装任何依赖项来完成安装：

     flutter doctor

在命令提示符或PowerShell窗口中运行此命令。目前，Flutter不支持像Git Bash这样的第三方shell。

该命令检查您的环境并在终端窗口中显示报告。Dart SDK已经在捆绑在Flutter里了，没有必要单独安装Dart。 仔细检查命令行输出以获取可能需要安装的其他软件或进一步需要执行的任务（以粗体显示）

例如:

<pre>[-] Android toolchain - develop for Android devices
    • Android SDK at D:\Android\sdk
    **✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ**
    • Try re-installing or updating your Android SDK,
      visit https://flutter.io/setup/#android-setup for detailed instructions.
</pre>

第一次运行一个flutter命令（如flutter doctor）时，它会下载它自己的依赖项并自行编译。以后再运行就会快得多。

以下各部分介绍如何执行这些任务并完成设置过程。你会看到在`flutter doctor`输出中， 如果你选择使用IDE，我们提供了，IntelliJ IDEA，Android Studio和VS Code的插件， 请参阅[编辑器设置](/get-started/editor/) 以了解安装Flutter和Dart插件的步骤。

一旦你安装了任何缺失的依赖，再次运行`flutter doctor`命令来验证你是否已经正确地设置了。

该flutter工具使用Google Analytics匿名报告功能使用情况统计信息和基本崩溃报告。 这些数据用于帮助改进Flutter工具。Analytics不是一运行或在运行涉及`flutter config`的任何命令时就发送， 因此您可以在发送任何数据之前退出分析。要禁用报告，请执行`flutter config --no-analytics`并显示当前设置，然后执行`flutter config`。 请参阅[Google的隐私政策](https://www.google.com/intl/en/policies/privacy/)。

## 编辑器设置

使用 `flutter` 命令行工具，您可以使用任何编辑器来开发Flutter应用程序。输入`flutter help`在提示符下查看可用的工具。

我们建议使用我们的插件来获得[丰富的IDE体验](/using-ide/)，支持编辑，运行和调试Flutter应用程序。请参阅[编辑器设置](/get-started/editor/)了解详细步骤

## Android设置

### 安装Android Studio

要为Android开发Flutter应用，您可以使用Mac，Windows或Linux（64位）机器.

Flutter需要安装和配置Android Studio:

1.  下载并安装 [Android Studio](https://developer.android.com/studio/index.html).

2.  启动Android Studio，然后执行“Android Studio安装向导”。这将安装最新的Android SDK，Android SDK平台工具和Android SDK构建工具，这是Flutter为Android开发时所必需的

### 设置您的Android设备

要准备在Android设备上运行并测试您的Flutter应用，您需要安装Android 4.1（API level 16）或更高版本的Android设备.

1.  在您的设备上启用 **开发人员选项** 和 **USB调试** 。详细说明可在[Android文档](https://developer.android.com/studio/debug/dev-options.html)中找到。
2.  使用USB将手机插入电脑。如果您的设备出现提示，请授权您的计算机访问您的设备。
3.  在终端中，运行 `flutter devices` 命令以验证Flutter识别您连接的Android设备。
4.  运行启动您的应用程序 `flutter run`。

默认情况下，Flutter使用的Android SDK版本是基于你的 `adb` 工具版本。 如果您想让Flutter使用不同版本的Android SDK，则必须将该 `ANDROID_HOME` 环境变量设置为SDK安装目录。

### 设置Android模拟器

要准备在Android模拟器上运行并测试您的Flutter应用，请按照以下步骤操作：

1.  在您的机器上启用 [VM acceleration](https://developer.android.com/studio/run/emulator-acceleration.html) .
2.  启动 **Android Studio>Tools>Android>AVD Manager** 并选择 **Create Virtual Device**.
3.  选择一个设备并选择 **Next**。
4.  为要模拟的Android版本选择一个或多个系统映像，然后选择 **Next**. 建议使用 _x86_ 或 _x86_64_ image .
5.  在 Emulated Performance下, 选择 **Hardware - GLES 2.0** 以启用 [硬件加速](https://developer.android.com/studio/run/emulator-acceleration.html).
6.  验证AVD配置是否正确，然后选择 **Finish**。

    有关上述步骤的详细信息，请参阅 [Managing AVDs](https://developer.android.com/studio/run/managing-avds.html).

7.  在 Android Virtual Device Manager中, 点击工具栏的 **Run**。模拟器启动并显示所选操作系统版本或设备的启动画面.
8.  运行 `flutter run` 启动您的设备. 连接的设备名是 `Android SDK built for <platform>`,其中 _platform_ 是芯片系列, 如 x86.