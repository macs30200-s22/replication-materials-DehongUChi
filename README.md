[![DOI](https://zenodo.org/badge/484103277.svg)](https://zenodo.org/badge/latestdoi/484103277)

**Examining the Predictive Power of Google Trends Data for Economic Indicators**  
Dehong Lu   

**Abstract**  
This study examines the predictive power of the search volume intensity of Google Search terms (i.e., Google Trends data) for a number of economic indicators including unemployment rate, labor force participation rate, Consumer Price Index and its variants, Gross Domestic Products, S&P 500 returns, as well as their modified versions by taking the differences, change in change, or volatility. Our study is motivated by the mixed results and limited scope of the previous studies, which demonstrated the need for further investigations and assessments. The initial analysis of the data seemed promising as illustrated by the high correlations between certain Google Trends search terms and economic indicators. Our results show that using the search volume intensity of single Google Trends topic under certain categories yields better results than using search volume intensity of all top 50 Google Search terms ranked by relevance. In addition, predictions for Consumer Price Index and Labor Force Participation Rate related metrics yielded more satisfactory results than other economic indicators. For other economic indicators, although the performances of most of the models improved when using Google Trends data as the predictors, the resulting R-squared is not significant enough, therefore the models for predicting these economic indicators can not serve as meaningful predictors for the purposes of policymaking or academic research in real life. 
   

You can find all necessary codes in the file run.ipynb.  
Run all of the codes in the file run.ipynb by sequence if you would like to build all of the models.  
However, since building random forest models takes a long time, it is suggested to only build models for economic indicators and data type that are of your interest. 

All of the data are located in the repository

Some of the graphs are created using Excel, open results graph.xlsx to access all of the graphs, click on the tab in the bottom of the excel to switch between graphs of models using the top 50 search terms and graphs of models using search topics. 

All of the codes are written in python 3.8.5. 
The version number of all required pakcages: 
Pandas: 1.2.4
Numpy: 1.20.1
Sklearn: 1.0.2
Seaborn: 0.11.1
matplotlib: 3.3.4

How to Cite:

```
@software{DehongUChi,
  author       = {Dehong Lu},
  title        = {macs30200-s22/replication-materials-DehongUChi},
  month        = Jun,
  year         = 2022,
  publisher    = {Github},
  journal      = {Github repository},
  howpublished = {\url{https://github.com/macs30200-s22/replication-materials-DehongUChi}},
  commit       = {}
}
```
