## EECS 731 Project 2: Classification by Matthew Taylor

### Overview

This project is meant to serve as an introduction to classification. Information about Shakespeare's plays will be used to train a model that can predict which actor delivered a given line. This project also provides more exposure to foundational data science concepts like data cleaning and feature engineering.

### Approach

I began by downloading [this dataset](https://www.kaggle.com/kingburrito666/shakespeare-plays). I noticed some of the rows had missing values, so I removed those. Then, I mapped the names of each play and each player to unique integer identifiers. Then, I split the act, scene, and line numbers of each entry into separate columns. Next, I split the data into training and testing sets with an 80/20 split. After that, I created a random forest. I decided to use a random forest because of its speed and accuracy in classification tasks. I trained the random forest to predict the player given the name of the play and the act, scene, and line numbers. This is a direct result of a key observation I made early on. I noticed many consecutive lines were spoken by the same player. I chose not to incorporate the line being spoken because it would greatly increase the complexity of the project. The text encoding/vectorization alone would take far longer than any other part of the project, and as we'll see, the model produced impressive results even without incorporating text.

### How to Run

This project was written in a Jupyter Notebook running Python 3.7.2. This project relies on a small number of modules, which can be installed by running this command:
```
pip3 install -r requirements.txt
```

Once the requirements are installed, each of the cells in the Jupyter Notebook can be executed. However, this is not required as each cell has already been executed and the results are shown.

### Results

The random forest only took about 5 minutes to train and had a test accuracy of about 72%. With about 900 possible players, the fact that this model can correctly predict the player that often is astounding. This lab did a fantastic job of demonstrating the simplicity and accuracy of random forests and classifiers in general.

### Future Work and Optimizations

The most obvious next step for this project is to incorporate the line being spoken. This would involve a form of text encoding/vectorization, but it would also increase the dimensionality of the model, and hopefully the testing accuracy. Another possible route is to implement a second machine learning algorithm. The second algorithm would be trained and tested with the same data and the accuracy of the two models could be compared.
