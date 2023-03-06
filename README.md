# Haowen-STATS201-Final
motivation: motivate others to get interested in your research (related to the existing literature)
Intellectual: contribution. Future work

# Ethereum Price Prediction and the impact of FTX's bankrupty on the Ethereum Price
## General information
- **Author**: Haowen Ji, Data Science, Class 2023, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the final project for [STATS201 Introduction to Machine Learning for Social Science, 2023 Spring Term (Seven Week - First)](https://ms.pubpub.org/) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: I would like to thank Prof. Luyao Zhang for her instructions on STATS201 and thanks all the classmates for the inspiring discussions and feedbacks. 

## Project Summary
**1. Explanation project:** 
* Background & Motivation: NFT is getting more and more popular, but the amount of research related to the prediction of the value a NFT product is still small. 
* Research Question: This project focus on the research question that what are the hot topics in the NFT prediction field. This question is important since it can help further research find new attributes in prediction. 
* Application Scenario: This project is applied to eight literatures related to the NFT prediction topic. 
* Methodology: The machine learning methodology explanation is used in this project, especially, word cload and bigram are used for text analysis. 
* Results: The results shows some new high-frequency words and new relationship of keywords. 
* Intellectual Merit & Practical Impacts: This project contributes to the future research direction of NFT prediction. More research can be conducted based on the new high-frequency words.

**2. Preidcation project:** 
* Background & Motivation: Ethereum has a large market cap, while its price predictability is not much addressed in the published literature. 
* Research Qeustion: Thus, this project focuses on the research question that how effetive is machine learning algorithmns in predicting Etherem open price. 
* Application Senerios: This project is applied to the Ethereum opening price from 2015 to 2021. The machine learning methodology prediction is used in this project. 
* Methodology: Linear regression and random forest regression are used as regression models. 
* Results: The result shows that linear regression has a good performance, which random forest regression is not efficient.
* Intellectual Merit & Practical Impacts: This project contributes to the times series data prediction, especially in the Ethereum value prediction. More researches on more kinds of machine learning models and more features related to the price prediction can be conducted in the future.

**3. Casual inference project:** 
* Background & Motivation: Digital asset prices in the cryptocurrency market have been rapidly fluctuating, indicating high volatility in recent years. Ethereum (ETH) is one of the digital assets that has become increasingly popular due to its decentralized nature and ability to support smart contracts (Leonhard 2019). However, according to the research, the value of Ethereum can be affected by various factors, including market sentiment, external events, and so on. (Akbulaev, Mammadov, and Hemdullayeva 2020) In this regard, the bankruptcy of FTX, a major cryptocurrency exchange, could have a significant impact on the price of Ethereum. FTX is a cryptocurrency derivatives exchange that allows users to trade a wide range of cryptocurrencies. It was launched in 2019 and quickly got popular due to its user-friendly interface and innovative features. However, FTX faced financial difficulties in 2022, leading to its bankruptcy (Jalan and Matkovskyy 2023). The relationship between the bankruptcy of FTX and the price of Ethereum remains inadequately explored. While some studies have investigated the impact of news events on cryptocurrency prices, such as the research executed by ÖNGEL (2022), the impact of FTX bankruptcy on Ethereum prices remains unexplored. Conducting such research could offer valuable insights into the resilience of the cryptocurrency market and could support making investment decisions in the future.

* Research Qeustion: What is the causal relationship between the bankruptcy of FTX and the price of Ethereum?
* Application Senerios: The data is extracted from Coin Metrics (Coin Metrics 2023). The data has two attributes, the first one is the date and the second is the closing price of Ethereum corresponding to each day in the unit ETH / USD. The date is the x variable, and it ranges from 2015/8/8 to 2023/2/23. The Y variable is the closing price of Ethereum, which ranges from 0.420000 to 4811.156463. The trend of the whole data is shown in Figure 1. It is obvious that the price of Ethereum has increased significantly overall since its release, but there has been a lot of fluctuation. The area between the orange line and the red line is the period of FTX bankruptcy. These two dates will be put into the regression discontinuity design as the representation of FTX bankruptcy separately. 
* Methodology: The regression discontinuity is used in this research. It is a statistical method commonly used to estimate the causal effects of a treatment or intervention on an outcome of interest. In the context of this research on the impact of FTX bankruptcy on the price of Ethereum, RDA is used to investigate the causal relationship between the two variables. Specifically, it can be examined whether there is a discontinuity in the trend of Ethereum prices at the time of FTX bankruptcy, and if so, whether this discontinuity can be attributed to the bankruptcy event or other confounding factors. 
* Results: The observed trend aligns with the expectations, as a sharp decline in the Ethereum price was observed immediately following FTX's bankruptcy. Moreover, after this event, the Ethereum price exhibited a gradual increase over time. Furthermore, the scatter plots reveal that the price of Ether displays a considerable degree of volatility.
* Intellectual Merit & Practical Impacts: This project contributes to the existing literature on the factors of cryptocurrency prices and how external events affect them. For the investors and traders in the cryptocurrency market, this research can inform them of the potential risks of external events like FTX bankruptcy, which supports them in making investment decisions. This research can also help policymakers to regulate the market and minimize the effect of this kind of event.

## Table of Contents

- [Data](https://github.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final#data)
- [Code](https://github.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final#code)
- [Spotlight](https://github.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final#spotlight)
- [More about the Author](https://github.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final#more-about-the-author)
- [References](https://github.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final#references) 

## Data

### Data Source: 
- [Queried Data](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/tree/main/data/Queried_Data)
- [Processed Data](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/tree/main/data/Processed_data)

### Meta Data Information
<div class="table-wrapper" markdown="block">

| Data files| Data Content | Type|
| ------------- | ------------- | ------------- |
| ETHUSD.csv | Ethereum historical data from 2015 to 2021 | queried data |
| Ethereum_value.csv | Ethereum data after preprocessing | queried data |
| Regression_Train.csv | Data for model training | processed data |
| Regression_Test.csv | Data for model test | processed data |

</div>

### Data Dictionary
<div class="table-wrapper" markdown="block">

| variable name | description | frequency     |  unit.    | range| type|
| :---         |     :---     |          ---: |---:        |---: |---: |
| Date | Represents the date at which the share is traded in the stock market | monthly |day|from 2015-08-07 to 2021-10-20|Object|
| Open | Represents the opening price of the stock at a particular date, which is the price at which a stock started trading when the opening bell rang | monthly |USD|from 0.431589 to 4174.635742|Numeric Types: float|
| Close | Represents the closing price of the stock at a particular date, which is the last buy-sell order executed between two traders. The closing price is the raw price, which is just the cash value of the last transacted price before the market closes | monthly |USD|from 0.434829 to 4168.701172|Numeric Types: float|

</div>

## Code
- [Query Ethereum Data](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/blob/main/code/Query_Data_Ethereum_Data.ipynb)
- [Process Regression Data](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/blob/main/code/Process_Data_Prepare_X_and_Y_for_Regressions.ipynb)
- [Analyze Data](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/blob/main/code/Analyze_Data_Machine_Learning_for_Predicting.ipynb)

### Table of Code
| Code files| Description | Type|
| :---         |     :---:     | ---: |
| Query_Data_Ethereum_Data.ipynb  | This code deals with the read and preprocessing of the original dataset | .ipynb |
| Process_Data_Prepare_X_and_Y_for_Regressions.ipynb | This code processed the X and Y dataset from Ethereum_value.csv for regression  | .ipynb |
| Analyze_Data_Machine_Learning_for_Predicting.ipynb | This code applied machine learning method for open price regression| .ipynb |

## More about the Author
<img src="https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/Haowen-STATS201-Final/main/spotlight/figures/Haowen.jpg" width="150" alt="Haowen" /><br/>

- **Self Introduction**: 
Yutong Quan is a junior student majoring in Political Economy with an Economics track at Duke Kunshan University. She is interested in Finance, Artificial intelligence, Blockchain, and Behavior Economics.
- **Final Reflections**:
The discussion on applying machine learning methods to solve social science problems can be divided into four parts. The first part is data explanation. We can use a variety of data visualization methods, including histograms and heatmaps, to communicate social science problems to the public more concisely and clearly, which is also convenient for us to conduct further analysis and interpretation. The second part is the data prediction. We input historical data containing X variables and Y variables into the machine and then use supervised machine learning algorithms to learn the data and results, thus figuring out the possibility we successfully predict the true value. Data prediction provides a good tool for us to solve prediction problems in social sciences by traversing a large amount of historical data and looking for internal laws. For example, we can use historical stock prices to predict future stock market movements and provide decision suggestions for investors, companies, and governments. The third part is causal inference. We conduct causal inference when social scientists want to explore the reasons why one variable in a system may affect another. Based on massive data and algorithms, machine learning evaluates the causal effect of each predictor variable on the outcome, making it more convenient to determine the causality. The last part is optimization, which is to find the strategy which maximizes our objectives based on a decision environment of state-action-reward pairs. By using a reinforcement learning algorithm and inputting our objectives, the machine can help to find the best strategy even though the detailed environment may change. The use of machine learning to find optimal solutions is widespread. One example is using artificial intelligence to find the portfolio that achieves the best performance.
(Reference: [Machine Learning for Social Science: Match the right tool to the job](https://whimsical.com/machine-learning-for-social-science-match-the-right-tool-to-the--8zuA7Bg5bYQPkRgMJCoywA))


## Spotlight
![image](https://raw.githubusercontent.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/main/spotlight/figures/Linear_Regression_Result.png)
*Figure 1: The prediction result of ethereum open price by linear regression*
- [Code source](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/blob/main/code/Analyze_Data_Machine_Learning_for_Predicting.ipynb)
- [Data source](https://github.com/Rising-Stars-by-Sunshine/stats201-prediction-Haowen/tree/main/data/Processed_data)
- Description: from figure 1, it is obvious that the predicted result is very close to the real open price value. The result is evaluated by R2 score, which is 0.984. The R-squre determines the proportion of variance, which shows how well the data fit the regression mode(Chicco, Warrens, and Jurman 2021). The closer the r-squared value is to 1, the better the fit. Thus, the linear regression reached a high accuracy regarding the r-squared value.

## References

### Data Source
- [Ethereum Historical Dataset](https://www.kaggle.com/datasets/abhimaneukj/ethereum-historical-dataset)
### Code Source
- [Rising-Stars-by-Sunshine/stats201-tutorial-prediction](https://github.com/Rising-Stars-by-Sunshine/stats201-tutorial-prediction/tree/main/code)
### Articles
- [Predicting Price Changes in Ethereum](https://cs229.stanford.edu/proj2017/final-reports/5244039.pdf)
- [The Coefficient of Determination R-Squared Is More Informative than SMAPE, MAE, MAPE, MSE and RMSE in Regression Analysis Evaluation](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8279135/)
### Literature
- Chen, Matthew, Neha Narwal, and Mila Schultz. 2019. “Predicting Price Changes in Ethereum.” *International Journal on Computer Science and Engineering (IJCSE) ISSN*: 0975-3397.

- Chicco, Davide, Matthijs J. Warrens, and Giuseppe Jurman. 2021. “The Coefficient of Determination R-Squared Is More Informative than SMAPE, MAE, MAPE, MSE and RMSE in Regression Analysis Evaluation.” PeerJ Computer Science 7 (July): e623. https://doi.org/10.7717/peerj-cs.623.

- Zhang, Luyao (Sunshine). 2022. “Machine Learning for Predictions.” Machine Learning for Social Science, November-. https://ms.pubpub.org/pub/ml-prediction/release/4.
