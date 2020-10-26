# LDSA Poject, Team 6

In this project we perform sentiment analysis on a data set of reddit comments. We used Spark and HDFS to implement the analysis. A data set loaded to HDFS was used for the experiments. Jupyter notebook named ```reddit_analysis.ipynb``` was used to perform all the scalability experiments. The number of workers was changed outside of the code.

## Prequisites

First step to execute the analysis is to set up HDFS and Spark cluster and load in reddit comments that are supposed to be processes. The master machine is required to have [sparkMeasure](https://github.com/lucacanali/sparkMeasure) package installed. This package is used to obtain information about spark performance.

For the analysis we use the [nltk](https://www.nltk.org/index.html) package, which also should be installed prior to running the experiment. In particular we use the [vader](https://www.nltk.org/_modules/nltk/sentiment/vader.html) lexicon. If it's not already downloaded on the master machine, following commands can be executed with python/jupyter-notebook:
```
>>> import nltk
>>> nltk.download('vader_lexicon')
```

## How to run the analysis

The program can be then run using jupyter-notebook. [sparkMeasure](https://github.com/lucacanali/sparkMeasure) requires the notebook to be started using the following command:
```
$ <path-to-spark-directory>/bin/pyspark --packages ch.cern.sparkmeasure:spark-measure_2.11:0.14
```
The code can be then executed in order to analyse the dataset which filepath is specified as a parameter to  the```SparkSession.read.json``` routine.
