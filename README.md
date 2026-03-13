# Vision-LLM pour la Reconnaissance des Émotions Faciales Composées (FER-CE)

Projet d’intelligence artificielle explorant l’utilisation de **Vision Transformers** et de **Vision-Large Language Models (Vision-LLM)** pour la **reconnaissance des émotions faciales composées** à partir du dataset **RAF-CE**.

L’objectif du projet est d’étudier comment les modèles modernes de vision et les modèles multimodaux peuvent **reconnaître et interpréter les expressions émotionnelles complexes** présentes sur les visages humains.

---

# Présentation du projet

La **reconnaissance des émotions faciales (Facial Emotion Recognition – FER)** est un domaine important de la vision par ordinateur avec de nombreuses applications :

- interaction humain–machine  
- robotique sociale  
- analyse comportementale  
- sécurité  
- accompagnement en santé mentale  

La plupart des systèmes FER classiques se concentrent sur les **émotions de base** (joie, tristesse, colère, peur, surprise, dégoût).

Cependant, dans les interactions réelles, les expressions humaines sont souvent **composées**, c’est-à-dire qu’elles résultent de la combinaison de plusieurs émotions.

Exemples d’émotions composées :

- happily surprised  
- sadly angry  
- fearfully disgusted  

Ces émotions impliquent plusieurs **Action Units (AUs)** du système FACS et sont donc plus difficiles à reconnaître.

Ce projet explore l’utilisation de **Vision-LLM**, capables de combiner **analyse visuelle et raisonnement linguistique**, afin d’aller au-delà de la simple classification.

---

# Objectifs

Les principaux objectifs du projet sont :

- Construire une **baseline de reconnaissance d’émotions faciales** basée uniquement sur la vision.
- Explorer l’utilisation de **Vision-Large Language Models** pour l’analyse multimodale.
- Comparer différentes approches pour la reconnaissance des émotions composées.
- Étudier l’interprétabilité des modèles à l’aide de techniques **Explainable AI (XAI)**.
- Relier les régions du visage importantes avec les **Action Units et les explications textuelles**.

---

# Dataset

Le projet utilise le dataset **RAF-CE (Real-world Affective Faces – Compound Emotions)**.

Caractéristiques :

- images de visages provenant de situations réelles  
- **14 classes d’émotions composées**  
- annotations des **Action Units (AUs)**  
- visages pré-alignés  

Le dataset présente un **déséquilibre important entre les classes**, ce qui rend la tâche de classification plus complexe.

---

# Pipeline du projet

Le projet est structuré en plusieurs étapes principales.

## 1. Préparation des données

Cette étape consiste à préparer le dataset RAF-CE afin qu’il soit exploitable par les modèles.

Principales tâches :

- chargement des images et annotations  
- fusion des différents fichiers d’annotations  
- visualisation d’exemples par classe  
- analyse du déséquilibre des classes  
- conversion du dataset au format **Hugging Face Datasets**

Le dataset est ensuite organisé en trois partitions :

- train  
- validation  
- test

---

## 2. Baseline Vision-Only

Une baseline classique est construite avec un **Vision Transformer (ViT)**.

Cette approche utilise uniquement les informations visuelles de l’image.

Principales étapes :

- prétraitement et augmentation des images  
- normalisation et transformation des données  
- adaptation de la tête de classification pour les 14 classes  
- gestion du déséquilibre des classes via des **class weights**

Cette baseline sert de **référence pour comparer les approches multimodales**.

---

## 3. Vision-LLM

La seconde approche explore les **Vision-Large Language Models**, qui combinent :

- un encodeur visuel
- un modèle de langage

Ces modèles peuvent :

- analyser une image
- décrire les indices faciaux visibles
- proposer une interprétation émotionnelle

Le projet utilise **BLIP-2**, testé dans deux configurations :

- analyse **zero-shot** sans entraînement supplémentaire  
- **fine-tuning léger avec LoRA**

L’objectif est d’évaluer la capacité de ces modèles à **relier les indices visuels à une interprétation linguistique des émotions**.

---

## 4. Comparaison des approches

Les différentes approches implémentées sont comparées selon plusieurs aspects :

- capacité de classification  
- robustesse face au déséquilibre des classes  
- capacité d’interprétation  
- complexité d’entraînement

Cette comparaison permet d’identifier les forces et les limites de chaque type de modèle.

---

## 5. Interprétabilité et Explainable AI

Afin de comprendre les décisions du modèle, des techniques d’**Explainable AI (XAI)** sont utilisées.

Le projet implémente notamment **Grad-CAM** afin de visualiser :

- les régions du visage les plus importantes pour la prédiction
- la correspondance avec les **Action Units du FACS**

Les zones observées incluent par exemple :

- les sourcils  
- les yeux  
- la bouche  
- les joues  

Cette analyse permet d’évaluer si le modèle se concentre sur des **indices faciaux pertinents**.

---

# Technologies utilisées

- Python  
- PyTorch  
- Hugging Face Transformers  
- Vision Transformers (ViT)  
- BLIP-2 Vision-Language Model  
- LoRA Fine-Tuning  
- Grad-CAM  
- Google Colab  

---


