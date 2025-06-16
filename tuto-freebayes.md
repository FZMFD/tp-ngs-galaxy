# 🧬 Étape 5 : Appel de variants – FreeBayes

## 🎯 Objectif pédagogique

Utiliser l'outil FreeBayes pour détecter les variants (SNPs et indels) à partir d’un fichier BAM aligné. 
---

## 🔗 Galaxy Europe

👉 [https://usegalaxy.eu](https://usegalaxy.eu)

---

## 📁 Données requises

- Fichier BAM trié et indexé (`sorted.bam` et `sorted.bam.bai`)
- Fichier FASTA du génome de référence (ex. : `hg38.fa`)

---

## 🧰 Outil utilisé

**FreeBayes**  
Détecteur bayésien de variants germinaux (SNPs, indels, multi-alleliques)

---

## ⚙️ Étapes dans Galaxy

### 🔍 Lancer FreeBayes

1. Recherche `FreeBayes` dans Galaxy
2. Sélectionne : `FreeBayes: Bayesian genetic variant detector`

### 📌 Paramètres à configurer

- **Choose the source for the reference genome** → `From history`
- **FASTA Reference Genome** → ton fichier `hg38.fa`
- **BAM alignment file** → ton fichier `sorted.bam`
- **Output format** → `VCF`
- Laisser les autres options par défaut pour une analyse simple

👉 Clique sur **Execute**

---

## 📄 Résultat obtenu

Un fichier `.vcf` contenant tous les variants détectés par FreeBayes.
- [➡️ Voir et télécharger le fichier VCF]-(https://drive.google.com/file/d/1zSprINEeNZH4Y3DdFdPyZ4FT4bf8eLOV/view?usp=drive_link).


### Exemple de lignes VCF :

```vcf
#CHROM  POS     ID      REF     ALT     QUAL    FILTER  INFO
chr7    140453136       .       A       G       225.5    .       DP=42;AF=0.48
chr3    37098205        .       C       T       190.7    .       DP=36;AF=0.51
