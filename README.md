# Automatic Pill Recognition System with Deep Learning and Hybrid Classifiers

[cite_start]This project evaluates standalone deep learning architectures (MobileNetV2, ResNet50, InceptionV3) and hybrid frameworks (CNN+SVM, CNN+kNN) against a real-world dataset of ten medication classes[cite: 1755, 1924].

## 📊 Key Findings
* [cite_start]**ResNet50** emerged as the unequivocally superior architecture, achieving a dominant benchmark accuracy of **90.18%** and a Macro-AUC of **0.9937**[cite: 1926, 2008, 2111]. [cite_start]It successfully resolved complex spatial hierarchies and severe visual ambiguities[cite: 2009, 2017].
* [cite_start]Lightweight backbones (**MobileNetV2** and **InceptionV3**) hit a structural performance ceiling below **80%** due to extreme inter-class visual similarities (frequently confusing visually analogous classes like Bioflu and Neozep)[cite: 1927, 1928, 2011].
* [cite_start]**Hybrid Frameworks (CNN+SVM & CNN+kNN)** failed to meaningfully surpass the lightweight baselines[cite: 1929, 2012, 2013]. [cite_start]Although the margin-maximizing nature of SVM provided high numerical stability in regression metrics ($RMSE = 1.0915$) [cite: 2148, 2151][cite_start], the classifiers were ultimately bottlenecked because the PCA-reduced embeddings lacked fine-grained morphological details[cite: 1930, 3111].

## ⚙️ Software Stack & Algorithmic Determinism
[cite_start]To eliminate experimental variance and ensure exact reproducibility, a global master seed (`SEED=42`) was strictly integrated across all computational levels[cite: 1891, 1896, 1897]:
* [cite_start]**OS/Hardware:** Linux (Kernel 6.6.113+) & NVIDIA Tesla T4 GPU [cite: 1893]
* [cite_start]**Language:** Python 3.12.13 [cite: 1894]
* [cite_start]**Core Libraries:** PyTorch 2.10.0 & Torchvision 0.25.0 [cite: 1895]
* [cite_start]**ML/Data:** Scikit-learn 1.6.1 & NumPy 2.0.2 [cite: 1895]

## 📂 Dataset Integrity & Validation Protocol
* [cite_start]**Total Scale:** 10,000 high-resolution digital pill images distributed evenly across 10 distinct pharmaceutical categories (1,000 samples per class)[cite: 1794, 1795].
* [cite_start]**Target Classes:** Alaxan, Bactidol, Bioflu, Biogesic, DayZinc, Decolgen, Fish Oil, Kremil S, Medicol, and Neozep[cite: 1794].
* [cite_start]**Real-World Noise:** Unlike standard laboratory datasets, images feature severe lighting inconsistencies, harsh shadowing, specular reflections, varying camera perspectives, and complex, cluttered household backgrounds[cite: 1796, 1797, 1799, 1800].
* [cite_start]**Zero-Leakage Validation:** Prior to optimization, the entire corpus was subjected to a rigorous **MD5 hash validation protocol** and Cross-Fold Hash Intersection Check, mathematically confirming the absolute absence of duplicate groups or data leakage across splits[cite: 1877, 1880, 1881, 1883].

---
[cite_start]*Developed as part of the "Drug Vision" project at Balikesir University[cite: 1753, 1816].*
