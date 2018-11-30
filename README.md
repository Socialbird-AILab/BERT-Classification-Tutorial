# BERT-Classification-Tutorial
标注数据，可以说是AI模型训练里最艰巨的一项工作了。自然语言处理的数据标注更是需要投入大量人力。相对计算机视觉的图像标注，文本的标注通常没有准确的标准答案，对句子理解也是因人而异，让这项工作更是难上加难。
但是！谷歌最近发布的BERT大大的解决了这个问题！根据我们的实验，BERT在文本多分类的任务中，能在极小的数据下，带来显著的分类准确率提升。并且，实验主要对比的是仅仅5个月前发布的State of the art 语言模型迁移学习模型 - ULMFiT (https://arxiv.org/abs/1801.06146)， 结果有着明显的提升。

![alt text](https://github.com/Socialbird-AILab/BERT-Classification-Tutorial/blob/master/pictures/Results.png)

从上图我们可以看出，在不同的数据集中，BERT都有非常出色的表现。我们用的实验数据分为1000、 6700 和 12000 条，并且各自包含了测试数据，训练测试分割为80%-20%。数据集从多个网页来源获得，并经过了一系列的分类映射。但Noisy数据集带有较为显著的噪音，抽样统计显示噪音比例在20%左右。实验对比了几个模型，从最基础的卷积网络作为Baseline，到卷积网络加上传统的词向量Glove embedding， 然后是ULMFiT和BERT。


# 1.运行环境
Tensorflow版本为Windows 1.10.0 GPU，具体安装教程可以参考此链接https://www.tensorflow.org/install/pip?lang=python3。Anaconda 版本为1.9.2 。

# 2.硬件配置
实验用的机器显卡为NVIDIA GeoForce GTX 1080 Ti，BERT base 模型占用显存约为9.5G。

# 3.下载模型
所有的运行环境设置好后，在这里可以下载到我们实验用的BERT base: https://storage.googleapis.com/bert_models/2018_10_18/uncased_L-12_H-768_A-12.zip
 下载完后，放在 BERT_BASE_DIR 中。

# 4.输入数据准备
我们需要将文本数据分为三部分:
"	Train: train.tsv
"	Evaluate: dev.tsv
"	Test: test.tsv
下面可以看到每个文件的格式，非常简单，一列为需要做分类的文本数据，另一列则是对应的Label。

data文件夹中包含了1000条10分类的样本数据，并分为训练和测试集。

![alt text](https://github.com/Socialbird-AILab/BERT-Classification-Tutorial/blob/master/pictures/Our%20data%20example.png)

# 5.实现细节
运行run_classifier.py实现1000条10分类样本数据的文本分类任务。具体实现细节请参考教程:https://mp.weixin.qq.com/s/XmeDjHSFI0UsQmKeOgwnyA


