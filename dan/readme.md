Deep Learning 
=

Overview
--------

To gain a better understanding of deep learning, we're going to look at deep averaging networks (DAN).  These are a very simple
framework, but they work well for a variety of tasks and will help
introduce some of the core concepts of using deep learning in
practice.

In this homework, you'll use Pytorch to implement a DAN embedder for
determining the answer to a Quizbowl question.

You'll turn in your code on Gradescope. This assignment is worth 35 points.

Dataset
----------------

We're working with the same data as before, except this time (because we need to use representations) we will need to create a vocabulary explicitly (like we did for the earlier tf-idf homework).  However, we'll do that for you.

Pytorch DataLoader
----------------

In this homework, we use Pytorch's build-in data loader to do data
mini-batching, which provides single or multi-process iterators over the
dataset(https://pytorch.org/docs/stable/data.html).

The data loader includes two functions, `batchify()` and `vectorize()`. For
each example, we need to vectorize the question text into a vector using the 
vocabulary. In this assignment, you need to write the `vectorize()` function
yourself. We provide the `batchify()` function to split the dataset into
mini-batches.

What's the loss function?
----------------

Given your question $$q_i$$, a positive match $$p^{+}_i$$ and many negative examples $$p_{i,1}^{-} \dots p_{i,n}^{-}$$, you need to optimize $$-\log{\frac{e^{q_i \cdot p^{+}_i}{e^{q_i \cdot p^{+}_i} + \sum_j e^{q_i \cdot p_{i,j}^{-}}}

What you have to do
----------------

**Coding**: (30 points)
1. Understand the structure of the code.
2. Write the data `vectorize()` funtion.
3. Write DAN model initialization. 
4. Write model `forward()` function.
5. Write the model training/testing function. We don't have unit tests for this part, but it's necessary to get it correct to achieve reasonable performance.

**Analysis**: (5 points)
1. Report the accuracy on the dev set. 
2. Look at the development set and give some examples and explain the possible reasons why these examples are predicted incorrectly. 


Pytorch install
----------------
In this homework, we use Pytorch again.  

You can install it via the following command (linux):
```
conda install pytorch torchvision -c pytorch
```
or 
```
conda install pytorch=0.4.1 torchvision -c pytorch
```

If you are using MacOS or Windows, please check the Pytorch website for installation instructions.


For more information, check
https://pytorch.org/get-started/locally/.

Extra Credit
----------------

(Please code extra credit part separately, not for submission to submit server) For extra credit, you need to initialize the word representations with word2vec,
GloVe, or some other representation.  Compare the final performance
based on these initializations *and* see how the word representations
change. Write down your findings in analysis.pdf.

What to turn in 
----------------

TODO: Update for Gradescope

0. Submit your model file
1. Submit your `dan.py` file.
2. Submit your `analysis.pdf` file. (Please make sure that this is **PDF** file!)

    No more than one page 
    
    Include your name at the top of the pdf


