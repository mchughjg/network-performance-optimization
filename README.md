# Optimizing Network Performance through Deep Learning: A Case Study on Small-Scale Networks

## Project Overview

In today's interconnected digital world, maintaining optimal network performance is crucial for seamless user experience and operational integrity. [cite_start]This project addresses the challenge of identifying network bottlenecks and developing optimization strategies by leveraging deep learning techniques to analyze network traffic data. 

## Problem Statement

As networks become more complex and traffic volumes increase, identifying performance bottlenecks and anomalies manually becomes increasingly difficult. This project aims to automate and enhance the analysis of network traffic to predict and pinpoint areas for optimization, ensuring efficient and reliable network operations.

## Data Collection

Network traffic data was meticulously sampled from a small-scale professional environment using **Wireshark**. [cite_start]This data encompasses various protocols and packet characteristics essential for comprehensive analysis. 

## Methodology

This study employed deep learning models to process and analyze the collected network traffic data:

1.  **Data Preprocessing:**
    * [cite_start]The `Network Traffic.csv` dataset was loaded and preprocessed using **Pandas** and **Scikit-learn**. 
    * [cite_start]The 'Protocol' column was encoded using `LabelEncoder`. 
    * [cite_start]'Time' data was converted to datetime objects, and the 'hour' of traffic was extracted. 
    * [cite_start]Packet 'Length' was converted to numeric type. 
    * [cite_start]A binary target variable, `is_large_packet`, was created based on a `large_packet_threshold` of 1000, classifying packets as large or not. 
    * [cite_start]Features (`Length`, `Protocol_encoded`, `hour`) were defined, and the target (`is_large_packet`) was one-hot encoded using `to_categorical`. 
    * [cite_start]Features were normalized using `StandardScaler`. 
    * [cite_start]Data was reshaped appropriately for input into both CNN and RNN models. 

2.  **Model Development:**
    * [cite_start]**Convolutional Neural Network (CNN):** A CNN model was designed with `Conv1D`, `MaxPooling1D`, `Flatten`, and `Dense` layers, suitable for extracting spatial features from the sequential network data. 
    * [cite_start]**Recurrent Neural Network (RNN):** An RNN model, specifically utilizing `LSTM` layers, was implemented to capture temporal dependencies and sequential patterns within the network traffic. 
    * [cite_start]Both models were compiled using the 'adam' optimizer, 'categorical_crossentropy' loss function, and 'accuracy' as the primary metric. 

3.  **Training and Evaluation:**
    * [cite_start]The preprocessed data was split into training and testing sets for both models. 
    * [cite_start]Both CNN and RNN models were trained and evaluated on their respective datasets. 

## Results

* **CNN Model:** Achieved a test accuracy of **0.96%**. [cite_start]However, it exhibited significant variability in validation measurements, suggesting potential difficulties with generalizing to unseen data. 
* **RNN Model:** Demonstrated superior performance, achieving a near-perfect test accuracy of **99.99%**. [cite_start]This highlights the effectiveness of RNNs in understanding and classifying complex sequential network traffic patterns. 

[cite_start]The significant difference in performance between the models emphasizes the importance of selecting appropriate models based on the characteristics of the data being used. 

## Future Work

[cite_start]Future efforts will focus on enhancing the robustness and generalizability of the models by: 
* Incorporating regularization techniques to prevent overfitting.
* Extending data collection to include a broader range of network traffic scenarios.
* Exploring hybrid deep learning models that combine the strengths of both CNNs and RNNs.

## Technologies Used

* **Python**
* **Jupyter Notebook**
* [cite_start]**Pandas** (for data manipulation and analysis) 
* [cite_start]**NumPy** (for numerical operations) 
* [cite_start]**Scikit-learn** (for data preprocessing, `LabelEncoder`, `StandardScaler`, `train_test_split`) 
* [cite_start]**TensorFlow/Keras** (for building and training deep learning models: `Sequential`, `Input`, `Conv1D`, `MaxPooling1D`, `Flatten`, `Dense`, `LSTM`, `to_categorical`) 
* [cite_start]**Matplotlib** (for plotting training and validation metrics) 
* [cite_start]**Wireshark** (for network traffic data collection) 

## How to Run the Code

1.  **Clone the Repository:**
    ```bash
    git clone [Your-GitHub-Repo-Link]
    cd [Your-Repo-Name]
    ```
2.  **Install Dependencies:**
    ```bash
    pip install pandas numpy scikit-learn tensorflow matplotlib
    ```
3.  **Data Acquisition:**
    * The project relies on a `Network Traffic.csv` dataset. You would typically collect this using Wireshark from a network environment. For replication, a sample dataset (or instructions to generate one, if applicable) would be provided here.
4.  **Run Jupyter Notebook:**
    ```bash
    jupyter notebook McHugh.ipynb
    ```
    Follow the cells in the notebook to execute the data loading, preprocessing, model training, and evaluation steps.

## Contact

For any questions or collaborations, please reach out:
* **Name:** Jared McHugh
* **Email:** jbmcque@icloud.com
* **LinkedIn:** https://www.linkedin.com/in/jared-mchugh-1a563a185
---
