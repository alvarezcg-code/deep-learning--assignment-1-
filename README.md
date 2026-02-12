# Deep Learning Assignment 1

## Objective
This project benchmarks two required architectures, MLP and CNN, across three datasets (Adult, CIFAR-10, and PCam) using a consistent PyTorch training pipeline.

## Datasets
- Adult (UCI): binary classification (`income > 50K`)
- CIFAR-10: multiclass image classification (10 classes)
- PCam: binary histopathology image classification

## Architectures
- MLP (required)
- CNN (required)
- Attention-based model not included (bonus/optional)

## Experimental Setup
- Framework: PyTorch
- Optimizer family: Adam (used consistently)
- Data split: train / validation / test
- Configurable hyperparameters: learning rate, batch size, epochs, early stopping
- Reproducibility: fixed random seed
- No pretrained models used
- No hyperparameter search libraries used

## Final Results

| Dataset  | Architecture | Accuracy | F1     | Train Time (sec) | Notes         |
|---------|--------------|----------|--------|------------------|---------------|
| Adult   | MLP          | 0.8581   | 0.6737 | 7.9              | best_epoch=3  |
| Adult   | CNN          | 0.8624   | 0.6885 | 94.2             | best_epoch=12 |
| CIFAR-10| MLP          | 0.5170   | 0.5167 | 211.1            | best_epoch=8  |
| CIFAR-10| CNN          | 0.7410   | 0.7383 | 765.4            | best_epoch=10 |
| PCam    | MLP          | 0.6770   | 0.6888 | 284.4            | best_epoch=1  |
| PCam    | CNN          | 0.7710   | 0.7910 | 1515.0           | best_epoch=1  |

## Analysis Summary
- CNN outperformed MLP on the image datasets (CIFAR-10 and PCam), which is consistent with CNN spatial inductive bias.
- On Adult tabular data, MLP and CNN performed similarly, with CNN slightly higher in this run.
- CNN models required more training time than MLP models.
- Early stopping helped reduce unnecessary training and limit overfitting.

## Constraints Check
- PyTorch only: Yes
- No pretrained models: Yes
- No hyperparameter search libraries: Yes
- Max training time per model <= 1 hour: Yes

## Run Instructions
1. Install dependencies:
   `pip install torch torchvision scikit-learn pandas datasets matplotlib`
2. Run notebook cells in order (setup, utilities, models, loaders, experiment loop, save results, plots).
3. Outputs:
   - `results_table.csv`
   - training/validation curves

## Submission
Repository includes:
- Notebook (`.ipynb`)
- `results_table.csv`
- `README.md`
