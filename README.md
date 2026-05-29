**Author:** MUDASSAR MUHAMMAD Huzaifa

**Context:**
Diabetes is one of the most common chronic diseases in the United States, affecting millions of people every year. This serious condition results in poor blood sugar regulation, which can reduce quality of life and even life expectancy in the long term. During digestion, food is broken down into sugars that enter the bloodstream. This prompts the pancreas to produce insulin, a hormone that allows cells to use these sugars as a source of energy. In diabetes, the body either does not produce enough insulin or does not respond properly to it.

Prolonged excess blood sugar increases the risk of serious complications, including cardiovascular disease, vision loss, amputations, and kidney failure. Although diabetes cannot be cured, its effects can be limited through weight loss, a healthy diet, regular physical activity, and appropriate medical care. The earlier the diagnosis, the more effective the treatment. This is why tools for predicting the risk of diabetes are an important public health issue.

The scale of the phenomenon is striking. According to the Centers for Disease Control and Prevention (CDC) in 2018, 34.2 million Americans were living with diabetes, and 88 million were prediabetic. One in five people with diabetes was unaware of their condition, and the vast majority of people with prediabetes were also unaware of their situation. Type 2 diabetes, the most common form, is influenced by many factors: age, education level, income, geographic location, ethnicity, and social conditions. The most disadvantaged populations are often the most affected.

The disease also represents a huge financial burden: the cost of diagnosed diabetes is estimated at around $327 billion per year, and if we include undiagnosed diabetes and prediabetes, the figure approaches $400 billion.

**Dataset description:**
The Behavioral Risk Factor Surveillance System (BRFSS) is an annual telephone survey conducted by the Centers for Disease Control and Prevention (CDC) on health. Each year, this survey collects responses from more than 400,000 Americans on their health risk behaviors, chronic diseases, and use of prevention services. It has been conducted annually since 1984. For this project, we used a CSV file of data available on Kaggle for the year 2015. This dataset contains responses from 253,680 individuals and includes 22 variables. These variables correspond either to questions asked directly to participants or to variables calculated from their individual responses.

The variables in the dataset are:

* Diabetes_binary (0 = no diabetes, 1 = prediabetes, 2 = diabetes)
* HighBP (0 = no high BP, 1 = high BP)
* HighChol (0 = no high cholesterol, 1 = high cholesterol)
* CholCheck (0 = no cholesterol check in 5 years, 1 = yes cholesterol check in 5 years)
* BMI (Body Mass Index)
* Smoker (Have you smoked at least 100 cigarettes in your entire life? 0 = no, 1 = yes)
* Stroke ((Ever told) you had a stroke. 0 = no, 1 = yes)
* HeartDiseaseorAttack (coronary heart disease (CHD) or myocardial infarction (MI) 0 = no, 1 = yes)
* PhysActivity (physical activity in past 30 days - not including job 0 = no, 1 = yes)
* Fruits (Consume Fruit 1 or more times per day 0 = no, 1 = yes)

**Objectives:**
In this workshop, you are tasked with building a binary classification model to predict the probability of a person having diabetes based on medical data from the Diabetes binary health indicator (BRFSS 2015) survey.

To do this, we will group the "no diabetes" (0) and "prediabetes" (1) classes of the Diabetes_binary variable under a single "no diabetes" (0) class. The class will therefore become:

* 0 → no diabetes or prediabetes
* 1 → diabetes

Your ultimate goal is to maximize the ROC AUC metric on an unlabeled test set.

**Methodology & Results:**
To address the dataset's severe class imbalance (86% vs 14%) and optimize for clinical relevance, a Multi-Layer Perceptron (MLP) pipeline was developed with the following implementations:

* **Experiment Tracking:** 10 experiments (5 architectures × 2 imbalance strategies) logged via Weights & Biases (wandb).
* **Class Imbalance Strategy:** Applied class weights, which significantly outperformed SMOTE on recall.
* **Final Architecture:** A Dropout + Class Weights MLP model optimized with a decision threshold of 0.35 to prioritize recall.
* **Performance Metrics:** Achieved an AUC of 0.811 and improved Recall from ~0.12 to 0.786.
* **Explainability:** SHAP values confirmed General Health, BMI, High Blood Pressure, Age, and High Cholesterol as the top risk predictors.
* **Efficiency:** The final model proved energy-efficient, with a tracked CO2 footprint of 0.000142 kg.