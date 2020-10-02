# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)
<h1><center>Web Scrappring and Data Science Project</center></h1> <h3><center>(by Wilson Alberto Torres)</center></h3>

# 1. Introduction

This project illustrates a case study where an unknown organisation which appears to offer services in the Information & Communication Technology (ICT) field. This company requires to recruit the most competitive data scientist professionals in the job market. Two main objectives/questions of this project are (1) determining the critical factors that predict salary amount for this type of professionals, and (2) establishing the relevant components that can distinguish job categories or titles.  Similarly, the project aims at applying the concepts that have been learnt in the data science immersive course, in this particular case, web scrapping, Exploratory Data Analysis (EDA), and modelling.

# 2. Summary of Research Undertaking

In the execution of this project, I chose seek.com.au to scrape information about jobs related to the data science field. I began by analysing the structure of the seek’s website to understand how jobs are presented and which parts were relevant for achieving the project’s objectives. I used ‘selenium’ application along with ‘XPath’ to scrape information of almost 8000 data science jobs which were stored in a CSV file. Specific details of this activity are shown in the jupyter notebook called ‘Project-4-WebScrapping-2’.
The EDA part, including in the jupyter notebook ‘EDA-Model-v2’, consisted of cleaning the dataset, which was created in the previous step. This part removes the duplicated jobs from the dataset, reducing its dimension from 8000 to 5898 records (or rows). Two CSV files were generated in this process to answer question one and two. In one file, the salary column from the dataset was cleaned by removing those records that not contain salary figures, and this shrank the dataset to just 1026 documents. After that, further cleaning was performed in the full job description by employing ‘regex’ and ‘Python String methods’. The second file had only cleaned the full job description, as well as the salary feature, was removed, this resulted in a dataset with 5898 records to address question two. Thus, this EDA stage outputs two CSV files that were used to run the modelling in questions one and two.
The dataset with 1026 was used to address objective one. The target variable (salary numbers) was classified into low and high salary in which the median of this variable distribution was used to set the boundary. In this stage, seven classification models were employed where Random Forest seems to achieve better results. For example, the cross-validation score was 0.80, with a ROC area of 0.90. Moreover, this model reveals that among the essential words to predict salary was ‘senior’, ‘leadership’, and ‘decisions’. The models were pre-processed (CountVectorizer) and executed by pipelines from where initial optimisation was performed with GridSearchCV to find the best score from different parameters. These results were stored in the jupyter notebook named as ‘Modelling-Q1’.
Finally, question two was explained in the jupyter notebook ‘Modelling-Q2’. This part received a dataset with 5898 rows from the EDA stage. Since the job title was very inconsistent and hard to find patterns to be classified, I utilised the keyword search that provides a straightforward approach to establish a formal classification. This feature was set as a target variable, having three classifiers: (1) data science, (2) data analyst, and (3) data engineer. However, this label showed an imbalance classification which was solved by utilising an oversampling technique, transforming the dimension of the data frame to 11020 rows. Similarly, this section also employs seven models. Preliminary results illustrate that the cross-validation score is consistent and higher (greater than 0.95) across the evaluated models. The most relevant words that predict ‘data science’ jobs in the search engine of seek.com.au are: ‘computer science’, ‘python’, and ‘engineering’.

# 3. Challenges and Conclusions

Even though the main objectives of this project were finalised, further analyses could achieve better outcomes. For instance, using tf-idf vectoriser, stemming, and lemmatisation. They might improve text processing before feeding it to the models.
