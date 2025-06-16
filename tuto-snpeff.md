# 🧬 Étape 6 : Annotation des variants – SnpEff

## 🎯 Objectif pédagogique

Annoter les variants (SNPs et indels) identifiés à l’étape précédente afin de prédire leur impact sur les gènes (ex : mutation silencieuse, faux-sens, non-sens).

---

## 🔗 Lien vers Galaxy Europe

👉 [https://usegalaxy.eu](https://usegalaxy.eu)

---

## 📁 Données requises

- Fichier VCF contenant les variants détectés (ex : `variants_freebayes.vcf` ou `variants_gatk.vcf`)

---

## 🧰 Outil utilisé

**SnpEff**  
C’est un annotateur de variants qui utilise une base de données génomique pour prédire :
- L’effet d’un variant sur les exons, introns, UTRs
- Le type d’impact : faible, modéré ou élevé
- Le nom du gène et la protéine affectée

---

## ⚙️ Étapes dans Galaxy

1. Recherche `SnpEff` dans Galaxy
2. Sélectionne : `SnpEff eff: Variant effect and annotation (Galaxy Version X.X)`

### 📌 Paramètres à configurer

- **Input VCF file** → ton fichier `.vcf` (issu de FreeBayes ou GATK)
- **Genome source** → `Pre-built database`
- **Genome version** → `GRCh38.86` (ou autre version selon ton fichier de référence)
- **Output format** → `VCF` (par défaut)

👉 Clique sur **Execute**

---

## 📄 Résultat obtenu

SnpEff produit un nouveau fichier `.vcf` **annoté** :

- Il contient les mêmes variants que le fichier d’origine
- Enrichi avec des colonnes **INFO** détaillant l’impact prédictif des mutations

### Exemple de champ INFO :

```vcf
ANN=C|missense_variant|MODERATE|BRCA1|ENSG00000012048|...|p.Val600Glu|...
