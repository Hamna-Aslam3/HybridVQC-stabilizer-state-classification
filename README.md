# HybridVQC-stabilizer-state-classification
Code for the classifications carried out in the paper "A hybrid variational quantum circuit approach for stabilizer states classifiers".

Each file corresponds to one one type of classification carried out within the paper. 

The current code represents the choice of states for the first result in each type of classification. Depending upon the state to be identified, the labels of the states can be swapped in the QuantumStateDataset function within the files. The hyperparameters of the hybrid VQC as well as the features of the dataset for each result also vary depending upon the state to be identified. Full details of the hyperparameters and dataset features selected for each result are shown in the tables below. The tables are numbered in correspondence with the tables in the paper.

The first column specifies the particular classification. The next four columns give the training and testing accuracy as well as loss. The sixth column specifies the number of training samples used (note that the number of training and test samples was always kept equal). The seventh column specifies the number of neurons in the hidden layers of the post-processing classical NN, with the number of neurons for each hidden layer separated by a comma. The next two columns specify the learning rate and the batch size. Column number ten gives the number of ansatz layers employed in the quantum circuit. Finally, the last column details the number of training epochs that were run in order to achieve the corresponding result (note that the training was run until the loss stayed steady for atleast 15 runs or the loss in the next step was greater than that of the previous step.)

**Table I: LU orbit of 3 qubit GHZ state against LU orbit of other 3 qubit states**

| State Name | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:-------------------------------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|             Fully separable     |           99          |          98          |      0.04     |     0.07     |      3000      |                    300                   |     0.002     |     20     |                 4                |         54        |
|               AB-C              |           98          |          97          |      0.06     |     0.09     |      5000      |                    300                   |     0.002     |     20     |                 4                |         33        |
|               A-BC              |           98          |          97          |      0.06     |     0.08     |      3000      |                    300                   |     0.002     |     20     |                 4                |         54        |
|               AC-B              |           99          |          99          |      0.04     |     0.05     |      4000      |                    300                   |     0.002     |     20     |                 4                |         69        |
|                W                |          100          |          100         |      0.00     |     0.01     |      5000      |                  300,100                 |     0.002     |     20     |                 4                |         37        |


**Table II: LU orbit of 3 qubit states against 3 qubit Hilbert space**

| State Name | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:----------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
| Fully sep. |           90          |          89          |      0.30     |     0.34     |      9000      |                  500,500                 |     0.001     |     10     |                 4                |         30        |
|    AB-C    |           98          |          97          |      0.07     |      0.1     |      4500      |                    400                   |     0.001     |     10     |                 4                |         40        |
|    A-BC    |          100          |          99          |      0.03     |     0.04     |      4500      |                    400                   |     0.001     |     10     |                 4                |         38        |
|    AC-B    |           97          |          95          |      0.1      |     0.16     |      4500      |                    400                   |     0.001     |     10     |                 4                |         78        |
|      W     |           84          |          83          |      0.49     |     0.51     |      7500      |                  200,100                 |     0.001     |     10     |                 4                |         46        |
|     GHZ    |           97          |          97          |      0.08     |     0.09     |      3500      |                    350                   |     0.001     |     10     |                 4                |         55        |


**Table IV: Entanglement classes of 4 qubit graphs states**

| Class no.  | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:----------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|     1      |          100          |          100         |       0       |       0      |      4800      |                  400,150                 |     0.001     |     10     |                 4                |         6         |
|     2      |          100          |          100         |       0       |       0      |      4800      |                  400,150                 |     0.001     |     10     |                 4                |         6         |
|     3      |           99          |          99          |      0.02     |     0.02     |      4800      |                  400,150                 |     0.001     |     10     |                 4                |         3         |
|     4      |           98          |          98          |      0.05     |     0.06     |      4800      |                  400,150                 |     0.001     |     10     |                 4                |         4         |
|     5      |           98          |          98          |      0.07     |     0.07     |      5280      |                  400,250                 |     0.001     |     10     |                 4                |         4         |
|     6      |          100          |          100         |       0       |       0      |      2880      |                  400,150                 |     0.001     |     10     |                 4                |         4         |


**Table V: Entanglement classes of 4 qubit stabilizer states**

| Class no. | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:---------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|     1     |           97          |          96          |      0.1      |     0.13     |      4800      |                  400,50                  |     0.001     |     10     |                 4                |         32        |
|     2     |           98          |          98          |      0.07     |     0.08     |      9600      |                  500,150                 |     0.001     |     10     |                 4                |         61        |
|     3     |           90          |          90          |      0.32     |     0.32     |      7200      |                  400,50                  |     0.001     |     10     |                 4                |         14        |
|     4     |           95          |          95          |      0.15     |     0.16     |      14400     |                  500,150                 |     0.001     |     10     |                 4                |         67        |
|     5     |          97           |          97          |      0.11     |     0.12     |      11040     |                  500,150                 |     0.001     |     10     |                 4                |         22        |
|     6     |           93          |          92          |      0.21     |     0.22     |      7200      |                  400,50                  |     0.001     |     10     |                 4                |         19        |


**Table VI: LU orbit of 4 qubit graph state against LU orbit of other 4 qubit graph states**

| Class no.  | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:----------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|     1      |           94          |          93          |      0.19     |     0.22     |      7200      |                  400,50                  |     0.001     |     10     |                 4                |         9         |
|     2      |           95          |          94          |      0.20     |     0.21     |      13200     |                  400,50                  |     0.001     |     10     |                 4                |         21        |
|     3      |           90          |          89          |      0.32     |     0.35     |      5280      |                  400,50                  |     0.001     |     10     |                 4                |         18        |
|     4      |           95          |          95          |      0.16     |      0.17    |      15600     |                  450,50                  |     0.001     |     10     |                 4                |         36        |
|     5      |           90          |          89          |      0.31     |     0.33     |     15600      |                  450,50                  |     0.001     |     10     |                 4                |         27        |
|     6      |           90          |          90          |      0.31     |     0.34     |      5280      |                  400,50                  |     0.001     |     10     |                 4                |         25        |


**Table VII: LU orbit of 4 qubit graph state against 4 qubit Hilbert space**

| Class no.  | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:----------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|     1      |           95          |          94          |      0.14     |     0.19     |      6000      |                  350, 50                 |     0.001     |     10     |                 4                |         13        |
|     2      |           93          |          91          |      0.23     |     0.27     |      6000      |                  350, 50                 |     0.001     |     10     |                 4                |         24        |
|     3      |          100          |          99          |      0.02     |     0.03     |      6000      |                  350, 50                 |     0.001     |     10     |                 4                |         10        |
|     4      |           89          |          88          |      0.35     |     0.37     |      15600     |                  450,50                  |     0.001     |     10     |                 4                |         41        |
|     5      |           98          |          97          |      0.08     |     0.09     |      8400      |                  350, 50                 |     0.001     |     10     |                 4                |         11        |
|     6      |          100          |          99          |      0.02     |     0.02     |      8400      |                  350, 50                 |     0.001     |     10     |                 4                |         9         |

**Table VIII: LU orbit of star graph state against LU orbits of the rest of graph states**

| No. of qubits | Training Accuracy (%) | Testing Accuracy (%) | Training Loss | Testing Loss | No. of Samples | Number of Hidden Neurons in Classical NN | Learning Rate | Batch Size | No. of Layers of Quantum Circuit | No. of Epochs Run |
|:-------------:|:---------------------:|:--------------------:|:-------------:|:------------:|:--------------:|:----------------------------------------:|:-------------:|:----------:|:--------------------------------:|:-----------------:|
|       4       |          99          |          99          |      0.04     |     0.05     |      9600      |                  200,50                  |     0.001     |     10     |                 4                |         14        |
|       5       |           97          |          97          |      0.09     |     0.09     |      14400     |                  300,50                  |     0.001     |     10     |                 4                |         11        |
|       6       |           96          |          96          |      0.13     |     0.15     |      32400     |                  500,50                  |     0.001     |     10     |                 4                |         11        |
