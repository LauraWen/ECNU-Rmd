# ECNU-本科毕业论文Rmarkdown模板

更新时间:2020年4月16日

### 1. 概述

本模板基于ECNU-本科毕业论文TeX模板进行定制, 突出文学化统计编程给论文写作带来的便利. TeX模板参照了袁轶君（Yijun Yuan）的TeX模板修改而成，参见[link](https://github.com/YijunYuan/ECNU-Undergraduate-LaTeX)

参考文献采用biblatex进行管理，后台biber (而不是传统的bibtex!),文献库采用满足国家标准GB/T7714-2015的[胡振震-biblatex样式包](https://github.com/hushidong/biblatex-gb7714-2015)，参见[hushidong](https://github.com/hushidong)详细介绍。

本模板基于book文档类构建，有许多个小文件组成。本模板提倡模块化的论文写作方式。所有tex文件，最终都会汇入到`main.tex`中进行编译。

### 2. 各文件作用

#### `main.tex`

本模板的核心，控制着整个项目的结构。在这个文件中，你需要修改的只有文章正文的各个section所在的tex文件，它们被建议放置在`~/body/`中。

#### `packages_and_settings.tex`

这个文件用来载入宏包并进行各种格式设置。简而言之，请不要轻易修改，删除本文件中的任何内容，特别是不要修改宏包的加载顺序，除非你真的知道你在做什么。这真的非常重要！！！！！！！

#### `~\preface\paper_info.tex`

本文件中定义了各种论文的基本信息，如作者名称，完成日期，中英文关键词等，需要你自己填写修改。

#### `biber-test.tex`

这是一个biblatex的测试文件，涉及的`reference`目录中的二个bib文件. 建议使用本模板时先熟悉bib文献库的编写文件，并作测试

#### `~\preface\inner-cover.tex`

这个文件定义了论文的封面，请勿进行任何修改，除非你真的知道你在做什么。

#### `~\preface\abstract-CHS.tex, ~\preface\abstract-ENG.tex`

这个两个文件定义了中英文的摘要（事实上还有关键词，只是关键词已经在`paper_info.tex`中填写所以在这个文件中会自动调用，你就不用管了）。


#### `~\body\ch1-xxx.tex`...,`~\body\ch4-xxx.tex`

这些文件定义了正文部分。这里我们按照chapter进行文件分割并在`main.tex`中统一input以便管理。

这些文件包括了各种常用的格式，包括公式、表格、图形、列表、定理及各类引用等。

#### `~\body\appendix.tex`

这个文件给出了论文可能用到的附录，包括R和Python代码的排版。

#### `~\body\thanks.tex`


这个文件定义了致谢的内容，请自行修改填写。

#### `~\figures\`

此文件夹存放图片,其中包括ECNU logo。

#### `~\reference\thesis-ref.bib`
#### `~\reference\refs.bib`

存放了所有的参考文献条码。本模板使用的biblatex系统可以处理多bib文件，我们建议你把所有条目都放在refs.bib文件中, 它列举了许多不同类型的文献类型。biber支持导入多个文献库。

### 3. 使用方法与编译环境

我们强烈推荐使用TeXstudio进行论文编写。

本模板在Mactex下开发，理论上支持texlive 2019。不建议使用CTex套装。

本模板使用了biblatex来进行文献管理，且使用了biber作为后端。如果需要完整编译一次，你需要依次进行以下操作：

```
xelatex main.tex
biber main.bcf
xelatex main.tex
xelatex main.tex
```

是的没错，xelatex指令一共要执行三次。最后的产物就是`main.pdf`。

### 4. 打印模式（新！）

由于最后打印纸质版论文需要调整单面/双面等事项，比较麻烦，所以本模板提供了一个非常易用的开关来控制是否需要启动打印模式。

具体地说，在`main.tex`的第五行有一条命令`\def \PrintMode{} `，默认情况下是打开的，此时产生的pdf文件里会有一些空页，且奇数页与偶数页的layout是相反的，这样在打印时只要在打印机上选择双面打印即可获得满足纸质版要求的论文，不用再做其他调整，非常方便。

当然在使用电子版论文时，这样的空页与layout的调整是没有必要的。此时我们只要将这行命令注释以后重新编译即可。


### 5. 其他

相信使用这份模板的人并不都精通TeX系统，甚至连作者自己也算不上精通，所以有些问题也需要慢慢摸索修改。

### 维护者：

* 汤银才（Yincai Tang）
* 微信号: tangyincai
* 邮箱: tangyc8866@qq.com



