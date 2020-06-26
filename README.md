# Data Science NanoDegree Capstone

### Overview

This repository is the code for the Udacity Data Science Nano Degree. <br>
Sparkify is a browser based, online music streaming service. The aim of the project is to predict users who leave the service ("churn"), by using Spark. <br>

### Data

The data is located on an Amazon S3 bucket. Udacity provides 2 datasets <br>
- <code>mini_sparkify_event_data.json</code> is a small snippet of the larger dataset (~123 MB)
- <code>sparkify_event_data.json</code> is the full dataset
<br>
Below is the data schema with a little bit of information about each column. <br>
 - artist:name of the artis
 - auth: type of authentication
 - firstName: user first name
 - gender:user gender
 - itemInSession: unknown
 - lastName: user last name
 - length: length of the current session
 - level: paid/free account
 - location: ip address location
 - method: unknown
 - page: current action being performed
 - registration: unique registration id
 - sessionId: unique session id
 - song: song name
 - status: unknown
 - ts: timestamp
 - userAgent: browser and system used
 - userId: unique ID
 <br>

 ### Method
  I  worked on the smaller dataset first on my local machine (most of the development and testing was done locally). Later all the code was imported to an AWS EMR to be executed on the complete dataset. <br>
Page and Length were the main columns I used to obtain information from. I performed a groupby method on the different pages, grouped by userId and gender. All the variables were converted to integers. <br>

## Files 

- <code>ETL_ML_Local.html --</code> The HTML export of the jupyter notebook pipeline that was written using my local machine 
- <code>ETL_ML_Local.ipynb --</code> The  jupyter notebook pipeline that was written using my local machine 
- <code>ETL_ML_AWS.html --</code> The HTML export of the jupyter notebook pipeline that was run on the AWS EMR Cluster
- <code>ETL_ML_AWS.ipynb --</code> The  jupyter notebook pipeline that was written using 

<b>The AWS EMR Configuration JSON:</b>
<code>[{"classification":"livy-conf", "properties":{"livy.server.session.timeout":"8h"}, "configurations":[]},{"classification":"spark", "properties":{"spark.executor.memory":"8g", "spark.driver.memory":"24g", "spark.pyspark.virtualenv.enabled":"True"}, "configurations":[]}] </code>

### Spark Environment
- Python 3.7.6
- spark 2.4.5
- numpy 1.18.1
- pandas 1.0.1
- seaborn 0.10.0
- scikit-learn 0.22.1
- matplotlib 3.1.3

To run the code, you have to change variables for the path in the ETL_ML_Loca.ipynb for the data path ( that is my local directory path).