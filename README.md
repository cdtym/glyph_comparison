# 两岸三地常用字Unicode对比

> 注：本文涉及对不同地区的称呼，将在名称上尽量与《新华社发布新闻报道禁用词和慎用词（2019年7月修订版）》所载规范对齐，使用内地、香港、澳门、台湾来简称不同地区。本文内容的主题在于语言文字相关，涉政类反馈请自行保留。

# 〇、背景

当前使用汉字的不同地区分别整理了各自的汉字使用规范，规范间互有差异，再加之Unicode中部分贯彻的“原字集分离原则”，使得在计算机上将汉字在各地规范之间正确转化面临许多困难，实际使用情况十分混乱。混乱一方面体现在古籍整理上，另一方面体现在“简繁转换”上。

古籍整理的例子如[中华书局《三国志》字形问题](https://www.zhihu.com/question/20726972)，链接中提及了中华书局《三国志》中的新旧字形共存问题；与此同时Unicode中又同时收录了“説說”、“吴吳”，但是误的繁体“誤”仅收录了一个码位，至于“誤”的右边显示“吴”还是“吳”，有赖于不同字体的实现。再有就是古籍文献数码化，所使用字形上与古籍影印上的细微差别是重灾区。

常见的“简繁转换”问题，一方面有“一简转多繁”时出现的错误情况，如“头发”未能正确转换成“頭髮”而被错误的转换成“頭發”；另一方面是字形与地区规范的差别，如内地的繁体文本一以“爲”为正字，而不少直接遵循港台地区的“简繁转换”系统会转为“為”。二者在应用上虽然都正确，大多数用户也不会对此感知，但是计算机内存储上的差异是真实存在的。

现有的知乎帖子、bilibili上的地区标准字形比较视频里，时常会举出很多有差别的例子。但是通过这些例子我们只能知道地区的标准之间存在差异，而不能够知道不同地区标准之间一共会有哪些差异点，无法做到尽数罗列。

# 一、本文内容

比较内地、香港、台湾三个地区的汉字标准体现在Unicode上的差异。在Excel中罗列出差同一个字在三地的规范下分别应该对应于那个Unicide字符，一方面便于统计，另一方面Excel中的文字可复制/导出，便于后续据此导出输入法的规范转换对应表，作为不同地区规范在计算机上的实现。本文给出了这个excel文件的制作方法及说明。

三地所参考的标准及资料如下：

1. 内地最新以《通用规范汉字表》（2013）规范所使用汉字的正异关系、新旧字形、简繁关系，共计8105字
   1. 该表使用新字形
   2. 其他相关的材料包括
      1. 《〈通用规范汉字表〉解读》
      2. 《通用规范汉字字典》http://www.unicode.org/L2/L2019/19160-adding-ktghz-2013.pdf
2. 香港特区以香港教育署语文教育学院中文系制定的《常用字字形表》（2007年重排本）作为参考，共计4762字。
3. 台湾地区参考《常用国字标准字体表》，共计4808字。

# 二、处理原则

1. 从内地标准出发。身边可以参考的资料较多，后期也容易处理难点较多的“简转繁”问题。
2. 限制处理范围。精力有限，本文只先处理三个规范8105/4762/4808字之间的关系，同时也便于计数。
3. 比较对象：内地繁体字、《常用字字形表》、《常用国字标准字体表》
4. 内地繁体字标准使用《通规》附表一《规范字与繁体字、异体字对照表》所记录的繁体字。原因见下
   1. 目前内地大部分时效较新的简繁对照资料贯彻了该附表，包括《新华字典》第12版、《现代汉语词典》第7版、《现代汉语规范词典》第4版、《海峡两岸汉字对照表》
   2. 该表使用了内地规范的新字形。正异关系处理上，港台差别较小。使用该附表便于体现出Unicode中通过码位区分的两岸三地字形差异，同时也体现出内地在正异处理上所发生的变化。
   3. 现代汉语繁体文本的选字标准尚无明确指导。先期以附表一作为本表的比较对象。后待现代汉语繁体文本的字形标准明确后（例如可能的推荐标准《古籍印刷通用字规范字形表》），再通过附表一与新标准的映射关系来得出新标准与港台两地规范的对照关系。内地已有繁体中文印刷品所遵从的规范如下
      1. 《通规》附表一《规范字与繁体字、异体字对照表》。用“爲”不用“為”、用“録”不用“錄”、用“群”不用“羣”、“誤”右从“吴”不从“吳”、用“并且”不用“並且”、用“衹有”不用“祗有”、用“説”不用“說”
      2. 《治国理政》繁体中文卷。用“爲”不用“為”、用“録”不用“錄”、用“羣”不用“群”、“誤”右从“吳”不从“吴”，用“並且”不用“并且”
      3. 王力《古代汉语》，用“爲”不用“為”、用“祗有”不用“衹有”、用“説”不用“說”
      4. 《辭源》第3版。用“箇”不用“個”
      5. 《古籍印刷通用字规范字形表》用“爲”不用“為”、用“錄”用“録””、用“群”不用“羣”
      6. 《新华字典》1954年版（部首排列）。新华字典在建国后文字改革前发行过两版，一版是1953年音序排列，一版是1954年部首排列版，这两版由人民教育出版社发行。而后转由商务印书馆1957年发行第一版时已经带有部分文字整理的成果了。
      7. 《国语辞典》影印版、《汉语词典》简本。这两版影印了1947年的《国语辞典》，用“錄”不用“録””、用“溫”不用“温”
      8. 《国语词典》（重排本）。这是1947年《国语辞典》使用新字形排版后的版本，用“緑”不用“綠””、用“溫”不用“温”
5. 考虑现实的操作效率，顾及含义的条件下做数量对比，但不在表格里明确写出字义。字义考虑未来做长期修订。
6. 不严格界定字形、异体的差别，只列举出不同项。内地新旧字形的定义，内地新字形的定义是明确的，即《印刷通用字汉字字形表》、《通用规范汉字表》一脉相承的字形。旧字形或者传承字形的定义是相对于新字形而言的，以下给出目前所有能想到的、关于旧字形的描述性材料：
   1. 新华字典、现代汉语词典、汉语大字典所附《新旧字形对照表》
   2. 古籍印刷规范字通用字形表
   3. 国语辞典、新华字典早期版本、其他文字整理前中文出版物（如中文版《工程控制论》）的影印本
   4. 一点字坊的传承字形整理文件
   5. 书同文网的新旧字形对照页面
   6. https://www.bilibili.com/read/mobile?id=4029851

以及这个链接提到的所有文献

# 三、《字数统计及比对表》说明

下面说明表格的制作过程，以及excel文件内各个子表格的含义说明

- “通规对一异表的调整原则”表中是对《〈通用规范汉字表〉解读》中异体字处理部分的摘抄
- 关于附录一规范下，繁体字集字数的统计。
  - 8105个规范字映射成8197字规范字繁体字集
    - 5559字，无对应繁体，其中：
      - 7个规范字，同时也作为其他规范字的繁体字：瞭乾麽夥剋徵藉
    - 2450字，一简对一繁，其中：
      - 5个规范字，其繁体字与其他规范字的繁体字相同：么苹𬞟𫫇锺
    - 96个规范字，一简对多繁，映射到198个繁体字上
- 在进行比对时，8105个规范字分为三部分进行考察：
  - 5552字=5559-7，此5552个字无繁体字对应，该部分下文简称作“无繁体集”
  - 2445字=2450-5，此2445字有一个繁体字对应，该部分下文简称作“一对一集”
  - 108字=96+7+5，包含所有一对多、多对一的情况，该部分下文简称作“复杂对应集”
- 港台原表
  - 港台地区常用字规范的数据，数据来源《CJKV Information Processing》附录
- 《通规》繁体字集8197字，港规《常用字字形表》4762字，台规《常用国字标准字体表》4808字，三个字集求交集，有共同的4442字
  - 就《通规》而言，共同的4442字中包含了无繁体集2946字，一对一集1332字，复杂对应集164字
- 三个字表在4442字之外的字，放在“差量对比表”中进行比较。相同的字放在一行，分别写出规范字及其在字表中的标号、港台地区所使用的字符。各列以颜色标识所属的地区标准，红色表示内地，黄色表示香港地区，蓝色表示台湾地区。表格左侧还使用excel的字数统计功能统计了表格内录入的字数，确保与计算出来的字数相合
- “差量对比表差异部分一”表格将三地对比有差异的内容进行了挑选，并将所有需要考察的范围限制在“差量对比表差异部分二”。
- 经过手动整理后的对比结果在“差量对比结果”表中，共有330组存在差异、需要考察的字。
  - 关于港台用法的参考，限于手上资料有限，主要参考香港《中华新字典》、《海峡两岸汉字对照表》
  - 该表侧重数量上的统计，对于字义及用法上的细致校对仍需未来的工作量。

# 四、未来计划

1. 持续校对订正

2. 新购买的《汉字字形对比字典》正在路上，待到手后结合《海峡两岸汉字对照表》对比参考

3. 对比《通用规范汉字表》与《古籍印刷通用字规范字形表》，进而得出《古籍印刷通用字规范字形表》与港台两地规范的对比情况。目前在知乎上已经看到有两位仁兄在做类似的工作，可以参考。



p.s. 欢迎电邮cdtym_vc@yeah.net 就相关问题进行讨论，也期待同仁指教，谢谢！
