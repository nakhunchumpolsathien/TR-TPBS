# TR-TPBS
Currently, the Largest Dataset for Thai Text Summarization

## Download TR-TPBS Dataset
**To be updated. For now, none of these file is released.** <br/>
Click on file name to download. All files are in .csv format.
| File | Remark |
|--- |  --- |
|[Original TR-TPBS]()| It contains full elements of TH-TRTPBS. |
|[EN-TRTPBS]()|This file contains `en_body`, `en_summary`, `url`.|
|[ZH-TRTPBS]()|This file contains `zh_body`, `zh_summary`, `url`.|
|[Test Sets]()|This folder contains 2 files. </n> These files are the test sets used in [cross lingual summarization experiment](#crosslingual-summarization) |

Use column `url` provided in ZH and EN TRTPBS files as the index to get its original Thai text in Original TR-TPBS.
### Additional Dataset
These two files are the previous versions of TR-TPBS, before being combined. Be noted that the articles in these files are preprocessed with slightly different filtering-out conditions of that TR-TPBS. The number in the end of datasets’ name indicates the approximate number of articles contained in each dataset. The newest articles contained in these two files are published online up to December 2019.
| File | Remark |
|--- |  --- |
|[Thairath-228k]()| contains `title`,	`body`,	`summary`,	`type`,	`tags`,	`url` and `date` columns.|
|[ThaiPBS-111k]()| contains similar columns as Thairath-228k’s. | 


## Introduction
TR-TPBS is a medium-size dataset, a multi-purpose NLP benchmark, especially for Thai language. This dataset is crawled from Thairath (TR) and ThaiPBS (TPBS) news websites. The main objectives of this corpus are for Thai text summarization and cross-lingual Thai text summarization. The article texts and summary texts are translated to English and Chinese using Google & Amazon translation services. Therefore, there are three language versions of this dataset: TH-TRTPBS, ENG-TRTPBS and ZH-TRTPBS. The TH version is the original crawled Thai text. ENG and ZH stand for English and simplified Chinese respectively.

This dataset is the largest news dataset for Thai text summarization since the previous studies on this topic, as far as we know, used small size of dataset up to 500 documents. It was understandable, sine those studies were based on statistic methods not deep learning ones. It didn’t require a large text for training. Therefore, our experiment is the very first study that experimented Thai text summarization with deep learning methods on the largest Thai text summarization dataset. We explored this dataet on both extractive and abstractive methods. 

Apart from text summarization objectives, TR-TPBS can be used for several other NLP tasks e.g. news classification and keyphrase extraction. 

## Dataset Properties 
> to be updated


<img src="abs_level.png" width="500" /><img>
## Experiment Settings and Results
We evaluate the performance of the TR-TPBS dataset using existing extractive and abstractive baselines. 
Please refer to [PreSum](https://arxiv.org/pdf/1908.08345.pdf), also [BertSum](https://arxiv.org/pdf/1903.10318.pdf) for more technical information and their implementation codes. 
### Exeriment Settings
#### Monolingual Summarization Settings
##### Extractive settings
All BetSumExt models were trained for 100,000 steps on a GPU (NVIDIA TITAN RTX) with 6000 batch size. The rest of training settings are set identically to [BertSum](https://github.com/nlpyang/BertSum#model-training). It tooks approximately 80 hours to train each extractive model.
##### Abstractive Settings
All abstractive models were trained for 300,000 steps on a GPU (NVIDIA TITAN RTX) with 1120 batch size for Bert-based models and 1200 for Tranformers-based models. The rest of training settings are set identically to [PreSum](https://github.com/nlpyang/PreSumm#bertabs). It took approximately 150 hours to train each abstractive model.

More importantly, we used different versions of Bert for each language version of the dataset. The used Bert-based versions are stated below the result tables of each language.<br />
We strongly suggest to train all Bert-based models on multiple GUPs for shorten the training time and the better results. 

#### CrosslingualSummarization Settings

### Results
#### Monolingual Summarization

##### TH -> Eng
##### TH -> Chinese
##### Eng -> Chinese

## Collected and Preposessed by 
- [Nakhun Chumpolsathien](https://github.com/nakhunchumpolsathien), School of Computer Science, Beijing Institute of Technology, China
- [Tanachat Ariyachutinan](https://github.com/caramelWaffle), School of Computer Science, Beijing Institute of Technology, China
## License 
