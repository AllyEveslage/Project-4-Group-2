# **Are the Jobs You're Looking For Real or Fake?**

# Introduction
In today's digital job market, it's easier than ever to search for employment opportunities—but it's also easier for scammers to post fake job listings that exploit hopeful applicants. 
With the rise in online recruitment platforms, distinguishing between genuine job offers and fraudulent ones has become a serious challenge. 

# Project Description
Utilizing machine learning enables the effective classification of job postings as real or fake by analyzing patterns in textual and structural features of job descriptions. 
By training models on labeled datasets, algorithms can learn to detect subtle cues such as unusual word usage, missing company details, or suspicious formatting that often characterize fraency in online recruitment systems.
Leveraging the power of machine learning, we can now build intelligent systems that classify job postings as real or fake. 
By analyzing patterns in the text and structure of job descriptions—such as unusual wording, lack of company information, or suspicious formatting—these models can detect red flags that often go unnoticed. 
This not only streamlines the job search process but also protects users from scams, building trust and improving the safety of online hiring platforms.

# Process

Our machine learning pipeline began with the integration of several columns from our CSV files. 
Specifically, we combined the job title, description, and requirements into a single, comprehensive text field. 
This combination allowed us to create a unified textual representation for each job posting, simplifying subsequent processing steps.

Once we had our combined text field, we employed TF-IDF vectorization. 
TF-IDF, or Term Frequency-Inverse Document Frequency, is a statistical measure used to evaluate the importance of a word in a document relative to a collection of documents. 
By applying this technique, we transformed our textual data into a numerical format that the machine learning model could interpret. 
The process highlights terms that are distinctive across job postings, thereby enhancing the model's ability to differentiate between various postings.

With our text data vectorized, we proceeded to the model training phase. 
We opted for a Random Forest Classifier: a versatile and powerful ensemble learning method that constructs multiple decision trees and merges their outputs for more accurate and stable predictions. 
To optimize the classifier's performance, we utilized GridSearchCV, a comprehensive search method that explores hyperparameter combinations. 
Our tuning focused on two critical hyperparameters: n_estimators, which determines the number of trees in the forest, and max_depth, which controls the maximum depth of each tree.
Given the highly imbalanced nature of our data, where certain classes were significantly underrepresented, our optimization efforts prioritized the F1 score. 
The F1 score provided a balanced measure that accounted for both false positives and false negatives. 
By focusing on this metric, we aimed to achieve a model that could effectively balance precision (the accuracy of the positive predictions) and recall (the ability to capture all relevant positive instances), ensuring robust performance even with the imbalanced dataset.

In summary, our machine learning pipeline involved the integration of text columns, TF-IDF vectorization for text transformation, and the training of a Random Forest Classifier with hyperparameter tuning focused on the F1 score to address data imbalance. 
This comprehensive approach enabled us to transform raw textual data from CSV files into a well-optimized predictive model.

# Analysis

Accuracy can be misleading with imbalanced datasets, so we focused more on the F1 score, which balances the detection of fake jobs against the occurrence of false positives. 
The overall weighted F1 score was 0.98, demonstrating strong overall model performance even with an imbalanced dataset. 
For fake job postings specifically, our model achieved an F1 score of 0.75, with 100% precision and 60% recall. 
This indicates that while the model is exceptionally accurate at identifying real job postings, it correctly identifies approximately 60% of fake jobs—a commendable achievement given the low class count of only 173 fake jobs in the test set. 
The high precision on fake jobs also means there are very few false alarms, ensuring reliable performance in practical applications.

![image](https://github.com/user-attachments/assets/df07f86e-64fc-4395-b07f-28743e0efab7)

![image](https://github.com/user-attachments/assets/d149e311-ebaa-405e-9dfe-57a6b9c18a38)

![image](https://github.com/user-attachments/assets/47057570-d838-4949-a0c8-999d5c5a0093)

# Conclusion

One significant caveat is that our training data originates from 2016, and scams have evolved since then. The patterns we learned may not capture the nuances of modern fraudulent techniques. Additionally, fake listings are relatively rare, making up only about 4% of our dataset. This scarcity poses a challenge for modeling, as it can easily bias the model towards the majority class.
Moreover, the "fake" labels in our data were manually determined, introducing a level of human subjectivity. For instance, a peculiar but legitimate listing might be mistakenly labeled as fake. These factors highlight the inherent limitations of our approach.
Rather than striving for a flawless scam detector, we view our model as an insightful tool to build intuition and identify potential red flags. It is not meant to make definitive decisions but to aid in the exploration and understanding of suspicious job postings.
Ultimately, while our model demonstrates robust performance, particularly in its high precision for fake jobs, it should be used with caution and in conjunction with other evaluative methods to ensure comprehensive and accurate detection of fraudulent listings.

# Resources

2016 Dataset
https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction

2023-24 Dataset
https://www.kaggle.com/datasets/arshkon/linkedin-job-postings?resource=download

# Credits

Jackson Popelka- HeatMap, Analysis Coding https://www.linkedin.com/in/jackson-popelka-b04755340/

Ally Eveslage- README, Analysis Coding https://www.linkedin.com/in/allyson-eveslage-a21496193/
 
Erica Wollmering- Project Manager, Data Implications/Writing  https://www.linkedin.com/in/ericawollmering/
 
Brynn Butler- Matplotlib Plotting, Analysis Coding https://www.linkedin.com/in/brynn-butler/

Derek Bates- Matplotlib Plotting, Analysis Coding https://www.linkedin.com/in/derek-bates-93aabb340/

# How to Contribute to the Project

If you would like to contribute further to the project, the continuation of data collection over time, dissection of data into finer geographical markers and funding are welcome.

Any suggestions for additional use cases are appreciated as well.

- [![Python 3.7.13](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)]([https://www.python.org/downloads/release/python-3713/) - Programming Language
- [![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/docs/#) - Data maniupulation library
- [![Matplotlib](https://img.shields.io/badge/Matplotlib-3776AB?style=for-the-badge&logo=plotly&logoColor=white)](https://matplotlib.org/) - Visualization library for plots
- [![Jupyter](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)](https://jupyter.org/) - Notebook IDE
- [![Anaconda](https://img.shields.io/badge/Anaconda-44A833?style=for-the-badge&logo=anaconda&logoColor=white)](https://www.anaconda.com/) - Data science platform
