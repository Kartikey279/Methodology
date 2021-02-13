# Methodology
* Methods involved in Analysis or Methodology used to solve different problems.
* Different problems needs different types of procedure to reach a wanted outcome, I will discuss the different methodology or steps i took during the analysis of any assingment/project, and will discuss the results.
## EDA Case Study
### Objective of the case study.
* The loan providing companies find it hard to give loans to the people due to their insufficient or non-existent credit history. Because of that, some consumers use it as their advantage by becoming a defaulter. Supposing we are a consumer finance company which specialises in lending various types of loans to urban customers. We have to use EDA to analyse the patterns present in the data. This will ensure that the applicants capable of repaying the loan are not rejected.
### Steps taken during the analysis.
* After importing the libraries, we look upto the dataset head to have a better understanding of the provided data.(In this case as we have to look upto both the datasets)
* Then after having the brief understanding of data by using 'describe', 'shape' and 'info', we look up for the null values present in the data.
* As frrom our previous understandings after looking upto data we drop the columns in both the datasets which have null values more than 50 percent by using 'drop' function.
* We move forward by looking upto columns one by one and analyzing the need of the null values and replacing it with suitable values.
* In applicationdata dataset, we replaced AMT_GOODS_PRICE null values with mean values because that will not affect the analysis, then NAME_TYPE_SUITE null values with most common values in that column, replaced AMT_REQ_CREDIT_BUREAU_HOUR, AMT_REQ_CREDIT_BUREAU_DAY, AMT_REQ_CREDIT_BUREAU_WEEK, AMT_REQ_CREDIT_BUREAU_MON, AMT_REQ_CREDIT_BUREAU_QRT, AMT_REQ_CREDIT_BUREAU_WEEK, AMT_REQ_CREDIT_BUREAU_YEAR null values with zero because after looking up the data we saw that these values are actually time consumption so if some values are not present it's better to go with zero and then we converted these values to integer format as per our need.
* Then we replaced all flag variables to Y(yes) and N(No).
* We also have to look upto the Outliers in the current dataset.
* Then we added two new columns which will help us to find the optimal solutions, one of them being the Income column which is divided on the base of percentile in four parts with four different labels, and other is age.
* Then we assign two more values defaulters and non-defaulters, according to the Target variable outcome of Y or N.
* After that countplot the variables to find out the defaulter in each columns respectively.
* Now in previousAppdata dataset, we look up for the null values.
* Then we merge both of these dataset using left merge on SK_ID_CURR.
* Now we crosstab different columns with 'NAME_CONTRACT_STATUS' and plotted bar graph for each which gives us a knowledge about status of clients on based of different criterion on which the bank can take there decisions.
