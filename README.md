# WARNING: This repository is no longer maintained :warning:

> This repository will not be updated. The repository will be kept available in read-only mode.

# Demand forecasting using Deep Learning

This pattern demonstrates how to forecast the demand for cash vending machines using Deep Learning. It is important for financial institutions to ensure there are no cash-outs in the cash vending machines which can increase the revenue and enhance customer experience. Forecasting for cash vending machines can be demanding with various reasons for dip & spike in demand like weekday, weekend, location, month beginning & ending, holidays to name a few. The biggest challenge is to remember the pattern of withdrawals with respect to the reasons stated earlier. This is were Deep Learning comes into picture & we are referring to Recurrent Neural Network. The Long Short-Term Memory, or LSTM network, is a type of Recurrent Neural Network. Recurrent Neural Networks, or RNNs for short, are a special type of neural network designed for sequence problems. We will be creating a sequence prediction LSTM model which can predict the next value given an input sequence.

But why Deep Learning for this? We will need to mimic human behaviour of cash withdrawals by remembering the recent past and use the learnings to predict the future. We will create the Neural Network model with recurrent layers which will process the information through the looping architecture of the network and generate the corresponding output which will produce accurate forecast of cash demand which will in turn optimize cash replenishments of the cash vending machines. 

> A Brief about LSTM - Source - [Introduction to LSTM](https://machinelearningmastery.com/gentle-introduction-long-short-term-memory-networks-experts/)

`The Long Short-Term Memory, or LSTM, network is a type of Recurrent Neural Network. Recurrent Neural Networks, or RNNs for short, are a special type of neural network designed for sequence problems. Given a standard feedforward MLP network, an RNN can be thought of as the addition of loops to the architecture. For example, in a given layer, each neuron may pass its signal laterally (sideways) in addition to forward to the next layer. The output of the network may feedback as an input to the network with the next input vector and so on. The recurrent connections add state or memory to the network and allow it to learn and harness the ordered nature of observations within input sequences. Because of this ability to learn long term correlations in a sequence, LSTM networks obviate the need for a pre-specified time window and are capable of accurately modelling complex multivariate sequences. There are a number of RNNs, but it is the LSTM that delivers on the promise of RNNs for sequence prediction. It is why there is so much buzz and application of LSTMs at the moment.`

We will develop a deep learning model using Recurrent Neural Network which will produce the sequence per below.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/seq_pred.PNG)

After completing this pattern, the developer will understand how to :

* Create a Deep Learning model using LSTM.
* Understand & tune the hyper parameters of the model.
* Transfer learning using LSTM.
* Generate new forecasts on new data using the same model & weights.
* Cross Validation technique for evaluating accuracy.
* GridSearch technique for fit & score using different parameters.

# Architecture Diagram

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/architecture.PNG)

* User uploads the first input csv file onto object storage.
* User executes the notebook which will create a deep learning model and churn out forecasts.
* User uploads the second input file onto object storage.
* User runs the notebook again using transfer learn of deep learning model and generates the forecasts.
* User will learn how to create a deep learning model to be used on different data sets & achieve good accuracy.


## Included components

* [Keras](https://keras.io/): The Python Deep Learning library.

* [Tensorflow](https://www.tensorflow.org/): An open-source software library for Machine Intelligence.

* [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.

* [IBM Cloud Object Storage](https://console.bluemix.net/catalog/services/cloud-object-storage): An IBM Cloud service that provides an unstructured cloud data store to build and deliver cost effective apps and services with high reliability and fast speed to market. This code pattern uses Cloud Object Storage.

* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.

## Featured technologies

* [Deep Learning](https://www.ibm.com/cloud/deep-learning): Design complex neural networks then experiment at scale to deploy optimized deep learning models, within Watson Studio.
* [Data Science](https://developer.ibm.com/code/technologies/data-science/): Systems and scientific methods to analyze structured and unstructured data in order to extract knowledge and insights.
* [Analytics](https://developer.ibm.com/code/technologies/analytics/): Analytics delivers the value of data for the enterprise.
* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.

# Watch the Video

[![](http://img.youtube.com/vi/ToQiQdEGtzM/0.jpg)](https://youtu.be/ToQiQdEGtzM)

# Steps

Follow these steps to setup and run this code pattern. The steps are
described in detail below.

1. [Create an account with IBM Cloud](#1-create-an-account-with-ibm-cloud)
1. [Create a new Watson Studio project](#2-create-a-new-watson-studio-project)
1. [Create the notebook](#3-create-the-notebook)
1. [Add the data](#4-add-the-data)
1. [Insert the dataframe](#5-insert-the-dataframe)
1. [Run the notebook](#6-run-the-notebook)
1. [Analyze the results](#7-analyze-the-results)
1. [Terminology](#8-terminology)

## 1. Create an account with IBM Cloud

Sign up for IBM [**Cloud**](https://console.bluemix.net/). By clicking on create a free account you will get 30 days trial account.

## 2. Create a new Watson Studio project

Sign up for IBM's [Watson Studio](http://dataplatform.ibm.com/). 

Click on `New project` and select `Data Science` as per below.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/new_project.PNG)

Define the project by giving a Name and hit `Create`.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/define_project.PNG)

## 3. Create the notebook

* Open [IBM Watson Studio](https://dataplatform.ibm.com).
* Click on `Create notebook` to create a notebook.
* Select the `From URL` tab.
* Enter a name for the notebook.
* Optionally, enter a description for the notebook.
* Enter this Notebook URL: https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/notebook/LSTM_PATTERN.ipynb
* Select the runtime of (4vCPU and 16GBRAM).
* Click the `Create` button.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/create_notebook.PNG)

## 4. Add the data

Use `Find and Add Data` (look for the `10/01` icon)
and its `Files` tab. From there you can click
`browse` and add data files from your computer.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/add_file.png)

Note: The data files are in the `data` directory. `We need to insert sample_data.csv first followed by holdout_sample.csv as called out in the notebook.` The data values are sorted & aggregated on a daily basis & the date attribute has been intentionally omitted from the data. The data was generated using random numbers to be used for this pattern.
> Citation : The dataset is created & owned by R K Sharath Kumar, IBM India Software Labs. 

## 5. Insert the DataFrame

Select the cell below `2. Read the Data & convert it into Dataframe` section in the notebook.

Use `Find and Add Data` (look for the `10/01` icon) and its `Files` tab. You should see the file names uploaded earlier. Make sure your active cell is the empty one created earlier. Select `Insert to code` (below your file name). Click `Insert pandas DataFrame` from drop down menu.

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/insert%20df.PNG)

## 6. Run the notebook

When a notebook is executed, what is actually happening is that each code cell in
the notebook is executed, in order, from top to bottom.

Each code cell is selectable and is preceded by a tag in the left margin. The tag
format is `In [x]:`. Depending on the state of the notebook, the `x` can be:

* A blank, this indicates that the cell has never been executed.
* A number, this number represents the relative order this code step was executed.
* A `*`, this indicates that the cell is currently executing.

There are several ways to execute the code cells in your notebook:

* One cell at a time.
  * Select the cell, and then press the `Play` button in the toolbar.
* Batch mode, in sequential order.
  * From the `Cell` menu bar, there are several options available. For example, you
    can `Run All` cells in your notebook, or you can `Run All Below`, that will
    start executing from the first cell under the currently selected cell, and then
    continue executing all cells that follow.
    
## 7. Analyze the results

In this section, we will review the accuracy score of the model which has generated similar `Mean Squared Error` values for training & validation data. We have achieved > 90% accuracy `(Mean Absolute Percentage Error)` with minimal training and optimal hyperparameters tuning which has resulted in striking a balance between accuracy & computation time. 

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/accuracy_check.PNG)

We can also see the `loss metric (error score)` for training & validation data has a steady descent and converge at the end which means the learning from training data is effectively tested on the validation data. The optimum accuracy has been achieved with the configueration of the deep learning neural network architecture. 

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/loss.PNG)

The accuracy can be further enhanced using cross validation & Grid Search techniques however they are computationally intensive and should be performed on a `GPU`.

We can save the entire model, weights of the model, model architecture etc onto the storage to be reused at a later stage. 

We have also demonstrated another concept called `Transfer Learning` where we have used the trained model on new data and were able to generate accurate results. This is helpful if you have to generate forecasts quickly without spending time on training and not compromise on accuracy. `Re-training would be required as per the variance in the data.`

## 8. Terminology

* `One epoch` = one forward pass and one backward pass of all the training examples

* `Batch Size` = The number of training examples in one forward/backward pass. The higher the batch size, the more memory space you'll need.

* `Number of iterations` = number of passes, each pass using [batch size] number of examples. To be clear, one pass = one forward pass + one backward pass (we do not count the forward pass and backward pass as two different passes). Example: if you have 1000 training examples, and your batch size is 500, then it will take 2 iterations to complete 1 epoch.

* `Neurons` = memory cells or computation cells or transmitters

* `Activation` = Which controls the initializing of weights/neurons. (most popular ones are Tanh(Range(-1,1)) & ReLu(Range(0,1))

* `Loss/Metric` = A metric is a function that is used to judge the performance of your model. Metric functions are to be supplied in the metrics parameter when a model is compiled.

* `Compilation` = consolidate the learnings of the model from different layers. 

* `Optimizers` = Which controls the learning ability of the model. (Adam & RMSprop are widely used for regression problems)

* `Stateful/Stateless` = Whether to remember the previous value to predict next value. 


# Troubleshooting

[See DEBUGGING.md.](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/DEBUGGING.md)

# Learn more

* **Artificial Intelligence Code Patterns**: Enjoyed this Code Pattern? Check out our other [Artificial Intelligence Code Patterns](https://developer.ibm.com/code/technologies/artificial-intelligence/)
* **AI and Data Code Pattern Playlist**: Bookmark our [playlist](https://www.youtube.com/playlist?list=PLzUbsvIyrNfknNewObx5N7uGZ5FKH0Fde) with all of our Code Pattern videos
* **Watson Studio**: Master the art of data science with IBM's [Watson Studio](https://www.ibm.com/cloud/watson-studio)
* **Spark on IBM Cloud**: Need a Spark cluster? Create up to 30 Spark executors on IBM Cloud with our [Spark service](https://console.bluemix.net/catalog/services/apache-spark)

# License

This code pattern is licensed under the Apache Software License, Version 2.  Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the Developer [Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.txt).

Check the [ASL FAQ link](http://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN) for more details.
