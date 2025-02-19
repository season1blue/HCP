 
# A Dual-way Enhanced Framework from Text Matching Point of View for Multimodal Entity Linking



## :sparkles: Overview

This repository contains official implementation of our paper [A Dual-way Enhanced Framework from Text Matching Point of View for Multimodal Entity Linking](https://arxiv.org/pdf/2312.11816).

Multimodal Entity Linking (MEL) aims at linking ambiguous mentions with multimodal information to entity in Knowledge Graph (KG) such as Wikipedia, which plays a key role in many applications. However, existing methods suffer from shortcomings, including modality impurity such as noise in raw image and ambiguous textual entity representation, which puts obstacles to MEL. We formulate multimodal entity linking as a neural text matching problem where each multimodal information (text and image) is treated as a query, and the model learns the mapping from each query to the relevant entity from candidate entities. This paper introduces a dual-way enhanced (DWE) framework for MEL: (1) our model refines queries with multimodal data and addresses semantic gaps using cross-modal enhancers between text and image information. Besides, DWE innovatively leverages fine-grained image attributes, including facial characteristic and scene feature, to enhance and refine visual features.
    (2)By using Wikipedia descriptions, DWE enriches entity semantics and obtains more comprehensive textual representation, which reduces between textual representation and the entities in KG. Extensive experiments on three public benchmarks demonstrate that our method achieves state-of-the-art (SOTA) performance, indicating the superiority of our model.
  

If you have any question, please feel free to contact me by e-mail: betterszsong@gmail.com or submit your issue in the repository.

## :fire: News

[23.12.09] The paper is accepted by AAAI-24.


## :rocket: Architecture


<p align="center" width="60%"><img src="model.png" alt="DWE" style="width: 100%;  display: block; margin: auto;"></p>


## :rotating_light: Usage
    
### Environment

```
conda create -n DWE python=3.8
conda activate DWE
pip install -r req.txt
```
 

### Data

Dataset: two well-established MEL datasets, namely [WikiDiverse](https://arxiv.org/abs/2204.06347) and [WikiMEL](https://dl.acm.org/doi/abs/10.1145/3477495.3531867)

Checkpoint and preprocessed data can be accessed [here](https://drive.google.com/drive/folders/1Gd9ykKgFmXl0_hkNTGk2DUdVhcIpJjV5?usp=drive_link), and move to the `./data` folder.

Put the image at data/ImgData. Image Data is obtained by [here](https://pan.baidu.com/s/1WbIfj3nAJAmFoHWSOxgcog) and the extract code is 1111. (Thanks for the download link provided from [GHMFC](https://drive.google.com/drive/folders/1Gd9ykKgFmXl0_hkNTGk2DUdVhcIpJjV5?usp=drive_link](https://github.com/seukgcode/MEL-GHMFC/tree/main/datasets))
 
The directory tree is:
```
├─ImgData
│  ├─richpedia
│  │  ├─images
│  │  └─old
│  ├─wikidiverse
│  └─wikipedia
├─richpedia
│  ├─rich_detection
│  └─rich_segement
├─wikidiverse
│  ├─dataset
│  │  └─cands
│  ├─entity
│  └─utils
└─wikipedia
    ├─wiki_detection
    └─wiki_segement
```

```
train.json, dev.json, test.json         ->      textual data files
cached_dev_img, cached_train_img      ->      visual data file
```

### Train
 
The model structure is in nel_model/nel.py, and most of the data processing is in data_process.

You can customize some parameter settings, see nel_model/args.py. Some examples of training are given here:

For training WikiDiverse:
```
sh diverse.sh
```

For training WikiMEL:
```
sh wwiki.sh
```

For training Richpedia:
```
sh rich.sh
```

For training Wikiperson:
```
sh person.sh
```


 

## Citation
```
@article{song2023dualway,
author = {Song, Shezheng and Zhao, Shan and Wang, Chengyu and Yan, Tianwei and Li, Shasha and Mao, Xiaoguang and Wang, Meng},
year = {2024},
month = {03},
pages = {19008-19016},
title = {A Dual-Way Enhanced Framework from Text Matching Point of View for Multimodal Entity Linking},
volume = {38},
journal = {Proceedings of the AAAI Conference on Artificial Intelligence},
doi = {10.1609/aaai.v38i17.29867}
}
```
## License
This repository respects to Apache license 2.0.


