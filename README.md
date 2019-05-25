# Kaggle-Competitions
kaggle竞赛入坑
## Quora Insincere Questions Classification
问题描述：预测所提问题是否真诚
官方给出的不真诚的问题的特点：
 > 1.偏激言论：过度强调一类人的观点
 >  
 > 2.具有贬低意味的或是具有煽动性的言论：
 >  
 >     意欲宣扬对受保护人群进行歧视或是宣扬教条主义的言论
 >     对特定的人或一群人进行贬低的攻击/侮辱
 >     Based on an outlandish premise about a group of people(没看懂)
 >     贬低一些无法更改和衡量的特征
 >
 > 3.与现实脱节：基于虚假信息，或包含荒谬的假设
 >
 > 4.包含大量与性相关的内容（乱伦、兽交、恋童癖）并不寻求答案
 
 官方提示：给出训练集标注的label可能包含一些噪声，数据集中问题的分布不应被视为代表Quora上提出的问题分布。
这部分是因为采用了最终数据集的采样程序和脱敏（sanitization ，不知道是不是可以这么理解）措施的组合。

## Jigsaw Unintended Bias in Toxicity Classification
