# HybridVQC-stabilizer-state-classification
Code for the classifications carried out in the paper "A hybrid variational quantum circuit approach for stabilizer states classifiers".

Each file corresponds to one one type of classification carried out within the paper. 

The current code represents the choice of states for the first result in each type of classification. Depending upon the state to be identified, the labels of the states can be swapped in the QuantumStateDataset function within the files. The ansatz and hyperparameters of the hybrid VQC as well as the number of samples in the dataset for each result also vary depending upon the state to be identified. 


| Class no. wrt images (wrt code) | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:-------------------------------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|             Full sep            |           99          |          98          |      0.04     |     0.06     |      3000      |                    300                   |     0.002     |     20     |                 4                |         54        |
|               AB-C              |           98          |          97          |      0.06     |     0.09     |      5000      |                    300                   |     0.002     |     20     |                 4                |         33        |
|               A-BC              |           98          |          97          |      0.05     |     0.08     |      3000      |                    300                   |     0.002     |     20     |                 4                |         54        |
|               AC-B              |           99          |          99          |      0.03     |     0.05     |      4000      |                    300                   |     0.002     |     20     |                 4                |         69        |
|                W                |          100          |          100         |      0.00     |     0.01     |      5000      |                  300,100                 |     0.002     |     20     |                 4                |         37        |
|                6                |           93          |          92          |      0.21     |     0.22     |      7200      |                  400,50                  |     0.001     |     10     |                 4                |         19        |
