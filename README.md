# Chinese-Preprocessing
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
•	THULAC（THU Lexical Analyzer for Chinese）（簡中）清华大学自然语言处理与社会人文计算实验室  
https://github.com/thunlp/THULAC-Python  
•	Jieba（結巴）（簡中、繁中）百度開發  
https://pypi.org/project/jieba/  
https://github.com/fxsjy/jieba  
•	ChineseWordSegmentation(CWS)  

•	CKIP分詞工具（繁中）中央研究院  
http://ckip.iis.sinica.edu.tw:8080/contact/  
•	CoreNLP Stanford (Java) (multi-language)  
https://stanfordnlp.github.io/CoreNLP/human-languages.html  
5)	POS Tagging (詞性標注)  
In Chinese NLP tasks, this step is not necessary, unless for specific tasks such as sentiment analysis.
Most commonly-used tool: THULAC、Stanford CoreNLP(他們都是工具包，有分詞也有標注)
6)	Eliminate not-needed information(去除停用詞)
停用詞一般指對文本特徵沒有任何貢獻的字詞，如：邊點符號、語氣、人稱等。
