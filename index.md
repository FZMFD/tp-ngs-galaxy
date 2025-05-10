# 🧬 TP : Analyse de Données NGS (Exome) avec Galaxy

## 🌟 Introduction

La génomique moderne a profondément transformé notre compréhension du vivant, notamment grâce aux technologies de séquençage de nouvelle génération (NGS). Ces technologies permettent de décoder rapidement et efficacement le génome humain, ouvrant la voie à des avancées majeures en recherche biomédicale, en diagnostic et en médecine personnalisée.

Cependant, la richesse de ces données brutes ne peut être exploitée qu’à travers une analyse bioinformatique rigoureuse et reproductible. C’est là que la plateforme **Galaxy** entre en jeu : une interface web libre, conviviale et puissante, qui permet de réaliser toutes les étapes de l’analyse NGS sans avoir à écrire une seule ligne de code.

## 🎯 Objectifs du TP

Ce TP vise à vous initier, de manière interactive et progressive, au pipeline standard d’analyse NGS pour l’étude de l’exome. Vous apprendrez à :

- Explorer la qualité des données de séquençage avec **FastQC**
- Nettoyer les lectures en supprimant les artéfacts techniques (adaptateurs, bases de faible qualité)
- Aligner les séquences sur le génome humain de référence (**GRCh38**) à l’aide de **BWA-MEM**
- Manipuler les fichiers BAM avec **SAMtools**
- Identifier les variants (SNPs et indels) à l’aide de **GATK HaplotypeCaller**
- Annoter les variants avec **VEP** afin d’évaluer leur impact biologique
- Visualiser les résultats dans **IGV** et interpréter les mutations identifiées

## 🧪 Contexte scientifique

Le jeu de données utilisé dans ce TP est un exome humain réel d´une patiente atteinte de cancer du sein. Le but est de simuler l’analyse d’un échantillon d’un patient atteint d’une maladie génétique suspectée, et d’identifier les mutations potentielles pouvant en être responsables.

Cet exercice vous permettra de comprendre les bases de l’analyse bioinformatique, tout en vous sensibilisant aux enjeux de la génomique médicale moderne.

## 🗺️ Déroulement du TP

Ce TP se décompose en plusieurs étapes pratiques, chacune hébergée dans un fichier séparé :

1. [Contrôle qualité - FastQC](./tuto-fastqc.md)
2. [Nettoyage des lectures - Cutadapt](./tuto-cutadapt.md)
3. [Alignement - BWA-MEM](./tuto-bwa.md)
4. [Tri et indexation - SAMtools](./tuto-samtools.md)
5. [Appel de variants - GATK](./tuto-gatk.md)
6. [Annotation des variants - VEP](./tuto-vep.md)
7. [Validation et interprétation - IGV](./validation.md)

## 🔗 Liens utiles

- 🌐 [Galaxy Europe](https://usegalaxy.eu)
- Pour toutes questions contactez-moi sur: fatimazohra.moufid@usmba.ac.ma
