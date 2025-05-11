# ✂️ Étape 2 : Nettoyage des lectures – Cutadapt

## 🎯 Objectif pédagogique

Supprimer les adaptateurs et les bases de mauvaise qualité présentes aux extrémités des séquences issues du séquençage, afin de garantir une analyse fiable des données.

---

## 🔗 Lien vers Galaxy Europe

👉 [https://usegalaxy.eu](https://usegalaxy.eu)

---

## 📁 Données utilisées

Nous allons réutiliser le fichier FASTQ brut inspecté précédemment -(https://drive.google.com/file/d/1NPX9jtgKhjIv0eH_4zcPl4CbL9qjfwx7/view?usp=sharing).

---

## 🧾 Pourquoi utiliser Cutadapt ?

Lors de la préparation des librairies, des séquences adaptatrices sont être ajoutées aux extrémités des fragments d’ADN. Si elles ne sont pas retirées, elles peuvent :

- Interférer avec l'alignement
- Produire des faux variants
- Réduire la qualité globale de l’analyse

Cutadapt permet de :

- Supprimer les séquences adaptatrices
- Supprimer les bases de faible qualité (par exemple, Q < 20)
- Ne garder que les lectures de longueur minimale souhaitée

---

## 🧬 Séquences adaptateurs utilisées (KAPA / Illumina TruSeq)

- **Adaptateur Read 1 (R1)** :  
  `AGATCGGAAGAGCACACGTCTGAACTCCAGTCAC`

---

## ⚙️ Étapes à suivre dans Galaxy

1. Tapez **Cutadapt** dans la barre de recherche
2. Sélectionnez l’outil `Cutadapt: Remove adapter sequences from FASTQ files`

---

### 📌 Paramètres recommandés (mode single-end) :

- **Single-end or paired-end reads?** → `Single-end`
- **FASTQ file** → sélectionnez votre fichier `.fastq.gz`
- **3' adapter sequence** →  
  `AGATCGGAAGAGCACACGTCTGAACTCCAGTCAC`
- **Minimum length** → `20` *(pour filtrer les fragments trop courts)*
- **Discard untrimmed reads?** → `No`
- **Trim low-quality bases** → `Yes`
  - **Quality cutoff** → `20`

Cliquez sur **Execute**

---


## 📊 Résultats obtenus

Cutadapt génère un fichier FASTQ nettoyé, nommé :
- [➡️ Voir et télécharger le fichier FASTQ]-(https://drive.google.com/file/d/1XRhf7ZlI0cfmMygdioahg-zXP1Stc7kd/view?usp=drive_link).
- [➡️ Voir et télécharger le rapport HTML](reports/Cutadapt%20on%20data%2029_%20Read%201%20Output%20fastqc.html) 

---


## 💡 Bonnes pratiques

- Toujours vérifier les résultats avec **FastQC** après le trimming
- S'assurer que la longueur des séquences est suffisante après nettoyage
- Ne pas trop couper → préserver la couverture



