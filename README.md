# complex-event-detection
=============================

  Complex-Event-Detection is a python library for implementing utilities which aim to fulfil a full Event Detection  workflow for analysing time series data. Complex-Event-Detection implements a series of training features, for the input time series, running variations of deviation detection algorithms in order to identify change points with a mixture of supervised and semi supervised methods so to achieve real time results , then behavior detection so to create two type of models, in order to find the most fitting model for the data at hand. Lastly a motif detection tool to extract motifs for summarized time series and for the deviation detection tool.  
  
===========
Description
===========	
For the development process, several python libraries will be used. In particular: `STUMPY <https://stumpy.readthedocs.io/en/latest/>`_, `MatrixProfile <https://matrixprofile.docs.matrixprofile.org/>`_ , `Pyscamp <https://pypi.org/project/pyscamp/>`_ and `Scikit-Learn <https://scikit-learn.org/stable/>`_. The aforementioned libraries are implemented in python3 (or provide python3 bindings to C++ code), thus the Event Detections module will adopt the same programming language. An installation of the CUDA toolkit8 is necessary for deploying the GPU-accelerated versions of the aforementioned libraries. 
The module consists of the following steps:

1. **Input/Output**

  This group of utilities includes all functions which are responsible for loading and storing time series to the disk. Moreover, it includes functions for loading/storing necessary metadata which are produced by any of the methods of this module and can be further processed.

2. **Preprocessing**

  Utilities regarding the handling and processing of the input data. Such functions handle filtering, resampling, adding noise, normalization and filling out missing values.
  
3. **Statistics**

  Utilities regarding the computation of useful statistics about the dataset, that implement variations of standard error measures, evaluating the performance of a regression   model, ranking time series.
   
4. **Plotting**   

  Functions that are used for the plotting of the results are presented, also include functions for plotting auxiliary information and helper functions for switching between     different data formats. 
  
5. **Basic pattern extraction**

  In this section, we discuss the implementation of functions related to pattern extraction. This includes functions for computing a matrix profile, but also functions related to the post-processing of a matrix profile. The latter refers to functions for discovering motifs/discords or segmenting a time series.
   
6. **Similarity**
  
  Utilities related to similarity search refer to functions which are responsible for performing proximity queries to a dataset. Queries that can be handled include finding the k-nearest neighbors of a given vector or time series. One example of such a query is computing the top k-nearest neighbors of a given subsequence in a multivariate time series, among all (or a subset of) subsequences in the same time series.

7. **Learning**
  
  In this set of utilities, we implement functions that build upon standard machine learning algorithms. In particular, functions contained in this module, handle tasks related 
  to approximating a time series by means of a regression model. Those functions are needed, for example, when we are trying to discover trends or changepoints.    

Complex Event Detection tools
========================
  The execution of the project starts with the presentation of the tools. 

1. **Deviation Detection**

  In this section, we present a tool for detecting segments of a time series where the behavior of a given target variable deviates much from the usual. We assume that certain 
  segments of the time series are labelled, representing the usual behavior of the variable in question. In this tool the user can find the list of variants that took place to implement it.
  *Self-supervised changepoint detection
  *Semi-supervised changepoint detection
  *Self-supervised modelling
  *Semi-supervised modelling
  *Deviation detection
  *Real-time deviation detection
  Link to the notebook:  `Deviation Detection <https://github.com/MORE-EU/more-pattern-extraction/blob/main/notebooks/deviation_detection.ipynb>`_


  
  The pattern discovery tool aims to detect interesting patterns in time series with labeled time intervals. In particular, given a time series which is divided into a sequence 
  of discrete segments, each one assigned to one of two classes, the goal is to detect patterns which correspond to distinguishable characteristics of one of the classes. The 
  intuition is that patterns that are representative of their respective class, should mostly appear in the time regions corresponding to that class.
  Link to the notebook: `Pattern Discovery <https://github.com/MORE-EU/more-pattern-extraction/blob/main/notebooks/interesting_patterns.ipynb>`_

2. **Behavior Detection**

  Given as input a time series, the time series segmentation tool finds points where a behavioral change is observed. Those points, partition the time series into discrete 
  segments. The user can specify the number of changepoints/segments which will be returned by the tool. In a scenario where ground truth, labelled, time series exist, the user 
  has the ability to calculate a cost, defined essentially as a distance function between the changepoints returned by the tool and the original changepoints (labels). This 
  allows for optimizing the parameters inherited by the matrix profile library in use cases where labelled data are available. 
  Link to the notebook: `Time Series Segmentation <https://github.com/MORE-EU/more-pattern-extraction/blob/main/notebooks/semantic_segmentation.ipynb>`_

3. **Motif Discovery**

  In this section, we present a tool for detecting and recognizing changepoints in a time series. Given a set of segments of the input time series, corresponding to periods of 
  time where a changepoint may occur, our tool essentially ranks those segments with respect to the possibility of containing a changepoint. This can be seen as a classification 
  task, where segments are classified with respect to whether they contain a changepoint or not.
  Link to the notebook: `ChangePoint Detection <https://github.com/MORE-EU/more-pattern-extraction/blob/main/notebooks/changepoint_detection.ipynb>`_
  

Documentation
=============

Source code documentation is available from `GitHub pages <https://more-eu.github.io/more-pattern-extraction/>`_
