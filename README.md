# Matrix-Factorization-Implicit-Feedback
使用矩阵分解算法处理隐式反馈数据，并进行Top-N推荐。The matrix factorization algorithm is used to process the implicit feedback data and make top-N recommendation.  
数据说明：
training.txt是用户-物品-隐式反馈的交互对，一共有四万多条交互信息。在代码中将其拆分为训练集和验证集。  
test.txt是真实的测试集，只有用户ID，我们最终需要在该测试集上进行Top-N推荐任务。  
result.csv是算法得到的结果，即对test.txt中的用户一一进行Top-10推荐。
实验细节：  
基于矩阵分解或概率矩阵分解算法。在处理该隐式反馈问题时使用了几个小trick。  
1.进行负采样，采样数量=training数据集的大小。  
2.在实际测试时发现令负采样的值等于-1并不好，所以将正反馈的值设置为5，负反馈的值设置为1。可以视为将隐式反馈问题转换为了一个显式（评分预测）反馈问题。  
3.在验证集上获得了0.6以上的precision和recall。  
