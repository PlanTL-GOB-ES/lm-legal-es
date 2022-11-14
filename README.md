# Spanish legal domain Language Model ⚖️
This repository contains the page for two main resources for the Spanish legal domain:
- A RoBERTa model: https://huggingface.co/PlanTL-GOB-ES/RoBERTalex
- FastText embeddings: https://zenodo.org/record/5036147
- Legal corpora: https://zenodo.org/record/5495529

*The repository and the pre-print will be updated with larger models, evaluations, etcetera.*

## Why❓
There are few models trained for the Spanish language. Some of the models have been trained with a low resource, unclean corpora. The ones derived from the Spanish National Plan for Language Technologies are proficient solving several tasks and have been trained using large scale clean corpora. However, the Spanish Legal domain language could be think of an independent language on its own. We therefore created a Spanish Legal model from scratch trained exclusively on legal corpora.

## Evaluation ✅
_Work in progress._

## Corpora 📃
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
| UN Resolutions                                |     0.023 |      3.539 |
| Spanish DOGC                                  |     0.826 |    132.569 |
| Spanish MultiUN                               |     2.200 |    352.653 |
| Consultas Tributarias Generales y Vinculantes |     0.466 |     77.691 |
| Constitución Española                         |     0.002 |      0.018 |
| COPPA Patents Corpus                          |     0.002 |          - |
| Biomedical Patents                            |     0.083 |          - |


## Usage example ⚗️
You can train your model for different downstream tasks using the scripts that Hugging Face provides ([Name Entity Recognition](https://github.com/huggingface/transformers/blob/master/examples/pytorch/token-classification/run_ner.py), [GLUE tasks](https://github.com/huggingface/transformers/blob/master/examples/pytorch/text-classification/run_glue.py) and [others](https://github.com/huggingface/transformers/tree/master/examples/pytorch))

```python
from transformers import AutoModelForMaskedLM
from transformers import AutoTokenizer, FillMaskPipeline
from pprint import pprint
tokenizer_hf = AutoTokenizer.from_pretrained('PlanTL-GOB-ES/RoBERTalex')
model = AutoModelForMaskedLM.from_pretrained('PlanTL-GOB-ES/RoBERTalex')
model.eval()
pipeline = FillMaskPipeline(model, tokenizer_hf)
text = f"¡Hola <mask>!"
res_hf = pipeline(text)
pprint([r['token_str'] for r in res_hf])
```

## Cite 📣
If this work is helpful, please cite it:
```
@misc{gutierrezfandino2021legal,
      title={Spanish Legalese Language Model and Corpora}, 
      author={Asier Gutiérrez-Fandiño and Jordi Armengol-Estapé and Aitor Gonzalez-Agirre and Marta Villegas},
      year={2021},
      eprint={2110.12201},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

## Contact 📧
📋 We are interested in (1) extending our corpora to make larger models (2) evaluate/train the model in other tasks.

For questions regarding this work, contact <plantl-gob-es@bsc.es>


## Disclaimer

The models published in this repository are intended for a generalist purpose and are available to third parties. These models may have bias and/or any other undesirable distortions.

When third parties, deploy or provide systems and/or services to other parties using any of these models (or using systems based on these models) or become users of the models, they should note that it is their responsibility to mitigate the risks arising from their use and, in any event, to comply with applicable regulations, including regulations regarding the use of artificial intelligence.

In no event shall the owner of the models (SEDIA – State Secretariat for digitalization and artificial intelligence) nor the creator (BSC – Barcelona Supercomputing Center) be liable for any results arising from the use made by third parties of these models.


Los modelos publicados en este repositorio tienen una finalidad generalista y están a disposición de terceros. Estos modelos pueden tener sesgos y/u otro tipo de distorsiones indeseables.

Cuando terceros desplieguen o proporcionen sistemas y/o servicios a otras partes usando alguno de estos modelos (o utilizando sistemas basados en estos modelos) o se conviertan en usuarios de los modelos, deben tener en cuenta que es su responsabilidad mitigar los riesgos derivados de su uso y, en todo caso, cumplir con la normativa aplicable, incluyendo la normativa en materia de uso de inteligencia artificial.

En ningún caso el propietario de los modelos (SEDIA – Secretaría de Estado de Digitalización e Inteligencia Artificial) ni el creador (BSC – Barcelona Supercomputing Center) serán responsables de los resultados derivados del uso que hagan terceros de estos modelos.
