
# Text classification for Finnish text data

For running a BERT based model for a text classification (e.g. sentiment analysis) task. In order to run the notebooks, you would need enough Finnish text data at hand (at least thousands of samples, preferably more). 

This repository contains the following notebooks:
- preprocessing
- pretraining (masked language modeling)
- finetuning (model training)

Preprocessing is conducted for "Tech in eldercare" data from JYU. For other datasets, adjust the code and/or data column names accordingly (e.g. number of labels in the config). For running the pretraining notebook, each dataset should be in a csv, json or txt file with the data being in a column named "text" or on the first column. For running the finetuning notebook, each dataset should be in a csv file with the data being in a column named "text" and the information of labels in column named "label".

The pretraining is unsupervised, so labels are not needed for it. For the finetuning there should be e.g. manually added labels for all of the samples. In BERT modeling, large-scale pretrained models are typically utilized to specialize your own finetuned model to downstream task(s). Before finetuning, you can add (further) pretraining (with MLM) for enhancing model performance. The backbone, in the notebooks, is currently set to FinBERT-base (Virtanen et al., 2019) as this repository has been built to deal with Finnish text data. It should work with many other backbones as well (search from https://huggingface.co/).

## Code tested with
- Python 3.7
- Torch 1.7.1
- Transformers 4.16.2

## References
- https://github.com/huggingface/transformers/blob/master/examples/pytorch/language-modeling/run_mlm_no_trainer.py
- https://www.kaggle.com/code/rhtsingh/commonlit-readability-prize-roberta-torch-itpt
- https://www.kaggle.com/code/rhtsingh/utilizing-transformer-representations-efficiently


## Contact
ida.m.toivanen(at)jyu.fi
