# Vim操作

## 复制，粘贴，剪切

### 选择文本

- v+光标移动 （按字符选择）高亮选中所要的文本，然后进行各种操作（比如，d表示删除）。
- V （按行选择）
- v+选中的内容+c 更改选中的文字

### 复制：y(ank)

- y 用v命令选中文本后，用y进行复制
- yy 复制当前行，然后用p进行复制
- 5yy 复制从当前行开始的5行
- y_ 等同于yy
- Y 等同于yy
- yw 复制当前单词
- y$ 从当前位置复制到行尾
- y0 从当前位置复制到行首
- y^ 从当前位置复制到第一个非空白字符
- yG 从当前行复制到文件结束
- y20G 从当前行复制到第20行
- y?bar 复制至上一个出现bar的位置

### 粘贴

- p 在光标位置之后粘贴
- P 在光标位置之前粘贴

### 剪切

- v+选中的内容+d 剪切

### 剪贴板

（1） 简单复制和粘贴

vim提供12个剪贴板，它们的名字分别为vim有12个粘贴板，分别是0、1、2、...、9、a、“、＋；用:reg命令可以查看各个粘贴板里的内容。在vim中简单用y只是复制到“（双引号)粘贴板里，同样用p粘贴的也是这个粘贴板里的内容。

（2）复制和粘贴到指定剪贴板

要将vim的内容复制到某个粘贴板，需要退出编辑模式，进入正常模式后，选择要复制的内容，然后按"Ny完成复制，其中N为粘贴板号（注意是按一下双引号然后按粘贴板号最后按y），例如要把内容复制到粘贴板a，选中内容后按"ay就可以了。

要将vim某个粘贴板里的内容粘贴进来，需要退出编辑模式，在正常模式按"Np，其中N为粘贴板号。比如，可以按"5p将5号粘贴板里的内容粘贴进来，也可以按"+p将系统全局粘贴板里的内容粘贴进来。

（3）系统剪贴板

+号粘贴板是系统粘贴板，用"+y将内容复制到该粘贴板后可以使用Ctrl＋V将其粘贴到其他文档（如firefox、gedit）中，同理，要把在其他地方用Ctrl＋C或右键复制的内容复制到vim中，需要在正常模式下按"+p。

另一种从系统剪贴板复制到vim的方法是使用Shift+Insert。

如果发现本机的vim没有+剪贴板，可以运行下面的命令。

```bash

$ sudo apt-get install vim-gui-common 

```

## 插件

- [Markdown语法高亮](https://github.com/plasticboy/vim-markdown)

### dmw多窗口管理

网址：http://www.vim.org/scripts/script.php?script_id=4186

窗口按下面方式组织。

```
================= 
|      |     S1 | 
|      |==========
|  M   |     S2 | 
|      |========== 
|      |     S3 | 
================= 
```

操作
- CTRL-N 在[M]区域创建一个新窗口，将以前的窗口都堆在[S]区域
- CTRL-C 关闭当前窗口
- CTRL-J 跳到下一个窗口（顺时针方向）
- CTRL-K 跳到前一个窗口（逆时针方向）
- CTRL-F 将当前窗口放入[M]区域，并将其他窗口放在[S]区域
