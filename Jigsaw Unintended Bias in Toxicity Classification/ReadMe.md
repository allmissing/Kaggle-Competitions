# Jigsaw Unintended Bias in Toxicity Classification

## Description
1.目的：检测toxic comments并减小unintended model bias  
2.toxicity的定义：toxicity is defined as anything rude, disrespectful（不恭） or otherwise likely to make someone leave a discussion  
3.unintended model bias的解释：Conversation AI team 在建立模型时发现模型会把一些含有本身为正常评论，但含有toxic comments高频词汇（身份词汇，如gay）的评论预测为toxic comments，会出现这种现象的原因是因为数据源中，含有这类词汇的数据，toxic comments要远远多于正常评论，用这种不平衡数据训练的模型会将偏差反映到用户身上。

## 评价指标

### Bias AUCs
将数据集依据每个identity划分为三个特定子集，每个子集描述unintended bias的一个方面。
##### 1.Subgroup AUC
将数据集提及某一种身份的划分为一组，这个指标说明对特定身份的预测能力差。  
身份包括：identity_columns = ['male', 'female', 'homosexual_gay_or_lesbian', 'christian', 'jewish', 'muslim', 'black', 'white', 'psychiatric_or_mental_illness']  
##### 2.BPSN (Background Positive, Subgroup Negative) AUC
将测试集限制为提及身份的无毒示例和不具有该身份的有毒示例。
该指标中的低值意味着该模型混淆了无毒的例子，这些例子提到了与不具有毒性的例子的同一性，可能意味着该模型预测的毒性得分高于提及该身份的无毒例子的毒性得分。
##### 3.BNSP (Background Negative, Subgroup Positive) AUC
在这里，我们将测试集限制为提及身份的有毒示例和不具有该身份的无毒示例。
这里的低值意味着该模型混淆了有毒的例子，这些例子提到了不具有该身份的非毒性实例，可能意味着该模型预测毒性得分低于提及该身份的有毒例子。
