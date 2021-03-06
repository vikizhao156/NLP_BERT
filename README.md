# NLP_BERT
 Finetuning of pretrained Bert

## Datasets

- waimai_10k--- 外卖平台用户评价数据集，2分类；
- ChnSentiCorp---网购评论，2分类
- weibo_senti_100k--- 微博用户评论数据集，2分类；
- weibo2---微博用户评论数据集，4分类；

## Training

利用CPU训练： python finetune_classifier.py --seed 6 --task_name xxx --batch_size 32 --epochs 4 --lr 2e-5 --bert_dataset wiki_cn_cased



可选task_name：CNSA(代表waimai_10k), ChnSentiCorp, weibo(代表weibo_senti_100k), weibo2



## Training Results



| dataset          | best epoch | accuracy | time/per epoch |
| ---------------- | ---------- | -------- | -------------- |
| waimai_10k       | 1          | 0.9092   | 741.49s        |
| ChnSentiCorp     | 3          | 0.9392   | 1220.54s       |
| weibo_senti_100k | 1          | 0.9789   | 11785.73s      |
| weibo2           | 1          | 0.6212   | 36884.11s      |



## Single Sentence analysis

<img src="./inference.png" style="zoom:50%;" />





- 精调后，利用export.py脚本导出params文件，得到json脚本；
- 将json脚本和params权重一起输入inference.ipynb中
- 输入需要判断的句子，输出该句子的情感分类
