## Description
The baseline system consists of two main scripts:
- `00_train.py`
  - This script trains models for each Machine Type by using the directory **dev_data/<Machine_Type>/train/** or **eval_data/<Machine_Type>/train/**.
- `01_test.py`
  - This script makes csv files for each Machine ID including the anomaly scores for each wav file in the directory **dev_data/<Machine_Type>/test/** or **eval_data/<Machine_Type>/test/**.
  - The csv files will be stored in the directory **result/**.
  - If the mode is "development", it also makes the csv files including the AUC and pAUC for each Machine ID. 


- Development dataset
  - Download `dev_data_<Machine_Type>.zip` from https://zenodo.org/record/3678171.
- "Additional training dataset", i.e. the evaluation dataset for training
  - After launch, download `eval_data_train_<Machine_Type>.zip` from https://zenodo.org/record/3727685 (not available until April. 1).
- "Evaluation dataset", i.e. the evaluation for test
  - After launch, download `eval_data_test_<Machine_Type>.zip` from https://zenodo.org/record/3841772 (not available until June. 1).

You can change the parameters for feature extraction and model definition by editing `baseline.yaml`.

`00_train.py` trains the models for each Machine Type and saves the trained models in the directory **model/**.

Run the test script `01_test.py`.

$ python3.6
## Dependency
We develop the source code on Ubuntu 16.04 LTS and 18.04 LTS.
In addition, we checked performing on **Ubuntu 16.04 LTS**, **18.04 LTS**, **Cent OS 7**, and **Windows 10**.

### Software packages
- p7zip-full
- Python == 3.6.5
- FFmpeg

### Python packages
- Keras                         == 2.1.6
- Keras-Applications            == 1.0.8
- Keras-Preprocessing           == 1.0.5
- matplotlib                    == 3.0.3
- numpy                         == 1.16.0
- PyYAML                        == 5.1
- scikit-learn                  == 0.20.2
- librosa                       == 0.6.0
- audioread                     == 2.1.5 (more)
- setuptools                    == 41.0.0
- tensorflow                    == 1.15.0
- tqdm                          == 4.23.4
