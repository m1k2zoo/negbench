# Datasets for NegBench

This document provides guidance on preparing the datasets required for evaluation (`NegBench`) and fine-tuning (`CC12M-NegCap` and `CC12M-NegMCQ`). 

---

## Evaluation Datasets (NegBench)

The `data/` directory should include datasets for evaluation, organized as follows:
```
data/
├── images/
│   ├── COCO_val_mcq_llama3.1_rephrased.csv
│   ├── VOC2007_mcq_llama3.1_rephrased.csv
│   ├── synthetic_mcq_llama3.1_rephrased.csv
│   ├── COCO_val_retrieval.csv
│   ├── COCO_val_negated_retrieval_llama3.1_rephrased_affneg_true.csv
│   ├── synthetic_retrieval_v1.csv
│   ├── synthetic_retrieval_v2.csv
│   ├── chexpert_binary_mcq.csv
│   └── chexpert_binary_mcq_control.csv
├── videos/
│   ├── msr_vtt_retrieval.csv
│   ├── msr_vtt_retrieval_rephrased_llama.csv
│   └── msr_vtt_mcq_rephrased_llama.csv
```

### Preprocessed CSV Files
The CSV files contain captions used for evaluation and are available for download:
**[Download Preprocessed CSV Files](https://drive.google.com/drive/folders/1kSEq0mkV1t1T8GuOAM65iz_iAA7e5gxB?usp=sharing)**

Each CSV file includes either `image_path` or `filepath` columns. After downloading the images, ensure you update these paths to match your directory structure.

### Image Datasets

1. **VOC2007**
   - Download images from the **[official link](http://host.robots.ox.ac.uk/pascal/VOC/voc2007/VOCtest_06-Nov-2007.tar)**.
   - Extract the dataset and ensure the file paths in the CSV files point to the correct directory.

2. **COCO 2017 Validation Set**
   - Download the 2017 validation images from **[COCO dataset](https://cocodataset.org/#download)**.
   - Update the `image_path` and `filepath` columns in the COCO CSV files.

3. **MSR-VTT Videos**
   - Download videos from **[MediaFire link](https://www.mediafire.com/folder/h14iarbs62e7p/shared)**.
   - Update the `image_path` and `filepath` columns in the relevant CSV files.

4. **CheXpert Medical Dataset**
   - Download images from the **[Kaggle link](https://www.kaggle.com/datasets/ashery/chexpert)**.
   - Update the `image_path` columns in the relevant CSV files.

### Notes
- Ensure that the paths in the CSV files are updated to reflect your local directory structure.
- The captions in the preprocessed CSV files can be used to reproduce the main evaluations in NegBench.

---

## Fine-Tuning Datasets (CC12M-NegCap and CC12M-NegMCQ)

The fine-tuning datasets are derived from the **CC12M dataset**. The datasets include:
- **CC12M-NegCap**: Captions with incorporated negated objects (~30 million captions).
- **CC12M-NegMCQ**: Multiple-choice questions with one correct and three hard negative captions (~40 million captions).

These datasets are constructed using the scripts in the `synthetic_datasets/finetuning/` directory. For detailed instructions, refer to [`synthetic_datasets/finetuning/README.md`](synthetic_datasets/finetuning/README.md).

---

## Contact and Updates

If you encounter any issues or need assistance, please reach out via GitHub issues or email.
