# DataScienceProject-P2
DS 4002: Data Science Project

## Section 1: Software and platform section
The software used for this project was Visual Studio Code (VS Code) and GitHub. The language used was Python (3.12.4). Additionally, the platform that was used was Windows, and the following packages were installed for this project:
* numpy
* pandas
* matplotlib
* Pillow
* tqdm
* scikit-learn
* transformers
* torch

## Section 2: Map of the documentation

**README.md**  
- Overview of the project, software and platform used, documentation map, and instructions for reproducing results

**LICENSE.md**  
- Terms for citing and reproducing the repository

**REFERENCES.md**  
- References to the nflfastR site where the data was obtained from

**SCRIPTS/**  
- DS4002_EDA_Proj3.ipynb
- deeplabs_exp1-2_flood_detection.ipynb
- segformer_exp0_flood_detection.ipynb
- segformer_exp1-4_flood_detection.ipynb
- unet_exp1-4_flood_detection.ipynb
- unet_exp12_flood_detection.ipynb
- unet_exp5-8_flood_detection.ipynb
- unet_exp9-11_flood_detection.ipynb

**DATA/**  
- data.md - contains a link to obtain the dataset

**OUTPUT/**  
- deeplab_experiment_plots
  - exp1_lr0.0001_wd0.0001_ep40_f1.png
  - exp1_lr0.0001_wd0.0001_ep40_iou.png
  - exp1_lr0.0001_wd0.0001_ep40_loss.png
  - exp1_lr0.0001_wd0.0001_ep40_predictions.png
  - exp2_lr0.0003_wd0.001_ep40_f1.png
  - exp2_lr0.0003_wd0.001_ep40_iou.png
  - exp2_lr0.0003_wd0.001_ep40_loss.png
  - exp2_lr0.0003_wd0.001_ep40_predictions.png
- eda
  - Flooded vs Non-Flooded Pixel Counts in Masks.png
  - Number of Images Per Dataset Split.png
  - Segmentation Class Pixel Distribution.png
- segformer_experiment_plots
  - exp1_lr5e-05_wd0.0001_ep10_f1.png
  - exp1_lr5e-05_wd0.0001_ep10_iou.png
  - exp1_lr5e-05_wd0.0001_ep10_loss.png
  - exp1_lr5e-05_wd0.0001_ep10_predictions.png
  - exp1_lr5e-05_wd0.0001_ep20_f1.png
  - exp1_lr5e-05_wd0.0001_ep20_iou.png
  - exp1_lr5e-05_wd0.0001_ep20_loss.png
  - exp2_lr3e-05_wd0.0001_ep10_f1.png
  - exp2_lr3e-05_wd0.0001_ep10_iou.png
  - exp2_lr3e-05_wd0.0001_ep10_loss.png
  - exp2_lr3e-05_wd0.0001_ep10_predictions.png
  - exp3_lr3e-05_wd0.01_ep10_f1.png
  - exp3_lr3e-05_wd0.01_ep10_iou.png
  - exp3_lr3e-05_wd0.01_ep10_loss.png
  - exp3_lr3e-05_wd0.01_ep10_predictions.png
  - exp4_lr1e-05_wd0.01_ep20_f1.png
  - exp4_lr1e-05_wd0.01_ep20_iou.png
  - exp4_lr1e-05_wd0.01_ep20_loss.png
  - exp4_lr1e-05_wd0.01_ep20_predictions.png
  - segformer_exp0_iou.png
  - segformer_exp0_loss.png
  - segformer_exp0_sample_image.png
- unet_experiment_plots
  - exp1-3
  - exp4-6
  - exp7-11

## Section 3: Instructions for reproducing the results
1. Download the data using the link in data.md
2. Download and install necessary packages listed above
3. Run the EDA script for the EDA analysis
4. Run the scripts for each of the following models in the scripts folder: segformer, unet, and deeplab (in order as listed under scripts) to obtain the three different models
5. Analyze results
