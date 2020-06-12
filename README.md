# TR-TPBS
Currently, the Largest Dataset for Thai Text Summarization

## Introduction
> to be updated
## Dataset Construction
> to be updated
## Dataset Properties 
> to be updated

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
##### Thai TR-TPBS ROUGE F1 Results
| Models | R1 | R2 | RL |
|--- | --- | --- | --- |
|**Extractive**| | | |
|Oracle | 26.87 | 7.56 | 26.34 | 
|Lead-2 | 12.91	|4.19|	12.64|
|BerSumExt| 20.65| 6.19 |	20.22 |
| **Abstractive**| | | |
|BertSumAbs|	20.87|	6.19|20.61|
|BertSumExtAbs|	22.05|7.08|21.80|
|TransformerAbs|	18.61	|5.49	|18.45|
> `bert-base-multilingual-uncased`

##### English TR-TPBS ROUGE F1 Results

| Models | R1 | R2 | RL |
|--- | --- | --- | --- |
|**Extractive**| | | |
| Oracle | 	30.30| 	10.74	| 25.66| 
| Lead-2	| 17.89| 	5.81| 	14.96| 
|BertSumExt| 31.68|	10.54	|24.53|
|**Abstactive**| | | |
|BertSumAbs|  |	|	 |
|BertSumExtAbs|	37.68 |	14.89|	28.17 |
|TransformerAbs|	
> `bert-base-uncased`
##### Chinese TR-TPBS ROUGE F1 Results
| Models | R1 | R2 | RL |
|--- | --- | --- | --- |
|**Extractive**| | | |
|Oracle |  21.03	| 5.99	| 20.59| 
|Lead-2 | 8.94	| 2.55	| 8.72| 
|BerSumExt| 17.28	| 4.96	| 16.96| 
|**Abstactive**| | | |
|BertSumAbs| 16.56	| 4.88 |	16.27  |
|BertSumExtAbs|17.44 |	5.21	 | 17.19 |
|TransformerAbs|	|	|	 |
> `bert-base-chinese`
#### Crosslingual Summarization
> To be updated

##### TH -> Eng
##### TH -> Chinese
##### Eng -> Chinese

## Collected and Preposessed by 
- [Nakhun Chumpolsathien](https://github.com/nakhunchumpolsathien), School of Computer Science, Beijing Institute of Technology, China
- [Tanachat Ariyachutinan](https://github.com/caramelWaffle), School of Computer Science, Beijing Institute of Technology, China
## License 
