### Code for Smooth Pair Sampling

## Prerequisites

1. **Python packages** 
The code should work with a standard Python3 version. In addition, one needs some widely used libraries like pandas, numpy, networkx, scikit-learn, etc. The file requirements.txt gives a list of the package versions we used.

2. **Graphs** The provided package contains the [Cora graph](https://graphsandnetworks.com/the-cora-dataset/) and instructions how to preprocess it. The [Citeseer graph](http://networkrepository.com/citeseer.php) can be preprocessed using the same code. For the other 4 graphs used in the experimental evaluation, we refer to the respective notebooks. They contain instructions where to download and unpack the data. 

## Running the code

1. **Preprocess a graph**
 
    
       python3 preprocess.py [--graphname < name >]

The default name is Cora.

2. **Train embeddings**


       python3 generate_embeddings.py 

Usage:

    generate_embeddings.py [-h] [--graphname [GRAPHNAME]]
                                  [--embedding_size EMBEDDING_SIZE]
                                  [--depth DEPTH] [--method [METHOD]]
                                  [--sketchsize SKETCHSIZE]

    
The default arguments are Cora, embedding size 5, depth 2, default method L2, and sketchsize 1. (See the paper for details.)

3. **Train a linear model**

    python3 linear_svm_training.py

Train and evaluate a linear SVM model for node classification for a given graph and a given method for embedding generation. The parameters are the same as above, just type the option `--help` for instructions.

4. (Optional) *Train a kernel model*

For comparison, one can also train a kernel SVM model with
    
    python3 kernel_svm_training.py
