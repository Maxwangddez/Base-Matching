## Base-Matching


### 使用说明

#### 软件包内容

- Base-Matching.cpp **C++源文件**
- Base.h **自定义头文件，包含程序依赖的函数和命令**
- Base.h.gch  **编译器形成的临时文件**
- Base-Matching.exe  **前者编译出的可执行文件**
- Readme.md  **软件说明（Markdown版本）（为保证查看效果，请选择Markdown编辑器或者查看下方的PDF版本）**
- Readme.pdf  **软件说明（PDF版本）**
- Readme.html **软件说明（HTML版本）（图片渲染可能有误）**
- develper.txt  **程序内需调用的文本文件**

#### 运行方法

点击文件夹中的 `Base-Matching.exe`，按照窗口及本说明说明操作即可。

#### 主界面

主界面有四个选项，请在看到 $\color{red}{[Enter]}$ 后直接输入对应选项的编号以跳转至对应功能。

- 在您看到红色的 $\color{red}{[Enter]}$  之前，不要触动键盘，否则程序会读取您误触键盘所获得的输入。

#### 【1】文件查找

文件内关键字查找是本程序的主要功能，首先程序会引导您输入所查找文件的文件名，请输入时务必包含文件后缀。

**提示：本程序目前仅支持未经加密的文本文件，包括但不限于txt、in、out文件。**

您所查找的文件必须是在程序所在文件夹下，您可以通过【2】操作查找您所有可以操作的文件。

如果您输入的文件名称有误或者文件未在正确位置，程序会输出以下结果并立即退出：

```plain
Assertion failed!

Program: C:\Users\Administrators\Desktop\Base-Matching\Base_Matching.exe
File: C:\Users\Administrators\Desktop\Base-Matching\Base_Matching.cpp, Line 22

Expression: infile.is_open()
```

请您重新运行程序并输入正确的文件名。

在您输入正确的文件名之后，程序会提示您输入您要查找的关键字，请您在窗口提示下输入该关键字，并按 $[Enter]$ 键。

之后您可以看到 “请选择是否输出到文件[Y/N]”：

如果您想把查找的结果写入文件，请输入 `Yes`、`yes`、`YES`、`Y`、`y` 中的任何一种，程序会提醒您输入文件名。

如果您只想在窗口浏览，请输入除上述 5 种字符串的任意一种。

接着程序会输出查询结果，如果您选择了输出至文件，文件会同步写入查询结果，并在关键字前后添加"__"，输出的文件会被清空，请谨慎选择输出的文件。

**注意：输出到的文件也只被允许是文本文件，包括但不限于诸如txt、in、out的未加密文件。**

查询完成后轻击键盘，程序会返回主菜单，您可以进行新一轮的查询，也可以选择退出程序。

#### 【2】文件列表

通过此功能，您可以查看目录下的所有文件名称。

此功能显示出的文件名称是您可以通过【1】功能读取并操作的。

#### 【3】开发者详情

详见下方开发者简介。

#### 【4】离开

通过此功能，您可以优雅地离开程序。

#### 常见问题

###### Q1:

为什么在主菜单程序会自动跳转？

###### ANS1：

是因为您在输入提示阶段误触了键盘，程序错把您的误触当做输入，您可以选择重新启动程序或者在其他功能完成后返回主菜单。

###### Q2:

为什么我输入了正确的文件名称程序依然读取不到？

###### ANS2:

您可以检查全/半角符号是否输入正确，或者该文件是否被其他进程占用。

###### Q3:

这个程序可以移植到其他系统上吗？

###### ANS3:

不可以，程序头文件包含 `conio.h` 且使用了 Windows 的系统函数，无法移植到其他平台上使用噢。 

### 项目简介

#### 项目名称

中文名：文字匹配系统

英文名：Base-Matching

#### 程序目标

给定一个文本文件，输入需要查找的关键字，查找该关键字在文章中出现的次数及位置并高亮显示出来。

#### 具体算法和实现

在字符串匹配时使用了 C++ 自带的 `string::find` 函数，该函数时间复杂度较高，最坏情况下为 $\operatorname{O}(n^2)$，但在实际应用中较小概率会出现最坏情况，而且该算法空间复杂度较低，为 $\operatorname{O}(1)$，相比之下，由于需要进行预处理，在实际应用中比其实现更复杂但时间复杂度更低的 KMP 等算法（时间复杂度为 $\operatorname{O}(m+n)$，空间复杂度为 $\operatorname{O}(n)$）反而运行效率更低，本程序无法充分发挥其优势，故采用 STL 模板库的 `string::find` 进行匹配，且该函数进行了优化，时间常数有所缩小，运行效率较高。

#### 不足及改进

由于能力有限以及时间匆忙，本项目没有采用图形界面，观感有些不好，但是经过测试，作者本人已经尽己所能优化实际操作体验以满足视觉清晰及操作便捷的要求，算法和功能经过作者的严格测试，但时间仓促，难免有纰漏和失误，如果有不足之处请联系作者改进，本人的联系方式已附上，敬请见谅。

### 开发者简介

- 作者姓名：王腾昊
- 学校：辽宁省丹东市第二中学
- 班级：2019级14班
- 联系方式 ：
- E-mail：1786166292@qq.com  
- TEL：18642510115
- QQ：1786166292

### 补充说明

#### 开源地址

- [Github](https://github.com/Maxwangddez/Base-Matching)

#### 版权协议

- 本作品在 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.zh)  下提供。

  <img src="https://i.loli.net/2020/04/30/AIfjVaoWUPGXgm3.png" style="zoom:100" />

#### 鸣谢

在本项目开发期间，征询了多位计算机博主的意见和建议，他们来自 [知乎社区](https://www.zhihu.com/)，和 [洛谷](https://www.luogu.com.cn/)，感谢他们为我提供的技术上的建议和支持。

感谢我的学校的老师为我提供了这次机会，让我领略程序设计的美好。

**欢迎各位师长、同学为本项目的进一步完善提出意见和建议，如果您有宝贵建议，请联系我，我将不遗余力完善我的项目，从而提升我的技术水平。**

- 感谢您关注并使用本项目

- 作者 王腾昊 @Maxwang





