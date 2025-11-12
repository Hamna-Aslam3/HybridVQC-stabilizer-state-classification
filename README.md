# HybridVQC-stabilizer-state-classification
Code for the classifications carried out in the paper "A hybrid variational quantum circuit approach for stabilizer states classifiers".

Each file corresponds to one one type of classification carried out within the paper. 

The current code represents the choice of states for the first result in each type of classification. Depending upon the state to be identified, the labels of the states can be swapped in the QuantumStateDataset function within the files. The ansatz and hyperparameters of the hybrid VQC as well as the number of samples in the dataset for each result also vary depending upon the state to be identified. 
