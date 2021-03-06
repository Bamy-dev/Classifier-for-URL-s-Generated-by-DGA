# Classifier for URL's Generated by DGA
 An investigation on a URL database to develop a DGA classification system using machine learning techniques. This investigation, is a Cyber Security Analytics investigation.

For this task, I developed a classifier that can decipher URL's generated by DGA's from legitimate URL's.This is a machine learning tool developed using Python and machine learning libraries.
The URLs based on Domain Generator Algorithms (DGA), are widely used by command and control malware to avoid static IP blocking. 

Methodology : Get a classified DGA dataset, use it as "train data" then test it using a fresh dataset.

Classification Approach: Basically, I'll be using a pattern based approach. From the domain in the datasets, i'll find the characteristics of each domain such as: vowel-consonant ratio, length of domain, number of identified digits, entropy, n-grams. These characteristics are numerical and will help any classifier ML model form a pattern for classification. In essence, new input features will be generated from the domain.

Link to reference approach: https://cyber.wtf/2017/08/30/dga-classification-and-detection-for-automated-malware-analysis/

Generally, ML models only understand numerical data. So there has to be a way of translate non-numerical data to an algorithm hence, the numerical characteristics. After a successful translation and addition of input variables, the domain column will be dropped.

The dataset was obtained from Alexa website ranking a blacklist of previous DGA domain names. The purpose is to build a classifier which can help us detect a potential machine infected by the DGA (Domain Generation Algorithm) malware.

Link to reference dataset: https://www.kaggle.com/datasets/gtkcyber/dga-dataset

For my investigation, I used the following 3 classifiers:

clf_1 = LogisticRegression(random_state=42)
clf_2 = RandomForestClassifier(max_depth=100, random_state=42)
clf_3 = MLPClassifier(random_state=42, max_iter=300)
