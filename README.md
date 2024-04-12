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


       python3 train_smooth_embeddings.py 

Usage:

    train_smooth_embeddings.py [-h] [--graphname [GRAPHNAME]]
                                  [--embedding_size EMBEDDING_SIZE]
                                  [--depth DEPTH] [--method [METHOD]]
                                  [--sketchsize SKETCHSIZE]

    
The default arguments are Cora, embedding size 5, depth 2, default method L2, and sketchsize 1. (See the paper for details.)

3. **Node classification**

    python3 node_classification.py

4. **Link prediction**

