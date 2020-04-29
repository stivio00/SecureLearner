# Introduction
This project is a proof of concept for capturing the time delays between the characters in aa typed password. And then build an "in-between-character-delay-vector" to train a statistical model to validate password authenticity.
This feature vector is a clection of times in milliseconds. First we start capturing the samples using a special tool.
After input we save a measure file and train a model (supervised learning) to generate a model. Withit test some intruders.

# Problem statement
Is it possible to characterize the writing pattern of a person?
Is it possible to identify features to detect if the password was typed by the same person?
Also, can we train a machine learning model to detect if this feature is made by the same person and validate the password?

# Plans and artifacts
- Debugging Gui (index.html): a small webpage to capture password and generate relevant features and save them in CSV file.
- Machine learning model to validate password (train.py): a sci-kit-learn project to learn security features
- Proof of concept (auth.html): client-side validation with the trained model.

# Future plans
- Implement a server site version of this prototype.
- usea a neural network to detect automatically outliers (unsupervised learning without labels)

## Atifacts and use cases
- Debuggin GUI Console (index.html):
    This page is to capture person behaviour. For example, yo can type your message (e.g. hello world) and click "Record!"
    for capturing the feature veector in a csv buffer. then click "Clean".
    And repeat the process until you have at leats 10 trys
    Then you can click "Download csv" to save the  samples
    Finally you can click "Clean and start over again" to clena everthing and repeat the process for other persons.

- Trainning Notebook (train.ipynb): 
    This Jupyter notebook is a csv analyser, you can slect and open a previusly  generated cvs created from the other tool.
    Here yo can get some insigth and parameters from the data set. Like means, mode, std dev and other statistically data from each sample.
    Trainning a personal model, and create threshholds to predict outliers in the dataset.
    This tool will generate the model.json used in a authentication app.

- Authentication (auth.html):
    Sample you need to load the model.json, and test the result. Good luck.

    As a general workflow:
    ![Workflow](/info_flow.png "Workflow")