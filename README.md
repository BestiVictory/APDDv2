# APDDv2: Aesthetics of Paintings and Drawings Dataset with Artist Labeled Scores and Comments

This is an open-source aesthetics of paintings and drawings dataset called APDD, which was completed by the victory-lab.

## Introduction

The Aesthetics Paintings and Drawings Dataset (APDDv2) stands as the pioneering comprehensive painting dataset, encompassing 24 distinct artistic categories and 10 aesthetic attributes. Comprising 10,023 painting images, 85,191 Scoring labels, and 6,249 linguistic comments, APDDv2 addresses the scarcity of datasets in the realm of aesthetic evaluation of artistic images. Its primary aim is to furnish researchers and practitioners with high-quality painting data, thereby fostering the development and application of automatic aesthetic evaluation methodologies.

ArtCLIP, tailored specifically for particular painting styles, is an artistic assessment network trained on the APDDv2 dataset. The ArtCLIP models excel in providing a comprehensive assessment of the total aesthetic score of artistic images, along with scoring various aesthetic attributes.

## APDDv2

- `APDDv2-10023.csv`: This file contains annotations for the APDDv2 dataset, including artistic categories, total aesthetic scores, aesthetic attribute scores and language comments for 10,023 images.
- `filesource.csv`: This file records the source URLs for 1892 images in the APDD dataset. The remaining images are sourced from [Wikiart](https://www.wikiart.org/) and student painting assignments.

We provide alternatives to obtain the dataset:

Baidu Netdisk: [Click here to download](https://drive.google.com/file/d/1ap5dhuEgpPC5PrJozAu2V), Access code: 9y91

Google Drive: [Click here to download](https://drive.google.com/file/d/1ap5dhuEgpPC5PrJozAu2VFmUNIRZrar2/view?usp=drive_link)

## ArtCLIP

Clone the repository:

```sh
git clone https://github.com/BestiVictory/APDDv2.git
cd APDDv2/
```

Install dependencies (works with python3.9):

```
pip3 install -r requirements.txt
```

The model checkpoints can be downloaded from 
[gcloud directory link](https://drive.google.com/drive/folders/1AOVKmSqZCW09J_Ypr7KzSYfRxQre-w_m?usp=drive_link).
The folder contains the following items:

- **./modle_weights/0.ArtCLIP_weight--e11-train2.4314-test4.0253_best.pth**: ArtCLIP model weight, which fine-tuned vanilla CLIP on categorized DPC2022 dataset.

- **./modle_weights/1.Score_reg_weight--e4-train0.4393-test0.6835_best.pth**: ArtCLIP finetuned on the APDDv2 database for predicting total aesthetic scores.

     **......**

- **./modle_weights/11.Mood_reg_weight--e7-train0.3108-test0.7097_best.pth**: ArtCLIP finetuned on the APDDv2 database for predicting mood scores.

For testing on ArtCLIP, use:

```
python eval.py
```

To obtain the total aesthetic score and aesthetic attribute scores predicted by the model, use:

```
python demo.py
```

## License
The dataset is licensed under [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)


## Citation
If you find this project useful, please consider citing:

```bibtex
@article{jin2024apddv2,
  title={APDDv2: Aesthetics of Paintings and Drawings Dataset with Artist Labeled Scores and Comments},
  author={Jin, Xin and Qiao, Qianqian and Lu, Yi and Wang, Huaye and Huang, Heng and Gao, Shan and Liu, Jianfei and Li, Rui},
  journal={Advances in Neural Information Processing Systems},
  volume={37},
  pages={103064--103075},
  year={2024}
}
```
