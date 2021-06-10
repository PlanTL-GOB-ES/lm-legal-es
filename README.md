# Spanish legal domain Language Model ⚖️
This repository contains the page for two main resources for the Spanish legal domain:
- A RoBERTa model.
- FastText embeddings.

The repository and the pre-print will be updated with larger models, evaluations, ...

## Why?
There are two main models made specifically for the Spanish language, the [BETO model](https://huggingface.co/dccuchile/bert-base-spanish-wwm-cased) and a [GPT-2](https://huggingface.co/datificate/gpt2-small-spanish).
There is also a multilingual BERT (mBERT) that is often used as it might be better sometimes.

Both BETO and GPT-2 models for Spanish have been trained with rather low resources, 4GB and 3GB of data respectively.
The data used for training both models might be various but the amount is not enough to cover all domains.
Furthermore, training a BERT-like domain-specific model is better as it effectively covers the vocabulary and understands the legal jargon.
We present our models trained on 9GB that are specifically of the legal domain.

## Evaluation
_Work in progress._

## Corpora
| Corpus name                                   | Size (GB) | Tokens (M) |
|-----------------------------------------------|-----------|------------|
| Procesos Penales                              |     0.625 |      0.119 |
| JRC Acquis                                    |     0.345 |     59.359 |
| Códigos Electrónicos Universitarios           |     0.077 |     11.835 |
| Códigos Electrónicos                          |     0.080 |     12.237 |
| Doctrina de la Fiscalía General del Estado    |     0.017 |      2.669 |
| Legislación BOE                               |     3.600 |    578.685 |
| Abogacía del Estado BOE                       |     0.037 |      6.123 |
| Consejo de Estado: Dictámenes                 |     0.827 |    135.348 |
| Spanish EURLEX                                |     0.001 |      0.072 |
| UN Resolutions                                |     0.023 |       3539 |
| Spanish DOGC                                  |     0.826 |    132.569 |
| Spanish MultiUN                               |     2.200 |    352.653 |
| Consultas Tributarias Generales y Vinculantes |     0.466 |     77.691 |
| Constitución Española                         |     0.002 |      0.018 |
| COPPA Patents Corpus                          |     0.002 |          - |
| Biomedical Patents                            |     0.083 |          - |


## Usage example
You can train your model for different downstream tasks using the scripts that Hugging Face provides ([Name Entity Recognition](https://github.com/huggingface/transformers/blob/master/examples/pytorch/token-classification/run_ner.py), [GLUE tasks](https://github.com/huggingface/transformers/blob/master/examples/pytorch/text-classification/run_glue.py) and [others](https://github.com/huggingface/transformers/tree/master/examples/pytorch))

```python
print("TBA")
```

## Cite
If this work is helpful, please cite it:
```
TBA
```

## Contact
We are interested in (1) extending our corpora to make larger models (2) evaluate/train the model in other tasks.

For questions regarding this work, contact Asier Gutiérrez-Fandiño (<asier.gutierrez@bsc.es>)
