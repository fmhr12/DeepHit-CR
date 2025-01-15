# DeepHit Survival Analysis Pipeline

DeepHit Survival Analysis Pipeline leverages the DeepHit model for competing risks survival analysis. This project provides a complete workflow from data preprocessing to model training, hyperparameter tuning, evaluation, and prediction storage, ideal for researchers and practitioners in survival analysis.

## Features

- **Data Preprocessing:** One-hot encoding for categorical variables and standard scaling for continuous variables.
- **Custom Neural Network:** Implements a cause-specific architecture using PyTorch.
- **Hyperparameter Tuning:** Grid search for optimizing model parameters.
- **Cross-Validation:** Repeated Stratified K-Fold for robust evaluation.
- **Survival Analysis:** Utilizes the DeepHit model from `pycox`.
- **Evaluation Metrics:** Calculates Concordance Index (C-index) and Integrated Brier Score (IBS) with 95% confidence intervals.
- **Prediction Storage:** Saves predicted Cumulative Incidence Functions (CIFs) for each fold.

## Installation

### Steps

1. **Clone the Repository**
    ```bash
    git clone https://github.com/yourusername/deep_hit_survival_analysis.git
    cd deep_hit_survival_analysis
    ```

2. **Create a Virtual Environment (Optional)**
    ```bash
    python -m venv venv
    source venv/bin/activate 
    ```

3. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```
    *If `requirements.txt` is unavailable:*
    ```bash
    pip install pandas numpy torch scikit-learn pycox torchtuples matplotlib scipy openpyxl
    ```

## Usage

1. **Configure the Script**
    - Update the `file_path` variable to your dataset location.
    - Modify `param_grid` for hyperparameter tuning as needed.
    - Adjust `num_nodes_shared` and `num_nodes_indiv` to change the network architecture.

2. **Run the Pipeline**
    ```bash
    python deep_hit_pipeline.py
    ```

## Output

- **Predictions:** CSV files saved in `deep_hit_predictions/` for each fold, containing observed times, event indicators, and predicted CIFs.
- **Evaluation Summary:** Prints C-index and IBS with 95% confidence intervals after all folds.

    ```
    ====================== Summary ======================
    C-index: 0.7523 (95% CI: 0.7321 - 0.7725)
    IBS:      0.1234 (95% CI: 0.1102 - 0.1366)
    ======================================================
    ```

## Evaluation Metrics

- **Concordance Index (C-index):** Measures the model's ability to correctly order survival times.
- **Integrated Brier Score (IBS):** Assesses the accuracy of probabilistic predictions over time.

## Contributing

Contributions are welcome! Fork the repository, create a new branch, commit your changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
