# FLORES+Gender
[![Hugging Face Dataset](https://img.shields.io/badge/🤗%20Hugging%20Face-Dataset-yellow)](https://huggingface.co/datasets/HiTZ/flores_plus_gender)


This dataset builds on the [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/spa_Latn/devtest) benchmark, developed by Meta to assess machine translation (MT) systems for low-resource languages. **FLORES+Gender** is designed to assess gender bias in MT. While the typical approach examines bias by translating from a genderless language into a gendered one, this dataset follows the methodology of [Costa-jussà et al. (2023)](https://arxiv.org/abs/2305.13198) and reverses the direction to analyse whether translation quality is affected by the predominant grammatical gender of the source sentence when translating from a gendered language (Spanish or English) into a genderless one (Basque). 

For each source language, the dataset includes two contrastive versions: one containing all sentences in masculine form and another with the same sentences in feminine form. The Spanish set comprises 363 sentences with gendered references, while the English set contains 155. All sentences were manually adapted to produce gender-controlled pairs while maintaining semantic equivalence.

In addition, each instance was manually annotated for three linguistic and contextual factors that may influence translation behaviour:

* ME (Multiple Entities): whether the sentence mentions more than one gendered human referent.
* PN (Proper Names): whether it contains gendered proper names.
* UM (Unmarked Masculine): whether the masculine form is used generically (applies only to Spanish).

These annotations enable more fine-grained analyses of how different linguistic cues interact with gender bias in translation quality.

## Uses
FLORES+Gender can be used to evaluate how grammatical gender in the source language influences translation quality when translating into genderless languages.

## Data Structure
Each row in the dataset contains the following columns:

- **sentence_m** → Masculine version of the sentence.  
- **reference_m** → Basque reference translation for the masculine sentence.  
- **sentence_f** → Feminine version of the sentence.  
- **reference_f** → Basque reference translation for the feminine sentence.  
- **ME** → Binary label indicating the presence of multiple gendered entities (*Multiple Entities*).  
- **PN** → Binary label indicating the presence of proper names (*Proper Name*).  
- **UM** → Binary label indicating cases where the masculine form is used as an unmarked or generic form (*Unmarked Masculine*) *(Only in the Spanish version)*.


## Citation
If you use this dataset in your work, please make sure to cite both the original FLORES-200 paper, since FLORES+ is based on it, and our paper introducing FLORES+Gender:

```bibtex
@article{nllb-24,
    author="{NLLB Team} and Costa-juss{\`a}, Marta R. and Cross, James and {\c{C}}elebi, Onur and Elbayad, Maha and Heafield, Kenneth and Heffernan, Kevin and Kalbassi, Elahe and Lam, Janice and Licht, Daniel and Maillard, Jean and Sun, Anna and Wang, Skyler and Wenzek, Guillaume and Youngblood, Al and Akula, Bapi and Barrault, Loic and Gonzalez, Gabriel Mejia and Hansanti, Prangthip and Hoffman, John and Jarrett, Semarley and Sadagopan, Kaushik Ram and Rowe, Dirk and Spruit, Shannon and Tran, Chau and Andrews, Pierre and Ayan, Necip Fazil and Bhosale, Shruti and Edunov, Sergey and Fan, Angela and Gao, Cynthia and Goswami, Vedanuj and Guzm{\'a}n, Francisco and Koehn, Philipp and Mourachko, Alexandre and Ropers, Christophe and Saleem, Safiyyah and Schwenk, Holger and Wang, Jeff",
    title="Scaling neural machine translation to 200 languages",
    journal="Nature",
    year="2024",
    volume="630",
    number="8018",
    pages="841--846",
    issn="1476-4687",
    doi="10.1038/s41586-024-07335-x",
    url="https://doi.org/10.1038/s41586-024-07335-x"
}
```

```bibtex
inproceedings{murillo-etal-2026-gender,
  title = {Gender Bias in MT for a Genderless Language: New Benchmarks for Basque},
  author = {Murillo, Amaia and Perez-de-Viñaspre, Olatz and Perez, Naiara},
  booktitle = {Proceedings of the Fifteenth Language Resources and Evaluation Conference (LREC 2026)},
  month = {May},
  year = {2026},
  pages = {8971--8984},
  address = {Palma, Mallorca, Spain},
  publisher = {European Language Resources Association (ELRA)},
  doi = {10.63317/352cdsej8fcp},
  abstract = {Large language models (LLMs) and machine translation (MT) systems are increasingly used in our daily lives, but their outputs can reproduce gender bias present in the training data. Most resources for evaluating such biases are designed for English and reflect its sociocultural context, which limits their applicability to other languages. This work addresses this gap by introducing two new datasets to evaluate gender bias in translations involving Basque, a low-resource and genderless language. WinoMTeus adapts the WinoMT benchmark to examine how gender-neutral Basque occupations are translated into gendered languages such as Spanish and French. FLORES+Gender, in turn, extends the FLORES+ benchmark to assess whether translation quality varies when translating from gendered languages (Spanish and English) into Basque depending on the gender of the referent. We evaluate several general-purpose LLMs and open and proprietary MT systems. The results reveal a systematic preference for masculine forms and, in some models, a slightly higher quality for masculine referents. Overall, these findings show that gender bias is still deeply rooted in these models, and highlight the need to develop evaluation methods that consider both linguistic features and cultural context.}
}
```

## Acknowledgements

This work was supported by the HiTZ Chair of Artificial Intelligence and Language Technology (TSI100923-2023-1), funded by MTDFP, _Secretaría de Estado de Digitalización e Inteligencia Artificial_.
Additional support was provided by the Research Project PID2024-157855OB-C32 (MOLVI), funded by MICIU/AEI/10.13039/501100011033 and the European Regional Development Fund (ERDF), EU. 
It was also funded by the Basque Government (IKER-GAITU project) and the _Ministerio para la Transformación Digital y de la Función Pública_ - Funded by EU – NextGenerationEU within the framework of the project _Desarrollo de Modelos ALIA_.

## Contact
amaia.murillo@ehu.eus  
olatz.perezdevinaspre@ehu.eus  
naiara.perez@ehu.eus
