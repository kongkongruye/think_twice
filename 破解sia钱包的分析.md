#背景知识
---
看了一遍破解sia钱包的文章[传送门](https://mtlynch.io/stole-siacoins/)，很感兴趣，简单总结下：

##siacoin
sia是一种基于区块链技术的存储共享系统。siacoin则是该系统中的货币，文件存储方利用siacoin可以购买存储，存储提供方则提供存储以获得siacoin。

##钱包助记句
钱包助记符是可以完全控制加密货币钱包的多个英语单词，像一句英文句子，但是句子没有实际意义。


## 编辑距离

> The Levenshtein distance is the number of letters you need to add, delete, or replace to get from one word to another. For example, “cat” and “car” have a Levenshtein distance of 1 because you can get from “cat” to “car” by replacing the “t” with an “r”. The words “cat” and “scar” have a distance of 2 because you have to replace the “t” and prepend an “s”.

## entropy-mnemonics 

[传送门](https://github.com/NebulousLabs/entropy-mnemonics)

#故事
有个用户在网上发布了自己的钱包助记句。并声称自己的助记句是完全正确的，但是就是进入不了钱包。事实上肯定是用户拼写错误，程序不会骗人。然后作者开始了破解之旅。作者首先假设用户只有一个拼写错误，破解有两个思路：

1. 如果钱包助记句中的某个单词不在助记符字典中，那么这个单词很明显就是错误单词。然后，就可以找相近的单词进行尝试，破解很简单很愉快。事实上的情况是 29个助记符都在助记符字典里，这条路走不通了。

2. 暴力破解，寻找所有助记符的编辑距离为1的单词，然后进行替换尝试，直到成功。幸运的是每个助记符的编辑距离为1的单词并不多，可以手工破解。事实上用户拼错的单词是那个有多个编辑距离为1的词的单词。我总结为***编辑距离越近的单词越多，人越容易搞混***。



