# BERT-LockedDown-Project
# 1. Introduction
Initially, the novel coronavirus disease 2019 (COVID-19) appeared and reported in December 2019 in China (Chahrour et al. 2020). To reduce the transmission, in 2020, the Chinese government took exceptional steps and locked down policies. Shortly after that, other countries reported cases of the virus and then it became a global issue (Spina et al, 2020), and the World Health Organization (WHO, 2020) announced the pandemic status. At the end of March 2020, in 177 countries a total of 722,435 positive cases with more than 33,997 mortality (JHU, 2020). Public health authorities, to control the spread of the virus and outbreaks, set different restrictions such as travel bans, social distancing, quarantining, and social gatherings (Bedford et al.,2020). This situation has been linked to mental health stress, morbidity, and mortality (Czeisler et al.,2020). Globally, Studies have indicated a significant surge in self-reported anxiety and depression between April and June 2020 in comparison to the same period in 2019. The authors showed that 13% started or heightened substance use to help them to cope with the pandemic, 31% reported anxiety or depression, and 26% showed stress related disorders (CDC, 2020: Yan et al.,2020).
This pandemic is an unprecedented incident, which is impacting the health care, economic and social systems. This traumatic event has affected society at individual and population levels. At the individual level, mental health issues are reported. At the population level, the nations experience economic adversity such as unemployment and poverty, school closures, domestic violence, inadequate basic food necessities. This situation caused pressure on the global supply chains and health care systems (Fefferbaum & North, 2020).
Fear of contracting the Covid-19, of dying, losing the loved ones, uncertainty and fear of future, separation from loved ones and social discrimination could lead to the psychopathological concerns. As a result, this pandemic manifests as a complicated and multifaceted novel event which is different from natural disasters or previous epidemics such as severe acute respiratory syndrome and Ebola (Brooks et al., 2020).
Educational institutions and training centres also have been affected and shut down, which resulted in social isolation among the younger generation and not being able to socialize with their peers and follow their routine of attending schools. This situation affected their parents’ job as well, since the children stayed home due to closing the childcare centres. The parents were obliged to handle working from home (office work) and providing childcare (double duty). This situation also added to the burnout in parents and caregivers. (Zhou et al., 2020).

# 2. Objectives
1. Accessing and Understanding the Data
2. Verifying the Translations with Language Experts
3. Preprocessing the Data
4. Creating and Fine-Tuning Machine Learning Models
5. Producing Scripts to Automate Testing of Machine Learning models
6. Compiling Machine Learning Result Data into Tables for Data Representation
7. Data Analysis and Representation 

# 3. Methods and Data Analysis

## 3.1 Data Description: 

The data accumulated for the survey responses are from students, staff, and faculty at various universities where each data entry has a survey response of the individual and its respective sentiment. Each dataset of the survey responses contains two major columns, the textual survey response and the sentiment of the respective textual response. The textual response contains the answer of the respondents to the question of how lockdowns during the COVID-19 pandemic affect their mental health.

## 3.2 Pre-Processing Data

Pre-processing the data involves multiple steps that clean and organize the textual data before using the data to fine-tune the machine learning models. Cleaning the data of unnecessary characters in the textual responses, for instance, any special characters while changing formats of the xlsx to CSV, or any redundant formatting in the textual data. Moreover, multiple survey respondents chose not to answer the question about lockdowns impacting their mental health which shows a null value in the textual-response field in our DataFrame. Eliminating such null values ensures no stoppage while fine-tuning the machine learning models. A similar technique of pre-processing the data was replicated for all languages.

## 3.3 Translating Data

The rationale behind the translation of textual responses to English from various languages is to generalize the textual data to a language that we native proficiency speakers could understand and validate the prediction through our understanding of the English language. Fine-tuning individual machine learning models for each language can be proven a redundant task and would involve different prediction accuracies across the models. Thus, having a unified English language machine learning model maintains consistency throughout the various language data. Most importantly, having a large English dataset with textual data for training that is classified to its respective sentiment incentivized translating various languages to English and generalizing the ML model to learn and predict the sentiment of the English Language. Besides, finding sources to train the model specific to languages such as Czech, Russian, Korean, or German could be proven cumbersome.

For the translation, the use of the Google API was effective since it allowed the translation of textual responses in multiple batches per API call. An API call is an instruction to the google translate application to translate the text embedded in the code of our machine learning model. The Google API allows multiple API calls without any major restrictions on the number of times the API is called, and since it uses Google's Cloud services during the translation there is no need for high-tech computers.


# Bert Model and Implementation

## 3.4 Machine learning model for sentiment extraction

BERT, short for Bidirectional Encoder Representations from Transformers, is a machine learning framework for natural language processing (Lutkevich, 2021). “Bidirectional” in BERT represents the model’s ability to read the total sequence of words at once i.e. each word in an input sentence is processed simultaneously. This mechanism allows the model to learn contextual relations between words (e.g. her in a sentence refers to Jessica) which is useful when predicting the sentiment of an input with multiple sentences. Additionally, BERT’s use in NLP “transfer learning” (Brownlee, 2017) enables us to fine tune the model for sentiment analysis by training with small amounts of data and achieving great results.

## 3.5 Fine Tuning BERT for sentiment classification and Training Results

A custom dataset consisting of classified english COVID-19 survey responses was used to fine tune the model for sentiment analysis. Training a machine learning model involves teaching the model to identify positive or negative textual data, thus the data that we train the model contains textual data classified according to their sentiment. On the contrary, testing data contains only textual responses since it's the trained model's job to predict each textual response's sentiment in terms of positive and negative. The model accuracy on the test set appeared as 80% which shows that the model can generalize well COVID survey responses in a good manner. 
