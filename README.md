# 山人全息码（定制版）


 github中的项目文件可能存在有问题，可能无法正常部署，抱歉。
 
 如有问题可自行查看rime部署时的日志文件（路径位于（就是后面这个，输入到资源管理器地址栏就可以转跳过去） %TEMP%\）进行排查，亦可提出issue。

### 这个山人方案是基于

> - 发明人 谢振斌
> - 方案制作 张仓〈QQ：1095863854〉
> - （词库还部分来自疏影孤桐）

### 上述版本进行定制修改获得的。

## 下面是项目更新说明：

2022-04-24
> - 1.整理码表，去重。

2021-09-08
> - 1.修改为一位群友编写的构词版，常用词汇均可以用双键组词了，方便本人打词的习惯，也可以造词。

2021-05-02
> - 1.**采用社区群友更新的码表，已经更新FG区拓展，目前全覆盖中日韩表意文字A~G区，收录编码汉字应达到九万多。**
> - 2.修改原先原先私用区的汉字上屏，如果是**私用区的汉字，在候选和上屏时字尾均带p**，将其与扩展区后收录的同字区分。
> - 3.因为字库较大，且配置不是很完善，rime的部署过程可能较久，请耐心等待。


## 原来的方案特点如下：

- 1.通过【袖珍简化字拼音】实现 ` 键拼音反查
- 2.简入繁出 需要安装 opencc 简繁转换词典（一般会自带）
- 3.原版**收录汉字单字个数8万多（理论上全覆盖中日韩表意文字A~E区，即截止2015年，Unicode8.0版本），词库中词语/句子个数超过35万**

## 修改后拥有新增以下特点

- 1.通过斜杠“/”加关键词输入大量特殊字符，该功能原版也有，我只不过是进行了一些调整。若要进行符号的增删修改，直接在mysymbols文件中调整即可；
- 2.常用字符如~！@#%……&*（）——=-+，。\；‘：’“”，全部一键上屏，没有原版rime的无用选择。货币符号正在考虑修改方向；
- 3.中文输入模式下，按下方括号键位直接上屏为“「”和“」”；
- 4.中文输入模式下，按下shift+方括号键位（即花括号键位），直接上屏为“【”和“】”，均没有原版rime的各种选择，以符合个人使用习惯。
- 5.调用了easy-English的词库，实现了**中英文混输**。
- 6.键入字码时按下Enter回车键直接上屏字码（英文），而不是像原版rime那样进行清空键入；键入字码时按下两侧shift按键均直接上屏字码并切换为英文输入模式；修改后的实现类似搜狗输入法，符合我的使用习惯。
- 7.为了支持超大的字库显示，请安装天珩全字库。
- 8.囿于rime的win发行版小狼毫输入法并不能设置多个备选字体(mac的rime发行版可以)，因此win用户请确保调整注册表使之设为系统备选字体（在字库软件安装时会自动打上注册表链接）。（即便设置好了，尚有部分特殊字符如变体假名𛂧𛄎等不能直接在输入面板显示，目前暂不知原因）

