# The-Zen-of-Python
WordCount
实现一个命令行程序，不妨称之为WordCount。

第一步、实现基本功能

  输入文件名以命令行参数传入。
  统计input.txt中的以下几个指标:

——统计文件的字符数：

  只需要统计Ascii码，汉字不需考虑
  空格，水平制表符，换行符，均算字符
  
——统计文件的单词总数，单词：以英文字母开头，跟上字母数字符号，单词以分隔符分割，不区分大小写。
  
  英文字母： A-Z，a-z
  字母数字符号：A-Z， a-z，0-9
  分割符：空格，非字母数字符号
  例：file123是一个单词， 123file不是一个单词。file，File和FILE是同一个单词
  
——统计文件的有效行数：任何包含非空白字符的行，都需要统计。
——统计文件中各单词的出现次数，最终只输出频率最高的10个。频率相同的单词，优先输出字典序靠前的单词。
——按照字典序输出到文件result.txt：例如，windows95，windows98和windows2000同时出现时，则先输出windows2000

  输出的单词统一为小写格式
  
——输出的格式为

 characters: number
 words: number
 lines: number
 <word1>: number
 <word2>: number
 ...
 
第二步、接口封装

把基本功能里的：

 1.统计字符数
 2.统计单词数
 3.统计最多的10个单词及其词频
这三个功能独立出来，成为一个独立的模块(class library, DLL, 或其它)。这样的话，命令行和GUI的程序都能使用同一份代码。
为了方便起见，我们称之为计算核心"Core模块"，这个模块至少可以在几个地方使用：

 1.命令行测试程序使用
 2.在单元测试框架下使用
 3.与数据可视化部分结合使用
把计算核心在单元测试框架中做过完备的测试后，我们就可以在算法层级保证了这个模块的正确性。
