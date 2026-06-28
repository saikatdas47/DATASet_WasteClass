# Multi-Source Waste Classification Dataset for Edge AI Benchmarking

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Dataset](https://img.shields.io/badge/Dataset-Waste%20Classification-green)](https://github.com/your-repo-link)

This repository provides a **dual-source waste classification dataset** specifically designed for training and evaluating deployment‑aware edge AI models on resource‑constrained devices (e.g., Raspberry Pi 4B). It includes a large public training set and a smaller, real‑world evaluation set captured under practical conditions.

---

## 📁 Dataset Composition

The dataset is split into two main directories:

### **ImageData-1** – Training Dataset  
- **Source:** [Kaggle – Garbage Classification v2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2)  
- **Total Images:** 4,000 labeled RGB images (JPEG)  
- **Classes:** 4 waste categories – Biological, Metal, Paper, Plastic  
- **Purpose:** Model training and cloud‑based validation  
- **Characteristics:** Natural variability in lighting, backgrounds, object orientations, and scales  
- **Distribution:** Balanced with ~997–998 images per class

### **ImageData-2** – Edge Evaluation Dataset  
- **Source:** Original data collected for this research  
- **Total Images:** 400 manually captured RGB images (JPEG)  
- **Classes:** 4 waste categories – Biological, Metal, Paper, Plastic  
- **Purpose:** Real‑world edge device testing and Raspberry Pi benchmarking  
- **Characteristics:** Diverse lighting, angles, and clutter to mimic deployment conditions  
- **Device:** Captured using a mobile phone camera  
- **Distribution:** Approximately balanced (100 images per class)

---

## 📊 Dataset Distribution

| Class       | ImageData‑1 (Training) | ImageData‑2 (Edge Testing) |
|-------------|------------------------|----------------------------|
| Biological  | 998                    | 107                         |
| Metal       | 997                    | 100                         |
| Paper       | 998                    | 100                         |
| Plastic     | 997                    | 100                         |
| **Total**   | **4,000**              | **400**                    |

---

## 🗂️ Folder Structure

```
DATASet_WasteClass/
├── ImageData-1/
│   ├── Biological/   (bio697.jpg – bio848.jpg, total 998)
│   ├── Metal/        (met697.jpg – met848.jpg, total 997)
│   ├── Paper/        (pap697.jpg – pap848.jpg, total 998)
│   └── Plastic/      (plas697.jpg – plas848.jpg, total 997)
├── ImageData-2/
│   ├── Biological/   (bio_0001.jpg – bio_0103.jpg, total ~107)
│   ├── Metal/        (met_0001.jpg – met_0100.jpg, total ~100)
│   ├── Paper/        (pap_0001.jpg – pap_0102.jpg, total ~100)
│   └── Plastic/      (pla_0001.jpg – pla_0100.jpg, total ~100)
├── LICENSE
└── README.md
```

> **Note:** The `ImageData‑2` subfolders contain **approximately** the numbers shown; exact counts may vary slightly.

---

## 🏷️ Naming Convention

| Dataset      | Format                        | Example          |
|--------------|-------------------------------|------------------|
| ImageData‑1  | `<class_prefix><3‑digit>.jpg` | `bio697.jpg`     |
| ImageData‑2  | `<class_prefix>_<4‑digit>.jpg`| `bio_0001.jpg`   |

**Class prefixes:**
- `bio` / `bio_` – Biological
- `met` / `met_` – Metal
- `pap` / `pap_` – Paper
- `plas` / `pla_` – Plastic *(ImageData‑2 uses `pla_`)*

---

## 🔍 Usage

### Training
- Use **ImageData‑1** to train your waste classification model.  
- The dataset is balanced and large enough for deep learning tasks.

### Edge Evaluation
- Use **ImageData‑2** to benchmark your model on edge devices (e.g., Raspberry Pi).  
- This dataset reflects real‑world conditions and is ideal for evaluating latency, memory footprint, and accuracy trade‑offs.

### Example (Python with PyTorch)
```python
from torchvision.datasets import ImageFolder
import torchvision.transforms as transforms

train_dataset = ImageFolder('ImageData-1', transform=transforms.ToTensor())
test_dataset  = ImageFolder('ImageData-2', transform=transforms.ToTensor())
```

---

## 📜 License

This repository is released under the **Apache License 2.0** – see the [LICENSE](LICENSE) file for details.

**Attribution:**  
- ImageData‑1 originates from the [Kaggle Garbage Classification v2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2) dataset (original license applies).  
- ImageData‑2 is contributed under the Apache 2.0 license.

---

## 📝 Citation

If you use this dataset in your research, please cite:

```bibtex
@misc{wasteclass2024,
  author = {Saikat Das},
  title = {A Deployment and Resource Aware Edge AI Framework for Real-Time Waste
Classification with Biometric Authentication and Secure Logging},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/saikatdas47/A-Deployment-Oriented-Edge-AI-Framework-for-Real-Time-Waste-Classification}
}
```

---

## 🙏 Acknowledgements

- The Kaggle community for providing the high‑quality [Garbage Classification v2](https://www.kaggle.com/datasets/sumn2u/garbage-classification-v2) dataset.  
- All contributors who assisted in capturing and labeling the edge evaluation images.  

---

**Happy benchmarking!** 🚀
