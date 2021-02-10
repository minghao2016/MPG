# An effective self-supervised framework for learning expressive molecular global representations to drug discovery

This repository is the official implementation.

> 📋 We provide the code of MPG implementation for pre-training, including the model and pre-training strategies.

## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```

## Dataset Download
All used datasets are public. Please refer to the paper for more details.


## Pre-training 

To pre-train the model from scrach, please run the following command to preprocess the data by PSD and AttrMasking:
```train
python loader.py 
```
Then, run:
```train
bash run_pretraining.sh
```

> 📋 To train the model, please download the [zinc](http://zinc15.docking.org/) and [ChemBL](https://www.ebi.ac.uk/chembl/) dataset first and put in the `data/pretraining/raw/` folder.

## Fine-tune
To fine-tune the pre-trained model on downstream tasks, please run:
```finetune
python finetune.py --dataset toxcast --lr 0.0001 
```
> 📋 To finetune the model, please put the datasets in the `data/downstream/` folder.

