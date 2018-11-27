# Chinese-Preprocessing
## Flowchart
### ***1)	Find Suitable Corpora***  
> For different tasks, there are different corpora that are suitable.  

Most commonly-used corpora (for all tasks):  
&nbsp;&nbsp;&nbsp;&nbsp;•	Wiki dump: 2 billion words  https://dumps.wikimedia.org/  
&nbsp;&nbsp;&nbsp;&nbsp;•	Baidu Encyclopedia: 5422K  http://research.baidu.com/Downloads  
&nbsp;&nbsp;&nbsp;&nbsp;•	People’s Daily News: 31 million   
&nbsp;&nbsp;&nbsp;&nbsp;•	Sogou News: 1226K  http://www.sogou.com/labs/  
&nbsp;&nbsp;&nbsp;&nbsp;•	Weibo: 850K  http://www.nlpir.org/download/weibo.7z  
&nbsp;&nbsp;&nbsp;&nbsp;•	Chinese Gigaword(v5)  https://catalog.ldc.upenn.edu/ldc2011t13  
&nbsp;&nbsp;&nbsp;&nbsp;•	(used a lot in ACL 2017, 2018) OntoNotes, includes text from various genres  https://catalog.ldc.upenn.edu/LDC2013T19  

Corpora used in ACL 2017, 2018 for some specific tasks:  
Sentiment Analysis  
&nbsp;&nbsp;&nbsp;&nbsp;•	HowNet  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=1276017  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;http://www.keenage.com/html/e_index.html  
POS Tagging  
&nbsp;&nbsp;&nbsp;&nbsp;•	Penn Chinese Treebank  https://verbs.colorado.edu/chinese/  
Summarization:  
&nbsp;&nbsp;&nbsp;&nbsp;•	Large Scale Chinese Short Text Summarization Dataset (LCSTS)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://arxiv.org/pdf/1506.05865.pdf  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;http://icrc.hitsz.edu.cn/Article/show/139.html  
Poem Generation  
&nbsp;&nbsp;&nbsp;&nbsp;•	Chinese poem corpus (CPC), Chinese quatrain corpus (CQC) 

### ***2)	Extract Needed Context/Sentences (語料清洗)***  
> Basically, this step is the same as English context preprocessing.   
> Eliminate tags, parse sentences from XML…  

### ***3)	Simplified/Traditional Chinese Conversion***  
> 因為簡轉繁在字上甚至是詞語上都是一對多，所以轉換過後在performance上難免會有一些落差。

Most commonly-used toolkit:  
&nbsp;&nbsp;&nbsp;&nbsp;• OpenCC  https://github.com/BYVoid/OpenCC  
&nbsp;&nbsp;&nbsp;&nbsp;• hanziconv   https://pypi.org/project/hanziconv/  

### ***4)	Tokenize (分詞)***  
> Differ from English, probably the most important part in Chinese context preprocessing.  

<pre>•	Character-based: “我|就|讀|清|大|，|目|前|大|二|。”  
•	Word-based: “我|就讀|清大|，|目前|大二|。” </pre>

Most commonly-used tokenize tool includes:  
&nbsp;&nbsp;&nbsp;&nbsp;•	THULAC (THU Lexical Analyzer for Chinese) （簡中）清华大学自然语言处理与社会人文计算实验室   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/thunlp/THULAC-Python    
&nbsp;&nbsp;&nbsp;&nbsp;•	Jieba（結巴）（簡中、繁中）百度開發    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://pypi.org/project/jieba/  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://github.com/fxsjy/jieba  
&nbsp;&nbsp;&nbsp;&nbsp;•	ChineseWordSegmentation(CWS)  
&nbsp;&nbsp;&nbsp;&nbsp;•	CKIP分詞工具（繁中）中央研究院  http://ckip.iis.sinica.edu.tw:8080/contact/    
&nbsp;&nbsp;&nbsp;&nbsp;•	CoreNLP Stanford (Java) (multi-language)  https://stanfordnlp.github.io/CoreNLP/human-languages.html  

### ***5)	POS Tagging (詞性標注)***  
> In Chinese NLP tasks, this step is not necessary, unless for specific tasks such as sentiment analysis.

Most commonly-used tool: THULAC、Stanford CoreNLP(他們都是工具包，有分詞也有標注)  
&nbsp;&nbsp;&nbsp;&nbsp;•	FudanNLP 中文自然语言处理工具包  https://github.com/FudanNLP/fnlp  

### ***6)	Eliminate not-needed information(去除停用詞)***  
> 停用詞一般指對文本特徵沒有任何貢獻的字詞，如：邊點符號、語氣、人稱等。

## Other Resources  
中文自然語言處理的相關資料  
*非常詳細！整理了很多不同的中文NLP資源*  
(including Chinese Word Segmentation tool, Chinese Corpora, Popular Toolkits)   
https://github.com/crownpku/Awesome-Chinese-NLP   

CA8 Chinese Word Embedding Evaluation tool  
*(ACL2018) a new Chinese word embedding evaluation toolkit*  
(Github裡包含在不同corpora pretrained好的word vectors)  
https://github.com/Embedding/Chinese-Word-Vectors  
http://aclweb.org/anthology/P18-2023  

哈工大ELMo pretrained 各種語言(包含簡、繁中)  
https://github.com/HIT-SCIR/ELMoForManyLangs/blob/master/README.md  

*上面link沒有整理到的*
中华新华字典数据库  
https://github.com/pwxcoo/chinese-xinhua  

Gluonnlp  
https://github.com/dmlc/gluon-nlp  



