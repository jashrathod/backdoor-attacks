# Backdoor Attacks

This project focuses on designing a backdoor detector for BadNets using the pruning defense strategy. Below you'll find a brief description of each file in the repository and instructions on how to run the code.

1. [**bd_net.h5**](./bd_net.h5): Contains the original backdoored neural network model.
2. [**bd_weights.h5**](./bd_weights.h5): Holds the weights for the backdoored neural network model.
3. [**model_repaired_threshold_10.h5**](./model_repaired_threshold_10.h5): A 'repaired' version of the BadNet model with a pruning threshold of 10%.
4. [**model_repaired_threshold_2.h5**](./model_repaired_threshold_2.h5): A 'repaired' model with a pruning threshold of 2%.
5. [**model_repaired_threshold_4.h5**](./model_repaired_threshold_4.h5): A 'repaired' model with a pruning threshold of 4%.
6. [**results.csv**](./results.csv): A table showing the accuracy on clean test data and the attack success rate (ASR) on backdoored test data as a function of the fraction of channels pruned.
7. [**report.pdf**](./report.pdf): A detailed two-page report accompanying the results.csv file, providing in-depth analysis and findings.
8. [**jsr10000_backdoor_attack.ipynb**](./jsr10000_backdoor_attack.ipynb): The Jupyter Notebook containing all the code used in this project.

## How to Run the Code

To run the code in this project, follow these steps:

1. **Python packages**: install the following python packages using `pip`.

```
gdown
h5py
numpy
pandas
tqdm
tensorflow
```

2. **Open the Notebook**: If you are using Google Colab, upload the notebook (`jsr10000_backdoor_attack.ipynb`) to your Colab workspace. If you are running locally, open the Jupyter notebook.

3. **Load Model Files**: The first few cells in the notebook download the required model and data files.

4. **Execute Notebook Cells**: Run the cells in the notebook sequentially. The notebook contains well-commented sections guiding you through each process step.

5. **Run Models Individually (Important for Colab Users)**: If you're using Google Colab, it is recommended to run the cells related to each repaired model (`model_repaired_threshold_X.h5`) one at a time. Running all models in the same runtime session might cause system RAM to run out due to the heavy computation involved. If you're running the notebook locally, it takes some more time (as GPUs are not available), but all the cells can be run in the same runtime session.

6. **View Results**: After running the notebook, you can view the results of the detection and repair process. The notebook shows the results for X = {2%, 4%, 10%} compiled in a table. For the next part, the `results.csv` file in the repository provides a summarized view of the outcomes as a function of the fraction of channels pruned.

7. **Read the Report**: The `report.pdf` file includes a table with the accuracy on clean test data and the attack success rate (on backdoored test data) as a function of the fraction of channels pruned (X).
