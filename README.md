    ## Detecting Financial Fraud 
    ### - Intructions on this Repo

    1. Heap size error
    - run this command line before run jupyter notebook on command line:

    export PYSPARK_SUBMIT_ARGS=' --conf spark.sql.shuffle.partitions=700 --conf spark.default.parallelism=700 --driver-memory 30g --driver-cores 6 --executor-memory 30g --executor-cores 6 pyspark-shell'

    OR use the following configuration when create SparkContext

    #Create a spark Context class, with custom config
    - conf = SparkConf()
    - conf.set('spark.sql.debug.maxToStringFields', 100)
    - conf.set('spark.default.parallelism', 700)
    - conf.set('spark.sql.shuffle.partitions', 700)
    - conf.set("spark.driver.memory", '30g')
    - conf.set('spark.driver.cores', 8)
    - conf.set('spark.executor.cores', 8)
    - conf.set("spark.executor.memory", '30g')
    - sc = SparkContext.getOrCreate(conf)

2. ERROR PythonRunner: Python worker exited unexpectedly (crashed) java.net.SocketException: Connection reset

- Try to run several times

### TECH STACK: MLflow, Pyspark, Jupyter, SQL

- Training a machine learning model to detect fraudulent behavior means teaching it to recognize patterns in the data that indicate fraud. To do this, you provide the model with a large dataset of examples. The model then learns how the input data relates to these labels. Detecting financial fraud with machine learning can be tough because there aren't many confirmed cases of fraud to learn from. Since fraud is rare and often hard to spot, the model might not get enough examples to understand what fraud looks like. 
- If there are many more non-fraud examples than fraud ones, the model might end up labeling most things as non-fraud, which isn't helpful for catching fraud. To address this, you can balance the training data by adding more examples of fraud, either by oversampling existing fraud cases or creating synthetic data. You can also improve the model by crafting new features from the existing data that give better clues about whether something is fraudulent or not.

![Fraud_not_Fraud_each_type_transactions](https://user-images.githubusercontent.com/93171100/217422354-6c7bd4ab-bf6f-48b1-b534-4f745b0fe9e5.png)


Copyright: This is from Big Book of Machine Learning Use Cases - 2nd Edition. I follow the instruction in this book with my modification
https://www.databricks.com/blog/2019/05/02/detecting-financial-fraud-at-scale-with-decision-trees-and-mlflow-on-databricks.html

