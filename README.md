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
### Results
* We provided the bank with different kinds of graph for defaulters and non-defaulters according to our analyis by the help of which they can decide whomsoever they want to lend the loan.


## Clustering
### Objective
* We have been provided with different types of datasets of multiple socio-economic and health factors of different countries around the world by NGO. We have to find those countries which are in dire need of help by analyzing different factors we have been provided to divide countries in different group with the help of clustering.
### Steps taken during analysis
* First step in any analysis is importing libraries and understanding the dataset provided to us. (Understanding the data involves looking up to its different features like, 'Describe' 'Shape' 'info' and finding null values)
* Now we change values in three columns to get exact value for analysis, because the columns import, export and health they are given as %age of the GDP per capita, so we multiply these columns with the GDPP columns(which itself is divided by 100 before multiplying) to get the required values.
* After that we make a list of columns and we drop the country. Then we plot the distplot of each columns to find out the distribution of data in each column.
* Then we look up for co-relation in each column by using 'corr()'. We plot the heatmap for these columns to have a better understanding of co-relation.
* Looking for outliers by plotting box plot for each column. And treating the outliers by doing soft capping of them, but during the soft capping we have to look for the outliers which does not effect the results of our analysis.(For child_mort, inflation, total_fer we only do soft capping for the lower limit outliers and for others we treat the outliers from the upper limit)
* As we move on to do the clustering, we need to define the hopinks using the 'def' function. And then pass our dataset from it.
* Then we create a new dataframe by performing  fit and transform on the dataframe passed by the hopkins.
* We can do the clustering with different methods. First being the silhouette_score.
* We find the silhouette_score for the dataframeand plot the graph for it and using this graph we define the Kmeans value or the number of clusters.
* Moving on to find the cluster centers and then providing them with the labels. Then we add a new label coulmn in the dataframe with the values of labels for the cluster centers and we can see that the data are divided into 3 different clusters by using value count function.
* Then we scatterplot for the three main values (i.e; child_mort, gdpp, income), and a boxplot with all these values to find out the cluster which is the most needfull group of countries.
* Second method of clustering be linkage method, we then performed the single and complete linkage to define the number of clusters, this method is more usefull when we have a better business idea  beacause we can choose the number of clusters according to our need.
### Results
* After doing the analysis of the data provided, we can see an outcome of three different clusters from both the methods of clustering, one can now easily choose the cluster of countries which are in the dire need of help.


## Lead score
### Objective
* We have to build a logistic regression model to assign a lead score between 0 and 100 to each of the leads which can be used by the company to target potential leads. A higher score would mean that the lead is hot, i.e. is most likely to convert whereas a lower score would mean that the lead is cold and will mostly not get converted. There are some more problems presented by the company which our model should be able to adjust to if the company's requirement changes in the future so we will need to handle these as well.
### Steps involved in the analysis
1. Reading	of	data
* Data	was	provided	in	form	of	csv	which	was	read to get a better understanding and performing the analysis.
2. Cleaning	of	data
* a. The	data	set	contained	missing	values
* b. Columns	with	more	than	75%	missing	values	were	dropped
* c. Some columns	 were	 replaced	 with	 mean,	 some	 with	 mode	 and	some	with	na
3. Data	Analysis
* a. EDA	helped	in	getting	imbalnce	data
* b. Relationship	with	conversion
4. Data	Preparation	for	Modelling
* a. Binary	results	were	converted	to	1/0
* b. Dummy	variables	were	introduced
* c. Outliers	were	capped
* d. Correlated	features	were	removed
5. Data	Modelling
* a. Data	was	split	into	training	and	test	data	set	in	ratio	70:30
* b. Feature	selection	was	done	using	RFE
* c. Model	was	improved	by	using	statsmodel
* d. Model	was	build	
* e. Test	data	were	executed	on	the	model
6. Prediction	was	done	for	the	data	and	lead	scores	were	calculated
7. Accuracy,	Sensitivity,	Specificity	was	calculated
* a. Training	data:	
* accuracy	:	90%
* sensitivity:	89%	
* specificity:	91%	
* b. Test	data:	
* accuracy	:	90%		
* sensitivity:	88%	
* specificity:91%
### Result
* We provided an additional column named lead score to have a better understanding of conerted leads.
* Tags	to	focus	on:
* Switched	off,Busy ,Lost	to	EINS, Identify	people	with	null	values	for	tags	and	Leads	profile
* Focus	on	Lead	Sources	from	Welingak	Website





