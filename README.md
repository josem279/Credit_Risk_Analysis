# Credit_Risk_Analysis

## Project Overview

This project focueses on using machine-learning models and processes to analyze a dataset from Lending Club, a peer-to-peer lending services company, for credit card risk. The challenging aspect of this project is employing the resampling and ensemble learning techniques to evaluate our algorithms and their outputs. These two techniques include using different algorithms like RandomOverSampler, SMOTE and ClusterCentroids we are able to oversample and undersample the dataset to test for accuracy, precision, and sensitivity.

## Results

The algorithms we used yielded the following results for the resampling and ensemble learning techniques:

### Naive Random Oversampling

![RandomOverSampler Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/Naive_Oversampling.PNG)

- As demonstrated above, the RandomOverSampler Algorithm resulted in a relatively low balanced accuracy score - about 64% accurate. The imbalanced classification report shows that although the majority class (low_risk) was completely precise, the minority class (high_risk) had incredibly low precision, recall, and f1 scores - 1%, 62%, and 2% respectively. These results imply that this machine learning model has a poor performance identifying high risk credit cases.

### SMOTE Oversampling

![SMOTE Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/SMOTE_Oversampling.PNG)

- The accuracy score for the SMOTE oversampling algorith was a low score of about 64%. The imbalanced classification report also showed a large disparity between the precision for the high_risk and low_risk classes. This is reflected in low sensitivity (recall) scores and disparate f1 scores. Again, this model may not be the best for calculating high_risk credit card cases and tends to incorrectly classify credit risk.

### Undersampling - ClusterCentroids

![Undersampling Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/Undersampling.PNG)

- As an alterante approach to oversampling, we tried the ClusterCentroids undersampling algorithm to see if the model would be better for analyzing credit card risk. This model had a balanced accuracy score of roughly 51.6% - very low. The imbalanced classification report, shows a very low average recall (40%) and a similarly low average F1 score (63%). Unfortunately, this undersampling model tends to also incorrectly classify most credit card risk as low and fails at distiguishing high risk instances.

### Combination (Over and Under) Sampling - SMOTEENN

![SMOTEENN Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/SMOTEEN.PNG)

- The final resampling technique that we used to analyze credit card risk was using the SMOTEENN algorith - a combination of oversampling and undersampling. The accuracy was rougly 62% - again, a low score. The imbalanced classification report also had similar results. The report had low recall and F1 scores as well as a large disparity between the two classes meaning it is not very precise at calculating high risk credit card loans even though it can catch all low risks.

### BalancedRandomForestClassifier

![RandomOverSampler Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/Balanced_Random_Forest.PNG)

- The first Ensemble Learners technique practiced to analyze credit card risk is the BalancedRandomForestClassifier algorithm. The balanced accuracy score for this model is roughly 79% which seems decent but does solely determine the efficacy of the model. Looking at the imbalanced classification report, we can see that there is a huge disparity between the precision for the high_risk and low_risk classes - the model can accurately identify the low risk cases but not the high risk cases. There is also a large difference in the F1 scores, further illustrating that the algorithm is not the best at identifying risk.

### EasyEnsembleClassifier

![RandomOverSampler Output](https://github.com/josem279/Credit_Risk_Analysis/blob/main/Images/EasyEnsembleClassifier.PNG)

- The final algorithm tested was the EasyEnsembleClassifier. The balanced accuracy score for this report was very high, about 92.5% meaning it should capture all cases. However, like the other models the precision scores for the high_risk and low_risk classes are very different - roughly 7% and 100%. Again, this means that this report may not be the best at calculating the high risk cases but will capture all low risk cases.

## Project Summary

Overall, it appears that some of the models were much better than others. Specifically it appears as though the best models to use were the Ensemble learning algorithms as they were more precise than the relearning algorithms. Of all of the algorithms, the best one was the EasyEnsembleClassifier model. This model has the highest balanced accuracy score meaning it will capture most credit card risk cases. The model also has high sensitivity (recall) scores for both high risk and low risk cases meaning it should be able to accurately classify cases as high risk or low risk. When it comes to credit card risk, a strong sensitivity score is very helpful as it allows the company to correctly present loans or deny them based on the risk a client poses. That being said, I do not recommend using any of these models as they all fail to correctly classify high risk cases and could open up the company to loans that may not be able to be paid back. Although the EasyEnsembeClassifier model had promising results, the truth is that they appear that way because of the disparate amounts in support. The model fails at scaling the data for high risk cases to match low risk cases and thus may lead to poor training. One potential fix would of course be to scale the data before applying the model and revise the output.