#  Sign Language Recognition — ASL Letters A–E

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/ScikitLearn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-00897B?style=for-the-badge&logo=google&logoColor=white)

##  Description
Système de reconnaissance de la langue des signes américaine (ASL) en temps réel,
capable de détecter et classifier les lettres A à E à partir d'une webcam.
Développé dans le cadre d'un Mini-Projet académique à la Faculté des Sciences
de Bizerte, Université de Carthage (CI1 - 2025).

##  Motivation
Des millions de personnes sourdes ou muettes font face à des barrières de
communication au quotidien. Ce projet utilise la Computer Vision et l'IA
pour rendre la communication plus accessible et inclusive.

##  Fonctionnalités
-  Détection de la main en temps réel via MediaPipe
-  Extraction de 21 landmarks 3D (63 features)
-  Classification via un réseau de neurones MLP
-  Affichage de la lettre reconnue à l'écran
-  Retour vocal — le système prononce la lettre détectée

##  Dataset
- **Source** : [ASL Alphabet — Kaggle](https://www.kaggle.com/datasets/grassknoted/asl-alphabet)
- **Classes** : 5 lettres (A, B, C, D, E)
- **Prétraitement** :
  - 500 images aléatoires par lettre
  - Redimensionnement à 64×64 pixels
  - Conversion BGR → RGB
  - Gaussian Blur pour réduire le bruit
  - Normalisation des pixels entre 0 et 1

##  Pipeline du projet

###  Prétraitement des images
- Chargement et redimensionnement
- Filtrage et normalisation
- Extraction des landmarks via MediaPipe

###  Extraction de features
- MediaPipe Hand Landmarks : 21 points × 3 coordonnées = **63 features**

###  Modèle & Entraînement
- **Modèle** : MLP (Multilayer Perceptron) — scikit-learn MLPClassifier
- **Input** : 63 coordonnées des landmarks
- **Output** : Lettre prédite (A–E)
- **Dataset custom** : images capturées + dataset public ASL

###  Évaluation
- Accuracy, Precision, Recall, F1-Score
- Matrice de confusion

##  Résultats

| Lettre | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| A | 0.96 | 1.00 | 0.98 |
| B | 1.00 | 0.91 | 0.95 |
| C | 1.00 | 1.00 | 1.00 |
| D | 1.00 | 0.96 | 0.98 |
| E | 0.94 | 1.00 | 0.97 |

 **Accuracy globale : 98%**

##  Structure du projet
projetImgPros/
├── Projet_img_procLVAH.ipynb   # Notebook principal
├── asl_mlp_model.pkl           # Modèle MLP sauvegardé
├── label_encoder.pkl           # Label encoder sauvegardé
├── A.PNG                       # Exemple lettre A
├── B.png                       # Exemple lettre B
├── C.PNG                       # Exemple lettre C
├── D.PNG                       # Exemple lettre D
├── E.PNG                       # Exemple lettre E
└── README.md

##  Comment lancer le projet
1. Cloner le repository
```bash
git clone https://github.com/hibatallah-hadjkacem/sign-language-recognition
```
2. Installer les dépendances
```bash
pip install opencv-python mediapipe scikit-learn numpy matplotlib pyttsx3
```
3. Ouvrir le notebook principal
```bash
jupyter notebook Projet_img_procLVAH.ipynb
```

##  Perspectives futures
- Étendre à toutes les 26 lettres de l'alphabet ASL
- Ajouter des signes dynamiques (HELLO, THANK YOU...)
- Créer une application mobile ou PC complète
- Ajouter la prédiction de phrases entières

##  Réalisé par
- Hibat Allah Hadj Kacem
- Amal Ktiti

##  Contexte académique
- **Établissement** : Faculté des Sciences de Bizerte, Université de Carthage
- **Classe** : CI1
- **Année** : 2025
