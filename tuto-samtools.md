# 🧪 Étape 4 : Gestion du fichier BAM avec SAMtools

## 🎯 Objectif pédagogique

Préparer le fichier BAM obtenu après l'alignement pour les étapes suivantes (appel de variants, visualisation IGV) en effectuant :

- Le tri des lectures alignées
- L’indexation du fichier BAM
- L’évaluation des statistiques d’alignement

---

## 🔗 Galaxy Europe

➡️ [https://usegalaxy.eu](https://usegalaxy.eu)

---

## 📁 Données d’entrée

- Le fichier BAM généré par **BWA-MEM** ou **HISAT2** à l’étape précédente

---

## 🧰 Outils utilisés

- **SAMtools sort** : tri du fichier BAM par position génomique
- **SAMtools index** : création d’un index `.bai` pour la visualisation
- **SAMtools flagstat** : statistiques générales d’alignement

---

## 🔃 Étape 1 : Trier le fichier BAM

1. Dans Galaxy, tapez `samtools sort`
2. Sélectionnez l’outil : `SAMtools: Sort alignment file`
3. Paramètres :
   - **Input BAM file** → sélectionne le fichier BAM de BWA
   - **Sort by** → `coordinate`
4. Clique sur **Execute**

Résultat : un fichier `sorted.bam`

---

## 📌 Étape 2 : Indexer le fichier trié

1. Tapez `samtools index`
2. Sélectionne `SAMtools: Index alignment file`
3. **Input BAM file** → le fichier `sorted.bam`
4. Clique sur **Execute`

Résultat : un fichier `sorted.bam.bai`  
(nécessaire pour IGV ou GATK)

---

## 📊 Étape 3 : Obtenir les statistiques d’alignement

1. Tapez `samtools flagstat`
2. Choisis l’outil `SAMtools: flagstat`
3. Sélectionne le même fichier `sorted.bam`
4. Clique sur **Execute**

Résultat : un fichier texte avec les infos suivantes :
- Nombre total de lectures
- Nombre et pourcentage de lectures mappées
- Lectures correctement appariées (si paired-end)

---

## ✅ Exemple d’interprétation (extrait de flagstat)


📌 Un bon alignement présente généralement :
- >95 % de lectures mappées
- Un faible taux de duplication
- Peu de lectures non appariées (en paired-end)

---

## 💡 Bonnes pratiques

- Toujours indexer le fichier BAM avant de l’utiliser avec GATK, IGV ou VEP
- Le fichier `.bai` doit avoir exactement le même nom que le `.bam` trié
- Les statistiques flagstat permettent de détecter des erreurs précoces (fichier vide, mauvais alignement, etc.)

---

## 📥 Résultats attendus

- `sorted.bam`
- `sorted.bam.bai`
- `flagstat report.txt`

---


