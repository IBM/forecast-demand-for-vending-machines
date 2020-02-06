# Short title

Demand Forecasting using Deep Learning

# Long title

Forecasting demand for cash vending maching using IBM Watson.

# Author

* Sharath Kumar RK sharrkum@in.ibm.com
* Manjula Hosurmath mhosurma@in.ibm.com

# URLs

### Github repo

* https://github.com/IBM/forecast-demand-for-vending-machines

### Other URLs

* Video URL - https://youtu.be/ToQiQdEGtzM
* Demo URL  - https://youtu.be/ToQiQdEGtzM

# Summary

This pattern demonstrates how to forecast the demand for cash vending machines using Deep Learning. It is important for financial institutions to ensure there are no cash-outs in the cash vending machines which can increase the revenue and enhance customer experience. 

# Technologies

* Artificial Intelligence
* Data Science
* Deep Learning
* Analytics

# Description

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

# Flow

![](https://github.com/IBM/forecast-demand-for-vending-machines/blob/master/doc/source/images/architecture.PNG)

* User uploads the first input csv file onto object storage.
* User executes the notebook which will create a deep learning model and churn out forecasts.
* User uploads the second input file onto object storage.
* User runs the notebook again using transfer learn of deep learning model and generates the forecasts.
* User will learn how to create a deep learning model to be used on different data sets & achieve good accuracy.

# Instructions

Find the detailed steps for this pattern in the [readme file](https://github.com/IBM/forecast-demand-for-vending-machines/edit/master/README.md). The steps will show you how to:

* Create a Deep Learning model using LSTM.
* Understand & tune the hyper parameters of the model.
* Transfer learning using LSTM.
* Generate new forecasts on new data using the same model & weights.
* Cross Validation technique for evaluating accuracy.
* GridSearch technique for fit & score using different parameters.

# Components and services

* [Keras](https://keras.io/): The Python Deep Learning library.

* [Tensorflow](https://www.tensorflow.org/): An open-source software library for Machine Intelligence.

* [IBM Watson Studio](https://www.ibm.com/cloud/watson-studio): Analyze data using RStudio, Jupyter, and Python in a configured, collaborative environment that includes IBM value-adds, such as managed Spark.

* [IBM Cloud Object Storage](https://console.bluemix.net/catalog/services/cloud-object-storage): An IBM Cloud service that provides an unstructured cloud data store to build and deliver cost effective apps and services with high reliability and fast speed to market. This code pattern uses Cloud Object Storage.

* [Jupyter Notebooks](http://jupyter.org/): An open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text.

# Runtimes

* Spark
* Python

# Related IBM Developer content

* **Artificial Intelligence Code Patterns**: Enjoyed this Code Pattern? Check out our other [Artificial Intelligence Code Patterns](https://developer.ibm.com/code/technologies/artificial-intelligence/)
* **AI and Data Code Pattern Playlist**: Bookmark our [playlist](https://www.youtube.com/playlist?list=PLzUbsvIyrNfknNewObx5N7uGZ5FKH0Fde) with all of our Code Pattern videos
* **Watson Studio**: Master the art of data science with IBM's [Watson Studio](https://www.ibm.com/cloud/watson-studio)
* **Spark on IBM Cloud**: Need a Spark cluster? Create up to 30 Spark executors on IBM Cloud with our [Spark service](https://console.bluemix.net/catalog/services/apache-spark)

# Related links

* [Python](https://www.python.org/): Python is a programming language that lets you work more quickly and integrate your systems more effectively.
