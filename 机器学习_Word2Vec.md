﻿#机器学习--Word2Vec
##介绍
word2vec是一款将词表征为实数值向量的高效工具，采用的模型有CBOW（ Continuous Bag-Of-Words，即连续的词袋模型）和Skip-Gram 两种。

word2vec代码链接为：https://code.google.com/p/word2vec/<br>
word2vec通过训练，可以把对文本内容的处理简化为K维向量空间中的向量运算，而向量空间上的相似度可以用来表示文本语义上的相似度。因此，word2vec输出的词向量可以被用来做很多NLP相关的工作，比如聚类、找同义词、词性分析等等。 

word2vec只是一个简单三层神经网络。

##One-hot Representation
NLP相关任务中最常见的第一步是创建一个词表库并把每个词顺序编号。这
实际就是词表示方法中的 One-hot Representation，这种方法把每个词顺序编号,
每个词就是一个很长的向量，向量的维度等于词表大小，只有对应位置上的数字
为1，其他都为 0。当然在实际应用中，一般采用稀疏编码存储，主要采用词的
编号。

这种表示方法一个最大的问题是任意两个词之间都是孤立的，无法捕捉词与词之间的相似度，就算是近义
词也无法从词向量中看出任何关系。此外这种表示方法还容易发生维数灾难，尤其是在Deep Learning相关的一些应用中。


##Distributed representation
基本思想是通过训练将每个词映射成K维实数向量（K一般为模型中的超参数），通过词之间的距离（比如cosine相似度、欧氏距离等）来判断它们之间的语义相似度。而word2vec使用的就是这种Distributed representation的词向量表示方式。

其基本想法是直接用一个普通的向量表示一个词，这种向量一般长成这个样子：[0.792, −0.177, −0.107, 0.109, −0.542, ...]，也就是普通的向量表示形式。维度以 50维和100维比较常见。当然一个词怎么表示成这么样的一个向量是要经过一番训练的，训练方法较多，word2vec是其中一种。

由于是用向量表示，而且用较好的训练算法得到的词向量的向量一般是有空间上的意义的，也就是说，将所有这些向量放在一起形成一个词向量空间，而每一向量则为该空间中的一个点，在这个空间上的词向量之间的距离度量也可以表示对应的两个词之间的“距离”。所谓两个词之间的“距离”，就是这两个词之间的语法，语义之间的相似性。





神经网络的隐含层中设置节点个数？
点图的软件。
实现一个简单的ranknet。

参考：<br>
1《Deep Learning 实战之 word2vec》(网易有道团队)<br>
2 [深度学习word2vec笔记之基础篇](http://blog.csdn.net/mytestmy/article/details/26961315)<br>


--------------------------------
--------------------------------
######（转载本站文章请注明作者和出处 <a href="https://github.com/MangoLiu">MangoLiu</a> ，请勿用于任何商业用途）

