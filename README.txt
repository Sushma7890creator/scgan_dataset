Dataset Title: Synthetic HAM10000 Extension Dataset with Skin Tone Balance  
Author: Safrina Kabir  
Date: July 2025  

Overview
--------
This dataset extends the HAM10000 skin lesion dataset by introducing synthetic images with **medium** and **dark** skin tones to address the bias toward light-skinned individuals. Using a Conditional SCGAN (Skin-tone Conditional GAN), 10,000 synthetic images (5,000 per tone) were generated, preserving the class distribution across all 7 diagnostic categories in HAM10000.
The dataset contains synthetic skin lesion images generated using a ResNet-based conditional GAN. All images are 128×128 resolution, which reflects the training constraints of the model and ensures computational efficiency. This resolution has been found sufficient for exploring tone-variant image synthesis in dermatological AI research.

Folder Structure
----------------
synthetic_skin_dataset/
├── medium/
│   ├── akiec/
│   ├── bcc/
│   ├── bkl/
│   ├── df/
│   ├── mel/
│   ├── nv/
│   └── vasc/
└── dark/
    ├── akiec/
    ├── bcc/
    ├── bkl/
    ├── df/
    ├── mel/
    ├── nv/
    └── vasc/

Diagnostic Classes
------------------
| Class | Description                                       |
|-------|---------------------------------------------------|
| akiec | Actinic keratoses and intraepithelial carcinoma   |
| bcc   | Basal cell carcinoma                              |
| bkl   | Benign keratosis-like lesions                     |
| df    | Dermatofibroma                                    |
| mel   | Melanoma                                          |
| nv    | Melanocytic nevi                                  |
| vasc  | Vascular lesions                                  |

Motivation
----------
The original HAM10000 dataset predominantly represents light-skinned individuals, which poses fairness and generalization risks in AI-based dermatology. This work aims to:
- Expand dataset inclusivity across **melanin spectrum**
- Encourage **bias-aware** ML practices in medical AI
- Provide synthetic skin lesion images with **diverse tone conditions**

Generation Method
-----------------
- **Model**: Conditional SCGAN (StarGAN-style)
- **Base Resolution**: 128×128 px
- **Tone Conditioning**:
  - Medium-tone skin target: `#AE703A`
  - Dark-tone skin target: `#623A18`
- **Input**: Gaussian noise + class condition + tone condition
- **Post-Processing**: Class-balanced distribution based on original HAM10000 statistics

Use Cases
---------
- Training and evaluating **fairer dermatology classifiers**
- Research on **AI fairness, bias mitigation, and debiasing**
- Educational use for **bias-aware model design and auditing**

Files and Format
----------------
- `.jpg` images organized into skin tone and diagnostic class folders
- Provided as a `.zip` archive
- A `metadata.csv` file is included with the following fields:
  - `image_id`, `lesion_type`, `skin_tone`, `is_synthetic` (yes for all)

Citation
--------
If you use this dataset, please cite it as:

Kabir, S. (2025). *Synthetic HAM10000 Extension Dataset with Skin Tone Balance*. IEEE DataPort. https://doi.org/XXXXX

License
-------
This dataset is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.  
You are free to use, modify, and redistribute the dataset with appropriate credit.

Disclaimer
----------
This dataset is synthetic and intended for **research and educational use only**. It should not be used for clinical diagnosis or treatment without expert consultation.

Contact
-------
For questions, suggestions, or collaborations, contact:  
**Safrina Kabir**  
Email: safrinakabir@iut-dhaka.edu

