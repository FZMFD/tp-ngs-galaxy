# 🧪 Étape 1 : Contrôle Qualité des Lectures – FastQC

## 🎯 Objectif pédagogique

Avant toute analyse bioinformatique, il est crucial d'évaluer la qualité des données de séquençage brutes (au format FASTQ). Cette étape permet d'identifier les problèmes éventuels (biais, adaptateurs, séquences de faible qualité) et de décider des étapes de nettoyage nécessaires.

---

## 🔗 Lien vers Galaxy Europe

Nous utiliserons l'instance Galaxy Europe, accessible sans inscription :  
👉 [https://usegalaxy.eu](https://usegalaxy.eu)

---

## 📁 Données utilisées

Pour ce TP, nous allons analyser un fichier FASTQ d'exome humain issu d’un projet SRA :

- **Identifiant SRA** : [SRR123456](https://www.ncbi.nlm.nih.gov/sra/?term=SRR123456)
- Vous pouvez utiliser un fichier d’exemple comme celui-ci (compress\u00e9) :  
  👉 `https://ftp.sra.ebi.ac.uk/vol1/fastq/SRR123/006/SRR1234566/SRR1234566_1.fastq.gz`

Dans Galaxy :
1. Cliquez sur **Upload Data** (icône en haut à gauche)
2. Collez l’URL dans l’onglet **Paste/Fetch Data**
3. Cliquez sur **Start** puis **Close**

---

## ⚙️ Utilisation de l'outil FastQC

### 🔍 Description
FastQC est un outil d’analyse rapide de la qualité des fichiers FASTQ. Il fournit des graphiques et résumés pour détecter :
- Les bases de faible qualité
- Les adaptateurs résiduels
- Les biais GC
- Les doublons

### 📌 Étapes à suivre sur Galaxy :

1. Dans la barre de recherche Galaxy, tapez **FastQC**
2. Cliquez sur l’outil `FastQC: Read Quality reports`
3. **Paramètre à configurer** :
   - `Short read data from your current history` → sélectionnez votre fichier `.fastq.gz`
   - Laissez les autres paramètres par défaut
4. Cliquez sur **Execute**

---

## 📊 Résultats obtenus

FastQC génère deux fichiers :
- **`fastqc.html`** → rapport interactif (visualisation dans Galaxy)
- **`fastqc_data.txt`** → données brutes du rapport

### ✅ Points à observer dans le rapport :

| Rubrique | À vérifier | Interprétation |
|----------|------------|----------------|
| Per base sequence quality | Score moyen par base > 20 | Bonne qualité |
| Adapter Content | Présence d’adaptateurs ? | Si oui → trim requis |
| Per base GC content | Distribution symétrique | OK si pas trop biaisée |
| Sequence Length Distribution | Uniforme ou variable ? | Peut indiquer des artefacts |
