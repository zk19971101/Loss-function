#深度学习中几种 常用的损失函数

1.交叉熵损失函数 crossentropyloss

    熵是计算事件所有可能性的信息量的期望。离散随机事件出现的概率越大，信息熵越小。
  
  ![image](https://github.com/zk19971101/Loss-function/blob/main/images/entropy.png?raw=true)
  
    交叉熵（Cross entropy）：在信息论中，基于相同事件测度的两个概率分布p和q，p为‘真实分布’，
    当基于一个“非自然”的概率分布Q进行编码时，在事件集合中唯一标识一个事件需要的平均比特数。
  ![image](https://github.com/zk19971101/Loss-function/blob/main/images/cross_entropy.png?raw=true)
  
  ###交叉熵用于衡量两个概率分布之间的差异性信息。

2.负对数似然函数 negative log likelihood loss,NLLLoss

    在pytorch中，交叉熵损失函数 = 负对数似然函数 + softmax + log
    交叉熵与似然之间的关系：假设模型预测的观测样本qθ（x=i）中的某个样本在训练集中出现的频率记为p(x=i)，给定N个条件独立的样本时，
    则模型在训练集中的似然可以写为：
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/%E4%BA%A4%E5%8F%89%E7%86%B5%E4%B8%8E%E8%B4%9F%E5%AF%B9%E6%95%B0%E4%BC%BC%E7%84%B6.png?raw=true)
   
    可以理解为：采用这个模型对训练集建模的可能性有多大？越大表示模型对观测数据拟合得越好。

3.二元交叉熵损失函数 binary crossentropy loss,BCELoss
 
    二元交叉熵与负对数似然相同，负对数似然为一般形式，二元交叉熵为0-1分布的情况
  ![image](https://github.com/zk19971101/Loss-function/blob/main/images/%E4%BA%A4%E5%8F%89%E7%86%B5%E4%B8%8E%E8%B4%9F%E5%AF%B9%E6%95%B0%E4%BC%BC%E7%84%B6.png?raw=true)
  
4.KL散度（相对熵） KL divergence，KLDiveLoss

    相同概率空间的两个概率分布p,q之间的相对熵为KL散度，定义为基于q分布的编码来编码来自p分布的样本所需要的额外的bit个数。
    衡量两个概率分布之间差异的非对称性度量。
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/KL_divegence.png?raw=true)
   
   通过p分布的编码方式编码来自p分布样本时，其最优编码所需要的bit个数为：
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/%E4%BF%A1%E6%81%AF%E7%86%B5.png?raw=true)
   
   通过q分布的编码方式编码来自p分布样本时，其最优编码所需要的bit个数为：
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/entropy.png?raw=true)
   
   KL(p,q) = 交叉熵 - 信息熵
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/kl%E6%95%A3%E5%BA%A6.png?raw=true)
   
5.余弦相似度 cosine similarity

    用向量空间中两个向量夹角之间的余弦值来衡量向量间差异的大小。相对于欧式距离，更适用与两个向量长度不相同的情况。
   ![image](https://github.com/zk19971101/Loss-function/blob/main/images/cosine_similarity.png?raw=true)
