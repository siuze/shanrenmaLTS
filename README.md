![Social Preview](https://user-images.githubusercontent.com/54578647/217300073-75a2cd02-756e-45ad-a272-5e32178a51dc.png)

山人码LTS是山人全息码输入方案的长期支持版。

该方案继承了谢振斌、持双山、疏影孤桐、五磅兔、张仓等前辈的大部分山人码方案设计，单字码表已完全覆盖Unicode13.0内9万字余汉字

主要维护工作由本人负责，并欢迎开源社区贡献。以实现：

- 码表长期维护
- 字根与构字成词方法长期稳定，不做大大幅度改动
- 对提交的码表更新建议与错误反馈会及时处理

## 使用方法/功能说明/编码与输入规则

请参考[项目文档](https://siuze.github.io/ShanRenMaLTS/)主页


## 项目更新日志：

**2023-03-04**
> 1. 增加unicode相关功能插件，实现：①unicode编码查字；②对私用区、扩展区的单字，在编码提示区提示相应分区与unicode编码；
> 2. 调整方案配色

**2023-03-03**
> 【方案架构较大调整】
> 
> 1. 调整N+N规则，放弃1+1的通配（方案原有词汇快速码不受影响），现在N的范围限制在[2, 4]；
> 2. 方案的核心翻译器放弃使用table_translator，不增设table_translator实现词汇预测，减少资源调用开销。这使得词汇联想功能失效，本人修改了librime的源码，见该[commit](https://github.com/rime/librime/issues/568#issuecomment-1452135770)，可实现输入音节数大于等于4时的词汇预测。对应的框架发行版本获取方式见项目主页安装说明；
> 3. 恢复使用新的lua导入方式；
> 4. 调整部分lua扩展插件行为；
> 
> 
> 已知问题（尚未影响常规使用）：
> 1. 长词汇编码结尾似乎有点问题，存在冗余，需要排查；
> 2. 用户词典内的自造词尚未实现词汇联想；
> 3. 大写锁定时只能用caps lock按键关闭，无法使用shift进行开关
> 4. 开启英文词库table翻译器时日志频繁打印english made a futile translation.
> 5. 小狼毫在chrome等软件下较卡顿，在QQ下正常

> 
> 近期维护计划：
> 1. 实现提示生僻字unicode编码区的lua插件；
> 2. 使用unicode编码输入文字的lua插件；
> 3. 测试拼写纠错功能配置项translator/enable_correction的效果；
> 4. 排查大写锁定相关问题
> 5. 排查长词编码问题
> 
> 次优先维护计划：
> 1. 用户词典词汇预测；
> 2. 小于三个音节时的词汇预测；
> 3. 词库进行筛选优化
> 4. 日志频繁打印问题

**2023-02-08**
> 1. 拆分超大词库，使方案在小狼毫下可以正常部署，当前Release版本的码表已包含近280万条词句
> 2. 调整n+n输入规则，现在n的范围为1到4
> 3. 调整翻译器配置（尚在调试中，对造词和权值排序的影响尚未可知） 

**2023-02-07**

>1. 词库调整
>
>  -  45万核心词库，来自于过去山人方案的35万词汇表和结巴分词词库。已引入“2+2”码表方案和“n+n”码表方案
>
>  -  200万扩展词库，码表已生成，但词库过大，小狼毫下部署长时间卡死，遂暂在代码仓库中存放，未在Release的方案中引入
>
>2. 因小狼毫维护者[暂不打算更新librime版本](https://github.com/rime/weasel/issues/821)，故回退lua引入方式

**2023-01-26**

>重构码表后正式发布山人码LTS
>
> 1. 具完整单字码表，与过去山人方案变动不大；
> 2. 含30万核心+70万扩展词库；
> 3. 具输入增强功能，支持n+n任意省略规则进行词汇输入，支持长词的4+1输入规则；
> 4. 含英文词库，支持中英混输功能开关；
> 5. 增设日期、数字输入转换插件；
> 6. 使用原创【风入松】样式配置；
>
>该方案已验证可在[替换最新rime.dll](https://github.com/rime/weasel/issues/821)后的[小狼毫v0.14.3_dev_0.98](https://github.com/fxliang/weasel/releases/tag/0.14.3_dev_0.98)下运行。
>
>已知问题：
>
> - 开启扩展词库和输入增强插件后输入法使用卡顿
> - 开启扩展词库下日志文件频繁警告【...engine.cc:204] Oops, got a futile translation.】

**2022-04-24**
> - 1.整理码表，去重。

**2021-09-08**
> - 1.修改为一位群友编写的构词版，常用词汇均可以用双键组词了，方便本人打词的习惯，也可以造词。

**2021-05-02**
> - 1.**采用社区群友更新的码表，已经更新FG区拓展，目前全覆盖中日韩表意文字A~G区，收录编码汉字应达到九万多。**
> - 2.修改原先原先私用区的汉字上屏，如果是**私用区的汉字，在候选和上屏时字尾均带p**，将其与扩展区后收录的同字区分。
> - 3.因为字库较大，且配置不是很完善，rime的部署过程可能较久，请耐心等待。
