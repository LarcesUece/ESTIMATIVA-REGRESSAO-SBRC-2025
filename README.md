# ESTIMATIVA-REGRESSAO-SBRC-2025

This repository provides the code and datasets used in the study "Network Performance Estimation Based on Regression Techniques Applied to Monitoring Data", presented at SBRC 2025. The study explores the use of regression models to estimate network throughput based on monitoring metrics like delay and traceroute.


1. Repository Content
code/: Contains the Python scripts used for data preprocessing, regression model training, and result evaluation.

    complete-pre-processing.ipynb: Script for processing and merging throughput, delay, and traceroute data.
    regression_script.ipynb: Script for training and evaluating regression models.
    correlation-nrmse-var.ipynb: Script for computing performance metrics such as NRMSE and accuracy.
    nrmse.ipynb: script to generate nrmse graphs.
    accuracy: script to generate accuracy graphs.

datasets/: Contains the datasets used in the study, sourced from the National Education and Research Network (RNP).

    originals/: original data collected from RNP
    datasets vazao/: Throughput data collected at 4-hour intervals.
    datasets atraso: Delay data collected every minute.
    datasets traceroute: Traceroute data collected every 10 minutes
    pos-process/: network leak, delay and traceroute data after processing and joining based on timestamp, including the number of hops and identification of bottleneck links.

results/nrmse/:  Normalized Root Mean Square Error (NRMSE) results for each model and communication point.

results/prediction-by-source/: files with prediction values ​​for each dataset contained in pos-process


requirements.txt: List of dependencies required to run the Python scripts.



2. How to Reproduce the Experiments

Environment Setup:
To execute the scripts, it is necessary to set up a Python environment with the dependencies listed in the requirements.txt file. You can do this using the following command:

pip install -r requirements.txt


Data Preprocessing:
The first step is to process the raw data on flow, delay, and traceroute. Run the preprocessing script:

python code/complete-pre-processing.pynb

This script will generate a unified file containing all the necessary metrics for model training.

Model Training:
After preprocessing, you can train the regression models using the training script:

python code/regression_script.pynb

This script trains various regression models (Random Forest, XGBoost, LightGBM, CatBoost, etc.) and saves the results in the results/ directory.

Evaluation of Results:
To evaluate the performance of the models, run the evaluation scripts:

code/correlation-rmse-var.ipynb

code/acuraccy.ipynb

code/nrmse.ipynb

These scripts calculate metrics such as NRMSE and accuracy, and also generate comparative graphs.

3. Key Results

NRMSE: The CatBoost and LightGBM models showed the lowest mean errors (NRMSE), with consistent values across different communication points.
Accuracy: Over 60% of the estimates achieved accuracy greater than 80%, with boosting-based models standing out.
Regional Variability: The performance of the models varied significantly between different states, with better results in regions with more stable traffic patterns.

4. Contribution

This work contributes to the field of network monitoring by proposing an effective approach to estimate network flow from low-cost monitoring metrics such as delay and traceroute. The integration of multiple metrics and the use of advanced regression models enabled precise and robust estimates, even in high-variability scenarios.

5. For questions or suggestions, please contact the authors

Maria L. Linhares: malu.linhares@aluno.uece.br

Rafael L. Gomes: rafa.lopes@uece.br
