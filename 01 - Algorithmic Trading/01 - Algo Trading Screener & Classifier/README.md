# Algorithmic Trading
---

This repository contains implementation of Algorithmic Trading.

Following are the files: 
* **01 - Algo Trading - Screener & Classifier.ipynb** - This script scans entire universe of S&P500 and NASDAQ stocks. Computes momentum score, value score and social sentiment scores and finally computes composite scores from the above mentioned scores. Finally picks top n stocks based on the composite score. It then evaluates 6 classifiers and select the best classifier that predicts future price actions such as short sell or long. Alpaca API keys are required to extract past price action data.

* **techanalysislib.py** - Library of custom built technical indicators which are used for feature engineering.


## How to run the notebooks <br>
Clone the entire repository - "01 - Algo Trading - Screener & Classifier"  into a local folder by issuing the following command from gitbash <br>
```
$git clone https://github.com/sal-trevino18/01 - Algo Trading - Screener & Classifier.git
```
Stay in the same gitbash directory and open Jupyter lab by issuing the following command from gitbash: <br>
```
$jupyter lab
```


<hr style="border:2px solid blue"> </hr>

## Sal Trevino

**Email:** sal.trevino18@gmail.com# lstm-price-predictor