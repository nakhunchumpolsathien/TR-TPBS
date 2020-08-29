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

## Data examples

body | labels | summary | tags | title | url
-----|--------|---------|------|-------|-----
สำนักข่าวต่างประเทศรายงานวันที่ 28 ม.ค. ว่า ฮูลิโอ บาปติสตา อดีตหัวหอกตีนระเบิดของ ราชันชุดขาว เรอัล มาดริด ชี้ว่าต้นสังกัดของเขาโชคดีเหลือเกินที่ได้เซ็นสัญญากับ ลูคัส ซิลวา เพลย์เมกเกอร์ ดาวโรจน์จาก ครูไซโร มาร่วมทีมบาปติสตา เคยลงเล่นกับ เจ้าหนูลูคัส ที่สโมสรครูไซโร มาแล้วเมื่อฤดูกาลที่ผ่านมาโดยเจ้าตัวมั่นใจว่า การเซ็นสัญญา ลูคัส ซิลวา ของอดีตต้นสังกัดของเขา จะเป็นการเซ็นสัญญาอันยอดเยี่ยมอย่างแน่นอนเรอัล มาดริด โชคดีที่เซ็นสัญญา ลูคัส ซิลวา นะ พวกเขาต้องคิดถึงแผนการระยะยาวเพราะเขาจะกลายเป็นนักเตะที่มีความสำคัญมากลูคัส ซิลวา เป็นคนที่เล่นในยุโรปได้เลยเพราะเขามีสไตล์การเล่นแบบยุโรปอยู่แล้ว แต่เขายังไม่เตรียมพร้อมและต้องปรับตัวให้ชินที่เรอัล มาดริดในฐานะนักเตะเขาเป็นออแกไนเซอร์ เมื่อเขาไม่ได้เล่นในทีมให้สังเกตตอนที่เขาไม่อยู่เพราะเขามีความก้าวหน้าเกินกว่าคนที่อายุเท่าเขา เขามีความคล้ายคลึงกับ ซาบี อลอนโซ ในเรื่องของคุณภาพเลยนะ อีกทั้งเขายังเป็นคนที่ยิงแบบบ้าพลังมากซึ่งทำให้เขาอันตรายยิ่งกว่าเดิมด้วย บาปติสตาเผย | *n/a* | ฮูลิโอ บาปติสตา อดีตแข้งตีนระเบิดของ ราชันชุดขาว เรอัล มาดริด ชี้ว่าต้นสังกัดเก่าโชคดีที่ เซ็นสัญญา ลูคัส ซิลวา กองกลางพรสวรรค์สูงมาร่วมทีม | ลาลีกา,เรอัล มาดริด,ฮูลิโอ บาปติสตา,ลูคัส ซิลวา,ข่าวกีฬา | 'บาปติสตา' ชี้ 'ราชัน' โชคดีกระชาก 'ลูคัส' มาร่วมทีมได้ | https://www.thairath.co.th/content/477519
สมเด็จพระเจ้าลูกเธอ เจ้าฟ้าสิริวัณณวรี นารีรัตนราช กัญญา ผู้อำนวยการฝ่ายสร้างสรรค์แห่งแบรนด์ SIRIVANNAVARI ทรงพร้อมจัดแฟชั่นโชว์ เผยโฉมคอลเลกชันทรงออกแบบ AUTUMN/ WINTER 2019-2020 เต็มรูปแบบ วันที่ 26 ต.ค. เวลา 19.00 น. ณ ห้องบอลรูม โรงแรมพาร์ค ไฮแอท กรุงเทพฯสุขสันต์ เจียมใจสว่างฤกษ์ ปลื้มใจ หายเหนื่อย เพราะนำซีพีเอฟ ทำความดีเพื่อสังคมมาตลอด จนได้รับเลือกเป็น บุคคล ตัวอย่าง ภาคธุรกิจ 2019 จากมูลนิธิสภาวิทยาศาสตร์และเทคโนโลยีแห่งประเทศไทยอุบอยู่นานเพื่อเตรียมบิ๊กโปรเจกต์ฉลองยิ่งใหญ่ 50 ปี พลตรี พัชร รัตตกุล เผยเซอร์ไพรส์กับการยกเกาะมาไว้กลางกรุง จัดเฟสติวัลสุดครื้น-เครงบันเทิงครบรส ธีม เกาะสวาทหาดทิพย์ เทด-กาล-งาน-หนุก-หนัด สไตล์โค้ก-หาดทิพย์--แถลงข่าว 21 ต.ค. เวลา 18.00 น. ณ เซ็นทรัลคอร์ท (โถงลิฟต์แก้ว) เซ็นทรัลเวิลด์ไปชมแฟชั่นวีกที่มิลาน และปารีส ธันยลักษณ์ พรหมมณี ใส่ชุดผ้าไหมไทยดีไซน์และสั่งตัดพิเศษ สวยหยดจนฝรั่งตะลึง รุมถามว่าผ้าอะไร คุณธันย่า จึงถือโอกาสช่วยชาติ โดยแจกอินสตาแกรม tanyamaithai ท่านย่าไหมไทยณัฐธีรา จิราธิวัฒน์ บุญศรี เอาใจคนชอบแต่งบ้าน เปิด Living House คอนเซปต์ใหม่ ที่ชั้น 7 เซน พร้อมบริการและโซน ใหม่ๆ ทั้ง Co-Living สินค้าตกแต่ง บ้าน และ Co-Eating อาหารระดับ Michelin Guideลูกสาวคนเดียวแต่งงานไปนานแล้ว พงษ์ชัย–วันทนา อมตานนท์ รอลุ้นลูกชาย 2 หนุ่มมาหลายปี เพราะมีแต่สาวรุมตอม จนพ่อแม่ใจหายใจคว่ำ จนได้ข่าวดีว่า ปีหน้าทั้งคู่จะจูงสาวนิสัยดี แต่งงานติดๆกัน.โสมชบา | *n/a* | สุขสันต์ เจียมใจสว่างฤกษ์ ปลื้มใจ หายเหนื่อย เพราะนำซีพีเอฟ ทำความดีเพื่อสังคมมาตลอด จนได้รับเลือกเป็น บุคคล ตัวอย่าง ภาคธุรกิจ 2019 | โสมชบาจ๊ะจ๋า,โสมชบา,สุขสันต์ เจียมใจสว่างฤกษ์ | โสมชบาจ๊ะจ๋า 21/10/62 | https://www.thairath.co.th/lifestyle/woman/hisoceleb/1686341
สืบเนื่องจากกรณีที่มีประชาชนส่วนหนึ่ง เดินทางมาร้องเรียน และยื่นข้อเสนอต่อผู้บริหารองค์การกระจายเสียงและแพร่ภาพสาธารณะแห่งประเทศไทย หรือไทยพีบีเอสให้ระงับการออกอากาศรายการตอบโจทย์ประเทศไทย ตอน สถาบันพระมหากษัตริย์ ภายใต้รัฐธรรมนูญ ตอนที่ 5 ซึ่งเป็นตอนสุดท้าย ที่มีกำหนดออกอากาศในวันศุกร์ที่ 15 มีนาคม 2556ทั้งนี้รายการตอบโจทย์ประเทศไทยที่ออกอากาศในช่วงสัปดาห์ที่ผ่านมา ได้นำเสนอมุมมองที่หลากหลาย ในเรื่องการปรองดอง การนิรโทษกรรม ซึ่งในหลายกรณีคาบเกี่ยวกับความผิดตามประมวลกฎหมายอาญามาตรา 112 ซึ่งกำลังเป็นประเด็นที่อยู่ในกระแสข่าว ทั้งในสื่อกระแสหลัก และในสื่อสังคมออนไลน์โดยทางรายการได้เชิญแขกรับเชิญหลายฝ่าย นับจากนายสุรเกียรติเสถียรไทย อดีตรัฐมนตรีว่าการกระทรวงการต่างประเทศ ผู้เคยถวายงานรับใช้ใกล้ชิดพระราชวงศ์ ในฐานะประธานจัดงานครองสิริราชสมบัติ 60 ปี ซึ่งเป็นแขกรับเชิญในวันจันทร์ที่11 มีนาคม 2556 ตามมาด้วยนายสมศักดิ์ เจียมธีรสกุล อาจารย์ภาควิชาประวัติศาสตร์ คณะศิลปศาสตร์มหาวิทยาลัยธรรมศาสตร์ ในวันอังคารที่ 12 มีนาคม 2556 ซึ่งได้ก่อให้เกิดเสียงวิพากษ์วิจารณ์อย่างกว้างขวาง ในวันพุธที่ 13 มีนาคม 2556 ทางรายการได้เชิญ พล.ต.อ.วสิษฐ เดชกุญชร อดีตหัวหน้านายตำรวจประจำราชสำนัก มานำเสนอมุมมองต่อข้อวิพากษ์ของนายสมศักดิ์ โดยเปิดโอกาสให้ผู้ชมเป็นคนตัดสินแต่ช่วงเวลาที่ก่อให้เกิดข้อวิพากษ์มากที่สุด เป็นเนื้อหารายการในวันพฤหัสบดีที่ 14 มีนาคม 2556 ที่มีการดีเบตระหว่างนายสมศักดิ์ เจียมธีรสกุล กับนายสุลักษณ์ ศิวรักษ์ถึงแม้ทางฝ่ายหลังจะประกาศตัวเป็นคนรักเจ้า ที่ต้องการปกปักรักษาให้มีสถาบันพระมหากษัตริย์อยู่ในประเทศไทยอย่างเปิดเผย แต่ก็ยังถูกตั้งคำถามจากผู้ชมบางส่วนถึงการวิจารณ์อย่างตรงไปตรงมาของนายสุลักษณ์ ศิวรักษ์ ซึ่งผู้ชมหลายฝ่ายอาจจะกังขาต่อท่าทีและวิธีการนำเสนอ ที่เชื่อมโยงไปถึงประเด็นการแก้ไขกฎหมายอาญา มาตรา112 ซึ่งเป็นประเด็นที่อ่อนไหวและถูกถามถึงวัตถุประสงค์ของการนำเสนอรายการจากการแสดงความคิดเห็นของกลุ่มประชาชนที่เดินทางมาประท้วงการนำเสนอรายการดังกล่าวไทยพีบีเอส มิได้เพิกเฉย โดยนำเรื่องเข้าหารือเป็นวาระเร่งด่วนในคณะกรรมการนโยบายพร้อมทั้งเรียกประชุมกองบรรณาธิการข่าวเพื่อพิจารณาเนื้อหาของเทปรายการและตัดสินใจ โดยการประชุมดังกล่าว ดำเนินไปโดยอิสระตามจริยธรรมและวิชาชีพ โดยมิได้รับการร้องขอหรือถูกบังคับจากหน่วยงานหรือสถาบันใดทั้งนี้ การประชุมพิจารณาเทปรายการ พบว่า มีเนื้อหาที่สมดุลในการแสดงความคิดเห็น แต่ในการประเมินสถานการณ์ เวลาประมาณ 21 นาฬิกา วันที่ 15 มีนาคม 2556 พบว่า อาจมีการขยายความขัดแย้งที่รุนแรงขึ้น คณะผู้บริหารพิจารณาภายใต้หลักการแสดงความรับผิดชอบต่อสังคม องค์การฯจะต้องไม่สร้างปัจจัยความขัดแย้งเพิ่มเติม หรือเป็นคู่ขัดแย้งเอง นำมาสู่การตัดสินใจพิจารณาทบทวนการนำเสนอประเด็นอ่อนไหวอย่างรอบคอบอีกครั้งนายสมชัย สุวรรณบรรณ ผู้อำนวยการไทยพีบีเอส จึงได้มีข้อเสนอให้นำเรื่องร้องเรียนของกลุ่มประชาชนดังกล่าว เข้าสู่การพิจารณาของอนุกรรมการรับและพิจารณาเรื่องร้องเรียนจากประชาชน ตามมาตรา 46 พ.ร.บ. องค์การกระจายเสียงและแพร่ภาพสาธารณะแห่งประเทศไทย พ.ศ. 2551 | สังคม | การตัดสินใจระงับออกอากาศเทปรายการตอบโจทย์ ตอน สถาบันพระมหากษัตริย์ ภายใต้รัฐธรรมนูญ เมื่อคืนนี้ ซึ่งเป็นตอนที่ 5 หลังจากมีประชาชนจำนวนหนึ่งมาที่ไทยพีบีเอส เพื่อขอให้ระงับการออกอากาศ ทำให้ไทยพีบีเอสถูกวิพากษ์วิจารณ์ถึงความมีอิสระในการนำเสนอข่าว และเมื่อคืนที่ผ่านมา ฝ่ายบริหารได้มีคำชี้แจงว่า การตัดสินใจครั้งนี้ไม่ได้ถูกร้องขอจากหน่วยงานหรือสถาบันใดๆ | พระมหากษัตริย์,รัฐธรรมนูญ,รายการตอบโจทย์,ไทยพีบีเอส | "ไทยพีบีเอส" แจงเหตุระงับ "ตอบโจทย์"  ไม่ได้ถูกร้องขอจากหน่วยงานใด | https://news.thaipbs.or.th/content/154643
