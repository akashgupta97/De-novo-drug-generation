# De-novo-drug-generation

This model is built using Python 3.7, and utilizes the following packages;

- numpy 1.18.2
- tensorflow 2.1.0
- tqdm 4.43.0
- Bunch 1.0.1
- matplotlib 3.1.2
- RDKit 2019.09.3
- scikit-learn 0.22.2.post1

## Dataset

You can get 556134 SMILES in dataset.smi. According to the paper, the dataset was preprocessed and duplicates, salts, and stereochemical information were removed, SMILES strings with lengths from 34 to 74 (tokens). So I made SMILES clean up script. Run the following to get cleansed SMILES. It takes about 10 miniutes or more. Please wait.

```
$ python cleanup_smiles.py datasets/dataset.smi datasets/dataset_cleansed.smi

```
You can get 438552 SMILES. This dataset is used for training.

## Training
Just run below. However, all the data is used according to the default setting. So please be careful, it will take a long time. If you don't have enough time, set ```data_length``` to a different value in ```base_config.json```.
```
$ python train.py
```
After training, ```experiments/{exp_name}/{YYYY-mm-dd}/config.json``` is generated. It's a copy of ```base_config.json``` with additional settings for internal variable. Since it is used for generation, be careful when rewriting.

## Generation
See ```example_Randomly_generate_SMILES.ipynb```.

