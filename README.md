# [SkillFinder](http://skillfinder1.azurewebsites.net/)

# Data Collection
Data was collected using Selenium web crawler. Job postings on linkedin and jobstreet which are related to “Data Science" are collected. 
The steps and procedure could be found in the notebook [collect_data](https://github.com/czlee0223/skill_finder/blob/master/notebook/collect_data.ipynb).  

# Data Preprocessing
Preprocessing steps are as shown below:
1. Filtered the unrelated roles.
2. Approrpriately Splitting Data.
3. Format the data to pandas readable format and save as json file.
4. Generate entity rules for later usage.

Detail procedures could be found in notebook [data_formatting](https://github.com/czlee0223/skill_finder/blob/master/notebook/Data%20formatting%20and%20Preprocessing.ipynb)
and [location_preprocessing](https://github.com/czlee0223/skill_finder/blob/master/notebook/Location%20Preprocessing.ipynb).  

# Modelling
Manually finding jobs skills from the data could be very inefficient and troublesome. Thus, natural langangue processing model was built to identify the skills from
the description.  

Procedures:
1. NLP information extraction model is built to identify the skills.
2. This is a named entity recognition model which is based on spacy.
3. The collected data is split to train and test data
4. Entity rules has been generated during data preprocessing and 
custom entity ruler is built before training the model.
5. Model trained has an accuracy around 90%.

Detail procedures could be found in notebook [Modelling](https://github.com/czlee0223/skill_finder/tree/master/notebook/Modelling).

# DataBase
- Predictions outcome are formatted into dataframe based on the roles.  
- All dataframes are converted to sql and pushed to Azure database for later front end usage.

Detail procedures could be found in notebook [convert_to_sql](https://github.com/czlee0223/skill_finder/blob/master/notebook/ConvertToSQL.ipynb).

Front end respository could be found [here](https://github.com/czlee0223/skillFinderV1_frontend).
