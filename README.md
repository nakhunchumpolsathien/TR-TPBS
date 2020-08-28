# TR-TPBS
Currently, the largest dataset for Thai text summarization.

## Download TR-TPBS Dataset
| File | Remark |Size |
|--- |  --- | --- |
|[TR-TPBS](https://docs.google.com/forms/d/e/1FAIpQLSepG5NFdsxbidsoLiXIToW9PCBMqT0WywISMBjtugJiA5nTYw/viewform?usp=sf_link)| contains `title`,	`body`,	`summary`,	`labels`,	`tags` and `url` columns.| 2.05 GB |

### Additional Datasets
These two files are the previous versions of TR-TPBS, before being combined. Be noted that the articles in these files are preprocessed with slightly different filtering-out conditions of that TR-TPBS. The number in the end of datasets’ name indicates the approximate number of articles contained in each dataset. The newest articles contained in these two files are published online up to December 2019.
| File | Remark |Size |
|--- |  --- | --- |
|[Thairath-222k](https://docs.google.com/forms/d/e/1FAIpQLSdy23SSMuUn46sFPqELyn-BoiYvLbg_JG5-5KkwbJiWTV2PaA/viewform?usp=sf_link)| contains `title`,	`body`,	`summary`,	`labels`,	`tags`,	`url` and `date` columns.| 1.72 GB |
|[ThaiPBS-111k](https://docs.google.com/forms/d/e/1FAIpQLSfai0uEXTyFqkqwVzm31fvyqduCZJZy6iVRbXflTS-KLBRPCw/viewform?usp=sf_link)| contains similar columns as Thairath-222k’s except `date`. |0.51 GB| 


## Introduction
TR-TPBS is a medium-size dataset, a multi-purpose NLP benchmark, especially for Thai language. This dataset is crawled from Thairath (TR) and ThaiPBS (TPBS) news websites. The main objectives of this corpus is for Thai text summarization.

This dataset is the largest news dataset for Thai text summarization since the previous studies on this topic, as far as we know, used small size of dataset up to 500 documents. It was understandable because those studies were based on statistic methods not sequence-to-sequence ones. It didn’t require a large text for training. Therefore, our experiment is the very first study that experimented Thai text summarization with deep learning methods on the largest Thai text summarization dataset. We explored this dataset on both extractive and abstractive methods. 

Apart from text summarization objectives, TR-TPBS can be used for several other NLP tasks e.g. headline generation, news classification and keyphrase extraction. 

## Dataset Properties 
See [exploration.ipynb](https://github.com/nakhunchumpolsathien/TR-TPBS/blob/master/exploration.ipynb)

<img src="abs_level.png" width="500" /><img>
## Experiment Settings and Results
We evaluate the performance of the TR-TPBS dataset using existing extractive and abstractive baselines. 
Please refer to [PreSum](https://arxiv.org/pdf/1908.08345.pdf), [BertSum](https://arxiv.org/pdf/1903.10318.pdf), and [ARedSum](https://arxiv.org/pdf/2004.06176.pdf) for more technical information and their implementation codes. 
### Exeriment Settings
Both abstractive and extractive Bert-based (including ARedSum) summarization models are trained on a single GPU (NVIDIA TITAN RTX).
##### Extractive settings
Both BertSumExt and ARedSum models were trained for 100,000 steps with 6000 batch size. The rest of training settings are set identically to [BertSum](https://github.com/nlpyang/BertSum#model-training). It tooks approximately 80 hours to train each extractive model.
##### Abstractive Settings
All abstractive models were trained for 300,000 steps with 1120 batch size for Bert-based models and 1200 for Tranformers-based models. The rest of training settings are set identically to [PreSum](https://github.com/nlpyang/PreSumm#bertabs). It took approximately 150 hours to train each abstractive model.

We used ‘bert-base-multilingual-cased’ version of BERT in this experiment. We strongly suggest to train all Bert-based models on multiple GPUs for shorten the training time and the better results.

### Results
ROUGE F1 of R1 R2 and RL are used to report these experimental results. 

##### TR-TPBS (test set): 

| Models | R1 | R2 | RL |
|--- | --- | --- | --- |
|**Extractive**| | | |
|Oracle |50.89|22.10|50.74|
|Lead-2 |42.98|22.71|42.94|
|ARedSum |40.35|20.38|40.30|
|BertSumExt |44.58|20.26|44.51|
| **Abstractive**| | | |
|BertSumAbs|51.09|26.92|51.04| 
|BertSumExtAbs|53.19|28.19|53.13|

## Collected and Preposessed by 
- [Nakhun Chumpolsathien](https://github.com/nakhunchumpolsathien), School of Computer Science, Beijing Institute of Technology, China
- [Tanachat Arayachutinan](https://github.com/caramelWaffle), School of Computer Science, Beijing Institute of Technology, China

## License 
Thairath-222k and ThaiPBS-111k datasets are licensed under [MIT License](https://github.com/nakhunchumpolsathien/TR-TPBS/blob/master/LICENSE). 
