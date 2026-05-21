# 🫁 Détection de la Pneumonie à partir de Radiographies Thoraciques

<div align="center">

<img src="https://img.shields.io/badge/Deep%20Learning-CNN-blue?style=for-the-badge" />
<img src="https://img.shields.io/badge/Python-PyTorch-yellow?style=for-the-badge" />
<img src="https://img.shields.io/badge/Medical%20AI-Computer%20Vision-red?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />

<br><br>

### 🧠 Projet de Deep Learning appliqué à l’imagerie médicale

Développement d’un modèle **CNN** capable de détecter automatiquement la **pneumonie** à partir de radiographies thoraciques.

</div>

---

# 📌 Aperçu du projet

La pneumonie est une infection pulmonaire pouvant devenir grave si elle n’est pas détectée rapidement.

L’objectif de ce projet est de développer un système d’intelligence artificielle capable de :

✅ analyser automatiquement des radiographies thoraciques  
✅ détecter les signes de pneumonie  
✅ assister les professionnels de santé dans le diagnostic  

---

# 🖼️ Classification du modèle

Le modèle réalise une **classification binaire** :

| Classe | Description |
|---|---|
| 🟢 NORMAL | Poumons sans anomalies |
| 🔴 PNEUMONIA | Présence d’une infection pulmonaire |

---

# ⚙️ Stack Technique

<div align="center">

| Deep Learning | Data Processing | Visualisation |
|---|---|---|
| PyTorch | NumPy | Matplotlib |
| CNN | Pandas | Seaborn |
| Torchvision | Scikit-Learn | Confusion Matrix |

</div>

---

# 🧪 Prétraitement des images

Afin d’optimiser les performances du modèle, plusieurs techniques de preprocessing ont été appliquées :

## 🔹 Redimensionnement
- Conversion des images en `128x128`
- Optimisation des opérations de convolution

## 🔹 Normalisation
- Conversion en tenseurs PyTorch
- Standardisation des données

## 🔹 Data Augmentation
- `RandomHorizontalFlip`
- Amélioration de la robustesse du modèle

---

# ⚖️ Gestion du déséquilibre des classes

Le dataset contient beaucoup plus d’images **PNEUMONIA** que **NORMAL**.

👉 Pour éviter un biais du modèle :

```python
WeightedRandomSampler()
