# 🔍 Étape 7 : Validation et interprétation – IGV

## 🎯 Objectif pédagogique

Visualiser les variants détectés (SNPs, indels) dans leur **contexte génomique** afin de :
- Vérifier leur position réelle
- Valider leur présence visuellement
- Détecter d’éventuels artefacts (alignement ambigu, faible couverture, erreurs techniques)

---

## 🔧 Outil utilisé

**[IGV – Integrative Genomics Viewer](https://software.broadinstitute.org/software/igv/)**  
Un visualiseur interactif de fichiers BAM et VCF.

---

## 📁 Données requises

- Fichier BAM trié et indexé (`sorted.bam` + `sorted.bam.bai`)
- Fichier VCF annoté (`variants_annotated.vcf`)
- Fichier FASTA du génome de référence (`hg38.fa`) + index `.fai`

---

## 🖥️ Installation d’IGV

1. Va sur : [https://software.broadinstitute.org/software/igv/download](https://software.broadinstitute.org/software/igv/download)
2. Télécharge la version correspondant à ton système (Windows, macOS, Linux)
3. Lance IGV

---

## ⚙️ Chargement des fichiers dans IGV

1. Sélectionne le **génome** dans IGV (ex. : `Human (hg38)` ou `hg19`)
2. Clique sur **File > Load from File...**
   - Charge d'abord le fichier `sorted.bam` (Galaxy > Download > .bam)
   - Puis le fichier `.bai` (index)
   - Ensuite charge le fichier `.vcf`
3. Va dans le menu **"Go to"** → entre une position (ex. : `chr7:140453100-140453200`) pour voir un variant

---

## 🧪 Interprétation d’un variant

Regarde la position du variant dans la piste VCF :

- ✔️ Couverture suffisante (min 10x)
- ✔️ L’allele alternatif est visible dans plusieurs lectures ?
- ❌ Présence d’erreurs systématiques ?
- ❌ Variant supporté par une seule lecture ou en fin de lecture ?

---

### 🖼️ Exemple de visualisation (IGV)

![Exemple IGV](images/igv-variant.png)

> *Exemple : SNP confirmé par plusieurs lectures sur un gène codant. Couverture homogène, pas d’artefact visible.*

---

## 📝 Bonnes pratiques

| Critère | À vérifier dans IGV |
|--------|---------------------|
| Couverture | >10 lectures |
| Qualité de lecture | Pas d’erreurs massives, bons scores |
| Position | Le variant tombe dans un exon connu ? |
| Validation | Le variant est-il hétérozygote (0/1) ou homozygote (1/1) ? |

---

## ❓ À faire dans le TP

- Choisissez **1 variant intéressant**
- Localisez-le dans IGV
- Prenez une **capture d’écran annotée** (avec flèche, position, gène)
- Ajoutez une **brève interprétation** :
  - Gène impliqué ?
  - Variant potentiel pathogène ?
  - Justification ?

---
