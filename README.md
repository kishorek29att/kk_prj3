# Disaster Response Pipeline Project

[Github Link](https://github.com/kishorek29att/kk_prj3.git)

**Project Description:**

In this Disaster response project, i have analyzed disaster data from Figure Eight to build a model 
for an API that classifies disaster messages.

Data set contains real messages that were sent during disaster events. I have created a machine learning pipeline 
to categorize these events so that messages can be sent to an appropriate disaster relief agency.
Project includes a web app where an emergency worker can input a new message and get classification results in 
several categories. The web app will also display visualizations of the data. 

**Dataset**
Dataset used is from Figure Eight. 
Dataset has 2 files. disaster_categories.csv and disaster_messages.csv

**File Description**
- app
| - template
| |- master.html  # main page of web app
| |- go.html  # classification result page of web app
|- run.py  # Flask file that runs app

- data
|- disaster_categories.csv  # data to process 
|- disaster_messages.csv  # data to process
|- process_data.py    #  etl pipeline to load,clean and store the data into database
|- DisasterResponse.db   # database to save clean data to

- models
|- train_classifier.py  # machine learning pipeline the loads,builds,trains dataset and exports the final model as a pickle file 
|- classifier.pkl  # saved model (now deleted due to size issue) 

- README.md

**Implementation**
Project has 3 components:
1. ETL Pipeline: a. Loads the datsets
                 b. Cleans the Data
                 c. Stores cleansed data to SQLite database
2. ML Pipeline:  a. Loads data from database
                 b. Splits the dataset into training and test data sets
                 c. trains the model
                 d. Exports the final model as a pickle file
3. Web interface: a. build flask web app that enables user to enter disaster message and then view the categories.
                  b. provides visulaization of the data

### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/

**Acknowledgements**

I would like to thank Figure Eight and  Udacity for providing the dataset and tools.  


