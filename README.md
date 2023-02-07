# Loss-function
#深度学习中几种 常用的损失函数

##1.交叉熵损失函数 crossentropyloss
    交叉熵（Cross entropy）：在信息论中，基于相同事件测度的两个概率分布p和q，p为‘真实分布’，
    当基于一个“非自然”的概率分布Q进行编码时，在事件集合中唯一标识一个事件需要的平均比特数。
  ![image](images\cross_entropy.png)
  ###交叉熵用于衡量两个概率分布之间的差异性信息。
    信息熵：信息熵用来量化信息，信息熵是用来衡量不确定性的指标，也就是离散随机事件出现的概率，事件越确定，信息熵越小。
  ![image](images\entropy.png)

    信息熵与交叉熵的关系：交叉熵=信息熵+KL散度

2.负对数似然函数 negative log likelihood loss,NLLLoss

    在pytorch中，交叉熵损失函数 = 负对数似然函数 + softmax + log
    交叉熵与似然之间的关系：

3.二元交叉熵损失函数 binary crossentropy loss,BCELoss
 
    二元交叉熵与负对数似然相同，负对数似然为一般形式，二元交叉熵为
  ![image](images\BCELoss.png)
4.KL散度（相对熵） KL divergence，KLDiveLoss

    定义为相同概率空间的两个概率分布p,q之间的相对熵为KL散度，是两个概率分布之间差异的非对称性度量。
   ![image](images\KL_divegence.png)
   
5.余弦相似度 cosine similarity

    yu
