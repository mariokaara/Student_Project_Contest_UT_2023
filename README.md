Backround:

Occupational accidents are a major global concern which results in significant human
and economic losses. In Estonia, over 4, 000 work-related accidents are recorded annually,
and 428 fatalities were reported between 2001 and 2021. For example, work-related
accidents led to a loss of 141, 000 workdays and approximately 5.3 million euros in 2021.
Several studies across different countries have recently proposed automated data analytic
tools and machine learning based models to understand occupational hazards and predict
the likelihood and severity of accidents. These applications can identify high-risk
workers and ensure robust safety management systems across various industries, such
as construction and manufacturing. However, these proposed models are not directly
applicable to Estonia, and no specific tools can handle the local settings.
I aim to develop automated models based on machine learning techniques to
predict the severity of occupational accidents in Estonia. Raw dataset consists of 82, 641
work-related accidents, featuring 37 variables, and spans the period from 2002 to 2022.
The primary outcomes of this project include critical insights into the important factors and the development
of tailored machine learning models for occupations in specific economic sectors.
Therefore, I propose accurate and efficient automated tools that can handle the inherent
data challenges and ensure the significance of targeted modelling in accident prevention.
ProtectWise project illustrates the potential of understanding the data patterns, developing specific
data analytic tools and machine learning algorithms to improve decision-making in workplace
safety and developing cost-effective prevention strategies.



ProtectWise project execution steps:

For raw dataset preprocessing use the files 'Raw data preprocessing.ipynb' and 'data.pickle'.
Download file '2002-2022_encoded_csv.csv' from here https://www.dropbox.com/s/le2ixwygx9kq8yn/2002-2022_encoded_csv.csv?dl=0
and 'data.pickle' from here https://www.dropbox.com/s/obtcbv8etymvu1l/data.pickle?dl=0
You also need the dataset of occupation codes and business activities. Occupation codes dataset is named 'ametikood.csv'
and business activities dataset is named as 'emtak.csv'. Both you can find from Code folder here.

If you have runned the 'Raw data preprocessing.ipynb' you get a 'data.csv' as a preprocessed dataset to be used for training purposes.

You can use 'data.csv' to train models on the subsets of the data. Subset means that in the set there will be occupational
accidents only about specific occupations class in the specific economic sector (for example, only the accidents
of elementary workers in construction sector).
To divide dataset into subsets and train every subset that passes the margin of error test (on the test set target size)
you can use the file named 'Training combinations.ipynb'
There you can choose desired resampling method (ROS is preferred) or the method for preselecting features
(all features or only statistically significant features using Kendall's tau and chi-squared correlations).

After you have trained all the combinations you can choose the one you want to go forward with. For example
we choose F9 conbination (F - Construction sector and 9 - elementary workers)

To find better features for the F9 combination which affect the target class 1 F1 score the most you can use
'Important features selection.ipynb' which removes a feature one by one from the dataset to find which feature
improves the model and which is not.
This code saves all the results into and excel report and you can choose desired model or resampling technique
as well as the amount of iterations to be saved.
If you have found the best performing set of features you can use 'F9.ipynb' to train mudel, make predictions
and find out model-based feature importances which you can use to evaluate the risk level of an employee
by connecting data from Site Access Management System (AMS).

For the backround and details, please read the Masters Thesis: https://comserv.cs.ut.ee/ati_thesis/datasheet.php?id=77069
