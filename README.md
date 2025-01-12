# Causality-Testing
This repo is created for ICSE 2023 paper - **Testing for Software Fairness (via Causality)**

##Abstract
What causes software to make decisions that are unfair to different social groups? How can we mitigate that problem?

There are many ways to address these questions from a sociological and/or psychological and/or algorithmic perspective. Here, we take an algorithmic causal approach that states: (1) It is unfair if final decisions make an unnecessarily causal connection between decisions and attributes that identify specific social groups (e.g. race, gender, etc); (2) decisions can be made fairer by reducing the number of those causal connections.

Based on experiments with causality-based testing for software fairness on ten data sets, we warn that causality-based testing for software fairness should not use a single causal graph. These graphs are complex to generate. Numerous heuristics are used
to speed up that process. Different graph generators used different heuristics and so produced different causal graphs. Hence, this single graph approach makes it hard to definitively mitigate for decision bias.

Rather, it is better to report unfairness propensity as a probability P computed using causal intervention. We show here this P probabilistic propensity measure satisfies the required properties of an unfairness/bias metric; i.e. (1) P decreases as we apply the standard bias mitigation algorithms; and (2) when the data set is perturbed, P changes in the manner predicted by theory (in this paper, those perturbations include random common causes, placebo treatments, and explorations of random subsets ).

## Dataset Description - 

1> Adult Income dataset - http://archive.ics.uci.edu/ml/datasets/Adult

2> COMPAS - https://github.com/propublica/compas-analysis

3> German Credit - https://archive.ics.uci.edu/ml/datasets/Statlog+%28German+Credit+Data%29 

4> Default Credit - https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

5> Heart - https://archive.ics.uci.edu/ml/datasets/Heart+Disease

6> MEPS - https://meps.ahrq.gov/mepsweb/

7> Titanic - https://www.kaggle.com/c/home-credit-default-risk

## Data Preprocessing -
* We have used data preprocessing as suggested by [IBM AIF360](https://github.com/IBM/AIF360)
* The rows containing missing values are ignored, continuous features are converted to categorical (e.g., age<25: young,age>=25: old), non-numerical features are converted to numerical(e.g., male: 1, female: 0). Fiinally, all the feature values are normalized(converted between 0 to 1). 
* For MEPS data, due to file size limitation, we upload the pre-processed files rather than the original csv files. Feel free to obtain raw data following the guidance (https://meps.ahrq.gov/mepsweb/data_stats/download_data_files_detail.jsp?cboPufNumber=HC-192)

## DoWhy Package Version
We are aware that the Dowhy API has been constantly updating and expanding itself. In our experimentation, we used DoWhy version==0.6.

## Experiment Results
In our paper, we collected DoWhy's propensity scores as well as several fairness measures for each bias mitigation method. The results are mean values from 5-graphs **X** 10-repeats. The final mean scores used in the paper can be found in the [fairness score file](/data/fairness_scores.xlsx) and [propensity score file](/data/propensity_scores.xlsx).
